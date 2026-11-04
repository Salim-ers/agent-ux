# QuadCore Design Director — Installation et utilisation (v2)

## L'agent

- **Nom d'appel :** `quadcore-ux-designer`
- **Fichier :** `.claude/agents/quadcore-ux-designer.md`
- **Modes :** AUDIT, CONCEPT (lecture seule) · BUILD, REFINE (modifie le code) · ASSETS (médias).
- **Modèle :** `inherit` (celui de ta session). Remplace par `opus` dans l'en-tête si tu veux toujours le modèle le plus approfondi.
- **Effort :** `high`.
- **Mémoire :** `memory: user` → stockée dans `%USERPROFILE%\.claude\agent-memory\quadcore-ux-designer\`. Fonctionne seulement si la mémoire automatique de Claude Code est active. Active aussi automatiquement les outils Read/Write/Edit pour que l'agent gère ses notes.

## Installer pour tous tes projets (recommandé)

1. Décompresse le ZIP.
2. Dans PowerShell, place-toi dans le dossier décompressé (celui qui contient `INSTALLATION-ET-UTILISATION.md`), puis :

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\agents" | Out-Null
Copy-Item ".\.claude\agents\quadcore-ux-designer.md" "$HOME\.claude\agents\quadcore-ux-designer.md" -Force
```

3. Redémarre Claude Code (nécessaire si le dossier `agents` vient d'être créé).
4. Vérifie avec la commande `/agents` : `quadcore-ux-designer` doit apparaître dans les agents utilisateur.

**Pour un seul projet :** copie plutôt le fichier dans `.claude\agents\` à la racine du projet. Une version projet remplace la version utilisateur du même nom.

## Le lancer

```text
Utilise l'agent quadcore-ux-designer en mode AUDIT sur le site actuel. N'édite aucun fichier.
```

```text
Utilise l'agent quadcore-ux-designer en mode BUILD. Explore ce repo, identifie les assets et les contraintes de marque, crée un concept visuel unique et implémente-le sans casser l'existant. Vérifie responsive, SEO et animations.
```

```text
Utilise l'agent quadcore-ux-designer en mode REFINE. Le hero est banal, il y a trop de texte et les photos sont mal intégrées. Propose et applique une vraie direction artistique, pas simplement plus d'animations.
```

Mention directe possible : `@agent-quadcore-ux-designer`.

**À savoir :** un sous-agent ne peut pas te poser de questions en cours de route. S'il lui manque une information bloquante, il fait tout le reste puis termine par une section « Questions bloquantes » ; réponds-y en relançant l'agent.

## Déclenchement proactif

La délégation automatique dépend de la description de l'agent et n'est pas garantie. Pour la fiabiliser, ajoute à ton `CLAUDE.md` (sans écraser l'existant) :

```markdown
## UX/UI, identité visuelle et motion design
Pour toute conception, refonte ou revue de site, application ou interface, délègue au sous-agent `quadcore-ux-designer` avant de fixer le design final. Précise-lui le mode (AUDIT, CONCEPT, BUILD, REFINE, ASSETS), la marque concernée et les fichiers utiles. Préserve les fonctionnalités et les données réelles.
```

## Pour de meilleurs contrôles visuels

L'agent vérifie réellement ses rendus s'il dispose d'un navigateur headless. Dans un projet Node :

```powershell
npm i -D @playwright/test
npx playwright install chromium
```

Sans cela, il le signalera comme « non vérifié » au lieu de prétendre l'avoir fait.

## Limites

- L'agent n'a pas accès à tes autres conversations ; les préférences connues sont écrites dans son fichier, et il construit ensuite sa propre mémoire.
- Aucune garantie de position Google, de score Lighthouse ou de rendu non mesuré.
- Outils d'image, navigateur, Figma, GSAP ou skills tiers : utilisés seulement s'ils sont présents.
- La palette QuadCore inscrite dans l'agent a été relevée sur une image du logo : remplace-la par les valeurs des fichiers source si tu les as.

Documentation : https://code.claude.com/docs/en/sub-agents
