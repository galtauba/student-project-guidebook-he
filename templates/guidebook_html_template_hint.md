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
      width: min(1700px, calc(100% - 40px));
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

    /* Desktop-focused layout only */
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
          <a href="#unit-app-duplicate-username-check">בדיקת שם משתמש קיים</a>
          <a href="#unit-app-register-validation">ולידציה של הרשמה</a>
          <a href="#unit-app-build-selected-items">בניית selected_items</a>
          <a href="#unit-app-shortage-detection">בדיקת חוסרים במלאי</a>
          <a href="#unit-app-approve-order">אישור הזמנה והפחתת מלאי</a>
          <a href="#unit-app-reject-return-block">דחיית החזרה ויצירת חסימה</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-templates-login-html">templates/login.html</a>
        <div class="toc-sub">
          <a href="#unit-login-form-structure">מבנה הטופס</a>
          <a href="#unit-login-inputs">שדות הקלט</a>
          <a href="#unit-login-submit">כפתור השליחה</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-static-style-css">static/style.css</a>
        <div class="toc-sub">
          <a href="#unit-style-root-vars">משתני root</a>
          <a href="#unit-style-layout">מבנה layout</a>
          <a href="#unit-style-sidebar">עיצוב sidebar</a>
          <a href="#unit-style-cards-tables">כרטיסים וטבלאות</a>
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
            לפני שכל route יוכל לקרוא או לעדכן נתונים, האפליקציה חייבת לדעת איך לפתוח חיבור למסד הנתונים ולסגור אותו נכון.
          </div>
          <p><strong>מה היחידה עושה:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
          <pre class="code-block"><code>def get_db():
    ...
</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר מפורט לקוד עצמו.</p>
        </article>

        <article class="unit-section" id="unit-app-duplicate-username-check">
          <h3>יחידה רעיונית: בדיקת שם משתמש קיים</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            בזמן הרשמה המערכת חייבת לוודא שאין כבר משתמש עם אותו username.
          </div>
          <p><strong>מה היחידה עושה:</strong> בודקת אם כבר קיימת רשומת משתמש עם אותו שם משתמש, ואם כן מוסיפה שגיאה.</p>
          <pre class="code-block"><code>if query_db("SELECT user_id FROM users WHERE username = ?", (username,), one=True):
    errors.append("שם המשתמש כבר קיים במערכת.")</code></pre>
          <p><strong>איך זה עובד:</strong> השאילתה מחפשת התאמה בטבלת users. אם התקבלה תוצאה, המשמעות היא שהשם כבר תפוס ולכן ההרשמה לא אמורה להמשיך כרגיל.</p>
        </article>

        <article class="unit-section" id="unit-app-register-validation">
          <h3>יחידה רעיונית: ולידציה של הרשמה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי קריאת השדות מהטופס, המערכת חייבת לוודא שהנתונים תקינים לפני שמירת משתמש חדש.
          </div>
          <pre class="code-block"><code>errors = []
if not username:
    errors.append("יש להזין שם משתמש.")
if not password:
    errors.append("יש להזין סיסמה.")
if not full_name:
    errors.append("יש להזין שם מלא.")
if role == "user" and not team_id:
    errors.append("יש לבחור צוות למשתמש רגיל.")</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לולידציה הזאת.</p>
        </article>

        <article class="unit-section" id="unit-app-build-selected-items">
          <h3>יחידה רעיונית: בניית selected_items</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            בזמן יצירת הזמנה, צריך לבנות רשימה של רק הפריטים שבאמת הוזמנו בכמות חיובית.
          </div>
          <pre class="code-block"><code>selected_items = []
for item in items:
    qty = parse_positive_int(request.form.get(f"item_{item['item_id']}", "0"))
    if qty is None:
        ...
    if qty > 0:
        selected_items.append((item, qty))</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לבניית הרשימה.</p>
        </article>

        <article class="unit-section" id="unit-app-shortage-detection">
          <h3>יחידה רעיונית: בדיקת חוסרים במלאי</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי שנבנתה רשימת הפריטים המבוקשים, צריך לבדוק אם יש מספיק מלאי לכל אחד מהם.
          </div>
          <pre class="code-block"><code>shortages = []
