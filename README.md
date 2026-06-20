 <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Tapas Kumar Behera — Data Analyst</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@400;600;700&family=Inter:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0e1116;
    --panel:#151a22;
    --panel-2:#11151c;
    --line: rgba(255,255,255,0.08);
    --line-soft: rgba(255,255,255,0.05);
    --ink:#e7e9ed;
    --ink-dim:#8b93a3;
    --ink-faint:#5b6478;
    --accent:#c9a14a;       /* muted brass/gold */
    --accent-soft: rgba(201,161,74,0.12);
    --teal:#3e7c8c;
    --teal-soft: rgba(62,124,140,0.14);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  body{
    background:var(--bg); color:var(--ink);
    font-family:'Inter', sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  .mono{ font-family:'IBM Plex Mono', monospace; }
  .serif{ font-family:'Fraunces', serif; }

  .shell{ max-width:1160px; margin:0 auto; padding:0 32px; }

  /* ===== TOP BAR ===== */
  .topbar{
    border-bottom:1px solid var(--line);
    background: linear-gradient(180deg, rgba(255,255,255,0.015), transparent);
  }
  .topbar-inner{
    display:flex; justify-content:space-between; align-items:center;
    padding:20px 0; max-width:1160px; margin:0 auto; padding-left:32px; padding-right:32px;
  }
  .brand{ display:flex; align-items:center; gap:12px; }
  .brand-mark{
    width:36px; height:36px; border-radius:8px;
    background: linear-gradient(145deg, var(--accent), #8a6c2e);
    display:flex; align-items:center; justify-content:center;
    font-weight:800; font-size:13px; color:#0e1116; letter-spacing:-0.5px;
    box-shadow: 0 6px 14px -4px rgba(201,161,74,0.5);
  }
  .brand-name{ font-size:14.5px; font-weight:700; letter-spacing:0.2px; }
  .brand-role{ font-size:11.5px; color:var(--ink-faint); margin-top:1px; }
  .topnav{ display:flex; gap:28px; font-size:13px; color:var(--ink-dim); }
  .topnav a{ color:inherit; text-decoration:none; transition:color .2s; }
  .topnav a:hover{ color:var(--ink); }
  .status-pill{
    display:flex; align-items:center; gap:7px; font-size:12px; color:var(--ink-dim);
    border:1px solid var(--line); padding:6px 12px; border-radius:20px;
  }
  .status-dot{ width:6px; height:6px; border-radius:50%; background:#5fb87a; box-shadow:0 0 6px #5fb87a; }

  /* ===== HERO ===== */
  .hero{ padding:64px 0 56px; border-bottom:1px solid var(--line); }
  .hero-grid{ display:grid; grid-template-columns:1.3fr 1fr; gap:48px; align-items:end; }
  .hero-eyebrow{
    font-size:11.5px; letter-spacing:3px; text-transform:uppercase; color:var(--accent);
    font-weight:600; margin-bottom:18px; display:flex; align-items:center; gap:10px;
  }
  .hero-eyebrow::before{ content:''; width:24px; height:1px; background:var(--accent); }
  .hero h1{
    font-family:'Fraunces', serif; font-size:46px; font-weight:600; line-height:1.12;
    letter-spacing:-0.5px; color:#fff;
  }
  .hero h1 em{ font-style:italic; color:var(--accent); }
  .hero p.lede{ margin-top:18px; font-size:15.5px; color:var(--ink-dim); line-height:1.7; max-width:480px; }
  .hero-meta{ display:flex; gap:26px; margin-top:28px; }
  .hero-meta div{ font-size:12.5px; color:var(--ink-faint); }
  .hero-meta strong{ display:block; color:var(--ink); font-size:14px; font-weight:600; margin-bottom:2px; }
  .hero-actions{ display:flex; gap:10px; margin-top:30px; }
  .btn{
    font-size:13px; font-weight:600; padding:11px 20px; border-radius:9px; text-decoration:none;
    display:inline-flex; align-items:center; gap:8px; transition: all .22s ease;
  }
  .btn-fill{ background:var(--ink); color:#11151c; }
  .btn-fill:hover{ background:var(--accent); transform:translateY(-2px); box-shadow:0 10px 20px -8px rgba(201,161,74,0.5); }
  .btn-line{ border:1px solid var(--line); color:var(--ink); }
  .btn-line:hover{ border-color:var(--ink-dim); transform:translateY(-2px); }

  /* hero side panel - looks like a real BI card */
  .hero-card{
    background: linear-gradient(160deg, var(--panel), var(--panel-2));
    border:1px solid var(--line); border-radius:16px; padding:26px;
    box-shadow: 0 24px 50px -28px rgba(0,0,0,0.85), inset 0 1px 0 rgba(255,255,255,0.04);
    transform: perspective(1000px) rotateY(-4deg) rotateX(2deg);
  }
  .hero-card-head{ display:flex; justify-content:space-between; align-items:center; margin-bottom:18px; }
  .hero-card-head span{ font-size:11px; color:var(--ink-faint); letter-spacing:1px; text-transform:uppercase; }
  .kpi-row{ display:grid; grid-template-columns:1fr 1fr; gap:16px; margin-bottom:18px; }
  .kpi{ border-left:2px solid var(--accent); padding-left:12px; }
  .kpi .v{ font-size:24px; font-weight:700; color:#fff; font-family:'IBM Plex Mono', monospace; }
  .kpi .l{ font-size:11px; color:var(--ink-faint); margin-top:3px; }
  .bars{ display:flex; align-items:flex-end; gap:6px; height:54px; }
  .bars i{ flex:1; background: linear-gradient(180deg, var(--teal), var(--teal-soft)); border-radius:3px 3px 0 0; }

  /* ===== SECTION HEADERS ===== */
  .section{ padding:56px 0; border-bottom:1px solid var(--line); }
  .section-head{ display:flex; justify-content:space-between; align-items:baseline; margin-bottom:30px; }
  .section-head .idx{ font-family:'IBM Plex Mono', monospace; font-size:11px; color:var(--accent); letter-spacing:2px; }
  .section-head h2{ font-family:'Fraunces', serif; font-size:24px; font-weight:600; color:#fff; margin-top:6px; }
  .section-head p{ font-size:13px; color:var(--ink-faint); max-width:340px; text-align:right; }

  /* ===== STACK GRID ===== */
  .stack-grid{ display:grid; grid-template-columns:repeat(4,1fr); gap:1px; background:var(--line); border:1px solid var(--line); border-radius:14px; overflow:hidden; }
  .stack-cell{ background:var(--panel); padding:22px 18px; transition: background .25s ease; }
  .stack-cell:hover{ background:var(--panel-2); }
  .stack-cell .label{ font-size:10.5px; color:var(--ink-faint); letter-spacing:1.5px; text-transform:uppercase; margin-bottom:10px;}
  .stack-cell .items{ display:flex; flex-wrap:wrap; gap:6px; }
  .stack-cell .items span{ font-size:12px; color:var(--ink); background:rgba(255,255,255,0.04); padding:4px 10px; border-radius:6px; border:1px solid var(--line-soft); }

  /* ===== PROJECTS ===== */
  .proj-list{ display:flex; flex-direction:column; }
  .proj-row{
    display:grid; grid-template-columns:60px 1fr 1.4fr 140px; gap:24px; align-items:center;
    padding:22px 20px; border-top:1px solid var(--line);
    transition: background .25s ease, transform .25s ease;
    border-radius:10px;
  }
  .proj-row:last-child{ border-bottom:1px solid var(--line); }
  .proj-row:hover{ background:var(--panel); transform: translateX(4px); }
  .proj-row .pid{ font-family:'IBM Plex Mono', monospace; color:var(--ink-faint); font-size:13px; }
  .proj-row .ptitle{ }
  .proj-row .ptitle h3{ font-size:15.5px; font-weight:600; color:#fff; margin-bottom:6px; }
  .proj-row .ptitle .stack{ display:flex; gap:6px; flex-wrap:wrap; }
  .proj-row .ptitle .stack span{ font-size:10.5px; color:var(--teal); background:var(--teal-soft); padding:3px 8px; border-radius:6px; }
  .proj-row .pdesc{ font-size:12.8px; color:var(--ink-dim); line-height:1.6; }
  .proj-row .plink{ text-align:right; }
  .proj-row .plink a{ font-size:12px; font-weight:600; color:var(--ink); border:1px solid var(--line); padding:8px 14px; border-radius:8px; text-decoration:none; transition: all .2s ease; white-space:nowrap; }
  .proj-row .plink a:hover{ border-color:var(--accent); color:var(--accent); }

  /* ===== CERTS ===== */
  .cert-list{ display:flex; flex-direction:column; gap:1px; background:var(--line); border:1px solid var(--line); border-radius:12px; overflow:hidden; }
  .cert-item{ background:var(--panel); display:grid; grid-template-columns:1fr 220px 90px; gap:20px; padding:18px 22px; align-items:center; }
  .cert-item .name{ font-size:13.5px; font-weight:600; color:#fff; }
  .cert-item .issuer{ font-size:12.5px; color:var(--ink-dim); }
  .cert-item .year{ font-size:12px; color:var(--accent); font-family:'IBM Plex Mono', monospace; text-align:right; }

  /* ===== FOCUS ===== */
  .focus-grid{ display:grid; grid-template-columns:1fr 1fr; gap:1px; background:var(--line); border:1px solid var(--line); border-radius:14px; overflow:hidden; }
  .focus-cell{ background:var(--panel); padding:26px; }
  .focus-cell h4{ font-size:11px; letter-spacing:1.5px; text-transform:uppercase; color:var(--ink-faint); margin-bottom:14px; }
  .focus-cell ul{ list-style:none; }
  .focus-cell li{ font-size:13.5px; color:var(--ink); padding:8px 0; border-top:1px solid var(--line-soft); }
  .focus-cell li:first-child{ border-top:none; }

  /* ===== CTA FOOTER ===== */
  .cta{ padding:70px 0; text-align:center; }
  .cta h2{ font-family:'Fraunces', serif; font-size:30px; color:#fff; margin-bottom:12px; }
  .cta p{ color:var(--ink-dim); font-size:14px; margin-bottom:28px; }
  .cta-actions{ display:flex; justify-content:center; gap:12px; }
  footer{ text-align:center; padding:26px 0; font-size:11.5px; color:var(--ink-faint); border-top:1px solid var(--line); }

  @media(max-width:880px){
    .hero-grid{ grid-template-columns:1fr; }
    .hero-card{ transform:none; }
    .stack-grid{ grid-template-columns:repeat(2,1fr); }
    .proj-row{ grid-template-columns:1fr; text-align:left; }
    .proj-row .plink{ text-align:left; }
    .section-head{ flex-direction:column; align-items:flex-start; gap:8px; }
    .section-head p{ text-align:left; }
    .cert-item{ grid-template-columns:1fr; gap:4px; }
    .focus-grid{ grid-template-columns:1fr; }
  }
</style>
</head>
<body>

  <div class="topbar">
    <div class="topbar-inner">
      <div class="brand">
        <div class="brand-mark">TB</div>
        <div>
          <div class="brand-name">Tapas Kumar Behera</div>
          <div class="brand-role">Data Analyst</div>
        </div>
      </div>
      <div class="topnav">
        <a href="#stack">Stack</a>
        <a href="#projects">Projects</a>
        <a href="#certs">Certifications</a>
        <a href="#contact">Contact</a>
      </div>
      <div class="status-pill"><span class="status-dot"></span>Open to opportunities</div>
    </div>
  </div>

  <div class="shell">

    <!-- HERO -->
    <div class="hero">
      <div class="hero-grid">
        <div>
          <div class="hero-eyebrow">Portfolio Overview</div>
          <h1>Data, structured into<br><em>clarity</em> and decisions.</h1>
          <p class="lede">I build dashboards and analyses with Python, SQL, Power BI and Excel — translating raw datasets into insight that businesses can act on, with AI tools woven into the workflow for speed and precision.</p>
          <div class="hero-meta">
            <div><strong>Delhi, India</strong>Based in</div>
            <div><strong>8</strong>Projects shipped</div>
            <div><strong>3</strong>Certifications</div>
          </div>
          <div class="hero-actions">
            <a class="btn btn-fill" href="https://www.linkedin.com/in/tapas-kumar-behera-670813239" target="_blank">Connect on LinkedIn</a>
            <a class="btn btn-line" href="https://github.com/tapas-tech29" target="_blank">View GitHub</a>
            <a class="btn btn-line" href="mailto:tapas29122003@gmail.com">Email</a>
          </div>
        </div>

        <div class="hero-card">
          <div class="hero-card-head">
            <span>Skill Index</span>
            <span class="mono">FY26</span>
          </div>
          <div class="kpi-row">
            <div class="kpi"><div class="v">11+</div><div class="l">Tools &amp; Languages</div></div>
            <div class="kpi"><div class="v">8</div><div class="l">Dashboards Built</div></div>
          </div>
          <div class="bars">
            <i style="height:40%"></i><i style="height:65%"></i><i style="height:50%"></i>
            <i style="height:80%"></i><i style="height:60%"></i><i style="height:95%"></i>
            <i style="height:70%"></i><i style="height:55%"></i><i style="height:85%"></i>
            <i style="height:45%"></i>
          </div>
        </div>
      </div>
    </div>

    <!-- STACK -->
    <div class="section" id="stack">
      <div class="section-head">
        <div><div class="idx">01 — TOOLKIT</div><h2>Technical Stack</h2></div>
        <p>Languages, libraries and platforms used across analysis and reporting work.</p>
      </div>
      <div class="stack-grid">
        <div class="stack-cell">
          <div class="label">Languages</div>
          <div class="items"><span>Python</span><span>SQL</span></div>
        </div>
        <div class="stack-cell">
          <div class="label">Analysis</div>
          <div class="items"><span>Pandas</span><span>NumPy</span><span>Excel</span></div>
        </div>
        <div class="stack-cell">
          <div class="label">Visualization</div>
          <div class="items"><span>Power BI</span><span>Matplotlib</span><span>Seaborn</span></div>
        </div>
        <div class="stack-cell">
          <div class="label">AI Tools</div>
          <div class="items"><span>ChatGPT</span><span>Claude</span><span>Copilot</span></div>
        </div>
      </div>
    </div>

    <!-- PROJECTS -->
    <div class="section" id="projects">
      <div class="section-head">
        <div><div class="idx">02 — WORK</div><h2>Featured Projects</h2></div>
        <p>End-to-end dashboards and analyses, from raw data to business recommendations.</p>
      </div>
      <div class="proj-list">

        <div class="proj-row">
          <div class="pid">01</div>
          <div class="ptitle"><h3>US EV Adoption &amp; Renewable Energy</h3><div class="stack"><span>Power BI</span><span>DAX</span></div></div>
          <div class="pdesc">Executive KPI dashboard mapping EV adoption across US states against renewable energy output, with correlation analysis and strategic recommendations.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/-US-EV-Adoption-Renewable-Energy-Dashboard" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">02</div>
          <div class="ptitle"><h3>Spotify Music Analytics</h3><div class="stack"><span>Power BI</span><span>CSV</span></div></div>
          <div class="pdesc">Artist and genre performance dashboard covering streaming trends, explicit-content split, and release pattern intelligence for label strategy.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/Spotify-Music-Analytics-Dashboard" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">03</div>
          <div class="ptitle"><h3>Netflix Content Analysis</h3><div class="stack"><span>Power BI</span><span>DAX</span></div></div>
          <div class="pdesc">Comparative breakdown of movies vs. TV shows, production-by-country heatmap, and year-over-year content growth for catalog strategy.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/Netflix-Content-Analysis-PowerBI" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">04</div>
          <div class="ptitle"><h3>Zomato Restaurant Analytics</h3><div class="stack"><span>Power BI</span><span>CSV</span></div></div>
          <div class="pdesc">Multi-city restaurant benchmarking with a cost-vs-rating matrix and location-based market opportunity mapping.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/Zomato-Restaurant-Analytics-Dashboard-Power-Bi" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">05</div>
          <div class="ptitle"><h3>Superstore Sales BI</h3><div class="stack"><span>Power BI</span><span>Excel</span></div></div>
          <div class="pdesc">Sales, profit and order KPI dashboard with regional drilldowns, dynamic slicers, and custom DAX measures.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/Zomato-Restaurant-Analytics-Dashboard-Power-Bi" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">06</div>
          <div class="ptitle"><h3>Courier Billing Audit</h3><div class="stack"><span>Power BI</span><span>Excel</span></div></div>
          <div class="pdesc">Logistics cost audit dashboard auto-flagging over/undercharged invoices and comparing delivery zone performance.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/Courier-Billing-Audit-Logistics-Cost-Analysis-Dashboard" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">07</div>
          <div class="ptitle"><h3>Loan Approval Analysis</h3><div class="stack"><span>Python</span><span>Power BI</span></div></div>
          <div class="pdesc">Full EDA pipeline — missing values, outliers, encoding — plus statistical analysis of income, CIBIL score and approval risk.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/loan-approval-analysis" target="_blank">View repo →</a></div>
        </div>

        <div class="proj-row">
          <div class="pid">08</div>
          <div class="ptitle"><h3>Pizza Hut Sales Analysis</h3><div class="stack"><span>SQL</span><span>MySQL</span></div></div>
          <div class="pdesc">Advanced SQL across four relational tables to surface top products, peak order hours, and rolling revenue trends.</div>
          <div class="plink"><a href="https://github.com/tapas-tech29/pizza-hut-sales-analysis" target="_blank">View repo →</a></div>
        </div>

      </div>
    </div>

    <!-- CERTS -->
    <div class="section" id="certs">
      <div class="section-head">
        <div><div class="idx">03 — CREDENTIALS</div><h2>Certifications</h2></div>
        <p>Formal training completed alongside applied project work.</p>
      </div>
      <div class="cert-list">
        <div class="cert-item"><div class="name">Data Analytics Certification</div><div class="issuer">Skill Circle</div><div class="year">2026</div></div>
        <div class="cert-item"><div class="name">Data Science Essentials with Python <span style="color:var(--ink-faint);font-weight:400;">(Verified)</span></div><div class="issuer">Cisco Networking Academy</div><div class="year">Feb 2026</div></div>
        <div class="cert-item"><div class="name">Yuva AI for All</div><div class="issuer">NASSCOM FutureSkills / INDIAai (MeitY)</div><div class="year">Feb 2026</div></div>
      </div>
    </div>

    <!-- FOCUS -->
    <div class="section" style="border-bottom:none;">
      <div class="section-head">
        <div><div class="idx">04 — IN PROGRESS</div><h2>Current Focus</h2></div>
        <p>What I'm learning and building right now.</p>
      </div>
      <div class="focus-grid">
        <div class="focus-cell">
          <h4>Learning</h4>
          <ul><li>Machine Learning</li><li>Tableau</li><li>Advanced Statistics</li></ul>
        </div>
        <div class="focus-cell">
          <h4>Building</h4>
          <ul><li>HR Analytics Dashboard</li><li>E-commerce Sales Analysis</li></ul>
        </div>
      </div>
    </div>

    <!-- CTA -->
    <div class="cta" id="contact">
      <h2>Let's build something with data.</h2>
      <p>Open to Data Analyst, Business Analyst and Reporting Analyst roles.</p>
      <div class="cta-actions">
        <a class="btn btn-fill" href="https://www.linkedin.com/in/tapas-kumar-behera-670813239" target="_blank">Connect on LinkedIn</a>
        <a class="btn btn-line" href="mailto:tapas29122003@gmail.com">Send an Email</a>
      </div>
    </div>

  </div>

  <footer>© 2026 Tapas Kumar Behera — Built with data, refined with care.</footer>

</body>
</html>
