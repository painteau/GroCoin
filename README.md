# 🪙 GroCoin
> *"a tiny blockchain for a big coin"*

[![Solidity](https://img.shields.io/badge/Solidity-0.8.27-blue)](https://soliditylang.org/)
[![BSC](https://img.shields.io/badge/BSC-BEP20-yellow)](https://www.binance.org/en/smartChain)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

GroCoin est un token déflationniste BEP20 avec mécanisme de reflection, construit sur la Binance Smart Chain.

---

## 📁 Structure du Projet

```
GroCoin/
├── contracts/          # Smart contracts Solidity
│   ├── grocoin.sol     # Contrat principal (v0.8.27)
│   └── grocoin.sol.backup  # Version originale (v0.7.4)
├── website/            # Site web GroCoin
│   ├── index.html      # Page principale
│   ├── grocoin.css     # Styles
│   ├── HO1736_prt.mp3  # Audio
│   └── images/         # Assets visuels
├── docs/               # Documentation
│   └── SECURITY_IMPROVEMENTS.md  # Guide des améliorations
├── README.md           # Ce fichier
└── LICENSE             # Licence MIT
```

---

## 🎯 Caractéristiques

### Token Details
- **Nom**: GroCoin
- **Symbole**: GRD
- **Décimales**: 10
- **Supply initiale**: 6,969,696,969 GRD
- **Blockchain**: Binance Smart Chain (BEP20)
- **Version Solidity**: 0.8.27

### Distribution initiale
- **69%** reste dans la GroBanque
- **31%** distribution publique

### Transaction Fees (1% total)
- **0.30%** (30/100) → Reflection automatique proportionnelle aux holders
- **0.69%** (69/100) → Burn automatique (déflationniste)
- **0.01%** (1/100) → Wallet du Président

---

## 🚀 Démarrage Rapide

### Smart Contract

Le contrat principal se trouve dans `/contracts/grocoin.sol`

```bash
# Compiler avec Solidity 0.8.27
solc --optimize --bin --abi contracts/grocoin.sol
```

### Site Web

Le site web est dans `/website/`

```bash
# Ouvrir directement
open website/index.html

# Ou servir avec un serveur local
cd website && python3 -m http.server 8000
```

---

## 📖 Documentation

- **[SECURITY_IMPROVEMENTS.md](docs/SECURITY_IMPROVEMENTS.md)**: Guide complet des améliorations de sécurité
- **Contrat README**: [contracts/README.md](contracts/README.md)
- **Website README**: [website/README.md](website/README.md)

---

## 🔒 Sécurité

Le contrat a été modernisé avec :
- ✅ Solidity 0.8.27 (protection overflow/underflow native)
- ✅ Implémentation complète des fees
- ✅ Events pour traçabilité
- ✅ Limites de gas optimisées
- ✅ Validations renforcées

⚠️ **Recommandation**: Audit de sécurité professionnel avant déploiement en production.

---

## 🌐 Liens

- **Telegram**: https://t.me/LeGroCoin
- **Website**: https://www.grocoin.info/
- **Twitter**: @Groland

---

## 📜 Licence

Ce projet est sous licence MIT. Voir [LICENSE](LICENSE) pour plus de détails.

---

## 🎪 Credits

*"Groland, je mourrirai pour toi"*
*RIP Salengro ❤️*

© 2021-2025 GroCoin Team
