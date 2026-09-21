# swapps-deployment-status

Live deployment status for apps managed by [`swapps-deployment`](https://github.com/slaclab/swapps-deployment).

This repo holds no code or secrets — just small, public JSON status files updated
automatically by `swapps-deployment`'s deploy workflow after each successful
deploy. Each file records only the app name, environment, and deployed image
tag; nothing sensitive.

The repo is public (and separate from `swapps-deployment`, which is private)
so status badges can be read by [shields.io](https://shields.io) without
authentication.

## Status files

Each file lives at `status/<app>-<environment>.json` and follows the
[shields.io endpoint badge schema](https://shields.io/badges/endpoint-badge):

```json
{
  "schemaVersion": 1,
  "label": "<app> <environment>",
  "message": "sha-abc1234",
  "color": "blue"
}
```

## Adding a badge

```markdown
![elog-plus dev](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/slaclab/swapps-deployment-status/main/status/elog-plus-dev.json)
```
