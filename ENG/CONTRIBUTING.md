# THE PROMPT : HOW TO CONTRIBUTE?

Thanks for your interest. Here's how you can help, depending on what you want to do.

## You tested the engine: share your feedback

This is the most useful contribution you can make. Open a **Discussion** (the repository's *Discussions* tab) in the appropriate category:

| Category | When to use it |
|---|---|
| 💡 **Suggestions** | An idea for a command, mechanic, or improvement |
| 🐛 **Issues** | The engine behaves strangely or fails to follow a rule |
| 🎮 **Session feedback** | What worked, what got in the way, your overall experience |
| 🌍 **Remixes / other settings** | You adapted the engine to another field or language |

No need for a perfect report. One sentence is enough.

## You found a specific bug: open an Issue

Use an **Issue** (the *Issues* tab) if you can describe:

1. What you did
2. What happened
3. What you expected

Attach your `SAVE.json` if the bug is progression-related. Remove any sensitive data first.

## You want to modify the files: open a Pull Request

The repository contains five main files. The rules depend on which file you change.

### `Instructions.md`: bootstrap (paste into the instructions)

A short file loaded into the AI's instructions. It tells the AI to read the source files and run the BOOT sequence, nothing more. No gameplay rules belong here: those live in `THE_PROMPT.md`. A PR should only change the bootstrap order or the authority hierarchy between files.

### `GAME_ENGINE.md`: learning engine (authority)

This is the source file that defines all game behavior. It now lives as a project source file instead of being pasted into the instructions, so it is no longer constrained by instruction size limits. Still, favor density: a shorter engine is regenerated and applied more faithfully across models.

Any change must:
- avoid introducing setting-specific terms into the learning rules (the lore explains **why**, the engine defines **how**);
- preserve the engine invariants (simulation / real-world boundary, no validation without evidence, per-activity gain cap);
- be tested on at least two models (Claude, ChatGPT, or Gemini).

Open a Discussion first to validate the intent before writing the change.

### `NARRATIVE_LORE.md`: narrative layer

Lore proposals are welcome. One strict rule: the lore explains **why**, the engine defines **how**. A narrative PR must never change engine behavior. Any persistent fictional element must live exclusively in the save's `narrative` field.

### `SAVE.json`: save schema

Current schema: 1.1. Backward-compatible changes only: any added field must default to a neutral value and must not break an existing save. All setting-specific terms (Watch Level, revealed fragments) live under `narrative` and nowhere else, so player state survives when the lore is removed. Include a migration example in the PR.

### `README.md`: overview and usage guide

Fixes, clarifications, and translations are welcome without prior discussion.

## What we're not looking for

- Full rewrites without prior discussion
- Lore that contradicts the learning rules
- External dependencies (the engine must remain zero-install)

## Pull Request format

```
Short, descriptive title

What: what changes
Why: the problem it solves
Tested on: [models used]
```

## One last thing

The Prompt is an **engine**, not a fixed game. If you've adapted it to another field (network administration, SQL, DevOps, etc.), share it in Discussions. That's exactly the kind of remix this project is meant to inspire.
