<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>BTEC - منصة مهندس بهاء</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">

  <style>
    :root{
      --card:#ffffff; --text:#101828; --muted:#667085;
      --primary:#0d39ff; --primary2:#000000;
      --line:#e6e9f5; --soft:#f5f7ff;
      --shadow: 0 18px 45px rgba(0,0,0,.22);
      --shadow2: 0 10px 25px rgba(0,0,0,.18);
      --r:16px;
    }
    *{box-sizing:border-box}
    body{
      margin:0; font-family:"Tajawal",system-ui,Arial;
      background: linear-gradient(135deg, #000 0%, #1a1a2e 100%);
      color:#fff; min-height:100vh;
    }
    .topbar{
      position:sticky; top:0; z-index:50;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary2) 100%);
      box-shadow: var(--shadow2);
    }
    .topbar .inner{
      max-width:1100px; margin:0 auto; padding:12px 14px;
      display:flex; align-items:center; justify-content:space-between; gap:12px;
    }
    .brand{display:flex; flex-direction:column; gap:2px; text-decoration:none; color:#fff;}
    .brand b{font-size:16px}
    .brand span{font-size:12px; opacity:.9}
    .nav{display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
    .btn{
      border:0; cursor:pointer; font-family:inherit;
      padding:10px 12px; border-radius:12px;
      background:#fff; color:var(--primary);
      font-weight:800; transition:.15s transform ease, .15s opacity ease;
    }
    .btn:hover{transform: translateY(-1px); opacity:.95}
    .btn.ghost{
      background: rgba(255,255,255,.14);
      color:#fff; border:1px solid rgba(255,255,255,.22);
    }
    .btn.danger{background: #ffe4e2; color:#b42318}
    .btn.ok{background: #d1fadf; color:#027a48}
    .btn.dark{background:#101828; color:#fff}
    .btn.small{padding:8px 10px; border-radius:10px; font-weight:800; font-size:13px}
    .hide{display:none !important}

    .wrap{max-width:1100px; margin:18px auto; padding:0 14px}
    .grid{display:grid; grid-template-columns: repeat(auto-fit,minmax(280px,1fr)); gap:14px}
    .card{
      background: var(--card); color: var(--text);
      border-radius: var(--r); box-shadow: var(--shadow);
      padding:16px; overflow:hidden;
    }
    .card.soft{background:#fbfcff}
    .cardHeader{
      display:flex; align-items:flex-start; justify-content:space-between; gap:10px;
      border-bottom:1px solid var(--line); padding-bottom:12px; margin-bottom:12px;
    }
    .h1{margin:0; font-size:26px; font-weight:900; color:var(--primary)}
    .h2{margin:0; font-size:18px; font-weight:900}
    .muted{color:var(--muted); font-size:14px}
    .pill{
      display:inline-flex; align-items:center; gap:6px;
      padding:6px 10px; border-radius:999px;
      font-size:12px; font-weight:800;
      background: var(--soft); color: var(--primary);
      border:1px solid var(--line);
    }
    .row{display:flex; gap:10px; flex-wrap:wrap; align-items:center}
    .list{display:flex; flex-direction:column; gap:10px}
    .item{
      padding:12px; border-radius:14px;
      background: var(--soft); border:1px solid var(--line);
      display:flex; justify-content:space-between; align-items:center; gap:10px;
    }
    .item:hover{border-color:#b9c4ff}
    .item .title{font-weight:900}
    .item .sub{font-size:13px; color:var(--muted); margin-top:2px}
    .item .meta{display:flex; gap:8px; align-items:center; flex-wrap:wrap}

    .form{display:flex; flex-direction:column; gap:10px}
    label{font-size:13px; font-weight:900; color:#344054}
    input, textarea, select{
      width:100%; padding:10px 12px;
      border-radius:12px; border:1px solid #d0d5dd;
      font-family:inherit; outline:none; background:#fff;
    }
    textarea{min-height:120px; resize:vertical}
    input:focus, textarea:focus, select:focus{border-color:#98a6ff; box-shadow: 0 0 0 4px rgba(13,57,255,.12)}
    .help{font-size:12px; color:var(--muted)}
    .split{display:grid; grid-template-columns:1fr 1fr; gap:10px}
    @media (max-width:720px){ .split{grid-template-columns:1fr} }

    .alert{
      padding:10px 12px; border-radius:12px;
      border:1px solid var(--line);
      background:#fff; color:#111;
      display:flex; justify-content:space-between; align-items:center; gap:10px;
    }
    .alert.ok{border-color:#abefc6; background:#ecfdf3}
    .alert.bad{border-color:#fecdca; background:#fffbfa}
    .alert.warn{border-color:#fedf89; background:#fffaeb}

    .lessonWrap{background:#fff;color:#111;border-radius:18px;overflow:hidden;box-shadow:var(--shadow)}
    .lessonHeader{background: linear-gradient(135deg, var(--primary) 0%, #000 100%);color:#fff;padding:20px;}
    .lessonTitle{margin:8px 0 0; font-size:26px; font-weight:1000}
    .lessonBody{padding:18px; line-height:1.95}
    .slide{border:1px solid var(--line);background:#fbfcff;border-radius:16px;padding:14px;margin-bottom:12px;}
    .slide h3{margin:0 0 8px;color:var(--primary)}
    .slide ul{margin:0; padding-right:18px}
    .slide pre{background:#111827;color:#d1fae5;padding:12px;border-radius:14px;overflow:auto;direction:ltr;text-align:left;margin:10px 0 0;}

    .footer{margin:20px 0 30px;text-align:center;opacity:.9;font-size:13px;}
    .mono{font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;}
  </style>
</head>

<body>
  <div class="topbar">
    <div class="inner">
      <a class="brand" href="#/">
        <b>(BTEC) منصة مهندس بهاء حجيج</b>
        <span>أجيال + مهمات + مستندات • ودروس Python برسنتيشن</span>
      </a>

      <div class="nav">
        <button class="btn ghost" onclick="go('#/')">الرئيسية</button>
        <button class="btn ghost" onclick="go('#/python')">دروس بايثون</button>
        <button class="btn ghost" onclick="go('#/search')">بحث</button>
        <button class="btn ghost" onclick="go('#/login')" id="loginBtn">دخول</button>
        <button class="btn ghost hide" onclick="go('#/admin')" id="adminBtn">لوحة التحكم</button>
        <button class="btn danger small hide" onclick="logout()" id="logoutBtn">خروج</button>
      </div>
    </div>
  </div>

  <div class="wrap">
    <div id="alertBox" class="alert hide"></div>

    <div id="page-home" class="grid hide"></div>
    <div id="page-python" class="hide"></div>
    <div id="page-python-lesson" class="hide"></div>

    <div id="page-search" class="hide"></div>
    <div id="page-login" class="hide"></div>
    <div id="page-admin" class="hide"></div>

    <div class="footer">© منصة BTEC – إعداد مهندس بهاء | Instagram: <b>btec_zone.2_008</b></div>
  </div>

<script>
/* ============================================================================
  ✅ ملف واحد فقط (Static)
  ✅ بدون Firestore وبدون سيرفر

  مهم جدًا:
  - أي تعديل يعمل عليه الأدمن داخل الموقع هو "مسودة محلية" على جهازه.
  - حتى يشوفه كل الطلاب: الأدمن يضغط (تصدير JSON) وينسخه
    ثم يلصقه داخل INITIAL_DATA بالأسفل ويرفع index.html على GitHub.
============================================================================ */

/* ====== 1) بيانات الأدمن الثابتة ====== */
const ADMIN_EMAIL = "bahaahajaj@btec.com";
const ADMIN_PASSWORD = "bahaahajaj0775135361btec2007";

/* ====== 2) هنا مكان بيانات الموقع التي ستظهر للطلاب على GitHub ======
   الأدمن: بعد ما يضيف دروس من لوحة التحكم → اضغط "تصدير JSON"
   وانسخ الناتج ثم الصقه مكان INITIAL_DATA بالكامل (بين الأقواس).
*/
const INITIAL_DATA = {
  "pythonLessons": [
    {
      "id": "py_demo_1",
      "title": "الدرس 1 - مقدمة بايثون",
      "createdAt": Date.now(),
      "slides": [
        { "title":"ما هي بايثون؟", "bullets":["لغة برمجة سهلة","تستخدم للويب والذكاء الاصطناعي"], "code":"print('Hello Python')" },
        { "title":"تثبيت بايثون", "bullets":["نثبت Python","نثبت VS Code"], "code":"python --version" }
      ]
    },
    {
      "id": "py_demo_2",
      "title": "الدرس 2 - المتغيرات",
      "createdAt": Date.now(),
      "slides": [
        { "title":"المتغير", "bullets":["مكان نخزن فيه قيمة"], "code":"name = 'Ali'\\nage = 15\\nprint(name, age)" }
      ]
    }
  ]
};

/* ====== تخزين محلي ====== */
const LS_DB = "btec_db_v1";
const LS_SESSION = "btec_session_v1";
const LS_DEVICE = "btec_device_v1";
const LS_PROGRESS = "btec_progress_v1";

/* ---------- Utilities ---------- */
const $ = (sel) => document.querySelector(sel);
const esc = (s="") => String(s)
  .replaceAll("&","&amp;").replaceAll("<","&lt;")
  .replaceAll(">","&gt;").replaceAll('"',"&quot;")
  .replaceAll("'","&#039;");

function uid(prefix="id"){
  return prefix + "_" + Math.random().toString(16).slice(2) + Date.now().toString(16);
}

function showAlert(type, msg){
  const box = $("#alertBox");
  box.className = "alert " + (type || "");
  box.innerHTML = `<div><b>${type==="ok"?"✅":"⚠️"}</b> ${esc(msg)}</div>
                   <button class="btn small dark" onclick="hideAlert()">إغلاق</button>`;
  box.classList.remove("hide");
}
function hideAlert(){ $("#alertBox").classList.add("hide"); }
function go(hash){ location.hash = hash; }

/* ---------- Device id ---------- */
function getDeviceId(){
  let d = localStorage.getItem(LS_DEVICE);
  if(!d){
    d = "dev_" + Math.random().toString(16).slice(2) + "_" + Date.now().toString(16);
    localStorage.setItem(LS_DEVICE, d);
  }
  return d;
}

/* ---------- Session ---------- */
function getSession(){
  try{ return JSON.parse(localStorage.getItem(LS_SESSION) || "null"); }
  catch{ return null; }
}
function setSession(s){
  localStorage.setItem(LS_SESSION, JSON.stringify(s));
  renderNav();
}
function logout(){
  localStorage.removeItem(LS_SESSION);
  renderNav();
  showAlert("ok","تم تسجيل الخروج");
  go("#/");
}

/* ---------- Progress (آخر درس) ---------- */
function loadProgress(){
  try{ return JSON.parse(localStorage.getItem(LS_PROGRESS) || "{}"); }
  catch{ return {}; }
}
function saveProgress(p){ localStorage.setItem(LS_PROGRESS, JSON.stringify(p)); }
function setUserLast(type, id){
  const s = getSession();
  if(!s) return;
  const p = loadProgress();
  p[s.key] = { type, id, updatedAt: Date.now() };
  saveProgress(p);
}
function getUserLast(){
  const s = getSession();
  if(!s) return null;
  const p = loadProgress();
  return p[s.key] || null;
}

/* ---------- DB ---------- */
function normalizeU(u){ return (u||"").trim().toLowerCase(); }

function seedData(){
  return {
    pythonLessons: Array.isArray(INITIAL_DATA.pythonLessons) ? INITIAL_DATA.pythonLessons : []
  };
}

function loadDB(){
  const raw = localStorage.getItem(LS_DB);
  if(!raw){
    const d = seedData();
    localStorage.setItem(LS_DB, JSON.stringify(d));
    return d;
  }
  try{
    const d = JSON.parse(raw);
    if(!d.pythonLessons) throw new Error("bad");
    return d;
  }catch{
    const d = seedData();
    localStorage.setItem(LS_DB, JSON.stringify(d));
    return d;
  }
}

function saveDB(db){ localStorage.setItem(LS_DB, JSON.stringify(db)); }

function pythonLessonsSorted(db){
  return db.pythonLessons.slice().sort((a,b)=> (b.createdAt||0)-(a.createdAt||0));
}

/* ---------- Admin? ---------- */
function isAdmin(){
  const s = getSession();
  return !!s && s.role === "admin";
}

/* ---------- Nav ---------- */
function renderNav(){
  const s = getSession();
  const authed = !!s;
  $("#loginBtn").classList.toggle("hide", authed);
  $("#logoutBtn").classList.toggle("hide", !authed);
  $("#adminBtn").classList.toggle("hide", !isAdmin());
}

/* ---------- Router ---------- */
function hideAllPages(){
  ["home","python","python-lesson","search","login","admin"].forEach(p=>{
    $("#page-"+p).classList.add("hide");
  });
}

function route(){
  hideAlert();
  hideAllPages();

  const hash = location.hash || "#/";
  const parts = hash.replace("#","").split("/").filter(Boolean);
  if(parts.length === 0) return renderHome();

  const [p, id] = parts;
  if(p === "python") return renderPython();
  if(p === "pythonLesson" && id) return renderPythonLesson(id);
  if(p === "search") return renderSearch();
  if(p === "login") return renderLogin();
  if(p === "admin") return renderAdmin();
  return renderHome();
}

/* ===================== Pages ===================== */

/* ---------- HOME ---------- */
function renderHome(){
  const db = loadDB();
  const root = $("#page-home");
  root.classList.remove("hide");

  const last = getUserLast();
  let lastHtml = `<div class="muted">سجّل دخول حتى نحفظ آخر درس فتحته على هذا الجهاز.</div>`;
  if(last && last.type === "python"){
    lastHtml = `
      <div class="alert ok">
        <div><b>أكمل من حيث توقفت:</b> آخر درس بايثون فتحته</div>
        <button class="btn small" onclick="go('#/pythonLesson/${esc(last.id)}')">متابعة</button>
      </div>
    `;
  }

  const py = pythonLessonsSorted(db).slice(0,5);

  root.innerHTML = `
    <div class="card" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">الرئيسية</h1>
          <div class="muted">دروس بايثون تظهر للطلاب مباشرة بعد تحديث ملف GitHub.</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/python')">دروس بايثون</button>
        </div>
      </div>
      ${lastHtml}
    </div>

    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">أحدث دروس بايثون</div>
          <div class="muted">الدروس على شكل شرائح (Presentation).</div>
        </div>
      </div>

      <div class="list">
        ${
          py.length ? py.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">${new Date(l.createdAt||Date.now()).toLocaleString("ar")}</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- PYTHON LIST ---------- */
function renderPython(){
  const db = loadDB();
  const root = $("#page-python");
  root.classList.remove("hide");

  const lessons = pythonLessonsSorted(db);

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">دروس بايثون</h1>
          <div class="muted">افتح أي درس. (الدروس تظهر بعد تحديث GitHub)</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="list">
        ${
          lessons.length ? lessons.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">${new Date(l.createdAt||Date.now()).toLocaleString("ar")}</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- PYTHON LESSON VIEW ---------- */
function renderPythonLesson(id){
  const db = loadDB();
  const lesson = db.pythonLessons.find(x => x.id === id);

  if(!lesson){
    showAlert("bad","الدرس غير موجود");
    return go("#/python");
  }

  setUserLast("python", id);

  const root = $("#page-python-lesson");
  root.classList.remove("hide");

  const slides = Array.isArray(lesson.slides) ? lesson.slides : [];

  root.innerHTML = `
    <div class="lessonWrap">
      <div class="lessonHeader">
        <div class="row" style="justify-content:space-between">
          <div>
            <div style="font-weight:900;opacity:.95">بسم الله الرحمن الرحيم</div>
            <div class="lessonTitle">${esc(lesson.title||"")}</div>
          </div>
          <div class="row">
            <button class="btn ghost" onclick="go('#/python')">رجوع</button>
            <button class="btn ghost" onclick="go('#/')">الرئيسية</button>
          </div>
        </div>
      </div>

      <div class="lessonBody">
        ${
          slides.length ? slides.map((s,idx)=>`
            <div class="slide">
              <h3>${idx+1}. ${esc(s.title || "شريحة")}</h3>
              ${
                (s.bullets||[]).length
                  ? `<ul>${(s.bullets||[]).map(b=>`<li>${esc(b)}</li>`).join("")}</ul>`
                  : `<div class="muted">—</div>`
              }
              ${s.code ? `<pre>${esc(s.code)}</pre>` : ``}
            </div>
          `).join("") : `<div class="muted">لا يوجد شرائح بعد.</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- SEARCH ---------- */
function renderSearch(){
  const root = $("#page-search");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">بحث</h1>
          <div class="muted">بحث داخل عناوين الدروس والشرائح والكود.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="form">
        <label>اكتب كلمة البحث</label>
        <input id="q" placeholder="مثال: متغيرات / print / loops" oninput="doSearch()">
      </div>

      <div id="searchResults" class="grid" style="margin-top:14px"></div>
    </div>
  `;
  doSearch();
}

function doSearch(){
  const db = loadDB();
  const q = ($("#q")?.value || "").trim().toLowerCase();
  const out = $("#searchResults");
  if(!out) return;

  if(!q){
    out.innerHTML = `<div class="card soft" style="grid-column:1/-1"><div class="muted">اكتب كلمة للبحث…</div></div>`;
    return;
  }

  const match = (s)=> (s||"").toLowerCase().includes(q);

  const lessons = db.pythonLessons.filter(l=>{
    if(match(l.title)) return true;
    return (l.slides||[]).some(s=> match(s.title) || (s.bullets||[]).some(b=>match(b)) || match(s.code));
  });

  out.innerHTML = `
    <div class="card soft" style="grid-column:1/-1">
      <div class="cardHeader">
        <div class="h2">نتائج البحث (دروس بايثون)</div>
        <span class="pill">${lessons.length}</span>
      </div>
      <div class="list">
        ${
          lessons.length ? lessons.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">درس برسنتيشن</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا نتائج</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- LOGIN (Admin + Student local) ---------- */
function renderLogin(){
  const root = $("#page-login");
  root.classList.remove("hide");

  const deviceId = getDeviceId();
  const short = deviceId.split("_").slice(-1)[0].slice(-4);
  const suggested = "student_" + short;

  root.innerHTML = `
    <div class="card" style="max-width:560px;margin:0 auto;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">تسجيل الدخول</h1>
          <div class="muted">
            الأدمن يدخل بالإيميل والباسورد.
            الطالب يقدر يدخل بأي بيانات (وتنحفظ على نفس الجهاز).
          </div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="alert warn">
        <div>
          <b>الأدمن:</b> ${esc(ADMIN_EMAIL)}
          <div class="muted">ملاحظة: هذا نظام بسيط داخل ملف واحد (غير آمن 100%).</div>
        </div>
      </div>

      <form class="form" onsubmit="event.preventDefault(); doAuth();">
        <label> <input type="checkbox" id="asAdmin"> دخول كأدمن </label>

        <label>الإيميل / اليوزر</label>
        <input id="userKey" placeholder="مثال: ${esc(suggested)} أو student@gmail.com" value="${esc(suggested)}" required>

        <label>كلمة المرور</label>
        <input id="pass" type="password" placeholder="اكتب كلمة مرور" required>

        <button class="btn" type="submit">متابعة</button>

        <div class="help">
          الطالب: اكتب أي بيانات تريدها، واحفظها — حتى ترجع لنفس آخر درس.
        </div>
      </form>
    </div>
  `;
}

function doAuth(){
  const asAdmin = $("#asAdmin").checked;
  const key = ($("#userKey").value || "").trim();
  const pass = ($("#pass").value || "").trim();

  if(asAdmin){
    if(normalizeU(key) === normalizeU(ADMIN_EMAIL) && pass === ADMIN_PASSWORD){
      setSession({ role:"admin", key:"admin" });
      showAlert("ok","تم تسجيل الدخول كأدمن ✅");
      go("#/admin");
    }else{
      showAlert("bad","بيانات الأدمن غير صحيحة");
    }
    return;
  }

  // طالب: نخزن جلسة محلية بهذا الجهاز
  const deviceId = getDeviceId();
  const studentKey = "student:" + deviceId + ":" + normalizeU(key);

  // بسيط: نحفظ كلمة مرور الطالب في LocalStorage (على نفس الجهاز فقط)
  const storedPassKey = "btec_student_pass_" + studentKey;
  const saved = localStorage.getItem(storedPassKey);

  if(saved && saved !== pass){
    showAlert("bad","كلمة المرور غير صحيحة لهذا الحساب على هذا الجهاز.");
    return;
  }
  if(!saved){
    localStorage.setItem(storedPassKey, pass);
  }

  setSession({ role:"student", key: studentKey, display: key });
  showAlert("ok","تم تسجيل الدخول ✅");
  go("#/");
}

/* ---------- ADMIN ---------- */
let PY_DRAFT = [];

function requireAdminUI(){
  if(!isAdmin()){
    showAlert("bad","هذه الصفحة للأدمن فقط.");
    go("#/login");
    return false;
  }
  return true;
}

function renderAdmin(){
  if(!requireAdminUI()) return;

  const db = loadDB();
  const root = $("#page-admin");
  root.classList.remove("hide");

  const lessons = pythonLessonsSorted(db).slice(0,10);

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">لوحة التحكم (الأدمن)</h1>
          <div class="muted">أضف دروس بايثون كشرائح. ثم صدّر JSON والصقه داخل INITIAL_DATA وارفع الملف على GitHub.</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">عرض الموقع</button>
        </div>
      </div>

      <div class="alert ok">
        <div>
          <b>أنت أدمن ✅</b>
          <div class="muted">لجعل الدروس تظهر لكل الطلاب: استخدم (تصدير JSON) ثم حدث ملف GitHub.</div>
        </div>
      </div>
    </div>

    <div class="grid" style="margin-top:14px">
      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة درس بايثون (برسنتيشن)</div>
            <div class="muted">ضيف شرائح ثم احفظ الدرس محليًا، وبعدها صدّر JSON.</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); return false;">
          <label>عنوان الدرس</label>
          <input id="pyTitle" placeholder="مثال: الدرس 3 - شروط if" required>

          <div class="split">
            <div>
              <label>عنوان الشريحة</label>
              <input id="pySlideTitle" placeholder="مثال: ما هي if ؟">
            </div>
            <div>
              <label>كود (اختياري)</label>
              <input id="pySlideCodeOneLine" placeholder='مثال: x=5; print(x)'>
            </div>
          </div>

          <label>نقاط الشريحة (كل سطر نقطة)</label>
          <textarea id="pySlideBullets" placeholder="اكتب نقاط...\nكل سطر = نقطة"></textarea>

          <div class="row">
            <button class="btn dark" type="button" onclick="addSlideToDraft()">+ إضافة الشريحة إلى المسودة</button>
            <span class="pill" id="draftCount">0 شريحة</span>
            <button class="btn ok" type="button" onclick="savePythonLessonLocal()">حفظ الدرس (محلي)</button>
          </div>

          <div class="help">بعد ما تخلص: اضغط "تصدير JSON" وانسخه إلى INITIAL_DATA داخل الملف ثم ارفعه GitHub.</div>
          <div id="draftPreview" class="list" style="margin-top:10px"></div>
        </form>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">آخر الدروس</div>
            <div class="muted">تقدر تحذف أي درس.</div>
          </div>
          <div class="row">
            <button class="btn" onclick="exportJSON()">تصدير JSON</button>
            <button class="btn ghost dark" onclick="showImportBox()">استيراد JSON</button>
          </div>
        </div>

        <div id="importBox" class="hide" style="margin-bottom:12px">
          <div class="alert warn">
            <div>
              <b>استيراد JSON</b>
              <div class="muted">ألصق JSON الذي صدّرته سابقًا ثم اضغط استيراد.</div>
            </div>
          </div>
          <textarea id="importText" class="mono" placeholder='{"pythonLessons":[...]} أو [... ]'></textarea>
          <div class="row" style="margin-top:10px">
            <button class="btn ok" onclick="importJSON()">استيراد</button>
            <button class="btn danger" onclick="hideImportBox()">إلغاء</button>
          </div>
        </div>

        <div class="list">
          ${
            lessons.length ? lessons.map(l=>`
              <div class="item">
                <div>
                  <div class="title">${esc(l.title||"")}</div>
                  <div class="sub">${(l.slides||[]).length} شريحة • ${new Date(l.createdAt||Date.now()).toLocaleString("ar")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
                  <button class="btn small danger" onclick="deleteLessonLocal('${l.id}')">حذف</button>
                </div>
              </div>
            `).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
          }
        </div>
      </div>
    </div>

    <div id="exportBox" class="card soft hide" style="margin-top:14px">
      <div class="cardHeader">
        <div>
          <div class="h2">JSON جاهز للنسخ</div>
          <div class="muted">انسخه والصقه داخل INITIAL_DATA في أعلى الملف، ثم ارفعه GitHub.</div>
        </div>
        <button class="btn danger small" onclick="hideExport()">إغلاق</button>
      </div>
      <textarea id="exportText" class="mono" style="min-height:260px"></textarea>
      <div class="row" style="margin-top:10px">
        <button class="btn ok" onclick="copyExport()">نسخ</button>
      </div>
    </div>
  `;

  resetDraftUI();
}

/* ----- Draft UI ----- */
function resetDraftUI(){
  PY_DRAFT = [];
  $("#draftCount").textContent = "0 شريحة";
  $("#draftPreview").innerHTML = "";
}
function addSlideToDraft(){
  const title = ($("#pySlideTitle").value||"").trim();
  const bulletsText = ($("#pySlideBullets").value||"").trim();
  const code = ($("#pySlideCodeOneLine").value||"").trim();

  if(!title){
    showAlert("bad","اكتب عنوان الشريحة");
    return;
  }

  const bullets = bulletsText ? bulletsText.split("\n").map(x=>x.trim()).filter(Boolean) : [];
  PY_DRAFT.push({ title, bullets, code });

  $("#pySlideTitle").value = "";
  $("#pySlideBullets").value = "";
  $("#pySlideCodeOneLine").value = "";
  renderDraftPreview();
}
function renderDraftPreview(){
  $("#draftCount").textContent = `${PY_DRAFT.length} شريحة`;
  $("#draftPreview").innerHTML = PY_DRAFT.map((s,idx)=>`
    <div class="item">
      <div>
        <div class="title">${idx+1}. ${esc(s.title)}</div>
        <div class="sub">${(s.bullets||[]).length} نقاط ${s.code ? "• مع كود" : ""}</div>
      </div>
      <div class="meta">
        <button class="btn small danger" type="button" onclick="removeDraftSlide(${idx})">حذف</button>
      </div>
    </div>
  `).join("");
}
function removeDraftSlide(i){
  PY_DRAFT.splice(i,1);
  renderDraftPreview();
}

/* ----- Save lesson local ----- */
function savePythonLessonLocal(){
  if(!requireAdminUI()) return;

  const title = ($("#pyTitle").value||"").trim();
  if(!title){ showAlert("bad","اكتب عنوان الدرس"); return; }
  if(PY_DRAFT.length === 0){ showAlert("bad","أضف على الأقل شريحة"); return; }

  const db = loadDB();
  db.pythonLessons.push({
    id: uid("py"),
    title,
    slides: PY_DRAFT.slice(),
    createdAt: Date.now()
  });
  saveDB(db);

  showAlert("ok","تم حفظ الدرس محليًا ✅ (الآن صدّر JSON وارفعه GitHub ليظهر للطلاب)");
  $("#pyTitle").value = "";
  resetDraftUI();
  renderAdmin();
}

function deleteLessonLocal(id){
  if(!requireAdminUI()) return;
  if(!confirm("حذف الدرس؟")) return;

  const db = loadDB();
  db.pythonLessons = db.pythonLessons.filter(x => x.id !== id);
  saveDB(db);

  showAlert("ok","تم حذف الدرس ✅");
  renderAdmin();
}

/* ----- Export / Import ----- */
function exportJSON(){
  if(!requireAdminUI()) return;
  const db = loadDB();

  const payload = {
    pythonLessons: pythonLessonsSorted(db).map(l => ({
      id: l.id,
      title: l.title,
      createdAt: l.createdAt || Date.now(),
      slides: (l.slides||[]).map(s => ({
        title: s.title || "",
        bullets: Array.isArray(s.bullets) ? s.bullets : [],
        code: s.code || ""
      }))
    }))
  };

  $("#exportText").value = JSON.stringify(payload, null, 2);
  $("#exportBox").classList.remove("hide");
  location.hash = "#/admin";
}
function hideExport(){ $("#exportBox").classList.add("hide"); }
async function copyExport(){
  try{
    await navigator.clipboard.writeText($("#exportText").value);
    showAlert("ok","تم النسخ ✅");
  }catch{
    showAlert("bad","انسخ يدويًا (Ctrl+C)");
  }
}

function showImportBox(){ $("#importBox").classList.remove("hide"); }
function hideImportBox(){ $("#importBox").classList.add("hide"); }

function importJSON(){
  if(!requireAdminUI()) return;
  const txt = ($("#importText").value||"").trim();
  if(!txt){ showAlert("bad","الصق JSON أولاً"); return; }

  try{
    const parsed = JSON.parse(txt);
    const payload = Array.isArray(parsed) ? { pythonLessons: parsed } : parsed;

    if(!payload || !Array.isArray(payload.pythonLessons)){
      showAlert("bad","JSON غير صحيح. لازم يحتوي pythonLessons");
      return;
    }

    const cleaned = payload.pythonLessons.map(l => ({
      id: l.id || uid("py"),
      title: l.title || "درس بدون عنوان",
      createdAt: l.createdAt || Date.now(),
      slides: Array.isArray(l.slides) ? l.slides.map(s => ({
        title: s.title || "",
        bullets: Array.isArray(s.bullets) ? s.bullets : [],
        code: s.code || ""
      })) : []
    }));

    const db = loadDB();
    db.pythonLessons = cleaned;
    saveDB(db);

    showAlert("ok","تم الاستيراد ✅");
    $("#importText").value = "";
    hideImportBox();
    renderAdmin();
  }catch(e){
    showAlert("bad","فشل الاستيراد: تأكد أن JSON صحيح.");
  }
}

/* ---------- Boot ---------- */
window.addEventListener("hashchange", route);
renderNav();
route();
</script>
</body>
</html>
