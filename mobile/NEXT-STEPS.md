## GitHub publication completed — 18 October 2026

- Pushed current app source to main: 114314a942d8a0ea7ed4666611a53869d37da29f.
- Published release v1.2.7: Android 1.2.3 (build 8), iOS 1.2.7 (build 12).
- GitHub Android build 39126428365 and iOS build/archive 39126428403 passed.
- Clean local Android unit tests, release lint, signed APK/AAB build passed; signature matches previous release.
- New release files and store preparation package saved in dist/.
- iOS archive downloaded from successful CI, version checked; unsigned and requires Apple team signing.
- Personal Xcode settings remain local in project.pbxproj; this file's remaining diff is intentional. NEXT-STEPS.md remains local. No private signing material was published.
- No device installation or interactive gameplay test during this publication task. Website code was not changed.

## Play keyboard update — 18 October 2026, iOS 1.2.7 (build 12)

- Extended the isolated-world native focus request to the active gameplay input as well as the copy-answer field. Handles Play, Resume and return from copying; avoids pre-game, pause and game-over screens and repeated focus within one input session.
- Signed build passed. DOM transition checks passed (Play/copy/return/Resume, value and selection preserved, no repeated focus, trusted origins only).
- Android code already schedules focus on entering FREE_FALL; no Android phone connected for real-device verification, so Android was not changed.
- Owner check after installation: press Play with software keyboard closed; keyboard should open automatically. Repeat after a missed asteroid and after Pause/Resume. No interactive device test performed in this task.

## Keyboard update installed — 18 October 2026, iOS 1.2.6 (build 11)

- Added isolated-world copy-answer observation and native evaluateJavaScript focus to open the software keyboard after a missed asteroid. No website deployment or Android changes.
- Signed build succeeded; installed on the connected iPad in place and confirmed 1.2.6 / 11 with devicectl.
- DOM checks passed for matching only the copy field, one request per mounted field, repeated missed terms, disabled/stale inputs, preserving typed value and selection, and rejecting untrusted origins. This does not replace real-device keyboard testing.
- Owner test: let an asteroid fall while the on-screen keyboard is closed; the copy-answer field should focus and open the keyboard automatically. Also check the next miss and transition back to play. Do not interactively test unless requested.

## Icon update — 18 October 2026, iOS 1.2.5 (build 10)

- Owner accepts a one-pixel Home Screen size difference and explicitly requests preservation of the original logo shape.
- iOS icon is now artwork/app-icon-ios.svg: the original large Q path and colours, uniformly scaled about the canvas centre. No nonuniform scaling or path edits. Android artwork and carousel remain unchanged.
- Signed build and in-place installation use the existing local Xcode team. Interactive game checks remain with the owner.

## Installation completed — 18 October 2026

- Installed signed iOS 1.2.4 (build 9) on the connected iPad using the existing local Xcode team; verified the installed version with devicectl. Existing app was updated in place.
- Home Screen screenshot checked with the owner's permission: both icon tiles are the same size. The visible Q in Quizlet Gravity is slightly larger (approximately 116 × 117 pixels versus 111 × 112 in the full-resolution screenshot, depending on antialiasing/clear icon appearance). They are visually close, not pixel-identical. No icon changes were made in this installation task.
- Owner still checks the latest keyboard layout in portrait/landscape and top bar/answer input visibility. The app was not launched or interactively tested during this installation.
- Build log: /tmp/quizlet-ios-install-1.2.4.log. Installed-version record: /tmp/quizlet-ipad-installed-20261018.json.

# Next iPad update — 17 October 2026

The owner disconnected the iPad to charge the Mac. They subsequently requested another code fix; that fix is prepared. Do not install or launch on a device until the owner reconnects it and asks to continue.

## Current source

- iOS 1.2.4 (build 9), commit 2a359b8; saved on this Mac and pushed to GitHub.
- Latest fix follows Android's keyboard insets: the iOS WKWebView ends at the keyboard layout guide. Game header and play area share the available height; the extra native Privacy policy / Support footer is removed. Import pages remain scrollable.
- Previous changes included: full Android-style iOS carousel with white Q; original starting screen for 0.67 seconds; larger launcher icon from quizlet-q-chip-large-gold-on-indigo-3.svg; phone layout without external keyboard, laptop layout when connected; dark safe areas; UIKit scene lifecycle.
- Android source remains 1.2.3 (build 8), including the larger icon. No Android code changed in the keyboard fix.

## Still required

- Install the latest iOS app on the iPad when requested. No update was installed by Codex during these two sessions. The last directly verified device version was 1.2.2 (build 7).
- Owner says icon size/carousel looked good, but the latest keyboard/footer change still needs installation and device checks.
- Rebuild/sign with the existing local Xcode team, then install without deleting the app or its data.
- Owner checks: portrait/landscape; on-screen keyboard open/closed; top bar and typing field visible together; missed-answer input and accents; import scrolling; external keyboard switching; complete carousel and larger icon.
- No Samsung installation unless requested.

## Build state

- Local iOS 1.2.4 generic-device build with signing disabled PASSED. Log: /tmp/quizlet-ios-build-1.2.4.log.
- The previous local iOS 1.2.3 build ultimately PASSED after a long helper startup delay. No installation followed.
- Previous GitHub iOS and Android runs for e47c7ae both passed (39053510860 and 39053510692). Check latest runs for 2a359b8 before release publication.
- Android 1.2.3 local signed release build failed because AAPT2 startup timed out; release APK/AAB packaging and publication remain pending. Retain the existing private signing key described in BUILDING.md.
- Use DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer.
- iOS derived data: ~/Library/Developer/Xcode/DerivedData/QuizletGravity-iPad. It currently contains an unsigned 1.2.4 build, so rebuild with signing before installing.
- Keep personal Xcode team settings in the working project local. Only version changes were committed; do not reset the project or publish signing material.
- Website files were not modified.
