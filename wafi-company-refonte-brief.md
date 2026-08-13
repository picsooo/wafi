# 🏜️ Refonte Homepage Wafi Company — Brief Complet

## Contexte Client

**Client:** Wafi Company Timimoun  
**Contact:** Dr. Azzedine Messai  
**Email:** contact@waficompany.com  
**WhatsApp:** +213 676 088 160  
**Site actuel:** https://waficompany.com  
**Localisation:** Timimoun, Gourara, Algérie (Sahara)  
**Secteur:** Tourisme Saharien — Hébergements & Restauration  
**Recommandé par:** Lonely Planet (édition Algérie)

---

## 📋 Cahier des Charges

### Demandes du Client

1. **Site "10/10" immersif** — Un design fort valorisant le tourisme saharien
2. **Architecture ombrelle claire** — Une page d'accueil qui sépare et présente distinctement :
   - 4 structures d'hébergement (Dar El Hakim, Dar El Wafi, Dar Tin Hinan, Wafi Bivouac)
   - 2 restaurants (Wafi Restauration Traditionnelle, La Table de Nadia)
3. **Design fort valorisant le tourisme saharien** — Hero immersif, couleurs du désert, authenticité
4. **Ultra-rapide sur mobile** malgré les connexions locales faibles (Sahara)
5. **Maintien du modèle de contact actuel** — Mise en relation directe (boutons WhatsApp visibles)
6. **Aucun outil tiers de réservation autonome** — Pas de GDS; tout converge vers WhatsApp/formulaire

### Périmètre Exclu (géré en interne)

- Gestion Google Maps / TripAdvisor
- Système de paiement tiers
- Gestion des disponibilités en temps réel

---

## 🎨 Design et Branding

### Palette Couleurs (extraite du logo Dar El Wafi)

```
Primary (Terracotta):  #a0613a
Secondary (Beige):     #d4a574
Accent (Light Beige):  #e8c4a0
Dark (Marron):         #3d2817
Light (Crème):         #faf9f7
White:                 #ffffff
```

### Inspirations Visuelles

- Minimal élégant (référence: Batinov Promotion, Just Easy Travel)
- Valorise le patrimoine architectural saharien
- Typographie sereine, espaces généreux
- Aucun clipart ou illustration générée — images réelles seulement

---

## 🔄 Données à Fetcher

### Depuis https://waficompany.com

Tu DOIS fetcher et extraire dynamiquement :

#### 1. **Hébergements (4)**
Pour chaque, récupérer :
- Nom : `Dar El Hakim`, `Dar El Wafi`, `Dar Tin Hinan`, `Wafi Bivouac`
- Description courte (2-3 lignes)
- Prix de départ (en DA)
- URL de l'image bannière (si disponible sur le site)

*Endpoint possible :* La page accueil list les maisons + prix. Scrape depuis `.projet-card` ou équivalent.

#### 2. **Restauration (2)**
- Nom : `Wafi Restauration Traditionnelle`, `La Table de Nadia`
- Description courte
- Prix moyen (en DA)

*Endpoint possible :* Section "Restauration" sur la homepage.

#### 3. **Avis Clients**
Récupérer au moins 3-5 avis 5 étoiles depuis la section "Avis de nos hôtes" :
- Texte avis
- Nom / Prénom du client
- Note (★★★★★)

*Endpoint possible :* Section testimonials au bas du site.

#### 4. **Activités** (optionnel, si listé sur le site)
- Balades à dromadaire
- Sorties en 4x4
- Soirées musicales Ahellil
- Circuit visites guidées
- Luge / Skimboard

#### 5. **Logo & Couleurs**
- Utilise le logo Dar El Wafi comme référence visuelle
- Applique la palette terracotta/beige partout

---

## 🏗️ Structure de la Page

### 1. Navigation (Sticky)
```
[Logo Wafi Company] [Accueil] [Hébergements] [Activités] [Contact] [WhatsApp CTA Button]
```
- Fond blanc semi-transparent avec backdrop-filter blur
- Barre fine en bas
- Responsive : hamburger menu sur mobile

### 2. Hero Section — Fullscreen Slider (AUTO-ROTATE)

**Concept:** Chaque hébergement brille en tant qu'héros  
**Durée:** Auto-scroll toutes les 6 secondes, contrôle manuel possible

