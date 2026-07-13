
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SpeakUP English — платформа для изучения английского</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,600;9..144,700;9..144,900&family=Inter:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#211c30;
  --ink-soft:#4c4563;
  --petrol:#2a1b4d;
  --petrol-2:#3c2570;
  --paper:#f6f0e4;
  --paper-2:#ffffff;
  --marigold:#e8724a;
  --marigold-dark:#c0562f;
  --teal:#4a9b76;
  --coral:#d4483f;
  --line:rgba(24,34,52,0.12);
  --shadow:0 18px 40px -18px rgba(15,50,56,0.45);
  --radius:18px;
}
*{box-sizing:border-box;}
html,body{margin:0;padding:0;}
body{
  font-family:'Inter',sans-serif;
  background:
    radial-gradient(1200px 800px at 8% -10%, #3c2570 0%, transparent 60%),
    radial-gradient(1000px 700px at 110% 10%, #1a1030 0%, transparent 55%),
    linear-gradient(180deg,var(--petrol) 0%, var(--petrol-2) 100%);
  color:var(--ink);
  min-height:100vh;
  -webkit-font-smoothing:antialiased;
}
.hidden{display:none !important;}
h1,h2,h3,.display{
  font-family:'Fraunces',serif;
  letter-spacing:-0.01em;
}
.mono{font-family:'IBM Plex Mono',monospace;}
button{font-family:inherit;cursor:pointer;}
::selection{background:var(--marigold);color:var(--ink);}

/* ---------- shell ---------- */
.app-shell{
  max-width:1180px;
  margin:0 auto;
  padding:28px 20px 80px;
}
.topbar{
  display:flex;
  align-items:center;
  justify-content:space-between;
  color:var(--paper);
  margin-bottom:22px;
  padding:0 4px;
}
.brand{
  display:flex;align-items:center;gap:10px;
  font-family:'Fraunces',serif;
  font-weight:700;
  font-size:22px;
  color:var(--paper);
}
.brand-mark{
  width:34px;height:34px;border-radius:8px;
  background:var(--marigold);
  display:flex;align-items:center;justify-content:center;
  color:var(--ink);font-weight:800;font-size:15px;
  box-shadow:0 4px 0 var(--marigold-dark);
  transform:rotate(-4deg);
}
.topbar-right{display:flex;align-items:center;gap:14px;font-size:13px;color:rgba(244,239,226,0.75);}
.user-chip{
  background:rgba(244,239,226,0.1);
  border:1px solid rgba(244,239,226,0.2);
  padding:6px 12px;border-radius:999px;
  display:flex;align-items:center;gap:8px;
}
.user-chip .dot{width:8px;height:8px;border-radius:50%;background:var(--teal);}
.logout-link{color:rgba(244,239,226,0.6);text-decoration:underline;background:none;border:none;font-size:13px;}

/* ---------- card base ---------- */
.card{
  background:var(--paper-2);
  border-radius:var(--radius);
  box-shadow:var(--shadow);
  border:1px solid rgba(24,34,52,0.06);
}

/* ---------- LOGIN ---------- */
.login-wrap{
  min-height:78vh;
  display:flex;align-items:center;justify-content:center;
}
.login-card{
  width:100%;max-width:460px;
  padding:44px 38px 36px;
  position:relative;
  overflow:hidden;
}
.login-card::before{
  content:"";
  position:absolute;top:-60px;right:-60px;
  width:180px;height:180px;border-radius:50%;
  background:radial-gradient(circle,rgba(232,163,61,0.35),transparent 70%);
}
.passport-cover{
  width:56px;height:56px;border-radius:12px;
  background:linear-gradient(160deg,var(--petrol),var(--petrol-2));
  display:flex;align-items:center;justify-content:center;
  color:var(--marigold);font-size:26px;margin-bottom:18px;
  box-shadow:0 6px 0 rgba(15,50,56,0.3);
}
.login-card h1{font-size:30px;margin:0 0 6px;color:var(--ink);}
.login-card p.sub{margin:0 0 26px;color:var(--ink-soft);font-size:14.5px;line-height:1.5;}
.field{margin-bottom:16px;}
.field label{display:block;font-size:12.5px;text-transform:uppercase;letter-spacing:0.06em;color:var(--ink-soft);margin-bottom:6px;font-weight:600;}
.field input{
  width:100%;padding:13px 14px;border-radius:10px;
  border:1.5px solid var(--line);font-size:15px;
  background:#fbf9f4;color:var(--ink);
}
.field input:focus{outline:2px solid var(--marigold);outline-offset:1px;border-color:var(--marigold);}
.btn{
  border:none;border-radius:11px;
  padding:13px 22px;font-size:15px;font-weight:700;
  display:inline-flex;align-items:center;justify-content:center;gap:8px;
  transition:transform .12s ease, box-shadow .12s ease;
}
.btn:active{transform:translateY(2px);}
.btn-primary{
  background:var(--marigold);color:var(--ink);
  box-shadow:0 5px 0 var(--marigold-dark);
  width:100%;
}
.btn-primary:hover{filter:brightness(1.03);}
.btn-primary:active{box-shadow:0 2px 0 var(--marigold-dark);}
.btn-ghost{
  background:transparent;color:var(--paper);
  border:1.5px solid rgba(244,239,226,0.35);
}
.btn-dark{
  background:var(--ink);color:var(--paper);
  box-shadow:0 5px 0 #000;
}
.btn-outline{
  background:transparent;border:1.5px solid var(--line);color:var(--ink);
}
.btn:focus-visible{outline:3px solid var(--marigold);outline-offset:2px;}
.login-note{margin-top:18px;font-size:12.5px;color:var(--ink-soft);display:flex;gap:8px;align-items:flex-start;line-height:1.5;}
.lang-switch{position:absolute;top:18px;right:18px;display:flex;gap:4px;background:#f0e9d6;border-radius:999px;padding:3px;z-index:2;}
.lang-switch button{
  border:none;background:transparent;padding:6px 10px;border-radius:999px;
  font-size:11.5px;font-weight:700;color:var(--ink-soft);font-family:'IBM Plex Mono',monospace;letter-spacing:.02em;
}
.lang-switch button.active{background:var(--ink);color:var(--paper);}
.lang-switch.topbar-variant{background:rgba(244,239,226,0.12);}
.lang-switch.topbar-variant button{color:rgba(244,239,226,0.7);}
.lang-switch.topbar-variant button.active{background:var(--marigold);color:var(--ink);}

/* ---------- DASHBOARD ---------- */
.dash-header{
  display:grid;grid-template-columns:1.4fr 1fr;gap:18px;margin-bottom:22px;
}
@media(max-width:820px){.dash-header{grid-template-columns:1fr;}}
.passport-hero{
  padding:30px 32px;position:relative;overflow:hidden;color:var(--paper);
  background:linear-gradient(135deg,#2a1b4d 0%,#4a2f8a 100%);
  border-radius:var(--radius);box-shadow:var(--shadow);
}
.passport-hero::after{
  content:"";position:absolute;right:-40px;bottom:-60px;width:220px;height:220px;
  border:2px dashed rgba(244,239,226,0.18);border-radius:50%;
}
.eyebrow{font-family:'IBM Plex Mono',monospace;font-size:12px;letter-spacing:0.12em;text-transform:uppercase;color:var(--marigold);margin-bottom:10px;}
.passport-hero h2{font-size:28px;margin:0 0 6px;color:var(--paper);}
.passport-hero p{margin:0 0 20px;color:rgba(244,239,226,0.8);font-size:14.5px;max-width:46ch;}
.stat-row{display:flex;gap:22px;flex-wrap:wrap;}
.stat{min-width:90px;}
.stat .num{font-family:'Fraunces',serif;font-size:26px;font-weight:700;color:var(--marigold);line-height:1;}
.stat .label{font-size:12px;color:rgba(244,239,226,0.65);margin-top:4px;}

.stamps-card{padding:24px 26px;display:flex;flex-direction:column;}
.stamps-card h3{margin:0 0 4px;font-size:16px;color:var(--ink);}
.stamps-card .hint{font-size:12.5px;color:var(--ink-soft);margin:0 0 14px;}
.stamps-scroll{display:flex;gap:12px;overflow-x:auto;padding-bottom:6px;flex:1;align-items:center;min-height:78px;}
.stamp{
  flex:0 0 auto;width:74px;height:74px;border-radius:50%;
  border:2.5px dashed var(--coral);color:var(--coral);
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  transform:rotate(-6deg);font-family:'IBM Plex Mono',monospace;
  font-size:10px;text-align:center;line-height:1.25;padding:4px;
  opacity:0.85;
}
.stamp:nth-child(3n+1){transform:rotate(5deg);border-color:var(--teal);color:var(--teal);}
.stamp:nth-child(3n+2){transform:rotate(-9deg);border-color:var(--marigold-dark);color:var(--marigold-dark);}
.stamp b{font-size:14px;display:block;}
.stamps-empty{color:var(--ink-soft);font-size:13px;font-style:italic;}

.section-title{color:var(--paper);display:flex;align-items:baseline;justify-content:space-between;margin:34px 0 14px;}
.section-title h3{font-size:20px;margin:0;color:var(--paper);}
.section-title span{font-size:12.5px;color:rgba(244,239,226,0.55);font-family:'IBM Plex Mono',monospace;}

.topic-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:16px;}
.topic-card{
  padding:20px 20px 18px;display:flex;flex-direction:column;gap:10px;
  transition:transform .15s ease, box-shadow .15s ease;
}
.topic-card:hover{transform:translateY(-3px);}
.topic-card .icon{
  width:42px;height:42px;border-radius:10px;
  background:#f0e9d6;display:flex;align-items:center;justify-content:center;font-size:20px;
}
.topic-card h4{margin:0;font-size:16.5px;color:var(--ink);}
.topic-card p{margin:0;font-size:12.8px;color:var(--ink-soft);line-height:1.45;flex:1;}
.topic-meta{display:flex;justify-content:space-between;align-items:center;font-size:11.5px;color:var(--ink-soft);font-family:'IBM Plex Mono',monospace;}
.best-badge{background:#eef6f0;color:var(--teal);padding:2px 8px;border-radius:999px;font-weight:600;}
.topic-card .btn{margin-top:6px;padding:10px 16px;font-size:13.5px;}

.two-col{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
@media(max-width:820px){.two-col{grid-template-columns:1fr;}}
.feature-card{padding:24px;display:flex;flex-direction:column;gap:10px;}
.feature-card .icon-lg{font-size:30px;}
.feature-card h4{margin:0;font-size:19px;color:var(--ink);}
.feature-card p{margin:0;color:var(--ink-soft);font-size:13.5px;line-height:1.5;}

/* ---------- TEST SCREEN ---------- */
.test-wrap{max-width:720px;margin:0 auto;}
.progress-track{height:8px;border-radius:99px;background:rgba(244,239,226,0.18);overflow:hidden;margin-bottom:18px;}
.progress-fill{height:100%;background:var(--marigold);border-radius:99px;transition:width .3s ease;}
.progress-info{display:flex;justify-content:space-between;color:rgba(244,239,226,0.75);font-size:12.5px;font-family:'IBM Plex Mono',monospace;margin-bottom:10px;}
.question-card{padding:32px 30px;}
.q-eyebrow{font-family:'IBM Plex Mono',monospace;font-size:11.5px;color:var(--marigold-dark);text-transform:uppercase;letter-spacing:.08em;margin-bottom:10px;}
.q-text{font-size:21px;line-height:1.5;margin:0 0 22px;color:var(--ink);font-weight:500;}
.q-text b{color:var(--petrol-2);font-family:'IBM Plex Mono',monospace;background:#f0e9d6;padding:1px 6px;border-radius:5px;}
.options{display:grid;gap:10px;}
.opt-btn{
  text-align:left;padding:14px 16px;border-radius:12px;border:1.5px solid var(--line);
  background:#fbf9f4;font-size:15px;color:var(--ink);display:flex;align-items:center;gap:10px;
}
.opt-btn .letter{
  width:26px;height:26px;border-radius:7px;background:#eee6d3;color:var(--ink-soft);
  display:flex;align-items:center;justify-content:center;font-size:12.5px;font-weight:700;flex:0 0 auto;
  font-family:'IBM Plex Mono',monospace;
}
.opt-btn:hover{border-color:var(--marigold);}
.opt-btn.correct{background:#eaf6ee;border-color:var(--teal);color:#215c43;}
.opt-btn.correct .letter{background:var(--teal);color:#fff;}
.opt-btn.wrong{background:#fbebe9;border-color:var(--coral);color:#7f2b25;}
.opt-btn.wrong .letter{background:var(--coral);color:#fff;}
.opt-btn:disabled{cursor:default;}
.test-footer{display:flex;justify-content:space-between;align-items:center;margin-top:20px;}
.exit-link{color:rgba(244,239,226,0.65);background:none;border:none;font-size:13px;text-decoration:underline;}

/* ---------- RESULTS ---------- */
.results-wrap{max-width:720px;margin:0 auto;}
.score-card{padding:36px 32px;text-align:center;position:relative;overflow:hidden;}
.score-ring{
  width:130px;height:130px;border-radius:50%;margin:0 auto 18px;
  display:flex;align-items:center;justify-content:center;flex-direction:column;
  background:conic-gradient(var(--teal) calc(var(--pct)*1%), #eee6d3 0);
  position:relative;
}
.score-ring::before{content:"";position:absolute;inset:9px;border-radius:50%;background:var(--paper-2);}
.score-ring .val{position:relative;font-family:'Fraunces',serif;font-size:30px;font-weight:700;color:var(--ink);}
.score-ring .sub{position:relative;font-size:11px;color:var(--ink-soft);}
.score-title{font-size:20px;margin:0 0 4px;}
.score-topic{color:var(--ink-soft);font-size:13.5px;margin:0 0 22px;}
.ai-feedback{
  text-align:left;background:#f7f2e5;border:1px solid #eadfc2;border-radius:14px;
  padding:18px 20px;margin:20px 0;font-size:14.5px;line-height:1.6;color:var(--ink);
}
.ai-feedback .ai-tag{display:flex;align-items:center;gap:8px;font-family:'IBM Plex Mono',monospace;font-size:11px;color:var(--marigold-dark);text-transform:uppercase;letter-spacing:.06em;margin-bottom:8px;font-weight:600;}
.ai-dot{width:7px;height:7px;border-radius:50%;background:var(--marigold);animation:pulse 1.4s infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.3;}}
.review-list{text-align:left;margin-top:22px;}
.review-item{padding:12px 14px;border-radius:10px;background:#fbf9f4;border:1px solid var(--line);margin-bottom:8px;font-size:13.5px;}
.review-item .q{color:var(--ink-soft);margin-bottom:4px;}
.review-item .a-wrong{color:var(--coral);text-decoration:line-through;margin-right:8px;}
.review-item .a-right{color:var(--teal);font-weight:600;}
.results-actions{display:flex;gap:12px;margin-top:24px;justify-content:center;flex-wrap:wrap;}

/* ---------- LISTENING ---------- */
.listen-card{padding:34px 30px;text-align:center;}
.speed-row{display:flex;gap:6px;justify-content:center;margin-bottom:14px;}
.speed-row button{border:1.5px solid var(--line);background:#fbf9f4;color:var(--ink-soft);padding:5px 12px;border-radius:999px;font-size:12px;font-family:'IBM Plex Mono',monospace;font-weight:600;}
.speed-row button.active{background:var(--petrol);color:var(--marigold);border-color:var(--petrol);}
.level-tag{display:inline-block;font-family:'IBM Plex Mono',monospace;font-size:10.5px;text-transform:uppercase;letter-spacing:.06em;background:#f0e9d6;color:var(--ink-soft);padding:3px 9px;border-radius:999px;margin-bottom:14px;}
.example-line{background:#fbf9f4;border:1px solid var(--line);border-radius:10px;padding:10px 14px;font-size:14px;}
.example-line .en-ex{font-family:'Fraunces',serif;color:var(--ink);}
.example-line .tr-ex{color:var(--ink-soft);font-size:12.5px;margin-top:3px;}
.audio-btn{
  width:88px;height:88px;border-radius:50%;border:none;
  background:var(--petrol);color:var(--marigold);font-size:32px;
  box-shadow:0 6px 0 #1a1030;margin:6px auto 18px;
  display:flex;align-items:center;justify-content:center;
}
.audio-btn:active{box-shadow:0 2px 0 #1a1030;transform:translateY(4px);}
.audio-btn.speaking{animation:soundwave 1s infinite;}
@keyframes soundwave{0%,100%{box-shadow:0 6px 0 #1a1030, 0 0 0 0 rgba(232,114,74,0.5);}50%{box-shadow:0 6px 0 #1a1030, 0 0 0 14px rgba(232,114,74,0);}}
.replay-row{display:flex;gap:10px;justify-content:center;margin-bottom:22px;}
.small-link{background:none;border:none;color:var(--ink-soft);font-size:12.5px;text-decoration:underline;}
.transcript-box{background:#f0e9d6;border-radius:10px;padding:10px 14px;font-size:12.5px;color:var(--ink-soft);margin-bottom:18px;font-family:'IBM Plex Mono',monospace;text-align:left;display:none;}

/* ---------- SPEAKING ---------- */
.speak-card{padding:34px 30px;text-align:center;}
.phrase-box{background:#f7f2e5;border:1px solid #eadfc2;border-radius:14px;padding:20px 22px;margin-bottom:22px;}
.phrase-box .ru{color:var(--ink-soft);font-size:12.5px;margin-bottom:8px;text-transform:uppercase;letter-spacing:.04em;}
.phrase-box .en{font-size:22px;font-family:'Fraunces',serif;color:var(--ink);}
.mic-btn{
  width:88px;height:88px;border-radius:50%;border:none;
  background:var(--coral);color:#fff;font-size:30px;
  box-shadow:0 6px 0 #7f2b25;margin:6px auto 16px;
  display:flex;align-items:center;justify-content:center;
}
.mic-btn.listening{background:var(--teal);box-shadow:0 6px 0 #215c43;animation:soundwave 1s infinite;}
.mic-btn:active{transform:translateY(4px);}
.mic-btn:disabled{opacity:.5;cursor:not-allowed;}
.mic-status{font-size:13px;color:var(--ink-soft);margin-bottom:16px;min-height:18px;}
.speak-result{background:#fbf9f4;border-radius:12px;padding:14px 16px;margin-top:6px;text-align:left;font-size:13.5px;display:none;}
.speak-result .said{font-family:'IBM Plex Mono',monospace;color:var(--ink-soft);margin-bottom:6px;}
.match-bar-track{height:8px;border-radius:99px;background:#eee6d3;overflow:hidden;margin:6px 0;}
.match-bar-fill{height:100%;background:var(--teal);border-radius:99px;transition:width .3s ease;}
.unsupported-note{background:#fbebe9;border:1px solid #f0cdc9;color:#7f2b25;border-radius:10px;padding:12px 14px;font-size:13px;margin-bottom:18px;text-align:left;}
.mic-hear-btn{background:none;border:1.5px solid var(--line);color:var(--ink-soft);border-radius:999px;padding:6px 14px;font-size:12.5px;margin-bottom:14px;}

/* ---------- SPLASH ---------- */
#screen-splash{
  position:fixed;inset:0;z-index:100;
  display:flex;align-items:center;justify-content:center;flex-direction:column;
  background:
    radial-gradient(1200px 800px at 8% -10%, #3c2570 0%, transparent 60%),
    radial-gradient(1000px 700px at 110% 10%, #1a1030 0%, transparent 55%),
    linear-gradient(180deg,var(--petrol) 0%, var(--petrol-2) 100%);
  transition:opacity .5s ease, visibility .5s ease;
}
#screen-splash.fade-out{opacity:0;visibility:hidden;pointer-events:none;}
.splash-badge{
  width:84px;height:84px;border-radius:20px;
  background:var(--marigold);
  display:flex;align-items:center;justify-content:center;
  font-size:38px;color:var(--ink);
  box-shadow:0 8px 0 var(--marigold-dark);
  animation:splashFloat 2.2s ease-in-out infinite;
  margin-bottom:22px;
}
@keyframes splashFloat{
  0%,100%{transform:translateY(0) rotate(-4deg);}
  50%{transform:translateY(-10px) rotate(3deg);}
}
.splash-title{
  font-family:'Fraunces',serif;font-weight:700;font-size:28px;color:var(--paper);
  margin:0 0 6px;letter-spacing:-0.01em;
}
.splash-title span{color:var(--marigold);}
.splash-sub{color:rgba(244,239,226,0.6);font-size:13px;font-family:'IBM Plex Mono',monospace;margin-bottom:28px;letter-spacing:.03em;}
.splash-track{width:200px;height:5px;border-radius:99px;background:rgba(244,239,226,0.15);overflow:hidden;}
.splash-fill{height:100%;width:30%;border-radius:99px;background:var(--marigold);animation:splashLoad 1.4s ease-in-out infinite;}
@keyframes splashLoad{
  0%{transform:translateX(-100%);}
  100%{transform:translateX(400%);}
}

/* ---------- AUTH TABS / ADMIN ---------- */
.auth-tabs{display:flex;gap:6px;background:#f0e9d6;border-radius:12px;padding:4px;margin-bottom:22px;}
.auth-tabs button{flex:1;border:none;background:transparent;padding:10px;border-radius:9px;font-size:13.5px;font-weight:700;color:var(--ink-soft);}
.auth-tabs button.active{background:var(--ink);color:var(--paper);}
.field-error{color:var(--coral);font-size:12.5px;margin-top:-8px;margin-bottom:14px;min-height:16px;}
.pw-row{position:relative;}
.pw-toggle{position:absolute;right:12px;top:38px;background:none;border:none;color:var(--ink-soft);font-size:12px;text-decoration:underline;padding:2px;}
.admin-link{color:rgba(244,239,226,0.6);background:none;border:none;font-size:13px;text-decoration:underline;}
.admin-table{width:100%;border-collapse:collapse;font-size:13.5px;}
.admin-table th{text-align:left;padding:10px 12px;color:var(--ink-soft);font-size:11.5px;text-transform:uppercase;letter-spacing:.05em;font-family:'IBM Plex Mono',monospace;border-bottom:1.5px solid var(--line);}
.admin-table td{padding:11px 12px;border-bottom:1px solid var(--line);color:var(--ink);}
.admin-table tr:last-child td{border-bottom:none;}
.admin-you{color:var(--teal);font-weight:700;font-size:11px;margin-left:6px;}

/* toast */
.toast{
  position:fixed;bottom:22px;left:50%;transform:translateX(-50%);
  background:var(--ink);color:var(--paper);padding:12px 20px;border-radius:10px;
  font-size:13.5px;box-shadow:0 10px 30px rgba(0,0,0,0.3);z-index:50;
  opacity:0;pointer-events:none;transition:opacity .25s ease, transform .25s ease;
}
.toast.show{opacity:1;transform:translateX(-50%) translateY(-6px);}

@media(max-width:600px){
  .q-text{font-size:18px;}
  .app-shell{padding:20px 14px 60px;}
  .login-card{padding:32px 22px 28px;}
}
</style>
</head>
<body>

<!-- ===================== SPLASH ===================== -->
<div id="screen-splash">
  <div class="splash-badge">🗣️</div>
  <h1 class="splash-title">SpeakUP <span>English</span></h1>
  <div class="splash-sub" id="splash-sub">ЗАГРУЖАЕМ ВАШ КАБИНЕТ…</div>
  <div class="splash-track"><div class="splash-fill"></div></div>
</div>

<div class="app-shell">

  <!-- ===================== LOGIN ===================== -->
  <div id="screen-login" class="hidden">
    <div class="login-wrap">
      <div class="card login-card">
        <div class="lang-switch" id="lang-switch-login"></div>
        <div class="passport-cover">🗣️</div>
        <h1>SpeakUP <span style="color:var(--marigold-dark);">English</span></h1>
        <p class="sub" data-i18n="login_sub">Персональный кабинет для изучения английского. Создайте аккаунт с логином и паролем — и мы сохраним ваш профиль с историей тестов, темами и разбором результатов от ИИ.</p>

        <div class="auth-tabs">
          <button id="tab-login" class="active" data-i18n="tab_login">Вход</button>
          <button id="tab-register" data-i18n="tab_register">Регистрация</button>
        </div>

        <div class="field">
          <label for="login-name" data-i18n="login_name_label">Имя пользователя</label>
          <input id="login-name" type="text" data-i18n-placeholder="login_name_ph" placeholder="Например, aziz" maxlength="24" autocomplete="username">
        </div>
        <div class="field pw-row">
          <label for="login-pass" data-i18n="login_pass_label">Пароль</label>
          <input id="login-pass" type="password" data-i18n-placeholder="login_pass_ph" placeholder="Минимум 4 символа" maxlength="60" autocomplete="current-password">
          <button type="button" class="pw-toggle" id="pw-toggle" data-i18n="pw_show">показать</button>
        </div>
        <div class="field hidden" id="field-pass-confirm">
          <label for="login-pass2" data-i18n="login_pass2_label">Повторите пароль</label>
          <input id="login-pass2" type="password" data-i18n-placeholder="login_pass2_ph" placeholder="Ещё раз пароль" maxlength="60" autocomplete="new-password">
        </div>
        <div class="field-error" id="login-error"></div>

        <button class="btn btn-primary" id="btn-login" data-i18n="login_btn">Войти в кабинет →</button>
        <div class="login-note">
          <span>ℹ️</span>
          <span data-i18n="login_note">Логин и пароль сохраняются в защищённом хранилище (пароль хешируется и никогда не хранится открытым текстом). При следующем визите с любого устройства войдите с теми же данными — кабинет будет там же, где вы его оставили.</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ===================== ADMIN ===================== -->
  <div id="screen-admin" class="hidden">
    <div class="topbar">
      <div class="brand"><span class="brand-mark">🎤</span> SpeakUP English</div>
      <div class="topbar-right">
        <button class="logout-link" id="btn-admin-back" data-i18n="admin_back">← в кабинет</button>
        <button class="logout-link" id="btn-admin-logout" data-i18n="logout">выйти</button>
      </div>
    </div>
    <div class="section-title"><h3 data-i18n="admin_title">Пользователи платформы</h3><span id="admin-count">0</span></div>
    <div class="card" style="padding:10px 20px 20px;overflow-x:auto;">
      <table class="admin-table">
        <thead>
          <tr>
            <th data-i18n="admin_col_user">Пользователь</th>
            <th data-i18n="admin_col_joined">Регистрация</th>
            <th data-i18n="admin_col_tests">Тестов</th>
            <th data-i18n="admin_col_avg">Средний балл</th>
          </tr>
        </thead>
        <tbody id="admin-tbody"></tbody>
      </table>
    </div>
  </div>

  <!-- ===================== APP (после входа) ===================== -->
  <div id="screen-app" class="hidden">

    <div class="topbar">
      <div class="brand"><span class="brand-mark">🎤</span> SpeakUP English</div>
      <div class="topbar-right">
        <div class="lang-switch topbar-variant" id="lang-switch-app"></div>
        <button class="admin-link hidden" id="btn-open-admin" data-i18n="admin_open">👥 пользователи</button>
        <div class="user-chip"><span class="dot"></span><span id="chip-name">—</span></div>
        <button class="logout-link" id="btn-logout" data-i18n="logout">выйти</button>
      </div>
    </div>

    <!-- ---------- DASHBOARD ---------- -->
    <div id="screen-dashboard">
      <div class="dash-header">
        <div class="passport-hero">
          <div class="eyebrow" data-i18n="hero_eyebrow">Языковой профиль</div>
          <h2 id="hero-greeting">Добро пожаловать!</h2>
          <p data-i18n="hero_desc">Каждый тест — новый и уникальный набор из 20 вопросов. Изучайте темы подробно, слушайте диалоги, тренируйте произношение — и получайте разбор результатов от ИИ.</p>
          <div class="stat-row">
            <div class="stat"><div class="num" id="stat-tests">0</div><div class="label" data-i18n="stat_tests">тестов пройдено</div></div>
            <div class="stat"><div class="num" id="stat-avg">—</div><div class="label" data-i18n="stat_avg">средний результат</div></div>
            <div class="stat"><div class="num" id="stat-topics">0</div><div class="label" data-i18n="stat_topics">тем затронуто</div></div>
            <div class="stat"><div class="num" id="stat-streak">0</div><div class="label" data-i18n="stat_streak">дней подряд</div></div>
          </div>
        </div>
        <div class="card stamps-card">
          <h3 data-i18n="stamps_title">Штампы прогресса</h3>
          <p class="hint" data-i18n="stamps_hint">Каждый завершённый тест — новый штамп</p>
          <div class="stamps-scroll" id="stamps-scroll">
            <div class="stamps-empty" data-i18n="stamps_empty">Пока пусто — пройдите первый тест!</div>
          </div>
        </div>
      </div>

      <div class="section-title"><h3 data-i18n="topics_title">Темы: грамматика и лексика</h3><span id="topics-count-label">10 тем</span></div>
      <div class="topic-grid" id="topic-grid"></div>

      <div class="section-title"><h3 data-i18n="av_title">Аудирование и говорение</h3><span data-i18n="av_sub">практика вживую</span></div>
      <div class="two-col">
        <div class="card feature-card">
          <div class="icon-lg">🎧</div>
          <h4 data-i18n="listening_card_title">Listening — аудирование</h4>
          <p data-i18n="listening_card_desc">ИИ озвучивает диалоги и короткие тексты вслух (синтез речи браузера), с разной скоростью и уровнем сложности. Слушайте и отвечайте на вопросы по содержанию — набор фрагментов каждый раз новый.</p>
          <button class="btn btn-dark" id="btn-start-listening" data-i18n="listening_card_btn">Начать аудирование →</button>
        </div>
        <div class="card feature-card">
          <div class="icon-lg">🎤</div>
          <h4 data-i18n="speaking_card_title">Speaking — говорение</h4>
          <p data-i18n="speaking_card_desc">Произносите фразы вслух в микрофон — распознавание речи браузера сравнит сказанное с эталоном и оценит точность произношения и попадание в текст.</p>
          <button class="btn btn-dark" id="btn-start-speaking" data-i18n="speaking_card_btn">Начать говорение →</button>
        </div>
      </div>

      <div class="section-title"><h3 data-i18n="history_title">История результатов</h3><span id="history-count">0 записей</span></div>
      <div class="card" style="padding:8px 0;" id="history-card">
        <div id="history-list" style="padding:6px 20px 14px;"></div>
      </div>
    </div>

    <!-- ---------- EXPLAIN (подробное объяснение темы) ---------- -->
    <div id="screen-explain" class="hidden">
      <div class="test-wrap">
        <div class="card" style="padding:32px 30px;">
          <div class="level-tag" id="explain-level">A2 · GRAMMAR</div>
          <h2 id="explain-title" style="margin:0 0 14px;font-size:26px;">Тема</h2>
          <p id="explain-rule" style="font-size:15px;line-height:1.7;color:var(--ink-soft);margin:0 0 18px;"></p>
          <ul id="explain-points" style="margin:0 0 20px;padding-left:20px;line-height:1.8;font-size:14.5px;color:var(--ink);"></ul>
          <div id="explain-examples" style="display:flex;flex-direction:column;gap:8px;margin-bottom:26px;"></div>
          <div style="display:flex;gap:12px;flex-wrap:wrap;">
            <button class="btn btn-primary" id="btn-explain-start" style="width:auto;" data-i18n="start_test_btn">Пройти тест по теме (20 вопросов) →</button>
            <button class="btn btn-outline" id="btn-explain-back" style="width:auto;" data-i18n="back_dash_btn">В кабинет</button>
          </div>
        </div>
      </div>
    </div>

    <!-- ---------- TEST (грамматика/лексика) ---------- -->
    <div id="screen-test" class="hidden">
      <div class="test-wrap">
        <div class="progress-info">
          <span id="test-topic-label">ТЕМА</span>
          <span id="test-progress-label">Вопрос 1 / 20</span>
        </div>
        <div class="progress-track"><div class="progress-fill" id="test-progress-fill" style="width:5%"></div></div>
        <div class="card question-card">
          <div class="q-eyebrow" id="q-eyebrow">Выберите правильный вариант</div>
          <p class="q-text" id="q-text">—</p>
          <div class="options" id="q-options"></div>
        </div>
        <div class="test-footer">
          <button class="exit-link" id="btn-exit-test" data-i18n="exit_no_save">← Выйти без сохранения</button>
          <button class="btn btn-primary hidden" id="btn-next-question" style="width:auto;" data-i18n="next_btn">Далее →</button>
        </div>
      </div>
    </div>

    <!-- ---------- RESULTS ---------- -->
    <div id="screen-results" class="hidden">
      <div class="results-wrap">
        <div class="card score-card">
          <div class="score-ring" id="score-ring" style="--pct:0;">
            <div class="val" id="score-value">0/20</div>
            <div class="sub" data-i18n="score_sub">верных ответов</div>
          </div>
          <h2 class="score-title" id="score-title">Тест завершён</h2>
          <p class="score-topic" id="score-topic">Тема</p>

          <div class="ai-feedback" id="ai-feedback">
            <div class="ai-tag"><span class="ai-dot"></span> <span data-i18n="ai_tag">Разбор от ИИ-преподавателя</span></div>
            <div id="ai-feedback-text">Формируем персональный разбор результата…</div>
          </div>

          <div class="review-list" id="review-list"></div>

          <div class="results-actions">
            <button class="btn btn-primary" id="btn-retry-topic" style="width:auto;" data-i18n="retry_btn">🔁 Пройти новый тест по теме</button>
            <button class="btn btn-outline" id="btn-back-dash" style="width:auto;" data-i18n="back_dash_btn">В кабинет</button>
          </div>
        </div>
      </div>
    </div>

    <!-- ---------- LISTENING SCREEN ---------- -->
    <div id="screen-listening" class="hidden">
      <div class="test-wrap">
        <div class="progress-info">
          <span data-i18n="listening_label">АУДИРОВАНИЕ</span>
          <span id="listen-progress-label">Фрагмент 1 / 10</span>
        </div>
        <div class="progress-track"><div class="progress-fill" id="listen-progress-fill" style="width:10%"></div></div>
        <div class="card listen-card">
          <div class="speed-row" id="speed-row"></div>
          <button class="audio-btn" id="btn-play-audio">🔊</button>
          <div class="replay-row">
            <button class="small-link" id="btn-replay-audio" data-i18n="replay_btn">▶ прослушать ещё раз</button>
            <button class="small-link" id="btn-show-transcript" data-i18n="transcript_btn">показать текст</button>
          </div>
          <div class="transcript-box" id="listen-transcript"></div>
          <p class="q-text" id="listen-question" style="text-align:left;">—</p>
          <div class="options" id="listen-options"></div>
        </div>
        <div class="test-footer">
          <button class="exit-link" id="btn-exit-listening" data-i18n="exit_no_save">← Выйти без сохранения</button>
          <button class="btn btn-primary hidden" id="btn-next-listen" style="width:auto;" data-i18n="next_btn">Далее →</button>
        </div>
      </div>
    </div>

    <!-- ---------- SPEAKING SCREEN ---------- -->
    <div id="screen-speaking" class="hidden">
      <div class="test-wrap">
        <div class="progress-info">
          <span data-i18n="speaking_label">ГОВОРЕНИЕ</span>
          <span id="speak-progress-label">Фраза 1 / 12</span>
        </div>
        <div class="progress-track"><div class="progress-fill" id="speak-progress-fill" style="width:8%"></div></div>
        <div class="card speak-card">
          <div id="speak-unsupported" class="unsupported-note hidden" data-i18n="speak_unsupported">
            Ваш браузер не поддерживает распознавание речи (Web Speech API). Эта функция лучше всего работает в Google Chrome на компьютере или Android. Вы можете продолжить и просто потренировать произношение вслух — но автоматическая проверка будет недоступна.
          </div>
          <div class="phrase-box">
            <div class="ru" id="speak-ru">перевод</div>
            <div class="en" id="speak-en">Phrase to say</div>
          </div>
          <button class="mic-hear-btn" id="btn-hear-phrase" data-i18n="hear_phrase_btn">🔊 услышать образец</button>
          <br>
          <button class="mic-btn" id="btn-mic">🎤</button>
          <div class="mic-status" id="mic-status" data-i18n="mic_status_default">Нажмите на микрофон и произнесите фразу</div>
          <div class="speak-result" id="speak-result">
            <div class="said"><span data-i18n="you_said">Вы сказали:</span> <span id="speak-said">—</span></div>
            <div class="match-bar-track"><div class="match-bar-fill" id="speak-match-fill" style="width:0%"></div></div>
            <div id="speak-match-text" style="color:var(--ink-soft);"></div>
          </div>
        </div>
        <div class="test-footer">
          <button class="exit-link" id="btn-exit-speaking" data-i18n="exit_no_save">← Выйти без сохранения</button>
          <button class="btn btn-primary hidden" id="btn-next-speak" style="width:auto;" data-i18n="next_phrase_btn">Следующая фраза →</button>
        </div>
      </div>
    </div>

  </div>
</div>

<div class="toast" id="toast"></div>

<script>
/* ==========================================================================
   WORDPORT — ENGINE
   ========================================================================== */

/* ---------------------------- УТИЛИТЫ ---------------------------------- */
function rnd(n){ return Math.floor(Math.random()*n); }
function pick(arr){ return arr[rnd(arr.length)]; }
function shuffle(arr){
  const a = arr.slice();
  for(let i=a.length-1;i>0;i--){
    const j = rnd(i+1);
    [a[i],a[j]] = [a[j],a[i]];
  }
  return a;
}
function pickN(arr, n){ return shuffle(arr).slice(0, Math.min(n, arr.length)); }
function uniqueOptions(correct, pool, count){
  // собирает count вариантов, включая correct, без повторов
  const set = new Set([correct]);
  const shuffledPool = shuffle(pool);
  for(const item of shuffledPool){
    if(set.size >= count) break;
    set.add(item);
  }
  return shuffle(Array.from(set));
}
function showToast(msg){
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'), 2600);
}
function escapeHtml(str){
  return String(str).replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}

/* ==========================================================================
   ИНТЕРФЕЙС НА 4 ЯЗЫКАХ: EN / RU / UZ (Oʻzbekcha) / TJ (Тоҷикӣ)
   ========================================================================== */
const LANGS = [
  {code:'ru', label:'RU'},
  {code:'en', label:'EN'},
  {code:'uz', label:'UZ'},
  {code:'tj', label:'TJ'}
];
const TR = {
  ru:{
    login_sub:"Персональный кабинет для изучения английского. Создайте аккаунт с логином и паролем — и мы сохраним ваш профиль с историей тестов, темами и разбором результатов от ИИ.",
    tab_login:"Вход", tab_register:"Регистрация",
    login_name_label:"Имя пользователя", login_name_ph:"Например, aziz", login_btn:"Войти в кабинет →",
    login_pass_label:"Пароль", login_pass_ph:"Минимум 4 символа",
    login_pass2_label:"Повторите пароль", login_pass2_ph:"Ещё раз пароль",
    pw_show:"показать", pw_hide:"скрыть",
    login_note:"Логин и пароль сохраняются в защищённом хранилище (пароль хешируется и никогда не хранится открытым текстом). При следующем визите с любого устройства войдите с теми же данными — кабинет будет там же, где вы его оставили.",
    logout:"выйти",
    err_name_short:"Имя пользователя — минимум 3 символа (латиница/цифры).",
    err_pass_short:"Пароль должен быть не короче 4 символов.",
    err_pass_mismatch:"Пароли не совпадают.",
    err_user_exists:"Пользователь с таким именем уже зарегистрирован.",
    err_user_notfound:"Такого пользователя не существует. Нажмите «Регистрация».",
    err_wrong_pass:"Неверный пароль.",
    admin_open:"👥 пользователи", admin_title:"Пользователи платформы", admin_back:"← в кабинет",
    admin_col_user:"Пользователь", admin_col_joined:"Регистрация", admin_col_tests:"Тестов", admin_col_avg:"Средний балл",
    hero_eyebrow:"Языковой профиль", hero_desc:"Каждый тест — новый и уникальный набор из 20 вопросов. Изучайте темы подробно, слушайте диалоги, тренируйте произношение — и получайте разбор результатов от ИИ.",
    stat_tests:"тестов пройдено", stat_avg:"средний результат", stat_topics:"тем затронуто", stat_streak:"дней подряд",
    stamps_title:"Штампы прогресса", stamps_hint:"Каждый завершённый тест — новый штамп", stamps_empty:"Пока пусто — пройдите первый тест!",
    topics_title:"Темы: грамматика и лексика", av_title:"Аудирование и говорение", av_sub:"практика вживую",
    listening_card_title:"Listening — аудирование", listening_card_desc:"ИИ озвучивает диалоги и короткие тексты вслух (синтез речи браузера), с разной скоростью и уровнем сложности. Слушайте и отвечайте на вопросы по содержанию — набор фрагментов каждый раз новый.", listening_card_btn:"Начать аудирование →",
    speaking_card_title:"Speaking — говорение", speaking_card_desc:"Произносите фразы вслух в микрофон — распознавание речи браузера сравнит сказанное с эталоном и оценит точность произношения и попадание в текст.", speaking_card_btn:"Начать говорение →",
    history_title:"История результатов",
    exit_no_save:"← Выйти без сохранения", next_btn:"Далее →", next_phrase_btn:"Следующая фраза →",
    score_sub:"верных ответов", ai_tag:"Разбор от ИИ-преподавателя", retry_btn:"🔁 Пройти новый тест по теме", back_dash_btn:"В кабинет",
    listening_label:"АУДИРОВАНИЕ", speaking_label:"ГОВОРЕНИЕ",
    replay_btn:"▶ прослушать ещё раз", transcript_btn:"показать текст",
    hear_phrase_btn:"🔊 услышать образец",
    speak_unsupported:"Ваш браузер не поддерживает распознавание речи (Web Speech API). Эта функция лучше всего работает в последней версии Google Chrome на компьютере или Android, и требует разрешения на использование микрофона. Вы можете продолжить и просто потренировать произношение вслух — но автоматическая проверка будет недоступна.",
    mic_status_default:"Нажмите на микрофон и произнесите фразу", you_said:"Вы сказали:",
    mic_status_listening:"Слушаю… говорите сейчас",
    mic_status_denied:"Доступ к микрофону запрещён. Разрешите доступ в настройках браузера и попробуйте снова.",
    mic_status_noresult:"Речь не распознана. Попробуйте произнести фразу чётче и ближе к микрофону.",
    mic_status_error:"Ошибка распознавания речи. Проверьте подключение к интернету и попробуйте снова.",
    mic_status_ready:"Готово! Можете попробовать ещё раз или продолжить",
    start_test_btn:"Пройти тест по теме (20 вопросов) →",
    attempts_short:"попыт.", best_badge:"лучший",
    study_topic_btn:"Изучить тему →",
    empty_history:"История пуста. Пройдите тест, аудирование или тренировку говорения — результат появится здесь.",
    lang_note:"Язык интерфейса", topics_word:"тем", records_word:"записей"
  },
  en:{
    login_sub:"Your personal English learning dashboard. Create an account with a username and password and we'll keep your profile, test history, topics and AI feedback.",
    tab_login:"Log in", tab_register:"Register",
    login_name_label:"Username", login_name_ph:"e.g. aziz", login_btn:"Enter my dashboard →",
    login_pass_label:"Password", login_pass_ph:"At least 4 characters",
    login_pass2_label:"Confirm password", login_pass2_ph:"Type your password again",
    pw_show:"show", pw_hide:"hide",
    login_note:"Your username and password are saved in secure storage (the password is hashed and never stored as plain text). Next time, from any device, log in with the same details — your dashboard will be exactly as you left it.",
    logout:"log out",
    err_name_short:"Username must be at least 3 characters (letters/numbers).",
    err_pass_short:"Password must be at least 4 characters.",
    err_pass_mismatch:"Passwords do not match.",
    err_user_exists:"This username is already taken.",
    err_user_notfound:"No such user. Tap \"Register\" to create an account.",
    err_wrong_pass:"Incorrect password.",
    admin_open:"👥 users", admin_title:"Platform users", admin_back:"← back to dashboard",
    admin_col_user:"User", admin_col_joined:"Joined", admin_col_tests:"Tests", admin_col_avg:"Avg score",
    hero_eyebrow:"Language profile", hero_desc:"Every test is a brand-new set of 20 questions. Study each topic in detail, listen to dialogues, practice pronunciation — and get AI feedback after every attempt.",
    stat_tests:"tests taken", stat_avg:"average score", stat_topics:"topics tried", stat_streak:"day streak",
    stamps_title:"Progress stamps", stamps_hint:"Every finished test adds a new stamp", stamps_empty:"Nothing yet — complete your first test!",
    topics_title:"Topics: grammar & vocabulary", av_title:"Listening & Speaking", av_sub:"live practice",
    listening_card_title:"Listening", listening_card_desc:"Dialogues and short texts are read aloud (browser speech synthesis), with adjustable speed and difficulty. Listen and answer comprehension questions — a fresh set every time.", listening_card_btn:"Start listening →",
    speaking_card_title:"Speaking", speaking_card_desc:"Say phrases out loud into your microphone — browser speech recognition compares what you said to the target phrase and scores your accuracy.", speaking_card_btn:"Start speaking →",
    history_title:"Result history",
    exit_no_save:"← Exit without saving", next_btn:"Next →", next_phrase_btn:"Next phrase →",
    score_sub:"correct answers", ai_tag:"AI teacher feedback", retry_btn:"🔁 Take a new test on this topic", back_dash_btn:"Back to dashboard",
    listening_label:"LISTENING", speaking_label:"SPEAKING",
    replay_btn:"▶ play again", transcript_btn:"show transcript",
    hear_phrase_btn:"🔊 hear the sample",
    speak_unsupported:"Your browser doesn't support speech recognition (Web Speech API). This works best in the latest Google Chrome on desktop or Android, and requires microphone permission. You can still practice speaking out loud, but automatic scoring won't be available.",
    mic_status_default:"Tap the microphone and say the phrase", you_said:"You said:",
    mic_status_listening:"Listening… speak now",
    mic_status_denied:"Microphone access denied. Please allow microphone access in your browser settings and try again.",
    mic_status_noresult:"Couldn't recognize your speech. Try speaking more clearly, closer to the microphone.",
    mic_status_error:"Speech recognition error. Check your internet connection and try again.",
    mic_status_ready:"Done! Try again or move on",
    start_test_btn:"Take the topic test (20 questions) →",
    attempts_short:"tries", best_badge:"best",
    study_topic_btn:"Study this topic →",
    empty_history:"No history yet. Take a test, listening or speaking practice — results will show up here.",
    lang_note:"Interface language", topics_word:"topics", records_word:"records"
  },
  uz:{
    login_sub:"Ingliz tilini o'rganish uchun shaxsiy kabinet. Login va parol bilan hisob yarating — biz profilingizni, testlar tarixini va AI tahlilini saqlaymiz.",
    login_name_label:"Foydalanuvchi nomi", login_name_ph:"Masalan, aziz", login_btn:"Kabinetga kirish →",
    login_pass_label:"Parol", login_pass_ph:"Kamida 4 belgi",
    login_pass2_label:"Parolni takrorlang", login_pass2_ph:"Parolni yana kiriting",
    logout:"chiqish",
    hero_eyebrow:"Til profili", hero_desc:"Har bir test — 20 ta savoldan iborat yangi va o'ziga xos to'plam. Mavzularni batafsil o'rganing, dialoglarni tinglang, talaffuzni mashq qiling — va AI dan natijalar tahlilini oling.",
    stat_tests:"testlar topshirildi", stat_avg:"o'rtacha natija", stat_topics:"mavzular o'rganildi", stat_streak:"kun ketma-ket",
    stamps_title:"Muvaffaqiyat shtamplari", stamps_hint:"Har bir yakunlangan test — yangi shtamp", stamps_empty:"Hozircha bo'sh — birinchi testni topshiring!",
    topics_title:"Mavzular: grammatika va lug'at", av_title:"Tinglash va gapirish", av_sub:"jonli mashq",
    listening_card_title:"Listening — tinglab tushunish", listening_card_desc:"Dialoglar va qisqa matnlar ovoz chiqarib o'qiladi (brauzer nutq sintezi), tezlik va qiyinlik darajasi moslashtiriladi. Tinglang va savollarga javob bering — har safar yangi to'plam.", listening_card_btn:"Tinglashni boshlash →",
    speaking_card_title:"Speaking — gapirish", speaking_card_desc:"Iboralarni mikrofonga ovoz chiqarib ayting — brauzer nutqni tanish tizimi aytilgan so'zlarni namuna bilan solishtirib, aniqligini baholaydi.", speaking_card_btn:"Gapirishni boshlash →",
    history_title:"Natijalar tarixi",
    exit_no_save:"← Saqlamasdan chiqish", next_btn:"Keyingisi →", next_phrase_btn:"Keyingi ibora →",
    score_sub:"to'g'ri javoblar", ai_tag:"AI o'qituvchi tahlili", retry_btn:"🔁 Mavzu bo'yicha yangi test", back_dash_btn:"Kabinetga qaytish",
    listening_label:"TINGLASH", speaking_label:"GAPIRISH",
    replay_btn:"▶ yana tinglash", transcript_btn:"matnni ko'rsatish",
    speak_unsupported:"Brauzeringiz nutqni tanishni (Web Speech API) qo'llab-quvvatlamaydi. Bu funksiya Google Chrome brauzerida (kompyuter yoki Android) yaxshi ishlaydi va mikrofonga ruxsat talab qiladi. Siz baribir talaffuzni mashq qilishingiz mumkin, lekin avtomatik baholash mavjud bo'lmaydi.",
    mic_status_default:"Mikrofonni bosing va iborani talaffuz qiling", you_said:"Siz aytdingiz:",
    start_test_btn:"Mavzu bo'yicha testni boshlash (20 savol) →",
    attempts_short:"urinish", best_badge:"eng yaxshi",
    study_topic_btn:"Mavzuni o'rganish →",
    empty_history:"Tarix hali bo'sh. Test, tinglash yoki gapirish mashqini bajaring — natija shu yerda ko'rinadi.",
    lang_note:"Interfeys tili", topics_word:"mavzu", records_word:"yozuv"
  },
  tj:{
    login_sub:"Кабинети шахсӣ барои омӯзиши забони англисӣ. Ҳисоберо бо логин ва парол созед — мо профил, таърихи тестҳо ва таҳлили ИИ-ро нигоҳ медорем.",
    login_name_label:"Номи корбар", login_name_ph:"Масалан, aziz", login_btn:"Ворид шудан ба кабинет →",
    login_pass_label:"Парол", login_pass_ph:"Ҳадди ақал 4 аломат",
    login_pass2_label:"Паролро такрор кунед", login_pass2_ph:"Боз як бор парол",
    logout:"баромадан",
    hero_eyebrow:"Профили забонӣ", hero_desc:"Ҳар тест — маҷмӯи нав аз 20 савол. Мавзӯъҳоро муфассал омӯзед, диалогҳоро гӯш кунед, талаффузро машқ кунед — ва аз ИИ таҳлили натиҷаҳоро гиред.",
    stat_tests:"тестҳо гузаронида шуд", stat_avg:"натиҷаи миёна", stat_topics:"мавзӯъҳо фаро гирифта шуд", stat_streak:"рӯзи паиҳам",
    stamps_title:"Мӯҳрҳои пешравӣ", stamps_hint:"Ҳар тести анҷомёфта — мӯҳри нав", stamps_empty:"Ҳоло холист — аввалин тестро гузаронед!",
    topics_title:"Мавзӯъҳо: грамматика ва луғат", av_title:"Гӯш кардан ва гуфтугӯ", av_sub:"машқи зинда",
    listening_card_title:"Listening — гӯш кардан", listening_card_desc:"Диалогҳо ва матнҳои кӯтоҳ бо овоз хонда мешаванд (синтези нутқи браузер), бо суръат ва сатҳи гуногун. Гӯш кунед ва ба саволҳо ҷавоб диҳед — ҳар дафъа маҷмӯи нав.", listening_card_btn:"Гӯш карданро сар кунед →",
    speaking_card_title:"Speaking — гуфтугӯ", speaking_card_desc:"Ибораҳоро бо овоз ба микрофон гӯед — системаи шинохти нутқи браузер гуфтаи шуморо бо намуна муқоиса карда, дурустиро баҳо медиҳад.", speaking_card_btn:"Гуфтугӯро сар кунед →",
    history_title:"Таърихи натиҷаҳо",
    exit_no_save:"← Бе сабт баромадан", next_btn:"Баъдӣ →", next_phrase_btn:"Ибораи навбатӣ →",
    score_sub:"ҷавобҳои дуруст", ai_tag:"Таҳлили муаллими ИИ", retry_btn:"🔁 Тести нав аз рӯи мавзӯъ", back_dash_btn:"Ба кабинет",
    listening_label:"ГӮШ КАРДАН", speaking_label:"ГУФТУГӮ",
    replay_btn:"▶ дубора гӯш кунед", transcript_btn:"матнро нишон диҳед",
    speak_unsupported:"Браузери шумо шинохти нутқро (Web Speech API) дастгирӣ намекунад. Ин функсия дар Google Chrome (компютер ё Android) беҳтарин кор мекунад ва иҷозати микрофонро талаб мекунад. Шумо метавонед талаффузро машқ кунед, аммо санҷиши худкор дастрас нахоҳад буд.",
    mic_status_default:"Микрофонро пахш кунед ва ибораро талаффуз кунед", you_said:"Шумо гуфтед:",
    start_test_btn:"Тестро аз рӯи мавзӯъ сар кунед (20 савол) →",
    attempts_short:"кӯшиш", best_badge:"беҳтарин",
    study_topic_btn:"Омӯхтани мавзӯъ →",
    empty_history:"Таърих ҳанӯз холист. Тест, гӯш кардан ё гуфтугӯро иҷро кунед — натиҷа дар ин ҷо пайдо мешавад.",
    lang_note:"Забони интерфейс", topics_word:"мавзӯъ", records_word:"сабт"
  }
};
function t2(key){
  const dict = TR[App.lang] || TR.ru;
  return dict[key] !== undefined ? dict[key] : (TR.ru[key] || key);
}
function applyI18n(){
  document.documentElement.lang = App.lang;
  document.querySelectorAll('[data-i18n]').forEach(el=>{
    el.textContent = t2(el.getAttribute('data-i18n'));
  });
  document.querySelectorAll('[data-i18n-placeholder]').forEach(el=>{
    el.setAttribute('placeholder', t2(el.getAttribute('data-i18n-placeholder')));
  });
  renderLangSwitch();
}
function renderLangSwitch(){
  const html = LANGS.map(l=>`<button class="${App.lang===l.code?'active':''}" data-lang="${l.code}">${l.label}</button>`).join('');
  ['lang-switch-login','lang-switch-app'].forEach(id=>{
    const wrap = document.getElementById(id);
    if(!wrap) return;
    wrap.innerHTML = html;
    wrap.querySelectorAll('button').forEach(btn=>{
      btn.addEventListener('click', async ()=>{
        App.lang = btn.getAttribute('data-lang');
        try{ await window.storage.set('lang', App.lang, false); }catch(e){}
        applyI18n();
        if(App.profile){ renderDashboard(); }
      });
    });
  });
}

/* ---------------------------- ДАННЫЕ: ГЛАГОЛЫ --------------------------- */
const VERBS = [
  {base:"work", s:"works", ing:"working", past:"worked"},
  {base:"play", s:"plays", ing:"playing", past:"played"},
  {base:"study", s:"studies", ing:"studying", past:"studied"},
  {base:"go", s:"goes", ing:"going", past:"went"},
  {base:"do", s:"does", ing:"doing", past:"did"},
  {base:"have", s:"has", ing:"having", past:"had"},
  {base:"watch", s:"watches", ing:"watching", past:"watched"},
  {base:"read", s:"reads", ing:"reading", past:"read"},
  {base:"write", s:"writes", ing:"writing", past:"wrote"},
  {base:"eat", s:"eats", ing:"eating", past:"ate"},
  {base:"drink", s:"drinks", ing:"drinking", past:"drank"},
  {base:"speak", s:"speaks", ing:"speaking", past:"spoke"},
  {base:"see", s:"sees", ing:"seeing", past:"saw"},
  {base:"buy", s:"buys", ing:"buying", past:"bought"},
  {base:"make", s:"makes", ing:"making", past:"made"},
  {base:"take", s:"takes", ing:"taking", past:"took"},
  {base:"give", s:"gives", ing:"giving", past:"gave"},
  {base:"cook", s:"cooks", ing:"cooking", past:"cooked"},
  {base:"clean", s:"cleans", ing:"cleaning", past:"cleaned"},
  {base:"travel", s:"travels", ing:"travelling", past:"travelled"},
  {base:"visit", s:"visits", ing:"visiting", past:"visited"},
  {base:"finish", s:"finishes", ing:"finishing", past:"finished"},
  {base:"start", s:"starts", ing:"starting", past:"started"},
  {base:"live", s:"lives", ing:"living", past:"lived"},
  {base:"drive", s:"drives", ing:"driving", past:"drove"},
  {base:"call", s:"calls", ing:"calling", past:"called"},
  {base:"help", s:"helps", ing:"helping", past:"helped"},
  {base:"open", s:"opens", ing:"opening", past:"opened"},
  {base:"close", s:"closes", ing:"closing", past:"closed"},
  {base:"walk", s:"walks", ing:"walking", past:"walked"}
];
const PP = {go:"gone",do:"done",have:"had",watch:"watched",read:"read",write:"written",eat:"eaten",drink:"drunk",speak:"spoken",see:"seen",buy:"bought",make:"made",take:"taken",give:"given",cook:"cooked",clean:"cleaned",travel:"travelled",visit:"visited",finish:"finished",start:"started",live:"lived",drive:"driven",call:"called",help:"helped",open:"opened",close:"closed",walk:"walked",work:"worked",play:"played",study:"studied",sell:"sold",build:"built",check:"checked",paint:"painted"};

const SUBJECTS = ["I","You","He","She","It","We","They","My friend","The children","Our teacher","My parents","The dog"];
function isThirdSingular(subj){ return ["He","She","It","My friend","Our teacher","The dog"].includes(subj); }
function auxBe(subj){
  if(subj==="I") return "am";
  if(isThirdSingular(subj)) return "is";
  return "are";
}
function auxHave(subj){ return isThirdSingular(subj) ? "has" : "have"; }

/* ---------------------------- ГЕНЕРАТОРЫ ГРАММАТИКИ --------------------- */

function genPresentSimple(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const time = pick(["every day","every morning","every week","on Mondays","usually","often","every year","at the weekend","every summer","most days"]);
  const correct = isThirdSingular(subj) ? v.s : v.base;
  const wrongPool = [v.base===correct?null:v.base, v.s===correct?null:v.s, v.ing, v.past].filter(Boolean);
  const options = uniqueOptions(correct, wrongPool, 4);
  return {
    eyebrow:"Present Simple",
    text:`${subj} ___ (${v.base}) ${time}.`,
    options, correct
  };
}
function genPresentContinuous(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const time = pick(["right now","at the moment","now","currently","at this moment"]);
  const correctAux = auxBe(subj);
  const correct = `${correctAux} ${v.ing}`;
  const otherAux = ["am","is","are"].filter(a=>a!==correctAux);
  const wrongPool = [
    `${otherAux[0]} ${v.ing}`,
    `${otherAux[1]} ${v.ing}`,
    v.base,
    v.past
  ];
  const options = uniqueOptions(correct, wrongPool, 4);
  return {
    eyebrow:"Present Continuous",
    text:`${subj} ___ (${v.base}) ${time}.`,
    options, correct
  };
}
function genPastSimple(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const time = pick(["yesterday","last week","two days ago","last night","last summer","in 2019","a moment ago","last month"]);
  const correct = v.past;
  const wrongPool = [v.base, v.s, v.ing];
  const options = uniqueOptions(correct, wrongPool, 4);
  return {
    eyebrow:"Past Simple",
    text:`${subj} ___ (${v.base}) ${time}.`,
    options, correct
  };
}
function genPresentPerfect(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const marker = pick(["already","just","never","yet","for three years","since 2015","recently","many times"]);
  const correctAux = auxHave(subj);
  const pp = PP[v.base] || v.past;
  const correct = `${correctAux} ${pp}`;
  const otherAux = ["have","has"].filter(a=>a!==correctAux)[0];
  const wrongPool = [`${otherAux} ${pp}`, v.past, v.base];
  const options = uniqueOptions(correct, wrongPool, 4);
  return {
    eyebrow:"Present Perfect",
    text:`${subj} ___ (${v.base}) ${marker}.`,
    options, correct
  };
}
const ARTICLE_NOUNS = [
  {n:"apple", cat:"vowel"}, {n:"orange", cat:"vowel"}, {n:"umbrella", cat:"vowel"},
  {n:"hour", cat:"vowel"}, {n:"idea", cat:"vowel"}, {n:"elephant", cat:"vowel"}, {n:"office", cat:"vowel"},
  {n:"book", cat:"cons"}, {n:"car", cat:"cons"}, {n:"dog", cat:"cons"}, {n:"university", cat:"cons"},
  {n:"house", cat:"cons"}, {n:"student", cat:"cons"}, {n:"teacher", cat:"cons"}, {n:"laptop", cat:"cons"},
  {n:"water", cat:"unc"}, {n:"music", cat:"unc"}, {n:"information", cat:"unc"}, {n:"advice", cat:"unc"}, {n:"rice", cat:"unc"}, {n:"money", cat:"unc"},
  {n:"sun", cat:"uniq"}, {n:"moon", cat:"uniq"}, {n:"internet", cat:"uniq"}, {n:"sky", cat:"uniq"}
];
function genArticles(){
  const item = pick(ARTICLE_NOUNS);
  const templates = {
    vowel: `I saw ___ ${item.n} in the shop.`,
    cons: `She bought ___ ${item.n} yesterday.`,
    unc: `Can I have ___ ${item.n}, please?`,
    uniq: `Look at ___ ${item.n} tonight.`
  };
  const answerMap = {vowel:"an", cons:"a", unc:"no article", uniq:"the"};
  const correct = answerMap[item.cat];
  const allOptions = ["a","an","the","no article"];
  return {
    eyebrow:"Articles: a / an / the",
    text: templates[item.cat],
    options: shuffle(allOptions),
    correct
  };
}
const PREP_SCENARIOS = [
  {t:"The cat is ___ the box.", c:"in"},
  {t:"The book is ___ the table.", c:"on"},
  {t:"We met ___ the corner of the street.", c:"at"},
  {t:"The picture is ___ the wall.", c:"on"},
  {t:"She is standing ___ the door.", c:"at"},
  {t:"The ball rolled ___ the bed.", c:"under"},
  {t:"He arrived ___ 8 o'clock.", c:"at"},
  {t:"My birthday is ___ July.", c:"in"},
  {t:"The meeting is ___ Monday.", c:"on"},
  {t:"There is a bridge ___ the river.", c:"over"},
  {t:"The shop is ___ the bank and the cafe.", c:"between"},
  {t:"We arrived ___ the airport early.", c:"at"},
  {t:"She lives ___ Paris.", c:"in"},
  {t:"He was born ___ 1995.", c:"in"},
  {t:"The plane flew ___ the clouds.", c:"above"},
  {t:"Put the vase ___ the shelf.", c:"on"},
  {t:"The dog is hiding ___ the sofa.", c:"behind"},
  {t:"I'll see you ___ the morning.", c:"in"},
  {t:"The store closes ___ midnight.", c:"at"},
  {t:"They walked ___ the park.", c:"through"},
  {t:"The keys are ___ my bag.", c:"in"},
  {t:"We'll meet ___ the weekend.", c:"at"}
];
const PREP_POOL = ["in","on","at","under","over","between","behind","through","above","near","into","from"];
function genPrepositions(){
  const s = pick(PREP_SCENARIOS);
  const wrongPool = PREP_POOL.filter(p=>p!==s.c);
  const options = uniqueOptions(s.c, wrongPool, 4);
  return { eyebrow:"Prepositions", text:s.t, options, correct:s.c };
}
const MODAL_SCENARIOS = [
  {t:"You ___ smoke in the hospital. It's forbidden.", c:"mustn't"},
  {t:"It's cloudy, so it ___ rain later.", c:"might"},
  {t:"___ you help me with this bag, please?", c:"Can"},
  {t:"Students ___ wear a uniform at this school. It's a rule.", c:"must"},
  {t:"You look tired. You ___ go to bed early.", c:"should"},
  {t:"___ I open the window? It's hot in here.", c:"May"},
  {t:"She ___ speak three languages fluently.", c:"can"},
  {t:"We ___ finish the report by Friday, it's the deadline.", c:"must"},
  {t:"You don't have to come, but you ___ if you want.", c:"can"},
  {t:"He ___ be at home now, I saw his car outside.", c:"must"},
  {t:"You ___ eat more vegetables, it's good for your health.", c:"should"},
  {t:"___ I borrow your pen for a second?", c:"Could"},
  {t:"They ___ arrive late, the traffic is terrible today.", c:"might"},
  {t:"You ___ touch that, it's very hot!", c:"mustn't"},
  {t:"When I was young, I ___ climb trees very fast.", c:"could"},
  {t:"You ___ apologize, it wasn't your fault at all.", c:"don't have to"}
];
const MODAL_POOL = ["can","could","must","mustn't","should","might","may","have to","don't have to","Can","May","Could"];
function genModals(){
  const s = pick(MODAL_SCENARIOS);
  const wrongPool = MODAL_POOL.filter(m=>m.toLowerCase()!==s.c.toLowerCase());
  const options = uniqueOptions(s.c, wrongPool, 4);
  return { eyebrow:"Modal Verbs", text:s.t, options, correct:s.c };
}
const ADJS = [
  {b:"big",c:"bigger",s:"biggest"},{b:"small",c:"smaller",s:"smallest"},
  {b:"fast",c:"faster",s:"fastest"},{b:"happy",c:"happier",s:"happiest"},
  {b:"easy",c:"easier",s:"easiest"},{b:"beautiful",c:"more beautiful",s:"most beautiful"},
  {b:"expensive",c:"more expensive",s:"most expensive"},{b:"good",c:"better",s:"best"},
  {b:"bad",c:"worse",s:"worst"},{b:"far",c:"farther",s:"farthest"},
  {b:"interesting",c:"more interesting",s:"most interesting"},{b:"hot",c:"hotter",s:"hottest"},
  {b:"cold",c:"colder",s:"coldest"},{b:"tall",c:"taller",s:"tallest"},
  {b:"intelligent",c:"more intelligent",s:"most intelligent"},{b:"cheap",c:"cheaper",s:"cheapest"},
  {b:"difficult",c:"more difficult",s:"most difficult"},{b:"young",c:"younger",s:"youngest"},{b:"old",c:"older",s:"oldest"}
];
function genComparatives(){
  const a = pick(ADJS);
  const isSuper = Math.random()<0.5;
  const correct = isSuper ? a.s : a.c;
  const other = pick(ADJS.filter(x=>x.b!==a.b));
  const wrongPool = isSuper ? [a.c, a.b, other.s] : [a.s, a.b, other.c];
  const options = uniqueOptions(correct, wrongPool, 4);
  const text = isSuper
    ? `This is ${["a","e","i","o","u"].includes(a.s[0])?"the":"the"} ___ (${a.b}) building I have ever seen.`
    : `My car is ___ (${a.b}) than my brother's car.`;
  return { eyebrow: isSuper?"Superlatives":"Comparatives", text, options, correct };
}

function genFutureSimple(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const time = pick(["tomorrow","next week","next year","soon","in two days","next summer","later today","next month"]);
  const correct = `will ${v.base}`;
  const wrongPool = [v.base, v.s, v.past, `will ${v.ing}`];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Future Simple (will)", text:`${subj} ___ (${v.base}) ${time}.`, options, correct };
}
const COND_RESULTS = ["we will stay at home","I will be very happy","she will call you immediately","they will be surprised","we will cancel the trip","he will help you at once","I will buy a new umbrella","we will go to the beach"];
function genConditional(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const result = pick(COND_RESULTS);
  const correct = isThirdSingular(subj) ? v.s : v.base;
  const wrongPool = [v.past, v.ing, `will ${v.base}`];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"First Conditional (if)", text:`If ${subj} ___ (${v.base}) tomorrow, ${result}.`, options, correct };
}
const PASSIVE_ITEMS = [
  {subj:"The letter", plural:false, base:"write", pp:"written", ing:"writing"},
  {subj:"These cars", plural:true, base:"make", pp:"made", ing:"making"},
  {subj:"The house", plural:false, base:"clean", pp:"cleaned", ing:"cleaning"},
  {subj:"The windows", plural:true, base:"open", pp:"opened", ing:"opening"},
  {subj:"Breakfast", plural:false, base:"cook", pp:"cooked", ing:"cooking"},
  {subj:"The books", plural:true, base:"sell", pp:"sold", ing:"selling"},
  {subj:"The bridge", plural:false, base:"build", pp:"built", ing:"building"},
  {subj:"The reports", plural:true, base:"check", pp:"checked", ing:"checking"},
  {subj:"The room", plural:false, base:"paint", pp:"painted", ing:"painting"},
  {subj:"The tickets", plural:true, base:"buy", pp:"bought", ing:"buying"}
];
function genPassive(){
  const item = pick(PASSIVE_ITEMS);
  const correctAux = item.plural ? "are" : "is";
  const wrongAux = item.plural ? "is" : "are";
  const correct = `${correctAux} ${item.pp}`;
  const wrongPool = [`${wrongAux} ${item.pp}`, item.base, item.ing];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Passive Voice", text:`${item.subj} ___ (${item.base}) every day.`, options, correct };
}
const QUESTION_PAIRS = [
  {v:"like", o:"coffee"}, {v:"play", o:"football on Sundays"}, {v:"live", o:"in London"},
  {v:"speak", o:"French"}, {v:"work", o:"in a bank"}, {v:"have", o:"a car"},
  {v:"study", o:"at university"}, {v:"watch", o:"TV every evening"}, {v:"read", o:"the news"},
  {v:"drink", o:"tea"}, {v:"go", o:"to the gym"}, {v:"cook", o:"dinner"}
];
function genQuestions(){
  const subj = pick(SUBJECTS);
  const pair = pick(QUESTION_PAIRS);
  const correct = isThirdSingular(subj) ? "Does" : "Do";
  const options = shuffle(["Do","Does","Is","Are"]);
  return { eyebrow:"Questions with Do / Does", text:`___ ${subj} ${pair.v} ${pair.o}?`, options, correct };
}
const QUANT_SCENARIOS = [
  {t:"There isn't ___ milk in the fridge.", c:"any"},
  {t:"I have ___ good friends in this city.", c:"many"},
  {t:"Would you like ___ tea?", c:"some"},
  {t:"How ___ money do you have?", c:"much"},
  {t:"There are ___ books on the shelf.", c:"many"},
  {t:"She doesn't have ___ time today.", c:"any"},
  {t:"We need ___ sugar for the cake.", c:"some"},
  {t:"How ___ apples did you buy?", c:"many"},
  {t:"There is ___ water left in the bottle.", c:"some"},
  {t:"I don't have ___ questions right now.", c:"any"},
  {t:"He drinks ___ coffee every day.", c:"a lot of"},
  {t:"Are there ___ eggs in the basket?", c:"any"}
];
const QUANT_POOL = ["some","any","much","many","a lot of","a few"];
function genQuantifiers(){
  const s = pick(QUANT_SCENARIOS);
  const wrongPool = QUANT_POOL.filter(q=>q!==s.c);
  const options = uniqueOptions(s.c, wrongPool, 4);
  return { eyebrow:"Some / Any / Much / Many", text:s.t, options, correct:s.c };
}
const POSS_PAIRS = [
  {owner:"Peter", obj:"car"}, {owner:"Maria", obj:"phone"}, {owner:"the teacher", obj:"book"},
  {owner:"my sister", obj:"bag"}, {owner:"the children", obj:"toys"}, {owner:"John", obj:"house"},
  {owner:"my parents", obj:"car"}, {owner:"the dog", obj:"food"}, {owner:"Anna", obj:"laptop"},
  {owner:"my brother", obj:"bicycle"}
];
function genPossessive(){
  const p = pick(POSS_PAIRS);
  const ownerCap = p.owner.charAt(0).toUpperCase()+p.owner.slice(1);
  const correct = `${ownerCap}'s ${p.obj}`;
  const wrongPool = [`${p.obj} of ${p.owner}`, `${ownerCap} ${p.obj}'s`, `${p.obj}'s ${p.owner}`];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Possessive Case", text:`How do you correctly say: "the ${p.obj} that belongs to ${p.owner}"?`, options, correct };
}

const PHRASAL_VERBS = [
  {p:"give up", m:"прекратить попытки, сдаться"},
  {p:"look after", m:"заботиться о ком-то"},
  {p:"look for", m:"искать что-то"},
  {p:"turn on", m:"включить"},
  {p:"turn off", m:"выключить"},
  {p:"put off", m:"откладывать"},
  {p:"pick up", m:"забрать, поднять"},
  {p:"break down", m:"сломаться (о технике)"},
  {p:"come across", m:"случайно встретить или найти"},
  {p:"figure out", m:"разобраться, понять"},
  {p:"get along with", m:"ладить с кем-то"},
  {p:"run out of", m:"у чего-то заканчивается запас"},
  {p:"take off", m:"взлетать / снимать одежду"},
  {p:"check in", m:"регистрироваться в отеле или аэропорту"},
  {p:"check out", m:"выписываться из отеля"},
  {p:"look up", m:"искать информацию в словаре или интернете"},
  {p:"set up", m:"устанавливать, организовывать"},
  {p:"call off", m:"отменять"},
  {p:"carry on", m:"продолжать"},
  {p:"fill out", m:"заполнять форму"},
  {p:"get over", m:"оправиться от чего-то"},
  {p:"hang out", m:"проводить время с кем-то"},
  {p:"hold on", m:"подождать"},
  {p:"keep up with", m:"не отставать от чего-то"},
  {p:"make up", m:"придумывать или мириться"},
  {p:"point out", m:"указывать на что-то"},
  {p:"put up with", m:"мириться с чем-то неприятным"},
  {p:"run into", m:"случайно встретить"},
  {p:"show up", m:"появиться, прийти"},
  {p:"switch off", m:"выключать"},
  {p:"take after", m:"быть похожим на родственника"},
  {p:"work out", m:"тренироваться или срабатывать"},
  {p:"bring up", m:"воспитывать или поднимать тему"},
  {p:"come up with", m:"придумать идею"},
  {p:"drop off", m:"подвезти и высадить кого-то"},
  {p:"end up", m:"в итоге оказаться где-то"},
  {p:"go on", m:"продолжаться, происходить"},
  {p:"leave out", m:"пропустить, не включить"},
  {p:"stand for", m:"означать (об аббревиатуре)"},
  {p:"take over", m:"взять на себя управление"}
];
function genPhrasalVerb(){
  const item = pick(PHRASAL_VERBS);
  const wrongPool = PHRASAL_VERBS.filter(x=>x.p!==item.p).map(x=>x.m);
  const options = uniqueOptions(item.m, wrongPool, 4);
  return { eyebrow:"Phrasal Verbs", text:`Что означает фразовый глагол «${item.p}»?`, options, correct:item.m };
}

const VOCAB_BANK = [
  {w:"boarding pass", m:"посадочный талон"},
  {w:"luggage", m:"багаж"},
  {w:"departure", m:"вылет, отправление"},
  {w:"arrival", m:"прибытие"},
  {w:"customs", m:"таможня"},
  {w:"passport control", m:"паспортный контроль"},
  {w:"itinerary", m:"маршрут поездки"},
  {w:"accommodation", m:"жильё, размещение"},
  {w:"fare", m:"стоимость проезда"},
  {w:"platform", m:"платформа на вокзале"},
  {w:"jet lag", m:"усталость от смены часовых поясов"},
  {w:"souvenir", m:"сувенир"},
  {w:"currency exchange", m:"обмен валюты"},
  {w:"round trip", m:"поездка туда и обратно"},
  {w:"layover", m:"пересадка в аэропорту"},
  {w:"appetizer", m:"закуска"},
  {w:"main course", m:"основное блюдо"},
  {w:"dessert", m:"десерт"},
  {w:"leftovers", m:"остатки еды"},
  {w:"recipe", m:"рецепт"},
  {w:"ingredient", m:"ингредиент"},
  {w:"to roast", m:"жарить или запекать в духовке"},
  {w:"to boil", m:"варить"},
  {w:"to chop", m:"нарезать"},
  {w:"to season", m:"приправлять"},
  {w:"flavor", m:"вкус, аромат"},
  {w:"tasty", m:"вкусный"},
  {w:"bland", m:"безвкусный"},
  {w:"spicy", m:"острый (о еде)"},
  {w:"sightseeing", m:"осмотр достопримечательностей"},
  {w:"guided tour", m:"экскурсия с гидом"},
  {w:"reservation", m:"бронирование"},
  {w:"check-in time", m:"время заселения"},
  {w:"local cuisine", m:"местная кухня"},
  {w:"budget traveler", m:"путешественник с ограниченным бюджетом"}
];
function genVocab(){
  const item = pick(VOCAB_BANK);
  const wrongPool = VOCAB_BANK.filter(x=>x.w!==item.w).map(x=>x.m);
  const options = uniqueOptions(item.m, wrongPool, 4);
  return { eyebrow:"Vocabulary: Travel & Food", text:`Что означает слово «${item.w}»?`, options, correct:item.m };
}

/* ---------------------------- ДОПОЛНИТЕЛЬНЫЕ ТЕМЫ ------------------------ */
const PAST_CONT_SCENARIOS = [
  {subj:"I", v:"read", time:"when the phone rang"},
  {subj:"She", v:"cook", time:"when I arrived"},
  {subj:"They", v:"play", time:"all afternoon yesterday"},
  {subj:"We", v:"walk", time:"when it started to rain"},
  {subj:"He", v:"work", time:"at 9pm last night"},
  {subj:"The children", v:"sleep", time:"when we came home"},
  {subj:"I", v:"drive", time:"when I saw the accident"},
  {subj:"She", v:"study", time:"the whole evening"},
  {subj:"We", v:"watch", time:"a movie when the power went out"},
  {subj:"He", v:"talk", time:"on the phone for an hour"},
  {subj:"They", v:"wait", time:"for the bus when it began to snow"},
  {subj:"I", v:"write", time:"an email when my boss called"}
];
function genPastContinuous(){
  const s = pick(PAST_CONT_SCENARIOS);
  const v = VERBS.find(x=>x.base===s.v) || pick(VERBS);
  const correctAux = isThirdSingular(s.subj) ? "was" : (s.subj==="I" ? "was" : "were");
  const correct = `${correctAux} ${v.ing}`;
  const otherAux = correctAux === "was" ? "were" : "was";
  const wrongPool = [`${otherAux} ${v.ing}`, v.base, v.past];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Past Continuous", text:`${s.subj} ___ (${v.base}) ${s.time}.`, options, correct };
}

function genPresentPerfectContinuous(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const marker = pick(["for two hours","since morning","all day","for a week","since 8am","for the last few days"]);
  const correctAux = isThirdSingular(subj) ? "has been" : "have been";
  const correct = `${correctAux} ${v.ing}`;
  const wrongAux = correctAux === "has been" ? "have been" : "has been";
  const wrongPool = [`${wrongAux} ${v.ing}`, v.past, v.base];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Present Perfect Continuous", text:`${subj} ___ (${v.base}) ${marker}.`, options, correct };
}

const PAST_PERFECT_SCENARIOS = [
  {t:"When I arrived, the film ___ (start) already.", v:"start"},
  {t:"She ___ (finish) her homework before dinner.", v:"finish"},
  {t:"They ___ (leave) by the time we got there.", v:"leave"},
  {t:"He was tired because he ___ (work) all day.", v:"work"},
  {t:"We ___ (never see) snow before that winter.", v:"see"},
  {t:"By the time I woke up, everyone ___ (go).", v:"go"},
  {t:"I ___ (already eat) when she invited me to lunch.", v:"eat"},
  {t:"The train ___ (leave) before we reached the station.", v:"leave"}
];
const PAST_PERFECT_PP = {start:"started",finish:"finished",leave:"left",work:"worked",see:"seen",go:"gone",eat:"eaten"};
function genPastPerfect(){
  const s = pick(PAST_PERFECT_SCENARIOS);
  const pp = PAST_PERFECT_PP[s.v];
  const correct = `had ${pp}`;
  const wrongPool = [`have ${pp}`, `has ${pp}`, pp];
  const options = uniqueOptions(correct, wrongPool, 4);
  const text = s.t.replace(/___ \([a-z ]+\)/, "___");
  return { eyebrow:"Past Perfect", text, options, correct };
}

const COND2_RESULTS = ["I would travel around the world","she would be much happier","we would buy a bigger house","he would help you immediately","they would move to another city","I would learn a new language","we would live by the sea"];
function genSecondConditional(){
  const subj = pick(SUBJECTS);
  const v = pick(VERBS);
  const result = pick(COND2_RESULTS);
  const correct = v.past;
  const wrongPool = [v.base, `will ${v.base}`, v.ing];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Second Conditional", text:`If ${subj} ___ (${v.base}) more money, ${result}.`, options, correct };
}

const REPORTED_SCENARIOS = [
  {direct:'"I am tired," she said.', correct:"was", wrong:["is","am","be"]},
  {direct:'"I work every day," he said.', correct:"worked", wrong:["works","work","working"]},
  {direct:'"I will call you," she said.', correct:"would", wrong:["will","shall","can"]},
  {direct:'"I have finished," he said.', correct:"had finished", wrong:["has finished","have finished","finished already"]},
  {direct:'"I am reading a book," she said.', correct:"was reading", wrong:["is reading","reads","reading"]},
  {direct:'"I can help you," he said.', correct:"could", wrong:["can","may","must"]},
  {direct:'"I saw him yesterday," she said.', correct:"had seen", wrong:["saw","has seen","sees"]}
];
function genReportedSpeech(){
  const s = pick(REPORTED_SCENARIOS);
  const options = uniqueOptions(s.correct, s.wrong, 4);
  return { eyebrow:"Reported Speech", text:`Direct speech: ${s.direct} Reported: She/He said (that) ___...`, options, correct:s.correct };
}

const GERUND_INF_SCENARIOS = [
  {t:"I enjoy ___ (read) books in the evening.", c:"reading", wrong:["read","to read","reads"]},
  {t:"She wants ___ (learn) French.", c:"to learn", wrong:["learning","learn","learns"]},
  {t:"They finished ___ (eat) dinner.", c:"eating", wrong:["eat","to eat","ate"]},
  {t:"He decided ___ (buy) a new car.", c:"to buy", wrong:["buying","buy","bought"]},
  {t:"We avoid ___ (drive) in the city center.", c:"driving", wrong:["to drive","drive","drove"]},
  {t:"I hope ___ (see) you soon.", c:"to see", wrong:["seeing","see","saw"]},
  {t:"She suggested ___ (go) to the cinema.", c:"going", wrong:["to go","go","went"]},
  {t:"He promised ___ (help) me tomorrow.", c:"to help", wrong:["helping","help","helps"]},
  {t:"I don't mind ___ (wait) a few minutes.", c:"waiting", wrong:["to wait","wait","waited"]}
];
function genGerundInfinitive(){
  const s = pick(GERUND_INF_SCENARIOS);
  const options = uniqueOptions(s.c, s.wrong, 4);
  const text = s.t.replace(/\([a-z]+\)/, "");
  return { eyebrow:"Gerunds & Infinitives", text, options, correct:s.c };
}

const RELATIVE_SCENARIOS = [
  {t:"The man ___ lives next door is a doctor.", c:"who"},
  {t:"This is the book ___ I told you about.", c:"that"},
  {t:"The city ___ we visited last year was beautiful.", c:"which"},
  {t:"That's the house ___ I grew up.", c:"where"},
  {t:"She is the woman ___ car was stolen.", c:"whose"},
  {t:"I know a place ___ we can eat cheaply.", c:"where"},
  {t:"The teacher ___ taught me English moved away.", c:"who"},
  {t:"This is the reason ___ I called you.", c:"why"}
];
const RELATIVE_POOL = ["who","which","that","where","whose","why","when"];
function genRelativeClauses(){
  const s = pick(RELATIVE_SCENARIOS);
  const wrongPool = RELATIVE_POOL.filter(r=>r!==s.c);
  const options = uniqueOptions(s.c, wrongPool, 4);
  return { eyebrow:"Relative Clauses", text:s.t, options, correct:s.c };
}

const USED_TO_SCENARIOS = [
  {subj:"I", v:"play", time:"football every weekend when I was a kid."},
  {subj:"She", v:"live", time:"in Paris before she moved here."},
  {subj:"We", v:"go", time:"to that beach every summer."},
  {subj:"He", v:"smoke", time:"but he quit two years ago."},
  {subj:"They", v:"have", time:"a small shop in the old town."},
  {subj:"I", v:"be", time:"much shyer when I was younger."},
  {subj:"She", v:"walk", time:"to school every day."}
];
function genUsedTo(){
  const s = pick(USED_TO_SCENARIOS);
  const v = s.v === "be" ? "be" : (VERBS.find(x=>x.base===s.v)?.base || s.v);
  const correct = `used to ${v}`;
  const wrongPool = [`use to ${v}`, `${v}ed`, `is used to ${v}`];
  const options = uniqueOptions(correct, wrongPool, 4);
  return { eyebrow:"Used to", text:`${s.subj} ___ (${v}) ${s.time}`, options, correct };
}

const TAG_SCENARIOS = [
  {t:"She is your sister, ___?", c:"isn't she"},
  {t:"They don't live here, ___?", c:"do they"},
  {t:"You can swim, ___?", c:"can't you"},
  {t:"He didn't call you, ___?", c:"did he"},
  {t:"We are late, ___?", c:"aren't we"},
  {t:"You haven't seen this movie, ___?", c:"have you"},
  {t:"She will come tomorrow, ___?", c:"won't she"},
  {t:"It wasn't very expensive, ___?", c:"was it"}
];
const TAG_POOL = ["isn't she","do they","can't you","did he","aren't we","have you","won't she","was it","don't you","is she"];
function genTagQuestions(){
  const s = pick(TAG_SCENARIOS);
  const wrongPool = TAG_POOL.filter(x=>x!==s.c);
  const options = uniqueOptions(s.c, wrongPool, 4);
  return { eyebrow:"Question Tags", text:s.t, options, correct:s.c };
}

const COUNTABLE_NOUNS = [
  {n:"information", type:"unc"}, {n:"advice", type:"unc"}, {n:"furniture", type:"unc"},
  {n:"news", type:"unc"}, {n:"luggage", type:"unc"}, {n:"bread", type:"unc"}, {n:"rice", type:"unc"},
  {n:"apple", type:"c"}, {n:"chair", type:"c"}, {n:"idea", type:"c"}, {n:"suitcase", type:"c"}, {n:"loaf of bread", type:"c"}
];
function genCountableUncountable(){
  const item = pick(COUNTABLE_NOUNS);
  const isUnc = item.type === "unc";
  const correct = isUnc ? "uncountable" : "countable";
  const options = shuffle(["countable","uncountable"]);
  return { eyebrow:"Countable / Uncountable Nouns", text:`Слово «${item.n}» — исчисляемое или неисчисляемое?`, options, correct };
}

/* ---------------------------- ТЕМЫ (TOPICS) ----------------------------- */
const TOPICS = [
  {id:"present_simple", title:"Present Simple", icon:"🕐", desc:"Повседневные действия и привычки.", gen:genPresentSimple},
  {id:"present_continuous", title:"Present Continuous", icon:"⏳", desc:"Действия, происходящие сейчас.", gen:genPresentContinuous},
  {id:"past_simple", title:"Past Simple", icon:"📜", desc:"Завершённые действия в прошлом.", gen:genPastSimple},
  {id:"present_perfect", title:"Present Perfect", icon:"✅", desc:"Связь прошлого с настоящим.", gen:genPresentPerfect},
  {id:"future_simple", title:"Future Simple (will)", icon:"🚀", desc:"Планы, обещания и предсказания.", gen:genFutureSimple},
  {id:"conditional1", title:"First Conditional", icon:"🌦️", desc:"Реальные условия: if + present, will.", gen:genConditional},
  {id:"passive", title:"Passive Voice", icon:"🔄", desc:"Пассивный залог в Present Simple.", gen:genPassive},
  {id:"questions", title:"Questions: Do / Does", icon:"❓", desc:"Построение вопросов в Present Simple.", gen:genQuestions},
  {id:"articles", title:"Articles a/an/the", icon:"🔤", desc:"Артикли в английском языке.", gen:genArticles},
  {id:"prepositions", title:"Prepositions", icon:"📍", desc:"Предлоги места и времени.", gen:genPrepositions},
  {id:"modals", title:"Modal Verbs", icon:"🧭", desc:"Can, must, should, might и другие.", gen:genModals},
  {id:"comparatives", title:"Comparatives & Superlatives", icon:"📈", desc:"Сравнение предметов и людей.", gen:genComparatives},
  {id:"quantifiers", title:"Some / Any / Much / Many", icon:"🔢", desc:"Слова количества в английском.", gen:genQuantifiers},
  {id:"possessive", title:"Possessive Case", icon:"👤", desc:"Притяжательный падеж 's.", gen:genPossessive},
  {id:"phrasal", title:"Phrasal Verbs", icon:"🧩", desc:"Популярные фразовые глаголы.", gen:genPhrasalVerb},
  {id:"vocab_travel", title:"Vocabulary: Travel & Food", icon:"🍽️", desc:"Лексика путешествий и еды.", gen:genVocab},
  {id:"past_continuous", title:"Past Continuous", icon:"🌀", desc:"Действие в процессе в прошлом.", gen:genPastContinuous},
  {id:"present_perfect_continuous", title:"Present Perfect Continuous", icon:"⏱️", desc:"Длительность действия до сейчас.", gen:genPresentPerfectContinuous},
  {id:"past_perfect", title:"Past Perfect", icon:"⏮️", desc:"Действие раньше другого действия в прошлом.", gen:genPastPerfect},
  {id:"conditional2", title:"Second Conditional", icon:"🌙", desc:"Нереальные условия в настоящем/будущем.", gen:genSecondConditional},
  {id:"reported_speech", title:"Reported Speech", icon:"🗨️", desc:"Косвенная речь.", gen:genReportedSpeech},
  {id:"gerund_infinitive", title:"Gerunds & Infinitives", icon:"➰", desc:"Глагол + -ing или to + глагол.", gen:genGerundInfinitive},
  {id:"relative_clauses", title:"Relative Clauses", icon:"🔗", desc:"Придаточные определительные who/which/that.", gen:genRelativeClauses},
  {id:"used_to", title:"Used to", icon:"🕰️", desc:"Привычки и состояния в прошлом.", gen:genUsedTo},
  {id:"tag_questions", title:"Question Tags", icon:"❔", desc:"Разделительные вопросы.", gen:genTagQuestions},
  {id:"countable_uncountable", title:"Countable / Uncountable", icon:"⚖️", desc:"Исчисляемые и неисчисляемые существительные.", gen:genCountableUncountable}
];
function getTopic(id){ return TOPICS.find(t=>t.id===id); }

/* ==========================================================================
   ПОДРОБНЫЕ ОБЪЯСНЕНИЯ ТЕМ НА 4 ЯЗЫКАХ
   ========================================================================== */
const EXPLAIN = {
  present_simple:{
    level:"A1 · GRAMMAR",
    rule:{
      ru:"Present Simple используется для регулярных действий, привычек, фактов и расписаний. К глаголу добавляется -s/-es, если подлежащее — He/She/It (третье лицо единственного числа).",
      en:"Present Simple is used for routines, habits, facts and schedules. Add -s/-es to the verb when the subject is He/She/It (third person singular).",
      uz:"Present Simple doimiy harakatlar, odatlar, faktlar va jadvallar uchun ishlatiladi. Ega He/She/It bo'lsa, fe'lga -s/-es qo'shiladi.",
      tj:"Present Simple барои амалҳои мунтазам, одатҳо, далелҳо ва ҷадвалҳо истифода мешавад. Агар мубтадо He/She/It бошад, ба феъл -s/-es илова карда мешавад."
    },
    points:{
      ru:["I / You / We / They + базовая форма глагола","He / She / It + глагол + -s / -es","Отрицание: don't / doesn't + базовая форма","Маркеры времени: every day, usually, often, always"],
      en:["I / You / We / They + base verb","He / She / It + verb + -s / -es","Negative: don't / doesn't + base verb","Time markers: every day, usually, often, always"],
      uz:["I / You / We / They + fe'lning asosiy shakli","He / She / It + fe'l + -s / -es","Inkor: don't / doesn't + asosiy shakl","Vaqt so'zlari: every day, usually, often, always"],
      tj:["I / You / We / They + шакли асосии феъл","He / She / It + феъл + -s / -es","Инкор: don't / doesn't + шакли асосӣ","Аломатҳои вақт: every day, usually, often, always"]
    },
    examples:[
      {en:"She works in a hospital.", ru:"Она работает в больнице."},
      {en:"They don't like spicy food.", ru:"Они не любят острую еду."},
      {en:"The shop opens at nine every morning.", ru:"Магазин открывается в девять каждое утро."}
    ]
  },
  present_continuous:{
    level:"A1-A2 · GRAMMAR",
    rule:{
      ru:"Present Continuous описывает действия, происходящие прямо сейчас или временные ситуации. Строится по формуле: am/is/are + глагол с окончанием -ing.",
      en:"Present Continuous describes actions happening right now or temporary situations. Formula: am/is/are + verb + -ing.",
      uz:"Present Continuous hozir sodir bo'layotgan yoki vaqtinchalik holatlarni ifodalaydi. Formula: am/is/are + fe'l + -ing.",
      tj:"Present Continuous амалҳое, ки ҳозир рух медиҳанд ё ҳолатҳои муваққатиро тасвир мекунад. Формула: am/is/are + феъл + -ing."
    },
    points:{
      ru:["I am + -ing","He/She/It is + -ing","You/We/They are + -ing","Маркеры: now, right now, at the moment, currently"],
      en:["I am + -ing","He/She/It is + -ing","You/We/They are + -ing","Markers: now, right now, at the moment, currently"],
      uz:["I am + -ing","He/She/It is + -ing","You/We/They are + -ing","Belgilar: now, right now, at the moment, currently"],
      tj:["I am + -ing","He/She/It is + -ing","You/We/They are + -ing","Аломатҳо: now, right now, at the moment, currently"]
    },
    examples:[
      {en:"I am reading an interesting book right now.", ru:"Я сейчас читаю интересную книгу."},
      {en:"She is cooking dinner at the moment.", ru:"Она сейчас готовит ужин."},
      {en:"They are travelling in Europe this month.", ru:"Они путешествуют по Европе в этом месяце."}
    ]
  },
  past_simple:{
    level:"A1-A2 · GRAMMAR",
    rule:{
      ru:"Past Simple используется для завершённых действий в прошлом с указанным временем. У правильных глаголов добавляется -ed, у неправильных — особая форма (go → went).",
      en:"Past Simple is used for completed actions at a specific time in the past. Regular verbs add -ed; irregular verbs have a special form (go → went).",
      uz:"Past Simple o'tmishda ma'lum vaqtda tugallangan harakatlar uchun ishlatiladi. To'g'ri fe'llarga -ed qo'shiladi, noto'g'ri fe'llar maxsus shaklga ega (go → went).",
      tj:"Past Simple барои амалҳои дар вақти муайяни гузашта анҷомёфта истифода мешавад. Ба феълҳои дуруст -ed илова мешавад, феълҳои нодуруст шакли махсус доранд (go → went)."
    },
    points:{
      ru:["Правильные глаголы: verb + -ed","Неправильные глаголы: особая форма (2-я колонка)","Отрицание: didn't + базовая форма","Маркеры: yesterday, last week, in 2020, ago"],
      en:["Regular verbs: verb + -ed","Irregular verbs: special form (2nd column)","Negative: didn't + base verb","Markers: yesterday, last week, in 2020, ago"],
      uz:["To'g'ri fe'llar: verb + -ed","Noto'g'ri fe'llar: maxsus shakl","Inkor: didn't + asosiy shakl","Belgilar: yesterday, last week, in 2020, ago"],
      tj:["Феълҳои дуруст: verb + -ed","Феълҳои нодуруст: шакли махсус","Инкор: didn't + шакли асосӣ","Аломатҳо: yesterday, last week, in 2020, ago"]
    },
    examples:[
      {en:"We visited our grandparents last weekend.", ru:"Мы навестили бабушку с дедушкой на прошлых выходных."},
      {en:"She didn't call me yesterday.", ru:"Она не позвонила мне вчера."},
      {en:"He went to Paris in 2019.", ru:"Он ездил в Париж в 2019 году."}
    ]
  },
  present_perfect:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"Present Perfect связывает прошлое с настоящим: результат важнее, чем точное время действия. Формула: have/has + причастие прошедшего времени (participle).",
      en:"Present Perfect connects the past with the present: the result matters more than the exact time. Formula: have/has + past participle.",
      uz:"Present Perfect o'tmishni hozirgi zamon bilan bog'laydi: aniq vaqtdan ko'ra natija muhimroq. Formula: have/has + past participle.",
      tj:"Present Perfect гузаштаро бо ҳозира мепайвандад: натиҷа муҳимтар аз вақти дақиқ аст. Формула: have/has + past participle."
    },
    points:{
      ru:["I/You/We/They + have + participle","He/She/It + has + participle","Маркеры: already, just, never, yet, ever, since, for","Не используется с точным указанием времени (yesterday, in 2020)"],
      en:["I/You/We/They + have + participle","He/She/It + has + participle","Markers: already, just, never, yet, ever, since, for","Not used with a specific past time (yesterday, in 2020)"],
      uz:["I/You/We/They + have + participle","He/She/It + has + participle","Belgilar: already, just, never, yet, ever, since, for","Aniq vaqt bilan ishlatilmaydi (yesterday, in 2020)"],
      tj:["I/You/We/They + have + participle","He/She/It + has + participle","Аломатҳо: already, just, never, yet, ever, since, for","Бо вақти дақиқ истифода намешавад (yesterday, in 2020)"]
    },
    examples:[
      {en:"I have already finished my homework.", ru:"Я уже закончил домашнее задание."},
      {en:"She has never been to Japan.", ru:"Она никогда не была в Японии."},
      {en:"We have lived here for ten years.", ru:"Мы живём здесь уже десять лет."}
    ]
  },
  future_simple:{
    level:"A2 · GRAMMAR",
    rule:{
      ru:"Future Simple выражает решения, принятые в момент речи, обещания и предсказания. Формула: will + базовая форма глагола, одинаковая для всех подлежащих.",
      en:"Future Simple expresses spontaneous decisions, promises and predictions. Formula: will + base verb, the same for every subject.",
      uz:"Future Simple gapirish paytida qabul qilingan qarorlar, va'dalar va bashoratlarni ifodalaydi. Formula: will + fe'lning asosiy shakli.",
      tj:"Future Simple қарорҳои дар лаҳзаи гуфтугӯ қабулшуда, ваъдаҳо ва пешгӯиҳоро ифода мекунад. Формула: will + шакли асосии феъл."
    },
    points:{
      ru:["Формула одинакова для всех: will + базовая форма","Отрицание: won't (will not) + базовая форма","Маркеры: tomorrow, next week, soon, in two days","Используется для обещаний: I will help you."],
      en:["Same formula for everyone: will + base verb","Negative: won't (will not) + base verb","Markers: tomorrow, next week, soon, in two days","Used for promises: I will help you."],
      uz:["Barcha uchun bir xil formula: will + asosiy shakl","Inkor: won't (will not) + asosiy shakl","Belgilar: tomorrow, next week, soon, in two days","Va'dalar uchun: I will help you."],
      tj:["Формулаи ягона барои ҳама: will + шакли асосӣ","Инкор: won't (will not) + шакли асосӣ","Аломатҳо: tomorrow, next week, soon, in two days","Барои ваъдаҳо: I will help you."]
    },
    examples:[
      {en:"I will call you tomorrow.", ru:"Я позвоню тебе завтра."},
      {en:"It will probably rain later.", ru:"Возможно, позже пойдёт дождь."},
      {en:"We will help you with the project.", ru:"Мы поможем тебе с проектом."}
    ]
  },
  conditional1:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"First Conditional описывает реальные и возможные условия в будущем. Формула: If + Present Simple, ... will + базовая форма глагола.",
      en:"First Conditional describes real, possible conditions in the future. Formula: If + Present Simple, ... will + base verb.",
      uz:"First Conditional kelajakda real va mumkin bo'lgan shartlarni tasvirlaydi. Formula: If + Present Simple, ... will + asosiy shakl.",
      tj:"First Conditional шартҳои воқеӣ ва имконпазирро дар оянда тасвир мекунад. Формула: If + Present Simple, ... will + шакли асосӣ."
    },
    points:{
      ru:["Условие (if-часть) всегда в Present Simple, не в will","Результат — в Future Simple (will + base)","Можно менять части местами: We will stay home if it rains.","Используется для реальных, вероятных ситуаций"],
      en:["The if-clause is always in Present Simple, never with will","The result clause uses Future Simple (will + base)","Clauses can be reversed: We will stay home if it rains.","Used for real, likely situations"],
      uz:["If-qism doimo Present Simple'da, will bilan emas","Natija qismi Future Simple (will + asosiy shakl)","Qismlarni almashtirish mumkin: We will stay home if it rains.","Real, ehtimoli baland vaziyatlar uchun"],
      tj:["Қисми if ҳамеша дар Present Simple аст, на бо will","Қисми натиҷа дар Future Simple (will + шакли асосӣ)","Қисмҳоро иваз кардан мумкин: We will stay home if it rains.","Барои вазъиятҳои воқеӣ ва эҳтимолӣ истифода мешавад"]
    },
    examples:[
      {en:"If it rains tomorrow, we will stay at home.", ru:"Если завтра пойдёт дождь, мы останемся дома."},
      {en:"If she studies hard, she will pass the exam.", ru:"Если она будет усердно учиться, она сдаст экзамен."},
      {en:"If you call me, I will explain everything.", ru:"Если ты мне позвонишь, я всё объясню."}
    ]
  },
  passive:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"Пассивный залог используется, когда важнее действие или объект, чем тот, кто его выполняет. Формула для Present Simple: is/are + причастие прошедшего времени (participle).",
      en:"The passive voice is used when the action or the object matters more than who does it. Present Simple formula: is/are + past participle.",
      uz:"Passiv nisbat harakat yoki obyekt kim tomonidan bajarilganidan muhimroq bo'lganda ishlatiladi. Present Simple formulasi: is/are + past participle.",
      tj:"Овози пассивӣ вақте истифода мешавад, ки амал ё объект муҳимтар аз иҷрокунанда аст. Формулаи Present Simple: is/are + past participle."
    },
    points:{
      ru:["Единственное число: is + participle","Множественное число: are + participle","Исполнитель действия можно указать через by: written by her","Часто используется в новостях, инструкциях, официальных текстах"],
      en:["Singular: is + participle","Plural: are + participle","The doer can be added with by: written by her","Common in news, instructions and formal texts"],
      uz:["Birlik: is + participle","Ko'plik: are + participle","Bajaruvchini by bilan qo'shish mumkin: written by her","Yangiliklar, yo'riqnomalar va rasmiy matnlarda ko'p ishlatiladi"],
      tj:["Танҳо: is + participle","Ҷамъ: are + participle","Иҷрокунандаро бо by илова кардан мумкин: written by her","Дар хабарҳо, дастурҳо ва матнҳои расмӣ бисёр истифода мешавад"]
    },
    examples:[
      {en:"The letter is written by hand.", ru:"Письмо написано от руки."},
      {en:"These cars are made in Germany.", ru:"Эти машины произведены в Германии."},
      {en:"Breakfast is cooked every morning.", ru:"Завтрак готовится каждое утро."}
    ]
  },
  questions:{
    level:"A1 · GRAMMAR",
    rule:{
      ru:"Вопросы в Present Simple строятся с помощью вспомогательных глаголов Do и Does. Does используется с He/She/It, Do — со всеми остальными подлежащими.",
      en:"Questions in Present Simple are formed with the auxiliary verbs Do and Does. Does is used with He/She/It, Do with all other subjects.",
      uz:"Present Simple'da savollar Do va Does yordamchi fe'llari bilan tuziladi. Does He/She/It bilan, Do esa boshqa barcha egalar bilan ishlatiladi.",
      tj:"Саволҳо дар Present Simple бо ёрии феълҳои ёрирасон Do ва Does сохта мешаванд. Does бо He/She/It, Do бо ҳамаи дигар мубтадоҳо истифода мешавад."
    },
    points:{
      ru:["Do/Does + подлежащее + базовая форма глагола + ?","После Do/Does глагол НЕ получает -s","Краткий ответ: Yes, he does. / No, they don't.","Порядок слов: вспомогательный глагол всегда первый"],
      en:["Do/Does + subject + base verb + ?","The verb never gets -s after Do/Does","Short answer: Yes, he does. / No, they don't.","Word order: the auxiliary verb always comes first"],
      uz:["Do/Does + ega + fe'lning asosiy shakli + ?","Do/Does'dan keyin fe'lga -s qo'shilmaydi","Qisqa javob: Yes, he does. / No, they don't.","So'z tartibi: yordamchi fe'l doim birinchi"],
      tj:["Do/Does + мубтадо + шакли асосии феъл + ?","Пас аз Do/Does ба феъл -s илова намешавад","Ҷавоби кӯтоҳ: Yes, he does. / No, they don't.","Тартиби калимаҳо: феъли ёрирасон ҳамеша аввал меояд"]
    },
    examples:[
      {en:"Does she like coffee?", ru:"Она любит кофе?"},
      {en:"Do they live in London?", ru:"Они живут в Лондоне?"},
      {en:"Does he work in a bank?", ru:"Он работает в банке?"}
    ]
  },
  articles:{
    level:"A1-A2 · GRAMMAR",
    rule:{
      ru:"Артикль a/an ставится перед исчисляемым существительным в единственном числе при первом упоминании; the — когда предмет уже известен или уникален; перед неисчисляемыми существительными в общем смысле артикль не нужен.",
      en:"A/an goes before a singular countable noun mentioned for the first time; the is used when the thing is already known or unique; no article is needed before uncountable nouns used in a general sense.",
      uz:"A/an birinchi marta tilga olinayotgan birlikdagi sanaladigan ot oldiga qo'yiladi; the narsa allaqachon ma'lum yoki noyob bo'lganda ishlatiladi; sanalmaydigan otlar oldida umumiy ma'noda artikl kerak emas.",
      tj:"A/an пеш аз исми ҳисобшавандаи танҳо, ки бори аввал зикр мешавад, гузошта мешавад; the вақте истифода мешавад, ки чиз аллакай маълум ё беназир аст; пеш аз исмҳои ношумурдашаванда дар маънои умумӣ артикл лозим нест."
    },
    points:{
      ru:["a — перед словом на согласный звук (a book)","an — перед словом на гласный звук (an apple)","the — уникальные объекты, повторное упоминание (the sun, the Internet)","Нулевой артикль — неисчисляемые в общем смысле (water, music)"],
      en:["a — before a consonant sound (a book)","an — before a vowel sound (an apple)","the — unique objects, repeated mention (the sun, the Internet)","No article — uncountables in general (water, music)"],
      uz:["a — undosh tovush oldida (a book)","an — unli tovush oldida (an apple)","the — noyob narsalar, qayta eslatish (the sun, the Internet)","Artiklsiz — sanalmaydiganlar umumiy ma'noda (water, music)"],
      tj:["a — пеш аз садои ҳамсадо (a book)","an — пеш аз садои садонок (an apple)","the — объектҳои беназир, зикри такрорӣ (the sun, the Internet)","Бе артикл — исмҳои ношумурдашаванда умуман (water, music)"]
    },
    examples:[
      {en:"I saw an elephant at the zoo.", ru:"Я видел слона в зоопарке."},
      {en:"She bought a book yesterday.", ru:"Она купила книгу вчера."},
      {en:"Look at the moon tonight.", ru:"Посмотри сегодня на луну."}
    ]
  },
  prepositions:{
    level:"A1-A2 · GRAMMAR",
    rule:{
      ru:"Предлоги места и времени показывают, где находится предмет или когда происходит действие. In используется для месяцев/лет и «внутри», on — для дней и поверхностей, at — для точного времени и точек.",
      en:"Prepositions of place and time show where something is or when something happens. In is used for months/years and 'inside', on for days and surfaces, at for exact times and points.",
      uz:"O'rin va vaqt predloglari narsa qayerda joylashganini yoki harakat qachon sodir bo'lishini ko'rsatadi. In oylar/yillar va 'ichida' uchun, on kunlar va yuzalar uchun, at aniq vaqt va nuqtalar uchun ishlatiladi.",
      tj:"Пешояндҳои макон ва вақт нишон медиҳанд, ки чиз дар куҷост ё амал кай рух медиҳад. In барои моҳҳо/солҳо ва 'дар дохил', on барои рӯзҳои ва сатҳҳо, at барои вақти дақиқ ва нуқтаҳо истифода мешавад."
    },
    points:{
      ru:["in — месяцы, годы, внутри чего-то (in July, in the box)","on — дни недели, поверхности (on Monday, on the table)","at — точное время, точки (at 8 o'clock, at the door)","under/over/between/behind — относительное расположение"],
      en:["in — months, years, inside something (in July, in the box)","on — days of the week, surfaces (on Monday, on the table)","at — exact time, points (at 8 o'clock, at the door)","under/over/between/behind — relative position"],
      uz:["in — oylar, yillar, ichida (in July, in the box)","on — hafta kunlari, yuzalar (on Monday, on the table)","at — aniq vaqt, nuqtalar (at 8 o'clock, at the door)","under/over/between/behind — nisbiy joylashuv"],
      tj:["in — моҳҳо, солҳо, дар дохил (in July, in the box)","on — рӯзҳои ҳафта, сатҳҳо (on Monday, on the table)","at — вақти дақиқ, нуқтаҳо (at 8 o'clock, at the door)","under/over/between/behind — ҷойгиршавии нисбӣ"]
    },
    examples:[
      {en:"The meeting is on Monday at nine.", ru:"Встреча в понедельник в девять."},
      {en:"My birthday is in July.", ru:"Мой день рождения в июле."},
      {en:"The shop is between the bank and the cafe.", ru:"Магазин находится между банком и кафе."}
    ]
  },
  modals:{
    level:"A2-B1 · GRAMMAR",
    rule:{
      ru:"Модальные глаголы выражают возможность, обязанность, разрешение или совет. После модального глагола всегда идёт базовая форма смыслового глагола без to.",
      en:"Modal verbs express ability, obligation, permission or advice. A modal verb is always followed by the base form of the main verb, without to.",
      uz:"Modal fe'llar imkoniyat, majburiyat, ruxsat yoki maslahatni ifodalaydi. Modal fe'ldan keyin doim asosiy fe'lning to'siz shakli keladi.",
      tj:"Феълҳои модалӣ имконият, ӯҳдадорӣ, иҷозат ё маслиҳатро ифода мекунанд. Пас аз феъли модалӣ ҳамеша шакли асосии феъли асосӣ бе to меояд."
    },
    points:{
      ru:["must/have to — обязанность, mustn't — запрет","should — совет, рекомендация","can/could — возможность, умение, просьба","might/may — вероятность, разрешение"],
      en:["must/have to — obligation, mustn't — prohibition","should — advice, recommendation","can/could — ability, permission, requests","might/may — possibility, permission"],
      uz:["must/have to — majburiyat, mustn't — taqiq","should — maslahat, tavsiya","can/could — imkoniyat, ruxsat, iltimos","might/may — ehtimollik, ruxsat"],
      tj:["must/have to — ӯҳдадорӣ, mustn't — манъ","should — маслиҳат, тавсия","can/could — қобилият, иҷозат, дархост","might/may — эҳтимолият, иҷозат"]
    },
    examples:[
      {en:"You mustn't smoke here.", ru:"Здесь нельзя курить."},
      {en:"You should drink more water.", ru:"Тебе стоит пить больше воды."},
      {en:"It might rain later.", ru:"Возможно, позже пойдёт дождь."}
    ]
  },
  comparatives:{
    level:"A2 · GRAMMAR",
    rule:{
      ru:"Сравнительная степень (comparative) сравнивает два предмета, превосходная (superlative) выделяет один предмет среди многих. Короткие прилагательные получают -er/-est, длинные — more/most.",
      en:"The comparative form compares two things; the superlative singles out one thing among many. Short adjectives take -er/-est, longer ones take more/most.",
      uz:"Qiyosiy daraja (comparative) ikkita narsani solishtiradi, orttirma daraja (superlative) esa ko'plar orasidan bittasini ajratadi. Qisqa sifatlar -er/-est, uzun sifatlar more/most oladi.",
      tj:"Дараҷаи муқоисавӣ (comparative) ду чизро муқоиса мекунад, дараҷаи олӣ (superlative) якеро аз бисёрҳо ҷудо мекунад. Сифатҳои кӯтоҳ -er/-est, дарозҳо more/most мегиранд."
    },
    points:{
      ru:["Короткие прилагательные: big → bigger → the biggest","Длинные прилагательные: more beautiful → the most beautiful","Сравнение: than (This is bigger than that)","Исключения: good → better → best, bad → worse → worst"],
      en:["Short adjectives: big → bigger → the biggest","Longer adjectives: more beautiful → the most beautiful","Comparison word: than (This is bigger than that)","Irregulars: good → better → best, bad → worse → worst"],
      uz:["Qisqa sifatlar: big → bigger → the biggest","Uzun sifatlar: more beautiful → the most beautiful","Solishtirish so'zi: than (This is bigger than that)","Istisnolar: good → better → best, bad → worse → worst"],
      tj:["Сифатҳои кӯтоҳ: big → bigger → the biggest","Сифатҳои дароз: more beautiful → the most beautiful","Калимаи муқоиса: than (This is bigger than that)","Истисноҳо: good → better → best, bad → worse → worst"]
    },
    examples:[
      {en:"My car is faster than his car.", ru:"Моя машина быстрее, чем его."},
      {en:"This is the most interesting book I've read.", ru:"Это самая интересная книга, которую я читал."},
      {en:"Today is colder than yesterday.", ru:"Сегодня холоднее, чем вчера."}
    ]
  },
  quantifiers:{
    level:"A2 · GRAMMAR",
    rule:{
      ru:"Some/any/much/many показывают количество. Some — в утверждениях, any — в вопросах и отрицаниях, much — с неисчисляемыми, many — с исчисляемыми существительными во множественном числе.",
      en:"Some/any/much/many show quantity. Some is used in affirmative sentences, any in questions and negatives, much with uncountable nouns, many with plural countable nouns.",
      uz:"Some/any/much/many miqdorni ko'rsatadi. Some — tasdiq gaplarda, any — savol va inkorlarda, much — sanalmaydiganlar bilan, many — ko'plikdagi sanaladiganlar bilan.",
      tj:"Some/any/much/many миқдорро нишон медиҳанд. Some — дар ҷумлаҳои тасдиқӣ, any — дар саволу инкор, much — бо исмҳои ношумурдашаванда, many — бо исмҳои ҷамъи ҳисобшаванда."
    },
    points:{
      ru:["some — утверждения: I have some money.","any — вопросы/отрицания: Do you have any money?","much — неисчисляемые: much water","many — исчисляемые во мн.ч.: many books"],
      en:["some — affirmatives: I have some money.","any — questions/negatives: Do you have any money?","much — uncountables: much water","many — plural countables: many books"],
      uz:["some — tasdiq: I have some money.","any — savol/inkor: Do you have any money?","much — sanalmaydigan: much water","many — ko'plik: many books"],
      tj:["some — тасдиқ: I have some money.","any — савол/инкор: Do you have any money?","much — ношумурдашаванда: much water","many — ҷамъи ҳисобшаванда: many books"]
    },
    examples:[
      {en:"There isn't any milk in the fridge.", ru:"В холодильнике нет молока."},
      {en:"I have many good friends here.", ru:"У меня здесь много хороших друзей."},
      {en:"Would you like some tea?", ru:"Хочешь чаю?"}
    ]
  },
  possessive:{
    level:"A1-A2 · GRAMMAR",
    rule:{
      ru:"Притяжательный падеж 's показывает принадлежность и используется, в основном, с людьми и животными: Peter's car. Для неодушевлённых предметов чаще используется конструкция с of.",
      en:"The possessive 's shows ownership and is mainly used with people and animals: Peter's car. For inanimate objects, the of-construction is more common.",
      uz:"Egalik kelishigi 's mansublikni ko'rsatadi va asosan odamlar va hayvonlar bilan ishlatiladi: Peter's car. Jonsiz narsalar uchun ko'proq of konstruksiyasi ishlatiladi.",
      tj:"Ҳолати соҳибӣ 's тааллуқро нишон медиҳад ва асосан бо одамон ва ҳайвонот истифода мешавад: Peter's car. Барои ашёи беҷон бештар сохтори of истифода мешавад."
    },
    points:{
      ru:["Одно лицо: Peter's car","Множественное число на -s: the students' books (апостроф после s)","Неправильное мн.ч.: the children's toys","Неодушевлённые предметы: the door of the house"],
      en:["One person: Peter's car","Plural ending in -s: the students' books (apostrophe after s)","Irregular plural: the children's toys","Inanimate objects: the door of the house"],
      uz:["Bitta shaxs: Peter's car","-s bilan tugagan ko'plik: the students' books (s dan keyin apostrof)","Noto'g'ri ko'plik: the children's toys","Jonsiz narsalar: the door of the house"],
      tj:["Як шахс: Peter's car","Ҷамъи бо -s: the students' books (апостроф пас аз s)","Ҷамъи ғайримунтазам: the children's toys","Ашёи беҷон: the door of the house"]
    },
    examples:[
      {en:"This is Peter's car.", ru:"Это машина Питера."},
      {en:"The children's toys are on the floor.", ru:"Игрушки детей на полу."},
      {en:"The door of the house is blue.", ru:"Дверь дома синяя."}
    ]
  },
  phrasal:{
    level:"B1 · VOCABULARY",
    rule:{
      ru:"Фразовые глаголы — это глагол + предлог/наречие, которые вместе образуют новое значение, часто отличное от значения глагола отдельно. Они очень часто встречаются в разговорной речи.",
      en:"Phrasal verbs are a verb + a preposition/adverb that together create a new meaning, often different from the verb alone. They are very common in everyday spoken English.",
      uz:"Frazaviy fe'llar — fe'l + predlog/ravish, ular birgalikda alohida fe'l ma'nosidan farq qiluvchi yangi ma'no hosil qiladi. Ular kundalik nutqda juda ko'p uchraydi.",
      tj:"Феълҳои фразавӣ — феъл + пешоянд/зарф, ки якҷоя маънои наверо ба вуҷуд меоранд, ки аксар вақт аз маънои феъли алоҳида фарқ мекунад. Онҳо дар нутқи ҳаррӯза хеле маъмуланд."
    },
    points:{
      ru:["Значение часто нельзя угадать по отдельным словам","Многие фразовые глаголы имеют несколько значений","Учите их в контексте предложения, а не по отдельности","Очень распространены в разговорном английском"],
      en:["The meaning often can't be guessed from the individual words","Many phrasal verbs have more than one meaning","Learn them in context, not in isolation","Extremely common in spoken English"],
      uz:["Ma'noni ko'pincha alohida so'zlardan taxmin qilib bo'lmaydi","Ko'p frazaviy fe'llar bir nechta ma'noga ega","Ularni kontekstda o'rganing, alohida emas","Og'zaki nutqda juda keng tarqalgan"],
      tj:["Маъноро аксар вақт аз калимаҳои алоҳида тахмин кардан мумкин нест","Бисёр феълҳои фразавӣ якчанд маъно доранд","Онҳоро дар матн омӯзед, на алоҳида","Дар нутқи гуфтугӯӣ хеле маъмуланд"]
    },
    examples:[
      {en:"I need to look after my little brother tonight.", ru:"Мне нужно присмотреть за младшим братом сегодня вечером."},
      {en:"Please turn off the lights before leaving.", ru:"Пожалуйста, выключи свет перед уходом."},
      {en:"She gave up smoking last year.", ru:"Она бросила курить в прошлом году."}
    ]
  },
  vocab_travel:{
    level:"A2-B1 · VOCABULARY",
    rule:{
      ru:"Лексика путешествий и еды пригодится в аэропорту, отеле, ресторане и во время готовки. Знание этих слов делает поездки и повседневную жизнь намного проще.",
      en:"Travel and food vocabulary is essential at the airport, in a hotel, at a restaurant and while cooking. Knowing these words makes trips and everyday life much easier.",
      uz:"Sayohat va oziq-ovqat lug'ati aeroportda, mehmonxonada, restoranda va ovqat pishirishda kerak bo'ladi. Bu so'zlarni bilish sayohat va kundalik hayotni ancha osonlashtiradi.",
      tj:"Луғати сафар ва хӯрок дар фурудгоҳ, меҳмонхона, тарабхона ва ҳангоми пухтупаз лозим мешавад. Донистани ин калимаҳо сафар ва ҳаёти ҳаррӯзаро хеле осон мекунад."
    },
    points:{
      ru:["Аэропорт и транспорт: boarding pass, layover, round trip","Отель: accommodation, check-in, reservation","Еда: appetizer, main course, dessert, ingredient","Готовка: to roast, to boil, to chop, to season"],
      en:["Airport & transport: boarding pass, layover, round trip","Hotel: accommodation, check-in, reservation","Food: appetizer, main course, dessert, ingredient","Cooking: to roast, to boil, to chop, to season"],
      uz:["Aeroport va transport: boarding pass, layover, round trip","Mehmonxona: accommodation, check-in, reservation","Ovqat: appetizer, main course, dessert, ingredient","Pishirish: to roast, to boil, to chop, to season"],
      tj:["Фурудгоҳ ва нақлиёт: boarding pass, layover, round trip","Меҳмонхона: accommodation, check-in, reservation","Хӯрок: appetizer, main course, dessert, ingredient","Пухтупаз: to roast, to boil, to chop, to season"]
    },
    examples:[
      {en:"Don't forget your boarding pass at the gate.", ru:"Не забудь посадочный талон у выхода."},
      {en:"The soup needs a bit more seasoning.", ru:"Супу нужно немного больше приправ."},
      {en:"We booked our accommodation online.", ru:"Мы забронировали жильё онлайн."}
    ]
  },
  past_continuous:{
    level:"A2 · GRAMMAR",
    rule:{
      ru:"Past Continuous описывает действие в процессе в определённый момент прошлого, часто прерванное другим действием. Формула: was/were + глагол с -ing.",
      en:"Past Continuous describes an action in progress at a specific moment in the past, often interrupted by another action. Formula: was/were + verb-ing."
    },
    points:{
      ru:["I/He/She/It + was + -ing","You/We/They + were + -ing","Часто с Past Simple: was reading when the phone rang","Маркеры: while, when, all evening, at that moment"],
      en:["I/He/She/It + was + -ing","You/We/They + were + -ing","Often paired with Past Simple: was reading when the phone rang","Markers: while, when, all evening, at that moment"]
    },
    examples:[
      {en:"I was reading when the phone rang.", ru:"Я читал, когда зазвонил телефон."},
      {en:"They were playing football all afternoon.", ru:"Они играли в футбол весь день."},
      {en:"She was cooking dinner when I arrived.", ru:"Она готовила ужин, когда я пришёл."}
    ]
  },
  present_perfect_continuous:{
    level:"B1-B2 · GRAMMAR",
    rule:{
      ru:"Present Perfect Continuous подчёркивает длительность действия, которое началось в прошлом и продолжается до сих пор (или только что закончилось). Формула: have/has been + -ing.",
      en:"Present Perfect Continuous emphasizes the duration of an action that started in the past and continues now (or has just stopped). Formula: have/has been + -ing."
    },
    points:{
      ru:["I/You/We/They + have been + -ing","He/She/It + has been + -ing","Маркеры: for, since, all day, lately","Акцент на процессе и длительности, а не результате"],
      en:["I/You/We/They + have been + -ing","He/She/It + has been + -ing","Markers: for, since, all day, lately","Focus on the ongoing process and duration, not the result"]
    },
    examples:[
      {en:"I have been studying English for two years.", ru:"Я изучаю английский уже два года."},
      {en:"She has been working since 8am.", ru:"Она работает с 8 утра."},
      {en:"They have been waiting for an hour.", ru:"Они ждут уже час."}
    ]
  },
  past_perfect:{
    level:"B1-B2 · GRAMMAR",
    rule:{
      ru:"Past Perfect используется для действия, которое произошло раньше другого действия в прошлом. Формула: had + причастие прошедшего времени (participle).",
      en:"Past Perfect is used for an action that happened before another action in the past. Formula: had + past participle."
    },
    points:{
      ru:["Одинаковая форма had для всех подлежащих","Показывает 'прошлое до прошлого'","Часто с before, after, by the time, already","Отрицание: hadn't + participle"],
      en:["Same form had for every subject","Shows 'the past before the past'","Often used with before, after, by the time, already","Negative: hadn't + participle"]
    },
    examples:[
      {en:"When I arrived, the film had already started.", ru:"Когда я пришёл, фильм уже начался."},
      {en:"She had finished her homework before dinner.", ru:"Она закончила домашнее задание до ужина."},
      {en:"They had left by the time we got there.", ru:"Они уже ушли к тому времени, как мы приехали."}
    ]
  },
  conditional2:{
    level:"B1-B2 · GRAMMAR",
    rule:{
      ru:"Second Conditional описывает нереальные или маловероятные условия в настоящем/будущем. Формула: If + Past Simple, ... would + базовая форма глагола.",
      en:"Second Conditional describes unreal or unlikely conditions in the present/future. Formula: If + Past Simple, ... would + base verb."
    },
    points:{
      ru:["If-часть в Past Simple, но значение не прошедшее","Результат: would + базовая форма","Часто с 'were' вместо 'was' в формальном стиле: If I were you...","Используется для гипотетических ситуаций"],
      en:["The if-clause uses Past Simple, but the meaning isn't past","Result: would + base verb","Often 'were' instead of 'was' in formal style: If I were you...","Used for hypothetical situations"]
    },
    examples:[
      {en:"If I had more money, I would travel the world.", ru:"Если бы у меня было больше денег, я бы путешествовал по миру."},
      {en:"If she studied harder, she would get better grades.", ru:"Если бы она усерднее училась, у неё были бы лучшие оценки."},
      {en:"If I were you, I would apologize.", ru:"На твоём месте я бы извинился."}
    ]
  },
  reported_speech:{
    level:"B1-B2 · GRAMMAR",
    rule:{
      ru:"В косвенной речи время глагола обычно сдвигается на один шаг назад (present → past, will → would и т.д.), когда мы пересказываем чужие слова.",
      en:"In reported speech, the verb tense usually shifts one step back (present → past, will → would, etc.) when we report someone else's words."
    },
    points:{
      ru:["Present Simple → Past Simple","am/is/are → was/were","will → would, can → could","Present Perfect → Past Perfect"],
      en:["Present Simple → Past Simple","am/is/are → was/were","will → would, can → could","Present Perfect → Past Perfect"]
    },
    examples:[
      {en:"\"I am tired,\" she said. → She said she was tired.", ru:"«Я устала», — сказала она. → Она сказала, что устала."},
      {en:"\"I will call you,\" he said. → He said he would call me.", ru:"«Я тебе позвоню», — сказал он. → Он сказал, что позвонит мне."},
      {en:"\"I work every day,\" she said. → She said she worked every day.", ru:"«Я работаю каждый день», — сказала она. → Она сказала, что работает каждый день."}
    ]
  },
  gerund_infinitive:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"Некоторые глаголы требуют после себя герундий (-ing), другие — инфинитив (to + глагол). Это нужно запоминать для каждого глагола отдельно.",
      en:"Some verbs are followed by a gerund (-ing), others by an infinitive (to + verb). This has to be learned verb by verb."
    },
    points:{
      ru:["+ -ing: enjoy, finish, avoid, suggest, mind","+ to: want, decide, promise, hope, plan","Некоторые глаголы допускают оба варианта: like, start, love","После предлогов всегда -ing: interested in reading"],
      en:["+ -ing: enjoy, finish, avoid, suggest, mind","+ to: want, decide, promise, hope, plan","Some verbs allow both: like, start, love","After a preposition it's always -ing: interested in reading"]
    },
    examples:[
      {en:"I enjoy reading books in the evening.", ru:"Мне нравится читать книги по вечерам."},
      {en:"She wants to learn French.", ru:"Она хочет выучить французский."},
      {en:"He decided to buy a new car.", ru:"Он решил купить новую машину."}
    ]
  },
  relative_clauses:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"Относительные придаточные предложения добавляют информацию о существительном с помощью слов who, which, that, where, whose.",
      en:"Relative clauses add information about a noun using who, which, that, where, whose."
    },
    points:{
      ru:["who — для людей","which — для предметов и животных","that — для людей и предметов (неформально)","where — для мест, whose — для принадлежности"],
      en:["who — for people","which — for things and animals","that — for people and things (informal)","where — for places, whose — for possession"]
    },
    examples:[
      {en:"The man who lives next door is a doctor.", ru:"Мужчина, который живёт по соседству, — врач."},
      {en:"This is the book that I told you about.", ru:"Это та книга, о которой я тебе рассказывал."},
      {en:"That's the house where I grew up.", ru:"Это дом, где я вырос."}
    ]
  },
  used_to:{
    level:"A2-B1 · GRAMMAR",
    rule:{
      ru:"Used to + базовая форма глагола описывает привычки или состояния, которые были правдой в прошлом, но больше не актуальны.",
      en:"Used to + base verb describes past habits or states that were true before but are not true anymore."
    },
    points:{
      ru:["Форма одинакова для всех подлежащих: used to + base","Отрицание: didn't use to","Вопрос: Did you use to...?","Не путать с 'to be used to' (привыкнуть к чему-то)"],
      en:["Same form for every subject: used to + base","Negative: didn't use to","Question: Did you use to...?","Don't confuse with 'to be used to' (to be accustomed to)"]
    },
    examples:[
      {en:"I used to play football every weekend.", ru:"Раньше я играл в футбол каждые выходные."},
      {en:"She used to live in Paris.", ru:"Раньше она жила в Париже."},
      {en:"They didn't use to like coffee.", ru:"Раньше им не нравился кофе."}
    ]
  },
  tag_questions:{
    level:"B1 · GRAMMAR",
    rule:{
      ru:"Разделительные вопросы (question tags) добавляются в конец утверждения, чтобы уточнить или подтвердить информацию. Если основная часть утвердительная — хвостик отрицательный, и наоборот.",
      en:"Question tags are added to the end of a statement to check or confirm information. If the main clause is positive, the tag is negative, and vice versa."
    },
    points:{
      ru:["Утверждение + отрицательный хвостик: She is nice, isn't she?","Отрицание + положительный хвостик: You don't smoke, do you?","Хвостик повторяет вспомогательный глагол утверждения","Интонация вверх — настоящий вопрос, вниз — подтверждение"],
      en:["Positive statement + negative tag: She is nice, isn't she?","Negative statement + positive tag: You don't smoke, do you?","The tag repeats the auxiliary verb of the statement","Rising intonation = real question, falling = confirmation"]
    },
    examples:[
      {en:"She is your sister, isn't she?", ru:"Она твоя сестра, не так ли?"},
      {en:"They don't live here, do they?", ru:"Они здесь не живут, правда?"},
      {en:"You can swim, can't you?", ru:"Ты умеешь плавать, да?"}
    ]
  },
  countable_uncountable:{
    level:"A2 · GRAMMAR",
    rule:{
      ru:"Исчисляемые существительные можно посчитать (an apple, two apples), у них есть форма множественного числа. Неисчисляемые существительные обозначают вещество или понятие и не имеют множественного числа (water, information, advice).",
      en:"Countable nouns can be counted (an apple, two apples) and have a plural form. Uncountable nouns refer to a substance or concept and have no plural form (water, information, advice)."
    },
    points:{
      ru:["Исчисляемые: a/an в единственном числе, -s во множественном","Неисчисляемые: без a/an, без -s, глагол в единственном числе","Много неисчисляемых: money, furniture, news, luggage, advice","С неисчисляемыми — much, a little; с исчисляемыми — many, a few"],
      en:["Countable: a/an in the singular, -s in the plural","Uncountable: no a/an, no -s, singular verb form","Common uncountables: money, furniture, news, luggage, advice","Use much/a little with uncountables, many/a few with countables"]
    },
    examples:[
      {en:"I need some information about the trip.", ru:"Мне нужна информация о поездке."},
      {en:"She bought a new chair for the office.", ru:"Она купила новый стул для офиса."},
      {en:"We don't have much furniture in this room.", ru:"У нас не так много мебели в этой комнате."}
    ]
  }
};

/* Генерация теста из 20 непохожих вопросов по теме */
function generateTest(topicId, count){
  const topic = getTopic(topicId);
  const n = count || 20;
  const questions = [];
  const seenTexts = new Set();
  let guard = 0;
  while(questions.length < n && guard < n*12){
    guard++;
    const q = topic.gen();
    if(seenTexts.has(q.text)) continue;
    seenTexts.add(q.text);
    questions.push(q);
  }
  return questions;
}

/* ---------------------------- LISTENING DATA ---------------------------- */
const LISTENING_BANK = [
  {
    text:"Hi, I'm calling about the apartment you advertised online. Is it still available for rent? I would like to visit it this weekend if possible, maybe on Saturday morning.",
    q:"Почему звонит человек?",
    options:["Хочет продать квартиру","Хочет узнать, доступна ли аренда квартиры","Хочет пожаловаться на соседей","Ищет работу"],
    correct:"Хочет узнать, доступна ли аренда квартиры"
  },
  {
    text:"Good morning, passengers. This is the final call for flight BA 249 to London. Please proceed immediately to gate 14. The gate closes in ten minutes.",
    q:"Что должны сделать пассажиры?",
    options:["Подождать на регистрации","Немедленно пройти к выходу 14","Сдать багаж","Купить билет"],
    correct:"Немедленно пройти к выходу 14"
  },
  {
    text:"I usually wake up at seven, have a quick breakfast, and then walk to work because the office is only fifteen minutes away from my house.",
    q:"Как человек добирается до работы?",
    options:["На машине","На автобусе","Пешком","На велосипеде"],
    correct:"Пешком"
  },
  {
    text:"The weather forecast for tomorrow says it will be sunny in the morning, but heavy rain is expected in the afternoon, so remember to bring an umbrella.",
    q:"Что советуют взять с собой?",
    options:["Солнцезащитные очки","Зонт","Тёплую куртку","Ничего не нужно"],
    correct:"Зонт"
  },
  {
    text:"Welcome to the museum. Please note that photography is not allowed in the main hall, but you are welcome to take pictures in the garden area outside.",
    q:"Где разрешено фотографировать?",
    options:["Везде в музее","Только в главном зале","В саду снаружи","Фотографировать запрещено везде"],
    correct:"В саду снаружи"
  },
  {
    text:"Could you pass me the salt, please? This soup is a little bland, and I think it just needs a bit more seasoning to taste better.",
    q:"Что не так с супом?",
    options:["Он слишком солёный","Он слишком острый","Он безвкусный","Он холодный"],
    correct:"Он безвкусный"
  },
  {
    text:"Our train was delayed by forty minutes because of a technical problem, so we missed our connection and had to wait two more hours at the station.",
    q:"Почему пассажиры пропустили пересадку?",
    options:["Проспали","Поезд задержали из-за технической проблемы","Купили не тот билет","Заблудились на вокзале"],
    correct:"Поезд задержали из-за технической проблемы"
  },
  {
    text:"If you have any questions about your order, please don't hesitate to contact our customer support team, available twenty four hours a day, seven days a week.",
    q:"Когда доступна поддержка клиентов?",
    options:["Только по будням","С 9 до 18","Круглосуточно","Только по выходным"],
    correct:"Круглосуточно"
  },
  {
    text:"She has been learning English for about two years now, and she says watching movies without subtitles has really improved her listening skills a lot.",
    q:"Что помогло ей улучшить понимание речи на слух?",
    options:["Учебники","Просмотр фильмов без субтитров","Разговоры с носителями языка","Прослушивание музыки"],
    correct:"Просмотр фильмов без субтитров"
  },
  {
    text:"Attention, shoppers. Our store will be closing in fifteen minutes. Please bring your final purchases to the checkout. Thank you for shopping with us today.",
    q:"Через сколько минут закроется магазин?",
    options:["Через 5 минут","Через 15 минут","Через 30 минут","Через час"],
    correct:"Через 15 минут"
  },
  {
    text:"I ran into an old friend from university yesterday at the coffee shop. We hadn't seen each other for almost five years, so we talked for hours.",
    q:"Что произошло с человеком вчера?",
    options:["Он потерял друга","Он случайно встретил старого друга","Он поссорился с другом","Он переехал в другой город"],
    correct:"Он случайно встретил старого друга"
  },
  {
    text:"To reset your password, click the link we sent to your email, enter a new password twice, and then log in again with your new credentials.",
    q:"Что нужно сделать в первую очередь?",
    options:["Позвонить в поддержку","Кликнуть по ссылке в письме","Удалить аккаунт","Написать в чат"],
    correct:"Кликнуть по ссылке в письме"
  },
  {
    text:"The restaurant is fully booked tonight, but we do have a table available tomorrow at eight in the evening if that works for you.",
    q:"Когда есть свободный столик?",
    options:["Сегодня вечером","Завтра в 8 вечера","Через неделю","Столиков нет вообще"],
    correct:"Завтра в 8 вечера"
  },
  {
    text:"Remember to submit your assignment before midnight on Friday. Late submissions will lose ten percent of the total grade for every day they are delayed.",
    q:"Что произойдёт при опоздании со сдачей задания?",
    options:["Ничего не изменится","Оценка снизится на 10% за каждый день","Задание не примут вообще","Дадут дополнительное время"],
    correct:"Оценка снизится на 10% за каждый день"
  },
  {
    text:"We spent the whole afternoon hiking up the mountain, and even though it was exhausting, the view from the top was absolutely worth it.",
    q:"Как чувствовали себя люди после похода?",
    options:["Скучали","Устали, но вид того стоил","Испугались","Замёрзли"],
    correct:"Устали, но вид того стоил"
  },
  {
    text:"Before you leave the office, please make sure all the lights are switched off and the doors are properly locked for security reasons.",
    q:"Что нужно сделать перед уходом из офиса?",
    options:["Оставить свет включённым","Выключить свет и запереть двери","Позвонить охране","Ничего специального"],
    correct:"Выключить свет и запереть двери"
  },
  {
    text:"I have never been particularly good at cooking, but since I started following simple recipes online, my meals have become much tastier.",
    q:"Что помогло улучшить готовку?",
    options:["Кулинарные курсы","Простые рецепты онлайн","Помощь мамы","Дорогая техника"],
    correct:"Простые рецепты онлайн"
  },
  {
    text:"The concert has been postponed until next month due to unforeseen circumstances. All tickets already purchased will remain valid for the new date.",
    q:"Что будет с уже купленными билетами?",
    options:["Их аннулируют","Они останутся действительными","Нужно купить новые","Деньги вернут"],
    correct:"Они останутся действительными"
  },
  {
    text:"He decided to give up sugar for a month to see how it would affect his energy levels, and surprisingly, he started sleeping much better too.",
    q:"Что дополнительно улучшилось у него?",
    options:["Настроение","Сон","Зрение","Память"],
    correct:"Сон"
  },
  {
    text:"Passengers travelling with children or those who need extra assistance are kindly invited to board the aircraft first, before general boarding begins.",
    q:"Кто садится в самолёт первым?",
    options:["Пассажиры бизнес-класса","Пассажиры с детьми и те, кому нужна помощь","Экипаж","Все одновременно"],
    correct:"Пассажиры с детьми и те, кому нужна помощь"
  },
  {
    text:"I'm afraid the item you ordered is currently out of stock, but we expect a new delivery by the end of next week if you'd like to wait.",
    q:"Что происходит с заказанным товаром?",
    options:["Он уже отправлен","Его нет в наличии","Он был отменён","Он стоит слишком дорого"],
    correct:"Его нет в наличии"
  },
  {
    text:"On your left you can see the old town hall, which was built in the fourteenth century and is now one of the most visited landmarks in the city.",
    q:"Что говорится про ратушу?",
    options:["Она была построена недавно","Она была построена в 14 веке","Она закрыта для посещения","Она находится за городом"],
    correct:"Она была построена в 14 веке"
  },
  {
    text:"Before the interview, take a few minutes to research the company, prepare examples of your past achievements, and think of a couple of questions to ask them.",
    q:"Что нужно сделать перед собеседованием?",
    options:["Только выспаться","Изучить компанию и подготовить примеры","Ничего специального","Купить новый костюм"],
    correct:"Изучить компанию и подготовить примеры"
  },
  {
    text:"Due to heavy snowfall, several flights have been cancelled this morning, and passengers are advised to check the status of their flight online before travelling to the airport.",
    q:"Что советуют сделать пассажирам?",
    options:["Приехать в аэропорт как можно раньше","Проверить статус рейса онлайн","Купить новый билет","Позвонить в полицию"],
    correct:"Проверить статус рейса онлайн"
  },
  {
    text:"After moving to a new city, it took her a few months to make friends, but joining a local sports club really helped her meet new people.",
    q:"Что помогло ей завести друзей?",
    options:["Работа","Спортивный клуб","Онлайн-знакомства","Соседи"],
    correct:"Спортивный клуб"
  },
  {
    text:"The doctor recommended drinking at least eight glasses of water a day and getting a full night of sleep to help the headaches go away.",
    q:"Что порекомендовал врач?",
    options:["Больше спать и меньше пить воды","Пить больше воды и высыпаться","Принимать таблетки","Меньше работать"],
    correct:"Пить больше воды и высыпаться"
  },
  {
    text:"Unfortunately, the elevator is out of order today, so please use the stairs on the left to reach the second and third floors.",
    q:"Почему нужно пользоваться лестницей?",
    options:["Лифт слишком медленный","Лифт не работает","Лестница ближе","Лифт только для персонала"],
    correct:"Лифт не работает"
  },
  {
    text:"The company announced that all employees will be able to work from home two days a week starting next month, following positive feedback from the trial period.",
    q:"Что изменится у сотрудников со следующего месяца?",
    options:["Они будут работать из дома два дня в неделю","Их уволят","Они получат прибавку","Они будут работать больше часов"],
    correct:"Они будут работать из дома два дня в неделю"
  },
  {
    text:"I forgot my umbrella at home this morning, and of course, it started raining heavily right when I left the office.",
    q:"Что забыл человек дома?",
    options:["Телефон","Ключи","Зонт","Кошелёк"],
    correct:"Зонт"
  },
  {
    text:"The new library opens at eight in the morning on weekdays, but on weekends it only opens at eleven and closes earlier, at six in the evening.",
    q:"Во сколько библиотека открывается по выходным?",
    options:["В 8 утра","В 9 утра","В 11 утра","В 6 вечера"],
    correct:"В 11 утра"
  },
  {
    text:"She was so nervous before her driving test that she could barely sleep the night before, but in the end she passed with no mistakes at all.",
    q:"Как прошёл экзамен по вождению?",
    options:["Она провалила экзамен","Она сдала без единой ошибки","Экзамен перенесли","Она не пришла на экзамен"],
    correct:"Она сдала без единой ошибки"
  },
  {
    text:"Please keep your seatbelt fastened while the sign is on, even if the seatbelt sign has been turned off during the flight, for your own safety.",
    q:"Что советуют делать пассажирам во время полёта?",
    options:["Снять ремень сразу после взлёта","Держать ремень пристёгнутым для безопасности","Вставать как можно чаще","Отключить телефон"],
    correct:"Держать ремень пристёгнутым для безопасности"
  },
  {
    text:"After trying several diets that didn't work, she finally found success by simply cooking more meals at home instead of ordering takeout.",
    q:"Что помогло ей добиться результата?",
    options:["Дорогая диета","Готовка дома вместо заказа еды","Тренажёрный зал","Таблетки для похудения"],
    correct:"Готовка дома вместо заказа еды"
  },
  {
    text:"The hotel offers free breakfast every morning from seven to ten, and guests can also use the swimming pool at any time during their stay.",
    q:"До скольки подаётся завтрак в отеле?",
    options:["До 9 утра","До 10 утра","До 11 утра","Завтрак не включён"],
    correct:"До 10 утра"
  },
  {
    text:"He was late for the meeting because his car broke down on the highway, and he had to wait almost an hour for roadside assistance to arrive.",
    q:"Почему он опоздал на встречу?",
    options:["Проспал","Машина сломалась","Забыл о встрече","Попал в пробку"],
    correct:"Машина сломалась"
  },
  {
    text:"Welcome aboard. We will be flying at an altitude of thirty five thousand feet, and the flight time to our destination is approximately six hours.",
    q:"Сколько будет длиться полёт?",
    options:["Три часа","Шесть часов","Девять часов","Не указано"],
    correct:"Шесть часов"
  },
  {
    text:"I can't find my keys anywhere. I checked my bag, my coat pockets, and the kitchen table, but they seem to have completely disappeared.",
    q:"Что человек не может найти?",
    options:["Телефон","Кошелёк","Ключи","Очки"],
    correct:"Ключи"
  },
  {
    text:"The gym is open twenty four hours for members, but the swimming pool closes at ten in the evening every day of the week.",
    q:"До скольки работает бассейн?",
    options:["До 22:00","Круглосуточно","До полуночи","До 20:00"],
    correct:"До 22:00"
  },
  {
    text:"She applied for the job last month and finally got a call for an interview next Tuesday at ten in the morning.",
    q:"Когда у неё собеседование?",
    options:["В понедельник","Во вторник в 10 утра","В среду вечером","Дата неизвестна"],
    correct:"Во вторник в 10 утра"
  },
  {
    text:"Due to roadworks on Main Street, buses are being diverted through Park Avenue until further notice, adding about ten minutes to the journey.",
    q:"Почему автобусы едут в объезд?",
    options:["Из-за аварии","Из-за дорожных работ","Из-за протеста","Из-за погоды"],
    correct:"Из-за дорожных работ"
  },
  {
    text:"I'd recommend the grilled salmon, it's our chef's specialty today, served with roasted vegetables and a lemon butter sauce.",
    q:"Что рекомендует официант?",
    options:["Стейк","Жареного лосося","Суп","Пасту"],
    correct:"Жареного лосося"
  },
  {
    text:"The library is extending its opening hours during exam season, staying open until midnight instead of the usual eight in the evening.",
    q:"Как меняются часы работы библиотеки во время сессии?",
    options:["Сокращаются","Не меняются","Продлеваются до полуночи","Библиотека закрывается совсем"],
    correct:"Продлеваются до полуночи"
  },
  {
    text:"He's been saving up for a new laptop for months, and he finally has enough money to buy the one he wanted.",
    q:"Что он копил деньги, чтобы купить?",
    options:["Телефон","Ноутбук","Машину","Велосипед"],
    correct:"Ноутбук"
  },
  {
    text:"The package was supposed to arrive yesterday, but according to the tracking information, it's still at the sorting facility.",
    q:"Где сейчас находится посылка?",
    options:["Уже доставлена","На сортировочном центре","Потеряна","В пути к клиенту"],
    correct:"На сортировочном центре"
  },
  {
    text:"We're thinking about repainting the living room. My partner wants a bright yellow, but I prefer something calmer, like light gray.",
    q:"Какой цвет предпочитает рассказчик?",
    options:["Ярко-жёлтый","Светло-серый","Красный","Синий"],
    correct:"Светло-серый"
  },
  {
    text:"The conference has been moved online this year, so you can attend all the sessions from home through the official website.",
    q:"Как теперь проходит конференция?",
    options:["Очно, как обычно","Онлайн","Отменена совсем","Только для VIP"],
    correct:"Онлайн"
  },
  {
    text:"I switched to a plant based diet six months ago, and I've noticed I have a lot more energy throughout the day.",
    q:"Что заметил человек после смены питания?",
    options:["Проблемы со сном","Больше энергии","Потерю аппетита","Ничего не изменилось"],
    correct:"Больше энергии"
  },
  {
    text:"The landlord said he would fix the heating by the end of the week, but it's already been broken for ten days.",
    q:"Что должен починить арендодатель?",
    options:["Кондиционер","Отопление","Водопровод","Электричество"],
    correct:"Отопление"
  },
  {
    text:"Tickets for the festival go on sale this Friday at noon, and organizers expect them to sell out within a few hours.",
    q:"Когда начнётся продажа билетов?",
    options:["В четверг вечером","В пятницу в полдень","В субботу утром","Уже началась"],
    correct:"В пятницу в полдень"
  },
  {
    text:"My phone battery drains so fast these days that I have to charge it at least twice a day just to get through work.",
    q:"Какая проблема у телефона рассказчика?",
    options:["Экран разбит","Быстро садится батарея","Не включается","Медленно работает"],
    correct:"Быстро садится батарея"
  },
  {
    text:"The new employee orientation starts at nine sharp, so please make sure you arrive at least fifteen minutes early to sign in.",
    q:"Во сколько нужно приехать новым сотрудникам?",
    options:["Ровно в 9","Не позже 8:45","В любое время до полудня","В 9:15"],
    correct:"Не позже 8:45"
  },
  {
    text:"She's been trying to learn how to play the guitar for a year now, but she still struggles with changing chords quickly.",
    q:"С чем у неё сложности при игре на гитаре?",
    options:["С настройкой инструмента","Со сменой аккордов","С пением","С покупкой инструмента"],
    correct:"Со сменой аккордов"
  },
  {
    text:"The city council approved a plan to build a new park downtown, which should be completed by the end of next year.",
    q:"Что одобрил городской совет?",
    options:["Новую дорогу","Новый парк","Новый мост","Новую школу"],
    correct:"Новый парк"
  },
  {
    text:"I usually meal prep on Sundays, cooking enough food for the whole week so I don't have to cook every single day.",
    q:"Зачем человек готовит еду по воскресеньям?",
    options:["Чтобы сэкономить деньги","Чтобы не готовить каждый день","Потому что любит готовить","Для гостей"],
    correct:"Чтобы не готовить каждый день"
  },
  {
    text:"The internet connection has been really unstable lately, cutting out several times a day, especially in the evening.",
    q:"Какая проблема с интернетом?",
    options:["Слишком медленный","Постоянно отключается","Слишком дорогой","Всё в порядке"],
    correct:"Постоянно отключается"
  },
  {
    text:"He's allergic to peanuts, so he always checks the ingredients carefully before trying any new food at a restaurant.",
    q:"На что у него аллергия?",
    options:["На молоко","На арахис","На морепродукты","На глютен"],
    correct:"На арахис"
  },
  {
    text:"The museum offers free admission on the first Sunday of every month, which is when it tends to get the most crowded.",
    q:"Когда вход в музей бесплатный?",
    options:["Каждое воскресенье","В первое воскресенье месяца","По праздникам","Никогда"],
    correct:"В первое воскресенье месяца"
  },
  {
    text:"We had to reschedule the picnic because of the storm warning, so we're planning to go next weekend instead if the weather is better.",
    q:"Почему пикник перенесли?",
    options:["Из-за отпуска","Из-за штормового предупреждения","Из-за ремонта парка","Без причины"],
    correct:"Из-за штормового предупреждения"
  },
  {
    text:"The company is offering a discount of twenty percent on all orders placed before the end of this month, using the code SAVE20.",
    q:"Какая скидка предлагается?",
    options:["10 процентов","20 процентов","50 процентов","Скидки нет"],
    correct:"20 процентов"
  }
];

/* ---------------------------- SPEAKING DATA ------------------------------ */
const SPEAKING_BANK = [
  {en:"I would like a cup of coffee, please.", ru:"Я бы хотел чашку кофе, пожалуйста."},
  {en:"Could you tell me the way to the station?", ru:"Не могли бы вы подсказать дорогу до вокзала?"},
  {en:"How much does this cost?", ru:"Сколько это стоит?"},
  {en:"I have been living here for five years.", ru:"Я живу здесь уже пять лет."},
  {en:"She is the most talented singer in the class.", ru:"Она самая талантливая певица в классе."},
  {en:"We should leave early to avoid the traffic.", ru:"Нам стоит выехать пораньше, чтобы избежать пробок."},
  {en:"Can you help me carry these bags?", ru:"Можешь помочь мне донести эти сумки?"},
  {en:"I have never tried sushi before.", ru:"Я никогда раньше не пробовал суши."},
  {en:"The weather is absolutely beautiful today.", ru:"Погода сегодня просто прекрасная."},
  {en:"He is looking for a new job in marketing.", ru:"Он ищет новую работу в маркетинге."},
  {en:"Please turn off the lights before you leave.", ru:"Пожалуйста, выключи свет перед уходом."},
  {en:"They are travelling around Europe this summer.", ru:"Этим летом они путешествуют по Европе."},
  {en:"I usually wake up early on weekdays.", ru:"Обычно я просыпаюсь рано по будням."},
  {en:"What time does the museum open?", ru:"Во сколько открывается музей?"},
  {en:"This is the best restaurant in the city.", ru:"Это лучший ресторан в городе."},
  {en:"I need to finish my homework tonight.", ru:"Мне нужно закончить домашнее задание сегодня вечером."},
  {en:"She has just arrived from the airport.", ru:"Она только что приехала из аэропорта."},
  {en:"Would you like something to drink?", ru:"Хотели бы вы что-нибудь выпить?"},
  {en:"We must finish this project by Friday.", ru:"Мы должны закончить этот проект к пятнице."},
  {en:"I am really looking forward to the trip.", ru:"Я очень жду эту поездку."},
  {en:"Can I open the window? It is quite hot.", ru:"Можно открыть окно? Здесь довольно жарко."},
  {en:"He speaks three languages fluently.", ru:"Он свободно говорит на трёх языках."},
  {en:"Excuse me, is this seat taken?", ru:"Извините, это место занято?"},
  {en:"I'm sorry, I didn't catch that. Could you repeat it?", ru:"Простите, я не расслышал. Повторите, пожалуйста."},
  {en:"What do you recommend from the menu?", ru:"Что вы посоветуете из меню?"},
  {en:"I'll have the same, please.", ru:"Мне то же самое, пожалуйста."},
  {en:"Could you turn down the volume a little?", ru:"Не могли бы вы немного убавить громкость?"},
  {en:"I think I made a mistake in my report.", ru:"Кажется, я допустил ошибку в отчёте."},
  {en:"Let's meet at the entrance at six o'clock.", ru:"Давай встретимся у входа в шесть часов."},
  {en:"I'm not sure if I can make it tonight.", ru:"Я не уверен, что смогу прийти сегодня вечером."},
  {en:"Do you have any plans for the weekend?", ru:"У тебя есть планы на выходные?"},
  {en:"I'll send you the details by email.", ru:"Я пришлю тебе детали по почте."},
  {en:"Could you recommend a good hotel nearby?", ru:"Не могли бы вы порекомендовать хороший отель поблизости?"},
  {en:"I really appreciate your help with this.", ru:"Я очень ценю твою помощь с этим."},
  {en:"Let me know if you need anything else.", ru:"Дай знать, если тебе нужно что-то ещё."},
  {en:"I have a doctor's appointment this afternoon.", ru:"У меня сегодня после обеда приём у врача."},
  {en:"The traffic was terrible this morning.", ru:"Сегодня утром были ужасные пробки."},
  {en:"I'm looking forward to seeing you soon.", ru:"Жду не дождусь встречи с тобой."},
  {en:"Could you explain that one more time?", ru:"Не могли бы вы объяснить это ещё раз?"},
  {en:"I forgot to bring my umbrella today.", ru:"Я забыл сегодня взять зонт."},
  {en:"She is much better at cooking than I am.", ru:"Она готовит намного лучше меня."},
  {en:"We need to buy some groceries after work.", ru:"Нам нужно купить продукты после работы."},
  {en:"I couldn't sleep well last night.", ru:"Я плохо спал прошлой ночью."},
  {en:"This project has taken longer than expected.", ru:"Этот проект занял больше времени, чем ожидалось."},
  {en:"Could you keep an eye on my bag for a second?", ru:"Не могли бы вы присмотреть за моей сумкой секунду?"},
  {en:"I'm trying to save money for a trip abroad.", ru:"Я пытаюсь накопить деньги на поездку за границу."}
];

/* ==========================================================================
   ХРАНИЛИЩЕ (window.storage)
   Артефакты Claude.ai блокируют fetch к сторонним доменам (CSP), поэтому
   Supabase отсюда недоступен. Вместо этого используем встроенное shared-
   хранилище артефактов: логин/пароль/история сохраняются навсегда и видны
   на любом устройстве, где человек заходит под тем же аккаунтом Claude.
   Админ-панель в самом приложении (кнопка "👥 пользователи") показывает
   всех зарегистрированных — это ваш способ управлять данными.
   ========================================================================== */
async function sha256Hex(text){
  const enc = new TextEncoder().encode(text);
  const buf = await crypto.subtle.digest('SHA-256', enc);
  return Array.from(new Uint8Array(buf)).map(b=>b.toString(16).padStart(2,'0')).join('');
}
function randomSalt(){
  const arr = new Uint8Array(16);
  crypto.getRandomValues(arr);
  return Array.from(arr).map(b=>b.toString(16).padStart(2,'0')).join('');
}
function normUser(name){ return name.trim().toLowerCase(); }

const Store = {
  async getUserRecord(username){
    try{ const r = await window.storage.get('user:'+normUser(username), true); return r ? JSON.parse(r.value) : null; }
    catch(e){ return null; }
  },
  async setUserRecord(username, record){
    try{ await window.storage.set('user:'+normUser(username), JSON.stringify(record), true); }catch(e){ console.error(e); }
  },
  async addToUserIndex(username){
    try{
      const key = 'users_index';
      let list = [];
      try{ const r = await window.storage.get(key, true); list = r ? JSON.parse(r.value) : []; }catch(e){ list = []; }
      const u = normUser(username);
      if(!list.includes(u)){ list.push(u); await window.storage.set(key, JSON.stringify(list), true); }
    }catch(e){ console.error(e); }
  },
  async getUserIndex(){
    try{ const r = await window.storage.get('users_index', true); return r ? JSON.parse(r.value) : []; }
    catch(e){ return []; }
  },
  async getProfile(username){
    try{ const r = await window.storage.get('profile:'+normUser(username), true); return r ? JSON.parse(r.value) : null; }
    catch(e){ return null; }
  },
  async setProfile(username, profile){
    try{ await window.storage.set('profile:'+normUser(username), JSON.stringify(profile), true); }catch(e){ console.error(e); }
  },
  async getHistory(username){
    try{ const r = await window.storage.get('history:'+normUser(username), true); return r ? JSON.parse(r.value) : []; }
    catch(e){ return []; }
  },
  async addHistory(username, record){
    const hist = await this.getHistory(username);
    hist.unshift(record);
    try{ await window.storage.set('history:'+normUser(username), JSON.stringify(hist.slice(0,300)), true); }catch(e){ console.error(e); }
    return hist;
  },
  async rememberDevice(username){
    try{ await window.storage.set('remember_me', username, false); }catch(e){}
  },
  async getRememberedUser(){
    try{ const r = await window.storage.get('remember_me', false); return r ? r.value : null; }
    catch(e){ return null; }
  },
  async forgetDevice(){
    try{ await window.storage.set('remember_me', '', false); }catch(e){}
  }
};

/* ==========================================================================
   СОСТОЯНИЕ ПРИЛОЖЕНИЯ
   ========================================================================== */
const App = {
  profile:null,
  username:null,
  history:[],
  lang:'ru',
  authMode:'login', // 'login' | 'register'
  currentTest:null,       // {topicId, questions, index, correctCount, answers:[]}
  currentListen:null,     // {items, index, correctCount, answered}
  listenRate:0.95,
  currentSpeak:null,      // {items, index}
  speechRecognition:null,
  recognizing:false,
  micStream:null
};

function screen(id){
  ['screen-dashboard','screen-explain','screen-test','screen-results','screen-listening','screen-speaking'].forEach(s=>{
    document.getElementById(s).classList.toggle('hidden', s!==id);
  });
  window.scrollTo({top:0, behavior:'smooth'});
}

/* ---------------------------- SPLASH ------------------------------------ */
function hideSplash(){
  const splash = document.getElementById('screen-splash');
  splash.classList.add('fade-out');
  setTimeout(()=>{ splash.style.display='none'; }, 550);
}

/* ---------------------------- ВХОД / РЕГИСТРАЦИЯ ------------------------------ */
document.getElementById('btn-login').addEventListener('click', doAuthSubmit);
document.getElementById('login-name').addEventListener('keydown', e=>{ if(e.key==='Enter') doAuthSubmit(); });
document.getElementById('login-pass').addEventListener('keydown', e=>{ if(e.key==='Enter') doAuthSubmit(); });
document.getElementById('login-pass2').addEventListener('keydown', e=>{ if(e.key==='Enter') doAuthSubmit(); });

document.getElementById('tab-login').addEventListener('click', ()=>setAuthMode('login'));
document.getElementById('tab-register').addEventListener('click', ()=>setAuthMode('register'));
function setAuthMode(mode){
  App.authMode = mode;
  document.getElementById('tab-login').classList.toggle('active', mode==='login');
  document.getElementById('tab-register').classList.toggle('active', mode==='register');
  document.getElementById('field-pass-confirm').classList.toggle('hidden', mode!=='register');
  document.getElementById('login-btn') && null;
  document.getElementById('btn-login').textContent = mode==='login' ? t2('login_btn') : (App.lang==='en' ? 'Create account →' : (App.lang==='ru' ? 'Создать аккаунт →' : t2('login_btn')));
  document.getElementById('login-error').textContent = '';
}

document.getElementById('pw-toggle').addEventListener('click', ()=>{
  const p1 = document.getElementById('login-pass');
  const p2 = document.getElementById('login-pass2');
  const showing = p1.type === 'text';
  p1.type = showing ? 'password' : 'text';
  p2.type = showing ? 'password' : 'text';
  document.getElementById('pw-toggle').textContent = showing ? t2('pw_show') : t2('pw_hide');
});

async function doAuthSubmit(){
  const errEl = document.getElementById('login-error');
  errEl.textContent = '';
  const nameInput = document.getElementById('login-name');
  const passInput = document.getElementById('login-pass');
  const pass2Input = document.getElementById('login-pass2');
  const username = nameInput.value.trim();
  const pass = passInput.value;
  const pass2 = pass2Input.value;

  if(username.length < 3 || !/^[a-zA-Z0-9_\-\.]+$/.test(username)){
    errEl.textContent = t2('err_name_short'); nameInput.focus(); return;
  }
  if(pass.length < 4){
    errEl.textContent = t2('err_pass_short'); passInput.focus(); return;
  }

  const btn = document.getElementById('btn-login');
  btn.disabled = true;
  const originalLabel = btn.textContent;
  btn.textContent = '…';

  try{
    if(App.authMode === 'register'){
      if(pass !== pass2){ errEl.textContent = t2('err_pass_mismatch'); pass2Input.focus(); return; }
      const existing = await Store.getUserRecord(username);
      if(existing){ errEl.textContent = t2('err_user_exists'); return; }
      const salt = randomSalt();
      const hash = await sha256Hex(salt + pass);
      const joined = new Date().toISOString();
      await Store.setUserRecord(username, { username, salt, hash, joined });
      await Store.addToUserIndex(username);
      await Store.setProfile(username, { name: username, joined });
      await completeLogin(username);
    } else {
      const existing = await Store.getUserRecord(username);
      if(!existing){ errEl.textContent = t2('err_user_notfound'); return; }
      const hash = await sha256Hex(existing.salt + pass);
      if(hash !== existing.hash){ errEl.textContent = t2('err_wrong_pass'); return; }
      await completeLogin(username);
    }
  } catch(e){
    errEl.textContent = App.lang==='en' ? 'Connection error. Please try again.' : 'Ошибка соединения. Попробуйте ещё раз.';
    console.error(e);
  } finally {
    btn.disabled = false;
    btn.textContent = originalLabel;
  }
}

async function completeLogin(username){
  App.username = normUser(username);
  let profile = await Store.getProfile(App.username);
  if(!profile){ profile = { name: username, joined: new Date().toISOString() }; }
  App.profile = profile;
  App.history = await Store.getHistory(App.username);
  await Store.rememberDevice(App.username);
  document.getElementById('screen-login').classList.add('hidden');
  document.getElementById('screen-app').classList.remove('hidden');
  document.getElementById('chip-name').textContent = profile.name;
  document.getElementById('btn-open-admin').classList.remove('hidden');
  renderDashboard();
}

document.getElementById('btn-logout').addEventListener('click', async ()=>{
  await Store.forgetDevice();
  App.profile = null; App.username = null; App.history = [];
  document.getElementById('screen-app').classList.add('hidden');
  document.getElementById('screen-admin').classList.add('hidden');
  document.getElementById('screen-login').classList.remove('hidden');
  document.getElementById('login-name').value='';
  document.getElementById('login-pass').value='';
  document.getElementById('login-pass2').value='';
});

/* ---------------------------- АДМИН-ПАНЕЛЬ (список пользователей) ------- */
document.getElementById('btn-open-admin').addEventListener('click', openAdmin);
document.getElementById('btn-admin-back').addEventListener('click', ()=>{
  document.getElementById('screen-admin').classList.add('hidden');
  document.getElementById('screen-app').classList.remove('hidden');
});
document.getElementById('btn-admin-logout').addEventListener('click', ()=>{
  document.getElementById('btn-logout').click();
});
async function openAdmin(){
  document.getElementById('screen-app').classList.add('hidden');
  document.getElementById('screen-admin').classList.remove('hidden');
  const tbody = document.getElementById('admin-tbody');
  tbody.innerHTML = `<tr><td colspan="4">…</td></tr>`;
  const usernames = await Store.getUserIndex();
  document.getElementById('admin-count').textContent = usernames.length;
  const rows = await Promise.all(usernames.map(async u=>{
    const [rec, hist] = await Promise.all([Store.getUserRecord(u), Store.getHistory(u)]);
    const total = hist.length;
    const avg = total ? Math.round(hist.reduce((s,h)=>s+(h.percent||0),0)/total) : null;
    const joined = rec && rec.joined ? new Date(rec.joined).toLocaleDateString('ru-RU') : '—';
    const youTag = (u === App.username) ? `<span class="admin-you">(вы)</span>` : '';
    return `<tr><td>${escapeHtml(u)}${youTag}</td><td>${joined}</td><td>${total}</td><td>${avg===null?'—':avg+'%'}</td></tr>`;
  }));
  tbody.innerHTML = rows.length ? rows.join('') : `<tr><td colspan="4">—</td></tr>`;
}

/* Инициализация: язык интерфейса + сплэш + автовход по "запомненному" устройству */
(async function init(){
  const splashStart = Date.now();
  try{
    const langRes = await window.storage.get('lang', false);
    if(langRes && langRes.value && TR[langRes.value]) App.lang = langRes.value;
  }catch(e){ /* нет сохранённого языка — используем ru по умолчанию */ }
  applyI18n();
  setAuthMode('login');

  let autoLoggedIn = false;
  try{
    const remembered = await Store.getRememberedUser();
    if(remembered){
      const profile = await Store.getProfile(remembered);
      if(profile){
        App.username = remembered;
        App.profile = profile;
        App.history = await Store.getHistory(remembered);
        document.getElementById('chip-name').textContent = profile.name;
        document.getElementById('btn-open-admin').classList.remove('hidden');
        autoLoggedIn = true;
      }
    }
  }catch(e){ /* ignore */ }

  // не даём сплэшу мигнуть слишком быстро — минимум ~900мс красивой загрузки
  const elapsed = Date.now() - splashStart;
  const wait = Math.max(0, 900 - elapsed);
  setTimeout(()=>{
    if(autoLoggedIn){
      document.getElementById('screen-login').classList.add('hidden');
      document.getElementById('screen-app').classList.remove('hidden');
      renderDashboard();
    } else {
      document.getElementById('screen-login').classList.remove('hidden');
    }
    hideSplash();
  }, wait);
})();

/* ---------------------------- DASHBOARD ---------------------------------- */
function renderDashboard(){
  const greetings = { ru:'Добро пожаловать', en:'Welcome', uz:'Xush kelibsiz', tj:'Хуш омадед' };
  document.getElementById('hero-greeting').textContent = `${greetings[App.lang]||greetings.ru}, ${App.profile.name}!`;
  const tests = App.history.filter(h=>h.kind!=='speaking_session');
  const total = App.history.length;
  const avg = total ? Math.round(App.history.reduce((s,h)=>s+ (h.percent||0),0)/total) : null;
  const topicsSet = new Set(App.history.map(h=>h.topicId));
  document.getElementById('stat-tests').textContent = total;
  document.getElementById('stat-avg').textContent = avg===null ? '—' : avg+'%';
  document.getElementById('stat-topics').textContent = topicsSet.size;

  // streak (уникальные календарные дни подряд, считая от сегодня)
  const days = new Set(App.history.map(h=>h.date.slice(0,10)));
  let streak = 0;
  for(let i=0;i<365;i++){
    const d = new Date(); d.setDate(d.getDate()-i);
    const key = d.toISOString().slice(0,10);
    if(days.has(key)) streak++; else if(i>0) break; else continue;
  }
  document.getElementById('stat-streak').textContent = streak;

  // Штампы
  const stampsWrap = document.getElementById('stamps-scroll');
  if(App.history.length===0){
    stampsWrap.innerHTML = `<div class="stamps-empty">${t2('stamps_empty')}</div>`;
  } else {
    stampsWrap.innerHTML = App.history.slice(0,12).map(h=>{
      const d = new Date(h.date);
      const dateLabel = `${String(d.getDate()).padStart(2,'0')}.${String(d.getMonth()+1).padStart(2,'0')}`;
      return `<div class="stamp" title="${escapeHtml(h.topicTitle)} — ${h.percent}%"><b>${h.percent}%</b>${dateLabel}</div>`;
    }).join('');
  }

  // Сетка тем
  const grid = document.getElementById('topic-grid');
  document.getElementById('topics-count-label').textContent = TOPICS.length + ' ' + t2('topics_word');
  grid.innerHTML = TOPICS.map(t=>{
    const attempts = App.history.filter(h=>h.topicId===t.id);
    const best = attempts.length ? Math.max(...attempts.map(a=>a.percent)) : null;
    return `
    <div class="card topic-card">
      <div class="icon">${t.icon}</div>
      <h4>${t.title}</h4>
      <p>${t.desc}</p>
      <div class="topic-meta">
        <span>${attempts.length} ${t2('attempts_short')}</span>
        ${best!==null ? `<span class="best-badge">${t2('best_badge')} ${best}%</span>` : `<span>—</span>`}
      </div>
      <button class="btn btn-primary" data-topic="${t.id}" onclick="openExplain('${t.id}')">${t2('study_topic_btn')}</button>
    </div>`;
  }).join('');

  // История
  document.getElementById('history-count').textContent = App.history.length + ' ' + t2('records_word');
  const histList = document.getElementById('history-list');
  if(App.history.length===0){
    histList.innerHTML = `<p style="color:var(--ink-soft);font-size:13.5px;padding:14px 0;">${t2('empty_history')}</p>`;
  } else {
    histList.innerHTML = App.history.slice(0,25).map(h=>{
      const d = new Date(h.date);
      const dateLabel = d.toLocaleDateString('ru-RU', {day:'2-digit',month:'2-digit',year:'numeric'}) + ' ' + d.toLocaleTimeString('ru-RU',{hour:'2-digit',minute:'2-digit'});
      const color = h.percent>=80 ? 'var(--teal)' : (h.percent>=50 ? 'var(--marigold-dark)' : 'var(--coral)');
      return `<div style="display:flex;justify-content:space-between;align-items:center;padding:11px 0;border-bottom:1px solid var(--line);font-size:13.5px;">
        <div>
          <div style="font-weight:600;color:var(--ink);">${escapeHtml(h.topicTitle)}</div>
          <div style="color:var(--ink-soft);font-size:12px;font-family:'IBM Plex Mono',monospace;">${dateLabel}</div>
        </div>
        <div style="font-weight:700;color:${color};">${h.percent}%</div>
      </div>`;
    }).join('');
  }
}

document.getElementById('btn-back-dash').addEventListener('click', ()=>{ renderDashboard(); screen('screen-dashboard'); });

/* ==========================================================================
   ПОДРОБНОЕ ОБЪЯСНЕНИЕ ТЕМЫ
   ========================================================================== */
const TRANSLATION_LABEL = { ru:"Перевод:", en:"Translation:", uz:"Tarjima:", tj:"Тарҷума:" };
function openExplain(topicId){
  const topic = getTopic(topicId);
  const ex = EXPLAIN[topicId];
  document.getElementById('explain-level').textContent = ex ? ex.level : topic.title.toUpperCase();
  document.getElementById('explain-title').textContent = topic.title;
  if(ex){
    const lang = TR[App.lang] ? App.lang : 'ru';
    document.getElementById('explain-rule').textContent = ex.rule[lang] || ex.rule.ru;
    document.getElementById('explain-points').innerHTML = (ex.points[lang] || ex.points.ru).map(p=>`<li>${escapeHtml(p)}</li>`).join('');
    const label = TRANSLATION_LABEL[App.lang] || TRANSLATION_LABEL.ru;
    document.getElementById('explain-examples').innerHTML = ex.examples.map(e=>`
      <div class="example-line">
        <div class="en-ex">${escapeHtml(e.en)}</div>
        <div class="tr-ex">${label} ${escapeHtml(e.ru)}</div>
      </div>`).join('');
  } else {
    document.getElementById('explain-rule').textContent = topic.desc;
    document.getElementById('explain-points').innerHTML = '';
    document.getElementById('explain-examples').innerHTML = '';
  }
  document.getElementById('btn-explain-start').onclick = ()=>startTopicTest(topicId);
  screen('screen-explain');
}
document.getElementById('btn-explain-back').addEventListener('click', ()=>{ renderDashboard(); screen('screen-dashboard'); });

/* ==========================================================================
   ТЕСТ ПО ТЕМЕ
   ========================================================================== */
function startTopicTest(topicId){
  const topic = getTopic(topicId);
  const questions = generateTest(topicId, 20);
  App.currentTest = { topicId, topic, questions, index:0, correctCount:0, answers:[] };
  screen('screen-test');
  renderTestQuestion();
}

function renderTestQuestion(){
  const t = App.currentTest;
  const q = t.questions[t.index];
  document.getElementById('test-topic-label').textContent = t.topic.title.toUpperCase();
  document.getElementById('test-progress-label').textContent = `Вопрос ${t.index+1} / ${t.questions.length}`;
  document.getElementById('test-progress-fill').style.width = `${((t.index)/t.questions.length)*100}%`;
  document.getElementById('q-eyebrow').textContent = q.eyebrow;
  document.getElementById('q-text').innerHTML = escapeHtml(q.text).replace('___','<b>___</b>');
  const optsWrap = document.getElementById('q-options');
  const letters = ['A','B','C','D'];
  optsWrap.innerHTML = q.options.map((opt,i)=>`<button class="opt-btn" data-idx="${i}"><span class="letter">${letters[i]}</span><span>${escapeHtml(opt)}</span></button>`).join('');
  document.getElementById('btn-next-question').classList.add('hidden');
  Array.from(optsWrap.querySelectorAll('.opt-btn')).forEach(btn=>{
    btn.addEventListener('click', ()=>onAnswerTest(btn, q));
  });
}

function onAnswerTest(btn, q){
  const t = App.currentTest;
  const chosen = btn.querySelector('span:last-child').textContent;
  const isCorrect = chosen === q.correct;
  Array.from(document.querySelectorAll('#q-options .opt-btn')).forEach(b=>{
    b.disabled = true;
    const val = b.querySelector('span:last-child').textContent;
    if(val === q.correct) b.classList.add('correct');
    else if(b===btn) b.classList.add('wrong');
  });
  if(isCorrect) t.correctCount++;
  t.answers.push({ question:q.text, chosen, correct:q.correct, isCorrect });
  document.getElementById('btn-next-question').classList.remove('hidden');
}

document.getElementById('btn-next-question').addEventListener('click', ()=>{
  const t = App.currentTest;
  t.index++;
  if(t.index >= t.questions.length){
    finishTest();
  } else {
    renderTestQuestion();
  }
});
document.getElementById('btn-exit-test').addEventListener('click', ()=>{
  App.currentTest = null;
  renderDashboard();
  screen('screen-dashboard');
});

async function finishTest(){
  const t = App.currentTest;
  const percent = Math.round((t.correctCount / t.questions.length) * 100);
  const record = {
    date: new Date().toISOString(),
    kind:'topic_test',
    topicId: t.topicId,
    topicTitle: t.topic.title,
    correct: t.correctCount,
    total: t.questions.length,
    percent,
    wrongItems: t.answers.filter(a=>!a.isCorrect).slice(0,8)
  };
  App.history = await Store.addHistory(App.username, record);
  renderResults(record);
  screen('screen-results');
}

function renderResults(record){
  document.getElementById('score-ring').style.setProperty('--pct', record.percent);
  document.getElementById('score-value').textContent = `${record.correct}/${record.total}`;
  const scoreTitles = {
    ru:{great:'Отличный результат!', mid:'Неплохо, есть куда расти', low:'Стоит повторить тему'},
    en:{great:'Great result!', mid:'Not bad, room to grow', low:'This topic needs review'},
    uz:{great:'Ajoyib natija!', mid:"Yomon emas, o'sishga joy bor", low:'Mavzuni takrorlash kerak'},
    tj:{great:'Натиҷаи аъло!', mid:'Бад не, ҷои рушд ҳаст', low:'Мавзӯъро такрор кардан лозим'}
  };
  const stKey = record.percent>=80 ? 'great' : (record.percent>=50 ? 'mid' : 'low');
  document.getElementById('score-title').textContent = (scoreTitles[App.lang]||scoreTitles.ru)[stKey];
  document.getElementById('score-topic').textContent = record.topicTitle;

  const reviewTitles = { ru:'Разбор ошибок', en:'Mistakes review', uz:'Xatolar tahlili', tj:'Таҳлили хатогиҳо' };
  const allCorrectMsg = { ru:'Все ответы верны — ошибок нет! 🎉', en:'All answers correct — no mistakes! 🎉', uz:"Barcha javoblar to'g'ri — xato yo'q! 🎉", tj:'Ҳамаи ҷавобҳо дуруст — хато нест! 🎉' };
  const reviewWrap = document.getElementById('review-list');
  if(record.wrongItems && record.wrongItems.length){
    reviewWrap.innerHTML = `<h3 style="font-size:15px;margin:0 0 10px;">${reviewTitles[App.lang]||reviewTitles.ru}</h3>` + record.wrongItems.map(w=>`
      <div class="review-item">
        <div class="q">${escapeHtml(w.question)}</div>
        <div><span class="a-wrong">${escapeHtml(w.chosen)}</span><span class="a-right">✓ ${escapeHtml(w.correct)}</span></div>
      </div>`).join('');
  } else {
    reviewWrap.innerHTML = `<p style="color:var(--teal);font-weight:600;">${allCorrectMsg[App.lang]||allCorrectMsg.ru}</p>`;
  }

  document.getElementById('ai-feedback-text').textContent = 'Формируем персональный разбор результата…';
  fetchAIFeedback(record);

  document.getElementById('btn-retry-topic').onclick = ()=>{ startTopicTest(record.topicId); };
}

/* ---------------------------- ИИ-ОБРАТНАЯ СВЯЗЬ -------------------------- */
const FEEDBACK_LANG_NAME = { ru:"русском", en:"English", uz:"o'zbek", tj:"тоҷикӣ" };
async function fetchAIFeedback(record){
  const el = document.getElementById('ai-feedback-text');
  const wrongList = (record.wrongItems||[]).map(w=>`"${w.question}" — chosen "${w.chosen}", correct "${w.correct}"`).join('; ');
  const langName = FEEDBACK_LANG_NAME[App.lang] || FEEDBACK_LANG_NAME.ru;
  const prompt = `You are an experienced, friendly English teacher. A student just finished a test on the topic "${record.topicTitle}" and answered ${record.correct} out of ${record.total} questions correctly (${record.percent}%). ${wrongList ? 'Examples of mistakes: '+wrongList+'.' : 'There were no mistakes.'} Write short, personal feedback IN THE ${langName.toUpperCase()} LANGUAGE ONLY (3-4 sentences, friendly and motivating tone): mention their strengths, point out any pattern in the mistakes if there is one, and give one concrete tip on what to review next. Do not use markdown formatting, just plain text, and do not mix in other languages.`;
  try{
    const response = await fetch("https://api.anthropic.com/v1/messages", {
      method:"POST",
      headers:{ "Content-Type":"application/json" },
      body: JSON.stringify({
        model:"claude-sonnet-4-6",
        max_tokens:1000,
        messages:[{ role:"user", content: prompt }]
      })
    });
    const data = await response.json();
    const text = (data.content||[]).map(b=>b.text||'').join('\n').trim();
    el.textContent = text || fallbackFeedback(record);
  }catch(e){
    el.textContent = fallbackFeedback(record);
  }
}
const FALLBACK_FEEDBACK = {
  ru:{
    great:(r)=>`Превосходно! ${r.correct} из ${r.total} — вы уверенно владеете темой «${r.topicTitle}». Попробуйте более сложную тему или повторите этот тест ещё раз — вопросы будут другими.`,
    good:(r)=>`Хороший результат — ${r.correct} из ${r.total}. Тема «${r.topicTitle}» усвоена достаточно хорошо, но стоит ещё раз просмотреть вопросы, где были ошибки.`,
    mid:(r)=>`Результат ${r.correct} из ${r.total} — вы на верном пути, но тема «${r.topicTitle}» требует ещё практики. Повторите правило и пройдите тест ещё раз — вопросы будут новыми.`,
    low:(r)=>`Результат ${r.correct} из ${r.total} показывает, что тему «${r.topicTitle}» стоит изучить внимательнее. Разберите ошибки ниже и попробуйте снова.`
  },
  en:{
    great:(r)=>`Excellent! ${r.correct} out of ${r.total} — you have a strong grasp of "${r.topicTitle}". Try a more challenging topic, or retake this test — the questions will be different.`,
    good:(r)=>`Good result — ${r.correct} out of ${r.total}. You know "${r.topicTitle}" fairly well, but it's worth reviewing the questions you got wrong.`,
    mid:(r)=>`${r.correct} out of ${r.total} — you're on the right track, but "${r.topicTitle}" needs more practice. Review the rule and try the test again with fresh questions.`,
    low:(r)=>`${r.correct} out of ${r.total} shows that "${r.topicTitle}" needs more attention. Go through the mistakes below and give it another try.`
  },
  uz:{
    great:(r)=>`Ajoyib! ${r.correct} tadan ${r.total} — siz "${r.topicTitle}" mavzusini yaxshi bilasiz. Qiyinroq mavzuni sinab ko'ring yoki testni qayta topshiring — savollar boshqacha bo'ladi.`,
    good:(r)=>`Yaxshi natija — ${r.correct} tadan ${r.total}. "${r.topicTitle}" mavzusi yetarlicha o'zlashtirilgan, lekin xato qilingan savollarni qayta ko'rib chiqing.`,
    mid:(r)=>`${r.correct} tadan ${r.total} — to'g'ri yo'ldasiz, lekin "${r.topicTitle}" ko'proq mashq talab qiladi. Qoidani takrorlang va testni qayta topshiring.`,
    low:(r)=>`${r.correct} tadan ${r.total} natija "${r.topicTitle}" mavzusini diqqat bilan o'rganish kerakligini ko'rsatadi. Quyidagi xatolarni ko'rib chiqing va qayta urinib ko'ring.`
  },
  tj:{
    great:(r)=>`Аъло! ${r.correct} аз ${r.total} — шумо мавзӯи "${r.topicTitle}"-ро хуб медонед. Мавзӯи мураккабтарро санҷед ё тестро аз нав гузаронед — саволҳо дигар хоҳанд буд.`,
    good:(r)=>`Натиҷаи хуб — ${r.correct} аз ${r.total}. Мавзӯи "${r.topicTitle}" хуб азхуд карда шудааст, аммо саволҳои хатогиро аз нав дида бароед.`,
    mid:(r)=>`${r.correct} аз ${r.total} — шумо дар роҳи дуруст ҳастед, аммо мавзӯи "${r.topicTitle}" бештар машқ лозим дорад. Қоидаро такрор кунед ва тестро аз нав гузаронед.`,
    low:(r)=>`Натиҷаи ${r.correct} аз ${r.total} нишон медиҳад, ки мавзӯи "${r.topicTitle}" бояд бодиққаттар омӯхта шавад. Хатогиҳои дар поён овардашударо дида бароед ва аз нав кӯшиш кунед.`
  }
};
function fallbackFeedback(record){
  const dict = FALLBACK_FEEDBACK[App.lang] || FALLBACK_FEEDBACK.ru;
  if(record.percent>=90) return dict.great(record);
  if(record.percent>=70) return dict.good(record);
  if(record.percent>=50) return dict.mid(record);
  return dict.low(record);
}

/* ==========================================================================
   LISTENING
   ========================================================================== */
document.getElementById('btn-start-listening').addEventListener('click', startListening);
function startListening(){
  const items = pickN(LISTENING_BANK, 15);
  App.currentListen = { items, index:0, correctCount:0, answered:false };
  screen('screen-listening');
  renderSpeedRow();
  renderListenItem();
}
function renderSpeedRow(){
  const speeds = [{v:0.75,l:'0.75x'},{v:0.95,l:'1x'},{v:1.25,l:'1.25x'}];
  const wrap = document.getElementById('speed-row');
  wrap.innerHTML = speeds.map(s=>`<button data-rate="${s.v}" class="${App.listenRate===s.v?'active':''}">${s.l}</button>`).join('');
  wrap.querySelectorAll('button').forEach(btn=>{
    btn.addEventListener('click', ()=>{
      App.listenRate = parseFloat(btn.getAttribute('data-rate'));
      renderSpeedRow();
      const st = App.currentListen;
      if(st) playListeningAudio(st.items[st.index].text);
    });
  });
}
function renderListenItem(){
  const st = App.currentListen;
  const item = st.items[st.index];
  document.getElementById('listen-progress-label').textContent = `Фрагмент ${st.index+1} / ${st.items.length}`;
  document.getElementById('listen-progress-fill').style.width = `${(st.index/st.items.length)*100}%`;
  document.getElementById('listen-question').textContent = item.q;
  document.getElementById('listen-transcript').style.display = 'none';
  document.getElementById('listen-transcript').textContent = item.text;
  const optsWrap = document.getElementById('listen-options');
  const letters = ['A','B','C','D'];
  optsWrap.innerHTML = item.options.map((opt,i)=>`<button class="opt-btn" data-idx="${i}"><span class="letter">${letters[i]}</span><span>${escapeHtml(opt)}</span></button>`).join('');
  document.getElementById('btn-next-listen').classList.add('hidden');
  Array.from(optsWrap.querySelectorAll('.opt-btn')).forEach(btn=>{
    btn.addEventListener('click', ()=>onAnswerListen(btn, item));
  });
  playListeningAudio(item.text);
}
let listenVoicesReady = false;
function ensureVoicesLoaded(){
  return new Promise(resolve=>{
    if(!('speechSynthesis' in window)){ resolve(); return; }
    const voices = window.speechSynthesis.getVoices();
    if(voices && voices.length){ listenVoicesReady = true; resolve(); return; }
    window.speechSynthesis.onvoiceschanged = ()=>{ listenVoicesReady = true; resolve(); };
    setTimeout(resolve, 800); // защита от браузеров, не поддерживающих onvoiceschanged
  });
}
async function playListeningAudio(text){
  if(!('speechSynthesis' in window)) { showToast('Синтез речи не поддерживается в этом браузере'); return; }
  await ensureVoicesLoaded();
  window.speechSynthesis.cancel();
  const u = new SpeechSynthesisUtterance(text);
  u.lang = 'en-US';
  u.rate = App.listenRate || 0.95;
  const voices = window.speechSynthesis.getVoices();
  const enVoice = voices.find(v=>v.lang && v.lang.toLowerCase().startsWith('en'));
  if(enVoice) u.voice = enVoice;
  const btn = document.getElementById('btn-play-audio');
  btn.classList.add('speaking');
  u.onend = ()=>btn.classList.remove('speaking');
  u.onerror = ()=>btn.classList.remove('speaking');
  // небольшой таймаут перед запуском — надёжнее в некоторых браузерах после cancel()
  setTimeout(()=>{ try{ window.speechSynthesis.speak(u); }catch(e){ btn.classList.remove('speaking'); } }, 60);
}
document.getElementById('btn-play-audio').addEventListener('click', ()=>{
  const st = App.currentListen;
  if(st) playListeningAudio(st.items[st.index].text);
});
document.getElementById('btn-replay-audio').addEventListener('click', ()=>{
  const st = App.currentListen;
  if(st) playListeningAudio(st.items[st.index].text);
});
document.getElementById('btn-show-transcript').addEventListener('click', ()=>{
  const box = document.getElementById('listen-transcript');
  box.style.display = box.style.display==='none' ? 'block' : 'none';
});
function onAnswerListen(btn, item){
  const st = App.currentListen;
  if(st.answered) return;
  st.answered = true;
  const chosen = btn.querySelector('span:last-child').textContent;
  const isCorrect = chosen === item.correct;
  Array.from(document.querySelectorAll('#listen-options .opt-btn')).forEach(b=>{
    b.disabled = true;
    const val = b.querySelector('span:last-child').textContent;
    if(val === item.correct) b.classList.add('correct');
    else if(b===btn) b.classList.add('wrong');
  });
  if(isCorrect) st.correctCount++;
  document.getElementById('btn-next-listen').classList.remove('hidden');
}
document.getElementById('btn-next-listen').addEventListener('click', async ()=>{
  const st = App.currentListen;
  st.index++;
  st.answered = false;
  if(st.index >= st.items.length){
    const percent = Math.round((st.correctCount/st.items.length)*100);
    const record = {
      date:new Date().toISOString(), kind:'listening', topicId:'listening', topicTitle:'Listening — аудирование',
      correct: st.correctCount, total: st.items.length, percent, wrongItems:[]
    };
    App.history = await Store.addHistory(App.username, record);
    renderResults(record);
    document.getElementById('btn-retry-topic').onclick = ()=>{ startListening(); };
    screen('screen-results');
  } else {
    renderListenItem();
  }
});
document.getElementById('btn-exit-listening').addEventListener('click', ()=>{
  window.speechSynthesis && window.speechSynthesis.cancel();
  App.currentListen = null;
  renderDashboard();
  screen('screen-dashboard');
});

/* ==========================================================================
   SPEAKING
   ========================================================================== */
const SpeechRecCtor = window.SpeechRecognition || window.webkitSpeechRecognition;
const isSecureCtx = window.isSecureContext !== false; // https или localhost

document.getElementById('btn-start-speaking').addEventListener('click', startSpeaking);
function startSpeaking(){
  const items = pickN(SPEAKING_BANK, 12);
  App.currentSpeak = { items, index:0, scores:[] };
  screen('screen-speaking');
  const supported = !!SpeechRecCtor && isSecureCtx;
  document.getElementById('speak-unsupported').classList.toggle('hidden', supported);
  document.getElementById('btn-mic').disabled = !supported;
  renderSpeakItem();
}
function renderSpeakItem(){
  const st = App.currentSpeak;
  const item = st.items[st.index];
  document.getElementById('speak-progress-label').textContent = `Фраза ${st.index+1} / ${st.items.length}`;
  document.getElementById('speak-progress-fill').style.width = `${(st.index/st.items.length)*100}%`;
  document.getElementById('speak-ru').textContent = item.ru;
  document.getElementById('speak-en').textContent = item.en;
  document.getElementById('speak-result').style.display = 'none';
  document.getElementById('mic-status').textContent = t2('mic_status_default');
  document.getElementById('btn-next-speak').classList.add('hidden');
  document.getElementById('btn-mic').classList.remove('listening');
}
document.getElementById('btn-hear-phrase').addEventListener('click', ()=>{
  const st = App.currentSpeak;
  if(!st) return;
  playListeningAudio(st.items[st.index].en);
});
function wordOverlapScore(target, said){
  const norm = s => s.toLowerCase().replace(/[^a-z\s']/g,'').split(/\s+/).filter(Boolean);
  const t = norm(target), sSaid = norm(said);
  if(t.length===0) return 0;
  let matched = 0;
  const saidCopy = sSaid.slice();
  t.forEach(w=>{
    const idx = saidCopy.indexOf(w);
    if(idx>-1){ matched++; saidCopy.splice(idx,1); }
  });
  return Math.round((matched/t.length)*100);
}
async function requestMicPermission(){
  if(!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia){
    return true; // нет способа проверить заранее — пробуем через SpeechRecognition напрямую
  }
  try{
    const stream = await navigator.mediaDevices.getUserMedia({ audio:true });
    stream.getTracks().forEach(tr=>tr.stop());
    return true;
  }catch(e){
    return false;
  }
}
document.getElementById('btn-mic').addEventListener('click', async ()=>{
  if(!SpeechRecCtor){ showToast(t2('speak_unsupported')); return; }
  if(!isSecureCtx){ showToast(t2('mic_status_denied')); return; }
  if(App.recognizing){ App.speechRecognition && App.speechRecognition.stop(); return; }

  const micBtn = document.getElementById('btn-mic');
  document.getElementById('mic-status').textContent = '…';
  micBtn.disabled = true;
  const granted = await requestMicPermission();
  micBtn.disabled = false;
  if(!granted){
    document.getElementById('mic-status').textContent = t2('mic_status_denied');
    return;
  }

  const rec = new SpeechRecCtor();
  rec.lang = 'en-US';
  rec.continuous = false;
  rec.interimResults = false;
  rec.maxAlternatives = 1;
  App.speechRecognition = rec;
  App.recognizing = true;
  micBtn.classList.add('listening');
  document.getElementById('mic-status').textContent = t2('mic_status_listening');

  let gotResult = false;
  const safetyTimeout = setTimeout(()=>{
    if(App.recognizing){ try{ rec.stop(); }catch(e){} }
  }, 9000);

  rec.onresult = (e)=>{
    gotResult = true;
    const said = e.results[0][0].transcript;
    handleSpeechResult(said);
  };
  rec.onerror = (e)=>{
    let msg = t2('mic_status_error');
    if(e.error === 'not-allowed' || e.error === 'permission-denied') msg = t2('mic_status_denied');
    else if(e.error === 'no-speech') msg = t2('mic_status_noresult');
    document.getElementById('mic-status').textContent = msg;
  };
  rec.onend = ()=>{
    clearTimeout(safetyTimeout);
    App.recognizing = false;
    micBtn.classList.remove('listening');
    if(!gotResult && document.getElementById('mic-status').textContent === t2('mic_status_listening')){
      document.getElementById('mic-status').textContent = t2('mic_status_noresult');
    }
  };
  try{
    rec.start();
  }catch(e){
    App.recognizing = false;
    micBtn.classList.remove('listening');
    document.getElementById('mic-status').textContent = t2('mic_status_error');
  }
});
function handleSpeechResult(said){
  const st = App.currentSpeak;
  const item = st.items[st.index];
  const score = wordOverlapScore(item.en, said);
  st.scores.push(score);
  document.getElementById('speak-result').style.display = 'block';
  document.getElementById('speak-said').textContent = said;
  document.getElementById('speak-match-fill').style.width = score+'%';
  document.getElementById('speak-match-fill').style.background = score>=75 ? 'var(--teal)' : (score>=45 ? 'var(--marigold)' : 'var(--coral)');
  const matchMsgs = {
    ru:{great:'Отличное совпадение!', mid:'Неплохо, но есть расхождения', low:'Попробуйте произнести фразу ещё раз, чётче'},
    en:{great:'Excellent match!', mid:'Not bad, some differences', low:'Try saying the phrase again, more clearly'},
    uz:{great:"Ajoyib mos keldi!", mid:"Yomon emas, farqlar bor", low:"Iborani yana aniqroq talaffuz qiling"},
    tj:{great:'Мутобиқати аъло!', mid:'Бад не, фарқият ҳаст', low:'Ибораро дубора возеҳтар гӯед'}
  };
  const m = matchMsgs[App.lang] || matchMsgs.ru;
  document.getElementById('speak-match-text').textContent = score>=75 ? m.great : (score>=45 ? m.mid : m.low);
  document.getElementById('mic-status').textContent = t2('mic_status_ready');
  document.getElementById('btn-next-speak').classList.remove('hidden');
}
document.getElementById('btn-next-speak').addEventListener('click', async ()=>{
  const st = App.currentSpeak;
  st.index++;
  if(st.index >= st.items.length){
    const avg = st.scores.length ? Math.round(st.scores.reduce((a,b)=>a+b,0)/st.scores.length) : 0;
    const record = {
      date:new Date().toISOString(), kind:'speaking', topicId:'speaking', topicTitle:'Speaking — говорение',
      correct: Math.round(avg/100*st.items.length), total: st.items.length, percent: avg, wrongItems:[]
    };
    App.history = await Store.addHistory(App.username, record);
    renderResults(record);
    document.getElementById('btn-retry-topic').onclick = ()=>{ startSpeaking(); };
    screen('screen-results');
  } else {
    renderSpeakItem();
  }
});
document.getElementById('btn-exit-speaking').addEventListener('click', ()=>{
  App.speechRecognition && App.speechRecognition.stop();
  App.currentSpeak = null;
  renderDashboard();
  screen('screen-dashboard');
});

</script>
</body>
</html>
