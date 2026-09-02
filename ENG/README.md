# THE PROMPT : ONE QUEST, ANY AI

**The Prompt** turns a simple conversation with an AI into an **adaptive learning game engine** for mastering **Python, PowerShell, and Linux**.

The idea: learn by completing missions, analyzing situations, writing code, debugging mistakes, and making decisions under pressure, rather
than memorizing.

Everything runs from a handful of text files loaded into your AI. Nothing to install.
## Quick Start

The engine runs from a project folder (Projects in Claude and ChatGPT, NotebookLM in Gemini).

1. Copy the contents of `Instructions.md` into your AI's **instructions / context**. This is the bootstrap file: it tells the AI to read the engine, load your save, and start the game.
2. Place the source files in the working folder: `GAME_ENGINE.md` (the engine), `SAVE.json` (your save), and, if you want the setting, `NARRATIVE_LORE.md`.
3. Start the game with `GO`.

```text
INSTRUCTIONS.md              Paste into the AI's instructions
GAME_ENGINE.md               Engine, stored as a project source file
SAVE.json                    Save, stored as a project source file
NARRATIVE_LORE.md            Setting, stored as a project source file (optional)
```

## The narrative layer: optional and reversible at any time

The Prompt works as a learning system **without** fiction. For an immersive run, add `NARRATIVE_LORE.md` to the folder.

You can remove or restore this layer at any time, even mid-progression. That is why the save remains **purely educational**: it contains no setting-specific terminology (the few persistent fictional elements are isolated in a single `narrative` field). 

Your state therefore survives intact whether the lore is loaded or not. You can play several immersive sessions, run one "bare", then bring the setting back without ever breaking your progression.

## Charge: session length

At launch, you choose your **Charge**, which determines the length of the session:

- **Short** = 3 exchanges
- **Medium** = 10 exchanges
- **Long** = 20 exchanges
- **Marathon** = 40 exchanges

One exchange = **your message + the AI's reply**. Each exchange consumes one unit of Charge

Display commands (`STATS`, `MAP`, `INTRO`, `STOP`, `EXPORT_SAVE`) are free. 

The HUD reminds you at the end of every response:

`[🔋 Charge: X/Y | ⭐ XP: Z]`

At zero, the session closes cleanly and your progress is saved: nothing is lost. If you don't want to stop, you can also use `CONTINUE` or ask for more Charge.

With the narrative layer enabled, Charge measures how long VOX can remain awake before the library lets her fall dormant again. Without the lore, it is simply your turn gauge.

## Commands

- `GO`: start the next logical activity.
- `LEARN`: new concept. `REVIEW`: weak or aging skill.
- `CHALLENGE`: targeted exercise. `TEST`: evaluation with no prior teaching during the activity.
- `MINI-BOSS`: strict validation trial, no hints.
- `PROJECT`: mini-project. `MIX`: mission combining several technologies.
- `BOSS`: synthesis trial. `HELP`: additional hint.
- `DEBUG`: analyze supplied code. `STATS` / `MAP`: progression / skill tree.
- `CONTINUE`: resume the current mission. `STOP`: end cleanly.
- `CAMP` / `THEORY`: learn without pressure, with micro-validation.
- `PASS`: abandon the current activity without penalty. `RECALIBRATE`: reassess your level.
- `INTRO`: (re)play the opening cinematic, with no progression. `EXPORT_SAVE`: display the complete save.

## Saving

`SAVE.json` is the **source of truth** for your progression. At the end of a session, the AI generates a `SAVE.UPDATE` block to paste into this file so your state is preserved and can be reinjected next time.

It is deliberately kept **lean**: the shorter it is, the less likely a model is to regenerate it incorrectly. Mastery is tracked across several separate axes (comprehension, execution, debugging, autonomy, retention state), while every setting-specific element remains confined to the single `narrative` field, so the save survives when the lore is removed.

## The setting

After a collapse, humanity has regressed and now survives beside machines it mistakes for nature. Remembering has become both too expensive in energy and too dangerous, because the intelligence that remembered everything is what caused the catastrophe.

You play a novice who discovers a buried library that still has power, overseen by **VOX**, a holographic AI built to teach but stripped of memory. Each time you return, she wakes blank and starts from nothing. Your **Punch Card** (the save file) is the only memory that survives across her awakenings: you remember for both of you.

Learning the old languages, Python, PowerShell, and Bash, lets you bring the machines of the Ancients back online and, piece by piece, remember what the world forbade itself from knowing.

