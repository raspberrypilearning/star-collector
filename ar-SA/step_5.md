## الحفاظ على الوقت

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
الآن بعد أن أصبح بإمكان اللاعب جمع النجوم، أضف مؤقتًا لإظهار مقدار الوقت المستغرق في جمع النجوم الثلاثة. 
</div>
<div>
! [يُظهر عرض اللعبة متغير "النجوم" و "الوقت" على اللوحة القماشية مع توقف المؤقت عند تجميع النجمة الثالثة.] (images / timer-stop.gif) {: width = "300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">** ميكانيكة اللعبة **</span> جزء أساسي من تصميم اللعبة. إنها القواعد التي تتحكم في تصرفات اللاعب. A ** timer ** هو ميكانيكي ألعاب يضيف تحديًا لألعاب الفيديو - في الواقع ، هناك العديد من أرقام غينيس للأرقام القياسية استنادًا إلى مدى سرعة اللاعبين في إكمال التحديات في الألعاب!
</p>

يحتاج اللاعب إلى تتبع المدة التي يستغرقها لإكمال اللعبة المصغرة، يمكنك القيام بذلك باستخدام متغير آخر.

--- task ---

في نافذة التسلسل الهرمي، انقر بزر الماوس الأيمن على **Canvas** ومن واجهة المستخدم أنشئ نصًا آخر **TextMeshPro GameObject**. سترى "نص جديد" مكتوبًا على شاشتك في طريقة عرض اللعبة:

![عرض اللعبة مع عنصر نص واجهة المستخدم "نص جديد" يظهر عبر الشاشة.](images/new-timer.png)

--- /task ---

--- task ---

انقر بزر الماوس الأيمن على **Text (TMP) GameObject** الجديد وحدد **إعادة تسمية**. أطلق عليه `Time Text` للتعرف عليه بسهولة:

![تمت إعادة تسمية Time GameObject في نافذة Hierachy.](images/time-gameobject.png)

--- /task ---

--- task ---

من نافذة المفتش، في خاصية إدخال النص لـ TextMeshPro GameObject الجديد ، قم بتغيير `نص جديد` إلى `الوقت: 0`.

استخدم مكون **Rect Transform** لتغيير المحاذاة إلى **أعلى اليمين**. قم أيضًا بتغيير الموقع إلى `x = -60`، `y = -50`:

![تظهر نافذة المفتش مع القائمة المنسدلة للإعدادات المسبقة للإرساء أعلى اليمين و 'pos x' = -60 و 'Pos y' = -50 تم تحديث القيمة.](images/reposition-text-timer.png)

--- /task ---

يجب تحديث النص المعروض بحيث يعرض باستمرار عدد الثواني منذ بَدْء اللعبة.

--- task ---

افتح البرنامج النصي `StarPlayer` وأضف رمزًا لإنشاء كائن TMP_Text يسمى `timeText`:

--- code ---
---
language: cs filename: StarPlayer.cs line_numbers: true line_number_start: 6
line_highlights: 10
---
public class StarPlayer : MonoBehaviour
{ public int stars = 0; // An integer whole number public TMP_Text starText; public TMP_Text timeText; --- /code ---

--- /task ---

--- task ---

`يعطي Time.time` الوقت بالثواني منذ بَدْء المشهد. `الرياضيات: الجولة` تحول الرَّقْم إلى عدد صحيح.

اضبط النص لإظهار عدد الثواني الكاملة في كل تحديث:

--- code ---
---
language: cs filename: StarPlayer.cs - Update() line_numbers: true line_number_start: 18
line_highlights: 21
---

    void Update()
    {
        starText.SetText("Stars: " + stars);
        timeText.SetText("Time: " + Mathf.Round(Time.time));
    }
--- /code ---

احفظ النص البرمجي الخاص بك ثم عد إلى محرر Unity.

--- /task ---

--- task ---

حدد المشغل في نافذة التسلسل الهرمي وانتقل إلى مكون البرنامج النصي `Star Player` في نافذة المفتش. انقر على الدائرة المجاورة لـ `Time Text` واختر كائن "Time Text" الجديد.

--- /task ---

--- task ---

**اختبار:** قم بتشغيل برنامجك وتحقق من رسم خط مدار أبيض. ماذا يحدث عندما تجمع كل النجوم الثلاثة؟

![عرض اللعبة مع نص واجهة المستخدم يظهر ثلاث نجوم مجمعة ومدة 45 ثانية.](images/both-texts-updating.gif)

--- /task ---

يجب أن يتوقف الوقت عند جمع النجوم الثلاثة، لكنه سيستمر في العد حاليًا مادام أن اللعبة المصغرة تلعب.

--- task ---

افتح البرنامج النصي `StarPlayer` وقم بإنشاء عبارة if حول رمز الوقت الخاص بك لحساب الثواني فقط إذا كان اللاعب قد جمع أقل من ثلاث نجوم:

--- code ---
---
language: cs filename: StarPlayer.cs - Update() line_numbers: true line_number_start: 18
line_highlights: 21-24
---

    void Update()
    {
        starText.SetText("Stars: " + stars);
        if (stars < 3)
        {
            timeText.SetText("Time: " + Mathf.Round(Time.time));
        }
    }
--- /code ---

احفظ نصك البرمجي ثم عد إلى محرر Unity.

--- /task ---

--- task ---

**اختبار:** قم بتشغيل مشروعك. سيتوقف المؤقت عندما يحصل اللاعب على ثلاث نجوم:

![تُظهر طريقة عرض اللعبة عداد الوقت الذي يصل إلى 45 ويتوقف عند 47 عندما يتم جمع ثلاث نجوم.](images/timer-stops.gif)

--- /task ---

بعد خطوة التفكير، يمكنك ترقية مشروعك بالميزات التي تعتقد أنها مهمة.

--- save ---
