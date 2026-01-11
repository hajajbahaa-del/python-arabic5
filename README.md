<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>BTEC - منصة مهندس بهاء</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap');

    :root{
      --card:#ffffff;
      --text:#101828;
      --muted:#667085;
      --primary:#0d39ff;
      --primary2:#000000;
      --line:#e6e9f5;
      --soft:#f5f7ff;
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
      display:inline-flex; align-items:center; justify-content:center;
      gap:8px;
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
    .btn.link{background:transparent;color:var(--primary);text-decoration:underline;padding:0;border-radius:0}

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
    input:focus, textarea:focus, select:focus{border-color:#98a6ff; box-shadow: 0 0 0 4px rgba(13,57,255,.12)}
    .help{font-size:12px; color:var(--muted)}
    .split{display:grid; grid-template-columns:1fr 1fr; gap:10px}
    @media (max-width: 720px){ .split{grid-template-columns:1fr} }

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

    /* presentation lesson */
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
    .lessonTitle{margin:8px 0 0; font-size:26px; font-weight:1000}
    .lessonBody{padding:18px; line-height:1.95}
    .slide{
      border:1px solid var(--line);
      background:#fbfcff;
      border-radius:16px;
      padding:14px;
      margin-bottom:12px;
    }
    .slide h3{margin:0 0 8px;color:var(--primary)}
    .slide ul{margin:0; padding-right:18px}
    .slide pre{
      background:#111827; color:#d1fae5;
      padding:12px; border-radius:14px;
      overflow:auto; direction:ltr; text-align:left;
      margin:10px 0 0;
    }
    .slide code{
      background:#111827; color:#d1fae5;
      padding:2px 6px; border-radius:8px;
      direction:ltr;
    }

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
    <div id="page-task" class="hide"></div>

    <div id="page-python" class="hide"></div>
    <div id="page-python-lesson" class="hide"></div>

    <div id="page-search" class="hide"></div>
    <div id="page-login" class="hide"></div>
    <div id="page-admin" class="hide"></div>

    <div class="footer">
      © منصة BTEC – إعداد مهندس بهاء | Instagram: <b>btec_zone.2_008</b>
    </div>
  </div>

<script>
/* ============================================================================
   Single-file Platform (LocalStorage) - نسخة بدون سيرفر
============================================================================ */

const LS_KEY = "btec_platform_v4";
const SESSION_KEY = "btec_session_v4";
const DEVICE_KEY = "btec_device_v1";
const PROGRESS_KEY = "btec_progress_v4";

/* ✅ ملف الدروس الذي ترفعه بجانب index.html على الاستضافة */
const BACKUP_FILE_URL = "btec-backup.json";

/* ---------- Utilities ---------- */
const $ = (sel) => document.querySelector(sel);

/* ✅✅ esc بدون replaceAll (يدعم الأجهزة القديمة) */
const esc = (s="") => String(s)
  .replace(/&/g,"&amp;")
  .replace(/</g,"&lt;")
  .replace(/>/g,"&gt;")
  .replace(/"/g,"&quot;")
  .replace(/'/g,"&#039;");

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

/* ✅✅ تحميل ملف الدروس بأمان (حتى لا ينزل HTML إذا الملف مش موجود) */
async function safeDownloadBackup(){
  try{
    const r = await fetch(BACKUP_FILE_URL, { cache: "no-store" });
    if(!r.ok){
      showAlert("bad","ملف الدروس غير موجود على الموقع. ارفع btec-backup.json بجانب index.html");
      return;
    }
    const ct = (r.headers.get("content-type") || "").toLowerCase();
    if(!ct.includes("application/json") && !ct.includes("text/json")){
      showAlert("bad","الملف الموجود ليس JSON (يبدو صفحة HTML). تأكد أنك رفعت btec-backup.json الصحيح.");
      return;
    }
    const a = document.createElement("a");
    a.href = BACKUP_FILE_URL;
    a.download = "btec-backup.json";
    document.body.appendChild(a);
    a.click();
    a.remove();
  }catch(e){
    showAlert("bad","فشل تحميل ملف الدروس. تحقق من الرابط/الانترنت.");
  }
}

/* ---------- Session ---------- */
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

/* ---------- Device identity ---------- */
function getDeviceId(){
  let d = localStorage.getItem(DEVICE_KEY);
  if(!d){
    d = "dev_" + Math.random().toString(16).slice(2) + "_" + Date.now().toString(16);
    localStorage.setItem(DEVICE_KEY, d);
  }
  return d;
}

/* ---------- Progress ---------- */
function loadProgress(){
  try{ return JSON.parse(localStorage.getItem(PROGRESS_KEY) || "{}"); }
  catch{ return {}; }
}
function saveProgress(p){ localStorage.setItem(PROGRESS_KEY, JSON.stringify(p)); }

function setUserLast(type, id){
  const s = getSession();
  if(!s) return;
  const p = loadProgress();
  p[s.id] = { type, id, updatedAt: Date.now() };
  saveProgress(p);
}
function getUserLast(){
  const s = getSession();
  if(!s) return null;
  const p = loadProgress();
  return p[s.id] || null;
}

/* ---------- Data Model ---------- */
function seedData(){
  return {
    users: [
      { id:"u_admin", username:"bahaa_hajaj", password:"bahaahajaj0775135361n", role:"admin", name:"Baha Admin", deviceId:"*" }
    ],
    generations: [
      { id:"g_2008", name:"جيل 2008", desc:"" },
      { id:"g_2009", name:"جيل 2009", desc:"" },
      { id:"g_2010", name:"جيل 2010", desc:"" }
    ],
    tasks: [],
    taskDocs: [],
    pythonLessons: []
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
    if(!d.users || !d.generations || !d.tasks || !d.taskDocs || !d.pythonLessons) throw new Error("bad");
    return d;
  }catch{
    const d = seedData();
    localStorage.setItem(LS_KEY, JSON.stringify(d));
    return d;
  }
}
function saveDB(db){ localStorage.setItem(LS_KEY, JSON.stringify(db)); }

/* ---------- Helpers ---------- */
function normalizeU(u){ return (u||"").trim().toLowerCase(); }
function dbFind(db, arr, id){ return db[arr].find(x => x.id === id); }
function tasksByGen(db, genId){ return db.tasks.filter(t => t.genId === genId); }
function docsByTask(db, taskId){
  return db.taskDocs.filter(d => d.taskId === taskId).sort((a,b)=> (b.createdAt||0)-(a.createdAt||0));
}
function pythonLessonsSorted(db){
  return db.pythonLessons.slice().sort((a,b)=> (b.createdAt||0)-(a.createdAt||0));
}

/* ---------- Auth: register/login per device ---------- */
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
  if(normalizeU(u) === "bahaa_hajaj") return { ok:false, msg:"هذا الاسم محجوز." };

  const existsSameDevice = db.users.find(x => x.role !== "admin" && x.deviceId === deviceId && normalizeU(x.username) === normalizeU(u));
  if(existsSameDevice) return { ok:false, msg:"هذا المستخدم موجود على هذا الجهاز. سجّل دخول بدل إنشاء." };

  const newUser = { id: uid("u"), username: u, password: p, role:"student", name: u, deviceId };
  db.users.push(newUser);
  saveDB(db);
  return { ok:true, user:newUser };
}
function loginUser(db, username, password, deviceId){
  const u = (username||"").trim();
  const p = (password||"").trim();
  const user = findUserForDevice(db, u, deviceId);
  if(!user) return { ok:false, msg:"المستخدم غير موجود على هذا الجهاز. إذا أول مرة اختر إنشاء حساب جديد." };
  if(user.password !== p) return { ok:false, msg:"كلمة المرور غير صحيحة." };
  return { ok:true, user };
}

/* ---------- Nav ---------- */
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
  ["home","task","python","python-lesson","search","login","admin"].forEach(p=>{
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

  if(p === "task" && id) return renderTask(id);
  if(p === "python") return renderPython();
  if(p === "pythonLesson" && id) return renderPythonLesson(id);
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

  const last = getUserLast();
  let lastHtml = `<div class="muted">سجّل دخول عشان نحفظ آخر شيء وصلت له على هذا الجهاز.</div>`;
  if(last){
    if(last.type === "task"){
      lastHtml = `<div class="alert ok"><div><b>أكمل من حيث توقفت:</b> آخر مهمة فتحتها</div>
      <button class="btn small" onclick="go('#/task/${esc(last.id)}')">متابعة</button></div>`;
    }else if(last.type === "python"){
      lastHtml = `<div class="alert ok"><div><b>أكمل من حيث توقفت:</b> آخر درس بايثون فتحته</div>
      <button class="btn small" onclick="go('#/pythonLesson/${esc(last.id)}')">متابعة</button></div>`;
    }
  }

  const py = pythonLessonsSorted(db).slice(0,5);

  root.innerHTML = `
    <div class="card" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">الرئيسية</h1>
          <div class="muted">الأجيال → المهمات → مستندات المهمة. ودروس بايثون كبرسنتيشن.</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/python')">دروس بايثون</button>
        </div>
      </div>
      ${lastHtml}
    </div>

    <!-- ✅✅✅ بطاقة ملف الدروس (بدل الرسالة القديمة + بدون استيراد تلقائي) -->
    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">📌 مهم: لإظهار الدروس على أي جهاز</div>
          <div class="muted">
            المنصة بدون سيرفر، لذلك البيانات (الدروس/المهام) تكون محفوظة داخل المتصفح فقط.<br>
            إذا ما ظهرت الدروس عندك: ارفع/استيراد ملف الدروس مرة واحدة.
          </div>
        </div>
      </div>

      <div class="row">
        <button class="btn ok" onclick="safeDownloadBackup()">تحميل ملف الدروس</button>

        <label class="btn ghost" style="cursor:pointer;">
          رفع / استيراد ملف الدروس
          <input type="file" accept="application/json" style="display:none" onchange="importDB(this.files[0])">
        </label>
      </div>
    </div>

    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">تعلم دروس بايثون من تحت صفر (Python)</div>
          <div class="muted">تضاف من لوحة التحكم (برسنتيشن).</div>
        </div>
      </div>
      <div class="list">
        ${
          py.length ? py.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title)}</div>
                <div class="sub">${new Date(l.createdAt||Date.now()).toLocaleDateString("ar")}</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا يوجد دروس بايثون بعد.</div>`
        }
      </div>
    </div>
  `;

  db.generations.forEach(g=>{
    const tasks = tasksByGen(db, g.id);
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
            tasks.length ? tasks.map(t=>{
              const docsCount = docsByTask(db, t.id).length;
              return `
                <div class="item">
                  <div>
                    <div class="title">${esc(t.title)}</div>
                    <div class="sub">${esc(t.description||"")} • ${docsCount} مستند</div>
                  </div>
                  <div class="meta">
                    <button class="btn small" onclick="go('#/task/${t.id}')">فتح المهمة</button>
                  </div>
                </div>
              `;
            }).join("") : `<div class="muted">لا يوجد مهام بعد. (أضفها من لوحة التحكم)</div>`
          }
        </div>
      </div>
    `;
    root.insertAdjacentHTML("beforeend", html);
  });
}

function renderTask(taskId){
  const db = loadDB();
  const task = dbFind(db, "tasks", taskId);
  if(!task){ showAlert("bad","المهمة غير موجودة"); return go("#/"); }

  const gen = dbFind(db, "generations", task.genId);
  const docs = docsByTask(db, taskId);

  setUserLast("task", taskId);

  const root = $("#page-task");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">${esc(task.title)}</h1>
          <div class="muted">الجيل: <b>${esc(gen?.name||"-")}</b></div>
          <div class="muted">${esc(task.description||"")}</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
          <span class="pill">${docs.length} مستند</span>
        </div>
      </div>

      <div class="grid">
        <div class="card soft">
          <div class="cardHeader">
            <div>
              <div class="h2">مستندات المهمة</div>
              <div class="muted">تنزيل مستندات هذه المهمة.</div>
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
                    <button class="btn small ok" onclick="downloadTaskDoc('${d.id}')">تنزيل</button>
                  </div>
                </div>
              `).join("") : `<div class="muted">لا يوجد مستندات بعد.</div>`
            }
          </div>

          <div class="alert warn" style="margin-top:12px">
            <div><b>تنبيه:</b> المستندات تُحفظ محليًا داخل المتصفح (LocalStorage).</div>
            <button class="btn small dark" onclick="hideAlert()">حسنًا</button>
          </div>
        </div>

        <div class="card soft">
          <div class="cardHeader">
            <div>
              <div class="h2">ملاحظات المهمة</div>
              <div class="muted">اكتب وصف المهمة من لوحة التحكم، وسيظهر هنا.</div>
            </div>
          </div>
          <div class="muted">${esc(task.description || "لا يوجد وصف بعد.")}</div>
        </div>
      </div>
    </div>
  `;
}

/* ---------- Python pages (presentation) ---------- */
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
          <div class="muted">دروس على شكل برسنتيشن (شرائح) تضاف من لوحة التحكم.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
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
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا يوجد دروس بعد. (أضفها من لوحة التحكم)</div>`
        }
      </div>
    </div>
  `;
}

