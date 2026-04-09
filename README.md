<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vaibhav Yadav — GitHub Profile</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Outfit:wght@300;400;500;600;700;800;900&display=swap');
:root{--bg:#0a0d13;--surface:#0f1318;--card:#141920;--border:#1e2733;--border-bright:#2a3547;--text:#e8edf5;--muted:#5a6a82;--cyan:#00d4ff;--orange:#ff6b35;--green:#39ff85;--purple:#9b7dff;--yellow:#ffd166;--pink:#ff4da6;--mono:'Space Mono',monospace;--sans:'Outfit',sans-serif}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--sans);min-height:100vh;overflow-x:hidden}
body::before{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(0,212,255,.03) 1px,transparent 1px),linear-gradient(90deg,rgba(0,212,255,.03) 1px,transparent 1px);background-size:40px 40px;pointer-events:none;z-index:0}
.orb{position:fixed;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0;animation:drift 12s ease-in-out infinite alternate}
.orb-1{width:400px;height:400px;background:rgba(0,212,255,.06);top:-100px;left:-100px}
.orb-2{width:300px;height:300px;background:rgba(155,125,255,.07);bottom:0;right:-50px;animation-delay:-4s}
.orb-3{width:200px;height:200px;background:rgba(255,107,53,.05);top:50%;left:50%;animation-delay:-8s}
@keyframes drift{from{transform:translate(0,0) scale(1)}to{transform:translate(30px,20px) scale(1.1)}}
.wrapper{position:relative;z-index:1;max-width:860px;margin:0 auto;padding:40px 24px 80px}
.hero{text-align:center;padding:60px 20px 50px;animation:fadeUp .7s ease both}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
.hero-badge{display:inline-flex;align-items:center;gap:8px;background:rgba(0,212,255,.08);border:1px solid rgba(0,212,255,.2);border-radius:20px;padding:6px 16px;font-size:12px;font-family:var(--mono);color:var(--cyan);margin-bottom:28px;letter-spacing:.05em}
.hero-badge::before{content:'';width:6px;height:6px;background:var(--cyan);border-radius:50%;box-shadow:0 0 8px var(--cyan);animation:pulse 2s ease infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}
.hero-name{font-size:clamp(42px,8vw,72px);font-weight:900;letter-spacing:-2px;line-height:1;margin-bottom:12px;background:linear-gradient(135deg,#fff 0%,var(--cyan) 50%,var(--purple) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-handle{font-family:var(--mono);font-size:16px;color:var(--muted);margin-bottom:20px;letter-spacing:.08em}
.hero-handle span{color:var(--cyan)}
.hero-tagline{font-size:18px;font-weight:400;color:#8a9ab5;max-width:500px;margin:0 auto 36px;line-height:1.6}
.hero-links{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
.hero-link{display:flex;align-items:center;gap:8px;padding:10px 20px;border-radius:8px;font-size:13px;font-weight:600;text-decoration:none;cursor:pointer;transition:all .2s;border:1px solid var(--border-bright);background:var(--card);color:var(--text)}
.hero-link:hover{transform:translateY(-2px);border-color:var(--cyan);box-shadow:0 8px 24px rgba(0,212,255,.15)}
.hero-link.primary{background:linear-gradient(135deg,rgba(0,212,255,.15),rgba(155,125,255,.15));border-color:rgba(0,212,255,.4);color:var(--cyan)}
.section{margin-bottom:40px;animation:fadeUp .6s ease both}
.section:nth-child(2){animation-delay:.1s}.section:nth-child(3){animation-delay:.2s}.section:nth-child(4){animation-delay:.3s}.section:nth-child(5){animation-delay:.4s}
.section-header{display:flex;align-items:center;gap:12px;margin-bottom:24px}
.section-icon{font-size:22px}.section-title{font-size:22px;font-weight:800;letter-spacing:-.5px;color:var(--text)}
.section-line{flex:1;height:1px;background:linear-gradient(90deg,var(--border-bright),transparent)}
.stats-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.stat-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:28px 20px;text-align:center;position:relative;overflow:hidden;transition:all .3s;cursor:default}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;border-radius:16px 16px 0 0}
.stat-card.contributions::before{background:linear-gradient(90deg,var(--cyan),var(--purple))}
.stat-card.streak::before{background:linear-gradient(90deg,var(--orange),var(--yellow))}
.stat-card.longest::before{background:linear-gradient(90deg,var(--green),var(--cyan))}
.stat-card:hover{transform:translateY(-4px);border-color:var(--border-bright);box-shadow:0 16px 40px rgba(0,0,0,.4)}
.stat-value{font-size:48px;font-weight:900;line-height:1;margin-bottom:8px;font-family:var(--mono)}
.stat-card.contributions .stat-value{color:var(--cyan)}.stat-card.streak .stat-value{color:var(--orange)}.stat-card.longest .stat-value{color:var(--green)}
.stat-label{font-size:13px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;margin-bottom:6px}
.stat-sub{font-size:11px;color:var(--muted);font-family:var(--mono);opacity:.7}
.streak-ring{width:80px;height:80px;margin:0 auto 12px;position:relative}
.streak-ring svg{transform:rotate(-90deg)}
.streak-ring .track{fill:none;stroke:rgba(255,107,53,.15);stroke-width:6}
.streak-ring .fill{fill:none;stroke:var(--orange);stroke-width:6;stroke-linecap:round;stroke-dasharray:220;stroke-dashoffset:176;animation:ringFill 1.5s ease .5s both;filter:drop-shadow(0 0 6px var(--orange))}
@keyframes ringFill{from{stroke-dashoffset:220}to{stroke-dashoffset:176}}
.streak-ring .ring-inner{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:24px;font-weight:900;font-family:var(--mono);color:var(--orange)}
.chart-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:28px;overflow:hidden}
.chart-title{font-size:13px;font-family:var(--mono);color:var(--muted);text-align:center;margin-bottom:20px;letter-spacing:.05em}
.chart-title span{color:var(--cyan)}
.chart-area{position:relative;height:160px}
.chart-area svg{width:100%;height:100%}
.tech-category{margin-bottom:20px}
.tech-cat-label{font-size:12px;font-family:var(--mono);color:var(--muted);letter-spacing:.1em;text-transform:uppercase;margin-bottom:10px;display:flex;align-items:center;gap:8px}
.tech-cat-label::before{content:'';width:20px;height:1px;background:var(--border-bright)}
.badge-row{display:flex;flex-wrap:wrap;gap:8px;justify-content:center}
.tech-badge{display:inline-flex;align-items:center;gap:7px;padding:8px 16px;border-radius:8px;font-size:12px;font-weight:700;letter-spacing:.08em;font-family:var(--mono);border:1px solid transparent;transition:all .2s;cursor:default}
.tech-badge:hover{transform:translateY(-3px) scale(1.05);box-shadow:0 8px 20px rgba(0,0,0,.4)}
.badge-cpp{background:rgba(0,89,220,.15);border-color:rgba(0,89,220,.4);color:#4da6ff}
.badge-py{background:rgba(255,214,0,.1);border-color:rgba(255,214,0,.35);color:#ffd500}
.badge-js{background:rgba(240,219,79,.12);border-color:rgba(240,219,79,.35);color:#f0db4f}
.badge-ts{background:rgba(49,120,198,.15);border-color:rgba(49,120,198,.4);color:#3178c6}
.badge-react{background:rgba(97,218,251,.1);border-color:rgba(97,218,251,.3);color:#61dafb}
.badge-next{background:rgba(255,255,255,.07);border-color:rgba(255,255,255,.15);color:#fff}
.badge-tw{background:rgba(56,189,248,.1);border-color:rgba(56,189,248,.3);color:#38bdf8}
.badge-node{background:rgba(104,160,99,.15);border-color:rgba(104,160,99,.4);color:#68a063}
.badge-express{background:rgba(255,255,255,.06);border-color:rgba(255,255,255,.12);color:#aaa}
.badge-mongo{background:rgba(77,179,61,.12);border-color:rgba(77,179,61,.3);color:#4db33d}
.badge-pg{background:rgba(51,103,145,.18);border-color:rgba(51,103,145,.45);color:#336791}
.badge-docker{background:rgba(0,150,250,.12);border-color:rgba(0,150,250,.3);color:#0096fa}
.badge-aws{background:rgba(255,153,0,.12);border-color:rgba(255,153,0,.35);color:#ff9900}
.badge-git{background:rgba(240,80,50,.12);border-color:rgba(240,80,50,.35);color:#f05032}
.badge-actions{background:rgba(38,137,255,.12);border-color:rgba(38,137,255,.3);color:#2689ff}
.cp-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:14px;margin-bottom:20px}
.cp-card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:18px 20px;display:flex;align-items:center;justify-content:space-between;transition:all .2s;cursor:pointer}
.cp-card:hover{transform:translateY(-3px);border-color:var(--border-bright);box-shadow:0 12px 30px rgba(0,0,0,.3)}
.cp-platform{font-size:13px;font-family:var(--mono);color:var(--muted);text-transform:uppercase;letter-spacing:.08em;margin-bottom:4px}
.cp-handle{font-size:15px;font-weight:700;color:var(--text)}
.cp-badge{padding:5px 12px;border-radius:6px;font-size:12px;font-weight:700;font-family:var(--mono)}
.cp-badge.cf{background:rgba(57,255,133,.12);border:1px solid rgba(57,255,133,.3);color:var(--green)}
.cp-badge.lc{background:rgba(255,161,22,.12);border:1px solid rgba(255,161,22,.3);color:#ffa116}
.cp-badge.cc{background:rgba(255,77,53,.12);border:1px solid rgba(255,77,53,.3);color:#ff4d35}
.solved-banner{background:linear-gradient(135deg,rgba(255,107,53,.1),rgba(255,209,102,.1));border:1px solid rgba(255,107,53,.3);border-radius:12px;padding:20px 28px;display:flex;align-items:center;justify-content:center;gap:16px}
.solved-text{font-size:13px;font-family:var(--mono);color:var(--muted);text-transform:uppercase;letter-spacing:.1em}
.solved-count{font-size:28px;font-weight:900;font-family:var(--mono);background:linear-gradient(135deg,var(--orange),var(--yellow));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.solved-platforms{font-size:12px;color:var(--muted);font-family:var(--mono);margin-top:4px;letter-spacing:.05em}
.footer{text-align:center;margin-top:60px;padding-top:30px;border-top:1px solid var(--border);font-size:12px;font-family:var(--mono);color:var(--muted)}
.footer span{color:var(--cyan)}
</style>
</head>
<body>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>
<div class="wrapper">
  <div class="hero section">
    <div class="hero-badge">🟢 Open to opportunities</div>
    <h1 class="hero-name">Vaibhav Yadav</h1>
    <div class="hero-handle"><span>@</span>v-vaibhav07</div>
    <p class="hero-tagline">Full-Stack Developer &amp; Competitive Programmer — building fast, scalable, and beautiful things.</p>
    <div class="hero-links">
      <a class="hero-link primary" href="https://github.com/v-vaibhav07">
        <svg width="16" height="16" fill="currentColor" viewBox="0 0 16 16"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
        GitHub Profile
      </a>
      <a class="hero-link" href="mailto:vaibhavyadav6533@gmail.com">📧 vaibhavyadav6533@gmail.com</a>
      <a class="hero-link" href="#">💼 LinkedIn</a>
    </div>
  </div>

  <div class="section">
    <div class="section-header"><span class="section-icon">📊</span><span class="section-title">GitHub Stats</span><div class="section-line"></div></div>
    <div class="stats-grid">
      <div class="stat-card contributions">
        <div class="stat-value" id="contribCount">0</div>
        <div class="stat-label">Total Contributions</div>
        <div class="stat-sub">Jan 25, 2025 — Present</div>
      </div>
      <div class="stat-card streak">
        <div class="streak-ring">
          <svg viewBox="0 0 80 80"><circle class="track" cx="40" cy="40" r="35"/><circle class="fill" cx="40" cy="40" r="35"/></svg>
          <div class="ring-inner">6</div>
        </div>
        <div class="stat-label">Current Streak 🔥</div>
        <div class="stat-sub">Apr 4 — Apr 9</div>
      </div>
      <div class="stat-card longest">
        <div class="stat-value">13</div>
        <div class="stat-label">Longest Streak</div>
        <div class="stat-sub">Mar 17 — Mar 29</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header"><span class="section-icon">🔥</span><span class="section-title">Contribution Graph</span><div class="section-line"></div></div>
    <div class="chart-card">
      <div class="chart-title"><span>Vaibhav</span>'s Contribution Activity</div>
      <div class="chart-area">
        <svg id="contribChart" viewBox="0 0 800 160" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <linearGradient id="chartGrad" x1="0" y1="0" x2="0" y2="1">
              <stop offset="0%" stop-color="#00d4ff" stop-opacity="0.4"/>
              <stop offset="100%" stop-color="#00d4ff" stop-opacity="0.02"/>
            </linearGradient>
            <filter id="glow"><feGaussianBlur stdDeviation="3" result="blur"/><feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge></filter>
          </defs>
          <line x1="0" y1="32" x2="800" y2="32" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
          <line x1="0" y1="64" x2="800" y2="64" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
          <line x1="0" y1="96" x2="800" y2="96" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
          <line x1="0" y1="128" x2="800" y2="128" stroke="rgba(255,255,255,0.04)" stroke-width="1"/>
          <text x="0" y="30" fill="rgba(255,255,255,0.25)" font-size="10" font-family="Space Mono">35</text>
          <text x="0" y="62" fill="rgba(255,255,255,0.25)" font-size="10" font-family="Space Mono">25</text>
          <text x="0" y="95" fill="rgba(255,255,255,0.25)" font-size="10" font-family="Space Mono">15</text>
          <text x="0" y="127" fill="rgba(255,255,255,0.25)" font-size="10" font-family="Space Mono">5</text>
          <path id="chartArea" fill="url(#chartGrad)"/>
          <path id="chartLine" fill="none" stroke="#00d4ff" stroke-width="2" filter="url(#glow)" stroke-linecap="round" stroke-linejoin="round"/>
          <g id="chartDots"></g>
        </svg>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header"><span class="section-icon">⚡</span><span class="section-title">Tech Arsenal</span><div class="section-line"></div></div>
    <div class="tech-category">
      <div class="tech-cat-label">💻 Languages</div>
      <div class="badge-row">
        <span class="tech-badge badge-cpp">⚙ C++</span>
        <span class="tech-badge badge-py">🐍 Python</span>
        <span class="tech-badge badge-js">JS JavaScript</span>
        <span class="tech-badge badge-ts">TS TypeScript</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">🌐 Frontend</div>
      <div class="badge-row">
        <span class="tech-badge badge-react">⚛ React</span>
        <span class="tech-badge badge-next">▲ Next.js</span>
        <span class="tech-badge badge-tw">🌊 Tailwind</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">🛠 Backend &amp; Databases</div>
      <div class="badge-row">
        <span class="tech-badge badge-node">🟢 Node.js</span>
        <span class="tech-badge badge-express">EX Express</span>
        <span class="tech-badge badge-mongo">🍃 MongoDB</span>
        <span class="tech-badge badge-pg">🐘 PostgreSQL</span>
      </div>
    </div>
    <div class="tech-category">
      <div class="tech-cat-label">☁ DevOps &amp; Tools</div>
      <div class="badge-row">
        <span class="tech-badge badge-docker">🐳 Docker</span>
        <span class="tech-badge badge-aws">☁ AWS</span>
        <span class="tech-badge badge-git">🔥 Git</span>
        <span class="tech-badge badge-actions">⚡ Actions</span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-header"><span class="section-icon">🧠</span><span class="section-title">Competitive Programming</span><div class="section-line"></div></div>
    <div class="cp-grid">
      <div class="cp-card"><div><div class="cp-platform">Codeforces</div><div class="cp-handle">SIDHANT08</div></div><span class="cp-badge cf">Active</span></div>
      <div class="cp-card"><div><div class="cp-platform">LeetCode</div><div class="cp-handle">SIDHANT_8</div></div><span class="cp-badge lc">1800+</span></div>
      <div class="cp-card"><div><div class="cp-platform">CodeChef</div><div class="cp-handle">SIDHANT_8</div></div><span class="cp-badge cc">Active</span></div>
    </div>
    <div class="solved-banner">
      <div>
        <div class="solved-text">🔥 Total Problems Solved</div>
        <div class="solved-platforms">LeetCode · Codeforces · CodeChef · GFG · AtCoder</div>
      </div>
      <div class="solved-count">1800+</div>
    </div>
  </div>

  <div class="footer">Made with <span>♥</span> by Vaibhav Yadav &nbsp;·&nbsp; <span>v-vaibhav07</span></div>
</div>

<script>
const el=document.getElementById('contribCount');let count=0;const target=316;const interval=setInterval(()=>{count+=Math.ceil((target-count)/12);if(count>=target){count=target;clearInterval(interval);}el.textContent=count;},40);
const data=[35,10,6,4,5,4,7,11,12,9,14,13,10,8,12,11,10,8,7,9,8,7,6,8,9,6,7,8,10,8,5,4,6,5,4,3,2,3,4,3,2,3,4,3,2,3,2,3,2,3,2,3,2,3];
const labels=Array.from({length:data.length},(_,i)=>String(10+i));
const W=800,H=160,padL=28,padR=10,padT=10,padB=20,maxVal=Math.max(...data),plotW=W-padL-padR,plotH=H-padT-padB;
const xs=data.map((_,i)=>padL+(i/(data.length-1))*plotW);
const ys=data.map(v=>padT+plotH-(v/maxVal)*plotH);
function smooth(pts){let d=`M ${pts[0][0]} ${pts[0][1]}`;for(let i=1;i<pts.length;i++){const cp1x=pts[i-1][0]+(pts[i][0]-pts[i-1][0])*.4,cp1y=pts[i-1][1],cp2x=pts[i][0]-(pts[i][0]-pts[i-1][0])*.4,cp2y=pts[i][1];d+=` C ${cp1x} ${cp1y} ${cp2x} ${cp2y} ${pts[i][0]} ${pts[i][1]}`;}return d;}
const pts=xs.map((x,i)=>[x,ys[i]]);
const linePath=smooth(pts);
document.getElementById('chartLine').setAttribute('d',linePath);
document.getElementById('chartArea').setAttribute('d',linePath+` L ${xs[xs.length-1]} ${H-padB} L ${xs[0]} ${H-padB} Z`);
const dotsG=document.getElementById('chartDots');
pts.forEach(([x,y],i)=>{if(i%4===0||data[i]===maxVal){const dot=document.createElementNS('http://www.w3.org/2000/svg','circle');dot.setAttribute('cx',x);dot.setAttribute('cy',y);dot.setAttribute('r',data[i]===maxVal?5:3);dot.setAttribute('fill',data[i]===maxVal?'#ff6b35':'#00d4ff');dot.setAttribute('stroke','#0a0d13');dot.setAttribute('stroke-width','2');if(data[i]===maxVal)dot.setAttribute('filter','url(#glow)');dotsG.appendChild(dot);}});
const line=document.getElementById('chartLine');
const length=line.getTotalLength?.()||2000;
line.style.strokeDasharray=length;line.style.strokeDashoffset=length;line.style.transition='stroke-dashoffset 2s cubic-bezier(0.4,0,0.2,1) 0.5s';
setTimeout(()=>line.style.strokeDashoffset=0,100);
</script>
</body>
</html>
