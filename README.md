# Utilisation de Modbus TCP pour la lecture et l'écriture de donnes sur M340-ATV

### Mise en situation:

 [L'école universitaire de physique et d'ingénierie](https://eupi.uca.fr/) dispose d'une ligne de production pédagogique, où un convoyeur rotatif (C) est utilisé pour transporter les pièces fournies par un convoyeur (T1) à un autre convoyeur (T2) perpendiculaire à T1.  Ce convoyeur rotatif est un élément clé de la ligne de production, car il permet de transporter les pièces d'une station à l'autre en utilisant des capteurs et des actionneurs pour optimiser le processus de production. Il est donc crucial de bien comprendre son fonctionnement et son utilisation pour garantir une efficacité maximale de la ligne de production.

### Présentation du convoyeur et de son fonctionnement en mode automatique :
Ce convoyeur rotatif est équipé de différents capteurs, tels que des capteurs de position de vérins et de la pièce, ainsi que de plusieurs actionneurs, tels que des vérins et des moteurs. L'ensemble du système est contrôlé par un automate programmable industriel (API) M340, qui est responsable de l'exécution des différents processus de la machine.
```
1. Condition initiale (Convoyeur en face du convoyeur (T1)).
2. Condition (À la détection d'une pièce au début du convoyeur) : convoyeur monte.
3. Condition (Une fois arrivé au niveau haut) : rotation vers la direction du convoyeur (T2).
4. Condition (Rotation terminée) : convoyeur descend.
```

### L'objectif du projet : 

- Améliorer la connectivité, la surveillance et l'automatisation d'une machine industrielle existante.

### Solution proposée: (domaine industrie 4.0)

- En intégrant une carte Raspberry Pi dans cette machine, nous pouvons connecter les capteurs et les actionneurs de la machine à la carte. La carte peut alors lire les données des capteurs et les envoyer à un système de surveillance à distance.
- En utilisant Node-RED comme interface, nous pouvons créer une interface graphique conviviale pour surveiller les données des capteurs et les états des actionneurs.

### Problematique :

1. Comment intégrer une carte Raspberry Pi dans une machine industrielle automatisée ?
2. Comment concevoir une interface Node-RED pour le contrôle en temps réel des actionneurs et l'automatisation des processus industriels ?

### Réalisation :

### Matériels :
J'ai eu à ma disposition le convoyeur relié à un automate Schneider M340 équipé d'un module de communication Ethernet NOC 0401, d'une carte Raspberry Pi 3 B+ et d'un ordinateur de bureau.
### 1. Définition du protocole de communication :

La communication entre les dispositifs d'automatisation industrielle se fait avec le protocole Modbus, tandis qu'Ethernet est un protocole de communication pour les réseaux locaux.

Il existe une variante de Modbus appelée Modbus TCP qui permet une communication directe via Ethernet en encapsulant les données Modbus dans des paquets TCP/IP. 

La relation entre Modbus et Ethernet peut être établie via un convertisseur Modbus vers Ethernet ou directement via le protocole Modbus TCP.

### 2. Connexions des trois appareils à un même réseau Modbus TCP :
Il existe 3 conditions à respecter :

#### i. Les adresses IP des trois appareils doivent être dans le même réseau IP.

Dans cet exemple, nous avons défini le réseau IP comme étant "192.168.0.0".

#### ii. Les adresses IP doivent être dans la plage d'adresses IP attribuée au réseau.

Nous avons attribué une plage d'adresses IP de 192.168.0.1 à 192.168.0.254.

#### iii. Les adresses IP doivent être différentes l'une de l'autre, car chaque adresse IP doit être unique sur le réseau.

Pour respecter ces conditions, nous pouvons attribuer les adresses IP suivantes à chaque appareil :
```
Automate : 192.168.0.1
Ordinateur fixe : 192.168.0.241
Carte Raspberry : 192.168.0.121
```
	

## Auteur
* **Mehdi Allani** [@Mehdi Allani](https://www.linkedin.com/in/mehdi-allani-3a18ab1b2/)