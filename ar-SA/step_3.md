## اصنع عقبات

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
قم بإنشاء العقبات التي سيتعين عليك تجنبها لمواصلة لعب اللعبة.
</div>
<div>

! [مثال لمشروع تزلج بعوائق شجرية] (images / brothers.png) {: width = "300px"}

</div>
</div>

### ابدأ بعائق واحد

يمكنك صنع العوائق بنفس الطرق التي صنعت بها لاعبك. كيف تتناسب العقبات مع موضوعك؟

ستستخدم حلقة `مقابل` لعمل الكثير من النسخ لذا ما عليك سوى عمل أو اختيار عقبة واحدة.

--- task ---

حدد دالة `draw_obstacles ()`:

--- code ---
---
def draw_obstacles():
line_highlights: 4
---

def draw_obstacles(): ob_x = width/2 ob_y = height/2 text('🌵', ob_x, ob_y) #استبدل بعقبتك

--- /code ---

أضف الكود إلى `draw ()` لاستدعاء `draw_obstacles ()` لكل إطار.

--- code ---
---
filename: main.py - draw()
line_highlights: 5
---

def draw(): safe = color(200, 100, 0) #أضف لون الخلفية الخاصة بك background(safe)  
draw_obstacles() #قبل رسم اللاعب draw_player()

--- /code ---

--- /task ---

--- task ---

**اختر:** كيف تبدو العقبة التي تواجهك؟ قد تكون عقبتك:
+ صورة مقدمة في مشروع البداية
+ رمز تعبيري 🌵 أو نص
+ مرسومة باستخدام سلسلة من الأشكال

--- collapse ---
---
العنوان: استخدم صورة أولية
---

سيتم عرض الصور المضمنة في مشروع البداية في قائمة `Image library`.

![The Image gallery displaying the included images.](images/starter-images.png)

قم بتدوين اسم الصورة التي تريد استخدامها.

قم بتحميل الصورة في دالة `()setup`.

--- code ---
---
language: python filename: main.py - setup() line_numbers: true line_number_start: 9
line_highlights: 12
---

def setup(): size(400, 400) player = load_image('skiing.png') #تحميل صورتك obstacle = load_image('rocket.png') #تحميل صورتك

--- /code ---

Find the line `# Keep this to run your code`. Before that line, define a new `draw_obstacles()` function, call `obstacle` as a global variable and use it in the call to `image()`.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def draw_obstacles(): ob_x = width/2 ob_y = height/2

    image(obstacle, ob_x, ob_y, 30, 30) #Resize لتناسب موضوعك

--- /code ---

--- /collapse ---

--- collapse ---
---
العنوان: استخدم أحرف الرموز التعبيرية
---

يمكنك استخدام أحرف الرموز التعبيرية في دالة النص p5 `()text` لاستخدام رمز تعبيري لتمثيل المشغل الخاص بك.

إليك مثالاً:

--- code ---
---
language: python
filename: main.py - setup()
---

def setup(): size(400, 400) text_size(40) #يتحكم في حجم الرموز التعبيرية text_align(CENTER, TOP) #موضع حول المركز

--- /code ---

Find the line `# Keep this to run your code`. Before that line, define a new `draw_obstacles()` function.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def draw_obstacles(): ob_x = width/2 ob_y = height/2 text('🌵', ob_x, ob_y)

--- /code ---

--- /collapse ---

[[[processing-python-text]]]

[[[generic-theory-simple-colours]]]

[[[processing-python-ellipse]]]

[[[processing-python-rect]]]

[[[processing-python-triangle]]]

[[[processing-tint]]]

[[[processing-stroke]]]

**نصيحة:** يمكنك استخدام عدة أشكال بسيطة في نفس الدالة لإنشاء مشغل أكثر تعقيدًا.

--- collapse ---
---
العنوان: ارسم لاعبًا باستخدام أشكال متعددة
---

![A tree drawn with green triangles for the body and a brown rectangle for the trunk](images/tree_obstacle.png)

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def draw_obstacles(): ob_x = width/2 ob_y = height/2 #رسم شجرة الصنوبر no_stroke() fill(0,255,0) #اخضر للاوراق الإبرية triangle(ob_x + 20, ob_y + 20, ob_x + 10, ob_y + 40, ob_x + 30, ob_y + 40) triangle(ob_x + 20, ob_y + 30, ob_x + 5, ob_y + 55, ob_x + 35, ob_y + 55) triangle(ob_x + 20, ob_y + 40, ob_x + 0, ob_y + 70, ob_x + 40, ob_y + 70) fill(150,100,100) # بني للساق rect(ob_x + 15, ob_y + 70, 10, 10)

--- /code ---

--- /collapse ---

--- /task ---

### احصل على عقبة تتحرك

--- task ---

أضف الآن تعليمات برمجية لزيادة موضع العائق `y` لكل إطار ، واجعله يلتف حوله عندما يصل إلى أسفل لإنشاء تأثير عقبة أخرى.

يبدأ المتغير p5 `frame_count` في حساب الإطارات عند النقر فوق "تشغيل".

`ob_y٪ = height` يعين موضع `y` على الباقي عند القسمة على `الارتفاع`. ويكون الارتفاع `height` مساويا لـ "400"، سيؤدي ذلك لتحويل `401` الى `1`، لذلك عندما تنحرف العوائق عن أسفل الشاشة، فإنها تظهر مرة أخرى في الأعلى.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

