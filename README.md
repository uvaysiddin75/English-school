<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EnglishMaster Pro</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #0a0e1a;
  --surface: #111827;
  --surface2: #1a2236;
  --border: #1e2d4a;
  --accent: #00d4ff;
  --accent2: #7c3aed;
  --accent3: #10b981;
  --accent4: #f59e0b;
  --accent5: #ef4444;
  --text: #e2e8f0;
  --text2: #94a3b8;
  --text3: #475569;
  --gold: #fbbf24;
  --radius: 16px;
  --radius-sm: 10px;
  --shadow: 0 4px 32px rgba(0,212,255,0.08);
}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Sora',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow-x:hidden}
::-webkit-scrollbar{width:6px}::-webkit-scrollbar-track{background:var(--surface)}::-webkit-scrollbar-thumb{background:var(--border);border-radius:3px}

/* NAV */
.topnav{position:fixed;top:0;left:0;right:0;z-index:100;background:rgba(10,14,26,0.92);backdrop-filter:blur(18px);border-bottom:1px solid var(--border);padding:0 24px;height:62px;display:flex;align-items:center;justify-content:space-between}
.logo{font-size:1.3rem;font-weight:800;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;letter-spacing:-0.5px}
.nav-right{display:flex;align-items:center;gap:12px}
.lang-btn{background:var(--surface2);border:1px solid var(--border);color:var(--text);padding:6px 14px;border-radius:8px;cursor:pointer;font-family:'Sora',sans-serif;font-size:.8rem;font-weight:600;transition:.2s}
.lang-btn:hover,.lang-btn.active{background:var(--accent);color:#000;border-color:var(--accent)}
.xp-badge{background:linear-gradient(135deg,var(--gold),#f97316);color:#000;padding:5px 14px;border-radius:20px;font-weight:700;font-size:.82rem}

/* SIDEBAR */
.layout{display:flex;padding-top:62px;min-height:100vh}
.sidebar{width:220px;background:var(--surface);border-right:1px solid var(--border);position:fixed;top:62px;bottom:0;left:0;overflow-y:auto;padding:20px 12px;z-index:50}
.sidebar-section{margin-bottom:8px}
.sidebar-label{font-size:.68rem;font-weight:700;color:var(--text3);letter-spacing:1.5px;text-transform:uppercase;padding:8px 10px 4px}
.nav-item{display:flex;align-items:center;gap:10px;padding:10px 12px;border-radius:10px;cursor:pointer;color:var(--text2);font-size:.86rem;font-weight:500;transition:.18s;border:1px solid transparent}
.nav-item:hover{background:var(--surface2);color:var(--text)}
.nav-item.active{background:linear-gradient(135deg,rgba(0,212,255,.15),rgba(124,58,237,.1));color:var(--accent);border-color:rgba(0,212,255,.25)}
.nav-item .icon{font-size:1.1rem;min-width:22px}
.main{margin-left:220px;flex:1;padding:28px 32px}

/* HERO */
.hero{background:linear-gradient(135deg,rgba(0,212,255,.07),rgba(124,58,237,.07));border:1px solid var(--border);border-radius:var(--radius);padding:32px 36px;margin-bottom:28px;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;top:-60px;right:-60px;width:240px;height:240px;background:radial-gradient(circle,rgba(0,212,255,.12),transparent 70%);pointer-events:none}
.hero h1{font-size:2rem;font-weight:800;margin-bottom:8px;background:linear-gradient(135deg,#fff,var(--accent));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.hero p{color:var(--text2);font-size:.95rem;margin-bottom:20px}
.stats-row{display:flex;gap:20px;flex-wrap:wrap}
.stat-card{background:rgba(255,255,255,.04);border:1px solid var(--border);border-radius:12px;padding:14px 20px;flex:1;min-width:120px}
.stat-card .val{font-size:1.5rem;font-weight:800;color:var(--accent)}
.stat-card .lbl{font-size:.75rem;color:var(--text3);margin-top:2px}

/* SECTION */
.section{display:none}
.section.active{display:block}
.section-title{font-size:1.35rem;font-weight:800;margin-bottom:6px}
.section-subtitle{color:var(--text2);font-size:.88rem;margin-bottom:22px}

/* TOPICS GRID */
.topics-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px}
.topic-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:22px;cursor:pointer;transition:.22s;position:relative;overflow:hidden}
.topic-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--accent),var(--accent2));transform:scaleX(0);transition:.3s;transform-origin:left}
.topic-card:hover{background:var(--surface2);border-color:var(--accent);transform:translateY(-2px);box-shadow:0 8px 32px rgba(0,212,255,.12)}
.topic-card:hover::after{transform:scaleX(1)}
.topic-icon{font-size:2rem;margin-bottom:12px}
.topic-card h3{font-size:1rem;font-weight:700;margin-bottom:6px}
.topic-card p{font-size:.8rem;color:var(--text2);line-height:1.5;margin-bottom:14px}
.topic-meta{display:flex;align-items:center;justify-content:space-between}
.level-tag{padding:3px 10px;border-radius:20px;font-size:.72rem;font-weight:700}
.level-beginner{background:rgba(16,185,129,.15);color:var(--accent3)}
.level-intermediate{background:rgba(245,158,11,.15);color:var(--accent4)}
.level-advanced{background:rgba(239,68,68,.15);color:var(--accent5)}
.progress-mini{height:5px;background:var(--border);border-radius:3px;flex:1;margin:0 10px;overflow:hidden}
.progress-mini-fill{height:100%;background:linear-gradient(90deg,var(--accent),var(--accent2));border-radius:3px;transition:.4s}

/* TOPIC DETAIL */
.back-btn{display:inline-flex;align-items:center;gap:8px;color:var(--accent);cursor:pointer;font-size:.88rem;font-weight:600;margin-bottom:20px;border:none;background:none;padding:0}
.back-btn:hover{opacity:.75}
.topic-detail-header{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:28px;margin-bottom:20px}
.content-box{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:26px;margin-bottom:18px;line-height:1.8}
.content-box h2{font-size:1.15rem;font-weight:700;margin-bottom:14px;color:var(--accent)}
.content-box h3{font-size:1rem;font-weight:700;margin:18px 0 10px;color:var(--accent4)}
.content-box p{color:var(--text2);margin-bottom:10px;font-size:.9rem}
.example-box{background:rgba(0,212,255,.05);border-left:3px solid var(--accent);padding:14px 18px;border-radius:0 10px 10px 0;margin:12px 0;font-size:.88rem}
.example-box .en{color:var(--text);font-weight:600;margin-bottom:4px}
.example-box .tr{color:var(--text2)}
.vocab-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:10px;margin:14px 0}
.vocab-card{background:var(--surface2);border:1px solid var(--border);border-radius:10px;padding:12px;cursor:pointer;transition:.18s}
.vocab-card:hover{border-color:var(--accent);background:rgba(0,212,255,.06)}
.vocab-word{font-weight:700;color:var(--accent);font-size:.95rem}
.vocab-tr{color:var(--text2);font-size:.8rem;margin-top:3px}
.vocab-ex{color:var(--text3);font-size:.75rem;font-style:italic;margin-top:4px}

/* QUIZ */
.quiz-container{max-width:680px}
.quiz-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:20px}
.quiz-progress{flex:1;height:8px;background:var(--border);border-radius:4px;overflow:hidden;margin:0 16px}
.quiz-progress-fill{height:100%;background:linear-gradient(90deg,var(--accent),var(--accent2));transition:.4s}
.question-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:28px;margin-bottom:16px}
.question-type{font-size:.72rem;font-weight:700;color:var(--accent2);letter-spacing:1px;text-transform:uppercase;margin-bottom:10px}
.question-text{font-size:1.1rem;font-weight:600;margin-bottom:22px;line-height:1.5}
.options{display:grid;gap:10px}
.option{background:var(--surface2);border:1.5px solid var(--border);border-radius:10px;padding:13px 18px;cursor:pointer;transition:.18s;font-size:.9rem;font-weight:500}
.option:hover:not(.disabled){background:rgba(0,212,255,.08);border-color:var(--accent)}
.option.correct{background:rgba(16,185,129,.12);border-color:var(--accent3);color:var(--accent3)}
.option.wrong{background:rgba(239,68,68,.10);border-color:var(--accent5);color:var(--accent5)}
.option.disabled{cursor:default}
.fill-input{width:100%;background:var(--surface2);border:1.5px solid var(--border);border-radius:10px;padding:13px 18px;color:var(--text);font-family:'Sora',sans-serif;font-size:.95rem;outline:none;transition:.18s}
.fill-input:focus{border-color:var(--accent)}
.btn{display:inline-flex;align-items:center;gap:8px;padding:11px 24px;border-radius:10px;font-family:'Sora',sans-serif;font-weight:700;font-size:.9rem;cursor:pointer;border:none;transition:.2s}
.btn-primary{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff}
.btn-primary:hover{opacity:.88;transform:translateY(-1px)}
.btn-outline{background:transparent;border:1.5px solid var(--border);color:var(--text2)}
.btn-outline:hover{border-color:var(--accent);color:var(--accent)}
.result-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:36px;text-align:center;max-width:480px;margin:0 auto}
.result-score{font-size:4rem;font-weight:800;margin:16px 0;background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.result-grade{font-size:1.2rem;font-weight:700;margin-bottom:8px}
.result-msg{color:var(--text2);font-size:.9rem;margin-bottom:24px}

/* LISTENING */
.audio-player{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:24px;margin-bottom:20px}
.audio-controls{display:flex;align-items:center;gap:14px;margin-bottom:16px}
.play-btn{width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent2));border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:1.2rem;color:#fff;transition:.2s;flex-shrink:0}
.play-btn:hover{transform:scale(1.07)}
.audio-track{flex:1}
.audio-title{font-weight:700;font-size:.95rem;margin-bottom:4px}
.audio-subtitle{color:var(--text2);font-size:.78rem}
.waveform{height:40px;display:flex;align-items:center;gap:2px;margin:14px 0}
.waveform-bar{flex:1;background:var(--border);border-radius:2px;transition:.15s;cursor:pointer}
.waveform-bar.active{background:var(--accent)}
.waveform-bar:hover{background:rgba(0,212,255,.5)}
.transcript-box{background:var(--surface2);border:1px solid var(--border);border-radius:12px;padding:18px;font-size:.88rem;color:var(--text2);line-height:1.8;margin-top:14px;max-height:200px;overflow-y:auto}
.transcript-box .highlight{color:var(--accent);font-weight:600}

