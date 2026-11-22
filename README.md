# AZET Desktop

Releases of AZET Desktop for Mac (Apple silicon). The app updates itself from the releases of this repository.

- Download: https://azet.io/download/desktop
- Help: hello@azet.io

This repository holds releases and the small public files the app reads:

- `agent-cli-model-requirements.json`: which agent CLI version each model needs.
- `orca-catalog.json`: AZET's official plugin catalog. To list a plugin, open a pull request that adds the `azet-desktop plugin release-entry <dir>` output to `plugins`.
- `plugins/kill-list.json`: plugins AZET blocks for safety (`pluginKey`, `reason`, optional `advisoryUrl`; raise `generatedAt` on every change).
- `whats-new/nudge.json`: the what's-new prompt campaign (`id` plus `minVersion` and/or `maxVersion`).
- Feedback, crash reports and phone diagnostics arrive as issues here, posted by the person who sends them.
