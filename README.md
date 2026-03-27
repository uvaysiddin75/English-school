<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>SpeakUP English</title>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800;900&family=Crimson+Pro:ital,wght@0,300;0,400;1,300&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
--bg:#07090f;--s1:#0d1117;--s2:#161b27;--s3:#1c2333;
--brd:#232d40;--brd2:#2a3650;
--blue:#4f8ef7;--cyan:#22d3ee;--purple:#a78bfa;
--green:#34d399;--red:#f87171;--gold:#fbbf24;
--txt:#dde4f0;--muted:#5a6a85;--muted2:#8899b0;
--r:12px;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--txt);font-family:'Outfit',sans-serif;min-height:100vh;overflow-x:hidden}

/* BG */
body::before{content:'';position:fixed;inset:0;
background:radial-gradient(ellipse 80% 50% at 10% 0%,rgba(79,142,247,.07) 0%,transparent 60%),
            radial-gradient(ellipse 60% 40% at 90% 100%,rgba(167,139,250,.05) 0%,transparent 60%);
pointer-events:none;z-index:0}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;height:60px;
background:rgba(7,9,15,.92);backdrop-filter:blur(20px);
border-bottom:1px solid var(--brd);
display:flex;align-items:center;padding:0 24px;gap:12px}
.logo{font-weight:900;font-size:1.25rem;letter-spacing:-.03em;
background:linear-gradient(135deg,var(--blue),var(--cyan));
-webkit-background-clip:text;-webkit-text-fill-color:transparent;
margin-right:auto}
.lng{padding:5px 12px;border-radius:20px;border:1px solid var(--brd);
background:transparent;color:var(--muted2);cursor:pointer;
font-family:'Outfit',sans-serif;font-size:.8rem;font-weight:600;
transition:.2s;letter-spacing:.02em}
.lng:hover{color:var(--txt);border-color:var(--brd2)}
.lng.on{background:var(--blue);color:#fff;border-color:var(--blue)}

/* TABS BAR */
.tabbar{position:fixed;top:60px;left:0;right:0;z-index:190;
background:rgba(7,9,15,.88);backdrop-filter:blur(16px);
border-bottom:1px solid var(--brd);
display:flex;overflow-x:auto;padding:0 12px;
scrollbar-width:none}
.tabbar::-webkit-scrollbar{display:none}
.tbtn{display:flex;align-items:center;gap:6px;padding:14px 16px;
background:none;border:none;border-bottom:2px solid transparent;
color:var(--muted2);cursor:pointer;font-family:'Outfit',sans-serif;
font-size:.85rem;font-weight:500;white-space:nowrap;transition:.2s}
.tbtn:hover{color:var(--txt)}
.tbtn.on{color:var(--blue);border-bottom-color:var(--blue)}

/* MAIN */
.wrap{position:relative;z-index:1;max-width:1080px;margin:0 auto;padding:136px 20px 60px}

/* HERO */
.hero{text-align:center;padding:20px 0 48px}
.hero h1{font-size:clamp(2rem,4.5vw,3.2rem);font-weight:900;
letter-spacing:-.04em;line-height:1.1;
background:linear-gradient(135deg,#dde4f0 0%,var(--cyan) 100%);
-webkit-background-clip:text;-webkit-text-fill-color:transparent;margin-bottom:12px}
.hero p{color:var(--muted2);font-size:1rem;margin-bottom:24px}
.hero-stats{display:flex;justify-content:center;gap:32px;flex-wrap:wrap}
.hstat{text-align:center}
.hstat-n{font-size:1.6rem;font-weight:800;color:var(--blue)}
.hstat-l{font-size:.75rem;color:var(--muted);text-transform:uppercase;letter-spacing:.08em}

/* PAGE */
.page{display:none;animation:fin .25s ease}
.page.on{display:block}
@keyframes fin{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}

/* SECTION HEADER */
.sh{margin-bottom:24px}
.sh h2{font-size:1.5rem;font-weight:800;letter-spacing:-.02em;margin-bottom:4px}
.sh p{color:var(--muted2);font-size:.9rem}

/* CARD */
.card{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);padding:20px}
.card+.card{margin-top:12px}

/* TOPIC GRID */
.tgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:12px}.tcard{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);
padding:18px;cursor:pointer;transition:.22s;position:relative;overflow:hidden}
.tcard::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;
background:var(--tc,var(--blue));transform:scaleX(0);transform-origin:left;transition:.22s}
.tcard:hover{transform:translateY(-2px);border-color:var(--tc,var(--blue))}
.tcard:hover::after{transform:scaleX(1)}
.tcard-ico{font-size:1.8rem;margin-bottom:10px}
.tcard-name{font-weight:700;font-size:.95rem;margin-bottom:4px}
.tcard-desc{color:var(--muted2);font-size:.8rem;line-height:1.5;margin-bottom:12px}
.tcard-foot{display:flex;align-items:center;gap:8px}
.badge{font-size:.7rem;font-weight:700;padding:2px 9px;border-radius:10px;
background:rgba(79,142,247,.15);color:var(--blue)}
.tcard-qs{font-size:.75rem;color:var(--muted)}
.pbar{height:3px;background:var(--brd);border-radius:2px;margin-top:10px;overflow:hidden}
.pbar-f{height:100%;border-radius:2px;background:var(--tc,var(--blue));transition:width .6s}

/* TOPIC DETAIL */
#detail-view{display:none}
#detail-view.on{display:block}
.back{display:inline-flex;align-items:center;gap:6px;
  background:none;border:none;color:var(--muted2);cursor:pointer;
  font-family:'Outfit',sans-serif;font-size:.88rem;margin-bottom:20px;transition:.2s}
.back:hover{color:var(--txt)}
.lesson-body{color:#8899b0;line-height:1.85;font-size:.92rem}
.lesson-body h3{color:var(--cyan);font-size:.95rem;margin:16px 0 6px}
.lesson-body strong{color:var(--txt)}
.ex-box{background:var(--s2);border-left:3px solid var(--blue);
  border-radius:0 8px 8px 0;padding:10px 14px;margin:10px 0;
  font-style:italic;color:var(--cyan);font-size:.88rem}
.formula{font-family:monospace;background:var(--s2);border:1px solid var(--brd);
  border-radius:8px;padding:8px 12px;color:var(--blue);font-size:.88rem;margin:8px 0}
.btn-start{display:inline-flex;align-items:center;gap:8px;margin-top:16px;
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  color:#fff;border:none;border-radius:10px;padding:12px 24px;
  font-family:'Outfit',sans-serif;font-size:.95rem;font-weight:700;cursor:pointer;transition:.2s}
.btn-start:hover{opacity:.85}

/* TEST */
#test-view{display:none}
#test-view.on{display:block}
.test-top{display:flex;justify-content:space-between;align-items:center;
  background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);
  padding:16px 20px;margin-bottom:16px;flex-wrap:wrap;gap:12px}
.test-top-l h3{font-weight:700;font-size:1rem}
.test-top-l span{font-size:.75rem;color:var(--muted2)}
.test-prog{display:flex;align-items:center;gap:10px}
.prog-track{width:130px;height:5px;background:var(--brd);border-radius:3px;overflow:hidden}
.prog-fill{height:100%;background:linear-gradient(90deg,var(--blue),var(--cyan));transition:width .3s}
.qnum{font-size:.82rem;color:var(--muted2)}
.qcard{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);padding:24px}
.qcard-num{font-size:.75rem;font-weight:700;color:var(--blue);text-transform:uppercase;margin-bottom:10px}
.qcard-q{font-size:1rem;font-weight:600;line-height:1.6;margin-bottom:20px}
.opts{display:flex;flex-direction:column;gap:8px}
.opt{display:flex;align-items:center;gap:10px;background:var(--s2);
  border:1px solid var(--brd);border-radius:10px;padding:12px 14px;
  cursor:pointer;transition:.18s;font-size:.9rem}
.opt:hover{border-color:var(--blue);background:rgba(79,142,247,.08)}
.opt.sel{border-color:var(--blue);background:rgba(79,142,247,.14)}
.opt.ok{border-color:var(--green);background:rgba(52,211,153,.1)}
.opt.bad{border-color:var(--red);background:rgba(248,113,113,.08)}
.opt-l{width:26px;height:26px;border-radius:50%;background:var(--brd);
  display:flex;align-items:center;justify-content:center;font-size:.75rem;font-weight:700;flex-shrink:0}
.test-btns{display:flex;justify-content:space-between;margin-top:20px}
.btn{padding:9px 20px;border-radius:9px;border:none;cursor:pointer;
  font-family:'Outfit',sans-serif;font-size:.88rem;font-weight:600;transition:.2s}
.btn-p{background:var(--blue);color:#fff}
.btn-p:hover{background:#3a7ef0}
.btn-o{background:transparent;border:1px solid var(--brd);color:var(--txt)}
.btn-o:hover{border-color:var(--blue);color:var(--blue)}
.btn:disabled{opacity:.35;cursor:not-allowed}

/* RESULT */
.result-box{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);
  padding:32px;text-align:center}
.score-ring{width:110px;height:110px;border-radius:50%;border:4px solid;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  margin:0 auto 20px}
.score-n{font-size:1.8rem;font-weight:900}
.score-s{font-size:.7rem;color:var(--muted2)}
.res-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:20px 0}
.rstat{background:var(--s2);border-radius:9px;padding:12px;text-align:center}
.rstat-n{font-size:1.3rem;font-weight:800}
.rstat-l{font-size:.72rem;color:var(--muted2)}
.ai-box{background:var(--s2);border:1px solid var(--brd);border-radius:var(--r);
  padding:16px;text-align:left;margin:16px 0}
.ai-tag{display:inline-flex;align-items:center;gap:5px;font-size:.75rem;font-weight:700;
  background:rgba(167,139,250,.15);color:var(--purple);
  border-radius:20px;padding:3px 10px;margin-bottom:10px}
.ai-txt{color:var(--muted2);font-size:.88rem;line-height:1.7}
.dot-wrap{display:flex;gap:4px;align-items:center}
.dot{width:6px;height:6px;border-radius:50%;background:var(--blue);
  animation:bop .6s ease infinite}
.dot:nth-child(2){animation-delay:.15s}
.dot:nth-child(3){animation-delay:.3s}
@keyframes bop{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}


/* READING */
.read-txt{background:var(--s2);border:1px solid var(--brd);border-radius:var(--r);
  padding:16px;color:var(--muted2);line-height:1.85;font-size:.9rem;
  max-height:240px;overflow-y:auto;margin-bottom:12px}
.read-txt p{margin-bottom:12px}

/* WRITING */
.w-prompt{background:rgba(167,139,250,.08);border:1px solid rgba(167,139,250,.25);
  border-radius:var(--r);padding:12px 16px;color:var(--purple);font-size:.88rem;margin-bottom:10px}
.w-area{width:100%;background:var(--s2);border:1px solid var(--brd);
  border-radius:var(--r);padding:12px;color:var(--txt);
  font-family:'Outfit',sans-serif;font-size:.9rem;line-height:1.7;
  resize:vertical;min-height:140px;outline:none;transition:.2s}
.w-area:focus{border-color:var(--purple)}
.w-foot{display:flex;justify-content:space-between;align-items:center;margin-top:8px}
.wc{font-size:.78rem;color:var(--muted)}/* VOCAB */
.vgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:10px}
.vcard{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);
  padding:14px;cursor:pointer;transition:.2s}
.vcard:hover{border-color:var(--gold);transform:translateY(-2px)}
.vword{font-size:1rem;font-weight:800;color:var(--gold);margin-bottom:4px}
.vtrans{font-size:.8rem;color:var(--muted2);margin-bottom:6px}
.vex{font-size:.77rem;color:#6a7a90;font-style:italic;line-height:1.5}

/* GRAMMAR */
.grule{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);
  padding:18px;margin-bottom:12px}
.grule h3{font-size:.95rem;font-weight:700;color:var(--cyan);margin-bottom:8px}
.grule p{color:var(--muted2);font-size:.87rem;line-height:1.7}

/* SPEAKING */
.sp-card{display:flex;gap:14px;background:var(--s1);border:1px solid var(--brd);
  border-radius:var(--r);padding:18px;margin-bottom:12px}
