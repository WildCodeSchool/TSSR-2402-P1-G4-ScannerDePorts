# Documentation générale 
### Présentation du projet et objectif finaux 
 **Objectif principal :**
Scanner les ports d’un serveur à partir d’un client et en déduire les failles de sécurité et les attaques possible. 

 **Objectif secondaire :**
Création de profils de scan personnalisés
### Membres du groupe de projet (rôles par sprint) 
***Semaine 1:*** 
|Nom|Rôles|taches|
|---|---|---|
|Ahmed|membre|Doc Admin|
|Nicolas C|membre|Doc Utilisateur Gratté nmap|
|Sébastien|Scrum Ma|VM, IP, Gratté nmap|
|Patrick|PO|DOC Général| 

***Semaine 2:***

|Nom|Rôles|taches|
|---|---|---|
|Ahmed|PO|Doc Admin|
|Nicolas C|Scrum M|Doc Utilisateur Gratté nmap|
|Sébastien|membre|VM, IP, Gratté nmap|
|Patrick|membre|DOC Général| 

### Choix techniques : quel OS, quelle version, etc.. 
**logiciels:** Nmap.
disponible sous toute les distributiuons.

**Serveur:** Debian 12.
- Nom : SRVLX01
- Compte : root
- Mot de passe : Azerty1*
- Adresse IP fixe : 172.16.10.10/24

**client:**
Ubuntu 22.04
- nom : CLILIN01
- Compte utilisateur : wilder
- Mot de passe : Azerty1*
- Adresse IP fixe : 172.16.10.20/24

Windows 10 
- Nom : CLIWIN02 
- Compte utilisatuer : wilder
- Mot de passe : Azerty1*
- Adresse IP fixe : 172.16.10.30/24

### Introduction : mise en contexte  
Dans un monde où la sécurité informatique est un point important au sein d'une sociéte ou d'un organisme, la nécessité de détecter et de contrer les menaces potentielles sur les réseaux est cruciale. L'un des moyens pour y arrive est le scan des ports. Pour se faire different outils sont utilisable tel que nmap ou netcat, mais nous utiliseront pricipalement ici nmap etant largement suffisant pour notre projet.

### Difficultés rencontrées : problèmes techniques rencontrés 
Concernant les problèmes rencontrés, au niveau du logiciel, aucun problème n'a été rencontré lors de l'installation mais on s'est retrouve vite embêté avec le script SSH brute-force qui ne se lance pas sous Ubuntu mais fonctionne sur Windows. Ensuite nous avons rencontré des difficultés avec la mise en réseau entre nos client et notre serveur debian. Et la reconnaissance des ports.

### Solutions trouvées : Solutions et alternatives trouvées 
Concernant le serveur Debian, nous avons dû configurer une adresse IP fixe. Pour ce faire, nous avons modifié le fichier /etc/network/interfaces. Ensuite, une fois nos machines reliées, nous avons dû ouvrir des ports afin de pouvoir les scanner, car par défaut, les 1000 ports que nous avons scannés étaient tous fermés.
### Améliorations possibles : suggestions d’améliorations futures 
Actuellement, nous travaillons sur la possibilité de créer des scans personnalisés, c'est-à-dire de pouvoir scanner des ports spécifiques ou une certaine plage de ports.

### Next step :
On vous a montré quelques commandes en guise d'introduction mais, beaucoup de terme technique et acronyme ont été passer sous silence our une meilleur comprehension de la démonstration.
Pour la suite,il serais bon de comprendre le tenant et les aboutisant de tout ces protocles et port, pour allez plus loin dans notre formation réseau.
