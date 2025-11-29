# 🎨 Style Santiago - Thème Premium Minimaliste

Ce document explique l'implémentation du style **Santiago** inspiré de santiago.ma dans le thème Shopify Dawn.

---

## 🎯 Objectif

Créer un thème premium, minimaliste et luxueux pour une boutique de chaussures homme, avec un design élégant utilisant uniquement les couleurs de marque :

- **Couleur principale** : `#231f20` (noir profond)
- **Couleur secondaire** : `#ffffff` (blanc)

---

## 📁 Structure des Fichiers Modifiés

### Styles Globaux
- **`assets/base.css`** : Tous les styles Santiago sont ajoutés à la fin du fichier (lignes 3658+)
  - Typographie (Playfair Display + Inter)
  - Styles header, hero, collections, produits, footer
  - Animations et transitions
  - Responsive breakpoints

### Sections
- **`sections/header.liquid`** : Header minimaliste avec menu centré
- **`sections/hero-homme.liquid`** : Hero premium avec animations
- **`sections/collection-list-homme.liquid`** : Grid collections avec hover premium
- **`sections/benefits.liquid`** : Section avantages (nouvelle)
- **`sections/footer.liquid`** : Footer noir premium

### Snippets
- **`snippets/card-product.liquid`** : Cartes produits style Santiago avec badge luxe

### JavaScript
- **`assets/global.js`** : Animations reveal et scroll (fin du fichier)

---

## 🎨 Couleurs et Styles

### Couleurs de Marque
```css
--brand-dark: #231f20;  /* Noir profond */
--brand-light: #ffffff;  /* Blanc */
```

**⚠️ Important** : Aucune autre couleur n'est autorisée. Seules les opacités et ombres basées sur `#231f20` sont permises.

### Typographie
- **Titres** : `'Playfair Display', serif` (premium, élégant)
- **Corps** : `'Inter', system-ui, sans-serif` (moderne, lisible)

---

## 🏗️ Sections Principales

### 1. Header (sections/header.liquid)

**Style** :
- Fond blanc (`#ffffff`)
- Logo noir à gauche
- Menu centré (Home, Collections, Nouveautés, Contact)
- Icônes à droite (recherche, compte, panier)
- Sticky avec ombre fine au scroll
- Hamburger moderne sur mobile

**Animations** :
- Ligne fine qui glisse sous les liens au hover (width: 0 → 100%)

**Classes CSS** :
- `.header-wrapper` : Container principal
- `.header__menu-item` : Items du menu avec animation hover

---

### 2. Hero (sections/hero-homme.liquid)

**Style** :
- Grande image pleine largeur
- Texte centré avec typographie Playfair Display
- CTA rectangulaire noir et blanc
- Animation fade + translateY au chargement

**Classes CSS** :
- `.hero-santiago` : Container hero
- `.hero-santiago-title` : Titre principal
- `.hero-santiago-subtitle` : Sous-titre
- `.hero-santiago-button` : Bouton CTA

**Animations** :
- `heroReveal` : Fade in + translateY pour titre, sous-titre et bouton

---

### 3. Collections (sections/collection-list-homme.liquid)

**Style** :
- Grid responsive (1 → 2 → 3 colonnes)
- Images avec bordure fine noire
- Hover : zoom léger (scale 1.04) + overlay blanc semi-transparent
- Titre centré sous l'image

**Breakpoints** :
- Mobile (≤480px) : 1 colonne
- Tablet (481-768px) : 2 colonnes
- Desktop (≥769px) : 3 colonnes

**Classes CSS** :
- `.collection-santiago-grid` : Grid container
- `.collection-santiago-item` : Item de collection avec hover

**Collections affichées** :
- Bottes & Bottines
- Chaussures de Ville
- Baskets & Espadrilles
- Chaussures Confort+
- Mocassins
- Sabots & Babouches
- Chaussures Classiques
- Portefeuille
- Sandales Homme

---

### 4. Cartes Produit (snippets/card-product.liquid)

**Style** :
- Image portrait 4:5
- Hover : zoom + ombre premium
- Nom du produit (typographie Playfair Display)
- Prix en noir
- Badge luxe si tag "haute_gamme"

**Classes CSS** :
- `.product-card-santiago` : Carte produit
- `.badge-luxe` : Badge "👑 Haute Gamme"

**Badge Luxe** :
```liquid
{%- if card_product.tags contains 'haute_gamme' -%}
  <span class="badge-luxe">👑 Haute Gamme</span>
{%- endif -%}
```

---

