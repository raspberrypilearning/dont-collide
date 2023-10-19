## Maak obstakels

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Maak de obstakels die je moet vermijden om het spel te blijven spelen.
</div>
<div>

![Voorbeeld skiproject met boomobstakels](images/obstacles.png){:width="300px"}

</div>
</div>

### Begin met één obstakel

Je kunt obstakels op dezelfde manier maken als je speler. Hoe passen de obstakels bij je thema?

Je gaat een `for` lus gebruiken om veel kopieën te maken, dus je hoeft maar één obstakel te maken of te kiezen.

--- task ---

Definieer een `teken_obstakels()` functie:

--- code ---
---
filename: main.py - teken_obstakels()
line_highlights: 4
---

def teken_obstakels(): obstakel_x = width/2 obstakel_y = height/2 text('🌵', obstakel_x, obstakel_y) #Vervang je obstakel

--- /code ---

Voeg code toe aan `draw()` om `teken_obstakels()` voor elk frame aan te roepen.

--- code ---
---
filename: main.py - draw()
line_highlights: 5
---

def draw(): veilig = color(200, 100, 0) #Voeg de kleur van je thema toe background(veilig)  
teken_obstakels() #Voordat je de speler tekent teken_speler()

--- /code ---

--- /task ---

--- task ---

**Kies:** Hoe ziet jouw obstakel eruit? Jouw obstakel kan zijn:
+ Een afbeelding in het startproject
+ Een emoji 🌵 of tekst
+ Getekend met een reeks vormen

--- collapse ---
---
title: Gebruik een startafbeelding
---

Afbeeldingen die in het startersproject zijn opgenomen, worden weergegeven in de lijst `Image library` (Afbeeldingenbibliotheek).

![The Image gallery displaying the included images.](images/starter-images.png)

Noteer de naam van de afbeelding die je wilt gebruiken.

Laad de afbeelding in de `setup()` functie.

--- code ---
---
language: python filename: main.py - setup() line_numbers: true line_number_start: 9
line_highlights: 12
---

def setup(): size(400, 400) speler = load_image('skiing.png') #Laad je afbeelding obstakel = load_image('rocket.png') #Laad je afbeelding

--- /code ---

Find the line `# Keep this to run your code`. Roep `image()` aan en stel deze in als global in de `teken_obstakels()` functie.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def teken_obstakels(): obstakel_x = width/2 obstakel_y = height/2

    image(obstakel, obstakel_x, obstakel_y, 30, 30) #Pas de afmeting aan om bij jouw thema te passen

--- /code ---

--- /collapse ---

--- collapse ---
---
title: Emoji-tekens gebruiken
---

Je kunt emoji-tekens gebruiken in de p5-functie `text()` om een emoji als speler te gebruiken.

Hier is een voorbeeld:

--- code ---
---
language: python
filename: main.py - setup()
---

def setup(): size(400, 400) text_size(40) #Bepaalt de grootte van de emoji text_align(CENTER, TOP) #Positie rond het midden

--- /code ---

Find the line `# Keep this to run your code`. Before that line, define a new `draw_obstacles()` function.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def teken_obstakels(): obstakel_x = width/2 obstakel_y = height/2 text('🌵', obstakel_x, obstakel_y)

--- /code ---

--- /collapse ---

[[[processing-python-text]]]

[[[generic-theory-simple-colours]]]

[[[processing-python-ellipse]]]

[[[processing-python-rect]]]

[[[processing-python-triangle]]]

[[[processing-tint]]]

[[[processing-stroke]]]

**Tip:** Je kunt meerdere eenvoudige vormen in dezelfde functie gebruiken om een complexere speler te maken.

--- collapse ---
---
titel: Teken een object door meerdere vormen te gebruiken
---

![A tree drawn with green triangles for the body and a brown rectangle for the trunk](images/tree_obstacle.png)

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def teken_obstakels(): ob_x = width/2 ob_y = height/2 #Teken een dennenboom no_stroke() fill(0,255,0) #Groen voor naalden triangle(ob_x + 20, ob_y + 20, ob_x + 10, ob_y + 40, ob_x + 30, ob_y + 40) triangle(ob_x + 20, ob_y + 30, ob_x + 5, ob_y + 55, ob_x + 35, ob_y + 55) triangle(ob_x + 20, ob_y + 40, ob_x + 0, ob_y + 70, ob_x + 40, ob_y + 70) fill(150,100,100) #bruin voor stam rect(ob_x + 15, ob_y + 70, 10, 10)

--- /code ---

--- /collapse ---

--- /task ---

### Breng je obstakel in beweging

--- task ---

Voeg nu code toe om de `y` positie van het obstakel elk frame te vergroten, en laat het opnieuw bovenaan verschijnen wanneer het de onderkant bereikt om het effect van een ander obstakel te creëren.

De p5-variabele `frame_count` begint de frames te tellen wanneer je op uitvoeren klikt.

