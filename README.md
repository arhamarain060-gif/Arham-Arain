<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YourGoatViper — Official</title>
<style>
/* RESET & STYLES */
* {margin:0; padding:0; box-sizing:border-box;}
body {font-family:"Poppins", sans-serif; color:#fff; overflow-x:hidden; scroll-behavior:smooth;}
body {background: linear-gradient(270deg, #b365ff, #6e00ff, #00c6ff, #b365ff); background-size:800% 800%; animation:gradientBG 20s ease infinite;}
@keyframes gradientBG {0%{background-position:0% 50%;}50%{background-position:100% 50%;}100%{background-position:0% 50%;}}
body::before {content:""; position:fixed; inset:0; background: rgba(0,0,0,0.5); z-index:-1;}
body::after {content:""; position:fixed; inset:0; background: radial-gradient(circle, rgba(255,255,255,0.05) 1px, transparent 1px); background-size:20px 20px; animation:float 15s linear infinite; z-index:-2;}
@keyframes float {0%{transform:translateY(0);}100%{transform:translateY(-20px);}}

/* HEADER */
header {width:100%; padding:15px 30px; display:flex; justify-content:space-between; align-items:center; background: rgba(0,0,0,0.4); position:fixed; top:0; left:0; z-index:10; backdrop-filter: blur(10px);}
.logo {font-size:1.5rem; font-weight:700; color:#fff; text-shadow:0 0 10px #fff;}
nav a {margin:0 10px; text-decoration:none; color:#fff; font-weight:500; position:relative; transition:0.3s; cursor:pointer; font-size:0.9rem;}
nav a:hover {color:#b365ff; transform:scale(1.05);}
nav a::after {content:""; position:absolute; bottom:-3px; left:0; width:0; height:2px; background:#b365ff; transition:0.3s;}
nav a:hover::after {width:100%;}

/* HERO */
.hero {display:flex; flex-direction:column; align-items:center; justify-content:center; height:90vh; text-align:center; padding:100px 15px 15px;}
.hero h1 {font-size:3rem; color:#fff; margin-bottom:10px; text-shadow:0 0 20px #b365ff;}
.hero p {font-size:1rem; color:#ddd; max-width:90%; line-height:1.5;}
.hero button {margin-top:20px; padding:10px 25px; border:none; background:linear-gradient(135deg,#b365ff,#6e00ff); color:#fff; border-radius:25px; font-weight:600; cursor:pointer; transition:0.3s; font-size:0.9rem;}
.hero button:hover {transform: scale(1.05);}

/* MODAL */
.modal {display:none; position:fixed; inset:0; background: rgba(0,0,0,0.75); backdrop-filter: blur(6px); justify-content:center; align-items:center; z-index:100; padding:15px;}
.modal.active {display:flex;}
.form-box {width:100%; max-width:400px; background: rgba(255,255,255,0.1); border-radius:15px; padding:20px; text-align:center;}
.form-box input, .form-box select {width:100%; padding:10px; margin-bottom:12px; border:none; border-radius:8px; background: rgba(255,255,255,0.1); color:#fff; font-size:0.9rem;}
.form-box button {width:100%; padding:10px; background:linear-gradient(135deg,#b365ff,#6e00ff); border:none; border-radius:8px; color:#fff; cursor:pointer; font-size:0.9rem;}
.form-box .switch {font-size:0.8rem; margin-top:10px;}
.form-box .switch a {color:#b365ff; text-decoration:none;}
.form-box .switch a:hover {color:#fff;}

/* DASHBOARD */
.dashboard {display:none; padding:120px 15px 50px; text-align:center;}
.dashboard.active {display:block;}
.dashboard h2 {color:#fff; margin-bottom:10px; font-size:1.4rem;}
.section {background: rgba(255,255,255,0.05); padding:15px; margin:15px auto; max-width:95%; border-radius:15px; font-size:0.9rem;}
.section h3 {color:#b365ff; margin-bottom:10px; font-size:1.1rem;}

/* Registration Cards */
.registration-card {background: rgba(255,255,255,0.05); margin:10px 0; padding:12px; border-radius:12px; border-left:4px solid #b365ff; box-shadow:0 4px 15px rgba(0,0,0,0.3); transition: transform 0.3s, box-shadow 0.3s; opacity:0; transform:translateY(20px);}
.registration-card:hover {transform:translateY(-3px); box-shadow:0 8px 25px rgba(179,101,255,0.5);}
@keyframes fadeUp {to{opacity:1; transform:translateY(0);}}

/* Leaderboard */
#leaderboardList .leader-card {background: rgba(255,255,255,0.05); margin:10px 0; padding:12px; border-radius:12px; border-left:5px solid #b365ff; box-shadow:0 4px 15px rgba(0,0,0,0.3); transition: transform 0.3s, box-shadow 0.3s; opacity:0; transform:translateY(20px); display:flex; justify-content:space-between; align-items:center; font-weight:600;}
#leaderboardList .leader-card:hover {transform:translateY(-3px); box-shadow:0 8px 25px rgba(179,101,255,0.5);}
.leader-gold {border-left-color:#FFD700; background: rgba(255,215,0,0.1);}
.leader-silver {border-left-color:#C0C0C0; background: rgba(192,192,192,0.1);}
.leader-bronze {border-left-color:#CD7F32; background: rgba(205,127,50,0.1);}

/* Stats */
#totalPlayers {font-weight:700; color:#b365ff;}

/* ABOUT & CONTACT */
#about,#contact {display:none; padding:120px 15px; max-width:95%; margin:auto; background: rgba(255,255,255,0.05); border-radius:15px; font-size:0.9rem;}
#about.active,#contact.active {display:block;}
.link-list a {display:block; margin:5px 0; color:#b365ff; text-decoration:none; padding:6px; border-radius:5px; font-size:0.9rem;}
.link-list a:hover {background: rgba(179,101,255,0.1);}

/* FOOTER */
footer {text-align:center; padding:15px; color:#aaa; background: rgba(0,0,0,0.2); font-size:0.8rem;}

/* RESPONSIVE */
@media(max-width:600px){header{padding:10px 15px;} .hero h1{font-size:2rem;} .hero p{font-size:0.9rem;} nav a{margin:0 5px; font-size:0.8rem;} .dashboard h2{font-size:1.2rem;}}
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
<h3>📊 Tournament Stats</h3>
<p>Total Registered Players: <span id="totalPlayers">0</span></p>
<p>Tournament Starts In: <span id="countdownTimer">--:--:--</span></p>
</div>

<div class="section leaderboard">
<h3>🏆 Tournament Leaderboard</h3>
<div id="leaderboardList"></div>
</div>

<div class="section registration-form">
<h3>🎮 Register for Tournament</h3>
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
<h3>📋 Registered Participants</h3>
<div id="registrationsList"></div>
</div>

<button id="logoutBtn" style="margin-top:15px;">Logout</button>

<section id="about">
<h2>About</h2>
<p>Meet <strong>YourGoatViper</strong>, a force in PUBG universe! Content creator, TDM pro, live streamer, and editor.</p>
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
const clickSound = new Audio("https://www.soundjay.com/button/sounds/button-16.mp3");

// 32 Passcodes
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

// NAVIGATION
document.getElementById("nav-home").onclick = () => showSection("home");
document.getElementById("nav-about").onclick = () => showSection("about");
document.getElementById("nav-contact").onclick = () => showSection("contact");
document.getElementById("nav-login").onclick = openModal;

// SHOW/HIDE SECTIONS
function showSection(id){
document.querySelectorAll("#home,#about,#contact,.dashboard").forEach(s=>s.classList.remove("active"));
document.getElementById(id).classList.add("active");
}

// MODAL
function openModal(){document.getElementById("authModal").classList.add("active");}
function closeModal(){document.getElementById("authModal").classList.remove("active");}
document.getElementById("openLogin").onclick=openModal;

// SWITCH FORMS
document.getElementById("alreadyAccount").onclick = e => {e.preventDefault(); document.getElementById("signupForm").style.display="none"; document.getElementById("loginForm").style.display="block";}
document.getElementById("backSignup").onclick = e => {e.preventDefault(); document.getElementById("loginForm").style.display="none"; document.getElementById("signupForm").style.display="block";}

// CREATE ACCOUNT
document.getElementById("createAccount").onclick = e => {
e.preventDefault(); clickSound.play();
const username = document.getElementById("username").value.trim();
const email = document.getElementById("email").value.trim();
const passcode = document.getElementById("passcode").value.trim();
if(!username||!email||!passcode) return alert("Fill all fields!");

// Check if passcode valid & unused on this device
let usedPasscodes = JSON.parse(localStorage.getItem("usedPasscodes")||"[]");
if(!validPasscodes.includes(passcode)) return alert("Invalid passcode!");
if(usedPasscodes.includes(passcode)) return alert("Passcode already used on this device!");

// Save user
localStorage.setItem("user",JSON.stringify({username,email,passcode}));
usedPasscodes.push(passcode);
localStorage.setItem("usedPasscodes",JSON.stringify(usedPasscodes));
currentUser=username;
closeModal();
showDashboard();
}

// LOGIN
document.getElementById("loginBtn").onclick = e => {
e.preventDefault(); clickSound.play();
const email = document.getElementById("loginEmail").value.trim();
const passcode = document.getElementById("loginPasscode").value.trim();
const stored = JSON.parse(localStorage.getItem("user")||"{}");
if(stored.email===email && stored.passcode===passcode){currentUser=stored.username; closeModal(); showDashboard();}
else alert("Invalid credentials!");
}

// SHOW DASHBOARD
function showDashboard(){
document.querySelectorAll("#home,#about,#contact,.dashboard").forEach(s=>s.classList.remove("active"));
document.getElementById("dashboard").classList.add("active");
document.getElementById("userName").textContent=currentUser;
renderRegistrations();
}

// LOGOUT
document.getElementById("logoutBtn").onclick = e => {clickSound.play(); currentUser=null; showSection("home");}

// TOURNAMENT FORM
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

// RENDER REGISTRATIONS & LEADERBOARD
function renderRegistrations(){
const regs = JSON.parse(localStorage.getItem("registrations")||"[]");
const list = document.getElementById("registrationsList"); list.innerHTML="";
regs.forEach((r,i)=>{
const div=document.createElement("div"); div.className="registration-card"; div.style.animation="fadeUp 0.5s forwards"; div.style.animationDelay=(i*0.1)+"s";
div.innerHTML=`<strong>${r.name}</strong> | Device: ${r.device} | Slots: ${r.slots}`; list.appendChild(div);
});
document.getElementById("totalPlayers").textContent=regs.length;
renderLeaderboard();
}

// LEADERBOARD
function renderLeaderboard(){
const regs = JSON.parse(localStorage.getItem("registrations")||"[]");
const lb = document.getElementById("leaderboardList"); lb.innerHTML="";
regs.sort((a,b)=>b.slots-a.slots);
regs.forEach((r,i)=>{
const div=document.createElement("div"); div.className="leader-card";
if(i===0) div.classList.add("leader-gold"); else if(i===1) div.classList.add("leader-silver"); else if(i===2) div.classList.add("leader-bronze");
div.style.animation="fadeUp 0.5s forwards"; div.style.animationDelay=(i*0.1)+"s";
div.innerHTML=`<span>${r.name}</span><span>Slots: ${r.slots}</span>`; lb.appendChild(div);
});
}

// AUTO LOGIN
window.onload=()=>{
const stored=JSON.parse(localStorage.getItem("user")||"{}");
if(stored.username){currentUser=stored.username; showDashboard();}
else showSection("home");
startCountdown();
}

// COUNTDOWN
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
</script>
</body>
</html>
