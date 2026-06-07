
<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:wght@300;400;500;600&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#03050f;
  --surface:rgba(255,255,255,0.04);
  --surface-hover:rgba(255,255,255,0.07);
  --border:rgba(255,255,255,0.08);
  --border-accent:rgba(0,245,212,0.18);
  --cyan:#00f5d4;
  --violet:#7c3aed;
  --pink:#f472b6;
  --blue:#38bdf8;
  --text:#f0f4ff;
  --text-2:rgba(240,244,255,0.65);
  --text-3:rgba(240,244,255,0.35);
  --font-d:'Syne',sans-serif;
  --font-b:'DM Sans',sans-serif;
  --r:12px;
  --r-lg:18px;
}
body{background:var(--bg);color:var(--text);font-family:var(--font-b);font-size:14px;line-height:1.5;padding:24px;min-height:100vh}
.sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}

/* Profile header */
.profile{display:flex;gap:24px;align-items:flex-start;margin-bottom:24px}
.avatar-wrap{position:relative;flex-shrink:0}
.avatar-img{width:80px;height:80px;border-radius:50%;background:linear-gradient(135deg,#00f5d4,#7c3aed);display:flex;align-items:center;justify-content:center;font-family:var(--font-d);font-size:26px;font-weight:800;color:#060914;box-shadow:0 0 0 3px var(--bg),0 0 0 5px var(--cyan)}
.status-dot{position:absolute;bottom:4px;right:4px;width:14px;height:14px;border-radius:50%;background:#22c55e;border:2.5px solid var(--bg);box-shadow:0 0 8px #22c55e}
.profile-info{flex:1}
.profile-name{font-family:var(--font-d);font-size:22px;font-weight:800;letter-spacing:-0.5px;margin-bottom:2px}
.profile-name span{background:linear-gradient(135deg,var(--cyan),var(--violet));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.profile-handle{font-size:13px;color:var(--text-2);margin-bottom:10px}
.profile-bio{font-size:13px;color:var(--text-2);font-weight:300;line-height:1.6;max-width:480px;margin-bottom:12px}
.profile-pills{display:flex;flex-wrap:wrap;gap:8px}
.pill{font-size:11px;font-weight:500;padding:3px 10px;border-radius:50px;border:1px solid var(--border);color:var(--text-2);display:flex;align-items:center;gap:5px;background:var(--surface)}
.pill i{font-size:13px;color:var(--cyan)}

/* Stats bar */
.stats-bar{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:24px}
.stat-card{background:var(--surface);border:0.5px solid var(--border);border-radius:var(--r);padding:14px 16px;transition:border-color 0.2s,background 0.2s}
.stat-card:hover{background:var(--surface-hover);border-color:var(--border-accent)}
.stat-val{font-family:var(--font-d);font-size:22px;font-weight:800;letter-spacing:-0.5px;color:var(--cyan);display:block;margin-bottom:2px}
.stat-lbl{font-size:11px;color:var(--text-3);letter-spacing:0.06em;text-transform:uppercase}

/* Two column layout */
.cols{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px}
.col-wide{grid-column:span 2}

/* Card */
.card{background:var(--surface);border:0.5px solid var(--border);border-radius:var(--r-lg);padding:20px;transition:border-color 0.2s}
.card:hover{border-color:var(--border-accent)}
.card-title{font-size:11px;font-weight:600;letter-spacing:0.1em;text-transform:uppercase;color:var(--text-3);margin-bottom:16px;display:flex;align-items:center;gap:8px}
.card-title i{font-size:14px;color:var(--cyan)}

/* Contribution grid */
.contrib-grid{display:flex;flex-direction:column;gap:3px}
.contrib-row{display:flex;gap:3px;align-items:center}
.contrib-label{font-size:10px;color:var(--text-3);width:20px;text-align:right;flex-shrink:0;font-family:var(--font-b)}
.contrib-cells{display:flex;gap:3px}
.cell{width:11px;height:11px;border-radius:3px;transition:transform 0.15s,opacity 0.15s;cursor:default;flex-shrink:0}
.cell:hover{transform:scale(1.4);z-index:10;position:relative}
.c0{background:rgba(255,255,255,0.05)}
.c1{background:rgba(0,245,212,0.2)}
.c2{background:rgba(0,245,212,0.45)}
.c3{background:rgba(0,245,212,0.7)}
.c4{background:var(--cyan);box-shadow:0 0 6px rgba(0,245,212,0.5)}
.month-labels{display:flex;gap:3px;padding-left:28px;margin-bottom:4px}
.month-label{font-size:9px;color:var(--text-3);font-family:var(--font-b)}

/* Lang bars */
.lang-item{margin-bottom:14px}
.lang-header{display:flex;justify-content:space-between;margin-bottom:5px}
.lang-name{font-size:13px;font-weight:500;display:flex;align-items:center;gap:7px}
.lang-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0}
.lang-pct{font-size:12px;color:var(--text-3);font-weight:600}
.lang-track{height:5px;background:rgba(255,255,255,0.06);border-radius:50px;overflow:hidden}
.lang-fill{height:100%;border-radius:50px;transition:width 1.2s cubic-bezier(0.16,1,0.3,1)}

/* Pinned repos */
.repos-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.repo-card{background:rgba(255,255,255,0.025);border:0.5px solid var(--border);border-radius:var(--r);padding:16px;transition:all 0.25s;cursor:pointer;position:relative;overflow:hidden}
.repo-card::before{content:'';position:absolute;top:0;left:-100%;width:50%;height:100%;background:linear-gradient(105deg,transparent,rgba(255,255,255,0.04),transparent);transform:skewX(-15deg);transition:left 0.5s}
.repo-card:hover::before{left:140%}
.repo-card:hover{border-color:rgba(0,245,212,0.15);background:rgba(0,245,212,0.03)}
.repo-name{font-size:13px;font-weight:600;color:var(--cyan);margin-bottom:6px;display:flex;align-items:center;gap:6px}
.repo-name i{font-size:14px}
.repo-desc{font-size:12px;color:var(--text-2);font-weight:300;line-height:1.5;margin-bottom:12px}
.repo-meta{display:flex;gap:12px;align-items:center}
.repo-lang{display:flex;align-items:center;gap:5px;font-size:11px;color:var(--text-3)}
.repo-stat{display:flex;align-items:center;gap:4px;font-size:11px;color:var(--text-3)}
.repo-stat i{font-size:12px}

/* Activity feed */
.activity-item{display:flex;gap:12px;align-items:flex-start;padding:10px 0;border-bottom:0.5px solid rgba(255,255,255,0.04)}
.activity-item:last-child{border:none;padding-bottom:0}
.act-icon{width:30px;height:30px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0}
.act-text{flex:1}
.act-main{font-size:12px;color:var(--text);line-height:1.5}
.act-main strong{color:var(--cyan);font-weight:600}
.act-time{font-size:10px;color:var(--text-3);margin-top:2px}

/* Skill radar area */
.skill-bars{display:flex;flex-direction:column;gap:10px}
.sk-row{display:flex;align-items:center;gap:10px}
.sk-name{font-size:12px;color:var(--text-2);width:80px;flex-shrink:0;text-align:right}
.sk-track{flex:1;height:6px;background:rgba(255,255,255,0.06);border-radius:50px;overflow:hidden}
.sk-fill{height:100%;border-radius:50px}
.sk-val{font-size:11px;color:var(--text-3);width:32px;text-align:right;flex-shrink:0}

/* streak */
.streak-row{display:flex;gap:16px;margin-top:4px}
.streak-item{text-align:center}
.streak-num{font-family:var(--font-d);font-size:28px;font-weight:800;letter-spacing:-1px}
.streak-sub{font-size:10px;color:var(--text-3);text-transform:uppercase;letter-spacing:0.08em;margin-top:2px}
.cyan{color:var(--cyan)}
.violet{color:#a78bfa}
.pink{color:var(--pink)}

/* chart canvas */
.chart-wrap{position:relative;width:100%;height:180px}
</style>

<h2 class="sr-only">Amal K B — GitHub-style developer portfolio dashboard</h2>

<!-- Profile -->
<div class="profile">
  <div class="avatar-wrap">
    <div class="avatar-img">AKB</div>
    <div class="status-dot"></div>
  </div>
  <div class="profile-info">
    <div class="profile-name"><span>Amal K B</span></div>
    <div class="profile-handle">@amalkb10 · Full Stack Developer</div>
    <div class="profile-bio">Building end-to-end products — from MERN web apps to Vision Transformer surveillance systems. CS graduate, Coorg Institute of Technology.</div>
    <div class="profile-pills">
      <div class="pill"><i class="ti ti-map-pin" aria-hidden="true"></i>Coorg, Karnataka</div>
      <div class="pill"><i class="ti ti-briefcase" aria-hidden="true"></i>Open to SDE roles</div>
      <div class="pill"><i class="ti ti-school" aria-hidden="true"></i>B.E. CSE 2026</div>
      <div class="pill"><i class="ti ti-building" aria-hidden="true"></i>Ex-Intern @ Prinston</div>
    </div>
  </div>
</div>

<!-- Stats -->
<div class="stats-bar">
  <div class="stat-card"><span class="stat-val">4</span><span class="stat-lbl">Repositories</span></div>
  <div class="stat-card"><span class="stat-val" id="contrib-count">312</span><span class="stat-lbl">Contributions</span></div>
  <div class="stat-card"><span class="stat-val">3+</span><span class="stat-lbl">Months intern</span></div>
  <div class="stat-card"><span class="stat-val">7.0</span><span class="stat-lbl">CGPA</span></div>
</div>

<!-- Row 1: Contribution graph (full width) -->
<div class="card col-wide" style="margin-bottom:16px">
  <div class="card-title"><i class="ti ti-chart-dots" aria-hidden="true"></i>Contribution activity — 2025 → 2026</div>
  <div id="contrib-area"></div>
  <div style="display:flex;justify-content:space-between;align-items:center;margin-top:12px">
    <div style="display:flex;align-items:center;gap:6px;font-size:11px;color:var(--text-3)">
      Less
      <div class="cell c0"></div><div class="cell c1"></div><div class="cell c2"></div><div class="cell c3"></div><div class="cell c4"></div>
      More
    </div>
    <div class="streak-row">
      <div class="streak-item"><div class="streak-num cyan" id="streak-val">14</div><div class="streak-sub">Day streak</div></div>
      <div class="streak-item"><div class="streak-num violet">312</div><div class="streak-sub">This year</div></div>
      <div class="streak-item"><div class="streak-num pink">47</div><div class="streak-sub">Best week</div></div>
    </div>
  </div>
</div>

<!-- Row 2: Languages + Skills -->
<div class="cols" style="margin-bottom:16px">
  <div class="card">
    <div class="card-title"><i class="ti ti-code" aria-hidden="true"></i>Languages used</div>
    <div id="lang-bars"></div>
    <div style="margin-top:16px">
      <div class="card-title" style="margin-bottom:12px"><i class="ti ti-chart-bar" aria-hidden="true"></i>Commits by language</div>
      <div class="chart-wrap" style="height:140px"><canvas id="langChart" role="img" aria-label="Bar chart of commits by programming language">JavaScript 140, Python 85, C/C++ 40, CSS 28, Others 19.</canvas></div>
    </div>
  </div>
  <div class="card">
    <div class="card-title"><i class="ti ti-adjustments" aria-hidden="true"></i>Tech proficiency</div>
    <div class="skill-bars" id="skill-bars"></div>
    <div style="margin-top:20px">
      <div class="card-title" style="margin-bottom:12px"><i class="ti ti-activity" aria-hidden="true"></i>Commit activity (last 6 months)</div>
      <div class="chart-wrap" style="height:120px"><canvas id="actChart" role="img" aria-label="Line chart of monthly commit activity over the last 6 months">Nov 12, Dec 8, Jan 22, Feb 38, Mar 54, Apr 47.</canvas></div>
    </div>
  </div>
</div>

<!-- Row 3: Pinned repos -->
<div class="card" style="margin-bottom:16px">
  <div class="card-title"><i class="ti ti-pin" aria-hidden="true"></i>Pinned repositories</div>
  <div class="repos-grid">
    <div class="repo-card">
      <div class="repo-name"><i class="ti ti-brand-github" aria-hidden="true"></i>AI-Surveillance-UAD</div>
      <div class="repo-desc">Vision Transformer model for unusual activity detection. Pruned & quantized for embedded deployment.</div>
      <div class="repo-meta">
        <div class="repo-lang"><span class="lang-dot" style="background:#3572A5"></span>Python</div>
        <div class="repo-stat"><i class="ti ti-star" aria-hidden="true"></i>12</div>
        <div class="repo-stat"><i class="ti ti-git-fork" aria-hidden="true"></i>3</div>
      </div>
    </div>
    <div class="repo-card">
      <div class="repo-name"><i class="ti ti-brand-github" aria-hidden="true"></i>Coorg-Pantry</div>
      <div class="repo-desc">Full-stack MERN food ordering platform with cart, auth, and RESTful backend for Coorg-region products.</div>
      <div class="repo-meta">
        <div class="repo-lang"><span class="lang-dot" style="background:#f1e05a"></span>JavaScript</div>
        <div class="repo-stat"><i class="ti ti-star" aria-hidden="true"></i>8</div>
        <div class="repo-stat"><i class="ti ti-git-fork" aria-hidden="true"></i>2</div>
      </div>
    </div>
    <div class="repo-card">
      <div class="repo-name"><i class="ti ti-brand-github" aria-hidden="true"></i>Weather-Monitor</div>
      <div class="repo-desc">React + Node.js dashboard with live weather API, dynamic charts, and real-time data updates.</div>
      <div class="repo-meta">
        <div class="repo-lang"><span class="lang-dot" style="background:#f1e05a"></span>JavaScript</div>
        <div class="repo-stat"><i class="ti ti-star" aria-hidden="true"></i>5</div>
        <div class="repo-stat"><i class="ti ti-git-fork" aria-hidden="true"></i>1</div>
      </div>
    </div>
    <div class="repo-card">
      <div class="repo-name"><i class="ti ti-brand-github" aria-hidden="true"></i>Smart-Livestock-RFID</div>
      <div class="repo-desc">Arduino + RFID IoT attendance tracker for livestock, with automated sensor data logging.</div>
      <div class="repo-meta">
        <div class="repo-lang"><span class="lang-dot" style="background:#89e051"></span>C++</div>
        <div class="repo-stat"><i class="ti ti-star" aria-hidden="true"></i>4</div>
        <div class="repo-stat"><i class="ti ti-git-fork" aria-hidden="true"></i>1</div>
      </div>
    </div>
  </div>
</div>

<!-- Row 4: Activity feed -->
<div class="card">
  <div class="card-title"><i class="ti ti-timeline" aria-hidden="true"></i>Recent activity</div>
  <div id="activity-feed"></div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<script>
const MONTHS = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];

function buildContrib() {
  const weeks = 26;
  const days = ['M','','W','','F','',''];
  const monthLabels = [];
  const seed = (i) => {
    const s = Math.sin(i * 9301 + 49297) * 233280;
    return s - Math.floor(s);
  };
  const getLevel = (w, d, i) => {
    const r = seed(i);
    const weekActivity = 0.3 + 0.7 * Math.pow(Math.sin(w / 4), 2);
    if (r < 0.28) return 0;
    if (r < 0.48) return 1;
    if (r < 0.68) return 2;
    if (r < 0.85) return 3;
    return 4;
  };
  let html = '<div class="month-labels">';
  for (let w = 0; w < weeks; w++) {
    if (w % 4 === 0) {
      const mIdx = Math.floor(w / 4) % 12;
      html += `<div class="month-label" style="width:${4*14}px">${MONTHS[mIdx]}</div>`;
    }
  }
  html += '</div><div class="contrib-grid">';
  let total = 0;
  for (let d = 0; d < 7; d++) {
    html += `<div class="contrib-row"><div class="contrib-label">${days[d]}</div><div class="contrib-cells">`;
    for (let w = 0; w < weeks; w++) {
      const lvl = getLevel(w, d, w * 7 + d);
      if (lvl > 0) total += lvl * 2;
      const titles = ['No contributions','1-3 contributions','4-6 contributions','7-9 contributions','10+ contributions'];
      html += `<div class="cell c${lvl}" title="${titles[lvl]}"></div>`;
    }
    html += '</div></div>';
  }
  html += '</div>';
  document.getElementById('contrib-area').innerHTML = html;
}
buildContrib();

const LANGS = [
  { name: 'JavaScript', pct: 44, color: '#f1e05a' },
  { name: 'Python',     pct: 27, color: '#3572A5' },
  { name: 'C / C++',   pct: 14, color: '#f34b7d' },
  { name: 'CSS / HTML', pct: 9,  color: '#e34c26' },
  { name: 'Others',    pct: 6,  color: '#00f5d4' },
];
const langHtml = LANGS.map(l => `
  <div class="lang-item">
    <div class="lang-header">
      <div class="lang-name"><div class="lang-dot" style="background:${l.color}"></div>${l.name}</div>
      <div class="lang-pct">${l.pct}%</div>
    </div>
    <div class="lang-track"><div class="lang-fill" style="width:0%;background:${l.color}" data-w="${l.pct}"></div></div>
  </div>`).join('');
document.getElementById('lang-bars').innerHTML = langHtml;
setTimeout(() => {
  document.querySelectorAll('.lang-fill').forEach(el => { el.style.width = el.dataset.w + '%'; });
}, 100);

const SKILLS = [
  { name: 'React.js',   val: 88, color: '#38bdf8' },
  { name: 'Node.js',    val: 82, color: '#00f5d4' },
  { name: 'MongoDB',    val: 75, color: '#22c55e' },
  { name: 'Python',     val: 78, color: '#3572A5' },
  { name: 'Deep Learn', val: 65, color: '#a78bfa' },
  { name: 'Arduino',    val: 60, color: '#f472b6' },
  { name: 'SQL',        val: 70, color: '#fb923c' },
  { name: 'Git',        val: 85, color: '#f1e05a' },
];
document.getElementById('skill-bars').innerHTML = SKILLS.map(s => `
  <div class="sk-row">
    <div class="sk-name">${s.name}</div>
    <div class="sk-track"><div class="sk-fill" style="width:0%;background:${s.color}" data-w="${s.val}"></div></div>
    <div class="sk-val">${s.val}%</div>
  </div>`).join('');
setTimeout(() => {
  document.querySelectorAll('.sk-fill').forEach(el => { el.style.width = el.dataset.w + '%'; el.style.transition = 'width 1.2s cubic-bezier(0.16,1,0.3,1)'; });
}, 200);

const ACTIVITY = [
  { icon: 'ti-git-commit', bg: 'rgba(0,245,212,0.1)', color: '#00f5d4', text: 'Pushed <strong>3 commits</strong> to <strong>AI-Surveillance-UAD</strong> — model pruning optimizations', time: '2 days ago' },
  { icon: 'ti-git-pull-request', bg: 'rgba(124,58,237,0.12)', color: '#a78bfa', text: 'Opened PR <strong>#14</strong> in <strong>Coorg-Pantry</strong> — cart persistence with localStorage', time: '5 days ago' },
  { icon: 'ti-star', bg: 'rgba(251,146,60,0.12)', color: '#fb923c', text: 'Starred <strong>vercel/next.js</strong> and <strong>vitejs/vite</strong>', time: '1 week ago' },
  { icon: 'ti-git-commit', bg: 'rgba(0,245,212,0.1)', color: '#00f5d4', text: 'Pushed <strong>6 commits</strong> to <strong>Weather-Monitor</strong> — real-time chart integration', time: '1 week ago' },
  { icon: 'ti-brand-github', bg: 'rgba(240,244,255,0.05)', color: 'rgba(240,244,255,0.4)', text: 'Created repository <strong>Smart-Livestock-RFID</strong>', time: '3 weeks ago' },
];
document.getElementById('activity-feed').innerHTML = ACTIVITY.map(a => `
  <div class="activity-item">
    <div class="act-icon" style="background:${a.bg};color:${a.color}"><i class="ti ${a.icon}" aria-hidden="true"></i></div>
    <div class="act-text">
      <div class="act-main">${a.text}</div>
      <div class="act-time">${a.time}</div>
    </div>
  </div>`).join('');

const isDark = true;
const gridColor = 'rgba(255,255,255,0.05)';
const tickColor = 'rgba(240,244,255,0.35)';

new Chart(document.getElementById('langChart'), {
  type: 'bar',
  data: {
    labels: ['JS','Python','C/C++','CSS','Others'],
    datasets: [{
      data: [140,85,40,28,19],
      backgroundColor: ['rgba(241,224,90,0.7)','rgba(53,114,165,0.7)','rgba(243,75,125,0.7)','rgba(227,76,38,0.7)','rgba(0,245,212,0.7)'],
      borderColor: ['#f1e05a','#3572A5','#f34b7d','#e34c26','#00f5d4'],
      borderWidth: 1,
      borderRadius: 5,
      borderSkipped: false,
    }]
  },
  options: {
    responsive: true, maintainAspectRatio: false,
    plugins: { legend: { display: false }, tooltip: { callbacks: { label: ctx => ` ${ctx.raw} commits` } } },
    scales: {
      x: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } } },
      y: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } }, border: { dash: [4,4] } }
    }
  }
});

new Chart(document.getElementById('actChart'), {
  type: 'line',
  data: {
    labels: ['Nov','Dec','Jan','Feb','Mar','Apr'],
    datasets: [{
      data: [12,8,22,38,54,47],
      borderColor: '#00f5d4',
      backgroundColor: (ctx) => {
        const g = ctx.chart.ctx.createLinearGradient(0,0,0,120);
        g.addColorStop(0,'rgba(0,245,212,0.25)');
        g.addColorStop(1,'rgba(0,245,212,0)');
        return g;
      },
      borderWidth: 2,
      pointBackgroundColor: '#00f5d4',
      pointRadius: 3,
      pointHoverRadius: 5,
      fill: true,
      tension: 0.45,
    }]
  },
  options: {
    responsive: true, maintainAspectRatio: false,
    plugins: { legend: { display: false }, tooltip: { callbacks: { label: ctx => ` ${ctx.raw} commits` } } },
    scales: {
      x: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } } },
      y: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } }, border: { dash: [4,4] } }
    }
  }
});
</script>
