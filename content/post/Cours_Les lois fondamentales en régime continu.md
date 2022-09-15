---
author: "Zahkthar"
title: "Les lois fondamentales en régime continu"
date: 2022-09-01T00:47:41+02:00
description: "Les principales lois à connaître pour pouvoir aller plus loin dans l'électronique."

categoriesEnabled: true
Catégories: [
    "Cours"
]

Étiquettes: [
    "Lois",
    "Théorie"
]

Séries: ["Les bases de l'électronique"]
draft: false
---

**Les principales lois à connaître pour pouvoir aller plus loin dans l'électronique.**

Avant de pouvoir réellement faire de l'électronique, c'est-à-dire lire des schémas, programmer des microcontrôleurs, découvrir des nouveaux composants ou même designer/construire ses propres circuits, il faut avoir un minimum de bases ! C'est donc ce que je propose de faire dans cette série d'articles : récapituler les bases vitales à la poursuite de l'électronique. Je recommande donc de lire cette série en premier si vous débutez l'électronique, ce qui vous amènera ensuite à pouvoir vous spécialiser un peu plus vers le sujet qui vous intéresse.

Nous allons donc commencer par quelques définitions peut-être évidentes pour certains, mais qui permettront de mieux comprendre la suite :

1. [La charge électrique, l'intensité et la loi des nœuds](#la-charge-électrique-lintensité-et-la-loi-des-nœuds)
2. [La tension et la loi des mailles](#la-tension-et-la-loi-des-mailles)
3. [La résistance et la loi d'Ohm](#la-résistance-et-la-loi-dohm)

### La charge électrique, l'intensité et la loi des nœuds

#### La charge électrique et l'intensité

N'importe quel matériau conducteur dans un circuit fermé contenant un électromoteur (ça peut être un générateur, une batterie, une pile, un panneau solaire, etc...) est traversé par un courant électrique. Le courant électrique est en réalité un flux d'électrons qui traverse le circuit depuis une borne du générateur dans l'objectif d'y retourner par son autre borne.

La charge électrique d'un électron étant négative (-1.6 * 10-19 C -> Coulombs), le sens conventionnel du courant (du + vers le -) est opposé à celui des électrons (du - vers le +)

Si on note "dq" la charge électrique en Coulombs transportées par les électrons traversant un conducteur pendant une durée "dt", l'intensité que l'on notera I (ou i) sera donnée par la formule :

$$I = \frac{dq}{dt}$$

Où :
- I est en **ampères** (A)
- dq est en **coulombs** (C)
- dt est en **secondes** (s)

#### La loi des nœuds

La loi des nœuds peut se résumer simplement par une seule phrase : 

**"La somme des intensités des courants qui entrent par un nœud est égale à la somme des intensités des courants qui sortent du même nœud."**

[![Image représentant la loi des nœuds](https://upload.wikimedia.org/wikipedia/commons/f/f2/Kirchhoff%27s_Current_Law.svg "Image représentant la loi des nœuds")](https://fr.wikipedia.org/wiki/Lois_de_Kirchhoff#/media/Fichier:Kirchhoff's_Current_Law.svg)

Ici, la somme des courants i1 et i2 qui rentrent dans le nœud est égale à la somme des courants i3 et i4 qui sortent du nœud.

### La tension et la loi des mailles

#### La tension électrique

La tension n'est pas une grandeur qu'il est facile de définir sans entrer dans la théorie. Mais par analogie, on arrive à s'approcher du sens de cette grandeur. On peut faire l'analogie entre la tension électrique à un point donnée du circuit et l'énergie potentielle en mécanique.

$$Ep = m * g * h$$

L'énergie potentielle dépend directement de la hauteur à laquelle se trouve l'objet de la formule. La hauteur maximale serait dans cet exemple la tension d'alimentation (par exemple 5 volts) qui diminue à chaque fois que l'on rencontre un conducteur.

[![Pont diviseur de tension](https://upload.wikimedia.org/wikipedia/commons/d/d9/Pont_diviseur_tension.svg "Pont diviseur de tension")](https://fr.wikipedia.org/wiki/Diviseur_de_tension#/media/Fichier:Pont_diviseur_tension.svg)

Dans ce circuit, que l'on appelle un "pont diviseur de tension" (nous y reviendrons plus tard), si on imagine que U est la tension d'alimentation du circuit, 5V par exemple, avant la première résistance la tension sera égale à U, soit 5V. Après la première résistance, la tension aura chuté. Après la deuxième résistance, la tension sera égale à 0.

L'intérêt de ce circuit étant de convertir une tension en une tension plus basse en jouant sur le rapport entre les deux résistances

#### La différence de potentiel

La différence de potentiel (aussi appelée ddp à l'écrit) est une grandeur que l'on confond souvent avec la tension. La différence de potentiel, comme son nom l'indique, est une différence entre deux points d'un circuit. Elle demande donc un point de repère. 

Si l'on reprend le circuit ci-dessus et que l'on admet que pour les 5V totaux, il y a une répartition égale de la tension entre les deux résistances, nous nous retrouvons donc avec U1 qui vaut 2.5V et U2 qui vaut aussi 2.5V. Mais d'où viennent ces 2.5V ? En réalité U1 est une **différence** de potentiel et représente donc le résultat de la soustraction entre la tension U et la tension après le passage dans la résistance. Nous avons donc bien 5V - 2.5V = **2.5V**. U2 suit exactement le même raisonnement. Nous n'avons plus que 2.5V après le passage du courant dans R1. La différence entre 2.5V et 0V est donc de 2.5 - 0 = **2.5V**

On admet donc que lorsque l'on parle généralement de tension, on parle de la valeur de la tension à un point du circuit alors que si l'on parle de la tension **aux bornes** ou **autour** d'un composant, nous parlons bien de la différence entre le point avant et après ledit composant, de la tension qui le traverse en somme (si la tension est représentée par une flèche comme ci-dessus avec U, U1 et U2, on peut aussi appeler la ddp par son nom sur le schéma).

#### La loi des mailles

La loi des mailles est la deuxième des [lois de Kirchhoff](https://fr.wikipedia.org/wiki/Lois_de_Kirchhoff) dont la première était la [loi des nœuds](#la-loi-des-nœuds).

La loi des mailles nous dit que lorsque l'on traverse une maille (c'est-à-dire une portion de circuit fermé) et partant d'un point N pour revenir au même point N, la somme des différences de potentiel rencontrées est égale à **zéro**.

[![Loi des mailles](https://upload.wikimedia.org/wikipedia/commons/4/40/Kirchhoff_voltage_law.svg "Loi des mailles")](https://fr.wikipedia.org/wiki/Lois_de_Kirchhoff#/media/Fichier:Kirchhoff_voltage_law.svg)

Dans cette image, nous pouvons voir une maille d'un circuit plus grand. Selon cette loi, la somme des tensions présentes maille présente sur cette image est égale à zéro. Ici :

$$v1+v2+v3+v4 = 0$$

Si nous reprenons un exemple avec une tension d'alimentation de 5V et que nous admettons que "R1 = R2 = R3", c'est à dire que la tension aux bornes de chaque résistance est égale. Nous aurons donc :

$$v1 = v2 = v3 = v4 / 3$$

Soit 1.66...V par résistance. Mais là vous vous demandez sûrement : "ais 5 + 1.66 + 1.66 +1.66 ça fait 10 pas 0" et oui, vu comme ça, le résultat est bien de 10V. Mais il y a un souci, une résistance **s'oppose** au passage du courant, donc ici la tension **chute** de 1.66V entre l'entrée et la sortie de la résistance. Si vous regardez une nouvelle fois [le schéma du pont diviseur](#la-tension-électrique), vous remarquerez que les flèches représentant les tensions U1 et U2 sont dans le sens opposé à la flèche représentant la tension d'alimentation U. C'est justement en raison du fait que la résistance s'oppose au passage du courant. Si nous reprenons donc notre calcul où nous en étions mais cette fois si en inversant les tensions aux bornes des résistances, nous obtenons :

$$5 - 1.66 - 1.66 - 1.66 = 0V$$

Ce qui correspond bien à ce que nous attendions.

**Note 1** : Pour calculer une différence de potentiel il faut simplement faire la soustraction entre la tension avant le composant et la tension après (ce qui permet d'avoir le delta). Sur le dernier schéma, v1 peut aussi être nommée "Uab" soit "La différence de tension entre le point **a** et le point **b**" Nous pouvons donc la calculer en faisant **Uab = Ua - Ub** (A noter qu'une tension négative est une tension positive dans l'autre sens -> -Uab = Uba il suffit d'inverser le sens de la flèche).

**Note 2** : Quand on a le nom de la différence de potentiel, Uab par exemple, la flèche part de la 2ème lettre et pointe vers la première.

**Note 3** : La loi des mailles peut être vérifiée dans les deux sens de rotation. Choisissez celui qui vont convient le mieux. Pensez simplement à mettre toutes les tensions dans le bon sens.

### La résistance et la loi d'Ohm

#### La résistance électrique

Je l'ai beaucoup utilisée en exemple au-dessus dans cet article et il est venu le temps de clarifier la définition de **la résistance électrique**.

La résistance électrique est la propriété d'un conducteur à s'opposer au passage du courant. Dit plus simplement, plus la résistance d'un conducteur sera grande, et plus l'intensité du courant sera faible pour une tension donnée. À l'inverse, si la résistance du conducteur est plus faible, l'intensité sera plus forte.

#### La loi d'Ohm

La loi d'Ohm est la loi empirique nommée en référence à **Georg Simon Ohm** qui l'a publiée en 1827 qui relie l'intensité du courant électrique traversant un conducteur à la tension à ses bornes. Elle énonce que :

$$U = R * I$$

Où :
- U est la tension en Volts (V)
- R est la résistance en Ohms (Ω)
- I est l'intensité en Ampères (A)

On appelle un conducteur **ohmique** un composant qui respecte la loi d'Ohm (nous verrons dans d'autres articles que ce n'est pas tout le temps le cas). La résistance est un exemple de conducteur ohmique.

La principale caractéristique principale d'une résistance étant d'opposer une plus ou moins grande résistance (mesurée en ohms donc) à la circulation du courant électrique, on l'appelle par convention de langage une résistance. En anglais, son nom est "resistor", qui serait traduisible en "résisteur" en français qui correspondrait plus à l'idée d'un "composant qui résiste" mais l'appellation "résistance" est complètement majoritaire.

#### Implications de la loi d'Ohm

- La loi d'Ohm permet de retrouver la troisième donnée lorsque l'on n'en a que deux. "I = U/R" permet de trouver l'intensité, "R = U/I" permet de trouver la résistance et "U = R*I" permet de trouver la tension. 
- On peut considérer la valeur de la résistance comme étant un coefficient de proportionnalité entre la valeur de la tensio net l'intensité. Si l'on trace la caractéristique d'une résistance (c'est-à-dire la courbe de la tension en fonction de l'intensité) nous obtiendrons une droite passant par l'origine et donc la pente sera la valeur de la résistance.

&nbsp;