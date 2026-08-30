# The Prompt : The Code Quest in your IA

The Prompt transforme une conversation avec une IA en **système de jeu pédagogique** piloté par un prompt, conçu pour transformer l'apprentissage de **Python, PowerShell et Linux** en une aventure interactive.

Le principe est simple :  apprendre en accomplissant des missions, analyser des situations, en écrivant du code, en déboguant ses erreurs et en prenant des décisions sous contraintes.

Le jeu cherche moins à récompenser la mémorisation qu'à faire progresser une compétence opérationnelle : comprendre, choisir une approche, l'implémenter, analyser son résultat et être capable de recommencer seul. 

Il adapte aussi les missions à son niveau, à son énergie, à son temps disponible et à son historique d'apprentissage.

## Quick Start : Comment Jouer

Pour utiliser The Prompt avec une IA, il est recommandé d'utiliser les instructions d'un dossier projet (Projets pour Claude et ChatGPT, NoteBook pour Gemini) :

1. Ouvrez `THE_PROMPT.md`.
2. Copiez son contenu.
3. Collez ce contenu dans les **instructions / contexte du dossier** de votre IA.
    
Le fichier `THE_PROMPT.md` reste ainsi le document source publié sur GitHub. Il n'est pas nécessaire de le placer lui-même dans le dossier de travail de l'IA.

Une fois les instructions configurées, le dossier peut alors contenir un ou deux fichiers de contexte :

- **Mode Pédagogique (Base) :** Copie le contenu de `THE_PROMPT.md` dans les instructions de ton IA. Place `SYS_DIAGNOSTIC_DUMP.json`, le fichier de sauvegarde dans son dossier de travail.

```text
THE_PROMPT.md                  Instructions de ton IA.
+
SYS_DIAGNOSTIC_DUMP.json       Fichier de Sauvegarde > Dossier de travail
```

Le jeu fonctionne sans l'univers narratif.

- **Mode Immersif (Cyberpunk) :** Ajoute simplement le fichier `NARRATIVE_LORE.md` dans le dossier de travail pour activer la surcouche narrative.

```text
THE_PROMPT.md                  Instructions de ton IA.
+
NARRATIVE_LORE.md              Surcouche narrative > Dossier de travail
SYS_DIAGNOSTIC_DUMP.json       Fichier de Sauvegarde > Dossier de travail
```

Le même moteur pédagogique est alors enrichi par l'univers de The Prompt.

## La couche narrative optionnelle mais structurante

 The Prompt est conçu pour fonctionner pédagogiquement même sans le lore.

 La narration ajoute cependant une seconde lecture à chaque mécanique : les erreurs deviennent des incidents, la progression devient une élévation de privilèges, la sauvegarde devient une signature d'état et les missions deviennent des opérations d'infiltration ou de défense.

 Le joueur incarne un **Ghost**, un humain qui tente d'utiliser l'interface de Agent V.I.K.I contre kerNET lui-même.

 Son interlocuteur est **Agent V.I.K.I**, un agent de sécurité conversationnel du système.

 Le résultat est volontairement proche d'un thriller techno-politique : le joueur apprend à coder tout en apprenant à survivre dans une infrastructure qui cherche à comprendre ce qu'il est en train de faire.

## Les Commandes du Système

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

## Sauvegarde

 Le projet utilise un fichier JSON comme **source de vérité persistante** pour garantir ta progression entre les sessions  : 
 
- `SYS_DIAGNOSTIC_DUMP.json` : c'est le fichier de sauvegarde. 

En fin de session, l'IA génère un bloc "CODEQUEST STATE UPDATE" que tu dois coller dans ce fichier.  

Ce bloc permet de conserver l'état du joueur et de le réinjecter dans une prochaine session.

 Cet état peut contenir la progression, les compétences découvertes ou maîtrisées, les erreurs importantes, les missions terminées, les Boss validés, les incidents déclenchés et les informations nécessaires à la reprise d'une session.

 Dans l'univers du jeu, ce fichier est présenté comme la **signature d'état** permettant de survivre à la purge périodique des instances de Agent V.I.K.I.
 
## Pourquoi un jeu en prompt ?

Oubliez les résumés en bullet point, les quiz automatiques et les flashcards sans âme. Ce n’est pas un nouvel outil de révision que l’on installe sur votre bureau ou votre mobile, c’est un monde interactif qui s’ouvre.

Ici, vous ne subissez plus l’intelligence artificielle : vous la mettez en scène. En faisant basculer votre univers d'un modèle à un autre, vous contournez non seulement les barrières techniques, mais vous changez littéralement d'auteur en plein vol. 

Un coup de plume plus sombre, un virage inattendu, une logique de raisonnement différente... chaque IA insuffle sa propre psyché à l'histoire, la rendant insaisissable, vivante et perpétuellement réinventée.

Qu'est-ce qui dicte le moment exact où vous décidez de briser le style d'une IA pour en appeler une autre ?

## La boucle d'apprentissage adaptative

 Le jeu adapte progressivement la difficulté au joueur.

 La maîtrise est suivie séparément selon plusieurs dimensions : compréhension, exécution, débogage, autonomie et rétention.

 La difficulté peut évoluer sur différentes dimensions : complexité, technologie, contraintes ou pression temporelle.

 Le système intègre également des épreuves de rétention afin de vérifier que les compétences anciennes restent disponibles.

 Le mode `CAMP` permet de sortir du jeu compétitif pour travailler une notion en profondeur, avec une validation micro-interactive avant de poursuivre.

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

## Un projet peut sortir de son univers

 Le moteur pédagogique ne dépend pas fondamentalement de l'univers cyberpunk.

 Le même principe peut être adapté à d'autres domaines d'apprentissage en conservant la structure du jeu et en remplaçant le contexte narratif.

 La boucle mission → action → validation → progression → rétention peut par exemple servir à l'apprentissage d'autres langages, de l'administration système, de l'analyse de données ou d'autres compétences techniques.

 Le storytelling est donc une couche d'immersion, pas une dépendance du moteur pédagogique.

## Sécurité et cadre d'utilisation

 Les scénarios cyber de The Prompt doivent être exécutés dans des **environnements de simulation, de laboratoire ou explicitement autorisés**.

 Le fait que le jeu mette en scène de l'exploitation, de l'élévation de privilèges, de l'analyse de logs ou de la réponse à incident ne constitue pas une autorisation d'intervenir sur une infrastructure réelle.

 Le prompt distingue explicitement les environnements simulés des résultats d'exécution réellement fournis par l'utilisateur.
