## Botsingen

Je weet misschien nog dat je in de eerste stap een 'veilige' kleur hebt gemaakt.

--- task ---

Maak een variabele om de kleur op te slaan die de speler-emoji op dat moment raakt.

--- code ---
---
language: python line_numbers: true line_number_start: 8
line_highlights: 9
---

def draw_player(): player_on = get(mouse_x, 320).hex text('🤠', mouse_x, 320)

--- /code ---

--- /task ---

--- task ---

Als de speler de veilige kleur raakt, teken dan de emoji van de speler. Als dat niet zo is, teken dan een explosie-emoji om aan te geven dat ze zijn gebotst.

--- code ---
---
language: python line_numbers: true line_number_start: 8
line_highlights: 10, 12-13
---

def draw_player(): player_on = get(mouse_x, 320).hex if player_on == safe.hex: text('🤠', mouse_x, 320) else:  
text('💥', mouse_x, 320)

--- /code ---

--- /task ---


--- task ---

**Test:** Voer je code uit en verplaats de speler. Je zou de explosie-emoji moeten zien als je speler een obstakel raakt.

Zorg ervoor dat in `draw()` de regel code voor `teken_obstakels()` vóór `teken_speler()` staat. Als je controleert op botsingen voordat je de obstakels in een frame tekent, zijn er geen obstakels waar je tegenaan kunt botsen!

--- /task ---