# ColorFigures

Des objets du quotidien, encrés à la main et en isométrie, qu'on fait tourner, qu'on regarde de l'intérieur et
qu'on fait fonctionner. Chaque figure est une seule page web autonome, dessinée par Claude avec le skill
[Colorfigures](https://april-zhu.com/colorfigures) d'April Zhu.

**Voir la galerie : https://w3cdotorg.github.io/ColorFigures/**

| Fig. | Figure | Ce qu'on peut faire |
| --- | --- | --- |
| 01 | [Locomotive à vapeur](https://w3cdotorg.github.io/ColorFigures/figures/locomotive-a-vapeur.html) | Faire le plein d'eau au château d'eau, charger le bois, nourrir le feu, siffler et partir, revenir. En transparence : foyer, tubes à fumée, régulateur, pistons, injecteur, caisse à eau du tender, réservoir et flotteur du château d'eau. |

## Organisation

```
index.html            la page de présentation (galerie)
figures/<nom>.html    les figures prêtes à ouvrir (moteur inclus, aucune requête extérieure)
thumbs/<nom>.jpg      vignette, et <nom>-dedans.jpg pour la vue en transparence (affichée au survol)
src/<nom>/figure.html la source de chaque figure (géométrie, mécanisme, boutons)
```

## Ajouter une figure

1. Créer la figure avec le skill Colorfigures dans Claude Code, puis copier sa source dans `src/<nom>/figure.html`.
2. La construire avec le script du skill :
   `python3 ~/.claude/skills/colorfigures/scripts/build.py src/<nom>/figure.html figures/<nom>.html`
   (la source charge `core.js` : copier `~/.claude/skills/colorfigures/assets/core.js` à côté pour l'ouvrir telle quelle).
3. Ajouter deux vignettes 4:3 (vue normale et vue en transparence) dans `thumbs/`.
4. Ajouter une carte dans la section `#figures` de `index.html`, et une ligne au tableau ci-dessus.

La locomotive accepte quelques paramètres d'URL pour les captures et les tests :
`?yaw=200&pitch=40` (angle de vue), `?xr=1&labels=1` (transparence et étiquettes), `?shot=1` (le dessin seul),
`?sim=Faire@0.3,Charger@7&at=9` (appuie sur les boutons aux instants donnés, en accéléré, puis dessine l'état obtenu).

## Crédits

- Skill et moteur [Colorfigures](https://april-zhu.com/colorfigures) : April Zhu (MIT).
- Construit sur [ISO-GLOW](https://isoglow.dev) (April Zhu, MIT) et [iso-figure](https://github.com/MrBongoC/ai-iso-skill)
  (Tolga Cohce, MIT).
- Figures de ce dépôt dessinées avec Claude.

## Licence

MIT, voir [LICENSE](LICENSE).
