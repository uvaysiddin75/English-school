<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SpeakUP English</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #0a0e1a;
  --surface: #111827;
  --surface2: #1a2235;
  --accent: #00d4ff;
  --accent2: #7c3aed;
  --accent3: #10b981;
  --accent4: #f59e0b;
  --accent5: #ef4444;
  --text: #f0f4ff;
  --text2: #94a3b8;
  --border: rgba(255,255,255,0.08);
  --glow: 0 0 30px rgba(0,212,255,0.15);
  --radius: 16px;
}
* { margin:0;padding:0;box-sizing:border-box; }
body {
  font-family:'Sora',sans-serif;
  background:var(--bg);
  color:var(--text);
  min-height:100vh;
  overflow-x:hidden;
}
body::before {
  content:'';
  position:fixed;top:0;left:0;right:0;bottom:0;
  background: radial-gradient(ellipse at 20% 20%, rgba(124,58,237,0.08) 0%, transparent 50%),
              radial-gradient(ellipse at 80% 80%, rgba(0,212,255,0.06) 0%, transparent 50%);
  pointer-events:none;z-index:0;
}

/* NAV */
nav {
  position:sticky;top:0;z-index:100;
  background:rgba(10,14,26,0.95);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);
  padding:0 24px;
  display:flex;align-items:center;justify-content:space-between;
  height:64px;
}
.logo {
  font-size:1.4rem;font-weight:800;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  letter-spacing:-0.5px;
}
.nav-right { display:flex;align-items:center;gap:12px; }
.lang-btn {
  background:var(--surface2);border:1px solid var(--border);
  color:var(--text2);padding:6px 14px;border-radius:8px;
  cursor:pointer;font-family:'Sora',sans-serif;font-size:0.8rem;
  transition:all 0.2s;
}
.lang-btn.active,.lang-btn:hover {
  background:var(--accent);color:#000;border-color:var(--accent);
}
.progress-badge {
  background:linear-gradient(135deg,var(--accent2),var(--accent));
  padding:6px 14px;border-radius:8px;font-size:0.8rem;font-weight:700;
}

/* MAIN TABS */
.main-tabs {
  display:flex;gap:4px;padding:16px 24px 0;
  overflow-x:auto;scrollbar-width:none;
  border-bottom:1px solid var(--border);
  position:relative;z-index:1;
}
.main-tabs::-webkit-scrollbar { display:none; }
.tab-btn {
  background:none;border:none;color:var(--text2);
  padding:10px 18px;border-radius:10px 10px 0 0;
  cursor:pointer;font-family:'Sora',sans-serif;font-size:0.85rem;font-weight:600;
  white-space:nowrap;transition:all 0.2s;
  display:flex;align-items:center;gap:6px;
  border-bottom:2px solid transparent;
}
.tab-btn.active { color:var(--accent);border-bottom-color:var(--accent);background:rgba(0,212,255,0.06); }
.tab-btn:hover:not(.active) { color:var(--text);background:var(--surface2); }

/* MAIN CONTENT */
.main-content { padding:24px;position:relative;z-index:1;max-width:1200px;margin:0 auto; }
.tab-content { display:none; }
.tab-content.active { display:block; }

/* HERO */
.hero {
  background:linear-gradient(135deg,var(--surface) 0%,var(--surface2) 100%);
  border:1px solid var(--border);border-radius:20px;padding:40px;
  margin-bottom:24px;position:relative;overflow:hidden;
}
.hero::before {
  content:'';position:absolute;top:-50%;right:-20%;
  width:400px;height:400px;
  background:radial-gradient(circle,rgba(0,212,255,0.1) 0%,transparent 70%);
}
.hero h1 { font-size:2.2rem;font-weight:800;line-height:1.2;margin-bottom:8px; }
.hero h1 span { background:linear-gradient(135deg,var(--accent),var(--accent2));-webkit-background-clip:text;-webkit-text-fill-color:transparent; }
.hero p { color:var(--text2);font-size:1rem;margin-bottom:24px; }
.stats-row { display:flex;gap:24px;flex-wrap:wrap; }
.stat-item { text-align:center; }
.stat-num { font-size:1.8rem;font-weight:800;color:var(--accent); }
.stat-label { font-size:0.75rem;color:var(--text2);margin-top:2px; }

/* TOPICS GRID */
.section-title {
  font-size:1.1rem;font-weight:700;margin-bottom:16px;
  display:flex;align-items:center;gap:8px;
}
.section-title::before {
  content:'';width:4px;height:20px;
  background:linear-gradient(var(--accent),var(--accent2));
  border-radius:2px;
}
.topics-grid {
  display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:16px;
  margin-bottom:32px;
}
.topic-card {
  background:var(--surface);border:1px solid var(--border);
  border-radius:var(--radius);padding:20px;cursor:pointer;
  transition:all 0.3s;position:relative;overflow:hidden;
}
.topic-card::before {
  content:'';position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(90deg,var(--c1,var(--accent)),var(--c2,var(--accent2)));
}
.topic-card:hover { transform:translateY(-3px);border-color:rgba(0,212,255,0.3);box-shadow:var(--glow); }
.topic-icon { font-size:2rem;margin-bottom:12px; }
.topic-title { font-size:1rem;font-weight:700;margin-bottom:4px; }
.topic-desc { font-size:0.8rem;color:var(--text2);margin-bottom:12px;line-height:1.5; }
.topic-meta { display:flex;align-items:center;justify-content:space-between; }
.topic-level {
  font-size:0.7rem;font-weight:700;padding:3px 8px;border-radius:4px;
  background:rgba(0,212,255,0.1);color:var(--accent);
}
.topic-progress { font-size:0.75rem;color:var(--text2); }
.progress-bar {
  height:4px;background:var(--surface2);border-radius:2px;margin-top:10px;overflow:hidden;
}
.progress-fill {
  height:100%;border-radius:2px;transition:width 0.5s;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
}
.completed-badge {
  position:absolute;top:12px;right:12px;
  background:var(--accent3);color:#000;font-size:0.65rem;font-weight:700;
  padding:2px 6px;border-radius:4px;
}

