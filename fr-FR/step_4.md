## Détection de collision

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Les jeux de coureurs sans fin se terminent souvent lorsque le joueur entre en collision avec un obstacle.
</div>
<div>

![Image de l'étape terminée.](images/collision.png){:width="300px"}

</div>
</div>

Tu peux maintenant configurer ton joueur pour qu'il réagisse à une collision avec un obstacle.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">**La détection de collision**</span> détermine le moment où deux objets créés dans une simulation informatique (qu'il s'agisse d'un jeu, d'une animation ou d'autre chose) se touchent. Il y a plusieurs façons de le faire, par exemple : 
  - vérifier si les couleurs apparaissant à l'emplacement d'un objet sont les couleurs de cet objet, ou d'un autre
  - suivre la forme de chaque objet et vérifier si ces formes se chevauchent
  - créer un ensemble de points de délimitation, ou lignes, autour d'un objet et vérifiant s'ils entrent en contact avec d'autres objets "collisionnables"
Lorsqu'une telle collision est détectée, le programme peut réagir d'une manière ou d'une autre. Dans un jeu vidéo, il s'agit généralement d'infliger des dégâts (si le joueur entre en collision avec un ennemi ou un danger) ou de donner un avantage (si le joueur entre en collision avec un bonus).
</p>

--- task ---

Dans ta fonction `dessine_joueur()`, crée une variable appelée `collision` et régle-la pour obtenir la couleur à la position du joueur.

--- code ---
---
language: python
filename: main.py - draw_player()
---

collision = get(mouse_x, joueur_y)

--- /code ---

--- /task ---

--- task ---

Crée une condition pour vérifier `if` la variable `collision` est la même que la variable `sur` — si c'est le cas, alors ton joueur touche l'arrière-plan en toute sécurité et n'a pas heurté un obstacle.

Déplace ton code pour dessiner ton joueur à l'intérieur de ta condition `if collision == sur` et ajoute du code dans l'instruction `else` pour que le joueur réagisse à la collision.

**Choisir :** Comment ton joueur doit-il réagir ? Tu pourrais :
+ Remplacer l'image par une version `chute`
+ Utiliser un emoji différent pour le joueur
+ Tu peux utiliser `tint()` pour changer l'apparence d'une image, n'oublie pas d'appeler `no_tint()` après avoir dessiné l'image

--- collapse ---
---
title: Changer l'image
---

Tu peux utiliser une image différente pour représenter ton joueur lorsqu'il entre en collision avec un obstacle.

Voici un exemple :

--- code ---
---
language: python
filename: main.py - draw_player()
---

def dessine_joueur(): joueur_y = int(height * 0.8)

  collision = get(mouse_x, joueur_y)

  if collision == sur: #sur l'arrière plan image(ski, mouse_x, joueur_y, 30, 30) else: #collision image(chute, mouse_x, joueur_y, 30, 30)

--- /code ---

--- /collapse ---

--- collapse ---
---
title: Utiliser les caractères emoji
---

Tu peux utiliser des caractères emoji dans la fonction p5 `text()` pour représenter ton joueur après collision.

Voici un exemple :

--- code ---
---
language: python
filename: main.py - setup()
---

def configuration(): size(400, 400) text_size(40) #Contrôle la taille de l'emoji text_align(CENTER, TOP) #Position autour du centre

--- /code ---

--- code ---
---
language: python
filename: main.py - dessine_joueur()
---

def dessine_joueur(): if collision == sur: #sur l'arrière-plan text('🎈', mouse_x, joueur_y) else: #collision text('💥', mouse_x, joueur_y)

--- /code ---

--- /collapse ---

[[[processing-tint]]]

[[[generic-theory-simple-colours]]]

--- /task ---

--- task ---

**Test :** Vérifie si une collision est détectée et si la réaction a lieu à chaque fois qu'une collision se produit.

--- /task ---

--- task ---

**Débogage :** Il est possible que tu trouves des bogues dans ton projet que tu dois corriger. Voici quelques bogues assez courants.

--- collapse ---
---
title: Il n'y a pas de collision lorsque le joueur atteint un obstacle
---

Si ton personnage joueur touche l'obstacle et que rien ne se passe, il y a quelques points à vérifier :

 - Assure-toi d'appeler `dessine_obstacles()` avant `dessine_joueur()`. Si tu vérifies les collisions avant de dessiner les obstacles dans un cadre, il n'y aura aucun obstacle avec lequel entrer en collision !
 - Assure-toi que tu utilises exactement la même couleur lors du dessin de l'objet et dans l'instruction `if` vérifiant la collision. Tu peux t'en assurer en utilisant la même variable `globale` aux deux endroits.
 - Dessines-tu le personnage du joueur avant de vérifier la couleur aux coordonnées de la souris ? Si c'est le cas, tu n'obtiendras jamais que les couleurs du joueur. Tu dois d'abord vérifier la couleur et **puis** dessiner le joueur.
 - As-tu du code dans la partie `else` pour faire quelque chose de différent lorsqu'une collision est détectée, comme appliquer une teinte ou utiliser une image différente ?
 - As-tu correctement indenté le code de ton instruction `if` afin qu'elle s'exécute lorsque la condition est remplie ?

L'impression de la couleur du pixel dont tu vérifies une collision peut être utile :

```python
  impression (red (collision), green (collision), blue (collision))
```

Tu peux également imprimer un cercle autour du point que tu vérifies et ajuster le point que tu vérifies si tu dois :

```python
  no_fill()
  ellipse(mouse_x, joueur_y, 10, 10) #Dessiner un point de collision
```

--- /collapse ---

--- /task ---

--- task ---

**Facultatif :** Pour le moment, tu ne détectes que des collisions sur un pixel de ton joueur. Tu peux également détecter des collisions au niveau d'autres pixels au bord de ton joueur, tels que les bords inférieur ou les plus à gauche et à droite.

--- collapse ---
---
title: Détection de collision avec plusieurs pixels
---

```python
def dessine_joueur():

  joueur_y = int(height * 0.8)
  #Utile pour le débogage
  #Dessiner des cercles autour des pixels pour vérifier les collisions

  no_fill()
  ellipse(mouse_x, joueur_y, 10, 10) #Dessiner le point de collision
  ellipse(mouse_x, joueur_y + 40, 10, 10)
  ellipse(mouse_x - 12, joueur_y + 20, 10, 10)
  ellipse(mouse_x + 12, joueur_y + 20, 10, 10)

  collision = get(mouse_x, joueur_y )
  collision2 = get(mouse_x - 12, joueur_y + 20)
  collision3 = get(mouse_x + 12, joueur_y + 20)
  collision4 = get(mouse_x, joueur_y + 40)

  if mouse_x < width : #À gauche de l'écran
    collision2 = sur

  if mouse_x > width: #à droite de l'écran
    collision3 = sur

  if collision == sur and collision2 == sur and collision3 == sur and collision4 == sur:
    text('🎈' , mouse_x, joueur_y)
  else :
    text('💥', mouse_x, joueur_y)
```

--- /collapse ---

Tu peux même utiliser une boucle et vérifier de nombreux pixels différents. C'est ainsi que fonctionne la détection de collision dans les jeux.

--- /task ---

--- save ---
