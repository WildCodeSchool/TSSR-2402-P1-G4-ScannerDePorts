# Guide utilisateur

## Présentation  

À la base, Nmap (Network Mapper) est un logiciel de cartographie de réseaux qui utilise les paquets IP pour identifier tous les périphériques connectés à ce réseau. Il s'agit également d'un des outils de découverte qui permet de fournir des informations sur les services et les systèmes d'exploitation qu'ils exécutent.

Utilisé par les administrateurs réseau, Nmap peut être utilisé pour effectuer un balayage de ports ou encore trouver des hôtes actifs sur un réseau. Ce scan de ports libre peut aussi détecter les systèmes d'exploitation d'une machine et la version logiciel, trouver des balayages ping…

Compatible avec de nombreux systèmes d'exploitation, ce programme est en général utilisé grâce à une interface en ligne de commande. Initialement développé pour des réseaux d'entreprise, Nmap est capable d'analyser des milliers d'appareils connectés.


## Guide pour Linux Ubuntu

### Quelques commandes pour commencer

Voila deux commandes très utile pour avoir des informations sur le programme nmap.

Manuel de l'application
```
man nmap
``` 

Résumé des options
``` 
nmap --help  
```

### Utilisation simple

**Les commandes simple peuvent être faites sans appliquer ``sudo``**  
Quelques exemples simples pour commencer a utiliser nmap :  

Scan rapide des ports d'une cible unique
```
nmap 10.0.0.1   
```

Scan rapide des ports d'une série de cibles
```
nmap 10.0.0.1-50
```

Scan rapide des ports d'un sous-réseau
```
nmap 10.0.0.0/24
```

Scan rapide des ports d'une liste de machine préétabli 
```
nmap -iL "list"
```

Scan rapide d'un seul port
```
nmap -p "port" 10.0.0.1
```

Archivage normal du scan rapide effectué
```
nmap -oN 10.0.0.1
```

Archivage XML du scan rapide effectué
```
nmap oX 10.0.0.1 
```

### Utilisation avancé

**Les commandes avancé doivent être faite avec la commande ``sudo``**  

La commande ``sudo`` permet a la machine d'exploiter la carte réseau plus profondement, cela permet donc d'avoir plus d'informations sur les commandes simple. Mais il permet aussi d'avoir d'autre parametre applicable a la commande ``nmap``  
Quelques exemples :  

Scan des ports avec des paquets UDP a la place des paquets TCP

```
sudo nmap sU 10.0.0.1
```

Scan Infiltration SYN :  
L’option -sS est celle utilisée par défaut par Nmap. Contrairement au scan TCP celle-ci créer une demi-connexion, puisqu’une connexion TCP se passe en trois temps avec une confirmation d’établissement de la connexion.  
Cette technique envoie un paquet RST qui clôt celle-ci au lieu de la confirmer. Cela a pour effet de réduire le trafic sur la cible et d’augmenter la vitesse du scan.

```
sudo nmap -sS 10.0.0.1
```

Scan avec ACK : 
L’option -sN provoque une attaque dite « null ». Une attaque « null » se produit lorsqu’un paquet TCP est envoyé avec tous ses bits de contrôles à zéro. Le paquet est envoyé vers la cible dans l’espoir que le système cible se plaigne du paquet. Les pare-feux classiques ne filtrant que les paquets SYN, le fait que notre paquet soit à zéro pourrait permettre de le faire passer inaperçue.  

```
sudo -sN 10.0.0.1
```

Scan avec FIN :  
L’option -sX est un scan avec tous les drapeaux d’activés dans un paquet TCP. Un paquet avec tous les bits d’activés n’a pas de signification dans le protocole TCP.  
Donc le pare-feu, ne connaissant pas ce type de paquet, laissera passer, puisque les pare-feux classiques filtrent uniquement les paquets SYN et ne regardent pas toujours ce genre d’anomalie.

```
nmap -sX 10.0.0.1
```

Scan NULL :  
L’option -sA envoie des paquets ACK sur la cible dans l’espoir que le pare-feu supposera qu’une communication existe déjà entre l’attaquant et la cible. Dans le cas ci-dessous le pare-feu renvoie des paquets RST, car il n’y avait pas de paquet ACK attendu, car aucune connexion n’est en cours. Mais si une communication avait été en cours, des paquets ICMP seraient revenus et nous aurions eu un résultat similaire à l’option -sF présente dans cet article.

```
nmap -sA 10.0.0.1
```

Scan de l’arbre de Noël
L’option -sF fonctionne avec les FIN bits. Ceux-ci sont présents à la fin des sessions TCP. Un FIN est envoyé à la cible dans l’espoir que le pare-feu supposera qu’une connexion existe déjà entre l’attaquant et la cible. Les pare-feux classiques filtrent uniquement les paquets SYN, de sorte que le FIN indépendant pourrait passer inaperçu.  

