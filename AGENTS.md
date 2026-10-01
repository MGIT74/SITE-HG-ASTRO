# SITE-HG-ASTRO

Site vitrine Astro 4 pour Hands Graphic (agence automatisation IA + marketing digital).

## Commandes

- `npm run dev` — serveur de dev
- `npm run build` — build de production (validation obligatoire avant commit)
- `npm run preview` — prévisualiser le build

## Workflow Git

- Après CHAQUE mise à jour : `npm run build` (validation obligatoire), puis commit ET push directement sur `main`. Le build copie `.htaccess` dans `dist/` — il faut TOUJOURS committer `dist/` (Hostinger sert le site depuis là).
- Déploiement Hostinger (production, handsgraphic.com) : auto via le repo GitHub connecté — aucun besoin d'agir côté panel après un push. Le site est en MODE CONSTRUCTION (le `.htaccess` sert `construction/index.html` partout ; pour publier, activer le bloc PUBLICATION en commentaire du `.htaccess`).
- Messages de commit courts, en français, sans accents.

## Points d'attention

- `@astrojs/sitemap` est épinglé en 3.2.x (les versions 3.3+ cassent le build avec Astro 4).
- Webhook n8n du chat : variable d'environnement `PUBLIC_N8N_WEBHOOK_URL` (voir `.env.example`).
- Domaine du site : `https://handgraphic.com` (dans `astro.config.mjs`, `src/layouts/Layout.astro`, `public/robots.txt`).
- Le routage Hostinger se fait via `.htaccess` à la racine qui sert tout depuis `dist/` (syntaxe compatible LiteSpeed, pas de `-%{REQUEST_URI}` exotique).
- xCloud est supprimé — Hostinger est le seul environnement de production.