.mic-btn{width:44px;height:44px;border-radius:50%;flex-shrink:0;
  background:rgba(248,113,113,.12);border:1px solid rgba(248,113,113,.3);
  cursor:pointer;font-size:1.1rem;transition:.2s}
.mic-btn:hover{background:rgba(248,113,113,.25)}
.sp-body{}
.sp-task{font-weight:600;font-size:.9rem;margin-bottom:6px}
.sp-hint{font-size:.8rem;color:var(--muted2)}

/* AI CHAT */
.chat-wrap{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);overflow:hidden}
.chat-head{display:flex;align-items:center;gap:10px;padding:14px 18px;border-bottom:1px solid var(--brd)}
.chat-av{width:34px;height:34px;border-radius:50%;
  background:linear-gradient(135deg,var(--purple),var(--blue));
  display:flex;align-items:center;justify-content:center;font-size:.9rem;flex-shrink:0}
.chat-info-name{font-weight:700;font-size:.9rem}
.chat-info-stat{font-size:.72rem;color:var(--green)}
.chat-msgs{padding:16px;min-height:280px;max-height:380px;overflow-y:auto;
  display:flex;flex-direction:column;gap:12px}
.msg{max-width:82%}
.msg.ai{align-self:flex-start}
.msg.usr{align-self:flex-end}
.msg-b{padding:10px 14px;border-radius:12px;font-size:.88rem;line-height:1.6;word-break:break-word}
.msg.ai .msg-b{background:var(--s2);border:1px solid var(--brd)}
.msg.usr .msg-b{background:var(--blue);color:#fff}
.msg-t{font-size:.68rem;color:var(--muted);margin-top:4px}
.chat-inp-row{display:flex;gap:8px;padding:12px 16px;border-top:1px solid var(--brd)}
.chat-inp{flex:1;background:var(--s2);border:1px solid var(--brd);border-radius:9px;
  padding:9px 13px;color:var(--txt);font-family:'Outfit',sans-serif;font-size:.88rem;
  outline:none;transition:.2s}
.chat-inp:focus{border-color:var(--blue)}
.send-btn{background:var(--blue);color:#fff;border:none;border-radius:9px;
  padding:9px 14px;cursor:pointer;font-size:1rem;transition:.2s}
.send-btn:hover{background:#3a7ef0}

/* PROGRESS */
.prog-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:10px;margin-bottom:20px}
.pgcard{background:var(--s1);border:1px solid var(--brd);border-radius:var(--r);padding:16px}
.pgcard-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:12px}
.pgcard-lbl{font-size:.85rem;color:var(--muted2)}
.pgcard-pct{font-size:1.6rem;font-weight:900}
.pgbar{height:6px;background:var(--brd);border-radius:3px;overflow:hidden}
.pgbar-f{height:100%;border-radius:3px;transition:width 1s ease}
.analyze-btn{display:inline-flex;align-items:center;gap:8px;margin-bottom:20px;
  background:linear-gradient(135deg,var(--purple),var(--blue));
  color:#fff;border:none;border-radius:10px;padding:11px 22px;
  font-family:'Outfit',sans-serif;font-size:.9rem;font-weight:700;cursor:pointer;transition:.2s}
.analyze-btn:hover{opacity:.85}

/* SCROLLBAR */
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:var(--s1)}
::-webkit-scrollbar-thumb{background:var(--brd2);border-radius:3px}

@media(max-width:580px){
  .res-grid{grid-template-columns:1fr 1fr}
  .hero-stats{gap:20px}
  nav{padding:0 14px}
}
</style>
</head>
<body><nav>
  <div class="logo">✦ SpeakUP  </div>
  <button class="lng on" id="l-en" onclick="setLang('en')">EN</button>
  <button class="lng" id="l-ru" onclick="setLang('ru')">RU</button>
  <button class="lng" id="l-uz" onclick="setLang('uz')">UZ</button>
</nav>

<div class="tabbar" id="tabbar"></div>

<div class="wrap">
  <!-- HERO (only on topics page) -->
  <div class="hero" id="hero-block">
    <h1 id="hero-title">Master English with AI</h1>
    <p id="hero-sub">Interactive lessons · 30-question tests · AI-powered feedback</p>
    <div class="hero-stats">
      <div class="hstat"><div class="hstat-n">12</div><div class="hstat-l" id="s-topics">Topics</div></div>
      <div class="hstat"><div class="hstat-n">30</div><div class="hstat-l" id="s-qper">Q / Test</div></div>
      <div class="hstat"><div class="hstat-n">AI</div><div class="hstat-l" id="s-check">AI Check</div></div>
      <div class="hstat"><div class="hstat-n">3</div><div class="hstat-l" id="s-langs">Languages</div></div>
    </div>
  </div>

  <!-- ===== TOPICS PAGE ===== -->
  <div class="page on" id="p-topics">
    <div class="sh"><h2 id="ph-topics">Choose a Topic</h2><p id="ph-topics-sub">Each topic has a lesson + 30-question test with AI analysis</p></div>
    <div id="topics-list" class="tgrid"></div>
    <!-- TOPIC DETAIL -->
    <div id="detail-view">
      <button class="back" onclick="backToTopics()" id="back-btn">← Back</button>
      <div class="card" id="lesson-card"></div>
      <button class="btn-start" onclick="startTest()" id="btn-take-test" style="margin-bottom:24px">🧪 Take 30-Question Test</button>
      <!-- TEST -->
      <div id="test-view">
        <div class="test-top">
          <div class="test-top-l"><h3 id="test-hd"></h3><span id="test-sub">30 Questions · AI Checked</span></div>
          <div class="test-prog">
            <span class="qnum" id="qnum">1 / 30</span>
            <div class="prog-track"><div class="prog-fill" id="qfill" style="width:3%"></div></div>
          </div>
        </div>
        <div id="qarea"></div>
        <div class="test-btns">
          <button class="btn btn-o" id="pbtn" onclick="prevQ()">← Prev</button>
          <button class="btn btn-p" id="nbtn" onclick="nextQ()">Next →</button>
        </div>
        <div id="result-area" style="margin-top:24px;display:none"></div>
      </div>
    </div>
  </div>



  <!-- ===== READING ===== -->
  <div class="page" id="p-reading">
    <div class="sh"><h2 id="ph-read">Reading Comprehension</h2><p id="ph-read-sub">Read articles and answer comprehension questions</p></div>
    <div id="read-content"></div>
  </div>

  <!-- ===== WRITING ===== -->
  <div class="page" id="p-writing">
    <div class="sh"><h2 id="ph-write">Writing Practice</h2><p id="ph-write-sub">Write essays and get instant AI feedback</p></div>
    <div id="write-content"></div>
  </div>

  <!-- ===== SPEAKING ===== -->
  <div class="page" id="p-speaking">
    <div class="sh"><h2 id="ph-speak">Speaking Practice</h2><p id="ph-speak-sub">Practice pronunciation and conversational fluency</p></div>
    <div id="speak-content"></div>
  </div>

  <!-- ===== VOCABULARY ===== -->
  <div class="page" id="p-vocabulary">
    <div class="sh"><h2 id="ph-vocab">Vocabulary Builder</h2><p id="ph-vocab-sub">Learn themed word sets with translations</p></div>
    <div id="vocab-content"></div>
  </div>

  <!-- ===== GRAMMAR ===== -->
  <div class="page" id="p-grammar">
    <div class="sh"><h2 id="ph-gram">Grammar Reference</h2><p id="ph-gram-sub">Clear rules, formulas and examples</p></div>
    <div id="gram-content"></div>
  </div>
  <!-- ===== AI TUTOR ===== -->
  <div class="page" id="p-aitutor">
    <div class="sh"><h2 id="ph-ai">AI English Tutor</h2><p id="ph-ai-sub">Ask anything about English — grammar, vocabulary, pronunciation</p></div>
    <div class="chat-wrap">
      <div class="chat-head">
        <div class="chat-av">🤖</div>
        <div><div class="chat-info-name">EnglishPro AI</div><div class="chat-info-stat">● Online</div></div>
      </div>
      <div class="chat-msgs" id="chat-msgs">
        <div class="msg ai"><div class="msg-b" id="ai-greet">Hello! I am your AI English tutor. Ask me anything about grammar, vocabulary or pronunciation! 🎓</div><div class="msg-t">now</div></div>
      </div>
      <div class="chat-inp-row">
        <input class="chat-inp" id="chat-inp" id="ph-chat-inp-placeholder" placeholder="Ask about grammar, vocabulary..." onkeydown="if(event.key==='Enter')sendChat()"/>
        <button class="send-btn" onclick="sendChat()">➤</button>
      </div>
    </div>
  </div>

  <!-- ===== PROGRESS ===== -->
  <div class="page" id="p-progress">
    <div class="sh"><h2 id="ph-prog">My Progress</h2><p id="ph-prog-sub">Track your results across all topics</p></div>
    <button class="analyze-btn" onclick="analyzeProgress()" id="analyze-btn">📊 Analyze My Progress</button>
    <div id="prog-grid" class="prog-grid"></div>
    <div class="ai-box" id="prog-ai-box" style="display:none">
      <div class="ai-tag">🤖 AI Analysis</div>
      <div class="ai-txt" id="prog-ai-txt"></div>
    </div>
  </div>
</div>

