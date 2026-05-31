<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Aditya Kumar Singh — Site Reliability Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=DM+Mono:wght@400;500&family=Cabinet+Grotesk:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<style>
:root{
  --bg:#05080e;--bg2:#090e18;--bg3:#0e1420;--bg4:#131b27;
  --border:rgba(255,255,255,0.06);--border2:rgba(255,255,255,0.12);--border3:rgba(255,255,255,0.2);
  --text:#dde4ef;--muted:#5d7090;--muted2:#8aa0bc;
  --cyan:#00d4ff;--cyan2:rgba(0,212,255,0.15);--cyan3:rgba(0,212,255,0.06);
  --green:#00e5a0;--amber:#f5a623;--red:#ff4f6b;--purple:#a78bfa;
  --mono:'DM Mono',monospace;--display:'Clash Display',sans-serif;--body:'Cabinet Grotesk',sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--body);font-size:15px;line-height:1.7;overflow-x:hidden}

/* ── GLOBAL BG ── */
.bg-fx{position:fixed;inset:0;pointer-events:none;z-index:0}
.bg-fx .grad1{position:absolute;width:800px;height:800px;border-radius:50%;background:radial-gradient(circle,rgba(0,212,255,0.05) 0%,transparent 70%);top:-200px;left:-200px}
.bg-fx .grad2{position:absolute;width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(167,139,250,0.04) 0%,transparent 70%);bottom:0;right:-100px}
.bg-fx .grid{position:absolute;inset:0;background-image:linear-gradient(var(--border) 1px,transparent 1px),linear-gradient(90deg,var(--border) 1px,transparent 1px);background-size:64px 64px}
.bg-fx .noise{position:absolute;inset:0;opacity:.025;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E")}

/* ── NAV ── */
nav{position:fixed;top:0;left:0;right:0;z-index:200;height:64px;display:flex;align-items:center;justify-content:space-between;padding:0 48px;background:rgba(5,8,14,0.8);backdrop-filter:blur(24px);border-bottom:1px solid var(--border)}
.nav-brand{display:flex;align-items:center;gap:12px;text-decoration:none}
.nav-badge{width:36px;height:36px;border-radius:8px;background:linear-gradient(135deg,var(--cyan),#0066ff);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:13px;font-weight:500;color:#fff;letter-spacing:-.02em;position:relative;overflow:hidden}
.nav-badge::after{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,0.2),transparent)}
.nav-wordmark{font-family:var(--mono);font-size:13px;color:var(--text);letter-spacing:.04em}
.nav-wordmark span{color:var(--cyan)}
.nav-links{display:flex;align-items:center;gap:36px;list-style:none}
.nav-links a{font-family:var(--mono);font-size:11px;color:var(--muted);text-decoration:none;letter-spacing:.12em;text-transform:uppercase;transition:color .2s}
.nav-links a:hover{color:var(--cyan)}
.nav-status{display:flex;align-items:center;gap:8px;font-family:var(--mono);font-size:11px;color:var(--green);padding:6px 14px;border:1px solid rgba(0,229,160,0.25);background:rgba(0,229,160,0.05);border-radius:2px}
.nav-status::before{content:'';width:6px;height:6px;border-radius:50%;background:var(--green);animation:blink 2s ease infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.3}}

/* ── HERO ── */
.hero{position:relative;z-index:1;min-height:100vh;display:grid;grid-template-columns:1fr 420px;gap:60px;align-items:center;padding:0 48px;padding-top:64px;max-width:1280px;margin:0 auto}
.hero-left{}
.hero-tag{display:inline-flex;align-items:center;gap:8px;font-family:var(--mono);font-size:11px;color:var(--cyan);letter-spacing:.15em;text-transform:uppercase;margin-bottom:32px;padding:6px 14px;border:1px solid rgba(0,212,255,0.2);background:rgba(0,212,255,0.05)}
.hero-tag svg{width:12px;height:12px}
.hero h1{font-family:var(--display);font-size:clamp(56px,6vw,90px);line-height:1;font-weight:700;margin-bottom:6px;letter-spacing:-.02em}
.hero h1 .name-first{color:var(--text)}
.hero h1 .name-last{color:var(--text);display:block}
.hero h1 .name-accent{background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-role-line{display:flex;align-items:center;gap:16px;margin:24px 0 32px}
.hero-role-text{font-family:var(--mono);font-size:13px;color:var(--muted2);letter-spacing:.06em}
.hero-role-divider{flex:1;height:1px;background:linear-gradient(90deg,var(--border2),transparent)}
.hero-desc{font-size:16px;color:var(--muted2);line-height:1.85;max-width:560px;margin-bottom:48px;font-weight:300}
.hero-desc strong{color:var(--text);font-weight:500}
.hero-actions{display:flex;gap:14px;flex-wrap:wrap;margin-bottom:56px}
.btn-primary{font-family:var(--mono);font-size:12px;padding:13px 28px;background:var(--cyan);color:var(--bg);font-weight:500;letter-spacing:.06em;text-decoration:none;border:none;cursor:pointer;position:relative;overflow:hidden;transition:all .25s;display:inline-flex;align-items:center;gap:8px}
.btn-primary::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,0.15),transparent);opacity:0;transition:opacity .25s}
.btn-primary:hover::before{opacity:1}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 8px 32px rgba(0,212,255,0.3)}
.btn-secondary{font-family:var(--mono);font-size:12px;padding:13px 28px;background:transparent;color:var(--muted2);border:1px solid var(--border2);letter-spacing:.06em;text-decoration:none;transition:all .25s;display:inline-flex;align-items:center;gap:8px}
.btn-secondary:hover{border-color:var(--border3);color:var(--text);background:var(--bg3)}
.hero-chips{display:flex;gap:10px;flex-wrap:wrap}
.chip{font-family:var(--mono);font-size:10px;padding:5px 12px;border:1px solid var(--border);color:var(--muted);background:var(--bg2);letter-spacing:.06em;border-radius:2px}

