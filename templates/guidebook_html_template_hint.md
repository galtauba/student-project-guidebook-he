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
      width: min(1750px, calc(100% - 40px));
      margin: 0 auto;
      display: grid;
      grid-template-columns: 360px 1fr;
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
          <a href="#unit-app-register-field-read">קריאת שדות בטופס הרשמה</a>
          <a href="#unit-app-register-validation">ולידציה של הרשמה</a>
          <a href="#unit-app-duplicate-username-check">בדיקת שם משתמש קיים</a>
          <a href="#unit-app-login-password-check">בדיקת סיסמה בהתחברות</a>
          <a href="#unit-app-build-selected-items">בניית selected_items</a>
          <a href="#unit-app-shortage-detection">בדיקת חוסרים במלאי</a>
          <a href="#unit-app-insert-order">יצירת רשומת הזמנה</a>
          <a href="#unit-app-insert-order-items">יצירת שורות הזמנה</a>
          <a href="#unit-app-approve-order">אישור הזמנה והפחתת מלאי</a>
          <a href="#unit-app-approve-return">אישור החזרה והחזרת מלאי</a>
          <a href="#unit-app-reject-return-block">דחיית החזרה ויצירת חסימה</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-templates-base-html">templates/base.html</a>
        <div class="toc-sub">
          <a href="#unit-base-head">head וקישור ל-CSS</a>
          <a href="#unit-base-topbar">ניווט עליון</a>
          <a href="#unit-base-flash">flash messages</a>
          <a href="#unit-base-content-block">בלוק התוכן הראשי</a>
          <a href="#unit-base-footer">footer</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-templates-login-html">templates/login.html</a>
        <div class="toc-sub">
          <a href="#unit-login-card-shell">מעטפת הכרטיס</a>
          <a href="#unit-login-form">טופס ההתחברות</a>
          <a href="#unit-login-fields">שדות username ו-password</a>
          <a href="#unit-login-submit">כפתור השליחה</a>
        </div>
      </div>

      <div class="toc-file">
        <a href="#file-static-style-css">static/style.css</a>
        <div class="toc-sub">
          <a href="#unit-style-root-vars">משתני root</a>
          <a href="#unit-style-base-body">עיצוב body ובסיס</a>
          <a href="#unit-style-layout-shell">מבנה layout</a>
          <a href="#unit-style-topbar-nav">topbar ו-nav</a>
          <a href="#unit-style-cards-tables">כרטיסים וטבלאות</a>
          <a href="#unit-style-forms-buttons">טפסים וכפתורים</a>
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
            לפני שכל route במערכת יוכל לשלוף או לעדכן נתונים, האפליקציה חייבת לדעת איך לפתוח חיבור למסד הנתונים.
          </div>
          <pre class="code-block"><code>BASE_DIR = os.path.abspath(os.path.dirname(__file__))
DATABASE_PATH = os.path.join(BASE_DIR, "instance", "scout_wms.db")

app = Flask(__name__)
app.config["SECRET_KEY"] = "change-this-secret-key"
app.config["DATABASE"] = DATABASE_PATH

def get_db():
    if "db" not in g:
        os.makedirs(os.path.dirname(app.config["DATABASE"]), exist_ok=True)
        g.db = sqlite3.connect(app.config["DATABASE"])
        g.db.row_factory = sqlite3.Row
        g.db.execute("PRAGMA foreign_keys = ON")
    return g.db</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-register-field-read">
          <h3>יחידה רעיונית: קריאת שדות בטופס הרשמה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            כאשר המשתמש שולח טופס הרשמה, צריך קודם למשוך את השדות מתוך request.form.
          </div>
          <pre class="code-block"><code>username = request.form.get("username", "").strip()
password = request.form.get("password", "").strip()
full_name = request.form.get("full_name", "").strip()
role = request.form.get("role", "user")
team_id = request.form.get("team_id") or None</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-register-validation">
          <h3>יחידה רעיונית: ולידציה של הרשמה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי קריאת השדות, צריך לוודא שלא חסר מידע חובה ושמשתמש רגיל אכן בחר צוות.
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
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-duplicate-username-check">
          <h3>יחידה רעיונית: בדיקת שם משתמש קיים</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            לפני יצירת משתמש חדש, המערכת חייבת לוודא שאין כבר משתמש עם אותו username.
          </div>
          <pre class="code-block"><code>if query_db("SELECT user_id FROM users WHERE username = ?", (username,), one=True):
    errors.append("שם המשתמש כבר קיים במערכת.")</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-login-password-check">
          <h3>יחידה רעיונית: בדיקת סיסמה בהתחברות</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי שליפת המשתמש לפי username, צריך לבדוק שהסיסמה שהוזנה מתאימה ל-hash השמור.
          </div>
          <pre class="code-block"><code>user = query_db("SELECT * FROM users WHERE username = ?", (username,), one=True)

