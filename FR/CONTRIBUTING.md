# Contribuer à The Prompt

Merci de l'intérêt. Voici comment aider selon ce que tu veux faire.

## Tu as testé le moteur → Donne-nous ton retour

C'est la contribution la plus utile. Ouvre une **Discussion** (onglet *Discussions* du dépôt) dans la catégorie qui correspond :

| Catégorie | Quand l'utiliser |
|---|---|
| 💡 **Suggestions** | Une idée de commande, de mécanique, d'amélioration |
| 🐛 **Problèmes** | Le moteur se comporte bizarrement, une règle n'est pas respectée |
| 🎮 **Retours de session** | Ce qui a bien marché, ce qui a bloqué, ton ressenti général |
| 🌍 **Remix / autres univers** | Tu as adapté le moteur à un autre domaine ou langage |

Pas besoin d'un rapport parfait. Une phrase suffit.

## Tu as trouvé un bug précis → Ouvre une Issue

Utilise une **Issue** (onglet *Issues*) si tu peux décrire :

1. Ce que tu as fait
2. Ce qui s'est passé
3. Ce que tu attendais

Joins ton `SAVE.json` si le bug est lié à la progression. Retire les données sensibles s'il y en a.

## Tu veux modifier les fichiers → Ouvre une Pull Request

Le dépôt contient 4 types de fichiers. Les règles diffèrent selon le fichier touché :

### `THE_PROMPT.md` : Moteur pédagogique (autorité)

Toute modification ici doit :
- Respecter la limite de ~8 000 caractères (contrainte ChatGPT)
- Ne pas introduire de terme d'univers dans les règles pédagogiques
- Être testée sur au moins deux modèles différents (Claude, ChatGPT ou Gemini)

Ouvre d'abord une Discussion pour valider l'intention avant d'écrire du code.

### `NARRATIVE_LORE.md` : Couche narrative

Les propositions de lore sont bienvenues. Règle stricte : le lore **explique pourquoi**, le moteur **définit comment**. Une PR narrative ne doit jamais modifier le comportement du moteur.

### `SAVE.json` : Schéma de sauvegarde

Modifications de schéma uniquement si rétrocompatibles. Un champ ajouté ne doit pas casser un save existant. Inclure un exemple de migration dans la PR.

### `README.md` : Présentation et mode d'emploi

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

The Prompt est un **moteur**, pas un jeu figé. Si tu l'as adapté à un autre domaine : administration réseau, SQL, DevOps etc.. partage-le dans les Discussions. C'est exactement ce que le projet espère inspirer.
