

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
	- La barque, le loup et le chou, et une chèvre :   la barque ne peut embarquer qu'un passager
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
- Problèmes d'optimisation où la fonction objectif et les contraintes sont toutes linéaires == pas de puissance (y = ax + n)
- Cherche maximum  ou minimum
- Problème de programmation linéaire
- On modélise pour trouver la solution
	- **Variables** intrinsèques (inconnues) ou variable de décision.
	- **Objectif** visé (optimisation) : Fonction objectif
	-  Différentes **contraintes** auquelles sont soumises ces variable
    Dans un problème de programmation Linéaire, les contraintes et les objectifs sont  des fonctions **linéaires** des variables (positives).

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

### Représenter l'infomration pour un programmation linéaire

- **Canonique :**Comme au dessus, avec des inéquations
- **Forme standard :** Vérifie les conditions suivantes  :
	- Les variables du problème doivent-être positives
	- Le type d'optimisation doit-être une recherche de maximum
	- Les contraintes sont des contraintes d'**égalités**
Transformation des variables :
- Si une variable X est négative, on pose y = -x. Ainsi on garde la linéaire
- Si une variable X est de signe quelconque, on pose X = X1-X2 où X1 et X1 nouvelles variables positives
- Si type optimisation =min : On procède à min(Z) = -Max(-Z)
- Pour transformer les inégalités en égalité, on ajout des variables dites "variables d'écart" qui doivent-être positives.
	- Si le signe est <= ou < alors : rajouter une variable + e à l'inéquation pour remplacer par un '='
	- Si le signe est >= ou > alors : rajouter une variable - e à l'inéquaton pour remplacer par un '='
![](https://image.noelshack.com/fichiers/2019/24/4/1560417600-canonique.png)![](https://image.noelshack.com/fichiers/2019/24/4/1560417600-cart.png)


- **Forme matricielle :** ?
- **Forme dual** : ?

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
- Développée en 1947 par George Dantzig
- Méthode algébrique basée sur la résolution de systèmes d'équations linéaires à n variables
- Méthodede "Gauss-Jordan" permet d'identifier : Variables fixées / dépendantes / indépendances

Le principe de la méthode est de transformer les contraintes qui sont des inéquations en équations en ajoutant des variables positives que l'on appelle variable écart. Puis on transforme ce système d'équations linéaire jusqu'à trouver la solution optimale.

- 1- Formulation mathématique du problème
- 2 - Mise sous forme **standard** du problème. On obtient donc des "e" qui sont les variables d'écart, ou "**en départ de base**". Alors que le X et Y sont dites "**Hors base**".
- 3 - Applicationde l'algorithme du simplexe

### **Méthode algébrique  :**

Soit le programme suivant : 
```J
X1 + X2 <= 21 000

X1 <= 13 000

X2 >= 6000

X1 - 2X2 <= 0

xi >= 0 pour i = 1,2

F max (x1, x2) = 0.1X1 + 0.08X2
```
- 1) Rajouter des **variables d'écarts** "e" pour transformer en "="

```J
X1 + X2 + e1 = 21 000

X1  + e2 = 13 000

X2 - e3 = 6000

X1 - 2X2 + e4 = 0

F max (x1, x2) = 0.1X1 + 0.08X2
```
- 2) Déterminer un programme de base qui servira de départ au cheminement ver la solution optimale (programme optimal).
	- On passe les "e" de l'autre côté (aussi appellés variables "dans le programmes") alors que X1 et X2 sont des variables hors programme.
```J

e1 = 21000 - X1 - X2

e2 = 13000 - X1

e3 = - 6000 + X2

e4 = - X1 + 2X2
```
-  On remplace les variables "hors programme" par leur valeur (0) 

```J
e1 = 21000 - X1 - X2  = 21000 – 0 – 0 = 21000

e2 = 13000 - X1  = 13000 – 0  = 13000

e3 = - 6000 + X2 = - 6000

e4 = - X1 + 2X2 =  0 + 6000 = 0

FE max (ou min) (….) =  0.1 * 0 + 0.08*0 = 0
```
	- Quelle est la sigification de cette solution ? Non investissement du capital
	- Est-ce une solution admissible : Non (0,0) ne respecte pas la contrainte X2 >= 6000
	- Est-ce une solution optimale : Non (cf ci dessous)
- 3 : Expliciter la fonction économique et déterminer si elle peut-être améliorée : recherche de l'éventuelle variable (hors programme) admettant le plus grand coefficient positif.  Dans la négative, le programme est optimal
	-  On repars sur notre équation de tout à l'heure:
