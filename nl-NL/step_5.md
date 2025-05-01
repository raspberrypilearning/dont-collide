## Veel obstakels

Nu ga je code toevoegen om heel veel obstakels te maken die je moet vermijden.

--- task ---

Voeg een lus toe en laat de code inspringen om een obstakel te tekenen. De lus voert deze code meerdere keren uit.

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 15-19
---

def draw_obstacles(): seed(1234) for i in range(8): obstacle_x = randint(0, screen_size) obstacle_y = randint(0, screen_size) + frame_count obstacle_y = obstacle_y % screen_size text('🌵', obstacle_x, obstacle_y)

--- /code ---

Zorg ervoor dat de code voor de seed vóór de lus staat, anders worden al je obstakels bovenop elkaar gegenereerd!

--- /task ---

--- task ---

Wijzig het getal binnen `range()` om te bepalen hoeveel obstakels er worden gecreëerd.

--- /task ---

--- task ---

**Test:** Voer je code uit, je zou verschillende obstakels moeten zien.

--- /task ---