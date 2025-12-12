# 📜 GroCoin Smart Contracts

Ce dossier contient les smart contracts du projet GroCoin.

---

## 📁 Fichiers

### `grocoin.sol` (Version actuelle)
- **Version Solidity**: 0.8.27
- **Standard**: BEP20 (Binance Smart Chain)
- **Statut**: ✅ Modernisé et sécurisé

**Améliorations apportées**:
- Migration vers Solidity 0.8.27 (protection overflow/underflow native)
- Suppression de SafeMath (-166 lignes)
- Implémentation complète de la taxe Président
- Events ajoutés pour traçabilité
- Validations renforcées
- Optimisations gas

### `grocoin.sol.backup` (Version originale)
- **Version Solidity**: 0.7.4
- **Statut**: ⚠️ Archive (obsolète)
- **Utilité**: Référence historique et comparaison

---

## 🔧 Compilation

### Prérequis
```bash
# Installer Solidity 0.8.27
npm install -g solc@0.8.27
```

### Compiler le contrat
```bash
solc --optimize --optimize-runs 200 --bin --abi contracts/grocoin.sol -o build/
```

### Avec Hardhat
```bash
npx hardhat compile
```

### Avec Foundry
```bash
forge build
```

---

## 🚀 Déploiement

### Configuration initiale
Au déploiement, le contrat :
1. Attribue tout le supply au déployeur
2. Définit le déployeur comme président (wallet recevant la taxe)
3. Émet un event Transfer initial

### Fonctions à configurer après déploiement
```solidity
// Changer le wallet du président (optionnel)
setPresidentWallet(address newWallet) // onlyOwner

// Exclure des adresses des fees (ex: pool de liquidité)
excludeAccount(address account) // onlyOwner

// Réinclure une adresse
includeAccount(address account) // onlyOwner
```

---

## 📊 Caractéristiques du Token

| Paramètre | Valeur |
|-----------|--------|
| Nom | GroCoin |
| Symbole | GRD |
| Décimales | 10 |
| Supply totale | 6,969,696,969 GRD |
| Max transaction | 6,969,696,969 GRD |
| Max exclusions | 100 comptes |

---

## 💰 Structure des Fees

Pour une transaction de 1000 GRD :
- **Reflection**: 3 GRD (0.30%) → Redistribué aux holders
- **Burn**: 6.9 GRD (0.69%) → Brûlé définitivement
- **Président**: 0.1 GRD (0.01%) → Wallet du président
- **Reçu**: ~990 GRD

**Calcul**:
```solidity
tFee = (amount * 30) / 100 / 100 = 0.30%
tBurn = (amount * 69) / 100 / 100 = 0.69%
tPresident = (amount * 1) / 100 / 100 = 0.01%
```

---

## 🔐 Fonctions de Sécurité

### Modifiers
- `onlyOwner()`: Restreint aux propriétaire du contrat

### Validations
- Vérification `address(0)` sur toutes les fonctions critiques
- Limite de comptes exclus (MAX_EXCLUDED = 100)
- Protection overflow/underflow native (Solidity 0.8.x)

### Events
```solidity
event Transfer(address indexed from, address indexed to, uint256 value)
event Approval(address indexed owner, address indexed spender, uint256 value)
event OwnershipTransferred(address indexed previousOwner, address indexed newOwner)
event PresidentWalletChanged(address indexed previousWallet, address indexed newWallet)
event AccountExcluded(address indexed account)
event AccountIncluded(address indexed account)
```

---

## 🧪 Tests Recommandés

Avant déploiement en production, tester :

1. **Transfers basiques**
   - Transfer entre deux comptes standard
   - Transfer avec compte exclus
   - Transfer vers/depuis le président

2. **Calcul des fees**
   - Vérifier les montants de reflection
   - Vérifier les montants de burn
   - Vérifier les montants président

3. **Fonctions admin**
   - setPresidentWallet()
   - excludeAccount()
   - includeAccount()
   - transferOwnership()

4. **Cas limites**
   - Transfer de 0
   - Transfer du total supply
   - Max exclusions atteint
   - Division par zéro (protection native)

---

## 📚 Documentation

- **Guide complet**: [../docs/SECURITY_IMPROVEMENTS.md](../docs/SECURITY_IMPROVEMENTS.md)
- **README principal**: [../README.md](../README.md)

---

## ⚠️ Avertissements

1. **Audit recommandé**: Faites auditer le contrat avant production
2. **Tests unitaires**: Écrivez des tests complets
3. **Gas limit**: Attention aux transactions avec beaucoup d'exclusions
4. **Irréversibilité**: Les transactions blockchain sont irréversibles

---

## 📞 Support

- **Issues**: Reportez les bugs sur GitHub
- **Telegram**: https://t.me/LeGroCoin
- **Twitter**: @Groland

---

*Vive Groland! 🎪*
