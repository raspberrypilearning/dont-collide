## Définir la scène

--- task ---

Ouvre le [projet de démarrage](https://editor.raspberrypi.org/en/projects/dont-collide-starter){:target="_blank"}.

--- /task ---

--- task ---

Crée une variable appelée `sur` pour stocker la couleur d'arrière-plan.

Dans le jeu, le joueur est en sécurité s'il touche la couleur d'arrière-plan.

--- code ---
---
language: python line_numbers: true line_number_start: 20
line_highlights: 22-24
---

def draw():   
# Put code to run every frame here global safe safe = Color(200, 100, 0) background(safe)

--- /code ---

--- /task ---

--- task ---

**Test :** exécute ton code et tu devrais voir un carré coloré.

La couleur est composée de trois nombres : la quantité de rouge, de vert et de bleu. Essaie de remplacer les nombres par n'importe quel nombre entier compris entre 0 et 255 pour obtenir une couleur différente.

--- /task ---

--- task ---

Définis une fonction `dessine_joueur` . À l'intérieur, ajoute un emoji et une paire de coordonnées x, y pour représenter le joueur.

--- code ---
---
language: python line_numbers: true line_number_start: 7
line_highlights: 8-9
---
# Draw player function goes here
def draw_player(): text('🤠', 200, 320)

--- /code ---

--- /task ---

--- task ---

Appelle la fonction `dessine_joueur` pour que le joueur soit dessiné à l'écran.

--- code ---
---
language: python line_numbers: true line_number_start: 21
line_highlights: 26
---

def draw():  
# Put code to run every frame here global safe safe = Color(200, 100, 0) background(safe) draw_player()

--- /code ---

--- /task ---

--- task ---

**Test :** exécute ton code et tu devrais voir l’emoji apparaître près du bas de l’écran.

Tu peux coller un emoji différent si tu le souhaites.

--- /task ---

[[[choose-an-emoji]]]

--- task ---

Pour que le joueur suive la souris lorsqu'elle se déplace d'un côté à l'autre, modifie la position x du joueur sur `mouse_x`.

--- code ---
---
language: python line_numbers: true line_number_start: 7
line_highlights: 9
---
# Draw player function goes here
def draw_player(): text('🤠', mouse_x, 320)

--- /code ---

--- /task ---

--- task ---

Exécute ton code et vérifie que le joueur se déplace à gauche et à droite lorsque tu déplaces la souris.


--- /task ---