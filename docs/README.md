# 📚 Documentation GroCoin

Ce dossier contient toute la documentation technique du projet GroCoin.

---

## 📁 Fichiers

### `SECURITY_IMPROVEMENTS.md`
Guide complet des améliorations de sécurité apportées au smart contract.

**Contenu**:
- Migration Solidity 0.7.4 → 0.8.27
- Corrections de bugs
- Implémentation taxe Président
- Optimisations gas
- Events ajoutés
- Validations renforcées
- Checklist de sécurité

**Public cible**: Développeurs, auditeurs, utilisateurs techniques

---

## 📖 Documentation Complète

### Structure de la documentation

```
docs/
├── README.md                      # Ce fichier
└── SECURITY_IMPROVEMENTS.md       # Guide des améliorations
```

---

## 🎯 Guides Rapides

### Pour les Développeurs

1. **Comprendre le contrat**
   - Lire [SECURITY_IMPROVEMENTS.md](SECURITY_IMPROVEMENTS.md)
   - Voir [../contracts/README.md](../contracts/README.md)
   - Analyser le code dans `/contracts/`

2. **Deployer le contrat**
   - Compiler avec Solidity 0.8.27
   - Tester sur testnet (BSC Testnet)
   - Audit de sécurité recommandé
   - Déployer sur mainnet

3. **Contribuer**
   - Fork le projet
   - Créer une branche feature
   - Soumettre une pull request

### Pour les Auditeurs

Points d'attention lors de l'audit :

1. **Mécanisme de reflection**
   - Vérifier les calculs de `_getRate()`
   - Tester `_getCurrentSupply()` avec beaucoup d'exclusions
   - Valider les arrondis dans les divisions

2. **Gestion des fees**
   - Vérifier `_getTValues()` et `_getRValues()`
   - Tester tous les scénarios de transfer
   - Valider que 30% + 69% + 1% = 100%

3. **Contrôles d'accès**
   - Vérifier `onlyOwner()` sur fonctions critiques
   - Tester `setPresidentWallet()`
   - Valider `excludeAccount()` / `includeAccount()`

4. **Limites et validations**
   - Tester `MAX_EXCLUDED` (100 comptes)
   - Vérifier `MAX_TX_SIZE`
   - Valider protection `address(0)`

### Pour les Utilisateurs

**Questions fréquentes**:

**Q: Comment fonctionnent les rewards de reflection ?**
R: À chaque transaction, 0.30% est redistribué proportionnellement à tous les holders. Pas besoin de claim, c'est automatique.

**Q: Les tokens sont-ils brûlés définitivement ?**
R: Oui, 0.69% de chaque transaction est envoyé à l'adresse de burn, réduisant le supply total.

**Q: Qui est le "Président" ?**
R: Le wallet du président reçoit 0.01% de chaque transaction. Par défaut c'est le déployeur, mais peut être changé par le owner.

**Q: Puis-je être exclu des fees ?**
R: Seul le owner peut exclure des comptes (ex: pools de liquidité). Maximum 100 comptes exclus.

---

## 📊 Ressources Additionnelles

### Outils recommandés

**Pour l'analyse**:
- [Remix IDE](https://remix.ethereum.org/) - IDE Solidity en ligne
- [BscScan](https://bscscan.com/) - Explorateur BSC
- [Slither](https://github.com/crytic/slither) - Analyseur statique

**Pour les tests**:
- [Hardhat](https://hardhat.org/) - Framework de développement
- [Foundry](https://getfoundry.sh/) - Suite d'outils Solidity
- [Tenderly](https://tenderly.co/) - Simulation de transactions

**Pour l'audit**:
- [MythX](https://mythx.io/) - Analyse de sécurité
- [Certik](https://www.certik.com/) - Audit professionnel
- [OpenZeppelin Defender](https://openzeppelin.com/defender/) - Monitoring

---

## 🔐 Sécurité

### Bonnes pratiques

1. **Avant déploiement**
   - ✅ Tests unitaires complets
   - ✅ Tests d'intégration
   - ✅ Audit de sécurité externe
   - ✅ Vérification sur testnet
   - ✅ Timelock sur fonctions admin (optionnel)

2. **Après déploiement**
   - ✅ Vérifier le code source sur BscScan
   - ✅ Renouncer l'ownership si approprié
   - ✅ Monitoring des transactions
   - ✅ Plan de réponse aux incidents

### Reporting de vulnérabilités

Si vous découvrez une vulnérabilité :

1. **NE PAS** la divulguer publiquement
2. Contacter l'équipe en privé via Telegram
3. Attendre un correctif avant publication
4. Possibilité de bug bounty (à déterminer)

---

## 📝 Changelog

### Version 2.0 (Décembre 2025)
- ✅ Migration Solidity 0.8.27
- ✅ Implémentation taxe Président
- ✅ Corrections bugs
- ✅ Optimisations gas
- ✅ Events ajoutés

### Version 1.0 (2021)
- ✅ Contrat initial Solidity 0.7.4
- ✅ Mécanisme de reflection
- ✅ Burn automatique

---

## 🤝 Contribution

Pour contribuer à la documentation :

1. **Améliorer la doc existante**
   - Corriger les fautes
   - Ajouter des exemples
   - Clarifier les explications

2. **Ajouter de nouveaux guides**
   - Guide de déploiement détaillé
   - Tutoriel pour holders
   - Guide d'audit complet

3. **Traductions**
   - Version anglaise
   - Autres langues

---

## 📞 Contact

- **Telegram**: https://t.me/LeGroCoin
- **Twitter**: @Groland
- **GitHub**: Issues et Pull Requests

---

## 📄 Licence

Toute la documentation est sous licence MIT, comme le reste du projet.

---

*"Groland, je mourrirai pour toi"*
*RIP Salengro ❤️*
