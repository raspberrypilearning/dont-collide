## Willekeurig obstakels


Momenteel verdwijnt het obstakel van de onderkant van het scherm, omdat de `obstakel_y` positie groter wordt dan de schermgrootte.

--- task ---

Gebruik de modulo (%) operator om de y-positie te delen door de schermgrootte, je krijgt dan de **restwaarde**. Hierdoor verschijnt het obstakel opnieuw bovenaan!

--- code ---
---
language: python
line_numbers: true
line_number_start: 13
line_highlights: 16
---
 
def teken_obstakels():
    obstakel_x = 200
    obstakel_y = 200 + frame_count
    obstakel_y = obstakel_y % scherm_grootte
    text('🌵', obstakel_x, obstakel_y) 
  
--- /code ---

--- /task ---

--- task ---

**Test:** Voer je code uit, je zou moeten zien dat het obstakel de onderkant van het scherm bereikt en vervolgens opnieuw begint vanaf de bovenkant.

--- /task ---

--- task ---

Voeg een regel code toe voor een willekeurige **seed**. Met een seed kun je in elk frame dezelfde willekeurige getallen genereren.

--- code ---
---
language: python
line_numbers: true
line_number_start: 12
line_highlights: 14
---
 
# Draw obstacles function goes here
def teken_obstakels():
    seed(1234)
    obstakel_x = 200
    obstakel_y = 200 + frame_count

--- /code ---

--- /task ---

--- task ---

Werk de code bij zodat de x- en y-coördinaten voor het obstakel willekeurig worden gegenereerd.

--- code ---
---
language: python
line_numbers: true
line_number_start: 12
line_highlights: 15-16
---
 
# Draw obstacles function goes here
def teken_obstakels():
    seed(1234)
    obstakel_x = randint(0, scherm_grootte)
    obstakel_y = randint(0, scherm_grootte) + frame_count

--- /code ---

--- /task ---

--- task ---

**Test:** Voer je code uit en je zou de cactus op een willekeurige positie moeten zien verschijnen. Verander de waarde `1234` van de seed naar een ander getal, dan verschijnt de cactus ergens anders.

--- /task ---