function renderPythonLesson(id){
  const db = loadDB();
  const lesson = dbFind(db, "pythonLessons", id);
  if(!lesson){ showAlert("bad","درس بايثون غير موجود"); return go("#/python"); }

  setUserLast("python", id);

  const root = $("#page-python-lesson");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="lessonWrap">
      <div class="lessonHeader">
        <div class="row" style="justify-content:space-between">
          <div>
            <div style="font-weight:900;opacity:.95">بسم الله الرحمن الرحيم</div>
            <div class="lessonTitle">${esc(lesson.title)}</div>
          </div>
          <div class="row">
            <button class="btn ghost" onclick="go('#/python')">رجوع</button>
            <button class="btn ghost" onclick="go('#/')">الرئيسية</button>
          </div>
        </div>
      </div>

      <div class="lessonBody">
        ${
          (lesson.slides||[]).length ? (lesson.slides||[]).map((s,idx)=>`
            <div class="slide">
              <h3>${idx+1}. ${esc(s.title || "شريحة")}</h3>
              ${
                (s.bullets||[]).length ? `<ul>${s.bullets.map(b=>`<li>${esc(b)}</li>`).join("")}</ul>` : `<div class="muted">—</div>`
              }
              ${
                s.code ? `<pre>${esc(s.code)}</pre>` : ``
              }
            </div>
          `).join("") : `<div class="muted">لا يوجد شرائح بعد.</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- Search ---------- */
function renderSearch(){
  const root = $("#page-search");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">بحث</h1>
          <div class="muted">ابحث داخل الأجيال/المهمات/المستندات/دروس بايثون.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="form">
        <label>اكتب كلمة البحث</label>
        <input id="q" placeholder="مثال: مهمة قواعد / متغيرات / loops ..." oninput="doSearch()">
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

  const match = (s)=> (s||"").toLowerCase().includes(q);
  if(!q){
    out.innerHTML = `<div class="card soft" style="grid-column:1/-1"><div class="muted">اكتب كلمة للبحث…</div></div>`;
    return;
  }

  const gens = db.generations.filter(g=> match(g.name) || match(g.desc));
  const tasks = db.tasks.filter(t=> match(t.title) || match(t.description));
  const docs = db.taskDocs.filter(d=> match(d.displayName) || match(d.filename));
  const py = db.pythonLessons.filter(l=> match(l.title) || (l.slides||[]).some(s=> match(s.title) || (s.bullets||[]).some(b=>match(b)) || match(s.code)));

  const mk = (title, items) => `
    <div class="card soft">
      <div class="cardHeader">
        <div class="h2">${title}</div>
        <span class="pill">${items.length}</span>
      </div>
      <div class="list">${items.length ? items.join("") : `<div class="muted">لا نتائج</div>`}</div>
    </div>
  `;

  out.innerHTML = `
    ${mk("الأجيال", gens.map(g=>`
      <div class="item">
        <div>
          <div class="title">${esc(g.name)}</div>
          <div class="sub">${esc(g.desc||"")}</div>
        </div>
        <div class="meta"><span class="pill">جيل</span></div>
      </div>
    `))}
    ${mk("المهمات", tasks.map(t=>`
      <div class="item">
        <div>
          <div class="title">${esc(t.title)}</div>
          <div class="sub">${esc(t.description||"")}</div>
        </div>
        <div class="meta">
          <button class="btn small" onclick="go('#/task/${t.id}')">فتح</button>
        </div>
      </div>
    `))}
    ${mk("المستندات", docs.map(d=>`
      <div class="item">
        <div>
          <div class="title">${esc(d.displayName)}</div>
          <div class="sub">${esc(d.filename)}</div>
        </div>
        <div class="meta">
          <button class="btn small ok" onclick="downloadTaskDoc('${d.id}')">تنزيل</button>
        </div>
      </div>
    `))}
    ${mk("دروس بايثون", py.map(l=>`
      <div class="item">
        <div>
          <div class="title">${esc(l.title)}</div>
          <div class="sub">درس برسنتيشن</div>
        </div>
        <div class="meta">
          <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
        </div>
      </div>
    `))}
  `;
}

/* ---------- Login/Register ---------- */
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
            ملاحظة: كل جهاز له حسابه الخاص. أنشئ حساب طالب باسم مختلف، وسيبقى محفوظًا على نفس الجهاز.
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
          إذا عندك حساب سابق على نفس الجهاز: أزل علامة "إنشاء حساب جديد" ثم ادخل نفس البيانات.
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

/* ---------- Admin ---------- */
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
          <div class="muted">تحكم كامل بالأسماء: الجيل / المهمة / المستند / درس بايثون.</div>
        </div>

        <!-- ✅✅✅ تم حذف زر تصدير البيانات + حذف زر الاستيراد التلقائي -->
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">عرض الموقع</button>

          <label class="btn ghost" style="cursor:pointer;">
            استيراد البيانات
            <input id="importFile" type="file" accept="application/json" style="display:none" onchange="importDB(this.files[0])">
          </label>

          <button class="btn danger" onclick="resetAll()">إعادة ضبط البيانات</button>
        </div>
      </div>

      <div class="grid">
        ${adminStatsCard("الأجيال", db.generations.length)}
        ${adminStatsCard("المهمات", db.tasks.length)}
        ${adminStatsCard("مستندات المهمات", db.taskDocs.length)}
        ${adminStatsCard("دروس بايثون", db.pythonLessons.length)}
      </div>
    </div>

    <div class="grid" style="margin-top:14px">

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة جيل</div>
            <div class="muted">أنت تختار اسم الجيل.</div>
          </div>
        </div>
        <form class="form" onsubmit="event.preventDefault(); addGen();">
          <label>اسم الجيل</label>
          <input id="genName" placeholder="مثال: جيل 2011" required>
          <label>وصف مختصر</label>
          <input id="genDesc" placeholder="اختياري">
          <button class="btn" type="submit">إضافة</button>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.generations.map(g=>`
            <div class="item">
              <div>
                <div class="title">${esc(g.name)}</div>
                <div class="sub">${esc(g.desc||"")}</div>
              </div>
              <div class="meta">
                <button class="btn small danger" onclick="delGen('${g.id}')">حذف</button>
              </div>
            </div>
          `).join("")}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة مهمة داخل جيل</div>
            <div class="muted">أنت تكتب اسم المهمة بنفسك.</div>
          </div>
        </div>
        <form class="form" onsubmit="event.preventDefault(); addTask();">
          <label>اختر الجيل</label>
          <select id="taskGenId" required>
            ${db.generations.map(g=>`<option value="${g.id}">${esc(g.name)}</option>`).join("")}
          </select>

          <label>اسم المهمة</label>
          <input id="taskTitle" placeholder="مثال: مهمة قواعد البيانات" required>

          <label>وصف المهمة</label>
          <input id="taskDesc" placeholder="اختياري">

          <button class="btn" type="submit">إضافة</button>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.tasks.slice().reverse().map(t=>{
            const g = dbFind(db,"generations",t.genId);
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(t.title)}</div>
                  <div class="sub">${esc(g?.name||"-")} • ${esc(t.description||"")}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/task/${t.id}')">فتح</button>
                  <button class="btn small danger" onclick="delTask('${t.id}')">حذف</button>
                </div>
              </div>
            `;
          }).join("") || `<div class="muted">لا يوجد مهمات بعد.</div>`}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">رفع مستند لمهمة</div>
            <div class="muted">اختر الجيل ثم المهمة، واكتب اسم المستند.</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); addTaskDoc();">
          <label>اختر الجيل</label>
          <select id="docGenId" onchange="refreshDocTasks()" required>
            ${db.generations.map(g=>`<option value="${g.id}">${esc(g.name)}</option>`).join("")}
          </select>

          <label>اختر المهمة</label>
          <select id="docTaskId" required></select>

          <label>اسم المستند (يظهر للطلاب)</label>
          <input id="docDisplayName" placeholder="مثال: حل المهمة PDF" required>

          <label>اختر الملف</label>
          <input id="docFile" type="file" required>

          <button class="btn" type="submit">رفع</button>
          <div class="help">ملاحظة: التخزين محلي (LocalStorage) مناسب للملفات الصغيرة.</div>
        </form>

        <div style="margin-top:12px" class="list">
          ${db.taskDocs.slice().reverse().slice(0,10).map(d=>{
            const t = dbFind(db,"tasks",d.taskId);
            const g = t ? dbFind(db,"generations",t.genId) : null;
            return `
              <div class="item">
                <div>
                  <div class="title">${esc(d.displayName)}</div>
                  <div class="sub">${esc(g?.name||"-")} • ${esc(t?.title||"-")} • ${esc(d.filename)}</div>
                </div>
                <div class="meta">
                  <button class="btn small ok" onclick="downloadTaskDoc('${d.id}')">تنزيل</button>
                  <button class="btn small danger" onclick="delTaskDoc('${d.id}')">حذف</button>
                </div>
              </div>
            `;
          }).join("") || `<div class="muted">لا يوجد مستندات بعد.</div>`}
        </div>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة درس بايثون (برسنتيشن)</div>
            <div class="muted">تكتب محتوى مرتب، والطلاب يفتحوه كشرائح.</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); return false;">
          <label>عنوان الدرس</label>
          <input id="pyTitle" placeholder="مثال: المتغيرات في بايثون" required>

          <div class="split">
            <div>
              <label>عنوان الشريحة</label>
              <input id="pySlideTitle" placeholder="مثال: ما هو المتغير؟">
            </div>
            <div>
              <label>كود (اختياري)</label>
              <input id="pySlideCodeOneLine" placeholder='مثال: name = "Ali"'>
            </div>
          </div>

          <label>نقاط الشريحة (كل سطر نقطة)</label>
          <textarea id="pySlideBullets" placeholder="اكتب نقاط...\nكل سطر = نقطة"></textarea>

          <div class="row">
            <button class="btn dark" type="button" onclick="addSlideToDraft()">+ إضافة الشريحة إلى المسودة</button>
            <span class="pill" id="draftCount">0 شريحة</span>
            <button class="btn" type="button" onclick="addPythonLesson()">حفظ الدرس</button>
          </div>

          <div class="help">نصيحة: اعمل 5-10 شرائح للدرس، وبعدها اضغط حفظ.</div>

          <div id="draftPreview" class="list" style="margin-top:10px"></div>
        </form>

        <div style="margin-top:12px" class="list">
          ${pythonLessonsSorted(db).slice(0,10).map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title)}</div>
                <div class="sub">${(l.slides||[]).length} شريحة • ${new Date(l.createdAt||Date.now()).toLocaleDateString("ar")}</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
                <button class="btn small danger" onclick="delPythonLesson('${l.id}')">حذف</button>
              </div>
            </div>
          `).join("") || `<div class="muted">لا يوجد دروس بايثون بعد.</div>`}
        </div>
      </div>

    </div>
  `;

  refreshDocTasks();
  resetDraftUI();
}