/* ── HERO RIGHT — TERMINAL CARD ── */
.hero-right{position:relative}
.terminal-card{background:var(--bg2);border:1px solid var(--border2);border-radius:12px;overflow:hidden;box-shadow:0 32px 80px rgba(0,0,0,0.5),0 0 0 1px rgba(0,212,255,0.05)}
.terminal-bar{padding:12px 16px;background:var(--bg3);border-bottom:1px solid var(--border);display:flex;align-items:center;gap:8px}
.t-dot{width:10px;height:10px;border-radius:50%}
.t-dot.r{background:#ff5f57}.t-dot.y{background:#febc2e}.t-dot.g{background:#28c840}
.t-title{flex:1;text-align:center;font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.08em}
.terminal-body{padding:20px;font-family:var(--mono);font-size:12px;line-height:1.9}
.t-line{display:flex;gap:8px}
.t-prompt{color:var(--green);flex-shrink:0}
.t-cmd{color:#a8d8f0}
.t-out{color:var(--muted2);padding-left:0}
.t-out.good{color:var(--green)}
.t-out.warn{color:var(--amber)}
.t-out.err{color:var(--red)}
.t-comment{color:#3d5a7a}
.t-key{color:var(--cyan)}
.t-val{color:var(--purple)}
.t-blank{height:8px}
.t-cursor{display:inline-block;width:8px;height:14px;background:var(--cyan);animation:cur .9s step-end infinite;vertical-align:middle;margin-left:2px}
@keyframes cur{0%,100%{opacity:1}50%{opacity:0}}

/* ── LOGO TICKER ── */
.ticker-section{position:relative;z-index:1;padding:48px 0;border-top:1px solid var(--border);border-bottom:1px solid var(--border);overflow:hidden;background:var(--bg2)}
.ticker-label{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.2em;text-transform:uppercase;text-align:center;margin-bottom:28px}
.ticker-track{display:flex;gap:0;white-space:nowrap}
.ticker-inner{display:flex;gap:0;animation:tick 30s linear infinite;flex-shrink:0}
.ticker-inner:nth-child(2){animation-delay:-15s}
@keyframes tick{from{transform:translateX(0)}to{transform:translateX(-100%)}}
.tool-logo{display:inline-flex;flex-direction:column;align-items:center;gap:8px;padding:0 36px;opacity:.5;transition:opacity .2s;cursor:default}
.tool-logo:hover{opacity:1}
.tool-logo svg{width:32px;height:32px}
.tool-logo span{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.06em}

/* ── SECTION ── */
section{position:relative;z-index:1;padding:110px 48px;max-width:1280px;margin:0 auto}
.s-label{font-family:var(--mono);font-size:10px;color:var(--cyan);letter-spacing:.25em;text-transform:uppercase;margin-bottom:14px;display:flex;align-items:center;gap:12px}
.s-label::before{content:'';width:20px;height:1px;background:var(--cyan)}
.s-title{font-family:var(--display);font-size:clamp(36px,4vw,58px);line-height:1.05;margin-bottom:0;font-weight:700;letter-spacing:-.02em}
.s-title em{font-style:normal;background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.s-sub{font-size:15px;color:var(--muted2);margin-top:16px;max-width:480px;line-height:1.7;font-weight:300}
.divider{max-width:1280px;margin:0 auto;height:1px;background:linear-gradient(90deg,transparent 0%,var(--border2) 20%,var(--border2) 80%,transparent 100%)}

/* ── SKILLS ── */
.skills-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:52px;flex-wrap:wrap;gap:24px}
.skills-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border)}
.skill-card{background:var(--bg2);padding:32px;transition:background .25s;position:relative;overflow:hidden}
.skill-card::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--cyan),transparent);transform:scaleX(0);transform-origin:center;transition:transform .3s}
.skill-card:hover{background:var(--bg3)}
.skill-card:hover::before{transform:scaleX(1)}
.skill-card-head{display:flex;align-items:flex-start;gap:14px;margin-bottom:20px}
.skill-icon-wrap{width:40px;height:40px;border-radius:8px;border:1px solid var(--border2);display:flex;align-items:center;justify-content:center;flex-shrink:0;background:var(--bg3)}
.skill-icon-wrap svg{width:20px;height:20px}
.skill-cat{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.1em;text-transform:uppercase;margin-bottom:4px}
.skill-name{font-size:15px;font-weight:500;color:var(--text)}
.skill-tags{display:flex;flex-wrap:wrap;gap:6px}
.stag{font-family:var(--mono);font-size:10px;padding:3px 9px;border:1px solid var(--border);color:var(--muted2);letter-spacing:.03em;border-radius:2px;transition:all .2s}
.stag:hover{border-color:rgba(0,212,255,.4);color:var(--cyan)}
.stag.hot{border-color:rgba(0,212,255,.25);color:var(--cyan);background:rgba(0,212,255,.04)}

/* ── IMPACT ── */
.impact-wrap{position:relative;z-index:1;background:var(--bg2);border-top:1px solid var(--border);border-bottom:1px solid var(--border);overflow:hidden}
.impact-inner{max-width:1280px;margin:0 auto;padding:80px 48px;display:grid;grid-template-columns:repeat(5,1fr);gap:1px;background:var(--border)}
.impact-item{background:var(--bg2);padding:40px 24px;text-align:center;transition:background .2s;position:relative;overflow:hidden}
.impact-item:hover{background:var(--bg3)}
.impact-num{font-family:var(--display);font-size:52px;font-weight:700;letter-spacing:-.03em;display:block;margin-bottom:8px;background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.impact-label{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase;line-height:1.6}

/* ── SERVICES ── */
.services-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:56px}
.svc-card{border:1px solid var(--border);background:var(--bg2);padding:36px;position:relative;overflow:hidden;transition:border-color .3s,background .3s;cursor:default}
.svc-card-glow{position:absolute;top:-40px;right:-40px;width:120px;height:120px;border-radius:50%;opacity:0;transition:opacity .4s}
.svc-card:hover .svc-card-glow{opacity:1}
.svc-card:hover{border-color:var(--border2);background:var(--bg3)}
.svc-num{font-family:var(--mono);font-size:11px;color:var(--muted);margin-bottom:20px;letter-spacing:.08em}
.svc-icon{width:48px;height:48px;border-radius:10px;border:1px solid var(--border2);display:flex;align-items:center;justify-content:center;margin-bottom:20px}
.svc-icon svg{width:24px;height:24px}
.svc-name{font-family:var(--display);font-size:19px;font-weight:600;margin-bottom:12px;letter-spacing:-.01em;color:var(--text)}
.svc-desc{font-size:13px;color:var(--muted2);line-height:1.75;font-weight:300;margin-bottom:20px}
.svc-tools{display:flex;flex-wrap:wrap;gap:6px}

/* ── TOOL LOGOS GRID ── */
.tools-section{position:relative;z-index:1;padding:110px 48px;max-width:1280px;margin:0 auto}
.tools-mosaic{display:grid;grid-template-columns:repeat(8,1fr);gap:1px;background:var(--border);margin-top:52px}
.tool-tile{background:var(--bg2);aspect-ratio:1;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:10px;transition:background .2s,border-color .2s;cursor:default;border:1px solid transparent;margin:-1px}
.tool-tile:hover{background:var(--bg3);border-color:var(--border2);z-index:1}
.tool-tile svg{width:36px;height:36px;transition:transform .2s}
.tool-tile:hover svg{transform:scale(1.1)}
.tool-tile-name{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.06em;text-align:center}
.tool-tile-cat{font-family:var(--mono);font-size:9px;color:var(--muted);opacity:.5;letter-spacing:.04em}

/* ── PROJECTS ── */
.projects-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:48px;flex-wrap:wrap;gap:20px}
.projects-list{display:flex;flex-direction:column;gap:1px;background:var(--border)}
.proj-row{background:var(--bg2);padding:36px;display:grid;grid-template-columns:60px 1fr auto;gap:32px;align-items:start;transition:background .2s;position:relative;overflow:hidden}
.proj-row::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--cyan),var(--purple));transform:scaleY(0);transform-origin:top;transition:transform .3s}
.proj-row:hover{background:var(--bg3)}
.proj-row:hover::before{transform:scaleY(1)}
.proj-num{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.08em;padding-top:3px}
.proj-name{font-family:var(--display);font-size:18px;font-weight:600;margin-bottom:8px;letter-spacing:-.01em}
.proj-desc{font-size:13px;color:var(--muted2);line-height:1.75;font-weight:300;max-width:680px}
.proj-badge{font-family:var(--mono);font-size:10px;padding:4px 12px;border:1px solid;letter-spacing:.04em;align-self:start;white-space:nowrap;border-radius:2px}
.pb-obs{border-color:rgba(0,229,160,.4);color:var(--green);background:rgba(0,229,160,.04)}
.pb-iac{border-color:rgba(0,212,255,.4);color:var(--cyan);background:rgba(0,212,255,.04)}
.pb-sec{border-color:rgba(255,79,107,.4);color:var(--red);background:rgba(255,79,107,.04)}
.pb-cost{border-color:rgba(245,166,35,.4);color:var(--amber);background:rgba(245,166,35,.04)}
.pb-rel{border-color:rgba(167,139,250,.4);color:var(--purple);background:rgba(167,139,250,.04)}

