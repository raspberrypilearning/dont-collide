## Maak een obstakel

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Maak de obstakels die je moet vermijden om het spel te blijven spelen.
</div>
<div>

![Voorbeeld skiproject met boomobstakels](images/obstacles.png){:width="300px"}

</div>
</div>

--- task ---

Definieer een `teken_obstakels` functie om een cactus-emoji te tekenen 🌵.

--- code ---
---
language: python
line_numbers: true
line_number_start: 12
line_highlights: 13-14
---
 
# De teken_obstakels functie komt hier
def teken_obstakels():
    text('🌵', 200, 200)
  
--- /code ---

Roep de functie `teken_obstakels` aan, zodat de cactus op het scherm wordt getekend.

--- code ---
---
language: python
line_numbers: true
line_number_start: 22
line_highlights: 27
---

def draw():   
    # Zet hier code om bij elk frame uit te voeren
    global veilig
    veilig = Color(200, 100, 0) 
    background(veilig)
    teken_obstakels()
    teken_speler()
  
--- /code ---

--- /task ---


--- task ---

**Test:** Voer je code uit en je zou een cactus en je speler moeten zien.

--- /task ---

--- task --- 

Voeg twee variabelen toe om de x- en y-coördinaten van het obstakel bij te houden. Werk de code bij om de emoji te tekenen, zodat het deze variabelen gebruikt.

--- code ---
---
language: python
line_numbers: true
line_number_start: 13
line_highlights: 14-16
---

def teken_obstakels():
    obstakel_x = 200
    obstakel_y = 200 
    text('🌵', obstakel_x, obstakel_y) 

--- /code ---

--- /task ---

--- task ---

Voeg nu `frame_count` toe aan de y-positie (verticaal) van het obstakel.

--- code ---
---
language: python
line_numbers: true
line_number_start: 13
line_highlights: 15
---

def teken_obstakels():
    obstakel_x = 200
    obstakel_y = 200 + frame_count
    text('🌵', obstakel_x, obstakel_y) 

--- /code ---

--- /task ---

--- task --- 

**Test:** Voer je code uit en de cactus-emoji zou over het scherm moeten bewegen tot hij de onderkant bereikt.

--- /task ---