if user is None or not check_password_hash(user["password_hash"], password):
    flash("שם המשתמש או הסיסמה שגויים.", "danger")
elif not user["is_approved"]:
    flash("החשבון עדיין ממתין לאישור מנהל.", "warning")
else:
    session.clear()
    session["user_id"] = user["user_id"]</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
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
        flash("יש להזין רק מספרים תקינים.", "danger")
        return render_template("new_order.html", actions=actions, items=items)
    if qty > 0:
        selected_items.append((item, qty))</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
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
        )

if shortages:
    return render_template("rejection.html", title="ההזמנה נדחתה", reasons=shortages)</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-insert-order">
          <h3>יחידה רעיונית: יצירת רשומת הזמנה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי שכל הבדיקות עברו, אפשר ליצור את רשומת ההזמנה הראשית בטבלת orders.
          </div>
          <pre class="code-block"><code>created_at = datetime.now().strftime("%Y-%m-%d %H:%M")
cursor = run_db(
    """
    INSERT INTO orders (team_id, action_id, created_by_user_id, created_at, status, approved_by, approved_at, rejection_reason)
    VALUES (?, ?, ?, ?, ?, ?, ?, ?)
    """,
    (g.user["team_id"], action_id, g.user["user_id"], created_at, "pending", None, None, None),
)
order_id = cursor.lastrowid</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-insert-order-items">
          <h3>יחידה רעיונית: יצירת שורות הזמנה</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            אחרי שיש order_id להזמנה הראשית, צריך לשמור את כל הפריטים והכמויות שהוזמנו.
          </div>
          <pre class="code-block"><code>for item, qty in selected_items:
    run_db(
        "INSERT INTO order_items (order_id, item_id, requested_qty) VALUES (?, ?, ?)",
        (order_id, item["item_id"], qty),
    )</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-approve-order">
          <h3>יחידה רעיונית: אישור הזמנה והפחתת מלאי</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            רק אחרי שמנהל מאשר הזמנה בפועל, המערכת מפחיתה מלאי.
          </div>
          <pre class="code-block"><code>shortages = []
for item in items:
    if item["requested_qty"] > item["current_qty"]:
        shortages.append(f"{item['item_name']} לא זמין בכמות המבוקשת.")

if shortages:
    reason = " ; ".join(shortages)
    run_db(
        """
        UPDATE orders
        SET status = 'rejected', approved_by = ?, approved_at = ?, rejection_reason = ?
        WHERE order_id = ?
        """,
        (g.user["user_id"], datetime.now().strftime("%Y-%m-%d %H:%M"), reason, order_id),
    )

for item in items:
    run_db(
        "UPDATE inventory_items SET current_qty = current_qty - ? WHERE item_id = ?",
        (item["requested_qty"], item["item_id"]),
    )</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>

        <article class="unit-section" id="unit-app-approve-return">
          <h3>יחידה רעיונית: אישור החזרה והחזרת מלאי</h3>
          <div class="context-box">
            <strong>הקשר:</strong>
            כאשר המנהל בודק החזרה תקינה, המערכת צריכה להחזיר את הכמויות למלאי ולעדכן את סטטוס ההחזרה.
          </div>
          <pre class="code-block"><code>original_by_item = {row["item_id"]: row["requested_qty"] for row in original_items}
missing_items = []

for row in returned_items:
    requested_qty = original_by_item.get(row["item_id"], 0)
    returned_qty = row["returned_qty"]
    if returned_qty < requested_qty:
        missing_items.append((row["item_name"], requested_qty - returned_qty))

if missing_items:
    flash("נמצא חוסר בהחזרה. יש לדחות את ההחזרה ולבחור פעולה לחסימה.", "warning")
    return redirect(url_for("admin_returns"))

