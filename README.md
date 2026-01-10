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
   Single-file Platform (LocalStorage)
============================================================================ */

const LS_KEY = "btec_platform_v4";
const SESSION_KEY = "btec_session_v4";
const DEVICE_KEY = "btec_device_v1";
const PROGRESS_KEY = "btec_progress_v4";

// ✅✅ جديد: رابط ملف الدروس على نفس الموقع (ارفع btec-backup.json بجانب index.html)
const BACKUP_FILE_URL = "./btec-backup.json";

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

    <!-- ✅✅✅ جديد: صندوق تحميل/استيراد ملف الدروس في الرئيسية -->
    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">📌 لإظهار الدروس على أي جهاز</div>
          <div class="muted">
            هذه المنصة تعمل بدون سيرفر، لذلك الدروس لا تظهر تلقائيًا على الأجهزة الجديدة.
            <br>
            <b>عشان تظهر الدروس: حمّل ملف الدروس ثم استورده مرة واحدة فقط.</b>
          </div>
        </div>
      </div>

      <div class="row">
        <a class="btn ok" href="${BACKUP_FILE_URL}" download>تحميل ملف الدروس</a>

        <label class="btn ghost" style="cursor:pointer;">
          استيراد ملف الدروس
          <input type="file" accept="application/json" style="display:none"
                 onchange="importDB(this.files[0])">
        </label>
      </div>

      <div class="help" style="margin-top:8px">
        إذا زر التحميل ما اشتغل: الأدمن لازم يرفع ملف <b>btec-backup.json</b> على الموقع (نفس مكان index.html).
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

/* باقي الكود كما هو من نسختك (لم يتم حذفه) */
/* ---------- (مهم) لأنك أرسلت كود قديم طويل، أبقيت الجزء المهم للتعديل فقط ---------- */

/* ============================================================================
   ✅✅✅ الاستيراد والتصدير (موجودة عندك في القديم)
============================================================================ */

function exportDB(){
  const db = loadDB();
  const blob = new Blob([JSON.stringify(db, null, 2)], { type: "application/json" });
  const a = document.createElement("a");
  a.href = URL.createObjectURL(blob);
  a.download = "btec-backup.json";
  document.body.appendChild(a);
  a.click();
  a.remove();
  URL.revokeObjectURL(a.href);
  showAlert("ok","تم تصدير ملف النسخة الاحتياطية ✅");
}

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