function adminStatsCard(title, num){
  return `
    <div class="card soft">
      <div class="h2">${esc(title)}</div>
      <div style="font-size:34px;font-weight:1000;color:var(--primary);margin-top:6px">${num}</div>
    </div>
  `;
}

/* ---------- Admin actions ---------- */
function resetAll(){
  if(!confirm("هل تريد إعادة ضبط كل البيانات؟")) return;
  localStorage.removeItem(LS_KEY);
  localStorage.removeItem(PROGRESS_KEY);
  showAlert("ok","تمت إعادة الضبط");
  route();
}

function addGen(){
  const db = loadDB();
  const name = ($("#genName").value||"").trim();
  const desc = ($("#genDesc").value||"").trim();
  if(!name) return;

  if(db.generations.some(g => (g.name||"").toLowerCase() === name.toLowerCase())){
    showAlert("bad","اسم الجيل موجود مسبقًا");
    return;
  }
  db.generations.push({ id: uid("g"), name, desc });
  saveDB(db);
  showAlert("ok","تم إضافة الجيل ✅");
  route();
}

function delGen(id){
  if(!confirm("حذف الجيل سيحذف المهمات والمستندات التابعة له. متابعة؟")) return;
  const db = loadDB();
  const tasks = db.tasks.filter(t=>t.genId===id).map(t=>t.id);
  db.taskDocs = db.taskDocs.filter(d => !tasks.includes(d.taskId));
  db.tasks = db.tasks.filter(t => t.genId !== id);
  db.generations = db.generations.filter(g => g.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف الجيل ✅");
  route();
}

function addTask(){
  const db = loadDB();
  const genId = $("#taskGenId").value;
  const title = ($("#taskTitle").value||"").trim();
  const description = ($("#taskDesc").value||"").trim();
  if(!title) return;

  db.tasks.push({ id: uid("t"), genId, title, description });
  saveDB(db);
  showAlert("ok","تم إضافة المهمة ✅");
  route();
}

function delTask(id){
  if(!confirm("حذف المهمة سيحذف المستندات التابعة لها. متابعة؟")) return;
  const db = loadDB();
  db.taskDocs = db.taskDocs.filter(d => d.taskId !== id);
  db.tasks = db.tasks.filter(t => t.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف المهمة ✅");
  route();
}

/* --- Dependent dropdown for uploading docs: gen -> tasks --- */
function refreshDocTasks(){
  const db = loadDB();
  const genId = $("#docGenId")?.value;
  const sel = $("#docTaskId");
  if(!sel) return;

  const tasks = db.tasks.filter(t=>t.genId === genId);
  sel.innerHTML = tasks.length
    ? tasks.map(t=>`<option value="${t.id}">${esc(t.title)}</option>`).join("")
    : `<option value="">لا يوجد مهمات لهذا الجيل</option>`;
}

function addTaskDoc(){
  const db = loadDB();
  const taskId = $("#docTaskId").value;
  const displayName = ($("#docDisplayName").value||"").trim();
  const fileInput = $("#docFile");
  const file = fileInput.files?.[0];

  if(!taskId){ showAlert("bad","اختر مهمة صحيحة"); return; }
  if(!displayName){ showAlert("bad","اكتب اسم المستند"); return; }
  if(!file){ showAlert("bad","اختر ملفًا"); return; }

  if(file.size > 3 * 1024 * 1024){
    if(!confirm("الملف أكبر من 3MB وقد لا يُحفظ. متابعة؟")) return;
  }

  const reader = new FileReader();
  reader.onload = () => {
    const dataUrl = reader.result;
    db.taskDocs.push({
      id: uid("doc"),
      taskId,
      displayName,
      filename: file.name,
      mime: file.type || "application/octet-stream",
      size: file.size,
      dataUrl,
      createdAt: Date.now()
    });

    try{
      saveDB(db);
      showAlert("ok","تم رفع المستند ✅");
      route();
    }catch(e){
      showAlert("bad","فشل الحفظ: LocalStorage امتلأ. جرّب ملف أصغر.");
    }
  };
  reader.onerror = () => showAlert("bad","تعذر قراءة الملف");
  reader.readAsDataURL(file);
}

function delTaskDoc(id){
  if(!confirm("حذف المستند؟")) return;
  const db = loadDB();
  db.taskDocs = db.taskDocs.filter(d => d.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف المستند ✅");
  route();
}

function downloadTaskDoc(id){
  const db = loadDB();
  const doc = dbFind(db, "taskDocs", id);
  if(!doc){ showAlert("bad","المستند غير موجود"); return; }
  const a = document.createElement("a");
  a.href = doc.dataUrl;
  a.download = doc.filename || "file";
  document.body.appendChild(a);
  a.click();
  a.remove();
}

/* ---------- Python lesson draft ---------- */
let PY_DRAFT = [];

function resetDraftUI(){
  PY_DRAFT = [];
  const cnt = $("#draftCount");
  const prev = $("#draftPreview");
  if(cnt) cnt.textContent = "0 شريحة";
  if(prev) prev.innerHTML = "";
}

function addSlideToDraft(){
  const title = ($("#pySlideTitle").value||"").trim();
  const bulletsText = ($("#pySlideBullets").value||"").trim();
  const code = ($("#pySlideCodeOneLine").value||"").trim();

  if(!title){ showAlert("bad","اكتب عنوان الشريحة"); return; }

  const bullets = bulletsText
    ? bulletsText.split("\n").map(x=>x.trim()).filter(Boolean)
    : [];

  PY_DRAFT.push({ title, bullets, code });

  $("#pySlideTitle").value = "";
  $("#pySlideBullets").value = "";
  $("#pySlideCodeOneLine").value = "";

  renderDraftPreview();
}

function renderDraftPreview(){
  const cnt = $("#draftCount");
  const prev = $("#draftPreview");
  if(cnt) cnt.textContent = `${PY_DRAFT.length} شريحة`;
  if(!prev) return;

  prev.innerHTML = PY_DRAFT.map((s,idx)=>`
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

/* ✅ حفظ الدرس */
function addPythonLesson(){
  const db = loadDB();

  const titleEl = $("#pyTitle");
  const title = (titleEl?.value || "").trim();

  if(!title){
    showAlert("bad","اكتب عنوان الدرس");
    return;
  }

  if(!Array.isArray(PY_DRAFT) || PY_DRAFT.length === 0){
    showAlert("bad","لازم تضيف على الأقل شريحة واحدة (اضغط + إضافة الشريحة)");
    return;
  }

  const slides = PY_DRAFT.map(s => ({
    title: (s.title || "").trim() || "شريحة",
    bullets: Array.isArray(s.bullets) ? s.bullets.map(x=>String(x).trim()).filter(Boolean) : [],
    code: (s.code || "").trim()
  }));

  db.pythonLessons.push({
    id: uid("py"),
    title,
    slides,
    createdAt: Date.now()
  });

  try{
    saveDB(db);
  }catch(e){
    showAlert("bad","فشل الحفظ: المتصفح امتلأ (LocalStorage). احذف ملفات كبيرة أو قلل البيانات.");
    return;
  }

  showAlert("ok","تم حفظ درس بايثون ✅");

  if(titleEl) titleEl.value = "";
  resetDraftUI();
  route();
}

function delPythonLesson(id){
  if(!confirm("حذف درس بايثون؟")) return;
  const db = loadDB();
  db.pythonLessons = db.pythonLessons.filter(l => l.id !== id);
  saveDB(db);
  showAlert("ok","تم حذف الدرس ✅");
  route();
}

/* ============================================================================
   ✅ استيراد قاعدة البيانات (يدوي فقط)
============================================================================ */
function importDB(file){
  if(!file) return;
  if(!confirm("استيراد البيانات سيستبدل البيانات الحالية على هذا الجهاز. متابعة؟")) return;

  const reader = new FileReader();
  reader.onload = () => {
    try{
      const data = JSON.parse(reader.result);

      if(!data || !data.users || !data.generations || !data.tasks || !data.taskDocs || !data.pythonLessons){
        showAlert("bad","الملف غير صالح أو ناقص بيانات.");
        return;
      }

      localStorage.setItem(LS_KEY, JSON.stringify(data));
      showAlert("ok","تم استيراد البيانات ✅");
      route();
    }catch(e){
      showAlert("bad","فشل الاستيراد: الملف ليس JSON صحيح.");
    }
  };
  reader.onerror = () => showAlert("bad","تعذر قراءة الملف");
  reader.readAsText(file, "utf-8");
}

/* ---------- Boot ---------- */
window.addEventListener("hashchange", route);
renderNav();
route();
</script>

</body>
</html>