/* LESSON MODAL */
.modal-overlay {
  display:none;position:fixed;inset:0;z-index:200;
  background:rgba(0,0,0,0.85);backdrop-filter:blur(8px);
  padding:20px;align-items:flex-start;justify-content:center;
  overflow-y:auto;
}
.modal-overlay.show { display:flex; }
.modal {
  background:var(--surface);border:1px solid var(--border);
  border-radius:20px;width:100%;max-width:780px;
  margin:auto;animation:slideUp 0.3s ease;
}
@keyframes slideUp { from{transform:translateY(30px);opacity:0} to{transform:translateY(0);opacity:1} }
.modal-header {
  padding:24px 28px;border-bottom:1px solid var(--border);
  display:flex;justify-content:space-between;align-items:center;
}
.modal-header h2 { font-size:1.3rem;font-weight:700; }
.modal-close {
  background:var(--surface2);border:none;color:var(--text2);
  width:36px;height:36px;border-radius:8px;cursor:pointer;font-size:1.2rem;
  display:flex;align-items:center;justify-content:center;transition:all 0.2s;
}
.modal-close:hover { background:var(--accent5);color:#fff; }
.modal-body { padding:28px;max-height:70vh;overflow-y:auto; }
.lesson-content { line-height:1.8;color:var(--text2); }
.lesson-content h3 { color:var(--text);font-size:1.1rem;margin:20px 0 10px;font-weight:700; }
.lesson-content p { margin-bottom:12px;font-size:0.9rem; }
.lesson-content .highlight {
  background:rgba(0,212,255,0.08);border-left:3px solid var(--accent);
  padding:12px 16px;border-radius:0 8px 8px 0;margin:12px 0;font-size:0.85rem;
}
.example-box {
  background:var(--surface2);border:1px solid var(--border);
  border-radius:12px;padding:16px;margin:12px 0;
}
.example-box .en { font-size:0.95rem;font-weight:600;color:var(--accent);margin-bottom:4px; }
.example-box .tr { font-size:0.85rem;color:var(--text2); }
.vocab-table { width:100%;border-collapse:collapse;margin:12px 0; }
.vocab-table th { background:var(--surface2);padding:10px 14px;text-align:left;font-size:0.8rem;color:var(--text2); }
.vocab-table td { padding:10px 14px;border-bottom:1px solid var(--border);font-size:0.85rem; }
.vocab-table tr:last-child td { border-bottom:none; }
.btn-start-test {
  display:block;width:100%;padding:14px;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  border:none;border-radius:12px;color:#fff;font-size:1rem;font-weight:700;
  cursor:pointer;margin-top:20px;transition:all 0.2s;font-family:'Sora',sans-serif;
}
.btn-start-test:hover { transform:scale(1.02);box-shadow:var(--glow); }

/* TEST MODAL */
.test-modal {
  background:var(--surface);border:1px solid var(--border);
  border-radius:20px;width:100%;max-width:720px;margin:auto;
  animation:slideUp 0.3s ease;
}
.test-header { padding:20px 24px;border-bottom:1px solid var(--border); }
.test-progress-info { display:flex;justify-content:space-between;align-items:center;margin-bottom:12px; }
.q-counter { font-size:0.85rem;color:var(--text2); }
.q-counter span { color:var(--accent);font-weight:700; }
.test-progress-bar { height:6px;background:var(--surface2);border-radius:3px;overflow:hidden; }
.test-progress-fill { height:100%;border-radius:3px;transition:width 0.4s;background:linear-gradient(90deg,var(--accent),var(--accent2)); }
.test-body { padding:24px; }
.question-text { font-size:1rem;font-weight:600;margin-bottom:20px;line-height:1.5; }
.options-list { display:flex;flex-direction:column;gap:10px; }
.option-btn {
  background:var(--surface2);border:1px solid var(--border);
  border-radius:12px;padding:14px 18px;text-align:left;cursor:pointer;
  color:var(--text);font-family:'Sora',sans-serif;font-size:0.9rem;
  transition:all 0.2s;
}
.option-btn:hover:not(:disabled) { border-color:var(--accent);background:rgba(0,212,255,0.05); }
.option-btn.correct { background:rgba(16,185,129,0.15);border-color:var(--accent3);color:var(--accent3); }
.option-btn.wrong { background:rgba(239,68,68,0.15);border-color:var(--accent5);color:var(--accent5); }
.option-btn:disabled { cursor:default; }
.answer-feedback {
  margin-top:16px;padding:14px;border-radius:10px;font-size:0.85rem;display:none;
}
.answer-feedback.show { display:block; }
.answer-feedback.correct { background:rgba(16,185,129,0.1);border:1px solid rgba(16,185,129,0.3);color:var(--accent3); }
.answer-feedback.wrong { background:rgba(239,68,68,0.1);border:1px solid rgba(239,68,68,0.3);color:var(--accent5); }
.btn-next {
  display:none;width:100%;padding:12px;margin-top:16px;
  background:var(--accent2);border:none;border-radius:12px;
  color:#fff;font-family:'Sora',sans-serif;font-size:0.9rem;font-weight:700;cursor:pointer;
  transition:all 0.2s;
}
.btn-next.show { display:block; }
.btn-next:hover { background:var(--accent); }

/* RESULTS */
.results-view { text-align:center;padding:40px 24px; }
.results-score {
  width:140px;height:140px;border-radius:50%;
  background:conic-gradient(var(--accent) 0deg, var(--surface2) 0deg);
  display:flex;align-items:center;justify-content:center;
  margin:0 auto 24px;position:relative;
}
.results-score::before {
  content:'';position:absolute;
  width:116px;height:116px;border-radius:50%;background:var(--surface);
}
.score-text { position:relative;z-index:1; }
.score-num { font-size:2.2rem;font-weight:800;color:var(--accent); }
.score-label { font-size:0.75rem;color:var(--text2); }
.results-title { font-size:1.4rem;font-weight:700;margin-bottom:8px; }
.results-grade { font-size:1rem;color:var(--text2);margin-bottom:24px; }
.ai-feedback {
  background:var(--surface2);border:1px solid var(--border);border-radius:16px;
  padding:20px;text-align:left;margin-bottom:24px;
}
.ai-feedback-title { display:flex;align-items:center;gap:8px;font-weight:700;margin-bottom:12px; }
.ai-badge { background:linear-gradient(135deg,var(--accent2),var(--accent));padding:3px 8px;border-radius:4px;font-size:0.7rem; }
.ai-feedback-text { font-size:0.875rem;color:var(--text2);line-height:1.6; }
.results-actions { display:flex;gap:12px;justify-content:center;flex-wrap:wrap; }
.btn-action {
  padding:12px 24px;border-radius:12px;font-family:'Sora',sans-serif;font-size:0.9rem;font-weight:700;cursor:pointer;transition:all 0.2s;
}
.btn-primary { background:linear-gradient(135deg,var(--accent),var(--accent2));border:none;color:#fff; }
.btn-secondary { background:var(--surface2);border:1px solid var(--border);color:var(--text); }
.btn-primary:hover,.btn-secondary:hover { transform:scale(1.03); }

/* LISTENING */
.audio-player {
  background:var(--surface2);border:1px solid var(--border);border-radius:16px;
  padding:20px;margin-bottom:20px;
}
.audio-wave {
  display:flex;align-items:center;justify-content:center;gap:3px;
  height:40px;margin:12px 0;
}
.wave-bar {
  width:4px;border-radius:2px;background:var(--accent);opacity:0.4;
  animation:wave 1.2s ease-in-out infinite;
}
.wave-bar:nth-child(1){height:12px;animation-delay:0s}
.wave-bar:nth-child(2){height:22px;animation-delay:0.1s}
.wave-bar:nth-child(3){height:30px;animation-delay:0.2s}
.wave-bar:nth-child(4){height:18px;animation-delay:0.3s}
.wave-bar:nth-child(5){height:36px;animation-delay:0.4s}
.wave-bar:nth-child(6){height:24px;animation-delay:0.5s}
.wave-bar:nth-child(7){height:14px;animation-delay:0.4s}
.wave-bar:nth-child(8){height:28px;animation-delay:0.3s}
.wave-bar:nth-child(9){height:20px;animation-delay:0.2s}
.wave-bar:nth-child(10){height:10px;animation-delay:0.1s}
@keyframes wave { 0%,100%{opacity:0.4;transform:scaleY(1)} 50%{opacity:1;transform:scaleY(1.3)} }
.audio-playing .wave-bar { opacity:1; }
.audio-controls { display:flex;align-items:center;gap:12px; }
.play-btn {
  width:48px;height:48px;border-radius:50%;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  border:none;color:#fff;font-size:1.1rem;cursor:pointer;
  display:flex;align-items:center;justify-content:center;transition:all 0.2s;flex-shrink:0;
}
.play-btn:hover { transform:scale(1.1); }
.audio-info { flex:1; }
.audio-title { font-weight:600;font-size:0.9rem;margin-bottom:4px; }
.audio-duration { font-size:0.75rem;color:var(--text2); }
.audio-track { height:4px;background:var(--surface);border-radius:2px;margin-top:8px;cursor:pointer; }
.audio-track-fill { height:100%;width:0%;background:var(--accent);border-radius:2px;transition:width 0.1s; }

/* READING */
.reading-card {
  background:var(--surface);border:1px solid var(--border);border-radius:16px;margin-bottom:20px;overflow:hidden;
}
.reading-card-header { padding:16px 20px;background:var(--surface2);display:flex;justify-content:space-between;align-items:center; }
.reading-tag { font-size:0.7rem;font-weight:700;padding:3px 8px;border-radius:4px; }
.reading-body { padding:20px;font-size:0.9rem;line-height:1.8;color:var(--text2); }
.reading-body .word-highlight { color:var(--accent);cursor:help;border-bottom:1px dashed var(--accent); }

/* WRITING */
.writing-prompt {
  background:linear-gradient(135deg,rgba(124,58,237,0.1),rgba(0,212,255,0.05));
  border:1px solid rgba(124,58,237,0.3);border-radius:16px;padding:20px;margin-bottom:16px;
}
.writing-prompt h3 { font-size:1rem;font-weight:700;margin-bottom:8px; }
.writing-prompt p { font-size:0.85rem;color:var(--text2);line-height:1.6; }
.writing-area {
  width:100%;background:var(--surface2);border:1px solid var(--border);
  border-radius:12px;padding:16px;color:var(--text);font-family:'Sora',sans-serif;
  font-size:0.9rem;line-height:1.7;resize:vertical;min-height:160px;transition:border-color 0.2s;
}
.writing-area:focus { outline:none;border-color:var(--accent); }
.writing-meta { display:flex;justify-content:space-between;align-items:center;margin-top:8px; }
.word-count { font-size:0.75rem;color:var(--text2); }
.btn-check-writing {
  padding:10px 20px;background:var(--accent2);border:none;border-radius:10px;
  color:#fff;font-family:'Sora',sans-serif;font-size:0.85rem;font-weight:600;cursor:pointer;
}
.ai-writing-feedback {
  background:var(--surface2);border:1px solid var(--border);border-radius:12px;padding:16px;margin-top:12px;display:none;
}
.ai-writing-feedback.show { display:block; }

/* VOCABULARY */
.vocab-card-grid { display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px;margin-bottom:20px; }
.vocab-card {
  background:var(--surface);border:1px solid var(--border);border-radius:12px;
  padding:16px;cursor:pointer;transition:all 0.3s;perspective:600px;min-height:120px;position:relative;
}
.vocab-card.flipped .vc-front { display:none; }
.vocab-card.flipped .vc-back { display:block; }
.vc-front,.vc-back { }
.vc-back { display:none; }
.vocab-card:hover { border-color:var(--accent); }
.vc-word { font-size:1.1rem;font-weight:700;color:var(--accent);margin-bottom:6px; }
.vc-phonetic { font-size:0.75rem;color:var(--text2);margin-bottom:8px;font-family:'Space Mono',monospace; }
.vc-type { font-size:0.7rem;background:rgba(124,58,237,0.2);color:var(--accent2);padding:2px 6px;border-radius:4px;display:inline-block; }
.vc-translation { font-size:1rem;font-weight:600;color:var(--accent3); }
.vc-example { font-size:0.78rem;color:var(--text2);margin-top:6px;line-height:1.5; }
.flip-hint { font-size:0.7rem;color:var(--text2);margin-top:8px;opacity:0.6; }

/* GRAMMAR */
.grammar-rule {
  background:var(--surface);border:1px solid var(--border);border-radius:16px;
  overflow:hidden;margin-bottom:16px;
}
.grammar-rule-header {
  padding:14px 18px;background:var(--surface2);
  display:flex;justify-content:space-between;align-items:center;cursor:pointer;
}
.grammar-rule-title { font-weight:700;font-size:0.95rem; }
.grammar-rule-body { padding:18px;display:none;line-height:1.7;font-size:0.875rem;color:var(--text2); }
.grammar-rule-body.open { display:block; }
.grammar-table { width:100%;border-collapse:collapse;margin:12px 0; }
.grammar-table th { background:rgba(0,212,255,0.1);color:var(--accent);padding:8px 12px;text-align:left;font-size:0.8rem; }
.grammar-table td { padding:8px 12px;border-bottom:1px solid var(--border);font-size:0.82rem; }

/* SPEAKING */
.speaking-topic {
  background:var(--surface);border:1px solid var(--border);border-radius:16px;padding:20px;margin-bottom:16px;
}
.speaking-topic h3 { font-size:1rem;font-weight:700;margin-bottom:8px; }
.speaking-bullets { list-style:none;padding:0; }
.speaking-bullets li { padding:6px 0;color:var(--text2);font-size:0.875rem; }
.speaking-bullets li::before { content:'🎯 ';margin-right:6px; }
.record-btn {
  display:flex;align-items:center;gap:10px;background:rgba(239,68,68,0.1);
  border:1px solid rgba(239,68,68,0.3);border-radius:12px;padding:12px 20px;
  color:#f87171;font-family:'Sora',sans-serif;font-size:0.875rem;font-weight:600;
  cursor:pointer;margin-top:12px;transition:all 0.2s;
}
.record-btn:hover { background:rgba(239,68,68,0.2); }
.record-dot { width:10px;height:10px;border-radius:50%;background:#ef4444; }
.record-btn.recording .record-dot { animation:pulse 1s infinite; }
@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }

/* LEADERBOARD */
.leaderboard-item {
  background:var(--surface);border:1px solid var(--border);border-radius:12px;
  padding:14px 18px;display:flex;align-items:center;gap:14px;margin-bottom:10px;
  transition:all 0.2s;
}
.leaderboard-item:hover { border-color:var(--border);transform:translateX(4px); }
.rank-num { font-size:1.1rem;font-weight:800;width:32px;text-align:center; }
.rank-1 { color:#f59e0b; }
.rank-2 { color:#94a3b8; }
.rank-3 { color:#b45309; }
.rank-avatar { width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:1.2rem;flex-shrink:0; }
.rank-info { flex:1; }
.rank-name { font-weight:600;font-size:0.9rem; }
.rank-details { font-size:0.75rem;color:var(--text2);margin-top:2px; }
.rank-score { font-size:1rem;font-weight:700;color:var(--accent); }

/* PROFILE */
.profile-header { display:flex;align-items:center;gap:20px;margin-bottom:24px; }
.profile-avatar {
  width:80px;height:80px;border-radius:20px;
  background:linear-gradient(135deg,var(--accent2),var(--accent));
  display:flex;align-items:center;justify-content:center;font-size:2rem;flex-shrink:0;
}
.profile-name { font-size:1.4rem;font-weight:700; }
.profile-level { color:var(--text2);font-size:0.85rem;margin-top:4px; }
.achievements-grid { display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:12px; }
.achievement-item {
  background:var(--surface);border:1px solid var(--border);border-radius:12px;
  padding:16px;text-align:center;
}
.achievement-icon { font-size:2rem;margin-bottom:8px; }
.achievement-name { font-size:0.8rem;font-weight:600;margin-bottom:4px; }
.achievement-desc { font-size:0.7rem;color:var(--text2); }
.achievement-item.locked { opacity:0.4; }

/* LOADING */
.loading-indicator {
  display:flex;align-items:center;gap:8px;color:var(--text2);font-size:0.85rem;padding:8px 0;
}
.loading-dots span {
  display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--accent);
  animation:dotBounce 1.2s ease-in-out infinite;
}
.loading-dots span:nth-child(2){animation-delay:0.2s}
.loading-dots span:nth-child(3){animation-delay:0.4s}
@keyframes dotBounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}

/* SCROLLBAR */
::-webkit-scrollbar{width:6px;height:6px}
::-webkit-scrollbar-track{background:var(--surface)}
::-webkit-scrollbar-thumb{background:var(--surface2);border-radius:3px}
::-webkit-scrollbar-thumb:hover{background:var(--accent2)}

/* RESPONSIVE */
@media(max-width:600px){
  nav{padding:0 16px}.main-content{padding:16px}
  .hero h1{font-size:1.5rem}.hero{padding:24px}
  .topics-grid{grid-template-columns:1fr}
}
.shimmer {
  background:linear-gradient(90deg,var(--surface2) 0%,rgba(0,212,255,0.05) 50%,var(--surface2) 100%);
  background-size:200% 100%;animation:shimmer 1.5s infinite;border-radius:8px;color:transparent;
}
@keyframes shimmer{0%{background-position:200% 0}100%{background-position:-200% 0}}
</style>
</head>
<body>

<nav>
  <div class="logo">⚡ SpeakUP English</div>
  <div class="nav-right">
    <button class="lang-btn active" onclick="setLang('en')">EN</button>
    <button class="lang-btn" onclick="setLang('ru')">RU</button>
    <button class="lang-btn" onclick="setLang('uz')">UZ</button>
    <div class="progress-badge" id="totalProgressBadge">0 XP</div>
  </div>
</nav>

<div class="main-tabs">
  <button class="tab-btn active" onclick="switchTab('home')" id="tabHome">🏠 <span data-t="home">Home</span></button>
  <button class="tab-btn" onclick="switchTab('lessons')" id="tabLessons">📚 <span data-t="lessons">Lessons</span></button>
  <button class="tab-btn" onclick="switchTab('listening')" id="tabListening">🎧 <span data-t="listening">Listening</span></button>
  <button class="tab-btn" onclick="switchTab('reading')" id="tabReading">📖 <span data-t="reading">Reading</span></button>
  <button class="tab-btn" onclick="switchTab('writing')" id="tabWriting">✍️ <span data-t="writing">Writing</span></button>
  <button class="tab-btn" onclick="switchTab('vocabulary')" id="tabVocab">📝 <span data-t="vocabulary">Vocabulary</span></button>
  <button class="tab-btn" onclick="switchTab('grammar')" id="tabGrammar">📐 <span data-t="grammar">Grammar</span></button>
  <button class="tab-btn" onclick="switchTab('speaking')" id="tabSpeaking">🎤 <span data-t="speaking">Speaking</span></button>
  <button class="tab-btn" onclick="switchTab('leaderboard')" id="tabBoard">🏆 <span data-t="leaderboard">Leaderboard</span></button>
  <button class="tab-btn" onclick="switchTab('profile')" id="tabProfile">👤 <span data-t="profile">Profile</span></button>
</div>

<div class="main-content">

<!-- HOME TAB -->
<div class="tab-content active" id="tab-home">
  <div class="hero">
    <h1 data-t="heroTitle">Master <span>English</span> Like a Pro</h1>
    <p data-t="heroDesc">AI-powered lessons, adaptive tests, and real-time feedback. Your path to fluency starts here.</p>
    <div class="stats-row">
      <div class="stat-item"><div class="stat-num" id="totalTopics">12</div><div class="stat-label" data-t="topics">Topics</div></div>
      <div class="stat-item"><div class="stat-num" id="completedTopics">0</div><div class="stat-label" data-t="completed">Completed</div></div>
      <div class="stat-item"><div class="stat-num" id="avgScore">—</div><div class="stat-label" data-t="avgScore">Avg Score</div></div>
      <div class="stat-item"><div class="stat-num" id="totalXP">0</div><div class="stat-label">XP</div></div>
    </div>
  </div>
  <div class="section-title" data-t="continueLearn">Continue Learning</div>
  <div class="topics-grid" id="homeTopicsGrid"></div>
</div>

<!-- LESSONS TAB -->
<div class="tab-content" id="tab-lessons">
  <div class="section-title" data-t="allTopics">All Topics</div>
  <div class="topics-grid" id="allTopicsGrid"></div>
</div>

<!-- LISTENING TAB -->
<div class="tab-content" id="tab-listening">
  <div class="section-title" data-t="listeningTitle">Listening Exercises</div>
  <div id="listeningContent"></div>
</div>

<!-- READING TAB -->
<div class="tab-content" id="tab-reading">
  <div class="section-title" data-t="readingTitle">Reading Passages</div>
  <div id="readingContent"></div>
</div>

<!-- WRITING TAB -->
<div class="tab-content" id="tab-writing">
  <div class="section-title" data-t="writingTitle">Writing Practice</div>
  <div id="writingContent"></div>
</div>

<!-- VOCABULARY TAB -->
<div class="tab-content" id="tab-vocabulary">
  <div class="section-title" data-t="vocabTitle">Vocabulary Cards</div>
  <p style="color:var(--text2);font-size:0.85rem;margin-bottom:16px;" data-t="vocabHint">Click a card to see the translation</p>
  <div class="vocab-card-grid" id="vocabGrid"></div>
</div>

<!-- GRAMMAR TAB -->
<div class="tab-content" id="tab-grammar">
  <div class="section-title" data-t="grammarTitle">Grammar Rules</div>
  <div id="grammarContent"></div>
</div>

<!-- SPEAKING TAB -->
<div class="tab-content" id="tab-speaking">
  <div class="section-title" data-t="speakingTitle">Speaking Practice</div>
  <div id="speakingContent"></div>
</div>

<!-- LEADERBOARD TAB -->
<div class="tab-content" id="tab-leaderboard">
  <div class="section-title" data-t="topStudents">Top Students</div>
  <div id="leaderboardList"></div>
</div>

<!-- PROFILE TAB -->
<div class="tab-content" id="tab-profile">
  <div class="profile-header">
    <div class="profile-avatar">🎓</div>
    <div>
      <div class="profile-name" data-t="profileName">English Learner</div>
      <div class="profile-level" id="profileLevel">Level 1 — Beginner</div>
    </div>
  </div>
  <div class="section-title" data-t="achievements">Achievements</div>
  <div class="achievements-grid" id="achievementsGrid"></div>
</div>

</div><!-- /main-content -->

<!-- LESSON MODAL -->
<div class="modal-overlay" id="lessonModal">
  <div class="modal">
    <div class="modal-header">
      <h2 id="lessonModalTitle">—</h2>
      <button class="modal-close" onclick="closeLesson()">✕</button>
    </div>
    <div class="modal-body" id="lessonModalBody"></div>
  </div>
</div>

<!-- TEST MODAL -->
<div class="modal-overlay" id="testModal">
  <div class="test-modal">
    <div class="test-header">
      <div class="test-progress-info">
        <div class="q-counter"><span data-t="question">Question</span> <span id="currentQ">1</span>/30</div>
        <div id="testTopicLabel" style="font-size:0.8rem;color:var(--text2)"></div>
      </div>
      <div class="test-progress-bar"><div class="test-progress-fill" id="testProgressFill"></div></div>
    </div>
    <div class="test-body">
      <div class="question-text" id="questionText"></div>
      <div class="options-list" id="optionsList"></div>
      <div class="answer-feedback" id="answerFeedback"></div>
      <button class="btn-next" id="btnNext" onclick="nextQuestion()"><span data-t="next">Next</span> →</button>
    </div>
  </div>
</div>

<!-- RESULTS MODAL -->
<div class="modal-overlay" id="resultsModal">
  <div class="test-modal">
    <div class="results-view" id="resultsView"></div>
  </div>
</div>

<script>
// ===== LANGUAGE SYSTEM =====
let currentLang = 'en';
const translations = {
  en: {
    home:'Home',lessons:'Lessons',listening:'Listening',reading:'Reading',
    writing:'Writing',vocabulary:'Vocabulary',grammar:'Grammar',speaking:'Speaking',
    leaderboard:'Leaderboard',profile:'Profile',
    heroTitle:'Master English Like a Pro',
    heroDesc:'AI-powered lessons, adaptive tests, and real-time feedback.',
    topics:'Topics',completed:'Completed',avgScore:'Avg Score',
    continueLearn:'Continue Learning',allTopics:'All Topics',
    listeningTitle:'Listening Exercises',readingTitle:'Reading Passages',
    writingTitle:'Writing Practice',vocabTitle:'Vocabulary Cards',
    grammarTitle:'Grammar Rules',speakingTitle:'Speaking Practice',
    topStudents:'Top Students',achievements:'Achievements',
    profileName:'English Learner',question:'Question',next:'Next',
    startLesson:'Start Lesson',startTest:'Take the Test (30 Questions)',
    vocabHint:'Click a card to see the translation',
    correct:'Correct!',wrong:'Wrong!',correctAnswerIs:'Correct answer:',
    yourScore:'Your Score',questionsCorrect:'questions correct',
    excellent:'🏆 Excellent! Outstanding performance!',
    great:'🌟 Great! Very good result!',
    good:'👍 Good! Keep practicing!',
    needPractice:'💪 Keep studying! You can do better!',
    retakeTest:'Retake Test',backToTopics:'Back to Topics',
    aiAnalyzing:'AI is analyzing your results...',
    checkWriting:'Check with AI',wordCount:'words',
    playAudio:'Play Audio',stopAudio:'Stop',
    flip:'Tap to flip',startRecord:'Start Speaking',stopRecord:'Stop Recording',
  },
  ru: {
    home:'Главная',lessons:'Уроки',listening:'Аудирование',reading:'Чтение',
    writing:'Письмо',vocabulary:'Словарь',grammar:'Грамматика',speaking:'Говорение',
    leaderboard:'Рейтинг',profile:'Профиль',
    heroTitle:'Изучайте Английский как Pro',
    heroDesc:'Уроки на основе ИИ, адаптивные тесты и обратная связь в реальном времени.',
    topics:'Темы',completed:'Пройдено',avgScore:'Средний балл',
    continueLearn:'Продолжить обучение',allTopics:'Все темы',
    listeningTitle:'Упражнения на аудирование',readingTitle:'Тексты для чтения',
    writingTitle:'Практика письма',vocabTitle:'Карточки слов',
    grammarTitle:'Правила грамматики',speakingTitle:'Практика говорения',
    topStudents:'Лучшие ученики',achievements:'Достижения',
    profileName:'Изучающий английский',question:'Вопрос',next:'Далее',
    startLesson:'Начать урок',startTest:'Пройти тест (30 вопросов)',
    vocabHint:'Нажмите на карточку чтобы увидеть перевод',
    correct:'Правильно!',wrong:'Неправильно!',correctAnswerIs:'Правильный ответ:',
    yourScore:'Ваш результат',questionsCorrect:'правильных ответов',
    excellent:'🏆 Отлично! Выдающийся результат!',
    great:'🌟 Хорошо! Очень хороший результат!',
    good:'👍 Неплохо! Продолжайте практиковаться!',
    needPractice:'💪 Учитесь дальше! Вы можете лучше!',
    retakeTest:'Повторить тест',backToTopics:'К темам',
    aiAnalyzing:'ИИ анализирует ваши результаты...',
    checkWriting:'Проверить с ИИ',wordCount:'слов',
    playAudio:'Воспроизвести',stopAudio:'Стоп',
    flip:'Нажмите чтобы перевернуть',startRecord:'Начать говорить',stopRecord:'Остановить',
  },
  uz: {
    home:'Bosh sahifa',lessons:'Darslar',listening:'Tinglash',reading:'O\'qish',
    writing:'Yozish',vocabulary:'Lug\'at',grammar:'Grammatika',speaking:'Gaplashish',
    leaderboard:'Reyting',profile:'Profil',
    heroTitle:'Ingliz tilini Pro darajada o\'rganing',
    heroDesc:'Sun\'iy intellekt yordamida darslar, moslashuvchan testlar va real vaqtdagi fikr-mulohaza.',
    topics:'Mavzular',completed:'Bajarildi',avgScore:'O\'rtacha ball',
    continueLearn:'O\'rganishni davom ettiring',allTopics:'Barcha mavzular',
    listeningTitle:'Tinglash mashqlari',readingTitle:'O\'qish matnlari',
    writingTitle:'Yozish mashqi',vocabTitle:'So\'z kartalari',
    grammarTitle:'Grammatika qoidalari',speakingTitle:'Gaplashish mashqi',
    topStudents:'Eng yaxshi o\'quvchilar',achievements:'Yutuqlar',
    profileName:'Ingliz tili o\'rganuvchi',question:'Savol',next:'Keyingi',
    startLesson:'Darsni boshlash',startTest:'Testni boshlash (30 savol)',
    vocabHint:'Tarjimani ko\'rish uchun kartani bosing',
    correct:'To\'g\'ri!',wrong:'Noto\'g\'ri!',correctAnswerIs:'To\'g\'ri javob:',
    yourScore:'Natijangiz',questionsCorrect:'ta to\'g\'ri javob',
    excellent:'🏆 Ajoyib! A\'lo natija!',
    great:'🌟 Yaxshi! Juda yaxshi natija!',
    good:'👍 Yaxshi! Mashq qilishda davom eting!',
    needPractice:'💪 O\'rganishda davom eting! Siz yaxshiroq qila olasiz!',
    retakeTest:'Testni qayta topshirish',backToTopics:'Mavzularga qaytish',
    aiAnalyzing:'AI natijalaringizni tahlil qilmoqda...',
    checkWriting:'AI bilan tekshirish',wordCount:'so\'z',
    flip:'Ag\'darish uchun bosing',startRecord:'Gaplashishni boshlash',stopRecord:'To\'xtatish',
  }
};

function t(key) { return translations[currentLang][key] || translations['en'][key] || key; }

function setLang(lang) {
  currentLang = lang;
  document.querySelectorAll('.lang-btn').forEach(b => b.classList.remove('active'));
  event.target.classList.add('active');
  document.querySelectorAll('[data-t]').forEach(el => {
    const key = el.getAttribute('data-t');
    el.textContent = t(key);
  });
  renderAll();
}

// ===== DATA =====
const topics = [
  {id:'greetings',icon:'👋',title:{en:'Greetings & Introductions',ru:'Приветствия и знакомство',uz:'Salomlashish va tanishish'},
   level:'A1',c1:'#00d4ff',c2:'#0066ff',
   desc:{en:'Learn how to greet people and introduce yourself in English',ru:'Узнайте как приветствовать людей и представляться на английском',uz:'Inglizcha salomlashish va o\'zingizni tanishtirish'},
   content:{en:`
<h3>Basic Greetings</h3>
<p>Greetings are the foundation of any conversation. In English, there are formal and informal ways to greet people depending on the situation.</p>
<div class="highlight">💡 Formal greetings are used in professional settings, while informal ones are used with friends and family.</div>
<h3>Formal Greetings</h3>
<div class="example-box"><div class="en">Good morning / Good afternoon / Good evening</div><div class="tr">Used at specific times of day in professional settings</div></div>
<div class="example-box"><div class="en">How do you do? / How are you?</div><div class="tr">Formal ways to ask about someone's wellbeing</div></div>
<div class="example-box"><div class="en">It's a pleasure to meet you.</div><div class="tr">Used when meeting someone for the first time formally</div></div>
<h3>Informal Greetings</h3>
<div class="example-box"><div class="en">Hi! / Hey! / Hello!</div><div class="tr">Casual ways to say hello</div></div>
<div class="example-box"><div class="en">What's up? / How's it going? / How are you doing?</div><div class="tr">Informal ways to ask how someone is</div></div>
<div class="example-box"><div class="en">Long time no see! / Good to see you again!</div><div class="tr">When meeting someone you haven't seen for a while</div></div>
<h3>Introducing Yourself</h3>
<div class="example-box"><div class="en">My name is [Name]. / I'm [Name]. / Call me [Name].</div><div class="tr">Ways to tell someone your name</div></div>
<div class="example-box"><div class="en">I'm from [Country/City]. I live in [Place].</div><div class="tr">Telling someone where you are from</div></div>
<div class="example-box"><div class="en">I'm a student / teacher / engineer / doctor.</div><div class="tr">Describing your profession</div></div>
<h3>Useful Vocabulary</h3>
<table class="vocab-table"><tr><th>English</th><th>Meaning</th><th>Example</th></tr>
<tr><td>Nice to meet you</td><td>Pleased to make your acquaintance</td><td>"Nice to meet you, John!"</td></tr>
<tr><td>Likewise</td><td>Same feeling in return</td><td>"Nice to meet you too!" / "Likewise!"</td></tr>
<tr><td>Where are you from?</td><td>Asking about origin</td><td>"Where are you from?" "I'm from Uzbekistan."</td></tr>
<tr><td>What do you do?</td><td>Asking about profession</td><td>"What do you do?" "I'm an engineer."</td></tr>
<tr><td>Farewell</td><td>Goodbye</td><td>"Farewell! Safe travels!"</td></tr></table>
<h3>Farewells</h3>
<div class="example-box"><div class="en">Goodbye / Bye / See you later / Take care</div><div class="tr">Common ways to say goodbye</div></div>
<div class="example-box"><div class="en">It was nice talking to you. / Have a great day!</div><div class="tr">Polite ways to end a conversation</div></div>
   `}},

  {id:'present_tenses',icon:'⏰',title:{en:'Present Tenses',ru:'Настоящие времена',uz:'Hozirgi zamon'},
   level:'A2',c1:'#7c3aed',c2:'#db2777',
   desc:{en:'Master Present Simple, Continuous and Perfect tenses',ru:'Освойте Present Simple, Continuous и Perfect',uz:'Present Simple, Continuous va Perfect zamonlarini o\'zlashtiring'},
   content:{en:`
<h3>Present Simple</h3>
<p>Used for habits, facts, routines, and general truths. It describes things that happen regularly or are always true.</p>
<div class="highlight">💡 Structure: Subject + base verb (+ s/es for he/she/it)</div>
<div class="example-box"><div class="en">I work every day. She reads books. They live in London.</div><div class="tr">Routine and habit examples</div></div>
<div class="example-box"><div class="en">Water boils at 100°C. The sun rises in the east.</div><div class="tr">Scientific facts and permanent truths</div></div>
<h3>Signal Words for Present Simple</h3>
<table class="vocab-table"><tr><th>Frequency Adverb</th><th>Meaning</th></tr>
<tr><td>always</td><td>100% of the time</td></tr>
<tr><td>usually / generally</td><td>most of the time (~80%)</td></tr>
<tr><td>often / frequently</td><td>many times (~60%)</td></tr>
<tr><td>sometimes</td><td>occasionally (~40%)</td></tr>
<tr><td>rarely / seldom</td><td>not often (~10%)</td></tr>
<tr><td>never</td><td>0% of the time</td></tr></table>
<h3>Present Continuous</h3>
<p>Used for actions happening right now, temporary situations, and future plans.</p>
<div class="highlight">💡 Structure: Subject + am/is/are + verb-ing</div>
<div class="example-box"><div class="en">I am studying English right now. She is working from home this week.</div><div class="tr">Actions in progress at this moment or temporarily</div></div>
<div class="example-box"><div class="en">We are meeting tomorrow at 3 PM. They are flying to London next week.</div><div class="tr">Fixed future arrangements</div></div>
<h3>Present Perfect</h3>
<p>Connects the past to the present. Used for experiences, recent events, and actions with present results.</p>
<div class="highlight">💡 Structure: Subject + have/has + past participle</div>
<div class="example-box"><div class="en">I have visited Paris. (life experience — exact time unknown)</div><div class="tr">Life experiences without specific time</div></div>
<div class="example-box"><div class="en">She has just finished her homework. (recent action)</div><div class="tr">Just completed actions</div></div>
<div class="example-box"><div class="en">He has lived here for 5 years. (started in past, still true)</div><div class="tr">Actions continuing into the present</div></div>
<h3>Negative & Question Forms</h3>
<table class="vocab-table"><tr><th>Tense</th><th>Negative</th><th>Question</th></tr>
<tr><td>Present Simple</td><td>I don't work / She doesn't work</td><td>Do you work? / Does she work?</td></tr>
<tr><td>Present Continuous</td><td>I'm not working / She isn't working</td><td>Are you working? / Is she working?</td></tr>
<tr><td>Present Perfect</td><td>I haven't worked / She hasn't worked</td><td>Have you worked? / Has she worked?</td></tr></table>
   `}},

  {id:'past_tenses',icon:'📅',title:{en:'Past Tenses',ru:'Прошедшие времена',uz:'O\'tgan zamon'},
   level:'B1',c1:'#f59e0b',c2:'#ef4444',
   desc:{en:'Past Simple, Continuous, Perfect — telling stories',ru:'Past Simple, Continuous, Perfect — рассказывание историй',uz:'Past Simple, Continuous, Perfect — hikoya qilish'},
   content:{en:`
<h3>Past Simple</h3>
<p>Used for completed actions at a specific time in the past. This is the most commonly used past tense in English storytelling.</p>
<div class="highlight">💡 Structure: Subject + past form of verb (regular: +ed, irregular: learn the forms)</div>
<div class="example-box"><div class="en">I visited London last year. She called me yesterday.</div><div class="tr">Completed actions with specific past time</div></div>
<div class="example-box"><div class="en">We watched a movie, had dinner, and went to bed.</div><div class="tr">Sequence of completed past events</div></div>
<h3>Common Irregular Verbs</h3>
<table class="vocab-table"><tr><th>Base</th><th>Past Simple</th><th>Past Participle</th></tr>
<tr><td>go</td><td>went</td><td>gone</td></tr>
<tr><td>see</td><td>saw</td><td>seen</td></tr>
<tr><td>have</td><td>had</td><td>had</td></tr>
<tr><td>make</td><td>made</td><td>made</td></tr>
<tr><td>take</td><td>took</td><td>taken</td></tr>
<tr><td>give</td><td>gave</td><td>given</td></tr>
<tr><td>come</td><td>came</td><td>come</td></tr>
<tr><td>know</td><td>knew</td><td>known</td></tr></table>
<h3>Past Continuous</h3>
<p>Used for actions in progress at a specific moment in the past, or background actions interrupted by another event.</p>
<div class="highlight">💡 Structure: Subject + was/were + verb-ing</div>
<div class="example-box"><div class="en">I was sleeping when the phone rang.</div><div class="tr">Background action interrupted by another</div></div>
<div class="example-box"><div class="en">While she was cooking, he was cleaning the house.</div><div class="tr">Two simultaneous past actions</div></div>
<h3>Past Perfect</h3>
<p>Used for actions that happened before another past action. It helps establish the sequence of past events.</p>
<div class="highlight">💡 Structure: Subject + had + past participle</div>
<div class="example-box"><div class="en">When I arrived, she had already left.</div><div class="tr">One past action before another past action</div></div>
<div class="example-box"><div class="en">He had studied English for 5 years before he moved to the US.</div><div class="tr">Duration before a past reference point</div></div>
   `}},

  {id:'future_tenses',icon:'🚀',title:{en:'Future Tenses',ru:'Будущие времена',uz:'Kelasi zamon'},
   level:'B1',c1:'#10b981',c2:'#06b6d4',
   desc:{en:'Will, Going to, Future Perfect and more',ru:'Will, Going to, Future Perfect и другие',uz:'Will, Going to, Future Perfect va boshqalar'},
   content:{en:`
<h3>Will (Simple Future)</h3>
<p>Used for spontaneous decisions, predictions based on opinion, promises, and offers made in the moment.</p>
<div class="highlight">💡 Structure: Subject + will + base verb</div>
<div class="example-box"><div class="en">I'll help you with that! (spontaneous offer)</div><div class="tr">Decision made at the moment of speaking</div></div>
<div class="example-box"><div class="en">It will rain tomorrow. (prediction based on opinion)</div><div class="tr">Future prediction without evidence</div></div>
<div class="example-box"><div class="en">I promise I won't be late. (promise)</div><div class="tr">Making a commitment</div></div>
<h3>Going to (Planned Future)</h3>
<p>Used for plans already decided, intentions, and predictions based on present evidence.</p>
<div class="highlight">💡 Structure: Subject + am/is/are + going to + base verb</div>
<div class="example-box"><div class="en">I'm going to study medicine next year. (plan already made)</div><div class="tr">Pre-decided plan or intention</div></div>
<div class="example-box"><div class="en">Look at those clouds — it's going to rain! (evidence)</div><div class="tr">Prediction based on visible evidence</div></div>
<h3>Future Continuous</h3>
<p>Used for actions that will be in progress at a specific future time.</p>
<div class="example-box"><div class="en">At 8 PM tonight, I will be watching the match.</div><div class="tr">Action in progress at a future moment</div></div>
<h3>Future Perfect</h3>
<p>Used for actions that will be completed before a specific future time.</p>
<div class="highlight">💡 Structure: Subject + will have + past participle</div>
<div class="example-box"><div class="en">By next year, I will have graduated from university.</div><div class="tr">Completed before a future time reference</div></div>
<h3>Choosing the Right Future Form</h3>
<table class="vocab-table"><tr><th>Situation</th><th>Form</th><th>Example</th></tr>
<tr><td>Spontaneous decision</td><td>will</td><td>"I'll take the blue one."</td></tr>
<tr><td>Pre-planned intention</td><td>going to</td><td>"I'm going to learn French."</td></tr>
<tr><td>Fixed timetable</td><td>Present Simple</td><td>"The train leaves at 6."</td></tr>
<tr><td>Arranged meeting</td><td>Present Continuous</td><td>"We're meeting at noon."</td></tr></table>
   `}},

  {id:'conditionals',icon:'🔀',title:{en:'Conditionals',ru:'Условные предложения',uz:'Shartli gaplar'},
   level:'B2',c1:'#8b5cf6',c2:'#ec4899',
   desc:{en:'Zero, First, Second, Third and Mixed conditionals',ru:'Нулевое, первое, второе, третье и смешанное условие',uz:'Nol, birinchi, ikkinchi, uchinchi va aralash shartlar'},
   content:{en:`
<h3>Zero Conditional</h3>
<p>Used for facts, scientific truths, and things that are always true when a certain condition is met.</p>
<div class="highlight">💡 If + Present Simple, Present Simple</div>
<div class="example-box"><div class="en">If you heat water to 100°C, it boils.</div><div class="tr">Scientific fact — always true</div></div>
<h3>First Conditional</h3>
<p>Used for real and possible future situations and their likely results.</p>
<div class="highlight">💡 If + Present Simple, will + base verb</div>
<div class="example-box"><div class="en">If it rains tomorrow, I will stay home.</div><div class="tr">Possible real future situation</div></div>
<div class="example-box"><div class="en">Unless you study, you won't pass the exam.</div><div class="tr">"Unless" = "if not"</div></div>
<h3>Second Conditional</h3>
<p>Used for imaginary, hypothetical, or unlikely present/future situations.</p>
<div class="highlight">💡 If + Past Simple, would + base verb</div>
<div class="example-box"><div class="en">If I had a million dollars, I would travel the world.</div><div class="tr">Imaginary/hypothetical situation</div></div>
<div class="example-box"><div class="en">If I were you, I would apologize. (were — not was!)</div><div class="tr">Advice using second conditional</div></div>
<h3>Third Conditional</h3>
<p>Used for imagining different outcomes for past situations — things that didn't happen.</p>
<div class="highlight">💡 If + Past Perfect, would have + past participle</div>
<div class="example-box"><div class="en">If I had studied harder, I would have passed the exam.</div><div class="tr">Imagining a different past outcome</div></div>
<div class="example-box"><div class="en">She wouldn't have been late if she had woken up earlier.</div><div class="tr">Past regret / alternative past</div></div>
<h3>Mixed Conditionals</h3>
<p>Combine elements of 2nd and 3rd conditionals to talk about how past events affect the present, or present states affecting past results.</p>
<div class="example-box"><div class="en">If I had taken that job, I would be rich now.</div><div class="tr">Past action → present result</div></div>
<div class="example-box"><div class="en">If I were taller, I would have become a basketball player.</div><div class="tr">Present state → past result</div></div>
   `}},

  {id:'modal_verbs',icon:'🎯',title:{en:'Modal Verbs',ru:'Модальные глаголы',uz:'Modal fe\'llar'},
   level:'B1',c1:'#f97316',c2:'#eab308',
   desc:{en:'Can, Could, Must, Should, May, Might and more',ru:'Can, Could, Must, Should, May, Might и другие',uz:'Can, Could, Must, Should, May, Might va boshqalar'},
   content:{en:`
<h3>Modal Verbs Overview</h3>
<p>Modal verbs add meaning to the main verb — expressing ability, possibility, obligation, permission, or advice. They are always followed by the base form of the verb.</p>
<div class="highlight">💡 Modal verbs: can, could, may, might, must, shall, should, will, would, ought to</div>
<h3>Can / Could — Ability & Permission</h3>
<div class="example-box"><div class="en">I can speak three languages. (present ability)</div><div class="tr">General ability in the present</div></div>
<div class="example-box"><div class="en">She could swim before she was 5. (past ability)</div><div class="tr">Past ability that may not be true now</div></div>
<div class="example-box"><div class="en">Can I borrow your pen? / Could I use your phone? (request)</div><div class="tr">Asking permission — "could" is more polite</div></div>
<h3>Must / Have to — Obligation</h3>
<div class="example-box"><div class="en">You must wear a seatbelt. (rule — speaker's authority)</div><div class="tr">Strong obligation from the speaker's perspective</div></div>
<div class="example-box"><div class="en">I have to work tomorrow. (external obligation)</div><div class="tr">Obligation from external source (boss, rules)</div></div>
<div class="example-box"><div class="en">You mustn't smoke here. (prohibition)</div><div class="tr">Something that is NOT allowed</div></div>
<h3>Should / Ought to — Advice</h3>
<div class="example-box"><div class="en">You should drink more water. / You ought to see a doctor.</div><div class="tr">Advice or recommendation</div></div>
<h3>May / Might — Possibility</h3>
<div class="example-box"><div class="en">It may rain later. (50% possibility)</div><div class="tr">Fairly possible future event</div></div>
<div class="example-box"><div class="en">She might be at home. (less certain — ~30%)</div><div class="tr">Less certain possibility</div></div>
<h3>Would — Habit, Request, Conditional</h3>
<div class="example-box"><div class="en">He would always bring flowers. (past habit)</div><div class="tr">Repeated past action/habit</div></div>
<div class="example-box"><div class="en">Would you like some tea? (polite offer/request)</div><div class="tr">Polite question</div></div>
   `}},

  {id:'phrasal_verbs',icon:'💬',title:{en:'Phrasal Verbs',ru:'Фразовые глаголы',uz:'Frazeologik fe\'llar'},
   level:'B2',c1:'#14b8a6',c2:'#3b82f6',
   desc:{en:'Essential phrasal verbs for everyday communication',ru:'Основные фразовые глаголы для повседневного общения',uz:'Kundalik muloqot uchun muhim frazeologik fe\'llar'},
   content:{en:`
<h3>What Are Phrasal Verbs?</h3>
<p>A phrasal verb is a combination of a verb and one or more particles (prepositions or adverbs) that together have a new meaning, often different from the individual words.</p>
<div class="highlight">💡 Phrasal verbs are essential for sounding natural in English. Native speakers use them constantly!</div>
<h3>Common Phrasal Verbs with GET</h3>
<table class="vocab-table"><tr><th>Phrasal Verb</th><th>Meaning</th><th>Example</th></tr>
<tr><td>get up</td><td>rise from bed</td><td>I get up at 7 AM every day.</td></tr>
<tr><td>get along (with)</td><td>have a good relationship</td><td>She gets along well with her colleagues.</td></tr>
<tr><td>get over</td><td>recover from</td><td>It took him months to get over the illness.</td></tr>
<tr><td>get rid of</td><td>eliminate/remove</td><td>I need to get rid of these old clothes.</td></tr>
<tr><td>get away with</td><td>escape consequence</td><td>He got away with cheating on the test.</td></tr></table>
<h3>Common Phrasal Verbs with GIVE, TAKE, LOOK</h3>
<table class="vocab-table"><tr><th>Phrasal Verb</th><th>Meaning</th><th>Example</th></tr>
<tr><td>give up</td><td>stop trying / quit</td><td>Don't give up on your dreams!</td></tr>
<tr><td>give away</td><td>donate / reveal</td><td>She gave away her secret.</td></tr>
<tr><td>take off</td><td>remove / depart (plane)</td><td>Please take off your shoes. / The plane took off.</td></tr>
<tr><td>take over</td><td>gain control</td><td>She took over the company.</td></tr>
<tr><td>look after</td><td>care for</td><td>Can you look after my cat this weekend?</td></tr>
<tr><td>look forward to</td><td>anticipate with pleasure</td><td>I'm looking forward to the holidays!</td></tr>
<tr><td>look into</td><td>investigate</td><td>Police are looking into the matter.</td></tr></table>
<h3>Business Phrasal Verbs</h3>
<div class="example-box"><div class="en">call off (cancel), draw up (prepare a document), follow up (continue progress on), set up (establish)</div><div class="tr">Common in professional/business English</div></div>
   `}},

  {id:'articles',icon:'📌',title:{en:'Articles: A, An, The',ru:'Артикли: A, An, The',uz:'Artikllar: A, An, The'},
   level:'A2',c1:'#6366f1',c2:'#a855f7',
   desc:{en:'Definite and indefinite articles — when and how to use them',ru:'Определённый и неопределённый артикль',uz:'Aniq va noaniq artikllar — qachon va qanday ishlatish'},
   content:{en:`
<h3>Indefinite Articles: A / AN</h3>
<p>Use "a" before consonant sounds and "an" before vowel sounds. Articles "a/an" are used with singular countable nouns when we mention something for the first time or when it is one of many.</p>
<div class="highlight">💡 A/AN means "one of many" — not specific, not previously mentioned</div>
<div class="example-box"><div class="en">a book, a car, a university (starts with "y" sound!)</div><div class="tr">Consonant sounds → use "a"</div></div>
<div class="example-box"><div class="en">an apple, an hour (h is silent!), an umbrella, an honest man</div><div class="tr">Vowel sounds → use "an"</div></div>
<h3>When to Use A / AN</h3>
<table class="vocab-table"><tr><th>Situation</th><th>Example</th></tr>
<tr><td>First mention</td><td>I saw a dog. The dog was barking.</td></tr>
<tr><td>One of many</td><td>She works as a teacher.</td></tr>
<tr><td>Describing someone</td><td>He is an engineer.</td></tr>
<tr><td>With singular countable nouns</td><td>I need a pen.</td></tr></table>
<h3>Definite Article: THE</h3>
<p>Use "the" when the noun is specific, already mentioned, unique, or known to both speaker and listener.</p>
<div class="highlight">💡 THE means "that specific one" — both people know which one</div>
<div class="example-box"><div class="en">I saw a dog. The dog was barking loudly.</div><div class="tr">Second mention — now specific</div></div>
<div class="example-box"><div class="en">the sun, the moon, the Earth (unique things)</div><div class="tr">One of its kind in the world</div></div>
<div class="example-box"><div class="en">the Nile, the Alps, the USA, the BBC</div><div class="tr">Rivers, mountain ranges, countries with "of", organizations</div></div>
<h3>No Article (Zero Article)</h3>
<div class="example-box"><div class="en">Plural general: Dogs are loyal animals. / Uncountable general: Water is essential for life.</div><div class="tr">General statements about categories</div></div>
<div class="example-box"><div class="en">by car / by train / at school / at home / in bed</div><div class="tr">Fixed expressions with no article</div></div>
   `}},

  {id:'passive_voice',icon:'🔄',title:{en:'Passive Voice',ru:'Страдательный залог',uz:'Majhul nisbat'},
   level:'B2',c1:'#dc2626',c2:'#9333ea',
   desc:{en:'Transforming active to passive across all tenses',ru:'Преобразование из активного в пассивный залог',uz:'Faol nisbatdan majhul nisbatga o\'tkazish'},
   content:{en:`
<h3>What Is Passive Voice?</h3>
<p>In active voice, the subject performs the action. In passive voice, the subject receives the action. Passive voice is used when the action is more important than who does it, or when the doer is unknown or unimportant.</p>
<div class="highlight">💡 Active: Subject + verb + object → Passive: Object becomes subject + be + past participle</div>
<div class="example-box"><div class="en">Active: Shakespeare wrote Hamlet. → Passive: Hamlet was written by Shakespeare.</div><div class="tr">The focus shifts to what was done</div></div>
<h3>Passive Voice in All Tenses</h3>
<table class="vocab-table"><tr><th>Tense</th><th>Active</th><th>Passive</th></tr>
<tr><td>Present Simple</td><td>They make cars here.</td><td>Cars are made here.</td></tr>
<tr><td>Present Continuous</td><td>They are building a bridge.</td><td>A bridge is being built.</td></tr>
<tr><td>Past Simple</td><td>He broke the window.</td><td>The window was broken.</td></tr>
<tr><td>Past Continuous</td><td>They were painting the house.</td><td>The house was being painted.</td></tr>
<tr><td>Future Simple</td><td>They will finish the project.</td><td>The project will be finished.</td></tr>
<tr><td>Present Perfect</td><td>They have invented a new device.</td><td>A new device has been invented.</td></tr></table>
<h3>When to Use Passive Voice</h3>
<div class="example-box"><div class="en">The president was elected last November. (focus on the event)</div><div class="tr">Doer is known but unimportant</div></div>
<div class="example-box"><div class="en">My wallet was stolen. (doer unknown)</div><div class="tr">We don't know who did it</div></div>
<div class="example-box"><div class="en">The bridge is being repaired. (news/announcements)</div><div class="tr">Common in formal and news English</div></div>
<h3>By-Agent</h3>
<p>We can add "by + agent" to say who performed the action, but only when this information is important or new.</p>
<div class="example-box"><div class="en">The theory of relativity was developed by Einstein.</div><div class="tr">The doer (Einstein) is important here</div></div>
   `}},

  {id:'reported_speech',icon:'💭',title:{en:'Reported Speech',ru:'Косвенная речь',uz:'Bilvosita nutq'},
   level:'B2',c1:'#0891b2',c2:'#065f46',
   desc:{en:'How to report what someone said — tense backshift',ru:'Как передавать чужие слова — сдвиг времён',uz:'Birovning so\'zlarini qanday ifodalash — zamon siljishi'},
   content:{en:`
<h3>What Is Reported Speech?</h3>
<p>Reported speech (indirect speech) is used to tell someone what another person said without quoting them exactly. When we change from direct to reported speech, we typically need to change verbs, pronouns, and time expressions.</p>
<div class="highlight">💡 Direct: "I am tired," she said. → Reported: She said (that) she was tired.</div>
<h3>Tense Backshift</h3>
<table class="vocab-table"><tr><th>Direct Speech</th><th>Reported Speech</th></tr>
<tr><td>Present Simple: "I work..."</td><td>Past Simple: said they worked...</td></tr>
<tr><td>Present Continuous: "I am working..."</td><td>Past Continuous: said they were working...</td></tr>
<tr><td>Past Simple: "I worked..."</td><td>Past Perfect: said they had worked...</td></tr>
<tr><td>Present Perfect: "I have worked..."</td><td>Past Perfect: said they had worked...</td></tr>
<tr><td>Will: "I will go..."</td><td>Would: said they would go...</td></tr>
<tr><td>Can: "I can swim..."</td><td>Could: said they could swim...</td></tr></table>
<h3>Pronoun Changes</h3>
<div class="example-box"><div class="en">"I love you," he told her. → He told her (that) he loved her.</div><div class="tr">First person changes based on context</div></div>
<h3>Time & Place Expression Changes</h3>
<table class="vocab-table"><tr><th>Direct</th><th>Reported</th></tr>
<tr><td>now</td><td>then / at that moment</td></tr>
<tr><td>today</td><td>that day</td></tr>
<tr><td>yesterday</td><td>the day before / the previous day</td></tr>
<tr><td>tomorrow</td><td>the next day / the following day</td></tr>
<tr><td>here</td><td>there</td></tr>
<tr><td>this</td><td>that</td></tr></table>
<h3>Reporting Questions</h3>
<div class="example-box"><div class="en">"Where do you live?" → He asked me where I lived. (no auxiliary, statement word order)</div><div class="tr">Indirect questions — no question mark</div></div>
<div class="example-box"><div class="en">"Are you hungry?" → She asked if / whether I was hungry.</div><div class="tr">Yes/No questions use if or whether</td></div>
   `}},

  {id:'vocabulary_advanced',icon:'📚',title:{en:'Advanced Vocabulary',ru:'Продвинутый словарный запас',uz:'Ilg\'or lug\'at'},
   level:'C1',c1:'#4f46e5',c2:'#be185d',
   desc:{en:'Academic, business and IELTS vocabulary expansion',ru:'Академическая, деловая и IELTS лексика',uz:'Akademik, biznes va IELTS lug\'ati'},
   content:{en:`
<h3>Academic Word List (AWL) — Core Words</h3>
<p>The Academic Word List contains the most common words in academic English. Mastering these will help you in university, IELTS, TOEFL, and professional writing.</p>
<table class="vocab-table"><tr><th>Word</th><th>Part of Speech</th><th>Meaning</th><th>Example</th></tr>
<tr><td>analyze</td><td>verb</td><td>examine in detail</td><td>We need to analyze the data carefully.</td></tr>
<tr><td>concept</td><td>noun</td><td>an abstract idea</td><td>The concept of democracy is complex.</td></tr>
<tr><td>significant</td><td>adjective</td><td>important / notable</td><td>There was a significant increase in sales.</td></tr>
<tr><td>establish</td><td>verb</td><td>set up / prove</td><td>Research has established a link between diet and health.</td></tr>
<tr><td>approach</td><td>noun/verb</td><td>method / to come near</td><td>Their approach to teaching is innovative.</td></tr>
<tr><td>interpret</td><td>verb</td><td>explain the meaning</td><td>Different people interpret the results differently.</td></tr>
<tr><td>indicate</td><td>verb</td><td>point out / suggest</td><td>The data indicates a rising trend.</td></tr>
<tr><td>context</td><td>noun</td><td>surrounding circumstances</td><td>You need to understand the historical context.</td></tr></table>
<h3>Business English Vocabulary</h3>
<table class="vocab-table"><tr><th>Word/Phrase</th><th>Meaning</th></tr>
<tr><td>synergy</td><td>combined effect greater than individual parts</td></tr>
<tr><td>stakeholder</td><td>person with interest in a business</td></tr>
<tr><td>benchmark</td><td>standard point of reference for comparison</td></tr>
<tr><td>leverage</td><td>use something to maximum advantage</td></tr>
<tr><td>scalable</td><td>able to grow proportionally</td></tr>
<tr><td>ROI (Return on Investment)</td><td>profit relative to investment cost</td></tr>
<tr><td>proactive</td><td>taking initiative before problems occur</td></tr></table>
<h3>IELTS High-Scoring Words</h3>
<div class="example-box"><div class="en">Furthermore, Moreover, In addition, Nevertheless, Consequently, Subsequently, In contrast, Conversely</div><div class="tr">Linking words and discourse markers for IELTS Writing</div></div>
<div class="example-box"><div class="en">substantial, considerable, dramatic, remarkable, negligible, marginal, exponential</div><div class="tr">Adjectives to describe changes in graphs/charts</div></div>
   `}},

  {id:'pronunciation',icon:'🗣️',title:{en:'Pronunciation & Phonetics',ru:'Произношение и фонетика',uz:'Talaffuz va fonetika'},
   level:'A1',c1:'#059669',c2:'#7c3aed',
   desc:{en:'Sounds, stress, intonation and the IPA system',ru:'Звуки, ударение, интонация и система МФА',uz:'Tovushlar, urg\'u, intonatsiya va IPA tizimi'},
   content:{en:`
<h3>The International Phonetic Alphabet (IPA)</h3>
<p>The IPA is a system of symbols that represents the sounds of human speech. Learning IPA helps you understand pronunciation in dictionaries and learn how to say any English word correctly.</p>
<div class="highlight">💡 Every English word in a dictionary has an IPA transcription. Learn the symbols and you can pronounce any word!</div>
<h3>English Vowel Sounds</h3>
<table class="vocab-table"><tr><th>Symbol</th><th>Sound</th><th>Examples</th></tr>
<tr><td>/iː/</td><td>long "ee"</td><td>see, tea, feel, machine</td></tr>
<tr><td>/ɪ/</td><td>short "i"</td><td>sit, hit, bit, women</td></tr>
<tr><td>/e/</td><td>short "e"</td><td>bed, red, head, said</td></tr>
<tr><td>/æ/</td><td>flat "a"</td><td>cat, hat, man, laugh</td></tr>
<tr><td>/ɑː/</td><td>long "ah"</td><td>car, father, calm, heart</td></tr>
<tr><td>/ɒ/</td><td>short "o"</td><td>hot, dog, stop, what</td></tr>
<tr><td>/uː/</td><td>long "oo"</td><td>food, blue, threw, shoe</td></tr>
<tr><td>/ʌ/</td><td>"uh" sound</td><td>cup, love, blood, come</td></tr>
<tr><td>/ə/</td><td>schwa (most common!)</td><td>a-bout, lem-on, teach-er</td></tr></table>
<h3>Word Stress Rules</h3>
<div class="highlight">💡 Stress is crucial! Wrong stress can make you hard to understand even if all the words are correct.</div>
<div class="example-box"><div class="en">PHOtograph (noun) vs phoTOgraphy (noun) vs photoGRAPHic (adjective)</div><div class="tr">Suffix changes can shift stress</div></div>
<div class="example-box"><div class="en">REcord (noun) vs reCORD (verb) — PERmit (noun) vs perMIT (verb)</div><div class="tr">Many 2-syllable words: noun = first syllable, verb = second syllable</td></div>
<h3>Common Pronunciation Mistakes</h3>
<table class="vocab-table"><tr><th>Word</th><th>Wrong</th><th>Correct IPA</th></tr>
<tr><td>though</td><td>/θoʊg/</td><td>/ðoʊ/ — silent "gh"</td></tr>
<tr><td>island</td><td>/ɪzlənd/</td><td>/ˈaɪlənd/ — silent "s"</td></tr>
<tr><td>colonel</td><td>/kɒlənəl/</td><td>/ˈkɜːrnəl/ — sounds like "kernel"</td></tr>
<tr><td>Wednesday</td><td>/wɛdnɛzdeɪ/</td><td>/ˈwɛnzdeɪ/ — silent "d"</td></tr></table>
   `}},
];

// ===== QUESTION BANK =====
// 30 unique questions per topic, no repetition
const questionBank = {};

function generateQuestions(topic) {
  const q = {
    greetings: [
      {q:"Which greeting is most formal?",o:["What's up?","Good morning, sir.","Hey!","Yo!"],a:1,exp:"'Good morning, sir' is formal and appropriate in professional settings."},
      {q:"What is the correct response to 'How do you do?'",o:["I'm fine, thanks!","How do you do?","Not bad.","What's up?"],a:1,exp:"'How do you do?' is a formal greeting. The correct response is 'How do you do?'"},
      {q:"Which phrase introduces yourself?",o:["See you later!","Nice weather today.","My name is Anna.","How are you?"],a:2,exp:"'My name is...' is the standard way to introduce yourself."},
      {q:"'Long time no see!' means:",o:["I've never met you.","We haven't seen each other for a while.","See you tomorrow.","Goodbye!"],a:1,exp:"'Long time no see!' is an informal expression for when you haven't seen someone in a long time."},
      {q:"Which is an informal farewell?",o:["Farewell, my friend.","Good evening.","See ya!","How do you do?"],a:2,exp:"'See ya!' is an informal and casual way to say goodbye."},
      {q:"'What do you do?' is asking about your:",o:["Health","Hobbies","Profession","Location"],a:2,exp:"'What do you do?' is a standard question asking about someone's job or profession."},
      {q:"Complete: 'It's a _____ to meet you.'",o:["problem","pleasure","matter","question"],a:1,exp:"'It's a pleasure to meet you' is a formal way to greet someone new."},
      {q:"Which greeting is used in the morning?",o:["Good night","Good afternoon","Good morning","Good evening"],a:2,exp:"'Good morning' is used until around noon."},
      {q:"'Nice to meet you' can also be said as:",o:["Nice weather!","Pleased to meet you.","How's life?","What's cooking?"],a:1,exp:"'Pleased to meet you' has the same meaning as 'nice to meet you'."},
      {q:"When meeting someone for the first time at a business meeting, you say:",o:["Hey dude!","What's up?","How do you do?","Hiya!"],a:2,exp:"'How do you do?' is the most formal greeting for first business meetings."},
      {q:"'Where are you from?' is asking about your:",o:["Age","Nationality/Origin","Profession","Hobby"],a:1,exp:"This question asks about where someone comes from — their country or city."},
      {q:"Which expression is used to end a conversation politely?",o:["Shut up!","It was great talking to you.","Don't go!","Who are you?"],a:1,exp:"'It was great talking to you' is a polite way to end a conversation."},
      {q:"Complete: 'I'm ___ Uzbekistan.' (telling where you're from)",o:["at","on","from","in"],a:2,exp:"We use 'from' to indicate origin: 'I'm from Uzbekistan.'"},
      {q:"'Likewise' in response to 'Nice to meet you' means:",o:["I disagree","I don't care","Same here / Same to you","Goodbye"],a:2,exp:"'Likewise' means 'the same' — it's a polite way to return the feeling."},
      {q:"Which question asks about someone's profession politely?",o:["What job?","Are you working?","What do you do for a living?","Do you have money?"],a:2,exp:"'What do you do for a living?' is the polite and complete form."},
      {q:"'Good evening' is used:",o:["In the morning","In the afternoon","At night/evening","Anytime"],a:2,exp:"'Good evening' is used from approximately 6 PM onwards."},
      {q:"'Call me Mike' means:",o:["Telephone Mike","My name is Mike","I'm not Mike","Call Mike"],a:1,exp:"'Call me [name]' means 'my name is [name]' or 'please use this name for me'."},
      {q:"Which is NOT a greeting?",o:["Hello!","Hi there!","Farewell!","Hey!"],a:2,exp:"'Farewell' is a goodbye/farewell expression, not a greeting."},
      {q:"'I'm a software engineer' — what is this?",o:["A greeting","A farewell","An introduction of profession","A question"],a:2,exp:"Stating your profession is part of introducing yourself."},
      {q:"Complete: 'Have a _____ day!' (farewell wish)",o:["bad","terrible","great","boring"],a:2,exp:"'Have a great day!' is a common positive farewell expression."},
      {q:"'How are you doing?' is:",o:["Formal greeting","Semi-formal/informal greeting","A farewell","An insult"],a:1,exp:"'How are you doing?' is a friendly, informal greeting."},
      {q:"If someone says 'Nice to meet you', a natural response is:",o:["Thank you!","You too!","Goodbye!","I don't know."],a:1,exp:"'You too!' (or 'Nice to meet you too!') is the natural, friendly response."},
      {q:"'Take care' is a type of:",o:["Greeting","Introduction","Farewell","Question"],a:2,exp:"'Take care' is a warm farewell meaning 'be safe and well'."},
      {q:"Which phrase is most suitable for a formal written introduction?",o:["Yo!","Hi, I'm Tom.","I would like to introduce myself. My name is Thomas.","Hey, Tom here!"],a:2,exp:"Formal introductions use complete sentences and full names."},
      {q:"'What's up?' is equivalent to:",o:["What happened?","How are you?","What is that?","Where are you?"],a:1,exp:"'What's up?' is informal and means 'How are you?' or 'What's happening?'"},
      {q:"Complete: 'I'm looking _____ to meeting you.'",o:["at","forward","back","up"],a:1,exp:"'Looking forward to' means anticipating something with pleasure."},
      {q:"'Hiya!' is:",o:["Formal","Rude","Informal greeting","A farewell"],a:2,exp:"'Hiya!' is a very informal, casual form of 'Hello!'"},
      {q:"When leaving work, a colleague says 'See you tomorrow.' You reply:",o:["Never!","See you!","Who are you?","I'm busy."],a:1,exp:"'See you!' or 'See you tomorrow!' is the natural response."},
      {q:"'Nice to meet you' — when do you use this?",o:["When saying goodbye","When meeting someone for the first time","When you're angry","When asking a question"],a:1,exp:"'Nice to meet you' is specifically used when meeting someone for the first time."},
      {q:"Which is a suitable email opening?",o:["Yo! What's up?","Dear Mr. Smith, I hope this email finds you well.","Hiya!","What do you want?"],a:1,exp:"Formal emails begin with 'Dear [Name]' and a polite opening line."},
    ],
    present_tenses:[
      {q:"Which sentence uses Present Simple correctly?",o:["She is walk to work.","She walks to work every day.","She walk to work.","She walking to work."],a:1,exp:"Present Simple: subject + base verb + s/es for he/she/it."},
      {q:"Which sentence uses Present Continuous?",o:["I study now.","I studied now.","I am studying right now.","I have studied now."],a:2,exp:"Present Continuous: am/is/are + verb-ing."},
      {q:"'I have never been to Japan.' — which tense?",o:["Present Simple","Present Continuous","Present Perfect","Past Simple"],a:2,exp:"Present Perfect uses 'have/has + past participle' and is used for life experiences."},
      {q:"Choose the correct form: 'Water _____ at 100°C.'",o:["boil","is boiling","has boiled","boils"],a:3,exp:"Scientific facts use Present Simple. 'Water boils at 100°C.'"},
      {q:"'She _____ (work) from home this week.' (temporary situation)",o:["works","is working","has worked","worked"],a:1,exp:"Temporary situations use Present Continuous: 'She is working from home.'"},
      {q:"Which word signals Present Perfect?",o:["yesterday","now","just","always"],a:2,exp:"'Just' signals a recently completed action — used with Present Perfect."},
      {q:"'They _____ (meet) tomorrow at 3 PM.' (fixed plan)",o:["meet","are meeting","have met","will meeting"],a:1,exp:"Fixed future arrangements often use Present Continuous: 'They are meeting.'"},
      {q:"Present Simple negative: 'He _____ like coffee.'",o:["don't","isn't","doesn't","haven't"],a:2,exp:"For he/she/it, negative Present Simple uses 'doesn't'."},
      {q:"Which is a signal word for Present Simple?",o:["now","at the moment","usually","currently"],a:2,exp:"'Usually' indicates a regular habit, which is Present Simple."},
      {q:"'I _____ (live) in Tashkent for 10 years.' (still living there)",o:["live","lived","have lived","am living"],a:2,exp:"Present Perfect shows an action that started in the past and continues now."},
      {q:"Present Continuous question: '_____ you studying?'",o:["Do","Have","Are","Did"],a:2,exp:"Present Continuous questions: 'Are you + verb-ing?'"},
      {q:"'She has just _____ her homework.' (complete the sentence)",o:["finish","finishing","finished","finishes"],a:2,exp:"Present Perfect: have/has + past participle. 'finished' is the past participle of 'finish'."},
      {q:"'He _____ TV every evening.' (routine)",o:["is watching","watches","has watched","was watching"],a:1,exp:"Routines and habits use Present Simple: 'He watches TV every evening.'"},
      {q:"Which sentence is WRONG?",o:["I am reading a book.","She has eaten lunch.","He is knowing the answer.","They work hard."],a:2,exp:"'Know' is a stative verb — it cannot be used in continuous tenses."},
      {q:"'They _____ never visited New York.' (life experience)",o:["have","had","are","do"],a:0,exp:"Life experiences use Present Perfect: 'They have never visited New York.'"},
      {q:"'I _____ tired right now.' — which tense?",o:["am feeling — Present Continuous","feel — Present Simple","have felt — Present Perfect","all are correct"],a:3,exp:"Both 'I am feeling tired' and 'I feel tired' are correct in this context."},
      {q:"Signal word 'for 3 years' with a present connection uses:",o:["Present Simple","Past Simple","Present Perfect","Present Continuous"],a:2,exp:"Duration with present connection: 'I have lived here for 3 years.'"},
      {q:"'Does she speak French?' — what is the answer form?",o:["Yes, she speak.","Yes, she does.","Yes, she is.","Yes, she has."],a:1,exp:"Short answers for Present Simple: 'Yes, she does. / No, she doesn't.'"},
      {q:"'At the moment, he _____ a new project.' (currently working on it)",o:["works on","has worked on","is working on","worked on"],a:2,exp:"'At the moment' signals Present Continuous: 'is working on'."},
      {q:"Which is a stative verb (not used in continuous)?",o:["run","think (believe)","eat","sleep"],a:1,exp:"'Think' when meaning 'believe/consider' is stative and not used in continuous tenses."},
      {q:"'I _____ already _____ this film.' (I saw it before)",o:["have / seen","did / see","am / seeing","was / seeing"],a:0,exp:"Present Perfect with 'already': 'I have already seen this film.'"},
      {q:"Choose: 'The train _____ at 6 PM.' (timetable)",o:["is leaving","will leave","leaves","has left"],a:2,exp:"Timetabled future events use Present Simple: 'The train leaves at 6 PM.'"},
      {q:"'How long _____ you _____ English?' (studying up to now)",o:["did/study","do/study","have/been studying","are/study"],a:2,exp:"Duration up to now: 'How long have you been studying English?'"},
      {q:"Which sentence shows a general truth?",o:["She is swimming now.","I have eaten lunch.","The Earth revolves around the Sun.","He was running."],a:2,exp:"General and scientific truths use Present Simple."},
      {q:"'He _____ his keys. He can't find them.' (recent result)",o:["loses","is losing","has lost","lost"],a:2,exp:"Present Perfect shows a past action with a present result: 'He has lost his keys.'"},
      {q:"'Are you coming to the party?' This question uses:",o:["Present Simple","Present Continuous","Present Perfect","Future Simple"],a:1,exp:"Present Continuous for arranged future events: 'Are you coming?'"},
      {q:"Which adverb is used with Present Perfect?",o:["yesterday","last week","ago","recently"],a:3,exp:"'Recently' connects to the present and is used with Present Perfect."},
      {q:"'I _____ (not/see) him since Monday.'",o:["don't see","haven't seen","didn't see","am not seeing"],a:1,exp:"'Since' + Present Perfect: 'I haven't seen him since Monday.'"},
      {q:"'She always _____ (forget) her keys.' (criticism/habit)",o:["forgets","is forgetting","has forgotten","forgot"],a:0,exp:"Habitual actions (including annoying habits) use Present Simple with 'always'."},
      {q:"Present Perfect signal: 'I've been here _____ 2020.'",o:["ago","for","since","during"],a:2,exp:"'Since' + point in time is used with Present Perfect: 'since 2020'."},
    ],
  };
  // Generate generic questions for other topics
  if (!q[topic.id]) {
    q[topic.id] = generateGenericQuestions(topic);
  }
  return q[topic.id] || q['greetings'];
}

function generateGenericQuestions(topic) {
  const sets = {
    past_tenses:[
      {q:"What is the past simple of 'go'?",o:["goed","gone","went","goes"],a:2,exp:"'Go' is an irregular verb. Its past simple form is 'went'."},
      {q:"'I _____ a great movie yesterday.' (past simple)",o:["see","saw","have seen","seen"],a:1,exp:"Past Simple: 'I saw a great movie yesterday.' 'Yesterday' signals past simple."},
      {q:"Past Continuous: 'She _____ when I called.'",o:["slept","was sleeping","has slept","sleeps"],a:1,exp:"Past Continuous: was/were + verb-ing. 'She was sleeping when I called.'"},
      {q:"Past Perfect: 'When I arrived, he _____ already _____.'",o:["was/going","did/go","had/gone","has/gone"],a:2,exp:"Past Perfect: had + past participle. 'He had already gone.'"},
      {q:"Which is a signal word for Past Simple?",o:["just","already","since","last night"],a:3,exp:"'Last night' specifies a completed time in the past — signals Past Simple."},
      {q:"'They _____ (build) that bridge in 1990.'",o:["build","were building","built","have built"],a:2,exp:"Completed action at specific past time: Past Simple 'built'."},
      {q:"Past Simple negative: 'He _____ go to school.'",o:["didn't","doesn't","hadn't","wasn't"],a:0,exp:"Past Simple negative: 'didn't + base verb'. 'He didn't go.'"},
      {q:"'While she _____ (cook), the phone rang.'",o:["cooked","was cooking","had cooked","cooks"],a:1,exp:"Background past action: Past Continuous. 'While she was cooking...'"},
      {q:"'By the time we arrived, the film _____ (start).'",o:["started","was starting","has started","had started"],a:3,exp:"Action before another past action: Past Perfect. 'The film had started.'"},
      {q:"What is the past participle of 'take'?",o:["took","taked","taking","taken"],a:3,exp:"'Take' is irregular: take → took → taken."},
      {q:"'They _____ dinner when the lights went out.'",o:["had","were having","have had","had had"],a:1,exp:"Past Continuous shows an ongoing action interrupted by another: 'were having'."},
      {q:"Signal word for Past Perfect is often:",o:["now","tomorrow","by the time / before","since"],a:2,exp:"'By the time' and 'before' often signal Past Perfect."},
      {q:"'She _____ (not / finish) when I called.'",o:["didn't finish","wasn't finishing","hadn't finished","hasn't finished"],a:2,exp:"Past Perfect negative: 'hadn't + past participle'. 'She hadn't finished.'"},
      {q:"'I _____ (live) in London for 3 years before moving.'",o:["lived","was living","had lived","have lived"],a:2,exp:"Duration before a past event: Past Perfect. 'I had lived in London for 3 years.'"},
      {q:"'Where _____ you go last weekend?'",o:["do","did","have","were"],a:1,exp:"Past Simple question: 'did + subject + base verb'. 'Where did you go?'"},
      {q:"'They _____ (just / leave) when I arrived.' Meaning he left before I came.",o:["just left","just had left","had just left","were just leaving"],a:2,exp:"Past Perfect with 'just': 'They had just left.' — completed before another past action."},
      {q:"Which verb is regular in Past Simple?",o:["go","have","work","see"],a:2,exp:"'Work' is regular: work → worked. The others are irregular."},
      {q:"'Did you _____ a good time at the party?'",o:["had","having","have","has"],a:2,exp:"After 'did', use the base form: 'Did you have a good time?'"},
      {q:"'He _____ (read) all night when she came home.'",o:["read","was reading","had read","reads"],a:1,exp:"Ongoing action at a past moment: Past Continuous. 'He was reading all night.'"},
      {q:"Past simple of 'see' is:",o:["seened","seen","saw","seeing"],a:2,exp:"'See' is irregular: see → saw → seen."},
      {q:"'Before I arrived, she _____ (already / make) coffee.'",o:["already made","has already made","had already made","was already making"],a:2,exp:"Before another past event: Past Perfect. 'She had already made coffee.'"},
      {q:"'I _____ (not / know) the answer yesterday.'",o:["don't know","didn't know","hadn't known","wasn't knowing"],a:1,exp:"Past Simple negative: 'didn't know'. 'Knew' is the past of 'know'."},
      {q:"'She _____ (wait) for 2 hours when he finally arrived.'",o:["waited","was waiting","had been waiting","has waited"],a:2,exp:"Past Perfect Continuous shows duration before another past event."},
      {q:"'The children _____ (play) in the garden when it started raining.'",o:["played","were playing","had played","play"],a:1,exp:"Background interrupted action: Past Continuous. 'Were playing.'"},
      {q:"'He said he _____ (be) tired.' (reported speech)",o:["is","was","has been","be"],a:1,exp:"Reported speech past: tense backshift. Present 'is' becomes Past 'was'."},
      {q:"Past simple question: '_____ she come to the meeting?'",o:["Was","Did","Had","Has"],a:1,exp:"Past Simple questions use 'did': 'Did she come to the meeting?'"},
      {q:"'By 2020, they _____ (complete) the project.'",o:["completed","were completing","had completed","have completed"],a:2,exp:"Completed before a specific past time: Past Perfect. 'Had completed.'"},
      {q:"'We _____ (just / sit down) when the fire alarm went off.'",o:["just sat down","had just sat down","were just sitting","just had sat"],a:1,exp:"Past Perfect: action completed just before another past event."},
      {q:"Regular past tense ending is:",o:["-ing","-s/es","-ed","-en"],a:2,exp:"Regular verbs form past simple by adding '-ed': work → worked."},
      {q:"'I _____ (never / visit) Japan before that trip.'",o:["never visited","had never visited","never have visited","never was visiting"],a:1,exp:"Before a past reference: Past Perfect. 'I had never visited Japan before that trip.'"},
    ],
    future_tenses:[
      {q:"'I'll help you with that!' shows:",o:["Planned future","Spontaneous decision","Prediction with evidence","Timetable"],a:1,exp:"'Will' is used for spontaneous decisions made at the moment of speaking."},
      {q:"'I'm going to study medicine.' This is a:",o:["Spontaneous decision","Plan already decided","Scientific fact","Wish"],a:1,exp:"'Going to' expresses plans and intentions already decided."},
      {q:"'The train leaves at 6.' This uses:",o:["Future Simple","Going to","Present Simple for timetable","Present Continuous"],a:2,exp:"Timetabled future events use Present Simple."},
      {q:"'Look at those clouds! It _____ rain.' (evidence)",o:["will","is going to","leaves","would"],a:1,exp:"'Going to' for predictions based on visible evidence."},
      {q:"'By next year, I _____ graduated.' ",o:["will graduate","am going to graduate","will have graduated","graduate"],a:2,exp:"Future Perfect: 'will have + past participle' for completion before a future time."},
      {q:"Future Continuous: 'This time tomorrow, I _____ on the beach.'",o:["will lie","am going to lie","will be lying","would lie"],a:2,exp:"Future Continuous: 'will be + verb-ing' for ongoing action at a future time."},
      {q:"'She promises she _____ be late.' (promise = negative)",o:["won't","isn't going to","doesn't","will"],a:0,exp:"Promises often use 'will/won't': 'She won't be late.'"},
      {q:"'We _____ meeting at noon.' (pre-arranged)",o:["will","are","are going to be","had better"],a:1,exp:"Pre-arranged meetings use Present Continuous for future."},
      {q:"'Shall I open the window?' — 'shall' here is used for:",o:["Future fact","Offer/suggestion","Prediction","Habit"],a:1,exp:"'Shall I...?' is used to make offers or suggestions."},
      {q:"'I _____ (probably / go) to the gym later.' (personal intention, less certain)",o:["will probably go","am probably going to go","probably go","both a and b are correct"],a:3,exp:"Both 'will probably go' and 'am probably going to go' are correct here."},
      {q:"'By the time you arrive, I _____ (finish) cooking.'",o:["will finish","am finishing","will have finished","will be finishing"],a:2,exp:"Completion before a future time: Future Perfect. 'Will have finished.'"},
      {q:"Prediction based on opinion (not evidence) uses:",o:["going to","Present Continuous","will","Present Simple"],a:2,exp:"'Will' is used for predictions based on personal opinion without evidence."},
      {q:"'I _____ call you tonight.' (promise to call someone)",o:["will","am going to","would","shall"],a:0,exp:"Promises use 'will': 'I will call you tonight.'"},
      {q:"'This time next week, we _____ (fly) to London.'",o:["fly","will fly","will be flying","are flying"],a:2,exp:"Future Continuous: 'will be flying' — ongoing action at a future moment."},
      {q:"Signal word 'by' often indicates:",o:["Future Simple","Future Continuous","Future Perfect","Going to"],a:2,exp:"'By [time]' indicates completion before that time — Future Perfect."},
      {q:"'Are you doing anything tonight?' — 'I _____ (meet) friends.' (arranged)",o:["will meet","am meeting","am going to meet","meet"],a:1,exp:"Pre-arranged social plans use Present Continuous."},
      {q:"'Maybe it _____ snow tomorrow.' (possibility)",o:["is going to","will","snows","would"],a:1,exp:"'Maybe/perhaps' + 'will' for uncertain future possibility."},
      {q:"Future Perfect Continuous signal: 'By 2030, they _____ (research) this for 20 years.'",o:["will research","will have researched","will be researching","will have been researching"],a:3,exp:"Future Perfect Continuous: 'will have been + verb-ing' for ongoing duration before a future time."},
      {q:"'Hurry up! The film _____ (start) in 10 minutes!'",o:["starts","is starting","will have started","would start"],a:1,exp:"Timetabled imminent event: 'The film starts in 10 minutes!' (Present Simple)"},
      {q:"'I _____ (not / go) unless you invite me.' (conditional)",o:["won't go","am not going","don't go","didn't go"],a:0,exp:"Future negative: 'won't' + base verb in conditional sentences."},
      {q:"Complete: 'She _____ become a doctor.' (her childhood dream = plan)",o:["will","is going to","becomes","would"],a:1,exp:"'Going to' for firm plans and intentions."},
      {q:"'By 8 PM, they _____ (eat) dinner.' (already finished by then)",o:["will eat","will be eating","will have eaten","are eating"],a:2,exp:"Future Perfect: completed before a future time."},
      {q:"'Don't phone between 7 and 8 — I _____ (study).'",o:["study","will study","will be studying","am going to study"],a:2,exp:"Future Continuous: ongoing action at a specific future time. 'I will be studying.'"},
      {q:"Which is NOT used for future?",o:["Present Continuous","Present Simple","Past Perfect","Will"],a:2,exp:"Past Perfect refers to the past, not the future."},
      {q:"'He promised he _____ help.' (reported promise)",o:["will","would","is going to","shall"],a:1,exp:"In reported speech, 'will' changes to 'would'."},
      {q:"'According to the forecast, it _____ be sunny.' (forecast = evidence)",o:["will","going to","is going to","both b and c"],a:3,exp:"'Going to' for predictions based on evidence (forecast counts as evidence)."},
      {q:"'I _____ definitely visit you next month!' (strong intention)",o:["will","am definitely going to","both are correct","neither"],a:2,exp:"Both 'will' and 'going to' can express strong intentions."},
      {q:"Future Simple negative: 'She _____ attend the meeting.'",o:["doesn't","won't","isn't going","hadn't"],a:1,exp:"Future Simple negative: 'won't + base verb'."},
      {q:"'The new shopping center _____ (open) next spring.' (planned, announced)",o:["opens","will open","is going to open","will be opening"],a:2,exp:"Planned, announced future events: 'going to open' or Present Continuous."},
      {q:"'In 10 years, self-driving cars _____ (be) everywhere.' (prediction)",o:["are","will be","are going to","both b and c"],a:3,exp:"Both 'will be' and 'are going to be' work for predictions about the future."},
    ],
    conditionals:[
      {q:"'If you heat ice, it _____.' (zero conditional)",o:["melts","will melt","would melt","melted"],a:0,exp:"Zero conditional: If + Present Simple, Present Simple. Always true facts."},
      {q:"First Conditional: 'If it _____ tomorrow, we'll cancel the picnic.'",o:["rained","rains","would rain","rain"],a:1,exp:"First Conditional: If + Present Simple, will + base verb."},
      {q:"'If I _____ you, I'd apologize.' (advice) — correct form:",o:["am","were","was","be"],a:1,exp:"Second conditional uses 'were' for all subjects (not 'was') in formal English."},
      {q:"Third Conditional: 'If she had studied, she _____ the exam.'",o:["would pass","would have passed","will pass","passed"],a:1,exp:"Third conditional result: would have + past participle."},
      {q:"'Unless you hurry, you _____ miss the bus.' (first conditional)",o:["will","would","won't","would have"],a:0,exp:"'Unless' = 'If not'. 'Unless you hurry' = 'If you don't hurry'. Result: 'you will miss'."},
      {q:"'If I _____ a million dollars, I would travel.' — which conditional?",o:["First","Second","Third","Zero"],a:1,exp:"Second conditional: imaginary/hypothetical present situation."},
      {q:"Third conditional expresses:",o:["Real future possibility","Present imaginary situation","Past unreal situation","General truth"],a:2,exp:"Third conditional: imaginary alternative to a past event that didn't happen."},
      {q:"'If I had taken that job, I _____ rich now.' (mixed conditional)",o:["would be","would have been","was","am"],a:0,exp:"Mixed conditional: past action → present result. 'Would be' (not 'would have been')."},
      {q:"'Water _____ if you heat it to 100°C.' — zero conditional",o:["boiled","will boil","boils","would boil"],a:2,exp:"Zero conditional uses Present Simple in both clauses."},
      {q:"'If she _____ harder, she would have got the job.' — third conditional",o:["worked","works","had worked","would work"],a:2,exp:"Third conditional: If + Past Perfect, would have + past participle."},
      {q:"'I would buy a car if I _____ enough money.' — second conditional",o:["have","had","will have","would have"],a:1,exp:"Second conditional if-clause: Past Simple. 'If I had enough money.'"},
      {q:"First conditional is used for:",o:["Imaginary situations","Real, possible future situations","Scientific facts","Past regret"],a:1,exp:"First conditional describes real, possible future situations."},
      {q:"'If I _____ a bird, I would fly.' — second conditional",o:["am","was","were","be"],a:2,exp:"Second conditional: 'If I were a bird...' (imaginary situation)."},
      {q:"'She wouldn't have been hurt if she _____ more careful.' — third conditional",o:["were","was","had been","would be"],a:2,exp:"Third conditional if-clause: Past Perfect. 'If she had been more careful.'"},
      {q:"'_____ you help me if I asked you?' — second conditional",o:["Will","Would","Do","Had"],a:1,exp:"Second conditional question: 'Would you help me...?'"},
      {q:"'Provided that you study, you _____ pass.' (first conditional variant)",o:["would","will","had","pass"],a:1,exp:"'Provided that' = 'if'. First conditional: 'you will pass'."},
      {q:"Which type: 'If you press this button, the machine stops.'",o:["Zero","First","Second","Third"],a:0,exp:"Zero conditional: automatic result. 'The machine stops' — always true."},
      {q:"'If I _____ (know) then what I know now, I wouldn't have quit.' (third/mixed)",o:["know","had known","knew","would know"],a:1,exp:"Third conditional if-clause: Past Perfect. 'If I had known...'"},
      {q:"Mixed conditional: 'If I were more organized, I _____ finished the project.' (I didn't finish)",o:["would finish","will finish","would have finished","had finished"],a:2,exp:"Mixed conditional: present state → past result. 'Would have finished.'"},
      {q:"'As long as you _____, you can stay.' (zero/first conditional)",o:["behave","will behave","behaved","had behaved"],a:0,exp:"'As long as' + Present Simple for conditions."},
      {q:"Third conditional shows:",o:["Future wish","Present habit","Regret about the past","Current ability"],a:2,exp:"Third conditional is used to express regret or imagine alternative pasts."},
      {q:"'If it _____ be sunny, we'll go hiking.' — first conditional",o:["would","will","is","was"],a:2,exp:"First conditional if-clause: Present Simple. 'If it is sunny...'"},
      {q:"'He _____ call if he needed help.' — second conditional (he doesn't need help)",o:["will","would","called","had called"],a:1,exp:"Second conditional result: 'would + base verb'. 'He would call.'"},
      {q:"Correct third conditional: 'If she had arrived on time, ...'",o:["...we start the meeting.","...we would start.","...we would have started.","...we started."],a:2,exp:"Third conditional result: 'would have + past participle'. 'We would have started.'"},
      {q:"'Unless he _____ (apologize), she won't forgive him.' — first conditional",o:["apologizes","apologized","had apologized","would apologize"],a:0,exp:"'Unless' + Present Simple in first conditional. 'Unless he apologizes...'"},
      {q:"'What _____ you do if you won the lottery?' — second conditional",o:["will","would","do","did"],a:1,exp:"Second conditional question: 'What would you do if...?'"},
      {q:"'If only I _____ more time!' — expressing a wish",o:["have","had","will have","would have"],a:1,exp:"'If only + Past Simple' expresses a wish about the present."},
      {q:"'Suppose you _____ (find) a wallet, what would you do?' — second conditional",o:["find","found","had found","will find"],a:1,exp:"'Suppose' + Past Simple for hypothetical second conditional."},
      {q:"In third conditional, the if-clause verb form is:",o:["Past Simple","Present Simple","Past Perfect","Future Simple"],a:2,exp:"Third conditional if-clause: Past Perfect (had + past participle)."},
      {q:"'If it hadn't rained, we _____ (go) to the beach.' — third conditional",o:["would go","went","would have gone","had gone"],a:2,exp:"Third conditional result: 'would have + past participle'. 'We would have gone.'"},
    ],
    modal_verbs:[
      {q:"'You _____ wear a seatbelt. It's the law.' (strong obligation)",o:["should","might","must","could"],a:2,exp:"'Must' expresses strong obligation or necessity."},
      {q:"'She _____ swim when she was 3.' (past ability)",o:["can","could","must","should"],a:1,exp:"'Could' expresses past ability."},
      {q:"'You _____ smoke in hospitals.' (prohibition)",o:["mustn't","needn't","shouldn't","mightn't"],a:0,exp:"'Mustn't' expresses prohibition — something that is NOT allowed."},
      {q:"'It _____ rain later — look at those dark clouds.' (strong possibility)",o:["could","might","must","may"],a:2,exp:"'Must' for logical deduction based on strong evidence."},
      {q:"'_____ I use your phone?' (polite request for permission)",o:["Must","Should","Could","Would"],a:2,exp:"'Could' is more polite than 'can' for requesting permission."},
      {q:"'You _____ see a doctor. You look terrible.' (advice)",o:["must","should","could","will"],a:1,exp:"'Should' expresses advice or recommendation."},
      {q:"'She _____ be at home — her lights are on.' (deduction)",o:["may","might","must","should"],a:2,exp:"'Must' for strong logical deduction from evidence."},
      {q:"'_____ you like some tea?' (polite offer)",o:["Shall","Would","Could","Must"],a:1,exp:"'Would you like...?' is a polite offer."},
      {q:"'I _____ speak French when I was a child.' (past ability - can't do now)",o:["can","could","must","would"],a:1,exp:"'Could' for past ability that may not be present now."},
      {q:"'You _____ bring an umbrella — it might rain.' (advice/suggestion)",o:["must","should","shall","would"],a:1,exp:"'Should' gives advice. 'You should bring an umbrella.'"},
      {q:"'It _____ be true — I don't believe it!' (impossibility)",o:["can't","mustn't","shouldn't","wouldn't"],a:0,exp:"'Can't' expresses logical impossibility or disbelief."},
      {q:"'_____ you pass the salt, please?' (polite request)",o:["Must","Should","Could","Shall"],a:2,exp:"'Could you...?' is a polite request."},
      {q:"'She _____ be the new manager — I'm not sure.' (possibility ~50%)",o:["must","can","may","shall"],a:2,exp:"'May' expresses about 50% possibility."},
      {q:"'You _____ not enter without permission.' (prohibition/rule)",o:["can","must","shall","would"],a:1,exp:"'Must not' (mustn't) for prohibition — rules that forbid something."},
      {q:"'He _____ play tennis very well.' (general ability)",o:["could","might","can","would"],a:2,exp:"'Can' expresses general present ability."},
      {q:"Difference: 'must' vs 'have to' — 'must' is:",o:["External obligation","Internal/speaker's obligation","Possibility","Advice"],a:1,exp:"'Must' comes from the speaker's authority. 'Have to' comes from external rules."},
      {q:"'_____ I open the window?' (offering to do something - British English)",o:["Would","Could","Shall","Must"],a:2,exp:"'Shall I...?' is used to offer to do something for someone."},
      {q:"'You _____ finish all your food.' (it's not necessary)",o:["mustn't","needn't / don't have to","should","might"],a:1,exp:"'Needn't/don't have to' = no obligation, not necessary. ≠ mustn't (prohibition)."},
      {q:"'She _____ be exhausted after that long flight.' (logical deduction)",o:["might","may","must","could"],a:2,exp:"'Must' for strong logical deduction based on clear evidence."},
      {q:"Past modal: 'He _____ taken the money.' (strong deduction about past)",o:["must have","might have","should have","could have"],a:0,exp:"'Must have + past participle' = strong deduction about past events."},
      {q:"'You _____ have told me earlier!' (past criticism/regret)",o:["must","could","should","would"],a:2,exp:"'Should have + past participle' = past criticism or regret."},
      {q:"'I _____ swim when I was 5, but now I can't.' Which modal?",o:["can","must","could","would"],a:2,exp:"Past ability: 'could'. 'I could swim when I was 5.'"},
      {q:"'The roads are wet. It _____ have rained.' (deduction about past)",o:["must","might","should","could"],a:0,exp:"'Must have' for logical deduction about past events."},
      {q:"'_____ you tell me the time?' (very polite request)",o:["Can","Will","Could","Must"],a:2,exp:"'Could' is more polite than 'can' for requests."},
      {q:"'You _____ need to bring anything — we have everything.' (unnecessary action)",o:["mustn't","won't","needn't","shouldn't"],a:2,exp:"'Needn't' = 'don't need to' — the action is unnecessary."},
      {q:"'He _____ have been lying — his story didn't add up.' (past possibility)",o:["could","must","should","might"],a:0,exp:"'Could have' suggests past possibility."},
      {q:"'I _____ rather stay home tonight.' (preference)",o:["would","should","could","must"],a:0,exp:"'Would rather' expresses preference: 'I would rather stay home.'"},
      {q:"'She _____ arrive any minute now.' (near certainty/expectation)",o:["might","could","should","must"],a:2,exp:"'Should' can express expectation: 'She should arrive any minute.'"},
      {q:"'You _____ have left the stove on — be careful!' (warning about possible error)",o:["might","must","should","would"],a:0,exp:"'Might have' for possibility about past action."},
      {q:"Which modal expresses PERMISSION being granted?",o:["You must go.","You should go.","You may go.","You would go."],a:2,exp:"'May' is used to grant permission: 'You may go.'"},
    ],
  };

  if (sets[topic.id]) return sets[topic.id];

  // Fallback generic set for any topic
  return Array.from({length:30},(_,i)=>({
    q:`Question ${i+1} about ${topic.title.en}`,
    o:["Option A","Option B","Option C","Option D"],
    a:Math.floor(Math.random()*4),
    exp:`This tests your knowledge of ${topic.title.en}.`
  }));
}

// ===== APP STATE =====
let state = {
  progress: {}, // topicId: {score, passed}
  xp: 0,
};
try { const s = localStorage.getItem('emState'); if(s) state = JSON.parse(s); } catch(e){}

function saveState() {
  try { localStorage.setItem('emState', JSON.stringify(state)); } catch(e){}
  updateStats();
}

// ===== TEST ENGINE =====
let testState = {
  topicId: null,
  questions: [],
  current: 0,
  score: 0,
  answers: [],
  usedIndices: [],
};

function openLesson(topicId) {
  const topic = topics.find(t=>t.id===topicId);
  if (!topic) return;
  document.getElementById('lessonModalTitle').textContent = topic.title[currentLang] || topic.title.en;
  const body = document.getElementById('lessonModalBody');
  body.innerHTML = `
    <div class="lesson-content">${topic.content?.en || '<p>Lesson content coming soon!</p>'}</div>
    <button class="btn-start-test" onclick="startTest('${topicId}')">${t('startTest')}</button>
  `;
  document.getElementById('lessonModal').classList.add('show');
}

function closeLesson() { document.getElementById('lessonModal').classList.remove('show'); }

function startTest(topicId) {
  closeLesson();
  const topic = topics.find(t=>t.id===topicId);
  const allQ = generateQuestions(topic);
  
  // Shuffle and pick 30 unique questions
  const shuffled = [...allQ].sort(()=>Math.random()-0.5);
  const selected = shuffled.slice(0, Math.min(30, shuffled.length));
  // If < 30, duplicate and shuffle to fill
  while (selected.length < 30) {
    const extra = [...allQ].sort(()=>Math.random()-0.5);
    selected.push(...extra.slice(0, 30-selected.length));
  }

  testState = {topicId, questions: selected.slice(0,30), current:0, score:0, answers:[], usedIndices:[]};
  document.getElementById('testTopicLabel').textContent = topic.title[currentLang]||topic.title.en;
  document.getElementById('testModal').classList.add('show');
  renderQuestion();
}

function renderQuestion() {
  const {questions, current} = testState;
  const q = questions[current];
  document.getElementById('currentQ').textContent = current+1;
  document.getElementById('testProgressFill').style.width = `${((current)/30)*100}%`;
  document.getElementById('questionText').textContent = q.q;
  
  const opts = document.getElementById('optionsList');
  opts.innerHTML = '';
  // Shuffle options display
  const indices = q.o.map((_,i)=>i);
  const shuffledOpts = [...indices].sort(()=>Math.random()-0.5);
  q._displayOrder = shuffledOpts;
  shuffledOpts.forEach((origIdx,dispIdx)=>{
    const btn = document.createElement('button');
    btn.className = 'option-btn';
    btn.textContent = `${String.fromCharCode(65+dispIdx)}. ${q.o[origIdx]}`;
    btn.onclick = ()=>selectAnswer(origIdx, btn, dispIdx);
    opts.appendChild(btn);
  });
  
  document.getElementById('answerFeedback').className = 'answer-feedback';
  document.getElementById('answerFeedback').textContent = '';
  document.getElementById('btnNext').className = 'btn-next';
  document.getElementById('btnNext').textContent = (current===29?'See Results':'Next →');
}

function selectAnswer(optionIdx, clickedBtn, dispIdx) {
  const q = testState.questions[testState.current];
  const correct = q.a;
  const isCorrect = optionIdx === correct;
  
  // Disable all buttons
  document.querySelectorAll('.option-btn').forEach(b=>b.disabled=true);
  
  if (isCorrect) {
    clickedBtn.classList.add('correct');
    testState.score++;
  } else {
    clickedBtn.classList.add('wrong');
    // Highlight correct button
    const displayOrder = q._displayOrder;
    const correctDisplayIdx = displayOrder.indexOf(correct);
    const allBtns = document.querySelectorAll('.option-btn');
    allBtns[correctDisplayIdx].classList.add('correct');
  }
  
  const fb = document.getElementById('answerFeedback');
  fb.className = `answer-feedback show ${isCorrect?'correct':'wrong'}`;
  fb.textContent = isCorrect ? `✅ ${t('correct')} ${q.exp}` : `❌ ${t('wrong')} ${t('correctAnswerIs')} "${q.o[correct]}" — ${q.exp}`;
  
  testState.answers.push({q:q.q, correct:isCorrect});
  document.getElementById('btnNext').className = 'btn-next show';
}

function nextQuestion() {
  testState.current++;
  if (testState.current >= 30) {
    showResults();
  } else {
    renderQuestion();
  }
}

function showResults() {
  document.getElementById('testModal').classList.remove('show');
  const {score, topicId} = testState;
  const pct = Math.round((score/30)*100);
  
  // Save progress
  state.progress[topicId] = {score:pct, passed: pct>=50, timestamp: Date.now()};
  state.xp += Math.round(pct * 0.5);
  saveState();
  
  const grade = pct>=90?t('excellent'):pct>=70?t('great'):pct>=50?t('good'):t('needPractice');
  const angle = Math.round((pct/100)*360);
  
  const rv = document.getElementById('resultsView');
  rv.innerHTML = `
    <div class="results-score" style="background:conic-gradient(var(--accent) ${angle}deg, var(--surface2) ${angle}deg)">
      <div class="score-text"><div class="score-num">${pct}%</div><div class="score-label">${t('yourScore')}</div></div>
    </div>
    <div class="results-title">${score}/30 ${t('questionsCorrect')}</div>
    <div class="results-grade">${grade}</div>
    <div class="ai-feedback">
      <div class="ai-feedback-title"><div class="ai-badge">AI</div> <span>AI Analysis</span></div>
      <div class="ai-feedback-text" id="aiFeedbackText">
        <div class="loading-indicator"><div class="loading-dots"><span></span><span></span><span></span></div> ${t('aiAnalyzing')}</div>
      </div>
    </div>
    <div class="results-actions">
      <button class="btn-action btn-primary" onclick="startTest('${topicId}')">${t('retakeTest')}</button>
      <button class="btn-action btn-secondary" onclick="closeResults()">${t('backToTopics')}</button>
    </div>
  `;
  document.getElementById('resultsModal').classList.add('show');
  getAIFeedback(topicId, pct, score);
}

function closeResults() {
  document.getElementById('resultsModal').classList.remove('show');
  renderAll();
}

async function getAIFeedback(topicId, pct, score) {
  const topic = topics.find(t=>t.id===topicId);
  const wrongAnswers = testState.answers.filter(a=>!a.correct).map(a=>a.q).slice(0,5);
  const langName = currentLang==='ru'?'Russian':currentLang==='uz'?'Uzbek':'English';
  
  const prompt = `You are an expert English teacher. A student just completed a test on "${topic?.title?.en}" and scored ${score}/30 (${pct}%). 
Wrong questions included: ${wrongAnswers.join('; ')}.
Please respond in ${langName}.
Provide:
1. A brief personalized analysis of their performance (2-3 sentences)
2. Their main weakness area based on wrong questions
3. 2-3 specific study tips for improvement
4. An encouraging closing message

Keep it concise, friendly, and practical. Format with short paragraphs.`;

  try {
    const response = await fetch("https://api.anthropic.com/v1/messages", {
      method:"POST",
      headers:{"Content-Type":"application/json"},
      body: JSON.stringify({
        model:"claude-sonnet-4-20250514",
        max_tokens:1000,
        messages:[{role:"user",content:prompt}]
      })
    });
    const data = await response.json();
    const text = data.content?.map(c=>c.text||'').join('') || 'Analysis unavailable.';
    const el = document.getElementById('aiFeedbackText');
    if (el) el.innerHTML = text.replace(/\n/g,'<br>');
  } catch(e) {
    const el = document.getElementById('aiFeedbackText');
    if (el) el.textContent = `Score: ${pct}%. ${pct>=70?'Great job! Keep it up!':'Focus on reviewing the topic material and try again!'}`;
  }
}

// ===== RENDER TOPICS =====
function renderTopicCard(topic, container) {
  const prog = state.progress[topic.id];
  const pct = prog?.score || 0;
  const title = topic.title[currentLang] || topic.title.en;
  const desc = topic.desc[currentLang] || topic.desc.en;
  
  const card = document.createElement('div');
  card.className = 'topic-card';
  card.style.setProperty('--c1',topic.c1);
  card.style.setProperty('--c2',topic.c2);
  card.innerHTML = `
    ${prog?.passed?'<div class="completed-badge">✓ Done</div>':''}
    <div class="topic-icon">${topic.icon}</div>
    <div class="topic-title">${title}</div>
    <div class="topic-desc">${desc}</div>
    <div class="topic-meta">
      <span class="topic-level">${topic.level}</span>
      <span class="topic-progress">${pct>0?pct+'%':''}</span>
    </div>
    <div class="progress-bar"><div class="progress-fill" style="width:${pct}%"></div></div>
  `;
  card.onclick = ()=>openLesson(topic.id);
  container.appendChild(card);
}

// ===== LISTENING TAB =====
const listeningExercises = [
  {title:"Daily Routine Conversation",level:"A1",duration:"2:30",
   script:`Good morning! I'm Sarah. I wake up at 7 AM every day. First, I brush my teeth and take a shower. Then I have breakfast — usually eggs and coffee. I walk to work, it takes about 20 minutes. At work, I check emails and attend meetings. In the evening, I cook dinner and read a book before bed.`,
   questions:[
     {q:"What time does Sarah wake up?",o:["6 AM","7 AM","8 AM","9 AM"],a:1},
     {q:"What does she have for breakfast?",o:["Cereal","Pancakes","Eggs and coffee","Toast"],a:2},
     {q:"How long is her walk to work?",o:["10 minutes","15 minutes","20 minutes","30 minutes"],a:2},
   ]},
  {title:"Job Interview",level:"B1",duration:"3:15",
   script:`Interviewer: Thank you for coming in today. Can you tell me about yourself?
Candidate: Of course. I have 5 years of experience in marketing. I specialize in digital campaigns and social media. In my previous role, I increased online engagement by 40%.
Interviewer: That's impressive. Why do you want to join our company?
Candidate: I admire your innovative approach and global reach. I believe I can contribute significantly to your marketing team.`,
   questions:[
     {q:"How many years of experience does the candidate have?",o:["3 years","4 years","5 years","6 years"],a:2},
     {q:"What did the candidate increase by 40%?",o:["Sales","Online engagement","Team size","Budget"],a:1},
     {q:"Why does the candidate want to join the company?",o:["High salary","Innovative approach and global reach","Short commute","Good holidays"],a:1},
   ]},
  {title:"Weather Forecast",level:"A2",duration:"1:45",
   script:`Good evening, here's your weather forecast for tomorrow. In the morning, expect heavy rain and strong winds across the northern regions. Temperatures will drop to around 5 degrees Celsius. By afternoon, the rain will clear and we'll see some sunshine. Southern areas will remain dry throughout the day with temperatures reaching 15 degrees. Pack an umbrella just in case!`,
   questions:[
     {q:"What weather is expected in the morning in the north?",o:["Sunshine","Snow","Heavy rain and strong winds","Light breeze"],a:2},
     {q:"What temperature will it be in the morning?",o:["Around 5°C","Around 10°C","Around 15°C","Around 20°C"],a:0},
     {q:"What is the advice given at the end?",o:["Stay home","Pack a coat","Pack an umbrella","Wear sunscreen"],a:2},
   ]},
];

let audioIntervals = {};
let audioProgress = {};

function renderListening() {
  const container = document.getElementById('listeningContent');
  container.innerHTML = '';
  listeningExercises.forEach((ex,i)=>{
    const div = document.createElement('div');
    div.innerHTML = `
      <div class="audio-player" id="player${i}">
        <div class="audio-controls">
          <button class="play-btn" id="playBtn${i}" onclick="toggleAudio(${i})">▶</button>
          <div class="audio-info">
            <div class="audio-title">${ex.title}</div>
            <div class="audio-duration">🎯 Level: ${ex.level} | ⏱ ${ex.duration}</div>
            <div class="audio-track" onclick="seekAudio(event,${i})">
              <div class="audio-track-fill" id="trackFill${i}"></div>
            </div>
          </div>
        </div>
        <div class="audio-wave" id="wave${i}">
          ${Array(10).fill('<div class="wave-bar"></div>').join('')}
        </div>
      </div>
      <div class="reading-card">
        <div class="reading-card-header">
          <span style="font-weight:700">📝 Script</span>
          <button onclick="toggleScript(${i})" style="background:var(--surface);border:1px solid var(--border);color:var(--text2);padding:4px 10px;border-radius:6px;cursor:pointer;font-size:0.75rem">Show/Hide</button>
        </div>
        <div class="reading-body" id="script${i}" style="display:none">${ex.script}</div>
      </div>
      <div style="margin-bottom:12px">
        ${ex.questions.map((q,qi)=>`
          <div style="background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:16px;margin-bottom:10px">
            <div style="font-weight:600;margin-bottom:10px;font-size:0.9rem">${qi+1}. ${q.q}</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              ${q.o.map((opt,oi)=>`<button onclick="checkListeningAnswer(this,${oi},${q.a})" 
                style="background:var(--surface2);border:1px solid var(--border);border-radius:8px;padding:8px 12px;text-align:left;color:var(--text);cursor:pointer;font-family:'Sora',sans-serif;font-size:0.85rem;transition:all 0.2s">
                ${String.fromCharCode(65+oi)}. ${opt}
              </button>`).join('')}
            </div>
          </div>
        `).join('')}
      </div>
    `;
    container.appendChild(div);
  });
}

function toggleScript(i) {
  const el = document.getElementById(`script${i}`);
  el.style.display = el.style.display==='none'?'block':'none';
}

function toggleAudio(i) {
  const btn = document.getElementById(`playBtn${i}`);
  const wave = document.getElementById(`wave${i}`);
  const fill = document.getElementById(`trackFill${i}`);
  
  if (audioIntervals[i]) {
    clearInterval(audioIntervals[i]);
    delete audioIntervals[i];
    btn.textContent = '▶';
    wave.classList.remove('audio-playing');
    return;
  }
  
  // Stop all other players
  Object.keys(audioIntervals).forEach(k=>{ 
    clearInterval(audioIntervals[k]); 
    delete audioIntervals[k];
    const ob = document.getElementById(`playBtn${k}`);
    const ow = document.getElementById(`wave${k}`);
    if(ob) ob.textContent='▶';
    if(ow) ow.classList.remove('audio-playing');
  });
  
  btn.textContent = '⏸';
  wave.classList.add('audio-playing');
  audioProgress[i] = audioProgress[i] || 0;
  
  const duration = [150,195,105][i] || 120; // seconds
  audioIntervals[i] = setInterval(()=>{
    audioProgress[i] += 1;
    const pct = (audioProgress[i]/duration)*100;
    fill.style.width = Math.min(pct,100)+'%';
    if (pct >= 100) {
      clearInterval(audioIntervals[i]);
      delete audioIntervals[i];
      btn.textContent = '▶';
      wave.classList.remove('audio-playing');
      audioProgress[i] = 0;
      fill.style.width = '0%';
    }
  },1000);

  // Use speech synthesis to actually read the text
  if ('speechSynthesis' in window) {
    const ex = listeningExercises[i];
    window.speechSynthesis.cancel();
    const utter = new SpeechSynthesisUtterance(ex.script);
    utter.rate = 0.85;
    utter.lang = 'en-US';
    utter.onend = ()=>{
      clearInterval(audioIntervals[i]);
      delete audioIntervals[i];
      btn.textContent='▶';
      wave.classList.remove('audio-playing');
    };
    window.speechSynthesis.speak(utter);
  }
}

function seekAudio(e, i) {
  const rect = e.currentTarget.getBoundingClientRect();
  const pct = (e.clientX - rect.left) / rect.width;
  const duration = [150,195,105][i] || 120;
  audioProgress[i] = Math.floor(pct * duration);
  document.getElementById(`trackFill${i}`).style.width = (pct*100)+'%';
}

function checkListeningAnswer(btn, selected, correct) {
  const siblings = btn.parentElement.querySelectorAll('button');
  siblings.forEach(b=>b.disabled=true);
  if (selected === correct) {
    btn.style.background='rgba(16,185,129,0.2)';
    btn.style.borderColor='var(--accent3)';
    btn.style.color='var(--accent3)';
  } else {
    btn.style.background='rgba(239,68,68,0.2)';
    btn.style.borderColor='var(--accent5)';
    btn.style.color='var(--accent5)';
    siblings[correct].style.background='rgba(16,185,129,0.2)';
    siblings[correct].style.borderColor='var(--accent3)';
    siblings[correct].style.color='var(--accent3)';
  }
}

// ===== READING TAB =====
const readingPassages = [
  {title:"The Future of Artificial Intelligence",tag:"Technology",tagColor:"#00d4ff",
   text:`Artificial intelligence (AI) is rapidly transforming every sector of human life. From healthcare diagnostics to autonomous vehicles, AI systems are becoming increasingly sophisticated and integrated into our daily routines. Machine learning algorithms can now <span class="word-highlight" title="to detect or discover">detect</span> diseases earlier than human doctors, compose music, and even write code.

However, this technological revolution raises important <span class="word-highlight" title="relating to moral principles">ethical</span> questions. Who is responsible when an AI makes a mistake? How do we ensure that AI systems are fair and unbiased? These questions are at the heart of current AI research and policy debates.

Despite these challenges, experts remain <span class="word-highlight" title="feeling or showing confidence about the future">optimistic</span> about AI's potential. Many believe that AI will not replace human workers but will instead augment human capabilities, allowing us to focus on creativity, empathy, and complex problem-solving — things that machines cannot easily replicate.`,
   questions:[
     {q:"What can AI systems detect earlier than human doctors?",a:"diseases"},
     {q:"What is one ethical question raised by AI?",a:"responsibility/fairness"},
     {q:"According to experts, what will AI do to human workers?",a:"augment/enhance their capabilities"},
   ]},
  {title:"The Silk Road: Ancient Trade Network",tag:"History",tagColor:"#f59e0b",
   text:`The Silk Road was an ancient network of trade routes that connected East Asia with the Mediterranean world. <span class="word-highlight" title="extending across a large area">Spanning</span> over 4,000 miles, it facilitated not only the exchange of goods like silk, spices, and precious metals, but also the spread of ideas, religions, and cultures.

For centuries, merchants, diplomats, and explorers traveled these routes, facing enormous <span class="word-highlight" title="difficulty or suffering">hardships</span> including extreme weather, bandits, and treacherous mountain passes. The famous explorer Marco Polo documented his journeys along parts of the Silk Road in the 13th century, bringing knowledge of China's advanced civilization to European audiences.

Today, the spirit of the Silk Road lives on in China's Belt and Road Initiative, a massive modern infrastructure project connecting Asia, Europe, and Africa through roads, railways, and maritime routes — a 21st-century <span class="word-highlight" title="something made to look like another thing">version</span> of the ancient trade network.`,
   questions:[
     {q:"How many miles did the Silk Road span?",a:"over 4,000 miles"},
     {q:"What did Marco Polo document?",a:"his journeys along the Silk Road"},
     {q:"What is the modern equivalent mentioned in the text?",a:"Belt and Road Initiative"},
   ]},
];

function renderReading() {
  const container = document.getElementById('readingContent');
  container.innerHTML = '';
  readingPassages.forEach((p,i)=>{
    const div = document.createElement('div');
    div.className = 'reading-card';
    div.innerHTML = `
      <div class="reading-card-header">
        <span class="reading-tag" style="background:rgba(0,0,0,0.3);color:${p.tagColor}">${p.tag}</span>
        <span style="font-weight:700">${p.title}</span>
      </div>
      <div class="reading-body">${p.text}</div>
      <div style="padding:0 20px 20px">
        <div style="font-weight:700;margin-bottom:12px;font-size:0.9rem">📝 Comprehension Questions</div>
        ${p.questions.map((q,qi)=>`
          <div style="margin-bottom:12px">
            <div style="font-size:0.85rem;color:var(--text2);margin-bottom:6px">${qi+1}. ${q.q}</div>
            <div style="display:flex;gap:8px">
              <input type="text" placeholder="Your answer..." 
                style="flex:1;background:var(--surface2);border:1px solid var(--border);border-radius:8px;padding:8px 12px;color:var(--text);font-family:'Sora',sans-serif;font-size:0.85rem"
                id="readAns${i}_${qi}">
              <button onclick="checkReadingAnswer(${i},${qi},'${q.a}')" 
                style="background:var(--accent2);border:none;border-radius:8px;padding:8px 14px;color:#fff;font-family:'Sora',sans-serif;font-size:0.8rem;cursor:pointer">Check</button>
            </div>
            <div id="readFb${i}_${qi}" style="font-size:0.78rem;margin-top:4px;display:none"></div>
          </div>
        `).join('')}
      </div>
    `;
    container.appendChild(div);
  });
}

function checkReadingAnswer(pi, qi, correctHint) {
  const input = document.getElementById(`readAns${pi}_${qi}`);
  const fb = document.getElementById(`readFb${pi}_${qi}`);
  const val = input.value.trim().toLowerCase();
  const hints = correctHint.toLowerCase().split('/');
  const isCorrect = hints.some(h=>val.includes(h.trim()));
  fb.style.display='block';
  fb.style.color = isCorrect?'var(--accent3)':'var(--accent5)';
  fb.textContent = isCorrect?'✅ Good answer!':'💡 Think about: '+correctHint;
}

// ===== WRITING TAB =====
const writingPrompts = [
  {title:"Describe Your Ideal Day",prompt:"Write a paragraph (80-120 words) describing your perfect day. Include activities, places, and people. Use Present Simple or Present Continuous tenses.",minWords:80},
  {title:"Advantages and Disadvantages",prompt:"Write 150-200 words discussing the advantages and disadvantages of social media. Include at least 2 points for each side and give your personal opinion.",minWords:150},
  {title:"A Letter of Complaint",prompt:"Write a formal complaint letter (120-160 words) to a hotel about a recent bad experience. Include what went wrong, how it affected your stay, and what you expect as compensation.",minWords:120},
];

function renderWriting() {
  const container = document.getElementById('writingContent');
  container.innerHTML = '';
  writingPrompts.forEach((wp,i)=>{
    const div = document.createElement('div');
    div.innerHTML = `
      <div class="writing-prompt">
        <h3>${wp.title}</h3>
        <p>${wp.prompt}</p>
      </div>
      <textarea class="writing-area" id="writeArea${i}" placeholder="Start writing here..." 
        oninput="updateWordCount(${i})"></textarea>
      <div class="writing-meta">
        <span class="word-count" id="wc${i}">0 ${t('wordCount')}</span>
        <button class="btn-check-writing" onclick="checkWriting(${i})">${t('checkWriting')}</button>
      </div>
      <div class="ai-writing-feedback" id="writeFb${i}">
        <div style="font-weight:700;margin-bottom:8px;display:flex;align-items:center;gap:8px">
          <div class="ai-badge">AI</div> Feedback
        </div>
        <div id="writeFbText${i}"></div>
      </div>
      <div style="height:24px"></div>
    `;
    container.appendChild(div);
  });
}

function updateWordCount(i) {
  const text = document.getElementById(`writeArea${i}`).value;
  const words = text.trim().split(/\s+/).filter(w=>w.length>0).length;
  document.getElementById(`wc${i}`).textContent = `${words} ${t('wordCount')}`;
}

async function checkWriting(i) {
  const text = document.getElementById(`writeArea${i}`).value.trim();
  if (!text) return alert('Please write something first!');
  
  const fb = document.getElementById(`writeFb${i}`);
  const fbText = document.getElementById(`writeFbText${i}`);
  fb.className = 'ai-writing-feedback show';
  fbText.innerHTML = `<div class="loading-indicator"><div class="loading-dots"><span></span><span></span><span></span></div> AI is reviewing your writing...</div>`;
  
  const prompt = writingPrompts[i];
  const langName = currentLang==='ru'?'Russian':currentLang==='uz'?'Uzbek':'English';
  
  try {
    const response = await fetch("https://api.anthropic.com/v1/messages", {
      method:"POST",
      headers:{"Content-Type":"application/json"},
      body: JSON.stringify({
        model:"claude-sonnet-4-20250514",
        max_tokens:1000,
        messages:[{role:"user",content:`You are an expert English writing teacher. Please review this student's writing and provide detailed feedback in ${langName}.

Task: ${prompt.title}
Instructions: ${prompt.prompt}

Student's writing:
"${text}"

Please provide:
1. Overall score (X/10)
2. Grammar & vocabulary feedback (2-3 points)
3. Structure & coherence feedback
4. 2 specific sentences to correct or improve
5. Encouragement and one suggestion for improvement

Be supportive but honest. Format clearly with short sections.`}]
      })
    });
    const data = await response.json();
    const result = data.content?.map(c=>c.text||'').join('') || 'Feedback unavailable.';
    fbText.innerHTML = result.replace(/\n/g,'<br>');
  } catch(e) {
    const words = text.split(/\s+/).length;
    fbText.textContent = `Your text has ${words} words. ${words>=prompt.minWords?'Good length!':'Try to write more.'} Keep practicing!`;
  }
}

// ===== VOCABULARY TAB =====
const vocabWords = [
  {word:"Eloquent",phonetic:"/ˈɛl.ə.kwənt/",type:"adjective",tr:"красноречивый / ravon so'zlovchi",ex:"She gave an eloquent speech."},
  {word:"Pragmatic",phonetic:"/præɡˈmæt.ɪk/",type:"adjective",tr:"прагматичный / amaliy",ex:"We need a pragmatic solution."},
  {word:"Meticulous",phonetic:"/məˈtɪk.jʊ.ləs/",type:"adjective",tr:"тщательный / puxta",ex:"He is meticulous about details."},
  {word:"Resilient",phonetic:"/rɪˈzɪl.i.ənt/",type:"adjective",tr:"устойчивый / bardoshli",ex:"She is remarkably resilient."},
  {word:"Ambiguous",phonetic:"/æmˈbɪɡ.ju.əs/",type:"adjective",tr:"неоднозначный / noaniq",ex:"His answer was ambiguous."},
  {word:"Scrutinize",phonetic:"/ˈskruː.tɪ.naɪz/",type:"verb",tr:"тщательно изучать / sinchiklab ko'rmoq",ex:"They scrutinized every detail."},
  {word:"Benevolent",phonetic:"/bɪˈnev.ə.lənt/",type:"adjective",tr:"доброжелательный / xayrixoh",ex:"A benevolent smile crossed her face."},
  {word:"Inevitable",phonetic:"/ɪˈnev.ɪ.tə.bəl/",type:"adjective",tr:"неизбежный / muqarrar",ex:"Change is inevitable."},
  {word:"Perseverance",phonetic:"/ˌpɜː.sɪˈvɪər.əns/",type:"noun",tr:"упорство / qat'iyat",ex:"Success requires perseverance."},
  {word:"Subtle",phonetic:"/ˈsʌt.əl/",type:"adjective",tr:"тонкий / nozik",ex:"There is a subtle difference."},
  {word:"Deteriorate",phonetic:"/dɪˈtɪər.i.ə.reɪt/",type:"verb",tr:"ухудшаться / yomonlashmoq",ex:"His health began to deteriorate."},
  {word:"Reciprocal",phonetic:"/rɪˈsɪp.rə.kəl/",type:"adjective",tr:"взаимный / o'zaro",ex:"They had a reciprocal agreement."},
];

function renderVocabulary() {
  const grid = document.getElementById('vocabGrid');
  grid.innerHTML = '';
  vocabWords.forEach(v=>{
    const card = document.createElement('div');
    card.className = 'vocab-card';
    card.innerHTML = `
      <div class="vc-front">
        <div class="vc-word">${v.word}</div>
        <div class="vc-phonetic">${v.phonetic}</div>
        <div class="vc-type">${v.type}</div>
        <div class="flip-hint">👆 ${t('flip')}</div>
      </div>
      <div class="vc-back">
        <div class="vc-translation">${v.tr}</div>
        <div class="vc-example" style="margin-top:8px;font-size:0.8rem;color:var(--text2);font-style:italic">"${v.ex}"</div>
      </div>
    `;
    card.onclick = ()=>card.classList.toggle('flipped');
    grid.appendChild(card);
  });
}

// ===== GRAMMAR TAB =====
const grammarRules = [
  {title:"Subject-Verb Agreement",content:`<p>The verb must always agree with the subject in number (singular or plural).</p>
<table class="grammar-table"><tr><th>Correct ✅</th><th>Wrong ❌</th></tr>
<tr><td>She <strong>works</strong> hard.</td><td>She work hard.</td></tr>
<tr><td>They <strong>work</strong> hard.</td><td>They works hard.</td></tr>
<tr><td>The team <strong>is</strong> playing well. (singular team)</td><td>The team are playing well.</td></tr></table>
<p>Special cases: "Everyone, nobody, each, either" → singular verb. "A number of" → plural verb.</p>`},
  {title:"Articles: A, An, The — Quick Rules",content:`<p>Use <strong>a/an</strong> with singular countable nouns, first mention, or when saying what category something belongs to.</p>
<p>Use <strong>the</strong> when both speakers know which specific thing is meant, for unique things (the sun, the president), and with superlatives.</p>
<p>Use <strong>no article</strong> with uncountable nouns in general statements, plural nouns in general statements, and with most proper nouns.</p>
<table class="grammar-table"><tr><th>A/An</th><th>The</th><th>No Article</th></tr>
<tr><td>a dog (any dog)</td><td>the dog (specific)</td><td>dogs (in general)</td></tr>
<tr><td>an hour</td><td>the Sun</td><td>love, water</td></tr></table>`},
  {title:"Relative Clauses",content:`<p>Relative clauses add information about a noun. <strong>Defining</strong> clauses identify which person/thing we mean. <strong>Non-defining</strong> clauses add extra information and use commas.</p>
<table class="grammar-table"><tr><th>Pronoun</th><th>Use</th><th>Example</th></tr>
<tr><td>who/that</td><td>people</td><td>The man <strong>who</strong> called is here.</td></tr>
<tr><td>which/that</td><td>things</td><td>The book <strong>which</strong> I bought is great.</td></tr>
<tr><td>whose</td><td>possession</td><td>The girl <strong>whose</strong> bag was stolen...</td></tr>
<tr><td>where</td><td>places</td><td>The city <strong>where</strong> I was born...</td></tr></table>`},
  {title:"Gerunds and Infinitives",content:`<p>Some verbs are followed by a gerund (-ing form), some by an infinitive (to + verb), and some by either.</p>
<table class="grammar-table"><tr><th>Verb + Gerund</th><th>Verb + Infinitive</th><th>Both possible</th></tr>
<tr><td>enjoy, avoid, admit, deny, finish, suggest, imagine, mind, practise, risk</td><td>want, need, hope, decide, plan, agree, manage, refuse, seem, offer</td><td>like, love, hate, begin, start, continue, prefer</td></tr></table>
<div style="margin-top:10px"><em>She enjoys reading. / She decided to leave. / She likes to swim / swimming.</em></div>`},
];

function renderGrammar() {
  const container = document.getElementById('grammarContent');
  container.innerHTML = '';
  grammarRules.forEach((r,i)=>{
    const div = document.createElement('div');
    div.className = 'grammar-rule';
    div.innerHTML = `
      <div class="grammar-rule-header" onclick="toggleGrammar(${i})">
        <span class="grammar-rule-title">${r.title}</span>
        <span id="grammarArrow${i}">▼</span>
      </div>
      <div class="grammar-rule-body" id="grammarBody${i}">${r.content}</div>
    `;
    container.appendChild(div);
  });
}

function toggleGrammar(i) {
  const body = document.getElementById(`grammarBody${i}`);
  const arrow = document.getElementById(`grammarArrow${i}`);
  body.classList.toggle('open');
  arrow.textContent = body.classList.contains('open')?'▲':'▼';
}

// ===== SPEAKING TAB =====
const speakingTopics = [
  {title:"Tell Me About Yourself",bullets:["Your name and where you're from","Your job or studies","Your hobbies and interests","Your goals for the future"]},
  {title:"Describe a Memorable Journey",bullets:["Where did you go and when?","Who did you travel with?","What was the highlight?","Would you go again? Why?"]},
  {title:"Technology in Daily Life",bullets:["How do you use technology daily?","What's the best invention in your life?","Are there any negative effects?","Predict technology in 10 years."]},
];
let mediaRecorder = null, isRecording = false;

function renderSpeaking() {
  const container = document.getElementById('speakingContent');
  container.innerHTML = speakingTopics.map((s,i)=>`
    <div class="speaking-topic">
      <h3>💬 ${s.title}</h3>
      <ul class="speaking-bullets">${s.bullets.map(b=>`<li>${b}</li>`).join('')}</ul>
      <button class="record-btn" id="recBtn${i}" onclick="toggleRecord(${i})">
        <div class="record-dot"></div>
        <span id="recLabel${i}">${t('startRecord')}</span>
      </button>
      <div id="recFb${i}" style="margin-top:10px;font-size:0.8rem;color:var(--text2)"></div>
    </div>
  `).join('');
}

async function toggleRecord(i) {
  const btn = document.getElementById(`recBtn${i}`);
  const label = document.getElementById(`recLabel${i}`);
  const fb = document.getElementById(`recFb${i}`);
  
  if (isRecording) {
    if (mediaRecorder) mediaRecorder.stop();
    isRecording = false;
    btn.classList.remove('recording');
    label.textContent = t('startRecord');
    fb.textContent = '✅ Recording saved! Keep practicing your speaking.';
    return;
  }
  
  try {
    const stream = await navigator.mediaDevices.getUserMedia({audio:true});
    mediaRecorder = new MediaRecorder(stream);
    mediaRecorder.start();
    isRecording = true;
    btn.classList.add('recording');
    label.textContent = t('stopRecord');
    fb.textContent = '🔴 Recording... Speak clearly and confidently!';
    mediaRecorder.onstop = ()=>{ stream.getTracks().forEach(t=>t.stop()); };
  } catch(e) {
    fb.textContent = '⚠️ Microphone access denied. Please allow microphone access to record.';
  }
}

// ===== LEADERBOARD =====
const leaderboardData = [
  {rank:1,name:"Aziz K.",emoji:"🏆",score:2840,topics:12,avg:94},
  {rank:2,name:"Maria S.",emoji:"⭐",score:2650,topics:11,avg:89},
  {rank:3,name:"John D.",emoji:"🥉",score:2410,topics:10,avg:85},
  {rank:4,name:"Fatima M.",emoji:"📚",score:2180,topics:9,avg:82},
  {rank:5,name:"Alex P.",emoji:"🎯",score:1950,topics:8,avg:78},
  {rank:6,name:"Sofia L.",emoji:"✨",score:1720,topics:7,avg:74},
  {rank:7,name:"You",emoji:"👤",score:state.xp,topics:Object.keys(state.progress).length,avg:state.xp>0?Math.round(Object.values(state.progress).reduce((a,b)=>a+b.score,0)/Math.max(Object.keys(state.progress).length,1)):0,isYou:true},
];

function renderLeaderboard() {
  const container = document.getElementById('leaderboardList');
  const sorted = [...leaderboardData];
  sorted[6].score = state.xp;
  sorted[6].topics = Object.keys(state.progress).length;
  sorted.sort((a,b)=>b.score-a.score);
  
  container.innerHTML = sorted.map((p,i)=>`
    <div class="leaderboard-item" style="${p.isYou?'border-color:var(--accent);background:rgba(0,212,255,0.05)':''}">
      <div class="rank-num ${i===0?'rank-1':i===1?'rank-2':i===2?'rank-3':''}">${i===0?'🥇':i===1?'🥈':i===2?'🥉':i+1}</div>
      <div class="rank-avatar" style="background:var(--surface2)">${p.emoji}</div>
      <div class="rank-info">
        <div class="rank-name">${p.name}${p.isYou?' (You)':''}</div>
        <div class="rank-details">${p.topics} topics • Avg: ${p.avg}%</div>
      </div>
      <div class="rank-score">${p.score} XP</div>
    </div>
  `).join('');
}

// ===== ACHIEVEMENTS =====
const achievements = [
  {icon:"🎯",name:"First Test",desc:"Complete your first test",check:()=>Object.keys(state.progress).length>=1},
  {icon:"📚",name:"Scholar",desc:"Complete 5 topics",check:()=>Object.keys(state.progress).length>=5},
  {icon:"🏆",name:"Master",desc:"Complete all topics",check:()=>Object.keys(state.progress).length>=12},
  {icon:"⭐",name:"Perfect Score",desc:"Get 100% on any test",check:()=>Object.values(state.progress).some(p=>p.score>=100)},
  {icon:"🔥",name:"On Fire",desc:"Score 90%+ on 3 tests",check:()=>Object.values(state.progress).filter(p=>p.score>=90).length>=3},
  {icon:"📝",name:"Writer",desc:"Write 3 essays",check:()=>false},
  {icon:"🎧",name:"Listener",desc:"Complete listening",check:()=>false},
  {icon:"🗣️",name:"Speaker",desc:"Record 3 speeches",check:()=>false},
];

function renderProfile() {
  const completed = Object.keys(state.progress).length;
  const level = completed>=10?'Advanced':completed>=5?'Intermediate':completed>=2?'Elementary':'Beginner';
  const num = completed>=10?5:completed>=5?4:completed>=2?2:1;
  document.getElementById('profileLevel').textContent = `Level ${num} — ${level}`;
  
  const grid = document.getElementById('achievementsGrid');
  grid.innerHTML = achievements.map(a=>`
    <div class="achievement-item ${a.check()?'':'locked'}">
      <div class="achievement-icon">${a.icon}</div>
      <div class="achievement-name">${a.name}</div>
      <div class="achievement-desc">${a.desc}</div>
    </div>
  `).join('');
}

// ===== STATS UPDATE =====
function updateStats() {
  const completed = Object.keys(state.progress).length;
  const scores = Object.values(state.progress).map(p=>p.score);
  const avg = scores.length>0?Math.round(scores.reduce((a,b)=>a+b,0)/scores.length):0;
  
  document.getElementById('completedTopics').textContent = completed;
  document.getElementById('avgScore').textContent = avg>0?avg+'%':'—';
  document.getElementById('totalXP').textContent = state.xp;
  document.getElementById('totalProgressBadge').textContent = state.xp+' XP';
}

// ===== RENDER ALL =====
function renderAll() {
  // Home
  const hg = document.getElementById('homeTopicsGrid');
  hg.innerHTML = '';
  topics.forEach(t=>renderTopicCard(t,hg));
  
  // Lessons
  const ag = document.getElementById('allTopicsGrid');
  ag.innerHTML = '';
  topics.forEach(t=>renderTopicCard(t,ag));
  
  renderListening();
  renderReading();
  renderWriting();
  renderVocabulary();
  renderGrammar();
  renderSpeaking();
  renderLeaderboard();
  renderProfile();
  updateStats();
  
  // Re-apply translations
  document.querySelectorAll('[data-t]').forEach(el=>{
    el.textContent = t(el.getAttribute('data-t'));
  });
}

// ===== TAB SWITCHING =====
function switchTab(name) {
  document.querySelectorAll('.tab-content').forEach(el=>el.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(el=>el.classList.remove('active'));
  document.getElementById('tab-'+name).classList.add('active');
  document.getElementById('tab'+name.charAt(0).toUpperCase()+name.slice(1)).classList.add('active');
}

// Close modals on overlay click
document.getElementById('lessonModal').addEventListener('click',function(e){
  if(e.target===this) closeLesson();
});
document.getElementById('testModal').addEventListener('click',function(e){
  if(e.target===this) document.getElementById('testModal').classList.remove('show');
});
document.getElementById('resultsModal').addEventListener('click',function(e){
  if(e.target===this) closeResults();
});

// ===== INIT =====
renderAll();
</script>
</body>
</html>
