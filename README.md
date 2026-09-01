# Aperçu logos — page client

Page statique : nom de marque + aperçu de chaque logo calé dans la zone 40 × 40 cm,
avec un filtre de recherche en haut.

## Régénérer

Depuis `logos-projet/` :

```
python3 build_web.py
```

Recrée `web/index.html` + `web/img/*.jpg` à partir du dernier traitement
(`output/recadres/`). Relancer après chaque modif de logo.

## Mettre en ligne (Vercel)

**Option A — CLI (le plus rapide)**

```
cd web
npx vercel          # 1re fois : répondre aux questions, ça crée le projet
npx vercel --prod   # déploiement final, donne l'URL à partager
```

**Option B — GitHub + Vercel (auto-déploiement)**

1. Commit le dossier (ou tout le repo) sur GitHub.
2. Sur vercel.com → *Add New Project* → importer le repo.
3. **Root Directory** : `logos-projet/web` — Framework Preset : *Other*.
4. Deploy. À chaque `git push`, Vercel redéploie tout seul.

Pour mettre à jour : `python3 build_web.py` → `git add web && git commit && git push`.

## Notes

- `<meta name="robots" content="noindex">` : la page n'est pas indexée par Google.
- Pour restreindre l'accès : activer *Password Protection* dans les réglages Vercel
  du projet (plan Pro) ou déployer en *Preview* et partager le lien preview.