<script>
// ======================================================
// TRANSLATIONS
// ======================================================
var LANG = 'en';
var TR = {
  en:{
    heroTitle:"Master English with AI",
    heroSub:"Interactive lessons · 30-question tests · AI-powered feedback",
    sTopics:"Topics",sQper:"Q / Test",sCheck:"AI Check",sLangs:"Languages",
    tabTopics:"📚 Topics",tabListen:"🎧 Listening",tabRead:"📖 Reading",
    tabWrite:"✍️ Writing",tabSpeak:"🎙️ Speaking",tabVocab:"📝 Vocabulary",
    tabGram:"⚙️ Grammar",tabAI:"🤖 AI Tutor",tabProg:"📊 Progress",
    phTopics:"Choose a Topic",phTopicsSub:"Each topic has a lesson + 30-question test with AI analysis",
    phListen:"Listening Practice",phListenSub:"Train your ear with authentic audio materials",
    phRead:"Reading Comprehension",phReadSub:"Read articles and answer comprehension questions",
    phWrite:"Writing Practice",phWriteSub:"Write essays and get instant AI feedback",
    phSpeak:"Speaking Practice",phSpeakSub:"Practice pronunciation and conversational fluency",
    phVocab:"Vocabulary Builder",phVocabSub:"Learn themed word sets with translations",
    phGram:"Grammar Reference",phGramSub:"Clear rules, formulas and examples",
    phAI:"AI English Tutor",phAISub:"Ask anything about English — grammar, vocabulary, pronunciation",
    phProg:"My Progress",phProgSub:"Track your results across all topics",
    backBtn:"← Back to Topics",
    takeTest:"🧪 Take 30-Question Test",
    testSub:"30 Questions · AI Checked",
    prev:"← Prev",next:"Next →",finish:"✅ Finish",
    scoreLabel:"Score",correct:"Correct",wrong:"Wrong",skipped:"Skipped",
    retake:"🔁 Retake",
    analyzeBtn:"📊 Analyze My Progress",
    aiTag:"AI Analysis",
    aiGreet:"Hello! I am your AI English tutor. Ask me anything about grammar, vocabulary or pronunciation! 🎓",
    chatPlaceholder:"Ask about grammar, vocabulary...",
    submitWrite:"🤖 AI Review",
    words:"words",
    openEx:"Open Exercise",
    readQs:"Comprehension Questions",
    recordHint:"Press mic to record your response (1-2 min)",
    listenNote:"Listen and answer comprehension questions below",
  },
  ru:{
    heroTitle:"Изучайте английский с ИИ",
    heroSub:"Интерактивные уроки · тесты из 30 вопросов · обратная связь ИИ",sTopics:"Темы",sQper:"Воп. / Тест",sCheck:"ИИ Проверка",sLangs:"Языка",
    tabTopics:"📚 Темы",tabListen:"📖 Чтение",
    tabWrite:"✍️ Письмо",tabSpeak:"🎙️ Речь",tabVocab:"📝 Словарь",
    tabGram:"⚙️ Грамматика",tabAI:"🤖 ИИ Репетитор",tabProg:"📊 Прогресс",
    phTopics:"Выберите тему",phTopicsSub:"Каждая тема содержит урок и тест из 30 вопросов с ИИ-анализом",
    phListen:"Практика аудирования",phListenSub:"Тренируйте слух на аутентичных материалах",
    phRead:"Понимание прочитанного",phReadSub:"Читайте статьи и отвечайте на вопросы по тексту",
    phWrite:"Практика письма",phWriteSub:"Пишите эссе и получайте мгновенную обратную связь от ИИ",
    phSpeak:"Практика речи",phSpeakSub:"Тренируйте произношение и разговорную речь",
    phVocab:"Расширение словаря",phVocabSub:"Учите тематические наборы слов с переводом",
    phGram:"Справочник по грамматике",phGramSub:"Чёткие правила, формулы и примеры",
    phAI:"ИИ-репетитор английского",phAISub:"Задайте любой вопрос об английском — грамматика, лексика, произношение",
    phProg:"Мой прогресс",phProgSub:"Отслеживайте результаты по всем темам",
    backBtn:"← К темам",
    takeTest:"🧪 Пройти тест из 30 вопросов",
    testSub:"30 вопросов · Проверено ИИ",
    prev:"← Назад",next:"Далее →",finish:"✅ Завершить",
    scoreLabel:"Результат",correct:"Правильно",wrong:"Неверно",skipped:"Пропущено",
    retake:"🔁 Заново",
    analyzeBtn:"📊 Анализировать прогресс",
    aiTag:"Анализ ИИ",
    aiGreet:"Привет! Я ваш ИИ-репетитор английского. Задайте любой вопрос о грамматике, лексике или произношении! 🎓",
    chatPlaceholder:"Спросите о грамматике, лексике...",
    submitWrite:"🤖 Проверить ИИ",
    words:"слов",
    openEx:"Открыть упражнение",
    readQs:"Вопросы по тексту",
    recordHint:"Нажмите микрофон и запишите ответ (1-2 мин)",
    listenNote:"Прослушайте и ответьте на вопросы ниже",
  },
  uz:{
    heroTitle:"Sun'iy intellekt bilan ingliz tili",
    heroSub:"Interaktiv darslar · 30 savollik testlar · AI fikr-mulohazasi",
    sTopics:"Mavzular",sQper:"Sav. / Test",sCheck:"AI Tekshir",sLangs:"Til",
    tabTopics:"📚 Mavzular",tabListen:"🎧 Tinglash",tabRead:"📖 O'qish",
    tabWrite:"✍️ Yozish",tabSpeak:"🎙️ Gapirish",tabVocab:"📝 Lug'at",
    tabGram:"⚙️ Grammatika",tabAI:"🤖 AI Ustoz",tabProg:"📊 Taraqqiyot",
    phTopics:"Mavzuni tanlang",phTopicsSub:"Har bir mavzuda dars va 30 savollik test bor",
    phListen:"Tinglash mashqi",phListenSub:"Autentik audio materiallar bilan qulog'ingizni charhlang",
    phRead:"O'qishni tushunish",phReadSub:"Maqolalarni o'qing va savollarga javob bering",
    phWrite:"Yozish mashqi",phWriteSub:"Insho yozing va AI dan tezkor fikr-mulohaza oling",
    phSpeak:"Gapirish mashqi",phSpeakSub:"Talaffuz va suhbat ravonligini mashq qiling",
    phVocab:"Lug'at rivojlantirish",phVocabSub:"Mavzuli so'z to'plamlari va tarjimalari",
    phGram:"Grammatika ma'lumotnomasi",phGramSub:"Aniq qoidalar, formulalar va misollar",
    phAI:"AI ingliz tili ustozi",phAISub:"Ingliz tili haqida istalgan narsani so'rang",
    phProg:"Mening taraqqiyotim",phProgSub:"Barcha mavzular bo'yicha natijalarni kuzating",
    backBtn:"← Mavzularga qaytish",
    takeTest:"🧪 30 savollik test topshirish",
    testSub:"30 savol · AI tekshirdi",
    prev:"← Oldingi",next:"Keyingi →",finish:"✅ Tugatish",
    scoreLabel:"Natija",correct:"To'g'ri",wrong:"Noto'g'ri",skipped:"O'tkazilgan",
    retake:"🔁 Qayta topshirish",
    analyzeBtn:"📊 Taraqqiyotni tahlil qilish",
    aiTag:"AI tahlili",
    aiGreet:"Salom! Men sizning AI ingliz tili ustozingizman. Grammatika, lug'at yoki talaffuz haqida savol bering! 🎓",
    chatPlaceholder:"Grammatika, lug'at haqida so'rang...",
    submitWrite:"🤖 AI tekshiruvi",
    words:"so'z",
    openEx:"Mashqni ochish",
    readQs:"Matn bo'yicha savollar",
    recordHint:"Mikrofonni bosing va javobingizni yozib oling (1-2 daqiqa)",
    listenNote:"Tinglang va quyidagi savollarga javob bering",
  }
};

function tr(k){ return (TR[LANG] && TR[LANG][k]) ? TR[LANG][k] : (TR['en'][k] || k); }function setLang(l){
  LANG = l;
  ['en','ru','uz'].forEach(function(x){ document.getElementById('l-'+x).classList.toggle('on', x===l); });
  applyAll();
}

function applyAll(){
  // static IDs
  var map = {
    'hero-title':'heroTitle','hero-sub':'heroSub',
    's-topics':'sTopics','s-qper':'sQper','s-check':'sCheck','s-langs':'sLangs',
    'ph-topics':'phTopics','ph-topics-sub':'phTopicsSub',
    'ph-listen':'phListen','ph-listen-sub':'phListenSub',
    'ph-read':'phRead','ph-read-sub':'phReadSub',
    'ph-write':'phWrite','ph-write-sub':'phWriteSub',
    'ph-speak':'phSpeak','ph-speak-sub':'phSpeakSub',
    'ph-vocab':'phVocab','ph-vocab-sub':'phVocabSub',
    'ph-gram':'phGram','ph-gram-sub':'phGramSub',
    'ph-ai':'phAI','ph-ai-sub':'phAISub',
    'ph-prog':'phProg','ph-prog-sub':'phProgSub',
    'back-btn':'backBtn','btn-take-test':'takeTest',
    'test-sub':'testSub','pbtn':'prev','analyze-btn':'analyzeBtn',
    'ai-greet':'aiGreet'
  };
  Object.keys(map).forEach(function(id){
    var el = document.getElementById(id);
    if(el) el.textContent = tr(map[id]);
  });
  var ci = document.getElementById('chat-inp');
  if(ci) ci.placeholder = tr('chatPlaceholder');
  // rebuild tabs
  buildTabs();
  // rebuild dynamic content in current page
  var active = document.querySelector('.page.on');
  if(active) renderPage(active.id.replace('p-',''));
  // rebuild topics
  renderTopics();
}

// ======================================================
// TABS
// ======================================================
var TABS = [
  {id:'topics',    key:'tabTopics'},
  {id:'reading',   key:'tabRead'},
  {id:'writing',   key:'tabWrite'},
  {id:'speaking',  key:'tabSpeak'},
  {id:'vocabulary',key:'tabVocab'},
  {id:'grammar',   key:'tabGram'},
  {id:'aitutor',   key:'tabAI'},
  {id:'progress',  key:'tabProg'},
];

function buildTabs(){
  var bar = document.getElementById('tabbar');
  bar.innerHTML = TABS.map(function(t){
    var act = document.getElementById('p-'+t.id) && document.getElementById('p-'+t.id).classList.contains('on') ? ' on' : '';
    return '<button class="tbtn'+act+'" onclick="showPage(\''+t.id+'\')">'+tr(t.key)+'</button>';
  }).join('');
}

var currentPage = 'topics';
function showPage(id){
  currentPage = id;
  document.querySelectorAll('.page').forEach(function(p){ p.classList.remove('on'); });
  var pg = document.getElementById('p-'+id);
  if(pg) pg.classList.add('on');
  document.getElementById('hero-block').style.display = (id==='topics') ? '' : 'none';
  buildTabs();
  renderPage(id);
}

function renderPage(id){
  if(id==='listening') renderListening();
  else if(id==='reading') renderReading();
  else if(id==='writing') renderWriting();
  else if(id==='speaking') renderSpeaking();
  else if(id==='vocabulary') renderVocab();
  else if(id==='grammar') renderGrammar();
  else if(id==='progress') renderProgress();
}

