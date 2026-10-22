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

Copie `templates/article.md` vers `src/content/blog/mon-article.md`. Remplace le titre, le résumé et la date dans le frontmatter, choisis `Physique`, `Chimie` ou `Sciences`, puis rédige après le séparateur `---`. Laisse le frontmatter en place : `title`, `description` et `pubDate` sont requis pour générer la page.

La catégorie accepte `Physique`, `Chimie` ou `Sciences`. `updatedDate` est facultatif. Pour une image de couverture, ajoute-la sous `src/assets/` et référence-la via le frontmatter `heroImage` selon le format du schéma Astro. Les images insérées dans le texte peuvent être placées dans `public/images/` et liées par `/images/nom-image.jpg`.

Les équations s’écrivent en LaTeX, par exemple `$E = mc^2$` ou `$$F = ma$$`. Pour une formule chimique, utilise mhchem, par exemple `\ce{2H2 + O2 -> 2H2O}` à l’intérieur des délimiteurs mathématiques.

Ajoute des références directement sous forme de liens dans le texte ou sous le titre « Références » en fin d’article.

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
- `templates/article.md` : modèle réutilisable d’article
- `src/pages/` : pages d’accueil, liste, à propos et articles
- `src/layouts/` : mise en page des articles
- `public/` : fichiers statiques et images à chemin stable
- `.github/workflows/deploy.yml` : déploiement GitHub Pages
