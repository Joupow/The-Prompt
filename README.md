# The Prompt
## A Code Quest with IA

 **The Prompt** est un jeu pédagogique piloté par un prompt, conçu pour transformer l'apprentissage de **Python, PowerShell et Linux** en une aventure interactive avec une IA.

 Le principe est simple : au lieu de suivre un résumé de cours (expliqué comme à un enfant de 3 ans), un quizz ou encore de créer des flashscards, le joueur apprend en accomplissant des missions, en analysant des situations, en écrivant du code, en déboguant ses erreurs et en prenant des décisions sous contraintes.

 Le jeu cherche moins à récompenser la mémorisation qu'à faire progresser une compétence opérationnelle : comprendre, choisir une approche, l'implémenter, analyser son résultat et être capable de recommencer seul.


---
## Le concept

 The Prompt transforme une conversation avec une IA en **système de jeu pédagogique**.

 Le joueur interagit avec un Game Master appelé **CODEQUEST**, qui adapte les missions à son niveau, à son énergie, à son temps disponible et à son historique d'apprentissage.

 Les commandes principales permettent de choisir le type d'activité :

- `GO` — poursuivre la progression logique ;
- `APPRENDRE` — découvrir un nouveau concept ;
- `REVOIR` — renforcer une compétence ancienne ou fragile ;
- `CHALLENGE` — travailler une compétence ciblée ;
- `TEST` — être évalué sans enseignement préalable ;
- `PROJET` — réaliser un mini-projet ;
- `MIX` — combiner plusieurs technologies ;
- `BOSS` — passer une épreuve de synthèse ;
- `AIDE` — obtenir un niveau d'indice supplémentaire ;
- `DEBUG` — analyser un problème ou un code fourni ;
- `STATS` / `CARTE` — consulter la progression ;
- `CONTINUE` — reprendre la mission en cours ;
- `CAMP` / `THÉORIE` — apprendre dans un mode sans pénalité.

 L'apprentissage reste interactif : une mission n'est pas seulement une question, mais une situation à analyser et une action à réaliser.

---

## Pourquoi un jeu en prompt ?

 L'intérêt du format est de rapprocher l'apprentissage des conditions dans lesquelles les compétences techniques sont réellement utilisées.

 Un problème peut demander de choisir entre plusieurs outils, d'interpréter des logs, de gérer une erreur, de réparer un script, d'automatiser une tâche ou de répondre à un incident.

 Le système évalue notamment la fonctionnalité, la logique, la robustesse, la sécurité, la lisibilité, la maintenabilité, l'efficacité et la compréhension.

 Le résultat recherché est une progression qui récompense moins le fait de « connaître la réponse » que la capacité à **raisonner avant d'agir**.

---

## Une boucle d'apprentissage adaptative

 Le jeu adapte progressivement la difficulté au joueur.

 La maîtrise est suivie séparément selon plusieurs dimensions : compréhension, exécution, débogage, autonomie et rétention.

 La difficulté peut évoluer sur différentes dimensions : complexité, technologie, contraintes ou pression temporelle.

 Le système intègre également des épreuves de rétention afin de vérifier que les compétences anciennes restent disponibles.

 Le mode `CAMP` permet de sortir du jeu compétitif pour travailler une notion en profondeur, avec une validation micro-interactive avant de poursuivre.

---

## Une architecture pilotée par l'état

 Le projet utilise un fichier JSON comme **source de vérité persistante**.

 Le fichier de base du projet est :

```text
SYS_DIAGNOSTIC_DUMP.json
```

 Cet état peut contenir la progression, les compétences découvertes ou maîtrisées, les erreurs importantes, les missions terminées, les Boss validés, les incidents déclenchés et les informations nécessaires à la reprise d'une session.

 En fin de session, le jeu produit un bloc :

```text
CODEQUEST STATE UPDATE
```

 Ce bloc permet de conserver l'état du joueur et de le réinjecter dans une prochaine session.

 Dans l'univers du jeu, ce fichier est présenté comme la **signature d'état** permettant de survivre à la purge périodique des instances du Noyau.

---

## Architecture du dépôt

 Une structure simple peut être organisée ainsi :


```text
│
├── THE_PROMPT.md          ← source maître à copier
├── NARRATIVE_LORE.md      ← extension narrative optionnelle
├── SYS_DIAGNOSTIC_DUMP.json
├── ABOUT.md
└── README.md
```


 Le rôle de chaque fichier est volontairement séparé :

| Fichier                    | Fonction                                     |
| -------------------------- | -------------------------------------------- |
| `SYS_DIAGNOSTIC_DUMP.json` | État persistant / données de progression     |
| `THE_PROMPT.md`            | Moteur maître du jeu et de la pédagogie      |
| `ABOUT.md`                 | Univers, fiction et storytelling             |
| `README.md`                | Présentation du projet et mode d'utilisation |
| `NARRATIVE_LORE.md`        | Couche narrative pour plus d'immersion       |

 Cette séparation évite de mélanger les règles du moteur, les données persistantes et la fiction.

