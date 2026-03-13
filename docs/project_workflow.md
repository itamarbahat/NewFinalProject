# NewFinalProject – Development Workflow

## Project Overview

This repository contains experiments for the final deep learning project
based on THz-like image degradation and image classification.

Main model currently under investigation: **TransNeXt**.

---

# Repository Structure

src/
data/
runs/
artifacts/

---

# Code Changes So Far

## datasets.py
Added ImageNet normalization after degradation.

## runner.py
Added freeze_backbone option for linear probe experiments.

---

# How to Work on the Project

## Opening in VSCode

1. Open folder `NewFinalProject`
2. Select interpreter `.venv`

---

# Git Workflow

Before starting work:

git pull

After finishing work:

git add .
git commit -m "Describe changes"
git push

בטח. הנה סיכום מסודר של מה שעשינו, ואיך לעבוד מעכשיו עם הפרויקט דרך VSCode ו־Git.

# מה עשינו עד עכשיו

## 1. קידמנו את הפרויקט עצמו

עבדנו על שילוב **TransNeXt** בתוך הפרויקט:

* הוספת את הקוד הרשמי של `TransNeXt`
* יצרנו `transnext_wrapper.py`
* חיברנו את `runner.py` כך שיוכל לטעון `transnext_micro`
* טענו pretrained checkpoint בהצלחה
* וידאנו שהמודל נטען ועושה forward pass
* הרצנו ניסויי smoke / pilot / long training
* הוספנו normalization ב־`datasets.py`
* הוספנו אפשרות `freeze_backbone` ב־`runner.py` לצורך linear probe
* תיעדנו ניסויים ב־`experiment_journal.md`
* ועדכנו טבלת סיכום דרך `summarize_runs`

## 2. שמרנו את שינויי הקוד החשובים לתיעוד

בפרט, נשמר בזיכרון שלי שאתה רוצה שאעקוב אחרי כל שינויי הקוד כדי לעזור לך לתעד אותם אחר כך.

## 3. הפכנו את הפרויקט ל־Git repository

עשינו:

* `git init`
* יצרנו `.gitignore`
* הוספנו את כל הפרויקט ל־Git
* יצרנו commit ראשון

## 4. חיברנו את הפרויקט ל־GitHub

יצרת repository והעלית את הכל ל:

`https://github.com/itamarbahat/NewFinalProject.git`

בנוסף:

* קבצי `.pt` ו־`.pth` מוגדרים דרך **Git LFS**
* כלומר weights/checkpoints עולים בצורה נכונה

---

# מה שינינו בקוד עד עכשיו

## ב־`datasets.py`

הוספנו **ImageNet normalization** אחרי ה־degradation:

* קודם: `ToTensor()` + `degrade_image(...)`
* עכשיו: גם `Normalize(mean, std)`

מטרה:
להתאים את הקלט למודל pretrained כמו TransNeXt.

## ב־`runner.py`

הוספנו תמיכה ב־**freeze_backbone**:

* פרמטר חדש ל־`run_experiment`
* דגל CLI בשם `--freeze_backbone`
* שמירה ב־`run_config.txt`
* לוג למסך
* הקפאת כל ה־backbone
* אימון רק של `model.head`

מטרה:
לבדוק אם head-only training עובד טוב יותר מ־fine-tuning מלא.

---

# איך לעבוד על הפרויקט מ־VSCode

## 1. לפתוח את הפרויקט

ב־VSCode:

* `File`
* `Open Folder`
* לבחור את התיקייה:

```text
C:\Users\ib94\Documents\NewFinalProject
```

## 2. לבחור את ה־Python interpreter הנכון

ב־VSCode:

* `Ctrl + Shift + P`
* חפש: `Python: Select Interpreter`
* בחר את ה־interpreter מתוך:

```text
.venv\Scripts\python.exe
```

זה חשוב מאוד, כדי ש־VSCode יעבוד עם אותה סביבה של PyCharm.

## 3. לעבוד על הקבצים

מכאן אפשר לערוך כרגיל:

* `src/data/datasets.py`
* `src/runner.py`
* `src/models/transnext_wrapper.py`
* `artifacts/summaries/experiment_journal.md`

## 4. להשתמש בטרמינל של VSCode

ב־VSCode:

* `Terminal`
* `New Terminal`

ואז אפשר להריץ משם:

```powershell
python main.py ...
git status
git add .
git commit -m "..."
git push
```

---