```
Slide 1: Dar El Hakim
  [Hero gradient terracotta]
  "Dar El Hakim"
  "Tradition, authenticité, confort et bien être"
  [CTA: "Découvrir"]

Slide 2: Dar El Wafi
  [Hero gradient beige]
  "Dar El Wafi"
  "Architecture néo-soudanaise, vous y serez comme chez vous"
  [CTA: "Découvrir"]

Slide 3: Dar Tin Hinan
  [Hero gradient accent]
  "Dar Tin Hinan"
  "Le petit ksar de l'oasis rouge"
  [CTA: "Découvrir"]

Slide 4: Wafi Bivouac
  [Hero gradient dark]
  "Wafi Bivouac"
  "Nuits sous un ciel étoilé au cœur du ksar de Lichta"
  [CTA: "Découvrir"]
```

**Contrôles:**
- Flèches (‹ ›) en bas à droite
- Indicateurs (dots) en haut à droite (cliquables)
- Auto-pause au hover

### 3. Nos Hébergements — Section Produits

**Grid responsive:** 4 colonnes (desktop) → 2 (tablette) → 1 (mobile)

Pour **chaque hébergement** (fetché depuis le site) :
```
┌─────────────────────────────┐
│ [Image Hero / Placeholder]  │
├─────────────────────────────┤
│ Nom (ex: "Dar El Hakim")    │
│                             │
│ Description courte          │
│ (2-3 lignes, fetché)        │
│                             │
│ "À partir de 9 000 DA"      │
│ [Réserver] Button           │ → Ouvre WhatsApp
└─────────────────────────────┘
```

**Styling:**
- Carte blanche avec ombre légère
- Hover: élever légèrement, ombre plus marquée
- Palette couleurs du logo appliquée en gradient sur zone image

### 4. Nos Restaurants — Section Courte

**Grid:** 2 colonnes (1 mobile)

Pour **chaque restaurant** (fetché) :
```
┌──────────────────────────┐
│  [Emoji ou icône food]   │
│                          │
│ Nom (ex: "Wafi Restaur.") │
│ Description courte       │
│ "À partir de 2 500 DA"   │
└──────────────────────────┘
```

### 5. Activités & Expériences

**Grid:** 3 colonnes (2 tablette, 1 mobile)

```
┌─────────────────────┐
│  [Icône Tabler]     │
│  "Balades à dromad" │
│  Description courte  │
└─────────────────────┘
```

Activités à inclure :
- 🐪 Balades à dromadaire
- 🏜️ Sorties en 4x4  
- 🎵 Soirées musicales
- 🗺️ Visites guidées
- 🛝 Luge & Skimboard

### 6. Avis Clients — Testimonials Section

**Grid:** 3 colonnes (2 tablette, 1 mobile)

Pour **chaque avis** (fetché) :
```
┌─────────────────────────┐
│ ★★★★★                  │
│                         │
│ "Citation avis..."      │
│ (italique, muted text)  │
│                         │
│ Nom Client              │
│ Localité / Profil       │
└─────────────────────────┘
```

**Important:** Affiche clairement "Recommandé par Lonely Planet"

### 7. CTA Final — Section Call-to-Action

```
Fond: Gradient terracotta → dark

"Prêt à vivre l'expérience ?"
"Contactez-nous directement sur WhatsApp pour planifier votre séjour"

[Big Button: "💬 Discuter sur WhatsApp"]
→ Ouvre: https://wa.me/213676088160?text=Bonjour%20Wafi%20Company...
```

### 8. Footer

```
Wafi Company — Hébergements d'exception à Timimoun
Conçu avec soin par Webminds Digital Solutions
+213 676 088 160
```

---

## 🔧 Spécifications Techniques

### Performance

- ✅ Zéro dépendances externes (pas de jQuery, pas de bootstrap)
- ✅ CSS inline ou `<style>` minimal
- ✅ Images optimisées (lazy-load si nécessaire)
- ✅ Slider auto-rotate sans lag (requestAnimationFrame ou transition CSS purs)
- ✅ Mobile first : 100% responsive

### Interactivité

- ✅ Slider fullscreen : auto-rotate (6s) + contrôle manuel (flèches + dots)
- ✅ Tous les boutons "Réserver" → ouvrent WhatsApp
- ✅ Lissage transitions (0.3s-0.6s)
- ✅ Hover effects subtils (shadow, scale légère)

