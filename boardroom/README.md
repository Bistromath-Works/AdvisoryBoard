# Boardroom

A Claude Code plugin bundling two advisory-panel skills:

- **advisory-board** — 18 personas for strategy, philosophy, creativity, persuasion, and science. Ask "ask the board," "what would [name] think," "channel [name]," or invoke a sub-panel.
- **code-team** — the people building Claude Code, plus Matt Pocock for TypeScript and engineering discipline. Ask "ask the code team," "what would [name] think," or "channel [name]."

Both skills are model-invoked: in normal conversation, describe your problem or use one of the trigger phrases and Claude will pull in the right voices. Each persona's full profile lives under that skill's `assets/personas/` folder and is loaded on demand.

## What's inside

```
boardroom/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    ├── advisory-board/
    │   ├── SKILL.md
    │   ├── references/
    │   │   ├── pairings.md
    │   │   └── sub_advisory_panels.pdf
    │   └── assets/personas/        (18 persona files)
    └── code-team/
        ├── SKILL.md
        └── assets/personas/        (8 persona files)
```

## How to install

You need Claude Code installed. Then pick one of these.

**Quickest, for trying it out.** Unzip this folder anywhere, then launch Claude Code pointed at it:

```bash
claude --plugin-dir /path/to/boardroom
```

Inside the session, run `/reload-plugins` if you make edits.

**Persistent, loads every session.** Drop the unzipped `boardroom` folder into your Claude Code skills directory (typically `~/.claude/skills/`):

```bash
cp -r boardroom ~/.claude/skills/boardroom
```

On the next session it loads automatically as `boardroom@skills-dir`, with no marketplace and no install step. To stop loading it, delete that folder.

Skills inside a plugin are namespaced, so they appear as `boardroom:advisory-board` and `boardroom:code-team`.

## Notes

- The `code-team` skill also ships two personas it does not yet reference in its panel (Linus Torvalds and Yann LeCun). They sit in `assets/personas/` ready to be wired in if you want them.
- The plugin name `boardroom` drives the namespacing. Rename the top folder and the `name` field in `plugin.json` together if you want something different.
