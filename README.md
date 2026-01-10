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
  </style>

  <!-- Firebase (CDN) -->
  <script src="https://www.gstatic.com/firebasejs/10.12.5/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.5/firebase-auth-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.5/firebase-firestore-compat.js"></script>
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
/* ======================= 1) ضع Firebase Config هنا ======================= */
const FIREBASE_CONFIG = {
  // ✅ الصق config من Firebase Console هنا:
  // apiKey: "...",
  // authDomain: "...",
  // projectId: "...",
  // storageBucket: "...",
  // messagingSenderId: "...",
  // appId: "..."
};
/* ======================================================================= */

firebase.initializeApp(FIREBASE_CONFIG);
const auth = firebase.auth();
const db = firebase.firestore();

/* ======================= الأدمن (فقط إيميل) ======================= */
const ADMIN_EMAIL = "bahaahajaj@btec.com";

/* ---------- Utilities ---------- */
const $ = (sel) => document.querySelector(sel);
const esc = (s="") => String(s)
  .replaceAll("&","&amp;").replaceAll("<","&lt;")
  .replaceAll(">","&gt;")
  .replaceAll('"',"&quot;")
  .replaceAll("'","&#039;");

function showAlert(type, msg){
  const box = $("#alertBox");
  box.className = "alert " + (type || "");
  box.innerHTML = `<div><b>${type==="ok"?"✅":"⚠️"}</b> ${esc(msg)}</div>
                   <button class="btn small dark" onclick="hideAlert()">إغلاق</button>`;
  box.classList.remove("hide");
}
function hideAlert(){ $("#alertBox").classList.add("hide"); }
function go(hash){ location.hash = hash; }

/* ---------- Auth state ---------- */
let CURRENT_USER = null;

function isAdmin(){
  return !!CURRENT_USER && (CURRENT_USER.email || "").toLowerCase() === ADMIN_EMAIL.toLowerCase();
}
function renderNav(){
  const isAuthed = !!CURRENT_USER;
  $("#loginBtn").classList.toggle("hide", isAuthed);
  $("#logoutBtn").classList.toggle("hide", !isAuthed);
  $("#adminBtn").classList.toggle("hide", !isAdmin());
}
function logout(){ auth.signOut(); }

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

  renderHome();
}

/* ======================= بيانات Firestore =======================
   collections:
   - pythonLessons: { title, createdAt }
   - pythonLessons/{lessonId}/slides: { title, bullets[], code, order, createdAt }
*/

/* ---------- HOME ---------- */
async function renderHome(){
  const root = $("#page-home");
  root.classList.remove("hide");

  const snap = await db.collection("pythonLessons").orderBy("createdAt","desc").limit(5).get();
  const lessons = snap.docs.map(d=>({ id:d.id, ...d.data() }));

  root.innerHTML = `
    <div class="card" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">الرئيسية</h1>
          <div class="muted">الدروس تُحفظ على الإنترنت — أي طالب يفتحها من أي جهاز.</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/python')">دروس بايثون</button>
        </div>
      </div>
      <div class="muted">
        ${CURRENT_USER ? `أنت مسجل دخول: <b>${esc(CURRENT_USER.email||"")}</b>` : `إذا أنت الأدمن: سجّل دخول حتى تضيف الدروس.`}
      </div>
    </div>

    <div class="card soft" style="grid-column: 1/-1;">
      <div class="cardHeader">
        <div>
          <div class="h2">آخر الدروس</div>
          <div class="muted">تضاف من لوحة التحكم.</div>
        </div>
      </div>
      <div class="list">
        ${
          lessons.length ? lessons.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">${l.createdAt ? new Date(l.createdAt.toDate ? l.createdAt.toDate() : l.createdAt).toLocaleString("ar") : ""}</div>
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
async function renderPython(){
  const root = $("#page-python");
  root.classList.remove("hide");

  const snap = await db.collection("pythonLessons").orderBy("createdAt","desc").get();
  const lessons = snap.docs.map(d=>({ id:d.id, ...d.data() }));

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">دروس بايثون</h1>
          <div class="muted">دروس على شكل برسنتيشن (شرائح).</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="list">
        ${
          lessons.length ? lessons.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">${l.createdAt ? new Date(l.createdAt.toDate ? l.createdAt.toDate() : l.createdAt).toLocaleString("ar") : ""}</div>
              </div>
              <div class="meta">
                <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
              </div>
            </div>
          `).join("") : `<div class="muted">لا يوجد دروس بعد. (الأدمن يضيف من لوحة التحكم)</div>`
        }
      </div>
    </div>
  `;
}

/* ---------- PYTHON LESSON VIEW ---------- */
async function renderPythonLesson(id){
  const root = $("#page-python-lesson");
  root.classList.remove("hide");

  const lessonDoc = await db.collection("pythonLessons").doc(id).get();
  if(!lessonDoc.exists){
    showAlert("bad","الدرس غير موجود");
    return go("#/python");
  }
  const lesson = { id: lessonDoc.id, ...lessonDoc.data() };

  const slidesSnap = await db.collection("pythonLessons").doc(id).collection("slides").orderBy("order","asc").get();
  const slides = slidesSnap.docs.map(d=>({ id:d.id, ...d.data() }));

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
                (s.bullets||[]).length ? `<ul>${(s.bullets||[]).map(b=>`<li>${esc(b)}</li>`).join("")}</ul>` : `<div class="muted">—</div>`
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
          <div class="muted">بحث داخل عناوين الدروس فقط.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <div class="form">
        <label>اكتب كلمة البحث</label>
        <input id="q" placeholder="مثال: متغيرات / print / VS Code" oninput="doSearch()">
      </div>

      <div id="searchResults" class="grid" style="margin-top:14px"></div>
    </div>
  `;
  doSearch();
}

