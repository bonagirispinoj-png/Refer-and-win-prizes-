<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Impact Walk | Referral Income</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: system-ui, sans-serif; background: #f0f4f8; padding-bottom: 80px; }
    .app-header {
      background: linear-gradient(135deg, #0f172a, #1e293b);
      color: white; padding: 1rem; text-align: center;
      position: sticky; top: 0; z-index: 10;
    }
    .app-header h2 { font-size: 1.3rem; }
    .app-header .bal { font-size: 1rem; margin-top: 4px; opacity: 0.9; }
    .card {
      background: white; margin: 1rem; padding: 1.2rem;
      border-radius: 1.5rem; box-shadow: 0 4px 12px rgba(0,0,0,0.06);
    }
    .card h3 { margin-bottom: 0.8rem; font-size: 1rem; color: #1e293b; }
    input {
      width: 100%; padding: 0.75rem 1rem; margin-top: 0.5rem;
      border-radius: 2rem; border: 1.5px solid #cbd5e1;
      font-size: 1rem; outline: none; background: #f8fafc;
    }
    input:focus { border-color: #16a34a; background: white; }
    .btn {
      display: block; width: 100%; padding: 0.75rem;
      margin-top: 0.6rem; border-radius: 2rem; border: none;
      font-size: 1rem; font-weight: 700; cursor: pointer;
      transition: opacity 0.2s, transform 0.1s;
    }
    .btn:active { transform: scale(0.98); }
    .btn:disabled { opacity: 0.5; cursor: not-allowed; }
    .btn-green  { background: #16a34a; color: white; }
    .btn-blue   { background: #3b82f6; color: white; }
    .btn-red    { background: #dc2626; color: white; }
    .btn-gray   { background: #e2e8f0; color: #1e293b; }
    .row { display: flex; gap: 0.5rem; }
    .row .btn { flex: 1; }
    .text-xs { font-size: 0.75rem; color: #64748b; margin-top: 0.5rem; line-height: 1.5; }
    /* ── Modal ── */
    .overlay {
      position: fixed; inset: 0;
      background: rgba(0,0,0,0.65);
      display: flex; align-items: center; justify-content: center;
      z-index: 100;
    }
    .overlay.hide { display: none; }
    .modal-box {
      background: white; width: 92%; max-width: 400px;
      padding: 1.5rem; border-radius: 1.5rem;
    }
    .modal-box h3 { text-align: center; font-size: 1.2rem; margin-bottom: 1rem; }
    .tabs { display: flex; gap: 0.5rem; margin-bottom: 1rem; }
    .tabs .btn { margin-top: 0; }
    .tab-body { display: none; }
    .tab-body.active { display: block; }
    /* ── Transactions ── */
    .tx {
      padding: 0.5rem 0.7rem; margin: 0.4rem 0;
      border-radius: 0.7rem; font-size: 0.85rem;
      border-left: 4px solid #16a34a; background: #f8fafc;
    }
    .tx.pending { border-left-color: #f59e0b; }
    /* ── Admin ── */
    .admin-card { background: #1e293b; color: white; padding: 0.6rem; margin: 0.4rem 0; border-radius: 8px; font-size: 0.82rem; }
    /* ── Toast ── */
    #toasts {
      position: fixed; bottom: 80px; left: 50%;
      transform: translateX(-50%);
      z-index: 999; width: 92%; max-width: 360px;
      display: flex; flex-direction: column; gap: 6px;
      pointer-events: none;
    }
    .toast {
      background: #0f172a; color: white;
      padding: 11px 16px; border-radius: 2rem;
      font-size: 0.88rem; text-align: center;
      box-shadow: 0 4px 14px rgba(0,0,0,0.25);
      animation: pop 3.2s ease forwards;
    }
    @keyframes pop {
      0%   { opacity:0; transform:translateY(16px); }
      12%  { opacity:1; transform:translateY(0);    }
      85%  { opacity:1; transform:translateY(0);    }
      100% { opacity:0; transform:translateY(-10px);}
    }
    /* ── Loading ── */
    #splash {
      position: fixed; inset: 0; background: #0f172a;
      color: white; display: flex; align-items: center;
      justify-content: center; font-size: 1.1rem; z-index: 200;
    }
  </style>
</head>
<body>

<!-- Splash -->
<div id="splash">⏳ Loading…</div>

<!-- Header -->
<div class="app-header">
  <h2>🏆 Impact Walk</h2>
  <div class="bal">💰 ₹<span id="hBal">0</span></div>
</div>

<!-- Main content -->
<div id="main"></div>

<!-- Auth overlay -->
<div id="authOverlay" class="overlay hide">
  <div class="modal-box">
    <h3>Welcome to Impact Walk</h3>
    <div class="tabs">
      <button class="btn btn-green" id="tabBtnLogin"  onclick="showTab('login')">Login</button>
      <button class="btn btn-gray"  id="tabBtnSignup" onclick="showTab('signup')">Sign Up</button>
    </div>

    <!-- Login -->
    <div id="tabLogin" class="tab-body active">
      <input id="lEmail" type="email"     placeholder="Email address">
      <input id="lPass"  type="password"  placeholder="Password">
      <button id="btnLogin" class="btn btn-green" onclick="doLogin()">Login</button>
    </div>

    <!-- Signup -->
    <div id="tabSignup" class="tab-body">
      <input id="sName"  type="text"      placeholder="Full Name">
      <input id="sEmail" type="email"     placeholder="Email address">
      <input id="sPass"  type="password"  placeholder="Password (min 6 chars)">
      <input id="sRef"   type="text"      placeholder="Referral Code (optional)">
      <button id="btnSignup" class="btn btn-green" onclick="doSignup()">Create Account</button>
    </div>
  </div>
</div>

<!-- Toasts -->
<div id="toasts"></div>

<!-- ═══════════════════════════════════════════════════════ SCRIPT ══ -->
<script type="module">
import { initializeApp }
  from "https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js";
import {
  getAuth, createUserWithEmailAndPassword, signInWithEmailAndPassword,
  onAuthStateChanged, signOut
} from "https://www.gstatic.com/firebasejs/10.7.1/firebase-auth.js";
import {
  getFirestore, doc, setDoc, getDoc, updateDoc, addDoc, collection,
  query, where, getDocs, serverTimestamp, increment, deleteDoc,
  runTransaction, onSnapshot, orderBy, limit, startAfter
} from "https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore.js";

// ── Firebase ────────────────────────────────────────────────────────────────
const app = initializeApp({
  apiKey:      "AIzaSyBIebPXVjzVBZl380ZCELg2LUSCLr-6QrE",
  authDomain:  "neurocoin-ntc.firebaseapp.com",
  projectId:   "neurocoin-ntc"
});
const auth = getAuth(app);
const db   = getFirestore(app);

// ── Config ──────────────────────────────────────────────────────────────────
const ADMIN_EMAIL   = "bonagirispinoj@gmail.com";
const ADMIN_WA      = "9110563921";
const REF_BONUS     = 500;
const UNLOCK_FEE    = 2000;
const MIN_WD        = 500;
const DAILY_WD_MAX  = 5000;
const UTR_COOLDOWN  = 60 * 60 * 1000; // 1 hour

// ── State ───────────────────────────────────────────────────────────────────
let CU   = null;   // currentUser (Firebase Auth)
let UD   = null;   // userData    (Firestore doc)
let unsubUser = null;
let unsubTx   = null;
let watchId   = null;
let totalDist = 0;
let lastPos   = null;
let lastT     = null;
let lastUserDoc = null;

// ── DOM helpers ──────────────────────────────────────────────────────────────
const $  = id => document.getElementById(id);
const on = (id, ev, fn) => $(id)?.addEventListener(ev, fn);

function toast(msg) {
  const t = document.createElement("div");
  t.className = "toast"; t.textContent = msg;
  $("toasts").appendChild(t);
  setTimeout(() => t.remove(), 3300);
}
function splash(show) { $("splash").style.display = show ? "flex" : "none"; }
function authModal(show) {
  $("authOverlay").classList.toggle("hide", !show);
}
function busy(btnId, yes) {
  const b = $(btnId);
  if (!b) return;
  b.disabled = yes;
  b.textContent = yes ? "Please wait…" : (btnId === "btnLogin" ? "Login" : "Create Account");
}

// ── Tab switcher ────────────────────────────────────────────────────────────
window.showTab = (tab) => {
  $("tabLogin").classList.toggle("active",  tab === "login");
  $("tabSignup").classList.toggle("active", tab === "signup");
  $("tabBtnLogin").className  = "btn " + (tab === "login"  ? "btn-green" : "btn-gray");
  $("tabBtnSignup").className = "btn " + (tab === "signup" ? "btn-green" : "btn-gray");
};

// ── URL ref prefill ─────────────────────────────────────────────────────────
const urlRef = new URLSearchParams(location.search).get("ref") || "";
if (urlRef) setTimeout(() => { if ($("sRef") && !$("sRef").value) $("sRef").value = urlRef; }, 200);

// ════════════════════════════════════════════════════════════════════════════
//  AUTH
// ════════════════════════════════════════════════════════════════════════════

// ── LOGIN ────────────────────────────────────────────────────────────────────
window.doLogin = async () => {
  const email = $("lEmail").value.trim();
  const pass  = $("lPass").value;
  if (!email || !pass) return toast("Enter email and password.");

  busy("btnLogin", true);
  try {
    const cred = await signInWithEmailAndPassword(auth, email, pass);
    // ✅ Explicitly hide modal and bootstrap UI — do NOT rely on onAuthStateChanged
    authModal(false);
    await bootUser(cred.user);
  } catch (e) {
    toast("Login failed: " + friendlyErr(e));
    busy("btnLogin", false);
  }
};

// ── SIGNUP ───────────────────────────────────────────────────────────────────
window.doSignup = async () => {
  const name  = $("sName").value.trim();
  const email = $("sEmail").value.trim();
  const pass  = $("sPass").value;
  const ref   = $("sRef").value.trim() || urlRef;

  if (!name || !email || !pass) return toast("All fields are required.");
  if (pass.length < 6)          return toast("Password must be at least 6 characters.");

  busy("btnSignup", true);
  try {
    const cred = await createUserWithEmailAndPassword(auth, email, pass);
    const uid  = cred.user.uid;

    // Resolve referrer UID
    let referredBy = null;
    if (ref) {
      const snap = await getDocs(query(collection(db, "users"), where("referralCode", "==", ref)));
      if (!snap.empty) referredBy = snap.docs[0].id;
    }

    const refCode = Math.random().toString(36).substring(2, 8).toUpperCase();

    // ✅ Write user doc FIRST, then show UI — prevents snapshot finding empty doc
    await setDoc(doc(db, "users", uid), {
      email, displayName: name,
      balance: 0, totalReferrals: 0,
      referralCode: refCode, referredBy,
      unlocked: false, bonusGiven: false,
      createdAt: serverTimestamp()
    });

    toast("Account created! Welcome 🎉");
    authModal(false);
    await bootUser(cred.user);
  } catch (e) {
    toast("Signup failed: " + friendlyErr(e));
    busy("btnSignup", false);
  }
};

// ── LOGOUT ───────────────────────────────────────────────────────────────────
window.doLogout = async () => {
  if (unsubUser) { unsubUser(); unsubUser = null; }
  if (unsubTx)   { unsubTx();   unsubTx   = null; }
  if (watchId)   { navigator.geolocation.clearWatch(watchId); watchId = null; }
  CU = null; UD = null;
  $("hBal").textContent = "0";
  $("main").innerHTML   = "";
  await signOut(auth);
  showTab("login");
  authModal(true);
};

// ── onAuthStateChanged: handles page reload / already-logged-in ───────────────
// Only used for auto-login on refresh, NOT for modal control after user action
onAuthStateChanged(auth, async (user) => {
  splash(false);
  if (user && !CU) {
    // Returning user (page refresh) — CU is null so bootUser not already called
    authModal(false);
    await bootUser(user);
  } else if (!user) {
    authModal(true);
  }
});

// ── Boot: set CU, load user doc, start real-time listener ───────────────────
async function bootUser(user) {
  CU = user;

  // Fetch user doc once first to make sure it exists
  const snap = await getDoc(doc(db, "users", user.uid));
  if (!snap.exists()) {
    toast("User profile not found. Please sign up.");
    await signOut(auth);
    authModal(true);
    return;
  }

  UD = snap.data();
  UD.uid = user.uid;
  $("hBal").textContent = UD.balance || 0;
  renderApp();

  // Start real-time listeners
  startUserListener(user.uid);
  startTxListener(user.uid);
}

// ── Real-time user doc listener ──────────────────────────────────────────────
function startUserListener(uid) {
  if (unsubUser) unsubUser();
  unsubUser = onSnapshot(
    doc(db, "users", uid),
    snap => {
      if (!snap.exists()) return;
      UD = snap.data(); UD.uid = uid;
      $("hBal").textContent = UD.balance || 0;
      // Only re-render cards that need updating (balance, unlock status)
      const balEl = $("uBalVal");
      if (balEl) balEl.textContent = "₹" + (UD.balance || 0);
      const refEl = $("unlockSection");
      if (refEl) renderUnlockSection();
    },
    err => console.error("User listener:", err)
  );
}

// ── Transaction listener ────────────────────────────────────────────────────
function startTxListener(uid) {
  if (unsubTx) unsubTx();
  const u1 = onSnapshot(
    query(collection(db, "withdrawals"),          where("userId", "==", uid)),
    () => loadTxHistory(uid)
  );
  const u2 = onSnapshot(
    query(collection(db, "referralTransactions"), where("userId", "==", uid)),
    () => loadTxHistory(uid)
  );
  unsubTx = () => { u1(); u2(); };
  loadTxHistory(uid);
}

async function loadTxHistory(uid) {
  try {
    const [ws, rs] = await Promise.all([
      getDocs(query(collection(db, "withdrawals"),          where("userId", "==", uid))),
      getDocs(query(collection(db, "referralTransactions"), where("userId", "==", uid)))
    ]);
    const all = [];
    ws.forEach(d => { const x = d.data(); all.push({ ...x, kind: "wd",  ts: x.createdAt?.toDate() || new Date(0) }); });
    rs.forEach(d => { const x = d.data(); all.push({ ...x, kind: "ref", ts: x.createdAt?.toDate() || new Date(0) }); });
    all.sort((a, b) => b.ts - a.ts);

    const el = $("txList");
    if (!el) return;
    if (!all.length) { el.innerHTML = "<p style='color:#94a3b8;font-size:0.85rem'>No transactions yet.</p>"; return; }

    el.innerHTML = all.map(x => {
      const d   = x.ts.getTime() ? x.ts.toLocaleDateString() : "Pending";
      const cls = x.kind === "wd" && x.status === "pending" ? "tx pending" : "tx";
      if (x.kind === "wd") return `<div class="${cls}">💸 Withdrawal ₹${x.amount} — <b>${(x.status||"").toUpperCase()}</b> · ${d}</div>`;
      return `<div class="${cls}">🤝 Referral Bonus ₹${x.amount} — from ${x.fromUser || "user"} · ${d}</div>`;
    }).join("");
  } catch (e) { console.error("TX load:", e); }
}

// ════════════════════════════════════════════════════════════════════════════
//  MAIN APP RENDER
// ════════════════════════════════════════════════════════════════════════════
function renderApp() {
  const isAdmin = UD.email === ADMIN_EMAIL;

  $("main").innerHTML = `
    <!-- Balance -->
    <div class="card">
      <h3>💰 Balance</h3>
      <p id="uBalVal" style="font-size:2rem;font-weight:800;color:#16a34a;margin:4px 0">₹${UD.balance || 0}</p>
      <p style="font-size:0.9rem;color:#475569">Referrals: ${UD.totalReferrals || 0} &nbsp;|&nbsp; Earned: ₹${(UD.totalReferrals||0)*REF_BONUS}</p>
    </div>

    <!-- Unlock -->
    <div class="card" id="unlockSection"></div>

    <!-- Walk -->
    <div class="card">
      <h3>🚶 Walk Tracker (Free GPS)</h3>
      <div style="font-size:0.9rem;color:#334155;line-height:2">
        📍 Distance: <b><span id="wDist">0.000</span> km</b><br>
        👣 Steps: <b><span id="wSteps">0</span></b><br>
        🔥 Calories: <b><span id="wCal">0</span></b>
      </div>
      <div class="row" style="margin-top:0.7rem">
        <button class="btn btn-green" onclick="startWalk()">▶ Start</button>
        <button class="btn btn-red"   onclick="stopWalk()">⏹ Stop</button>
      </div>
      <p class="text-xs">GPS only — no earnings. Anti-cheat active (max 4.5 m/s).</p>
    </div>

    <!-- Withdraw -->
    <div class="card">
      <h3>💸 Withdraw</h3>
      <input id="wdAmt" type="number" placeholder="Amount (min ₹${MIN_WD})">
      <input id="wdUpi" type="text"   placeholder="Your UPI ID">
      <button class="btn btn-green" onclick="doWithdraw()">Request Withdrawal</button>
      <p class="text-xs">Admin approves within 24–48h. Daily max ₹${DAILY_WD_MAX}.</p>
    </div>

    <!-- Prizes -->
    <div class="card">
      <h3>🏆 Top Referrer Prizes</h3>
      <p>🥇 1st — ₹1 Crore</p>
      <p>🥈 2nd — ₹75 Lakhs</p>
      <p>🥉 3rd — ₹50 Lakhs</p>
      <p class="text-xs">No time limit. Refer more, earn more!</p>
    </div>

    <!-- Transactions -->
    <div class="card">
      <h3>📋 Transaction History</h3>
      <div id="txList"><p style="color:#94a3b8;font-size:0.85rem">Loading…</p></div>
    </div>

    <!-- Admin -->
    ${isAdmin ? `
    <div class="card" style="background:#1e293b;color:white">
      <h3 style="color:white">👨‍💼 Admin Panel</h3>
      <div id="adminContent">Loading…</div>
      <div id="adminMore" style="text-align:center;margin-top:0.8rem"></div>
    </div>` : ""}

    <!-- Logout -->
    <div class="card">
      <button class="btn btn-red" onclick="doLogout()">Logout</button>
    </div>
  `;

  renderUnlockSection();
  if (isAdmin) loadAdmin();
}

function renderUnlockSection() {
  const el = $("unlockSection");
  if (!el || !UD) return;
  if (UD.unlocked) {
    const link = `${location.origin}${location.pathname}?ref=${UD.referralCode}`;
    el.innerHTML = `
      <h3>🔓 Referral Link</h3>
      <p style="margin-bottom:0.5rem">✅ Active! Code: <b>${UD.referralCode}</b></p>
      <div class="row">
        <input id="refLink" readonly value="${link}" style="font-size:0.78rem">
        <button class="btn btn-blue" onclick="copyRef()" style="min-width:70px">Copy</button>
      </div>
      <p class="text-xs">Share this link. Earn ₹${REF_BONUS} for each friend who pays ₹${UNLOCK_FEE} and unlocks.</p>`;
  } else {
    el.innerHTML = `
      <h3>🔒 Unlock Referral Link</h3>
      <p style="color:#475569;font-size:0.9rem;margin-bottom:0.3rem">Pay ₹${UNLOCK_FEE} to get your referral link.</p>
      <p class="text-xs" style="margin-bottom:0.5rem">UPI: <b>bonagirispinoj-1@oksbi</b></p>
      <input id="utrInput" placeholder="Enter UTR (8–20 alphanumeric)">
      <button class="btn btn-green" onclick="doSubmitUTR()">Submit UTR</button>
      <p class="text-xs">Admin approves within 24h.</p>`;
  }
}

// ════════════════════════════════════════════════════════════════════════════
//  FEATURES
// ════════════════════════════════════════════════════════════════════════════

// ── Copy ref link ────────────────────────────────────────────────────────────
window.copyRef = () => {
  const inp = $("refLink"); if (!inp) return;
  inp.select();
  navigator.clipboard.writeText(inp.value)
    .then(() => toast("Link copied! 📋"))
    .catch(() => { document.execCommand("copy"); toast("Link copied!"); });
};

// ── UTR submit ───────────────────────────────────────────────────────────────
window.doSubmitUTR = async () => {
  if (!CU) return;
  const utr = ($("utrInput")?.value || "").trim();
  if (!/^[A-Z0-9]{8,20}$/i.test(utr)) return toast("UTR must be 8–20 letters/numbers.");

  try {
    // Duplicate check
    const dup = await getDocs(query(collection(db, "payments"), where("utr", "==", utr)));
    if (!dup.empty) return toast("This UTR is already submitted.");

    // Rate-limit: fetch user's payments, find latest timestamp in JS
    const prev = await getDocs(query(collection(db, "payments"), where("userId", "==", CU.uid)));
    let latest = 0;
    prev.forEach(d => { const t = d.data().createdAt?.toDate()?.getTime() || 0; if (t > latest) latest = t; });
    if (latest && Date.now() - latest < UTR_COOLDOWN) return toast("Please wait 1 hour before re-submitting UTR.");

    await addDoc(collection(db, "payments"), {
      userId: CU.uid, email: UD.email, utr,
      amount: UNLOCK_FEE, status: "pending", createdAt: serverTimestamp()
    });

    const msg = `💰 Payment Request\nUser: ${UD.email}\nUTR: ${utr}\nAmount: ₹${UNLOCK_FEE}`;
    window.open(`https://wa.me/${ADMIN_WA}?text=${encodeURIComponent(msg)}`, "_blank");
    toast("UTR submitted! Admin will verify within 24h.");
    if ($("utrInput")) $("utrInput").value = "";
  } catch (e) { toast("Error: " + e.message); }
};

// ── Withdrawal ───────────────────────────────────────────────────────────────
window.doWithdraw = async () => {
  if (!CU) return;
  const amt = parseFloat($("wdAmt")?.value);
  const upi = ($("wdUpi")?.value || "").trim();

  if (isNaN(amt) || amt < MIN_WD)    return toast(`Minimum withdrawal ₹${MIN_WD}.`);
  if (amt > (UD.balance || 0))       return toast("Insufficient balance.");
  if (!upi)                          return toast("Enter your UPI ID.");

  try {
    // Pending check
    const pend = await getDocs(query(collection(db, "withdrawals"), where("userId","==",CU.uid), where("status","==","pending")));
    if (!pend.empty) return toast("You have a pending withdrawal already.");

    // Daily limit
    const today = new Date(); today.setHours(0,0,0,0);
    const allWd = await getDocs(query(collection(db, "withdrawals"), where("userId", "==", CU.uid)));
    let todayTotal = 0;
    allWd.forEach(d => {
      const x = d.data();
      if (x.createdAt?.toDate() >= today) todayTotal += x.amount || 0;
    });
    if (todayTotal + amt > DAILY_WD_MAX) return toast(`Daily limit is ₹${DAILY_WD_MAX}.`);

    await addDoc(collection(db, "withdrawals"), {
      userId: CU.uid, email: UD.email, amount: amt, upi,
      status: "pending", createdAt: serverTimestamp()
    });
    toast("Withdrawal request submitted! ✅");
    if ($("wdAmt")) $("wdAmt").value = "";
    if ($("wdUpi")) $("wdUpi").value = "";
  } catch (e) { toast("Error: " + e.message); }
};

// ── Walk tracker ─────────────────────────────────────────────────────────────
function haversine(la1, lo1, la2, lo2) {
  const R = 6371, r = x => x * Math.PI / 180;
  const a = Math.sin(r(la2-la1)/2)**2 + Math.cos(r(la1))*Math.cos(r(la2))*Math.sin(r(lo2-lo1)/2)**2;
  return R * 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));
}

window.startWalk = () => {
  if (watchId) return toast("Walk already active.");
  if (!navigator.geolocation) return toast("GPS not available on this device.");
  totalDist = 0; lastPos = null; lastT = null;
  if ($("wDist"))  $("wDist").textContent  = "0.000";
  if ($("wSteps")) $("wSteps").textContent = "0";
  if ($("wCal"))   $("wCal").textContent   = "0";

  watchId = navigator.geolocation.watchPosition(
    pos => {
      const now = Date.now();
      const la = pos.coords.latitude, lo = pos.coords.longitude;
      if (lastPos && lastT) {
        const d   = haversine(lastPos[0], lastPos[1], la, lo);
        const sec = (now - lastT) / 1000;
        if (sec > 0 && d < 0.3 && (d * 1000 / sec) < 4.5) {
          totalDist += d;
          if ($("wDist"))  $("wDist").textContent  = totalDist.toFixed(3);
          if ($("wSteps")) $("wSteps").textContent = Math.round(totalDist * 1300);
          if ($("wCal"))   $("wCal").textContent   = Math.round(totalDist * 100);
        }
      }
      lastPos = [la, lo]; lastT = now;
    },
    err => toast("GPS: " + err.message),
    { enableHighAccuracy: true }
  );
  toast("Walk started! 🚶 GPS tracking active.");
};

window.stopWalk = () => {
  if (!watchId) return toast("No active walk.");
  navigator.geolocation.clearWatch(watchId);
  watchId = null;
  toast(`Walk done! 🎉 ${totalDist.toFixed(3)} km · ${Math.round(totalDist*1300)} steps`);
};

// ════════════════════════════════════════════════════════════════════════════
//  ADMIN
// ════════════════════════════════════════════════════════════════════════════
async function loadAdmin() {
  const div = $("adminContent");
  if (!div || UD.email !== ADMIN_EMAIL) return;
  div.innerHTML = "Loading…";

  try {
    const uSnap = await getDocs(query(collection(db, "users"), orderBy("email"), limit(20)));
    lastUserDoc = uSnap.docs[uSnap.docs.length - 1];

    let html = "<b>👥 Users</b><br>";
    uSnap.forEach(d => {
      const u = d.data();
      html += `<div class="admin-card">
        <b>${u.displayName || u.email}</b><br>
        ₹${u.balance} | Refs: ${u.totalReferrals||0} | ${u.unlocked?"✅":"🔒"} | ${u.referralCode}
        <div class="row" style="margin-top:5px">
          <button class="btn btn-blue"  onclick="aAdd('${d.id}')">+₹</button>
          <button class="btn btn-red"   onclick="aDel('${d.id}')">Del</button>
        </div>
      </div>`;
    });

    const pPay = await getDocs(query(collection(db, "payments"),    where("status","==","pending")));
    html += "<br><b>💳 Pending Payments</b><br>";
    if (pPay.empty) html += "<p style='color:#94a3b8;font-size:0.8rem'>None.</p>";
    pPay.forEach(d => {
      const p = d.data();
      html += `<div class="admin-card">
        ${p.email} · UTR: <b>${p.utr}</b> · ₹${p.amount}
        <div class="row" style="margin-top:5px">
          <button class="btn btn-green" onclick="aAppPay('${d.id}','${p.userId}')">✅ Approve</button>
          <button class="btn btn-red"   onclick="aRejPay('${d.id}')">❌ Reject</button>
        </div>
      </div>`;
    });

    const pWd = await getDocs(query(collection(db, "withdrawals"),  where("status","==","pending")));
    html += "<br><b>💸 Pending Withdrawals</b><br>";
    if (pWd.empty) html += "<p style='color:#94a3b8;font-size:0.8rem'>None.</p>";
    pWd.forEach(d => {
      const w = d.data();
      html += `<div class="admin-card">
        ₹${w.amount} → ${w.upi}<br>${w.email || w.userId}
        <div class="row" style="margin-top:5px">
          <button class="btn btn-green" onclick="aAppWd('${d.id}','${w.userId}',${w.amount})">✅ Approve</button>
          <button class="btn btn-red"   onclick="aRejWd('${d.id}')">❌ Reject</button>
        </div>
      </div>`;
    });

    div.innerHTML = html;
    $("adminMore").innerHTML = uSnap.docs.length === 20
      ? `<button class="btn btn-blue" style="width:auto;padding:0.5rem 1.5rem" onclick="aLoadMore()">Load More</button>` : "";

  } catch (e) {
    div.innerHTML = `<p style="color:#fca5a5">Error: ${e.message}</p>`;
  }
}

window.aLoadMore = async () => {
  if (!lastUserDoc) return;
  const snap = await getDocs(query(collection(db,"users"), orderBy("email"), startAfter(lastUserDoc), limit(20)));
  if (snap.empty) { $("adminMore").innerHTML = ""; return; }
  lastUserDoc = snap.docs[snap.docs.length-1];
  let html = "";
  snap.forEach(d => {
    const u = d.data();
    html += `<div class="admin-card"><b>${u.displayName||u.email}</b> · ₹${u.balance}
      <div class="row" style="margin-top:5px">
        <button class="btn btn-blue" onclick="aAdd('${d.id}')">+₹</button>
        <button class="btn btn-red"  onclick="aDel('${d.id}')">Del</button>
      </div></div>`;
  });
  $("adminContent").insertAdjacentHTML("beforeend", html);
  if (snap.docs.length < 20) $("adminMore").innerHTML = "";
};

window.aAdd = async uid => {
  const amt = prompt("Add balance (₹):"); if (!amt || isNaN(amt)) return;
  await updateDoc(doc(db,"users",uid), { balance: increment(Number(amt)) });
  toast("Balance added ✅"); loadAdmin();
};
window.aDel = async uid => {
  if (!confirm("Delete user permanently?")) return;
  await deleteDoc(doc(db,"users",uid));
  toast("User deleted."); loadAdmin();
};
window.aAppPay = async (pid, uid) => {
  try {
    const uRef  = doc(db,"users",uid);
    const uSnap = await getDoc(uRef);
    if (!uSnap.exists()) return toast("User not found.");
    const u = uSnap.data();
    if (u.unlocked) return toast("Already unlocked.");

    // Run transaction for atomic update
    await runTransaction(db, async tx => {
      tx.update(uRef, { unlocked: true });
      tx.update(doc(db,"payments",pid), { status:"approved", at: serverTimestamp() });
      if (u.referredBy && !u.bonusGiven) {
        const rRef = doc(db,"users",u.referredBy);
        const rSnap = await tx.get(rRef);
        if (rSnap.exists()) {
          tx.update(rRef, { balance: increment(REF_BONUS), totalReferrals: increment(1) });
          tx.update(uRef, { bonusGiven: true });
        }
      }
    });
    // addDoc must be outside runTransaction
    if (u.referredBy && !u.bonusGiven) {
      await addDoc(collection(db,"referralTransactions"), {
        userId: u.referredBy, amount: REF_BONUS,
        fromUser: u.email, createdAt: serverTimestamp()
      });
    }
    toast("Payment approved & user unlocked ✅"); loadAdmin();
  } catch (e) { toast("Error: " + e.message); }
};
window.aRejPay = async pid => {
  await updateDoc(doc(db,"payments",pid), { status:"rejected" });
  toast("Payment rejected."); loadAdmin();
};
window.aAppWd = async (wid, uid, amt) => {
  try {
    await runTransaction(db, async tx => {
      const uRef  = doc(db,"users",uid);
      const uSnap = await tx.get(uRef);
      if (!uSnap.exists())              throw new Error("User not found.");
      if (uSnap.data().balance < amt)   throw new Error("User has insufficient balance.");
      tx.update(uRef, { balance: increment(-amt) });
      tx.update(doc(db,"withdrawals",wid), { status:"approved", at: serverTimestamp() });
    });
    toast("Withdrawal approved ✅"); loadAdmin();
  } catch (e) { toast("Error: " + e.message); }
};
window.aRejWd = async wid => {
  await updateDoc(doc(db,"withdrawals",wid), { status:"rejected" });
  toast("Withdrawal rejected."); loadAdmin();
};

// ── Friendly Firebase error messages ────────────────────────────────────────
function friendlyErr(e) {
  const map = {
    "auth/user-not-found":       "No account with this email.",
    "auth/wrong-password":       "Incorrect password.",
    "auth/invalid-email":        "Invalid email address.",
    "auth/email-already-in-use": "Email already registered. Please login.",
    "auth/too-many-requests":    "Too many attempts. Try again later.",
    "auth/network-request-failed": "Network error. Check your connection.",
    "auth/invalid-credential":   "Wrong email or password."
  };
  return map[e.code] || e.message;
}
</script>
</body>
</html>
