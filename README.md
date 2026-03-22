# prompt-buttons

**Telegram inline buttons skill for OpenClaw agents.** Provides short, tappable button menus that work seamlessly with Telegram's native inline keyboard format.

## Features

- ✅ Telegram native inline buttons
- ✅ Graceful fallback to plain text replies when buttons are unavailable
- ✅ Short label enforcement (≤3 characters by default)
- ✅ Clear instruction text in message body
- ✅ Works with OpenClaw's `message` tool

## Install

```bash
clawhub install prompt-buttons
```

## Quick Start

Add to your agent's SKILL.md reference:

```markdown
- When presenting choices, use the `prompt-buttons` skill
- Use short labels (≤3 chars): "1", "2", "3", "✓", "✗"
- Include one-line instruction in message body
- Buttons for selection only, not navigation
```

Then use the `message` tool with `buttons` parameter:

```javascript
{
  "action": "send",
  "channel": "telegram",
  "target": "USER_ID",
  "message": "Choose an option:",
  "buttons": [[
    {"text": "1", "callback_data": "1"},
    {"text": "2", "callback_data": "2"},
    {"text": "3", "callback_data": "3"}
  ]]
}
```

## Fallback Behavior

If Telegram buttons are unavailable or callback isn't wired, fall back to plain text options:

```
Choose an option:
1 - Option A
2 - Option B
3 - Option C
```

## Publish (maintainer)

```bash
# 1. Navigate to skill folder
cd skills/prompt-buttons

# 2. Login to ClawHub
clawhub login

# 3. Publish
clawhub publish . --slug prompt-buttons --name "Prompt Buttons" --version 1.0.2
```

## License

MIT
