
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
    
-   Optimum

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
    
# VII - Plan d’action

##  Recherche opérationnelle
    
ROADEF (Société française de Recherche Opérationnelle et Aide à la Décision), regroupe ~300 membres individuels et industriels


###   Définition

appliquer des méthodes d'analyse appropriées pour aider à la descision

La RO est la discipline des méthodes scientifiques utilisables pour élaborer de meilleures décisions. Elle permet de rationaliser, de simuler et d’optimiser l’architecture et le fonctionnement des systèmes de production ou d’organisation.

La RO s'appuie sur :

- la Théorie des Graphes (König, 1936 puis Berge, 1958),
- la Programmation Linéaire (Dantzig, 1949),
- la Programmation Dynamique (Bellmann, 1954),
- la Théorie des Jeux (Von Neumann et Morgestern, 1944).



###   Exemples
    
    gouv
    industrie
    banques
    medecine
    business
    transport
    sport
        


###   Méthodes :

####  Programmation linéaire + dualité

variable de decision :     
contraintes : ce qui nous borne
fonction objectif : ce qu'on veut max ou min
forme complete :

forme standard de pour du LP:
minimiser ou maximiser un fonction linéaires objective (linear objective function) sujet à des equations ou inégalités linéaires

on a des variables 
x-flèche = (x_1, x_2, ..., x_n) 
et une fonction objective c-flèche . x-flèche = c_1 x_1, ... , c_n x_n
on peut poser les inégalitéssous forme de matrice A . x-flèche <= (inf-égal) b-flèche

et on cherche à max c-flèche . x-flèche tel que les inégalités soient vraies et x-flèche >= 0


méthode graphique:

exemples : 
contraintes 
	x+y <=20
	3x + 4y <= 72
objectif : 
z =4x+5y

on prends nos contraintes et on cherche le chiffre pour x =0 et y =0
par exemple x+y<= 20 
on cherche 0+y=20 <=> y=20
et x+0=20 <=> x = 20