def draw_obstacles(): ob_x = width/2 ob_y = height/2 + frame_count #زيادة كل إطار ob_y %= height #الالتفاف text('🌵', ob_x, ob_y) #استبدل بعقبتك

--- /code ---

--- /task ---

### الكثير من العقبات

يمكنك رسم الكثير من نسخ العائق الخاص بك في مواقع بدء مختلفة ولكن هذا يتطلب الكثير من العمل. دعنا نستخدم الاختصار.

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;"> 
<span style="color: #0faeb0">**الجيل الإجرائي**</span> يُستخدم في إنشاء عوالم اللعبة والعقبات ومشاهد الأفلام لإنشاء عشوائية ولكن مع تطبيق قواعد معينة. يعني <span style="color: #0faeb0">بذرة</span> أنه يمكنك الحصول على نفس النتائج في كل مرة تستخدم فيها نفس البذرة.</p>

--- task ---

يستخدم هذا الرمز حلقة من `for` مع `()randint` لاختيار مواضع العائق لك. استدعاء الدالة العشوائية `()seed` أولاً يعني أنك ستحصل دائمًا على نفس الأرقام العشوائية. هذا يعني أن العوائق لن تقفز حول كل إطار ويمكنك تغيير البذرة حتى تحصل على واحدة تضع العوائق بشكل عادل.

--- code ---
---
language: python
filename: main.py - draw_obstacles()
---

seed(12345678)

    for i in range(6):<br x-id="2" />
        ob_x = randint(0, height)
        ob_y = randint(0, height) + frame_count
        ob_y %= height
        text('🌵', ob_x, ob_y) #استبدل بعقبتك

--- /code ---

معلومات مفيدة:

[[[using-seed-in-python]]]

[[[generic-python-for-loop-repeat]]]

--- /task ---

--- collapse ---
---
العنوان: تحذير الصرع
---

اختبار البرنامج الخاص بك لديه القدرة على إحداث نوبات للأشخاص الذين يعانون من صرع حساس للضوء. إذا كنت تعاني من صرع حساس للضوء أو تشعر أنك قد تكون عرضة لنوبة ، فلا تقم بتشغيل البرنامج. بدلاً من ذلك ، يمكنك:
- تأكد من أنك أضفت سطر التعليمات البرمجية ` () ` للتأكد من أن العوائق الخاصة بك لا تقفز
- اطلب من شخص ما تشغيله لك
- تابع المشروع وأكمله ، واطلب من شخص ما تشغيل المشروع نيابة عنك في النهاية حتى تتمكن من التصحيح
- Slow the game down by using `frame_rate = 10` in your call to `run()` like this:

```python
run(frame_rate = 10)
```
You can alter the speed of the game by changing `10` to a higher or lower value.

--- /collapse ---

--- task ---

**اختبار:** قم بتشغيل البرنامج وسترى كائنات متعددة على الشاشة ، تلتف حولها عندما تصل إلى الأسفل.

قم بتغيير الكود الخاص بك حتى تشعر بالرضا عن العقبات التي تواجهك. تستطيع:

+ قم بتغيير البذرة للحصول على عقبات في أوضاع بداية مختلفة
+ قم بتغيير عدد مرات تكرار التكرار للحصول على عدد مختلف من العوائق
+ اضبط حجم العوائق

**نصيحة:** تأكد من أنه من الممكن تجنب العقبات الخاصة بك ولكن لا يوجد طريق سهل خلال لعبتك.

--- /task ---

--- task ---

**تصحيح:** قد تجد بعض الأخطاء في مشروعك والتي تحتاج إلى إصلاحها. فيما يلي بعض الأخطاء الشائعة.

--- collapse ---
---
العنوان: يتم رسم عقبة واحدة فقط
---

تحقق من دالتك التي ترسم عوائق متعددة:
 + تأكد من أنه يستخدم حلقة `لـ` لاستدعاء وظيفة رسم العوائق أكثر من مرة
 + تأكد من أنه يستخدم `randint ()` لتغيير إحداثيات (س ، ص) التي يمر بها إلى دالة رسم العوائق
 + تأكد من أنك استخدمت `ob_x` و `ob_y` كإحداثيات لعائقك

مثال:

--- code ---
---
language: python
filename: main.py — draw_obstacles()
---

def draw_obstacles():

    for i in range(6):<br x-id="2" />
        ob_x = randint(0, height)
        ob_y = randint(0, height) + frame_count
        ob_y %= height
        text('🌵', ob_x, ob_y) #استبدل بعقبتك

--- /code ---

--- /collapse ---

--- collapse ---
---
العنوان: تقوم العوائق بتغيير موضعها في كل مرة يتم فيها رسم إطار
---

تأكد من أنك استخدمت `()seed` داخل الدالة التي ترسم عوائق متعددة.

--- /collapse ---

--- /task ---

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;"> 
يستخدم المبرمجون الكثير من الحيل الأنيقة مثل استخدام عامل التشغيل ``٪ '' لجعل الكائنات تلتف حول الشاشة و دالة 'seed ()`لتوليد نفس الأرقام العشوائية. كلما قمت بعمل المزيد من الترميز ، ستتعلم حيلًا أكثر دقة.</p>

--- save ---