// ======================================================
// TOPICS DATA
// ======================================================
var TOPICS = [
  { id:'present', ico:'⏱️', color:'#4f8ef7', level:'A1-A2',
    name:{en:'Present Tenses',ru:'Настоящее время',uz:"Hozirgi zamon"},
    desc:{en:'Simple, Continuous & Perfect present forms',ru:'Простое, длительное и перфектное настоящее',uz:"Oddiy, davom etuvchi va mukammal hozirgi zamon"},
    lesson:{
      en:'<h3>1. Present Simple</h3><p>Used for habits, facts, routines.</p><div class="ex-box">She <strong>works</strong> every day. / Water <strong>boils</strong> at 100°C.</div><h3>2. Present Continuous</h3><p>Actions happening right now or temporary situations.</p><div class="ex-box">He <strong>is reading</strong> a book right now.</div><h3>3. Present Perfect</h3><p>Past actions with present relevance.</p><div class="ex-box">I <strong>have lived</strong> here for five years.</div>',ru:'<h3>1. Present Simple</h3><p>Привычки, факты, расписание.</p><div class="ex-box">She <strong>works</strong> every day.</div><h3>2. Present Continuous</h3><p>Действия прямо сейчас.</p><div class="ex-box">He <strong>is reading</strong> right now.</div><h3>3. Present Perfect</h3><p>Прошлые действия, связанные с настоящим.</p><div class="ex-box">I <strong>have lived</strong> here for five years.</div>',
      uz:'<h3>1. Present Simple</h3><p>Odatlar, faktlar, jadval.</p><div class="ex-box">She <strong>works</strong> every day.</div><h3>2. Present Continuous</h3><p>Hozir sodir bo\'layotgan harakatlar.</p><div class="ex-box">He <strong>is reading</strong> right now.</div><h3>3. Present Perfect</h3><p>Hozirgi paytga aloqasi bor o\'tgan harakatlar.</p><div class="ex-box">I <strong>have lived</strong> here for five years.</div>'
    },
    qs: makeQs([
      {q:"She ___ to school every day.",o:["go","goes","is going","went"],a:1},
      {q:"They ___ TV right now.",o:["watch","watches","are watching","watched"],a:2},
      {q:"I ___ never been to Japan.",o:["have","has","had","am"],a:0},
      {q:"He ___ a doctor.",o:["is","are","am","be"],a:0},
      {q:"We ___ dinner at 7 PM every night.",o:["have","has","are having","had"],a:0},
      {q:"Look! It ___!",o:["rains","rain","is raining","rained"],a:2},
      {q:"She ___ already finished her homework.",o:["have","has","had","is"],a:1},
      {q:"The sun ___ in the west.",o:["set","sets","is setting","has set"],a:1},
      {q:"We ___ for the bus for 20 minutes.",o:["wait","waits","have been waiting","waited"],a:2},
      {q:"He ___ three languages.",o:["speak","speaks","is speaking","spoke"],a:1},
    ])
  },
  { id:'past', ico:'⌛', color:'#a78bfa', level:'A2-B1',
    name:{en:'Past Tenses',ru:'Прошедшее время',uz:"O'tgan zamon"},
    desc:{en:'Simple, Continuous & Perfect past forms',ru:'Простое, длительное и перфектное прошедшее',uz:"O'tgan zamoning barcha shakllari"},
    lesson:{
      en:'<h3>1. Past Simple</h3><p>Completed actions at a specific time.</p><div class="ex-box">She <strong>visited</strong> London last year.</div><h3>2. Past Continuous</h3><p>Action in progress when another happened.</p><div class="ex-box">I <strong>was sleeping</strong> when the phone rang.</div><h3>3. Past Perfect</h3><p>Action completed before another past action.</p><div class="ex-box">By noon, he <strong>had already left</strong>.</div>',
      ru:'<h3>1. Past Simple</h3><p>Завершённые действия в прошлом.</p><div class="ex-box">She <strong>visited</strong> London last year.</div><h3>2. Past Continuous</h3><p>Действие в процессе, прерванное другим.</p><div class="ex-box">I <strong>was sleeping</strong> when the phone rang.</div><h3>3. Past Perfect</h3><p>Действие, завершённое до другого прошлого действия.</p><div class="ex-box">He <strong>had already left</strong>.</div>',
      uz:'<h3>1. Past Simple</h3><p>O\'tganда yakunlangan harakatlar.</p><div class="ex-box">She <strong>visited</strong> London last year.</div><h3>2. Past Continuous</h3><p>Boshqa harakat bilan uzilgan davom etayotgan harakat.</p><div class="ex-box">I <strong>was sleeping</strong> when the phone rang.</div><h3>3. Past Perfect</h3><p>Boshqa o\'tgan harakatdan oldin tugagan harakat.</p><div class="ex-box">He <strong>had already left</strong>.</div>'
    },
    qs: makeQs([
      {q:"She ___ to Paris last year.",o:["go","goes","went","has gone"],a:2},
      {q:"When I arrived, he ___ already left.",o:["has","have","had","was"],a:2},
      {q:"They ___ TV when I called.",o:["watched","watch","were watching","had watched"],a:2},
      {q:"He ___ his keys yesterday.",o:["loses","lost","has lost","had lost"],a:1},
      {q:"We ___ dinner when the power went out.",o:["had","have","were having","would have"],a:2},
      {q:"I ___ him three times this week.",o:["see","saw","have seen","had seen"],a:2},{q:"She said she ___ tired.",o:["is","was","has been","were"],a:1},
      {q:"They ___ the project by noon.",o:["finish","finished","had finished","were finishing"],a:2},
      {q:"How long ___ you known him?",o:["have","had","did","were"],a:0},
      {q:"She ___ medicine for 10 years before retiring.",o:["study","studied","had studied","was studying"],a:2},
    ])
  },
  { id:'future', ico:'🚀', color:'#22d3ee', level:'A2-B1',
    name:{en:'Future Tenses',ru:'Будущее время',uz:"Kelasi zamon"},
    desc:{en:'Will, Going to, Future Continuous & Perfect',ru:'Will, Going to, Future Continuous и Perfect',uz:"Will, Going to va boshqa kelasi zamon shakllari"},
    lesson:{
      en:'<h3>Will</h3><p>Spontaneous decisions and predictions.</p><div class="ex-box">I think it <strong>will rain</strong> tomorrow.</div><h3>Going to</h3><p>Planned intentions and evidence-based predictions.</p><div class="ex-box">She <strong>is going to study</strong> medicine.</div><h3>Future Continuous</h3><p>Action in progress at a future moment.</p><div class="ex-box">This time tomorrow I <strong>will be flying</strong>.</div>',
      ru:'<h3>Will</h3><p>Спонтанные решения и предсказания.</p><div class="ex-box">I think it <strong>will rain</strong> tomorrow.</div><h3>Going to</h3><p>Запланированные намерения.</p><div class="ex-box">She <strong>is going to study</strong> medicine.</div><h3>Future Continuous</h3><p>Действие в процессе в будущий момент.</p><div class="ex-box">This time tomorrow I <strong>will be flying</strong>.</div>',
      uz:'<h3>Will</h3><p>Spontan qarorlar va bashoratlar.</p><div class="ex-box">I think it <strong>will rain</strong> tomorrow.</div><h3>Going to</h3><p>Rejalashtirilgan niyatlar.</p><div class="ex-box">She <strong>is going to study</strong> medicine.</div>'
    },
    qs: makeQs([
      {q:"I think it ___ rain tomorrow.",o:["will","would","is going to","shall"],a:0},
      {q:"She ___ to be a doctor — she has already applied.",o:["will","is going","goes","shall"],a:1},
      {q:"By 2030, scientists ___ a cure.",o:["find","will find","would find","will have found"],a:3},
      {q:"Look at those clouds! It ___ rain!",o:["will","would","is going to","might"],a:2},
      {q:"This time tomorrow, I ___ on the beach.",o:["will sit","will be sitting","sit","am sitting"],a:1},
      {q:"Don't worry, I ___ help you.",o:["will","am going to","would","shall"],a:0},
      {q:"She ___ married next month.",o:["gets","will get","is getting","would get"],a:2},
      {q:"If you study, you ___ pass.",o:["will","would","shall","can"],a:0},
      {q:"He ___ to leave at dawn.",o:["plans","is planning","will plan","would plan"],a:1},
      {q:"We ___ for three hours by the time we arrive.",o:["will drive","will have been driving","drive","drove"],a:1},
    ])
  },
  { id:'conditionals', ico:'🔀', color:'#fbbf24', level:'B1-B2',
    name:{en:'Conditionals',ru:'Условные предложения',uz:"Shartli gaplar"},
    desc:{en:'Zero, First, Second & Third conditionals',ru:'Нулевое, первое, второе и третье условные',uz:"Nol, birinchi, ikkinchi va uchinchi shartli gaplar"},
    lesson:{
      en:'<h3>Zero Conditional</h3><p>Universal truths.</p><div class="formula">If + Present Simple, Present Simple</div><div class="ex-box">If you heat water to 100°C, it <strong>boils</strong>.</div><h3>First Conditional</h3><p>Real future possibility.</p><div class="formula">If + Present Simple, will + V</div><div class="ex-box">If it rains, I <strong>will stay</strong> home.</div><h3>Second Conditional</h3><p>Hypothetical present/future.</p><div class="formula">If + Past Simple, would + V</div><div class="ex-box">If I <strong>won</strong> the lottery, I <strong>would travel</strong>.</div><h3>Third Conditional</h3><p>Hypothetical past.</p><div class="formula">If + Past Perfect, would have + V3</div><div class="ex-box">If she <strong>had studied</strong>, she <strong>would have passed</strong>.</div>',ru:'<h3>Zero Conditional</h3><p>Универсальные истины.</p><div class="formula">If + Present Simple, Present Simple</div><div class="ex-box">If you heat water, it <strong>boils</strong>.</div><h3>First Conditional</h3><p>Реальная возможность в будущем.</p><div class="formula">If + Present Simple, will + V</div><div class="ex-box">If it rains, I <strong>will stay</strong> home.</div><h3>Second Conditional</h3><p>Гипотетическое настоящее/будущее.</p><div class="ex-box">If I <strong>won</strong>, I <strong>would travel</strong>.</div><h3>Third Conditional</h3><p>Гипотетическое прошлое.</p><div class="ex-box">If she <strong>had studied</strong>, she <strong>would have passed</strong>.</div>',
      uz:'<h3>Zero Conditional</h3><p>Universal haqiqatlar.</p><div class="ex-box">If you heat water, it <strong>boils</strong>.</div><h3>First Conditional</h3><p>Haqiqiy kelajak imkoniyati.</p><div class="ex-box">If it rains, I <strong>will stay</strong> home.</div><h3>Second Conditional</h3><p>Gipotетик hozir/kelajak.</p><div class="ex-box">If I <strong>won</strong>, I <strong>would travel</strong>.</div>'
    },
    qs: makeQs([
      {q:"If it rains, I ___ stay home.",o:["will","would","had","should"],a:0},
      {q:"If I ___ rich, I would travel.",o:["am","was","were","be"],a:2},
      {q:"If she ___ studied, she would have passed.",o:["has","had","would","did"],a:1},
      {q:"Water boils if you ___ it to 100°C.",o:["heat","heated","would heat","had heated"],a:0},
      {q:"If I were you, I ___ apologise.",o:["will","would","should","am"],a:1},
      {q:"She ___ be happier if she exercised.",o:["will","would","shall","can"],a:1},
      {q:"If they had left earlier, they ___ missed the train.",o:["wouldn't have","won't have","didn't","hadn't"],a:0},
      {q:"If you press this button, the alarm ___.",o:["rings","will ring","would ring","rang"],a:1},
      {q:"I ___ gone if I had known.",o:["would have","will have","had","should have"],a:0},
      {q:"If I ___ a bird, I would fly.",o:["am","was","were","be"],a:2},
    ])
  },
  { id:'passive', ico:'🔄', color:'#34d399', level:'B1-B2',
    name:{en:'Passive Voice',ru:'Страдательный залог',uz:"Passiv nisbat"},
    desc:{en:'How to form and use passive structures',ru:'Образование и использование пассивного залога',uz:"Passiv nisbatni qurish va ishlatish"},
    lesson:{
      en:'<h3>Formation</h3><div class="formula">Subject + be (conjugated) + Past Participle (V3)</div><div class="ex-box">Active: They <strong>built</strong> the bridge in 1990.<br>Passive: The bridge <strong>was built</strong> in 1990.</div><h3>When to use</h3><p>Use passive when the action is more important than who does it, or when the doer is unknown.</p><div class="ex-box">English <strong>is spoken</strong> all over the world. / The thief <strong>was caught</strong> last night.</div>',
      ru:'<h3>Образование</h3><div class="formula">Подлежащее + be (спряж.) + Причастие II (V3)</div><div class="ex-box">Active: They built the bridge.<br>Passive: The bridge <strong>was built</strong>.</div><h3>Когда использовать</h3><p>Когда действие важнее исполнителя или исполнитель неизвестен.</p><div class="ex-box">English <strong>is spoken</strong> worldwide.</div>',
      uz:'<h3>Tuzilishi</h3><div class="formula">Ega + be (tuslanish) + O\'tgan zamon sifatdoshi (V3)</div><div class="ex-box">Active: They built the bridge.<br>Passive: The bridge <strong>was built</strong>.</div>'
    },
    qs: makeQs([
      {q:"The letter ___ by Mary.",o:["wrote","was written","is writing","writes"],a:1},
      {q:"English ___ all over the world.",o:["speak","is spoken","was speaking","speaks"],a:1},
      {q:"The cake ___ by the time I arrived.",o:["ate","was eaten","had been eaten","is eaten"],a:2},
      {q:"The new law ___ next year.",o:["will pass","will be passed","is passing","passes"],a:1},  {q:"The report ___ right now.",o:["is being written","writes","was written","had written"],a:0},
      {q:"The bridge ___ in 1850.",o:["built","builds","was built","has built"],a:2},
      {q:"She ___ told the news yesterday.",o:["was","is","has","had"],a:0},
      {q:"Dinner ___ at 7 every evening.",o:["will serve","is served","serves","served"],a:1},
      {q:"The problems ___ being solved.",o:["is","are","was","were"],a:1},
      {q:"The children ___ looked after carefully.",o:["are","is","were","was"],a:0},
    ])
  },
  { id:'modals', ico:'💬', color:'#f472b6', level:'A2-B1',
    name:{en:'Modal Verbs',ru:'Модальные глаголы',uz:"Modal fe'llar"},
    desc:{en:'Can, Could, May, Might, Should, Must…',ru:'Can, Could, May, Might, Should, Must и другие',uz:"Can, Could, May, Might, Should, Must va boshqalar"},
    lesson:{
      en:'<h3>Ability</h3><div class="ex-box">I <strong>can</strong> swim. / She <strong>could</strong> speak French.</div><h3>Obligation</h3><div class="ex-box">You <strong>must</strong> wear a seatbelt. / You <strong>have to</strong> register.</div><h3>Advice</h3><div class="ex-box">You <strong>should</strong> see a doctor.</div><h3>Possibility</h3><div class="ex-box">It <strong>might</strong> rain. / He <strong>may</strong> be late.</div><h3>Permission</h3><div class="ex-box"><strong>Can</strong> I borrow your pen? / <strong>May</strong> I come in?</div>',
      ru:'<h3>Способность</h3><div class="ex-box">I <strong>can</strong> swim.</div><h3>Обязательство</h3><div class="ex-box">You <strong>must</strong> wear a seatbelt.</div><h3>Совет</h3><div class="ex-box">You <strong>should</strong> see a doctor.</div><h3>Возможность</h3><div class="ex-box">It <strong>might</strong> rain.</div>',
      uz:'<h3>Qobiliyat</h3><div class="ex-box">I <strong>can</strong> swim.</div><h3>Majburiyat</h3><div class="ex-box">You <strong>must</strong> wear a seatbelt.</div><h3>Maslahat</h3><div class="ex-box">You <strong>should</strong> see a doctor.</div>'
    },
    qs: makeQs([
      {q:"You ___ smoke here — it's forbidden.",o:["mustn't","don't have to","shouldn't","couldn't"],a:0},
      {q:"She ___ speak three languages.",o:["can","must","shall","ought"],a:0},
      {q:"It ___ rain — the sky is very dark.",o:["might","should","can","will"],a:0},
      {q:"You ___ see a doctor soon.",o:["should","shall","can","must"],a:0},
      {q:"I ___ find my keys anywhere!",o:["can't","mustn't","shouldn't","won't"],a:0},
      {q:"___ I borrow your pen?",o:["Could","Should","Must","Shall"],a:0},
      {q:"You don't ___ come if you're busy.",o:["have to","must","should","need"],a:0},
      {q:"She ___ be at home — the lights are on.",o:["must","could","might","should"],a:0},
      {q:"We ___ leave now or we'll be late.",o:["must","can","might","could"],a:0},
      {q:"Children ___ play near the road.",o:["shouldn't","mustn't","can't","don't"],a:1},
    ])
  },
  { id:'articles', ico:'📌', color:'#fb923c', level:'A1-A2',
    name:{en:'Articles (A/An/The)',ru:'Артикли (A/An/The)',uz:"Artikllar (A/An/The)"},
    desc:{en:'Definite and indefinite articles in context',ru:'Определённый и неопределённый артикли',uz:"Aniq va noaniq artikllarni ishlatish"},
    lesson:{
      en:'<h3>A / An — Indefinite</h3><p>Used with singular countable nouns, first mention, or when the listener doesn\'t know which one.</p><div class="ex-box">I saw <strong>a</strong> dog. / She is <strong>an</strong> engineer.</div><h3>The — Definite</h3><p>Used when both speaker and listener know which one is meant, or when there is only one.</p><div class="ex-box"><strong>The</strong> dog I told you about is black. / <strong>The</strong> sun rises in the east.</div><h3>No article (Ø)</h3><p>Plural/uncountable nouns in general statements; names of countries (most), languages, meals.</p><div class="ex-box">I love <strong>Ø</strong> music. / She speaks <strong>Ø</strong> English.</div>',ru:'<h3>A / An — Неопределённый</h3><p>С исчисляемыми существительными в единственном числе при первом упоминании.</p><div class="ex-box">I saw <strong>a</strong> dog. / She is <strong>an</strong> engineer.</div><h3>The — Определённый</h3><p>Когда оба собеседника знают, о чём идёт речь.</p><div class="ex-box"><strong>The</strong> dog is black. / <strong>The</strong> sun rises in the east.</div><h3>Без артикля (Ø)</h3><div class="ex-box">I love <strong>Ø</strong> music.</div>',
      uz:'<h3>A / An — Noaniq</h3><div class="ex-box">I saw <strong>a</strong> dog. / She is <strong>an</strong> engineer.</div><h3>The — Aniq</h3><div class="ex-box"><strong>The</strong> dog is black.</div><h3>Artikl yo\'q (Ø)</h3><div class="ex-box">I love <strong>Ø</strong> music.</div>'
    },
    qs: makeQs([
      {q:"I saw ___ dog in the park.",o:["a","an","the","—"],a:0},
      {q:"She is ___ honest person.",o:["a","an","the","—"],a:1},
      {q:"___ Earth orbits the sun.",o:["A","An","The","—"],a:2},
      {q:"He plays ___ guitar beautifully.",o:["a","an","the","—"],a:2},
      {q:"I go to ___ school by bus.",o:["a","an","the","—"],a:3},
      {q:"She bought ___ umbrella.",o:["a","an","the","—"],a:1},
      {q:"___ Nile is the longest river in Africa.",o:["A","An","The","—"],a:2},
      {q:"He is ___ best student in class.",o:["a","an","the","—"],a:2},
      {q:"I had ___ apple for lunch.",o:["a","an","the","—"],a:1},
      {q:"They visited ___ France last summer.",o:["a","an","the","—"],a:3},
    ])
  },
  { id:'prepositions', ico:'📍', color:'#2dd4bf', level:'A2-B1',
    name:{en:'Prepositions',ru:'Предлоги',uz:"Predloglar"},
    desc:{en:'In, on, at, by, for, since and more',ru:'In, on, at, by, for, since и другие',uz:"In, on, at, by, for, since va boshqalar"},
    lesson:{
      en:'<h3>Place</h3><div class="ex-box"><strong>in</strong> the room · <strong>on</strong> the table · <strong>at</strong> the door</div><h3>Time</h3><div class="ex-box"><strong>in</strong> the morning · <strong>on</strong> Monday · <strong>at</strong> 9 PM</div><h3>Duration</h3><div class="ex-box"><strong>for</strong> three hours · <strong>since</strong> 2020 · <strong>by</strong> Friday</div><h3>Movement</h3><div class="ex-box"><strong>to</strong> school · <strong>from</strong> home · <strong>into</strong> the room</div>',
      ru:'<h3>Место</h3><div class="ex-box"><strong>in</strong> the room · <strong>on</strong> the table · <strong>at</strong> the door</div><h3>Время</h3><div class="ex-box"><strong>in</strong> the morning · <strong>on</strong> Monday · <strong>at</strong> 9 PM</div><h3>Длительность</h3><div class="ex-box"><strong>for</strong> three hours · <strong>since</strong> 2020</div>',
      uz:'<h3>Joy</h3><div class="ex-box"><strong>in</strong> the room · <strong>on</strong> the table · <strong>at</strong> the door</div><h3>Vaqt</h3><div class="ex-box"><strong>in</strong> the morning · <strong>on</strong> Monday · <strong>at</strong> 9 PM</div>'
    },
    qs: makeQs([
      {q:"She lives ___ London.",o:["in","on","at","by"],a:0},
      {q:"The meeting is ___ Monday.",o:["in","on","at","by"],a:1},
      {q:"The train leaves ___ 9 AM.",o:["in","on","at","by"],a:2},
      {q:"She finished the report ___ Friday.",o:["in","on","at","by"],a:3},
      {q:"He has been working here ___ 2018.",o:["since","for","from","by"],a:0},
      {q:"I've lived here ___ five years.",o:["since","for","from","by"],a:1},
      {q:"She sat ___ the chair.",o:["on","in","at","by"],a:0},
      {q:"He is good ___ mathematics.",o:["at","in","on","for"],a:0},
      {q:"The cat is ___ the table.",o:["under","below","beneath","all of these"],a:0},
      {q:"She's interested ___ art.",o:["in","on","at","by"],a:0},
    ])
  },
  { id:'reported', ico:'🗣️', color:'#818cf8', level:'B1-B2',name:{en:'Reported Speech',ru:'Косвенная речь',uz:"Bilvosita nutq"},
    desc:{en:'How to report what someone said',ru:'Передача чужих слов без прямого цитирования',uz:"Boshqa kishining so'zlarini yetkazish"},
    lesson:{
      en:'<h3>Tense Backshift</h3><p>When reporting speech, tenses usually shift back.</p><div class="formula">am/is → was · will → would · can → could · have → had</div><div class="ex-box">Direct: "I <strong>am</strong> happy."<br>Reported: She said she <strong>was</strong> happy.</div><h3>Reporting Questions</h3><div class="ex-box">Direct: "Where do you live?"<br>Reported: He asked where I <strong>lived</strong>.</div>',
      ru:'<h3>Сдвиг времён</h3><p>При косвенной речи времена сдвигаются назад.</p><div class="formula">am/is → was · will → would · can → could · have → had</div><div class="ex-box">Direct: "I am happy." → She said she <strong>was</strong> happy.</div>',
      uz:'<h3>Zamon o\'zgarishi</h3><p>Bilvosita nutqda zamonlar orqaga siljiydi.</p><div class="formula">am/is → was · will → would · can → could · have → had</div><div class="ex-box">"I am happy." → She said she <strong>was</strong> happy.</div>'
    },
    qs: makeQs([
      {q:"He said he ___ tired.",o:["is","was","has been","were"],a:1},
      {q:"She told me she ___ go.",o:["will","would","can","could"],a:1},
      {q:"They said they ___ the film.",o:["see","saw","had seen","have seen"],a:2},
      {q:"He asked if I ___ help.",o:["can","could","would","will"],a:1},
      {q:"She ___ she was leaving.",o:["told","said","asked","spoke"],a:1},
      {q:"He ___ me to wait outside.",o:["said","told","asked","spoke"],a:2},
      {q:'"I live here" → She said she ___ there.',o:["lives","lived","has lived","was living"],a:1},
      {q:'"It will rain" → He said it ___ rain.',o:["will","would","should","could"],a:1},
      {q:"She asked where I ___.",o:["live","lived","had lived","would live"],a:1},
      {q:'"I have done it" → He said he ___ it.',o:["has done","had done","did","does"],a:1},
    ])
  },
  { id:'questions', ico:'❓', color:'#86efac', level:'A1-A2',
    name:{en:'Questions & Negatives',ru:'Вопросы и отрицания',uz:"Savollar va inkor"},
    desc:{en:'Yes/No, Wh-questions and negative forms',ru:'Вопросы да/нет, Wh-вопросы и отрицания',uz:"Ha/yo'q savollari, Wh-savollari va inkor"},
    lesson:{
      en:'<h3>Yes/No Questions</h3><div class="formula">Do/Does/Did/Is/Are/Was/Were + Subject + V?</div><div class="ex-box">Do you like coffee? / Is she a teacher?</div><h3>Wh-Questions</h3><div class="formula">Wh-word + aux + Subject + V?</div><div class="ex-box">What do you do? / Where does he live?</div><h3>Negatives</h3><div class="formula">Subject + do not / does not / did not + V</div><div class="ex-box">She doesn\'t know. / They didn\'t come.</div>',
      ru:'<h3>Вопросы Да/Нет</h3><div class="ex-box">Do you like coffee? / Is she a teacher?</div><h3>Вопросы Wh-</h3><div class="ex-box">What do you do? / Where does he live?</div><h3>Отрицание</h3><div class="ex-box">She doesn\'t know. / They didn\'t come.</div>',
      uz:'<h3>Ha/Yo\'q savollari</h3><div class="ex-box">Do you like coffee? / Is she a teacher?</div><h3>Wh-savollari</h3><div class="ex-box">What do you do? / Where does he live?</div>'
    },
    qs: makeQs([
      {q:"___ she speak English?",o:["Do","Does","Is","Has"],a:1},
      {q:"___ they playing football?",o:["Do","Does","Are","Have"],a:2},
      {q:"___ have you been?",o:["What","Where","Who","Which"],a:1},
      {q:"___ does she live?",o:["What","Where","How","Why"],a:1},
      {q:"She doesn't ___ coffee.",o:["like","likes","liked","liking"],a:0},
      {q:"They ___ go to the party.",o:["doesn't","don't","aren't","isn't"],a:1},
      {q:"___ old are you?",o:["What","How","Which","Who"],a:1},
      {q:"He ___ a student, he's a teacher.",o:["isn't","doesn't","aren't","don't"],a:0},{q:"___ did you meet her?",o:["What","Where","When","Which"],a:2},
      {q:"You ___ like vegetables, do you?",o:["not","don't","doesn't","aren't"],a:1},
    ])
  },
  { id:'phrasal', ico:'⚡', color:'#f87171', level:'B2-C1',
    name:{en:'Phrasal Verbs',ru:'Фразовые глаголы',uz:"Fraza fe'llari"},
    desc:{en:'Common phrasal verbs in everyday English',ru:'Распространённые фразовые глаголы',uz:"Kundalik hayotdagi fraza fe'llari"},
    lesson:{
      en:'<p>A phrasal verb = verb + particle (preposition/adverb). The meaning is often idiomatic.</p><h3>Common Examples</h3><div class="ex-box"><strong>give up</strong> — to stop trying<br><strong>look after</strong> — to take care of<br><strong>put off</strong> — to postpone<br><strong>turn down</strong> — to refuse<br><strong>bring up</strong> — raise children / mention a topic<br><strong>take off</strong> — leave the ground / remove clothing<br><strong>run out of</strong> — have no more of something<br><strong>get along with</strong> — have a good relationship</div>',
      ru:'<p>Фразовый глагол = глагол + частица. Значение часто идиоматическое.</p><h3>Примеры</h3><div class="ex-box"><strong>give up</strong> — бросить<br><strong>look after</strong> — заботиться<br><strong>put off</strong> — откладывать<br><strong>turn down</strong> — отказаться<br><strong>bring up</strong> — воспитывать / упоминать</div>',
      uz:'<p>Fraza fe\'li = fe\'l + zarracha. Ma\'nosi ko\'pincha idiomatik bo\'ladi.</p><h3>Misollar</h3><div class="ex-box"><strong>give up</strong> — voz kechmoq<br><strong>look after</strong> — g\'amxo\'rlik qilmoq<br><strong>put off</strong> — kechiktirmoq</div>'
    },
    qs: makeQs([
      {q:"She ___ her dream of becoming a singer.",o:["gave up","gave in","gave away","gave out"],a:0},
      {q:"Can you ___ my dog while I'm away?",o:["look for","look after","look up","look into"],a:1},
      {q:"Don't ___ the meeting.",o:["put off","put on","put up","put out"],a:0},
      {q:"He ___ the job offer.",o:["turned down","turned up","turned off","turned in"],a:0},
      {q:"She ___ her children well.",o:["brought up","brought in","brought about","brought out"],a:0},
      {q:"The plane ___ at 6 AM.",o:["took off","took over","took up","took in"],a:0},
      {q:"I need to ___ this word in the dictionary.",o:["look up","look into","look for","look after"],a:0},
      {q:"We ___ of milk — can you buy some?",o:["ran out","run out","gave out","gave up"],a:0},
      {q:"She ___ early every morning.",o:["gets up","gets on","gets off","gets out"],a:0},
      {q:"He ___ the ladder quickly.",o:["went up","went on","went off","went out"],a:0},
    ])
  },
  { id:'pronunciation', ico:'🔊', color:'#c084fc', level:'A1-C1',
    name:{en:'Pronunciation',ru:'Произношение',uz:"Talaffuz"},
    desc:{en:'Sounds, word stress and connected speech',ru:'Звуки, ударение и связная речь',uz:"Tovushlar, urg'u va bog'liq nutq"},
    lesson:{
      en:'<h3>English has 44 phonemes</h3><p>More sounds than the 26 letters. Vowels and consonants behave differently from spelling.</p><h3>Word Stress</h3><p>Stress can change a word\'s grammatical category.</p><div class="ex-box">PREsent (noun) vs. preSENT (verb)<br>REcord (noun) vs. reCORD (verb)</div><h3>Connected Speech</h3><p>In natural speech, words link together.</p><div class="ex-box">"want to" → /wanna/<br>"going to" → /gonna/<br>"could you" → /kʊdʒə/</div>',
      ru:'<h3>В английском 44 фонемы</h3><p>Гласные и согласные ведут себя иначе, чем при написании.</p><h3>Ударение</h3><div class="ex-box">PREsent (noun) vs. preSENT (verb)</div><h3>Связная речь</h3><div class="ex-box">"want to" → /wanna/ / "going to" → /gonna/</div>',
      uz:'<h3>Ingliz tilida 44 ta fonem</h3><p>Unli va undosh tovushlar imlo bilan farq qiladi.</p><h3>Urg\'u</h3><div class="ex-box">PREsent (ot) vs. preSENT (fe\'l)</div><h3>Bog\'liq nutq</h3><div class="ex-box">"want to" → /wanna/ / "going to" → /gonna/</div>'},
    qs: makeQs([
      {q:"Which word has a different vowel sound? (bat / cat / hate / mat)",o:["bat","cat","hate","mat"],a:2},
      {q:"Where is the stress in 'photograph'?",o:["PHO-to-graph","pho-TO-graph","pho-to-GRAPH","equal stress"],a:0},
      {q:"The 'th' in 'the' sounds like:",o:["/t/","/d/","/ð/ (voiced)","/θ/ (voiceless)"],a:2},
      {q:"The 'th' in 'think' sounds like:",o:["/t/","/d/","/ð/ (voiced)","/θ/ (voiceless)"],a:3},
      {q:"Which letter is silent in 'knife'?",o:["k","n","i","e"],a:0},
      {q:"'Going to' in casual speech becomes:",o:["gonna","gotta","wanna","kinda"],a:0},
      {q:"Changing stress from PREsent to preSENT is called:",o:["Stress shift","Elision","Assimilation","Linking"],a:0},
      {q:"The /ɪ/ sound is found in:",o:["heat","hit","hate","hot"],a:1},
      {q:"'Could you' in fast speech sounds like:",o:["Could you","/kʊdʒə/","/kuːdʒuː/","/kɒdjuː/"],a:1},
      {q:"'Comfortable' is typically pronounced with ___ syllables.",o:["4","3","2","5"],a:1},
    ])
  },
];

