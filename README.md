# nat-and-pat
Découverte du NAT et du PAT

### Qu'est ce que le NAT?
```
Il s'agit d'un mécanisme mis en place sur les routeurs afin de remplacer l'adresse IP privée source d'une machine
par l'adresse IP publique du routeur dans un paquet réseau lorsqu'une machine tente de communiquer avec un serveur
situé sur Internet. Le NAT permet à plusieurs équipements présents dans un réseau privé d’utiliser une même adresse
IP publique.
```

* 1980 =  Création d’IPv4 (RFC 791)
* De 1980 à 1990 = BOOM internet (Accroissement exponentiel)
* IPv4 = 4,3 milliards (soit 2^32) adresses
* IPv4 se retrouve vite en pénurie d’adresse IP

#### Solution sur le court terme :
* Création du NAT / PAT.

#### Solution sur le long terme :
* Création d’un nouveau système d’adressage IP ( IPv6 ).

L’adressage IPv4 est toujours le plus utilisé au monde, toute entreprise et toute BOX internet utilise le NAT.<br>
L’adressage IPv6 est en cours de déploiement.


## Principe de fonctionnement

![image](https://user-images.githubusercontent.com/83721477/171190838-3c5ed222-2886-4849-806f-ef0a250c7ea1.png)

Création de deux zones :

* PRIVATE (Adressage privé)<br>
Définis par la RFC 1918
* PUBLIC (Adressage public) <br>
Géré par l’IANA (Internet Assigned Numbers Authority)

![image](https://user-images.githubusercontent.com/83721477/171194866-22e078e3-58de-448d-9698-3b65c8b41c78.png)

Il existe 3 modes de fonctionnement pour le NAT :
* NAT Statique
* NAT Dynamique
* NAT Overlay (PAT)

### NAT Statique
1 IP privée pour une IP publique
![image](https://user-images.githubusercontent.com/83721477/171199078-4660eab4-4279-4095-b621-796e7ad87190.png)

### NAT Dynamique

![image](https://user-images.githubusercontent.com/83721477/171199441-0e18ed38-dec6-41a4-8088-bb4ede1633c1.png)

### PAT
Permets de faire correspondre plusieurs adresses IP privées à une seule adresse publique.
Pour se faire, notre routeur va jouer sur les numéros de ports.

![image](https://user-images.githubusercontent.com/83721477/171199758-ea5bd70c-f74b-4382-b44a-73dff486aa64.png)

## Notes
* Toutes les BOX Internet fonctionnent en PAT.
* Les postes présents dans votre réseau domestique utilisent donc l’adresse IP publique de votre BOX.
* Si vous voulez mettre en place un serveur accessible de l’extérieur derrière votre BOX, vous allez devoir faire du Port-Forwarding. (Redirection de port) Une redirection de port permet de dire à votre BOX de rester en écoute sur un port en particulier. S’il reçoit quelque chose sur ce dernier, il va toujours le retransmettre à l’utilisateur spécifié.
