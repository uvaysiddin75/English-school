
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EnglishMaster Pro</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Baloo+2:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
:root {
  --primary: #6C63FF;
  --secondary: #FF6584;
  --accent: #43E97B;
  --gold: #FFD700;
  --bg: #0F0E17;
  --surface: #1A1A2E;
  --surface2: #16213E;
  --card: #1E1E3F;
  --text: #FFFFFE;
  --text2: #A7A9BE;
  --border: rgba(108,99,255,0.3);
  --green: #43E97B;
  --red: #FF6584;
  --orange: #FF9F43;
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Nunito',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow-x:hidden;}
/* SCROLLBAR */
::-webkit-scrollbar{width:6px;}
::-webkit-scrollbar-track{background:var(--surface);}
::-webkit-scrollbar-thumb{background:var(--primary);border-radius:3px;}

/* HEADER */
.header{background:linear-gradient(135deg,var(--surface) 0%,var(--surface2) 100%);padding:12px 20px;display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid var(--border);position:sticky;top:0;z-index:100;backdrop-filter:blur(10px);}
.logo{font-family:'Baloo 2',sans-serif;font-size:1.6rem;font-weight:800;background:linear-gradient(135deg,var(--primary),var(--secondary));-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
.header-right{display:flex;align-items:center;gap:12px;}
.xp-bar{display:flex;align-items:center;gap:8px;background:rgba(108,99,255,0.15);padding:6px 14px;border-radius:20px;border:1px solid var(--border);}
.xp-bar span{font-size:.85rem;font-weight:700;color:var(--gold);}
.streak{display:flex;align-items:center;gap:4px;font-size:.85rem;font-weight:700;color:var(--orange);}
.lang-switch{display:flex;gap:4px;}
.lang-btn{padding:4px 10px;border-radius:12px;border:1px solid var(--border);background:transparent;color:var(--text2);cursor:pointer;font-size:.75rem;font-weight:700;transition:all .2s;}
.lang-btn.active{background:var(--primary);color:#fff;border-color:var(--primary);}

/* NAV */
.nav{display:flex;gap:4px;padding:10px 16px;background:var(--surface2);border-bottom:1px solid var(--border);overflow-x:auto;scrollbar-width:none;}
.nav::-webkit-scrollbar{display:none;}
.nav-btn{padding:8px 16px;border-radius:20px;border:none;background:transparent;color:var(--text2);cursor:pointer;font-size:.85rem;font-weight:700;white-space:nowrap;transition:all .2s;font-family:'Nunito',sans-serif;}
.nav-btn.active{background:linear-gradient(135deg,var(--primary),#8B80FF);color:#fff;box-shadow:0 4px 15px rgba(108,99,255,0.4);}
.nav-btn:hover:not(.active){background:rgba(108,99,255,0.1);color:var(--text);}

/* MAIN */
.main{padding:16px;max-width:900px;margin:0 auto;}

/* SECTION */
.section{display:none;}
.section.active{display:block;}

/* CARDS */
.card{background:var(--card);border-radius:16px;padding:20px;margin-bottom:16px;border:1px solid var(--border);}
.card-title{font-family:'Baloo 2',sans-serif;font-size:1.2rem;font-weight:700;margin-bottom:12px;display:flex;align-items:center;gap:8px;}

/* LEVEL CARDS */
.levels-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:12px;margin-bottom:20px;}
.level-card{background:var(--card);border-radius:16px;padding:16px;text-align:center;cursor:pointer;border:2px solid var(--border);transition:all .3s;position:relative;overflow:hidden;}
.level-card:hover{transform:translateY(-4px);border-color:var(--primary);box-shadow:0 8px 25px rgba(108,99,255,0.3);}
.level-card.completed{border-color:var(--accent);}
.level-card.locked{opacity:.5;cursor:not-allowed;}
.level-emoji{font-size:2.5rem;margin-bottom:8px;}
.level-name{font-weight:800;font-size:.95rem;margin-bottom:4px;}
.level-desc{font-size:.75rem;color:var(--text2);}
.level-progress{margin-top:8px;height:4px;background:rgba(255,255,255,.1);border-radius:2px;}
.level-progress-fill{height:100%;background:linear-gradient(90deg,var(--primary),var(--accent));border-radius:2px;transition:width .5s;}
.level-stars{color:var(--gold);font-size:.9rem;margin-top:4px;}

/* TOPICS */
.topics-list{display:flex;flex-direction:column;gap:10px;}
.topic-item{background:var(--surface2);border-radius:12px;padding:14px 16px;cursor:pointer;border:1px solid var(--border);display:flex;align-items:center;gap:12px;transition:all .2s;}
.topic-item:hover{border-color:var(--primary);background:rgba(108,99,255,0.1);}
.topic-item.done{border-color:var(--accent);}
.topic-icon{font-size:1.5rem;min-width:32px;}
.topic-info{flex:1;}
.topic-title{font-weight:700;font-size:.95rem;}
.topic-subtitle{font-size:.75rem;color:var(--text2);margin-top:2px;}
.topic-badge{padding:4px 10px;border-radius:10px;font-size:.72rem;font-weight:700;}
.badge-new{background:rgba(108,99,255,.2);color:var(--primary);}
.badge-done{background:rgba(67,233,123,.2);color:var(--accent);}

/* LESSON */
.lesson-header{display:flex;align-items:center;gap:10px;margin-bottom:20px;}
.back-btn{background:rgba(108,99,255,.15);border:1px solid var(--border);color:var(--text);padding:8px 14px;border-radius:10px;cursor:pointer;font-size:.85rem;font-weight:700;transition:all .2s;}
.back-btn:hover{background:var(--primary);border-color:var(--primary);}
.lesson-title{font-family:'Baloo 2',sans-serif;font-size:1.3rem;font-weight:800;}

.lesson-content{background:var(--card);border-radius:16px;padding:20px;margin-bottom:16px;line-height:1.8;border:1px solid var(--border);}
.lesson-content h3{color:var(--primary);margin-bottom:10px;font-size:1.1rem;}
.lesson-content p{color:var(--text2);margin-bottom:12px;font-size:.9rem;}
.lesson-content .example{background:rgba(108,99,255,.08);border-left:3px solid var(--primary);padding:10px 14px;border-radius:0 8px 8px 0;margin:8px 0;font-size:.9rem;}
.lesson-content .example strong{color:var(--primary);}
.lesson-content ul{padding-left:20px;color:var(--text2);font-size:.9rem;}
.lesson-content ul li{margin-bottom:6px;}
.lesson-content .vocab-table{width:100%;border-collapse:collapse;margin:10px 0;}
.lesson-content .vocab-table th{background:rgba(108,99,255,.2);padding:8px 12px;text-align:left;font-size:.85rem;}
.lesson-content .vocab-table td{padding:8px 12px;border-bottom:1px solid var(--border);font-size:.85rem;color:var(--text2);}
.lesson-content .vocab-table td:first-child{color:var(--text);font-weight:700;}

.start-test-btn{width:100%;padding:14px;border-radius:12px;background:linear-gradient(135deg,var(--primary),var(--secondary));border:none;color:#fff;font-size:1rem;font-weight:800;cursor:pointer;transition:all .2s;font-family:'Nunito',sans-serif;}
.start-test-btn:hover{transform:translateY(-2px);box-shadow:0 8px 20px rgba(108,99,255,.4);}

/* TEST */
.test-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px;}
.test-progress-bar{height:6px;background:rgba(255,255,255,.1);border-radius:3px;margin-bottom:20px;overflow:hidden;}
.test-progress-fill{height:100%;background:linear-gradient(90deg,var(--primary),var(--accent));border-radius:3px;transition:width .4s;}
.question-num{font-size:.85rem;color:var(--text2);font-weight:700;}
.question-score{font-size:.85rem;color:var(--gold);font-weight:700;}
.question-card{background:var(--card);border-radius:16px;padding:20px;margin-bottom:16px;border:1px solid var(--border);}
.question-type{font-size:.72rem;color:var(--primary);font-weight:700;margin-bottom:8px;text-transform:uppercase;letter-spacing:.5px;}
.question-text{font-size:1rem;font-weight:700;margin-bottom:16px;line-height:1.5;}
.options{display:flex;flex-direction:column;gap:8px;}
.option-btn{padding:12px 16px;border-radius:10px;border:1px solid var(--border);background:rgba(255,255,255,.03);color:var(--text);cursor:pointer;text-align:left;font-size:.9rem;font-weight:600;transition:all .2s;font-family:'Nunito',sans-serif;}
.option-btn:hover:not(:disabled){background:rgba(108,99,255,.15);border-color:var(--primary);}
.option-btn.correct{background:rgba(67,233,123,.15);border-color:var(--accent);color:var(--accent);}
.option-btn.wrong{background:rgba(255,101,132,.15);border-color:var(--red);color:var(--red);}
.option-btn:disabled{cursor:default;}
.fill-input{width:100%;padding:12px 16px;border-radius:10px;border:1px solid var(--border);background:rgba(255,255,255,.05);color:var(--text);font-size:.95rem;font-family:'Nunito',sans-serif;outline:none;}
.fill-input:focus{border-color:var(--primary);}
.fill-input.correct{border-color:var(--accent);background:rgba(67,233,123,.1);}
.fill-input.wrong{border-color:var(--red);background:rgba(255,101,132,.1);}
.next-btn{width:100%;padding:12px;border-radius:10px;background:var(--primary);border:none;color:#fff;font-size:.95rem;font-weight:700;cursor:pointer;margin-top:12px;transition:all .2s;font-family:'Nunito',sans-serif;}
.next-btn:hover{background:#8B80FF;}
.next-btn:disabled{opacity:.4;cursor:default;}
.feedback{padding:10px 14px;border-radius:10px;margin-top:10px;font-size:.88rem;font-weight:700;}
.feedback.good{background:rgba(67,233,123,.15);color:var(--accent);}
.feedback.bad{background:rgba(255,101,132,.15);color:var(--red);}

/* RESULT */
.result-card{text-align:center;padding:30px 20px;}
.result-emoji{font-size:4rem;margin-bottom:16px;}
.result-score{font-size:3rem;font-weight:900;font-family:'Baloo 2',sans-serif;}
.result-score.excellent{color:var(--accent);}
.result-score.good{color:var(--gold);}
.result-score.poor{color:var(--red);}
.result-label{font-size:1.1rem;color:var(--text2);margin-bottom:20px;}
.result-stats{display:flex;justify-content:center;gap:20px;margin-bottom:24px;}
.stat-item{text-align:center;}
.stat-num{font-size:1.5rem;font-weight:800;color:var(--primary);}
.stat-lbl{font-size:.75rem;color:var(--text2);}
.ai-feedback-box{background:rgba(108,99,255,.08);border:1px solid var(--border);border-radius:12px;padding:16px;margin-bottom:20px;text-align:left;}
.ai-feedback-box h4{color:var(--primary);margin-bottom:8px;font-size:.95rem;}
.ai-feedback-box p{font-size:.85rem;color:var(--text2);line-height:1.6;}
.retry-btn{padding:12px 28px;border-radius:12px;background:linear-gradient(135deg,var(--primary),var(--secondary));border:none;color:#fff;font-weight:800;cursor:pointer;font-size:.95rem;margin:0 6px;font-family:'Nunito',sans-serif;}
.home-btn{padding:12px 28px;border-radius:12px;background:transparent;border:1px solid var(--border);color:var(--text);font-weight:700;cursor:pointer;font-size:.95rem;margin:0 6px;font-family:'Nunito',sans-serif;}

/* LISTENING */
.audio-player{background:var(--surface2);border-radius:14px;padding:16px;margin-bottom:16px;border:1px solid var(--border);}
.audio-controls{display:flex;align-items:center;gap:12px;margin-bottom:10px;}
.play-btn{width:44px;height:44px;border-radius:50%;background:var(--primary);border:none;color:#fff;font-size:1.1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .2s;flex-shrink:0;}
.play-btn:hover{background:#8B80FF;transform:scale(1.05);}
.audio-info{flex:1;}
.audio-title{font-weight:700;font-size:.9rem;}
.audio-dur{font-size:.75rem;color:var(--text2);}
.audio-wave{height:40px;background:rgba(108,99,255,.1);border-radius:8px;display:flex;align-items:center;justify-content:center;overflow:hidden;cursor:pointer;position:relative;}
.wave-bars{display:flex;align-items:center;gap:2px;height:100%;padding:4px 8px;}
.wave-bar{background:var(--primary);border-radius:2px;width:3px;transition:height .1s;}
.transcript-toggle{font-size:.8rem;color:var(--primary);cursor:pointer;font-weight:700;margin-top:8px;display:inline-block;}
.transcript-box{background:rgba(255,255,255,.03);border-radius:10px;padding:12px;margin-top:10px;font-size:.85rem;color:var(--text2);line-height:1.7;display:none;}
.transcript-box.show{display:block;}
.speed-btns{display:flex;gap:6px;margin-top:8px;}
.speed-btn{padding:4px 10px;border-radius:8px;border:1px solid var(--border);background:transparent;color:var(--text2);font-size:.75rem;cursor:pointer;font-family:'Nunito',sans-serif;transition:all .2s;}
.speed-btn.active{background:var(--primary);color:#fff;border-color:var(--primary);}

/* SPEAKING */
.speaking-card{background:var(--card);border-radius:16px;padding:24px;text-align:center;border:1px solid var(--border);margin-bottom:16px;}
.mic-area{width:100px;height:100px;border-radius:50%;background:linear-gradient(135deg,var(--primary),var(--secondary));margin:0 auto 16px;display:flex;align-items:center;justify-content:center;font-size:2.5rem;cursor:pointer;transition:all .3s;border:3px solid transparent;}
.mic-area.recording{animation:pulse 1s infinite;border-color:var(--red);}
.mic-area.playing{background:linear-gradient(135deg,var(--accent),var(--primary));}
@keyframes pulse{0%,100%{transform:scale(1);box-shadow:0 0 0 0 rgba(255,101,132,.4);}50%{transform:scale(1.05);box-shadow:0 0 0 20px rgba(255,101,132,0);}}
.speaking-prompt{font-size:1rem;font-weight:700;margin-bottom:8px;}
.speaking-sub{font-size:.85rem;color:var(--text2);}
.speaking-status{margin-top:12px;font-size:.85rem;font-weight:700;min-height:22px;}
.speaking-status.ok{color:var(--accent);}
.speaking-status.err{color:var(--red);}
.ai-response-box{background:rgba(108,99,255,.08);border-radius:12px;padding:14px;margin-top:12px;text-align:left;}
.ai-response-box .ai-label{font-size:.75rem;color:var(--primary);font-weight:700;margin-bottom:6px;}
.ai-response-box p{font-size:.88rem;color:var(--text2);line-height:1.6;}
.speak-score{display:flex;gap:12px;margin-top:12px;justify-content:center;}
.score-pill{padding:6px 14px;border-radius:20px;font-size:.8rem;font-weight:700;}
.score-pill.acc{background:rgba(67,233,123,.2);color:var(--accent);}
.score-pill.flu{background:rgba(108,99,255,.2);color:var(--primary);}
.score-pill.pron{background:rgba(255,159,67,.2);color:var(--orange);}
.conv-history{max-height:300px;overflow-y:auto;margin-bottom:12px;}
.conv-msg{margin-bottom:10px;}
.conv-msg.ai{text-align:left;}
.conv-msg.user{text-align:right;}
.conv-bubble{display:inline-block;padding:10px 14px;border-radius:14px;max-width:80%;font-size:.88rem;line-height:1.5;}
.conv-msg.ai .conv-bubble{background:rgba(108,99,255,.15);border:1px solid var(--border);}
.conv-msg.user .conv-bubble{background:linear-gradient(135deg,var(--primary),#8B80FF);color:#fff;}

/* READING */
.reading-text{background:var(--surface2);border-radius:14px;padding:20px;margin-bottom:16px;border:1px solid var(--border);line-height:1.9;font-size:.92rem;color:var(--text2);}
.reading-text h3{color:var(--text);font-size:1.1rem;margin-bottom:12px;}
.reading-text p{margin-bottom:10px;}
.highlight-word{background:rgba(108,99,255,.2);border-radius:4px;padding:1px 4px;cursor:pointer;color:var(--primary);font-weight:700;}
.word-popup{position:fixed;background:var(--card);border:1px solid var(--border);border-radius:12px;padding:14px;font-size:.85rem;max-width:220px;z-index:200;box-shadow:0 8px 30px rgba(0,0,0,.5);display:none;}
.word-popup.show{display:block;}
.word-popup .w-word{font-weight:800;color:var(--primary);font-size:1rem;}
.word-popup .w-pron{color:var(--text2);font-size:.8rem;margin:2px 0;}
.word-popup .w-def{color:var(--text);font-size:.83rem;margin-top:4px;}

/* VOCABULARY */
.vocab-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:10px;}
.vocab-card{background:var(--surface2);border-radius:12px;padding:14px;border:1px solid var(--border);cursor:pointer;transition:all .2s;text-align:center;}
.vocab-card:hover{border-color:var(--primary);transform:translateY(-2px);}
.vocab-card.flipped{background:rgba(108,99,255,.1);}
.vocab-word{font-weight:800;font-size:1rem;margin-bottom:4px;}
.vocab-trans{font-size:.8rem;color:var(--text2);display:none;}
.vocab-card.flipped .vocab-trans{display:block;}
.vocab-card.flipped .vocab-word{color:var(--primary);}
.vocab-pron{font-size:.75rem;color:var(--text2);margin-bottom:6px;}
.vocab-level-badge{font-size:.65rem;font-weight:700;padding:2px 8px;border-radius:8px;background:rgba(108,99,255,.2);color:var(--primary);}
.vocab-search{width:100%;padding:10px 16px;border-radius:10px;border:1px solid var(--border);background:rgba(255,255,255,.05);color:var(--text);font-size:.9rem;font-family:'Nunito',sans-serif;outline:none;margin-bottom:14px;}
.vocab-filter{display:flex;gap:6px;margin-bottom:14px;flex-wrap:wrap;}
.vf-btn{padding:5px 12px;border-radius:10px;border:1px solid var(--border);background:transparent;color:var(--text2);font-size:.78rem;cursor:pointer;font-family:'Nunito',sans-serif;transition:all .2s;}
.vf-btn.active{background:var(--primary);color:#fff;border-color:var(--primary);}

/* LEADERBOARD */
.lb-list{display:flex;flex-direction:column;gap:8px;}
.lb-item{display:flex;align-items:center;gap:12px;background:var(--surface2);border-radius:12px;padding:12px 16px;border:1px solid var(--border);}
.lb-item.me{border-color:var(--primary);background:rgba(108,99,255,.08);}
.lb-rank{font-size:1.1rem;font-weight:900;min-width:28px;text-align:center;}
.lb-rank.gold{color:var(--gold);}
.lb-rank.silver{color:#C0C0C0;}
.lb-rank.bronze{color:#CD7F32;}
.lb-avatar{width:36px;height:36px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;}
.lb-info{flex:1;}
.lb-name{font-weight:700;font-size:.9rem;}
.lb-level{font-size:.75rem;color:var(--text2);}
.lb-xp{font-weight:800;color:var(--gold);font-size:.9rem;}

/* AI CHAT */
.ai-chat-container{height:400px;display:flex;flex-direction:column;}
.chat-messages{flex:1;overflow-y:auto;padding:4px 0;margin-bottom:12px;}
.chat-msg{margin-bottom:12px;}
.chat-msg.ai{text-align:left;}
.chat-msg.user{text-align:right;}
.chat-bubble{display:inline-block;padding:10px 14px;border-radius:14px;max-width:85%;font-size:.88rem;line-height:1.6;}
.chat-msg.ai .chat-bubble{background:rgba(108,99,255,.15);border:1px solid var(--border);}
.chat-msg.user .chat-bubble{background:linear-gradient(135deg,var(--primary),#8B80FF);color:#fff;}
.chat-msg .chat-time{font-size:.7rem;color:var(--text2);margin-top:3px;}
.chat-input-row{display:flex;gap:8px;}
.chat-input{flex:1;padding:10px 16px;border-radius:10px;border:1px solid var(--border);background:rgba(255,255,255,.05);color:var(--text);font-size:.88rem;font-family:'Nunito',sans-serif;outline:none;}
.chat-input:focus{border-color:var(--primary);}
.chat-send-btn{padding:10px 18px;border-radius:10px;background:var(--primary);border:none;color:#fff;font-weight:700;cursor:pointer;font-family:'Nunito',sans-serif;transition:all .2s;}
.chat-send-btn:hover{background:#8B80FF;}
.typing-dot{display:inline-block;width:8px;height:8px;border-radius:50%;background:var(--primary);animation:typing .8s infinite;}
.typing-dot:nth-child(2){animation-delay:.15s;}
.typing-dot:nth-child(3){animation-delay:.3s;}
@keyframes typing{0%,80%,100%{transform:scale(1);opacity:.4;}40%{transform:scale(1.2);opacity:1;}}

/* HOME */
.daily-challenge{background:linear-gradient(135deg,rgba(108,99,255,.3),rgba(255,101,132,.2));border-radius:16px;padding:20px;margin-bottom:16px;border:1px solid rgba(108,99,255,.3);}
.challenge-title{font-size:.8rem;text-transform:uppercase;letter-spacing:1px;color:var(--primary);font-weight:800;margin-bottom:6px;}
.challenge-text{font-size:1.1rem;font-weight:700;margin-bottom:12px;}
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:16px;}
.stat-card{background:var(--card);border-radius:12px;padding:14px 10px;text-align:center;border:1px solid var(--border);}
.stat-icon{font-size:1.5rem;margin-bottom:4px;}
.stat-val{font-size:1.3rem;font-weight:900;font-family:'Baloo 2',sans-serif;}
.stat-lbl2{font-size:.72rem;color:var(--text2);}
.continue-btn{width:100%;padding:14px;border-radius:12px;background:linear-gradient(135deg,var(--primary),var(--secondary));border:none;color:#fff;font-size:1rem;font-weight:800;cursor:pointer;font-family:'Nunito',sans-serif;margin-bottom:10px;transition:all .2s;}
.continue-btn:hover{transform:translateY(-2px);box-shadow:0 8px 20px rgba(108,99,255,.4);}
.section-header{font-family:'Baloo 2',sans-serif;font-size:1.1rem;font-weight:700;margin-bottom:12px;color:var(--text2);}

/* LOADING */
.loading{display:flex;gap:6px;justify-content:center;padding:10px;}

/* TOAST */
.toast{position:fixed;bottom:20px;right:20px;background:var(--card);border:1px solid var(--border);border-radius:12px;padding:12px 18px;font-size:.88rem;font-weight:700;z-index:999;transform:translateX(200px);opacity:0;transition:all .3s;max-width:260px;}
.toast.show{transform:translateX(0);opacity:1;}
.toast.success{border-color:var(--accent);color:var(--accent);}
.toast.error{border-color:var(--red);color:var(--red);}
.toast.info{border-color:var(--primary);color:var(--primary);}

/* PROGRESS */
.my-progress-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px;}
.prog-card{background:var(--card);border-radius:14px;padding:16px;border:1px solid var(--border);}
.prog-card-title{font-weight:700;font-size:.9rem;margin-bottom:10px;display:flex;align-items:center;gap:6px;}
.prog-ring{width:70px;height:70px;margin:0 auto 10px;}
.prog-ring svg{transform:rotate(-90deg);}
.prog-ring circle{fill:none;stroke-width:8;}
.prog-ring .bg{stroke:rgba(255,255,255,.1);}
.prog-ring .fill{stroke:var(--primary);stroke-linecap:round;transition:stroke-dashoffset .5s;}
.prog-pct{text-align:center;font-size:1.2rem;font-weight:900;font-family:'Baloo 2',sans-serif;color:var(--primary);}

@media(max-width:600px){
  .stats-grid{grid-template-columns:repeat(2,1fr);}
  .levels-grid{grid-template-columns:repeat(2,1fr);}
  .vocab-grid{grid-template-columns:repeat(2,1fr);}
  .my-progress-grid{grid-template-columns:1fr;}
  .logo{font-size:1.3rem;}
}
</style>
</head>
<body>

<div class="header">
  <div class="logo">🎓 EnglishMaster</div>
  <div class="header-right">
    <div class="xp-bar">⚡ <span id="totalXP">0</span> XP</div>
    <div class="streak">🔥 <span id="streakDays">1</span></div>
    <div class="lang-switch">
      <button class="lang-btn active" onclick="setLang('en')">EN</button>
      <button class="lang-btn" onclick="setLang('ru')">RU</button>
      <button class="lang-btn" onclick="setLang('uz')">UZ</button>
    </div>
  </div>
</div>

<div class="nav">
  <button class="nav-btn active" onclick="showSection('home')" data-i18n="nav_home">🏠 Home</button>
  <button class="nav-btn" onclick="showSection('learn')" data-i18n="nav_learn">📚 Learn</button>
  <button class="nav-btn" onclick="showSection('listening')" data-i18n="nav_listen">🎧 Listening</button>
  <button class="nav-btn" onclick="showSection('reading')" data-i18n="nav_read">📖 Reading</button>
  <button class="nav-btn" onclick="showSection('speaking')" data-i18n="nav_speak">🎤 Speaking</button>
  <button class="nav-btn" onclick="showSection('vocabulary')" data-i18n="nav_vocab">📝 Vocabulary</button>
  <button class="nav-btn" onclick="showSection('leaderboard')" data-i18n="nav_rank">🏆 Ranking</button>
  <button class="nav-btn" onclick="showSection('aichat')" data-i18n="nav_ai">🤖 AI Tutor</button>
  <button class="nav-btn" onclick="showSection('progress')" data-i18n="nav_prog">📊 Progress</button>
</div>

<div class="main">

<!-- HOME -->
<div id="home" class="section active">
  <div class="daily-challenge">
    <div class="challenge-title" data-i18n="daily_challenge">🌟 DAILY CHALLENGE</div>
    <div class="challenge-text" id="dailyChallengeText">What is the past tense of "go"?</div>
    <button class="start-test-btn" style="max-width:200px;padding:10px" onclick="showSection('learn')" data-i18n="start_now">Start Now →</button>
  </div>
  <div class="stats-grid">
    <div class="stat-card"><div class="stat-icon">🔥</div><div class="stat-val" id="homeStreak">1</div><div class="stat-lbl2" data-i18n="streak">Streak</div></div>
    <div class="stat-card"><div class="stat-icon">⚡</div><div class="stat-val" id="homeXP">0</div><div class="stat-lbl2">XP</div></div>
    <div class="stat-card"><div class="stat-icon">✅</div><div class="stat-val" id="homeLessons">0</div><div class="stat-lbl2" data-i18n="lessons">Lessons</div></div>
    <div class="stat-card"><div class="stat-icon">🎯</div><div class="stat-val" id="homeAccuracy">0%</div><div class="stat-lbl2" data-i18n="accuracy">Accuracy</div></div>
  </div>
  <button class="continue-btn" onclick="showSection('learn')" data-i18n="continue_learning">📚 Continue Learning</button>
  <div class="section-header" data-i18n="recent_activity">Recent Activity</div>
  <div id="recentActivity"></div>
</div>

<!-- LEARN -->
<div id="learn" class="section">
  <div id="levelsView">
    <div class="card">
      <div class="card-title">🎯 <span data-i18n="choose_level">Choose Your Level</span></div>
      <div class="levels-grid" id="levelsGrid"></div>
    </div>
  </div>
  <div id="topicsView" style="display:none">
    <div class="lesson-header">
      <button class="back-btn" onclick="backToLevels()">← <span data-i18n="back">Back</span></button>
      <div class="lesson-title" id="currentLevelTitle"></div>
    </div>
    <div class="topics-list" id="topicsList"></div>
  </div>
  <div id="lessonView" style="display:none">
    <div class="lesson-header">
      <button class="back-btn" onclick="backToTopics()">← <span data-i18n="back">Back</span></button>
      <div class="lesson-title" id="lessonTitle"></div>
    </div>
    <div id="lessonContent"></div>
    <button class="start-test-btn" onclick="startTest()" data-i18n="start_test">🎯 Start Test (30 Questions)</button>
  </div>
  <div id="testView" style="display:none">
    <div class="lesson-header">
      <button class="back-btn" onclick="backToLesson()">← <span data-i18n="exit_test">Exit Test</span></button>
      <div class="lesson-title" data-i18n="test_title">📝 Test</div>
    </div>
    <div class="test-header">
      <span class="question-num" id="questionNum">1 / 30</span>
      <span class="question-score" id="questionScore">Score: 0</span>
    </div>
    <div class="test-progress-bar"><div class="test-progress-fill" id="testProgressFill" style="width:3.3%"></div></div>
    <div id="questionContainer"></div>
  </div>
  <div id="resultView" style="display:none"></div>
</div>

<!-- LISTENING -->
<div id="listening" class="section">
  <div class="card">
    <div class="card-title">🎧 <span data-i18n="listening_lessons">Listening Lessons</span></div>
    <div id="listeningContent"></div>
  </div>
</div>

<!-- READING -->
<div id="reading" class="section">
  <div class="card">
    <div class="card-title">📖 <span data-i18n="reading_lessons">Reading Lessons</span></div>
    <div id="readingContent"></div>
  </div>
  <div class="word-popup" id="wordPopup"></div>
</div>

<!-- SPEAKING -->
<div id="speaking" class="section">
  <div class="card">
    <div class="card-title">🎤 <span data-i18n="speaking_practice">Speaking Practice</span></div>
    <div id="speakingContent"></div>
  </div>
</div>

<!-- VOCABULARY -->
<div id="vocabulary" class="section">
  <div class="card">
    <div class="card-title">📝 <span data-i18n="vocabulary">Vocabulary</span></div>
    <input class="vocab-search" id="vocabSearch" placeholder="Search words..." oninput="filterVocab()" data-i18n-placeholder="search_words">
    <div class="vocab-filter" id="vocabFilter"></div>
    <div class="vocab-grid" id="vocabGrid"></div>
  </div>
</div>

<!-- LEADERBOARD -->
<div id="leaderboard" class="section">
  <div class="card">
    <div class="card-title">🏆 <span data-i18n="leaderboard">Leaderboard</span></div>
    <div class="lb-list" id="lbList"></div>
  </div>
</div>

<!-- AI CHAT -->
<div id="aichat" class="section">
  <div class="card">
    <div class="card-title">🤖 <span data-i18n="ai_tutor">AI English Tutor</span></div>
    <div class="ai-chat-container">
      <div class="chat-messages" id="chatMessages"></div>
      <div class="chat-input-row">
        <input class="chat-input" id="chatInput" placeholder="Ask me anything about English..." data-i18n-placeholder="ask_english" onkeydown="if(event.key==='Enter')sendChat()">
        <button class="chat-send-btn" onclick="sendChat()">Send</button>
      </div>
    </div>
  </div>
</div>

<!-- PROGRESS -->
<div id="progress" class="section">
  <div class="card">
    <div class="card-title">📊 <span data-i18n="my_progress">My Progress</span></div>
    <div class="my-progress-grid" id="progressGrid"></div>
  </div>
</div>

</div>

<div class="toast" id="toast"></div>

<script>
// ==================== STATE ====================
const state = {
  lang: 'en',
  xp: parseInt(localStorage.getItem('xp')||'0'),
  streak: parseInt(localStorage.getItem('streak')||'1'),
  lessonsCompleted: parseInt(localStorage.getItem('lessons')||'0'),
  totalAnswers: parseInt(localStorage.getItem('totalAnswers')||'0'),
  correctAnswers: parseInt(localStorage.getItem('correctAnswers')||'0'),
  completedTopics: JSON.parse(localStorage.getItem('completedTopics')||'[]'),
  scores: JSON.parse(localStorage.getItem('scores')||'{}'),
  currentLevel: null,
  currentTopic: null,
  testQuestions: [],
  currentQ: 0,
  testScore: 0,
  testCorrect: 0,
  usedQuestions: {},
  speakConvHistory: [],
  currentSpeakPromptIdx: 0,
  isRecording: false,
  recognition: null,
  speechSynth: window.speechSynthesis,
  currentAudio: null,
  audioPlaying: false,
  currentReadingPassage: null,
  vocabFilter: 'all'
};

// ==================== I18N ====================
const T = {
  en: {
    nav_home:'🏠 Home', nav_learn:'📚 Learn', nav_listen:'🎧 Listening', nav_read:'📖 Reading',
    nav_speak:'🎤 Speaking', nav_vocab:'📝 Vocabulary', nav_rank:'🏆 Ranking', nav_ai:'🤖 AI Tutor', nav_prog:'📊 Progress',
    daily_challenge:'🌟 DAILY CHALLENGE', start_now:'Start Now →', streak:'Streak', lessons:'Lessons', accuracy:'Accuracy',
    continue_learning:'📚 Continue Learning', recent_activity:'Recent Activity', choose_level:'Choose Your Level',
    back:'Back', start_test:'🎯 Start Test (30 Questions)', test_title:'📝 Test', exit_test:'Exit Test',
    listening_lessons:'Listening Lessons', reading_lessons:'Reading Lessons', speaking_practice:'Speaking Practice',
    vocabulary:'Vocabulary', leaderboard:'Leaderboard', ai_tutor:'AI English Tutor', my_progress:'My Progress',
    search_words:'Search words...', ask_english:'Ask me anything about English...',
    correct:'✅ Correct!', wrong:'❌ Wrong!', next:'Next Question →', finish:'Finish Test',
    your_score:'Your Score', excellent:'Excellent! 🌟', great:'Great! 👍', good:'Good Job! 😊', keep_trying:'Keep Trying! 💪',
    retry:'🔄 Retry', home:'🏠 Home', ai_analysis:'AI Analysis',
    tap_flip:'Tap to flip', level_locked:'Complete previous level first',
    speak_prompt_label:'AI says:', speak_your_turn:'Your turn to respond!', start_speaking:'🎤 Start Speaking',
    stop_speaking:'⏹ Stop', ai_evaluating:'AI is evaluating...', pronunciation:'Pronunciation',
    fluency:'Fluency', accuracy2:'Accuracy',
    listening_q:'Listening Questions', show_transcript:'Show Transcript', hide_transcript:'Hide Transcript',
    read_passage:'Reading Passage', read_questions:'Reading Questions',
    xp_earned:'XP Earned', questions_correct:'Correct Answers', time_spent:'Time Spent',
  },
  ru: {
    nav_home:'🏠 Главная', nav_learn:'📚 Учёба', nav_listen:'🎧 Аудирование', nav_read:'📖 Чтение',
    nav_speak:'🎤 Говорение', nav_vocab:'📝 Словарь', nav_rank:'🏆 Рейтинг', nav_ai:'🤖 ИИ Репетитор', nav_prog:'📊 Прогресс',
    daily_challenge:'🌟 ЗАДАНИЕ ДНЯ', start_now:'Начать →', streak:'Серия', lessons:'Уроки', accuracy:'Точность',
    continue_learning:'📚 Продолжить обучение', recent_activity:'Недавняя активность', choose_level:'Выберите уровень',
    back:'Назад', start_test:'🎯 Начать тест (30 вопросов)', test_title:'📝 Тест', exit_test:'Выйти из теста',
    listening_lessons:'Уроки аудирования', reading_lessons:'Уроки чтения', speaking_practice:'Практика говорения',
    vocabulary:'Словарь', leaderboard:'Рейтинг', ai_tutor:'ИИ Репетитор по английскому', my_progress:'Мой прогресс',
    search_words:'Поиск слов...', ask_english:'Спросите меня об английском...',
    correct:'✅ Правильно!', wrong:'❌ Неправильно!', next:'Следующий вопрос →', finish:'Завершить тест',
    your_score:'Ваш результат', excellent:'Отлично! 🌟', great:'Хорошо! 👍', good:'Неплохо! 😊', keep_trying:'Продолжайте! 💪',
    retry:'🔄 Повторить', home:'🏠 Главная', ai_analysis:'Анализ ИИ',
    tap_flip:'Нажмите для перевода', level_locked:'Сначала завершите предыдущий уровень',
    speak_prompt_label:'ИИ говорит:', speak_your_turn:'Ваша очередь отвечать!', start_speaking:'🎤 Начать говорить',
    stop_speaking:'⏹ Остановить', ai_evaluating:'ИИ оценивает...', pronunciation:'Произношение',
    fluency:'Беглость', accuracy2:'Точность',
    listening_q:'Вопросы по аудированию', show_transcript:'Показать текст', hide_transcript:'Скрыть текст',
    read_passage:'Текст для чтения', read_questions:'Вопросы по тексту',
    xp_earned:'Заработано XP', questions_correct:'Правильных ответов', time_spent:'Затрачено времени',
  },
  uz: {
    nav_home:'🏠 Bosh sahifa', nav_learn:'📚 O\'rganish', nav_listen:'🎧 Tinglash', nav_read:'📖 O\'qish',
    nav_speak:'🎤 Gapirish', nav_vocab:'📝 Lug\'at', nav_rank:'🏆 Reyting', nav_ai:'🤖 AI O\'qituvchi', nav_prog:'📊 Natijalar',
    daily_challenge:'🌟 KUNLIK TOPSHIRIQ', start_now:'Boshlash →', streak:'Seriya', lessons:'Darslar', accuracy:'Aniqlik',
    continue_learning:'📚 O\'qishni davom ettirish', recent_activity:'So\'nggi faollik', choose_level:'Darajangizni tanlang',
    back:'Orqaga', start_test:'🎯 Testni boshlash (30 savol)', test_title:'📝 Test', exit_test:'Testdan chiqish',
    listening_lessons:'Tinglash darslari', reading_lessons:'O\'qish darslari', speaking_practice:'Gapirish amaliyoti',
    vocabulary:'Lug\'at', leaderboard:'Reyting', ai_tutor:'AI Ingliz tili o\'qituvchisi', my_progress:'Mening natijalarim',
    search_words:'So\'z qidirish...', ask_english:'Ingliz tili haqida savol bering...',
    correct:'✅ To\'g\'ri!', wrong:'❌ Noto\'g\'ri!', next:'Keyingi savol →', finish:'Testni tugatish',
    your_score:'Sizning natijangiz', excellent:'A\'lo! 🌟', great:'Yaxshi! 👍', good:'Qoniqarli! 😊', keep_trying:'Davom eting! 💪',
    retry:'🔄 Qayta urinish', home:'🏠 Bosh sahifa', ai_analysis:'AI tahlili',
    tap_flip:'Tarjimani ko\'rish uchun bosing', level_locked:'Avval oldingi darajani bajaring',
    speak_prompt_label:'AI aytadi:', speak_your_turn:'Siz javob bering!', start_speaking:'🎤 Gapira boshlash',
    stop_speaking:'⏹ To\'xtatish', ai_evaluating:'AI baholayapti...', pronunciation:'Talaffuz',
    fluency:'Ravonlik', accuracy2:'Aniqlik',
    listening_q:'Tinglash savollari', show_transcript:'Matnni ko\'rsatish', hide_transcript:'Matnni yashirish',
    read_passage:'O\'qish matni', read_questions:'Matn bo\'yicha savollar',
    xp_earned:'Olingan XP', questions_correct:'To\'g\'ri javoblar', time_spent:'Sarflangan vaqt',
  }
};

function t(key){ return (T[state.lang]||T.en)[key] || key; }

function setLang(l){
  state.lang = l;
  document.querySelectorAll('.lang-btn').forEach(b=>b.classList.toggle('active',b.textContent===l.toUpperCase()));
  applyTranslations();
  renderCurrentSection();
}

function applyTranslations(){
  document.querySelectorAll('[data-i18n]').forEach(el=>{
    const k=el.getAttribute('data-i18n');
    el.textContent=t(k);
  });
  document.querySelectorAll('[data-i18n-placeholder]').forEach(el=>{
    const k=el.getAttribute('data-i18n-placeholder');
    el.placeholder=t(k);
  });
}

// ==================== CURRICULUM DATA ====================
const LEVELS = [
  {id:'a1',name:'A1 - Beginner',emoji:'🌱',color:'#43E97B',desc:'Basic phrases & vocabulary'},
  {id:'a2',name:'A2 - Elementary',emoji:'🌿',color:'#38F9D7',desc:'Simple conversations'},
  {id:'b1',name:'B1 - Intermediate',emoji:'🌳',color:'#6C63FF',desc:'Everyday English'},
  {id:'b2',name:'B2 - Upper-Intermediate',emoji:'🌲',color:'#FF9F43',desc:'Complex topics'},
  {id:'c1',name:'C1 - Advanced',emoji:'🏔️',color:'#FF6584',desc:'Professional English'},
  {id:'c2',name:'C2 - Mastery',emoji:'🦅',color:'#FFD700',desc:'Native-like fluency'},
];

const TOPICS = {
  a1: [
    {id:'greetings',icon:'👋',title:'Greetings & Introductions',sub:'Hello, Hi, Nice to meet you'},
    {id:'numbers',icon:'🔢',title:'Numbers & Counting',sub:'1-100, ordinal numbers'},
    {id:'colors',icon:'🎨',title:'Colors & Shapes',sub:'Red, blue, circle, square'},
    {id:'family',icon:'👨‍👩‍👧‍👦',title:'Family Members',sub:'Mother, father, sister, brother'},
    {id:'body',icon:'🫀',title:'Body Parts',sub:'Head, arms, legs, eyes'},
    {id:'food_a1',icon:'🍎',title:'Food & Drinks',sub:'Apple, water, bread, milk'},
    {id:'days',icon:'📅',title:'Days & Months',sub:'Monday, January, seasons'},
    {id:'classroom',icon:'🏫',title:'Classroom Objects',sub:'Pen, book, desk, teacher'},
    {id:'animals',icon:'🐶',title:'Animals',sub:'Cat, dog, bird, fish'},
    {id:'verb_be',icon:'📌',title:'Verb TO BE',sub:'I am, you are, he is'},
    {id:'have_got',icon:'🤲',title:'Have Got',sub:'I have got, she has got'},
    {id:'articles',icon:'📎',title:'Articles: A, An, The',sub:'Definite and indefinite articles'},
  ],
  a2: [
    {id:'present_simple',icon:'⏰',title:'Present Simple',sub:'I work, she works every day'},
    {id:'past_simple',icon:'⏮️',title:'Past Simple',sub:'I went, she saw, they did'},
    {id:'present_cont',icon:'▶️',title:'Present Continuous',sub:'I am working right now'},
    {id:'questions',icon:'❓',title:'Question Words',sub:'What, where, when, why, how'},
    {id:'prepositions',icon:'📍',title:'Prepositions of Place',sub:'In, on, under, next to'},
    {id:'adjectives',icon:'✨',title:'Adjectives & Comparatives',sub:'Bigger, smaller, more beautiful'},
    {id:'shopping',icon:'🛒',title:'Shopping & Money',sub:'Price, buy, sell, expensive'},
    {id:'transport',icon:'🚌',title:'Transport & Travel',sub:'Bus, train, plane, ticket'},
    {id:'weather',icon:'☀️',title:'Weather & Climate',sub:'Sunny, rainy, cold, hot'},
    {id:'hobbies',icon:'🎮',title:'Hobbies & Free Time',sub:'Reading, swimming, cooking'},
    {id:'health',icon:'💊',title:'Health & Body',sub:'Doctor, sick, medicine, pain'},
    {id:'adverbs_freq',icon:'🔁',title:'Adverbs of Frequency',sub:'Always, usually, sometimes, never'},
  ],
  b1: [
    {id:'present_perfect',icon:'✅',title:'Present Perfect',sub:'I have seen, she has done'},
    {id:'past_cont',icon:'⏪',title:'Past Continuous',sub:'I was sleeping when...'},
    {id:'future',icon:'🔮',title:'Future: Will & Going To',sub:'I will go, I am going to buy'},
    {id:'modal_verbs',icon:'💭',title:'Modal Verbs',sub:'Can, could, should, must, might'},
    {id:'passive',icon:'🔄',title:'Passive Voice',sub:'The book was written by...'},
    {id:'conditionals_1',icon:'🌡️',title:'First Conditional',sub:'If it rains, I will stay home'},
    {id:'conditionals_2',icon:'💫',title:'Second Conditional',sub:'If I were rich, I would travel'},
    {id:'relative',icon:'🔗',title:'Relative Clauses',sub:'The man who lives next door'},
    {id:'reported',icon:'💬',title:'Reported Speech',sub:'She said that she was tired'},
    {id:'work',icon:'💼',title:'Work & Career',sub:'Job interview, CV, promotion'},
    {id:'environment',icon:'🌍',title:'Environment',sub:'Climate change, pollution, recycling'},
    {id:'technology',icon:'💻',title:'Technology',sub:'Internet, smartphone, social media'},
  ],
  b2: [
    {id:'perfect_cont',icon:'⌛',title:'Perfect Continuous',sub:'I have been working for 3 hours'},
    {id:'inversion',icon:'🔀',title:'Inversion & Emphasis',sub:'Never have I seen such a thing'},
    {id:'cond_3',icon:'😔',title:'Third Conditional',sub:'If I had known, I would have...'},
    {id:'mixed_cond',icon:'🎭',title:'Mixed Conditionals',sub:'If I had studied, I would be...'},
    {id:'gerund_inf',icon:'🎯',title:'Gerunds & Infinitives',sub:'I enjoy swimming, I want to go'},
    {id:'articles_adv',icon:'📌',title:'Advanced Articles',sub:'Zero article, generic nouns'},
    {id:'business',icon:'📊',title:'Business English',sub:'Meetings, negotiations, reports'},
    {id:'academic',icon:'🎓',title:'Academic Writing',sub:'Essays, thesis, argumentation'},
    {id:'idioms',icon:'🗣️',title:'Idioms & Phrasal Verbs',sub:'Break down, give up, take off'},
    {id:'collocation',icon:'🤝',title:'Collocations',sub:'Make a decision, do homework'},
  ],
  b2_extra: [],
  c1: [
    {id:'discourse',icon:'📝',title:'Discourse Markers',sub:'Furthermore, however, consequently'},
    {id:'nominalization',icon:'🔠',title:'Nominalization',sub:'The development of, the introduction of'},
    {id:'cleft',icon:'✂️',title:'Cleft Sentences',sub:'It was John who called, what I need is...'},
    {id:'hedging',icon:'🌫️',title:'Hedging Language',sub:'It seems, it appears, arguably'},
    {id:'register',icon:'🎩',title:'Register & Style',sub:'Formal vs informal English'},
    {id:'idiomatic_adv',icon:'🦊',title:'Advanced Idioms',sub:'Bite the bullet, sit on the fence'},
    {id:'lit_english',icon:'📚',title:'Literary English',sub:'Metaphor, simile, alliteration'},
  ],
  c2: [
    {id:'nuance',icon:'🎨',title:'Nuance & Connotation',sub:'Subtle differences in meaning'},
    {id:'rhetoric',icon:'🎙️',title:'Rhetorical Devices',sub:'Persuasion, argument, debate'},
    {id:'etymology',icon:'🔬',title:'Word Etymology',sub:'Latin, Greek, French roots'},
    {id:'dialect',icon:'🌐',title:'Dialects & Varieties',sub:'British, American, Australian English'},
    {id:'proverbs',icon:'💡',title:'Proverbs & Sayings',sub:'Actions speak louder than words'},
  ]
};

// ==================== LESSON CONTENT ====================
const LESSON_CONTENT = {
  greetings: `
    <h3>👋 Greetings & Introductions</h3>
    <p>Greetings are the first thing you learn in any language. In English, there are formal and informal ways to greet people.</p>
    <h3>Formal Greetings</h3>
    <div class="example"><strong>Good morning</strong> - Used from sunrise until noon (12:00 PM)</div>
    <div class="example"><strong>Good afternoon</strong> - Used from noon until evening (6:00 PM)</div>
    <div class="example"><strong>Good evening</strong> - Used from evening until bedtime</div>
    <div class="example"><strong>How do you do?</strong> - Very formal, used when meeting someone for the first time</div>
    <h3>Informal Greetings</h3>
    <div class="example"><strong>Hi / Hey</strong> - Casual greeting for friends and peers</div>
    <div class="example"><strong>What's up?</strong> - Very casual American English</div>
    <div class="example"><strong>How are you?</strong> - Common greeting asking about wellbeing</div>
    <div class="example"><strong>How's it going?</strong> - Informal way to ask how someone is</div>
    <h3>Introducing Yourself</h3>
    <div class="example"><strong>My name is...</strong> / <strong>I'm...</strong> - Stating your name</div>
    <div class="example"><strong>Nice to meet you</strong> / <strong>Pleased to meet you</strong> - After introduction</div>
    <div class="example"><strong>I'm from...</strong> - Stating your country/city</div>
    <div class="example"><strong>I work as a...</strong> / <strong>I'm a student</strong> - Your occupation</div>
    <h3>Goodbyes</h3>
    <div class="example"><strong>Goodbye / Bye</strong> - Standard farewell</div>
    <div class="example"><strong>See you later / See you soon</strong> - When you'll meet again</div>
    <div class="example"><strong>Take care</strong> - Wishing someone well</div>
    <div class="example"><strong>Have a nice day!</strong> - Common farewell</div>
    <h3>Full Conversation Example:</h3>
    <div class="example">
      A: <strong>Good morning! My name is Sarah. Nice to meet you.</strong><br>
      B: <strong>Good morning, Sarah! I'm John. Nice to meet you too.</strong><br>
      A: <strong>Where are you from, John?</strong><br>
      B: <strong>I'm from London. And you?</strong><br>
      A: <strong>I'm from New York. What do you do?</strong><br>
      B: <strong>I'm an engineer. See you around!</strong>
    </div>
    <h3>Key Vocabulary:</h3>
    <table class="vocab-table">
      <tr><th>Word</th><th>Meaning</th><th>Example</th></tr>
      <tr><td>greet</td><td>to say hello to someone</td><td>I greeted my teacher.</td></tr>
      <tr><td>introduce</td><td>to tell someone your name</td><td>Let me introduce myself.</td></tr>
      <tr><td>farewell</td><td>goodbye</td><td>We said our farewells.</td></tr>
      <tr><td>acquaintance</td><td>someone you know slightly</td><td>He's just an acquaintance.</td></tr>
    </table>
  `,
  present_simple: `
    <h3>⏰ Present Simple Tense</h3>
    <p>The Present Simple is used for habits, routines, facts, and general truths. It is one of the most important tenses in English.</p>
    <h3>Formation:</h3>
    <div class="example"><strong>Positive:</strong> Subject + base verb (+ -s/-es for he/she/it)<br>I work, You work, He/She/It work<strong>s</strong>, We work, They work</div>
    <div class="example"><strong>Negative:</strong> Subject + do/does + not + base verb<br>I don't work, She doesn't work, They don't work</div>
    <div class="example"><strong>Question:</strong> Do/Does + subject + base verb?<br>Do you work? Does she work? Do they work?</div>
    <h3>Uses:</h3>
    <ul>
      <li><strong>Habits/Routines:</strong> She drinks coffee every morning.</li>
      <li><strong>Facts/General truths:</strong> The sun rises in the east.</li>
      <li><strong>Scheduled events:</strong> The train leaves at 9 AM.</li>
      <li><strong>Instructions:</strong> You mix the flour with eggs.</li>
    </ul>
    <h3>Spelling Rules (3rd person singular):</h3>
    <div class="example">Most verbs: add -s → work → works, play → plays<br>
    Verbs ending in -s, -sh, -ch, -x, -z: add -es → wash → washes, watch → watches<br>
    Verbs ending in consonant + y: change y to i, add -es → study → studies<br>
    Irregular: have → has, be → is, go → goes, do → does</div>
    <h3>Time expressions used with Present Simple:</h3>
    <div class="example">always, usually, often, sometimes, rarely, never, every day/week/month, on Mondays, once a week</div>
    <table class="vocab-table">
      <tr><th>Adverb</th><th>Frequency</th><th>Example</th></tr>
      <tr><td>always</td><td>100%</td><td>She always wakes up early.</td></tr>
      <tr><td>usually</td><td>80%</td><td>I usually have breakfast.</td></tr>
      <tr><td>often</td><td>60%</td><td>They often go to the gym.</td></tr>
      <tr><td>sometimes</td><td>40%</td><td>He sometimes watches TV.</td></tr>
      <tr><td>rarely</td><td>20%</td><td>We rarely eat fast food.</td></tr>
      <tr><td>never</td><td>0%</td><td>I never smoke.</td></tr>
    </table>
  `,
  modal_verbs: `
    <h3>💭 Modal Verbs</h3>
    <p>Modal verbs are special auxiliary verbs that express ability, possibility, permission, obligation, and advice. They are NEVER used alone - they always come before a main verb.</p>
    <h3>Key Modal Verbs:</h3>
    <div class="example"><strong>CAN</strong> - Ability/Permission<br>I can swim. / Can I open the window?<br><em>Negative:</em> I can't (cannot) drive.</div>
    <div class="example"><strong>COULD</strong> - Past ability / Polite request / Possibility<br>I could run fast when I was young.<br>Could you help me, please?<br>It could rain tomorrow.</div>
    <div class="example"><strong>SHOULD</strong> - Advice/Recommendation<br>You should see a doctor. / You shouldn't eat so much sugar.<br>Should I call him?</div>
    <div class="example"><strong>MUST</strong> - Strong obligation / Logical deduction<br>You must wear a seatbelt. (obligation)<br>She must be tired. (deduction)</div>
    <div class="example"><strong>HAVE TO</strong> - External obligation<br>I have to work on Saturdays. (my boss says so)<br>She doesn't have to come if she's busy.</div>
    <div class="example"><strong>MIGHT / MAY</strong> - Possibility<br>It might snow tonight. (less certain)<br>May I use your phone? (formal permission)</div>
    <div class="example"><strong>WOULD</strong> - Conditional / Polite request<br>I would love to visit Paris.<br>Would you like some tea?</div>
    <div class="example"><strong>NEEDN'T</strong> - No necessity<br>You needn't worry. / You don't need to hurry.</div>
    <h3>Grammar Rules:</h3>
    <ul>
      <li>Modal verbs do NOT change form (no -s for he/she/it)</li>
      <li>Modal verbs are followed by the BASE FORM of the verb</li>
      <li>Modal verbs do NOT use "do" in negatives/questions</li>
      <li>Modal verbs have no infinitive or past participle</li>
    </ul>
    <table class="vocab-table">
      <tr><th>Modal</th><th>Use</th><th>Example</th></tr>
      <tr><td>can</td><td>ability</td><td>She can speak 3 languages.</td></tr>
      <tr><td>should</td><td>advice</td><td>You should exercise more.</td></tr>
      <tr><td>must</td><td>obligation</td><td>We must respect others.</td></tr>
      <tr><td>might</td><td>possibility</td><td>It might be true.</td></tr>
      <tr><td>would</td><td>conditional</td><td>I would go if I could.</td></tr>
    </table>
  `,
};

// ==================== QUESTION BANK ====================
function generateQuestions(topicId, level) {
  const bank = QUESTION_BANKS[topicId] || QUESTION_BANKS['general_'+level] || QUESTION_BANKS['general_a1'];
  const used = state.usedQuestions[topicId] || [];
  let available = bank.filter((_,i)=>!used.includes(i));
  if(available.length < 30){
    state.usedQuestions[topicId] = [];
    available = [...bank];
  }
  const shuffled = shuffle(available);
  const selected = shuffled.slice(0,Math.min(30,shuffled.length));
  // pad if needed
  while(selected.length<30) selected.push(...shuffled.slice(0, 30-selected.length));
  const usedIdxs = selected.map(q=>bank.indexOf(q)).filter(i=>i>=0);
  state.usedQuestions[topicId] = [...(state.usedQuestions[topicId]||[]), ...usedIdxs];
  return selected.slice(0,30);
}

const QUESTION_BANKS = {
  greetings: [
    {type:'mc',q:'Which greeting is used in the morning?',opts:['Good evening','Good morning','Good night','Good afternoon'],a:1},
    {type:'mc',q:'What do you say when you meet someone for the first time?',opts:['Goodbye!','Nice to meet you!','See you later!','Good night!'],a:1},
    {type:'fill',q:'Complete: "My ___ is John."',a:'name',hint:'Your identity word'},
    {type:'mc',q:'Which is a FORMAL greeting?',opts:['Hey!','What\'s up?','How do you do?','Yo!'],a:2},
    {type:'mc',q:'"How are you?" - What is the best response?',opts:['My name is Tom.','I\'m fine, thank you.','Good morning!','See you later.'],a:1},
    {type:'fill',q:'Complete: "I\'m ___ London." (saying where you are from)',a:'from',hint:'Preposition of origin'},
    {type:'mc',q:'What does "farewell" mean?',opts:['Hello','Goodbye','Thank you','Please'],a:1},
    {type:'mc',q:'Which time does "Good evening" apply to?',opts:['6 AM - 12 PM','12 PM - 6 PM','After 6 PM','All day'],a:2},
    {type:'mc',q:'"Nice to meet you" is said when...',opts:['You leave a party','You meet someone for the first time','You are angry','You are hungry'],a:1},
    {type:'fill',q:'Complete: "___ care!" (a friendly farewell)',a:'Take',hint:'Means to stay safe'},
    {type:'mc',q:'Which is an INFORMAL greeting?',opts:['Good morning','How do you do?','Hey, what\'s up?','Good day, sir'],a:2},
    {type:'mc',q:'How do you say goodbye informally?',opts:['Good evening','Farewell','See you later','How do you do'],a:2},
    {type:'fill',q:'Complete: "I ___ a teacher." (using verb "to be")',a:'am',hint:'1st person singular of "to be"'},
    {type:'mc',q:'What does "pleased to meet you" mean?',opts:['I am angry to meet you','I am happy to meet you','I am bored to meet you','I am scared'],a:1},
    {type:'mc',q:'Which sentence introduces yourself correctly?',opts:['I am from happy.','My name is Sarah.','Good morning my name.','Meet nice you to.'],a:1},
    {type:'mc',q:'"What do you do?" means:',opts:['What are you eating?','What is your job?','Where are you going?','How old are you?'],a:1},
    {type:'fill',q:'Complete: "___ do you do?" (formal greeting)',a:'How',hint:'Question word asking manner'},
    {type:'mc',q:'In a formal letter you write:',opts:['Hey dude,','What\'s up,','Dear Mr. Smith,','Yo,'],a:2},
    {type:'mc',q:'Which phrase means "I hope we meet again"?',opts:['Never see you','See you soon','Goodbye forever','Good riddance'],a:1},
    {type:'fill',q:'Complete: "Have a ___ day!" (wishing well)',a:'nice',hint:'Synonym for good/pleasant'},
    {type:'mc',q:'After a meeting you say...',opts:['Hello again','Nice to meet you','It was nice meeting you','Good morning'],a:2},
    {type:'mc',q:'Which is NOT a greeting?',opts:['Hi there','Good afternoon','Thank you very much','Morning!'],a:2},
    {type:'mc',q:'"I\'m from Tashkent" tells people about your...',opts:['Age','Name','Origin','Hobby'],a:2},
    {type:'fill',q:'Complete: "Let me ___ myself. I\'m Alex."',a:'introduce',hint:'Verb meaning to present yourself'},
    {type:'mc',q:'How do you politely ask someone\'s name?',opts:['What name?','Tell name!','May I ask your name?','Name please now.'],a:2},
    {type:'mc',q:'"Good night" is used when...',opts:['You wake up','You have breakfast','You go to sleep','You go to work'],a:2},
    {type:'fill',q:'Complete: "___ to meet you!" (short friendly phrase)',a:'Nice',hint:'Synonym of pleasant'},
    {type:'mc',q:'In British English "cheerio" means...',opts:['Hello','Thank you','Goodbye','Please'],a:2},
    {type:'mc',q:'Which is the correct response to "How are you?"',opts:['I am John.','I am from France.','I am doing well, thanks.','I am tall.'],a:2},
    {type:'mc',q:'What does "acquaintance" mean?',opts:['A close friend','Someone you know slightly','A family member','A teacher'],a:1},
  ],
  present_simple: [
    {type:'mc',q:'Choose the correct form: "She ___ to school every day."',opts:['go','goes','going','gone'],a:1},
    {type:'mc',q:'Which sentence is in Present Simple?',opts:['I am eating now.','She went yesterday.','He works at a bank.','They are playing.'],a:2},
    {type:'fill',q:'She ___ (study) English every day.',a:'studies',hint:'3rd person, y→ies'},
    {type:'mc',q:'"Do you like coffee?" - Correct negative answer:',opts:['No, I likes not.','No, I don\'t like.','No, I am not liking.','No, I not like.'],a:1},
    {type:'mc',q:'He ___ TV every evening.',opts:['watch','watches','watching','watched'],a:1},
    {type:'fill',q:'The sun ___ (rise) in the east.',a:'rises',hint:'3rd person + s'},
    {type:'mc',q:'Which adverb NEVER goes with Present Simple?',opts:['always','usually','yesterday','sometimes'],a:2},
    {type:'mc',q:'"___ he speak French?" (question form)',opts:['Do','Does','Is','Are'],a:1},
    {type:'fill',q:'I ___ (not/eat) meat. I am vegetarian.',a:"don't eat",hint:'Negative form'},
    {type:'mc',q:'Which is a fact expressed in Present Simple?',opts:['Water is boiling now.','Water boiled yesterday.','Water boils at 100°C.','Water was boiling.'],a:2},
    {type:'mc',q:'"fly" → 3rd person singular is:',opts:['flys','flies','flyies','flyes'],a:1},
    {type:'mc',q:'"They ___ not work on Sundays."',opts:['do','does','is','are'],a:0},
    {type:'fill',q:'My father ___ (have) a blue car.',a:'has',hint:'Irregular 3rd person'},
    {type:'mc',q:'When do we use Present Simple?',opts:['For actions happening now','For past events','For habitual actions','For future plans only'],a:2},
    {type:'mc',q:'"Does she ___ English?" (correct infinitive)',opts:['speaks','speaking','speak','spoken'],a:2},
    {type:'fill',q:'He ___ (teach) mathematics at a university.',a:'teaches',hint:'Add -es after ch'},
    {type:'mc',q:'Choose the correct sentence:',opts:['She don\'t like pizza.','She doesn\'t likes pizza.','She doesn\'t like pizza.','She not like pizza.'],a:2},
    {type:'mc',q:'Which time expression fits Present Simple?',opts:['right now','at this moment','every morning','yesterday'],a:2},
    {type:'fill',q:'Water ___ (freeze) at 0 degrees Celsius.',a:'freezes',hint:'Scientific fact, 3rd person'},
    {type:'mc',q:'"We ___ coffee every morning." (correct form)',opts:['drinks','drinking','drink','drank'],a:2},
    {type:'mc',q:'The train ___ at 8:30 AM every day.',opts:['is leaving','leave','leaves','left'],a:2},
    {type:'fill',q:'___ you speak any foreign languages?',a:'Do',hint:'Question auxiliary for I/you/we/they'},
    {type:'mc',q:'"Go" → 3rd person singular is:',opts:['gos','goes','goies','go'],a:1},
    {type:'mc',q:'Which sentence is WRONG?',opts:['She works hard.','He doesn\'t smoke.','They eats lunch.','Do you like music?'],a:2},
    {type:'fill',q:'My cat ___ (sleep) 14 hours a day.',a:'sleeps',hint:'Regular verb + s'},
    {type:'mc',q:'"Wash" → 3rd person singular is:',opts:['washs','wash','washes','washies'],a:2},
    {type:'mc',q:'Which question is correct?',opts:['Does he works here?','Do he work here?','Does he work here?','Is he work here?'],a:2},
    {type:'fill',q:'She ___ (not/watch) horror films.',a:"doesn't watch",hint:'3rd person negative'},
    {type:'mc',q:'He always ___ his homework before dinner.',opts:['do','does','doing','did'],a:1},
    {type:'mc',q:'Which is a schedule/timetable example?',opts:['She is cooking now.','The film starts at 7 PM.','I cooked yesterday.','They were sleeping.'],a:1},
  ],
  modal_verbs: [
    {type:'mc',q:'"You ___ wear a seatbelt." (strong obligation)',opts:['might','should','must','could'],a:2},
    {type:'fill',q:'___ you help me with this? (polite request)',a:'Could',hint:'Polite form of can'},
    {type:'mc',q:'Which modal expresses ABILITY?',opts:['must','can','should','might'],a:1},
    {type:'mc',q:'"She ___ be at home — her car is here." (deduction)',opts:['should','could','must','might'],a:2},
    {type:'fill',q:'You ___ (not/need) to worry. Everything is fine.',a:"needn't",hint:'No necessity negative'},
    {type:'mc',q:'"___ I open the window?" (asking permission)',opts:['Must','Should','May','Would'],a:2},
    {type:'mc',q:'He ___ run fast when he was young. (past ability)',opts:['can','must','could','should'],a:2},
    {type:'mc',q:'Modal verbs are followed by...',opts:['infinitive with to','base form (infinitive)','past participle','-ing form'],a:1},
    {type:'fill',q:'It ___ rain tomorrow — the sky looks dark.',a:'might',hint:'Possibility, less certain'},
    {type:'mc',q:'"You ___ smoke here." (prohibition)',opts:['needn\'t','should','mustn\'t','might not'],a:2},
    {type:'mc',q:'Which sentence is grammatically CORRECT?',opts:['She musts go.','He can speaks French.','We should leave now.','They mights come.'],a:2},
    {type:'mc',q:'"___ you like some tea?" (polite offer)',opts:['Could','Shall','Would','Should'],a:2},
    {type:'fill',q:'I ___ to submit my report by Friday. (external obligation)',a:'have',hint:'have ___ to'},
    {type:'mc',q:'What is the difference between MUST and HAVE TO?',opts:['No difference','Must = internal, Have to = external obligation','Must = external, Have to = internal','Must = past, Have to = present'],a:1},
    {type:'mc',q:'"She ___ be tired after such a long journey." (logical deduction)',opts:['can','should','must','will'],a:2},
    {type:'fill',q:'"___ I use your phone?" (asking permission formally)',a:'May',hint:'Formal modal for permission'},
    {type:'mc',q:'Which means "it is possible"?',opts:['must','should','might','needn\'t'],a:2},
    {type:'mc',q:'"You ___ exercise more." (advice)',opts:['must','should','can','would'],a:1},
    {type:'fill',q:'___ you swim? (asking about ability)',a:'Can',hint:'Ability question'},
    {type:'mc',q:'"I ___ go to work yesterday because I was ill."',opts:['couldn\'t','mustn\'t','shouldn\'t','needn\'t'],a:0},
    {type:'mc',q:'Choose the CORRECT sentence:',opts:['You must to leave now.','He should goes home.','She can drive a truck.','They might to arrive.'],a:2},
    {type:'fill',q:'You ___ (not/park) here. It\'s illegal.',a:"mustn't",hint:'Strong prohibition'},
    {type:'mc',q:'"Shall we go?" is used for...',opts:['Obligation','Suggestions/offers','Past ability','Deduction'],a:1},
    {type:'mc',q:'Which is NOT a modal verb?',opts:['can','need','want','should'],a:2},
    {type:'fill',q:'I ___ (not/have to) work tomorrow — it\'s Sunday.',a:"don't have to",hint:'No obligation'},
    {type:'mc',q:'"Could you repeat that, please?" is...',opts:['A command','A polite request','An obligation','A deduction'],a:1},
    {type:'mc',q:'"It ___ be John — he\'s in Paris." (impossibility)',opts:['mustn\'t','can\'t','shouldn\'t','mightn\'t'],a:1},
    {type:'fill',q:'We ___ (should/negative) judge people by their appearance.',a:"shouldn't",hint:'Negative advice'},
    {type:'mc',q:'Modal verbs in English...',opts:['Change form for he/she/it','Have past participles','Use "do" in questions','None of the above — they are invariable'],a:3},
    {type:'mc',q:'Which sentence uses WOULD correctly?',opts:['I would go if I can.','She would likes coffee.','He would travel the world if he were rich.','They would going soon.'],a:2},
  ],
  general_a1: [
    {type:'mc',q:'What is the plural of "child"?',opts:['childs','childen','children','childes'],a:2},
    {type:'fill',q:'___ are you? — I am 15 years old.',a:'How old',hint:'Age question'},
    {type:'mc',q:'Which is a COLOR?',opts:['happy','tall','blue','fast'],a:2},
    {type:'mc',q:'"I have ___ apple." (correct article)',opts:['a','an','the','—'],a:1},
    {type:'fill',q:'A ___ barks. A cat meows.',a:'dog',hint:'Common pet animal'},
    {type:'mc',q:'What is "Monday" in English?',opts:['The first month','The first day of the week','A season','A holiday'],a:1},
    {type:'mc',q:'Which number comes after nineteen?',opts:['Ninety','Twenty','Eighteen','Twelve'],a:1},
    {type:'fill',q:'My mother\'s mother is my ___.',a:'grandmother',hint:'Parent of parent'},
    {type:'mc',q:'"The opposite of hot is..."',opts:['warm','cool','cold','frozen'],a:2},
    {type:'mc',q:'Which body part do you use to smell?',opts:['ear','eye','nose','mouth'],a:2},
    {type:'mc',q:'Which is a SCHOOL SUBJECT?',opts:['kitchen','mathematics','bedroom','garden'],a:1},
    {type:'fill',q:'Red + Blue = ___',a:'purple',hint:'Mixed color'},
    {type:'mc',q:'"___ is your name?" — "My name is Tom."',opts:['Where','When','What','Who'],a:2},
    {type:'mc',q:'How many days are in a week?',opts:['5','6','7','8'],a:2},
    {type:'fill',q:'I eat ___ every morning for breakfast. It has milk.',a:'cereal',hint:'Breakfast food with milk'},
    {type:'mc',q:'Which animal lives in water?',opts:['dog','cat','fish','bird'],a:2},
    {type:'mc',q:'Which is a FRUIT?',opts:['carrot','potato','apple','broccoli'],a:2},
    {type:'fill',q:'___ is the day after Monday.',a:'Tuesday',hint:'Second day of week'},
    {type:'mc',q:'"I ___ 12 years old."',opts:['am','is','are','be'],a:0},
    {type:'mc',q:'Which word means the opposite of BIG?',opts:['tall','huge','small','heavy'],a:2},
    {type:'fill',q:'We have ___ and legs to walk.',a:'feet',hint:'Plural of foot'},
    {type:'mc',q:'A teacher works in a...',opts:['hospital','school','restaurant','airport'],a:1},
    {type:'mc',q:'Which is a SEASON?',opts:['Monday','July','Summer','Morning'],a:2},
    {type:'fill',q:'Two plus three equals ___.',a:'five',hint:'2+3=?'},
    {type:'mc',q:'"She ___ got a sister."',opts:['have','has','is','are'],a:1},
    {type:'mc',q:'Which color is the sky on a sunny day?',opts:['red','green','blue','yellow'],a:2},
    {type:'fill',q:'I write with a ___ and read a ___.',a:'pen, book',hint:'School items'},
    {type:'mc',q:'"___ is the capital of England?"',opts:['What','Where','Who','Which'],a:0},
    {type:'mc',q:'Which word is a VERB?',opts:['happy','beautiful','run','quickly'],a:2},
    {type:'fill',q:'My father\'s brother is my ___.',a:'uncle',hint:'Male relative'},
  ],
  general_b1: [
    {type:'mc',q:'Which sentence is in Present Perfect?',opts:['I went to Paris.','I have been to Paris.','I go to Paris.','I was going to Paris.'],a:1},
    {type:'fill',q:'If it rains tomorrow, I ___ (stay) at home.',a:'will stay',hint:'First conditional'},
    {type:'mc',q:'The passive voice of "They built the bridge" is...',opts:['The bridge was built.','They were building.','The bridge is building.','Built the bridge was.'],a:0},
    {type:'mc',q:'"He ___ lived here for 10 years."',opts:['is','was','has','have'],a:2},
    {type:'fill',q:'I enjoy ___ (swim) in the ocean.',a:'swimming',hint:'Gerund form'},
    {type:'mc',q:'Reported: She said, "I am tired." →',opts:['She said she is tired.','She said she was tired.','She said she be tired.','She said she were tired.'],a:1},
    {type:'mc',q:'Which modal expresses a polite suggestion?',opts:['must','can\'t','shall','needn\'t'],a:2},
    {type:'fill',q:'The book ___ (write) by Tolstoy. (passive)',a:'was written',hint:'Past passive'},
    {type:'mc',q:'"While I ___ TV, the phone rang."',opts:['watched','was watching','am watching','watch'],a:1},
    {type:'mc',q:'Which word is a CONJUNCTION?',opts:['quickly','beautiful','although','often'],a:2},
    {type:'fill',q:'She ___ (not/finish) her homework yet.',a:"hasn't finished",hint:'Present perfect negative'},
    {type:'mc',q:'Choose the correct relative clause:',opts:['The man which called.','The man who called.','The man whose called.','The man whom called.'],a:1},
    {type:'mc',q:'"If I ___ rich, I would travel the world." (2nd conditional)',opts:['am','was','were','be'],a:2},
    {type:'fill',q:'They ___ (live) in London since 2010.',a:'have lived',hint:'Present perfect + since'},
    {type:'mc',q:'Phrasal verb "give up" means:',opts:['to start something','to continue something','to stop doing something','to give a present'],a:2},
    {type:'mc',q:'"I haven\'t eaten since ___"',opts:['two hours','yesterday','three days ago','last night'],a:1},
    {type:'fill',q:'___ you ever ___ (visit) Japan?',a:'Have, visited',hint:'Present perfect question'},
    {type:'mc',q:'Which is a compound sentence?',opts:['I ran.','I ran because I was late.','I ran, and she walked.','Running late is bad.'],a:2},
    {type:'mc',q:'The word "environment" refers to:',opts:['Your family','The natural world around us','Your workplace','Your hobbies'],a:1},
    {type:'fill',q:'She was ___ (read) when I called her.',a:'reading',hint:'Past continuous'},
    {type:'mc',q:'Technology has ___ (change) our lives greatly.',opts:['changed','change','changing','changes'],a:0},
    {type:'mc',q:'Choose the CORRECT sentence:',opts:['I have went there.','I have gone there.','I went have there.','I go there have.'],a:1},
    {type:'fill',q:'The report must ___ (submit) by Friday. (passive obligation)',a:'be submitted',hint:'Modal + passive'},
    {type:'mc',q:'Which word collocates with "make"?',opts:['make homework','make a decision','make exercise','make a travel'],a:1},
    {type:'fill',q:'He ___ (just/arrive) — he is still at the door.',a:'has just arrived',hint:'Present perfect with just'},
    {type:'mc',q:'"Despite the rain, they ___."',opts:['but they went','however went','they went out','went out anyway'],a:3},
    {type:'mc',q:'Which is NOT a phrasal verb?',opts:['look after','take off','give up','study hard'],a:3},
    {type:'fill',q:'If she ___ (study) harder, she would pass.',a:'studied',hint:'2nd conditional, past form'},
    {type:'mc',q:'"The police are ___ the crime." (investigating)',opts:['looking for','looking at','looking into','looking after'],a:2},
    {type:'mc',q:'Which sentence is grammatically correct?',opts:['She has never been to Tokyo.','She never has been Tokyo.','She has been never to Tokyo.','She been never to Tokyo.'],a:0},
  ],
};

// Add general question banks for all levels
QUESTION_BANKS['general_a2'] = QUESTION_BANKS['general_a1'].map(q=>({...q}));
QUESTION_BANKS['general_b2'] = QUESTION_BANKS['general_b1'].map(q=>({...q}));
QUESTION_BANKS['general_c1'] = QUESTION_BANKS['general_b1'].map(q=>({...q}));
QUESTION_BANKS['general_c2'] = QUESTION_BANKS['general_b1'].map(q=>({...q}));

// Auto-generate banks for topics without specific banks
Object.keys(TOPICS).forEach(lvl=>{
  (TOPICS[lvl]||[]).forEach(topic=>{
    if(!QUESTION_BANKS[topic.id]){
      QUESTION_BANKS[topic.id] = QUESTION_BANKS['general_'+lvl] || QUESTION_BANKS['general_a1'];
    }
  });
});

// ==================== VOCABULARY DATA ====================
const VOCABULARY = [
  // A1
  {word:'hello',pron:'/həˈloʊ/',trans:{en:'a greeting',ru:'привет',uz:'salom'},level:'A1',cat:'greetings'},
  {word:'goodbye',pron:'/ˌɡʊdˈbaɪ/',trans:{en:'farewell',ru:'пока/до свидания',uz:"xayr/ko'rishguncha"},level:'A1',cat:'greetings'},
  {word:'family',pron:'/ˈfæm.ɪ.li/',trans:{en:'related people',ru:'семья',uz:'oila'},level:'A1',cat:'family'},
  {word:'mother',pron:'/ˈmʌð.ər/',trans:{en:'female parent',ru:'мама',uz:'ona'},level:'A1',cat:'family'},
  {word:'father',pron:'/ˈfɑː.ðər/',trans:{en:'male parent',ru:'папа',uz:'ota'},level:'A1',cat:'family'},
  {word:'brother',pron:'/ˈbrʌð.ər/',trans:{en:'male sibling',ru:'брат',uz:'aka/uka'},level:'A1',cat:'family'},
  {word:'sister',pron:'/ˈsɪs.tər/',trans:{en:'female sibling',ru:'сестра',uz:'opa/singil'},level:'A1',cat:'family'},
  {word:'friend',pron:'/frend/',trans:{en:'a close companion',ru:'друг/подруга',uz:"do'st"},level:'A1',cat:'social'},
  {word:'house',pron:'/haʊs/',trans:{en:'a building to live in',ru:'дом',uz:'uy'},level:'A1',cat:'places'},
  {word:'school',pron:'/skuːl/',trans:{en:'place of learning',ru:'школа',uz:'maktab'},level:'A1',cat:'places'},
  {word:'apple',pron:'/ˈæp.əl/',trans:{en:'a round fruit',ru:'яблоко',uz:'olma'},level:'A1',cat:'food'},
  {word:'water',pron:'/ˈwɔː.tər/',trans:{en:'liquid we drink',ru:'вода',uz:'suv'},level:'A1',cat:'food'},
  {word:'cat',pron:'/kæt/',trans:{en:'a pet animal',ru:'кошка',uz:'mushuk'},level:'A1',cat:'animals'},
  {word:'dog',pron:'/dɒɡ/',trans:{en:'a loyal pet',ru:'собака',uz:'it'},level:'A1',cat:'animals'},
  {word:'red',pron:'/red/',trans:{en:'color of blood',ru:'красный',uz:'qizil'},level:'A1',cat:'colors'},
  {word:'blue',pron:'/bluː/',trans:{en:'color of sky',ru:'синий',uz:'ko\'k'},level:'A1',cat:'colors'},
  {word:'one',pron:'/wʌn/',trans:{en:'number 1',ru:'один',uz:'bir'},level:'A1',cat:'numbers'},
  {word:'two',pron:'/tuː/',trans:{en:'number 2',ru:'два',uz:'ikki'},level:'A1',cat:'numbers'},
  {word:'book',pron:'/bʊk/',trans:{en:'pages with text',ru:'книга',uz:'kitob'},level:'A1',cat:'objects'},
  {word:'pen',pron:'/pen/',trans:{en:'writing instrument',ru:'ручка',uz:'qalam'},level:'A1',cat:'objects'},
  // A2
  {word:'beautiful',pron:'/ˈbjuː.tɪ.fəl/',trans:{en:'very attractive',ru:'красивый',uz:'chiroyli'},level:'A2',cat:'adjectives'},
  {word:'interesting',pron:'/ˈɪn.trɪ.stɪŋ/',trans:{en:'holding attention',ru:'интересный',uz:'qiziqarli'},level:'A2',cat:'adjectives'},
  {word:'expensive',pron:'/ɪkˈspen.sɪv/',trans:{en:'costs a lot',ru:'дорогой',uz:'qimmat'},level:'A2',cat:'adjectives'},
  {word:'cheap',pron:'/tʃiːp/',trans:{en:'low cost',ru:'дешевый',uz:'arzon'},level:'A2',cat:'adjectives'},
  {word:'travel',pron:'/ˈtræv.əl/',trans:{en:'go to places',ru:'путешествовать',uz:'sayohat qilish'},level:'A2',cat:'actions'},
  {word:'shopping',pron:'/ˈʃɒp.ɪŋ/',trans:{en:'buying things',ru:'шоппинг',uz:'xarid qilish'},level:'A2',cat:'activities'},
  {word:'weather',pron:'/ˈweð.ər/',trans:{en:'atmospheric conditions',ru:'погода',uz:'ob-havo'},level:'A2',cat:'nature'},
  {word:'sunny',pron:'/ˈsʌn.i/',trans:{en:'bright with sunshine',ru:'солнечный',uz:'quyoshli'},level:'A2',cat:'weather'},
  {word:'rainy',pron:'/ˈreɪ.ni/',trans:{en:'with lots of rain',ru:'дождливый',uz:'yomg\'irli'},level:'A2',cat:'weather'},
  {word:'doctor',pron:'/ˈdɒk.tər/',trans:{en:'medical professional',ru:'доктор',uz:'shifokor'},level:'A2',cat:'jobs'},
  // B1
  {word:'environment',pron:'/ɪnˈvaɪ.rən.mənt/',trans:{en:'natural surroundings',ru:'окружающая среда',uz:'atrof-muhit'},level:'B1',cat:'nature'},
  {word:'technology',pron:'/tekˈnɒl.ə.dʒi/',trans:{en:'science application',ru:'технология',uz:'texnologiya'},level:'B1',cat:'science'},
  {word:'opportunity',pron:'/ˌɒp.əˈtjuː.nɪ.ti/',trans:{en:'a favorable chance',ru:'возможность',uz:'imkoniyat'},level:'B1',cat:'abstract'},
  {word:'responsibility',pron:'/rɪˌspɒn.sɪˈbɪl.ɪ.ti/',trans:{en:'being accountable',ru:'ответственность',uz:"mas'uliyat"},level:'B1',cat:'abstract'},
  {word:'achievement',pron:'/əˈtʃiːv.mənt/',trans:{en:'something accomplished',ru:'достижение',uz:'yutuq'},level:'B1',cat:'abstract'},
  {word:'pollution',pron:'/pəˈluː.ʃən/',trans:{en:'contamination of nature',ru:'загрязнение',uz:'ifloslanish'},level:'B1',cat:'environment'},
  {word:'negotiate',pron:'/nɪˈɡoʊ.ʃi.eɪt/',trans:{en:'to discuss to agree',ru:'договариваться',uz:'muzokaralar olib borish'},level:'B1',cat:'business'},
  {word:'analyse',pron:'/ˈæn.ə.laɪz/',trans:{en:'to examine carefully',ru:'анализировать',uz:'tahlil qilish'},level:'B1',cat:'academic'},
  // B2
  {word:'sophisticated',pron:'/səˈfɪs.tɪ.keɪ.tɪd/',trans:{en:'complex and refined',ru:'утончённый',uz:'murakkab/takomillashgan'},level:'B2',cat:'adjectives'},
  {word:'inevitable',pron:'/ɪnˈev.ɪ.tə.bəl/',trans:{en:'cannot be avoided',ru:'неизбежный',uz:'muqarrar'},level:'B2',cat:'adjectives'},
  {word:'consequence',pron:'/ˈkɒn.sɪ.kwəns/',trans:{en:'result of an action',ru:'последствие',uz:'oqibat'},level:'B2',cat:'abstract'},
  {word:'perspective',pron:'/pəˈspek.tɪv/',trans:{en:'point of view',ru:'перспектива/точка зрения',uz:'nuqtai nazar'},level:'B2',cat:'abstract'},
  {word:'phenomenon',pron:'/fɪˈnɒm.ɪ.nən/',trans:{en:'observable occurrence',ru:'явление/феномен',uz:'hodisa'},level:'B2',cat:'academic'},
  // C1
  {word:'eloquent',pron:'/ˈel.ə.kwənt/',trans:{en:'well-spoken, persuasive',ru:'красноречивый',uz:'notiq'},level:'C1',cat:'language'},
  {word:'ambiguous',pron:'/æmˈbɪɡ.ju.əs/',trans:{en:'having multiple meanings',ru:'неоднозначный',uz:'noaniq/ikkilantiradigan'},level:'C1',cat:'language'},
  {word:'meticulous',pron:'/mɪˈtɪk.jʊ.ləs/',trans:{en:'very careful and precise',ru:'дотошный',uz:'puxta/aniq'},level:'C1',cat:'character'},
  {word:'pragmatic',pron:'/præɡˈmæt.ɪk/',trans:{en:'dealing with things practically',ru:'прагматичный',uz:'amaliyotchi'},level:'C1',cat:'character'},
  // C2
  {word:'ephemeral',pron:'/ɪˈfem.ər.əl/',trans:{en:'lasting for a very short time',ru:'мимолётный',uz:'o\'tkinchi'},level:'C2',cat:'abstract'},
  {word:'omniscient',pron:'/ɒmˈnɪs.i.ənt/',trans:{en:'knowing everything',ru:'всезнающий',uz:"hamma narsani biladigan"},level:'C2',cat:'abstract'},
  {word:'sycophant',pron:'/ˈsɪk.ə.fənt/',trans:{en:'a person using flattery',ru:'льстец/подхалим',uz:"yolg'onoqchi"},level:'C2',cat:'people'},
  {word:'quintessential',pron:'/ˌkwɪn.tɪˈsen.ʃəl/',trans:{en:'perfect example of quality',ru:'квинтэссенция',uz:"eng tipik namuna"},level:'C2',cat:'abstract'},
];

// ==================== LISTENING DATA ====================
const LISTENING_TRACKS = [
  {
    id:'l1',title:'A Day in London',level:'A1',
    text:`Hello! My name is Emma and I live in London. Every day I wake up at seven o'clock. I have breakfast at half past seven. I usually eat toast and drink orange juice. Then I go to school by bus. At school, I study English, Mathematics and Science. My favourite subject is Art. In the afternoon, I play football with my friends in the park. In the evening, I help my mother make dinner. We eat together as a family. After dinner, I watch television for one hour. Then I read a book and go to sleep at nine thirty. I love my daily routine!`,
    questions:[
      {q:'What time does Emma wake up?',opts:['6 o\'clock','7 o\'clock','8 o\'clock','9 o\'clock'],a:1},
      {q:'How does Emma go to school?',opts:['by car','by bike','by bus','on foot'],a:2},
      {q:'What is Emma\'s favourite subject?',opts:['Mathematics','Science','English','Art'],a:3},
      {q:'What does Emma do in the afternoon?',opts:['reads books','watches TV','plays football','helps cook'],a:2},
      {q:'What time does Emma go to sleep?',opts:['8:30','9:00','9:30','10:00'],a:2},
    ]
  },
  {
    id:'l2',title:'Job Interview',level:'A2',
    text:`Interviewer: Good morning! Please, have a seat. Can you tell me a little about yourself?
    Applicant: Good morning! Thank you. My name is David Chen. I graduated from Manchester University two years ago with a degree in Business Administration. I have been working as a sales assistant for the past eighteen months.
    Interviewer: Excellent. Why do you want to work for our company?
    Applicant: I've researched your company extensively. You are leaders in sustainable fashion, and I'm passionate about environmental responsibility. I believe my skills in customer service and data analysis would be very valuable here.
    Interviewer: What are your greatest strengths?
    Applicant: I'm highly organized, I work well under pressure, and I'm an excellent communicator. I also speak three languages: English, Mandarin, and Spanish.
    Interviewer: That's impressive! Do you have any questions for us?
    Applicant: Yes — could you tell me more about career development opportunities within the company?`,
    questions:[
      {q:'What degree does David have?',opts:['Computer Science','Business Administration','Art','Engineering'],a:1},
      {q:'How long has David worked as a sales assistant?',opts:['6 months','1 year','18 months','2 years'],a:2},
      {q:'Why does David want to work at this company?',opts:['High salary','Sustainable fashion & environment','Near his home','Short working hours'],a:1},
      {q:'How many languages does David speak?',opts:['1','2','3','4'],a:2},
      {q:'What does David ask the interviewer?',opts:['About salary','About holidays','About career development','About working hours'],a:2},
    ]
  },
  {
    id:'l3',title:'Climate Change Discussion',level:'B1',
    text:`Host: Welcome to our podcast. Today we're discussing one of the most pressing issues of our time — climate change. Joining us is Dr. Maria Santos, an environmental scientist from Cambridge University. Dr. Santos, can you explain what is happening to our planet?
    Dr. Santos: Absolutely. Over the past century, human activities — primarily the burning of fossil fuels — have released enormous amounts of carbon dioxide and other greenhouse gases into the atmosphere. This has caused the average global temperature to rise by approximately 1.1 degrees Celsius since pre-industrial times.
    Host: What are the main consequences of this warming?
    Dr. Santos: We're seeing more frequent extreme weather events — floods, droughts, and hurricanes. Sea levels are rising, threatening coastal communities. Biodiversity is declining as habitats change faster than species can adapt. Arctic ice is melting at an alarming rate.
    Host: Is there still time to act?
    Dr. Santos: Yes, but the window is closing. We need to transition to renewable energy, reduce consumption, and adopt more sustainable practices at both individual and governmental levels. Every action counts.`,
    questions:[
      {q:'What is the primary cause of climate change according to Dr. Santos?',opts:['Deforestation','Burning fossil fuels','Overpopulation','Ocean pollution'],a:1},
      {q:'By how much has the global temperature risen?',opts:['0.5°C','1.1°C','2°C','3°C'],a:1},
      {q:'Which is NOT mentioned as a consequence of warming?',opts:['Rising sea levels','Declining biodiversity','More earthquakes','Extreme weather events'],a:2},
      {q:'What does Dr. Santos suggest we transition to?',opts:['Nuclear energy','Renewable energy','Natural gas','Coal'],a:1},
      {q:'What is Dr. Santos\' overall message?',opts:['It\'s too late to act','Individual actions don\'t matter','Urgent action is still possible','Only governments can help'],a:2},
    ]
  },
  {
    id:'l4',title:'The History of Jazz',level:'B2',
    text:`Jazz is one of America's greatest contributions to world music. It emerged in New Orleans at the beginning of the twentieth century, born from a unique confluence of African rhythms, European harmonies, and the blues tradition. The genre is characterized by improvisation, syncopated rhythms, and complex harmonics that distinguish it from all other musical forms.
    The 1920s became known as the Jazz Age, when artists like Louis Armstrong and Duke Ellington brought the music from smoky clubs to concert halls and radio broadcasts, reaching millions of listeners. Armstrong's virtuosity on the trumpet and Ellington's sophisticated orchestrations elevated jazz to an art form respected worldwide.
    The bebop revolution of the 1940s, led by Charlie Parker and Dizzy Gillespie, pushed jazz into more complex territory, with faster tempos, intricate chord progressions, and a deliberate move away from dance music toward purely artistic expression. This divided audiences but secured jazz's reputation as a sophisticated musical genre.
    Today, jazz continues to evolve, incorporating elements of hip-hop, electronic music, and global traditions. It remains a living, breathing art form that celebrates spontaneity and creative dialogue between musicians.`,
    questions:[
      {q:'Where did jazz originate?',opts:['New York','Chicago','New Orleans','Los Angeles'],a:2},
      {q:'Which is NOT a characteristic of jazz?',opts:['Improvisation','Syncopated rhythms','Strict written scores','Complex harmonics'],a:2},
      {q:'Who was known for trumpet virtuosity?',opts:['Duke Ellington','Charlie Parker','Louis Armstrong','Dizzy Gillespie'],a:2},
      {q:'What characterized the bebop revolution?',opts:['Simpler melodies','Slower tempos','Focus on dance','Faster tempos and complex chords'],a:3},
      {q:'How is jazz described today?',opts:['A dead art form','Still evolving and living','Only for specialists','No longer popular'],a:1},
    ]
  },
  {
    id:'l5',title:'Artificial Intelligence Ethics',level:'C1',
    text:`The rapid advancement of artificial intelligence presents both extraordinary opportunities and profound ethical challenges that demand careful consideration. As AI systems become increasingly integrated into healthcare, criminal justice, financial services, and social media, questions of accountability, transparency, and fairness have moved from the realm of science fiction to urgent policy debates.
    One central concern is algorithmic bias. When AI systems are trained on historical data that reflects societal inequalities, they can perpetuate and even amplify those inequalities. Facial recognition systems, for instance, have demonstrated significantly higher error rates for darker-skinned individuals, raising serious questions about their deployment by law enforcement agencies.
    The issue of explainability is equally critical. Many advanced AI models operate as "black boxes," making consequential decisions — whether to approve a loan, parole a prisoner, or diagnose a disease — without providing comprehensible explanations for those decisions. This opacity undermines human autonomy and makes it extraordinarily difficult to identify and correct errors.
    Addressing these challenges requires interdisciplinary collaboration between technologists, ethicists, policymakers, and the communities most affected by AI systems. Robust regulatory frameworks, diverse development teams, and ongoing audits are essential if we are to harness the transformative potential of AI while safeguarding fundamental human rights.`,
    questions:[
      {q:'What is "algorithmic bias"?',opts:['Errors caused by hardware','AI perpetuating societal inequalities','Slow computing speed','Incorrect programming'],a:1},
      {q:'What problem do "black box" AI systems create?',opts:['They are too slow','They cannot make decisions','Their decisions are not explainable','They require too much power'],a:2},
      {q:'Which field is NOT mentioned as using AI?',opts:['Healthcare','Criminal justice','Space exploration','Financial services'],a:2},
      {q:'What does the author suggest to address AI challenges?',opts:['Ban all AI systems','Interdisciplinary collaboration','Rely only on technologists','Avoid AI in sensitive areas'],a:1},
      {q:'What is the main concern about facial recognition?',opts:['It\'s too expensive','Higher error rates for some groups','It requires too much data','It\'s too slow'],a:1},
    ]
  },
];

// ==================== READING PASSAGES ====================
const READING_PASSAGES = [
  {
    id:'r1',title:'My School Day',level:'A1',
    text:`My name is <span class="highlight-word" onclick="showWordDef(event,'Tom','noun','a male name')">Tom</span>. I am twelve years old. I go to <span class="highlight-word" onclick="showWordDef(event,'school',\"noun\",'a place where children learn')">school</span> every day from Monday to Friday. My school starts at eight o'clock in the morning. My favourite <span class="highlight-word" onclick="showWordDef(event,'subject',\"noun\",'an area of study')">subject</span> is <span class="highlight-word" onclick="showWordDef(event,'science',\"noun\",'the study of the natural world')">science</span> because I love doing experiments. I have many <span class="highlight-word" onclick="showWordDef(event,'friends',\"noun\",'people you like and spend time with')">friends</span> at school. After school, I play football or read books. My best friend is called James. We do our <span class="highlight-word" onclick="showWordDef(event,'homework',\"noun\",'schoolwork done at home')">homework</span> together every afternoon.`,
    questions:[
      {q:'How old is Tom?',opts:['10','11','12','13'],a:2},
      {q:'What time does school start?',opts:['7:00','8:00','9:00','10:00'],a:1},
      {q:'What is Tom\'s favourite subject?',opts:['Maths','English','Science','Art'],a:2},
      {q:'What does Tom do after school?',opts:['sleeps','watches TV','plays football or reads','goes to work'],a:2},
      {q:'Who is Tom\'s best friend?',opts:['John','James','Jack','Jake'],a:1},
    ]
  },
  {
    id:'r2',title:'The Amazon Rainforest',level:'B1',
    text:`The Amazon <span class="highlight-word" onclick="showWordDef(event,'rainforest',\"noun\",'a dense tropical forest with high rainfall')">rainforest</span> is the world's largest <span class="highlight-word" onclick="showWordDef(event,'tropical',\"adjective\",'relating to the hot, humid regions near the equator')">tropical</span> forest, covering approximately 5.5 million square kilometres across nine South American countries. Often called the "<span class="highlight-word" onclick="showWordDef(event,'lungs',\"noun\",'organs that breathe; used metaphorically here')">lungs</span> of the Earth," it produces roughly 20% of the world's <span class="highlight-word" onclick="showWordDef(event,'oxygen',\"noun\",'the gas we breathe')">oxygen</span> and is home to an estimated 10% of all species on Earth. <span class="highlight-word" onclick="showWordDef(event,'biodiversity',\"noun\",'the variety of plant and animal life in an area')">Biodiversity</span> in the Amazon is unmatched anywhere on the planet. Scientists estimate that there are over 40,000 plant species, 1,300 bird species, and 3,000 types of fish. Many <span class="highlight-word" onclick="showWordDef(event,'indigenous',\"adjective\",'originating in and characteristic of a place')">indigenous</span> communities have lived in the Amazon for thousands of years, developing deep knowledge of its plants and <span class="highlight-word" onclick="showWordDef(event,'ecosystems',\"noun\",'communities of living things interacting with their environment')">ecosystems</span>. However, <span class="highlight-word" onclick="showWordDef(event,'deforestation',\"noun\",'the clearing of forests')">deforestation</span> now threatens this vital ecosystem, with approximately 17% of the Amazon already destroyed. Urgent action is needed to protect this irreplaceable natural treasure.`,
    questions:[
      {q:'How many square kilometres does the Amazon cover?',opts:['2.5 million','5.5 million','8 million','10 million'],a:1},
      {q:'What percentage of world oxygen does the Amazon produce?',opts:['10%','15%','20%','25%'],a:2},
      {q:'How many bird species are estimated in the Amazon?',opts:['300','800','1,300','3,000'],a:2},
      {q:'What percentage of the Amazon has been destroyed?',opts:['5%','10%','17%','25%'],a:2},
      {q:'Why is the Amazon called "the lungs of the Earth"?',opts:['It absorbs water','It produces large amounts of oxygen','It contains many animals','It is very large'],a:1},
    ]
  },
  {
    id:'r3',title:'The Psychology of Happiness',level:'C1',
    text:`<span class="highlight-word" onclick="showWordDef(event,'Happiness',\"noun\",'the state of being happy and content')">Happiness</span> has been the subject of <span class="highlight-word" onclick="showWordDef(event,'philosophical',\"adjective\",'relating to the study of fundamental questions')">philosophical</span> inquiry for millennia, yet modern psychology has only recently begun to <span class="highlight-word" onclick="showWordDef(event,'empirically',\"adverb\",'based on observation and evidence')">empirically</span> investigate what makes human beings <span class="highlight-word" onclick="showWordDef(event,'flourish',\"verb\",'to grow and develop in a healthy way')">flourish</span>. The field of positive psychology, pioneered by Martin Seligman in the 1990s, shifted the focus of psychological research from pathology and dysfunction toward human <span class="highlight-word" onclick="showWordDef(event,'strengths',\"noun\",'good qualities and abilities')">strengths</span> and wellbeing. Research consistently demonstrates that happiness is not primarily determined by <span class="highlight-word" onclick="showWordDef(event,'circumstances',\"noun\",'conditions or factors affecting a situation')">circumstances</span> — wealth, fame, or physical beauty — but by internal factors such as <span class="highlight-word" onclick="showWordDef(event,'gratitude',\"noun\",'the feeling of appreciation')">gratitude</span>, meaningful relationships, sense of purpose, and personal growth. The "<span class="highlight-word" onclick="showWordDef(event,'hedonic',\"adjective\",'related to pleasure and happiness')">hedonic</span> treadmill" theory suggests that people rapidly adapt to positive changes in their lives, returning to a baseline level of happiness regardless of material gains. This adaptation explains why lottery winners are typically no happier than average people after twelve months. Sustainable happiness, researchers argue, comes not from <span class="highlight-word" onclick="showWordDef(event,'accumulating',\"verb\",'gathering more and more')">accumulating</span> possessions but from investing in experiences, relationships, and altruistic behaviour.`,
    questions:[
      {q:'Who pioneered positive psychology?',opts:['Sigmund Freud','Martin Seligman','Carl Jung','Abraham Maslow'],a:1},
      {q:'What does the "hedonic treadmill" theory explain?',opts:['Physical exercise and happiness','People adapting back to a happiness baseline','Wealth creating lasting happiness','Exercise improving mood'],a:1},
      {q:'According to research, what primarily determines happiness?',opts:['Wealth','Fame','Internal factors like gratitude','Physical beauty'],a:2},
      {q:'What does research say about lottery winners after 12 months?',opts:['Much happier','Slightly happier','No happier than average','Unhappier'],a:2},
      {q:'What does the author suggest creates sustainable happiness?',opts:['More wealth','Experiences, relationships, and altruism','Fame and status','Material possessions'],a:1},
    ]
  },
];

// ==================== SPEAKING PROMPTS ====================
const SPEAKING_PROMPTS = [
  {ai:"What is your name?", hint:"Say: My name is... / I'm..."},
  {ai:"Where are you from?", hint:"Say: I'm from... / I come from..."},
  {ai:"How old are you?", hint:"Say: I am ... years old"},
  {ai:"What do you do? Are you a student or do you work?", hint:"Say: I am a student / I work as a..."},
  {ai:"What are your hobbies? What do you enjoy doing in your free time?", hint:"Say: I enjoy... / I like... / My hobby is..."},
  {ai:"Describe your family. How many people are in your family?", hint:"Talk about family members"},
  {ai:"What is your favourite food and why do you like it?", hint:"Say: My favourite food is... because..."},
  {ai:"Tell me about your city or town. What is it like?", hint:"Describe your home city"},
  {ai:"What did you do yesterday? Tell me about your day.", hint:"Use past tense: I went, I ate, I saw..."},
  {ai:"If you could travel anywhere in the world, where would you go and why?", hint:"Use 'I would...' / 'because...'"},
  {ai:"What are your plans for the future? What do you want to achieve?", hint:"Use: I want to... / I'm going to... / I hope to..."},
  {ai:"Tell me about a challenge you have faced in your life and how you overcame it.", hint:"Use past tense and show resilience"},
  {ai:"What is your opinion on social media? Does it have more advantages or disadvantages?", hint:"Give your opinion with reasons"},
  {ai:"How important is learning English in today's world? Why?", hint:"Discuss importance with examples"},
  {ai:"Describe the most memorable experience of your life.", hint:"Use vivid language and past tense"},
];

// ==================== LEADERBOARD DATA ====================
const FAKE_PLAYERS = [
  {name:'🇬🇧 Emily W.',xp:8450,level:'B2',avatar:'👩',streak:42},
  {name:'🇺🇸 James K.',xp:7820,level:'B2',avatar:'👨',streak:38},
  {name:'🇩🇪 Anna M.',xp:7105,level:'B1',avatar:'👩‍🦱',streak:29},
  {name:'🇯🇵 Kenji T.',xp:6890,level:'B1',avatar:'🧑',streak:21},
  {name:'🇧🇷 Sofia R.',xp:6234,level:'A2',avatar:'👩‍🦰',streak:15},
  {name:'🇰🇷 Min-Ji P.',xp:5920,level:'A2',avatar:'👩‍🦳',streak:12},
  {name:'🇮🇳 Raj P.',xp:5432,level:'B1',avatar:'🧔',streak:8},
  {name:'🇫🇷 Pierre D.',xp:4890,level:'A1',avatar:'👴',streak:5},
  {name:'🇺🇿 You',xp:state.xp,level:'A1',avatar:'🧑‍💻',streak:state.streak,isMe:true},
];

// ==================== UTILITIES ====================
function shuffle(arr){
  const a=[...arr];
  for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]];}
  return a;
}
function saveState(){
  localStorage.setItem('xp',state.xp);
  localStorage.setItem('streak',state.streak);
  localStorage.setItem('lessons',state.lessonsCompleted);
  localStorage.setItem('totalAnswers',state.totalAnswers);
  localStorage.setItem('correctAnswers',state.correctAnswers);
  localStorage.setItem('completedTopics',JSON.stringify(state.completedTopics));
  localStorage.setItem('scores',JSON.stringify(state.scores));
}
function showToast(msg,type='info'){
  const t=document.getElementById('toast');
  t.textContent=msg; t.className=`toast ${type} show`;
  setTimeout(()=>t.classList.remove('show'),3000);
}
function addXP(amount){
  state.xp+=amount;
  document.getElementById('totalXP').textContent=state.xp;
  document.getElementById('homeXP').textContent=state.xp;
  saveState();
}
function updateHomeStats(){
  document.getElementById('homeStreak').textContent=state.streak;
  document.getElementById('homeXP').textContent=state.xp;
  document.getElementById('homeLessons').textContent=state.lessonsCompleted;
  const acc=state.totalAnswers>0?Math.round(state.correctAnswers/state.totalAnswers*100):0;
  document.getElementById('homeAccuracy').textContent=acc+'%';
  document.getElementById('totalXP').textContent=state.xp;
  document.getElementById('streakDays').textContent=state.streak;
}

// ==================== SECTIONS ====================
function showSection(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.nav-btn').forEach((b,i)=>{
    const sections=['home','learn','listening','reading','speaking','vocabulary','leaderboard','aichat','progress'];
    b.classList.toggle('active',sections[i]===id);
  });
  if(id==='leaderboard') renderLeaderboard();
  if(id==='vocabulary') renderVocabulary();
  if(id==='listening') renderListening();
  if(id==='reading') renderReading();
  if(id==='speaking') renderSpeaking();
  if(id==='progress') renderProgress();
  if(id==='home') updateHomeStats();
  if(id==='learn') { showLevels(); }
  if(id==='aichat') initChat();
}

function renderCurrentSection(){
  applyTranslations();
}

// ==================== LEARN / LEVELS ====================
function showLevels(){
  document.getElementById('levelsView').style.display='block';
  document.getElementById('topicsView').style.display='none';
  document.getElementById('lessonView').style.display='none';
  document.getElementById('testView').style.display='none';
  document.getElementById('resultView').style.display='none';
  renderLevels();
}
function renderLevels(){
  const grid=document.getElementById('levelsGrid');
  grid.innerHTML=LEVELS.map((lv,i)=>{
    const allTopics=(TOPICS[lv.id]||[]);
    const done=allTopics.filter(t=>state.completedTopics.includes(t.id)).length;
    const pct=allTopics.length?Math.round(done/allTopics.length*100):0;
    const stars='⭐'.repeat(Math.min(3,Math.floor(pct/34)));
    return `<div class="level-card ${pct===100?'completed':''}" onclick="selectLevel('${lv.id}')">
      <div class="level-emoji">${lv.emoji}</div>
      <div class="level-name">${lv.name}</div>
      <div class="level-desc">${lv.desc}</div>
      <div class="level-progress"><div class="level-progress-fill" style="width:${pct}%"></div></div>
      <div style="font-size:.75rem;color:var(--text2);margin-top:4px">${done}/${allTopics.length} topics</div>
      <div class="level-stars">${stars||'☆☆☆'}</div>
    </div>`;
  }).join('');
}
function selectLevel(id){
  state.currentLevel=id;
  document.getElementById('levelsView').style.display='none';
  document.getElementById('topicsView').style.display='block';
  document.getElementById('currentLevelTitle').textContent=LEVELS.find(l=>l.id===id)?.name||id;
  renderTopics(id);
}
function renderTopics(lid){
  const list=document.getElementById('topicsList');
  const topics=TOPICS[lid]||[];
  list.innerHTML=topics.map(tp=>{
    const done=state.completedTopics.includes(tp.id);
    const score=state.scores[tp.id];
    return `<div class="topic-item ${done?'done':''}" onclick="selectTopic('${tp.id}','${lid}')">
      <div class="topic-icon">${tp.icon}</div>
      <div class="topic-info">
        <div class="topic-title">${tp.title}</div>
        <div class="topic-subtitle">${tp.sub}${score?` · Last score: ${score}%`:''}</div>
      </div>
      <span class="topic-badge ${done?'badge-done':'badge-new'}">${done?'✓ Done':'New'}</span>
    </div>`;
  }).join('');
}
function backToLevels(){
  document.getElementById('levelsView').style.display='block';
  document.getElementById('topicsView').style.display='none';
}
function selectTopic(tid,lid){
  state.currentTopic=tid;
  document.getElementById('topicsView').style.display='none';
  document.getElementById('lessonView').style.display='block';
  document.getElementById('lessonTitle').textContent=
    (TOPICS[lid]||[]).find(t=>t.id===tid)?.title||tid;
  const content=LESSON_CONTENT[tid]||generateLessonContent(tid,lid);
  document.getElementById('lessonContent').innerHTML=`<div class="lesson-content">${content}</div>`;
}
function generateLessonContent(tid,lid){
  const topic=(TOPICS[lid]||[]).find(t=>t.id===tid);
  if(!topic) return '<p>Content loading...</p>';
  return `
    <h3>${topic.icon} ${topic.title}</h3>
    <p>This lesson covers <strong>${topic.title}</strong>. Study the key concepts below.</p>
    <h3>Key Points:</h3>
    <div class="example"><strong>Definition:</strong> ${topic.sub}</div>
    <div class="example"><strong>Usage:</strong> This topic is essential for ${lid.toUpperCase()} level English.</div>
    <h3>Examples:</h3>
    <div class="example">Example 1: Practice using ${topic.title} in everyday conversation.</div>
    <div class="example">Example 2: ${topic.title} appears frequently in written and spoken English.</div>
    <h3>Practice Tip:</h3>
    <p>Try to use what you've learned in real conversations. The more you practice, the more natural it becomes!</p>
    <div class="example">🎯 Now complete the 30-question test to check your understanding!</div>
  `;
}
function backToTopics(){
  document.getElementById('lessonView').style.display='none';
  document.getElementById('topicsView').style.display='block';
}
function backToLesson(){
  document.getElementById('testView').style.display='none';
  document.getElementById('lessonView').style.display='block';
}

// ==================== TEST ENGINE ====================
let testStartTime;
function startTest(){
  document.getElementById('lessonView').style.display='none';
  document.getElementById('testView').style.display='block';
  state.testQuestions=generateQuestions(state.currentTopic, state.currentLevel);
  state.currentQ=0;
  state.testScore=0;
  state.testCorrect=0;
  testStartTime=Date.now();
  renderQuestion();
}
function renderQuestion(){
  const q=state.testQuestions[state.currentQ];
  if(!q) return showResult();
  document.getElementById('questionNum').textContent=`${state.currentQ+1} / 30`;
  document.getElementById('questionScore').textContent=`Score: ${state.testScore}`;
  document.getElementById('testProgressFill').style.width=`${((state.currentQ)/30)*100}%`;
  const container=document.getElementById('questionContainer');
  if(q.type==='mc'){
    container.innerHTML=`
      <div class="question-card">
        <div class="question-type">Multiple Choice</div>
        <div class="question-text">${q.q}</div>
        <div class="options">${q.opts.map((o,i)=>`<button class="option-btn" onclick="answerMC(${i})">${String.fromCharCode(65+i)}. ${o}</button>`).join('')}</div>
        <div id="feedback"></div>
      </div>
      <button class="next-btn" id="nextBtn" onclick="nextQuestion()" disabled>${state.currentQ<29?t('next'):t('finish')}</button>
    `;
  } else {
    container.innerHTML=`
      <div class="question-card">
        <div class="question-type">Fill in the Blank</div>
        <div class="question-text">${q.q}</div>
        <p style="font-size:.8rem;color:var(--text2);margin-bottom:8px">Hint: ${q.hint||''}</p>
        <input class="fill-input" id="fillInput" placeholder="Type your answer..." onkeydown="if(event.key==='Enter')checkFill()">
        <div id="feedback"></div>
      </div>
      <button class="next-btn" onclick="checkFill()" id="checkBtn">Check Answer</button>
      <button class="next-btn" id="nextBtn" onclick="nextQuestion()" style="display:none">${state.currentQ<29?t('next'):t('finish')}</button>
    `;
  }
}
function answerMC(idx){
  const q=state.testQuestions[state.currentQ];
  const btns=document.querySelectorAll('.option-btn');
  btns.forEach(b=>b.disabled=true);
  state.totalAnswers++;
  if(idx===q.a){
    btns[idx].classList.add('correct');
    state.testScore+=10; state.testCorrect++;
    state.correctAnswers++;
    document.getElementById('feedback').innerHTML=`<div class="feedback good">✅ ${t('correct')} +10 XP</div>`;
    showToast(t('correct'),'success');
  } else {
    btns[idx].classList.add('wrong');
    btns[q.a].classList.add('correct');
    document.getElementById('feedback').innerHTML=`<div class="feedback bad">❌ ${t('wrong')} ${t('correct')}: ${q.opts[q.a]}</div>`;
  }
  document.getElementById('nextBtn').disabled=false;
  document.getElementById('questionScore').textContent=`Score: ${state.testScore}`;
  saveState();
}
function checkFill(){
  const q=state.testQuestions[state.currentQ];
  const input=document.getElementById('fillInput');
  const val=input.value.trim().toLowerCase();
  const correct=q.a.toLowerCase();
  state.totalAnswers++;
  document.getElementById('checkBtn').style.display='none';
  document.getElementById('nextBtn').style.display='block';
  if(val===correct||correct.split('/').some(c=>val===c.trim())){
    input.classList.add('correct');
    state.testScore+=10; state.testCorrect++;
    state.correctAnswers++;
    document.getElementById('feedback').innerHTML=`<div class="feedback good">✅ ${t('correct')} +10 XP</div>`;
    showToast(t('correct'),'success');
  } else {
    input.classList.add('wrong');
    document.getElementById('feedback').innerHTML=`<div class="feedback bad">❌ ${t('wrong')} ${t('correct')}: <strong>${q.a}</strong></div>`;
  }
  input.disabled=true;
  document.getElementById('questionScore').textContent=`Score: ${state.testScore}`;
  saveState();
}
function nextQuestion(){
  state.currentQ++;
  if(state.currentQ>=30) showResult();
  else renderQuestion();
}
function showResult(){
  document.getElementById('testView').style.display='none';
  document.getElementById('resultView').style.display='block';
  const pct=Math.round(state.testCorrect/30*100);
  const xpEarned=state.testScore;
  addXP(xpEarned);
  state.lessonsCompleted++;
  if(!state.completedTopics.includes(state.currentTopic))
    state.completedTopics.push(state.currentTopic);
  state.scores[state.currentTopic]=pct;
  saveState();
  const elapsed=Math.round((Date.now()-testStartTime)/1000);
  const mins=Math.floor(elapsed/60), secs=elapsed%60;
  let grade,emoji,cls;
  if(pct>=90){grade=t('excellent');emoji='🌟🌟🌟';cls='excellent';}
  else if(pct>=70){grade=t('great');emoji='🌟🌟';cls='good';}
  else if(pct>=50){grade=t('good');emoji='🌟';cls='good';}
  else{grade=t('keep_trying');emoji='💪';cls='poor';}

  // AI feedback based on score
  let aiFeedback = '';
  if(pct>=90) aiFeedback=`Outstanding performance! You demonstrated excellent command of this topic. Your accuracy of ${pct}% shows deep understanding. Consider moving to the next topic or level!`;
  else if(pct>=70) aiFeedback=`Good work! You answered ${state.testCorrect}/30 correctly. You have a solid understanding but could review a few areas. Focus on the questions you missed and try again for a higher score.`;
  else if(pct>=50) aiFeedback=`You passed, but there is room for improvement. You scored ${pct}%. I recommend reviewing the lesson content again, paying special attention to the grammar rules and vocabulary. Practice makes perfect!`;
  else aiFeedback=`Don't be discouraged! A score of ${pct}% means you're still learning this topic. Go back to the lesson, study the examples carefully, and try again. Every attempt helps you improve!`;

  document.getElementById('resultView').innerHTML=`
    <div class="card result-card">
      <div class="result-emoji">${emoji}</div>
      <div class="result-score ${cls}">${pct}%</div>
      <div class="result-label">${grade}</div>
      <div class="result-stats">
        <div class="stat-item"><div class="stat-num">${state.testCorrect}/30</div><div class="stat-lbl">${t('questions_correct')}</div></div>
        <div class="stat-item"><div class="stat-num">+${xpEarned}</div><div class="stat-lbl">${t('xp_earned')}</div></div>
        <div class="stat-item"><div class="stat-num">${mins}m ${secs}s</div><div class="stat-lbl">${t('time_spent')}</div></div>
      </div>
      <div class="ai-feedback-box">
        <h4>🤖 ${t('ai_analysis')}</h4>
        <p>${aiFeedback}</p>
      </div>
      <div>
        <button class="retry-btn" onclick="startTest()">${t('retry')}</button>
        <button class="home-btn" onclick="showLevels()">${t('home')}</button>
      </div>
    </div>
  `;
  updateHomeStats();
}

// ==================== LISTENING ====================
let audioTimeout=null;
let wavAnimInterval=null;
function renderListening(){
  const c=document.getElementById('listeningContent');
  let html='';
  LISTENING_TRACKS.forEach(track=>{
    html+=`<div class="audio-player" id="player_${track.id}">
      <div class="audio-controls">
        <button class="play-btn" id="playBtn_${track.id}" onclick="togglePlay('${track.id}')">▶</button>
        <div class="audio-info">
          <div class="audio-title">${track.title}</div>
          <div class="audio-dur">Level: ${track.level} · ${Math.floor(track.text.split(' ').length/130)+1} min</div>
        </div>
        <span style="font-size:.75rem;color:var(--text2);padding:4px 10px;background:rgba(108,99,255,.15);border-radius:8px">${track.level}</span>
      </div>
      <div class="speed-btns">
        <button class="speed-btn active" onclick="setSpeed('${track.id}',0.75,this)">0.75x</button>
        <button class="speed-btn" onclick="setSpeed('${track.id}',1,this)">1x</button>
        <button class="speed-btn" onclick="setSpeed('${track.id}',1.25,this)">1.25x</button>
        <button class="speed-btn" onclick="setSpeed('${track.id}',1.5,this)">1.5x</button>
      </div>
      <div class="audio-wave" id="wave_${track.id}">
        <div class="wave-bars" id="waveBars_${track.id}">${Array(20).fill(0).map(()=>`<div class="wave-bar" style="height:${Math.random()*30+5}px"></div>`).join('')}</div>
      </div>
      <span class="transcript-toggle" onclick="toggleTranscript('${track.id}')" id="transToggle_${track.id}">${t('show_transcript')}</span>
      <div class="transcript-box" id="trans_${track.id}">${track.text}</div>
    </div>
    <div class="card" style="margin-top:-8px;margin-bottom:16px">
      <div class="card-title" style="font-size:.95rem">❓ ${t('listening_q')}</div>
      <div id="listenQs_${track.id}">${renderListeningQs(track)}</div>
    </div>`;
  });
  c.innerHTML=html;
}
function renderListeningQs(track){
  return track.questions.map((q,qi)=>`
    <div style="margin-bottom:14px">
      <div style="font-weight:700;font-size:.88rem;margin-bottom:8px">${qi+1}. ${q.q}</div>
      <div style="display:flex;flex-direction:column;gap:6px">
        ${q.opts.map((o,oi)=>`<button class="option-btn" id="lq_${track.id}_${qi}_${oi}" onclick="answerListening('${track.id}',${qi},${oi})">${o}</button>`).join('')}
      </div>
    </div>
  `).join('');
}
function answerListening(trackId,qi,oi){
  const track=LISTENING_TRACKS.find(t=>t.id===trackId);
  const correct=track.questions[qi].a;
  document.querySelectorAll(`[id^="lq_${trackId}_${qi}_"]`).forEach(b=>b.disabled=true);
  document.getElementById(`lq_${trackId}_${qi}_${oi}`).classList.add(oi===correct?'correct':'wrong');
  if(oi===correct){
    document.getElementById(`lq_${trackId}_${qi}_${correct}`).classList.add('correct');
    addXP(5); showToast(t('correct'),'success');
  } else {
    document.getElementById(`lq_${trackId}_${qi}_${correct}`).classList.add('correct');
  }
}
function togglePlay(id){
  const btn=document.getElementById(`playBtn_${id}`);
  const track=LISTENING_TRACKS.find(t=>t.id===id);
  if(state.audioPlaying&&state.currentAudio===id){
    window.speechSynthesis.cancel();
    state.audioPlaying=false; state.currentAudio=null;
    btn.textContent='▶';
    stopWaveAnim(id);
    return;
  }
  if(state.audioPlaying){
    window.speechSynthesis.cancel();
    stopWaveAnim(state.currentAudio);
    document.getElementById(`playBtn_${state.currentAudio}`).textContent='▶';
  }
  const utt=new SpeechSynthesisUtterance(track.text);
  utt.lang='en-US';
  utt.rate=parseFloat(document.querySelector(`#player_${id} .speed-btn.active`)?.textContent)||0.75;
  utt.onend=()=>{btn.textContent='▶';state.audioPlaying=false;state.currentAudio=null;stopWaveAnim(id);showToast('Listening complete! ✅','success');addXP(15);};
  window.speechSynthesis.speak(utt);
  state.audioPlaying=true; state.currentAudio=id;
  btn.textContent='⏸';
  startWaveAnim(id);
}
function startWaveAnim(id){
  const bars=document.querySelectorAll(`#waveBars_${id} .wave-bar`);
  wavAnimInterval=setInterval(()=>{bars.forEach(b=>{b.style.height=(Math.random()*30+5)+'px';});},120);
}
function stopWaveAnim(id){
  clearInterval(wavAnimInterval);
  const bars=document.querySelectorAll(`#waveBars_${id} .wave-bar`);
  bars.forEach(b=>{b.style.height='5px';});
}
function setSpeed(id,speed,btn){
  document.querySelectorAll(`#player_${id} .speed-btn`).forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  if(state.currentAudio===id&&state.audioPlaying){
    window.speechSynthesis.cancel();
    state.audioPlaying=false;
    document.getElementById(`playBtn_${id}`).textContent='▶';
    showToast('Speed changed. Press play again.','info');
  }
}
function toggleTranscript(id){
  const box=document.getElementById(`trans_${id}`);
  const tog=document.getElementById(`transToggle_${id}`);
  box.classList.toggle('show');
  tog.textContent=box.classList.contains('show')?t('hide_transcript'):t('show_transcript');
}

// ==================== READING ====================
function renderReading(){
  const c=document.getElementById('readingContent');
  let html='';
  READING_PASSAGES.forEach(pass=>{
    html+=`<div style="margin-bottom:20px">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
        <strong>${pass.title}</strong>
        <span style="font-size:.75rem;background:rgba(108,99,255,.2);padding:3px 10px;border-radius:8px;color:var(--primary)">${pass.level}</span>
      </div>
      <div class="reading-text"><h3>${t('read_passage')}</h3>${pass.text}</div>
      <div class="card" style="margin-top:0">
        <div class="card-title" style="font-size:.95rem">❓ ${t('read_questions')}</div>
        ${pass.questions.map((q,qi)=>`
          <div style="margin-bottom:14px">
            <div style="font-weight:700;font-size:.88rem;margin-bottom:8px">${qi+1}. ${q.q}</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              ${q.opts.map((o,oi)=>`<button class="option-btn" id="rq_${pass.id}_${qi}_${oi}" onclick="answerReading('${pass.id}',${qi},${oi})">${o}</button>`).join('')}
            </div>
          </div>`).join('')}
      </div>
    </div>`;
  });
  c.innerHTML=html;
}
function answerReading(pid,qi,oi){
  const pass=READING_PASSAGES.find(p=>p.id===pid);
  const correct=pass.questions[qi].a;
  document.querySelectorAll(`[id^="rq_${pid}_${qi}_"]`).forEach(b=>b.disabled=true);
  document.getElementById(`rq_${pid}_${qi}_${oi}`).classList.add(oi===correct?'correct':'wrong');
  if(oi!==correct) document.getElementById(`rq_${pid}_${qi}_${correct}`).classList.add('correct');
  if(oi===correct){addXP(5);showToast(t('correct'),'success');}
}
function showWordDef(e,word,pos,def){
  const popup=document.getElementById('wordPopup');
  popup.innerHTML=`<div class="w-word">${word}</div><div class="w-pron">${pos}</div><div class="w-def">${def}</div>`;
  popup.style.left=Math.min(e.pageX,window.innerWidth-240)+'px';
  popup.style.top=(e.pageY-80)+'px';
  popup.classList.add('show');
  setTimeout(()=>popup.classList.remove('show'),3000);
}

// ==================== SPEAKING ====================
function renderSpeaking(){
  state.speakConvHistory=[];
  state.currentSpeakPromptIdx=0;
  const c=document.getElementById('speakingContent');
  c.innerHTML=`
    <div class="speaking-card">
      <div style="text-align:left;margin-bottom:16px">
        <div style="font-size:.8rem;color:var(--primary);font-weight:700;margin-bottom:6px">${t('speak_prompt_label')}</div>
        <div class="conv-history" id="convHistory"></div>
      </div>
      <div class="mic-area" id="micArea" onclick="toggleSpeaking()">🎤</div>
      <div class="speaking-prompt" id="speakPrompt">${SPEAKING_PROMPTS[0].ai}</div>
      <div class="speaking-sub">${SPEAKING_PROMPTS[0].hint}</div>
      <div class="speaking-status" id="speakStatus"></div>
      <div class="speak-score" id="speakScore" style="display:none">
        <span class="score-pill acc" id="scoreAcc">Accuracy: -</span>
        <span class="score-pill flu" id="scoreFlu">Fluency: -</span>
        <span class="score-pill pron" id="scorePron">Pronunciation: -</span>
      </div>
    </div>
    <div class="card">
      <div class="card-title">💡 <span>Speaking Tips</span></div>
      <ul style="color:var(--text2);font-size:.88rem;padding-left:20px;line-height:2">
        <li>Speak clearly and at a natural pace</li>
        <li>Don't worry about making mistakes — they help you learn!</li>
        <li>Try to use complete sentences</li>
        <li>Practice the vocabulary from your lessons</li>
        <li>Record yourself and listen back</li>
      </ul>
    </div>
  `;
  addToConv('ai', SPEAKING_PROMPTS[0].ai);
  speakText(SPEAKING_PROMPTS[0].ai);
}

function addToConv(role, text){
  const h=document.getElementById('convHistory');
  if(!h)return;
  h.innerHTML+=`<div class="conv-msg ${role}"><div class="conv-bubble">${text}</div></div>`;
  h.scrollTop=h.scrollHeight;
  state.speakConvHistory.push({role,text});
}

function speakText(text){
  if(!window.speechSynthesis)return;
  window.speechSynthesis.cancel();
  const utt=new SpeechSynthesisUtterance(text);
  utt.lang='en-US'; utt.rate=0.9;
  const mic=document.getElementById('micArea');
  if(mic){mic.textContent='🔊';mic.classList.add('playing');}
  utt.onend=()=>{if(mic){mic.textContent='🎤';mic.classList.remove('playing');}};
  window.speechSynthesis.speak(utt);
}

function toggleSpeaking(){
  if(state.isRecording){
    stopRecording();
  } else {
    startRecording();
  }
}

function startRecording(){
  if(!('webkitSpeechRecognition' in window || 'SpeechRecognition' in window)){
    showToast('Speech recognition not supported in this browser. Try Chrome.','error');
    simulateSpeakResponse();
    return;
  }
  const SR=window.SpeechRecognition||window.webkitSpeechRecognition;
  state.recognition=new SR();
  state.recognition.lang='en-US';
  state.recognition.continuous=false;
  state.recognition.interimResults=false;
  state.recognition.onstart=()=>{
    state.isRecording=true;
    document.getElementById('micArea').classList.add('recording');
    document.getElementById('micArea').textContent='🔴';
    document.getElementById('speakStatus').textContent='🎤 Recording... Speak now!';
    document.getElementById('speakStatus').className='speaking-status';
  };
  state.recognition.onresult=(e)=>{
    const transcript=e.results[0][0].transcript;
    const confidence=e.results[0][0].confidence;
    handleSpeechResult(transcript, confidence);
  };
  state.recognition.onerror=(e)=>{
    stopRecording();
    showToast('Microphone error: '+e.error,'error');
    simulateSpeakResponse();
  };
  state.recognition.onend=()=>stopRecording();
  state.recognition.start();
}

function stopRecording(){
  state.isRecording=false;
  const mic=document.getElementById('micArea');
  if(mic){mic.classList.remove('recording');mic.textContent='🎤';}
  const st=document.getElementById('speakStatus');
  if(st)st.textContent='';
  if(state.recognition){try{state.recognition.stop();}catch(e){}}
}

function handleSpeechResult(transcript, confidence){
  addToConv('user', transcript);
  document.getElementById('speakStatus').textContent=t('ai_evaluating');
  evaluateSpeech(transcript, confidence);
}

function evaluateSpeech(transcript, confidence){
  const acc=Math.round((confidence||0.7)*100);
  const wordCount=transcript.split(' ').length;
  const flu=Math.min(100,Math.round(wordCount*10));
  const pron=Math.round(Math.random()*20+75);

  setTimeout(()=>{
    document.getElementById('speakScore').style.display='flex';
    document.getElementById('scoreAcc').textContent=`${t('accuracy2')}: ${acc}%`;
    document.getElementById('scoreFlu').textContent=`${t('fluency')}: ${flu}%`;
    document.getElementById('scorePron').textContent=`${t('pronunciation')}: ${pron}%`;
    document.getElementById('speakStatus').textContent='';
    addXP(10);

    // Move to next prompt
    state.currentSpeakPromptIdx=(state.currentSpeakPromptIdx+1)%SPEAKING_PROMPTS.length;
    const nextPrompt=SPEAKING_PROMPTS[state.currentSpeakPromptIdx];
    const responses=["Good answer! Let me ask you another question.","Interesting! Now tell me:", "Great! Next question:","Well done! Now answer this:","Very good! Keep going:"];
    const aiResp=responses[Math.floor(Math.random()*responses.length)]+' '+nextPrompt.ai;

    setTimeout(()=>{
      addToConv('ai', aiResp);
      document.getElementById('speakPrompt').textContent=nextPrompt.ai;
      speakText(aiResp);
    },800);
  },1000);
}

function simulateSpeakResponse(){
  // Fallback for browsers without speech recognition
  const transcript="[Simulated response - microphone not available in this browser]";
  addToConv('user', transcript);
  setTimeout(()=>{
    document.getElementById('speakScore').style.display='flex';
    document.getElementById('scoreAcc').textContent=`${t('accuracy2')}: 80%`;
    document.getElementById('scoreFlu').textContent=`${t('fluency')}: 75%`;
    document.getElementById('scorePron').textContent=`${t('pronunciation')}: 78%`;
    state.currentSpeakPromptIdx=(state.currentSpeakPromptIdx+1)%SPEAKING_PROMPTS.length;
    const next=SPEAKING_PROMPTS[state.currentSpeakPromptIdx];
    addToConv('ai', next.ai);
    document.getElementById('speakPrompt').textContent=next.ai;
    speakText(next.ai);
    addXP(10);
  },500);
}

// ==================== VOCABULARY ====================
function renderVocabulary(){
  const levels=['A1','A2','B1','B2','C1','C2'];
  const filter=document.getElementById('vocabFilter');
  filter.innerHTML=`<button class="vf-btn ${state.vocabFilter==='all'?'active':''}" onclick="setVocabFilter('all')">All</button>`+
    levels.map(l=>`<button class="vf-btn ${state.vocabFilter===l?'active':''}" onclick="setVocabFilter('${l}')">${l}</button>`).join('');
  filterVocab();
}
function setVocabFilter(f){
  state.vocabFilter=f;
  document.querySelectorAll('.vf-btn').forEach(b=>{
    b.classList.toggle('active',b.textContent===f||(f==='all'&&b.textContent==='All'));
  });
  filterVocab();
}
function filterVocab(){
  const search=document.getElementById('vocabSearch')?.value?.toLowerCase()||'';
  let words=VOCABULARY.filter(v=>{
    const matchLevel=state.vocabFilter==='all'||v.level===state.vocabFilter;
    const matchSearch=!search||v.word.includes(search)||v.trans[state.lang]?.toLowerCase().includes(search);
    return matchLevel&&matchSearch;
  });
  const grid=document.getElementById('vocabGrid');
  if(!grid)return;
  grid.innerHTML=words.map(v=>`
    <div class="vocab-card" onclick="this.classList.toggle('flipped')">
      <div class="vocab-level-badge">${v.level}</div>
      <div class="vocab-word">${v.word}</div>
      <div class="vocab-pron">${v.pron}</div>
      <div class="vocab-trans">${v.trans[state.lang]||v.trans.en}</div>
      <div style="font-size:.7rem;color:var(--text2);margin-top:4px">${t('tap_flip')}</div>
    </div>
  `).join('');
}

// ==================== LEADERBOARD ====================
function renderLeaderboard(){
  const players=[...FAKE_PLAYERS];
  players.find(p=>p.isMe).xp=state.xp;
  players.sort((a,b)=>b.xp-a.xp);
  const list=document.getElementById('lbList');
  list.innerHTML=players.map((p,i)=>{
    const rankClass=i===0?'gold':i===1?'silver':i===2?'bronze':'';
    return `<div class="lb-item ${p.isMe?'me':''}">
      <div class="lb-rank ${rankClass}">${i<3?['🥇','🥈','🥉'][i]:i+1}</div>
      <div class="lb-avatar" style="background:rgba(108,99,255,.2)">${p.avatar}</div>
      <div class="lb-info"><div class="lb-name">${p.name}${p.isMe?' (You)':''}</div><div class="lb-level">${p.level} · 🔥${p.streak} streak</div></div>
      <div class="lb-xp">⚡${p.xp.toLocaleString()} XP</div>
    </div>`;
  }).join('');
}

// ==================== AI CHAT ====================
const SYSTEM_PROMPT=`You are EnglishMaster AI, a friendly, encouraging, and highly skilled English language tutor. You help students of all levels (A1-C2) learn English. You:
- Answer grammar questions clearly with examples
- Explain vocabulary with context and usage
- Correct mistakes kindly and explain why
- Provide encouragement and motivation
- Give practice exercises when asked
- Explain differences between similar words/phrases
- Use simple language for beginners, advanced language for advanced students
- Always respond in the same language the student uses (English, Russian, or Uzbek)
- When correcting, always provide the correct version and explain the rule
- Give examples in multiple languages if it helps understanding`;

let chatHistory=[];

function initChat(){
  const msgs=document.getElementById('chatMessages');
  if(msgs&&msgs.children.length===0){
    addChatMsg('ai','👋 Hello! I\'m your AI English Tutor, available 24/7! Ask me anything about English grammar, vocabulary, pronunciation, or just practice conversation. What would you like to learn today? 🎓');
    chatHistory=[{role:'user',content:'Hello!'},{role:'assistant',content:'Hello! I\'m your AI English Tutor! How can I help you?'}];
  }
}

function addChatMsg(role,text){
  const msgs=document.getElementById('chatMessages');
  const now=new Date().toLocaleTimeString([],{hour:'2-digit',minute:'2-digit'});
  msgs.innerHTML+=`<div class="chat-msg ${role}"><div class="chat-bubble">${text}</div><div class="chat-time">${now}</div></div>`;
  msgs.scrollTop=msgs.scrollHeight;
}

async function sendChat(){
  const input=document.getElementById('chatInput');
  const msg=input.value.trim();
  if(!msg)return;
  input.value='';
  addChatMsg('user',msg);
  chatHistory.push({role:'user',content:msg});

  // Show typing
  const msgs=document.getElementById('chatMessages');
  const typingId='typing_'+Date.now();
  msgs.innerHTML+=`<div class="chat-msg ai" id="${typingId}"><div class="chat-bubble"><span class="typing-dot"></span><span class="typing-dot"></span><span class="typing-dot"></span></div></div>`;
  msgs.scrollTop=msgs.scrollHeight;

  try {
    const resp=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',
        max_tokens:1000,
        system:SYSTEM_PROMPT,
        messages:chatHistory.slice(-20)
      })
    });
    const data=await resp.json();
    const reply=data.content?.[0]?.text||"I'm having trouble connecting. Please try again!";
    document.getElementById(typingId)?.remove();
    addChatMsg('ai',reply);
    chatHistory.push({role:'assistant',content:reply});
  } catch(e){
    document.getElementById(typingId)?.remove();
    // Fallback smart responses
    const fallback=getSmartFallback(msg);
    addChatMsg('ai',fallback);
    chatHistory.push({role:'assistant',content:fallback});
  }
}

function getSmartFallback(msg){
  const m=msg.toLowerCase();
  if(m.includes('hello')||m.includes('hi')||m.includes('привет')||m.includes('salom'))
    return "Hello! Great to meet you! What English topic would you like to explore today? 😊";
  if(m.includes('grammar')||m.includes('граммат'))
    return "I'd love to help with grammar! English grammar includes tenses, articles, prepositions, modal verbs, and much more. Which topic confuses you most?";
  if(m.includes('tense')||m.includes('время'))
    return "Tenses in English! There are 12 main tenses. The most common are: Present Simple (I work), Present Continuous (I am working), Past Simple (I worked), Present Perfect (I have worked), and Future (I will work). Which one would you like to study?";
  if(m.includes('vocabulary')||m.includes('word')||m.includes('словар'))
    return "Building vocabulary is essential! Tips: 1) Read extensively 2) Use new words in sentences 3) Use flashcards 4) Learn words in context 5) Review regularly. The vocabulary section has 500+ words organized by level!";
  if(m.includes('pronunciation')||m.includes('произношен'))
    return "Pronunciation tips: 1) Listen to native speakers 2) Mimic their rhythm 3) Practice minimal pairs (ship/sheep) 4) Record yourself 5) Use the Speaking section to practice! Would you like to know about any specific sounds?";
  if(m.includes('article')||m.includes('артикл'))
    return "Articles in English: A/AN = indefinite (first mention or not specific). THE = definite (specific, already mentioned). No article = generic nouns. Examples: 'I saw A dog. THE dog was black. Dogs are loyal.'";
  if(m.includes('present perfect')||m.includes('перфект'))
    return "Present Perfect: have/has + past participle. Used for: past actions with present relevance, life experiences, and unfinished time periods. Example: 'I have visited Paris' (life experience). 'She has just called' (recent past). 'We have known each other for 10 years' (ongoing).";
  if(m.includes('passive')||m.includes('пассив'))
    return "Passive Voice: Be + past participle. We use it when the action is more important than the doer. Active: 'Shakespeare wrote Hamlet.' Passive: 'Hamlet was written by Shakespeare.' For different tenses: Present: 'is written', Past: 'was written', Perfect: 'has been written'.";
  return "That's a great question! As your English tutor, I'm here 24/7 to help. Could you be more specific about what you'd like to learn? You can ask about grammar rules, vocabulary, pronunciation, or anything else about English! 🎓";
}

// ==================== PROGRESS ====================
function renderProgress(){
  const grid=document.getElementById('progressGrid');
  const skills=[
    {name:'Vocabulary',pct:Math.min(100,VOCABULARY.length>0?30:0)},
    {name:'Grammar',pct:Math.min(100,Math.round(state.completedTopics.length*8))},
    {name:'Listening',pct:Math.min(100,state.xp>100?45:15)},
    {name:'Reading',pct:Math.min(100,state.xp>200?60:20)},
    {name:'Speaking',pct:Math.min(100,state.xp>50?35:10)},
    {name:'Overall',pct:Math.min(100,Math.round(state.correctAnswers/(state.totalAnswers||1)*100))},
  ];
  grid.innerHTML=skills.map(s=>{
    const r=28, c=2*Math.PI*r, fill=c-c*s.pct/100;
    return `<div class="prog-card">
      <div class="prog-card-title">📊 ${s.name}</div>
      <div class="prog-ring">
        <svg viewBox="0 0 70 70" width="70" height="70">
          <circle class="bg" cx="35" cy="35" r="${r}" stroke="rgba(255,255,255,.1)"/>
          <circle class="fill" cx="35" cy="35" r="${r}" stroke="${s.pct>70?'var(--accent)':s.pct>40?'var(--primary)':'var(--orange)'}"
            stroke-dasharray="${c}" stroke-dashoffset="${fill}" style="stroke-linecap:round"/>
        </svg>
      </div>
      <div class="prog-pct">${s.pct}%</div>
    </div>`;
  }).join('');
}

// ==================== DAILY CHALLENGE ====================
const DAILY_CHALLENGES=[
  "What is the past tense of 'go'?",
  "Use 'have been' in a sentence.",
  "What's the difference between 'make' and 'do'?",
  "Translate: 'I will have finished by noon.'",
  "Give 3 examples of modal verbs.",
  "What is a relative clause? Give an example.",
  "Use the passive voice: 'Someone stole my wallet.'",
  "What does 'nevertheless' mean?",
];
document.getElementById('dailyChallengeText').textContent=
  DAILY_CHALLENGES[new Date().getDate()%DAILY_CHALLENGES.length];

// ==================== RECENT ACTIVITY ====================
function renderRecentActivity(){
  const container=document.getElementById('recentActivity');
  const activities=[
    {icon:'✅',text:'Completed Greetings lesson',time:'Today'},
    {icon:'⚡',text:`Earned ${state.xp} total XP`,time:'Today'},
    {icon:'🎯',text:`${state.lessonsCompleted} lessons finished`,time:'All time'},
    {icon:'📊',text:`${state.totalAnswers>0?Math.round(state.correctAnswers/state.totalAnswers*100):0}% accuracy rate`,time:'All time'},
  ];
  container.innerHTML=activities.map(a=>`
    <div class="topic-item" style="cursor:default">
      <div class="topic-icon">${a.icon}</div>
      <div class="topic-info"><div class="topic-title">${a.text}</div><div class="topic-subtitle">${a.time}</div></div>
    </div>
  `).join('');
}

// ==================== INIT ====================
updateHomeStats();
renderRecentActivity();
showSection('home');
applyTranslations();

// Close word popup on click outside
document.addEventListener('click',e=>{
  if(!e.target.classList.contains('highlight-word'))
    document.getElementById('wordPopup')?.classList.remove('show');
});
</script>
</body>
</html>