// Expand 10 base questions to 30
function makeQs(base){
  var result = [];
  while(result.length < 30){
    for(var i=0;i<base.length && result.length<30;i++){
      result.push({q:base[i].q, o:base[i].o.slice(), a:base[i].a});
    }
  }
  return result;
}

// ======================================================
// STATE
// ======================================================
var progress = {};      // topic id -> percent
var curTopic = null;
var curQ = 0;
var answers = [];

// ======================================================
// RENDER TOPICS
// ======================================================
function renderTopics(){
  var el = document.getElementById('topics-list');
  if(!el) return;
  el.innerHTML = TOPICS.map(function(tp){
    var pct = progress[tp.id] || 0;
    var nm = tp.name[LANG] || tp.name.en;
    var ds = tp.desc[LANG] || tp.desc.en;
    return '<div class="tcard" style="--tc:'+tp.color+'" onclick="openTopic(\''+tp.id+'\')">'
      +'<div class="tcard-ico">'+tp.ico+'</div>'
      +'<div class="tcard-name">'+nm+'</div>'
      +'<div class="tcard-desc">'+ds+'</div>'
      +'<div class="tcard-foot"><span class="badge">'+tp.level+'</span><span class="tcard-qs">30 '+(LANG==='ru'?'вопросов':LANG==='uz'?'savol':'questions')+'</span></div>'
      +'<div class="pbar"><div class="pbar-f" style="width:'+pct+'%;background:'+tp.color+'"></div></div>'
      +'</div>';
  }).join('');
}

