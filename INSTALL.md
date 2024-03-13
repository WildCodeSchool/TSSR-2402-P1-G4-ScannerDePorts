**Nmap (Network Mapper) est un outil de découverte de réseau et de sécurité très puissant et polyvalent. Voici comment l'installer sur une distribution Linux en général :**

1. **Utilisation du gestionnaire de paquets** : La plupart des distributions Linux disposent d'un gestionnaire de paquets qui facilite grandement l'installation de logiciels. Pour installer Nmap, vous pouvez ouvrir un terminal et exécuter la commande suivante :

   - Pour les distributions basées sur Debian (comme Ubuntu) :

     ```
     sudo apt install nmap
     ```

   - Pour les distributions basées sur Red Hat (comme Fedora) :

     ```
     sudo dnf install nmap
     ```

   - Pour les distributions basées sur Arch Linux (comme Manjaro) :

     ```
     sudo pacman -Sy nmap
     ```

2. **Authentification** : Lorsque vous exécutez l'installation via le gestionnaire de paquets, le système peut vous demander votre mot de passe pour l'authentification.

3. **Attendre la fin de l'installation** : Une fois que vous avez entré votre mot de passe, le gestionnaire de paquets commencera à télécharger et à installer Nmap ainsi que toutes les dépendances nécessaires. Attendez que le processus soit terminé.

4. **Vérifier l'installation** : Une fois l'installation terminée, vous pouvez vérifier si Nmap a été installé correctement en exécutant la commande suivante dans le terminal :

   ```
   nmap --version
   ```

   Cette commande devrait afficher la version de Nmap installée sur votre système.

5. **Utilisation de Nmap** : Vous pouvez maintenant utiliser Nmap en tapant simplement `nmap` suivi des options appropriées dans le terminal. Par exemple :

   ```
   nmap -sP 192.168.1.0/24
   ```

   Cela va scanner les hôtes sur le réseau local pour voir s'ils sont en ligne.

 Vous avez maintenant installé et configuré Nmap sur votre système Linux et vous êtes prêt à l'utiliser pour explorer et sécuriser votre réseau.