```J
e1 = 21000 - X1 - X2

e2 = 13000 - X1

e3 = - 6000 + X2

e4 = - X1 + 2X2
```
-  On choisis une variable '**entrante**',  qui correspond à la valeur la plus haute dans la valeur de la fonction économique (ici X1)
- 4 - On va chercher pour ce X1 dans les équations du dessus, la valeur positive la plus petite, pour y récupérer la variable **sortante** (e). Ici ce sera **e2**. (X1 = 13 000). On ne prend pas X1=0 car il sort du calcul.
- 5 - Pour déterminer un nouveau programme de base,on doit transformer le système d'équations ainsi que l'expression de la fonction économique en exprimant les variables dans le programme de base en fonction des variable hors programme (par substitution)
	-  On remplace donc le e2 par substitution :
On a = x1 = 13000 - e2, donc :
```J
x1 = 13000 - e2
(substitutions)
e1 = 21000 - X1 - X2 = 21000 -13000 + e2 - X2 = 8000 + X4 - X2
e3 = - 6000 + X2
e4 = -13000 + e2 + 2X2
F max (x1, x2) = 0.1X1 + 0.08X2
F max (x1, x2) = 0.1*(13000 - e2) + 0.08X2
F max (x1, x2) = 1300 – 0,1e2 + 0.08X2
```
En simplification :
```J
x1 = 13000 - e2
e1 = 8000 + e2 - X2
e3 = - 6000 + X2
e4 = -13000 + e2 + 2X2
F max (x1, x2) = 1300 – 0,1e2 + 0.08X2
```
- Avec comme variable hors programme "X4 = X2 = 0"
- Et dans le programme X1 / E1/E3/E4

6 - On fais la même chose mais pour X2 cette fois ci :
``` J
x1 = 13000 - X4   ⇒ à Pas dépendante de X2 donc 0

e1 = 8000 + X4 - X2 ⇒  X2 = 8000

e3 = - 6000 + X2  ⇒  X2 = 6000 : "On prend le 6000 car c'est le plus petit"

e4 = -13000 + X4 + 2X2 ⇒  X2 = 6500
```

e3 = - 6000 + X2 ⇒ On récupère cette ligne
```J
x2 =  6000 + X5

(substitutions)

x1 = 13000 - X4

x3 = 8000 + X4 - X2 =  8000 + X4 - 6000 - X5 =  2000 + X4 - X5

x 6 = -13000 + X4 + 2X2 = -13000 + X4 + 12000 + 2 X5 = = -1000 + X4 + 2 X5

**F max (**x1, x2**)** = 1300 – 0,1X4 + 0.08X2

**F max (**x1, x2**)** = 1300 – 0,1X4 + 0.08*(6000 + X5)

**F max (**x1, x2**)** = 1300 – 0,1X4 + 480 + 0,08X5

**F max (**x1, x2**)** = 1780 – 0,1X4 + 0,08X5
```

Ce qui donne en forme simplifiée (avec x2 =  6000 + e3)
```J
x1 = 13000 - X4

x2 =  6000 + e3

e1 =  2000 + e3 - e4

e4 = -1000 + e3 + 2 e3

**F max (**x1, x2**)** = 1780 – 0,1X4 + 0,08X5
```
{...} on contiunue jusqu'à trouver la solution minimale, c à d qu'on trouve x1 et x2 :)


## Dualité
- On inverse un primal (problème initial). Ca revient à chercher les solutions qui ne sont pas possibles.
- En faisant le dual du dual, on trouve le pirmal
- Permet de trouver le plus bas prix total à payer pour l'acheteur doit être égal au bénéfice maximal pour le producteur