### Accessibilité Minimum

- ✅ Contraste texte/fond WCAG AA
- ✅ Boutons cliquables (min 44x44px)
- ✅ Alt text sur images si possible

### Dark Mode

- ⚠️ Optionnel pour MVP, mais palette terracotta/beige marche bien en mode clair (priorité)

---

## 📊 Fetch Strategy

### 1. Fetch la homepage : `https://waficompany.com`

```javascript
const html = await fetch('https://waficompany.com').then(r => r.text());
```

### 2. Parse les sections :

#### Section Hébergements
Cherche `.projet-card`, `.maison-card`, ou `h3` contenant "Dar El Hakim", etc.
Extrait :
- Nom
- Description (paragraphe suivant)
- Prix (texte contenant "DA")
- Image (background ou `<img>`)

#### Section Restauration
Cherche "Restauration", puis cartes enfants.
Extrait : Nom, description courte, prix.

#### Section Avis
Cherche "Avis de nos hôtes", puis `.testimonial`, `.review`, ou `<blockquote>`.
Extrait : Citation, nom, étoiles.

#### Section Activités
Cherche section "Activités" ou "Prestations".
Extrait : icône/emoji + titre + description courte.

### 3. Fallback Hardcoded

Si le fetch échoue ou si une section manque, utilise les **valeurs par défaut** hardcodées (ci-dessous).

---

## 📌 Données Hardcoded (Fallback)

Si le fetch échoue, utilise ceci :

### Hébergements

```json
[
  {
    "nom": "Dar El Hakim",
    "description": "Notre résidence allie tradition, authenticité, confort et bien être.",
    "prix": "9 000 DA"
  },
  {
    "nom": "Dar El Wafi",
    "description": "Une villa d'hôtes d'architecture Néo-Soudanaise, vous y serez comme chez vous.",
    "prix": "8 000 DA"
  },
  {
    "nom": "Dar Tin Hinan",
    "description": "Le Petit Ksar de l'Oasis Rouge, hommage à la Reine des Touaregs.",
    "prix": "12 000 DA"
  },
  {
    "nom": "Wafi Bivouac",
    "description": "Au cœur du Ksar de Lichta, vivez des nuits sous un ciel étoilé.",
    "prix": "3 000 DA"
  }
]
```

### Restauration

```json
[
  {
    "nom": "Wafi Restauration Traditionnelle",
    "description": "Saveurs authentiques du Sahara : Merdoum, Tandjia, brochettes.",
    "prix": "2 500 DA"
  },
  {
    "nom": "La Table de Nadia",
    "description": "Cuisine généreuse et savoureuse avec les recettes de famille.",
    "prix": "2 500 DA"
  }
]
```

### Avis (Top 3)

```json
[
  {
    "cite": "Séjour inoubliable. Accueil chaleureux, chambres magnifiques, cuisine exquise. Merci!",
    "nom": "Anna P.",
    "stars": 5
  },
  {
    "cite": "Expérience humaine et chaleureuse inoubliable. À y retourner sans hésiter.",
    "nom": "Fella S.",
    "stars": 5
  },
  {
    "cite": "Professionnalisme remarquable et générosité rare. Une adresse incontournable.",
    "nom": "Mohamed R.",
    "stars": 5
  }
]
```

---

## 🎯 Objectifs Finaux

✅ **Design moderne, élégant, valorise le Sahara**  
✅ **4 hébergements distincts, clairement présentés**  
✅ **Fullscreen slider immersif (auto-rotate)**  
✅ **Données fetchées depuis waficompany.com (live)**  
✅ **Tous les CTA pointent vers WhatsApp (+213 676 088 160)**  
✅ **Mobile-first, ultra-rapide (zéro JS lourd)**  
✅ **Palette couleurs cohérente (logo Dar El Wafi)**  
✅ **Avis clients en évidence (Lonely Planet)**  

---

## 📞 Contact Client

**Dr. Azzedine Messai**  
CEO — Wafi Company  
📧 contact@waficompany.com  
📱 +213 676 088 160 (WhatsApp)  
🌐 https://waficompany.com

---

## 🚀 Livrable

**Artifact:** HTML/CSS/JS (Fullpage, responsive, production-ready)  
**Format:** Standalone HTML (pas de dépendances externes)  
**Nom:** `wafi-company-homepage-refonte.html`
