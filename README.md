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
|Nicolas C|pion|Doc Utilisateur
|Sébastien|Scrum Ma|VM, IP, Gratté nmap|
|Patrick|PO|DOC Général| 

### <center>Choix techniques : quel OS, quelle version, etc.. <center>
**logiciels:** Nmap.

**Serveur:** Debian 12.

**client:** Windows 10 et Ubuntu 22.04.

### <center>Introduction : mise en contexte  <center>
Dans un monde où la sécurité informatique est un point important au sein d'une sociéte ou d'un organisme, la nécessité de détecter et de contrer les menaces potentielles sur les réseaux est cruciale. L'un des moyens pour y arrive est le scan des ports. Pour se faire different outils sont utilisable tel que nmap ou netcat, mais nous utiliseront pricipalement ici nmap entant largement suffisant pour notre projet.
### <center> Qu'est ce qu'un port et principaux port a connaitre <center>
**Les ports réseau sont des points d'accès numérotés permettant à un ordinateur d'interagir avec des services spécifiques sur un réseau, facilitant ainsi la communication et le transfert de données entre les dispositifs.**


**Cette liste comprend quelques-uns des ports les plus courants et largement utilisés sur Internet. Les administrateurs système et réseau devraient être familiarisés avec ces ports pour configurer correctement les pare-feu, les services et les applications sur leurs réseaux.**

1. **Port 21** : FTP (File Transfer Protocol) - Utilisé pour le transfert de fichiers sur Internet.
   
2. **Port 22** : SSH (Secure Shell) - Utilisé pour accéder à distance à des machines en toute sécurité et pour le transfert sécurisé de fichiers (SFTP).
   
3. **Port 23** : Telnet - Utilisé pour l'administration à distance et le contrôle de périphériques réseau.
   
4. **Port 25** : SMTP (Simple Mail Transfer Protocol) - Utilisé pour l'envoi de courrier électronique.
   
5. **Port 53** : DNS (Domain Name System) - Utilisé pour la résolution de noms de domaine en adresses IP et vice versa.
   
6. **Port 80** : HTTP (Hypertext Transfer Protocol) - Utilisé pour accéder à des sites web non sécurisés.
   
7. **Port 110** : POP3 (Post Office Protocol version 3) - Utilisé pour récupérer des e-mails depuis un serveur de messagerie.
   
8. **Port 143** : IMAP (Internet Message Access Protocol) - Utilisé pour récupérer des e-mails depuis un serveur de messagerie, avec plus de fonctionnalités que POP3.
   
9. **Port 443** : HTTPS (HTTP Secure) - Utilisé pour accéder à des sites web sécurisés à l'aide du protocole SSL/TLS.
   
10. **Port 465** : SMTPS (SMTP Secure) - Utilisé pour envoyer des courriels de manière sécurisée à l'aide du protocole SSL/TLS.
   
11. **Port 587** : Submission (Message Submission Agent) - Utilisé pour l'envoi de courriels à partir de clients de messagerie à l'aide du protocole SMTP.
   
12. **Port 3306** : MySQL - Utilisé pour les connexions à des bases de données MySQL.
   
13. **Port 3389** : RDP (Remote Desktop Protocol) - Utilisé pour accéder à distance à des ordinateurs Windows.
   
14. **Port 5432** : PostgreSQL - Utilisé pour les connexions à des bases de données PostgreSQL.
   
15. **Port 8080** : HTTP alternative - Utilisé comme alternative au port 80 pour les serveurs web.
 
**Numérotation des ports** : Les ports réseau sont identifiés de 0 à 65535. 
Les ports de 0 à 1023 sont réservés aux services bien connus et sont souvent désignés comme des ports système.
Les ports de 1024 à 49151 sont réservés aux applications et services enregistrés auprès de l'Internet Assigned Numbers Authority (IANA) et sont souvent appelés ports enregistrés ou ports d'utilisateur. 
Les ports de 49152 à 65535 sont des ports privés ou dynamiques qui peuvent être utilisés par des applications et des processus temporaires.

### <center>Difficultés rencontrées : problèmes techniques rencontrés <center>

### <center>Solutions trouvées : Solutions et alternatives trouvées <center>
### <center>Améliorations possibles : suggestions d’améliorations futures <center>
