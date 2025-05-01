## Veel obstakels

Nu ga je code toevoegen om heel veel obstakels te maken die je moet vermijden.

--- task ---

Voeg een lus toe en laat de code inspringen om een obstakel te tekenen. De lus voert deze code meerdere keren uit.

--- code ---
---
language: python
line_numbers: true
line_number_start: 13
line_highlights: 15-19
---
 
def teken_obstakels():
    seed(1234)
    for i in range(8):
        obstakel_x = randint(0, scherm_grootte)
        obstakel_y = randint(0, scherm_grootte) + frame_count
        obstakel_y = obstakel_y % scherm_grootte
        text('🌵', obstakel_x, obstakel_y)
  
--- /code ---

Zorg ervoor dat de code voor de seed vóór de lus staat, anders worden al je obstakels bovenop elkaar gegenereerd!

--- /task ---

--- task ---

Wijzig het getal binnen `range()` om te bepalen hoeveel obstakels er worden gecreëerd.

--- /task ---

--- task ---

**Test:** Voer je code uit, je zou verschillende obstakels moeten zien.

--- /task ---