ça nous fait 1 courbe
(et c'est la courbe y = 20 -x) 

0+4y <= 72
y <= 18
3x + 0 <= 72
x <= 24
(courbe 4y = 72 - 3x)








**dualité**

on peut certif l'optimalité (on peut avec une preuve méthématique de l'algo mais c'est long, donc on fait une preuvecourte qui marche pour notre cas spécifque)

primal LP
max c-flèche . x-flèche tel que les inégalités soient vraies et x-flèche >= 0

forme dual

min b-flèche * y-flèche tel que A^T * y-flèche >= c-flèche et y-flèche >=0






il y a 2 formes: primal et dual 

On suppose que A est une matrice de format m × n et b ∈ R m

soit le pb primal 

min z = c^t x,
Ax >= b,
x >= 0

la dual du pb est 
max z = b^t y,
A^t y < = c,
y >= 0 

On notera que, pour le problème primal, on a x ∈ R n tandis que y ∈ R m pour le dual

Par exemple, considérons le problème suivant 
min z = −x1 − x2 sous les contraintes
 −x1 − 3x2 ≥ −3, 
 −2x1 − x2 ≥ −2, 
 x1, x2 ≥ 0. 
 qui admet la solution (x1, x2) = (3/5, 4/5) et z = −7/5


Le problème dual s’écrit sous la forme :
 max z = −3y1 − 2y2 sous les contraintes
 −y1 − 2y2 ≤ −1,
 −3y1 − y2 ≤ −1,
  y1, y2 ≥ 0.
 qui admet la solution (y1, y2) = (1/5, 2/5) et z = −7/5

Dans cet exemple, on observe que la valeur minimale du primal est égale à la valeur maximale du dual


#### (Programmation dynamique)
    
#### Graphique
    
####  Simplex  

convertit le pb de forme canonique (système d'inéquations) en forme standard (système d'équation avec variables d'écarts). Les variables d'écart introsuites au cours de cette transfo représentent les contraintes 

par exemple :
3x +2y <= 1800 devient 3x + 2y + e1 = 1800
x <=400 <=> x +e2 = 400
y <= 600 <=> y+e3 = 600
max 30x + 50y

         | x | y | e1| e2| e3|    |
    | e1 | 3 | 2 | 1 | 0 | 0 |1800|
    | e2 | 1 | 0 | 0 | 1 | 0 |400 |
    | e3 | 0 | 1 | 0 | 0 | 1 |600 | 
	| max|30 |50 | 0 | 0 | 0 | 0  |


algo:
- forme standard
- construire le tableau de la forme standard
- callback
- choisir les variables à introduire dans la base : choef le plus fort de la fonction éco
- toujours choisir les var à intro dans la base : rapport entre second membres/coef de la variable choisie, on prends celle ayant le ratio le plu faible
- encadrer le pivot et on renome la ligne du pivot qui s'appelle mtn comme la colone du pivot
- multiplie la ligne du pivot par 1/ valeur du pivot
- calc les valeurs des autres lignes: E'_ij = E_ij - [ (A_ij / Pivot)* valeur même colone à la ligne du pivot ] <=> = E_ij - (A_ij / E_xpivot,ypivot)*E_i,ypivot
E_ij coef a transfo et A_ij coef de la colone du pivot (ligne i , colone j)
- les coef de la fonction éco sont ils tous nuls ou négatifs? oui: done, non : goto callback

pour cet exemple: 
coef éc max = 50 colone y
ratio le plus petit parmis 1800/2, 400/0 et 600/1 est 600/1, ligne e3
le pivot est donc y,e3 = 1

donc ligne 1 çafait 
E'_1,1 = E_1,1- (E_xpivot,1 / pivot )*E_1,ypivot
= 3 - (2/1)*0 = 3
E'_2,1 = E_2,1 -(E_xpivot,1/pivot)* E_2,ypivot
= 2 - (2/1)*1 = 0
E'_3,1 = E_3,1 -(E_xpivot,1/pivot)* E_3,ypivot
= 1 - (2/1)*0 = 1
E'_4,1 = E_4,1- (E_xpivot,1/pivot)* E_4,ypivot
= 0 - (2/1)*0 = 0
E'_5,1 = E_5,1 - (E_xpivot,1/pivot)* E_5,ypivot
= 0 - (2/1)*1 = -2
E'_6,1 = E_6,1 - (E_xpivot,1/pivot)*E_6,ypivot
= 1800 -(2/1)*600 = 600

E'_1,2 = E_1,2 - (E_xpivot,2/pivot)* E_1,ypivot
= 1 - (0/1)*0 = 1
E'_2,2 = E_2,2 - (E_xpivot,2/pivot)* E_2,ypivot
= 0-(0/1)*1 = 0 
etc
E'_1,5 = E_1,5 - (E_xpivot,5/pivot)*E_1,ypivot
= 30 - (50/1)*0 = 30
E'_2,5 = E_2,5 - (E_xpivot,5/pivot)*E_2,ypivot
= 50 - (50/1)*1 = 0
E'_3,5 = E_3,5 - (E_xpivot,5/pivot)*E_3,ypivot
= 0 - (50/1)*0 = 0
E'_4,5 = E_4,5 - (E_xpivot,5/pivot)*E_4,ypivot
= 0 - (50/1)*0 = 0
E'_1
4,5 = E_5,5 - (E_xpivot,5/pivot)*E_5,ypivot
= 0 - (50/1)*1 = -50
E'_6,5 = E_6,5 - (E_xpivot,5/pivot)*E_6,ypivot
= 0 - (50/1)*600 = -30 000

         | x | y | e1| e2| e3|      |
    | e1 | 3 | 0 | 1 | 0 |-2 | 600  |
    | e2 | 1 | 0 | 0 | 1 | 0 | 400  |
    | e3 | 0 | 1 | 0 | 0 | 1 | 600  | 
	| max|30 | 0 | 0 | 0 |-50|-30000|

tous les coefs de la fonction éco sont ils à 0 ou négatif ? non, on recommence

trouver le coef max de la foction éco: 30, rapoort min entre 600/3, 400/1 et 600/0 est 600/3 le pivot est en x,e1 = 3

on refait les calculs

        | x | y | e1 | e2| e3 |      |
    | x | 1 | 0 |1/3 | 0 |-2/3| 200  |
    |e2 | 0 | 0 |-1/3| 1 |2/3 | 200  |
    | y | 0 | 1 | 0  | 0 | 1  | 600  | 
	|max| 0 | 0 |-10 | 0 |-30 |-36000|

tous les coef de la fonction d'evo ont <= 0 on a donc fini
on a x = 200, y = 600 pour un profit de 36 000 € e1 et e3 sont saturés mais pas e2 qui pouvait encore venre 200 produits sans une des contraintes




nb de slack variable = nb de contraintes
nb de var = nb de variables non basiques
z est ce qu'on veut max

ex: pour 3var et 2 constr on a :
x1, x2, x3, s1, s2 et z

on fait un tableau
ex pour z = 8x1 + 10x2 + 7x3
et contraintes:
x1+3x2+2x3 <= 10
x1 + 5x2 + x3 <= 8

on reformule z en mettant 0 = sthg 
donc ici
-8x1 -10x2 - 7x3 +z = 0

       |x1 | x2 | x3 | s1 | s2 | z
       |1  | 3  | 2  | 1  |  0 | 0  | 10 | 10/3
       |1  | 5  | 1  | 0  |  1 | 0  | 8  |  8/5
       | -8|-10 | -7 | 0  |  0 | 1  | 0

on cherche le terme le plus négatif, ici -10 donc on "pivote" sur la colone du -10
on calcule la constante ( l'autre côté du égal) / la valeur 
le ratio le plus petit est 8/5 donc on pivote sur le 5 (colone de l'indicateur plus négatif et ligne du plus petit ratio)

on veut en faire un 1 donc on multiplie la ligne 2 par 1/5 
-3*R2 +R1 dans r1 pur annuler le 3
*10R2 +R3 dans r3

###   Workshop

### Corbeille


1 combien d’arbres de chaque culture faut-il planter pour maximiser la valeur de l’exportation annuelle ?

(production*prix - cout arbre)/(surface*manpower)

orange 10.4
clémentine : 17.45

vu que le coût est négligeable il doit être coût/heure de travail donc ça donne
(production*prix)/(surface*manpower*coût)
clémentine 11
orange 5.2
250k m²
20M de budget
dans tous les cas on est mieux à faire des clémentines

41666 pieds de clémentines ( 249 996m²)
et 4 m² donc 1 oranger


y = (a*150*10-2)/(4*36)
y = (b*200*15-0.5)/(72*5)
y = (c*50*15-1)/(50*3)
y = (d*150*7-1.5)/(10*6)

objectif max (a*150*10 + b*200*4 + c*50*15 + d*150*7)

contraintes:

4a+5b+3c+6d <= 250 000
2a+0.5b+c+1.5d <= 20M
36a+72b+50c+10d <= 8*200 *365


2 : 
max : 200* m1 + 150* m2 + 120*m3

découpe 315
finition 110
peinture 50

m1 = 15a+2b+1c
m2 = 7.5a+3b+c
m3 = 5a+2b+c

contrainte

15m1+7.5m2+5m3 <= 315
2m1+3m2+2m3 <= 110
m1+m2+m3 <= 50

3:

obj : min (a+b+c+d+e+f)
 contraintes:
 h = ancien_-1 - ancien_-2 + new
f+a <= 4
a+b <= 8
b+c <= 10
c+d = ?
d+e <= 12
e+f <= 4




II - algébrique

max 400x+ 800y

x+y <= 10k
2x+6y <=48k
3x+y <= 24k



y = 10k- x     | 1        |
y = 8k - x/3  |     |2     |
y = 24k- 3x        |      | 3

p1:    0 = 2k -2x/3 
<=> 2x = 6k 
          x = 3k 
  <=> y = 7k
p2:
16k -3x + x/3 = 0
x/3 - 3x = -16k
8x/3 = 16k
8x = 48k
x = 6k
<=> y = 6k

p3:  
 14k - 2x = 0
 x = 7k
 <=> y = 3k


p1 : 3,7
p2: 6,6
p3 : 7,3

400x + 800y



# WS


x_1 nb de kilos d'ingrédient 1 à utiliser
x_2 nb de kilos d'ingrédient 2 à utiliser

contraintes : 

x_1 / (x_1+ x_2) <= 0.8 ∅
x_2 /( x_1 + x_2) <= 0.5 ∅
x_1 + x_2 <= 100 kg

fonction économique :

max (50 * (x_1+x_2) - (x_1*10 + x_2 * 20) - 5* (x_1 + x_2))
      €/kg *( kg + kg) - (kg *€/kg + kg*€/kg) - €/kg*(kg+kg) = chaque fois on a kg* €/kg = €
<=>
max (35x_1 + 25x_2)


programme linéaire: 

maximiser 35x_1 + 25x_2
	tel que 
		x_1 / (x_1+ x_2) <= 0.5
		x_2 /( x_1 + x_2) <= 0.8
		x_1 + x_2 <= 100


équations:

1:
x_1 <= 0.5x_1 + 0.5x_2
0.5x_1 <= 0.5x_2
x_2 <= -x_1

2:
x_2 <= 08x_2 + 0.8x_1
0.2x_2 <= 0.8x_1
0.2/0.8 *x_2 <= x_1
x_1 <= -x_2/4

3:
x_2 <= 100 - x_1

exo 2 
x1 à x9 quantité de chaque aliage

(x1*0.2 + x2*0.5 + x3* 0.3 + x4* 0.3 + x5* 0.3 + x6* 0.6 + x7* 0.4 + x8* 0.1 + x9* 0.1) / (x1+x2+x3+x4+x5+x6+x7+x8+x9) <= 0.3

(x1*0.3 + x2*0.4 + x3* 0.2 + x4* 0.4 + x5* 0.3 + x6* 0.3 + x7* 0.5 + x8* 0.3 + x9* 0.1) / (x1+x2+x3+x4+x5+x6+x7+x8+x9) <= 0.3

(x1*0.5 + x2*0.1 + x3* 0.5 + x4* 0.3 + x5* 0.4 + x6* 0.1 + x7* 0.1 + x8* 0.6 + x9* 0.8) / (x1+x2+x3+x4+x5+x6+x7+x8+x9) <= 0.4

fonction éco:

min : x1*7.3 + x2*6.9 + x3* 7.3 + x4* 7.5 + x5* 7.6 + x6* 6.0 + x7* 5.8 + x8* 4.3 + x9 * 4.1


exo 3 :
on veut mettre le plus de qualité (somme des qualités la plus haute) dans l'espace fournis

somme poid <= 500Mo
objectif : max somme notes

contrainte :
somme sur n, i= 1 de x_n*poid_n <= 500

objectif : 
max (somme sur n, i =1 de x_n*note_n )

ici on a 10 var

contr :
x1*40+ x2* 52+ x3*27+ x4*68+ x5*80+ x6*62+ x7*63+ x8*53+ x9*56+ x10*59

obj : 
x1*2+ x2*5 +x3*1 + x4*2 + x5*3 + x6*5 + x7*2 +x8*3 +x9*1 +x10*1
