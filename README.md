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

## Set up with Claude Code
Paste this prompt into Claude Code to install ccstatusline and apply this config:

```text
Set up my Claude Code status line with ccstatusline (https://github.com/sirmalloc/ccstatusline) using the config from https://github.com/adithya-s-edstem/ccstatusline-config. Steps:

1. Install ccstatusline globally: npm i -g ccstatusline@latest (use bun if npm isn't available). Confirm the `ccstatusline` command is on PATH.
2. If ~/.config/ccstatusline/settings.json exists, back it up to settings.json.bak-<today's date> in the same folder before changing anything.
3. Download https://raw.githubusercontent.com/adithya-s-edstem/ccstatusline-config/main/ccstatusline-config.json and save it as ~/.config/ccstatusline/settings.json (create the folder if needed; on Windows this is %USERPROFILE%\.config\ccstatusline\settings.json).
4. In ~/.claude/settings.json, set "statusLine" to {"type": "command", "command": "ccstatusline", "padding": 0}. Keep every other setting as is, and show me the old statusLine value if one existed.
5. Verify: pipe sample input into it, e.g. echo '{"model":{"display_name":"Opus"},"cwd":"."}' | ccstatusline, and show me the output. It should print git, model, session usage and weekly usage lines.
6. Tell me where the backup is and that the new status line appears on the next refresh.
```

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
