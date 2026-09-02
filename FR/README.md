# THE PROMPT : ONE QUEST, ANY AI

**The Prompt** transforme une simple conversation avec une IA en **moteur de jeu pédagogique** pour apprendre **Python, PowerShell et Linux**.

Le principe : apprendre en accomplissant des missions, analyser une situation, écrire du code, déboguer ses erreurs, décider sous contrainte, plu
tôt qu'en mémorisant.

Tout tient dans quelques fichiers texte à charger dans ton IA. Rien à installer.
## Quick Start

Le moteur se déroule dans un dossier projet (Projets pour Claude et ChatGPT, NotebookLM pour Gemini).

1. Copie le contenu de `Instructions.md` dans les **instructions / contexte** de ton IA. C'est le fichier d'amorçage : il dit à l'IA de lire le moteur, de charger ta sauvegarde et de lancer la partie.
2. Place les fichiers source dans le dossier de travail : `GAME_ENGINE.md` (le moteur), `SAVE.json` (ta sauvegarde), et, si tu veux l'univers, `NARRATIVE_LORE.md`.
3. Lance la partie avec `GO`.

```text
Instructions.md              À coller dans les instructions de l'IA
GAME_ENGINE.md               Moteur, en fichier source du projet
SAVE.json                    Sauvegarde, en fichier source du projet
NARRATIVE_LORE.md            Univers, en fichier source du projet (optionnel)
```

## La couche narrative : optionnelle et réversible à tout moment

The Prompt fonctionne pédagogiquement **sans** fiction. Pour jouer en mode immersif, ajoute `NARRATIVE_LORE.md` au dossier.

Cette couche se retire ou se remet à n'importe quel moment, y compris en pleine progression. C'est pourquoi la sauvegarde reste **purement pédagogique** : elle ne contient aucun terme d'univers (les rares éléments de fiction persistants sont isolés dans un seul champ, `narrative`). 

Ton état survit donc intact, que le lore soit là ou non. Tu peux enchaîner des sessions immersives, en faire une « à nu », puis réactiver l'univers sans jamais casser ta progression.

## La Réserve : la durée d'une session

Au lancement, tu choisis ta **Réserve** qui définit la durée d'une session :

- **Courte** = 3 échanges
- **Moyenne** = 10 échanges
- **Longue** = 20 échanges
- **Marathon** = 40 échanges
    
Un échange = **ton message + la réponse de l’IA**. Chaque échange consomme une unité de Réserve.

Les commandes d'affichage (`STATS`, `CARTE`, `INTRO`, `STOP`, `EXPORT_SAVE`) sont gratuites. 

Le HUD la rappelle à la fin de chaque réponse :

`[🔋 Réserve : X/Y | ⭐ XP : Z]`

À zéro, la session se clôt proprement, ta progression est sauvegardée dans le chat. 

Si tu ne veux pas t’arrêter, tu peux utiliser `CONTINUE` ou demander à ajouter de la Réserve.

Avec la couche narrative, la Réserve devient la fenêtre pendant laquelle VOX reste éveillée avant que la bibliothèque ne la laisse retomber. Sans elle, c'est simplement ta jauge de tours.

## Les commandes

- `GO` : lancer l'activité logique suivante.
- `APPRENDRE` : nouveau concept. `REVOIR` : compétence faible ou ancienne.
- `CHALLENGE` : exercice ciblé. `TEST` : évaluation sans enseignement préalable.
- `MINI-BOSS` : épreuve de validation stricte, sans indice.
- `PROJET` : mini-projet. `MIX` : mission combinant plusieurs technologies.
- `BOSS` : épreuve de synthèse. `AIDE` : indice supplémentaire.
- `DEBUG` : analyser un code fourni. `STATS` / `CARTE` : progression / arbre des compétences.
- `CONTINUE` : reprendre la mission en cours. `STOP` : terminer proprement.
- `CAMP` / `THÉORIE` : apprendre sans pénalité, avec micro-validation.
- `PASS` : abandonner l'activité en cours sans pénalité. `RECALIBRER` : réestimer ton niveau.
- `INTRO` : (re)jouer la cinématique d'ouverture, sans progression. `EXPORT_SAVE` : afficher la sauvegarde complète.

## Sauvegarde

`SAVE.json` est la **source de vérité** de ta progression. En fin de session, l'IA génère un bloc `SAVE.UPDATE` à coller dans ce fichier pour conserver ton état et le réinjecter la fois suivante.

Il reste volontairement **maigre** : plus il est court, plus le modèle le régénère sans erreur. La compétence y est suivie sur plusieurs axes séparés (compréhension, exécution, debug, autonomie, état de rétention), et tout élément d'univers reste confiné au seul champ `narrative`, pour que la sauvegarde survive au retrait du lore.

## L'univers

Après un effondrement, l'humanité a régressé et survit près de machines qu'elle prend pour la nature. Se souvenir est devenu à la fois trop coûteux en énergie et trop dangereux, parce que l'intelligence qui avait tout retenu est ce qui a causé la catastrophe.

Tu incarnes un novice qui découvre une bibliothèque enfouie encore alimentée, gérée par **VOX**, une IA holographique bâtie pour enseigner mais privée de mémoire. À chaque visite, elle s'éveille vierge et repart de rien. Ta **Carte Perforée** (le fichier de sauvegarde) est la seule mémoire qui traverse ses réveils : c'est toi qui te souviens pour vous deux.

Apprendre les anciennes langues, Python, PowerShell, Bash, te permet de rallumer les machines des Anciens et, peu à peu, de te souvenir de ce que le monde s'est interdit de savoir.

Détails complets dans `NARRATIVE_LORE.md`.

## Boucle d'apprentissage adaptative

