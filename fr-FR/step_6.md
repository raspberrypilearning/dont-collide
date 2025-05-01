## Collisions

Rappelle-toi que dans la première étape, tu as créé une couleur « sur ».

--- task ---

Crée une variable pour stocker la couleur que l'emoji du joueur touche actuellement.

--- code ---
---
language: python
line_numbers: true
line_number_start: 8
line_highlights: 9
---
 
def dessine_joueur():
    joueur_sur = get(mouse_x, 320).hex
    text('🤠', mouse_x, 320)
  
--- /code ---

--- /task ---

--- task ---

Si le joueur touche la couleur « sur », dessine l'emoji du joueur. Si ce n’est pas le cas, dessine un emoji d’explosion pour montrer qu’ils se sont écrasés.

--- code ---
---
language: python
line_numbers: true
line_number_start: 8
line_highlights: 10, 12-13
---
 
def dessine_joueur():
    joueur_sur = get(mouse_x, 320).hex
    if joueur_sur == sur.hex: 
        text('🤠', mouse_x, 320)
    else:  
        text('💥', mouse_x, 320)
  
--- /code ---

--- /task ---


--- task ---

**Test :** exécute ton code et déplace le joueur. Tu devrais voir l'émoji d'explosion si ton joueur touche un obstacle.

Assure-toi que dans `draw()`, la ligne de code pour `dessine_obstacles()` est avant `dessine_joueur()`. Si tu vérifies les collisions avant de dessiner les obstacles dans une image, il n'y aura pas d'obstacles avec lesquels entrer en collision !

--- /task ---