/* ── CERTS ── */
.certs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:12px;margin-top:52px}
.cert-card{border:1px solid var(--border);padding:20px 24px;display:flex;align-items:center;gap:16px;transition:border-color .2s,background .2s;background:var(--bg2)}
.cert-card:hover{border-color:var(--border2);background:var(--bg3)}
.cert-icon-wrap{width:40px;height:40px;border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:20px;background:var(--bg3);border:1px solid var(--border)}
.cert-name{font-size:13px;font-weight:500;line-height:1.35;margin-bottom:4px;color:var(--text)}
.cert-org{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.06em;text-transform:uppercase}

/* ── CTA ── */
.cta-wrap{position:relative;z-index:1;padding:120px 48px;max-width:900px;margin:0 auto;text-align:center}
.cta-wrap h2{font-family:var(--display);font-size:clamp(42px,5vw,68px);line-height:1.05;margin-bottom:20px;font-weight:700;letter-spacing:-.02em}
.cta-wrap p{font-size:16px;color:var(--muted2);margin-bottom:52px;max-width:520px;margin-left:auto;margin-right:auto;font-weight:300}
.contact-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;max-width:600px;margin:0 auto}
.contact-card{display:flex;align-items:center;gap:14px;padding:18px 24px;border:1px solid var(--border);background:var(--bg2);text-decoration:none;transition:border-color .2s,background .2s}
.contact-card:hover{border-color:var(--border2);background:var(--bg3)}
.contact-card-icon{width:36px;height:36px;border-radius:6px;display:flex;align-items:center;justify-content:center;flex-shrink:0;background:var(--bg3);border:1px solid var(--border)}
.contact-card-icon svg{width:16px;height:16px;stroke:var(--cyan)}
.contact-card-label{font-family:var(--mono);font-size:10px;color:var(--muted);letter-spacing:.08em;text-transform:uppercase;margin-bottom:2px}
.contact-card-val{font-size:13px;color:var(--text);font-weight:400}

