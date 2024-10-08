# Projet Exemple Hardhat

Ce projet illustre l'utilisation de Hardhat pour le développement Ethereum, incluant un contrat simple, des tests, et un script de déploiement.

## Structure du Projet

- **Contrat intelligent (Lock.sol)** : Verrouille des fonds jusqu'à une date spécifiée.
- **Tests (test/Lock.js)** : Vérifie le bon fonctionnement du contrat.
- **Déploiement (Ignition/Lock.js)** : Déploie le contrat sur un réseau blockchain.

## Configuration du Déploiement

1. **Configurer Metamask** :
    -  Obtenez une clé API sepolia en allant dans Metamask > détails du compte > affichez la clé privé, et confirmer.
    - Configurez votre clé API avec Hardhat :
    ```bash
    npx hardhat vars set SEPOLIA_PRIVATE_KEY=YOUR_SEPOLIA_PRIVATE_KEY
    ```

2. **Configurer Infura** :
    - Obtenez une clé API Infura en vous inscrivant sur [Infura](https://infura.io/).
    - Configurez votre clé API avec Hardhat :
      ```bash
      npx hardhat vars set INFURA_API_KEY=YOUR_INFURA_API_KEY
      ```

3. **Déploiement avec Ignition** :
    ```bash
    npx hardhat ignition deploy ./ignition/modules/Lock.js
    ```

4. **Configurer Metamask** :
    - **Ajouter un Réseau** :
        - Nom du réseau : Hardhat Local
        - Nouvelle URL RPC : http://127.0.0.1:8545
        - ID de la chaîne : 31337
        - Symbole de la devise : ETH
    - **Importer une Clé Privée** :
        - Copiez la clé privée d'un compte généré par `npx hardhat node`.
        - Dans Metamask : Paramètres > Importer un compte et collez la clé privée.


## Interagir avec le Contrat

Après le déploiement, vous pouvez interagir avec votre contrat via Metamask en utilisant l'interface de votre dApp ou en accédant à l'ABI du contrat.

- Envoyez des transactions pour verrouiller des fonds ou demander leur retrait à la date spécifiée par le contrat.