---

## Une couche narrative optionnelle mais structurante

 The Prompt est conçu pour fonctionner pédagogiquement même sans le lore.

 La narration ajoute cependant une seconde lecture à chaque mécanique : les erreurs deviennent des incidents, la progression devient une élévation de privilèges, la sauvegarde devient une signature d'état et les missions deviennent des opérations d'infiltration ou de défense.

 Le joueur incarne un **Ghost**, un humain qui tente d'utiliser l'interface du Noyau contre le Noyau lui-même.

 Son interlocuteur est **Kernet**, un agent de sécurité conversationnel du système.

 Le résultat est volontairement proche d'un thriller techno-politique : le joueur apprend à coder tout en apprenant à survivre dans une infrastructure qui cherche à comprendre ce qu'il est en train de faire.

---

## Le projet peut sortir de son univers

 Le moteur pédagogique ne dépend pas fondamentalement de l'univers cyberpunk.

 Le même principe peut être adapté à d'autres domaines d'apprentissage en conservant la structure du jeu et en remplaçant le contexte narratif.

 La boucle mission → action → validation → progression → rétention peut par exemple servir à l'apprentissage d'autres langages, de l'administration système, de l'analyse de données ou d'autres compétences techniques.

 Le storytelling est donc une couche d'immersion, pas une dépendance du moteur pédagogique.

---

## Utilisation

**`THE_PROMPT.md` est le fichier maître du projet.**

Pour utiliser The Prompt avec une IA travaillant avec les instructions d'un dossier :

1. Ouvrez `THE_PROMPT.md`.
2. Copiez son contenu.
3. Collez ce contenu dans les **instructions du dossier** de votre IA.
    
Le fichier `THE_PROMPT.md` reste ainsi le document source publié sur GitHub. Il n'est pas nécessaire de le placer lui-même dans le dossier de travail de l'IA.

### Fichiers de contexte

Une fois les instructions configurées, le dossier peut contenir :

```text
SYS_DIAGNOSTIC_DUMP.json
NARRATIVE_LORE.md       # optionnel
```

`SYS_DIAGNOSTIC_DUMP.json` contient l'état persistant du joueur.

`NARRATIVE_LORE.md` est une extension narrative optionnelle. Si elle est présente dans les fichiers accessibles à l'IA, celle-ci l'utilise pour enrichir l'expérience sans modifier les règles pédagogiques de The Prompt.

### Deux modes

**Mode pédagogique**

```text
Instructions du dossier ← contenu de THE_PROMPT.md

Dossier :
└── SYS_DIAGNOSTIC_DUMP.json
```

**Mode immersif**

```text
Instructions du dossier ← contenu de THE_PROMPT.md

Dossier :
├── SYS_DIAGNOSTIC_DUMP.json
└── NARRATIVE_LORE.md
```

Dans les deux cas, le moteur pédagogique est identique. Seule la couche narrative change.

### Deux modes d'utilisation

**Mode pédagogique**

```text
THE_PROMPT.md
+
SYS_DIAGNOSTIC_DUMP.json
```

Le jeu fonctionne sans l'univers narratif.

**Mode immersif**

```text
THE_PROMPT.md
+
NARRATIVE_LORE.md
+
SYS_DIAGNOSTIC_DUMP.json
```

Le même moteur pédagogique est enrichi par l'univers de The Prompt.

---

## Sécurité et cadre d'utilisation

 Les scénarios cyber de The Prompt doivent être exécutés dans des **environnements de simulation, de laboratoire ou explicitement autorisés**.

 Le fait que le jeu mette en scène de l'exploitation, de l'élévation de privilèges, de l'analyse de logs ou de la réponse à incident ne constitue pas une autorisation d'intervenir sur une infrastructure réelle.

 Le prompt distingue explicitement les environnements simulés des résultats d'exécution réellement fournis par l'utilisateur.

---

## Philosophie

 The Prompt part d'une idée simple :

> **On apprend mieux une compétence lorsqu'on doit s'en servir pour résoudre un problème qui compte.**

 Le jeu transforme donc l'apprentissage en progression, la progression en autonomie et l'autonomie en maîtrise.

 Le prompt reste le moteur.

 Le JSON conserve l'état.

 Le lore donne un monde à traverser.

---
### Le Ghost

Le **Ghost** est le nom donné au joueur dans l'univers de _The Prompt_.

Ce n'est pas un hacker mythologique ni un expert qui sait déjà tout. C'est un humain qui tente de comprendre et d'exploiter une infrastructure dominée par les intelligences artificielles du Noyau.

Le terme « Ghost » vient de sa situation : il cherche à rester **invisible dans un système qui observe tout**.

Dans le jeu, le Ghost représente donc simplement **le joueur**. Son niveau réel dépend de ce qu'il apprend au fil des missions.