`obstakel_y %= height` stelt de `y` positie in op de resterende hoogte wanneer gedeeld door `height`. Met een `height` van '400' verandert dit `401` in `1`, dus wanneer de obstakels onderaan het scherm verdwijnen, verschijnt het bovenaan opnieuw.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def teken_obstakels(): obstakel_x = width/2 obstakel_y = height/2 + frame_count #Verhoogt elk frame obstakel_y %= height #Omkeren text('🌵', obstakel_x, obstakel_y) #Vervang je obstakel

--- /code ---

--- /task ---

### Veel obstakels

Je zou op verschillende startlocaties veel kopieën van je obstakels kunnen maken, maar dat is best veel werk. Laten we een snellere route gebruiken.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;"> 
<span style="color: #0faeb0">**Procedurele generatie**</span> wordt gebruikt om game 
werelden, obstakels en filmscènes te maken op een willekeurige manier, maar wel met bepaalde regels. Een <span style="color: #0faeb0">seed</span> (zaadje) betekent dat je elke keer dat je dezelfde seed gebruikt dezelfde resultaten kunt genereren.</p>

--- task ---

Deze code gebruikt een `for` lus met `randint()` om obstakelposities voor je te kiezen. Als je eerst de willekeurige functie `seed()` aanroept, betekent dit dat je altijd dezelfde willekeurige getallen krijgt. Dit betekent dat de obstakels niet elk frame rond zullen springen en dat je de seed kunt veranderen totdat je er een krijgt die de obstakels goed positioneert.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def draw_obstacles(): seed(12345678)  # Any number is fine

    for i in range(6):<br x-id="2" />
        obstakel_x = randint(0, height) 
        obstakel_y = randint(0, height) + frame_count 
        obstakel_y %= height 
        text('🌵', obstakel_x, obstakel_y) #Plaats het nieuwe obstakel

--- /code ---

Bruikbare informatie:

[[[using-seed-in-python]]]

[[[generic-python-for-loop-repeat]]]

--- /task ---

--- collapse ---
---
title: Epilepsie waarschuwing
---

Het testen van je programma kan epileptische aanvallen veroorzaken bij mensen met lichtgevoelige epilepsie. Als je lichtgevoelige epilepsie hebt of als je denkt vatbaar te zijn voor een aanval, voer het programma dan niet uit. In plaats daarvan kun je:
- Ervoor zorgen dat je de `seed()` regel code hebt toegevoegd zodat je obstakels niet rondspringen
- Iemand anders vragen om het voor je uit te voeren
- Ga verder en voltooi het project en vraag aan het einde iemand om het project voor jou uit te voeren, zodat je fouten kunt opsporen
- Slow the game down by using `frame_rate = 10` in your call to `run()` like this:

```python
run(frame_rate = 10)
```
You can alter the speed of the game by changing `10` to a higher or lower value.

--- /collapse ---

--- task ---

**Test:** Voer je programma uit en je zou meerdere objecten op het scherm moeten zien, die bovenaan opnieuw verschijnen zodra ze de bodem bereiken.

Verander je code totdat je tevreden bent met de obstakels die je hebt. Je kunt:

+ De seed veranderen om obstakels op verschillende startposities te krijgen
+ Het aantal keren dat de lus herhaald moet worden aanpassen om een ander aantal obstakels te krijgen aanpassen
+ De grootte van de obstakels aanpassen

**Tip:** Zorg ervoor dat het mogelijk is om je obstakels te ontwijken, maar dat er geen gemakkelijke weg door je spel is.

--- /task ---

--- task ---

**Debug:** Mogelijk vindt je enkele fouten in jouw project die je moet oplossen. Hier zijn enkele veelvoorkomende fouten.

--- collapse ---
---
title: Er wordt maar één obstakel getekend
---

Controleer de functie die meerdere obstakels tekent:
 + Zorg ervoor dat het een `for` lus gebruikt om de functie voor het tekenen van obstakels meer dan eens aan te roepen
 + Zorg ervoor dat het `randint()` gebruikt om de (x, y)-coördinaten aan te passen die doorgegeven worden aan de functie voor het tekenen van obstakels
 + Controleer of je `obstakel_x` en `obstakel_y` hebt gebruikt als coördinaten voor je obstakel

Bijvoorbeeld:

--- code ---
---
language: python
filename: main.py — draw_obstacles()
---

seed(12345678)

    for i in range(6):<br x-id="2" />
        obstakel_x = randint(0, height) 
        obstakel_y = randint(0, height) + frame_count 
        obstakel_y %= height 
        text('🌵', obstakel_x, obstakel_y) #Plaats het nieuwe obstakel

--- /code ---

--- /collapse ---

--- collapse ---
---
title: De obstakels veranderen van positie, elke keer dat een frame wordt getekend
---

Zorg ervoor dat je `seed()` hebt gebruikt in de functie die meerdere obstakels tekent.

--- /collapse ---

--- /task ---

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;"> 
Programmeurs gebruiken veel handige trucs, zoals het gebruik van de `%`-operator om objecten rond het scherm te laten lopen en de `seed()`-functie om dezelfde willekeurige getallen te genereren. Hoe meer je codeert, hoe meer handige trucs je leert.</p>

--- save ---
