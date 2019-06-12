

# Recherche opérationnelle

# I - Mots clefs

-   Programmation dynamique et linéaire
    
-   Problème de coloration (théorie des graphes)
    
-   Problème du sac à dos
    
-   NP-complétude
    
-   Recherche opérationnelle
    
-   Résolution graphique
    
-   Méthodes heuristiques
    
-   Méthodes approchées
    
-   Algorithme d’approximation
    
-   Optimum: maximum ou minimum d'une fonction à n variables

# II - Contexte

  

-   Quoi ?
    

-   Présentation sur programmation linéaire ou dynamique
    
-   Mettre en avant la recherche opérationnelle avec NP
    
-   Résoudre un problème d’une complexité élevée
    

-   Comment ?
    

-   Algorithme d’approximation
    
-   Problème dynamique
    

-   Pourquoi ?
    

-   Pour résoudr/e le problème

# III - Contraintes
Ø

# IV - Problématique

  

Comment résoudre un problème avec la programmation linéaire ou graphique ?

Comment résoudre un problème complexe avec la recherche opérationnelle ?


# V - Généralisation

-   Optimisation
    
-   Résolution de problèmes
  

# VI - Hypothèses

-   Problème du sac à dos : mettre plus d’objets ayant chacun un poids dans un sac
    
-   Recherche opérationnelle : rechercher une solution pour les problèmes les plus complexes
    
# Recherche opérationnelle

## Définition

- Discipline des méthodes scientifiques utilisables pour élaborer de meilleures décision. Permet de rationaliser, simuler et optimiser l'architecutre et lefonctionnement des systèmes de production ou d'organisation dans des problèmes complexes qui traitent de la **maximisation** d'un profit ou de la **minimisation** d'un coût.
- Carrefou rassociation les mathématiques,l'économie et l'informatique.
- S'appuie sur :
	- Théorie des graphes
	- Programmation linéaire
	- Programmation dynaique
	- Théorie des jeux
- Apparue grâce à l'informatique (moyens nécessaires pour calculer)
    
-   Exemples :
	- Coupe du monde de rubgy (7 j pour 7places, avec les joueurs qui peuvent jouer sur plusieurs pôles)
	- Apparetement magique : ?
	- La barque, le loup et le chou,  la barque ne peut embarquer qu'un passager
	- Le problème du voyageur de commerce
	- **Sac à dos** : Noté également KP (Knapsack Problem) :  Un sac ne peut pas supporter un certain poids avec tout ou partied'un ensemble donné d'objets ayant chacun un poid et unevaleur. Il faut maximiser la valeur sans dépasser le poids maximum. (additionner les poids)
		- **Solution 1 :** Méthode approchée
			- Calculer le rapport poid/valeur pour chaque objet
			- Les trier de par ordre décroissant (plus grand au plus petit)
			- Sélectionner les objets un à un dans l'ordre du tri tant que poid maximal respecté
		- **Solution 2** : Méthode exacte (temps long)
			- Utilisation de la procédure par "*Séparation et évaluation*"
			- Construit un arbre avec toutes les possibilités (en s'arrêtant si valeur supérieure)
			- Parcours à la fin l'arbre pour les solutions réalisables, sélectionnant la valeur maximale
    

## Programmation Linéaire :
- Problèmes d'optimisation où la fonction objectif et les contraintes sont toutes linéaires
- Cherche maximum  ou minimum
- Problème de programmation linéaire
- On modélise pour trouver la solution
	- **Variables** intrinsèques (inconnues) ou variable de décision.
	- **Objectif** visé (optimisation) : Fonction objectif
	-  Différentes **contraintes** auquelles sont soumises ces variable
    Dans un problème de programmation Linéaire, les contraintes et les objectifs sont  des fonctions **linéaires** des variables.

Exemple :
Une usine fabrique 2 produits P1 et P2 nécessitant des ressources d’ ́equipement, de main d’oeuvre et de matières premières disponibles en quantite limitée.

![](https://image.noelshack.com/fichiers/2019/24/3/1560341100-capture.png)P1 rapporte 6€ et P2 4€ à par unité

Quelle **quantité de produits** P1 et P2 doit produire l'usine pour maximiser le bénéfice total venant de la vente des 2 produits ?
- **Variables** = Quantités des produits P1 et T2 fabriqués (x,y)
- **Fonction objectif à maximiser (objectif)** : Bénéfice total F(x,y) = 6x + 4y
- **Contraintes** : Disponibilité de chaque ressources :
	- 3x + 9y < 81
	- 4x + 5y < 55
	- 2x + y < 20
	- x et y > 0
![](https://image.noelshack.com/fichiers/2019/24/3/1560341603-capture.png)
Nb : C'est représenté sous la forme standard 

### Représenter l'inforation pour un programmation linéaire

- **Canonique mixte :** Comme au dessus, avec des contraintes d'inégalités, égalités et de signe. Les variables (inconnus) sont des vecteurs. Les contraintes des martices.
- **Canonique pure :** ????
- **Forme standard :** comme au dessus


## Méthodes de résolutions : 

### Graphique : Utile pour deux variables ou plus


![](https://image.noelshack.com/fichiers/2019/24/3/1560346598-capture.png)
  - 1 - On trace un graphe avec l'axe X et Y  correspondant aux variables
- 2 - On trace les trois contraintes, pour se faire, pour chacune d'elle, on prend X = 0 (pour trouver le Y) puis Y = 0 (pour trouver le X)
- 3 - On place les **points** qui croisent les différentes contraintes, qu'on appellera "**optimum**"
- 4 - On hachure la zone en dessous de chacun des optimum : C'est la liste des possibilités, ou le **domaine réalisable**
- 5 - On trace notre fonction initiale F(x,y) = 6x + 4y = 0). On va trouver une droite. 
- 6 - En décallant cette droite, nous cherchons le dernier optimum
- 7 - On retrouve les coordonnées de cet optimum, ils correspondent au MAXIMUM que l'on peut trouver :) **CAD la solution optimale**. Peut-être unique, multiple, impossible, ou infinie (si une contrainte manque)
    
### Simplex : Utile pour deux variables ou plus

## Dualité

Méthode : 
On transforme la forme canonique de dualité (forme primale) en dual :
- Le min devient un **max**
- On passe les contraintes dans la fonction objective
- On passe le coût dans la fonction objective dans les contraintes (équations)
- On transpose la variable en échangeant les signes
![](https://image.noelshack.com/fichiers/2019/24/3/1560350043-screenshot-1.png)



## Programmation dynamique (Quelques mots dessus)
    

## Workshop
 