Méthode : 
On transforme la forme canonique de dualité (forme primale) en dual :
- Le min devient un **max**
- On passe les contraintes dans la fonction objective
- On passe le coût dans la fonction objective dans les contraintes (équations)
- On transpose la variable en échangeant les signes
![](https://image.noelshack.com/fichiers/2019/24/3/1560350043-screenshot-1.png)



## Programmation dynamique (Quelques mots dessus)

La programmation dynamique consiste à résoudre un problème en le décomposant en sous-problèmes, puis à résoudre les sous-problèmes, des plus petits aux plus grands en stockant les résultats intermédiaires. Elle a d'emblée connu un grand succès, car de nombreuses fonctions économiques de l'industrie étaient de ce type, comme la conduite et l'optimisation de procédés chimiques, ou la gestion de stocks.
- Botom up & bottom down

## Corbeille Exo


### Partie 1 : Modélisation

 **1 : Production agricole :**

- **Variables** = Quantités d'arbre O, C, P, Cl plantés (o,ci,p,cl)
- **Fonction objectif à maximiser (objectif)** : Max exportation F(o,c,p,c) = (o150 *10) + (ci200*4) + (p50*15) + (cl150*7) 
- **Contraintes** : Disponibilité de chaque ressources :
	- o4 + ci5 + p3 + cl6 <= 250 000 //Surface
	- o2 + ci0.5 + p1 + cl1.5 <= 20 000 000 //Coûts
	- (o36 + ci72 + p50 + cl10)  <= 200*8*365 //Personnel
	- o,c,p,c >= 0
	- //Abres productifs la troisième année 

**2 : Production de meubles IKEA**


- **Variables** = Meubles M1, M2, M3
- **Fonction objectif à maximiser (objectif)** : Majeur bénéfice F(M1,M2,/M3) = 200M1, 150M2, 120M3
- **Contraintes** : Disponibilité de chaque ressources :
	- 15M1 + 7.5M2 + 5 M3 <= 315 //Découpe
	- 2M1 + 3M2 + 2M3 <= 110 //Finission
	- M2 + M3 <= 50 //Peinture <-- vérrifier valeur (pas sûr)

**3 : Planification**


- **Variables** =  Chauffeur C, NBTaxis T, HoraireDépart HD
- **Fonction objectif à maximiser (objectif)** : Minimiser nombre chauffeur F(C,HD,T ) = C + HD
- **Contraintes** : Disp4nibilité de chaque ressources :
	- (HD % 8 == 0) //Heure départ 
	- C >= T //Nombre de chauffeurs supérieur ou égal aux nombre de taxis

⇒ Correction:

- **Variables** : C1/C2/C3/C4/C5/C6 le nombre  de chauffeurs pour chaque horaires
- **Fonction objectif :** C1 + C2 + C3 + C4 + C5 + C6
- **Contraintes** :
	- C1 + C6  = 4 
	- C1 + C2 = 8
	- C2 + C3 = 10
	- C4 + C5 = 12
	- C5 + C6 = 4

### Partie 2 : Résolution algébrique



### Corbeille exo

**Résolution graphique en python**
``` PYTHON
import numpy as np  
import matplotlib.pyplot as plt  
  
xmax = 100  
x = np.linspace(0, xmax) # on genere l'intervalle des x  
x = np.arange(0, xmax) # on genere l'intervalle des x - optimisation afficher  
  
y = 100-x # x < 100  
y2 = x # x1 <= x2  
y3 = 4*x # x2 <= 4x1  
ymax=max(np.amax(y), np.amax(y2), np.amax(y3)) # optimisation affichage  
  
# on trace la droite  
plt.plot(x, y)  
plt.plot(x,y2)  
plt.plot(x,y3)  
  
plt.fill_between(x, y,ymax, color='lightgrey')  
plt.fill_between(x, y2, color='lightgrey')  
plt.fill_between(x, y3,ymax, color='lightgrey')  
  
# on dessine entre 0 et les extremas de la fonction #optimisation afficher  
  
plt.xlim(0, xmax)  
plt.ylim(0, ymax)  
#plt.gcf().set_size_inches(18, 10) # cette fois on affiche en grand  
plt.show()
```


**Résolution algébrique :**

```PYTHON
from pulp import *
import numpy as np
from IPython.display import display, Latex

x1=LpVariable("X_1", 0, None)
x2=LpVariable("X_2", 0, None)
x3=LpVariable("X_3", 0, None)
x4=LpVariable("X_4", 0, None)
x5=LpVariable("X_5", 0, None)
x6=LpVariable("X_6", 0, None)
x7=LpVariable("X_7", 0, None)
x8=LpVariable("X_8", 0, None)
x9=LpVariable("X_9", 0, None)


#probleme
prob = LpProblem("alliage", LpMinimize)

#objectif
prob += 7.3*x1 + 6.9 *x2 + 7.3*x3 + 7.5*x4 + 7.6*x5 + 6*x6+ 5.8*x7 + 4.3*x8 + 4.1*x9

#contraintes
prob += (x1*0.2 + x2*0.5 + x3*0.3 + x4*0.3 + x5*0.3 + x6*0.6 + x7*0.4 + x8*0.1 + x9*0.1) <= 0.3
prob += (x1*0.3 + x2*0.4 + x3*0.2 + x4*0.4 + x5*0.3 + x6*0.3 + x7*0.5 + x8 * 0.3 + x9*0.1) <= 0.3
prob += (x1*0.5 + x2*0.1 + x3*0.5 + x4*0.3 + x5*0.4 + x6*0.1 + x7*0.1 + x8 * 0.6 + x9*0.8) <= 0.4
prob += x1 + x2 + x3 + x4 + x5 + x6 + x7 + x8 + x9 == 1

prob.solve()
print(LpStatus[prob.status])
print("Min=", value(prob.objective))

# variables resultat
#for v in prob.variables():
#    print("%s=%.2f"%(v.name,v.varValue), end=', ')
    
# variables resultat
result=""
for v in prob.variables():
    valeur=round(v.varValue*100, 2)
    if valeur > 0:
        result += "$"+v.name+"="+str(valeur)+"\%$, "

display(Latex(result))
```


