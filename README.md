# Quizlet Gravity Classic — no online leaderboards

Frozen source snapshot taken on 6 November 2026, before the accounts/shared-sets release.

- Website source: repository root, original commit `cc44e42`.
- Android and iOS sources: `mobile/`, original commit `114314a`, including the existing local Xcode team configuration.
- The classic game has no shared-set database, accounts or online leaderboards.
- The mobile wrappers originally loaded the live quizletgravity.com website. This source archive preserves that original configuration. To run the classic experience independently, host this archived website and point the archived wrappers to that host.
- No environment secrets or signing material are included.

See [original website notes](README-website-original.md) and [mobile build instructions](mobile/BUILDING.md).

The current accounts/leaderboards edition is maintained at https://github.com/markosaraf/quizlet-gravity.