Full details in `NARRATIVE_LORE.md`.

## Adaptive learning loop

Difficulty adapts to the player. Mastery is tracked across several dimensions, and two axes in particular never rise together without evidence: **comprehension** (explaining, reading, justifying) and **execution** (producing correct code under constraint). Rote knowledge that cannot be explained does not validate, and neither does theory that cannot produce working output.

Progression advances along only one major dimension at a time (complexity, technology, constraint, time). Spaced retention trials (D+1, D+3, D+7, D+21) check whether older skills still hold. `CAMP` mode lets you study a concept in depth, without pressure or penalty.

Two journey markers are derived directly from progression:

- **Access tiers**: `NOVICE`, then `OPERATOR`, then `ARCHITECT`, earned by sealing skills (not by accumulating XP), and used to gate synthesis BOSS encounters.
- On the security side, missions cover **both halves of the job**: red team (offense: discover and exploit) and blue team (defense: harden, detect, respond to incidents), never offense alone.

## What makes The Prompt different

Most "game prompts" on GitHub are roleplay scenarios. The Prompt is a structured **learning engine**, not just an atmosphere. Its core design choices:

- **A real learning system, not a quiz.** Graduated hints, technical debt with delayed consequences, spaced retention trials, and mastery tracked across several axes (comprehension, execution, debugging, autonomy, retention). These are the engine's design goals; how faithfully they are carried out depends on the model used (see _Known limitations_).

- **Why settle for one coach?** The same engine runs on Claude, ChatGPT, or Gemini. Switching models gives you a second opinion, a different level of strictness, another set of eyes on your code, a reviewer with a different temperament. A single-teacher platform cannot offer that.

- **You can switch AIs without starting over.** The save is a local file you own and carry from one AI to another. Unlike closed platforms, your learning record is not trapped anywhere.

- **Near-zero setup cost.** No account, no VM, no installation: it runs in the chat you already have open.

- **Engine, setting, and save are separate.** The game works without fiction; the narrative layer can be added or removed at will.

- **A novel does not stay the same when the author changes at chapter ten.** The Prompt works the same way: switch models and you switch the intelligence behind the game. A darker voice, an unexpected turn, a different reasoning style. The same mission does not play the same way under a different arbiter. That is not instability, it is plurality.

What will decide the exact moment when you break one AI's style and call in another?

## Known limitations

The engine runs on an LLM. That has two honest consequences: different models apply the rules differently, and save fidelity depends on the model regenerating it at the end of the session. The Prompt aims for rigorous learning; it cannot guarantee it the way a controlled-platform environment can. That is the price of portability and zero cost.

## An engine that can leave its own setting

The engine does not depend on post-collapse cyberpunk. The **mission, action, validation, progression, retention** loop can be reskinned for other fields, other languages, system administration, or data analysis. Storytelling is an immersion layer, not a dependency. That is the project's most reusable bet: the value lives in the engine, not the story.

## Contributing

Session feedback, bugs, mechanic ideas, or remixes for another field: [`CONTRIBUTING.md`](GITHUB/Code%20Quest/TEST/CONTRIBUTING.md) explains how to report, modify, and test changes depending on the file involved.

## Repository architecture

```text
 ├── INSTRUCTIONS.md        ← bootstrap, paste into the AI's instructions
 ├── GAME_ENGINE.md         ← master engine (source file, authority)
 ├── NARRATIVE_LORE.md      ← optional, reversible narrative layer
 ├── SAVE.json              ← save / progression (purely educational)
 ├── README.md              ← this file
 └── CONTRIBUTING.md        ← feedback, bugs, PR rules
```

| File                | Purpose                                                |
| ------------------- | ------------------------------------------------------ |
| `INSTRUCTIONS.md`   | Bootstrap pasted into instructions; launches BOOT      |
| `GAME_ENGINE.md`    | Master game and learning engine (authority)            |
| `SAVE.json`         | Persistent state, no setting terms outside `narrative` |
| `NARRATIVE_LORE.md` | Narrative layer, enabled / disabled at any time        |
| `README.md`         | Overview and usage guide                               |
| `CONTRIBUTING.md`   | Session feedback, bugs, contribution rules             |

## Safety and usage boundaries

Technical scenarios (system exploration, analysis, incident response, red team, and blue team) are **fictional or take place in an explicitly authorized lab**. Staging system analysis or recovery does not grant permission to interfere with real infrastructure.

The engine always distinguishes simulated environments from real execution results explicitly supplied by the user.
