# The Prompt : one quest, any IA

**The Prompt** transforme une simple conversation avec une IA en **moteur de jeu pédagogique** pour apprendre **Python, PowerShell et Linux**. 

Le principe : apprendre en accomplissant des missions, analyser une situation, écrire du code, déboguer ses erreurs ou encore décider sous contrainte, plutôt qu'en mémorisant.

Tout tient dans un fichier d'instructions à copier (`THE_PROMPT.md`) et un fichier de sauvegarde local (`SAVE.json`). 

Rien à installer.
## Quick Start

Il est recommandé d'utiliser un dossier projet (Projets pour Claude/ChatGPT, NotebookLM pour Gemini) :

1. Ouvre `THE_PROMPT.md`, copie son contenu.
2. Colle-le dans les **instructions / contexte** de ton IA.
3. Place `SAVE.json` (le fichier de sauvegarde) dans le dossier de travail.

```text
THE_PROMPT.md                Instructions de ton IA
SAVE.json                    Sauvegarde > dossier de travail
```

Lance la partie avec `GO`.
## La couche narrative : optionnelle et réversible à tout moment

The Prompt fonctionne pédagogiquement **sans** fiction. Pour jouer en mode immersif, ajoute `NARRATIVE_LORE.md` au dossier de travail.

```text
THE_PROMPT.md                Instructions de ton IA
NARRATIVE_LORE.md            Univers > dossier de travail (optionnel)
SAVE.json                    Sauvegarde > dossier de travail
```

Cette couche peut être **retirée ou remise à n'importe quel moment**, y compris en pleine progression. C'est un choix libre, session par session. 

C'est pourquoi la sauvegarde reste **purement pédagogique** : elle ne contient aucun terme d'univers, donc ton état survit intact que le lore soit présent ou non. Tu peux enchaîner des sessions immersives, en faire une « à nu », puis réactiver l'univers sans jamais casser ta progression.

## Les commandes

- `GO` : lancer l'activité logique suivante.
- `APPRENDRE` : nouveau concept. · `REVOIR` : compétence faible ou ancienne.
- `CHALLENGE` : exercice ciblé. · `TEST` : évaluation sans enseignement préalable.
- `PROJET` : mini-projet. · `MIX` : mission combinant plusieurs technologies.
- `BOSS` : épreuve de synthèse. · `AIDE` : indice supplémentaire.
- `DEBUG` : analyser un code fourni. · `STATS` / `CARTE` : progression / arbre des compétences.
- `CONTINUE` : reprendre la mission en cours. · `STOP` : terminer proprement.
- `CAMP` / `THÉORIE` : apprendre sans pénalité, avec micro-validation.
- `INTRO` : (re)jouer la cinématique d'ouverture. Sans pénalité, hors progression.

## Sauvegarde

`SAVE.json` est la **source de vérité** de ta progression. En fin de session, l'IA génère un bloc `SAVE_UPDATE` à coller dans ce fichier pour conserver ton état et le réinjecter la fois suivante. 

Il reste volontairement **maigre** : plus il est court, plus le modèle le régénère sans erreur.

## L'univers

Après un effondrement, l'humanité a régressé et survit près de machines qu'elle prend pour la nature. Se souvenir est devenu à la fois trop coûteux en énergie et trop dangereux parce que l'intelligence qui avait tout retenu est ce qui a causé la catastrophe. 

Tu incarnes un novice qui découvre une bibliothèque enfouie encore alimentée, gérée par **VOX**, une IA holographique bâtie pour enseigner mais privée de mémoire. 

Ta **Carte Perforée** (le fichier de sauvegarde) est la seule mémoire qui traverse ses réveils. 

Apprendre les anciennes langues : Python, PowerShell, Bash te permet de rallumer les machines des Anciens… et, peu à peu, de te souvenir de ce que le monde s'est interdit de savoir.

Détails complets `NARRATIVE_LORE.md`.

## Boucle d'apprentissage adaptative

La difficulté s'ajuste au joueur. La maîtrise est suivie séparément sur plusieurs dimensions (compréhension, exécution, debug, autonomie, rétention), et n'évolue que sur un axe à la fois (complexité, technologie, contrainte, temps). 