function openTopic(id){
  curTopic = null;
  for(var i=0;i<TOPICS.length;i++){ if(TOPICS[i].id===id){ curTopic=TOPICS[i]; break; } }
  if(!curTopic) return;

  document.getElementById('topics-list').style.display='none';
  var dv = document.getElementById('detail-view');
  dv.style.display='block';
  document.getElementById('test-view').style.display='none';
  document.getElementById('result-area').style.display='none';
  document.getElementById('btn-take-test').style.display='inline-flex';

  var lesson = curTopic.lesson[LANG] || curTopic.lesson.en;
  document.getElementById('lesson-card').innerHTML =
    '<h2 style="font-size:1.1rem;font-weight:800;margin-bottom:14px">'+( curTopic.name[LANG]||curTopic.name.en )+'</h2>'
    +'<div class="lesson-body">'+lesson+'</div>';

  document.getElementById('back-btn').textContent = tr('backBtn');
  document.getElementById('btn-take-test').textContent = tr('takeTest');
}

function backToTopics(){
  document.getElementById('topics-list').style.display='';
  document.getElementById('detail-view').style.display='none';
}

// ======================================================
// TEST
// ======================================================
function startTest(){
  curQ = 0;
  answers = new Array(30).fill(null);
  document.getElementById('btn-take-test').style.display='none';
  document.getElementById('test-view').style.display='block';
  document.getElementById('result-area').style.display='none';
  document.getElementById('test-hd').textContent = (curTopic.name[LANG]||curTopic.name.en)+' — Test';
  document.getElementById('test-sub').textContent = tr('testSub');
  renderQ();
}function renderQ(){
  var q = curTopic.qs[curQ];
  document.getElementById('qnum').textContent = (curQ+1)+' / 30';
  document.getElementById('qfill').style.width = (((curQ+1)/30)*100)+'%';
  var letters = ['A','B','C','D'];
  document.getElementById('qarea').innerHTML =
    '<div class="qcard">'
    +'<div class="qcard-num">Question '+(curQ+1)+' of 30</div>'
    +'<div class="qcard-q">'+q.q+'</div>'
    +'<div class="opts">'
    +q.o.map(function(opt,i){
      var cls = 'opt';
      if(answers[curQ]===i) cls+=' sel';
      return '<div class="'+cls+'" onclick="pickOpt('+i+')">'
        +'<div class="opt-l">'+letters[i]+'</div>'
        +'<span>'+opt+'</span></div>';
    }).join('')
    +'</div></div>';

  document.getElementById('pbtn').disabled = curQ===0;
  document.getElementById('pbtn').textContent = tr('prev');
  var nb = document.getElementById('nbtn');
  nb.textContent = (curQ===29) ? tr('finish') : tr('next');
  nb.onclick = (curQ===29) ? finishTest : nextQ;
}

function pickOpt(i){
  answers[curQ]=i;
  renderQ();
}
function prevQ(){ if(curQ>0){curQ--;renderQ();} }
function nextQ(){ if(curQ<29){curQ++;renderQ();} }

function finishTest(){
  var correct=0;
  for(var i=0;i<30;i++){ if(answers[i]===curTopic.qs[i].a) correct++; }
  var pct = Math.round((correct/30)*100);
  progress[curTopic.id] = pct;

  var skipped = 0; for(var j=0;j<30;j++){ if(answers[j]===null) skipped++; }
  var wrong = 30 - correct - skipped;

  var col = pct>=70 ? 'var(--green)' : pct>=40 ? 'var(--gold)' : 'var(--red)';

  document.getElementById('qarea').style.display='none';
  document.querySelector('.test-btns').style.display='none';
  var ra = document.getElementById('result-area');
  ra.style.display='block';
  ra.innerHTML =
    '<div class="result-box">'
    +'<div class="score-ring" style="border-color:'+col+'">'
    +'<div class="score-n" style="color:'+col+'">'+pct+'%</div>'
    +'<div class="score-s">'+tr('scoreLabel')+'</div></div>'
    +'<h2 style="font-size:1.1rem;font-weight:800;margin-bottom:4px">'+(curTopic.name[LANG]||curTopic.name.en)+'</h2>'
    +'<div class="res-grid">'
    +'<div class="rstat"><div class="rstat-n" style="color:var(--green)">'+correct+'</div><div class="rstat-l">'+tr('correct')+'</div></div>'
    +'<div class="rstat"><div class="rstat-n" style="color:var(--red)">'+wrong+'</div><div class="rstat-l">'+tr('wrong')+'</div></div>'
    +'<div class="rstat"><div class="rstat-n" style="color:var(--muted2)">'+skipped+'</div><div class="rstat-l">'+tr('skipped')+'</div></div>'
    +'</div>'
    +'<div class="ai-box">'
    +'<div class="ai-tag">🤖 '+tr('aiTag')+'</div>'
    +'<div class="ai-txt" id="ai-result-txt"><div class="dot-wrap"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div></div>'
    +'</div>'
    +'<button class="btn-start" onclick="retakeTest()" style="background:linear-gradient(135deg,#374151,#1f2937);margin-top:4px">'+tr('retake')+'</button>'
    +'</div>';

  ra.scrollIntoView({behavior:'smooth'});
  aiTestAnalysis(correct, pct, curTopic.name.en);
}

function retakeTest(){
  document.getElementById('qarea').style.display='';
  document.querySelector('.test-btns').style.display='';
  startTest();
}

