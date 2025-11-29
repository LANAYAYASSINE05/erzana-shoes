# 📦 Produits de Démonstration Premium

Ce dossier contient 25 produits de démonstration premium pour visualiser le thème Santiago sur votre boutique Shopify.

---

## 📋 Contenu

- **`products_demo.csv`** : Fichier CSV prêt à importer dans Shopify (25 produits)
- **`products.json`** : Version JSON des produits (pour référence)

---

## 🚀 Import dans Shopify

### Étape 1 : Préparer les Collections

Avant d'importer les produits, assurez-vous que les collections suivantes existent dans Shopify :

1. **Bottes & Bottines**
2. **Chaussures de Ville**
3. **Baskets & Espadrilles**
4. **Chaussures Confort+**
5. **Mocassins**
6. **Sabots & Babouches**
7. **Chaussures Classiques**
8. **Portefeuille**
9. **Sandales Homme**

**Créer les collections :**
1. Allez dans Shopify Admin → **Produits** → **Collections**
2. Cliquez sur **Créer une collection**
3. Créez chaque collection avec le nom exact ci-dessus
4. Type : **Manuel** ou **Automatique** (selon vos préférences)

---

### Étape 2 : Importer le CSV

1. **Téléchargez le fichier** `products_demo.csv` depuis ce dossier
2. Allez dans Shopify Admin → **Produits**
3. Cliquez sur **Importer** (en haut à droite)
4. Cliquez sur **Ajouter un fichier** et sélectionnez `products_demo.csv`
5. Cliquez sur **Télécharger et continuer**
6. Vérifiez le prévisualisation des produits
7. Cliquez sur **Importer les produits**

**⚠️ Important :**
- Les produits seront automatiquement assignés aux collections correspondantes
- Les images placeholder seront importées depuis les URLs (via.placeholder.com)
- Vous pourrez remplacer les images plus tard

---

### Étape 3 : Vérifier l'Import

Après l'import, vérifiez :

1. ✅ Les 25 produits sont bien importés
2. ✅ Chaque produit est dans la bonne collection
3. ✅ Les tags sont corrects (nouveaute, tendance, haute_gamme)
4. ✅ Les variantes (tailles 40-44) sont créées
5. ✅ Les prix sont corrects (449-1199 MAD)

---

## 🖼️ Remplacer les Images Placeholder

Les produits utilisent actuellement des images placeholder depuis `via.placeholder.com`. Pour les remplacer :

### Option 1 : Via Shopify Admin

1. Allez dans **Produits** → Sélectionnez un produit
2. Dans la section **Médias**, cliquez sur **Ajouter des images**
3. Téléchargez vos images premium
4. Supprimez l'image placeholder
5. Répétez pour tous les produits

### Option 2 : Via CSV (Re-import)

1. Modifiez le fichier `products_demo.csv`
2. Remplacez les URLs `https://via.placeholder.com/...` par vos URLs d'images
3. Ré-importez le CSV (Shopify mettra à jour les produits existants)

**Format d'image recommandé :**
- Taille : 1200x1500px (ratio 4:5)
- Format : JPG ou PNG
- Poids : < 500KB par image
- Fond : Blanc (#ffffff) ou Noir (#231f20)

---

## 🏷️ Tags et Filtres

Les produits incluent les tags suivants :

- **`nouveaute`** : Produits nouveaux (8 produits)
- **`tendance`** : Produits tendance (10 produits)
- **`haute_gamme`** : Produits premium (12 produits)
- **Tags de collection** : `bottes-bottines`, `chaussures-de-ville`, etc.

**Utiliser les tags pour filtrer :**
- Créez des collections automatiques basées sur les tags
- Utilisez les tags dans les sections de thème (ex: "Nouveautés")

---

## 📊 Répartition des Produits

| Collection | Nombre de Produits |
|------------|-------------------|
| Bottes & Bottines | 2 |
| Chaussures de Ville | 2 |
| Baskets & Espadrilles | 2 |
| Chaussures Confort+ | 1 |
| Mocassins | 1 |
| Sabots & Babouches | 1 |
| Chaussures Classiques | 1 |
| Portefeuille | 2 |
| Sandales Homme | 1 |
| **TOTAL** | **13 produits uniques** |

*Note : Chaque produit a 5 variantes de taille (40-44), soit 65 variantes au total.*

---

## 🎨 Caractéristiques des Produits

### Prix
- **Minimum** : 449 MAD (Espadrille)
- **Maximum** : 899 MAD (Chaussure Classique)
- **Prix moyen** : ~650 MAD

### Couleurs
- **Noir** (#231f20) : 11 produits
- **Blanc** (#ffffff) : 2 produits

### Tailles
- Toutes les tailles de 40 à 44 sont disponibles pour chaque chaussure

### Descriptions
- Chaque produit a une description premium de 100-150 mots
- Style inspiré de santiago.ma
- Vocabulaire luxe : "premium", "élégant", "savoir-faire artisanal", etc.

---

## 🔧 Personnalisation

### Modifier les Produits

1. **Via Shopify Admin** : Modifiez directement les produits importés
2. **Via CSV** : Modifiez `products_demo.csv` et ré-importez

### Ajouter des Produits

Pour ajouter plus de produits :

1. Ouvrez `products_demo.csv`
2. Ajoutez une nouvelle ligne avec le même format
3. Assurez-vous que la collection existe
4. Ré-importez le CSV

**Format de ligne :**
```csv
"Nom Produit","Description HTML",Erzana Homme,Type,"tags",TRUE,Taille,40,Couleur,Noir,599,799,"URL Image",1,"Collection"
```

---

## 📱 Afficher les Nouveautés sur la Page d'Accueil

Pour afficher les produits "Nouveautés" sur la page d'accueil :

1. Allez dans **Boutique en ligne** → **Thèmes** → **Personnaliser**
2. Sur la page d'accueil, ajoutez une section **Collection mise en avant**
3. Sélectionnez une collection ou créez une collection automatique avec le tag `nouveaute`
4. Configurez l'affichage (nombre de produits, grille, etc.)

**Collection automatique "Nouveautés" :**
- Type : Automatique
- Condition : Tag est égal à `nouveaute`

---

## ⚠️ Notes Importantes

1. **Images Placeholder** : Les images actuelles sont des placeholders. Remplacez-les par de vraies photos premium.

2. **Collections** : Les collections doivent exister AVANT l'import, sinon les produits ne seront pas assignés.

3. **Prix en MAD** : Les prix sont en Dirhams marocains. Ajustez selon votre devise.

4. **Stock** : Par défaut, les produits n'ont pas de stock défini. Configurez le stock dans Shopify Admin.

5. **SEO** : Les handles sont générés automatiquement. Vous pouvez les personnaliser dans Shopify Admin.

---

## 🆘 Support

Si vous rencontrez des problèmes lors de l'import :

1. Vérifiez que le format CSV est correct (UTF-8)
2. Assurez-vous que toutes les collections existent
3. Vérifiez que les noms de collections correspondent exactement
4. Consultez la documentation Shopify : [Importer des produits](https://help.shopify.com/fr/manual/products/import-export/using-csv)

---

## 📝 Fichiers Générés

- ✅ `products_demo.csv` : 25 produits prêts à importer
- ✅ `products.json` : Version JSON (référence)
- ✅ `README-demo-products.md` : Ce fichier

---

**Bon import ! 🚀**

