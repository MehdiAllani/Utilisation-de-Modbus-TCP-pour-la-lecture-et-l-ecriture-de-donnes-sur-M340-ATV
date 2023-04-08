# Utilisation-de-Modbus-TCP-pour-la-lecture-et-l-écriture-de-donnes-sur-M340-ATV

### Mise en situation:
	L'école universitaire de physique et d'ingénierie dispose d'une ligne de production pédagogique, où un convoyeur rotatif (C) est utilisé pour transporter les pièces fournies par un convoyeur (T1) à autre convoyeur (T2) perpendiculaire à T1. Ce convoyeur rotatif est équipé de différents capteurs, tels que des capteurs de position de vérins et de la pièce, ainsi que de plusieurs actionneurs, tels que des vérins et des moteurs. L'ensemble du système est contrôlé par un automate programmable industriel (API) M340, qui est responsable de l'exécution des différents processus de la machine. Ce convoyeur rotatif est un élément clé de la ligne de production, car il permet de transporter les pièces d'une station à l'autre en utilisant des capteurs et des actionneurs pour optimiser le processus de production. Il est donc crucial de bien comprendre son fonctionnement et son utilisation pour garantir une efficacité maximale de la ligne de production.

### Fonctionnement du convoyeur :
	1- Condition initiale (Convoyeur en face du convoyeur (T1)).
	2- Condition (À la détection d'une pièce au début du convoyeur) : convoyeur monte.
	3- Condition (Une fois arrivé au niveau haut) : rotation vers la direction du convoyeur (T2).
	4- Condition (Rotation terminée) : convoyeur descend.

### L'objectif du projet : 
	- Améliorer la connectivité, la surveillance et l'automatisation d'une machine industrielle existante.

### Solution proposée: (domaine industrie 4.0)
	- En intégrant une carte Raspberry Pi dans cette machine, nous pouvons connecter les capteurs et les actionneurs de la machine à la carte. La carte peut alors lire les données des capteurs et les envoyer à un système de surveillance à distance.
	- En utilisant Node-RED comme interface, nous pouvons créer une interface graphique conviviale pour surveiller les données des capteurs et les états des actionneurs.

### Problematique :
	1- Comment intégrer efficacement une carte Raspberry Pi dans une machine industrielle contrôlée par un automate ?
	2- Comment concevoir une interface Node-RED intuitive pour contrôler les actionneurs de la machine en temps réel et permettre une automatisation avancée des processus industriels ?

	Cette problématique soulève plusieurs questions clés telles que :

		* Quels sont les protocoles de communication à utiliser pour connecter la carte Raspberry Pi à l'API de la machine ?
		* Comment intégrer les capteurs existants de la machine avec la carte Raspberry Pi et comment configurer les GPIO (General Purpose Input Output) pour contrôler les actionneurs de la machine ?
		* Quels sont les besoins des utilisateurs finaux pour l'interface utilisateur de Node-RED, et comment concevoir une interface qui soit intuitive et facile à utiliser ?


## Auteur
* **Mehdi Allani** [@Mehdi Allani](https://www.linkedin.com/in/mehdi-allani-3a18ab1b2/)