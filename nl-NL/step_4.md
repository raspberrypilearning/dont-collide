## Willekeurig obstakels


Momenteel verdwijnt het obstakel van de onderkant van het scherm, omdat de `obstakel_y` positie groter wordt dan de schermgrootte.

--- task ---

Gebruik de modulo (%) operator om de y-positie te delen door de schermgrootte, je krijgt dan de **restwaarde**. Hierdoor verschijnt het obstakel opnieuw bovenaan!

--- code ---
---
language: python line_numbers: true line_number_start: 13
line_highlights: 16
---

def draw_obstacles(): obstacle_x = 200 obstacle_y = 200 + frame_count obstacle_y = obstacle_y % screen_size text('🌵', obstacle_x, obstacle_y)

--- /code ---

--- /task ---

--- task ---

**Test:** Voer je code uit, je zou moeten zien dat het obstakel de onderkant van het scherm bereikt en vervolgens opnieuw begint vanaf de bovenkant.

--- /task ---

--- task ---

Voeg een regel code toe voor een willekeurige **seed**. Met een seed kun je in elk frame dezelfde willekeurige getallen genereren.

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

Werk de code bij zodat de x- en y-coördinaten voor het obstakel willekeurig worden gegenereerd.

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

**Test:** Voer je code uit en je zou de cactus op een willekeurige positie moeten zien verschijnen. Verander de waarde `1234` van de seed naar een ander getal, dan verschijnt de cactus ergens anders.

--- /task ---
