<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>ספר הדרכה לפרויקט</title>
  <style>
    :root {
      --bg: #f7f3eb;
      --paper: #fffdf8;
      --line: #dccfb9;
      --text: #1f2937;
      --muted: #5b6472;
      --brand: #0f766e;
      --accent: #b45309;
      --soft: #eef8f5;
      --shadow: 0 16px 40px rgba(15, 23, 42, 0.08);
      --radius: 24px;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: "Segoe UI", Tahoma, sans-serif;
      color: var(--text);
      background: linear-gradient(180deg, #fbf8f2, var(--bg));
      line-height: 1.75;
    }

    .shell {
      width: min(1600px, calc(100% - 40px));
      margin: 0 auto;
      display: grid;
      grid-template-columns: 340px 1fr;
      gap: 24px;
      padding: 20px 0 40px;
    }

    .sidebar {
      position: sticky;
      top: 16px;
      align-self: start;
      max-height: calc(100vh - 32px);
      overflow: auto;
      background: var(--paper);
      border: 1px solid var(--line);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 20px;
    }

    .sidebar h2 {
      margin-top: 0;
      font-size: 1.1rem;
    }

    .toc-group {
      margin-bottom: 14px;
    }

    .toc-file {
      margin-top: 10px;
      padding-top: 10px;
      border-top: 1px solid #efe5d6;
    }

    .toc-file > a {
      display: block;
      font-weight: 700;
      text-decoration: none;
      color: var(--text);
      padding: 6px 0;
    }

    .toc-sub {
      margin-right: 14px;
      padding-right: 10px;
      border-right: 2px solid #eadfcd;
    }

    .toc-sub a {
      display: block;
      text-decoration: none;
      color: var(--muted);
      padding: 5px 0;
      font-size: 0.95rem;
    }

    .content {
      display: grid;
      gap: 20px;
    }

    .section {
      background: var(--paper);
      border: 1px solid var(--line);
      border-radius: 28px;
      box-shadow: var(--shadow);
      padding: 28px;
    }

    .hero {
      background:
        linear-gradient(135deg, rgba(15,118,110,.08), rgba(180,83,9,.08)),
        var(--paper);
    }

    h1, h2, h3, h4 {
      margin-top: 0;
      line-height: 1.25;
    }

    .lead {
      color: var(--muted);
      font-size: 1.05rem;
    }

    .file-section {
      margin-top: 24px;
      padding-top: 24px;
      border-top: 1px solid #ece3d4;
    }

    .unit-section {
      margin-top: 20px;
      padding: 18px;
      background: #fffaf1;
      border: 1px solid #eadfcd;
      border-radius: 20px;
    }

    .context-box {
      background: var(--soft);
      border: 1px solid #cfe7df;
      border-radius: 16px;
      padding: 14px 16px;
      margin: 12px 0;
    }

    .code-block {
      background: #111827;
      color: #f9fafb;
      border-radius: 18px;
      padding: 18px;
      overflow-x: auto;
      direction: ltr;
      text-align: left;
      font-family: Consolas, "Courier New", monospace;
      font-size: 0.92rem;
      line-height: 1.6;
      white-space: pre;
    }

    .question {
      margin-top: 16px;
      padding: 16px;
      border: 1px solid #eadfcd;
      border-radius: 18px;
      background: #fff;
    }

    .small {
      color: var(--muted);
      font-size: 0.95rem;
    }

    /* Desktop only target: no mobile-first collapsing */
  </style>
</head>
<body>
  <div class="shell">
    <aside class="sidebar">
      <h2>תוכן עניינים</h2>

      <div class="toc-group">
        <a href="#overview">סקירה כללית</a>
        <a href="#architecture">ארכיטקטורה</a>
        <a href="#flows">זרימות מערכת</a>
        <a href="#files-overview">מבנה הקבצים</a>
        <a href="#questions">שאלות לבחינה</a>
        <a href="#summary">סיכום</a>
      </div>

      <div class="toc-file">
        <a href="#file-app-py">app.py</a>
        <div class="toc-sub">
          <a href="#unit-app-init-db">אתחול וחיבור למסד</a>
          <a href="#unit-app-user-exists">בדיקת משתמש קיים</a>
          <a href="#unit-app-register-validation">ולידציה של הרשמה</a>
          <a href="#unit-app-approve-order">אישור הזמנה</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-templates-login-html">templates/login.html</a>
        <div class="toc-sub">
          <a href="#unit-login-form-structure">מבנה הטופס</a>
        </div>
      </div>
    </aside>

    <main class="content">
      <section class="section hero" id="overview">
        <h1>ספר הדרכה מלא לפרויקט</h1>
        <p class="lead">כאן יבוא הסבר פתיחה ברור על המערכת.</p>
      </section>

      <section class="section" id="architecture">
        <h2>ארכיטקטורה</h2>
        <p>כאן יבוא ההסבר הארכיטקטוני.</p>
      </section>

      <section class="section" id="flows">
        <h2>זרימות מערכת</h2>
        <p>כאן יבואו הזרימות המרכזיות.</p>
      </section>

      <section class="section" id="files-overview">
        <h2>מבנה הקבצים</h2>
        <p>כאן יבוא הסבר קצר על הקבצים בפרויקט.</p>
      </section>

      <section class="section" id="file-app-py">
        <h2>קובץ: app.py</h2>
        <p>כאן יבוא תפקיד הקובץ.</p>

        <article class="unit-section" id="unit-app-init-db">
          <h3>יחידה רעיונית: אתחול וחיבור למסד</h3>

          <div class="context-box">
            <strong>הקשר:</strong>
            לפני שכל פעולה במערכת יכולה לעבוד, האפליקציה חייבת לדעת איפה מסד הנתונים ואיך לפתוח אליו חיבור.
          </div>

          <p><strong>מה היחידה עושה:</strong> כאן מסבירים את תפקיד הבלוק.</p>

          <pre class="code-block"><code>def get_db():
    if "db" not in g:
        g.db = sqlite3.connect(...)
    return g.db</code></pre>

          <p><strong>איך זה עובד:</strong> כאן יבוא ההסבר של הקוד עצמו.</p>
          <p><strong>מה יקרה אם הבלוק יישבר:</strong> כאן יבוא הסבר ההשפעה.</p>
        </article>

        <article class="unit-section" id="unit-app-user-exists">
          <h3>יחידה רעיונית: בדיקת משתמש קיים</h3>

          <div class="context-box">
            <strong>הקשר:</strong>
            במהלך הרשמה, לפני יצירת משתמש חדש, המערכת חייבת לוודא שאין כבר משתמש עם אותו שם.
          </div>

          <p><strong>מה היחידה עושה:</strong> בודקת האם שם המשתמש כבר תפוס במסד הנתונים.</p>

          <pre class="code-block"><code>if query_db("SELECT user_id FROM users WHERE username = ?", (username,), one=True):
    errors.append("שם המשתמש כבר קיים במערכת.")</code></pre>

          <p><strong>איך זה עובד:</strong> השאילתה מחפשת משתמש קיים. אם נמצאה תוצאה, מוסיפים שגיאה ולא ממשיכים ליצירת החשבון.</p>
          <p><strong>מה יקרה אם הבלוק יישבר:</strong> ייתכן ניסיון ליצור משתמש כפול או קבלת שגיאת מסד.</p>
        </article>
      </section>

      <section class="section" id="file-templates-login-html">
        <h2>קובץ: templates/login.html</h2>
        <p>כאן יבוא הסבר על תפקיד המסך.</p>

        <article class="unit-section" id="unit-login-form-structure">
          <h3>יחידה רעיונית: מבנה טופס ההתחברות</h3>

          <div class="context-box">
            <strong>הקשר:</strong>
            זהו המסך שבו המשתמש מכניס את פרטי ההתחברות שלו.
          </div>

          <pre class="code-block"><code>&lt;form method="post"&gt;
  &lt;input name="username"&gt;
  &lt;input name="password" type="password"&gt;
  &lt;button type="submit"&gt;התחבר&lt;/button&gt;
&lt;/form&gt;</code></pre>

          <p><strong>איך זה עובד:</strong> הטופס שולח POST ל-route של ההתחברות, והשרת קורא את השדות מהבקשה.</p>
        </article>
      </section>

      <section class="section" id="questions">
        <h2>שאלות לבחינה</h2>

        <article class="question">
          <h3>שאלה — זרימה</h3>
          <p>תסביר מה קורה כאשר משתמש נרשם למערכת.</p>
          <ul>
            <li>אילו שדות נאספים מהטופס</li>
            <li>אילו בדיקות תקינות מתבצעות</li>
            <li>איך המידע נשמר</li>
            <li>למה צריך אישור מנהל</li>
          </ul>
        </article>
      </section>

      <section class="section" id="summary">
        <h2>סיכום</h2>
        <p>כאן יבוא סיכום לימודי של הפרויקט.</p>
      </section>
    </main>
  </div>
</body>
</html>