/* ── FOOTER ── */
footer{position:relative;z-index:1;border-top:1px solid var(--border);padding:28px 48px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px}
.footer-brand{display:flex;align-items:center;gap:10px}
.footer-badge{width:28px;height:28px;border-radius:6px;background:linear-gradient(135deg,var(--cyan),#0066ff);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:10px;color:#fff}
.footer-text{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.04em}
.footer-right{font-family:var(--mono);font-size:11px;color:var(--muted);display:flex;align-items:center;gap:6px}
.footer-right::before{content:'▸';color:var(--cyan)}

/* ── REVEAL ── */
.reveal{opacity:0;transform:translateY(24px);transition:opacity .65s ease,transform .65s ease}
.reveal.visible{opacity:1;transform:none}
.reveal-delay-1{transition-delay:.1s}
.reveal-delay-2{transition-delay:.2s}
.reveal-delay-3{transition-delay:.3s}

/* ── RESPONSIVE ── */
@media(max-width:1024px){
  .hero{grid-template-columns:1fr;padding:80px 24px 40px}
  .hero-right{display:none}
  .skills-grid{grid-template-columns:repeat(2,1fr)}
  .services-grid{grid-template-columns:1fr 1fr}
  .tools-mosaic{grid-template-columns:repeat(4,1fr)}
  .impact-inner{grid-template-columns:repeat(3,1fr)}
}
@media(max-width:640px){
  nav{padding:0 20px}
  .nav-links,.nav-status{display:none}
  section,.tools-section{padding:70px 20px}
  .skills-grid,.services-grid{grid-template-columns:1fr}
  .tools-mosaic{grid-template-columns:repeat(4,1fr)}
  .impact-inner{grid-template-columns:repeat(2,1fr)}
  .contact-grid{grid-template-columns:1fr}
  footer{padding:20px;flex-direction:column;text-align:center}
  .proj-row{grid-template-columns:40px 1fr;gap:16px}
  .proj-badge{display:none}
}
</style>
</head>
<body>

<div class="bg-fx">
  <div class="grad1"></div>
  <div class="grad2"></div>
  <div class="grid"></div>
  <div class="noise"></div>
</div>

<!-- ═══════════ NAV ═══════════ -->
<nav>
  <a href="#" class="nav-brand">
    <div class="nav-badge">AK</div>
    <span class="nav-wordmark">aditya<span>.</span>sre</span>
  </a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#tools">Tools</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <div class="nav-status">Open to opportunities</div>
</nav>

<!-- ═══════════ HERO ═══════════ -->
<div class="hero">
  <div class="hero-left">
    <div class="hero-tag">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="3"/><path d="M12 1v4M12 19v4M4.22 4.22l2.83 2.83M16.95 16.95l2.83 2.83M1 12h4M19 12h4M4.22 19.78l2.83-2.83M16.95 7.05l2.83-2.83"/></svg>
      Site Reliability Engineer — Noida, India
    </div>
    <h1>
      <span class="name-first">Aditya</span>
      <span class="name-last">Kumar <span class="name-accent">Singh</span></span>
    </h1>
    <div class="hero-role-line">
      <span class="hero-role-text">// AWS · Azure · GCP · Kubernetes · Observability</span>
      <div class="hero-role-divider"></div>
    </div>
    <p class="hero-desc">I design and operate <strong>production infrastructure</strong> that scales reliably under pressure — with the discipline to prevent incidents, the tooling to detect them instantly, and the runbooks to resolve them before users notice.</p>
    <div class="hero-actions">
      <a href="mailto:aksingh3134@gmail.com" class="btn-primary">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m22 2-7 20-4-9-9-4z"/><path d="M22 2 11 13"/></svg>
        Hire Me
      </a>
      <a href="https://linkedin.com/in/aditya-singh-cloud" target="_blank" class="btn-secondary">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-4 0v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn Profile
      </a>
    </div>
    <div class="hero-chips">
      <span class="chip">M.Tech · NIT Kurukshetra · 8.9 CGPA</span>
      <span class="chip">4+ Years SRE</span>
      <span class="chip">+91 74589 95596</span>
    </div>
  </div>

  <div class="hero-right">
    <div class="terminal-card">
      <div class="terminal-bar">
        <div class="t-dot r"></div><div class="t-dot y"></div><div class="t-dot g"></div>
        <div class="t-title">aditya@sre-terminal ~ kubectl</div>
      </div>
      <div class="terminal-body">
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-cmd">kubectl get nodes -o wide</span></div>
        <div class="t-line"><span class="t-out good">NAME&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;STATUS&nbsp;&nbsp;&nbsp;ROLES</span></div>
        <div class="t-line"><span class="t-out good">node-01&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ready&nbsp;&nbsp;&nbsp;&nbsp;control-plane</span></div>
        <div class="t-line"><span class="t-out good">node-02&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ready&nbsp;&nbsp;&nbsp;&nbsp;worker</span></div>
        <div class="t-line"><span class="t-out good">node-03&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ready&nbsp;&nbsp;&nbsp;&nbsp;worker</span></div>
        <div class="t-blank"></div>
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-cmd">kubectl get hpa --all-namespaces</span></div>
        <div class="t-line"><span class="t-out"><span class="t-key">NAMESPACE&nbsp;&nbsp;&nbsp;NAME&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MINPODS&nbsp;MAXPODS&nbsp;REPLICAS</span></span></div>
        <div class="t-line"><span class="t-out">production&nbsp;&nbsp;app-hpa&nbsp;&nbsp;&nbsp;4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;20&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="t-val">12</span></span></div>
        <div class="t-blank"></div>
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-cmd">terraform apply --auto-approve</span></div>
        <div class="t-line"><span class="t-out good">Apply complete! Resources: 14 added.</span></div>
        <div class="t-blank"></div>
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-cmd">redis-cli -h redis-cluster PING</span></div>
        <div class="t-line"><span class="t-out good">PONG</span></div>
        <div class="t-blank"></div>
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-comment"># p99 latency · error rate · CPU</span></div>
        <div class="t-line"><span class="t-out">SLO burn rate: <span class="t-val">0.12</span> <span class="t-comment">— nominal</span></span></div>
        <div class="t-line"><span class="t-out">Error rate:&nbsp;&nbsp;&nbsp;<span class="t-val">0.04%</span> <span class="t-comment">— within SLO</span></span></div>
        <div class="t-line"><span class="t-prompt">❯</span><span class="t-cursor"></span></div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════ TOOL TICKER ═══════════ -->
<div class="ticker-section">
  <div class="ticker-label">Tools & platforms I work with every day</div>
  <div class="ticker-track">
    <div class="ticker-inner">
      <!-- AWS -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32" fill="none"><path d="M9 20.5c-1.1.6-1.8 1.7-1.8 2.9 0 1.9 1.5 3.4 3.4 3.4.6 0 1.2-.2 1.7-.5l6.7-4 6.7 4c.5.3 1.1.5 1.7.5 1.9 0 3.4-1.5 3.4-3.4 0-1.2-.7-2.3-1.8-2.9V12c1.1-.6 1.8-1.7 1.8-2.9C31 7.2 29.5 5.7 27.6 5.7c-.6 0-1.2.2-1.7.5l-6.7 4-6.7-4C12 5.9 11.4 5.7 10.8 5.7 8.9 5.7 7.4 7.2 7.4 9.1c0 1.2.7 2.3 1.8 2.9v8.5H9z" fill="#FF9900" opacity=".2"/><text x="4" y="22" font-family="monospace" font-size="11" font-weight="700" fill="#FF9900">AWS</text></svg>
        <span>AWS</span>
      </div>
      <!-- Kubernetes -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="14" fill="#326CE5" opacity=".15" stroke="#326CE5" stroke-width="1"/><text x="8" y="20" font-family="monospace" font-size="10" font-weight="700" fill="#326CE5">K8s</text></svg>
        <span>Kubernetes</span>
      </div>
      <!-- Terraform -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><polygon points="12,4 12,16 21,11" fill="#7B42BC" opacity=".8"/><polygon points="21,11 21,23 30,18" fill="#7B42BC" opacity=".5"/><polygon points="3,18 12,23 12,11" fill="#7B42BC" opacity=".6"/></svg>
        <span>Terraform</span>
      </div>
      <!-- Prometheus -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="none" stroke="#E6522C" stroke-width="1.5" opacity=".6"/><circle cx="16" cy="16" r="4" fill="#E6522C" opacity=".8"/></svg>
        <span>Prometheus</span>
      </div>
      <!-- Grafana -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#F46800" opacity=".15" stroke="#F46800" stroke-width="1.5"/><path d="M10 20 L16 10 L22 16 L19 20 Z" fill="#F46800" opacity=".8"/></svg>
        <span>Grafana</span>
      </div>
      <!-- Datadog -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="6" fill="#632CA6" opacity=".15" stroke="#632CA6" stroke-width="1.5"/><text x="9" y="21" font-family="monospace" font-size="9" font-weight="700" fill="#632CA6">DD</text></svg>
        <span>Datadog</span>
      </div>
      <!-- Docker -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="3" y="10" width="7" height="5" rx="1" fill="#2496ED" opacity=".6"/><rect x="12" y="10" width="7" height="5" rx="1" fill="#2496ED" opacity=".8"/><rect x="12" y="4" width="7" height="5" rx="1" fill="#2496ED" opacity=".5"/><rect x="21" y="10" width="7" height="5" rx="1" fill="#2496ED"/><path d="M3 17c0 5 5 8 13 8s13-3 13-8H3z" fill="#2496ED" opacity=".3"/></svg>
        <span>Docker</span>
      </div>
      <!-- Helm -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><polygon points="16,3 29,10 29,22 16,29 3,22 3,10" fill="none" stroke="#0F1689" stroke-width="1.5" opacity=".7"/><text x="11" y="20" font-family="monospace" font-size="10" font-weight="700" fill="#0F1689">⎈</text></svg>
        <span>Helm</span>
      </div>
      <!-- ServiceNow -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#81B5A1" opacity=".2" stroke="#81B5A1" stroke-width="1.5"/><text x="8" y="21" font-family="monospace" font-size="9" font-weight="700" fill="#81B5A1">SN</text></svg>
        <span>ServiceNow</span>
      </div>
      <!-- Confluence -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#0052CC" opacity=".15" stroke="#0052CC" stroke-width="1.5"/><path d="M7 22 Q16 12 25 10" stroke="#0052CC" stroke-width="2" fill="none" opacity=".8"/><path d="M7 10 Q16 18 25 22" stroke="#0052CC" stroke-width="2" fill="none" opacity=".5"/></svg>
        <span>Confluence</span>
      </div>
      <!-- Jira -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><path d="M16 3 L29 16 L16 29 L3 16Z" fill="#0052CC" opacity=".15" stroke="#0052CC" stroke-width="1.5"/><path d="M16 9 L23 16 L16 20" stroke="#0052CC" stroke-width="2" fill="none" opacity=".8"/></svg>
        <span>Jira</span>
      </div>
      <!-- Slack -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="5" y="5" width="8" height="8" rx="3" fill="#E01E5A" opacity=".8"/><rect x="5" y="19" width="8" height="8" rx="3" fill="#36C5F0" opacity=".8"/><rect x="19" y="5" width="8" height="8" rx="3" fill="#2EB67D" opacity=".8"/><rect x="19" y="19" width="8" height="8" rx="3" fill="#ECB22E" opacity=".8"/></svg>
        <span>Slack</span>
      </div>
      <!-- Ansible -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="none" stroke="#EE0000" stroke-width="1.5" opacity=".6"/><text x="11" y="22" font-family="monospace" font-size="14" fill="#EE0000" opacity=".8">A</text></svg>
        <span>Ansible</span>
      </div>
      <!-- ArgoCD -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#EF7B4D" opacity=".15" stroke="#EF7B4D" stroke-width="1.5"/><path d="M10 22 C10 14 16 10 22 10" stroke="#EF7B4D" stroke-width="2" fill="none"/><circle cx="22" cy="10" r="3" fill="#EF7B4D"/></svg>
        <span>ArgoCD</span>
      </div>
      <!-- PagerDuty -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#06AC38" opacity=".15" stroke="#06AC38" stroke-width="1.5"/><text x="11" y="21" font-family="monospace" font-size="11" font-weight="700" fill="#06AC38">PD</text></svg>
        <span>PagerDuty</span>
      </div>
      <!-- ELK -->
      <div class="tool-logo">
        <svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#005571" opacity=".15" stroke="#005571" stroke-width="1.5"/><text x="9" y="21" font-family="monospace" font-size="10" font-weight="700" fill="#00BFB3">ELK</text></svg>
        <span>ELK Stack</span>
      </div>
    </div>
    <div class="ticker-inner" aria-hidden="true">
      <div class="tool-logo"><svg viewBox="0 0 32 32"><text x="4" y="22" font-family="monospace" font-size="11" font-weight="700" fill="#FF9900">AWS</text></svg><span>AWS</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="14" fill="#326CE5" opacity=".15" stroke="#326CE5" stroke-width="1"/><text x="8" y="20" font-family="monospace" font-size="10" font-weight="700" fill="#326CE5">K8s</text></svg><span>Kubernetes</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><polygon points="12,4 12,16 21,11" fill="#7B42BC" opacity=".8"/><polygon points="21,11 21,23 30,18" fill="#7B42BC" opacity=".5"/></svg><span>Terraform</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="none" stroke="#E6522C" stroke-width="1.5" opacity=".6"/><circle cx="16" cy="16" r="4" fill="#E6522C" opacity=".8"/></svg><span>Prometheus</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#F46800" opacity=".15" stroke="#F46800" stroke-width="1.5"/><path d="M10 20 L16 10 L22 16 L19 20 Z" fill="#F46800" opacity=".8"/></svg><span>Grafana</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="6" fill="#632CA6" opacity=".15" stroke="#632CA6" stroke-width="1.5"/><text x="9" y="21" font-family="monospace" font-size="9" font-weight="700" fill="#632CA6">DD</text></svg><span>Datadog</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="3" y="10" width="7" height="5" rx="1" fill="#2496ED" opacity=".6"/><rect x="12" y="10" width="7" height="5" rx="1" fill="#2496ED" opacity=".8"/><rect x="21" y="10" width="7" height="5" rx="1" fill="#2496ED"/></svg><span>Docker</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="5" y="5" width="8" height="8" rx="3" fill="#E01E5A" opacity=".8"/><rect x="5" y="19" width="8" height="8" rx="3" fill="#36C5F0" opacity=".8"/><rect x="19" y="5" width="8" height="8" rx="3" fill="#2EB67D" opacity=".8"/><rect x="19" y="19" width="8" height="8" rx="3" fill="#ECB22E" opacity=".8"/></svg><span>Slack</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#0052CC" opacity=".15" stroke="#0052CC" stroke-width="1.5"/><path d="M7 22 Q16 12 25 10" stroke="#0052CC" stroke-width="2" fill="none" opacity=".8"/></svg><span>Confluence</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><path d="M16 3 L29 16 L16 29 L3 16Z" fill="#0052CC" opacity=".15" stroke="#0052CC" stroke-width="1.5"/></svg><span>Jira</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#81B5A1" opacity=".2" stroke="#81B5A1" stroke-width="1.5"/><text x="8" y="21" font-family="monospace" font-size="9" font-weight="700" fill="#81B5A1">SN</text></svg><span>ServiceNow</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#06AC38" opacity=".15" stroke="#06AC38" stroke-width="1.5"/><text x="11" y="21" font-family="monospace" font-size="11" font-weight="700" fill="#06AC38">PD</text></svg><span>PagerDuty</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="none" stroke="#EE0000" stroke-width="1.5" opacity=".6"/><text x="11" y="22" font-family="monospace" font-size="14" fill="#EE0000" opacity=".8">A</text></svg><span>Ansible</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><circle cx="16" cy="16" r="13" fill="#EF7B4D" opacity=".15" stroke="#EF7B4D" stroke-width="1.5"/><path d="M10 22 C10 14 16 10 22 10" stroke="#EF7B4D" stroke-width="2" fill="none"/></svg><span>ArgoCD</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#005571" opacity=".15" stroke="#005571" stroke-width="1.5"/><text x="9" y="21" font-family="monospace" font-size="10" font-weight="700" fill="#00BFB3">ELK</text></svg><span>ELK Stack</span></div>
      <div class="tool-logo"><svg viewBox="0 0 32 32"><rect x="4" y="4" width="24" height="24" rx="4" fill="#EE0000" opacity=".15" stroke="#EE0000" stroke-width="1.5"/><text x="7" y="21" font-family="monospace" font-size="8" font-weight="700" fill="#EE0000">GitLab</text></svg><span>GitLab CI</span></div>
    </div>
  </div>
</div>

<!-- ═══════════ IMPACT ═══════════ -->
<div class="impact-wrap">
  <div class="impact-inner">
    <div class="impact-item reveal"><span class="impact-num">200+</span><span class="impact-label">Servers<br>Automated</span></div>
    <div class="impact-item reveal reveal-delay-1"><span class="impact-num">60+</span><span class="impact-label">Incident<br>Playbooks</span></div>
    <div class="impact-item reveal reveal-delay-2"><span class="impact-num">15</span><span class="impact-label">Microservices<br>Secured</span></div>
    <div class="impact-item reveal reveal-delay-3"><span class="impact-num">4h→45m</span><span class="impact-label">Provisioning<br>Time Cut</span></div>
    <div class="impact-item reveal"><span class="impact-num">12</span><span class="impact-label">User Journeys<br>Monitored</span></div>
  </div>
</div>

<!-- ═══════════ SKILLS ═══════════ -->
<section id="skills">
  <div class="skills-header">
    <div>
      <p class="s-label">Core competencies</p>
      <h2 class="s-title reveal">Skills &<br><em>expertise</em></h2>
    </div>
    <p class="s-sub reveal">Every tool chosen for production reliability, not résumé padding.</p>
  </div>
  <div class="skills-grid">

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.5"><path d="M3 3h7v7H3zM14 3h7v7h-7zM14 14h7v7h-7zM3 14h7v7H3z"/></svg>
        </div>
        <div><p class="skill-cat">Observability</p><p class="skill-name">Full-Stack Monitoring</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">Prometheus</span><span class="stag hot">Grafana</span><span class="stag hot">Datadog</span><span class="stag">Splunk</span><span class="stag">ELK Stack</span><span class="stag">CloudWatch</span><span class="stag">SLO Tracking</span><span class="stag">Synthetic Monitors</span><span class="stag">Burn-Rate Alerts</span></div>
    </div>

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#a78bfa" stroke-width="1.5"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
        </div>
        <div><p class="skill-cat">Cloud & Infrastructure</p><p class="skill-name">Multi-Cloud Operations</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">AWS EKS</span><span class="stag hot">Azure AKS</span><span class="stag">GCP GKE</span><span class="stag">EC2</span><span class="stag">RDS</span><span class="stag">S3</span><span class="stag">IAM</span><span class="stag">Secrets Manager</span><span class="stag">Azure Key Vault</span></div>
    </div>

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#00e5a0" stroke-width="1.5"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"/></svg>
        </div>
        <div><p class="skill-cat">Containers & K8s</p><p class="skill-name">Kubernetes at Scale</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">Kubernetes</span><span class="stag hot">Docker</span><span class="stag hot">Helm</span><span class="stag">HPA · VPA</span><span class="stag">KEDA</span><span class="stag">Cluster Autoscaler</span><span class="stag">ArgoCD</span><span class="stag">GitOps</span></div>
    </div>

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#f5a623" stroke-width="1.5"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
        </div>
        <div><p class="skill-cat">IaC & Automation</p><p class="skill-name">Zero-Touch Provisioning</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">Terraform</span><span class="stag hot">Ansible</span><span class="stag">Jenkins</span><span class="stag">GitLab CI/CD</span><span class="stag">Python</span><span class="stag">Bash</span><span class="stag">Config Drift Prevention</span></div>
    </div>

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#ff4f6b" stroke-width="1.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </div>
        <div><p class="skill-cat">Security & DevSecOps</p><p class="skill-name">Shift-Left Security</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">Trivy</span><span class="stag">Snyk</span><span class="stag">SonarQube</span><span class="stag">IRSA</span><span class="stag">OWASP</span><span class="stag">AWS Security Hub</span><span class="stag">Network Policies</span><span class="stag">Pod Security Standards</span></div>
    </div>

    <div class="skill-card reveal">
      <div class="skill-card-head">
        <div class="skill-icon-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.5"><path d="M18 8h1a4 4 0 0 1 0 8h-1"/><path d="M2 8h16v9a4 4 0 0 1-4 4H6a4 4 0 0 1-4-4V8z"/><line x1="6" y1="1" x2="6" y2="4"/><line x1="10" y1="1" x2="10" y2="4"/><line x1="14" y1="1" x2="14" y2="4"/></svg>
        </div>
        <div><p class="skill-cat">Incident Management</p><p class="skill-name">ITSM & Reliability</p></div>
      </div>
      <div class="skill-tags"><span class="stag hot">PagerDuty</span><span class="stag hot">ServiceNow</span><span class="stag">Confluence</span><span class="stag">Jira</span><span class="stag">Slack</span><span class="stag">Error Budgets</span><span class="stag">Blameless PIR</span><span class="stag">Runbook Library</span></div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- ═══════════ TOOLS MOSAIC ═══════════ -->
<div class="tools-section" id="tools">
  <p class="s-label">Technology stack</p>
  <h2 class="s-title reveal">Every tool,<br><em>production-proven</em></h2>
  <div class="tools-mosaic">

    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><text x="2" y="28" font-family="monospace" font-size="14" font-weight="800" fill="#FF9900">AWS</text></svg>
      <span class="tool-tile-name">AWS</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="none" stroke="#326CE5" stroke-width="2" opacity=".7"/><text x="11" y="25" font-family="monospace" font-size="12" font-weight="700" fill="#326CE5">K8s</text></svg>
      <span class="tool-tile-name">Kubernetes</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><polygon points="15,4 15,20 26,13" fill="#7B42BC"/><polygon points="26,13 26,29 37,22" fill="#7B42BC" opacity=".6"/><polygon points="4,22 15,29 15,13" fill="#7B42BC" opacity=".8"/></svg>
      <span class="tool-tile-name">Terraform</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="6" y="12" width="9" height="7" rx="1.5" fill="#2496ED" opacity=".7"/><rect x="16" y="12" width="9" height="7" rx="1.5" fill="#2496ED" opacity=".9"/><rect x="16" y="5" width="9" height="7" rx="1.5" fill="#2496ED" opacity=".5"/><rect x="26" y="12" width="9" height="7" rx="1.5" fill="#2496ED"/><path d="M4 22c0 6 6 10 16 10s16-4 16-10H4z" fill="#2496ED" opacity=".3"/></svg>
      <span class="tool-tile-name">Docker</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="16" fill="none" stroke="#E6522C" stroke-width="2" opacity=".7"/><circle cx="20" cy="20" r="6" fill="#E6522C"/><line x1="20" y1="4" x2="20" y2="10" stroke="#E6522C" stroke-width="2"/><line x1="20" y1="30" x2="20" y2="36" stroke="#E6522C" stroke-width="2"/><line x1="4" y1="20" x2="10" y2="20" stroke="#E6522C" stroke-width="2"/><line x1="30" y1="20" x2="36" y2="20" stroke="#E6522C" stroke-width="2"/></svg>
      <span class="tool-tile-name">Prometheus</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="#F46800" opacity=".12" stroke="#F46800" stroke-width="1.5"/><path d="M12 26 L20 12 L28 20 L24 26 Z" fill="#F46800" opacity=".9"/></svg>
      <span class="tool-tile-name">Grafana</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="5" y="5" width="30" height="30" rx="8" fill="#632CA6" opacity=".15" stroke="#632CA6" stroke-width="1.5"/><text x="11" y="26" font-family="monospace" font-size="12" font-weight="700" fill="#632CA6">DD</text></svg>
      <span class="tool-tile-name">Datadog</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><polygon points="20,4 36,13 36,27 20,36 4,27 4,13" fill="none" stroke="#0F1689" stroke-width="2" opacity=".7"/><text x="14" y="25" font-family="monospace" font-size="14" fill="#0F1689">⎈</text></svg>
      <span class="tool-tile-name">Helm</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="5" y="5" width="30" height="30" rx="6" fill="#0052CC" opacity=".12" stroke="#0052CC" stroke-width="1.5"/><path d="M8 28 Q20 14 32 12" stroke="#0052CC" stroke-width="2.5" fill="none" opacity=".9"/><path d="M8 12 Q20 24 32 28" stroke="#0052CC" stroke-width="2.5" fill="none" opacity=".5"/></svg>
      <span class="tool-tile-name">Confluence</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><path d="M20 4 L36 20 L20 36 L4 20Z" fill="#0052CC" opacity=".12" stroke="#0052CC" stroke-width="1.5"/><path d="M20 11 L29 20 L20 25" stroke="#0052CC" stroke-width="2.5" fill="none"/></svg>
      <span class="tool-tile-name">Jira</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="6" y="6" width="11" height="11" rx="4" fill="#E01E5A" opacity=".85"/><rect x="6" y="23" width="11" height="11" rx="4" fill="#36C5F0" opacity=".85"/><rect x="23" y="6" width="11" height="11" rx="4" fill="#2EB67D" opacity=".85"/><rect x="23" y="23" width="11" height="11" rx="4" fill="#ECB22E" opacity=".85"/></svg>
      <span class="tool-tile-name">Slack</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="#81B5A1" opacity=".15" stroke="#81B5A1" stroke-width="1.5"/><text x="10" y="26" font-family="monospace" font-size="11" font-weight="700" fill="#81B5A1">SN</text></svg>
      <span class="tool-tile-name">ServiceNow</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="5" y="5" width="30" height="30" rx="6" fill="#06AC38" opacity=".12" stroke="#06AC38" stroke-width="1.5"/><text x="12" y="26" font-family="monospace" font-size="12" font-weight="700" fill="#06AC38">PD</text></svg>
      <span class="tool-tile-name">PagerDuty</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="none" stroke="#EE0000" stroke-width="2" opacity=".7"/><text x="13" y="28" font-family="monospace" font-size="18" fill="#EE0000" opacity=".9">A</text></svg>
      <span class="tool-tile-name">Ansible</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="#EF7B4D" opacity=".12" stroke="#EF7B4D" stroke-width="1.5"/><path d="M12 28 C12 18 20 12 28 12" stroke="#EF7B4D" stroke-width="2.5" fill="none"/><circle cx="28" cy="12" r="4" fill="#EF7B4D"/></svg>
      <span class="tool-tile-name">ArgoCD</span>
    </div>
    <div class="tool-tile reveal">
      <svg viewBox="0 0 40 40"><rect x="5" y="5" width="30" height="30" rx="6" fill="#005571" opacity=".12" stroke="#005571" stroke-width="1.5"/><text x="8" y="27" font-family="monospace" font-size="11" font-weight="700" fill="#00BFB3">ELK</text></svg>
      <span class="tool-tile-name">ELK Stack</span>
    </div>

  </div>
</div>

<div class="divider"></div>

<!-- ═══════════ SERVICES ═══════════ -->
<section id="services">
  <p class="s-label">What I offer</p>
  <h2 class="s-title reveal">Services &<br><em>capabilities</em></h2>
  <div class="services-grid">

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(0,212,255,0.08),transparent)"></div>
      <p class="svc-num">01</p>
      <div class="svc-icon" style="border-color:rgba(0,212,255,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.5"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg></div>
      <p class="svc-name">SRE & Reliability Engineering</p>
      <p class="svc-desc">Define SLOs, track error budgets, build burn-rate alerts. Design incident workflows with PagerDuty and ServiceNow — including P1/P2 escalation, blameless PIR, and a Confluence runbook library that brings new engineers to speed in days, not weeks.</p>
      <div class="svc-tools"><span class="stag">SLO Design</span><span class="stag">Error Budgets</span><span class="stag">PagerDuty</span><span class="stag">ServiceNow</span></div>
    </div>

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(167,139,250,0.08),transparent)"></div>
      <p class="svc-num">02</p>
      <div class="svc-icon" style="border-color:rgba(167,139,250,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#a78bfa" stroke-width="1.5"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg></div>
      <p class="svc-name">Kubernetes & Multi-Cloud</p>
      <p class="svc-desc">Design and operate production-grade clusters on AWS EKS, Azure AKS, and GCP GKE. Implement HPA, KEDA, cluster autoscaler, and pod rightsizing with VPA recommendations for significant compute cost reduction.</p>
      <div class="svc-tools"><span class="stag">EKS · AKS · GKE</span><span class="stag">Helm</span><span class="stag">ArgoCD</span><span class="stag">KEDA</span></div>
    </div>

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(0,229,160,0.08),transparent)"></div>
      <p class="svc-num">03</p>
      <div class="svc-icon" style="border-color:rgba(0,229,160,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#00e5a0" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg></div>
      <p class="svc-name">Observability & Monitoring</p>
      <p class="svc-desc">Build full-stack observability with Prometheus, Grafana, and Datadog. Design synthetic monitors validating 12+ critical user journeys and golden-signal dashboards — latency, traffic, errors, saturation — with anomaly detection ahead of threshold alerts.</p>
      <div class="svc-tools"><span class="stag">Prometheus</span><span class="stag">Grafana</span><span class="stag">Datadog</span><span class="stag">ELK</span></div>
    </div>

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(245,166,35,0.08),transparent)"></div>
      <p class="svc-num">04</p>
      <div class="svc-icon" style="border-color:rgba(245,166,35,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#f5a623" stroke-width="1.5"><polyline points="4 17 10 11 4 5"/><line x1="12" y1="19" x2="20" y2="19"/></svg></div>
      <p class="svc-name">Infrastructure Automation</p>
      <p class="svc-desc">Eliminate toil with reusable Terraform modules, Ansible roles, and Python/Bash scripts. Cut provisioning from hours to minutes. Standardise environments across 200+ servers and eradicate configuration drift for good.</p>
      <div class="svc-tools"><span class="stag">Terraform</span><span class="stag">Ansible</span><span class="stag">Python</span><span class="stag">Bash</span></div>
    </div>

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(255,79,107,0.08),transparent)"></div>
      <p class="svc-num">05</p>
      <div class="svc-icon" style="border-color:rgba(255,79,107,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#ff4f6b" stroke-width="1.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg></div>
      <p class="svc-name">DevSecOps & CI/CD</p>
      <p class="svc-desc">Integrate Trivy, Snyk, and SonarQube into every merge request pipeline. Block critical CVEs before production. Enforce IRSA, least-privilege IAM, and secrets management across all microservices — tracked end-to-end in Jira.</p>
      <div class="svc-tools"><span class="stag">Trivy</span><span class="stag">Snyk</span><span class="stag">GitLab CI</span><span class="stag">Jira</span></div>
    </div>

    <div class="svc-card reveal">
      <div class="svc-card-glow" style="background:radial-gradient(circle,rgba(0,212,255,0.08),transparent)"></div>
      <p class="svc-num">06</p>
      <div class="svc-icon" style="border-color:rgba(0,212,255,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.5"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg></div>
      <p class="svc-name">Chaos Engineering</p>
      <p class="svc-desc">Design GameDay exercises using LitmusChaos and ChaosMonkey to validate resilience before production incidents do. Simulate pod kills, latency injection, DB failovers, and traffic spikes — all results documented in Confluence with corrective runbooks.</p>
      <div class="svc-tools"><span class="stag">LitmusChaos</span><span class="stag">ChaosMonkey</span><span class="stag">Confluence</span><span class="stag">GameDay</span></div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- ═══════════ PROJECTS ═══════════ -->
