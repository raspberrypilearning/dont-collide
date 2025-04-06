## Obstacles aléatoires


Actuellement, l'obstacle disparaît du bas de l'écran, car sa position `obstacle_y` devient plus grande que la taille de l'écran.

--- task ---

Utilise l'opérateur modulo (%) pour diviser la position y par la taille de l'écran et te donner le **reste**. Cela fait réapparaître l'obstacle en haut !

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 16
---

def draw_obstacles(): obstacle_x = 200 obstacle_y = 200 + frame_count obstacle_y = obstacle_y % screen_size text('🌵', obstacle_x, obstacle_y)

--- /code ---

--- /task ---

--- task ---

**Test :** exécute ton code et tu devrais voir l'obstacle atteindre le bas de l'écran, puis redémarrer depuis le haut.

--- /task ---

--- task ---

Ajoute une ligne de code pour un **seed** aléatoire. Un seed te permet de générer les mêmes nombres aléatoires dans chaque image.

--- code ---
---
language: python line_numbers: true line_number_start: 12
line_highlights: 14
---

# Draw obstacles function goes here
def draw_obstacles(): seed(1234) obstacle_x = 200 obstacle_y = 200 + frame_count

--- /code ---

--- /task ---

--- task ---

Mets à jour le code afin que les coordonnées x, y de l’obstacle soient générées de manière aléatoire.

--- code ---
---
language: python line_numbers: true line_number_start: 12
line_highlights: 15-16
---

# Draw obstacles function goes here
def draw_obstacles(): seed(1234) obstacle_x = randint(0, screen_size) obstacle_y = randint(0, screen_size) + frame_count

--- /code ---

--- /task ---

--- task ---

**Test :** exécute ton code et tu devrais voir le cactus apparaître à une position aléatoire. Modifie la valeur `1234` à l'intérieur du seed par un autre nombre et elle apparaîtra ailleurs.

--- /task ---
