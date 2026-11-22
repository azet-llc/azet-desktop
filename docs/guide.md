# AZET Desktop guide

AZET Desktop runs coding agents side by side, each in its own workspace, with a terminal, an editor, a
browser and review tools around them. This page is where the app's "Docs" and "Learn more" links land.

## Workspaces

<a id="worktrees"></a>
Each task gets its own workspace: a git worktree with its own branch, terminals and agents. Nothing is
stashed and no branch is juggled. Start several agents on the same task, compare what they did, and keep
the best result. New workspaces are created under `~/azet-desktop/workspaces` unless you choose another
folder in Settings.

<a id="quick-open"></a>
**Keyboard.** Jump between workspaces, open files by name and remap every shortcut in Settings → Shortcuts.

## Agents

<a id="supported"></a>
azet, Claude Code, Codex, Cursor CLI, Gemini, Copilot, OpenCode and Pi are preconfigured. An agent has to
be installed and signed in on the machine before AZET Desktop can start it; the app launches it and
shows its status.

<a id="status-hooks"></a>
**Status hooks.** To show what each agent is doing, the app adds a status hook to the agents' own settings
files in your home folder when it starts, for example `~/.claude/settings.json`, `~/.codex/hooks.json` and
`~/.gemini/settings.json`. It does this for the agents it knows, installed or not. The hook scripts are
kept in `~/.azet-desktop/azet-hooks`.

<a id="usage-tracking"></a>
**Usage.** The app shows Claude and Codex usage and when a rate limit resets, and can switch between
saved Codex accounts without signing in again. To get the numbers it reads the sign-in that Claude Code
and Codex keep on this computer and asks Anthropic and OpenAI with it.

## Terminal

<a id="terminal"></a>
A GPU-rendered terminal with splits, scrollback that survives a restart and search across the scrollback.

<a id="windows-administrator-mode"></a>
**Windows administrator mode.** On Windows, terminals can be restarted elevated from Settings → Terminal.
AZET Desktop has not been released for Windows yet.

## Editor and files

<a id="file-explorer"></a>
The Monaco editor with autosave, a file explorer and quick-open that includes hidden files. Drag a file,
or an image from Finder, into an agent's prompt.

<a id="viewers"></a>
**Viewers.** PDFs, images (with diff modes), CSV tables and Markdown with wiki links open in the app.

## Review

<a id="annotate-ai-diff"></a>
Comment on any line of a diff, collect the comments and send them back to the agent in one batch. CI
results, merge conflicts and pull requests are handled in the same view.

<a id="linear"></a>
**GitHub and Linear.** Connected GitHub and Linear work shows up under Tasks; open an item to read its
context and start a workspace from it.

## Browser

<a id="design-mode"></a>
Every workspace has its own Chromium window. In Design Mode, click an element to send its HTML, its CSS
and a cropped screenshot to the agent.

## Remote workspaces

<a id="ssh"></a>
Agents can run on another machine over SSH with the same editing, git and terminal workflow.

## Command line

<a id="overview"></a>
The app comes with a command line tool, `azet-desktop`, that agents and scripts use to drive it: create
workspaces, read terminals, take snapshots of the browser, click and fill in pages. Settings → Command
line puts it on your PATH; `azet-desktop --help` lists the commands.

## Plugins

<a id="plugins"></a>
Plugins add themes, panels, commands and language packs. Turn plugins on in Settings → Plugins and AZET
Desktop adds two catalogs: AZET's own (`orca-catalog.json` in this repository) and the community catalog.
Another catalog is added by its link. A plugin from a catalog runs only after you install it, and plugins
listed in `plugins/kill-list.json` here are blocked. To list a plugin in AZET's catalog, open a pull
request that adds its `azet-desktop plugin release-entry` output to `orca-catalog.json`.

## Mobile

<a id="mobile"></a>
<a id="android-apk"></a>
The AZET phone app is on the [App Store](https://apps.apple.com/app/id6834321894) and
[Google Play](https://play.google.com/store/apps/details?id=io.azet.agent). Pair it from Settings → Mobile
in the desktop app: scan the code on the phone, and the phone reaches this computer over your network or,
away from it, through AZET's relay.

## Feedback

<a id="feedback"></a>
Help → Send Feedback, the crash report dialog and the phone's network diagnostics open a prefilled issue
in this repository in your browser. Tokens are removed and your home folder is shortened to `~`; you read
it and post it from your own GitHub account. Screenshots and logs are saved to a folder that opens next
to it, for you to drag in.

## Privacy

<a id="telemetry"></a>
Usage statistics are sent only by builds that carry a statistics key. The builds published so far carry
none, so they send no usage statistics, whatever the switch under Settings → Privacy says. The app checks
`github.com/azet-llc/azet-desktop` for updates. Agents you start talk to their own providers under their
own terms.

## Licences

AZET Desktop includes open-source software. The licence notices ship inside the app.