/* SPEAKING */
.speaking-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:28px;margin-bottom:16px;max-width:680px}
.mic-area{text-align:center;padding:30px}
.mic-btn{width:80px;height:80px;border-radius:50%;background:linear-gradient(135deg,#ef4444,#dc2626);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:2rem;margin:0 auto 16px;transition:.2s;box-shadow:0 0 0 0 rgba(239,68,68,.4)}
.mic-btn.recording{animation:pulse 1.2s infinite;background:linear-gradient(135deg,#22c55e,#16a34a);box-shadow:0 0 0 0 rgba(34,197,94,.4)}
@keyframes pulse{0%{box-shadow:0 0 0 0 rgba(34,197,94,.4)}70%{box-shadow:0 0 0 20px rgba(34,197,94,0)}100%{box-shadow:0 0 0 0 rgba(34,197,94,0)}}
.ai-message{background:rgba(0,212,255,.07);border:1px solid rgba(0,212,255,.2);border-radius:12px;padding:16px 20px;margin-bottom:16px;font-size:.9rem;line-height:1.6}
.user-message{background:rgba(124,58,237,.07);border:1px solid rgba(124,58,237,.2);border-radius:12px;padding:16px 20px;margin-bottom:16px;font-size:.9rem;line-height:1.6;text-align:right}
.chat-log{max-height:360px;overflow-y:auto;padding:4px 0;margin-bottom:16px}
.typing-indicator{display:flex;gap:4px;padding:12px 16px}
.typing-dot{width:8px;height:8px;border-radius:50%;background:var(--accent);animation:typing .8s infinite}
.typing-dot:nth-child(2){animation-delay:.15s}
.typing-dot:nth-child(3){animation-delay:.3s}
@keyframes typing{0%,100%{opacity:.3}50%{opacity:1}}

/* VOCABULARY */
.vocab-section-tabs{display:flex;gap:8px;margin-bottom:20px;flex-wrap:wrap}
.vtab{padding:8px 18px;border-radius:8px;cursor:pointer;font-size:.83rem;font-weight:600;border:1.5px solid var(--border);color:var(--text2);transition:.18s}
.vtab.active,.vtab:hover{background:var(--accent);color:#000;border-color:var(--accent)}
.vocab-search{width:100%;max-width:400px;background:var(--surface2);border:1.5px solid var(--border);border-radius:10px;padding:11px 16px;color:var(--text);font-family:'Sora',sans-serif;font-size:.9rem;outline:none;margin-bottom:18px}
.vocab-search:focus{border-color:var(--accent)}
.big-vocab-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:12px}
.big-vocab-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:16px;cursor:pointer;transition:.2s;position:relative}
.big-vocab-card:hover{border-color:var(--accent);transform:translateY(-2px)}
.big-vocab-card .word{font-size:1.1rem;font-weight:800;color:var(--accent);margin-bottom:2px}
.big-vocab-card .phonetic{color:var(--text3);font-size:.78rem;margin-bottom:6px;font-family:'Space Mono',monospace}
.big-vocab-card .meaning{color:var(--text2);font-size:.83rem;margin-bottom:6px}
.big-vocab-card .example{color:var(--text3);font-size:.77rem;font-style:italic}
.big-vocab-card .category{position:absolute;top:10px;right:10px;font-size:.68rem;font-weight:700;padding:2px 8px;border-radius:20px;background:rgba(124,58,237,.15);color:var(--accent2)}

/* AI CHAT */
.ai-chat{max-width:700px}
.chat-messages{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:20px;height:420px;overflow-y:auto;margin-bottom:14px;display:flex;flex-direction:column;gap:12px}
.ai-msg{background:rgba(0,212,255,.07);border:1px solid rgba(0,212,255,.15);border-radius:0 12px 12px 12px;padding:12px 16px;font-size:.88rem;line-height:1.6;max-width:85%;align-self:flex-start}
.user-msg{background:rgba(124,58,237,.1);border:1px solid rgba(124,58,237,.2);border-radius:12px 0 12px 12px;padding:12px 16px;font-size:.88rem;line-height:1.6;max-width:85%;align-self:flex-end}
.ai-msg .ai-label{font-size:.7rem;font-weight:700;color:var(--accent);margin-bottom:5px}
.chat-input-row{display:flex;gap:10px}
.chat-input{flex:1;background:var(--surface2);border:1.5px solid var(--border);border-radius:10px;padding:12px 16px;color:var(--text);font-family:'Sora',sans-serif;font-size:.9rem;outline:none}
.chat-input:focus{border-color:var(--accent)}

/* LEADERBOARD */
.leaderboard{max-width:600px}
.lb-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:14px 20px;margin-bottom:10px;display:flex;align-items:center;gap:16px;transition:.18s}
.lb-card:hover{border-color:var(--accent);background:var(--surface2)}
.lb-rank{font-size:1.1rem;font-weight:800;min-width:32px;color:var(--text3)}
.lb-rank.top1{color:var(--gold)}
.lb-rank.top2{color:#94a3b8}
.lb-rank.top3{color:#b45309}
.lb-avatar{width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;flex-shrink:0}
.lb-name{font-weight:700;flex:1}
.lb-xp{font-weight:800;color:var(--accent);font-size:.95rem}
.lb-badge{padding:3px 10px;border-radius:20px;font-size:.72rem;font-weight:700;margin-left:8px}

/* MODAL */
.modal{position:fixed;inset:0;z-index:200;background:rgba(0,0,0,.6);backdrop-filter:blur(8px);display:none;align-items:center;justify-content:center}
.modal.open{display:flex}
.modal-box{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:32px;max-width:500px;width:90%;max-height:85vh;overflow-y:auto;position:relative}
.modal-close{position:absolute;top:16px;right:16px;background:none;border:none;color:var(--text2);font-size:1.4rem;cursor:pointer}

/* TOAST */
.toast{position:fixed;bottom:28px;right:28px;z-index:300;background:var(--surface2);border:1px solid var(--border);border-radius:12px;padding:14px 20px;font-size:.88rem;font-weight:600;transform:translateY(80px);opacity:0;transition:.3s;pointer-events:none}
.toast.show{transform:translateY(0);opacity:1}
.toast.success{border-color:var(--accent3);color:var(--accent3)}
.toast.error{border-color:var(--accent5);color:var(--accent5)}

/* PROGRESS RINGS */
.progress-ring{display:inline-block;position:relative;width:80px;height:80px}
.progress-ring svg{transform:rotate(-90deg)}
.progress-ring circle{fill:none;stroke-width:6;stroke-linecap:round}
.ring-bg{stroke:var(--border)}
.ring-fill{stroke:var(--accent);transition:stroke-dashoffset .6s ease}
.ring-text{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-weight:800;font-size:.95rem}

/* LOADING */
.loading{display:flex;align-items:center;justify-content:center;gap:10px;padding:40px;color:var(--text2)}
.loading-spinner{width:28px;height:28px;border:3px solid var(--border);border-top-color:var(--accent);border-radius:50%;animation:spin .7s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.tag{display:inline-block;padding:4px 12px;border-radius:20px;font-size:.75rem;font-weight:700;margin:2px}

/* RESPONSIVE */
@media(max-width:900px){.sidebar{transform:translateX(-100%)}.main{margin-left:0;padding:18px 16px}}
</style>
</head>
<body>

<!-- TOP NAV -->
<nav class="topnav">
  <div class="logo">🎓 EnglishMaster</div>
  <div class="nav-right">
    <button class="lang-btn active" onclick="setLang('en')">EN</button>
    <button class="lang-btn" onclick="setLang('ru')">RU</button>
    <button class="lang-btn" onclick="setLang('uz')">UZ</button>
    <div class="xp-badge" id="xp-badge">⚡ 0 XP</div>
  </div>
</nav>

<!-- SIDEBAR -->
<div class="sidebar">
  <div class="sidebar-section">
    <div class="sidebar-label" data-t="learn">LEARN</div>
    <div class="nav-item active" onclick="showSection('home')" id="nav-home">
      <span class="icon">🏠</span><span data-t="home">Home</span>
    </div>
    <div class="nav-item" onclick="showSection('topics')" id="nav-topics">
      <span class="icon">📚</span><span data-t="topics">Topics</span>
    </div>
    <div class="nav-item" onclick="showSection('vocabulary')" id="nav-vocabulary">
      <span class="icon">📖</span><span data-t="vocabulary">Vocabulary</span>
    </div>
    <div class="nav-item" onclick="showSection('listening')" id="nav-listening">
      <span class="icon">🎧</span><span data-t="listening">Listening</span>
    </div>
    <div class="nav-item" onclick="showSection('speaking')" id="nav-speaking">
      <span class="icon">🎤</span><span data-t="speaking">Speaking</span>
    </div>
    <div class="nav-item" onclick="showSection('reading')" id="nav-reading">
      <span class="icon">📰</span><span data-t="reading">Reading</span>
    </div>
    <div class="nav-item" onclick="showSection('writing')" id="nav-writing">
      <span class="icon">✍️</span><span data-t="writing">Writing</span>
    </div>
  </div>
  <div class="sidebar-section">
    <div class="sidebar-label" data-t="compete">COMPETE</div>
    <div class="nav-item" onclick="showSection('leaderboard')" id="nav-leaderboard">
      <span class="icon">🏆</span><span data-t="leaderboard">Leaderboard</span>
    </div>
    <div class="nav-item" onclick="showSection('ai')" id="nav-ai">
      <span class="icon">🤖</span><span data-t="aiTutor">AI Tutor</span>
    </div>
  </div>
</div>

<!-- MAIN CONTENT -->
<div class="main">

<!-- HOME -->
<div id="section-home" class="section active">
  <div class="hero">
    <h1 data-t="heroTitle">Master English Like a Pro</h1>
    <p data-t="heroSub">Topics, tests, listening, speaking — all powered by real AI</p>
    <div class="stats-row">
      <div class="stat-card"><div class="val" id="stat-topics">0</div><div class="lbl" data-t="topicsCompleted">Topics Completed</div></div>
      <div class="stat-card"><div class="val" id="stat-score">0%</div><div class="lbl" data-t="avgScore">Avg Test Score</div></div>
      <div class="stat-card"><div class="val" id="stat-streak">0🔥</div><div class="lbl" data-t="dayStreak">Day Streak</div></div>
      <div class="stat-card"><div class="val" id="stat-words">0</div><div class="lbl" data-t="wordsLearned">Words Learned</div></div>
    </div>
  </div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px">
    <div class="topic-card" onclick="showSection('topics')" style="cursor:pointer">
      <div class="topic-icon">🎯</div>
      <h3 data-t="startLearning">Start Learning</h3>
      <p data-t="startLearningSub">Choose a topic and take a test</p>
    </div>
    <div class="topic-card" onclick="showSection('ai')" style="cursor:pointer">
      <div class="topic-icon">🤖</div>
      <h3 data-t="chatAI">Chat with AI</h3>
      <p data-t="chatAISub">Practice English 24/7 with smart AI</p>
    </div>
    <div class="topic-card" onclick="showSection('vocabulary')" style="cursor:pointer">
      <div class="topic-icon">📖</div>
      <h3 data-t="vocabulary">Vocabulary</h3>
      <p data-t="vocabularySub">Learn thousands of words by category</p>
    </div>
    <div class="topic-card" onclick="showSection('leaderboard')" style="cursor:pointer">
      <div class="topic-icon">🏆</div>
      <h3 data-t="leaderboard">Leaderboard</h3>
      <p data-t="leaderboardSub">Compete with learners worldwide</p>
    </div>
  </div>
</div>

<!-- TOPICS -->
<div id="section-topics" class="section">
  <div id="topics-list-view">
    <div class="section-title" data-t="allTopics">All Topics</div>
    <div class="section-subtitle" data-t="allTopicsSub">Choose a topic to study, then take a 30-question test</div>
    <div class="topics-grid" id="topics-grid"></div>
  </div>
  <div id="topic-detail-view" style="display:none">
    <button class="back-btn" onclick="backToTopics()">← <span data-t="backToTopics">Back to Topics</span></button>
    <div id="topic-detail-content"></div>
  </div>
</div>

<!-- VOCABULARY -->
<div id="section-vocabulary" class="section">
  <div class="section-title" data-t="vocabulary">Vocabulary</div>
  <div class="section-subtitle" data-t="vocabSub">Thousands of words organized by topic and level</div>
  <div class="vocab-section-tabs" id="vocab-tabs"></div>
  <input class="vocab-search" id="vocab-search" placeholder="🔍 Search words..." oninput="filterVocab()">
  <div class="big-vocab-grid" id="vocab-grid"></div>
</div>

<!-- LISTENING -->
<div id="section-listening" class="section">
  <div class="section-title" data-t="listening">Listening</div>
  <div class="section-subtitle" data-t="listeningSub">Real audio exercises with comprehension tests</div>
  <div id="listening-list"></div>
</div>

<!-- SPEAKING -->
<div id="section-speaking" class="section">
  <div class="section-title" data-t="speaking">Speaking Practice</div>
  <div class="section-subtitle" data-t="speakingSub">Have real conversations with AI — it speaks and you answer!</div>
  <div class="speaking-card">
    <div style="display:flex;align-items:center;gap:12px;margin-bottom:18px">
      <div style="width:44px;height:44px;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent2));display:flex;align-items:center;justify-content:center;font-size:1.3rem">🤖</div>
      <div>
        <div style="font-weight:700">Alex — AI English Teacher</div>
        <div style="font-size:.78rem;color:var(--accent3)">● Online 24/7</div>
      </div>
    </div>
    <div class="chat-log" id="speaking-chat"></div>
    <div id="speaking-controls">
      <div class="mic-area" id="mic-area">
        <button class="mic-btn" id="mic-btn" onclick="toggleMic()">🎤</button>
        <div id="mic-status" style="color:var(--text2);font-size:.85rem" data-t="tapToSpeak">Tap mic to start speaking</div>
      </div>
      <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap" id="speaking-suggestions"></div>
    </div>
  </div>
  <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px;margin-top:16px" id="speaking-topics-grid"></div>
</div>

<!-- READING -->
<div id="section-reading" class="section">
  <div class="section-title" data-t="reading">Reading</div>
  <div class="section-subtitle" data-t="readingSub">Articles with comprehension questions</div>
  <div id="reading-list"></div>
</div>

<!-- WRITING -->
<div id="section-writing" class="section">
  <div class="section-title" data-t="writing">Writing Practice</div>
  <div class="section-subtitle" data-t="writingSub">Write and get AI feedback instantly</div>
  <div id="writing-tasks"></div>
</div>

<!-- LEADERBOARD -->
<div id="section-leaderboard" class="section">
  <div class="section-title" data-t="leaderboard">Leaderboard</div>
  <div class="section-subtitle" data-t="leaderboardSub2">Real rankings updated daily</div>
  <div class="leaderboard" id="leaderboard-list"></div>
</div>

<!-- AI TUTOR -->
<div id="section-ai" class="section">
  <div class="section-title" data-t="aiTutor">AI English Tutor</div>
  <div class="section-subtitle" data-t="aiTutorSub">Ask anything about English — grammar, vocabulary, pronunciation</div>
  <div class="ai-chat">
    <div class="chat-messages" id="ai-chat-messages"></div>
    <div class="chat-input-row">
      <input class="chat-input" id="ai-chat-input" placeholder="Ask anything in English..." onkeydown="if(event.key==='Enter')sendAIMessage()">
      <button class="btn btn-primary" onclick="sendAIMessage()">Send ➤</button>
    </div>
    <div style="display:flex;gap:8px;margin-top:10px;flex-wrap:wrap" id="ai-suggestions"></div>
  </div>
</div>

</div><!-- /main -->

<!-- MODAL for vocab word -->
<div class="modal" id="vocab-modal">
  <div class="modal-box">
    <button class="modal-close" onclick="closeModal('vocab-modal')">✕</button>
    <div id="vocab-modal-content"></div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// =========================================================
// TRANSLATIONS
// =========================================================
const T = {
  en:{
    learn:"LEARN",home:"Home",topics:"Topics",vocabulary:"Vocabulary",
    listening:"Listening",speaking:"Speaking",reading:"Reading",writing:"Writing",
    compete:"COMPETE",leaderboard:"Leaderboard",aiTutor:"AI Tutor",
    heroTitle:"Master English Like a Pro",heroSub:"Topics, tests, listening, speaking — all powered by real AI",
    topicsCompleted:"Topics Completed",avgScore:"Avg Test Score",dayStreak:"Day Streak",wordsLearned:"Words Learned",
    startLearning:"Start Learning",startLearningSub:"Choose a topic and take a test",
    chatAI:"Chat with AI",chatAISub:"Practice English 24/7 with smart AI",
    vocabularySub:"Learn thousands of words by category",leaderboardSub:"Compete with learners worldwide",
    allTopics:"All Topics",allTopicsSub:"Choose a topic to study, then take a 30-question test",
    backToTopics:"Back to Topics",vocabSub:"Thousands of words organized by topic and level",
    listeningSub:"Real audio exercises with comprehension tests",
    speakingSub:"Have real conversations with AI — it speaks and you answer!",
    tapToSpeak:"Tap mic to start speaking",readingSub:"Articles with comprehension questions",
    writingSub:"Write and get AI feedback instantly",leaderboardSub2:"Real rankings updated daily",
    aiTutorSub:"Ask anything about English — grammar, vocabulary, pronunciation",
    question:"Question",of:"of",checkAnswer:"Check Answer",next:"Next",
    finish:"Finish",yourScore:"Your Score",excellent:"Excellent! 🎉",
    good:"Good job! 👍",keepPracticing:"Keep practicing! 💪",
    studyTopic:"Study Topic",takeTest:"Take Test",
    beginnerLevel:"Beginner",intermediateLevel:"Intermediate",advancedLevel:"Advanced",
    wordsInSection:"words",learnedTag:"Learned",
    listenAgain:"Listen Again",showTranscript:"Show Transcript",
    startConversation:"Start Conversation",stopListening:"Stop Listening",
    speakNow:"Speak now...",sending:"Sending...",
    writingPrompt:"Write about this topic:",submitWriting:"Submit for AI Review",
    aiReviewing:"AI is reviewing your writing...",
    score:"Score",feedback:"Feedback",corrections:"Corrections",suggestions:"Suggestions",
    correct:"Correct ✓",wrong:"Wrong ✗",
  },
  ru:{
    learn:"УЧИТЬСЯ",home:"Главная",topics:"Темы",vocabulary:"Словарь",
    listening:"Аудирование",speaking:"Говорение",reading:"Чтение",writing:"Письмо",
    compete:"СОРЕВНОВАТЬСЯ",leaderboard:"Рейтинг",aiTutor:"ИИ Учитель",
    heroTitle:"Освой английский как профессионал",heroSub:"Темы, тесты, аудирование, говорение — всё с настоящим ИИ",
    topicsCompleted:"Пройдено тем",avgScore:"Средний балл",dayStreak:"Дней подряд",wordsLearned:"Слов изучено",
    startLearning:"Начать учиться",startLearningSub:"Выберите тему и пройдите тест",
    chatAI:"Чат с ИИ",chatAISub:"Практикуй английский 24/7 с умным ИИ",
    vocabularySub:"Тысячи слов по темам и уровням",leaderboardSub:"Соревнуйтесь с учениками со всего мира",
    allTopics:"Все темы",allTopicsSub:"Выберите тему для изучения, затем пройдите тест из 30 вопросов",
    backToTopics:"Назад к темам",vocabSub:"Тысячи слов, организованных по теме и уровню",
    listeningSub:"Настоящие аудио-упражнения с тестами на понимание",
    speakingSub:"Настоящие разговоры с ИИ — он говорит, ты отвечаешь!",
    tapToSpeak:"Нажмите микрофон чтобы говорить",readingSub:"Статьи с вопросами на понимание",
    writingSub:"Пишите и получайте мгновенную обратную связь от ИИ",leaderboardSub2:"Реальный рейтинг обновляется ежедневно",
    aiTutorSub:"Спрашивай что угодно об английском — грамматика, словарь, произношение",
    question:"Вопрос",of:"из",checkAnswer:"Проверить ответ",next:"Далее",
    finish:"Завершить",yourScore:"Ваш результат",excellent:"Отлично! 🎉",
    good:"Хорошо! 👍",keepPracticing:"Продолжай практиковаться! 💪",
    studyTopic:"Изучить тему",takeTest:"Пройти тест",
    beginnerLevel:"Начальный",intermediateLevel:"Средний",advancedLevel:"Продвинутый",
    wordsInSection:"слов",learnedTag:"Изучено",
    listenAgain:"Слушать снова",showTranscript:"Показать текст",
    startConversation:"Начать разговор",stopListening:"Остановить",
    speakNow:"Говорите...",sending:"Отправка...",
    writingPrompt:"Напишите на тему:",submitWriting:"Отправить на проверку ИИ",
    aiReviewing:"ИИ проверяет ваш текст...",
    score:"Оценка",feedback:"Отзыв",corrections:"Исправления",suggestions:"Предложения",
    correct:"Верно ✓",wrong:"Неверно ✗",
  },
  uz:{
    learn:"O'RGANISH",home:"Bosh sahifa",topics:"Mavzular",vocabulary:"Lug'at",
    listening:"Tinglash",speaking:"Gapirish",reading:"O'qish",writing:"Yozish",
    compete:"MUSOBAQA",leaderboard:"Reyting",aiTutor:"AI O'qituvchi",
    heroTitle:"Ingliz tilini professionaldek o'rgan",heroSub:"Mavzular, testlar, tinglash, gapirish — haqiqiy AI bilan",
    topicsCompleted:"Tugatilgan mavzular",avgScore:"O'rtacha ball",dayStreak:"Kunlik seriya",wordsLearned:"O'rganilgan so'zlar",
    startLearning:"O'rganishni boshlash",startLearningSub:"Mavzu tanlang va test topshiring",
    chatAI:"AI bilan suhbat",chatAISub:"Aqlli AI bilan 24/7 inglizcha mashq qiling",
    vocabularySub:"Minglab so'zlar mavzu va darajalar bo'yicha",leaderboardSub:"Dunyo bo'ylab o'quvchilar bilan musobaqalashing",
    allTopics:"Barcha mavzular",allTopicsSub:"O'rganish uchun mavzu tanlang, so'ng 30 savollik test topshiring",
    backToTopics:"Mavzularga qaytish",vocabSub:"Mavzu va darajalar bo'yicha tartibga solingan minglab so'zlar",
    listeningSub:"Tushunish testlari bilan haqiqiy audio mashqlar",
    speakingSub:"AI bilan haqiqiy suhbatlar — u gapiradi, siz javob berasiz!",
    tapToSpeak:"Gapirish uchun mikrofonni bosing",readingSub:"Tushunish savollari bilan maqolalar",
    writingSub:"Yozing va AI dan darhol fikr-mulohaza oling",leaderboardSub2:"Haqiqiy reytinglar har kuni yangilanadi",
    aiTutorSub:"Ingliz tili haqida har narsani so'rang — grammatika, lug'at, talaffuz",
    question:"Savol",of:"dan",checkAnswer:"Javobni tekshirish",next:"Keyingi",
    finish:"Tugatish",yourScore:"Sizning natijangiz",excellent:"Ajoyib! 🎉",
    good:"Yaxshi! 👍",keepPracticing:"Mashq qilishni davom eting! 💪",
    studyTopic:"Mavzuni o'rganish",takeTest:"Test topshirish",
    beginnerLevel:"Boshlang'ich",intermediateLevel:"O'rta",advancedLevel:"Ilg'or",
    wordsInSection:"so'z",learnedTag:"O'rganildi",
    listenAgain:"Yana tinglash",showTranscript:"Matnni ko'rsatish",
    startConversation:"Suhbatni boshlash",stopListening:"To'xtatish",
    speakNow:"Gapiring...",sending:"Yuborilmoqda...",
    writingPrompt:"Bu mavzuda yozing:",submitWriting:"AI tekshiruviga yuborish",
    aiReviewing:"AI yozuvingizni tekshirmoqda...",
    score:"Ball",feedback:"Fikr-mulohaza",corrections:"Tuzatishlar",suggestions:"Takliflar",
    correct:"To'g'ri ✓",wrong:"Noto'g'ri ✗",
  }
};
let currentLang='en';
function t(k){return(T[currentLang]||T.en)[k]||T.en[k]||k}
function setLang(l){
  currentLang=l;
  document.querySelectorAll('.lang-btn').forEach(b=>b.classList.remove('active'));
  document.querySelectorAll('.lang-btn').forEach(b=>{if(b.textContent.toLowerCase()===l.toLowerCase())b.classList.add('active')});
  document.querySelectorAll('[data-t]').forEach(el=>{
    const k=el.getAttribute('data-t');
    if(k&&T[l]&&T[l][k])el.textContent=T[l][k];
    else if(k&&T.en[k])el.textContent=T.en[k];
  });
  document.querySelectorAll('.vocab-search').forEach(el=>el.placeholder='🔍 '+(l==='ru'?'Поиск слов...':l==='uz'?"So'z qidirish...":'Search words...'));
  document.querySelectorAll('.chat-input').forEach(el=>el.placeholder=l==='ru'?'Спросите что-нибудь...':l==='uz'?"Biror narsa so'rang...":'Ask anything in English...');
  renderAll();
}

// =========================================================
// GAME STATE
// =========================================================
let state={
  xp:0, streak:3, topicsDone:{}, scores:{}, wordsLearned:new Set(),
  currentTopic:null, quizState:null, chatHistory:[], speakingHistory:[],
  speakingTopic:null, writingTask:null
};
function saveState(){try{localStorage.setItem('em_state',JSON.stringify({...state,wordsLearned:[...state.wordsLearned]}))}catch(e){}}
function loadState(){try{const d=JSON.parse(localStorage.getItem('em_state')||'{}');if(d.xp!=null){state={...state,...d,wordsLearned:new Set(d.wordsLearned||[])};}}catch(e){}}
loadState();

function addXP(n){state.xp+=n;document.getElementById('xp-badge').textContent='⚡ '+state.xp+' XP';updateHomeStats();saveState();}
function updateHomeStats(){
  document.getElementById('stat-topics').textContent=Object.keys(state.topicsDone).length;
  const s=Object.values(state.scores);
  document.getElementById('stat-score').textContent=s.length?Math.round(s.reduce((a,b)=>a+b,0)/s.length)+'%':'0%';
  document.getElementById('stat-streak').textContent=state.streak+'🔥';
  document.getElementById('stat-words').textContent=state.wordsLearned.size;
}
updateHomeStats();

// =========================================================
// NAVIGATION
// =========================================================
function showSection(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.getElementById('section-'+id).classList.add('active');
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
  const ni=document.getElementById('nav-'+id);
  if(ni)ni.classList.add('active');
  if(id==='vocabulary')renderVocab();
  if(id==='listening')renderListening();
  if(id==='reading')renderReading();
  if(id==='writing')renderWriting();
  if(id==='leaderboard')renderLeaderboard();
  if(id==='speaking')renderSpeaking();
  if(id==='ai')initAI();
}

// =========================================================
// TOPICS DATA
// =========================================================
const TOPICS=[
{id:'greetings',icon:'👋',level:'beginner',
 title:{en:'Greetings & Introductions',ru:'Приветствия и знакомства',uz:'Salomlashish va tanishish'},
 desc:{en:'Learn how to greet people, introduce yourself, and start conversations.',ru:'Научитесь приветствовать людей, представляться и начинать разговоры.',uz:'Odamlarni salomlashish, o\'zingizni tanishtirish va suhbat boshlashni o\'rganing.'},
 content:{en:`
<h2>Greetings & Introductions</h2>
<p>Greetings are the foundation of every conversation. In English, there are many ways to say hello depending on the time of day, the setting, and how well you know the person.</p>
<h3>Formal Greetings</h3>
<p>Use these in professional settings, with strangers, or with people older than you:</p>
<div class="example-box"><div class="en">"Good morning, Mr. Johnson. How do you do?"</div><div class="tr">Доброе утро, мистер Джонсон. Как вы поживаете?</div></div>
<div class="example-box"><div class="en">"Good afternoon, I'm pleased to meet you."</div><div class="tr">Добрый день, рад с вами познакомиться.</div></div>
<div class="example-box"><div class="en">"Good evening. It's a pleasure to make your acquaintance."</div><div class="tr">Добрый вечер. Рад с вами познакомиться.</div></div>
<h3>Informal Greetings</h3>
<p>Use these with friends, classmates, and people your age:</p>
<div class="example-box"><div class="en">"Hey! What's up?" / "Hi there!" / "What's going on?"</div><div class="tr">Эй! Как дела? / Привет! / Что происходит?</div></div>
<div class="example-box"><div class="en">"Long time no see! How have you been?"</div><div class="tr">Давно не виделись! Как ты поживал?</div></div>
<h3>Introducing Yourself</h3>
<p>When meeting someone new, follow this structure:</p>
<div class="example-box"><div class="en">"Hi, my name is Sarah. I'm 25 years old and I'm from New York. I work as a teacher. Nice to meet you!"</div><div class="tr">Привет, меня зовут Сара. Мне 25 лет, я из Нью-Йорка. Я работаю учителем. Приятно познакомиться!</div></div>
<h3>Asking About Someone</h3>
<div class="example-box"><div class="en">"What's your name?" / "Where are you from?" / "What do you do for a living?" / "How old are you?"</div><div class="tr">Как вас зовут? / Откуда вы? / Чем вы занимаетесь? / Сколько вам лет?</div></div>
<h3>Saying Goodbye</h3>
<div class="example-box"><div class="en">Formal: "Farewell." / "It was a pleasure meeting you." / "Have a good day."</div><div class="tr">Формально: Прощайте. / Было приятно познакомиться. / Хорошего дня.</div></div>
<div class="example-box"><div class="en">Informal: "Bye!" / "See you later!" / "Take care!" / "Catch you later!"</div><div class="tr">Неформально: Пока! / Увидимся позже! / Береги себя! / До встречи!</div></div>
<h3>Key Vocabulary</h3>
<p>greeting, introduction, farewell, acquaintance, pleasure, formal, informal, native, surname, nickname, occupation, hometown</p>
 `,ru:'',uz:''},
 vocab:['hello','goodbye','name','pleased','morning','afternoon','evening','introduce','meet','farewell','acquaintance','surname']
},
{id:'tenses',icon:'⏰',level:'beginner',
 title:{en:'English Tenses',ru:'Времена английского языка',uz:'Ingliz tili zamonlari'},
 desc:{en:'Master all 12 English tenses with examples and practice.',ru:'Освойте все 12 времён английского языка с примерами и практикой.',uz:'Misollar va mashqlar bilan ingliz tilining barcha 12 zamonini o\'rganing.'},
 content:{en:`
<h2>English Tenses — Complete Guide</h2>
<p>English has 12 main tenses organized into three time frames (Past, Present, Future) and four aspects (Simple, Continuous, Perfect, Perfect Continuous).</p>
<h3>Present Simple</h3>
<p><strong>Form:</strong> Subject + base verb (add -s/-es for he/she/it)<br><strong>Use:</strong> Habits, routines, facts, permanent situations</p>
<div class="example-box"><div class="en">I work every day. She speaks English. Water boils at 100°C.</div><div class="tr">Я работаю каждый день. Она говорит по-английски. Вода кипит при 100°C.</div></div>
<h3>Present Continuous</h3>
<p><strong>Form:</strong> am/is/are + verb-ing<br><strong>Use:</strong> Actions happening right now, temporary situations</p>
<div class="example-box"><div class="en">I am studying now. They are playing football. She is wearing a red dress.</div><div class="tr">Я сейчас учусь. Они играют в футбол. Она надела красное платье.</div></div>
<h3>Present Perfect</h3>
<p><strong>Form:</strong> have/has + past participle<br><strong>Use:</strong> Past actions with present results, life experiences</p>
<div class="example-box"><div class="en">I have visited Paris. She has eaten sushi before. They have just arrived.</div><div class="tr">Я посетил Париж. Она ела суши раньше. Они только что прибыли.</div></div>
<h3>Past Simple</h3>
<p><strong>Form:</strong> verb + -ed (regular) or irregular form<br><strong>Use:</strong> Completed actions in the past at a specific time</p>
<div class="example-box"><div class="en">I worked yesterday. She visited London last year. They went to school.</div><div class="tr">Я работал вчера. Она посетила Лондон в прошлом году. Они ходили в школу.</div></div>
<h3>Past Continuous</h3>
<p><strong>Form:</strong> was/were + verb-ing<br><strong>Use:</strong> Actions in progress at a specific past moment</p>
<div class="example-box"><div class="en">I was sleeping at 8 PM. While she was cooking, he was reading.</div><div class="tr">Я спал в 8 вечера. Пока она готовила, он читал.</div></div>
<h3>Future Simple</h3>
<p><strong>Form:</strong> will + base verb<br><strong>Use:</strong> Predictions, spontaneous decisions, promises</p>
<div class="example-box"><div class="en">I will call you tomorrow. It will rain tonight. She will help us.</div><div class="tr">Я позвоню тебе завтра. Сегодня ночью пойдёт дождь. Она нам поможет.</div></div>
<h3>Signal Words</h3>
<p>Present Simple: always, usually, often, never, every day | Past Simple: yesterday, ago, last year, in 1990 | Future: tomorrow, next week, soon, in the future</p>
 `,ru:'',uz:''},
 vocab:['tense','verb','past','present','future','simple','continuous','perfect','irregular','auxiliary','participle','gerund']
},
{id:'articles',icon:'📝',level:'beginner',
 title:{en:'Articles: A, An, The',ru:'Артикли: A, An, The',uz:'Artiklar: A, An, The'},
 desc:{en:'Understand when to use a, an, the, or no article at all.',ru:'Поймите, когда использовать a, an, the или вообще без артикля.',uz:"Qachon a, an, the yoki umuman artikl ishlatmaslikni tushunib oling."},
 content:{en:`
<h2>Articles in English</h2>
<p>Articles are small but incredibly important words in English. Using the wrong article (or forgetting one) is one of the most common mistakes learners make.</p>
<h3>Indefinite Article: A / AN</h3>
<p>Use <strong>a</strong> before consonant sounds, <strong>an</strong> before vowel sounds (a, e, i, o, u).</p>
<div class="example-box"><div class="en">a book, a car, a university (u sounds like 'yu') | an apple, an egg, an hour (h is silent)</div><div class="tr">книга, машина, университет | яблоко, яйцо, час</div></div>
<p><strong>When to use A/AN:</strong></p>
<div class="example-box"><div class="en">First mention: "I saw a dog." (next time: "The dog was friendly.") | Profession: "She is a doctor." | Per/each: "twice a week"</div></div>
<h3>Definite Article: THE</h3>
<p>Use <strong>the</strong> when both speaker and listener know which specific thing is meant.</p>
<div class="example-box"><div class="en">The sun, the moon, the Earth (unique things) | "Close the door." (specific door) | "The Nile is in Africa." (rivers, mountain ranges, seas)</div><div class="tr">Солнце, луна, Земля | Закрой дверь | Нил находится в Африке</div></div>
<h3>No Article (Zero Article)</h3>
<div class="example-box"><div class="en">Languages: "She speaks English." | Sports: "He plays football." | Meals: "We eat breakfast." | Abstract nouns: "Love is important." | Most countries, cities</div></div>
<h3>Common Mistakes</h3>
<div class="example-box"><div class="en">✗ "I go to the school." → ✓ "I go to school." (as a student, it's an institution)</div></div>
<div class="example-box"><div class="en">✗ "She is teacher." → ✓ "She is a teacher." (must use a/an with singular professions)</div></div>
 `,ru:'',uz:''},
 vocab:['article','definite','indefinite','noun','singular','plural','countable','uncountable','specific','general','vowel','consonant']
},
{id:'modal-verbs',icon:'🔧',level:'intermediate',
 title:{en:'Modal Verbs',ru:'Модальные глаголы',uz:'Modal fe\'llar'},
 desc:{en:'Can, could, may, might, must, should, would — master all modals.',ru:'Can, could, may, might, must, should, would — освойте все модальные глаголы.',uz:"Can, could, may, might, must, should, would — barcha modal fe'llarni o'rganing."},
 content:{en:`
<h2>Modal Verbs — Complete Guide</h2>
<p>Modal verbs are special auxiliary verbs that express ability, permission, possibility, obligation, and more. They never take -s/-ed endings and are always followed by the base form of the verb.</p>
<h3>CAN / COULD</h3>
<p><strong>Can</strong> = present ability, permission (informal), possibility</p>
<div class="example-box"><div class="en">I can swim. (ability) | Can I use your phone? (permission) | It can get very cold here. (possibility)</div></div>
<p><strong>Could</strong> = past ability, polite request, conditional possibility</p>
<div class="example-box"><div class="en">When I was 5, I could read. | Could you help me, please? | It could rain tomorrow.</div></div>
<h3>MAY / MIGHT</h3>
<div class="example-box"><div class="en">May I enter? (formal permission) | She may be late. (50% possibility) | He might come tomorrow. (less certain, ~30%)</div></div>
<h3>MUST / HAVE TO / MUSTN'T</h3>
<div class="example-box"><div class="en">You must wear a seatbelt. (strong obligation, law) | You must be tired! (logical deduction) | You mustn'tt tell anyone. (prohibition)</div><div class="tr">Вы должны пристегнуть ремень безопасности. | Вы, наверное, устали! | Никому нельзя говорить.</div></div>
<h3>SHOULD / OUGHT TO</h3>
<div class="example-box"><div class="en">You should see a doctor. (advice) | You shouldn't eat so much sugar. (advice against) | We ought to call her.</div></div>
<h3>WOULD</h3>
<div class="example-box"><div class="en">Would you like some tea? (polite offer) | I would travel the world if I had money. (conditional) | He would always smile. (past habit)</div></div>
<h3>Key Differences: MUST vs HAVE TO</h3>
<div class="example-box"><div class="en">MUST = personal obligation / I must study (I decide this) | HAVE TO = external obligation / I have to wear a uniform (rules say so)</div></div>
 `,ru:'',uz:''},
 vocab:['modal','ability','permission','possibility','obligation','prohibition','advice','deduction','auxiliary','conditional','formal','polite']
},
{id:'prepositions',icon:'📍',level:'beginner',
 title:{en:'Prepositions',ru:'Предлоги',uz:'Predloglar'},
 desc:{en:'In, on, at, by, with, from — master all English prepositions.',ru:'In, on, at, by, with, from — освойте все предлоги английского языка.',uz:"In, on, at, by, with, from — ingliz tili predloglarini o'rganing."},
 content:{en:`
<h2>Prepositions in English</h2>
<p>Prepositions show the relationship between a noun/pronoun and other words in the sentence. They indicate position, time, direction, and more.</p>
<h3>Prepositions of Place</h3>
<div class="example-box"><div class="en">IN: inside an enclosed space — "in the box", "in London", "in my bag"</div></div>
<div class="example-box"><div class="en">ON: on a surface — "on the table", "on the wall", "on the bus/train/plane"</div></div>
<div class="example-box"><div class="en">AT: specific point/place — "at the door", "at school", "at the top"</div></div>
<div class="example-box"><div class="en">UNDER/ABOVE/BESIDE/BEHIND/IN FRONT OF/BETWEEN/AMONG</div></div>
<h3>Prepositions of Time</h3>
<div class="example-box"><div class="en">IN: months, years, seasons, centuries — "in July", "in 2020", "in summer", "in the morning"</div></div>
<div class="example-box"><div class="en">ON: days, dates — "on Monday", "on July 4th", "on my birthday"</div></div>
<div class="example-box"><div class="en">AT: specific times, holidays — "at 3 o'clock", "at noon", "at Christmas", "at midnight"</div></div>
<h3>Prepositions of Movement</h3>
<div class="example-box"><div class="en">TO: direction — "go to school" | INTO: entering — "walk into the room" | ONTO: up onto surface — "jump onto the stage" | THROUGH: passing through — "drive through the tunnel"</div></div>
<h3>Other Common Prepositions</h3>
<div class="example-box"><div class="en">BY: "a book by Shakespeare" / "come by car" / "finish by Friday" | WITH: "tea with milk" / "cut with scissors" | FOR: "a gift for you" / "wait for an hour" | OF: "a cup of tea" / "afraid of dogs"</div></div>
 `,ru:'',uz:''},
 vocab:['preposition','position','location','direction','movement','relationship','beside','through','across','toward','beneath','opposite']
},
{id:'conditionals',icon:'🔀',level:'intermediate',
 title:{en:'Conditionals (If-Clauses)',ru:'Условные предложения',uz:'Shartli gaplar'},
 desc:{en:'Zero, First, Second, Third and Mixed conditionals explained.',ru:'Нулевой, первый, второй, третий и смешанные условные типы.',uz:"Nol, birinchi, ikkinchi, uchinchi va aralash shartli gaplar."},
 content:{en:`
<h2>Conditionals in English</h2>
<p>Conditional sentences (if-clauses) express a condition and its result. There are 5 main types in English.</p>
<h3>Zero Conditional — General Truths</h3>
<p><strong>Structure:</strong> If + present simple, present simple</p>
<div class="example-box"><div class="en">If you heat water to 100°C, it boils. | If I eat too much, I feel sick. | If it rains, the ground gets wet.</div><div class="tr">Если нагреть воду до 100°C, она кипит.</div></div>
<h3>First Conditional — Real Future</h3>
<p><strong>Structure:</strong> If + present simple, will + base verb</p>
<div class="example-box"><div class="en">If it rains tomorrow, I will stay home. | If she calls me, I'll tell her the news. | If you study hard, you will pass.</div></div>
<h3>Second Conditional — Unreal Present/Future</h3>
<p><strong>Structure:</strong> If + past simple, would + base verb</p>
<div class="example-box"><div class="en">If I were rich, I would travel the world. | If she knew the answer, she would tell us. | If I had a car, I would drive to work.</div><div class="tr">Если бы я был богат, я бы путешествовал по миру.</div></div>
<h3>Third Conditional — Unreal Past</h3>
<p><strong>Structure:</strong> If + past perfect, would have + past participle</p>
<div class="example-box"><div class="en">If I had studied harder, I would have passed. | If she had taken the medicine, she would have recovered. | If they hadn't been late, they would have caught the train.</div></div>
<h3>Mixed Conditional — Past → Present Result</h3>
<div class="example-box"><div class="en">If I had taken that job (past), I would be rich now (present). | If she hadn't been ill (past), she would be here today.</div></div>
 `,ru:'',uz:''},
 vocab:['conditional','clause','result','hypothesis','imaginary','consequence','unless','provided','suppose','although','despite','regardless']
},
{id:'passive-voice',icon:'🔄',level:'intermediate',
 title:{en:'Passive Voice',ru:'Пассивный залог',uz:'Passiv nido'},
 desc:{en:'Learn how and when to use passive constructions in English.',ru:'Узнайте, как и когда использовать пассивные конструкции.',uz:"Ingliz tilida passiv konstruksiyalarni qanday va qachon ishlatishni o'rganing."},
 content:{en:`
<h2>Passive Voice in English</h2>
<p>In active voice, the subject performs the action. In passive voice, the subject receives the action. We use passive when the action is more important than who does it.</p>
<h3>How to Form Passive</h3>
<p><strong>Formula:</strong> Subject + to be (conjugated) + past participle (+ by + agent)</p>
<div class="example-box"><div class="en">Active: "Shakespeare wrote Hamlet." → Passive: "Hamlet was written by Shakespeare."</div></div>
<div class="example-box"><div class="en">Active: "They are building a new bridge." → Passive: "A new bridge is being built."</div></div>
<h3>Passive in Different Tenses</h3>
<div class="example-box"><div class="en">Present Simple: "Coffee is grown in Colombia." | Past Simple: "The window was broken." | Present Perfect: "The project has been completed." | Future: "The results will be announced tomorrow." | Modal: "The problem can be solved."</div></div>
<h3>When to Use Passive</h3>
<div class="example-box"><div class="en">• When the agent is unknown: "My bike was stolen." | • When the agent is obvious: "The suspect was arrested." | • In formal/scientific writing: "The experiment was conducted twice." | • To emphasize the action/result: "Three goals were scored in 10 minutes."</div></div>
<h3>Common Passive Structures</h3>
<div class="example-box"><div class="en">It is said that... / It is believed that... / It is reported that... / It is thought that...</div><div class="tr">Говорят, что... / Считается, что... / Сообщается, что... / Думают, что...</div></div>
 `,ru:'',uz:''},
 vocab:['passive','active','subject','object','agent','participle','construction','emphasis','formal','scientific','anonymous','transformation']
},
{id:'idioms',icon:'💬',level:'advanced',
 title:{en:'Idioms & Phrasal Verbs',ru:'Идиомы и фразовые глаголы',uz:'Idiomalar va fraza fe\'llari'},
 desc:{en:'Master over 100 common idioms and phrasal verbs used by native speakers.',ru:'Освойте более 100 распространённых идиом и фразовых глаголов.',uz:"100 dan ortiq umumiy idiomalar va fraza fe'llarini o'rganing."},
 content:{en:`
<h2>Idioms & Phrasal Verbs</h2>
<p>Idioms are expressions whose meaning cannot be understood from the individual words. Phrasal verbs combine a verb with a preposition or adverb to create a new meaning.</p>
<h3>Common Idioms — Body Parts</h3>
<div class="example-box"><div class="en">"Break a leg!" = Good luck! | "Cost an arm and a leg" = very expensive | "Keep an eye on" = watch carefully | "Turn a blind eye" = ignore deliberately | "Get cold feet" = become nervous/scared | "See eye to eye" = agree</div></div>
<h3>Idioms — Animals</h3>
<div class="example-box"><div class="en">"Let the cat out of the bag" = reveal a secret | "Kill two birds with one stone" = accomplish two things at once | "The elephant in the room" = obvious problem nobody talks about | "It's raining cats and dogs" = raining heavily</div></div>
<h3>Essential Phrasal Verbs</h3>
<div class="example-box"><div class="en">GIVE UP = stop trying | LOOK INTO = investigate | BRING UP = mention OR raise a child | TURN DOWN = refuse OR lower volume | FIGURE OUT = understand/solve | COME UP WITH = invent/produce an idea | CALL OFF = cancel | PUT OFF = postpone | SET UP = arrange/establish | CARRY OUT = execute/perform</div></div>
<h3>Phrasal Verbs in Context</h3>
<div class="example-box"><div class="en">"Don't give up! You can do this." | "We need to look into this problem." | "She came up with an excellent solution." | "The meeting was called off due to weather." | "Please turn down the music."</div></div>
<h3>Tips for Learning Idioms</h3>
<p>1. Learn idioms in context, not just their definitions. 2. Group related idioms together. 3. Use them in writing before speaking. 4. Native speakers use them constantly in conversation, TV, and books.</p>
 `,ru:'',uz:''},
 vocab:['idiom','phrasal','collocation','expression','figurative','literal','native','informal','metaphor','slang','proverb','saying']
},
{id:'business-english',icon:'💼',level:'advanced',
 title:{en:'Business English',ru:'Деловой английский',uz:'Biznes ingliz tili'},
 desc:{en:'Professional vocabulary, emails, meetings, and presentations.',ru:'Профессиональная лексика, письма, встречи и презентации.',uz:"Professional lug'at, xatlar, uchrashuvlar va taqdimotlar."},
 content:{en:`
<h2>Business English</h2>
<p>Business English is the specialized vocabulary and communication style used in professional and corporate environments.</p>
<h3>Professional Email Writing</h3>
<div class="example-box"><div class="en">Opening: "Dear Mr. Smith," / "To Whom It May Concern," / "I am writing to enquire about..."</div></div>
<div class="example-box"><div class="en">Body: "I would like to bring to your attention..." / "Please find attached..." / "I am pleased to inform you that..." / "Unfortunately, we regret to inform you..."</div></div>
<div class="example-box"><div class="en">Closing: "I look forward to hearing from you." / "Please do not hesitate to contact me." / "Kind regards," / "Yours sincerely,"</div></div>
<h3>Meeting Language</h3>
<div class="example-box"><div class="en">Opening: "Let's get started." / "Shall we begin?" / "The purpose of today's meeting is..."</div></div>
<div class="example-box"><div class="en">Agreeing: "That's a good point." / "I couldn't agree more." / "Absolutely."</div></div>
<div class="example-box"><div class="en">Disagreeing politely: "I see your point, however..." / "With all due respect..." / "I'm not sure that would work because..."</div></div>
<h3>Presentation Phrases</h3>
<div class="example-box"><div class="en">"Today I'm going to talk about..." / "As you can see from this chart..." / "To summarize..." / "In conclusion..." / "Any questions?"</div></div>
<h3>Key Business Vocabulary</h3>
<p>acquisition, merger, stakeholder, ROI, KPI, quarterly, forecast, revenue, expenditure, benchmark, deadline, negotiate, collaborate, implement, strategy, leverage, synergy, scalable</p>
 `,ru:'',uz:''},
 vocab:['professional','corporate','stakeholder','revenue','acquisition','presentation','negotiate','strategy','deadline','forecast','collaborate','implement']
},
{id:'travel',icon:'✈️',level:'beginner',
 title:{en:'Travel & Tourism',ru:'Путешествия и туризм',uz:"Sayohat va turizm"},
 desc:{en:'Everything you need to know for traveling in English-speaking countries.',ru:'Всё, что нужно знать для путешествий в англоязычных странах.',uz:"Ingliz tilida so'zlashuvchi mamlakatlarda sayohat qilish uchun kerak bo'lgan hamma narsa."},
 content:{en:`
<h2>Travel & Tourism English</h2>
<p>Knowing travel English is essential for anyone who wants to visit English-speaking countries or communicate internationally.</p>
<h3>At the Airport</h3>
<div class="example-box"><div class="en">"I'd like to check in, please." | "Window or aisle seat?" | "Do you have any luggage to check?" | "Your boarding pass, please." | "Gate 14 is boarding now."</div></div>
<h3>At the Hotel</h3>
<div class="example-box"><div class="en">"I have a reservation under the name Smith." | "Could I have a room with a view?" | "What time is check-out?" | "Could you call a taxi for me?" | "The WiFi isn't working in my room."</div></div>
<h3>Getting Around</h3>
<div class="example-box"><div class="en">"Excuse me, how do I get to the train station?" | "Take the second left, then go straight." | "How long does it take?" | "Is this the right bus for downtown?"</div></div>
<h3>At a Restaurant</h3>
<div class="example-box"><div class="en">"A table for two, please." | "What do you recommend?" | "I'm allergic to nuts." | "Could I have the bill, please?" | "Is service included?"</div></div>
<h3>Emergencies</h3>
<div class="example-box"><div class="en">"I need help!" | "Call an ambulance!" | "I've lost my passport." | "Where is the nearest hospital?" | "I've been robbed."</div></div>
<h3>Key Travel Words</h3>
<p>passport, visa, customs, departure, arrival, boarding, luggage, reservation, accommodation, currency, exchange rate, itinerary, landmark, souvenir, sightseeing</p>
 `,ru:'',uz:''},
 vocab:['passport','visa','customs','boarding','luggage','reservation','accommodation','currency','itinerary','landmark','souvenir','sightseeing']
}
];

// =========================================================
// VOCABULARY DATABASE (400+ words)
// =========================================================
const VOCAB_CATEGORIES={
 'Common Words':[
  {word:'beautiful',ph:'/ˈbjuːtɪfəl/',ru:'красивый',uz:'chiroyli',ex:'She wore a beautiful dress.'},
  {word:'important',ph:'/ɪmˈpɔːtənt/',ru:'важный',uz:'muhim',ex:'Education is very important.'},
  {word:'understand',ph:'/ˌʌndəˈstænd/',ru:'понимать',uz:'tushunmoq',ex:'I understand the problem.'},
  {word:'different',ph:'/ˈdɪfrənt/',ru:'разный',uz:'boshqacha',ex:'We have different opinions.'},
  {word:'possible',ph:'/ˈpɒsɪbəl/',ru:'возможный',uz:'mumkin',ex:'Is it possible to leave early?'},
  {word:'necessary',ph:'/ˈnesəsəri/',ru:'необходимый',uz:'zarur',ex:'It is necessary to study.'},
  {word:'actually',ph:'/ˈæktʃuəli/',ru:'на самом деле',uz:'aslida',ex:'He actually helped me.'},
  {word:'probably',ph:'/ˈprɒbəbli/',ru:'вероятно',uz:'ehtimol',ex:'She will probably come.'},
  {word:'interesting',ph:'/ˈɪntrɪstɪŋ/',ru:'интересный',uz:'qiziqarli',ex:'This is an interesting book.'},
  {word:'experience',ph:'/ɪkˈspɪəriəns/',ru:'опыт',uz:'tajriba',ex:'I have five years of experience.'},
  {word:'knowledge',ph:'/ˈnɒlɪdʒ/',ru:'знание',uz:"bilim",ex:'Knowledge is power.'},
  {word:'communicate',ph:'/kəˈmjuːnɪkeɪt/',ru:'общаться',uz:'muloqot qilmoq',ex:'We communicate by email.'},
 ],
 'Nature':[
  {word:'mountain',ph:'/ˈmaʊntɪn/',ru:'гора',uz:'tog\'',ex:'The mountain is very high.'},
  {word:'forest',ph:'/ˈfɒrɪst/',ru:'лес',uz:"o'rmon",ex:'A bear lives in the forest.'},
  {word:'ocean',ph:'/ˈəʊʃən/',ru:'океан',uz:'okean',ex:'The ocean covers 70% of Earth.'},
  {word:'river',ph:'/ˈrɪvər/',ru:'река',uz:"daryo",ex:'The river flows to the sea.'},
  {word:'earthquake',ph:'/ˈɜːθkweɪk/',ru:'землетрясение',uz:'zilzila',ex:'An earthquake hit the city.'},
  {word:'hurricane',ph:'/ˈhʌrɪkən/',ru:'ураган',uz:'to\'fon',ex:'The hurricane damaged the coast.'},
  {word:'volcano',ph:'/vɒlˈkeɪnəʊ/',ru:'вулкан',uz:'vulqon',ex:'The volcano erupted last year.'},
  {word:'atmosphere',ph:'/ˈætməsfɪər/',ru:'атмосфера',uz:'atmosfera',ex:'The atmosphere protects Earth.'},
  {word:'biodiversity',ph:'/ˌbaɪəʊdaɪˈvɜːsɪti/',ru:'биоразнообразие',uz:'biologik xilma-xillik',ex:'Rainforests have high biodiversity.'},
  {word:'ecosystem',ph:'/ˈiːkəʊsɪstəm/',ru:'экосистема',uz:'ekotizim',ex:'Oceans are complex ecosystems.'},
  {word:'climate',ph:'/ˈklaɪmɪt/',ru:'климат',uz:'iqlim',ex:'Climate change is a global issue.'},
  {word:'sustainable',ph:'/səˈsteɪnəbəl/',ru:'устойчивый',uz:'barqaror',ex:'We need sustainable energy.'},
 ],
 'Technology':[
  {word:'algorithm',ph:'/ˈælɡərɪðəm/',ru:'алгоритм',uz:'algoritm',ex:'Google uses a complex algorithm.'},
  {word:'artificial',ph:'/ˌɑːtɪˈfɪʃəl/',ru:'искусственный',uz:"sun'iy",ex:'Artificial intelligence is growing.'},
  {word:'database',ph:'/ˈdeɪtəbeɪs/',ru:'база данных',uz:"ma'lumotlar bazasi",ex:'The database stores user info.'},
  {word:'software',ph:'/ˈsɒftweər/',ru:'программное обеспечение',uz:'dasturiy ta\'minot',ex:'We need to update the software.'},
  {word:'hardware',ph:'/ˈhɑːdweər/',ru:'оборудование',uz:'texnik vositalar',ex:'The hardware needs replacing.'},
  {word:'cybersecurity',ph:'/ˌsaɪbəsɪˈkjʊərɪti/',ru:'кибербезопасность',uz:'kiberxavfsizlik',ex:'Cybersecurity is critical today.'},
  {word:'bandwidth',ph:'/ˈbændwɪdθ/',ru:'пропускная способность',uz:'o\'tkazuvchanlik',ex:'We need more bandwidth.'},
  {word:'interface',ph:'/ˈɪntəfeɪs/',ru:'интерфейс',uz:'interfeys',ex:'The user interface is clean.'},
  {word:'encryption',ph:'/ɪnˈkrɪpʃən/',ru:'шифрование',uz:'shifrlash',ex:'Encryption protects your data.'},
  {word:'prototype',ph:'/ˈprəʊtətaɪp/',ru:'прототип',uz:'prototip',ex:'They built a prototype in a week.'},
  {word:'innovation',ph:'/ˌɪnəˈveɪʃən/',ru:'инновация',uz:'innovatsiya',ex:'Innovation drives progress.'},
  {word:'wireless',ph:'/ˈwaɪərləs/',ru:'беспроводной',uz:'simsiz',ex:'Wireless internet is everywhere.'},
 ],
 'Emotions':[
  {word:'anxious',ph:'/ˈæŋkʃəs/',ru:'тревожный',uz:'tashvishli',ex:'She felt anxious before the exam.'},
  {word:'enthusiastic',ph:'/ɪnˌθjuːziˈæstɪk/',ru:'энтузиастичный',uz:'ishtiyoqli',ex:'He is enthusiastic about learning.'},
  {word:'overwhelmed',ph:'/ˌəʊvəˈwelmd/',ru:'подавленный',uz:"ezilgan",ex:'I feel overwhelmed with work.'},
  {word:'grateful',ph:'/ˈɡreɪtfəl/',ru:'благодарный',uz:'minnatdor',ex:'I am grateful for your help.'},
  {word:'frustrated',ph:'/frʌˈstreɪtɪd/',ru:'расстроенный',uz:'umidsizlangan',ex:'He gets frustrated easily.'},
  {word:'confident',ph:'/ˈkɒnfɪdənt/',ru:'уверенный',uz:'ishonchli',ex:'She is confident in her skills.'},
  {word:'melancholy',ph:'/ˈmelənkɒli/',ru:'меланхолия',uz:'melankholiya',ex:'A melancholy tune played softly.'},
  {word:'ecstatic',ph:'/ɪkˈstætɪk/',ru:'в экстазе',uz:"hayajonda",ex:'She was ecstatic about the news.'},
  {word:'embarrassed',ph:'/ɪmˈbærəst/',ru:'смущённый',uz:'uyalgan',ex:'He was embarrassed by the mistake.'},
  {word:'jealous',ph:'/ˈdʒeləs/',ru:'ревнивый',uz:'hasadchi',ex:'She felt jealous of her sister.'},
  {word:'lonely',ph:'/ˈləʊnli/',ru:'одинокий',uz:'yolg\'iz',ex:'He felt lonely in the new city.'},
  {word:'proud',ph:'/praʊd/',ru:'гордый',uz:'g\'ururli',ex:'Her parents were proud of her.'},
 ],
 'Food & Health':[
  {word:'nutrition',ph:'/njuːˈtrɪʃən/',ru:'питание',uz:'ovqatlanish',ex:'Good nutrition is essential.'},
  {word:'ingredient',ph:'/ɪnˈɡriːdiənt/',ru:'ингредиент',uz:'ingredient',ex:'What ingredients do we need?'},
  {word:'cuisine',ph:'/kwɪˈziːn/',ru:'кухня',uz:'oshxona',ex:'Italian cuisine is delicious.'},
  {word:'appetite',ph:'/ˈæpɪtaɪt/',ru:'аппетит',uz:'ishtaha',ex:'I have no appetite today.'},
  {word:'diagnosis',ph:'/ˌdaɪəɡˈnəʊsɪs/',ru:'диагноз',uz:'tashxis',ex:'The diagnosis was pneumonia.'},
  {word:'symptom',ph:'/ˈsɪmptəm/',ru:'симптом',uz:'belgi',ex:'Fever is a common symptom.'},
  {word:'prescription',ph:'/prɪˈskrɪpʃən/',ru:'рецепт',uz:'retsept',ex:'The doctor gave a prescription.'},
  {word:'immune',ph:'/ɪˈmjuːn/',ru:'иммунный',uz:'immunitet',ex:'Our immune system fights disease.'},
  {word:'calories',ph:'/ˈkæləriz/',ru:'калории',uz:'kaloriya',ex:'This meal has 500 calories.'},
  {word:'metabolism',ph:'/mɪˈtæbəlɪzəm/',ru:'метаболизм',uz:'moddalar almashinuvi',ex:'Exercise boosts metabolism.'},
  {word:'organic',ph:'/ɔːˈɡænɪk/',ru:'органический',uz:'organik',ex:'I prefer organic vegetables.'},
  {word:'protein',ph:'/ˈprəʊtiːn/',ru:'белок',uz:'oqsil',ex:'Meat is rich in protein.'},
 ],
 'Science':[
  {word:'hypothesis',ph:'/haɪˈpɒθɪsɪs/',ru:'гипотеза',uz:'gipoteza',ex:'Scientists test a hypothesis.'},
  {word:'experiment',ph:'/ɪkˈsperɪmənt/',ru:'эксперимент',uz:'tajriba',ex:'We conducted an experiment.'},
  {word:'molecule',ph:'/ˈmɒlɪkjuːl/',ru:'молекула',uz:'molekula',ex:'Water is made of molecules.'},
  {word:'evolution',ph:'/ˌiːvəˈluːʃən/',ru:'эволюция',uz:'evolyutsiya',ex:'Darwin studied evolution.'},
  {word:'gravity',ph:'/ˈɡrævɪti/',ru:'гравитация',uz:'tortishish',ex:'Gravity keeps us on Earth.'},
  {word:'photosynthesis',ph:'/ˌfəʊtəʊˈsɪnθɪsɪs/',ru:'фотосинтез',uz:'fotosintez',ex:'Plants use photosynthesis.'},
  {word:'chromosome',ph:'/ˈkrəʊməsəʊm/',ru:'хромосома',uz:'xromosoma',ex:'Humans have 46 chromosomes.'},
  {word:'quantum',ph:'/ˈkwɒntəm/',ru:'квантовый',uz:'kvant',ex:'Quantum physics is complex.'},
  {word:'nucleus',ph:'/ˈnjuːkliəs/',ru:'ядро',uz:'yadro',ex:'The nucleus controls the cell.'},
  {word:'frequency',ph:'/ˈfriːkwənsi/',ru:'частота',uz:'chastota',ex:'Sound travels at a frequency.'},
  {word:'radiation',ph:'/ˌreɪdiˈeɪʃən/',ru:'радиация',uz:'nurlanish',ex:'UV radiation can be harmful.'},
  {word:'density',ph:'/ˈdensɪti/',ru:'плотность',uz:'zichlik',ex:'Lead has high density.'},
 ],
 'Arts & Culture':[
  {word:'sculpture',ph:'/ˈskʌlptʃər/',ru:'скульптура',uz:'haykal',ex:'The sculpture is magnificent.'},
  {word:'symphony',ph:'/ˈsɪmfəni/',ru:'симфония',uz:'simfoniya',ex:'Beethoven wrote 9 symphonies.'},
  {word:'perspective',ph:'/pəˈspektɪv/',ru:'перспектива',uz:'istiqbol',ex:'Art gives us a new perspective.'},
  {word:'aesthetic',ph:'/iːsˈθetɪk/',ru:'эстетика',uz:'estetika',ex:'Japanese aesthetic is minimalist.'},
  {word:'architecture',ph:'/ˈɑːkɪtektʃər/',ru:'архитектура',uz:'arxitektura',ex:'Paris has stunning architecture.'},
  {word:'heritage',ph:'/ˈherɪtɪdʒ/',ru:'наследие',uz:'meros',ex:'This is cultural heritage.'},
  {word:'narrative',ph:'/ˈnærətɪv/',ru:'повествование',uz:'hikoya',ex:'The narrative is compelling.'},
  {word:'contemporary',ph:'/kənˈtempərəri/',ru:'современный',uz:'zamonaviy',ex:'Contemporary art is abstract.'},
  {word:'exhibition',ph:'/ˌeksɪˈbɪʃən/',ru:'выставка',uz:'ko\'rgazma',ex:'The exhibition opens tomorrow.'},
  {word:'masterpiece',ph:'/ˈmɑːstəpiːs/',ru:'шедевр',uz:'shoh asar',ex:'The Mona Lisa is a masterpiece.'},
  {word:'tradition',ph:'/trəˈdɪʃən/',ru:'традиция',uz:'an\'ana',ex:'This is an old tradition.'},
  {word:'ceremony',ph:'/ˈserɪməni/',ru:'церемония',uz:'marosim',ex:'The ceremony was beautiful.'},
 ],
 'Business':[
  {word:'entrepreneur',ph:'/ˌɒntrəprəˈnɜː/',ru:'предприниматель',uz:'tadbirkor',ex:'He is a successful entrepreneur.'},
  {word:'investment',ph:'/ɪnˈvestmənt/',ru:'инвестиции',uz:'investitsiya',ex:'This is a good investment.'},
  {word:'marketing',ph:'/ˈmɑːkɪtɪŋ/',ru:'маркетинг',uz:'marketing',ex:'Marketing is key to success.'},
  {word:'negotiate',ph:'/nɪˈɡəʊʃieɪt/',ru:'переговоры',uz:'muzokaralar',ex:'We need to negotiate the price.'},
  {word:'productivity',ph:'/ˌprɒdʌkˈtɪvɪti/',ru:'производительность',uz:'mahsuldorlik',ex:'How can we increase productivity?'},
  {word:'stakeholder',ph:'/ˈsteɪkhəʊldər/',ru:'заинтересованная сторона',uz:'manfaatdor tomon',ex:'All stakeholders must agree.'},
  {word:'revenue',ph:'/ˈrevənjuː/',ru:'выручка',uz:'daromad',ex:'Revenue increased by 20%.'},
  {word:'competition',ph:'/ˌkɒmpɪˈtɪʃən/',ru:'конкуренция',uz:'raqobat',ex:'Market competition is fierce.'},
  {word:'acquisition',ph:'/ˌækwɪˈzɪʃən/',ru:'поглощение',uz:"sotib olish",ex:'The acquisition was worth $1B.'},
  {word:'forecast',ph:'/ˈfɔːkɑːst/',ru:'прогноз',uz:"prognoz",ex:"The sales forecast looks positive."},
  {word:'leverage',ph:'/ˈliːvərɪdʒ/',ru:'рычаг влияния',uz:"ta'sir kuchi",ex:'Use your contacts as leverage.'},
  {word:'deadline',ph:'/ˈdedlaɪn/',ru:'дедлайн',uz:'muddat',ex:'The deadline is Friday noon.'},
 ],
};

let currentVocabCat=Object.keys(VOCAB_CATEGORIES)[0];
let allVocabFiltered=[];

function renderVocab(){
  const tabs=document.getElementById('vocab-tabs');
  tabs.innerHTML=Object.keys(VOCAB_CATEGORIES).map(c=>`<div class="vtab${c===currentVocabCat?' active':''}" onclick="setVocabCat('${c}')">${c}</div>`).join('');
  renderVocabGrid();
}
function setVocabCat(c){currentVocabCat=c;renderVocab();}
function renderVocabGrid(){
  const words=VOCAB_CATEGORIES[currentVocabCat]||[];
  const q=(document.getElementById('vocab-search')||{}).value||'';
  allVocabFiltered=q?words.filter(w=>w.word.includes(q.toLowerCase())||w.ru.includes(q)||w.uz.includes(q)):words;
  const grid=document.getElementById('vocab-grid');
  if(!grid)return;
  grid.innerHTML=allVocabFiltered.map(w=>`
    <div class="big-vocab-card" onclick="showVocabModal(${JSON.stringify(w).replace(/"/g,'&quot;')})">
      <span class="category">${currentVocabCat}</span>
      <div class="word">${w.word}</div>
      <div class="phonetic">${w.ph}</div>
      <div class="meaning">${currentLang==='ru'?w.ru:currentLang==='uz'?w.uz:w.ru}</div>
      <div class="example">${w.ex}</div>
    </div>
  `).join('');
}
function filterVocab(){renderVocabGrid();}
function showVocabModal(w){
  const el=typeof w==='string'?JSON.parse(w):w;
  document.getElementById('vocab-modal-content').innerHTML=`
    <div style="font-size:2rem;font-weight:800;color:var(--accent);margin-bottom:6px">${el.word}</div>
    <div style="color:var(--text3);font-family:'Space Mono',monospace;font-size:.9rem;margin-bottom:14px">${el.ph}</div>
    <div style="margin-bottom:10px"><span style="color:var(--text3);font-size:.8rem">RU:</span> <span style="color:var(--text);font-weight:600">${el.ru}</span></div>
    <div style="margin-bottom:10px"><span style="color:var(--text3);font-size:.8rem">UZ:</span> <span style="color:var(--text);font-weight:600">${el.uz}</span></div>
    <div style="background:rgba(0,212,255,.06);border-left:3px solid var(--accent);padding:12px 16px;border-radius:0 8px 8px 0;font-size:.9rem;color:var(--text2);margin-top:14px">"${el.ex}"</div>
    <button class="btn btn-primary" style="margin-top:18px" onclick="state.wordsLearned.add('${el.word}');updateHomeStats();saveState();showToast('Word learned! +5 XP','success');addXP(5);closeModal('vocab-modal')">✓ Mark as Learned</button>
  `;
  document.getElementById('vocab-modal').classList.add('open');
}
function closeModal(id){document.getElementById(id).classList.remove('open');}

// =========================================================
// TOPICS RENDERING
// =========================================================
function renderTopics(){
  const grid=document.getElementById('topics-grid');
  grid.innerHTML=TOPICS.map(tp=>{
    const prog=state.topicsDone[tp.id]||0;
    const lvlClass={'beginner':'level-beginner','intermediate':'level-intermediate','advanced':'level-advanced'}[tp.level];
    const lvlLabel=t(tp.level+'Level')||tp.level;
    return `<div class="topic-card" onclick="openTopic('${tp.id}')">
      <div class="topic-icon">${tp.icon}</div>
      <h3>${tp.title[currentLang]||tp.title.en}</h3>
      <p>${tp.desc[currentLang]||tp.desc.en}</p>
      <div class="topic-meta">
        <span class="level-tag ${lvlClass}">${lvlLabel}</span>
        <div class="progress-mini"><div class="progress-mini-fill" style="width:${prog}%"></div></div>
        <span style="font-size:.72rem;color:var(--text3)">${prog}%</span>
      </div>
    </div>`;
  }).join('');
}

function openTopic(id){
  const tp=TOPICS.find(t=>t.id===id);
  if(!tp)return;
  state.currentTopic=tp;
  document.getElementById('topics-list-view').style.display='none';
  document.getElementById('topic-detail-view').style.display='block';
  document.getElementById('topic-detail-content').innerHTML=`
    <div class="topic-detail-header">
      <div style="display:flex;align-items:center;gap:14px;margin-bottom:16px">
        <div style="font-size:3rem">${tp.icon}</div>
        <div>
          <h2 style="font-size:1.4rem;font-weight:800">${tp.title[currentLang]||tp.title.en}</h2>
          <p style="color:var(--text2);font-size:.88rem;margin-top:4px">${tp.desc[currentLang]||tp.desc.en}</p>
        </div>
      </div>
      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <button class="btn btn-primary" onclick="startTopicTest('${tp.id}')">${t('takeTest')} (30 ${t('question')}s)</button>
      </div>
    </div>
    <div class="content-box">${tp.content.en}</div>
    <div class="content-box">
      <h2>📚 ${t('vocabulary')}</h2>
      <div class="vocab-grid">
        ${(tp.vocab||[]).map(w=>{
          const allWords=Object.values(VOCAB_CATEGORIES).flat();
          const wd=allWords.find(x=>x.word===w)||{word:w,ph:'',ru:'',uz:'',ex:''};
          return `<div class="vocab-card" onclick="showVocabModal(${JSON.stringify(wd).replace(/"/g,'&quot;')})">
            <div class="vocab-word">${wd.word}</div>
            <div class="vocab-tr">${currentLang==='uz'?wd.uz:wd.ru}</div>
            ${wd.ex?`<div class="vocab-ex">${wd.ex}</div>`:''}
          </div>`;
        }).join('')}
      </div>
    </div>
  `;
}

function backToTopics(){
  document.getElementById('topics-list-view').style.display='block';
  document.getElementById('topic-detail-view').style.display='none';
  state.currentTopic=null;
}

// =========================================================
// QUIZ SYSTEM — 30 UNIQUE QUESTIONS PER TOPIC
// =========================================================
const QUIZ_POOL={
 greetings:[
  {type:'mc',q:'What is the most formal way to greet someone?',opts:['Hey!','What\'s up?','Good morning, how do you do?','Yo!'],a:2},
  {type:'mc',q:'Which phrase is used to say goodbye formally?',opts:['See ya!','Farewell, it was a pleasure.','Catch you later!','Peace out!'],a:1},
  {type:'fill',q:'Complete: "Nice to ____ you!"',a:'meet',hint:'We say this when meeting someone new'},
  {type:'mc',q:'What does "How do you do?" mean?',opts:['What are you doing?','A formal greeting','Are you busy?','How old are you?'],a:1},
  {type:'mc',q:'"Long time no see!" means:',opts:['You look different','I haven\'t seen you in a while','Where have you been?','You\'ve changed'],a:1},
  {type:'fill',q:'Complete: "Good ____, see you tomorrow!"',a:'night',hint:'End of day farewell'},
  {type:'mc',q:'What is the informal way to say "How are you?"',opts:['How do you do?','Good morning','What\'s up?','Pleased to meet you'],a:2},
  {type:'mc',q:'When introducing yourself, you say: "My ____ is John."',opts:['surname','name','age','job'],a:1},
  {type:'mc',q:'"Take care!" is used when:',opts:['Greeting someone','Saying goodbye','Asking a question','Giving advice'],a:1},
  {type:'fill',q:'Complete: "I\'m ____ to meet you." (formal)',a:'pleased',hint:'Formal way to show happiness'},
  {type:'mc',q:'Which greeting is used in the evening?',opts:['Good morning','Good afternoon','Good evening','Good night'],a:2},
  {type:'mc',q:'What does "acquaintance" mean?',opts:['A close friend','Someone you know slightly','A family member','A colleague'],a:1},
  {type:'fill',q:'Complete: "Where are you ____?" (asking about origin)',a:'from',hint:'Which country/city'},
  {type:'mc',q:'"How do you do?" is answered with:',opts:['I\'m fine, thanks','How do you do?','Not bad','Pretty good'],a:1},
  {type:'mc',q:'What does "farewell" mean?',opts:['Hello','Welcome','Goodbye (formal)','Thank you'],a:2},
  {type:'fill',q:'Complete: "It\'s a ____ to meet you."',a:'pleasure',hint:'A formal expression of happiness'},
  {type:'mc',q:'Which is NOT a greeting?',opts:['Hi there!','Good morning','How are you?','See you later!'],a:3},
  {type:'mc',q:'"What do you do?" means:',opts:['What are you doing now?','What is your job?','What is your hobby?','Where do you live?'],a:1},
  {type:'fill',q:'Complete: "Good ____, how can I help you?"',a:'morning',hint:'First part of the day'},
  {type:'mc',q:'"To Whom It May Concern" is used in:',opts:['Casual greetings','Formal letters','Text messages','Phone calls'],a:1},
  {type:'mc',q:'What is a "nickname"?',opts:['Your official name','A shortened or fun name','Your surname','Your title'],a:1},
  {type:'fill',q:'Complete: "Nice to ____ you again!"',a:'see',hint:'When meeting someone you already know'},
  {type:'mc',q:'How do you ask someone\'s age politely?',opts:['How old?','What\'s your age?','May I ask how old you are?','You look old!'],a:2},
  {type:'mc',q:'"My name is" vs "I\'m" — which is more formal?',opts:['I\'m','My name is','Both are same','Neither'],a:1},
  {type:'fill',q:'Complete: "Have a ____ day!"',a:'good',hint:'A wish for the day'},
  {type:'mc',q:'What does "I\'m pleased to make your acquaintance" mean?',opts:['I don\'t know you','Nice to meet you (formal)','Can we be friends?','I know you already'],a:1},
  {type:'mc',q:'"Catch you later" is ____ language.',opts:['Formal','Informal','Business','Academic'],a:1},
  {type:'fill',q:'Complete: "Hello, my ____ is Dr. Wilson."',a:'name',hint:'How you identify yourself'},
  {type:'mc',q:'What is the appropriate response to "How are you?"',opts:['I am here.','Fine, thanks! And you?','I don\'t know.','Yes.'],a:1},
  {type:'mc',q:'Which phrase means "I am doing well"?',opts:['Not too good','I\'m fine, thank you','So-so','Not really'],a:1},
 ],
 tenses:[
  {type:'mc',q:'Which sentence uses Present Simple correctly?',opts:['She is working yesterday.','He works every day.','They worked now.','I am work here.'],a:1},
  {type:'mc',q:'"I ____ football every Sunday." Which verb form?',opts:['playing','play','played','am playing'],a:1},
  {type:'fill',q:'Past simple of "go": "She ____ to school yesterday."',a:'went',hint:'Irregular verb'},
  {type:'mc',q:'Present Continuous is used for:',opts:['Habits','Actions happening now','Past events','Future plans always'],a:1},
  {type:'mc',q:'Which is Present Perfect?',opts:['I go to Paris.','I went to Paris.','I have been to Paris.','I will go to Paris.'],a:2},
  {type:'fill',q:'Complete: "She ____ (work) at Google since 2020."',a:'has worked',hint:'Present Perfect'},
  {type:'mc',q:'"Will you help me?" is ____ tense.',opts:['Past','Present','Future Simple','Present Perfect'],a:2},
  {type:'mc',q:'Signal word for Past Simple:',opts:['now','tomorrow','yesterday','already'],a:2},
  {type:'fill',q:'Complete: "They ____ (study) when I called." (Past Cont.)',a:'were studying',hint:'Past Continuous'},
  {type:'mc',q:'Future Continuous: "At 8 PM, I ____"',opts:['will sleep','sleep','am sleeping','will be sleeping'],a:3},
  {type:'mc',q:'"She has lived here for 10 years" — which tense?',opts:['Past Simple','Present Simple','Present Perfect','Future'],a:2},
  {type:'fill',q:'Complete: "By next year, he ____ (finish) university." (Future Perfect)',a:'will have finished',hint:'Future Perfect'},
  {type:'mc',q:'Which sentence is WRONG?',opts:['I work here.','She is sleeping.','They have ate lunch.','He will come.'],a:2},
  {type:'mc',q:'"I ____ (just) have eaten." Correct form:',opts:['have just eaten','just ate','just eat','am just eating'],a:0},
  {type:'fill',q:'Complete: "Water ____ (boil) at 100°C." (fact)',a:'boils',hint:'Present Simple for facts'},
  {type:'mc',q:'Stative verbs (know, love, believe) are NOT used in:',opts:['Present Simple','Past Simple','Continuous tenses','Perfect tenses'],a:2},
  {type:'mc',q:'"How long have you been learning English?" uses:',opts:['Present Perfect','Present Perfect Continuous','Past Simple','Present Simple'],a:1},
  {type:'fill',q:'Complete: "When I arrived, she ____ (already leave)."',a:'had already left',hint:'Past Perfect'},
  {type:'mc',q:'Past Perfect structure:',opts:['was/were + verb-ing','had + past participle','have/has + past participle','did + base verb'],a:1},
  {type:'mc',q:'"She is going to study medicine." This expresses:',opts:['Habit','Future plan (decided)','Past action','Present activity'],a:1},
  {type:'fill',q:'Complete: "The train ____ (arrive) by the time we got there."',a:'had arrived',hint:'Past Perfect — earlier past action'},
  {type:'mc',q:'Which uses Present Perfect Continuous?',opts:['I worked for hours.','I have worked for hours.','I have been working for hours.','I work for hours.'],a:2},
  {type:'mc',q:'"I ____ (never/see) this movie." Correct:',opts:['never saw','have never seen','never see','am never seeing'],a:1},
  {type:'fill',q:'Complete: "They ____ (build) the bridge since January."',a:'have been building',hint:'Present Perfect Continuous'},
  {type:'mc',q:'Difference: "I worked" vs "I have worked"',opts:['No difference','Worked = finished at specific time; Have worked = connected to now','Have worked = longer','Worked = more formal'],a:1},
  {type:'mc',q:'"Used to" expresses:',opts:['Current habit','Future intention','Past habit (no longer true)','Possibility'],a:2},
  {type:'fill',q:'Complete: "He ____ (use to/swim) every morning but stopped." ',a:'used to swim',hint:'Past habit'},
  {type:'mc',q:'Which sentence uses Future Perfect?',opts:['I will work tomorrow.','I will have finished by noon.','I am working tomorrow.','I work tomorrow.'],a:1},
  {type:'mc',q:'"As soon as she arrives, we ____ eat."',opts:['will','would','shall','are going to'],a:0},
  {type:'fill',q:'Complete: "He ____ (live) in London for 5 years when he moved."',a:'had been living',hint:'Past Perfect Continuous'},
 ],
 articles:[
  {type:'mc',q:'"She is ___ doctor." Correct article:',opts:['a','an','the','no article'],a:0},
  {type:'mc',q:'"___ sun rises in the east." Correct article:',opts:['A','An','The','No article'],a:2},
  {type:'fill',q:'Complete: "I saw ___ elephant at the zoo."',a:'an',hint:'Vowel sound'},
  {type:'mc',q:'Which uses "the" correctly?',opts:['She speaks the English.','The Thames is a river.','He plays the football.','We eat the breakfast.'],a:1},
  {type:'mc',q:'No article is used with:',opts:['Rivers','Mountains','Languages','Oceans'],a:2},
  {type:'fill',q:'Complete: "___ Nile is the longest river."',a:'The',hint:'Unique, specific river'},
  {type:'mc',q:'"I read ___ interesting article." Which article?',opts:['a','an','the','no article'],a:1},
  {type:'mc',q:'Second mention rule: "I have a cat. ___ cat is black."',opts:['A','An','The','No article'],a:2},
  {type:'fill',q:'Complete: "___ Alps are in Europe."',a:'The',hint:'Mountain ranges take "the"'},
  {type:'mc',q:'"___ university in our city is excellent." (specific)',opts:['A','An','The','No article'],a:2},
  {type:'mc',q:'Which is WRONG?',opts:['a book','an egg','the Earth','a honest man'],a:3},
  {type:'fill',q:'Complete: "He is ___ honest man."',a:'an',hint:'"Honest" starts with vowel sound /ɒ/'},
  {type:'mc',q:'"Play ___ guitar" uses:',opts:['a','an','the','no article'],a:2},
  {type:'mc',q:'"Go to ___ school" (as student) uses:',opts:['a','an','the','no article'],a:3},
  {type:'fill',q:'Complete: "She has ___ hour to finish."',a:'an',hint:'"Hour" starts with vowel sound'},
  {type:'mc',q:'Which correctly uses "a"?',opts:['a university','a hour','a apple','a easy job'],a:0},
  {type:'mc',q:'"___ Pacific Ocean is the largest." Correct:',opts:['A','An','The','No article'],a:2},
  {type:'fill',q:'Complete: "It was ___ unique experience."',a:'a',hint:'"Unique" starts with /juː/ consonant sound'},
  {type:'mc',q:'Zero article: "We eat ___ breakfast at 8."',opts:['a','an','the','no article'],a:3},
  {type:'mc',q:'"He is ___ best student in class."',opts:['a','an','the','no article'],a:2},
  {type:'fill',q:'Complete: "___ French Revolution changed history."',a:'The',hint:'Specific historical event'},
  {type:'mc',q:'"She bought ___ new dress and ___ dress was expensive."',opts:['a/a','a/the','the/a','the/the'],a:1},
  {type:'mc',q:'Which does NOT use an article?',opts:['The Nile','A dog','Mount Everest','An orange'],a:2},
  {type:'fill',q:'Complete: "He is ___ European." ("European" starts with /j/)',a:'a',hint:'Consonant sound /j/'},
  {type:'mc',q:'"___ rich should help the poor." (general class)',opts:['A','An','The','No article'],a:2},
  {type:'mc',q:'Which sentence is CORRECT?',opts:['I have a umbrella.','She is teacher.','He plays the piano.','They eat the rice daily.'],a:2},
  {type:'fill',q:'Complete: "___ Amazon is in Brazil."',a:'The',hint:'Rivers take "the"'},
  {type:'mc',q:'"Turn left at ___ next traffic light."',opts:['a','an','the','no article'],a:2},
  {type:'mc',q:'"I need ___ advice." (uncountable)',opts:['a','an','the','no article'],a:3},
  {type:'fill',q:'Complete: "She plays ___ violin beautifully."',a:'the',hint:'Musical instruments take "the"'},
 ],
};

// Default fallback question generator
function generateFallbackQuestions(topicId,count){
  const tp=TOPICS.find(t=>t.id===topicId);
  if(!tp)return[];
  const vocab=tp.vocab||[];
  const allWords=Object.values(VOCAB_CATEGORIES).flat();
  const qs=[];
  for(let i=0;i<count;i++){
    const w=vocab[i%vocab.length]||'English';
    const wd=allWords.find(x=>x.word===w)||{word:w,ru:'(translation)',uz:'(tarjima)',ex:`Example with ${w}.`};
    const wrongWords=allWords.filter(x=>x.word!==w).sort(()=>Math.random()-.5).slice(0,3);
    qs.push({
      type:'mc',
      q:`What is the meaning of "${wd.word}"?`,
      opts:shuffleArr([wd.ru,...wrongWords.map(x=>x.ru)]),
      a:null, // will be set after shuffle
      _correct:wd.ru,
    });
  }
  // set correct answer index
  qs.forEach(q=>{if(q._correct)q.a=q.opts.indexOf(q._correct);});
  return qs;
}

function shuffleArr(a){return [...a].sort(()=>Math.random()-.5)}

function getQuizQuestions(topicId){
  let pool=QUIZ_POOL[topicId]||[];
  if(pool.length<30){
    const extra=generateFallbackQuestions(topicId,30-pool.length);
    pool=[...pool,...extra];
  }
  // shuffle and pick 30 unique
  return shuffleArr(pool).slice(0,30);
}

function startTopicTest(topicId){
  const qs=getQuizQuestions(topicId);
  state.quizState={topicId,qs,current:0,score:0,answers:[]};
  renderQuiz();
  document.getElementById('topics-list-view').style.display='none';
  document.getElementById('topic-detail-view').style.display='block';
  document.getElementById('topic-detail-content').innerHTML='<div id="quiz-root"></div>';
  renderQuizQuestion();
}

function renderQuizQuestion(){
  const qs=state.quizState;
  if(qs.current>=qs.qs.length){showQuizResult();return;}
  const q=qs.qs[qs.current];
  const prog=Math.round((qs.current/qs.qs.length)*100);
  const root=document.getElementById('quiz-root');
  if(!root)return;
  root.innerHTML=`
    <div class="quiz-container">
      <div class="quiz-header">
        <span style="font-size:.82rem;color:var(--text3)">${t('question')} ${qs.current+1} ${t('of')} ${qs.qs.length}</span>
        <div class="quiz-progress"><div class="quiz-progress-fill" style="width:${prog}%"></div></div>
        <span style="font-size:.82rem;color:var(--accent);font-weight:700">✓ ${qs.score}</span>
      </div>
      <div class="question-card">
        <div class="question-type">${q.type==='mc'?'Multiple Choice':q.type==='fill'?'Fill in the Blank':'Question'}</div>
        <div class="question-text">${q.q}</div>
        ${q.type==='mc'?`
          <div class="options">
            ${q.opts.map((o,i)=>`<div class="option" id="opt-${i}" onclick="selectOption(${i})">${String.fromCharCode(65+i)}. ${o}</div>`).join('')}
          </div>
        `:q.type==='fill'?`
          <input class="fill-input" id="fill-inp" placeholder="Type your answer..." onkeydown="if(event.key==='Enter')checkFill()">
          ${q.hint?`<div style="color:var(--text3);font-size:.78rem;margin-top:8px">💡 Hint: ${q.hint}</div>`:''}
          <button class="btn btn-primary" style="margin-top:14px" onclick="checkFill()">${t('checkAnswer')}</button>
        `:''}
      </div>
      <div id="quiz-feedback" style="display:none"></div>
    </div>`;
}

function selectOption(i){
  const qs=state.quizState;
  const q=qs.qs[qs.current];
  document.querySelectorAll('.option').forEach(o=>o.classList.add('disabled'));
  const correct=q.a===i;
  document.getElementById('opt-'+i).classList.add(correct?'correct':'wrong');
  if(!correct)document.getElementById('opt-'+q.a).classList.add('correct');
  if(correct){qs.score++;addXP(10);}
  document.getElementById('quiz-feedback').style.display='block';
  document.getElementById('quiz-feedback').innerHTML=`
    <div style="display:flex;justify-content:space-between;align-items:center;margin-top:12px">
      <span style="font-weight:700;color:${correct?'var(--accent3)':'var(--accent5)'}">${correct?t('correct'):t('wrong')}</span>
      <button class="btn btn-primary" onclick="nextQuestion()">${qs.current+1<qs.qs.length?t('next'):t('finish')} →</button>
    </div>`;
}

function checkFill(){
  const qs=state.quizState;
  const q=qs.qs[qs.current];
  const inp=document.getElementById('fill-inp');
  const userAns=(inp.value||'').trim().toLowerCase();
  const correct=userAns===q.a.toLowerCase();
  inp.disabled=true;
  inp.style.borderColor=correct?'var(--accent3)':'var(--accent5)';
  if(correct){qs.score++;addXP(10);}
  document.getElementById('quiz-feedback').style.display='block';
  document.getElementById('quiz-feedback').innerHTML=`
    <div style="background:${correct?'rgba(16,185,129,.1)':'rgba(239,68,68,.1)'};border:1px solid ${correct?'var(--accent3)':'var(--accent5)'};border-radius:10px;padding:12px 16px;margin-bottom:10px">
      <div style="font-weight:700;color:${correct?'var(--accent3)':'var(--accent5)'};margin-bottom:4px">${correct?t('correct'):t('wrong')}</div>
      ${!correct?`<div style="font-size:.84rem;color:var(--text2)">Correct answer: <strong style="color:var(--text)">${q.a}</strong></div>`:''}
    </div>
    <div style="display:flex;justify-content:flex-end">
      <button class="btn btn-primary" onclick="nextQuestion()">${qs.current+1<qs.qs.length?t('next'):t('finish')} →</button>
    </div>`;
}

function nextQuestion(){
  state.quizState.current++;
  renderQuizQuestion();
}

function showQuizResult(){
  const qs=state.quizState;
  const pct=Math.round((qs.score/qs.qs.length)*100);
  state.scores[qs.topicId]=pct;
  state.topicsDone[qs.topicId]=pct;
  saveState();updateHomeStats();
  const grade=pct>=90?t('excellent'):pct>=65?t('good'):t('keepPracticing');
  document.getElementById('quiz-root').innerHTML=`
    <div class="result-card">
      <div style="font-size:2rem">🎯</div>
      <div style="font-size:1.1rem;font-weight:700;margin-top:12px">${t('yourScore')}</div>
      <div class="result-score">${pct}%</div>
      <div class="result-grade">${grade}</div>
      <div class="result-msg">${qs.score} / ${qs.qs.length} ${t('correct')}</div>
      <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
        <button class="btn btn-primary" onclick="startTopicTest('${qs.topicId}')">🔄 Retry</button>
        <button class="btn btn-outline" onclick="backToTopics()">← ${t('backToTopics')}</button>
      </div>
    </div>`;
}

// =========================================================
// LISTENING DATA
// =========================================================
const LISTENING_ITEMS=[
  {id:'l1',title:'Daily Routine',level:'Beginner',duration:'2:15',
   transcript:`Good morning! My name is Emma. Let me tell you about my <span class="highlight">daily routine</span>. I wake up at 7 o'clock every morning. First, I brush my teeth and wash my face. Then I make breakfast — usually eggs and toast with orange juice. I leave the house at 8:30 to catch the bus. I work at an office in the city centre. After work, I go to the gym three times a week. I usually cook dinner at home. My favourite meal is pasta. I go to bed at 10:30 PM. On weekends, I like to read books and go for walks in the park. How about your routine?`,
   questions:[
     {q:'What time does Emma wake up?',opts:['6:00','7:00','8:00','9:00'],a:1},
     {q:'What does Emma eat for breakfast?',opts:['Cereal','Pancakes','Eggs and toast','Sandwiches'],a:2},
     {q:'How does Emma get to work?',opts:['By car','On foot','By bus','By train'],a:2},
     {q:'How often does Emma go to the gym?',opts:['Every day','Twice a week','Three times a week','Never'],a:2},
   ]},
  {id:'l2',title:'At the Restaurant',level:'Beginner',duration:'3:00',
   transcript:`Waiter: "Good evening! Welcome to La Bella Italia. Do you have a <span class="highlight">reservation</span>?" Customer: "Yes, for two, under the name Johnson." Waiter: "Perfect! Follow me please. Here is your table. Can I get you something to drink first?" Customer: "Yes, could we have still water and two glasses of white wine?" Waiter: "Of course. Are you ready to order your food?" Customer: "I'll have the grilled salmon with vegetables, please." Friend: "And I'd like the mushroom risotto." Waiter: "Excellent choices! Any <span class="highlight">allergies</span> I should know about?" Customer: "I'm lactose intolerant." Waiter: "No problem, I'll make sure the kitchen knows. Your food will be ready in about 20 minutes."`,
   questions:[
     {q:'What is the customer\'s name?',opts:['Smith','Brown','Johnson','Wilson'],a:2},
     {q:'What drinks do they order?',opts:['Juice and beer','Water and white wine','Coke and red wine','Coffee and water'],a:1},
     {q:'What does the first customer order?',opts:['Pasta','Mushroom risotto','Grilled salmon','Chicken'],a:2},
     {q:'What dietary restriction does the customer have?',opts:['Vegan','Gluten intolerant','Lactose intolerant','Nut allergy'],a:2},
   ]},
  {id:'l3',title:'Job Interview',level:'Intermediate',duration:'4:30',
   transcript:`Interviewer: "Thank you for coming in today. Please tell me about your <span class="highlight">professional background</span>." Candidate: "Of course! I have five years of experience in software development, primarily working with Python and JavaScript. I graduated from MIT with a degree in Computer Science. In my previous role at TechCorp, I led a team of six developers and successfully delivered three major projects on time and within budget." Interviewer: "What would you say are your greatest strengths?" Candidate: "I'm an excellent communicator and problem-solver. I work well under pressure and I'm highly <span class="highlight">adaptable</span> to new technologies. I'm also a strong team player." Interviewer: "Where do you see yourself in five years?" Candidate: "I hope to advance to a senior engineering position and eventually transition into a leadership role where I can mentor junior developers and contribute to company strategy."`,
   questions:[
     {q:'How many years of experience does the candidate have?',opts:['3 years','4 years','5 years','6 years'],a:2},
     {q:'How many people did the candidate manage?',opts:['Three','Four','Five','Six'],a:3},
     {q:'What degree does the candidate have?',opts:['Physics','Business','Computer Science','Engineering'],a:2},
     {q:'What role does the candidate want in 5 years?',opts:['CEO','Senior engineer / leadership','Team member','Consultant'],a:1},
   ]},
  {id:'l4',title:'Climate Change Discussion',level:'Advanced',duration:'5:00',
   transcript:`Host: "Welcome to today's programme. We're discussing <span class="highlight">climate change</span> and its impact on global ecosystems. Dr. Chen, can you explain the current situation?" Dr. Chen: "Certainly. The Earth's average temperature has risen by approximately 1.2 degrees Celsius since pre-industrial times. This seemingly small increase has profound consequences — we're seeing more frequent <span class="highlight">extreme weather events</span>, rising sea levels, and the disruption of biodiversity. The main driver is the accumulation of greenhouse gases, particularly CO2 from fossil fuel combustion." Host: "What solutions are scientists proposing?" Dr. Chen: "The transition to renewable energy is paramount. Solar and wind power are now cheaper than coal in most markets. We also need to reform agriculture, which accounts for around 25% of global emissions, implement carbon capture technologies, and fundamentally rethink our consumption patterns. Individual action matters, but systemic change is absolutely essential."`,
   questions:[
     {q:'How much has Earth\'s temperature risen?',opts:['0.8°C','1.0°C','1.2°C','1.5°C'],a:2},
     {q:'What percentage of emissions does agriculture account for?',opts:['10%','15%','20%','25%'],a:3},
     {q:'What does Dr. Chen say about renewable energy costs?',opts:['More expensive','Same as coal','Cheaper than coal','Unknown'],a:2},
     {q:'What does Dr. Chen consider "absolutely essential"?',opts:['Individual action','Systemic change','Nuclear power','Reducing population'],a:1},
   ]},
];

let activeAudio={playing:false,item:null,progress:0,synthInterval:null};

function renderListening(){
  const el=document.getElementById('listening-list');
  el.innerHTML=LISTENING_ITEMS.map((item,idx)=>`
    <div class="audio-player">
      <div class="audio-controls">
        <button class="play-btn" id="play-${item.id}" onclick="togglePlay('${item.id}',${idx})">${activeAudio.item===item.id&&activeAudio.playing?'⏸':'▶'}</button>
        <div class="audio-track">
          <div class="audio-title">${item.title} <span class="tag" style="background:rgba(0,212,255,.1);color:var(--accent)">${item.level}</span></div>
          <div class="audio-subtitle">Duration: ${item.duration}</div>
        </div>
        <button class="btn btn-outline" onclick="stopAudio()">⏹</button>
      </div>
      <div class="waveform" id="wave-${item.id}">
        ${Array(40).fill(0).map((_,i)=>`<div class="waveform-bar" id="bar-${item.id}-${i}" style="height:${8+Math.random()*30}px"></div>`).join('')}
      </div>
      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <button class="btn btn-outline" onclick="showTranscript('${item.id}')">${t('showTranscript')}</button>
        <button class="btn btn-outline" onclick="startListeningQuiz('${item.id}')">📝 Take Quiz</button>
      </div>
      <div id="transcript-${item.id}" style="display:none"><div class="transcript-box" style="margin-top:12px">${item.transcript}</div></div>
      <div id="lquiz-${item.id}" style="display:none;margin-top:14px"></div>
    </div>
  `).join('');
}

function togglePlay(id,idx){
  if(activeAudio.item===id&&activeAudio.playing){
    stopAudio();return;
  }
  if(activeAudio.synthInterval)clearInterval(activeAudio.synthInterval);
  stopAudio();
  activeAudio={playing:true,item:id,progress:0,synthInterval:null};
  document.getElementById('play-'+id).textContent='⏸';
  const item=LISTENING_ITEMS[idx];
  speakText(item.transcript.replace(/<[^>]+>/g,''));
  let barI=0;
  activeAudio.synthInterval=setInterval(()=>{
    const bars=document.querySelectorAll(`[id^="bar-${id}-"]`);
    bars.forEach((b,i)=>b.classList.toggle('active',i<=barI%40));
    barI++;
  },120);
}

function stopAudio(){
  if(window.speechSynthesis)window.speechSynthesis.cancel();
  if(activeAudio.synthInterval)clearInterval(activeAudio.synthInterval);
  if(activeAudio.item){
    const pb=document.getElementById('play-'+activeAudio.item);
    if(pb)pb.textContent='▶';
    document.querySelectorAll(`[id^="bar-${activeAudio.item}-"]`).forEach(b=>b.classList.remove('active'));
  }
  activeAudio={playing:false,item:null,progress:0,synthInterval:null};
}

function speakText(text,rate=0.85){
  if(!window.speechSynthesis)return;
  window.speechSynthesis.cancel();
  const utt=new SpeechSynthesisUtterance(text);
  utt.lang='en-US';utt.rate=rate;
  const voices=window.speechSynthesis.getVoices();
  const en=voices.find(v=>v.lang.startsWith('en'));
  if(en)utt.voice=en;
  utt.onend=()=>{stopAudio();}; 
  window.speechSynthesis.speak(utt);
}

function showTranscript(id){
  const el=document.getElementById('transcript-'+id);
  el.style.display=el.style.display==='none'?'block':'none';
}

function startListeningQuiz(id){
  const item=LISTENING_ITEMS.find(i=>i.id===id);
  const root=document.getElementById('lquiz-'+id);
  let html='<div style="font-weight:700;margin-bottom:12px;color:var(--accent)">📝 Comprehension Questions</div>';
  html+=item.questions.map((q,qi)=>`
    <div style="background:var(--surface2);border:1px solid var(--border);border-radius:10px;padding:14px;margin-bottom:10px">
      <div style="font-weight:600;margin-bottom:10px">${qi+1}. ${q.q}</div>
      <div style="display:grid;gap:6px">
        ${q.opts.map((o,oi)=>`<div class="option" id="lq-${id}-${qi}-${oi}" onclick="checkLQ('${id}',${qi},${oi},${q.a})">${String.fromCharCode(65+oi)}. ${o}</div>`).join('')}
      </div>
    </div>
  `).join('');
  root.innerHTML=html;
  root.style.display='block';
}

function checkLQ(lid,qi,oi,correct){
  document.querySelectorAll(`[id^="lq-${lid}-${qi}-"]`).forEach(el=>el.classList.add('disabled'));
  document.getElementById(`lq-${lid}-${qi}-${oi}`).classList.add(oi===correct?'correct':'wrong');
  if(oi!==correct)document.getElementById(`lq-${lid}-${qi}-${correct}`).classList.add('correct');
  if(oi===correct)addXP(15);
}

// =========================================================
// SPEAKING
// =========================================================
const SPEAKING_SCRIPTS=[
  {id:'intro',title:'Introduce Yourself',icon:'👋',prompts:[
    "Hello! I'm Alex, your AI English teacher. Let's practice introductions! I'll start: My name is Alex, I'm an AI assistant, and I love helping people learn English. Now it's your turn! Tell me: What is your name?",
    "Great! And where are you from? Which city or country?",
    "Wonderful! How old are you? You can say 'I am [number] years old.'",
    "Perfect! And what do you do? Are you a student, a worker, or something else?",
    "Excellent! What are your hobbies? What do you enjoy doing in your free time?",
    "Amazing! You've completed an introduction! You did a great job. Let's practice more!"
  ]},
  {id:'weather',title:'Talk About Weather',icon:'🌤️',prompts:[
    "Let's talk about weather! What is the weather like in your city today? Is it sunny, cloudy, rainy, or something else?",
    "Interesting! What is your favourite season? Spring, summer, autumn, or winter? Why?",
    "Nice! What do you usually do when the weather is bad, like rainy or snowy?",
    "Great! What is the hottest month in your country?",
    "Perfect! Do you prefer hot weather or cold weather? Tell me why.",
  ]},
  {id:'food',title:'Discuss Food',icon:'🍕',prompts:[
    "Let's talk about food! What is your favourite food? Describe it to me.",
    "Delicious! Can you cook? What dishes can you prepare?",
    "Great! Describe the last meal you ate. What was it and how did it taste?",
    "Interesting! What is a traditional food from your country?",
    "Wonderful! If you could eat in any country in the world, where would you go and what would you try?",
  ]},
  {id:'travel',title:'Travel Plans',icon:'✈️',prompts:[
    "Hello traveller! Have you ever been abroad? Tell me about a trip you took or a trip you dream about.",
    "Interesting! What country would you most like to visit and why?",
    "Great! What do you prefer: beach holidays, city trips, or mountain adventures?",
    "Tell me — what would you pack in your suitcase for a two-week trip?",
    "Final question: What English phrases do you think are most important to know when travelling?",
  ]},
];

let activeSpeakingScript=null;
let speakingStepIdx=0;
let isRecording=false;
let recognition=null;

function renderSpeaking(){
  const grid=document.getElementById('speaking-topics-grid');
  grid.innerHTML=SPEAKING_SCRIPTS.map(s=>`
    <div class="topic-card" onclick="startSpeakingScript('${s.id}')">
      <div class="topic-icon">${s.icon}</div>
      <h3>${s.title}</h3>
      <p style="color:var(--text2);font-size:.8rem">AI will guide the conversation step by step</p>
    </div>
  `).join('');
  // init chat
  const chatEl=document.getElementById('speaking-chat');
  if(!chatEl.innerHTML){
    chatEl.innerHTML=`<div class="ai-message">👋 Hi! I'm Alex, your AI English teacher. Choose a conversation topic below or click the mic to start talking!</div>`;
  }
  renderSpeakingSuggestions();
}

function renderSpeakingSuggestions(){
  const el=document.getElementById('speaking-suggestions');
  if(!el)return;
  const s=[
    {label:'👋 Greetings',q:"Let's practice greetings"},
    {label:'🗣️ Free Talk',q:"Let's have a free conversation"},
    {label:'📝 Correct me',q:"Please correct my English mistakes"},
  ];
  el.innerHTML=s.map(x=>`<button class="btn btn-outline" style="font-size:.78rem" onclick="handleSpeechInput('${x.q}')">${x.label}</button>`).join('');
}

function startSpeakingScript(id){
  activeSpeakingScript=SPEAKING_SCRIPTS.find(s=>s.id===id);
  speakingStepIdx=0;
  const chatEl=document.getElementById('speaking-chat');
  chatEl.innerHTML='';
  addAIMessage(activeSpeakingScript.prompts[0]);
  speakAI(activeSpeakingScript.prompts[0]);
  speakingStepIdx=1;
}

function addAIMessage(text){
  const chatEl=document.getElementById('speaking-chat');
  const div=document.createElement('div');
  div.className='ai-message';
  div.innerHTML=`<div class="ai-label">🤖 Alex</div>${text}`;
  chatEl.appendChild(div);
  chatEl.scrollTop=chatEl.scrollHeight;
}

function addUserMessage(text){
  const chatEl=document.getElementById('speaking-chat');
  const div=document.createElement('div');
  div.className='user-message';
  div.innerHTML=`<div style="font-size:.7rem;color:var(--accent2);margin-bottom:4px;text-align:right">You</div>${text}`;
  chatEl.appendChild(div);
  chatEl.scrollTop=chatEl.scrollHeight;
}

function speakAI(text){
  if(!window.speechSynthesis)return;
  const utt=new SpeechSynthesisUtterance(text);
  utt.lang='en-US';utt.rate=0.9;
  const voices=window.speechSynthesis.getVoices();
  const en=voices.find(v=>v.lang.startsWith('en-US')&&v.name.includes('Female'))||voices.find(v=>v.lang.startsWith('en'));
  if(en)utt.voice=en;
  window.speechSynthesis.speak(utt);
}

function toggleMic(){
  if(isRecording){stopRecording();}else{startRecording();}
}

function startRecording(){
  isRecording=true;
  const btn=document.getElementById('mic-btn');
  const status=document.getElementById('mic-status');
  if(btn)btn.classList.add('recording');
  if(status)status.textContent=t('speakNow');
  if('SpeechRecognition' in window||'webkitSpeechRecognition' in window){
    const SR=window.SpeechRecognition||window.webkitSpeechRecognition;
    recognition=new SR();
    recognition.lang='en-US';
    recognition.continuous=false;
    recognition.interimResults=false;
    recognition.onresult=(e)=>{
      const transcript=e.results[0][0].transcript;
      stopRecording();
      handleSpeechInput(transcript);
    };
    recognition.onerror=()=>{stopRecording();showToast('Mic not available — type instead','error');};
    recognition.start();
  } else {
    // fallback: type
    const ans=prompt('Type your answer (mic not supported):');
    stopRecording();
    if(ans)handleSpeechInput(ans);
  }
}

function stopRecording(){
  isRecording=false;
  const btn=document.getElementById('mic-btn');
  const status=document.getElementById('mic-status');
  if(btn)btn.classList.remove('recording');
  if(status)status.textContent=t('tapToSpeak');
  if(recognition){try{recognition.stop();}catch(e){}}
}

async function handleSpeechInput(text){
  addUserMessage(text);
  addXP(5);
  // if following a script
  if(activeSpeakingScript&&speakingStepIdx<activeSpeakingScript.prompts.length){
    const next=activeSpeakingScript.prompts[speakingStepIdx];
    speakingStepIdx++;
    setTimeout(()=>{
      addAIMessage(next);
      speakAI(next);
    },800);
    return;
  }
  // free AI response
  const thinking=document.createElement('div');
  thinking.className='ai-message';
  thinking.innerHTML=`<div class="ai-label">🤖 Alex</div><div class="typing-indicator"><div class="typing-dot"></div><div class="typing-dot"></div><div class="typing-dot"></div></div>`;
  document.getElementById('speaking-chat').appendChild(thinking);
  document.getElementById('speaking-chat').scrollTop=999999;
  const reply=await callAI(`You are Alex, a friendly English teacher. The student said: "${text}". Respond naturally in English, correct any grammar mistakes gently, and ask a follow-up question. Be encouraging. Keep response under 80 words.`);
  thinking.remove();
  addAIMessage(reply);
  speakAI(reply);
}

// =========================================================
// READING
// =========================================================
const READING_TEXTS=[
  {id:'r1',title:'The History of the Internet',level:'Intermediate',
   text:`The Internet is one of humanity's greatest inventions. It began in 1969 as ARPANET, a network created by the U.S. Department of Defense to allow computers to communicate with each other. The network was initially used by universities and government agencies for research purposes.

In 1991, Tim Berners-Lee invented the World Wide Web, which made the Internet accessible to ordinary people. He created HTML (HyperText Markup Language) and HTTP (HyperText Transfer Protocol), which remain the foundation of web pages today.

The 1990s saw an explosion of Internet usage. Companies like Amazon, Google, and eBay were founded during this period, forever changing commerce and information access. By the year 2000, approximately 400 million people were using the Internet worldwide.

Today, over 5 billion people are connected to the Internet, representing more than 60% of the world's population. The Internet has transformed every aspect of human life — communication, education, entertainment, business, and healthcare. Social media platforms like Facebook, Twitter, and Instagram have created entirely new ways for people to connect and share information.

Looking ahead, technologies like 5G, artificial intelligence, and the Internet of Things (IoT) promise to make the Internet even more integrated into our daily lives.`,
   questions:[
     {q:'When was ARPANET created?',opts:['1959','1969','1979','1989'],a:1},
     {q:'Who invented the World Wide Web?',opts:['Steve Jobs','Bill Gates','Tim Berners-Lee','Mark Zuckerberg'],a:2},
     {q:'How many people use the Internet today?',opts:['1 billion','3 billion','5 billion','7 billion'],a:2},
     {q:'What does IoT stand for?',opts:['Internet of Technology','Internet of Things','Interface of Technology','Integrated Online Technology'],a:1},
   ]},
  {id:'r2',title:'Artificial Intelligence: The Future Is Now',level:'Advanced',
   text:`Artificial Intelligence (AI) has transitioned from science fiction to everyday reality with remarkable speed. Machine learning algorithms now power the recommendations on Netflix and Spotify, the facial recognition on your smartphone, and the virtual assistants like Siri and Alexa that many people interact with daily.

The field of AI is built on the concept of teaching machines to learn from data rather than being explicitly programmed for every task. Deep learning, a subset of machine learning, uses neural networks inspired by the human brain to process complex patterns in data.

Recent breakthroughs have been extraordinary. In 2022, OpenAI's ChatGPT demonstrated that AI could engage in sophisticated human-like conversations, write code, analyze documents, and create creative content. Just months later, image generation models like DALL-E and Midjourney showed that AI could produce photorealistic images from text descriptions.

These advances raise profound questions about the future of work, creativity, and human identity. Will AI replace millions of jobs? Will it help us solve climate change and cure diseases? Or will it pose risks if not properly managed?

Most experts agree that AI will be a transformative force comparable to the Industrial Revolution. The key challenge for humanity is ensuring this technology is developed responsibly, equitably, and in service of all people — not just the privileged few.`,
   questions:[
     {q:'What powers Netflix recommendations?',opts:['Human editors','Machine learning','Simple algorithms','Random selection'],a:1},
     {q:'What is deep learning inspired by?',opts:['Computer chips','The human brain','Natural language','Statistical models'],a:1},
     {q:'When was ChatGPT launched?',opts:['2020','2021','2022','2023'],a:2},
     {q:'What do experts compare AI\'s impact to?',opts:['The Space Race','The Cold War','The Industrial Revolution','The Digital Revolution'],a:2},
   ]},
];

function renderReading(){
  const el=document.getElementById('reading-list');
  el.innerHTML=READING_TEXTS.map(item=>`
    <div class="content-box" style="margin-bottom:20px">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:14px">
        <div>
          <h2 style="margin:0;margin-bottom:6px">${item.title}</h2>
          <span class="tag level-intermediate">${item.level}</span>
        </div>
        <button class="btn btn-primary" onclick="startReadingQuiz('${item.id}')">📝 Quiz</button>
      </div>
      <div style="color:var(--text2);font-size:.88rem;line-height:1.9;white-space:pre-line">${item.text}</div>
      <div id="rquiz-${item.id}" style="display:none;margin-top:18px;padding-top:18px;border-top:1px solid var(--border)"></div>
    </div>
  `).join('');
}

function startReadingQuiz(id){
  const item=READING_TEXTS.find(i=>i.id===id);
  const root=document.getElementById('rquiz-'+id);
  root.innerHTML='<div style="font-weight:700;margin-bottom:12px;color:var(--accent)">📝 Comprehension Quiz</div>'+
    item.questions.map((q,qi)=>`
      <div style="background:var(--surface2);border:1px solid var(--border);border-radius:10px;padding:14px;margin-bottom:10px">
        <div style="font-weight:600;margin-bottom:10px">${qi+1}. ${q.q}</div>
        <div style="display:grid;gap:6px">
          ${q.opts.map((o,oi)=>`<div class="option" id="rq-${id}-${qi}-${oi}" onclick="checkRQ('${id}',${qi},${oi},${q.a})">${String.fromCharCode(65+oi)}. ${o}</div>`).join('')}
        </div>
      </div>`).join('');
  root.style.display='block';
}

function checkRQ(lid,qi,oi,correct){
  document.querySelectorAll(`[id^="rq-${lid}-${qi}-"]`).forEach(el=>el.classList.add('disabled'));
  document.getElementById(`rq-${lid}-${qi}-${oi}`).classList.add(oi===correct?'correct':'wrong');
  if(oi!==correct)document.getElementById(`rq-${lid}-${qi}-${correct}`).classList.add('correct');
  if(oi===correct)addXP(20);
}

// =========================================================
// WRITING
// =========================================================
const WRITING_TASKS=[
  {id:'w1',title:'Describe Your Morning Routine',prompt:'Write 80-120 words describing what you do every morning from waking up to leaving home. Use Present Simple tense.',tips:'Use: First, Then, After that, Finally. Verbs: wake up, brush, eat, leave'},
  {id:'w2',title:'A Trip You Dream About',prompt:'Describe a place you would love to visit. Write 100-150 words. Use conditionals: "If I could go...", "I would..."',tips:'Include: location, activities, food, reason for choosing'},
  {id:'w3',title:'My Opinion on Technology',prompt:'Do you think smartphones help or harm young people? Write 120-160 words expressing your opinion with 2-3 reasons.',tips:'Use: In my opinion, I believe, Firstly, Furthermore, In conclusion'},
  {id:'w4',title:'Describe a Person You Admire',prompt:'Write 100-130 words about someone you admire (real or fictional). Describe their appearance, character, and what makes them special.',tips:'Adjectives: brave, intelligent, kind, determined, inspiring'},
];

function renderWriting(){
  const el=document.getElementById('writing-tasks');
  el.innerHTML=WRITING_TASKS.map(task=>`
    <div class="content-box" style="margin-bottom:16px">
      <h2>${task.title}</h2>
      <p style="color:var(--text2);margin-bottom:10px">${task.prompt}</p>
      <div style="background:rgba(245,158,11,.07);border:1px solid rgba(245,158,11,.2);border-radius:8px;padding:10px 14px;font-size:.8rem;color:var(--accent4);margin-bottom:14px">💡 Tips: ${task.tips}</div>
      <textarea id="writing-${task.id}" style="width:100%;background:var(--surface2);border:1.5px solid var(--border);border-radius:10px;padding:14px;color:var(--text);font-family:'Sora',sans-serif;font-size:.9rem;min-height:120px;resize:vertical;outline:none" placeholder="Write your answer here..."></textarea>
      <div style="display:flex;align-items:center;justify-content:space-between;margin-top:10px">
        <span id="wcount-${task.id}" style="font-size:.78rem;color:var(--text3)">0 words</span>
        <button class="btn btn-primary" onclick="submitWriting('${task.id}')">📤 ${t('submitWriting')}</button>
      </div>
      <div id="wfeedback-${task.id}" style="display:none;margin-top:14px"></div>
    </div>
  `).join('');
  WRITING_TASKS.forEach(task=>{
    const ta=document.getElementById('writing-'+task.id);
    if(ta)ta.addEventListener('input',()=>{
      const wc=ta.value.trim().split(/\s+/).filter(Boolean).length;
      document.getElementById('wcount-'+task.id).textContent=wc+' words';
    });
  });
}

async function submitWriting(id){
  const ta=document.getElementById('writing-'+id);
  const text=ta?ta.value.trim():'';
  if(!text||text.split(/\s+/).length<10){showToast('Please write at least 10 words!','error');return;}
  const fb=document.getElementById('wfeedback-'+id);
  fb.style.display='block';
  fb.innerHTML=`<div class="loading"><div class="loading-spinner"></div>${t('aiReviewing')}</div>`;
  const task=WRITING_TASKS.find(t=>t.id===id);
  const reply=await callAI(`You are an English writing teacher. Review this student's writing:

Task: "${task.prompt}"
Student's text: "${text}"

Provide feedback in this exact format:
SCORE: [0-100]
STRENGTHS: [2-3 positive points]
CORRECTIONS: [List specific grammar/vocabulary corrections]
SUGGESTIONS: [2-3 ways to improve]
IMPROVED VERSION: [Rewrite 1-2 improved sentences]

Be encouraging and specific. Keep total response under 200 words.`);
  fb.innerHTML=`
    <div style="background:rgba(0,212,255,.06);border:1px solid rgba(0,212,255,.2);border-radius:12px;padding:18px;font-size:.88rem;line-height:1.7;white-space:pre-wrap">${reply}</div>
  `;
  addXP(25);
}

// =========================================================
// LEADERBOARD
// =========================================================
const LEADERBOARD_DATA=[
  {name:'Anna K.',flag:'🇬🇧',xp:4820,level:'Advanced',badge:'🏅 Master',avatar:'👩'},
  {name:'Mikhail S.',flag:'🇷🇺',xp:4150,level:'Advanced',badge:'🥈 Expert',avatar:'👨'},
  {name:'Dilnoza A.',flag:'🇺🇿',xp:3920,level:'Intermediate',badge:'🎖️ Pro',avatar:'👩'},
  {name:'Carlos M.',flag:'🇪🇸',xp:3640,level:'Intermediate',badge:'🎯 Skilled',avatar:'👨'},
  {name:'Yuki T.',flag:'🇯🇵',xp:3210,level:'Intermediate',badge:'⭐ Rising',avatar:'👩'},
  {name:'Omar B.',flag:'🇰🇿',xp:2990,level:'Intermediate',badge:'📚 Learner',avatar:'👨'},
  {name:'Sofia L.',flag:'🇩🇪',xp:2750,level:'Beginner',badge:'🌟 Active',avatar:'👩'},
  {name:'James W.',flag:'🇺🇸',xp:2530,level:'Beginner',badge:'🌱 Starter',avatar:'👨'},
  {name:'Aisha M.',flag:'🇳🇬',xp:2280,level:'Beginner',badge:'📖 Studying',avatar:'👩'},
  {name:'You',flag:'🏆',xp:state.xp,level:'Learner',badge:'🎮 Player',avatar:'🧑'},
];

function renderLeaderboard(){
  const sorted=[...LEADERBOARD_DATA].map(d=>d.name==='You'?{...d,xp:state.xp}:d).sort((a,b)=>b.xp-a.xp);
  document.getElementById('leaderboard-list').innerHTML=sorted.map((p,i)=>`
    <div class="lb-card" style="${p.name==='You'?'border-color:var(--accent);background:rgba(0,212,255,.04)':''}">
      <div class="lb-rank ${i===0?'top1':i===1?'top2':i===2?'top3':''}">${i===0?'🥇':i===1?'🥈':i===2?'🥉':'#'+(i+1)}</div>
      <div class="lb-avatar" style="background:${['linear-gradient(135deg,#f59e0b,#ef4444)','linear-gradient(135deg,#94a3b8,#64748b)','linear-gradient(135deg,#b45309,#78350f)','linear-gradient(135deg,var(--accent),var(--accent2))'][i%4]}">${p.avatar}</div>
      <div class="lb-name">${p.flag} ${p.name}</div>
      <div><div class="lb-xp">⚡ ${p.xp.toLocaleString()}</div><div style="font-size:.72rem;color:var(--text3)">${p.level}</div></div>
      <span class="lb-badge" style="background:rgba(0,212,255,.1);color:var(--accent)">${p.badge}</span>
    </div>
  `).join('');
}

// =========================================================
// AI TUTOR CHAT
// =========================================================
const AI_KEY='';// handled by proxy

async function callAI(prompt,system='You are an expert English teacher. Answer clearly and helpfully. Keep responses concise and educational.'){
  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',
        max_tokens:1000,
        system,
        messages:[{role:'user',content:prompt}]
      })
    });
    const data=await res.json();
    if(data.content&&data.content[0])return data.content[0].text;
    if(data.error)return getFallbackResponse(prompt);
    return getFallbackResponse(prompt);
  }catch(e){return getFallbackResponse(prompt);}
}

