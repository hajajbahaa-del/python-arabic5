<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>منصة BTEC - مهندس بهاء حجيج</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap');

    :root{
      --bg:#0b1020;
      --card:#ffffff;
      --text:#101828;
      --muted:#667085;
      --primary:#0d39ff;
      --primary2:#000000;
      --line:#e6e9f5;
      --soft:#f5f7ff;
      --ok:#12b76a;
      --bad:#f04438;
      --warn:#f79009;
      --shadow: 0 18px 45px rgba(0,0,0,.22);
      --shadow2: 0 10px 25px rgba(0,0,0,.18);
      --r:16px;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:"Tajawal",system-ui,Arial;
      background: linear-gradient(135deg, #000 0%, #1a1a2e 100%);
      color:#fff;
      min-height:100vh;
    }

    /* top bar */
    .topbar{
      position:sticky; top:0; z-index:50;
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary2) 100%);
      box-shadow: var(--shadow2);
    }
    .topbar .inner{
      max-width:1100px; margin:0 auto; padding:12px 14px;
      display:flex; align-items:center; justify-content:space-between; gap:12px;
    }
    .brand{
      display:flex; flex-direction:column; gap:2px;
      text-decoration:none; color:#fff;
    }
    .brand b{font-size:16px}
    .brand span{font-size:12px; opacity:.9}
    .nav{display:flex; flex-wrap:wrap; gap:8px; align-items:center;}

    .btn{
      border:0; cursor:pointer; font-family:inherit;
      padding:10px 12px; border-radius:12px;
      background:#fff; color:var(--primary);
      font-weight:800;
      transition:.15s transform ease, .15s opacity ease;
    }
    .btn:hover{transform: translateY(-1px); opacity:.95}
    .btn.ghost{
      background: rgba(255,255,255,.14);
      color:#fff;
      border:1px solid rgba(255,255,255,.22);
    }
    .btn.danger{background: #ffe4e2; color:#b42318}
    .btn.ok{background: #d1fadf; color:#027a48}
    .btn.dark{background:#101828; color:#fff}
    .btn.small{padding:8px 10px; border-radius:10px; font-weight:800; font-size:13px}

    /* layout */
    .wrap{max-width:1100px; margin:18px auto; padding:0 14px}
    .grid{display:grid; grid-template-columns: repeat(auto-fit,minmax(280px,1fr)); gap:14px}
    .card{
      background: var(--card);
      color: var(--text);
      border-radius: var(--r);
      box-shadow: var(--shadow);
      padding:16px;
      overflow:hidden;
    }
    .card.soft{background: #fbfcff}
    .cardHeader{
      display:flex; align-items:flex-start; justify-content:space-between; gap:10px;
      border-bottom:1px solid var(--line);
      padding-bottom:12px; margin-bottom:12px;
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

    /* list items */
    .list{display:flex; flex-direction:column; gap:10px}
    .item{
      padding:12px; border-radius:14px;
      background: var(--soft);
      border:1px solid var(--line);
      display:flex; justify-content:space-between; align-items:center; gap:10px;
    }
    .item:hover{border-color: #b9c4ff}
    .item .title{font-weight:900}
    .item .sub{font-size:13px; color:var(--muted); margin-top:2px}
    .item .meta{display:flex; gap:8px; align-items:center; flex-wrap:wrap}

    /* forms */
    .form{display:flex; flex-direction:column; gap:10px}
    label{font-size:13px; font-weight:900; color:#344054}
    input, textarea, select{
      width:100%;
      padding:10px 12px;
      border-radius:12px;
      border:1px solid #d0d5dd;
      font-family:inherit;
      outline:none;
      background:#fff;
    }
    textarea{min-height:120px; resize:vertical}
    input:focus, textarea:focus, select:focus{
      border-color:#98a6ff; box-shadow: 0 0 0 4px rgba(13,57,255,.12)
    }
    .help{font-size:12px; color:var(--muted)}
    .split{display:grid; grid-template-columns:1fr 1fr; gap:10px}
    @media (max-width: 720px){ .split{grid-template-columns:1fr} }

    /* lesson page */
    .lessonWrap{
      background:#fff; color:#111;
      border-radius: 18px; overflow:hidden;
      box-shadow: var(--shadow);
    }
    .lessonHeader{
      background: linear-gradient(135deg, var(--primary) 0%, #000 100%);
      color:#fff;
      padding:20px;
    }
    .bismillah{font-weight:900; font-size:18px; opacity:.95}
    .lessonTitle{margin:8px 0 0; font-size:26px; font-weight:1000}
    .lessonBody{padding:18px; line-height:1.95}
    .lessonBody pre{
      background:#111827; color:#d1fae5;
      padding:12px; border-radius:14px;
      overflow:auto; direction:ltr; text-align:left;
    }
    .lessonBody code{
      background:#111827; color:#d1fae5;
      padding:2px 6px; border-radius:8px;
      direction:ltr;
    }

    /* alerts */
    .alert{
      padding:10px 12px; border-radius:12px;
      border:1px solid var(--line);
      background:#fff; color:#111;
      display:flex; justify-content:space-between; align-items:center; gap:10px;
    }
    .alert.ok{border-color:#abefc6; background:#ecfdf3}
    .alert.bad{border-color:#fecdca; background:#fffbfa}
    .alert.warn{border-color:#fedf89; background:#fffaeb}
    .hide{display:none !important}

    /* footer */
    .footer{
      margin:20px 0 30px;
      text-align:center;
      opacity:.9;
      font-size:13px;
    }
  </style>
</head>

<body>

  <div class="topbar">
    <div class="inner">
      <a class="brand" href="#/">
        <b>(BTEC) منصة مهندس بهاء حجيج</b>
        <span>أجيال 2008 / 2009 / 2010 • مهام + مستندات + دروس يومية</span>
      </a>

      <div class="nav">
        <button class="btn ghost" onclick="go('#/')">الرئيسية</button>
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
    <div id="page-course" class="hide"></div>
    <div id="page-lesson" class="hide"></div>
    <div id="page-search" class="hide"></div>
    <div id="page-login" class="hide"></div>
    <div id="page-admin" class="hide"></div>

    <div class="footer">
      © منصة BTEC – إعداد مهندس بهاء | Instagram: <b>btec_zone.2_008</b>
    </div>
  </div>

<script>
/* ============================================================================
   Single-file Platform (LocalStorage)
   - Generation (fields) -> Tasks (courses) -> Lessons -> Documents
   - Admin CRUD
   - Login + Register (per device) + Save last lesson per user
============================================================================ */

const LS_KEY = "btec_platform_v3";
const SESSION_KEY = "btec_session_v3";
const PROGRESS_KEY = "btec_progress_v3";
const DEVICE_KEY = "btec_device_v1";

/* ---------- Utilities ---------- */
const $ = (sel) => document.querySelector(sel);
const esc = (s="") => String(s)
  .replaceAll("&","&amp;").replaceAll("<","&lt;")
  .replaceAll(">","&gt;")
  .replaceAll('"',"&quot;")
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

function getSession(){
  try{ return JSON.parse(localStorage.getItem(SESSION_KEY) || "null"); }
  catch{ return null; }
}
function setSession(s){ localStorage.setItem(SESSION_KEY, JSON.stringify(s)); renderNav(); }
function logout(){
  localStorage.removeItem(SESSION_KEY);
  renderNav();
  showAlert("ok","تم تسجيل الخروج");
  go("#/");
}

/* ---------- Device identity (per browser) ---------- */
function getDeviceId(){
  let d = localStorage.getItem(DEVICE_KEY);
  if(!d){
    d = "dev_" + Math.random().toString(16).slice(2) + "_" + Date.now().toString(16);
    localStorage.setItem(DEVICE_KEY, d);
  }
  return d;
}

/* ---------- Progress (last lesson) ---------- */
function loadProgress(){
  try{ return JSON.parse(localStorage.getItem(PROGRESS_KEY) || "{}"); }
  catch{ return {}; }
}
function saveProgress(p){ localStorage.setItem(PROGRESS_KEY, JSON.stringify(p)); }

function setUserLastLesson(lessonId){
  const s = getSession();
  if(!s) return;
  const p = loadProgress();
  p[s.id] = { lastLessonId: lessonId, updatedAt: Date.now() };
  saveProgress(p);
}
function getUserLastLesson(){
  const s = getSession();
  if(!s) return null;
  const p = loadProgress();
  return p[s.id] || null;
}

/* ---------- Data Model ---------- */
function seedData(){
  return {
    users: [
      // ✅ الأدمن فقط (لا نعرضه بأي مكان في الواجهة)
      { id:"u_admin", username:"bahaa_hajaj", password:"bahaahajaj0775135361n", role:"admin", name:"Baha Admin", deviceId:"*" }
    ],
    fields: [
      { id:"g_2008", name:"جيل 2008", desc:"مهام ومستندات خاصة بطلاب 2008" },
      { id:"g_2009", name:"جيل 2009", desc:"مهام ومستندات خاصة بطلاب 2009" },
      { id:"g_2010", name:"جيل 2010", desc:"مهام ومستندات خاصة بطلاب 2010" }
    ],
    courses: [
      { id:"t_2008_1", fieldId:"g_2008", title:"مهمة 1", description:"ارفع مستندات المهمة هنا" },
      { id:"t_2009_1", fieldId:"g_2009", title:"مهمة 1", description:"ارفع مستندات المهمة هنا" },
      { id:"t_2010_1", fieldId:"g_2010", title:"مهمة 1", description:"ارفع مستندات المهمة هنا" }
    ],
    lessons: [
      { id:"lesson_1", courseId:"t_2008_1", title:"درس 1 - اليوم الأول",
        contentHtml:`<h2>درس 1</h2><p>ابدأ من هنا…</p>`,
        createdAt: Date.now()
      }
    ],
    docs: []
  };
}

function loadDB(){
  let raw = localStorage.getItem(LS_KEY);
  if(!raw){
    const d = seedData();
    localStorage.setItem(LS_KEY, JSON.stringify(d));
    return d;
  }
  try{
    const d = JSON.parse(raw);
    if(!d.fields || !d.courses || !d.lessons || !d.docs || !d.users) throw new Error("bad");
    return d;
  }catch{
    const d = seedData();
    localStorage.setItem(LS_KEY, JSON.stringify(d));
    return d;
  }
}
function saveDB(db){ localStorage.setItem(LS_KEY, JSON.stringify(db)); }

/* ---------- Helpers ---------- */
function dbFind(db, arrName, id){ return db[arrName].find(x => x.id === id); }
function coursesByField(db, fieldId){ return db.courses.filter(c => c.fieldId === fieldId); }
function lessonsByCourse(db, courseId){
  return db.lessons.filter(l => l.courseId === courseId).sort((a,b)=> (a.createdAt||0)-(b.createdAt||0));
}
function docsByCourse(db, courseId){
  return db.docs.filter(d => d.courseId === courseId).sort((a,b)=> (b.createdAt||0)-(a.createdAt||0));
}

/* ---------- User auth: login/register per device ---------- */
function normalizeU(u){ return (u||"").trim().toLowerCase(); }

function findUserForDevice(db, username, deviceId){
  const u = normalizeU(username);
  return db.users.find(x =>
    normalizeU(x.username) === u &&
    (x.role === "admin" ? true : x.deviceId === deviceId)
  );
}

function registerStudent(db, username, password, deviceId){
  const u = (username||"").trim();
  const p = (password||"").trim();

  if(u.length < 3) return { ok:false, msg:"اسم المستخدم لازم يكون 3 أحرف أو أكثر." };
  if(p.length < 4) return { ok:false, msg:"كلمة المرور لازم تكون 4 أحرف/أرقام أو أكثر." };

  // لا نسمح بتسجيل طالب على اسم الأدمن
  if(normalizeU(u) === "bahaa_hajaj") return { ok:false, msg:"هذا الاسم محجوز." };

  // على نفس الجهاز: ممنوع تكرار نفس اليوزر
  const existsSameDevice = db.users.find(x => x.role !== "admin" && x.deviceId === deviceId && normalizeU(x.username) === normalizeU(u));
  if(existsSameDevice) return { ok:false, msg:"هذا المستخدم موجود على هذا الجهاز. جرّب تسجيل الدخول بدل إنشاء حساب." };

  const newUser = {
    id: uid("u"),
    username: u,
    password: p,
    role: "student",
    name: u,
    deviceId
  };
  db.users.push(newUser);
  saveDB(db);
  return { ok:true, user:newUser };
}

function loginUser(db, username, password, deviceId){
  const u = (username||"").trim();
  const p = (password||"").trim();
  const user = findUserForDevice(db, u, deviceId);

  if(!user) return { ok:false, msg:"المستخدم غير موجود على هذا الجهاز. إذا أول مرة، اختر (إنشاء حساب جديد)." };
  if(user.password !== p) return { ok:false, msg:"كلمة المرور غير صحيحة." };

  return { ok:true, user };
}

/* ---------- Navigation render ---------- */
function renderNav(){
  const s = getSession();
  const isAuthed = !!s;
  const isAdmin = isAuthed && s.role === "admin";

  $("#loginBtn").classList.toggle("hide", isAuthed);
  $("#logoutBtn").classList.toggle("hide", !isAuthed);
  $("#adminBtn").classList.toggle("hide", !isAdmin);
}

/* ---------- Router ---------- */
function hideAllPages(){
  ["home","course","lesson","search","login","admin"].forEach(p=>{
    $("#page-"+p).classList.add("hide");
  });
}
function route(){
  hideAlert();
  hideAllPages();

  const hash = location.hash || "#/";
  const parts = hash.replace("#","").split("/").filter(Boolean);

  if(parts.length === 0){ renderHome(); return; }

  const [p, id] = parts;
  if(p === "course" && id) return renderCourse(id);
  if(p === "lesson" && id) return renderLesson(id);
  if(p === "search") return renderSearch();
  if(p === "login") return renderLogin();
  if(p === "admin") return renderAdmin();

  renderHome();
}

/* ---------- Pages ---------- */
function renderHome(){
  const db = loadDB();
  const root = $("#page-home");
  root.classList.remove("hide");

  const last = getUserLastLesson();
  const lastLesson = last?.lastLessonId ? dbFind(db,"lessons", last.lastLessonId) : null;

  const latestLessons = db.lessons
    .slice()
    .sort((a,b)=> (b.createdAt||0)-(a.createdAt||0))
    .slice(0, 7);

  root.innerHTML = `
    <div class="card" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">الأجيال</h1>
          <div class="muted">اختر الجيل ثم افتح المهمة، وبعدها حمل مستندات المهمة أو اقرأ الدروس.</div>
        </div>
        <div class="row">
          <span class="pill">2008</span><span class="pill">2009</span><span class="pill">2010</span>
        </div>
      </div>

      ${
        lastLesson ? `
          <div class="alert ok" style="margin-top:10px">
            <div><b>أكمل من حيث توقفت:</b> ${esc(lastLesson.title)}</div>
            <button class="btn small" onclick="go('#/lesson/${lastLesson.id}')">متابعة</button>
          </div>
        ` : `
          <div class="muted">سجّل دخول بحسابك (على هذا الجهاز) عشان نحفظ آخر درس وصلت له.</div>
        `
      }
    </div>

    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">الدروس اليومية (آخر الدروس)</div>
          <div class="muted">كل يوم أضف درس جديد من لوحة التحكم (للأدمن).</div>
        </div>
      </div>
      <div class="list">
        ${
          latestLessons.length ? latestLessons.map(l=>{
            const task = dbFind(db,"courses", l.courseId);
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(l.title)}</div>
                  <div class="sub">ضمن: ${esc(task?.title || "—")} • ${new Date(l.createdAt||Date.now()).toLocaleDateString("ar")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/lesson/${l.id}')">فتح</button>
                </div>
              </div>
            `;
          }).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
        }
      </div>
    </div>
  `;

  db.fields.forEach(g=>{
    const tasks = coursesByField(db, g.id);
    const html = `
      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">${esc(g.name)}</div>
            <div class="muted">${esc(g.desc || "")}</div>
          </div>
          <span class="pill">${tasks.length} مهمة</span>
        </div>

        <div class="list">
          ${
            tasks.length ? tasks.map(t=>`
              <div class="item">
                <div>
                  <div class="title">${esc(t.title)}</div>
                  <div class="sub">${esc(t.description || "")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/course/${t.id}')">فتح المهمة</button>
                </div>
              </div>
            `).join("") : `<div class="muted">لا يوجد مهام بعد.</div>`
          }
        </div>
      </div>
    `;
    root.insertAdjacentHTML("beforeend", html);
  });
}

function renderCourse(taskId){
  const db = loadDB();
  const task = dbFind(db, "courses", taskId);
  if(!task){ showAlert("bad","المهمة غير موجودة"); return go("#/"); }

  const gen = dbFind(db, "fields", task.fieldId);
  const lessons = lessonsByCourse(db, taskId);
  const docs = docsByCourse(db, taskId);

  const root = $("#page-course");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">${esc(task.title)}</h1>
          <div class="muted">الجيل: <b>${esc(gen?.name || "-")}</b></div>
          <div class="muted">${esc(task.description || "")}</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
          <span class="pill">${lessons.length} درس</span>
          <span class="pill">${docs.length} مستند</span>
        </div>
      </div>

      <div class="grid">
        <div class="card soft">
          <div class="cardHeader">
            <div>
              <div class="h2">الدروس</div>
              <div class="muted">اضغط على أي درس لفتحه.</div>
            </div>
          </div>
          <div class="list">
            ${
              lessons.length ? lessons.map(l=>`
                <div class="item">
                  <div>
                    <div class="title">${esc(l.title)}</div>
                    <div class="sub">${new Date(l.createdAt||Date.now()).toLocaleString("ar")}</div>
                  </div>
                  <div class="meta">
                    <button class="btn small" onclick="go('#/lesson/${l.id}')">فتح</button>
                  </div>
                </div>
              `).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
            }
          </div>
        </div>

        <div class="card soft">
          <div class="cardHeader">
            <div>
              <div class="h2">مستندات المهمة</div>
              <div class="muted">حمّل المستندات المطلوبة للمهمة.</div>
            </div>
          </div>
          <div class="list">
            ${
              docs.length ? docs.map(d=>`
                <div class="item">
                  <div>
                    <div class="title">${esc(d.displayName)}</div>
                    <div class="sub">${esc(d.filename)} • ${Math.round((d.size||0)/1024)} KB</div>
                  </div>
                  <div class="meta">
                    <button class="btn small ok" onclick="downloadDoc('${d.id}')">تنزيل</button>
                  </div>
                </div>
              `).join("") : `<div class="muted">لا يوجد مستندات بعد.</div>`
            }
          </div>

          <div class="alert warn" style="margin-top:12px">
            <div><b>تنبيه:</b> المستندات تُخزَّن محليًا داخل المتصفح (LocalStorage) وقد لا تناسب الملفات الكبيرة.</div>
            <button class="btn small dark" onclick="hideAlert()">حسنًا</button>
          </div>
        </div>
      </div>
    </div>
  `;
}

function renderLesson(lessonId){
  const db = loadDB();
  const lesson = dbFind(db, "lessons", lessonId);
  if(!lesson){ showAlert("bad","الدرس غير موجود"); return go("#/"); }

  setUserLastLesson(lessonId);

  const task = dbFind(db, "courses", lesson.courseId);

  const root = $("#page-lesson");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="lessonWrap">
      <div class="lessonHeader">
        <div class="row" style="justify-content:space-between">
          <div>
            <div class="bismillah">بسم الله الرحمن الرحيم</div>
            <div class="lessonTitle">${esc(lesson.title)}</div>
            <div style="opacity:.92; margin-top:6px">المهمة: <b>${esc(task?.title || "-")}</b></div>
          </div>
          <div class="row">
            <button class="btn ghost" onclick="go('#/course/${lesson.courseId}')">رجوع للمهمة</button>
            <button class="btn ghost" onclick="go('#/')">الرئيسية</button>
          </div>
        </div>
      </div>
      <div class="lessonBody">
        ${lesson.contentHtml || "<p>لا يوجد محتوى</p>"}
      </div>
    </div>
  `;
}

function renderSearch(){
  const root = $("#page-search");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">بحث</h1>
          <div class="muted">ابحث داخل الأجيال/المهام/الدروس/المستندات.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="form">
        <label>اكتب كلمة البحث</label>
        <input id="q" placeholder="مثال: مهمة 1 / درس 2 ..." oninput="doSearch()">
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

  const hits = { fields:[], courses:[], lessons:[], docs:[] };
  const match = (s)=> (s||"").toLowerCase().includes(q);

  if(!q){
    out.innerHTML = `<div class="card soft" style="grid-column:1/-1"><div class="muted">اكتب كلمة للبحث…</div></div>`;
    return;
  }

  db.fields.forEach(f=>{ if(match(f.name) || match(f.desc)) hits.fields.push(f); });
  db.courses.forEach(c=>{ if(match(c.title) || match(c.description)) hits.courses.push(c); });
  db.lessons.forEach(l=>{ if(match(l.title) || match(l.contentHtml)) hits.lessons.push(l); });
  db.docs.forEach(d=>{ if(match(d.displayName) || match(d.filename)) hits.docs.push(d); });

  const mk = (title, items) => `
    <div class="card soft">
      <div class="cardHeader">
        <div class="h2">${title}</div>
        <span class="pill">${items.length}</span>
      </div>
      <div class="list">${
        items.length ? items.join("") : `<div class="muted">لا نتائج</div>`
      }</div>
    </div>
  `;

  const fieldsHtml = hits.fields.map(f=>`
    <div class="item">
      <div><div class="title">${esc(f.name)}</div><div class="sub">${esc(f.desc||"")}</div></div>
      <div class="meta"><span class="pill">جيل</span></div>
    </div>
  `);

  const tasksHtml = hits.courses.map(t=>`
    <div class="item">
      <div><div class="title">${esc(t.title)}</div><div class="sub">${esc(t.description||"")}</div></div>
      <div class="meta"><button class="btn small" onclick="go('#/course/${t.id}')">فتح</button></div>
    </div>
  `);

  const lessonsHtml = hits.lessons.map(l=>`
    <div class="item">
      <div><div class="title">${esc(l.title)}</div><div class="sub">درس</div></div>
      <div class="meta"><button class="btn small" onclick="go('#/lesson/${l.id}')">فتح</button></div>
    </div>
  `);

  const docsHtml = hits.docs.map(d=>`
    <div class="item">
      <div><div class="title">${esc(d.displayName)}</div><div class="sub">${esc(d.filename)}</div></div>
      <div class="meta"><button class="btn small ok" onclick="downloadDoc('${d.id}')">تنزيل</button></div>
    </div>
  `);

  out.innerHTML = `
    ${mk("نتائج الأجيال", fieldsHtml)}
    ${mk("نتائج المهام", tasksHtml)}
    ${mk("نتائج الدروس", lessonsHtml)}
    ${mk("نتائج المستندات", docsHtml)}
  `;
}

/* ---------- Login/Register page ---------- */
function renderLogin(){
  const root = $("#page-login");
  root.classList.remove("hide");

  const deviceId = getDeviceId();
  const short = deviceId.split("_").slice(-1)[0].slice(-4);
  const suggested = "student_" + short;

  root.innerHTML = `
    <div class="card" style="max-width:520px;margin:0 auto;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">تسجيل الدخول</h1>
          <div class="muted">
            ملاحظة: <b>كل جهاز له حسابه الخاص</b>. إذا أول مرة عندك على هذا الجهاز، اختر "إنشاء حساب جديد"
            وسجّل باسم مستخدم مختلف عن غيرك. الحساب ينحفظ على نفس الجهاز.
          </div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <form class="form" onsubmit="event.preventDefault(); doAuth();">
        <label>
          <input type="checkbox" id="isRegister" checked>
          إنشاء حساب جديد (طالب) على هذا الجهاز
        </label>

        <label>اسم المستخدم</label>
        <input id="username" autocomplete="username" placeholder="مثال: ${esc(suggested)}" value="${esc(suggested)}" required>

        <label>كلمة المرور</label>
        <input id="password" type="password" autocomplete="current-password" placeholder="اكتب كلمة مرور" required>

        <button class="btn" type="submit">متابعة</button>

        <div class="help">
          إذا كان عندك حساب سابق على نفس الجهاز: أزل علامة "إنشاء حساب جديد" ثم سجّل دخول بنفس البيانات.
        </div>
      </form>
    </div>
  `;
}

function doAuth(){
  const db = loadDB();
  const deviceId = getDeviceId();

  const isRegister = $("#isRegister").checked;
  const u = ($("#username").value || "").trim();
  const p = ($("#password").value || "").trim();

  // لو كان الأدمن: لازم يكون تسجيل دخول فقط (حتى ما ينشئ طالب بنفس الاسم)
  if(normalizeU(u) === "bahaa_hajaj"){
    const r = loginUser(db, u, p, deviceId);
    if(!r.ok){ showAlert("bad", r.msg); return; }
    setSession({ id:r.user.id, username:r.user.username, role:r.user.role, name:r.user.name });
    showAlert("ok","تم تسجيل الدخول كأدمن ✅");
    go("#/admin");
    return;
  }

  if(isRegister){
    const rr = registerStudent(db, u, p, deviceId);
    if(!rr.ok){ showAlert("bad", rr.msg); return; }
    setSession({ id:rr.user.id, username:rr.user.username, role:rr.user.role, name:rr.user.name });
    showAlert("ok","تم إنشاء الحساب وتسجيل الدخول ✅");
    go("#/");
    return;
  }

  const r = loginUser(db, u, p, deviceId);
  if(!r.ok){ showAlert("bad", r.msg); return; }
  setSession({ id:r.user.id, username:r.user.username, role:r.user.role, name:r.user.name });
  showAlert("ok","تم تسجيل الدخول ✅");
  go("#/");
}

/* ---------- Admin Page ---------- */
function requireAdmin(){
  const s = getSession();
  if(!s || s.role !== "admin"){
    showAlert("bad","هذه الصفحة للأدمن فقط.");
    go("#/login");
    return false;
  }
  return true;
}

function renderAdmin(){
  if(!requireAdmin()) return;

  const db = loadDB();
  const root = $("#page-admin");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">لوحة التحكم</h1>
          <div class="muted">إضافة/حذف: أجيال + مهام + دروس + مستندات (محليًا).</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">عرض الموقع</button>
          <button class="btn danger" onclick="resetAll()">إعادة ضبط</button>
        </div>
      </div>

      <div class="grid">
        ${adminStatsCard("الأجيال", db.fields.length)}
        ${adminStatsCard("المهام", db.courses.length)}
        ${adminStatsCard("الدروس", db.lessons.length)}
        ${adminStatsCard("المستندات", db.docs.length)}
      </div>
    </div>

    <div class="grid" style="margin-top:14px">
      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة جيل</div>
            <div class="muted">مثال: جيل 2011</div>
          </div>
        </div>
        <form class="form" onsubmit="event.preventDefault(); addField();">
          <label>اسم الجيل</label>
          <input id="fieldName" placeholder="جيل 2011" required>
          <label>وصف مختصر</label>
          <input id="fieldDesc" placeholder="وصف للجيل">
          <button class="btn" type="submit">إضافة</button>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.fields.map(f=>`
            <div class="item">
              <div>
                <div class="title">${esc(f.name)}</div>
                <div class="sub">${esc(f.desc||"")}</div>
              </div>
              <div class="meta">
                <button class="btn small danger" onclick="delField('${f.id}')">حذف</button>
              </div>
            </div>
          `).join("")}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة مهمة</div>
            <div class="muted">المهمة مرتبطة بجيل.</div>
          </div>
        </div>
        <form class="form" onsubmit="event.preventDefault(); addCourse();">
          <label>الجيل</label>
          <select id="courseFieldId" required>
            ${db.fields.map(f=>`<option value="${f.id}">${esc(f.name)}</option>`).join("")}
          </select>
          <label>عنوان المهمة</label>
          <input id="courseTitle" placeholder="مهمة 2" required>
          <label>وصف مختصر</label>
          <input id="courseDesc" placeholder="مطلوب: …">
          <button class="btn" type="submit">إضافة</button>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.courses.slice().reverse().map(c=>{
            const f = dbFind(db,"fields",c.fieldId);
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(c.title)}</div>
                  <div class="sub">${esc(f?.name||"-")} • ${esc(c.description||"")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/course/${c.id}')">فتح</button>
                  <button class="btn small danger" onclick="delCourse('${c.id}')">حذف</button>
                </div>
              </div>
            `;
          }).join("")}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة درس</div>
            <div class="muted">اختَر المهمة ثم اكتب محتوى الدرس.</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); addLesson();">
          <label>المهمة</label>
          <select id="lessonCourseId" required>
            ${db.courses.map(c=>`<option value="${c.id}">${esc(c.title)}</option>`).join("")}
          </select>

          <label>عنوان الدرس</label>
          <input id="lessonTitle" placeholder="درس 2 - اليوم الثاني" required>

          <label>محتوى الدرس (HTML)</label>
          <textarea id="lessonHtml" placeholder="<h2>عنوان</h2><p>شرح...</p><pre>print(&quot;Hello&quot;)</pre>"></textarea>

          <div class="help">للكود استخدم: <b>&lt;pre&gt;...&lt;/pre&gt;</b></div>
          <button class="btn" type="submit">إضافة</button>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.lessons.slice().reverse().slice(0,10).map(l=>{
            const c = dbFind(db,"courses",l.courseId);
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(l.title)}</div>
                  <div class="sub">${esc(c?.title||"-")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/lesson/${l.id}')">فتح</button>
                  <button class="btn small danger" onclick="delLesson('${l.id}')">حذف</button>
                </div>
              </div>
            `;
          }).join("")}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">رفع مستند لمهمة</div>
            <div class="muted">يرتبط بمهمة (محليًا).</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); addDoc();">
          <label>المهمة</label>
          <select id="docCourseId" required>
            ${db.courses.map(c=>`<option value="${c.id}">${esc(c.title)}</option>`).join("")}
          </select>

          <label>اسم يظهر للطلاب</label>
          <input id="docName" placeholder="مستند مهمة 1 - PDF" required>

          <label>اختر الملف</label>
          <input id="docFile" type="file" required>

          <button class="btn" type="submit">رفع</button>
          <div class="help">مناسب للملفات الصغيرة (LocalStorage).</div>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.docs.slice().reverse().slice(0,10).map(d=>{
            const c = dbFind(db,"courses",d.courseId);
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(d.displayName)}</div>
                  <div class="sub">${esc(c?.title||"-")} • ${esc(d.filename)} • ${Math.round((d.size||0)/1024)} KB</div>
                </div>
                <div class="meta">
                  <button class="btn small ok" onclick="downloadDoc('${d.id}')">تنزيل</button>
                  <button class="btn small danger" onclick="delDoc('${d.id}')">حذف</button>
                </div>
              </div>
            `;
          }).join("")}
        </div>
      </div>
    </div>
  `;
}

function adminStatsCard(title, num){
  return `
    <div class="card soft">
      <div class="h2">${esc(title)}</div>
      <div style="font-size:34px;font-weight:1000;color:var(--primary);margin-top:6px">${num}</div>
    </div>
  `;
}

/* ---------- Admin Actions ---------- */
function resetAll(){
  if(!confirm("هل تريد إعادة ضبط كل البيانات؟")) return;
  localStorage.removeItem(LS_KEY);
  localStorage.removeItem(PROGRESS_KEY);
  // ما نحذف DEVICE_KEY حتى يضل نفس الجهاز معروف
  showAlert("ok","تمت إعادة الضبط");
  route();
}

function addField(){
  const db = loadDB();
  const name = ($("#fieldName").value||"").trim();
  const desc = ($("#fieldDesc").value||"").trim();
  if(!name) return;

  if(db.fields.some(f => f.name.toLowerCase() === name.toLowerCase())){
    showAlert("bad","اسم الجيل موجود مسبقًا");
    return;
  }
  db.fields.push({ id: uid("g"), name, desc });
  saveDB(db);
  showAlert("ok","تم إضافة الجيل ✅");
  route();
}

function delField(id){
  if(!confirm("حذف الجيل سيحذف المهام والدروس والمستندات التابعة له. متابعة؟")) return;
  const db = loadDB();
  const tasks = db.courses.filter(c=>c.fieldId===id).map(c=>c.id);

  db.docs = db.docs.filter(d => !tasks.includes(d.courseId));
  db.lessons = db.lessons.filter(l => !tasks.includes(l.courseId));
  db.courses = db.courses.filter(c => c.fieldId !== id);
  db.fields = db.fields.filter(f => f.id !== id);

  saveDB(db);
  showAlert("ok","تم حذف الجيل ✅");
  route();
}

function addCourse(){
  const db = loadDB();
  const fieldId = $("#courseFieldId").value;
  const title = ($("#courseTitle").value||"").trim();
  const description = ($("#courseDesc").value||"").trim();
  if(!title) return;

  db.courses.push({ id: uid("t"), fieldId, title, description });
  saveDB(db);
  showAlert("ok","تم إضافة المهمة ✅");
  route();
}

function delCourse(id){
  if(!confirm("حذف المهمة سيحذف الدروس والمستندات التابعة لها. متابعة؟")) return;
  const db = loadDB();
  db.docs = db.docs.filter(d => d.courseId !== id);
  db.lessons = db.lessons.filter(l => l.courseId !== id);
  db.courses = db.courses.filter(c => c.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف المهمة ✅");
  route();
}

function addLesson(){
  const db = loadDB();
  const courseId = $("#lessonCourseId").value;
  const title = ($("#lessonTitle").value||"").trim();
  const contentHtml = ($("#lessonHtml").value||"").trim() || "<p>محتوى الدرس…</p>";
  if(!title) return;

  db.lessons.push({ id: uid("lesson"), courseId, title, contentHtml, createdAt: Date.now() });
  saveDB(db);
  showAlert("ok","تم إضافة الدرس ✅");
  route();
}

function delLesson(id){
  if(!confirm("حذف الدرس؟")) return;
  const db = loadDB();
  db.lessons = db.lessons.filter(l => l.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف الدرس ✅");
  route();
}

function addDoc(){
  const fileInput = $("#docFile");
  const file = fileInput.files?.[0];
  if(!file){ showAlert("bad","اختر ملفًا"); return; }

  if(file.size > 3 * 1024 * 1024){
    if(!confirm("الملف أكبر من 3MB وقد لا يُحفظ. متابعة؟")) return;
  }

  const courseId = $("#docCourseId").value;
  const displayName = ($("#docName").value||"").trim();
  if(!displayName){ showAlert("bad","اكتب اسمًا للمستند"); return; }

  const reader = new FileReader();
  reader.onload = () => {
    const dataUrl = reader.result;
    const db = loadDB();

    db.docs.push({
      id: uid("doc"),
      courseId,
      displayName,
      filename: file.name,
      mime: file.type || "application/octet-stream",
      size: file.size,
      dataUrl,
      createdAt: Date.now()
    });

    try{
      saveDB(db);
      showAlert("ok","تم رفع المستند ✅ (محليًا)");
      route();
    }catch(e){
      showAlert("bad","فشل الحفظ: مساحة LocalStorage امتلأت. جرّب ملف أصغر.");
    }
  };
  reader.onerror = () => showAlert("bad","تعذر قراءة الملف");
  reader.readAsDataURL(file);
}

function delDoc(id){
  if(!confirm("حذف المستند؟")) return;
  const db = loadDB();
  db.docs = db.docs.filter(d => d.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف المستند ✅");
  route();
}

function downloadDoc(id){
  const db = loadDB();
  const doc = dbFind(db,"docs",id);
  if(!doc){ showAlert("bad","المستند غير موجود"); return; }
  const a = document.createElement("a");
  a.href = doc.dataUrl;
  a.download = doc.filename || "file";
  document.body.appendChild(a);
  a.click();
  a.remove();
}

/* ---------- Boot ---------- */
window.addEventListener("hashchange", route);
renderNav();
route();
</script>

</body>
</html>
