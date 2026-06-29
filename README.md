# Handoff: Au Fournil du Sud — Site vitrine one-page

## Overview
Site vitrine one-page pour **Au Fournil du Sud**, boulangerie-pâtisserie à Saint-Herblain (Nantes). Une seule page longue avec nav fixe, hero, spécialités, commande spéciale, horaires + carte, et footer.

## About the Design Files
Les fichiers HTML dans ce bundle sont des **références de design** — des prototypes montrant l'apparence et le comportement souhaités, **pas du code de production à copier directement**. La mission est de **recréer ces designs dans l'environnement cible** (Next.js, React, Vue, etc.) en utilisant ses patterns et librairies existants. Si aucun environnement n'existe encore, choisir le framework le plus adapté (ex. Next.js + Tailwind).

## Fidelité
**High-fidelity** : couleurs finales, typographie précise, espacements, interactions et animations. Le développeur doit recréer l'UI au pixel près en utilisant les librairies du projet cible.

---

## Screens / Views

### Page unique — Au Fournil du Sud

#### 1. Navigation fixe
- **Position** : fixed top-0, full width, z-index 50
- **Background** : `rgba(12,26,18,0.92)` + `backdrop-filter: blur(10px)`
- **Border** : bottom 1px `rgba(255,255,255,0.05)`
- **Padding** : 18px 32px
- **Layout** : flex, space-between, align-items center
- **Logo** : Playfair Display 600 22px — "Au **Fournil** du Sud" (mot "Fournil" en `#C9A260`)
- **Badge** : "Ouvert 7j/7 · Fermé vendredi" — 12px Inter, color `#7A7A6A`, border 1px `rgba(255,255,255,0.08)`, border-radius 4px, padding 5px 12px, masqué < 720px
- **Bouton tél** : "02 28 03 12 42" — `href="tel:0228031242"`, border 1px `#5AAF7E`, color `#5AAF7E`, border-radius 4px, padding 10px 20px, 14px 500
- **Animation** : fade-in + translateY(-8px→0) 0.4s ease-out au load

#### 2. Hero
- **Min-height** : 100vh, padding-top 140px
- **Background 1** : `radial-gradient(circle at 1px 1px, rgba(201,162,96,0.06) 1px, transparent 0)` background-size 42px 42px (grille de points)
- **Background 2** : SVG overlay — étoile à 10 branches (polygon) + étoile intérieure + 4 lignes croisées, stroke `#C9A260` opacity 0.07, background-size 200px 200px (tuile répétée)
- **Badge pill** : "Boulangerie · Pâtisserie · Snacking" — 13px, letter-spacing 1.5px, uppercase, color `#C9A260`, border 1px `rgba(201,162,96,0.35)`, border-radius 40px, padding 8px 20px — animation reveal scroll
- **Titre H1** : Playfair Display 600, clamp(48px, 9vw, 108px), line-height 1.02, letter-spacing -1px
  - Ligne 1 : "Au Fournil" — color `#F0EBE0`
  - Ligne 2 : "du Sud" — italic, color `#5AAF7E`
  - **Animation** : stagger mot par mot, delay 350ms + 120ms × index
- **Adresse** : 15px, color `#7A7A6A`, letter-spacing 0.5px — reveal scroll
- **CTA 1** : "Nos spécialités" → `#specialites` — background `#5AAF7E`, color `#0C1A12`, border-radius 4px, padding 16px 32px, 15px 600
- **CTA 2** : "Itinéraire" → `#trouver` — border 1px `rgba(240,235,224,0.5)`, color `#F0EBE0`, border-radius 4px, padding 16px 32px, 15px 600

#### 3. Spécialités
- **Padding** : 100px 32px, border-top 1px `rgba(255,255,255,0.05)`
- **En-tête** : centré, ornement losange or (div 7×7px rotate 45° `#C9A260`) + texte 13px uppercase letter-spacing 2px `#C9A260` + H2 Playfair 600 clamp(32px,5vw,52px)
- **Grille** : 3 colonnes égales, gap 2px, background du gap `rgba(255,255,255,0.05)`
- **Chaque carte** : background `#142019`, padding 48px 36px, text-align center
  - Ornement losange 11×11px `#C9A260` mb 28px
  - H3 Playfair 600 26px
  - Paragraphe 15px `#7A7A6A` line-height 1.7
  - **Hover** : translateY(-4px), transition 0.3s ease-out
  - **Animation scroll** : stagger 0ms / 100ms / 200ms de délai
- **Cartes** :
  1. "Pâtisseries orientales" — cornes de gazelle, baklawas, makrouts…
  2. "Snacking & Sandwichs" — sandwichs, paninis, pizzas, formules midi
  3. "Pains artisanaux" — baguettes tradition, pains spéciaux, viennoiseries

#### 4. Commande spéciale
- **Padding** : 110px 32px, border-top 1px `rgba(255,255,255,0.05)`, text-align center
- **Max-width** : 720px centré
- Ornement losange 9×9px `#C9A260` mb 28px
- H2 Playfair 600 clamp(32px,5vw,52px) mb 24px : "Commander pour une occasion"
- Paragraphe 17px `#7A7A6A` line-height 1.7 mb 40px : "Gâteaux d'anniversaire, plateaux pâtisserie, commandes sur mesure — appelez-nous 48h à l'avance."
- CTA : "Appeler pour commander" → `tel:0228031242` — background `#5AAF7E`, color `#0C1A12`, border-radius 4px, padding 16px 36px, 15px 600