# איך עובדים עם Git מעכשיו

## שלושת השלבים הקבועים אחרי כל שינוי

### 1. לראות מה השתנה

```powershell
git status
```

### 2. להוסיף את השינויים

```powershell
git add .
```

### 3. לשמור אותם ב־commit

```powershell
git commit -m "תיאור קצר של השינוי"
```

### 4. להעלות ל־GitHub

```powershell
git push
```

---

# איך לכתוב commit message טוב

תכתוב תיאור קצר וברור של מה שינית.

דוגמאות טובות מהפרויקט שלך:

```powershell
git commit -m "Add TransNeXt wrapper and pretrained loading"
git commit -m "Add ImageNet normalization to CIFAR dataset"
git commit -m "Add freeze_backbone option for linear probe"
git commit -m "Update experiment journal and run summary"
git commit -m "Run TransNeXt batch size 8 experiment"
```

---

# איך לעבוד עם Git ישירות מתוך VSCode

בצד שמאל יש אייקון של:

```text
Source Control
```

שם אפשר:

* לראות אילו קבצים השתנו
* לכתוב הודעת commit
* לעשות Commit
* לעשות Push / Pull

כלומר לא חייבים לעבוד רק מהטרמינל.

אבל בהתחלה אני ממליץ לך עדיין להשתמש גם בפקודות:

* זה נותן יותר שליטה
* ויותר קל להבין מה קורה

---

# מה לעשות כשאתה מתחיל יום עבודה חדש

הסדר הכי נכון:

## אם אתה עובד על אותו מחשב

פשוט פתח את הפרויקט והמשך.

## אם השותפה או אתה עבדתם בינתיים

לפני כל עבודה חדשה תעשה:

```powershell
git pull
```

זה יוריד את העדכונים האחרונים מ־GitHub.

---

# מה לעשות אחרי שסיימת סשן עבודה

בסוף עבודה:

```powershell
git status
git add .
git commit -m "Describe what you changed"
git push
```

כך אף שינוי לא ילך לאיבוד.

---

# איך לעבוד עם השותפה נכון

הכלל הכי חשוב:

## לפני שמתחילים לעבוד

```powershell
git pull
```

## אחרי שמסיימים לעבוד

```powershell
git add .
git commit -m "..."
git push
```

זה ימנע התנגשויות ברוב המקרים.

---

# ממה להיזהר

## 1. לא לעבוד שתיכם על אותו קובץ בדיוק באותו זמן

למשל:

* אתה משנה `runner.py`
* והיא גם משנה `runner.py`

זה עלול ליצור conflict.

## 2. לעשות `git pull` לפני כל סשן עבודה

זה ההרגל הכי חשוב.

## 3. לא למחוק סתם קבצים מתוך `runs/` אם אתם משתפים הכל

כי עכשיו גם תוצאות הרצות נשמרות ב־GitHub.

---

# הפקודות הכי חשובות לזכור

```powershell
git status
git pull
git add .
git commit -m "message"
git push
```

---

# workflow מומלץ לפרויקט שלך

כל פעם שאתה עושה שינוי משמעותי:

1. משנה קוד
2. מריץ ניסוי
3. מעדכן `experiment_journal.md`
4. מריץ:

   ```powershell
   python -m src.tools.summarize_runs
   ```
5. ואז:

   ```powershell
   git add .
   git commit -m "Describe code changes and experiment"
   git push
   ```

זה ייתן לכם גם:

* ניהול גרסאות
* גם תיעוד
* גם גיבוי
* וגם שיתוף מסודר

---

# סיכום קצר מאוד

## מה עשינו

* שילבנו TransNeXt
* הוספנו normalization
* הוספנו freeze_backbone
* הרצנו ניסויים
* תיעדנו תוצאות
* חיברנו את כל הפרויקט ל־Git ו־GitHub

## איך לעבוד ב־VSCode

* לפתוח את התיקייה
* לבחור את ה־`.venv`
* לעבוד רגיל על הקבצים
* להשתמש בטרמינל או ב־Source Control

## איך לעבוד עם Git

* `git pull` לפני עבודה
* `git add .`
* `git commit -m "..."`
* `git push` בסוף

אם תרצה, הצעד הבא שאפשר לעשות הוא שאכין לך **דף עבודה קצר קבוע לפרויקט** — מין checklist יומי של 8–10 שורות, שתוכל לשמור בפרויקט ולעבוד לפיו כל פעם.

