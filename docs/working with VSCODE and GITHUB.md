.
איך לפתוח את הפרויקט שלך מ-GitHub בתוך **VSCode** בצורה נכונה.

יש שתי אפשרויות. במקרה שלך עדיף **אפשרות 1**, כי הפרויקט כבר קיים אצלך במחשב.

---

# אפשרות 1 (הכי פשוטה במקרה שלך)

## פתיחת הפרויקט המקומי ב-VSCode

הקוד כבר נמצא אצלך כאן:

```
C:\Users\ib94\Documents\NewFinalProject
```

### שלב 1 — פתיחת VSCode

פתח **Visual Studio Code**.

---

### שלב 2 — פתיחת התיקייה

בתפריט העליון:

```
File → Open Folder
```

בחר את התיקייה:

```
NewFinalProject
```

ואז לחץ:

```
Select Folder
```

---

### שלב 3 — בחירת סביבת Python הנכונה

מאוד חשוב לבחור את ה־environment שכבר יצרת.

לחץ:

```
Ctrl + Shift + P
```

כתוב:

```
Python: Select Interpreter
```

ובחר את:

```
.venv\Scripts\python.exe
```

זה אומר ש-VSCode משתמש באותה סביבת Python של הפרויקט.

---

### שלב 4 — בדיקה שהכל עובד

פתח Terminal בתוך VSCode:

```
Terminal → New Terminal
```

ואז תריץ:

```bash
python --version
```

ואז:

```bash
git status
```

אם אתה רואה:

```
On branch main
Your branch is up to date with 'origin/main'.
```

אז הכל מחובר ל-GitHub.

---

# איך לעבוד עם Git בתוך VSCode

בצד שמאל יש אייקון:

```
Source Control
```

שם תוכל לראות:

* אילו קבצים השתנו
* לבצע commit
* לבצע push
* לבצע pull

אבל אני ממליץ בהתחלה לעבוד גם דרך ה-Terminal.

---

# workflow רגיל בעבודה על הפרויקט

## בתחילת יום עבודה

```bash
git pull
```

כדי להוריד שינויים מ-GitHub.

---

## אחרי ששינית קוד

```bash
git status
git add .
git commit -m "תיאור השינוי"
git push
```

---

# אם תרצה לפתוח את הפרויקט במחשב אחר

אז עושים:

```bash
git clone https://github.com/itamarbahat/NewFinalProject.git
```

ואז פותחים את התיקייה ב-VSCode.

---

# טיפ חשוב לפרויקט שלך

כדאי לעבוד בעיקר על הקבצים האלה:

```
src/runner.py
src/data/datasets.py
src/models/transnext_wrapper.py
artifacts/summaries/experiment_journal.md
```

ולא לשנות סתם את הקוד בתוך:

```
src/models/transnext_official/
```

כי זה הקוד המקורי של המודל.

---

# אם תרצה

אני יכול גם להראות לך **טריק מאוד שימושי לעבודה עם Git בתוך VSCode** שנקרא:

**Git Graph**

הוא מאפשר לראות בצורה ויזואלית:

* כל הניסויים
* כל הקומיטים
* מי שינה מה

וזה מאוד נוח בפרויקטי Deep Learning.




מצוין — השאלה שלך בדיוק נוגעת ללב העבודה עם **Git + GitHub**, ואני אסביר לך את זה בצורה ברורה.
החדשות הטובות: **כבר יצרת את החיבור**. עכשיו רק צריך להבין איך עובדים איתו ביום-יום.

--
# איך GitHub + VSCode עובדים יחד

חשוב להבין את המודל:

יש **שלושה מקומות** שבהם הקוד קיים:

```
1️⃣ המחשב שלך (Local Repository)
2️⃣ GitHub (Remote Repository)
3️⃣ המחשב של השותפה שלך
```

החיבור ביניהם נראה כך:

```
המחשב שלך  ←→  GitHub  ←→  המחשב של השותפה
```

Git הוא הכלי שמסנכרן ביניהם.

---

# מה קורה בפועל

אתה **לא עובד ישירות על GitHub**.

אתה עובד על **הקבצים המקומיים במחשב שלך**, ואז:

```
git push
```

שולח אותם ל-GitHub.