Des épreuves de rétention vérifient que les acquis anciens tiennent. Le mode `CAMP` permet de travailler une notion en profondeur, sans pression ni pénalité.

## Ce qui fait la particularité de The Prompt 

La plupart des « prompts de jeu » sur GitHub sont des scénarios de roleplay. The Prompt est un **moteur pédagogique** structuré, pas une simple ambiance. Ses partis pris :

- **Un vrai système d'apprentissage, pas un quiz.** Progression par indices gradués, dette technique à conséquence différée, épreuves de rétention espacées, maîtrise suivie sur plusieurs axes (compréhension, exécution, debug, autonomie, rétention). Ce sont les intentions de design du moteur ; leur qualité d'exécution dépend du modèle utilisé (voir _Limites assumées_).

- **Changer d'IA en cours de partie est une mécanique, pas un bug.** Le même moteur tourne sur Claude, ChatGPT ou Gemini. Basculer de modèle, c'est obtenir un second avis, une autre sévérité, un autre œil sur ton code, un correcteur qui change de tempérament. Aucune plateforme à professeur unique ne le permet.

- **Ta progression t'appartient.** La sauvegarde est un fichier local que tu possèdes et transportes d'une IA à l'autre. Contrairement aux plateformes captives, ton dossier d'apprentissage n'est enfermé nulle part.

- **Énergie d'activation quasi nulle.** Pas de compte, pas de VM, pas d'installation : ça tourne dans le chat que tu as déjà ouvert.

- **Moteur, univers et sauvegarde sont séparés.** Le jeu fonctionne sans fiction ; la couche narrative s'ajoute et se retire à volonté.

- Un roman où l'auteur change au chapitre dix n'est pas le même roman. The Prompt fonctionne ainsi : en basculant de modèle, tu changes l'intelligence. Un coup de plume plus sombre, un virage inattendu, une logique de raisonnement différente. La même mission ne se joue pas pareil selon qui l'arbitre. Ce n'est pas de l'instabilité, c'est de la pluralité.

Qu'est-ce qui dictera le moment exact où vous décidez de briser le style d'une IA pour en appeler une autre ?

## Limites assumées

Le moteur repose sur un LLM. Deux conséquences honnêtes : des modèles différents appliquent les règles différemment, et la fidélité de la sauvegarde dépend du modèle qui la régénère en fin de session. The Prompt vise une rigueur pédagogique ; 

il ne la garantit pas comme le ferait une plateforme à environnement contrôlé. C'est le prix de la portabilité et du coût zéro.

## Un moteur qui peut sortir de son univers

Le moteur ne dépend pas du cyberpunk post-effondrement. 

La boucle **mission → action → validation → progression → rétention** peut être rhabillée pour d'autres domaines, autres langages, administration système, analyse de données. 

Le storytelling est une couche d'immersion, pas une dépendance. C'est le pari le plus réutilisable du projet : la valeur est dans le moteur, pas dans l'histoire.

## Architecture du dépôt

```text
├── THE_PROMPT.md          ← moteur maître à copier dans les instructions
├── NARRATIVE_LORE.md      ← couche narrative optionnelle et réversible
├── SAVE.json              ← sauvegarde / progression (purement pédagogique)
└── README.md              ← ce fichier
```

| Fichier             | Fonction                                               |
| ------------------- | ------------------------------------------------------ |
| `THE_PROMPT.md`     | Moteur maître du jeu et de la pédagogie (autorité)     |
| `SAVE.json`         | État persistant, sans terme d'univers                  |
| `NARRATIVE_LORE.md` | Couche narrative, activable/désactivable à tout moment |
| `README.md`         | Présentation et mode d'emploi                          |

## Sécurité et cadre d'usage

Les scénarios techniques (exploration système, analyse, réponse à incident) sont **fictifs ou en laboratoire autorisé**. Mettre en scène de l'analyse ou de la récupération de systèmes ne constitue pas une autorisation d'intervenir sur une infrastructure réelle. 

Le moteur distingue toujours les environnements simulés des résultats d'exécution réellement fournis par l'utilisateur.