async function doSearch(){
  const q = ($("#q")?.value || "").trim().toLowerCase();
  const out = $("#searchResults");
  if(!out) return;

  if(!q){
    out.innerHTML = `<div class="card soft" style="grid-column:1/-1"><div class="muted">اكتب كلمة للبحث…</div></div>`;
    return;
  }

  const snap = await db.collection("pythonLessons").orderBy("createdAt","desc").limit(200).get();
  const lessons = snap.docs.map(d=>({ id:d.id, ...d.data() }))
    .filter(l => (l.title||"").toLowerCase().includes(q));

  out.innerHTML = `
    <div class="card soft" style="grid-column:1/-1">
      <div class="cardHeader">
        <div class="h2">نتائج الدروس</div>
        <span class="pill">${lessons.length}</span>
      </div>
      <div class="list">
        ${
          lessons.length ? lessons.map(l=>`
            <div class="item">
              <div>
                <div class="title">${esc(l.title||"")}</div>
                <div class="sub">درس</div>
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

/* ---------- LOGIN ---------- */
function renderLogin(){
  const root = $("#page-login");
  root.classList.remove("hide");

  root.innerHTML = `
    <div class="card" style="max-width:520px;margin:0 auto;">
      <div class="cardHeader">
        <div>
          <h1 class="h1">تسجيل الدخول</h1>
          <div class="muted">الدخول فقط للأدمن حتى يضيف الدروس.</div>
        </div>
        <button class="btn ghost dark" onclick="go('#/')">رجوع</button>
      </div>

      <form class="form" onsubmit="event.preventDefault(); doLogin();">
        <label>الإيميل</label>
        <input id="email" type="email" placeholder="bahaahajaj@btec.com" required>

        <label>كلمة المرور</label>
        <input id="pass" type="password" placeholder="*****" required>

        <button class="btn" type="submit">دخول</button>

        <div class="help">
          ملاحظة: كلمة المرور ما تنكتب بالكود. لازم تكون موجودة داخل Firebase Auth.
        </div>
      </form>
    </div>
  `;
}

async function doLogin(){
  const email = ($("#email").value || "").trim();
  const pass = ($("#pass").value || "").trim();
  try{
    await auth.signInWithEmailAndPassword(email, pass);
    if(!isAdmin()){
      await auth.signOut();
      showAlert("bad","هذا الحساب ليس أدمن.");
      return;
    }
    showAlert("ok","تم تسجيل الدخول ✅");
    go("#/admin");
  }catch(e){
    showAlert("bad","فشل تسجيل الدخول. تأكد من الإيميل وكلمة المرور داخل Firebase Auth.");
  }
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

async function renderAdmin(){
  if(!requireAdminUI()) return;

  const root = $("#page-admin");
  root.classList.remove("hide");

  const snap = await db.collection("pythonLessons").orderBy("createdAt","desc").limit(10).get();
  const lessons = snap.docs.map(d=>({ id:d.id, ...d.data() }));

  root.innerHTML = `
    <div class="card">
      <div class="cardHeader">
        <div>
          <h1 class="h1">لوحة التحكم</h1>
          <div class="muted">أي درس تضيفه هنا يظهر لكل الطلاب تلقائيًا.</div>
        </div>
        <div class="row">
          <button class="btn ghost dark" onclick="go('#/')">عرض الموقع</button>
        </div>
      </div>

      <div class="alert ok">
        <div>
          <b>الأدمن:</b> ${esc(CURRENT_USER.email||"")}
          <div class="muted">الطلاب لا يحتاجون تسجيل دخول للقراءة.</div>
        </div>
      </div>
    </div>

    <div class="grid" style="margin-top:14px">
      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">إضافة درس بايثون (برسنتيشن)</div>
            <div class="muted">ضيف شرائح، بعدين احفظ الدرس.</div>
          </div>
        </div>

        <form class="form" onsubmit="event.preventDefault(); return false;">
          <label>عنوان الدرس</label>
          <input id="pyTitle" placeholder="مثال: الدرس 1 - تجهيز البيئة" required>

          <div class="split">
            <div>
              <label>عنوان الشريحة</label>
              <input id="pySlideTitle" placeholder="مثال: لماذا نجهز الكمبيوتر؟">
            </div>
            <div>
              <label>كود (اختياري)</label>
              <input id="pySlideCodeOneLine" placeholder='مثال: print("مرحبا")'>
            </div>
          </div>

          <label>نقاط الشريحة (كل سطر نقطة)</label>
          <textarea id="pySlideBullets" placeholder="اكتب نقاط...\nكل سطر = نقطة"></textarea>

          <div class="row">
            <button class="btn dark" type="button" onclick="addSlideToDraft()">+ إضافة الشريحة إلى المسودة</button>
            <span class="pill" id="draftCount">0 شريحة</span>
            <button class="btn ok" type="button" onclick="savePythonLessonOnline()">حفظ الدرس (أونلاين)</button>
          </div>

          <div class="help">نصيحة: اعمل 5-10 شرائح للدرس، وبعدها احفظ.</div>
          <div id="draftPreview" class="list" style="margin-top:10px"></div>
        </form>
      </div>

      <div class="card">
        <div class="cardHeader">
          <div>
            <div class="h2">آخر الدروس</div>
            <div class="muted">تقدر تحذف أي درس.</div>
          </div>
        </div>

        <div class="list">
          ${
            lessons.length ? lessons.map(l=>`
              <div class="item">
                <div>
                  <div class="title">${esc(l.title||"")}</div>
                  <div class="sub">${l.createdAt ? new Date(l.createdAt.toDate ? l.createdAt.toDate() : l.createdAt).toLocaleString("ar") : ""}</div>
                </div>
                <div class="meta">
                  <button class="btn small" onclick="go('#/pythonLesson/${l.id}')">فتح</button>
                  <button class="btn small danger" onclick="deleteLessonOnline('${l.id}')">حذف</button>
                </div>
              </div>
            `).join("") : `<div class="muted">لا يوجد دروس بعد.</div>`
          }
        </div>
      </div>
    </div>
  `;

  resetDraftUI();
}

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

async function savePythonLessonOnline(){
  if(!requireAdminUI()) return;

  const title = ($("#pyTitle").value||"").trim();
  if(!title){ showAlert("bad","اكتب عنوان الدرس"); return; }
  if(PY_DRAFT.length === 0){ showAlert("bad","أضف على الأقل شريحة"); return; }

  try{
    const lessonRef = await db.collection("pythonLessons").add({
      title,
      createdAt: firebase.firestore.FieldValue.serverTimestamp()
    });

    const batch = db.batch();
    PY_DRAFT.forEach((s, idx)=>{
      const slideRef = db.collection("pythonLessons").doc(lessonRef.id).collection("slides").doc();
      batch.set(slideRef, {
        title: s.title,
        bullets: s.bullets || [],
        code: s.code || "",
        order: idx + 1,
        createdAt: firebase.firestore.FieldValue.serverTimestamp()
      });
    });
    await batch.commit();

    showAlert("ok","تم حفظ الدرس ✅ وسيظهر لكل الطلاب تلقائيًا");
    $("#pyTitle").value = "";
    resetDraftUI();
    renderAdmin();
  }catch(e){
    console.error(e);
    showAlert("bad","صار خطأ بالحفظ. تأكد من Firebase config والقواعد.");
  }
}

async function deleteLessonOnline(id){
  if(!requireAdminUI()) return;
  if(!confirm("حذف الدرس؟")) return;

  try{
    const slidesSnap = await db.collection("pythonLessons").doc(id).collection("slides").get();
    const batch = db.batch();
    slidesSnap.docs.forEach(d=> batch.delete(d.ref));
    batch.delete(db.collection("pythonLessons").doc(id));
    await batch.commit();

    showAlert("ok","تم حذف الدرس ✅");
    renderAdmin();
  }catch(e){
    console.error(e);
    showAlert("bad","فشل الحذف. راجع القواعد.");
  }
}

/* ---------- Boot ---------- */
window.addEventListener("hashchange", route);
auth.onAuthStateChanged((u)=>{
  CURRENT_USER = u || null;
  renderNav();
  route();
});
</script>
</body>
</html>
