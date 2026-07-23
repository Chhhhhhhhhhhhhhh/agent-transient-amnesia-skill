# Fresh Slate — Agent Transient Amnesia Skill 🧠💥

> Make your AI agent forget you — for one turn, or for a whole session. No leaked context, no polluted answers.

## v2 — What's New

| Mode | Trigger | Duration |
|------|---------|----------|
| **Single-turn** | `@fresh` / `@遗忘` | One response only |
| **Multi-turn** | `@陌生人` / `@stranger` | Until `@恢复` / `@restore` |

```
@fresh explain closures              ← single-turn amnesia
@stranger who am I                   ← enter multi-turn amnesia
what OS do I use                     ← still amnesiac
@restore                             ← exit
I said earlier that...               ← back to normal
```

## What It Strips

The agent pretends these don't exist:

- **Memory** — user preferences, habits, conventions
- **User profile** — identity, background, skills
- **Chat history** — everything before the trigger
- **Project rules** — `.hermes.md`, `AGENTS.md`, commit conventions
- **Persona** — SOUL.md, agent personality definition

## What It Keeps

- Tool definitions — the agent can still work
- System facts — OS, working directory, PATH
- World knowledge — languages, frameworks, public information

## Why?

- Test how your agent responds to a stranger
- Get unbiased advice without personal context
- Check if answers change when the agent "knows" you
- Clean conversations when you need them

## Install

### Hermes Agent

```bash
hermes skills install https://raw.githubusercontent.com/Chhhhhhhhhhhhhhh/agent-transient-amnesia-skill/master/SKILL.md
```

### Manual

Copy `SKILL.md` to your agent's skills directory.

| Platform | Path |
|----------|------|
| Hermes Agent | `~/.hermes/skills/agent-transient-amnesia/SKILL.md` |
| Claude Code | `~/.claude/skills/agent-transient-amnesia/SKILL.md` |
| Codex CLI | add to skills directory and reference in config |

## Triggers

| Trigger | Language | Mode |
|---------|----------|------|
| `@fresh` | English | Single-turn |
| `@遗忘` | Chinese | Single-turn |
| `@陌生人` / `@stranger` | Chinese / English | Multi-turn start |
| `@恢复` / `@restore` | Chinese / English | Multi-turn end |

All triggers must appear at the **beginning** of a message.

## Honest Disclaimer

Memory and user profiles are injected at the system level — the agent can't remove them from context, only **choose to ignore them**. For true process-level isolation, use your platform's native mechanisms (e.g. `hermes --profile fresh-slate --ignore-rules`).

## License

MIT — fork it, remix it, ship it.
