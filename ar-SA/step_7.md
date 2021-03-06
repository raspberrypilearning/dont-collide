## قم بترقية مشروعك

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
إذا كان لديك الوقت ، يمكنك تطوير مشروعك.
</div>
<div>

![مثال مشروع sace مع حيوات.](images/example1.png){:width="300px"}

</div>
</div>

إليك بعض الأفكار لمساعدتك:

### قم بتضمين مجموعة متنوعة من العقبات
يمكنك إضافة مجموعة متنوعة إلى عقباتك بعدة طرق:
 - اختر عشوائيًا بين العديد من الصور أو الرموز التعبيرية أو دوال رسم العوائق
 - اضبط لون العوائق أو شكلها أو حجمها عشوائيًا عن طريق تغيير المتغيرات التي ترسمها
 - حرك العائق عن طريق إضافة دوران ، أو تغيير اللون ، أو بعض الاختلافات المرئية الأخرى التي يتم التحكم فيها بواسطة `frame_count`

### أضف شرط الفوز
يمكنك جعل اللاعبين يفوزون باللعبة بعدة طرق:
 - تحقيق نتيجة الفوز
 - الوصول إلى مستوى معين من اللعبة

بمجرد فوزهم ، يجب أن تخبرهم بطريقة ما - ربما باستخدام `()print` أو `()text` ثم إيقاف اللعبة.

### امنح اللاعبين أكثر من حياة واحدة
أضف الأرواح إلى لعبتك ، للسماح للاعبين بالنجاة من بعض الاصطدامات. هذا أصعب قليلاً من مجرد القيام `lives =- 1` في كل مرة يصطدمون بشيء ما:
 - قد يقضي اللاعب إطارات متعددة على اتصال بجسم ما ، وبالتالي يفقد أكثر من حياة لتصادم واحد - ستحتاج إلى منع حدوث ذلك
 - ستحتاج أيضًا إلى وسيلة للاعبين لمعرفة عدد الأرواح المتبقية لديهم ، وربما نوعًا من التحذير يخبرهم عندما يكونون في حياتهم الأخيرة
 - يمكنك إضافة كائن ، عندما يصطدم به اللاعب ، يمنحه حياة إضافية. تذكر أنك ستحتاج إلى تعديل الشفرة البرمجية للاصطدام العادي بحيث لا يطرح الحياة في نفس الوقت!

يحتوي كل مشروع مثال في [مقدمة](./) على رابط **انظر داخل** لكي تفتح المشروع وتنظر إلى الشفرة البرمجية للحصول على أفكار ومعرفة كيفية عملها. يحتوي مشروع "دودج كويكبات" أدناه على كل هذه الميزات:

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 175px; flex-grow: 1">  

**دودج كويكبات**: [راجع الداخل](https://trinket.io/python/e2993a6a3c){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/e2993a6a3c?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

</div>
</div>

ألقِ نظرة على بعض مشاريع "لا تصطدم" التي أنشأها أعضاء المجتمع في [لا تتعارض مع مؤسسة Raspberry Pi Foundation - مكتبة المجتمع](https://wke.lt/w/s/KobNfx){:target="_blank"}.

--- save ---
