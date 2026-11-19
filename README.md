# Kite plugin for Claude

Work with your [Kite](https://kite.ai) AI marketing team from Claude.

## What you get

- **Kite connector.** Connects Claude to your Kite account at `https://kite.ai/mcp`. You sign in with your Kite account the first time you use it.
- **`kite` skill.** Teaches Claude how to use the connector: find the right team and website, confirm before a change, and publish safely.

## What you can ask

- "What is my Kite team working on?"
- "Show me what publishing my website would ship."
- "Ask Kite to change the headline on my home page."
- "What is Kite waiting on me to approve?"
- "Start research on my top three competitors."

Claude asks you to confirm before it changes a website, starts work that uses Kite credits, or answers an approval.

## Install in Claude Code

```
/plugin marketplace add appsmithorg/kite-claude-plugin
/plugin install kite@kite
```

## Develop

Load the plugin for one session:

```
claude --plugin-dir .
```

Check the structure:

```
claude plugin validate . --strict
```

## Support

Contact the Kite team at https://kite.ai.
