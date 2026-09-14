# Léa & Emma — tes agents IA (template NAIOM)

Deux agents installés dans la même app, à ouvrir dans **Claude Code**.

| Agent | Slug | Ce qu'il fait | Livrables |
|---|---|---|---|
| **Léa** — Créateur de contenu | `createur-contenu` | Posts LinkedIn, carrousels, scripts Reels/TikTok/YouTube, threads, emails | `content/` |
| **Emma** — Agente e-commerce | `ecommerce` | Vidéos produit avec avatars IA (Arcads), prêtes à publier | dans l'app |

## Démarrer en 3 étapes
1. Ouvre **ce dossier** dans Claude Code.
2. Dans le terminal :
   ```bash
   cd naiom-platform
   cp .env.example .env.local     # puis colle ta clé Anthropic dans .env.local
   npm install
   npm run dev
   ```
3. Ouvre **http://localhost:3000** → tu arrives direct sur l'interface de l'agent actif.

Ta clé Anthropic : https://console.anthropic.com → API Keys.

## Basculer entre Léa et Emma
L'app ne débloque **qu'un agent à la fois**. Dans `naiom-platform/.env.local`, change ces
deux lignes puis relance `npm run dev` :

```bash
OWNED_AGENT=createur-contenu          # Léa  (valeur par défaut)
NEXT_PUBLIC_OWNED_AGENT=createur-contenu

# ou

OWNED_AGENT=ecommerce                 # Emma
NEXT_PUBLIC_OWNED_AGENT=ecommerce
```

Les autres agents de la plateforme restent visibles mais **verrouillés**
(page « Débloquer les autres »).

## 100 % vierge
Aucune clé, aucun historique, aucune donnée d'origine. Tout est à toi :
- Remplace `clients/votre-marque/brand.md` par ton contexte de marque — les deux
  agents le lisent avant de produire.
- Les prompts des agents sont dans `.claude/agents/`.

Clés éventuelles selon les fonctionnalités : voir `naiom-platform/.env.example`.
