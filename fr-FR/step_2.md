## Définir le thème

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Définis le thème de ton jeu et crée un personnage joueur qui suit le pointeur de la souris.

</div>
<div>

![Image d'une tortue de taille 100 x 100 sur un arrière-plan bleu avec une taille d'écran de 400 x 400.](images/theme-turtle.png){:width="300px"}

</div>
</div>

Quel est le thème de ton jeu ? Voici quelques idées:
- Un sport ou un hobby
- Hobbies
- Sciences ou nature
- Nature

--- task ---

Open the

Don't Collide! Ouvre le [projet de démarrage](https://trinket.io/python/829ed78936){:target="_blank"}. The code editor will open in another browser tab.</p> 

If you have a Raspberry Pi account, you can click on the **Save** button to save a copy to your **Projects**.

--- /task ---

--- task ---

**Choisir :** Définis la taille de ton canevas.

--- code ---


---

filename: main.py - setup()



line_highlights: 10
---

def setup():    
size(400, 400)

--- /code ---

--- /task ---

--- task ---

Crée une variable appelée `sur` pour stocker la couleur d'arrière-plan en fonction du thème que tu souhaites pour ton jeu. 

Il s'agit de la couleur sur laquelle le joueur peut être en sécurité et tu utiliseras à nouveau cette variable plus tard.

--- code ---


---

filename: main.py - draw()



line_highlights: 14, 15, 16
---

def draw():    
sur = color(200, 100, 0) #Ajouter la couleur de ton thème   
background(sur)

--- /code ---

[[[generic-theory-simple-colours]]]

--- /task ---

--- task ---

**Test :** Exécute ton code pour voir la couleur d'arrière-plan. Modifie-le jusqu'à ce que tu sois satisfait de la couleur et de la taille de l'écran.

--- /task ---

Choisis maintenant le personnage qui joue au jeu et évite les obstacles. Est-ce un objet, une personne, un animal ou autre chose ?

Le joueur apparaîtra à une position fixe `y` et à la même position `x` que le pointeur de la souris, qui est stocké dans la variable `p5` `mouse_x`. 

--- task ---

C'est une bonne idée d'organiser le code pour dessiner le personnage du joueur dans une fonction.

Définis une fonction `dessine_joueur()` et crée une position `joueur_y` pour la position fixe `y` du joueur : 

--- code ---


---

filename: main.py - dessine_joueur()



line_highlights: 12-14
---

def dessine_joueur():    
joueur_y = int(height * 0.8) #Positionné vers le bas de l'écran

--- /code ---

Ajoute du code à `draw()` pour appeler `dessine_joueur()` à chaque image.

--- code ---


---

filename: main.py - draw()



line_highlights: 19
---

def draw():    
sur = color(200, 100, 0) #Ta couleur choisie    
background(sur)    
dessine_joueur()

--- /code ---

--- /task ---

Ensuite, tu ajouteras du code à la fonction `dessine_joueur()` pour dessiner ta forme. Tu devras peut-être également ajouter le code `setup()`.

--- task ---

**Choisir :** À quoi ressemble ton joueur ? Ton joueur pourrait être :

+ Une image fournie dans le projet de démarrage
+ Un emoji 🎈 ou un texte
+ Un dessin utilisant une série de formes

--- collapse ---


---



title: Utiliser une image de démarrage
---

Les images incluses dans le projet de démarrage seront affichées dans la liste `Bibliothèque d'images`.