<section id="projects">
  <div class="projects-header">
    <div>
      <p class="s-label">Selected work</p>
      <h2 class="s-title reveal">Projects &<br><em>initiatives</em></h2>
    </div>
  </div>
  <div class="projects-list">
    <div class="proj-row reveal"><span class="proj-num">— 01</span><div><p class="proj-name">Full-Stack Observability Program</p><p class="proj-desc">Built Prometheus + Grafana + Datadog + ELK stack with synthetic monitors validating 12 critical user journeys. Enabled anomaly detection ahead of threshold alerts — incidents caught before user impact. Custom dashboards track golden signals per microservice with burn-rate alerting.</p></div><span class="proj-badge pb-obs">Observability</span></div>
    <div class="proj-row reveal"><span class="proj-num">— 02</span><div><p class="proj-name">Kubernetes Cost Optimisation</p><p class="proj-desc">Implemented HPA, Cluster Autoscaler, VPA-based pod rightsizing, and spot instance migration for batch workloads across EKS. Achieved significant monthly compute cost reduction without SLO impact. All change requests tracked in ServiceNow with CAB-approved change windows.</p></div><span class="proj-badge pb-cost">Cost Eng</span></div>
    <div class="proj-row reveal"><span class="proj-num">— 03</span><div><p class="proj-name">Runbook Library — 60+ Playbooks</p><p class="proj-desc">Built and maintained 60+ incident playbooks in Confluence covering every P1/P2 failure mode. On-call ramp-up reduced from 3 weeks to 5 days. Integrated with ServiceNow so the relevant playbook surfaces automatically when an incident is created.</p></div><span class="proj-badge pb-rel">Reliability</span></div>
    <div class="proj-row reveal"><span class="proj-num">— 04</span><div><p class="proj-name">Automated Provisioning Framework</p><p class="proj-desc">Reusable Terraform modules and Ansible roles standardising environment creation across AWS, Azure, and GCP. Provisioning time from 4 hours to 45 minutes. Eliminated configuration drift across 200+ servers. Zero rollback incidents over 6 consecutive quarterly releases.</p></div><span class="proj-badge pb-iac">IaC</span></div>
    <div class="proj-row reveal"><span class="proj-num">— 05</span><div><p class="proj-name">DevSecOps Shift-Left Pipeline</p><p class="proj-desc">Integrated Trivy, Snyk, and SonarQube into GitLab CI/CD. Hard gates on critical CVEs across 15 microservices over 12 months. All vulnerability tracking managed in Jira with SLA-based remediation targets and Slack notifications for critical findings.</p></div><span class="proj-badge pb-sec">Security</span></div>
    <div class="proj-row reveal"><span class="proj-num">— 06</span><div><p class="proj-name">Centralised Secrets Management</p><p class="proj-desc">AWS Secrets Manager + IRSA on EKS eliminating hardcoded credentials across 8 microservices. Passed first-pass external security audit. Secrets rotation automated with CloudWatch alerts on expiry. Network hardening — security groups, VPC NACLs, WAF — documented in Confluence.</p></div><span class="proj-badge pb-sec">Security</span></div>
  </div>
