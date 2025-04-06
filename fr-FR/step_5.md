## Beaucoup d'obstacles

Tu vas maintenant ajouter du code pour créer de nombreux obstacles à éviter.

--- task ---

Ajoute une boucle et indente le code pour dessiner un obstacle. La boucle exécutera ce code plusieurs fois.

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 15-19
---

def draw_obstacles(): seed(1234) for i in range(8): obstacle_x = randint(0, screen_size) obstacle_y = randint(0, screen_size) + frame_count obstacle_y = obstacle_y % screen_size text('🌵', obstacle_x, obstacle_y)

--- /code ---

Assure-toi que le code du seed est avant la boucle, sinon tous tes obstacles seront générés les uns sur les autres !

--- /task ---

--- task ---

Modifie le nombre dans `range()` pour contrôler le nombre d'obstacles créés.

--- /task ---

--- task ---

**Test :** exécute ton code et tu devrais voir plusieurs obstacles.

--- /task ---