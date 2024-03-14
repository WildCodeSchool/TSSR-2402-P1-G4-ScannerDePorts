# <center>Documentation générale <center>                      
### <center>Présentation du projet et objectif finaux <center>
 **Objectif principal :**
Scanner les ports d’un serveur à partir d’un client et en déduire les failles de sécurité et les attaques possible. 

 **Objectif secondaire :**
Création de profils de scan personnalisés
### <center>Membres du groupe de projet (rôles par sprint) <center>
***Semaine 1:*** 
|Nom|Rôles|taches|
|---|---|---|
|Ahmed|pion|Doc Admin|
|Nicolas C|pion|Doc Utilisateur Gratté nmap|
|Sébastien|Scrum Ma|VM, IP, Gratté nmap|
|Patrick|PO|DOC Général| 

### <center>Choix techniques : quel OS, quelle version, etc.. <center>
**logiciels:** Nmap.

**Serveur:** Debian 12.

**client:** Windows 10 et Ubuntu 22.04.

### <center>Introduction : mise en contexte  <center>
Dans un monde où la sécurité informatique est un point important au sein d'une sociéte ou d'un organisme, la nécessité de détecter et de contrer les menaces potentielles sur les réseaux est cruciale. L'un des moyens pour y arrive est le scan des ports. Pour se faire different outils sont utilisable tel que nmap ou netcat, mais nous utiliseront pricipalement ici nmap entant largement suffisant pour notre projet.

### <center>Difficultés rencontrées : problèmes techniques rencontrés <center>
Concernant les problèmes rencontrés, au niveau du logiciel, aucun problème n'a été rencontré lors de l'installation et de la mise en pratique, celle-ci s'est déroulée assez fluidement grâce à la documentation disponible sur le site. Le problème est survenu sur le serveur Debian, où nous avons rencontré des difficultés avec la mise en réseau et la reconnaissance des ports.

### <center>Solutions trouvées : Solutions et alternatives trouvées <center>
Concernant le serveur Debian, nous avons dû configurer une adresse IP fixe. Pour ce faire, nous avons modifié le fichier /etc/network/interfaces. Ensuite, une fois nos machines reliées, nous avons dû ouvrir des ports afin de pouvoir les scanner, car par défaut, les 1000 ports que nous avons scannés étaient tous fermés.
### <center>Améliorations possibles : suggestions d’améliorations futures <center>
Actuellement, nous travaillons sur la possibilité de créer des scans personnalisés, c'est-à-dire de pouvoir scanner des ports spécifiques ou une certaine plage de ports.