function aiTestAnalysis(correct, pct, topicName){
  var el = document.getElementById('ai-result-txt');
  if(!el) return;
  var langNote = LANG==='ru' ? 'Respond in Russian.' : LANG==='uz' ? 'Respond in Uzbek.' : '';
  var prompt = 'A student completed a 30-question English test on "'+topicName+'" and scored '+correct+'/30 ('+pct+'%). '+langNote+' Write a short warm analysis (3-4 sentences): what this score means, their approximate level, and 1-2 specific tips to improve on this topic. Be encouraging.';
  callAI(prompt, function(text){
    var e = document.getElementById('ai-result-txt');
    if(e) e.textContent = text;
  });
}// ======================================================
// AI API CALL
// ======================================================
function callAI(prompt, callback){
  fetch('https://api.anthropic.com/v1/messages',{
    method:'POST',
    headers:{'Content-Type':'application/json'},
    body:JSON.stringify({
      model:'claude-sonnet-4-20250514',
      max_tokens:600,
      messages:[{role:'user',content:prompt}]
    })
  }).then(function(r){ return r.json(); })
    .then(function(d){
      var txt = '';
      if(d.content && d.content.length){
        for(var i=0;i<d.content.length;i++){
          if(d.content[i].type==='text'){ txt = d.content[i].text; break; }
        }
      }
      callback(txt || 'AI analysis unavailable.');
    })
    .catch(function(){ callback('AI analysis unavailable. Please check your connection.'); });
}



function renderListening(){
  var c = document.getElementById('listen-content');
  if(!c) return;
  c.innerHTML = LISTENING.map(function(it,i){
    var nm = it.title[LANG] || it.title.en;
    return '<div class="card">'
      +'<div class="aud-card">'
      +'<button class="play-btn" onclick="togglePlay(this)">▶</button>'
      +'<div class="aud-info">'
      +'<div class="aud-title">'+nm+'</div>'
      +'<div class="aud-meta">'+it.level+' · '+it.dur+'</div>'
      +'<div class="aud-track"><div class="aud-prog" style="width:'+it.w+'%"></div></div>'
      +'</div>'
      +'<div class="aud-dur">'+it.dur+'</div>'
      +'</div>'
      +'<p style="font-size:.82rem;color:var(--muted2);margin:.6rem 0">📝 '+tr('listenNote')+'</p>'
      +'<button class="ex-btn" onclick="alert(\''+tr('openEx')+'\')" >🎧 '+tr('openEx')+'</button>'
      +'</div>';
  }).join('');
}

function togglePlay(btn){
  btn.textContent = btn.textContent==='▶' ? '⏸' : '▶';
}

// ======================================================
// READING
// ======================================================
var ARTICLES = [
  {title:{en:'The Future of Artificial Intelligence',ru:'Будущее искусственного интеллекта',uz:'Sun\'iy intellektning kelajagi'},
   level:'B1',
   body:{
     en:'<p>Artificial intelligence is transforming nearly every aspect of modern life. From virtual assistants on smartphones to complex algorithms that predict weather patterns, AI systems are becoming increasingly sophisticated.</p><p>Experts predict that by 2030, AI will have created millions of new jobs while also automating many routine tasks. Critical thinking, creativity, and emotional intelligence are skills that AI cannot easily replicate.</p><p>However, concerns remain about privacy, job displacement, and the ethical use of data. Governments and technology companies are working together to establish regulations that balance innovation with protection of individual rights.</p>',
     ru:'<p>Искусственный интеллект трансформирует почти все аспекты современной жизни. Системы ИИ становятся всё более сложными и интегрированными в повседневную жизнь.</p><p>Эксперты предсказывают, что к 2030 году ИИ создаст миллионы новых рабочих мест, одновременно автоматизируя рутинные задачи. Критическое мышление и творчество — навыки, которые ИИ не может легко воспроизвести.</p><p>Тем не менее остаются опасения относительно конфиденциальности и этичного использования данных.</p>',uz:'<p>Sun\'iy intellekt zamonaviy hayotning deyarli barcha jihatlarini o\'zgartirmoqda. AI tizimlari tobora murakkablashib, kundalik hayotga integratsiyalashib bormoqda.</p><p>Mutaxassislar 2030 yilga kelib AI millionlab yangi ish o\'rinlari yaratishini, shu bilan birga ko\'plab oddiy vazifalarni avtomatlashtirishini bashorat qilmoqda.</p><p>Biroq maxfiylik va ma\'lumotlardan axloqiy foydalanish bo\'yicha tashvishlar qolmoqda.</p>'
   }
  },
  {title:{en:'Benefits of Learning a Second Language',ru:'Преимущества изучения иностранного языка',uz:'Ikkinchi tilni o\'rganishning afzalliklari'},
   level:'A2',
   body:{
     en:'<p>Learning a second language has numerous cognitive benefits beyond simply communicating with more people. Research has shown that bilingual individuals often have better problem-solving skills and can focus more effectively.</p><p>Studies suggest that regularly switching between two languages exercises the brain and may even delay the onset of dementia by several years. Children who learn second languages at young ages tend to show greater creativity.</p><p>Moreover, in today\'s globalised world, being multilingual opens doors professionally. Many companies prefer candidates who can communicate across cultures, making language learning one of the most valuable investments.</p>',
     ru:'<p>Изучение второго языка имеет многочисленные когнитивные преимущества. Исследования показывают, что двуязычные люди часто лучше решают проблемы и более эффективно концентрируются.</p><p>Исследования также предполагают, что регулярное переключение между двумя языками может задержать появление деменции на несколько лет.</p><p>Кроме того, в современном глобализированном мире многоязычность открывает профессиональные двери.</p>',
     uz:'<p>Ikkinchi tilni o\'rganish bir qator kognitiv afzalliklarni beradi. Tadqiqotlar shuni ko\'rsatadiki, ikki tilli odamlar ko\'pincha muammolarni yaxshiroq hal qiladi.</p><p>Muntazam ravishda ikki til o\'rtasida almashinish miyani mashq qildiradi va demensia boshlanishini bir necha yilga kechiktirishi mumkin.</p><p>Bundan tashqari, globallashgan dunyoda ko\'p tilli bo\'lish professional imkoniyatlar eshigini ochadi.</p>'
   }
  },
];

function renderReading(){
  var c = document.getElementById('read-content');
  if(!c) return;
  c.innerHTML = ARTICLES.map(function(art,i){
    var nm = art.title[LANG]||art.title.en;
    var body = art.body[LANG]||art.body.en;
    return '<div class="card" style="margin-bottom:16px">'
      +'<div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">'
      +'<h3 style="font-size:.95rem;font-weight:700">'+nm+'</h3>'
      +'<span class="badge">'+art.level+'</span></div>'
      +'<div class="read-txt">'+body+'</div>'
      +'<button class="ex-btn" onclick="alert(\''+tr('readQs')+'\')" >❓ '+tr('readQs')+'</button>'
      +'</div>';
  }).join('');
}

// ======================================================
// WRITING
// ======================================================
var WRITE_PROMPTS = [
  {en:'Write an email (100-150 words) to your professor explaining why you missed class.',
   ru:'Напишите письмо (100-150 слов) профессору, объясняя, почему вы пропустили занятие.',
   uz:'Professoringizga dars o\'tkazib yuborganingizni tushuntiruvchi elektron xat yozing (100-150 so\'z).'},
  {en:'Describe your ideal city of the future. What would it look like? (150-200 words)',
   ru:'Опишите ваш идеальный город будущего (150-200 слов).',
   uz:'Kelajakdagi ideal shahringizni tasvirlab bering (150-200 so\'z).'},
  {en:'Opinion essay: "Social media does more harm than good." Agree or disagree? (150-200 words)',
   ru:'Эссе: «Социальные сети приносят больше вреда, чем пользы». Согласны или нет? (150-200 слов)',
   uz:'Fikr inshosi: «Ijtimoiy tarmoqlar foydadan ko\'ra ko\'proq zarar keltiradi.» Rozi yoki yo\'qsiz? (150-200 so\'z)'},
];function renderWriting(){
  var c = document.getElementById('write-content');
  if(!c) return;
  c.innerHTML = WRITE_PROMPTS.map(function(p,i){
    var prompt = p[LANG]||p.en;
    return '<div class="card" style="margin-bottom:16px">'
      +'<h3 style="font-size:.9rem;font-weight:700;color:var(--cyan);margin-bottom:8px">✍️ Prompt '+(i+1)+'</h3>'
      +'<div class="w-prompt">'+prompt+'</div>'
      +'<textarea class="w-area" id="wa'+i+'" placeholder="'+(LANG==='ru'?'Напишите ваш ответ здесь...':LANG==='uz'?'Bu yerga javobingizni yozing...':'Write your response here...')+'" oninput="updateWc('+i+')"></textarea>'
      +'<div class="w-foot">'
      +'<span class="wc" id="wc'+i+'">0 '+tr('words')+'</span>'
      +'<button class="btn btn-p" style="font-size:.82rem;padding:7px 14px" onclick="submitWrite('+i+')">'+tr('submitWrite')+'</button>'
      +'</div>'
      +'<div id="wfb'+i+'" style="display:none;margin-top:12px" class="ai-box">'
      +'<div class="ai-tag">🤖 AI Feedback</div>'
      +'<div class="ai-txt" id="wft'+i+'"></div>'
      +'</div></div>';
  }).join('');
}

function updateWc(i){
  var ta = document.getElementById('wa'+i);
  if(!ta) return;
  var w = ta.value.trim().split(/\s+/).filter(Boolean).length;
  var el = document.getElementById('wc'+i);
  if(el) el.textContent = w+' '+tr('words');
}

function submitWrite(i){
  var ta = document.getElementById('wa'+i);
  if(!ta||ta.value.trim().length<20){
    alert(LANG==='ru'?'Пожалуйста, напишите больше текста.':LANG==='uz'?'Iltimos, ko\'proq matn yozing.':'Please write more text first.');
    return;
  }
  var fb = document.getElementById('wfb'+i);
  var ft = document.getElementById('wft'+i);
  if(!fb||!ft) return;
  fb.style.display='block';
  ft.innerHTML='<div class="dot-wrap"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div>';

  var prompt_text = WRITE_PROMPTS[i][LANG]||WRITE_PROMPTS[i].en;
  var langNote = LANG==='ru'?'Respond in Russian.':LANG==='uz'?'Respond in Uzbek.':'';
  var req = 'You are an English writing teacher. '+langNote+' A student wrote this in response to: "'+prompt_text+'"\n\nStudent essay:\n"'+ta.value.trim()+'"\n\nGive feedback on: grammar, vocabulary, coherence, task achievement. Give an IELTS-style band score estimate (1-9) and 2-3 improvement tips. Be warm and constructive. Keep it under 200 words.';

  callAI(req, function(text){
    var e = document.getElementById('wft'+i);
    if(e) e.textContent = text;
  });
}

// ======================================================
// SPEAKING
// ======================================================
var SPEAK_TASKS = [
  {en:'Describe your hometown. What do you like most about it? (Speak for 1-2 minutes)',
   ru:'Опишите ваш родной город. Что вам в нём нравится больше всего? (1-2 минуты)',
   uz:'Tug\'ilgan shahringizni tasvirlab bering. Unda nimani ko\'proq yoqtirasiz? (1-2 daqiqa)'},
  {en:'Talk about a memorable trip you have taken. Where did you go and why was it special?',
   ru:'Расскажите о незабываемом путешествии. Куда вы ездили и почему это было особенным?',
   uz:'Unutilmas sayohatingiz haqida gapiring. Qayerga borgansiz va nima uchun u maxsus edi?'},
  {en:'What are the advantages and disadvantages of working from home?',
   ru:'Каковы преимущества и недостатки работы из дома?',
   uz:'Uydan ishlashning afzalliklari va kamchiliklari qanday?'},
  {en:'Describe a person who has had a big influence on your life.',
   ru:'Опишите человека, который оказал большое влияние на вашу жизнь.',
   uz:'Hayotingizga katta ta\'sir ko\'rsatgan insonni tasvirlab bering.'},
];

function renderSpeaking(){
  var c = document.getElementById('speak-content');
  if(!c) return;
  c.innerHTML = SPEAK_TASKS.map(function(t,i){
    var txt = t[LANG]||t.en;
    return '<div class="sp-card">'+'<button class="mic-btn" onclick="this.style.background=\'rgba(248,113,113,.4)\';setTimeout(()=>this.style.background=\'\',2000)">🎙️</button>'
      +'<div class="sp-body">'
      +'<div class="sp-task">'+(LANG==='ru'?'Задание':LANG==='uz'?'Topshiriq':'Task')+' '+(i+1)+'</div>'
      +'<div style="color:var(--muted2);font-size:.88rem;margin:.4rem 0">'+txt+'</div>'
      +'<div class="sp-hint">'+tr('recordHint')+'</div>'
      +'</div></div>';
  }).join('');
}

