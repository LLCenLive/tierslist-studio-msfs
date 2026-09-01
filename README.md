# Tier List Studios — MSFS 2024

Outil de tier list glisser-déposer pour classer les studios payware/freeware de MSFS 2024, aux couleurs LLCenLive (navy / glassmorphism / accent `#3b7fe8`). Même mécanique que la tier list Airliners, appliquée cette fois aux éditeurs eux-mêmes.

Fichier unique (`index.html`), aucune installation. Fonctionne exactement comme l'outil Airliners pour l'hébergement (Netlify Drop / GitHub Pages / Cloudflare Pages, voir plus bas).

## Ajouter les logos des studios

Même principe que les captures d'avion sur l'autre outil : dépose un fichier dans `images/`, nommé exactement comme l'identifiant du studio. **Tant qu'un logo n'est pas présent, la carte affiche un badge monogramme généré automatiquement** (les initiales du studio, dans ta DA) — rien ne casse.

Formats testés dans l'ordre : `.jpg` → `.jpeg` → `.png` → `.webp`. Pour un logo, privilégie un **PNG avec fond transparent** : la vignette est en `object-fit: contain` avec un léger fond clair semi-transparent, donc un logo transparent s'intègre proprement quelle que soit sa couleur dominante.

⚠️ Rappel copyright : les logos appartiennent aux studios. Les utiliser ici, sur un site perso non-officiel à but de classement communautaire, relève de l'usage nominatif classique (identifier une marque pour en parler) — mais évite de les redistribuer ailleurs ou de les présenter comme un contenu officiel du studio.

### Table de correspondance identifiant → studio

| Fichier attendu | Studio | Spécialité |
|---|---|---|
| `images/ini.jpg` | iniBuilds | Long, moyen-courrier & classiques |
| `images/fenix.jpg` | Fenix Simulations | Famille A320 CEO |
| `images/pmdg.jpg` | PMDG | 737NG & 777 |
| `images/justflight.jpg` | Just Flight | GA (PA-28) & régional (Fokker) |
| `images/fslabs.jpg` | Flight Sim Labs | A321 ceo/neo |
| `images/blacksquare.jpg` | BlackSquare | GA haut de gamme (Duke, TBM, Baron) |
| `images/fbw.jpg` | FlyByWire Simulations | A32NX & A380X freeware |
| `images/aerosoft.jpg` | Aerosoft | CRJ, Twin Otter, A340-600 Pro |
| `images/toliss.jpg` | ToLiss | A340-600 Pro (avec Aerosoft) |
| `images/tfdi.jpg` | TFDi Design | MD-11 |
| `images/fss.jpg` | Flight Sim Studio | 727 & E-Jets |
| `images/virtualcol.jpg` | VirtualCol | CRJ, Dash 8, E-Jets |
| `images/latinvfr.jpg` | Latin VFR | A320 family, A330, A380 |
| `images/hpg.jpg` | Hype Performance Group | H145, H160, H225 |
| `images/carenado.jpg` | Carenado | Aviation générale multi-sim |
| `images/dcdesigns.jpg` | DC Designs | Concorde, warbirds, jets classiques |
| `images/flyingiron.jpg` | FlyingIron Simulations | Warbirds WWII |
| `images/milviz.jpg` | Milviz | GA complexe & warbirds |
| `images/sws.jpg` | SimWorks Studios | Hélicoptères & brousse |
| `images/rotorsim.jpg` | RotorSim | Hélicoptères |

## Filtres

Contrairement à la tier list Airliners (filtrée par studio), celle-ci filtre par **spécialité** puisque chaque carte est déjà un studio : Long/moyen-courrier, Régional, Aviation générale, Hélicoptère, Warbird/Classique, Freeware. Un studio multi-spécialité (ex. Just Flight, à la fois GA et régional) apparaît dans les deux filtres.

## Héberger gratuitement

Identique à l'outil Airliners :
1. **Netlify Drop** (https://app.netlify.com/drop) — glisse le dossier, URL immédiate
2. **GitHub Pages** — upload `index.html` + `images/` dans un repo, puis Settings → Pages → Deploy from branch
3. **Cloudflare Pages / Vercel** — même principe, aucun build requis

Pour envoyer le dossier `images/` sur GitHub : glisse le **dossier entier** (pas les fichiers un par un) dans la zone "Add file → Upload files" à la racine du dépôt, GitHub reconstitue l'arborescence automatiquement.

## Personnaliser

- Couleurs / police : mêmes variables CSS qu'Airliners (`--accent`, `--font-display`, etc.)
- Ajouter/retirer un studio : tableau `STUDIOS` en JS — `id, nom, spécialité affichée, [tags de filtre], tag principal (couleur du badge)`
- Tags de filtre disponibles : `airliner`, `regional`, `ga`, `heli`, `classic`, `freeware`

## Fonctionnement

- Glisser-déposer souris et tactile (Pointer Events, sans librairie)
- Export en PNG partageable
- Rien n'est envoyé nulle part, tout se passe dans le navigateur
