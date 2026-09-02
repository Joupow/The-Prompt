# THE PROMPT : COMMENT CONTRIBUER ?

Merci de l'intérêt. Voici comment aider selon ce que tu veux faire.

## Tu as testé le moteur : donne ton retour

C'est la contribution la plus utile. Ouvre une **Discussion** (onglet *Discussions* du dépôt) dans la catégorie qui correspond :

| Catégorie | Quand l'utiliser |
|---|---|
| 💡 **Suggestions** | Une idée de commande, de mécanique, d'amélioration |
| 🐛 **Problèmes** | Le moteur se comporte bizarrement, une règle n'est pas respectée |
| 🎮 **Retours de session** | Ce qui a bien marché, ce qui a bloqué, ton ressenti général |
| 🌍 **Remix / autres univers** | Tu as adapté le moteur à un autre domaine ou langage |

Pas besoin d'un rapport parfait. Une phrase suffit.

## Tu as trouvé un bug précis : ouvre une Issue

Utilise une **Issue** (onglet *Issues*) si tu peux décrire :

1. Ce que tu as fait
2. Ce qui s'est passé
3. Ce que tu attendais

Joins ton `SAVE.json` si le bug est lié à la progression. Retire les données sensibles s'il y en a.

## Tu veux modifier les fichiers : ouvre une Pull Request

Le dépôt contient cinq fichiers principaux. Les règles diffèrent selon le fichier touché.

### `Instructions.md` : amorçage (à coller dans les instructions)

Court fichier chargé dans les instructions de l'IA. Il ordonne la lecture des fichiers source et le lancement du BOOT, rien de plus. Aucune règle de gameplay ici : elles vivent dans `THE_PROMPT.md`. Une PR ne doit toucher qu'à l'ordre d'amorçage ou à l'autorité entre fichiers.

### `GAME_ENGINE.md` : moteur pédagogique (autorité)

C'est le fichier source qui définit tout le comportement du jeu. Il vit désormais en fichier source, plus collé dans les instructions : il n'est donc plus limité en taille. Privilégie quand même la densité, un moteur court se régénère et s'applique plus fidèlement d'un modèle à l'autre.

Toute modification doit :
- ne pas introduire de terme d'univers dans les règles pédagogiques (le lore explique **pourquoi**, le moteur définit **comment**) ;
- préserver les invariants du moteur (frontière simulation / réel, pas de validation sans preuve, plafond de gain par activité) ;
- être testée sur au moins deux modèles (Claude, ChatGPT ou Gemini).

Ouvre d'abord une Discussion pour valider l'intention avant d'écrire.

### `NARRATIVE_LORE.md` : couche narrative

Les propositions de lore sont bienvenues. Règle stricte : le lore explique **pourquoi**, le moteur définit **comment**. Une PR narrative ne doit jamais modifier le comportement du moteur. Tout élément de fiction persistant doit passer par le seul champ `narrative` de la sauvegarde.

### `SAVE.json` : schéma de sauvegarde

Schéma actuel : 1.1. Modifications rétrocompatibles uniquement : un champ ajouté prend une valeur neutre et ne casse pas un save existant. Tout terme d'univers (niveau de veille, fragments révélés) vit sous `narrative` et nulle part ailleurs, pour que l'état survive au retrait du lore. Inclure un exemple de migration dans la PR.

### `README.md` : présentation et mode d'emploi

Corrections, clarifications, traductions : bienvenues sans discussion préalable.

## Ce qu'on ne cherche pas

- Des réécritures complètes sans discussion préalable
- Du lore qui contredit les règles pédagogiques
- Des dépendances externes (le moteur doit rester zéro-install)

## Format d'une Pull Request

```
Titre court et descriptif

Quoi : ce qui change
Pourquoi : le problème que ça résout
Testé sur : [modèles utilisés]
```

## Une dernière chose

The Prompt est un **moteur**, pas un jeu figé. Si tu l'as adapté à un autre domaine (administration réseau, SQL, DevOps, etc.), partage-le dans les Discussions. C'est exactement ce que le projet espère inspirer.