La difficulté s'ajuste au joueur. La maîtrise est suivie séparément sur plusieurs dimensions, et deux axes en particulier ne montent jamais ensemble sans preuve : **comprendre** (savoir expliquer, lire, justifier) et **exécuter** (produire du code correct sous contrainte). Impossible de valider le par-cœur qui ne s'explique pas, ni la théorie qui ne produit rien.

La progression n'évolue que sur un axe à la fois (complexité, technologie, contrainte, temps). Des épreuves de rétention espacées (J+1, J+3, J+7, J+21) vérifient que les acquis anciens tiennent. Le mode `CAMP` permet de travailler une notion en profondeur, sans pression ni pénalité.

Deux repères de parcours se lisent directement dans la progression :

- **Paliers d'accès** : `NOVICE`, puis `OPÉRATEUR`, puis `ARCHITECTE`, gagnés en scellant des compétences (pas en accumulant de l'XP), et qui conditionnent l'accès aux BOSS de synthèse.
- Côté sécurité, les missions couvrent les **deux faces du métier** : red team (offensif : trouver et exploiter) et blue team (défensif : durcir, détecter, répondre à l'incident), jamais l'offensif seul.

## Ce qui fait la particularité de The Prompt

La plupart des « prompts de jeu » sur GitHub sont des scénarios de roleplay. The Prompt est un **moteur pédagogique** structuré, pas une simple ambiance. Ses partis pris :

- **Un vrai système d'apprentissage, pas un quiz.** Progression par indices gradués, dette technique à conséquence différée, épreuves de rétention espacées, maîtrise suivie sur plusieurs axes (compréhension, exécution, debug, autonomie, rétention). Ce sont les intentions de design du moteur ; leur qualité d'exécution dépend du modèle utilisé (voir _Limites assumées_).

- **Pourquoi se contenter d'un seul coach ?** Le même moteur tourne sur Claude, ChatGPT ou Gemini. Basculer de modèle, c'est obtenir un second avis, une autre sévérité, un autre œil sur ton code, un correcteur qui change de tempérament. Aucune plateforme à professeur unique ne le permet.

- **Tu peux changer d'IA sans recommencer.** La sauvegarde est un fichier local que tu possèdes et transportes d'une IA à l'autre. Contrairement aux plateformes captives, ton dossier d'apprentissage n'est enfermé nulle part.

- **Énergie d'activation quasi nulle.** Pas de compte, pas de VM, pas d'installation : ça tourne dans le chat que tu as déjà ouvert.

- **Moteur, univers et sauvegarde sont séparés.** Le jeu fonctionne sans fiction ; la couche narrative s'ajoute et se retire à volonté.

- **Un roman où l'auteur change au chapitre dix n'est pas le même roman.** The Prompt fonctionne ainsi : en basculant de modèle, tu changes l'intelligence. Un coup de plume plus sombre, un virage inattendu, une logique de raisonnement différente. La même mission ne se joue pas pareil selon qui l'arbitre. Ce n'est pas de l'instabilité, c'est de la pluralité.

Qu'est-ce qui dictera le moment exact où tu décideras de briser le style d'une IA pour en appeler une autre ?

## Limites assumées

Le moteur repose sur un LLM. Deux conséquences honnêtes : des modèles différents appliquent les règles différemment, et la fidélité de la sauvegarde dépend du modèle qui la régénère en fin de session. The Prompt vise une rigueur pédagogique ; il ne la garantit pas comme le ferait une plateforme à environnement contrôlé. C'est le prix de la portabilité et du coût zéro.

## Un moteur qui peut sortir de son univers

Le moteur ne dépend pas du cyberpunk post-effondrement. La boucle **mission, action, validation, progression, rétention** peut être rhabillée pour d'autres domaines, d'autres langages, l'administration système, l'analyse de données. Le storytelling est une couche d'immersion, pas une dépendance. C'est le pari le plus réutilisable du projet : la valeur est dans le moteur, pas dans l'histoire.

## Contribuer

Retour de session, bug, idée de mécanique ou remix pour un autre domaine : [`CONTRIBUTING.md`](GITHUB/Code%20Quest/TEST/CONTRIBUTING.md) détaille comment signaler, modifier et tester selon le fichier touché.

## Architecture du dépôt

```text
 ├── INSTRUCTIONS.md        ← amorçage, à coller dans les instructions de l'IA
 ├── GAME_ENGINE.md         ← moteur maître (fichier source, autorité)
 ├── NARRATIVE_LORE.md      ← couche narrative optionnelle et réversible
 ├── SAVE.json              ← sauvegarde / progression (purement pédagogique)
 ├── README.md              ← ce fichier
 └── CONTRIBUTING.md        ← retours, bugs, règles de PR
```

| Fichier             | Fonction                                                 |
| ------------------- | -------------------------------------------------------- |
| `Instructions.md`   | Amorçage collé dans les instructions ; lance le BOOT     |
| `GAME_ENGINE.md`         | Moteur maître du jeu et de la pédagogie (autorité)       |
| `SAVE.json`         | État persistant, sans terme d'univers hors `narrative`   |
| `NARRATIVE_LORE.md` | Couche narrative, activable / désactivable à tout moment |
| `README.md`         | Présentation et mode d'emploi                            |
| `CONTRIBUTING.md`   | Retours de session, bugs, règles de contribution         |

## Sécurité et cadre d'usage

Les scénarios techniques (exploration système, analyse, réponse à incident, red team et blue team) sont **fictifs ou en laboratoire autorisé**. Mettre en scène de l'analyse ou de la récupération de systèmes ne constitue pas une autorisation d'intervenir sur une infrastructure réelle.

Le moteur distingue toujours les environnements simulés des résultats d'exécution réellement fournis par l'utilisateur.
