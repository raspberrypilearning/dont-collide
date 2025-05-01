## Het opzetten van de scene

--- task ---

Open het [startproject](https://editor.raspberrypi.org/en/projects/dont-collide-starter){:target="_blank"}.

--- /task ---

--- task ---

Maak een variabele met de naam `veilig` om de achtergrondkleur op te slaan.

In het spel is de speler veilig als hij de achtergrondkleur raakt.

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

**Test:** Voer je code uit, je zou een gekleurd vierkant moeten zien.

De kleur bestaat uit drie getallen: de hoeveelheid rood, groen en blauw. Probeer de getallen te vervangen door een geheel getal tussen 0 en 255 om een andere kleur te krijgen.

--- /task ---

--- task ---

Definieer een `teken_speler` functie. Voeg binnenin een emoji en een paar x- en y-coördinaten toe om de speler voor te stellen.

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

Roep de functie `teken_speler` aan, zodat de speler op het scherm wordt getekend.

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

**Test:** Voer je code uit, je zou de emoji onderaan het scherm moeten zien verschijnen.

Je kunt desgewenst een andere emoji plakken.

--- /task ---

[[[choose-an-emoji]]]

--- task ---

Om de speler de muis te laten volgen terwijl deze van links naar rechts beweegt, verander je de x-positie van de speler in `mouse_x`.

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

Voer je code uit en controleer of de speler naar links en rechts beweegt wanneer je de muis beweegt.


--- /task ---