```
nmap -sF 10.0.0.1
```

Scan des ports avec la détection de l'OS présent sur la machine cible

```
sudo nmap -O 172.16.10.10  
```

Scan de l'ensemble des 65535 ports de la machine cible. **Attention cette commande prend un certain temps pour s'executer**

```
nmap -p- 10.0.0.1
```

Scan service et OS  
il est possible de connaitre les services qui utilisent les ports ou encore l'OS qui fonctionne sur la machine cible. Il y a des parametres  possible suivant si l'on souhaite voir l'un ou l'autre, mais il y a un paramatre qui permet d'avoir les deux, pour cela taper la commande

```
nmap -A 10.0.0.1
```

### Utilisation des scripts

Le programme `nmap` permet l'utilisation de script pour permettre des actions plus poussée et aller plus loin dans la detection de faille.  

Ces scripts sont disponible dans le sous-dossier `/usr/share/nmap/scripts`

Pour utiliser un script il faut utiliser la commande 

```
nmap --scripts "nom du script" 10.0.0.1
```

### Résumé des options
Ce résumé des options est affiché quand Nmap est exécuté sans aucun argument; la plus récente version est toujours disponible sur https://nmap.org/data/nmap.usage.txt . Il sert d'aide-mémoire des options les plus fréquemment utilisées, mais ne remplace pas la documentation bien plus détaillée de la suite de ce manuel. Les options obscures n'y sont pas incluses.

Nmap 4.50 (insecure.org)
Utilisation: nmap [Type(s) de scan] [Options] {spécifications des cibles}

- SPÉCIFICATIONS DES CIBLES:  
Les cibles peuvent être spécifiées par des noms d'hôtes, des adresses IP, des adresses de réseaux, etc.  
Exemple: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0-255.0-255.1-254  
-iL <inputfilename>: Lit la liste des hôtes/réseaux cibles à partir du fichier  
-iR <num hosts>: Choisit les cibles au hasard  
--exclude <host1[,host2][,host3],...>: Exclut des hôtes/réseaux du scan   
--excludefile <exclude_file>: Exclut des hôtes/réseaux des cibles à partir du fichier  

- DÉCOUVERTE DES HÔTES:  
-sL: List Scan - Liste simplement les cibles à scanner  
-sP: Ping Scan - Ne fait que déterminer si les hôtes sont en ligne -P0: Considère que tous les hôtes sont en ligne -- évite la découverte des hôtes  
-PN: Considérer tous les hôtes comme étant connectés -- saute l'étape de découverte des hôtes  
-PS/PA/PU [portlist]: Découverte TCP SYN/ACK ou UDP des ports en paramètre  
-PE/PP/PM: Découverte de type requête ICMP echo, timestamp ou netmask   
-PO [num de protocole]: Ping IP (par type)  
-n/-R: Ne jamais résoudre les noms DNS/Toujours résoudre [résout les cibles actives par défaut]  
--dns-servers <serv1[,serv2],...>: Spécifier des serveurs DNS particuliers  

- TECHNIQUES DE SCAN:  
-sS/sT/sA/sW/sM: Scans TCP SYN/Connect()/ACK/Window/Maimon   
-sN/sF/sX: Scans TCP Null, FIN et Xmas  
-sU: Scan UDP  
--scanflags <flags>: Personnalise les flags des scans TCP  
-sI <zombie host[:probeport]>: Idlescan (scan passif)  
-sO: Scan des protocoles supportés par la couche IP  
-b <ftp relay host>: Scan par rebond FTP  
--traceroute: Détermine une route vers chaque hôte  
--reason: Donne la raison pour laquelle tel port apparait à tel état  

- SPÉCIFICATIONS DES PORTS ET ORDRE DE SCAN:  
-p <plage de ports>: Ne scanne que les ports spécifiés  
Exemple: -p22; -p1-65535; -pU:53,111,137,T:21-25,80,139,8080  
-F: Fast - Ne scanne que les ports listés dans le fichier nmap-services  
-r: Scan séquentiel des ports, ne mélange pas leur ordre  
--top-ports <nombre>: Scan <nombre> de ports parmis les plus courants  
--port-ratio <ratio>: Scan <ratio> pourcent des ports les plus courants  

- DÉTECTION DE SERVICE/VERSION:  
-sV: Teste les ports ouverts pour déterminer le service en écoute et sa version  
--version-light: Limite les tests aux plus probables pour une identification plus rapide  
--version-intensity <niveau>: De 0 (léger) à 9 (tout essayer)  
--version-all: Essaie un à un tous les tests possibles pour la détection des versions  
--version-trace: Affiche des informations détaillées du scan de versions (pour débogage)  

