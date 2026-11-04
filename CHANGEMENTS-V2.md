# Changements v1 → v2

## Corrections de fonctionnement
- **Questions impossibles pour un sous-agent** : la v1 demandait de « poser une question courte » ; un sous-agent Claude Code ne peut pas interroger l'utilisateur. La v2 lui fait terminer le travail possible puis lister des « Questions bloquantes » dans sa restitution.
- **Restitution adressée à la session principale** : ligne d'en-tête Mode · Marque · Périmètre, sections Hypothèses et Questions bloquantes.
- **Mode par défaut** : règle explicite (verbes d'analyse → lecture seule ; verbes de création → BUILD/REFINE ; doute → lecture seule).
- **Garde-fous** : pas de commit, push, déploiement ou migration sans demande explicite ; nouvelles dépendances justifiées.

## En-tête (frontmatter)
- Description plus courte et plus précise sur les déclencheurs (elle est chargée dans chaque session).
- Ajout `effort: high` ; retrait de `permissionMode: default` (valeur par défaut, inutile).
- Mode `PHOTO / ASSETS` renommé `ASSETS`.

## Contenu
- **Identité QuadCore** ajoutée d'après le logo : symbole, wordmark, palette relevée (à confirmer), contrastes calculés. Le cuivre foncé `#B8604A` fait 4,47:1 sur le fond : insuffisant pour du texte courant.
- **Écart signalé** : la baseline du logo dit « IT Services & Consulting » alors que l'offre principale est la création de sites/logiciels/apps + SEO.
- **Anti-clonage mesurable** : au moins 3 dimensions structurelles changées, comparaison avec l'index en mémoire.
- **Liste anti « look IA »** élargie (polices par défaut, emojis-icônes, sections 3 icônes en série, textes génériques…).
- **Repères chiffrés** : durées d'animation, cibles tactiles 44 px (min. 24 px), contrastes 4,5:1 / 3:1, 2 familles de polices max.
- **QA réelle** : captures 375 / 768 / 1440 px via Playwright si disponible, examen des captures, clavier, reduced-motion, console, 404.
- **Mémoire structurée** : `MEMORY.md` comme index (seules ~200 lignes sont chargées), `signatures.md`, `brands/<marque>.md`, `patterns-techniques.md`.
- Démarrage de mission ordonné : mémoire → mode → marque → observation.

## Guide d'installation
- Commande PowerShell corrigée : la v1 copiait `.\quadcore-ux-designer.md` alors que le fichier est dans `.\.claude\agents\`.
- Vérification par `/agents`, emplacement réel de la mémoire, installation de Playwright pour les contrôles visuels.
