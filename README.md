<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ritesh Paul — Cybersecurity Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root {
  --bg0:       #0d1117;   /* deepest bg */
  --bg1:       #111820;   /* main bg */
  --bg2:       #161d27;   /* card bg */
  --bg3:       #1c2531;   /* elevated */
  --bg4:       #222e3d;   /* hover state */
  --border:    #2a3a4a;
  --border-b:  #3a5060;
  --cyan:      #4fc3c8;   /* primary accent */
  --cyan-d:    #2d8f94;   /* muted accent */
  --cyan-xl:   rgba(79,195,200,.07);
  --slate:     #8ba4b8;   /* secondary text */
  --slate-d:   #5a7a90;   /* dim text */
  --white:     #d4dde6;   /* main text */
  --white-d:   #9db0c0;   /* mid text */
  --amber:     #c8a84b;
  --red:       #e06c75;
  --mono:      'JetBrains Mono', monospace;
  --sans:      'DM Sans', sans-serif;
}

*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }

body {
  background: var(--bg1);
  color: var(--white);
  font-family: var(--sans);
  font-size: 14px;
  line-height: 1.6;
  overflow-x: hidden;
}

/* scanline texture */
body::before {
  content: '';
  position: fixed; inset: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,.06) 2px, rgba(0,0,0,.06) 4px);
  pointer-events: none; z-index: 0;
}

/* corner grid accent */
body::after {
  content: '';
  position: fixed; inset: 0;
  background-image:
    linear-gradient(var(--border) 1px, transparent 1px),
    linear-gradient(90deg, var(--border) 1px, transparent 1px);
  background-size: 48px 48px;
  opacity: .12;
  pointer-events: none; z-index: 0;
}

/* ── NAV ── */
nav {
  position: fixed; top:0; left:0; right:0; z-index:100;
  display: flex; justify-content: space-between; align-items: center;
  padding: .7rem 2.5rem;
  background: rgba(13,17,23,.92);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
}
.nav-logo {
  font-family: var(--mono); font-size: .72rem; font-weight: 600;
  color: var(--cyan); letter-spacing: .06em;
}
.nav-logo span { color: var(--slate-d); font-weight: 400; }
nav ul { list-style:none; display:flex; gap:.2rem; }
nav ul a {
  color: var(--slate-d); text-decoration:none;
  font-family: var(--mono); font-size: .6rem; letter-spacing: .08em;
  padding: .25rem .65rem; border: 1px solid transparent;
  transition: all .15s;
}
nav ul a:hover { color: var(--cyan); border-color: var(--border); background: var(--bg3); }
.nav-status {
  display: flex; align-items: center; gap: .4rem;
  font-family: var(--mono); font-size: .58rem; color: var(--slate-d);
  border: 1px solid var(--border); padding: .2rem .6rem; background: var(--bg2);
}
.ndot { width:5px; height:5px; border-radius:50%; background: var(--cyan); animation: blink 2s step-end infinite; }
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:.15} }

main { position:relative; z-index:1; max-width:1100px; margin:0 auto; padding:5.5rem 2rem 4rem; }

/* ── HERO ── */
.hero { display:grid; grid-template-columns:1fr 270px; gap:.75rem; margin-bottom:.75rem; }

.hero-left {
  padding: 2.5rem;
  background: var(--bg2);
  border: 1px solid var(--border);
  position: relative; overflow: hidden;
}
.hero-left::before {
  content:''; position:absolute; top:0; left:0; right:0; height:2px;
  background: linear-gradient(90deg, var(--cyan), var(--cyan-d), transparent);
}
.hero-left::after {
  content:''; position:absolute; bottom:-60px; right:-60px;
  width:200px; height:200px;
  background: radial-gradient(circle, rgba(79,195,200,.06) 0%, transparent 70%);
  pointer-events:none;
}

.term-line {
  font-family: var(--mono); font-size: .6rem; color: var(--slate-d);
  margin-bottom: 1.4rem; display:flex; align-items:center; gap:.35rem;
}
.prompt { color: var(--cyan); }
.cur {
  display:inline-block; width:7px; height:.85em;
  background: var(--cyan); opacity:.7;
  animation: cur 1s step-end infinite; vertical-align:middle; margin-left:2px;
}
@keyframes cur { 0%,100%{opacity:.7} 50%{opacity:0} }

.hero-name {
  font-family: var(--mono); font-size: clamp(2.4rem,5vw,3.8rem);
  font-weight: 700; line-height:.95; letter-spacing:-.03em; color: var(--white);
}
.hero-name em { color: var(--cyan); font-style:normal; display:block; }

.hero-role {
  font-family: var(--mono); font-size: .58rem; color: var(--slate-d);
  letter-spacing: .18em; text-transform:uppercase;
  margin: 1.2rem 0 .8rem; display:flex; align-items:center; gap:.5rem;
}
.hero-role::before { content:''; display:inline-block; width:16px; height:1px; background: var(--border-b); }

