# SITE-HG-ASTRO

Site vitrine Astro 4 pour Hands Graphic (agence automatisation IA + marketing digital).

## Commandes

- `npm run dev` — serveur de dev
- `npm run build` — build de production (validation obligatoire avant commit)
- `npm run preview` — prévisualiser le build

## Workflow Git

- Après CHAQUE mise à jour : build de vérification, puis commit ET push directement sur `main` (ne pas attendre une demande explicite).
- Messages de commit courts, en français, sans accents.

## Points d'attention

- `@astrojs/sitemap` est épinglé en 3.2.x (les versions 3.3+ cassent le build avec Astro 4).
- Webhook n8n du chat : variable d'environnement `PUBLIC_N8N_WEBHOOK_URL` (voir `.env.example`).
- `astro.config.mjs` contient l'URL du site (`https://hands-graphic.fr`) utilisée par le sitemap, le canonical et le JSON-LD.