### 5. Page Produit (sections/main-product.liquid)

**Style** :
- Layout 2 colonnes desktop / 1 colonne mobile
- Grandes images avec miniatures
- Titre large serif
- Prix visible
- Bouton noir pleine largeur

**Classes CSS** :
- `.product-santiago-layout` : Layout principal
- `.product-santiago-gallery` : Galerie images
- `.product-santiago-info` : Informations produit
- `.product-santiago-button` : Bouton ajout panier

---

### 6. Section Avantages (sections/benefits.liquid)

**Nouvelle section** avec 4 avantages :
- Livraison Offerte
- Qualité Luxe
- Retour Simple
- Support Rapide

**Style** :
- Grid responsive (1 → 2 → 4 colonnes)
- Icônes noires SVG
- Texte centré

**Breakpoints** :
- Mobile (≤480px) : 1 colonne
- Tablet (481-768px) : 2 colonnes
- Desktop (≥769px) : 4 colonnes

---

### 7. Footer (sections/footer.liquid)

**Style** :
- Fond noir (`#231f20`)
- Texte blanc (`#ffffff`)
- 2-3 colonnes responsive
- Liens discrets avec hover

**Classes CSS** :
- `.footer-santiago` : Container footer
- `.footer-santiago-grid` : Grid colonnes
- `.footer-santiago-block` : Bloc de contenu

---

## 🎬 Animations

### IntersectionObserver (assets/global.js)

**Fonctionnalité** :
- Détecte les éléments avec classe `.reveal`
- Ajoute la classe `.revealed` quand l'élément entre dans le viewport
- Animation fade + translateY automatique

**Utilisation** :
```html
<div class="reveal">
  <!-- Contenu animé -->
</div>
```

### Header Scroll (assets/global.js)

**Fonctionnalité** :
- Ajoute la classe `.scrolled` au header après 50px de scroll
- Active l'ombre fine pour un effet premium

### Smooth Scroll (assets/global.js)

**Fonctionnalité** :
- Smooth scroll pour tous les liens d'ancres (`#`)

---

## 📱 Responsive

### Breakpoints
- **480px** : Petits téléphones
- **768px** : Tablettes portrait
- **1024px** : Tablettes paysage / petits laptops
- **1440px** : Écrans larges
- **4K** : Max-width 1600px centré

### Mobile-First
Tous les styles sont conçus en mobile-first avec des media queries `min-width`.

---

## 🎯 Classes CSS Utiles

### Typographie
- `.hero-santiago-title` : Titre hero premium
- `.product-card-santiago .card__heading` : Titre carte produit

### Layout
- `.collection-santiago-grid` : Grid collections
- `.product-santiago-layout` : Layout page produit
- `.benefits-santiago-grid` : Grid avantages

### Animations
- `.reveal` : Élément à animer au scroll
- `.revealed` : Élément animé (ajouté automatiquement)

### Boutons
- `.button-santiago` : Bouton style Santiago (noir/blanc)

---

## 🔧 Personnalisation

### Modifier les Couleurs
Toutes les couleurs sont définies dans `assets/base.css` :
- Rechercher `#231f20` pour le noir
- Rechercher `#ffffff` pour le blanc

### Modifier les Animations
Les animations sont dans :
- `assets/base.css` : Keyframes CSS
- `assets/global.js` : IntersectionObserver et scroll

### Ajouter une Nouvelle Section
1. Créer le fichier dans `sections/`
2. Ajouter les styles dans `assets/base.css` avec préfixe `.santiago-`
3. Utiliser les classes `.reveal` pour les animations

---

## 📝 Notes Importantes

1. **Couleurs strictes** : Utiliser uniquement `#231f20` et `#ffffff`
2. **Mobile-first** : Toujours commencer par le mobile
3. **Animations douces** : Transitions de 0.3s à 0.4s
4. **Typographie premium** : Playfair Display pour les titres
5. **Espacement généreux** : Padding et margins larges pour un look premium

---

## 🚀 Utilisation

1. **Header** : Configurer le menu dans Shopify Admin → Navigation
2. **Hero** : Ajouter la section "Hero Homme" dans le thème
3. **Collections** : Ajouter la section "Collection Homme"
4. **Avantages** : Ajouter la section "Avantages Santiago"
5. **Footer** : Configurer les blocs dans Shopify Admin → Footer

---

## 📞 Support

Pour toute question ou personnalisation, référez-vous aux commentaires dans le code ou consultez la documentation Shopify Theme Development.

---

**Style créé avec inspiration de santiago.ma** ✨

