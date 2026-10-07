
<!DOCTYPE html>
<html><head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>TULWET - Language + Users + Real AI Video</title>
<style>
*{box-sizing:border-box}body{margin:0;background:#000;color:#fff;font-family:Arial}
.h{background:#166534;padding:8px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:5px}
.lang select{padding:5px 8px;border-radius:15px;border:none;font-weight:bold;background:#facc15}
.users{background:rgba(0,0,0,0.5);padding:4px 8px;border-radius:10px;font-size:10px}
.main{height:100vh;display:flex;flex-direction:column}
.vid{flex:1;position:relative;background:#111;display:flex;align-items:center;justify-content:center}
video{width:100%;height:100%;object-fit:cover}
#userCam{position:absolute;bottom:100px;right:10px;width:90px;height:120px;border-radius:12px;border:2px solid #22c55e;object-fit:cover;transform:scaleX(-1);z-index:5;background:#222}
.badge{position:absolute;top:10px;left:10px;background:red;padding:4px 8px;border-radius:5px;font-size:10px;z-index:5;animation:bl 1s infinite}
@keyframes bl{50%{opacity:0.5}}
.bot{position:absolute;bottom:0;left:0;right:0;background:linear-gradient(transparent,rgba(0,0,0,0.95));padding:10px;z-index:6}
.verse{background:rgba(22,101,52,0.92);padding:10px;border-radius:10px;font-size:12px;max-height:110px;overflow:auto}
.ctrl{display:flex;gap:5px;margin-top:6px}
.b{flex:1;padding:10px;border:none;border-radius:20px;font-weight:bold;font-size:11px}
.play{background:#facc15;color:#000}
.stop{background:#ef4444;color:#fff}
.topics{display:flex;gap:5px;overflow:auto;padding:5px 0}
.topics button{background:rgba(255,255,255,0.15);color:#fff;border:1px solid #555;padding:5px 10px;border-radius:15px;font-size:10px;white-space:nowrap}
.stats{display:flex;gap:10px;font-size:10px;margin-top:5px;color:#aaa}
</style>
</head><body>
<div class="h">
<div>⛰️ TULWET AI BIBLE</div>
<div class="lang">
<select id="langSel" onchange="changeLang()">
<option value="en">🇬🇧 English</option>
<option value="sw">🇰🇪 Kiswahili</option>
<option value="kal">🌿 Kalenjin</option>
<option value="en-sw">🇰🇪 Eng + Swa Mix</option>
</select>
</div>
<div class="users">
<div>👥 <span id="totalUsers">1,247</span> Total</div>
<div>🟢 <span id="liveUsers">23</span> Live Now</div>
</div>
</div>

<div class="main">
<div class="vid">
<video id="aiVideo" controls playsinline poster="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=600">
<source src="jesus-healing.mp4" type="video/mp4">
</video>
<video id="userCam" autoplay muted playsinline></video>
<div class="badge">🔴 REAL AI VIDEO • <span id="langBadge">EN</span></div>
<div class="bot">
<div class="topics">
<button onclick="playType('healing')">🩹 Healing</button>
<button onclick="playType('fees')">💰 Fees</button>
<button onclick="playType('fear')">😨 Fear</button>
<button onclick="playType('anxiety')">😰 Anxiety</button>
<button onclick="playType('family')">👨‍👩‍👧 Family</button>
</div>
<div class="verse" id="verse">Loading language...</div>
<div class="stats">
<span>📍 Eldoret • Tulwet Mt</span>
<span>•</span>
<span id="visitCount">You are visitor #...</span>
<span>•</span>
<span id="timeNow">Time</span>
</div>
<div class="ctrl">
<button class="b" style="background:#fff;color:#000" onclick="startCam()">📷 Camera</button>
<button class="b play" onclick="playType('healing')">▶️ PLAY VIDEO</button>
<button class="b stop" onclick="stopAll()">⏹️ Stop</button>
</div>
<button onclick="listen()" style="width:100%;margin-top:6px;padding:10px;background:#16a34a;color:#fff;border:none;border-radius:20px">🎤 <span id="speakTxt">Speak Your Problem</span></button>
</div>
</div>
</div>

<script>
// Language translations
const LANG={
en:{healing:{v:"Jeremiah 30:17 - I will restore you to health.",t:"Put your hand where it hurts. God heals now.",p:"Receive healing!"},
fees:{v:"Philippians 4:19 - God will meet all needs.",t:"God sees fees letter. Miracle coming.",p:"Jehovah Jireh provides!"},
fear:{v:"Isaiah 41:10 - Fear not, I am with you.",t:"Fear is lying. You are safe.",p:"Peace be still!"},
anxiety:{v:"Philippians 4:6-7 - Present requests to God.",t:"Breathe in 4, hold 4, out 6.",p:"Peace guard your heart!"},
family:{v:"Joshua 24:15 - We will serve the Lord.",t:"Family stress hard. God is father too.",p:"Restore this family!"},
speak:"Speak Your Problem",welcome:"Welcome! Tap healing, fees, fear - Jesus will talk in your language!"},
sw:{healing:{v:"Yeremia 30:17 - Nitakurudishia afya yako.",t:"Weka mkono mahali pa maumivu. Mungu anaponya sasa.",p:"Pokea uponyaji!"},
fees:{v:"Wafilipi 4:19 - Mungu atak
