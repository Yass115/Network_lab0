# Network_lab0
Il s'agit du premier laboratoire du cours de réseaux et systèmes informatique.

Dans ce premier laboratoire nous allons aborder l'adressage ainsi que la mise en place de tables de routages.

## Adressage
L’adressage réseau est un élément fondamental des communications informatiques. Il permet aux appareils d’échanger des données au sein d’un réseau local (LAN) ou à travers Internet. Ce laboratoire vise à comprendre les bases de l’adressage IP, les masques de sous-réseau et l’organisation des réseaux pour assurer une communication efficace et structurée.

### Exercice 1
Dans le premier exercice lié à ce laboratoire, nous devons attribuer des plages d'adresses à chaque "service" de l'entreprise.

![Exercice 1](exo1.png)

Je vais vous indiquer la méthode à suivre afin de pouvoir attribuer des adresses sans problèmes.

1- On commence par voir quel service à le plus grand nombre d'hotes (dans notre cas il s'agit dela section "Autres Employés" qui devra compter 300 hotes).

2- En suite nous devons trouver n dans l'équation suivante 2<sup>n = 300, on truve donc n= 8,22 mais nous allons prendre n = 9 afin d'avoir assez d'adresses (donc ici nous aurons 512 adresses.

3- PVST+ (Per VLAN Spanning Tree Plus - Cisco) : Implémentation de Cisco qui permet d’avoir un STP distinct par VLAN.



### Exercice 2
![Exercice 2](exo2.png)




### Exercice 3
![Exercice 3](exo3.png)