והשותפה שלך מקבלת אותם עם:

```
git pull
```

---

# איך נראה יום עבודה רגיל

## שלב 1 — מתחילים לעבוד

פותחים את הפרויקט ב-VSCode.

ואז מריצים:

```bash
git pull
```

זה עושה:

```
GitHub → המחשב שלך
```

ומוריד את כל השינויים שהשותפה עשתה.

---

# שלב 2 — עובדים על הקוד

אתה משנה קבצים למשל:

```
runner.py
datasets.py
experiment_journal.md
```

VSCode יראה לך שהם השתנו.

---

# שלב 3 — שומרים את השינויים

ב-Terminal:

```bash
git add .
git commit -m "שינוי בקוד האימון"
```

---

# שלב 4 — מעלים ל-GitHub

```bash
git push
```

עכשיו השינויים נמצאים ב-GitHub.

---

# שלב 5 — השותפה מקבלת אותם

היא עושה:

```bash
git pull
```

והקוד המעודכן יורד אליה.

---

# סיכום זרימת העבודה

```
אתה משנה קוד
        ↓
git add
        ↓
git commit
        ↓
git push
        ↓
GitHub מתעדכן
        ↓
השותפה עושה git pull
        ↓
הקוד המעודכן מגיע אליה
```

---

# מה אתה צריך לעשות בפעם הבאה שתעבוד

פשוט:

### 1️⃣ פתח VSCode

### 2️⃣ פתח את תיקיית הפרויקט

```
NewFinalProject
```

### 3️⃣ תריץ

```bash
git pull
```

ואז אתה עובד רגיל.

לא צריך להוריד שוב את הפרויקט.

---

# הטריק שהבטחתי – Git Graph

זה אחד הכלים הכי טובים לפרויקטים כאלה.

הוא נותן **גרף ויזואלי של כל הקומיטים**.

---

## איך מתקינים

ב-VSCode:

```
Extensions
```

חפש:

```
Git Graph
```

והתקן.

האייקון נראה כך:

```
Git Graph
```

---

## מה הוא מראה

הוא מציג:

```
● commit
│
● commit
│
● commit
```

ואתה יכול לראות:

* מי עשה שינוי
* מתי
* באיזה קובץ

מאוד שימושי לפרויקט משותף.

---

# עוד טיפ חשוב לפרויקט Deep Learning

בגלל שאתם מעלים **ניסויים ומשקלים**, ה-workflow יהיה כזה:

```
קוד → git commit
ניסוי → נשמר ב runs/
תוצאות → git push
שותפה → git pull
```

כך שניכם רואים את כל הניסויים.

---

##משהו חשוב מאוד לגבי הפרויקט שלך

כרגע העלית בערך **3.4GB של משקלים** ל-GitHub.

זה עובד כי השתמשת ב-**Git LFS** 👍
      
אבל צריך להיזהר:

אם תמשיכו להעלות הרבה ניסויים, זה יכול להגיע ל-**עשרות גיגה**.

יש טריק לניהול נכון של זה.
הסבר:
---
מעולה. זה באמת אחד הדברים הכי חשובים בפרויקט כמו שלכם.
כשעובדים על **Deep Learning עם הרבה ניסויים**, מאוד מהר נהיה בלגן:

* עשרות תיקיות `runs`
* הרבה משקלים `.pt`
* גרסאות שונות של הקוד
* קשה לזכור איזה ניסוי נתן איזה תוצאה

השיטה המקצועית שבה משתמשים במעבדות נקראת:

# שיטת ניהול ניסויים (Experiment Management)

היא מבוססת על **3 עקרונות פשוטים**.

---

# 1️⃣ הפרדה בין קוד לניסויים

הכלל הכי חשוב:

```
הקוד נמצא ב-Git
התוצאות הן רק נתונים
```

מבנה נכון נראה כך:

```
NewFinalProject

src/
    runner.py
    datasets.py
    models/

data/

runs/
    experiment_001
    experiment_002
    experiment_003

artifacts/
    tables/
    summaries/
```

כל ניסוי מקבל תיקייה משלו.

לדוגמה:

```
runs/transnext_lr1e-4_bs8/
```

ובתוכה:

```
metrics.csv
log.txt
best.pt
model_last.pt
run_config.txt
```

זה כבר מה שעשיתם — וזה מצוין.

---

# 2️⃣ לכל ניסוי חייב להיות run_config

זה אחד הדברים הכי חשובים לשחזור ניסוי.

בתוך כל run יש:

```
run_config.txt
```

לדוגמה:

```
model=transnext_micro
pretrained=True
out_size=224
low_res=16
lr=0.001
batch_size=8
epochs=10
freeze_backbone=True
```

כך אפשר תמיד לדעת **איך הניסוי רץ**.

---

# 3️⃣ יומן ניסויים (Experiment Journal)

זה אחד הדברים שהכי מבדילים פרויקט מקצועי.

יש לכם כבר קובץ:

```
artifacts/summaries/experiment_journal.md
```

כל ניסוי חדש מתועד שם.

לדוגמה:

```markdown
## Experiment 17 — TransNeXt Linear Probe

Goal:
Check whether pretrained TransNeXt features already contain useful representations.

Parameters:
model = transnext_micro
pretrained = True
freeze_backbone = True
lr = 1e-3
batch_size = 8

Result:
Validation accuracy: 54%

Conclusion:
Linear probe performs significantly better than full fine-tuning.
```

כך אתם לא שוכחים מה ניסיתם.

---

# 4️⃣ טבלת סיכום אוטומטית

הסקריפט שכבר יש לכם:

```
src/tools/summarize_runs.py
```

סורק את כל התיקיות:

```
runs/
```

ויוצר:

```
artifacts/tables/run_summary.csv
```

לדוגמה:

| model           | lr   | resolution | accuracy |
| --------------- | ---- | ---------- | -------- |
| resnet50        | 1e-3 | 32         | 48%      |
| densenet121     | 1e-3 | 32         | 51%      |
| transnext_micro | 1e-3 | 224        | 54%      |

זה מאוד עוזר למצגת.

---

# 5️⃣ איך עובדים נכון עם Git בפרויקט כזה

הכלל:

### תמיד מתחילים עם

```bash
git pull
```

כדי לקבל שינויים מהשותפה.

---

### אחרי ניסוי חדש

```bash
git add .
git commit -m "Run TransNeXt linear probe experiment"
git push
```

---

# 6️⃣ טריק מקצועי מאוד

אל תעלו **כל ניסוי** ל-GitHub.

בדרך כלל מעלים רק:

```
runs/official/
```

ולא:

```
runs/pilot/
```

כלומר:

```
runs/
    pilot/      ← ניסויים זמניים
    official/   ← ניסויים שמופיעים בדוח
```

כך ה-repo לא מתנפח.

---

# 7️⃣ טריק מתקדם מאוד (מעבדות מחקר)

בפרויקטים גדולים משתמשים בכלים כמו:

* **Weights & Biases**
* **MLflow**
* **TensorBoard**

אבל לפרויקט שלכם זה **כנראה מוגזם**.

השיטה שאתם משתמשים בה עכשיו היא **יותר ממספיק לפרויקט גמר**.

---

# משהו מאוד חשוב לגבי הפרויקט שלכם

עברתי על הקומיט שעשית.

יש לכם כבר:

```
~3.4GB משקלים
```

וזה עוד לפני ניסויי הסיום.

כדאי לעשות שינוי קטן במבנה כדי שלא תגיעו ל-20GB.

---

💡 אם תרצה, אני יכול גם להראות לך:

### מבנה תיקיות **הרבה יותר טוב לפרויקט שלכם ספציפית**

שיעשה:

* פחות בלגן
* פחות משקלים מיותרים
* יותר קל להכין גרפים למצגת

וזה שינוי קטן של **5 דקות בלבד** אבל משפר מאוד את העבודה.

##💡.זה מה שעושים:
מצוין. עכשיו אראה לך **מבנה תיקיות הרבה יותר מקצועי לפרויקט שלכם**, כזה שמשתמשים בו בפרויקטי Deep Learning אמיתיים.
היתרון:

* פחות בלגן
* קל למצוא ניסויים
* GitHub לא מתנפח
* קל להכין גרפים למצגת

ואפשר לעבור אליו **ב־5 דקות בלי לשבור שום דבר בקוד**.

