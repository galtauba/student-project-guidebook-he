<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="UTF-8">
<title>ספר הדרכה לפרויקט</title>

<style>
body { font-family: Arial; line-height: 1.7; direction: rtl; background: #f8f6f2; }
section { margin-bottom: 30px; }
pre { background: #111; color: #eee; padding: 15px; border-radius: 10px; direction: ltr; }
.block { background: #fff3cd; padding: 15px; margin-bottom: 15px; border-radius: 10px; }
</style>

</head>

<body>

<h1>ספר הדרכה מלא לפרויקט</h1>

<h2>סקירה כללית</h2>

<h2>ארכיטקטורה</h2>

<h2>זרימות מערכת</h2>

<h2>פירוק קוד מלא</h2>

<section>

<h3>קובץ: example.py</h3>

<h4>תפקיד הקובץ</h4>
<p>...</p>

<h4>בלוק: בדיקת משתמש קיים</h4>

<div class="block">

<p><strong>הסבר:</strong></p>
<p>
כאן המערכת בודקת האם המשתמש כבר קיים במסד הנתונים.
אם כן, היא לא מאפשרת יצירת משתמש חדש עם אותו שם.
</p>

<p><strong>איך זה עובד:</strong></p>
<ul>
<li>מתבצעת שאילתה למסד הנתונים</li>
<li>נבדק אם התקבלה תוצאה</li>
<li>אם כן – מוסיפים שגיאה</li>
</ul>

<p><strong>קוד:</strong></p>

<pre><code>
user = query_db("SELECT * FROM users WHERE username = ?", (username,), one=True)
if user:
    errors.append("שם המשתמש כבר קיים")
</code></pre>

</div>

</section>

<h2>שאלות הכנה לראיון</h2>

<section>
<h3>שאלה 1 — Flow</h3>
<p>תסביר מה קורה כאשר משתמש נרשם למערכת.</p>
<ul>
<li>איזה בדיקות מתבצעות</li>
<li>איך נשמרים הנתונים</li>
<li>מה קורה במקרה של שגיאה</li>
</ul>
</section>

<h2>סיכום</h2>

</body>
</html>