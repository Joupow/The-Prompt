# The Prompt: one quest, any AI

**The Prompt** turns a plain conversation with an AI into a **pedagogical game engine** for learning **Python, PowerShell and Linux**.

The idea: you learn by completing missions, sizing up a situation, writing code, debugging your own mistakes, deciding under pressure, rather than by memorizing.

Everything fits in one instruction file to copy (`THE_PROMPT.md`) and a local save file (`SAVE.json`).

Nothing to install.
## Quick Start

We recommend a project folder (Projects in Claude/ChatGPT, a NotebookLM notebook for Gemini):

1. Open `THE_PROMPT.md`, copy its contents.
2. Paste it into your AI's **instructions / context**.
3. Drop `SAVE.json` (the save file) into the working folder.

```text
THE_PROMPT.md                Your AI's instructions
SAVE.json                    Save > working folder
```

Start the game with `GO`.
## The narrative layer: optional, reversible at any time

The Prompt works pedagogically **without** fiction. To play in immersive mode, add `NARRATIVE_LORE.md` to the working folder.

```text
THE_PROMPT.md                Your AI's instructions
NARRATIVE_LORE.md            Universe > working folder (optional)
SAVE.json                    Save > working folder
```

This layer can be **removed or added back at any moment**, mid-progression included. It's a free choice, session by session.

That's why the save stays **purely pedagogical**: it holds no universe terms, so your state survives intact whether the lore is present or not. You can string together immersive sessions, run one "bare", then switch the universe back on without ever breaking your progression.

## The commands

- `GO`: launch the next logical activity.
- `LEARN`: new concept. · `REVIEW`: weak or old skill.
- `CHALLENGE`: targeted exercise. · `TEST`: assessment with no prior teaching.
- `PROJECT`: mini-project. · `MIX`: mission spanning several technologies.
- `BOSS`: synthesis trial. · `HINT`: an extra clue.
- `DEBUG`: analyze supplied code. · `STATS` / `MAP`: progression / skill tree.
- `CONTINUE`: resume the current mission. · `STOP`: end cleanly.
- `CAMP` / `THEORY`: learn with no penalty, with a micro-check.
- `INTRO`: (re)play the opening cinematic. No penalty, outside progression.

## Saving

`SAVE.json` is the **source of truth** for your progression. At the end of a session, the AI generates a `SAVE_UPDATE` block for you to paste into this file, preserving your state and re-injecting it next time.

It's deliberately kept **lean**: the shorter it is, the more reliably the model regenerates it without error.

## The universe

After a collapse, humanity has regressed and survives beside machines it mistakes for nature. Remembering has become both too costly in energy and too dangerous because the intelligence that once retained everything is what caused the catastrophe.

You play a novice who discovers a buried library, still powered, run by **VOX**, a holographic AI built to teach but stripped of memory.

Your **Punch Card** (the save file) is the only memory that survives its awakenings.

Learning the old tongues : Python, PowerShell and Bash lets you switch the Ancients' machines back on… and, little by little, remember what the world forbade itself to know.

Full details in `NARRATIVE_LORE.md`.

## Adaptive learning loop

Difficulty adjusts to the player. Mastery is tracked separately across several dimensions (understanding, execution, debug, autonomy, retention), and only moves along one axis at a time (complexity, technology, constraint, time).

Retention trials check that older gains still hold. `CAMP` mode lets you work a notion in depth, with no pressure and no penalty.

## What makes The Prompt different

Most "game prompts" on GitHub are roleplay scenarios. The Prompt is a structured **pedagogical engine**, not just a mood. Its design choices:

- **A real learning system, not a quiz.** Progression through graduated hints, technical debt with deferred consequences, spaced retention trials, mastery tracked across several axes (understanding, execution, debug, autonomy, retention). These are the engine's design intentions; how well they're carried out depends on the model you use (see _Assumed limits_).

- **Switching AI mid-game is a mechanic, not a bug.** The same engine runs on Claude, ChatGPT or Gemini. Swapping models gets you a second opinion, a different severity, another eye on your code, a grader with a different temperament. No single-professor platform allows it.

- **Your progression is yours.** The save is a local file you own and carry from one AI to another. Unlike captive platforms, your learning record is locked away nowhere.

- **Near-zero activation energy.** No account, no VM, no install: it runs in the chat you already have open.

- **Engine, universe and save are separate.** The game works without fiction; the narrative layer is added and removed at will.

- A novel whose author changes at chapter ten isn't the same novel. The Prompt works this way: switch models and you switch the intelligence. A darker stroke of the pen, an unexpected turn, a different line of reasoning. The same mission doesn't play out the same depending on who referees it. That's not instability, it's plurality.

What will decide the exact moment you break one AI's style to summon another?

## Assumed limits

The engine runs on an LLM. Two honest consequences: different models apply the rules differently, and the fidelity of the save depends on the model that regenerates it at session's end. The Prompt aims for pedagogical rigor;

it doesn't guarantee it the way a controlled-environment platform would. That's the price of portability and zero cost.

## An engine that can leave its universe

The engine doesn't depend on post-collapse cyberpunk.

The **mission → action → validation → progression → retention** loop can be re-skinned for other domains, other languages, system administration, data analysis.

Storytelling is an immersion layer, not a dependency. That's the project's most reusable bet: the value is in the engine, not the story.

## Contributing

Session feedback, a bug, a mechanic idea or a remix for another domain: [`CONTRIBUTING.md`](CONTRIBUTING.md) spells out how to report, modify and test depending on the file you touch.

## Repository architecture

```text
 ├── THE_PROMPT.md          ← master engine to copy into the instructions
 ├── NARRATIVE_LORE.md      ← optional, reversible narrative layer
 ├── SAVE.json              ← save / progression (purely pedagogical)
 └── README.md              ← this file
 └── CONTRIBUTING.md        ← feedback, bugs, PR rules
```

| File                | Function                                              |
| ------------------- | ---------------------------------------------------- |
| `THE_PROMPT.md`     | Master engine for game and pedagogy (authority)      |
| `SAVE.json`         | Persistent state, no universe terms                  |
| `NARRATIVE_LORE.md` | Narrative layer, toggle on/off at any time           |
| `README.md`         | Overview and how-to                                  |
| `CONTRIBUTING.md`   | Session feedback, bugs, contribution rules           |

## Safety and usage boundaries

The technical scenarios (system exploration, analysis, incident response) are **fictional or in an authorized lab**. Staging analysis or system recovery is not authorization to act on real infrastructure.

The engine always distinguishes simulated environments from execution results actually supplied by the user.
