<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourGoatViper — Official</title>
<style>
/* ===== RESET ===== */
* {margin:0; padding:0; box-sizing:border-box; font-family: 'Poppins', sans-serif;}
body {background: #0b0c10; color:#fff; overflow-x:hidden;}

/* ===== HEADER ===== */
header {position:fixed; top:0; left:0; width:100%; padding:15px 30px; display:flex; justify-content:space-between; align-items:center; backdrop-filter:blur(10px); background:rgba(0,0,0,0.5); z-index:10; border-bottom:1px solid rgba(255,255,255,0.1);}
header .logo {font-size:1.8rem; font-weight:700; color:#b365ff; text-shadow:0 0 10px #b365ff;}
header nav a {margin:0 12px; text-decoration:none; color:#fff; font-weight:500; position:relative; cursor:pointer;}
header nav a::after {content:""; position:absolute; bottom:-3px; left:0; width:0; height:2px; background:#b365ff; transition:0.3s;}
header nav a:hover::after {width:100%;}

/* ===== HERO ===== */
.hero {height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; background:url('IMG_1703.jpeg') center/cover no-repeat; position:relative;}
.hero::before {content:""; position:absolute; inset:0; background:rgba(0,0,0,0.6);}
.hero h1 {color:#b365ff; font-size:3rem; margin-bottom:10px; text-shadow:0 0 15px #b365ff; position:relative; z-index:1;}
.hero p {color:#ddd; max-width:600px; margin-bottom:20px; position:relative; z-index:1;}
.hero button {padding:12px 35px; border:none; border-radius:25px; font-weight:600; background:linear-gradient(135deg,#b365ff,#6e00ff); color:#fff; cursor:pointer; position:relative; z-index:1; transition:0.3s;}
.hero button:hover {transform:scale(1.05); box-shadow:0 0 20px #b365ff;}

/* ===== MODAL ===== */
.modal {position:fixed; inset:0; display:flex; justify-content:center; align-items:center; background:rgba(0,0,0,0.75); backdrop-filter:blur(6px); visibility:hidden; opacity:0; transition:0.3s;}
.modal.active {visibility:visible; opacity:1;}
.form-box {width:100%; max-width:400px; background:rgba(255,255,255,0.1); border-radius:15px; padding:25px; backdrop-filter:blur(10px);}
.form-box h2 {text-align:center; margin-bottom:20px; color:#fff;}
.form-box input {width:100%; padding:12px; margin-bottom:15px; border:none; border-radius:8px; background:rgba(255,255,255,0.1); color:#fff;}
.form-box button {width:100%; padding:12px; border:none; border-radius:8px; background:linear-gradient(135deg,#b365ff,#6e00ff); color:#fff; cursor:pointer;}
.form-box .switch {text-align:center; margin-top:12px; font-size:0.9rem;}
.form-box .switch a {color:#b365ff; text-decoration:none;}
.form-box .switch a:hover {color:#fff;}

/* ===== DASHBOARD ===== */
.dashboard {display:none; padding:120px 20px; text-align:center;}
.dashboard.active {display:block;}
.dashboard h2 {color:#b365ff; margin-bottom:10px;}
.section {background:rgba(255,255,255,0.05); margin:15px auto; max-width:700px; padding:20px; border-radius:15px; text-align:left; box-shadow:0 10px 30px rgba(0,0,0,0.3);}
.section h3 {margin-bottom:10px; color:#b365ff;}
.registration-card {background:rgba(255,255,255,0.05); padding:12px; margin:8px 0; border-left:4px solid #b365ff; border-radius:10px; display:flex; justify-content:space-between;}

/* ===== LEADERBOARD ===== */
.leader-card {padding:12px; margin:6px 0; border-left:5px solid #b365ff; border-radius:10px; display:flex; justify-content:space-between; font-weight:600;}
.leader-gold {border-left-color:#FFD700; background:rgba(255,215,0,0.1);}
.leader-silver {border-left-color:#C0C0C0; background:rgba(192,192,192,0.1);}
.leader-bronze {border-left-color:#CD7F32; background:rgba(205,127,50,0.1);}

/* ===== ABOUT & CONTACT ===== */
#about,#contact {display:none; padding:120px 20px; max-width:700px; margin:auto; background:rgba(255,255,255,0.05); border-radius:15px;}
#about.active,#contact.active {display:block;}
.link-list a {display:block; margin:6px 0; color:#b365ff; text-decoration:none;}
.link-list a:hover {background:rgba(179,101,255,0.1); border-radius:5px;}

/* ===== FOOTER ===== */
footer {text-align:center; padding:20px; color:#aaa; background:rgba(0,0,0,0.2);}

/* ===== RESPONSIVE ===== */
@media(max-width:600px){.hero h1{font-size:2rem;}.hero p{font-size:0.9rem;} header nav a{margin:0 5px; font-size:0.8rem;}}
</style>
</head>
<body>

<header>
<div class="logo">YourGoatViper</div>
<nav>
<a id="nav-home">Home</a>
<a id="nav-about">About</a>
<a id="nav-contact">Contact</a>
<a id="nav-login">Login</a>
</nav>
</header>

<section class="hero" id="home">
<h1>Welcome to YourGoatViper</h1>
<p>Official Website of the PUBG Creator & Tournament Organizer</p>
<button id="openLogin">Login / Register</button>
</section>

<div class="modal" id="authModal">
<div class="form-box" id="signupForm">
<h2>Create Account</h2>
<input type="text" id="username" placeholder="Username">
<input type="email" id="email" placeholder="Email">
<input type="text" id="passcode" placeholder="Enter Passcode">
<button id="createAccount">Create Account</button>
<div class="switch">Already have an account? <a href="#" id="alreadyAccount">Login</a></div>
</div>
<div class="form-box" id="loginForm" style="display:none;">
<h2>Login</h2>
<input type="email" id="loginEmail" placeholder="Email">
<input type="text" id="loginPasscode" placeholder="Enter Passcode">
<button id="loginBtn">Login</button>
<div class="switch"><a href="#" id="backSignup">Create New Account</a></div>
</div>
</div>

<section class="dashboard" id="dashboard">
<h2>Welcome, <span id="userName"></span> 👋</h2>
<div class="section stats">
<p>Total Registered Players: <span id="totalPlayers">0</span></p>
<p>Tournament Countdown: <span id="countdownTimer">--:--:--</span></p>
</div>
<div class="section registration-form">
<h3>Register for Tournament</h3>
<form id="tournamentForm">
<label>PUBG In-Game Name:</label>
<input type="text" id="pubgName" placeholder="Enter PUBG username" required>
<label>Device:</label>
<select id="device" required>
<option value="">Select Device</option>
<option value="Android">Android</option>
<option value="iOS">iOS</option>
</select>
<label>Slots (1-4):</label>
<input type="number" id="slots" min="1" max="4" placeholder="Number of slots" required>
<button type="submit">Register</button>
</form>
</div>
<div class="section registered-players">
<h3>Registered Participants</h3>
<div id="registrationsList"></div>
</div>
<div class="section leaderboard">
<h3>Leaderboard</h3>
<div id="leaderboardList"></div>
</div>
<button id="logoutBtn" style="margin-top:15px;">Logout</button>
</section>

<section id="about">
<h2>About</h2>
<p>YourGoatViper is a force in PUBG universe! Content creator, TDM pro, live streamer, and editor bringing the heat with every match.</p>
</section>

<section id="contact">
<h2>Contact</h2>
<div class="link-list">
<a href="https://www.instagram.com/arham_arain333" target="_blank">Instagram</a>
<a href="https://www.tiktok.com/@yourgoatviper" target="_blank">TikTok</a>
<a href="https://www.youtube.com/@YourGoatViper" target="_blank">YouTube</a>
<a href="https://www.snapchat.com/add/aarain21553" target="_blank">Snapchat</a>
<a href="https://wa.me/923348666640" target="_blank">WhatsApp</a>
<a href="mailto:arhamarain060@gmail.com">Email</a>
</div>
</section>

<footer>© 2025 YourGoatViper | All Rights Reserved</footer>

<script>
// ===== CLICK SOUND =====
const clickSound = new Audio("https://www.soundjay.com/button/sounds/button-16.mp3");

// ===== PASSCODES =====
const validPasscodes = [
"YourGoatViper-TourneyPro-4j8KLm9Np2","YourGoatViper-GamingFrenzy-7h3GHj5Kl8","YourGoatViper-ChampMode-9p4MNl2kJh6",
"YourGoatViper-VictoryLap-1q2wS3eD4r","YourGoatViper-EliteWarrior-5t6Yh8Ij3k","YourGoatViper-TournamentTamer-9n8Bh4Lm2p",
"YourGoatViper-GamerGirl-2c4V6b8Nl1k","YourGoatViper-SniperKing-7g6Jh3Kl4m","YourGoatViper-PlayoffPro-9m8Nl4Kp2j",
"YourGoatViper-GamingMaster-4h6Gf2sD3p","YourGoatViper-NoobSlayer-1a2b3c4d5","YourGoatViper-TourneyTitan-6p9Lk4Jh3g",
"YourGoatViper-FPSFanatic-8m5Nl2pKj","YourGoatViper-GamingGuru-3q2w1e4r","YourGoatViper-ChampionshipChaser-9h8j7k6p",
"YourGoatViper-BattleHardened-2t4g6y8h","YourGoatViper-GamerGod-5m3j9p2k","YourGoatViper-TourneyTactician-1p8L4k2j3",
"YourGoatViper-SniperSavant-7g4h2j9p","YourGoatViper-EliteSquad-3m5n8b2v","YourGoatViper-GamingGenius-9p6l4j3h",
"YourGoatViper-TourneyTitan-2c8B4n6m","YourGoatViper-FPSFan-5t7y6h3","YourGoatViper-GamingGrind-9m2p4l8k",
"YourGoatViper-NoMercy-1q2w3e4r","YourGoatViper-TourneyTerror-6h8j3k2","YourGoatViper-GamingGamer-0x9p8l7m",
"YourGoatViper-LegendMode-7g5h4k3j","YourGoatViper-UltimatePro-2p3q4r5s","YourGoatViper-VictoryRush-9n8m7l6k",
"YourGoatViper-GameOver-1a2s3d4f","YourGoatViper-SniperElite-5h6j7k8l","YourGoatViper-MasterGamer-3q2w1e4r"
];

let currentUser = null;

// ===== NAVIGATION =====
document.getElementById("nav-home").onclick = () => showSection("home");
document.getElementById("nav-about").onclick = () => showSection("about");
document.getElementById("nav-contact").onclick = () => showSection("contact");
document.getElementById("nav-login").onclick = openModal;

// ===== SHOW/HIDE =====
function showSection(id){
document.querySelectorAll("#home,#about,#contact,.dashboard").forEach(s=>s.classList.remove("active"));
document.getElementById(id).classList.add("active");
}

// ===== MODAL =====
function openModal(){document.getElementById("authModal").classList.add("active");}
function closeModal(){document.getElementById("authModal").classList.remove("active");}
document.getElementById("openLogin").onclick=openModal;

// ===== SWITCH FORMS =====
document.getElementById("alreadyAccount").onclick = e => {e.preventDefault(); document.getElementById("signupForm").style.display="none"; document.getElementById("loginForm").style.display="block";}
document.getElementById("backSignup").onclick = e => {e.preventDefault(); document.getElementById("loginForm").style.display="none"; document.getElementById("signupForm").style.display="block";}

// ===== CREATE ACCOUNT =====
document.getElementById("createAccount").onclick = e => {
e.preventDefault(); clickSound.play();
const username = document.getElementById("username").value.trim();
const email = document.getElementById("email").value.trim();
const passcode = document.getElementById("passcode").value.trim();
if(!username||!email||!passcode) return alert("Fill all fields!");
let usedPasscodes = JSON.parse(localStorage.getItem("usedPasscodes")||"[]");
if(!validPasscodes.includes(passcode)) return alert("Invalid passcode!");
if(usedPasscodes.includes(passcode)) return alert("Passcode already used on this device!");
localStorage.setItem("user",JSON.stringify({username,email,passcode}));
usedPasscodes.push(passcode);
localStorage.setItem("usedPasscodes",JSON.stringify(usedPasscodes));
currentUser=username; closeModal(); showDashboard();
}

// ===== LOGIN =====
document.getElementById("loginBtn").onclick = e => {
e.preventDefault(); clickSound.play();
const email = document.getElementById("loginEmail").value.trim();
const passcode = document.getElementById("loginPasscode").value.trim();
const stored = JSON.parse(localStorage.getItem("user")||"{}");
if(stored.email===email && stored.passcode===passcode){currentUser=stored.username; closeModal(); showDashboard();}
else alert("Invalid credentials!");
}

// ===== DASHBOARD =====
function showDashboard(){
document.querySelectorAll("#home,#about,#contact,.dashboard").forEach(s=>s.classList.remove("active"));
document.getElementById("dashboard").classList.add("active");
document.getElementById("userName").textContent=currentUser;
renderRegistrations();
}

// ===== LOGOUT =====
document.getElementById("logoutBtn").onclick = e => {clickSound.play(); currentUser=null; showSection("home");}

// ===== TOURNAMENT FORM =====
document.getElementById("tournamentForm").onsubmit = e => {
e.preventDefault(); clickSound.play();
const name = document.getElementById("pubgName").value.trim();
const device = document.getElementById("device").value;
const slots = parseInt(document.getElementById("slots").value);
if(!name||!device||!slots) return alert("Fill all fields!");
let regs = JSON.parse(localStorage.getItem("registrations")||"[]");
regs.push({name,device,slots});
localStorage.setItem("registrations",JSON.stringify(regs));
document.getElementById("tournamentForm").reset();
renderRegistrations();
}

// ===== RENDER REGISTRATIONS & LEADERBOARD =====
function renderRegistrations(){
const regs = JSON.parse(localStorage.getItem("registrations")||"[]");
const list = document.getElementById("registrationsList"); list.innerHTML="";
regs.forEach(r=>{const div=document.createElement("div"); div.className="registration-card"; div.innerHTML=`<span>${r.name}</span><span>Device: ${r.device} | Slots: ${r.slots}</span>`; list.appendChild(div);});
document.getElementById("totalPlayers").textContent=regs.length;
renderLeaderboard();
}

function renderLeaderboard(){
const regs = JSON.parse(localStorage.getItem("registrations")||"[]");
const lb = document.getElementById("leaderboardList"); lb.innerHTML="";
regs.sort((a,b)=>b.slots-a.slots);
regs.forEach((r,i)=>{
const div=document.createElement("div"); div.className="leader-card";
if(i===0) div.classList.add("leader-gold"); else if(i===1) div.classList.add("leader-silver"); else if(i===2) div.classList.add("leader-bronze");
div.innerHTML=`<span>${r.name}</span><span>Slots: ${r.slots}</span>`; lb.appendChild(div);
});
}

// ===== AUTO LOGIN =====
window.onload=()=>{
const stored=JSON.parse(localStorage.getItem("user")||"{}");
if(stored.username){currentUser=stored.username; showDashboard();}
else showSection("home");
startCountdown();
}

// ===== COUNTDOWN =====
function startCountdown(){
const countdown=document.getElementById("countdownTimer");
const tournamentDate=new Date(); tournamentDate.setDate(tournamentDate.getDate()+7);
setInterval(()=>{
const now=new Date().getTime();
const distance=tournamentDate-now;
if(distance<0){countdown.textContent="Started!"; return;}
const h=Math.floor((distance%(1000*60*60*24))/(1000*60*60));
const m=Math.floor((distance%(1000*60*60))/(1000*60));
const s=Math.floor((distance%(1000*60))/1000);
countdown.textContent=`${h.toString().padStart(2,'0')}:${m.toString().padStart(2,'0')}:${s.toString().padStart(2,'0')}`;
},1000);
}

// ===== ENTER KEY SUBMIT =====
document.querySelectorAll("#authModal input").forEach(input=>{
input.addEventListener("keypress",function(e){if(e.key==="Enter"){document.getElementById("signupForm").style.display!=="none"?document.getElementById("createAccount").click():document.getElementById("loginBtn").click();}});});

</script>
</body>
</html>