// ======================================================
// VOCABULARY
// ======================================================
var VOCAB = [
  {word:'Eloquent',    trans:{en:'Fluent & persuasive in speech',ru:'Красноречивый',uz:'Notiq'},       ex:'She gave an eloquent speech.'},
  {word:'Perseverance',trans:{en:'Continued effort despite difficulty',ru:'Настойчивость',uz:'Qat\'iyat'},ex:'Success requires perseverance.'},
  {word:'Ambiguous',   trans:{en:'Open to more than one interpretation',ru:'Неоднозначный',uz:'Noaniq'},  ex:'His answer was ambiguous.'},
  {word:'Collaborate', trans:{en:'Work jointly on a task',ru:'Сотрудничать',uz:'Hamkorlik qilmoq'},      ex:'Teams must collaborate.'},
  {word:'Substantial', trans:{en:'Of considerable size or importance',ru:'Существенный',uz:'Muhim'},      ex:'A substantial amount of work.'},
  {word:'Inevitable',  trans:{en:'Certain to happen; unavoidable',ru:'Неизбежный',uz:'Muqarrar'},        ex:'Change is inevitable.'},
  {word:'Profound',    trans:{en:'Very great or having deep insight',ru:'Глубокий',uz:'Chuqur'},          ex:'A profound impact on society.'},
  {word:'Diligent',    trans:{en:'Showing careful and persistent effort',ru:'Прилежный',uz:'Mehnatsevar'},ex:'She was a diligent student.'},
  {word:'Versatile',   trans:{en:'Able to adapt to many functions',ru:'Разносторонний',uz:'Ko\'p qirrali'},ex:'A versatile team member.'},
  {word:'Concise',     trans:{en:'Brief and clearly expressed',ru:'Краткий',uz:'Qisqa'},                  ex:'Keep your writing concise.'},
  {word:'Empathy',     trans:{en:'Understanding others\' feelings',ru:'Эмпатия',uz:'Empatiya'},            ex:'Leaders show empathy.'},
  {word:'Resilient',   trans:{en:'Able to recover quickly from difficulties',ru:'Устойчивый',uz:'Bardoshli'},ex:'She is remarkably resilient.'},
  {word:'Meticulous',  trans:{en:'Showing great attention to detail',ru:'Скрупулёзный',uz:'Sinchkov'},    ex:'He is meticulous in his work.'},
  {word:'Eloquence',   trans:{en:'Fluent, forceful expression',ru:'Красноречие',uz:'Notiqlik'},            ex:'She spoke with great eloquence.'},
  {word:'Ambitious',   trans:{en:'Having a strong desire to succeed',ru:'Честолюбивый',uz:'Ambitsiyali'}, ex:'She is an ambitious student.'},
  {word:'Critique',    trans:{en:'A detailed analysis and assessment',ru:'Критика/разбор',uz:'Tahlil'},    ex:'She wrote a thoughtful critique.'},
];

function renderVocab(){
  var c = document.getElementById('vocab-content');
  if(!c) return;
  c.innerHTML = '<div class="vgrid">'
    +VOCAB.map(function(v){
      var t = v.trans[LANG]||v.trans.en;
      return '<div class="vcard">'
        +'<div class="vword">'+v.word+'</div>'
        +'<div class="vtrans">'+t+'</div>'
        +'<div class="vex">"'+v.ex+'"</div>'
        +'</div>';
    }).join('')+'</div>';
}

// ======================================================
// GRAMMAR
// ======================================================
var GRAMMAR_RULES = [
  {title:'Subject-Verb Agreement',
   en:'The verb must agree with its subject in number.',
   ru:'Глагол должен согласоваться с подлежащим в числе.',
   uz:'Fe\'l ega bilan sonda mos kelishi kerak.',
   formula:'[Singular subject] + [singular verb]',
   ex:'She works hard. / They work hard.'},
  {title:'Perfect Tenses',
   en:'Use "have/has/had + past participle" to connect time frames.',   ru:'Используйте "have/has/had + причастие II" для связи временных планов.',
   uz:'"have/has/had + o\'tgan zamon sifatdoshi" ni vaqt davrlarini bog\'lash uchun ishlating.',
   formula:'have / has / had + V3 (past participle)',
   ex:'I have finished. / She had left before I arrived.'},
  {title:'Comparative & Superlative',
   en:'Used to compare two or more things.',
   ru:'Используется для сравнения двух или более предметов.',
   uz:'Ikki yoki undan ko\'p narsani solishtirish uchun ishlatiladi.',
   formula:'Adj + -er than | the + Adj + -est',
   ex:'She is taller than him. / He is the tallest in class.'},
  {title:'Relative Clauses',
   en:'Clauses that give more information about a noun.',
   ru:'Придаточные предложения, дающие дополнительную информацию о существительном.',
   uz:'Ot haqida qo\'shimcha ma\'lumot beruvchi qo\'shma gaplar.',
   formula:'Noun + who / which / that + clause',
   ex:'The man who called you is here. / The book that I read was great.'},
  {title:'Gerunds vs Infinitives',
   en:'Some verbs take gerunds (-ing), others take infinitives (to + V).',
   ru:'Одни глаголы требуют герундия, другие — инфинитива.',
   uz:'Ba\'zi fe\'llar gerundiy (-ing) oladi, boshqalari infinitiv (to + V) oladi.',
   formula:'enjoy/finish/avoid + V-ing | want/plan/hope + to + V',
   ex:'She enjoys swimming. / He wants to swim.'},
  {title:'Reported Speech Rules',
   en:'Tenses shift back when reporting speech.',
   ru:'Времена сдвигаются назад при косвенной речи.',
   uz:'Bilvosita nutqda zamonlar orqaga siljiydi.',
   formula:'am/is → was | will → would | can → could | have → had',
   ex:'"I am tired." → She said she was tired.'},
];

function renderGrammar(){
  var c = document.getElementById('gram-content');
  if(!c) return;
  c.innerHTML = GRAMMAR_RULES.map(function(r){
    var desc = r[LANG]||r.en;
    return '<div class="grule">'
      +'<h3>'+r.title+'</h3>'
      +'<p>'+desc+'</p>'
      +'<div class="formula">'+r.formula+'</div>'
      +'<div class="ex-box">'+r.ex+'</div>'
      +'</div>';
  }).join('');
}

// ======================================================
// AI CHAT
// ======================================================
var chatHistory = [];

function sendChat(){
  var inp = document.getElementById('chat-inp');
  var msgs = document.getElementById('chat-msgs');
  var text = inp.value.trim();
  if(!text) return;
  inp.value='';

  chatHistory.push({role:'user',content:text});

  msgs.innerHTML += '<div class="msg usr"><div class="msg-b">'+escHtml(text)+'</div><div class="msg-t">now</div></div>';

  var loadId = 'ld'+Date.now();
  msgs.innerHTML += '<div class="msg ai" id="'+loadId+'"><div class="msg-b"><div class="dot-wrap"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div></div></div>';
  msgs.scrollTop = msgs.scrollHeight;

  var langNote = LANG==='ru'?'Please respond in Russian.':LANG==='uz'?'Please respond in Uzbek.':'';
  var sysMsg = 'You are EnglishPro AI, a friendly expert English language tutor. '+langNote+' Give clear, helpful answers about grammar, vocabulary, pronunciation, and usage. Use examples. Keep answers concise but complete (max 150 words).';

  // build message list for API
  var apiMsgs = [{role:'user',content:sysMsg+'\n\nUser says: '+text}];

  fetch('https://api.anthropic.com/v1/messages',{
    method:'POST',
    headers:{'Content-Type':'application/json'},
    body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:600,messages:apiMsgs})
  }).then(function(r){ return r.json(); })
    .then(function(d){
      var txt = '';
      if(d.content && d.content.length){
        for(var i=0;i<d.content.length;i++){
          if(d.content[i].type==='text'){txt=d.content[i].text;break;}
        }
      }
      txt = txt || 'Sorry, I could not process that.';chatHistory.push({role:'assistant',content:txt});
      var el = document.getElementById(loadId);
      if(el) el.innerHTML = '<div class="msg-b">'+escHtml(txt).replace(/\n/g,'<br>')+'</div><div class="msg-t">now</div>';
      msgs.scrollTop = msgs.scrollHeight;
    })
    .catch(function(){
      var el = document.getElementById(loadId);
      if(el) el.innerHTML = '<div class="msg-b">Connection error. Please try again.</div><div class="msg-t">now</div>';
    });
}

function escHtml(s){
  return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

// ======================================================
// PROGRESS
// ======================================================
function renderProgress(){
  var grid = document.getElementById('prog-grid');
  if(!grid) return;

  var total = 0; var done = 0;
  TOPICS.forEach(function(t){ total++; if(progress[t.id]) done++; });

  var overall = 0;
  TOPICS.forEach(function(t){ overall += (progress[t.id]||0); });
  overall = Math.round(overall/TOPICS.length);

  var sections = [
    {label:LANG==='ru'?'Общий прогресс':LANG==='uz'?'Umumiy taraqqiyot':'Overall Progress', pct:overall, color:'var(--blue)'},
    {label:LANG==='ru'?'Завершено тем':LANG==='uz'?'Tugatilgan mavzular':'Topics Completed', pct:Math.round((done/total)*100), color:'var(--cyan)'},
  ];

  grid.innerHTML = sections.map(function(s){
    return '<div class="pgcard">'
      +'<div class="pgcard-top"><div class="pgcard-lbl">'+s.label+'</div>'
      +'<div class="pgcard-pct" style="color:'+s.color+'">'+s.pct+'%</div></div>'
      +'<div class="pgbar"><div class="pgbar-f" style="width:'+s.pct+'%;background:'+s.color+'"></div></div>'
      +'</div>';
  }).join('')
  + TOPICS.map(function(t){
    var pct = progress[t.id]||0;
    var nm = t.name[LANG]||t.name.en;
    return '<div class="pgcard">'
      +'<div class="pgcard-top"><div class="pgcard-lbl">'+t.ico+' '+nm+'</div>'
      +'<div class="pgcard-pct" style="color:'+t.color+';font-size:1.3rem">'+pct+'%</div></div>'
      +'<div class="pgbar"><div class="pgbar-f" style="width:'+pct+'%;background:'+t.color+'"></div></div>'
      +'</div>';
  }).join('');

  document.getElementById('analyze-btn').textContent = tr('analyzeBtn');
}

function analyzeProgress(){
  var box = document.getElementById('prog-ai-box');
  var txt = document.getElementById('prog-ai-txt');
  if(!box||!txt) return;
  box.style.display='block';
  txt.innerHTML='<div class="dot-wrap"><div class="dot"></div><div class="dot"></div><div class="dot"></div></div>';

  var done = TOPICS.filter(function(t){return progress[t.id]>0;});
  var langNote = LANG==='ru'?'Respond in Russian.':LANG==='uz'?'Respond in Uzbek.':'';

  var prompt;
  if(done.length===0){
    prompt = 'A student has not started any English tests yet. '+langNote+' Encourage them warmly to start. Suggest starting with "Present Tenses" as it\'s good for beginners. Keep it to 3-4 sentences.';
  } else {
    var list = done.map(function(t){return (t.name.en)+': '+progress[t.id]+'%';}).join(', ');
    prompt = 'A student has completed these English tests: '+list+'. '+langNote+' Give a motivational progress analysis (4-5 sentences): overall level assessment, strongest topics, weakest areas, and what to study next. Be encouraging and specific.';
  }
  callAI(prompt, function(text){
    var e = document.getElementById('prog-ai-txt');
    if(e){ e.textContent=''; e.innerHTML='<div class="ai-tag">🤖 '+tr('aiTag')+'</div><div>'+escHtml(text)+'</div>'; }
  });
}

// ======================================================
// INIT
// ======================================================
buildTabs();
renderTopics();
showPage('topics');
</script>
</body>
</html>