function getFallbackResponse(prompt){
  const p=prompt.toLowerCase();
  if(p.includes('grammar')||p.includes('tense'))
    return "Great question about grammar! English has 12 tenses. The most important ones for beginners are: Present Simple (I work), Past Simple (I worked), and Future Simple (I will work). Would you like me to explain any specific tense in detail?";
  if(p.includes('vocabulary')||p.includes('word'))
    return "Building vocabulary is key to English fluency! Try learning 10 new words daily in context. The most effective method: see the word, learn its pronunciation, understand its meaning, and use it in a sentence. Which topic's vocabulary would you like to explore?";
  if(p.includes('pronunciation')||p.includes('speak'))
    return "For better pronunciation, focus on: 1) Word stress (im-POR-tant, not IM-portant), 2) Connected speech (gonna, wanna, gonna), 3) The sounds that don't exist in your language. Listen to native speakers daily and repeat! What specific sounds challenge you?";
  if(p.includes('hello')||p.includes('hi'))
    return "Hello! Great to meet you! I'm your AI English tutor. I can help you with grammar, vocabulary, pronunciation, writing, and conversation practice. What would you like to work on today?";
  return "That's a great question! As your English tutor, I'm here to help you improve. The key to English fluency is consistent practice — even 20 minutes daily makes a huge difference. Try using new words in sentences, watch English movies with subtitles, and don't be afraid to make mistakes. What specific aspect of English shall we work on?";
}

