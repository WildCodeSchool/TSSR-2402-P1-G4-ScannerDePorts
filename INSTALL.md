### Documentation administrative de Nmap

#### Prérequis techniques :

- **Système d'exploitation :**
  - Debian 12 ou Windows serveur 2022 (pour l'installation sur un serveur)
  - Windows 10 ou Ubuntu (pour l'installation sur un client)
  - connexion réseau fonctionnelle entre le clien et le serveur
  
- **Accès administrateur sur les systèmes pour installer et configurer le logiciel.**

- **Connexion Internet active pour télécharger les packages nécessaires.**

#### Étapes d'installation et de configuration sur Debian/Ubuntu :

1. **Téléchargement et installation de Nmap :**
    ```bash
    sudo apt update
    sudo apt install nmap
    ```

2. **Vérification de l'installation :**
    ```bash
    nmap --version
    ```
#### Étapes d'installation et de configuration sur Windows 10 :

1. **Téléchargement de Nmap :**
   - Téléchargez le programme d'installation depuis le site officiel de Nmap : [https://nmap.org/download.html](https://nmap.org/download.html)

2. **Installation de Nmap :**
   - Double-cliquez sur le fichier d'installation téléchargé et suivez les instructions à l'écran.

4. **Vérification de l'installation :**
   - Ouvrez l'invite de commandes (CMD) et exécutez la commande :
     ```cmd
     nmap --version
     ```
