## Вибір теми

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Встанови тему своєї гри та створи персонажа, який буде слідувати за курсором миші.

</div>
<div>

![Зображення черепахи розміром 100х100 на синьому фоні з розміром екрана 400х400.](images/theme-turtle.png){:width="300px"}

</div>
</div>

Яка тематика твоєї гри? Ти можеш вибрати все, що завгодно. Ось деякі ідеї:
- Спорт або хобі
- Фільм, шоу або гра
- Наука або природа
- Або що-небудь інше!

--- task ---

Відкрий [стартовий проєкт](https://trinket.io/python/cda05e5911){:target="_blank"}. Trinket відкриється в окремій вкладці браузера.

--- /task ---

--- task ---

**Обирай:** Встанови розмір свого полотна.

--- code ---
---
language: python
filename: main.py - setup()
---

def setup():    
size(400, 400)

--- /code ---

--- /task ---

--- task ---

Створи змінну з назвою `safe`, щоб зберегти колір фону, який був обраний тобою для своєї гри.

Це колір, на якому гравець може безпечно перебувати, і ти будеш використовувати цю змінну пізніше.

--- code ---
---
language: python
filename: main.py - draw()
---

def draw():    
safe = color(200, 100, 0) #Add the colour of your theme   
background(safe)

--- /code ---

[[[generic-theory-simple-colours]]]

--- /task ---

--- task ---

**Тест:** Запусти свій код, щоб побачити колір фону. Змінюй його до тих пір, поки колір та розмір екрана тебе влаштує.

--- /task ---

Тепер вибери персонажа, який буде вести гру та уникати перешкод. Це буде предмет, людина, тварина чи щось інше?

Гравець з'явиться на фіксованій позиції `y` та на тій самій позиції `x`, що і курсор миші, яка зберігається у змінній `p5` `mouse_x`.

--- task ---

Хороша ідея - оформити код для малювання персонажа у функцію.

Визнач функцію `draw_player()` та створи позицію `player_y`, для фіксації позиції гравця `y`:

--- code ---
---
language: python
filename: main.py - draw_player()
---

def draw_player():    
player_y = int(height * 0.8) #Positioned towards the screen bottom

--- /code ---

Додай до `draw()` код для виклику `draw_player()` на кожному кадрі.

--- code ---
---
language: python
filename: main.py - draw()
---

def draw():    
safe = color(200, 100, 0) #Your chosen colour    
background(safe)    
draw_player()

--- /code ---

--- /task ---

Далі треба додати код у функцію `draw_player()`, щоб намалювати твою фігуру. Також, може знадобитися додати код `setup()`.

--- task ---

**Обирай:** Як виглядатиме твій персонаж? Це може бути:
+ Зображення, які наведені у стартовому проєкті
+ Емодзі 🎈 або текст
+ Малюнок, виконаний за допомогою декількох фігур

--- collapse ---
---
title: Використання стартового зображення
---

Натисни на значок **manage images**.

![Піктограма у верхньому правому куті області коду.](images/manage-images.png)

Зображення, включені в стартовий проєкт, будуть відображені в списку `Image library`.

![Список зображень в Image library.](images/starter-images.png)

Запиши назву зображення, яке ти хочеш використати.

Завантажуємо зображення у функцію `setup()`

--- code ---
---
language: python
filename: main.py - setup()
---

def setup():   
size(400, 400)    
player = load_image('skiing.png') #Load your image

--- /code ---

Зроби виклик `image()` та встанови її, як глобальну, у функції `draw_player()`.

--- code ---
---
language: python
filename: main.py - draw_player()
---

def draw_player():    
player_y = int(height * 0.8) #Positioned towards the screen bottom

  global player

  image(player, mouse_x, player_y, 30, 30)

--- /code ---

--- /collapse ---

--- collapse ---
---
title: Використання символів емодзі
---

Ти можеш використовувати символи емодзі у функції p5 `text()`, щоб зобразити свого персонажа у вигляді емодзі.

Ось приклад:

--- code ---
---
language: python
filename: main.py - setup()
---

def setup():    
size(400, 400)     
text_size(40) #Controls the size of the emoji     
text_align(CENTER, TOP) #Position around the centre

--- /code ---

--- code ---
---
language: python
filename: main.py - draw_player()
---

def draw_player():     
player_y = int(height * 0.8)    
text('🎈', mouse_x, player_y)

--- /code ---

--- /collapse ---

[[[processing-python-text]]]

[[[generic-theory-simple-colours]]]

[[[processing-python-ellipse]]]

[[[processing-python-rect]]]

[[[processing-python-triangle]]]

[[[processing-tint]]]

[[[processing-stroke]]]

**Tip:** Ти можеш використати декілька простих фігур в одній функції, щоб створити більш різноманітного персонажа.

--- collapse ---
---
title: Малювання персонажа за допомогою декількох фігур
---

![опис](images/face_player.png)

--- code ---
---
language: python
filename: main.py - draw_player()
---

def draw_player():    
player_y = int(height * 0.8)    
noStroke()    
#Face    
fill(0, 200, 100)    
ellipse(mouse_x, player_y, 60, 60)

  #Eyes    
fill(0, 100, 200)    
ellipse(mouse_x - 10, player_y - 10, 20, 20)    
ellipse(mouse_x + 10, player_y - 10, 20, 20)    
fill(0)    
ellipse(mouse_x - 10, player_y - 10, 10, 10)     
ellipse(mouse_x + 10, player_y - 10, 10, 10)     
fill(255)    
ellipse(mouse_x - 12, player_y - 12, 5, 5)    
ellipse(mouse_x + 12, player_y - 12, 5, 5)

--- /code ---

--- /collapse ---

--- /task ---

--- task ---

**Тест:** Запусти свій код та переміщуй курсор миші, щоб керувати гравцем.

Чи рухається він так, як ти очікуєш?

--- /task ---

**Налагодження:** Можливо, у твоєму проєкті знайдуться помилки, які потрібно буде виправити. Ось деякі поширені помилки.

--- task ---

--- collapse ---
---
title: Я не бачу персонажа
---

Спробуй перейти до повноекранного режиму. Також, перевір координати `x` та `y`, які були використані для малювання персонажа. Переконайся, що вони знаходяться всередині полотна, яке було створено за допомогою `size()`.

--- /collapse ---

--- collapse ---
---
title: Зображення не завантажується
---

Спочатку переконайся, що зображення знаходиться в `Image library`. Потім дуже уважно перевір назву файлу. Пам'ятай, що великі літери відрізняються від малих. Також важлива пунктуація.

--- /collapse ---

--- collapse ---
---
title: Зображення має неправильний розмір
---

Слід перевірити код, який визначає ширину та висоту зображення:

```python
image(image_file, x_coord, y_coord, width, height)
```

--- /collapse ---

--- collapse ---
---
title: Емодзі має неправильний розмір
---

Якщо емодзі занадто великі або занадто маленькі, зміни введені значення у `text_size()`.

--- /collapse ---

--- /task ---

--- save ---
