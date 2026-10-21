# Sciences en clair

Blog statique de vulgarisation scientifique construit avec Astro. Les articles sont écrits en Markdown dans `src/content/blog/`. Le site gère les équations LaTeX/KaTeX, les formules chimiques mhchem, un flux RSS, un sitemap et le déploiement continu sur GitHub Pages.

## Démarrer en local

Version de Node attendue : Node 24 (voir `.nvmrc`).

```sh
npm install
npm run dev
```

Astro affiche l’adresse locale dans le terminal (par défaut `http://localhost:4321`). Avant publication, teste aussi la version de production :

```sh
npm run build
npm run preview
```

## Écrire un article

Crée `src/content/blog/mon-article.md` avec ce frontmatter :

```md
---
title: "Mon titre"
description: "En quelques mots, ce que l’article explique."
pubDate: 2026-10-21
category: "Physique"
---

Le texte de l’article commence ici.

Une équation dans le texte : $E = mc^2$.

Une équation isolée :

$$
F = m a
$$

Une réaction chimique avec mhchem : $\ce{2H2 + O2 -> 2H2O}$.
```

`category` accepte `Physique`, `Chimie` ou `Sciences`. `updatedDate` est facultatif. Pour une image de couverture, ajoute-la sous `src/assets/` et référence-la via le frontmatter `heroImage` selon le format du schéma Astro. Les images insérées dans le texte peuvent être placées dans `public/images/` et liées par `/images/nom-image.jpg`.

Ajoute des références directement sous forme de liens dans le texte ou en fin d’article. Pour afficher des notes, crée une section « Références ».

## Publication sur GitHub Pages

Le projet est publié sur `https://mathpe.github.io` depuis le dépôt public `MathPe/mathpe.github.io`, branche `master`. GitHub Actions construit Astro puis déploie le dossier généré. Après une modification, publie-la avec :

```sh
git add .
git commit -m "Décrire la mise à jour"
git push origin master
```

Le workflow est défini dans `.github/workflows/deploy.yml`. Pour utiliser un domaine personnalisé, modifie `site` dans `astro.config.mjs`, ajoute `public/CNAME` avec le nom de domaine, puis configure les DNS chez le fournisseur du domaine.

## Structure

- `src/content/blog/` : articles Markdown/MDX
- `src/pages/` : pages d’accueil, liste, à propos et articles
- `src/layouts/` : mise en page des articles
- `public/` : fichiers statiques et images à chemin stable
- `.github/workflows/deploy.yml` : déploiement GitHub Pages