- SCRIPT SCAN:  
-sC: équivalent de --script=safe,intrusive  
--script=<lua scripts>: <lua scripts> est une liste de répertoires ou de scripts séparés par des virgules  
--script-args=<n1=v1,[n2=v2,...]>: passer des arguments aux scripts  
--script-trace: Montre toutes les données envoyées ou recues  
--script-updatedb: Met à jour la base de données des scripts. Seulement fait si -sC ou --script a été aussi donné.  

- DÉTECTION DE SYSTÈME D'EXPLOITATION:  
-O: Active la détection d'OS  
--osscan-limit: Limite la détection aux cibles prometteuses  
--osscan-guess: Devine l'OS de façon plus agressive  

- TEMPORISATION ET PERFORMANCE:  
Les options qui prennent un argument de temps sont en milisecondes a moins que vous ne spécifiiez 's'
(secondes), 'm' (minutes), ou 'h' (heures) à la valeur (e.g. 30m).  
-T[0-5]: Choisit une politique de temporisation (plus élevée, plus rapide)  
--min-hostgroup/max-hostgroup <nombre>: Tailles des groupes d'hôtes à scanner en parallèle  
--min-parallelism/max-parallelism <nombre>: Parallélisation des paquets de tests (probes)  
--min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <msec>: Spécifie le temps d'aller-retour des paquets de tests  
--min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <msec>: Spécifie le temps d'aller-retour des paquets de tests  
--min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>: Précise
le round trip time des paquets de tests.  
--max-retries <tries>: Nombre de retransmissions des paquets de tests des scans de ports.  
--host-timeout <msec>: Délai d'expiration du scan d'un hôte  --scan-delay/--max-scan-delay <msec>: Ajuste le délai de retransmission entre deux paquets de tests  
--scan-delay/--max-scan-delay <time>: Ajuste le delais entre les paquets de tests.  

- ÉVASION PARE-FEU/IDS ET USURPATION D'IDENTITÉ  
-f; --mtu <val>: Fragmente les paquets (en spécifiant éventuellement la MTU)  
-D <decoy1,decoy2[,ME],...>: Obscurci le scan avec des leurres  
-S <IP_Address>: Usurpe l'adresse source  
-e <iface>: Utilise l'interface réseau spécifiée  
-g/--source-port <portnum>: Utilise le numéro de port comme source  
--data-length <num>: Ajoute des données au hasard aux paquets émis  
--ip-options <options>: Envoi des paquets avec les options IP spécifiées.   
--ttl <val>: Spécifie le champ time-to-live IP  
--spoof-mac <adresse MAC, préfixe ou nom du fabriquant>: Usurpe une adresse MAC  
--badsum: Envoi des paquets TCP/UDP avec une somme de controle erronnée.  

- SORTIE:  
-oN/-oX/-oS/-oG <file>: Sortie dans le fichier en paramètre des résultats du scan au format normal, XML, s|<rIpt kIddi3 et Grepable, respectivement  
-oA <basename>: Sortie dans les trois formats majeurs en même temps  
-v: Rend Nmap plus verbeux (-vv pour plus d'effet)  
-d[level]: Sélectionne ou augmente le niveau de débogage (significatif jusqu'à 9)  
--packet-trace: Affiche tous les paquets émis et reçus  
--iflist: Affiche les interfaces et les routes de l'hôte (pour débogage)  
--log-errors: Journalise les erreurs/alertes dans un fichier au format normal  
--append-output: Ajoute la sortie au fichier plutôt que de l'écraser   
--resume <filename>: Reprend un scan interrompu  
--stylesheet <path/URL>: Feuille de styles XSL pour transformer la sortie XML en HTML  
--webxml: Feuille de styles de références de Insecure.Org pour un XML plus portable   
--no-stylesheet: Nmap n'associe pas la feuille de styles XSL à la sortie XML  

- DIVERS:  
-6: Active le scan IPv6  
-A: Active la détection du système d'exploitation et des versions  
--datadir <dirname>: Spécifie un dossier pour les fichiers de données de Nmap  
--send-eth/--send-ip: Envoie des paquets en utilisant des trames Ethernet ou des paquets IP bruts  
--privileged: Suppose que l'utilisateur est entièrement privilégié   
-V: Affiche le numéro de version  
--unprivileged: Suppose que l'utilisateur n'a pas les privilèges d'usage des raw socket  
-h: Affiche ce résumé de l'aide  

- EXEMPLES:  
nmap -v -A scanme.nmap.org  
nmap -v -sP 192.168.0.0/16 10.0.0.0/8  
nmap -v -iR 10000 -P0 -p 80  

## Source

Pour plus d'informations le site [nmap.org](https://nmap.org/) est disponible.  