![La bibliothèque d'images avec la liste des images incluses.](images/starter-images.png)

Note le nom de l'image que tu souhaites utiliser.

Charger l'image dans la fonction `setup()` 

--- code ---


---

filename: main.py - setup()



line_highlights: 11-12
---

def configuration():   
size(400, 400)    
joueur = load_image('skiing.png') #Charger ton image

--- /code ---

Appelle `image()` et définis-la comme global dans la fonction `dessine_joueur()`.

--- code ---


---

filename: main.py - dessine_joueur()



line_highlights: 16
---

def dessine_joueur():    
joueur_y = int(height * 0.8) #Positionné vers le bas de l'écran

--- /code ---

--- /collapse ---

--- collapse ---


---



title: Utiliser les caractères emoji
---

Tu peux utiliser des caractères emoji dans la fonction p5 `text()` pour utiliser un emoji pour représenter ton joueur. 

Voici un exemple :

--- code ---


---

filename: main.py - setup()



line_highlights: 11-13
---

def configuration():    
size(400, 400)     
text_size(40) #Contrôle la taille de l'emoji     
text_align(CENTER, TOP) #Position autour du centre

--- /code ---

global joueur

--- code ---


---

filename: main.py - dessine_joueur()



line_highlights: 16-17
---

def dessine_joueur():     
joueur_y = int(height * 0.8)    
text('🎈', mouse_x, joueur_y)

--- /code ---

--- /collapse ---

[[[processing-python-text]]]

[[[generic-theory-simple-colours]]]

[[[processing-python-ellipse]]]

[[[processing-python-rect]]]

[[[processing-python-triangle]]]

[[[processing-tint]]]

[[[processing-stroke]]]

**Astuce :** Tu peux utiliser plusieurs formes simples dans la même fonction pour créer un joueur plus complexe.

--- collapse ---


---



title: Dessiner un joueur à l'aide de plusieurs formes
---

![A face shape made from a green circle as a background and two eyes drawn from blue circles, with black circles within and a glint within those using a white circle.](images/face_player.png)

--- code ---


---

language: python



filename: main.py - draw_player()
---

def dessine_joueur():    
joueur_y = int(height * 0.8)    
noStroke()    
#Le visage    
fill(0, 200, 100)    
ellipse(mouse_x, joueur_y, 60, 60)

    #Les yeux<br x-id="4" />
      fill(0, 100, 200)<br x-id="4" />
      ellipse(mouse_x - 10, joueur_y - 10, 20, 20)<br x-id="4" />
      ellipse(mouse_x + 10, joueur_y - 10, 20, 20)<br x-id="4" />
      fill(0)<br x-id="4" />
      ellipse(mouse_x - 10, joueur_y - 10, 10, 10)<br x-id="5" />
      ellipse(mouse_x + 10, joueur_y - 10, 10, 10)<br x-id="5" />
      fill(255)<br x-id="4" />
      ellipse(mouse_x - 12, joueur_y - 12, 5, 5)<br x-id="4" />
      ellipse(souris_x + 12, joueur_y - 12, 5, 5)
    

--- /code ---

--- /collapse ---

--- /task ---

--- task ---

**Test :** Exécute ton code et déplace la souris pour contrôler le joueur.

Est-ce que ça bouge comme prévu ?

--- /task ---

**Débogage :** Il est possible que tu trouves des bogues dans ton projet que tu dois corriger. Voici quelques bogues assez courants .

--- task ---

--- collapse ---


---



title: Je ne peux pas voir le joueur
---

Essaye de passer en plein écran. Vérifie également les coordonnées `x` et `y` que tu as utilisées pour dessiner le joueur - assure-toi qu'elles se trouvent à l'intérieur du canevas que tu as créé avec `size()`.

--- /collapse ---

--- collapse ---


---



title: Une image ne se charge pas
---

Vérifie d'abord que l'image se trouve dans la `bibliothèque d'images`. Ensuite, vérifie très attentivement le nom du fichier - rappelle-toi que les majuscules sont différentes des minuscules et que la ponctuation est importante.

--- /collapse ---

--- collapse ---


---



title: Une image n'a pas la bonne taille
---

Vérifie les entrées qui contrôlent la largeur et la hauteur de l'image :



```python
image(nom du fichier image, coordonnée x, coordonnée y, largeur, hauteur)
```


--- /collapse ---

--- collapse ---


---



title: Un emoji n'a pas la bonne taille
---

Si ton emoji est trop grand ou trop petit, change l'entrée en `text_size()`.

--- /collapse ---

--- /task ---

--- save ---
