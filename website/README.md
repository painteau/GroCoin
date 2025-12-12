# 🌐 GroCoin Website

Site web officiel de GroCoin - Interface humoristique et rétro pour présenter le projet.

---

## 📁 Structure

```
website/
├── index.html          # Page principale
├── grocoin.css         # Feuille de styles
├── HO1736_prt.mp3      # Musique d'ambiance
└── images/             # Assets visuels
    ├── LOGO_GRD*.png   # Logos en différentes tailles
    ├── groland.jpg     # Image de fond
    ├── bitcoin.gif     # Animation
    ├── UFO3.gif        # Curseur personnalisé
    └── ...
```

---

## 🎨 Design & Style

Le site web adopte un style **rétro/kitsch** volontaire, en accord avec l'esprit humoristique de Groland :

- ✨ Animations clignotantes
- 🎵 Auto-play musical
- 🖱️ Curseurs personnalisés (UFO)
- 🎪 Esthétique délibérément chaotique
- 🌈 Couleurs vives et contrastées

---

## 🚀 Utilisation

### Ouvrir localement

**Option 1 : Directement dans le navigateur**
```bash
open index.html
# ou
xdg-open index.html
```

**Option 2 : Serveur local Python**
```bash
cd website
python3 -m http.server 8000
# Puis ouvrir http://localhost:8000
```

**Option 3 : Serveur local Node.js**
```bash
cd website
npx http-server -p 8000
```

### Déployer en production

**GitHub Pages**
```bash
# Le dossier website peut être déployé sur GitHub Pages
# Configuration : Settings > Pages > Source : /website
```

**Netlify**
```bash
# Glisser-déposer le dossier website sur netlify.com
# Ou connecter le repo GitHub
```

**Serveur web classique**
```bash
# Copier le contenu vers votre serveur
scp -r website/* user@server:/var/www/html/
```

---

## 🎵 Audio

Le fichier `HO1736_prt.mp3` est joué automatiquement au chargement de la page.

**Contrôler l'audio**:
```html
<!-- Dans index.html, modifier les attributs -->
<audio autoplay loop controls>  <!-- autoplay = lecture auto -->
```

---

## 🖼️ Images

### Logos disponibles
- `LOGO_GRD.png` (originale)
- `LOGO_GRD_128.png` (128x128)
- `LOGO_GRD_32.png` (32x32 - favicon)
- `LOGO_GRD.psd` (source Photoshop - 2 MB)

### Optimisation recommandée
```bash
# Compresser les images pour le web
pngquant images/*.png
jpegoptim images/*.jpg
```

---

## 📱 Responsive

Le site actuel n'est **pas responsive**. Pour l'adapter au mobile :

```css
/* Ajouter dans grocoin.css */
@media screen and (max-width: 768px) {
  body {
    font-size: 14px;
  }

  img {
    max-width: 100%;
    height: auto;
  }
}
```

---

## 🔗 Liens externes

Le site contient des liens vers :
- **Twitter**: @Groland
- **Telegram**: https://t.me/LeGroCoin
- **Google Form**: Inscription GroBanque
- **YouTube**: Contenu Groland

**Vérifier les liens** avant déploiement :
```bash
# Tester les liens avec
grep -r "href=" index.html
```

---

## ⚡ Performance

### Optimisations possibles

1. **Lazy loading des images**
```html
<img src="image.jpg" loading="lazy">
```

2. **Compression audio**
```bash
# Réduire la taille du MP3
ffmpeg -i HO1736_prt.mp3 -b:a 128k HO1736_prt_compressed.mp3
```

3. **Minification CSS**
```bash
# Minifier le CSS
csso grocoin.css -o grocoin.min.css
```

---

## 🎯 Fonctionnalités

### Actuelles
- ✅ Page d'accueil avec présentation
- ✅ Liens sociaux (Twitter, Telegram)
- ✅ Formulaire d'inscription GroBanque
- ✅ Musique d'ambiance
- ✅ Animations et effets visuels

### À ajouter (suggestions)
- 📊 Widget de prix en temps réel
- 📈 Graphique de supply/burn
- 💰 Calculateur de reflection rewards
- 🔗 Lien vers explorateur blockchain (BscScan)
- 📝 FAQ section
- 🌍 Sélection de langue (FR/EN)

---

## 🛠️ Maintenance

### Fichiers à mettre à jour régulièrement
- Liens sociaux (si changement)
- Adresse du contrat (après déploiement)
- Prix/statistiques (si affichées)

### Checklist de déploiement
- [ ] Tester tous les liens
- [ ] Vérifier l'audio (volume, autoplay)
- [ ] Optimiser les images
- [ ] Tester sur mobile
- [ ] Vérifier les fautes de frappe
- [ ] Configurer le SEO (meta tags)

---

## 🔍 SEO

Améliorer le référencement en ajoutant dans `<head>` :

```html
<!-- Meta tags pour SEO -->
<meta name="description" content="GroCoin - Un token déflationniste BEP20 avec mécanisme de reflection">
<meta name="keywords" content="GroCoin, GRD, BEP20, BSC, crypto, token">
<meta property="og:title" content="GroCoin - Official Website">
<meta property="og:description" content="A tiny blockchain for a big coin">
<meta property="og:image" content="images/LOGO_GRD.png">
```

---

## 🎪 Style Guide

### Couleurs
Analyser les couleurs actuelles du site et documenter :
```css
/* À extraire de grocoin.css */
--primary-color: #...;
--secondary-color: #...;
--text-color: #...;
```

### Polices
Documenter les polices utilisées pour cohérence future.

---

## 📞 Support

Pour toute question sur le site web :
- **Issues GitHub**: Reportez les bugs
- **Telegram**: https://t.me/LeGroCoin

---

*Vive Groland! 🎪*