for item, qty in selected_items:
    if qty > item["current_qty"]:
        shortages.append(
            f"{item['item_name']} חסר במלאי. ביקשת {qty} ויש רק {item['current_qty']}."
        )</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי על איסוף כל החוסרים ביחד.</p>
        </article>

        <article class="unit-section" id="unit-app-approve-order">
          <h3>יחידה רעיונית: אישור הזמנה והפחתת מלאי</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            רק אחרי שמנהל מאשר הזמנה בפועל, המערכת מפחיתה מלאי.
          </div>
          <pre class="code-block"><code>for item in items:
    run_db(
        "UPDATE inventory_items SET current_qty = current_qty - ? WHERE item_id = ?",
        (item["requested_qty"], item["item_id"]),
    )</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי על המשמעות העסקית של ההפחתה.</p>
        </article>

        <article class="unit-section" id="unit-app-reject-return-block">
          <h3>יחידה רעיונית: דחיית החזרה ויצירת חסימה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אם יש בעיה בהחזרה, המערכת לא רק דוחה אותה אלא גם חוסמת פעולה עתידית לצוות.
          </div>
          <pre class="code-block"><code>run_db(
    """
    INSERT INTO team_action_blocks (team_id, action_id, return_id, blocked_by, created_at, reason)
    VALUES (?, ?, ?, ?, ?, ?)
    ON CONFLICT(team_id, action_id) DO UPDATE SET
        return_id = excluded.return_id,
        blocked_by = excluded.blocked_by,
        created_at = excluded.created_at,
        reason = excluded.reason
    """,
    (...),
)</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי על יצירת או עדכון חסימה לצוות.</p>
        </article>
      </section>

      <section class="section" id="file-templates-login-html">
        <h2>קובץ: templates/login.html</h2>
        <p>כאן יבוא הסבר על תפקיד המסך.</p>

        <article class="unit-section" id="unit-login-form-structure">
          <h3>יחידה רעיונית: מבנה הטופס</h3>
          <pre class="code-block"><code>&lt;form method="post"&gt;
  ...
&lt;/form&gt;</code></pre>
          <p>כאן יבוא הסבר על מבנה הטופס.</p>
        </article>

        <article class="unit-section" id="unit-login-inputs">
          <h3>יחידה רעיונית: שדות הקלט</h3>
          <pre class="code-block"><code>&lt;input name="username"&gt;
&lt;input name="password" type="password"&gt;</code></pre>
          <p>כאן יבוא הסבר על השדות.</p>
        </article>

        <article class="unit-section" id="unit-login-submit">
          <h3>יחידה רעיונית: כפתור השליחה</h3>
          <pre class="code-block"><code>&lt;button type="submit"&gt;התחבר&lt;/button&gt;</code></pre>
          <p>כאן יבוא הסבר על פעולת השליחה.</p>
        </article>
      </section>

      <section class="section" id="file-static-style-css">
        <h2>קובץ: static/style.css</h2>
        <p>כאן יבוא הסבר על תפקיד קובץ העיצוב.</p>

        <article class="unit-section" id="unit-style-root-vars">
          <h3>יחידה רעיונית: משתני root</h3>
          <pre class="code-block"><code>:root {
  --bg: ...;
  --panel: ...;
}</code></pre>
          <p>כאן יבוא הסבר על משתני הצבעים והעיצוב.</p>
        </article>

        <article class="unit-section" id="unit-style-layout">
          <h3>יחידה רעיונית: מבנה layout</h3>
          <pre class="code-block"><code>.wrap {
  display: grid;
  grid-template-columns: ...;
}</code></pre>
          <p>כאן יבוא הסבר על מבנה העמוד.</p>
        </article>

        <article class="unit-section" id="unit-style-sidebar">
          <h3>יחידה רעיונית: עיצוב sidebar</h3>
          <pre class="code-block"><code>.side {
  position: sticky;
  ...
}</code></pre>
          <p>כאן יבוא הסבר על הניווט הצדדי.</p>
        </article>

        <article class="unit-section" id="unit-style-cards-tables">
          <h3>יחידה רעיונית: כרטיסים וטבלאות</h3>
          <pre class="code-block"><code>.card { ... }
table { ... }</code></pre>
          <p>כאן יבוא הסבר על כרטיסים, טבלאות ורכיבי תוכן.</p>
        </article>
      </section>

      <section class="section" id="questions">
        <h2>שאלות לבחינה</h2>

        <article class="question">
          <h3>שאלה 1 — זרימה</h3>
          <p>תסביר מה קורה כאשר משתמש נרשם למערכת.</p>
          <ul>
            <li>אילו שדות נאספים</li>
            <li>אילו בדיקות מתבצעות</li>
            <li>איך נשמר המשתמש</li>
            <li>למה הוא לא יכול להתחבר מיד</li>
          </ul>
        </article>

        <article class="question">
          <h3>שאלה 2 — לוגיקה</h3>
          <p>למה צריך לבדוק אם שם המשתמש כבר קיים במסד הנתונים?</p>
          <ul>
            <li>מה בודק ה-query</li>
            <li>מה המשמעות העסקית</li>
            <li>מה יקרה אם נוותר על הבדיקה</li>
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