add_returned_items_back_to_inventory(return_id)</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
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
    (
        order_data["team_id"],
        blocked_action_id,
        return_id,
        g.user["user_id"],
        datetime.now().strftime("%Y-%m-%d %H:%M"),
        reason,
    ),
)</code></pre>
          <p><strong>איך זה עובד:</strong> כאן יבוא הסבר ספציפי לקטע.</p>
        </article>
      </section>

      <section class="section" id="file-templates-base-html">
        <h2>קובץ: templates/base.html</h2>
        <p>כאן יבוא הסבר על תפקיד תבנית האב.</p>

        <article class="unit-section" id="unit-base-head">
          <h3>יחידה רעיונית: head וקישור ל-CSS</h3>
          <pre class="code-block"><code>&lt;head&gt;
    &lt;meta charset="utf-8"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1"&gt;
    &lt;title&gt;{% block title %}מערכת מחסן{% endblock %}&lt;/title&gt;
    &lt;link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}"&gt;
&lt;/head&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-base-topbar">
          <h3>יחידה רעיונית: ניווט עליון</h3>
          <pre class="code-block"><code>&lt;header class="topbar"&gt;
    ...
&lt;/header&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-base-flash">
          <h3>יחידה רעיונית: flash messages</h3>
          <pre class="code-block"><code>{% with messages = get_flashed_messages(with_categories=true) %}
    ...
{% endwith %}</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-base-content-block">
          <h3>יחידה רעיונית: בלוק התוכן הראשי</h3>
          <pre class="code-block"><code>{% block content %}{% endblock %}</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-base-footer">
          <h3>יחידה רעיונית: footer</h3>
          <pre class="code-block"><code>&lt;footer class="footer"&gt;פרויקט Flask לימודי ברמת תיכון&lt;/footer&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>
      </section>

      <section class="section" id="file-templates-login-html">
        <h2>קובץ: templates/login.html</h2>
        <p>כאן יבוא הסבר על תפקיד מסך ההתחברות.</p>

        <article class="unit-section" id="unit-login-card-shell">
          <h3>יחידה רעיונית: מעטפת הכרטיס</h3>
          <pre class="code-block"><code>&lt;div class="card" style="max-width: 520px; margin: 0 auto;"&gt;
    ...
&lt;/div&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-login-form">
          <h3>יחידה רעיונית: טופס ההתחברות</h3>
          <pre class="code-block"><code>&lt;form method="post"&gt;
    ...
&lt;/form&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-login-fields">
          <h3>יחידה רעיונית: שדות username ו-password</h3>
          <pre class="code-block"><code>&lt;label&gt;שם משתמש&lt;input type="text" name="username" required&gt;&lt;/label&gt;
&lt;label&gt;סיסמה&lt;input type="password" name="password" required&gt;&lt;/label&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-login-submit">
          <h3>יחידה רעיונית: כפתור השליחה</h3>
          <pre class="code-block"><code>&lt;button type="submit"&gt;להתחבר&lt;/button&gt;</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>
      </section>

      <section class="section" id="file-static-style-css">
        <h2>קובץ: static/style.css</h2>
        <p>כאן יבוא הסבר על תפקיד קובץ העיצוב.</p>

        <article class="unit-section" id="unit-style-root-vars">
          <h3>יחידה רעיונית: משתני root</h3>
          <pre class="code-block"><code>:root {
  --bg: ...;
  --surface: ...;
  --text: ...;
}</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-style-base-body">
          <h3>יחידה רעיונית: עיצוב body ובסיס</h3>
          <pre class="code-block"><code>body {
  margin: 0;
  font-family: ...;
  direction: rtl;
  background: ...;
  color: ...;
}</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-style-layout-shell">
          <h3>יחידה רעיונית: מבנה layout</h3>
          <pre class="code-block"><code>.container { ... }
.page { ... }
.two-columns { ... }</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-style-topbar-nav">
          <h3>יחידה רעיונית: topbar ו-nav</h3>
          <pre class="code-block"><code>.topbar { ... }
.topbar-inner { ... }
.nav { ... }
.nav a { ... }</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-style-cards-tables">
          <h3>יחידה רעיונית: כרטיסים וטבלאות</h3>
          <pre class="code-block"><code>.card { ... }
.stat { ... }
table { ... }
th, td { ... }</code></pre>
          <p>כאן יבוא הסבר.</p>
        </article>

        <article class="unit-section" id="unit-style-forms-buttons">
          <h3>יחידה רעיונית: טפסים וכפתורים</h3>
          <pre class="code-block"><code>form { ... }
input, select, textarea, button { ... }
.button { ... }
.button-danger { ... }</code></pre>
          <p>כאן יבוא הסבר.</p>
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