#### 5. Horaires + Nous trouver
- **Padding** : 100px 32px, border-top 1px `rgba(255,255,255,0.05)`
- **Layout** : 2 colonnes égales, gap 2px, background du gap `rgba(255,255,255,0.05)`

**Colonne gauche — Horaires** : background `#0C1A12`, padding-right 48px
- H2 Playfair 600 32px précédé d'ornement losange 8×8px `#C9A260`
- Tableau flex (space-between) par jour, border-bottom 1px `rgba(255,255,255,0.05)`, padding 16px 0
- Vendredi : color `#E06060` (les deux colonnes)
- Autres jours label `#F0EBE0` / horaire `#7A7A6A`
- Horaires : Lun–Jeu + Sam–Dim 07:00–20:00 / Vendredi Fermé

**Colonne droite — Nous trouver** : background `#142019`, padding 48px
- H2 Playfair 600 32px précédé d'ornement losange 8×8px `#C9A260`
- Label "Adresse" — 13px uppercase letter-spacing 1.5px `#C9A260` mb 10px
- Adresse : 18px line-height 1.6 mb 32px
- Label "Téléphone" — idem
- Tél : 24px `#5AAF7E` 500 mb 36px, href tel:0228031242
- Bouton "Ouvrir dans Maps" → Google Maps URL — border 1px `rgba(240,235,224,0.5)`, color `#F0EBE0`, border-radius 4px, padding 14px 28px, 15px 600

#### 6. Footer
- **Background** : `#0A1810`, border-top 1px `rgba(255,255,255,0.05)`, padding 36px 32px
- Layout flex space-between, wrap, gap 16px
- Gauche : Logo Playfair 600 20px — "Au **Fournil** du Sud"
- Droite : "© 2026 Au Fournil du Sud — Saint-Herblain" 13px `#7A7A6A`

---

## Interactions & Behavior

### Animations
- **Nav** : fade-in + translateY(-8px→0), duration 0.4s ease-out, au chargement de la page
- **Scroll reveal** : `IntersectionObserver` (threshold 0.12, rootMargin "0px 0px -40px 0px") — tous les éléments `.reveal` passent de `{opacity:0, translateY(30px)}` à `{opacity:1, translateY(0)}`, duration 0.6s ease-out
- **Stagger cartes spécialités** : délai 0ms / 100ms / 200ms entre les 3 cartes
- **Stagger titre hero** : chaque mot du H1 animé séparément, delay = 350ms + index × 120ms
- **Hover cartes** : translateY(-4px), transition 0.3s ease-out
- **Hover boutons** : transition background / color / border-color 0.25s ease-out

### Navigation
- `scroll-behavior: smooth` sur `html`
- Ancres : `#specialites`, `#trouver`

---

## Design Tokens

| Token | Valeur |
|---|---|
| Fond principal | `#0C1A12` |
| Fond secondaire | `#142019` |
| Fond footer | `#0A1810` |
| Or accent | `#C9A260` |
| Vert accent | `#5AAF7E` |
| Texte principal | `#F0EBE0` |
| Texte secondaire | `#7A7A6A` |
| Rouge fermé | `#E06060` |
| Séparateur | `rgba(255,255,255,0.05)` |
| Border-radius max | `4px` |
| Pill border-radius | `40px` |

---

## Typography

| Usage | Font | Weight | Size |
|---|---|---|---|
| Titres H1/H2/H3 | Playfair Display | 600 | clamp ou fixe |
| Logo nav | Playfair Display | 600 | 22px |
| Corps | Inter | 400 | 15–17px |
| Labels uppercase | Inter | 400 | 13px |
| Boutons | Inter | 600 | 14–15px |

Google Fonts : `https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400;1,500;1,600&family=Inter:wght@300;400;500;600&display=swap`

---

## Infos métier

| | |
|---|---|
| Nom | Au Fournil du Sud |
| Adresse | 1 Boulevard Salvador Allende, 44800 Saint-Herblain |
| Téléphone | 02 28 03 12 42 / `tel:0228031242` |
| Horaires | Lun–Jeu + Sam–Dim 07:00–20:00 |
| Fermé | Vendredi |
| Maps URL | https://www.google.com/maps/search/?api=1&query=1+Boulevard+Salvador+Allende+44800+Saint-Herblain |

---

## Style Rules
- Flat design — **pas de box-shadow, pas de gradient**
- Border-radius max **4px** (sauf pill badge = 40px)
- Séparateurs **1px rgba(255,255,255,0.05)**
- Ornement losange : `div` 7–11px × 7–11px, `background:#C9A260`, `transform:rotate(45deg)`

---

## Assets
Aucun asset externe (images, icônes) — design purement typographique et géométrique. Les motifs de fond sont des SVG inline en data URI.

## Files
- `Au Fournil du Sud.dc.html` — prototype HTML complet, source of truth du design
