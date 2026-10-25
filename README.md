# ccstatusline config

My [ccstatusline](https://github.com/sirmalloc/ccstatusline) setup for the Claude Code status line.

## Layout
```
 ⎇ main / (+0,-0) / (no PR)
 Model: Opus 5.5 / [context bar]
 Session: [░░░░░░░░░░░░░░░░] 2.0% / Reset: 2h 10m
 Weekly: [░░░░░░░░░░░░░░░░] 0.0% / Weekly Reset: 5d 8hr 30m
```

| Line | Widgets | Colors |
|---|---|---|
| 1 | git branch, git changes, PR review | magenta, yellow, cyan |
| 2 | model, context bar | white, green |
| 3 | session usage, 5-hour reset timer | blue, red |
| 4 | weekly usage, weekly reset timer | blue, red |

Usage meters share blue and reset timers share red.

## Install
Launch the TUI and choose **Pinned global install**. This installs ccstatusline globally and writes the status line command to Claude Code's settings:
```bash
npx -y ccstatusline@latest
```

This adds the following to `~/.claude/settings.json`:
```json
"statusLine": {
  "type": "command",
  "command": "ccstatusline",
  "padding": 0
}
```

## Restore this config
Copy the config to where ccstatusline reads it:
```bash
mkdir -p ~/.config/ccstatusline
cp ccstatusline-config.json ~/.config/ccstatusline/settings.json
```
On Windows the path is `%USERPROFILE%\.config\ccstatusline\settings.json`.

## Save changes back to the repo
After editing in the TUI (`ccstatusline`), copy the live config back here so the repo stays current:
```bash
cp ~/.config/ccstatusline/settings.json ccstatusline-config.json
```

## Update
```bash
npm i -g ccstatusline@latest
```
Older configs are migrated automatically when loaded. Save the config back to the repo afterwards so it records the new schema version.