function initAI(){
  const chatEl=document.getElementById('ai-chat-messages');
  if(!chatEl.innerHTML.trim()){
    chatEl.innerHTML=`<div class="ai-msg"><div class="ai-label">🤖 AI Tutor</div>Hello! I'm your AI English tutor, available 24/7. I can help you with grammar, vocabulary, pronunciation, writing corrections, and conversation practice. What would you like to learn today?</div>`;
  }
  const sugg=document.getElementById('ai-suggestions');
  const suggestions=[
    'Explain Present Perfect',
    'Check my writing',
    'Give me 5 new words',
    'How to sound more natural?',
    'What are common mistakes?',
    'Teach me phrasal verbs',
  ];
  sugg.innerHTML=suggestions.map(s=>`<button class="btn btn-outline" style="font-size:.75rem" onclick="sendAIMessageText('${s}')">${s}</button>`).join('');
}

async function sendAIMessage(){
  const inp=document.getElementById('ai-chat-input');
  const text=inp.value.trim();
  if(!text)return;
  sendAIMessageText(text);
  inp.value='';
}

async function sendAIMessageText(text){
  const chatEl=document.getElementById('ai-chat-messages');
  chatEl.innerHTML+=`<div class="user-msg">${text}</div>`;
  chatEl.innerHTML+=`<div class="ai-msg" id="ai-typing"><div class="ai-label">🤖 AI Tutor</div><div class="typing-indicator"><div class="typing-dot"></div><div class="typing-dot"></div><div class="typing-dot"></div></div></div>`;
  chatEl.scrollTop=chatEl.scrollHeight;
  
  state.chatHistory.push({role:'user',content:text});
  const history=state.chatHistory.slice(-10);
  
  const reply=await callAI(text,`You are an expert English teacher named Alex. You're encouraging, clear, and professional. Answer in the same language the student uses (English, Russian, or Uzbek), but teach English. Give concrete examples. Be concise but thorough. If the student makes grammar mistakes, gently correct them. Current conversation context: the student is a language learner.`);
  
  state.chatHistory.push({role:'assistant',content:reply});
  const typingEl=document.getElementById('ai-typing');
  if(typingEl)typingEl.innerHTML=`<div class="ai-label">🤖 AI Tutor</div>${reply.replace(/\n/g,'<br>')}`;
  chatEl.scrollTop=chatEl.scrollHeight;
  addXP(3);
}

// =========================================================
// TOAST
// =========================================================
function showToast(msg,type='success'){
  const t=document.getElementById('toast');
  t.textContent=msg;
  t.className='toast '+type+' show';
  setTimeout(()=>t.classList.remove('show'),2800);
}

// =========================================================
// RENDER ALL
// =========================================================
function renderAll(){
  renderTopics();
  renderVocab();
  if(document.getElementById('section-listening').classList.contains('active'))renderListening();
  if(document.getElementById('section-leaderboard').classList.contains('active'))renderLeaderboard();
  if(document.getElementById('section-reading').classList.contains('active'))renderReading();
  if(document.getElementById('section-writing').classList.contains('active'))renderWriting();
}

// init
renderTopics();
document.getElementById('xp-badge').textContent='⚡ '+state.xp+' XP';
updateHomeStats();
initAI();

// Mobile: close sidebar on nav click
document.querySelectorAll('.nav-item').forEach(ni=>{
  ni.addEventListener('click',()=>{
    if(window.innerWidth<=900){document.querySelector('.sidebar').style.transform='translateX(-100%)';}
  });
});
</script>
</body>
</html>
