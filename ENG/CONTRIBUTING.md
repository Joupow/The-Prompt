# Contributing to The Prompt

Thanks for the interest. Here's how to help, depending on what you want to do.

## You tested the engine → Give us your feedback

This is the most useful contribution. Open a **Discussion** (the repo's *Discussions* tab) in the matching category:

| Category | When to use it |
|---|---|
| 💡 **Suggestions** | An idea for a command, a mechanic, an improvement |
| 🐛 **Problems** | The engine behaves oddly, a rule isn't respected |
| 🎮 **Session feedback** | What worked, what got stuck, your overall impression |
| 🌍 **Remix / other universes** | You adapted the engine to another domain or language |

No need for a perfect report. One sentence is enough.

## You found a specific bug → Open an Issue

Use an **Issue** (the *Issues* tab) if you can describe:

1. What you did
2. What happened
3. What you expected

Attach your `SAVE.json` if the bug relates to progression. Strip any sensitive data.

## You want to change the files → Open a Pull Request

The repo holds 4 types of file. The rules differ depending on which one you touch:

### `THE_PROMPT.md`: Pedagogical engine (authority)

Any change here must:
- Respect the ~8,000-character limit (ChatGPT constraint)
- Introduce no universe term into the pedagogical rules
- Be tested on at least two different models (Claude, ChatGPT or Gemini)

Open a Discussion first to validate the intent before you start editing.

### `NARRATIVE_LORE.md`: Narrative layer

Lore proposals are welcome. Strict rule: the lore **explains why**, the engine **defines how**. A narrative PR must never change the engine's behavior.

### `SAVE.json`: Save schema

Schema changes only if backward-compatible. An added field must not break an existing save. Include a migration example in the PR.

### `README.md`: Overview and getting started

Fixes, clarifications, translations: welcome without prior discussion.

## What we're not looking for

- Full rewrites with no prior discussion
- Lore that contradicts the pedagogical rules
- External dependencies (the engine must stay zero-install)

## Pull Request format

```
Short, descriptive title

What: what changes
Why: the problem it solves
Tested on: [models used]
```


## One last thing

The Prompt is an **engine**, not a fixed game. If you've adapted it to another domain — network administration, SQL, DevOps, etc. — share it in the Discussions. That's exactly what the project hopes to inspire.