.hero-desc { font-size: .83rem; color: var(--white-d); line-height:1.82; max-width:500px; margin-bottom:1.5rem; }

.hero-btns { display:flex; gap:.5rem; flex-wrap:wrap; }
.btn {
  font-family: var(--mono); font-size: .62rem; letter-spacing: .06em; text-transform:uppercase;
  padding: .5rem 1.1rem; text-decoration:none; border:1px solid; transition:all .15s;
  display:inline-flex; align-items:center; gap:.35rem;
}
.btn-p { border-color: var(--cyan-d); color: var(--bg0); background: var(--cyan); }
.btn-p:hover { background: var(--cyan-d); border-color: var(--cyan-d); }
.btn-o { border-color: var(--border); color: var(--slate); background: transparent; }
.btn-o:hover { border-color: var(--cyan-d); color: var(--cyan); background: var(--cyan-xl); }

/* SIDE PANELS */
.hero-right { display:flex; flex-direction:column; gap:.75rem; }
.panel { padding:1.2rem; background:var(--bg2); border:1px solid var(--border); }
.phdr {
  font-family: var(--mono); font-size: .5rem; letter-spacing: .22em; text-transform:uppercase;
  color: var(--slate-d); margin-bottom:.8rem; padding-bottom:.35rem; border-bottom:1px solid var(--border);
}
.drow { display:flex; justify-content:space-between; align-items:center; padding:.28rem 0; border-bottom:1px solid rgba(42,58,74,.5); font-size:.62rem; }
.drow:last-child { border-bottom:none; }
.dkey { font-family:var(--mono); color:var(--slate-d); font-size:.58rem; }
.dval { font-family:var(--mono); color:var(--cyan); font-weight:500; }
.dval.am { color:var(--amber); }
.dval.gr { color:#5cc8a0; }

.status-pill {
  display:inline-flex; align-items:center; gap:.38rem;
  font-family:var(--mono); font-size:.55rem; letter-spacing:.1em; text-transform:uppercase;
  color:var(--cyan); border:1px solid var(--border-b); padding:.22rem .6rem;
  background:rgba(79,195,200,.06); margin-top:.7rem;
}
.status-pill::before { content:''; width:5px; height:5px; border-radius:50%; background:var(--cyan); animation:blink 2s step-end infinite; }

/* ── STATS ── */
.stats {
  display:grid; grid-template-columns:repeat(4,1fr);
  gap:1px; background:var(--border); border:1px solid var(--border);
  margin-bottom:.75rem;
}
.stat { background:var(--bg2); padding:1.2rem 1rem; text-align:center; transition:background .15s; }
.stat:hover { background:var(--bg3); }
.stat-lbl { font-family:var(--mono); font-size:.5rem; letter-spacing:.14em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.3rem; }
.stat-n { font-family:var(--mono); font-size:2rem; font-weight:700; color:var(--cyan); line-height:1; }

/* ── SECTION HEADER ── */
.sg { margin-bottom:1.25rem; }
.sec-tag { font-family:var(--mono); font-size:.52rem; letter-spacing:.22em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.25rem; }
.sec-tag::before { content:'// '; color:var(--border-b); }
.sec-ttl { font-family:var(--mono); font-size:clamp(.95rem,2vw,1.25rem); font-weight:600; color:var(--white); }
.sec-ttl span { color:var(--cyan); }

/* ── PROJECT ── */
.pmain {
  background:var(--bg2); border:1px solid var(--border);
  padding:2rem; margin-bottom:.75rem; position:relative; overflow:hidden;
}
.pmain::before {
  content:''; position:absolute; top:0; left:0; right:0; height:2px;
  background:linear-gradient(90deg, var(--cyan), var(--cyan-d), transparent);
}
.pmain::after {
  content:''; position:absolute; top:-80px; right:-80px;
  width:260px; height:260px;
  background:radial-gradient(circle, rgba(79,195,200,.04) 0%, transparent 70%);
  pointer-events:none;
}
.pkick { font-family:var(--mono); font-size:.55rem; letter-spacing:.14em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.55rem; }
.pname { font-family:var(--mono); font-size:clamp(1.15rem,2.4vw,1.65rem); font-weight:700; color:var(--white); line-height:1.2; margin-bottom:.9rem; }
.pname em { color:var(--cyan); font-style:normal; }
.pbody { font-size:.82rem; color:var(--white-d); line-height:1.85; max-width:680px; margin-bottom:1.4rem; }
.pbody strong { color:var(--cyan); font-weight:600; }

.pipe-lbl { font-family:var(--mono); font-size:.5rem; letter-spacing:.18em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.45rem; }
.pipeline { display:flex; align-items:center; flex-wrap:wrap; margin-bottom:1.4rem; }
.pnode {
  border:1px solid var(--border); background:var(--bg3);
  padding:.42rem .72rem; font-family:var(--mono); font-size:.57rem; color:var(--slate);
  transition:all .15s; white-space:nowrap;
}
.pnode:hover { border-color:var(--border-b); color:var(--white); }
.pnode.mine { border-color:var(--cyan-d); background:var(--cyan-xl); color:var(--cyan); font-weight:600; }
.pvm { display:block; font-size:.45rem; letter-spacing:.14em; color:var(--slate-d); margin-bottom:.08rem; text-transform:uppercase; }
.pnode.mine .pvm { color:var(--cyan-d); }
.parr { color:var(--border-b); padding:0 .32rem; font-size:.75rem; }

.dtbl { width:100%; border-collapse:collapse; font-size:.71rem; margin:1rem 0; }
.dtbl th {
  font-family:var(--mono); font-size:.5rem; letter-spacing:.14em; text-transform:uppercase;
  color:var(--slate-d); padding:.42rem .72rem; text-align:left;
  border-bottom:1px solid var(--border); background:var(--bg3);
}
.dtbl td { padding:.62rem .72rem; border-bottom:1px solid rgba(42,58,74,.4); color:var(--white-d); vertical-align:top; line-height:1.55; }
.dtbl td:first-child { color:var(--cyan); font-family:var(--mono); font-size:.66rem; font-weight:500; }
.dtbl tr:hover td { background:var(--bg3); }

.tags { display:flex; flex-wrap:wrap; gap:.28rem; margin-top:1.2rem; }
.tag { font-family:var(--mono); font-size:.55rem; letter-spacing:.04em; padding:.18rem .48rem; border:1px solid var(--border); color:var(--slate-d); background:var(--bg3); }
.tag.c { border-color:rgba(79,195,200,.3); color:var(--cyan); background:var(--cyan-xl); }
.tag.r { border-color:rgba(224,108,117,.3); color:var(--red); background:rgba(224,108,117,.05); }

/* ── SUB CARDS ── */
.psub { display:grid; grid-template-columns:1fr 1fr; gap:.75rem; margin-bottom:.75rem; }
.subcard { padding:1.4rem; background:var(--bg2); border:1px solid var(--border); }
.card-hdr {
  font-family:var(--mono); font-size:.5rem; letter-spacing:.16em; text-transform:uppercase;
  color:var(--slate-d); margin-bottom:.55rem; padding-bottom:.38rem; border-bottom:1px solid var(--border);
}
.card-ttl { font-family:var(--mono); font-size:.88rem; font-weight:600; color:var(--white); margin-bottom:.8rem; }

.blist { list-style:none; }
.blist li { font-size:.71rem; color:var(--white-d); padding:.26rem 0; display:flex; gap:.45rem; line-height:1.55; border-bottom:1px solid rgba(42,58,74,.4); }
.blist li:last-child { border-bottom:none; }
.blist li::before { content:'→'; color:var(--cyan); flex-shrink:0; }

.rrow { display:flex; align-items:center; justify-content:space-between; padding:.38rem 0; border-bottom:1px solid rgba(42,58,74,.4); }
.rrow:last-of-type { border-bottom:none; }
.rdesc { font-size:.67rem; color:var(--white-d); }
.rval { font-family:var(--mono); font-size:.8rem; font-weight:600; color:var(--cyan); white-space:nowrap; margin-left:.6rem; }
.rbar { height:1px; background:linear-gradient(90deg, var(--cyan-d), var(--border)); margin:.1rem 0 .3rem; }

/* ── MINOR ── */
.mgrid { display:grid; grid-template-columns:1fr 1fr; gap:.75rem; margin-bottom:.75rem; }
.mcard { padding:1.4rem; background:var(--bg2); border:1px solid var(--border); position:relative; overflow:hidden; }
.mcard::before { content:''; position:absolute; top:0; left:0; width:2px; height:100%; background:linear-gradient(180deg, var(--cyan-d), transparent); }
.mkick { font-family:var(--mono); font-size:.5rem; letter-spacing:.12em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.38rem; }
.mtitle { font-family:var(--mono); font-size:.88rem; font-weight:600; color:var(--white); margin-bottom:.6rem; }
.mbody { font-size:.71rem; color:var(--white-d); line-height:1.78; }

/* ── EXPERIENCE ── */
.ecard {
  padding:1.4rem 1.7rem; background:var(--bg2); border:1px solid var(--border);
  margin-bottom:1px; position:relative; transition:border-color .15s;
}
.ecard:hover { border-color:var(--border-b); }
.ecard::before { content:''; position:absolute; left:0; top:0; bottom:0; width:2px; background:var(--bg4); transition:background .15s; }
.ecard:hover::before { background:var(--cyan); }
.etop { display:flex; justify-content:space-between; align-items:flex-start; margin-bottom:.55rem; gap:1rem; }
.erole { font-family:var(--mono); font-size:.92rem; font-weight:600; color:var(--white); }
.eorg { font-family:var(--mono); font-size:.6rem; color:var(--cyan-d); margin-top:.12rem; }
.eright { text-align:right; flex-shrink:0; }
.edate { font-family:var(--mono); font-size:.56rem; color:var(--slate-d); letter-spacing:.05em; }
.ebadge {
  display:inline-block; margin-top:.2rem;
  font-family:var(--mono); font-size:.48rem; letter-spacing:.1em; text-transform:uppercase;
  padding:.14rem .42rem; border:1px solid var(--border-b); color:var(--cyan); background:var(--cyan-xl);
}

/* ── SKILLS ── */
.sgrid { display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:var(--border); border:1px solid var(--border); margin-bottom:.75rem; }
.scell { background:var(--bg2); padding:1.2rem; transition:background .15s; }
.scell:hover { background:var(--bg3); }
.scat { font-family:var(--mono); font-size:.5rem; letter-spacing:.18em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.75rem; display:flex; align-items:center; gap:.32rem; }
.scat::before { content:'>_'; color:var(--cyan); }
.sitem { font-family:var(--mono); font-size:.65rem; color:var(--white-d); padding:.24rem 0; border-bottom:1px solid rgba(42,58,74,.35); }
.sitem:last-child { border-bottom:none; }
.sitem::before { content:'_ '; color:var(--border-b); }

/* ── CERTS ── */
.cgrid { display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:var(--border); border:1px solid var(--border); margin-bottom:.75rem; }
.ccell { background:var(--bg2); padding:1rem 1.2rem; display:flex; justify-content:space-between; align-items:flex-start; gap:.5rem; transition:background .15s; }
.ccell:hover { background:var(--bg3); }
.cname { font-size:.7rem; color:var(--white); font-weight:500; margin-bottom:.15rem; line-height:1.35; }
.ciss { font-family:var(--mono); font-size:.54rem; color:var(--slate-d); }
.cdate { font-family:var(--mono); font-size:.56rem; color:var(--cyan); white-space:nowrap; flex-shrink:0; }

/* ── EDUCATION ── */
.erow { display:grid; grid-template-columns:1fr 1fr; gap:1px; background:var(--border); border:1px solid var(--border); margin-bottom:.75rem; }
.educard { background:var(--bg2); padding:1.4rem 1.7rem; transition:background .15s; }
.educard:hover { background:var(--bg3); }
.edeg { font-family:var(--mono); font-size:.8rem; font-weight:600; color:var(--white); margin-bottom:.28rem; }
.esch { font-family:var(--mono); font-size:.62rem; color:var(--cyan-d); margin-bottom:.18rem; }
.eyr { font-family:var(--mono); font-size:.58rem; color:var(--slate-d); }

/* ── CONTACT ── */
.ctgrid { display:grid; grid-template-columns:1fr 1fr; gap:.75rem; margin-bottom:.75rem; }
.ctmain { padding:2rem; background:var(--bg2); border:1px solid var(--border); position:relative; overflow:hidden; }
.ctmain::before { content:''; position:absolute; top:0; left:0; right:0; height:2px; background:linear-gradient(90deg, var(--cyan), var(--cyan-d), transparent); }
.ctmain::after { content:''; position:absolute; bottom:-60px; left:-60px; width:200px; height:200px; background:radial-gradient(circle, rgba(79,195,200,.05), transparent 70%); pointer-events:none; }
.cth { font-family:var(--mono); font-size:clamp(1rem,2vw,1.4rem); font-weight:700; color:var(--white); line-height:1.25; margin-bottom:.65rem; }
.cth span { color:var(--cyan); }
.ctsub { font-size:.76rem; color:var(--white-d); line-height:1.78; margin-bottom:1.1rem; }
.ctlinks { display:flex; flex-direction:column; gap:1px; background:var(--border); border:1px solid var(--border); }
.ctlink { background:var(--bg2); padding:.9rem 1.1rem; display:flex; justify-content:space-between; align-items:center; text-decoration:none; color:inherit; transition:background .15s; }
.ctlink:hover { background:var(--bg3); }
.cll { display:block; font-family:var(--mono); font-size:.48rem; letter-spacing:.18em; text-transform:uppercase; color:var(--slate-d); margin-bottom:.12rem; }
.ctlink div { font-family:var(--mono); font-size:.68rem; color:var(--white-d); }
.cla { font-family:var(--mono); font-size:.7rem; color:var(--border-b); transition:color .15s; }
.ctlink:hover .cla { color:var(--cyan); }

/* ── FOOTER ── */
footer {
  border-top:1px solid var(--border); padding:1rem 2.5rem;
  display:flex; justify-content:space-between; align-items:center;
  font-family:var(--mono); font-size:.52rem; letter-spacing:.1em; text-transform:uppercase;
  color:var(--slate-d); background:var(--bg0); position:relative; z-index:1;
}

/* ── ANIMATIONS ── */
.fu { opacity:0; transform:translateY(16px); animation:fu .5s ease forwards; }
@keyframes fu { to { opacity:1; transform:translateY(0); } }
.d1{animation-delay:.05s}.d2{animation-delay:.12s}.d3{animation-delay:.19s}.d4{animation-delay:.26s}
</style>
</head>
<body>

<nav>
  <div class="nav-logo">RITESH_PAUL<span>.exe</span></div>
  <ul>
    <li><a href="#project">project</a></li>
    <li><a href="#exp">experience</a></li>
    <li><a href="#skills">skills</a></li>
    <li><a href="#contact">contact</a></li>
  </ul>
  <div class="nav-status"><span class="ndot"></span>available · bangalore</div>
</nav>

<main>

<div class="hero fu d1">
  <div class="hero-left">
    <div class="term-line"><span class="prompt">❯</span> whoami<span class="cur"></span></div>
    <div class="hero-name">RITESH<em>PAUL</em></div>
    <div class="hero-role">SOC Operations · Threat Intelligence · Incident Response</div>
    <p class="hero-desc">B.Tech Cybersecurity student (graduating 2027) with hands-on SOC experience in a live government Security Operations Center — triaging <strong style="color:var(--cyan)">50+ alerts daily</strong> using ArcSight SIEM. I build systems, not just learn tools.</p>
    <div class="hero-btns">
      <a class="btn btn-p" href="mailto:riteshpaul262@gmail.com">→ contact me</a>
      <a class="btn btn-o" href="https://linkedin.com/in/riteshpaul262" target="_blank">linkedin</a>
      <a class="btn btn-o" href="https://github.com/RITESH-we" target="_blank">github</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="panel">
      <div class="phdr">sys_status</div>
      <div class="drow"><span class="dkey">ARCSIGHT</span><span class="dval">PROFICIENT</span></div>
      <div class="drow"><span class="dkey">SURICATA IDS</span><span class="dval">PROFICIENT</span></div>
      <div class="drow"><span class="dkey">MITRE ATT&CK</span><span class="dval">PROFICIENT</span></div>
      <div class="drow"><span class="dkey">PYTHON 3.11</span><span class="dval">PROFICIENT</span></div>
      <div class="drow"><span class="dkey">REDIS STREAMS</span><span class="dval am">FAMILIAR</span></div>
      <div class="drow"><span class="dkey">SPLUNK</span><span class="dval am">FAMILIAR</span></div>
      <div class="status-pill">● analyst online</div>
    </div>
    <div class="panel">
      <div class="phdr">identity</div>
      <div class="drow"><span class="dkey">DEGREE</span><span class="dval gr">B.TECH CSE</span></div>
      <div class="drow"><span class="dkey">STREAM</span><span class="dval gr">CYBERSECURITY</span></div>
      <div class="drow"><span class="dkey">GRAD</span><span class="dval">JUL 2027</span></div>
      <div class="drow"><span class="dkey">BASE</span><span class="dval">BANGALORE</span></div>
    </div>
  </div>
</div>

<div class="stats fu d2">
  <div class="stat"><div class="stat-lbl">Azure VMs deployed</div><div class="stat-n">5</div></div>
  <div class="stat"><div class="stat-lbl">E2E pipeline latency</div><div class="stat-n">3–5s</div></div>
  <div class="stat"><div class="stat-lbl">Custom IDS rules</div><div class="stat-n">15</div></div>
  <div class="stat"><div class="stat-lbl">Attack scenarios validated</div><div class="stat-n">13</div></div>
</div>

<div class="sg fu d1" id="project">
  <div class="sec-tag">Major Project</div>
  <div class="sec-ttl">Location-Based <span>Threat Intel</span> Alert System</div>
</div>

<div class="pmain fu d2">
  <div class="pkick">// Sri Sri University · Team of 5 · Microsoft Azure · 2025–2026</div>
  <div class="pname">Distributed SOC Pipeline — <em>Detection to Dashboard</em></div>
  <p class="pbody">A fully distributed, multi-VM security monitoring system replicating a production Security Operations Center. Detection-to-dashboard across 5 Azure VMs with 3–5 second end-to-end latency. <strong>My role: I owned VM-1, the front-line sensor layer</strong> — deploying Suricata IDS, writing all 15 custom detection rules covering OWASP Top 10, configuring Filebeat with cursor persistence, and validating against 13 real attack scenarios on OWASP Juice Shop.</p>

  <div class="pipe-lbl">// pipeline architecture</div>
  <div class="pipeline">
    <div class="pnode"><span class="pvm">VM-7</span>Attacker</div>
    <div class="parr">→</div>
    <div class="pnode mine"><span class="pvm">VM-1 · my layer</span>Suricata IDS + Filebeat</div>
    <div class="parr">→</div>
    <div class="pnode"><span class="pvm">VM-2</span>Redis + TI Fetcher</div>
    <div class="parr">→</div>
    <div class="pnode"><span class="pvm">VM-3</span>Normaliser → Enricher → Correlator</div>
    <div class="parr">→</div>
    <div class="pnode"><span class="pvm">VM-4</span>PostgreSQL + PostGIS</div>
    <div class="parr">→</div>
    <div class="pnode"><span class="pvm">VM-5</span>FastAPI + React Dashboard</div>
  </div>

  <table class="dtbl">
    <thead><tr><th>// decision</th><th>implementation</th><th>why it matters</th></tr></thead>
    <tbody>
      <tr><td>Event-driven microservices</td><td>Redis Streams + Consumer Groups; 5 Python services</td><td>At-least-once delivery; independent failure isolation</td></tr>
      <tr><td>3-source TI correlation</td><td>Cache-first batch — VirusTotal, AbuseIPDB, AlienVault OTX</td><td>Stays within free API rate limits; O(1) enrichment</td></tr>
      <tr><td>Geospatial storage</td><td>PostGIS GEOGRAPHY(Point, 4326) with GIST index</td><td>Real spherical-earth queries; spatial analytics without a commercial SIEM</td></tr>
      <tr><td>Custom IDS ruleset</td><td>15 Suricata rules — signature + threshold — OWASP Top 10</td><td>Brute force &amp; port scan require threshold rules; signatures alone miss them</td></tr>
      <tr><td>Alert lifecycle mgmt</td><td>Acknowledge / Resolve + full audit_log table</td><td>PCI-DSS / ISO 27001 compliant; mirrors real SOC analyst workflows</td></tr>
    </tbody>
  </table>

  <div class="tags">
    <span class="tag c">Suricata 7.0</span><span class="tag c">Redis Streams</span><span class="tag c">PostgreSQL + PostGIS</span><span class="tag c">FastAPI</span><span class="tag c">React 18</span>
    <span class="tag r">VirusTotal API</span><span class="tag r">AbuseIPDB</span><span class="tag r">AlienVault OTX</span>
    <span class="tag">Python 3.11</span><span class="tag">Filebeat 8.11</span><span class="tag">Microsoft Azure</span><span class="tag">MITRE ATT&CK</span><span class="tag">OWASP Top 10</span><span class="tag">Leaflet.js</span>
  </div>
</div>

<div class="psub">
  <div class="subcard fu d2">
    <div class="card-hdr">// VM-1 · my contribution · sensor layer</div>
    <div class="card-ttl">Front-Line Detection Engineering</div>
    <ul class="blist">
      <li>Deployed Suricata IDS with AF-PACKET capture and EVE JSON logging on VM-1</li>
      <li>Wrote all 15 custom detection rules — SQLi, XSS, directory traversal, brute force, port scan — using signature-based and threshold-based detection logic</li>
      <li>Configured Filebeat for resilient log shipping to VM-2 Redis with cursor persistence (zero event loss on restart) and sensor metadata enrichment</li>
      <li>Set up OWASP Juice Shop as attack target; validated all 15 rules against 13 real attack scenarios</li>
    </ul>
  </div>
  <div class="subcard fu d3">
    <div class="card-hdr">// risk scoring algorithm · 0–100 composite</div>
    <div class="card-ttl">Threat Scoring Model</div>
    <div class="rrow"><span class="rdesc">Suricata rule severity × 10</span><span class="rval">+10–30</span></div>
    <div class="rbar" style="width:60%"></div>
    <div class="rrow"><span class="rdesc">AbuseIPDB confidence ÷ 10</span><span class="rval">+0–10</span></div>
    <div class="rbar" style="width:25%"></div>
    <div class="rrow"><span class="rdesc">Destination IP in TI feeds</span><span class="rval">+20</span></div>
    <div class="rbar" style="width:50%"></div>
    <div class="rrow"><span class="rdesc">Persistent attacker (5-min window)</span><span class="rval">+5/evt</span></div>
    <div class="rbar" style="width:35%"></div>
    <div class="rrow"><span class="rdesc">External source (not in CMDB)</span><span class="rval">+15</span></div>
    <div class="rbar" style="width:45%"></div>
    <div class="rrow"><span class="rdesc">Target is datacenter infrastructure</span><span class="rval">+20</span></div>
    <div class="rbar" style="width:50%"></div>
  </div>
</div>

<div class="sg fu d1">
  <div class="sec-tag">Other Projects</div>
  <div class="sec-ttl">More <span>Work</span></div>
</div>
<div class="mgrid">
  <div class="mcard fu d1">
    <div class="mkick">// Team of 5 · Sri Sri University · Cisco Packet Tracer</div>
    <div class="mtitle">Oil &amp; Gas Network Security Architecture</div>
    <p class="mbody">Designed a resilient five-zone network for a simulated oil and gas company. Zones: DMZ (WAF + IDPS + dual firewalls), Enterprise (VLAN-segmented), Field (PLCs / sensors / actuators), Control (SCADA / HMI / Historian), Secure Ops (SIEM + Jump Server + NMS). Distributed firewalls at every boundary. Fiber backbone with OSPF/BGP failover, IPSec VPNs, VSAT for offshore. Aligned to IEC 62443 &amp; NIST CSF.</p>
    <div class="tags" style="margin-top:1rem;"><span class="tag">Cisco Packet Tracer</span><span class="tag">VLAN / OSPF</span><span class="tag">SCADA / HMI</span><span class="tag">IPSec VPN</span><span class="tag">IEC 62443</span><span class="tag">NIST CSF</span></div>
  </div>
  <div class="mcard fu d2">
    <div class="mkick">// EDUNET Foundation Internship · May–Jun 2025</div>
    <div class="mtitle">Covert Data Hiding System</div>
    <p class="mbody">Built a steganography-based data-hiding system combining AES-256 encryption with LSB steganography to covertly embed data inside PNG/JPG images. Analysed detectability and extraction risks — exploring covert channel security gaps and forensic countermeasures that detect carrier image anomalies.</p>
    <div class="tags" style="margin-top:1rem;"><span class="tag">Python</span><span class="tag">AES-256</span><span class="tag">LSB Steganography</span><span class="tag">Cryptography</span></div>
  </div>
</div>

<div class="sg fu d1" id="exp">
  <div class="sec-tag">Work Experience</div>
  <div class="sec-ttl">In the <span>Field</span></div>
</div>

<div class="ecard fu d1">
  <div class="etop">
    <div><div class="erole">SOC Analyst Intern</div><div class="eorg">OCAC Tower — CSOC · Government of Odisha · Bhubaneswar</div></div>
    <div class="eright"><div class="edate">FEB 2026 – MAR 2026</div><div class="ebadge">45-day live engagement</div></div>
  </div>
  <ul class="blist">
    <li>Monitored and triaged 50+ live security alerts daily using ArcSight SIEM in a live government Security Operations Center</li>
    <li>Investigated a confirmed brute force attack (MITRE ATT&CK T1110) — log analysis, IOC enrichment via VirusTotal &amp; AbuseIPDB, managed ITMS tickets, escalated under senior analyst guidance</li>
    <li>Gained hands-on exposure to real SOC workflows, alert prioritisation, and TTP-based escalation in a high-stakes government environment</li>
  </ul>
</div>
<div class="ecard fu d2">
  <div class="etop">
    <div><div class="erole">Cybersecurity Intern</div><div class="eorg">EDUNET Foundation · Remote</div></div>
    <div class="eright"><div class="edate">MAY 2025 – JUN 2025</div></div>
  </div>
  <ul class="blist">
    <li>Built a steganography-based data-hiding system combining AES-256 encryption with LSB steganography to covertly embed data inside PNG/JPG images</li>
    <li>Analysed system for detectability and extraction risks; explored covert channel techniques and forensic countermeasures</li>
  </ul>
</div>
<div class="ecard fu d3">
  <div class="etop">
    <div><div class="erole">Cybersecurity Intern</div><div class="eorg">ACMEGRADE · Remote</div></div>
    <div class="eright"><div class="edate">JAN 2024 – MAR 2024</div></div>
  </div>
  <ul class="blist">
    <li>Performed Nmap-based network reconnaissance and vulnerability assessment in a simulated lab environment</li>
    <li>Documented findings in structured vulnerability reports</li>
  </ul>
</div>

<div class="sg fu d1" id="skills">
  <div class="sec-tag">Technical Skills</div>
  <div class="sec-ttl"><span>Capabilities</span></div>
</div>
<div class="sgrid fu d2">
  <div class="scell"><div class="scat">SIEM &amp; Detection</div><div class="sitem">ArcSight SIEM</div><div class="sitem">Splunk (familiar)</div><div class="sitem">Suricata IDS</div><div class="sitem">Filebeat</div><div class="sitem">Redis Streams</div></div>
  <div class="scat">Threat Intelligence</div><div class="sitem">VirusTotal</div><div class="sitem">AbuseIPDB</div><div class="sitem">AlienVault OTX</div><div class="sitem">IOC Analysis</div><div class="sitem">MITRE ATT&CK / TTP Mapping</div></div>
  <div class="scell"><div class="scat">Incident Response</div><div class="sitem">Alert Triage</div><div class="sitem">Log Analysis</div><div class="sitem">Escalation Workflows</div><div class="sitem">ITMS Ticketing</div></div>
  <div class="scell"><div class="scat">Network Security</div><div class="sitem">Firewall Design</div><div class="sitem">VLAN / DMZ Architecture</div><div class="sitem">Nmap Reconnaissance</div><div class="sitem">Cisco Packet Tracer</div></div>
  <div class="scell"><div class="scat">Cloud &amp; Infra</div><div class="sitem">Microsoft Azure (VMs)</div><div class="sitem">AWS EC2 / S3 (learning)</div><div class="sitem">Python 3.11</div><div class="sitem">Kali Linux / Ubuntu</div></div>
  <div class="scell"><div class="scat">Security Concepts</div><div class="sitem">AES-256 Encryption</div><div class="sitem">LSB Steganography</div><div class="sitem">Vulnerability Analysis</div><div class="sitem">OWASP Top 10</div></div>
</div>

<div class="sg fu d1">
  <div class="sec-tag">Certifications</div>
  <div class="sec-ttl"><span>Credentials</span></div>
</div>
<div class="cgrid fu d2">
  <div class="ccell"><div><div class="cname">CCNA: Introduction to Networks</div><div class="ciss">Cisco</div></div><div class="cdate">Jun 2024</div></div>
  <div class="ccell"><div><div class="cname">Introduction to CIP</div><div class="ciss">OPSWAT Academy</div></div><div class="cdate">Jan 2026</div></div>
  <div class="ccell"><div><div class="cname">Tata Cybersecurity Analyst Simulation</div><div class="ciss">Forage</div></div><div class="cdate">Jul 2025</div></div>
  <div class="ccell"><div><div class="cname">Mastercard Cybersecurity Simulation</div><div class="ciss">Forage</div></div><div class="cdate">Jan 2025</div></div>
  <div class="ccell"><div><div class="cname">Foundations of Cybersecurity</div><div class="ciss">Google</div></div><div class="cdate">Nov 2023</div></div>
  <div class="ccell"><div><div class="cname">Fundamentals of Red Hat Enterprise Linux</div><div class="ciss">Red Hat</div></div><div class="cdate">Dec 2023</div></div>
</div>

<div class="sg fu d1">
  <div class="sec-tag">Education</div>
  <div class="sec-ttl"><span>Training</span></div>
</div>
<div class="erow fu d2">
  <div class="educard"><div class="edeg">B.Tech — CSE (Cybersecurity &amp; Cyber Defense)</div><div class="esch">Sri Sri University · Cuttack, Odisha</div><div class="eyr">Expected Jul 2027</div></div>
  <div class="educard"><div class="edeg">Higher Secondary · Class XII — Science</div><div class="esch">Kendriya Vidyalaya AFS Yelahanka · Bangalore</div><div class="eyr">2023</div></div>
</div>

<div class="sg fu d1" id="contact">
  <div class="sec-tag">Contact</div>
  <div class="sec-ttl">Establish <span>Connection</span></div>
</div>
<div class="ctgrid fu d2">
  <div class="ctmain">
    <div class="cth">Open to<br><span>SOC roles</span><br>&amp; internships.</div>
    <p class="ctsub">Currently pursuing B.Tech Cybersecurity at Sri Sri University (graduating Jul 2027). Available for internships and entry-level cybersecurity positions in SOC operations, threat intelligence, or incident response.</p>
    <a class="btn btn-p" href="mailto:riteshpaul262@gmail.com">→ initiate contact</a>
  </div>
  <div class="ctlinks">
    <a class="ctlink" href="mailto:riteshpaul262@gmail.com"><div><span class="cll">Email</span>riteshpaul262@gmail.com</div><span class="cla">↗</span></a>
    <a class="ctlink" href="https://linkedin.com/in/riteshpaul262" target="_blank"><div><span class="cll">LinkedIn</span>linkedin.com/in/riteshpaul262</div><span class="cla">↗</span></a>
    <a class="ctlink" href="https://github.com/RITESH-we" target="_blank"><div><span class="cll">GitHub</span>github.com/RITESH-we</div><span class="cla">↗</span></a>
    <div class="ctlink" style="cursor:default"><div><span class="cll">Phone</span>+91 95472 44315</div><span style="color:var(--border-b)">◈</span></div>
    <div class="ctlink" style="cursor:default"><div><span class="cll">Location</span>Bangalore, India</div><span style="color:var(--border-b)">◈</span></div>
  </div>
</div>

</main>

<footer>
  <span>RITESH PAUL · CYBERSECURITY ANALYST</span>
  <span>B.TECH CSE (CYBERSECURITY) · SRI SRI UNIVERSITY · 2027</span>
  <span>SYS_VER: 2026.05</span>
</footer>

</body>
</html>
