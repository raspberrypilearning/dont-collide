## Créer un obstacle

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Crée les obstacles que tu devras éviter pour continuer à jouer.
</div>
<div>

![Exemple de projet de ski avec obstacles arborés](images/obstacles.png){:width="300px"}

</div>
</div>

--- task ---

Définis une fonction `dessine_obstacles` pour dessiner un emoji cactus 🌵.

--- code ---
---
language: python line_numbers: true line_number_start: 12
line_highlights: 13-14
---

# Draw obstacles function goes here
def draw_obstacles(): text('🌵', 200, 200)

--- /code ---

Appelle la fonction `dessine_obstacles` pour que le cactus soit dessiné sur l'écran.

--- code ---
---
language: python line_numbers: true line_number_start: 22
line_highlights: 27
---

def draw():   
# Put code to run every frame here global safe safe = Color(200, 100, 0) background(safe) draw_obstacles() draw_player()

--- /code ---

--- /task ---


--- task ---

**Test :** exécute ton code et tu devrais voir un cactus ainsi que ton joueur.

--- /task ---

--- task ---

Ajoute deux variables pour suivre les coordonnées x et y de l'obstacle. Mets à jour le code pour dessiner l'emoji afin qu'il utilise ces variables.

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 14-16
---

def draw_obstacles(): obstacle_x = 200 obstacle_y = 200 text('🌵', obstacle_x, obstacle_y)

--- /code ---

--- /task ---

--- task ---

Maintenant, ajoute `frame_count` à la position y (verticale) de l'obstacle.

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 15
---

def draw_obstacles(): obstacle_x = 200 obstacle_y = 200 + frame_count text('🌵', obstacle_x, obstacle_y)

--- /code ---

--- /task ---

--- task ---

**Test :** exécute ton code et l'emoji cactus devrait se déplacer vers le bas de l'écran jusqu'à ce qu'il atteigne le bas.

--- /task ---
