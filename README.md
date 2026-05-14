<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Student Saver</title>

<style>
:root{
  --primary:#6A0DAD;
  --primary-dark:#4A0878;
  --bg: linear-gradient(145deg,#8B1FE8,#5A08A0,#2D0455);
  --card:#FFFFFF;
  --text:#1A0336;
  --muted:#7A5A9E;
}

body{
  margin:0;
  font-family:Arial, sans-serif;
  background:var(--bg);
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
}

/* SCREEN */
.screen{
  width:360px;
  background:var(--card);
  color:var(--text);
  border-radius:20px;
  padding:25px;
  box-shadow:0 20px 50px rgba(0,0,0,0.3);
  display:none;
  overflow-y:auto;
  max-height:90vh;
}

.screen.active{
  display:block;
}

h1, h2{
  color:var(--primary);
  text-align:center;
}

.center{
  text-align:center;
  color:var(--muted);
}

p{
  font-size:14px;
  color:var(--muted);
  line-height:1.5;
}

ul{
  font-size:14px;
  color:var(--muted);
}

/* BUTTON */
button{
  width:100%;
  padding:12px;
  border:none;
  border-radius:12px;
  background:var(--primary);
  color:white;
  font-weight:bold;
  margin-top:15px;
  cursor:pointer;
}

button:hover{
  background:var(--primary-dark);
}
</style>

</head>

<body>

<!-- SCREEN 1 -->
<div class="screen active" id="screen1">
  <h1>Student Saver</h1>
  <p class="center">
    Mobile Application<br><br>
    Helping Students Save More and Supporting Local Businesses
  </p>
  <button onclick="nextScreen(2)">Next</button>
</div>

<!-- SCREEN 2 -->
<div class="screen" id="screen2">
  <h2>Group 1</h2>
  <ul>
    <li>Amarante, Junel</li>
    <li>Gonzales, Anne Thaddeus</li>
    <li>Gonzales, John Kervin</li>
    <li>Rodrigo, Sheene A.</li>
    <li>San Juan, Hamir A.</li>
    <li>Valmonte, Kenji</li>
    <li>Valmonte, Ma. Katrina</li>
  </ul>

  <h2>Technical Assistance</h2>
  <ul>
    <li>Caranay, John Reinier P.</li>
    <li>Regalado, Wendel Mark G.</li>
  </ul>

  <button onclick="nextScreen(3)">Next</button>
</div>

<!-- SCREEN 3 -->
<div class="screen" id="screen3">
  <h2>Brief Description</h2>

  <p>
    Student Saver is a mobile application designed for students of Nueva Ecija University of Science and Technology that helps them find affordable products, student discounts, and budget-friendly services near the campus. The app connects students with local businesses such as food stalls, printing shops, cafés, and school supply stores that offer exclusive student deals.
  </p>

  <p>
    The main target users are students who want to manage their daily expenses wisely, as well as small business owners who want to promote their products and services to the student community.
  </p>

  <p>
    Student Saver solves the common problem of limited student budgets by making it easier to discover low-cost options for everyday needs. At the same time, it helps local businesses gain visibility and attract more student customers.
  </p>

  <p>
    This app is useful because it saves money, saves time, supports local businesses, and creates a stronger campus community through smart and accessible digital deals.
  </p>

  <!-- ACTION BUTTONS -->
  <button onclick="goToApp()">Continue to App</button>
  <button onclick="nextScreen(1)">Back to Start</button>
</div>

<script>
function nextScreen(num){
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById('screen'+num).classList.add('active');
}

function goToApp(){
  alert("Welcome to Student Saver App!");
  // You can replace this with:
  // window.location.href = "home.html";
}
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Student Saver Combined App</title>

<style>
*{box-sizing:border-box;font-family:Arial,sans-serif}
:root{
  --bg:#0d0318;
  --app:#150722;
  --panel:#221033;
  --panel-2:#3a1d5e;
  --line:#553179;
  --text:#ffffff;
  --muted:#cab9ec;
  --soft:#c9b2ff;
  --accent:#9957ff;
  --accent-2:#8438f5;
  --accent-3:#d8c8ff;
  --pink:#ff72b6;
  --gold:#ffd36a;
  --danger:#ff5f8f;
}
body{
  margin:0;
  color:var(--text);
  background:
    radial-gradient(circle at 52% 42%,rgba(158,116,255,.5),transparent 34%),
    radial-gradient(circle at 37% 48%,rgba(122,82,207,.42),transparent 36%),
    linear-gradient(90deg,#0d0318 0%,#1a092b 29%,#56349a 43%,#8c68dc 50%,#56349a 57%,#1a092b 71%,#0d0318 100%);
}
.view{display:none;min-height:100vh}
.view.active{display:block}
.login-stage{min-height:100vh;width:min(980px,100%);margin:auto;display:grid;place-items:center;position:relative;padding:28px 16px}
.login-brand{position:absolute;top:28px;left:34px;display:flex;align-items:center;gap:12px;font-weight:900}
.logo{width:42px;height:42px;border-radius:14px;background:#fff;color:var(--accent-2);display:flex;align-items:center;justify-content:center;font-weight:900;box-shadow:0 14px 26px rgba(0,0,0,.22)}
.auth-card{width:min(360px,92vw);min-height:640px;padding:56px 34px 34px;border-radius:34px;position:relative;overflow:hidden;background:radial-gradient(circle at 99% 31%,rgba(201,178,255,.18) 0 18%,transparent 19%),radial-gradient(circle at 2% 79%,rgba(201,178,255,.12) 0 15%,transparent 16%),linear-gradient(180deg,#432268 0%,#28113f 38%,#1a082c 100%);box-shadow:0 34px 75px rgba(19,8,34,.54),inset 0 1px 0 rgba(255,255,255,.12)}
.auth-card h1{font-size:43px;line-height:.97;margin:0 0 28px}
.tab-radio{position:absolute;opacity:0;pointer-events:none}
.tabs{display:grid;grid-template-columns:1fr 1fr;gap:8px;width:210px;margin:0 auto 14px;font-size:12px;font-weight:900;color:rgba(255,255,255,.55);text-align:center}
.tabs label{padding:8px 0;border-bottom:2px solid transparent;cursor:pointer}
#student-tab:checked ~ .tabs label[for="student-tab"],#business-tab:checked ~ .tabs label[for="business-tab"]{color:#fff;border-color:#fff}
.form-panel{display:none}
#student-tab:checked ~ .forms .student-form,#business-tab:checked ~ .forms .business-form{display:block}
.input-group{position:relative;margin-bottom:14px}
.input-group svg{width:17px;height:17px;position:absolute;top:50%;left:18px;color:#4b2a72;transform:translateY(-50%);pointer-events:none}
.auth-card input{width:100%;height:50px;border:0;border-radius:999px;padding:0 18px 0 50px;background:#c9b2ff;color:#351757;font-size:14px;font-weight:800;outline:none}
.auth-card input::placeholder{color:#4d3372}
.login-button{width:100%;height:51px;margin-top:12px;border:0;border-radius:999px;color:#fff;background:linear-gradient(135deg,#a15cff,#8438f5);box-shadow:0 16px 28px rgba(132,56,245,.38);font-size:15px;font-weight:900;cursor:pointer}
.auth-links{display:flex;justify-content:space-between;margin:14px 4px 44px;font-size:12px;font-weight:800}
.auth-links a,.socials a{color:rgba(255,255,255,.75);text-decoration:none}
.socials{display:grid;gap:20px;margin-top:38px;padding-left:42px}
.socials a{display:inline-flex;align-items:center;gap:13px;font-size:14px;font-weight:900}
.socials span{width:23px;height:23px;display:grid;place-items:center;border-radius:7px;color:#d7c7ff;background:rgba(255,255,255,.12);font-size:18px}
.login-credit{position:absolute;right:34px;bottom:24px;font-size:15px;font-weight:900;font-style:italic}
.app{max-width:430px;margin:auto;min-height:100vh;padding-bottom:92px;background:radial-gradient(circle at 96% 22%,rgba(201,178,255,.16),transparent 28%),radial-gradient(circle at 0% 74%,rgba(201,178,255,.12),transparent 24%),linear-gradient(180deg,#26113d,#160824 55%,#0d0318);box-shadow:0 0 70px rgba(12,5,24,.5)}
.hero{padding:28px 18px 24px;background:radial-gradient(circle at 85% 20%,rgba(201,178,255,.26),transparent 32%),linear-gradient(180deg,#56349a,#26113d 88%);border-bottom:1px solid rgba(200,173,255,.18)}
.brand-row{display:flex;align-items:center;justify-content:space-between;gap:12px;margin-bottom:18px}
.brand-left{display:flex;align-items:center;gap:12px;font-weight:900}
.logout-btn{width:auto;padding:9px 13px;margin:0;border-radius:999px;background:#382052;color:#fff;box-shadow:none;font-size:12px}
.hero h1{margin:0;font-size:31px;line-height:1}
.hero p{color:#efe8ff;margin:7px 0 0;line-height:1.45}
.app-section,.student-section{display:none}
.app-section.active,.student-section.active{display:block}
.card,.promo-card,.tool-tile,.deal-card{background:rgba(36,17,56,.96);border:1px solid rgba(200,173,255,.18);border-radius:24px;margin:14px 18px;padding:16px;box-shadow:0 15px 32px rgba(10,4,20,.2)}
.card p,.promo-card p,.tool-tile p,.deal-card p{color:var(--muted);font-size:14px;line-height:1.45}
.card h2,.card h3{margin:0 0 8px}
.small{font-size:12px;color:var(--accent-3);text-transform:uppercase;letter-spacing:1px;font-weight:bold}
.badge{display:inline-block;background:#d8c7ff;color:#2a1642;font-weight:bold;border-radius:20px;padding:6px 12px;font-size:12px}
input,select,textarea{width:100%;background:#c7b2ff;color:#2a1642;border:0;border-radius:18px;padding:14px 15px;margin:7px 0 12px;font-size:15px;font-weight:700;outline:none}
input::placeholder,textarea::placeholder{color:#4d3372}
input:focus,select:focus,textarea:focus{box-shadow:0 0 0 4px rgba(199,178,255,.18)}
textarea{height:78px;resize:none}
button{width:100%;border:0;border-radius:25px;background:linear-gradient(135deg,var(--accent),var(--accent-2));color:#fff;font-weight:bold;padding:14px;margin-top:6px;cursor:pointer;box-shadow:0 14px 26px rgba(124,58,237,.26)}
button.dark{background:#382052;color:white;box-shadow:none}
button.red{background:var(--danger);color:white;box-shadow:none}
.grid,.creative-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin:14px 18px}
.stat{background:rgba(36,17,56,.96);border:1px solid rgba(200,173,255,.18);border-radius:20px;padding:16px}
.stat h2{margin:0;color:#d8c7ff;font-size:26px}.stat p{margin:4px 0 0;color:var(--muted);font-size:13px}
.feature-hero,.home-hero,.promo-studio,.growth-hero,.account-cover,.more-hero{margin:14px 18px;padding:22px;border-radius:30px;background:radial-gradient(circle at top right,rgba(200,173,255,.28),transparent 45%),linear-gradient(135deg,#361b5d,#1d0d32);border:1px solid rgba(200,173,255,.2)}
.feature-hero h2,.home-hero h2,.promo-studio h2,.growth-hero h2,.more-hero h2{font-size:27px;margin:6px 0}
.feature-hero p,.home-hero p,.promo-studio p,.growth-hero p,.more-hero p{color:#eee6ff}
.glow{box-shadow:0 0 26px rgba(147,84,255,.32)}
.mini-chart{height:90px;display:flex;gap:8px;align-items:end;margin-top:15px}
.mini-chart span{flex:1;background:linear-gradient(180deg,#c8adff,#7c3aed);border-radius:12px 12px 0 0}
.quick-actions,.date-row{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin:14px 18px}
.store-avatar{width:76px;height:76px;border-radius:24px;background:#d8c7ff;color:#2a1642;display:flex;align-items:center;justify-content:center;font-size:28px;font-weight:bold;margin-bottom:12px}
.promo-card{overflow:hidden;padding:0}.promo-card img{width:100%;height:170px;object-fit:cover;display:block;filter:saturate(1.05)}
.promo-content{padding:16px}.promo-content h3{margin:10px 0 6px;font-size:20px}
.promo-details{display:grid;gap:6px;margin:12px 0;color:#e6dcff;font-size:13px}
.row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px}.row button{font-size:12px;padding:11px}
.tool-icon{display:inline-flex;width:42px;height:42px;border-radius:14px;background:#d8c7ff;color:#2a1642;align-items:center;justify-content:center;font-weight:bold}
.more-hero{display:flex;justify-content:space-between;gap:16px;align-items:center}
.studio-ring{width:68px;height:68px;border-radius:50%;border:3px solid #c8adff;display:flex;align-items:center;justify-content:center;color:#f4eeff;font-weight:bold}
.suki-pass{margin:14px 18px;padding:18px;border-radius:26px;background:linear-gradient(145deg,#d8c7ff,#8b5cf6);color:#2a1642}
.suki-pass p{color:#3e2860}
.stamp-row{display:flex;gap:10px;margin:12px 0}
.stamp{width:34px;height:34px;border-radius:50%;border:2px solid #2a1642}.stamp.active{background:#2a1642}
.nav{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:430px;background:#10061c;border-top:1px solid rgba(200,173,255,.2);display:grid;grid-template-columns:repeat(5,1fr);padding:8px 0}
.student-nav{grid-template-columns:repeat(3,1fr)}
.nav button{background:transparent;color:#ad99d0;border-radius:0;font-size:12px;padding:8px 2px;box-shadow:none;margin:0}
.nav button.active{color:#d8c7ff}
.success{color:#d8c7ff;font-size:14px;font-weight:bold}
.deal-card strong{display:block;color:#fff;font-size:20px;margin:8px 0}
.deal-meta{display:flex;justify-content:space-between;gap:10px;color:#d8c7ff;font-size:13px;margin:12px 0}
.wallet-card{margin:14px 18px;padding:20px;border-radius:28px;color:#2a1642;background:linear-gradient(145deg,#ffd36a,#c8adff)}
.wallet-card h2{margin:5px 0;font-size:30px}
.subscription-studio{margin:14px 18px;padding:20px;border-radius:30px;background:linear-gradient(145deg,#241138,#160826);border:1px solid rgba(200,173,255,.2)}
.subscription-studio h2{margin:6px 0;font-size:27px}
.subscription-studio p{color:var(--muted);font-size:14px}
.billing-toggle{display:grid;grid-template-columns:1fr 1fr;background:#382052;border-radius:24px;padding:4px;margin:16px 0}
.billing-toggle button{margin:0;background:transparent;color:#bfaee0;padding:11px;box-shadow:none}
.billing-toggle button.active{background:#d8c7ff;color:#2a1642}
.pricing-card{position:relative;background:#2a1642;border:1px solid rgba(200,173,255,.18);border-radius:24px;padding:16px;margin-top:12px}
.pro-plan{border-color:#c8adff;box-shadow:0 0 24px rgba(147,84,255,.2)}
.pricing-card h3{margin:6px 0;font-size:22px}
.pricing-card strong{display:block;color:#d8c7ff;font-size:20px;margin:10px 0}
.plan-tag{display:inline-block;color:#c8adff;font-size:12px;text-transform:uppercase;letter-spacing:1px}
.recommended{position:absolute;top:14px;right:14px;background:#d8c7ff;color:#2a1642;border-radius:20px;padding:5px 10px;font-size:11px;font-weight:bold}
.pricing-card ul{padding-left:18px;color:#e1d6f7;font-size:14px;line-height:1.7}
@media(max-width:640px){.login-brand{position:static;justify-self:start;margin-bottom:18px}.login-stage{align-content:start}.login-credit{position:static;justify-self:end;margin-top:18px}}
@media(max-width:460px){.grid,.creative-grid,.quick-actions,.date-row{grid-template-columns:1fr}.row{grid-template-columns:1fr}}
</style>
</head>

<body>
<div id="loginView" class="view active">
  <main class="login-stage">
    <div class="login-brand"><div class="logo">SS</div><span>Student Saver</span></div>

    <section class="auth-card" aria-label="Student Saver login">
      <h1>Welcome<br>Back</h1>
      <input class="tab-radio" type="radio" name="login-type" id="student-tab" checked>
      <input class="tab-radio" type="radio" name="login-type" id="business-tab">

      <div class="tabs">
        <label for="student-tab">Student</label>
        <label for="business-tab">Business</label>
      </div>

      <div class="forms">
        <form class="form-panel student-form" onsubmit="loginAs('student');return false;">
          <div class="input-group">
            <svg viewBox="0 0 24 24" fill="none"><path d="M4 6h16v12H4V6Z" stroke="currentColor" stroke-width="2"/><path d="m4 7 8 6 8-6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
            <input type="text" placeholder="Email or Username" required>
          </div>
          <div class="input-group">
            <svg viewBox="0 0 24 24" fill="none"><path d="M7 11V8a5 5 0 0 1 10 0v3" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><rect x="5" y="11" width="14" height="9" rx="2" stroke="currentColor" stroke-width="2"/></svg>
            <input type="password" placeholder="Password" required>
          </div>
          <button class="login-button" type="submit">Login</button>
          <div class="auth-links"><a href="#">Create account</a><a href="#">Forgot password?</a></div>
        </form>

        <form class="form-panel business-form" onsubmit="loginAs('business');return false;">
          <div class="input-group">
            <svg viewBox="0 0 24 24" fill="none"><path d="M4 6h16v12H4V6Z" stroke="currentColor" stroke-width="2"/><path d="m4 7 8 6 8-6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
            <input type="email" placeholder="Business Email" required>
          </div>
          <div class="input-group">
            <svg viewBox="0 0 24 24" fill="none"><path d="M4 7h16M7 7V5h10v2M6 7l1 13h10l1-13" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
            <input type="text" placeholder="Business ID" required>
          </div>
          <div class="input-group">
            <svg viewBox="0 0 24 24" fill="none"><path d="M7 11V8a5 5 0 0 1 10 0v3" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><rect x="5" y="11" width="14" height="9" rx="2" stroke="currentColor" stroke-width="2"/></svg>
            <input type="password" placeholder="Password" required>
          </div>
          <button class="login-button" type="submit">Login</button>
          <div class="auth-links"><a href="#">Register business</a><a href="#">Need help?</a></div>
        </form>
      </div>

      <div class="socials">
        <a href="#"><span>G</span>Continue with Google</a>
        <a href="#"><span>f</span>Continue with Facebook</a>
      </div>
    </section>
    <div class="login-credit">Student Saver</div>
  </main>
</div>

<div id="studentView" class="view">
  <div class="app">
    <div class="hero">
      <div class="brand-row">
        <div class="brand-left"><div class="logo">SS</div><strong>Student Saver</strong></div>
        <button class="logout-btn" onclick="logout()">Log out</button>
      </div>
      <h1>Student Home</h1>
      <p>Find campus deals, save favorites, and track your student rewards.</p>
    </div>

    <section id="student-home" class="student-section active">
      <div class="feature-hero">
        <p class="small">Student Pass</p>
        <h2>Save more around campus</h2>
        <p>Your violet student pass is ready for food, printing, transport, and study deals.</p>
        <button onclick="openStudentTab('student-deals',document.querySelectorAll('#studentView .nav button')[1])">Browse Deals</button>
      </div>
      <div class="grid">
        <div class="stat glow"><h2>12</h2><p>Saved Deals</p></div>
        <div class="stat"><h2>PHP 430</h2><p>Saved This Month</p></div>
        <div class="stat"><h2>5</h2><p>Rewards</p></div>
        <div class="stat"><h2>88%</h2><p>Pass Level</p></div>
      </div>
      <div class="card">
        <h3>Recommended Today</h3>
        <p>Lunch and printing discounts are most active near your campus today.</p>
        <div class="mini-chart">
          <span style="height:42%"></span><span style="height:70%"></span><span style="height:60%"></span>
          <span style="height:92%"></span><span style="height:74%"></span><span style="height:86%"></span>
        </div>
      </div>
    </section>

    <section id="student-deals" class="student-section">
      <div class="feature-hero"><p class="small">Nearby Offers</p><h2>Student deals live now</h2><p>Claim offers from verified Student Saver business partners.</p></div>
      <div class="deal-card"><span class="badge">Food</span><strong>15% off Lunch Combo</strong><p>Campus Cafe gives students a discount on rice meals and drinks.</p><div class="deal-meta"><span>Code: LUNCH15</span><span>85 claimed</span></div><button onclick="claimDeal(this)">Claim Deal</button></div>
      <div class="deal-card"><span class="badge">Printing</span><strong>PHP 30 off Projects</strong><p>Save on reviewers, reports, and school project printing.</p><div class="deal-meta"><span>Code: PRINT30</span><span>42 claimed</span></div><button onclick="claimDeal(this)">Claim Deal</button></div>
      <div class="deal-card"><span class="badge">Drinks</span><strong>Buy 1 Take 1 Milk Tea</strong><p>Friday study deal from 2 PM to 6 PM with valid school ID.</p><div class="deal-meta"><span>Code: STUDYTEA</span><span>120 claimed</span></div><button onclick="claimDeal(this)">Claim Deal</button></div>
    </section>

    <section id="student-wallet" class="student-section">
      <div class="wallet-card"><div class="small">Digital Wallet</div><h2>PHP 430</h2><p>Total estimated savings this month.</p></div>
      <div class="suki-pass"><div class="small">Suki Loyalty Pass</div><h3>Campus Cafe Rewards</h3><p>Collect 5 stamps to unlock a free iced coffee.</p><div class="stamp-row"><span class="stamp active"></span><span class="stamp active"></span><span class="stamp active"></span><span class="stamp"></span><span class="stamp"></span></div></div>
      <div class="card"><h3>Account</h3><p>Student account: student@example.com</p><button class="dark" onclick="logout()">Return to Login</button></div>
    </section>

    <div class="nav student-nav">
      <button class="active" onclick="openStudentTab('student-home',this)">Home</button>
      <button onclick="openStudentTab('student-deals',this)">Deals</button>
      <button onclick="openStudentTab('student-wallet',this)">Wallet</button>
    </div>
  </div>
</div>

<div id="businessView" class="view">
<div class="app">
<div class="hero">
  <div class="brand-row">
    <div class="brand-left"><div class="logo">SS</div><strong>Student Saver</strong></div>
    <button class="logout-btn" onclick="logout()">Log out</button>
  </div>
  <h1>Business App</h1>
  <p>Student promos, ads, loyalty, and growth tools in one violet dashboard.</p>
</div>

<div class="card">
  <div class="small">Business Profile</div>
  <h2 id="businessDisplay">Campus Cafe</h2>
  <p id="businessInfo">Food and drinks near university area</p>
  <span class="badge" id="planBadge">Monthly Pro</span>
</div>

<section id="biz-home" class="app-section active">
  <div class="home-hero"><p class="small">Today's Business Pulse</p><h2>Campus Cafe is trending near students</h2><p>Your lunch deals are getting strong claim activity this week.</p><button onclick="simulateActivity()">Refresh Live Stats</button></div>
  <div class="grid">
    <div class="stat glow"><h2 id="promoCount">3</h2><p>Active Promos</p></div>
    <div class="stat"><h2 id="views">850</h2><p>Views</p></div>
    <div class="stat"><h2 id="claims">215</h2><p>Claims</p></div>
    <div class="stat"><h2 id="visibility">88%</h2><p>Visibility</p></div>
  </div>
  <div class="card"><h3>Smart Business Insight</h3><p id="smartTip">Best posting window: 10 AM - 1 PM. Students claim food promos faster before lunch.</p><div class="mini-chart"><span style="height:45%"></span><span style="height:70%"></span><span style="height:55%"></span><span style="height:90%"></span><span style="height:66%"></span><span style="height:78%"></span></div></div>
  <div class="quick-actions"><button onclick="openBizTab('biz-promos',document.querySelectorAll('#businessView .nav button')[2])">Post Promo</button><button onclick="openBizTab('biz-growth',document.querySelectorAll('#businessView .nav button')[3])">Boost Store</button></div>
</section>

<section id="biz-account" class="app-section">
  <div class="account-cover"><div class="store-avatar" id="storeAvatar">CC</div><h2 id="accountBusinessDisplay">Campus Cafe</h2><p id="accountBusinessInfo">Food and drinks near university area</p><span class="badge">Verified Business</span></div>
  <div class="card">
    <h2>Business Profile Setup</h2>
    <input id="businessName" placeholder="Business name">
    <input id="ownerName" placeholder="Owner name">
    <input id="email" type="email" placeholder="B
