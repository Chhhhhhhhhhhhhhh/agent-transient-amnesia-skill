# Agent Transient Amnesia Skill 🧠💥

> Give your AI agent temporary amnesia. One trigger, one fresh response, zero context leaked. 🔑

Trigger with `@fresh` or `@遗忘` — your agent forgets everything it knows about you for just one turn, then snaps right back. No new session needed, no context pollution. Works with any agent that has persistent memory.

## Why?

AI agents with long-term memory are great — until they're not. Sometimes you want a pure, unbiased answer that isn't colored by everything your agent knows about you:

- Testing how your agent responds to a stranger
- Getting generic advice without personal context
- Checking if your agent's answer changes when it "knows" you
- Just having a clean conversation for a moment

## How It Works

```
You: @fresh What's the best programming language for beginners?
Agent: Python is widely recommended for beginners — simple syntax, great community...

You: But I already know Python basics, remember?
Agent: Oh right! You've got variables, loops, functions down. Next step...
```

One trigger. One turn. Then back to normal. That's it.

## Install

### One-liner (Hermes Agent)

```bash
hermes skills install https://raw.githubusercontent.com/Chhhhhhhhhhhhhhh/agent-transient-amnesia-skill/master/SKILL.md
```

### Manual

Copy `SKILL.md` to your agent's skills directory:

- **Hermes Agent**: `~/.hermes/skills/agent-transient-amnesia/SKILL.md`
- **Claude Code**: `~/.claude/skills/agent-transient-amnesia/SKILL.md`
- **Codex CLI**: add to your skills directory and reference in config

Make sure your agent platform supports skill-based trigger words (`@fresh`, `@遗忘`).

## Triggers

| Trigger | Language | Example |
|---------|----------|---------|
| `@fresh` | English | `@fresh explain closures` |
| `@遗忘` | Chinese | `@遗忘 解释一下闭包` |

Only works at the **beginning** of a message. Using it mid-message won't trigger.

## License

MIT — fork it, remix it, ship it.
