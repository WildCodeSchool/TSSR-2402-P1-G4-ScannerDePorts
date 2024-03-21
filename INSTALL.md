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

# Guide d'installation de Nmap sur Windows

1. **Téléchargement de Nmap :**

   - Allez sur le [lien de téléchargement de Nmap](https://nmap.org/download.html) et téléchargez la dernière version stable.

2. **Lancement de l'installation :**

   - Accédez à l'emplacement où le fichier est téléchargé.
   - Cliquez avec le bouton droit sur le fichier EXE et sélectionnez "Exécuter en tant qu'administrateur.
   - ![Étape 1](https://geekflare.com/cdn-cgi/image/width=617,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/run-as-administrator.png)

3. **Acceptation du contrat de licence :**

   - Cela démarrera le processus d'installation, suivez les instructions à l'écran et acceptez le contrat de licence.
   - ![Étape 3](https://geekflare.com/cdn-cgi/image/width=802,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/nmap-agreement.png)

4. **Choix des composants :**

   - Vous pouvez choisir les composants à installer, cependant, il est recommandé d'installer tous les composants.
   - ![Étape 4](https://geekflare.com/cdn-cgi/image/width=802,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/nmap-components.png)

5. **Emplacement d'installation :**

   - Par défaut, Nmap s'installera sous `C:\Program Files (x86)\Nmap`, mais vous pouvez changer l'emplacement si nécessaire.
   - ![Étape 5](https://geekflare.com/cdn-cgi/image/width=802,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/nmap-installation-location.png)

6. **Installation de Nmap :**

   - Le processus d'installation de Nmap débutera automatiquement.

7. **Confirmation de l'installation :**

   - Une fois l'installation terminée, vous recevrez une confirmation.
   - ![Étape 6](https://geekflare.com/cdn-cgi/image/width=802,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/nmap-installed.png)

8. **Fin de l'installation :**

   - Félicitations ! Nmap est maintenant installé avec succès sur votre système.
   - ![Étape 8](https://geekflare.com/cdn-cgi/image/width=704,quality=90,gravity=auto,sharpen=1,metadata=none,format=auto,onerror=redirect/wp-content/uploads/2017/10/nmap.png)
