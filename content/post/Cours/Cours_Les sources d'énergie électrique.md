---
author: "Zahkthar"
title: "Les sources d'énergie électrique"
date: 2022-10-24T16:08:30+02:00
description: "Qu'est-ce qu'une source d'énergie électrique ?"

Catégories: [
    "Cours"
]

Étiquettes: [
    "Lois",
    "Théorie",
    "Alimentation"
]

Séries: ["Les bases de l'électronique"]
draft: false
---

**Qu'est-ce qu'une source d'énergie électrique et comment la modéliser ?**

Comment alimenter un circuit n'est pas forcément la première chose à laquelle on pense quand on le pense ou lorsqu'on le dessine. Mais au final, c'est ce qui va faire que le circuit marche ou pas ! Dans cet article, nous allons voir quelle est la différence entre une source de tension et de courant et la différence entre un générateur parfait et réel.

Le programme sera donc le suivant :
1. [La source d'énergie électrique](#la-source-dénergie-électrique)
2. [La source de tension](#la-source-de-tension)
3. [La source de courant](#la-source-de-courant)

### La source d'énergie électrique

La définition d'une source d'énergie est assez simple et elle est partout autour de nous. Une source d'énergie doit est un circuit ou un composant dont le but est de fournir via ses deux bornes que l'on peut appeller A et B une tension U et une intensité I, soit une puissance P qui est le produit de U par I. Une puissance maximale notée généralement Pmax est donnée en raison de l'effet Joule dont nous reverrons l'implication dans les paragraphes sur les générateurs réels.

La manière dont la source va fournir l'énergie peut donc être séparée en deux grandes catégories :
- La tension est constante et l'intensité varie : C'est une [source de tension](#la-source-de-tension).
- L'intensité est constante et la tension varie : C'est une [source de courant](#la-source-de-courant).

### La source de tension

#### La source de tension parfaite

Une source de tension parfaite est un générateur dont la tension est parfaitement contante et l'intensité varie en fonction de la charge.

[![Courbe caractéristique d'une source de tension parfaite](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceTensionParfaite.png#center "Courbe caractéristique d'une source de tension parfaite")](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceTensionParfaite.png)

La tension UAB aux bornes de la source est constante quelle que soit l'intensité du courant généré. La source est dite "idéale"

#### La source de tension réelle

Pour des raisons évidente, un source de tension parfaite ne peut pas exister. Si la tension est constante peu importe le courant I débité par la source, cela sous-entendrait que la puissance augmenterait linéairement en fonction de l'intensité (pour 1000 Ampères et 5V, nous aurions 5000W, pour 100kA, nous aurions 500kW, etc... ce qui n'a évidemment aucun sens si on parle d'une batterie de téléphone par exemple).

En réalité, la source de tension doit prendre en compte les pertes par effet Joule. Pertes qui sont responsables de la limitation de puissances sur tous les types de générateurs. Pour modéliser cette perte par effet Joule, nous pouvons rajouter une résistance interne en série avec la source de tension.

On se retrouve donc avec un modèle équivalent à une source réelle de tension :

[![Modèle équivalent d'une source de tension réelle](/res/images/Cours_LesSourcesDEnergieElectrique/ModeleEquivalentSourceTensionReelle.png#center "Modèle équivalent source de tension réelle")](/res/images/Cours_LesSourcesDEnergieElectrique/ModeleEquivalentSourceTensionReelle.png)

Où l'on voit bien la résistance interne, ici R1 et R2 qui représente la charge alimentés par un générateur parfait V1.

On peut en déduire que la tension du générateur réel de tension (ici V1 et R1) que l'on mesurera au bords de la borne "-" du générateur et la borne de la résistance qui n'est pas en contact avec le générateur (ou plus simplement aux bornes de R2) sera donnée par la formule suivatne :

$$E = \text{UV1} - \text{UR1}$$

$$\Rightarrow E = \text{UV1} - (\text{R1} * I)$$

Et cette fois ci, la tension n'est bel et bien plus du tout constante mais plus l'intensité devient grande, et plus la chute de tension dans la résistance R1 est grande à cause des pertes dues à l'effet Joule.

[![Courbe caractéristique d'une source de tension réelle](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceTensionReelle.png#center "Courbe caractéristique d'une source de tension réelle")](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceTensionReelle.png)

Nous voyons bien sur la courbe que le coefficient directeur est l'opposé de la valeur de la résistance interne de la source de tension.

Une résistance interne de 2Ω peut être beaucoup ou peu selon les types d'alimentation et ce que l'on alimente. Mais avec cette résistance interne, nous pouvons remarquer que la tension chute assez vite et atteint 0V pour I = 2.5A (En effet, 5 - 2*2.5 = 0 pour reprendre la formule).

Note : La résistance interne d'une source de tension peut être déterminée empiriquement avec la tension de l'alim pendant qu'elle tire du courant et la tension à vide de la source grâce à la formule :

$$\text{UV1} - E = \text{UR1}$$

$$\text{R1} = \frac{\text{UR1}}{I} = \frac{\text{UV1} - E}{I}$$

### La source de courant

#### La source de courant parfaite

Une source de courant parfaite est un générateur dont le courant est parfaitement contant et la tension varie en fonction de la charge

[![Courbe caractéristique d'une source de courant réelle](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceCourantParfaite.png#center "Courbe caractéristique d'une source de courant parfaite")](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceCourantParfaite.png)

#### La source de courant réelle

Pour les mêmes raisons qu'au dessus, une telle source d'énergie ne peut pas exister.

Dans un circuit avec plusieures résistances en série (cf. [source de tension réelle](#la-source-de-tension-réelle)), la tension se sépare entre les résistances, ce qui était pratique pour modéliser les pertes dûes à l'effet Joule. Dans le cas d'une source de courant, il faudrait que l'intensité se sérpare entre les résistances... Pour cela nous allons mettre notre résistance interne en dérivation par rapport à la source !

Nous nous retrouvons donc avec un modèle équivalent à celui-ci :

[![Courbe caractéristique d'une source de courant réelle](/res/images/Cours_LesSourcesDEnergieElectrique/ModeleEquivalentSourceCourantReelle.png#center "Modèle équivalent source de courant réelle")](/res/images/Cours_LesSourcesDEnergieElectrique/ModeleEquivalentSourceCourantReelle.png)

La tension aux bornes de R2 que l'on peut appeler UR2 se calcule donc avec la loi d'Ohm :

$$U_{R2} = R2*(I - I_{R1})$$

Où :
- I est l'intensité totale, ici 2A
- IR1 est l'intensité qui passe dans la résistance interne

Ce qui implique que :

$$I_{R1} = I - I_{R2}$$
$$\Rightarrow I_{R2} = I - (\frac{U_{R2}}{R2})$$

[![Courbe caractéristique d'une source de courant réelle](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceCourantReelle.png#center "Courbe caractéristique d'une source de courant reelle")](/res/images/Cours_LesSourcesDEnergieElectrique/CaractéristiqueSourceCourantReelle.png)

$$\text{Courbe prise avec R2 = 30Ω}$$

Comme nous pouvons le voir sur la courbe, si l'on monte la tension (pas intuitif de considérer l'ordonnée comme variable je sais), l'intensité va doucement se rapprocher de l'odonnée. Pour une tension de 0V, nous retrouvons bien nos 2A, par contre pour 3V, on peut voir que l'intensité a déjà chutée à 1.9A.

L'équation de la courbe étant U(x) = 30(2 - x) = 60 - 30x, nous pouvons facilement deviner que l'intensité sera de 0A lorsque la tension sera à 60V.

&nbsp;