</section>

<div class="divider"></div>

<!-- ═══════════ CERTIFICATIONS ═══════════ -->
<section id="certs">
  <p class="s-label">Credentials</p>
  <h2 class="s-title reveal">Education &<br><em>certifications</em></h2>
  <div class="certs-grid">
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(0,212,255,0.08);border-color:rgba(0,212,255,0.2)"><span style="font-size:18px">🎓</span></div><div><p class="cert-name">M.Tech — CGPA 8.9 / 10</p><p class="cert-org">NIT Kurukshetra · 2013–2015</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(167,139,250,0.08);border-color:rgba(167,139,250,0.2)"><span style="font-size:18px">🎓</span></div><div><p class="cert-name">B.Tech — CGPA 8.2 / 10</p><p class="cert-org">Sir Chhotu Ram Inst. · 2009–2013</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(255,79,107,0.08);border-color:rgba(255,79,107,0.2)"><span style="font-size:18px">🛡</span></div><div><p class="cert-name">Application Security in DevSecOps</p><p class="cert-org">NASBA</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(0,229,160,0.08);border-color:rgba(0,229,160,0.2)"><span style="font-size:18px">⚙</span></div><div><p class="cert-name">DevOps Foundations</p><p class="cert-org">CompTIA</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(255,153,0,0.08);border-color:rgba(255,153,0,0.2)"><span style="font-size:18px">☁</span></div><div><p class="cert-name">DevOps and AI on AWS: AIOps</p><p class="cert-org">Coursera</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(238,0,0,0.08);border-color:rgba(238,0,0,0.2)"><span style="font-size:18px">⎈</span></div><div><p class="cert-name">Cloud-Native with OpenShift & Kubernetes</p><p class="cert-org">Red Hat</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(0,120,212,0.08);border-color:rgba(0,120,212,0.2)"><span style="font-size:18px">🤖</span></div><div><p class="cert-name">Foundations of AI & Machine Learning</p><p class="cert-org">Microsoft</p></div></div>
    <div class="cert-card reveal"><div class="cert-icon-wrap" style="background:rgba(66,133,244,0.08);border-color:rgba(66,133,244,0.2)"><span style="font-size:18px">🔧</span></div><div><p class="cert-name">Developing a Google SRE Culture</p><p class="cert-org">Google Cloud Skills Boost</p></div></div>
  </div>
