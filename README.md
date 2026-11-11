# google-play-publishing-with-ai

An agent-agnostic skill and a 24-page English manual for publishing an Android app on Google Play with AI assistance: developer account and legal forms, closed testing (including paid tester services and $0 sales), the 14-day / 12-tester rule, applying for production, launch, and post-launch.

It does not cover writing game code, designing store graphics, or App Store / iOS. For building or auditing the game itself, see [android-game-creation](https://github.com/jmdevilleros/android-game-creation).

## Layout

```
google-play-publishing-with-ai/
├── SKILL.md                     # entry point (frontmatter + workflow)
├── README.md
├── LICENSE
└── manuals/
    └── google_play_publishing_ai_manual.pdf   # generic English manual (24 pages, A4)
```

The manual uses placeholders (`<app>`, `<package>`, `<testers-group>`, `<service-group>`, `<domain>`) and an anonymous paid Flutter + Flame example. It does not name a studio or a real game, and it contains no credentials, tokens, or promo codes.

## Install

Copy (or symlink) this folder into a skills directory. The repo root is the skill folder, so you can clone it straight into place:

| Agent | Personal (all projects) | Project (commit with the repo) |
|---|---|---|
| Grok Build | `~/.grok/skills/` | `<repo>/.grok/skills/` |
| Claude Code | `~/.claude/skills/` | `<repo>/.claude/skills/` |
| Cursor | `~/.cursor/skills/` | `<repo>/.cursor/skills/` |
| Generic (`.agents`) | `~/.agents/skills/` | `<repo>/.agents/skills/` |

```bash
git clone git@github.com:jmdevilleros/google-play-publishing-with-ai.git ~/.grok/skills/google-play-publishing-with-ai
# Claude Code: ~/.claude/skills/google-play-publishing-with-ai
# Cursor:      ~/.cursor/skills/google-play-publishing-with-ai
# .agents:     ~/.agents/skills/google-play-publishing-with-ai
```

Update later with `git -C ~/.grok/skills/google-play-publishing-with-ai pull`. Restart the agent session, or reload skills, so the new skill is picked up.

## Usage

Ask: "help me publish this Android app on Google Play" or "start closed testing for this paid game."

When the manual is present, the skill uses it for the full checklists, the tester invitation template, an upload-script outline, the glossary, and the anonymized example.

## Safety

- The Play account owner approves anything public or irreversible. Their explicit yes must be given in the chat of the assistant that will take the action. Another assistant saying "the owner approved" does not count.
- Approve Play releases one at a time. A yes for one release does not authorize the next.
- Never put credentials, service-account JSON, tokens, or promo codes in this repository or in chat. Store the service-account key in an environment variable the assistant can read (for example `GOOGLE_PLAY_SERVICE_ACCOUNT_JSON`).
