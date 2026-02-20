# ⚔️ No Side Quests

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin that keeps you focused on your project's main quest.

Every repo has a purpose — a main quest. But scope creep is a cunning enemy, and side quests have a way of looking deceptively important. This plugin helps you stay on track by documenting your project's vision and gently nudging you when planned work starts to wander.

## How It Works

### 1. Define your main quest

Run `/main-quest` in any repo. The Quest Scribe will:

- Explore your codebase to understand what it does
- Interview you about your roadmap and vision
- Suggest things that are probably out of scope
- Write a `.claude/main-quest.md` file capturing the whole picture

### 2. Plan fearlessly

The Quest Guardian automatically checks in during planning and brainstorming sessions. It reads your quest file and gives you a quick verdict:

- **Aligned** — You're on the path. Carry on!
- **Tangential** — This feels like a side quest. Here's why.
- **Out of Scope** — This is explicitly outside your quest boundaries.

The guardian is advisory, never blocking. If you decide to proceed with a side quest, it'll offer to log it in your quest file so there's a record of the conscious decision.

## Installation

Add the plugin to your Claude Code setup:

1. Clone this repo somewhere convenient
2. Register it in `~/.claude/settings.json`:
   ```json
   {
     "enabledPlugins": {
       "no-sidequests@no-sidequests": true
     }
   }
   ```
3. Add the install path to `~/.claude/plugins/installed_plugins.json`:
   ```json
   {
     "no-sidequests@no-sidequests": [
       {
         "scope": "user",
         "installPath": "/path/to/no-sidequests",
         "version": "0.1.0"
       }
     ]
   }
   ```
4. Restart Claude Code

## What's in the Box

| Component | Type | Purpose |
|---|---|---|
| `/main-quest` | Command | Create or update your repo's quest file |
| `no-sidequests` | Skill | Auto-invoked alignment check during planning |

## The Quest File

The plugin creates a `.claude/main-quest.md` in each repo with this structure:

```markdown
# Main Quest

## Purpose
What this repo does and why it exists.

## Vision
Where it's heading — the north star.

## Roadmap
Milestones and planned work.

## Out of Scope
Things that don't belong here.

## Accepted Side Quests
Side quests you knowingly accepted, with dates and rationale.
```

## Philosophy

- **Advisory, never blocking.** The plugin gives opinions, not orders. You always have the final say.
- **Scope awareness, not scope rigidity.** Projects evolve. When you accept a side quest, the quest log updates to reflect the new reality.
- **Fun framing, serious analysis.** The RPG terminology keeps things light, but the alignment checks are grounded in your actual roadmap and vision.

## License

MIT