</section>

<div class="divider"></div>

<!-- ═══════════ CTA ═══════════ -->
<div class="cta-wrap" id="contact">
  <p class="s-label" style="justify-content:center">Let's work together</p>
  <h2 class="reveal">Your infrastructure,<br><em style="font-family:var(--display);background:linear-gradient(135deg,var(--cyan),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text">made reliable.</em></h2>
  <p class="reveal">Whether it's a greenfield SRE programme, a reliability crisis, a Kubernetes cost problem, or a DevSecOps pipeline — I'm ready to help.</p>
  <div class="contact-grid reveal">
    <a href="mailto:aksingh3134@gmail.com" class="contact-card">
      <div class="contact-card-icon"><svg viewBox="0 0 24 24" fill="none" stroke-width="1.5"><rect x="2" y="4" width="20" height="16" rx="2" stroke="currentColor"/><path d="m2 7 10 7 10-7" stroke="currentColor"/></svg></div>
      <div><p class="contact-card-label">Email</p><p class="contact-card-val">aksingh3134@gmail.com</p></div>
    </a>
    <a href="https://linkedin.com/in/aditya-singh-cloud" target="_blank" class="contact-card">
      <div class="contact-card-icon"><svg viewBox="0 0 24 24" fill="none" stroke-width="1.5"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-4 0v7h-4v-7a6 6 0 0 1 6-6z" stroke="currentColor"/><rect x="2" y="9" width="4" height="12" stroke="currentColor"/><circle cx="4" cy="4" r="2" stroke="currentColor"/></svg></div>
      <div><p class="contact-card-label">LinkedIn</p><p class="contact-card-val">aditya-singh-cloud</p></div>
    </a>
    <a href="tel:+917458995596" class="contact-card">
      <div class="contact-card-icon"><svg viewBox="0 0 24 24" fill="none" stroke-width="1.5"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.8 19.8 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.12 4.18 2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z" stroke="currentColor"/></svg></div>
      <div><p class="contact-card-label">Phone</p><p class="contact-card-val">+91 74589 95596</p></div>
    </a>
    <div class="contact-card" style="border-color:rgba(0,212,255,.2);background:rgba(0,212,255,.03)">
      <div class="contact-card-icon" style="border-color:rgba(0,212,255,.2)"><svg viewBox="0 0 24 24" fill="none" stroke="#00d4ff" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg></div>
      <div><p class="contact-card-label" style="color:var(--cyan)">Location</p><p class="contact-card-val">Noida, India · Open to Remote</p></div>
    </div>
  </div>
</div>

<!-- ═══════════ FOOTER ═══════════ -->
<footer>
  <div class="footer-brand">
    <div class="footer-badge">AK</div>
    <span class="footer-text">Aditya Kumar Singh — Site Reliability Engineer</span>
  </div>
  <p class="footer-right">Noida, Uttar Pradesh, India · 2025</p>
</footer>

<script>
const obs = new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible')});
},{threshold:.08,rootMargin:'0px 0px -30px 0px'});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body>
</html>