---

# הבעיה במבנה הנוכחי

כרגע יש לכם:

```
runs/
    archive/
    pilot/
    official/
```

ובתוך כל תיקייה יש הרבה ניסויים עם:

```
best.pt
model_last.pt
metrics.csv
log.txt
run_config.txt
```

הבעיה:

1️⃣ כל משקל ~90MB
2️⃣ הרבה ניסויים → הרבה GB
3️⃣ קשה לראות מהר **איזה ניסוי טוב**

---

# המבנה המקצועי יותר

המבנה המומלץ:

```
NewFinalProject

src/

data/

runs/
    experiments/

artifacts/
    figures/
    tables/
    summaries/

models/
    checkpoints/

docs/
```

---

# מה המשמעות של כל תיקייה

## runs/experiments

כל ניסוי מקבל תיקייה.

```
runs/experiments/

resnet50_baseline_lr1e3
densenet121_baseline
transnext_linear_probe
transnext_finetune_small
```

ובתוכה:

```
metrics.csv
log.txt
run_config.txt
```

שימו לב:

❗ לא חייבים לשמור כאן את המשקלים.

---

# models/checkpoints

פה שמים **רק משקלים חשובים**.

לדוגמה:

```
models/checkpoints/

resnet50_best.pt
densenet121_best.pt
transnext_linear_probe_best.pt
transnext_final.pt
```

כלומר:

שומרים רק את **המודלים הכי טובים**.

---

# artifacts

זה כל מה שצריך למצגת / דוח.

```
artifacts/

figures/
tables/
summaries/
```

לדוגמה:

```
artifacts/figures/accuracy_vs_resolution.png
artifacts/tables/run_summary.csv
artifacts/summaries/experiment_journal.md
```

---

# למה זה הרבה יותר טוב

## במקום

```
runs/
    30 תיקיות
        model_last.pt
```

יש:

```
runs/experiments/
    רק לוגים וmetrics

models/checkpoints/
    רק המודלים הכי טובים
```

התוצאה:

```
Repository קטן פי 5
```

---

# דוגמה לניסוי

נניח שאתה מריץ:

```
TransNeXt
lr=1e-4
lowres=16
```

הקוד יוצר:

```
runs/experiments/transnext_lr1e4_lowres16/

metrics.csv
log.txt
run_config.txt
```

ואם הוא טוב:

אתה מעתיק את המשקל ל:

```
models/checkpoints/transnext_lr1e4_best.pt
```

---

# יתרון נוסף למצגת

כשתכינו גרפים:

הסקריפט שלכם קורא:

```
metrics.csv
```

ולא את המודל.

כלומר:

אפשר אפילו למחוק משקלים ישנים.

---

# שינוי קטן שמומלץ לעשות

כרגע כל run שומר:

```
best.pt
model_last.pt
```

אפשר לשמור רק:

```
best.pt
```

זה חוסך:

```
50% מקום
```

---

# workflow מומלץ לפרויקט שלכם

### לפני עבודה

```
git pull
```

---

### אחרי ניסוי

```
git add .
git commit -m "Run TransNeXt linear probe"
git push
```

---

# טיפ חשוב מאוד

לפעמים עדיף **לא להעלות משקלים ל-GitHub בכלל**.

במקום זה:

שומרים אותם מקומית.

ורק מעלים:

```
metrics.csv
run_config.txt
```

כי זה מספיק כדי להציג תוצאות.

---

# משהו מאוד חשוב לגבי הפרויקט שלכם

ראיתי שאתם כבר עם:

```
~3.4GB ב-GitHub
```

וזה עוד לפני ניסויי הסיום.

GitHub LFS נותן בערך:

```
10GB bandwidth
```

לכן כדאי לנהל משקלים בזהירות.

---

# אם תרצה

אני יכול גם להראות לך משהו **מאוד חזק לפרויקט שלכם**:

איך לייצר אוטומטית:

```
גרף Accuracy
גרף Loss
טבלת השוואה בין מודלים
```

מכל הניסויים ב־`runs/`.

זה לוקח בערך **30 שורות Python**
ויחסוך לכם שעות בהכנת המצגת
---אולי בהמשך...
