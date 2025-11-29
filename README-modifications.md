# 📋 Guide des Modifications - Thème Premium Minimaliste Homme

Ce document décrit toutes les modifications apportées au thème Shopify Dawn pour le transformer en une boutique premium minimaliste et luxueuse pour Homme, utilisant exclusivement les couleurs **#231f20** (noir) et **#ffffff** (blanc).

---

## 🎨 **1. MODIFICATIONS DU STYLE GLOBAL**

### **Fichier : `assets/base.css`**

**Variables CSS ajoutées :**
- `--brand-dark: #231f20` (noir)
- `--brand-light: #ffffff` (blanc)

**Styles ajoutés :**
- `body` : Fond blanc, texte noir, police Inter
- Boutons : Fond noir (#231f20), texte blanc, hover avec opacité réduite
- Cartes produits : Hover avec `transform: scale(1.04)` et ombre légère
- Badge haute gamme : Style `.badge-luxe` pour les produits avec tag "haute_gamme"

**Où modifier les couleurs :**
- Ligne ~9 : Variables `--brand-dark` et `--brand-light`
- Tous les styles utilisent ces variables pour une cohérence totale

---

## 🔝 **2. HEADER (Sticky & Navigation)**

### **Fichier : `sections/header.liquid`**

**Modifications apportées :**
- Header rendu **sticky** avec `position: sticky; top: 0; z-index: 1000;`
- Fond blanc forcé : `background-color: var(--brand-light) !important;`
- Navigation en noir : `color: var(--brand-dark) !important;`
- Animation underline sur hover des liens de navigation :
  - Animation `underlineExpand` : width de 0 à 100% en 0.3s

**Où modifier les textes de navigation :**
- Dans l'éditeur Shopify : **Thème > Navigation > Menu principal**
- Les modifications sont gérées via le système de menus Shopify

---

## 🏠 **3. SECTION HERO (Page d'Accueil)**

### **Fichier : `sections/hero-homme.liquid`** (NOUVEAU)

**Caractéristiques :**
- Section hero minimaliste full width
- Fond blanc ou image de fond optionnelle
- Titre large avec animation fade-in + translateY(10px)
- Bouton "Boutique Homme" avec animation décalée

**Où modifier :**
- Dans l'éditeur Shopify : **Thème > Sections > Hero Homme**
- Paramètres disponibles :
  - Titre
  - Label du bouton
  - Lien du bouton
  - Image de fond (optionnelle)
  - Overlay sombre (optionnel)

**Pour activer la section :**
1. Aller dans **Thème > Personnaliser**
2. Ajouter la section **"Hero Homme"** sur la page d'accueil
3. Configurer les paramètres selon vos besoins

---

## 📦 **4. SECTION COLLECTION HOMME**

### **Fichier : `sections/collection-list-homme.liquid`** (NOUVEAU)

**Collections créées :**
Cette section affiche automatiquement les collections suivantes (si elles existent dans votre boutique) :
- `bottes-bottines`
- `chaussures-de-ville`
- `baskets-espadrilles`
- `chaussures-confort`
- `mocassins`
- `sabots-babouches`
- `chaussures-classiques`
- `portefeuille`
- `sandales-homme`

**Caractéristiques :**
- Grid minimaliste 3 colonnes sur desktop
- Hover : zoom léger (scale 1.05) + fond blanc bordé #231f20
- Titre centré
- Animation reveal au scroll

**Où modifier :**
- Dans l'éditeur Shopify : **Thème > Sections > Collection Homme**
- Pour ajouter/modifier les collections affichées : Modifier la ligne 42 du fichier `collection-list-homme.liquid`

**Pour activer la section :**
1. Créer les collections dans **Produits > Collections** avec les handles exacts listés ci-dessus
2. Aller dans **Thème > Personnaliser**
3. Ajouter la section **"Collection Homme"** sur la page souhaitée

---

## 🏷️ **5. CARTE PRODUIT (Badge Haute Gamme)**

### **Fichier : `snippets/card-product.liquid`**

**Modifications apportées :**
- Badge "👑 Haute Gamme" ajouté pour les produits avec le tag `haute_gamme`
- Hover : Scale 1.04 (défini dans `base.css`)
- Style du badge : Fond noir, texte blanc, padding 3px 8px

**Où gérer les badges haute_gamme :**
1. Dans **Produits > Produits**
2. Sélectionner un produit
3. Dans la section **Tags**, ajouter le tag : `haute_gamme`
4. Le badge apparaîtra automatiquement sur la carte produit

**CSS du badge :**
```css
.badge-luxe {
  background: var(--brand-dark);
  color: var(--brand-light);
  padding: 3px 8px;
  border-radius: 4px;
  font-size: 11px;
}
```

---

## 📄 **6. PAGE PRODUIT**

### **Fichiers modifiés :**
- `sections/main-product.liquid` (structure existante)
- `assets/base.css` (styles boutons)

**Modifications apportées :**
- Bouton "Ajouter au panier" : Fond noir (#231f20), texte blanc, pleine largeur
- Lazy-loading : Activé par défaut sur toutes les images (déjà présent dans Dawn)

**Où modifier :**
- Les images produits sont gérées via la galerie produit dans l'éditeur Shopify
- Les boutons utilisent automatiquement le style défini dans `base.css`

**Pour activer le lazy-loading :**
- Déjà activé par défaut dans le thème Dawn
- Toutes les images ont `loading="lazy"` sauf la première

---

## 🛒 **7. CART DRAWER (Panier latéral)**

### **Fichiers modifiés :**
- `snippets/cart-drawer.liquid` (structure)
- `assets/component-cart-drawer.css` (styles)

**Modifications apportées :**
- Fond blanc : `background-color: #ffffff`
- Bord gris léger : `border-color: rgba(35, 31, 32, 0.2)`
- Animation slide : `transition: transform 0.35s ease`
- Bouton Checkout : Fond noir, texte blanc, pleine largeur

**Où modifier :**
- Les styles sont dans `component-cart-drawer.css`
- Le contenu du panier est géré automatiquement par Shopify

---

## ✨ **8. ANIMATIONS REVEAL**

### **Fichier : `assets/animations.js`** (MODIFIÉ)

**Fonctionnalité ajoutée :**
- IntersectionObserver pour animer les éléments avec la classe `.reveal`
- Animation : Opacité 0→1 et translateY(12px)→0
- CSS injecté dynamiquement pour les styles de transition

**Utilisation :**
- Ajouter la classe `reveal` à n'importe quel élément HTML
- L'animation se déclenchera automatiquement quand l'élément entre dans le viewport

**Exemple :**
```html
<div class="reveal">
  Contenu qui s'anime au scroll
</div>
```

**Où modifier :**
- Le code se trouve dans `assets/animations.js` (lignes ~95-120)
- Les styles CSS sont injectés automatiquement

---

## 📝 **9. RÉSUMÉ DES FICHIERS MODIFIÉS**

| Fichier | Type de Modification |
|---------|---------------------|
| `assets/base.css` | ✅ Styles globaux, variables couleurs, cartes produits, badges |
| `sections/header.liquid` | ✅ Header sticky, styles navigation, animation underline |
| `sections/hero-homme.liquid` | ✨ NOUVEAU - Section hero avec animation |
| `sections/collection-list-homme.liquid` | ✨ NOUVEAU - Grid collections 3 colonnes |
| `snippets/card-product.liquid` | ✅ Badge haute_gamme ajouté |
| `assets/component-cart-drawer.css` | ✅ Styles fond blanc, bord gris, bouton checkout noir |
| `assets/animations.js` | ✅ Animation reveal ajoutée |

---

## 🚀 **10. POUR APPLIQUER DANS SHOPIFY**

### **Étape 1 : Télécharger les fichiers modifiés**
1. Ouvrir l'éditeur Shopify en ligne
2. Aller dans **Thème > Actions > Télécharger le thème** (backup d'abord !)
3. Remplacer les fichiers modifiés dans le thème téléchargé

### **Étape 2 : Re-uploader le thème**
1. Aller dans **Thème > Actions > Télécharger un thème**
2. Sélectionner le dossier avec les modifications
3. Attendre la compilation

### **Étape 3 : Activer les nouvelles sections**
1. Aller dans **Thème > Personnaliser**
2. Ajouter la section **"Hero Homme"** sur la page d'accueil
3. Ajouter la section **"Collection Homme"** où souhaité

### **Étape 4 : Configurer les collections**
1. Créer les collections avec les handles exacts :
   - `bottes-bottines`
   - `chaussures-de-ville`
   - `baskets-espadrilles`
   - `chaussures-confort`
   - `mocassins`
   - `sabots-babouches`
   - `chaussures-classiques`
   - `portefeuille`
   - `sandales-homme`

### **Étape 5 : Ajouter le tag haute_gamme**
1. Pour chaque produit premium, ajouter le tag : `haute_gamme`
2. Le badge apparaîtra automatiquement

---

## 🎯 **11. RÉGLAGES IMPORTANTS**

### **Couleurs**
- ✅ **Aucune modification manuelle nécessaire** - Tous les styles utilisent les variables CSS `--brand-dark` et `--brand-light`
- Si vous devez changer les couleurs, modifier uniquement les lignes 11-12 dans `assets/base.css`

### **Polices**
- Police principale : **Inter** (définie dans `base.css`)
- Fallback : `system-ui, sans-serif`

### **Responsive**
- ✅ Toutes les modifications sont **mobile-first** et responsive
- Les grid s'adaptent automatiquement (3 colonnes desktop → 2 tablette → 1 mobile)

---

## ⚠️ **12. NOTES IMPORTANTES**

1. **Backup** : Toujours faire un backup avant d'uploader les modifications
2. **Couleurs strictes** : Seules les couleurs #231f20 et #ffffff sont autorisées (sauf opacité)
3. **Tags produits** : Le tag `haute_gamme` doit être exactement écrit ainsi (minuscules, underscore)
4. **Handles collections** : Les handles des collections doivent correspondre exactement à ceux listés
5. **Animations** : Respecte `prefers-reduced-motion` pour l'accessibilité

---

## 📞 **13. SUPPORT**

Pour toute question ou modification supplémentaire :
- Vérifier que tous les fichiers sont correctement uploadés
- Vérifier les handles des collections
- Vérifier les tags des produits
- Vérifier que les sections sont activées dans l'éditeur Shopify

---

**Version** : 1.0  
**Date** : Novembre 2025  
**Thème de base** : Shopify Dawn

