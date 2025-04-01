# Network_lab0
Il s'agit du premier laboratoire du cours de réseaux et systèmes informatique.

Dans ce premier laboratoire nous allons aborder l'adressage ainsi que la mise en place de tables de routages.

## Adressage
L’adressage réseau est un élément fondamental des communications informatiques. Il permet aux appareils d’échanger des données au sein d’un réseau local (LAN) ou à travers Internet. Ce laboratoire vise à comprendre les bases de l’adressage IP, les masques de sous-réseau et l’organisation des réseaux pour assurer une communication efficace et structurée.

### Exercice 1
Dans le premier exercice lié à ce laboratoire, nous devons attribuer des plages d'adresses à chaque "service" de l'entreprise, l'adresse global est 156.200.32.0 /22

![Exercice 1](exo1.png)

Je vais vous indiquer la méthode à suivre afin de pouvoir attribuer des adresses sans problèmes.

1- On commence par voir quel service à le plus grand nombre d'hotes (dans notre cas il s'agit dela section "Autres Employés" qui devra compter 300 hotes).

2- En suite nous devons trouver n dans l'équation suivante 2<sup>n </sup> = 300, on trouve donc n= 8,22 mais nous allons prendre n = 9 afin d'avoir assez d'adresses (donc ici nous aurons 512 adresses).

3- On peut alors calculer le masque : 32 - 9 = 23 donc le masque ici sera un /23 (ici on utilise 32 car dans une adresse IP s'écrit sous la forme x.x.x.x (ou chaque x represente un octet et donc naturellement on a 8*4 octets

4- Addresses totales -> 156.200.32.0 jusqu'à 156.200.33.255

5- Addresses utilisables par les hotes -> 156.200.32.1 jusqu'à 156.200.33.254 (on enlève 156.200.32.0 car il s'agit de l'adresse du sous réseau et 156.200.33.255 est l'adresse de diffusion (appelé Broadcast))

Et voilà nous avons fini l'adressag pour un service, il nous reste maintenant à faire la meme chose avec les autres services, je vais ici directement afficher les réponses car la méthodologie est la meme.


| Service | Nombre d'hotes |Adresses Totales |Adresses utilisables par les hotes |
| --- | --- |--- |--- |
| Autres employés | 300 | 156.200.32.0 --> 156.200.33.255 | 156.200.32.1 --> 156.200.33.254 |
| Salle de réunion | 50 | 156.200.34.0 --> 156.200.34.63 | 156.200.34.1 --> 156.200.34.62 |
| Serveurs internes | 20 | 156.200.34.64 --> 156.200.34.95 | 156.200.34.65 --> 156.200.34.94 |
| Zone démilitarisée | 10 | 156.200.34.96 --> 156.200.34.111 | 156.200.34.97 --> 156.200.34.110 |
| Ressources humaines | 8 | 156.200.34.112 --> 156.200.34.127 | 156.200.34.113 --> 156.200.34.126 |
| Comptabilité | 5 | 156.200.34.128 --> 156.200.34.135 | 156.200.34.129 --> 156.200.34.134 |

**Attention l'adresse 156.200.34.0 est comptée comme la 1ere adresse donc pour 64 adresses on fait 0+64-1 = 63**

la toute première adresse de la plage des adresses totales est réservé au sous réseau et la dernière adresse est reservé au broadcast

Petit apparté important, voici comment faire pour avoir un masque sous réseau sous la forme /x à partir de la forme x.x.x.x exemple: si on a un masque de 255.255.255.192 alors on fait 256 - 192 = 64 et après il faut résoudre cette équation 2<sup>n </sup> = 64 on trouve donc n = 6 et donc on fait 32 - 6 = 26 donc le masque de sous réseau peut s'écrire comme celà /26

Voilà le réseau avec les sous réseaux mis en place : 

![Exercice fini](archi.png)


### Exercice 2
![Exercice 2](exo2.png)




### Exercice 3
![Exercice 3](exo3.png)
