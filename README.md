<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SpeakUP English</title>
  <link
    href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Orbitron:wght@700;900&display=swap"
    rel="stylesheet">
  <style>
    :root {
      --bg: #0d0f1a;
      --bg2: #151827;
      --bg3: #1e2235;
      --card: #1a1e30;
      --accent: #6c63ff;
      --accent2: #ff6584;
      --accent3: #43e97b;
      --accent4: #f7971e;
      --text: #e8eaf6;
      --text2: #9fa8c9;
      --border: #2a2f4a;
      --gold: #ffd700;
      --silver: #c0c0c0;
      --bronze: #cd7f32;
      --danger: #ff4757;
      --success: #2ed573;
      --radius: 16px;
      --shadow: 0 8px 32px rgba(108, 99, 255, 0.15);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Nunito', sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      background: var(--bg2);
      border-bottom: 1px solid var(--border);
      padding: 0 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 64px;
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    .logo {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.3rem;
      color: var(--accent);
      letter-spacing: 2px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .logo span {
      color: var(--accent2);
    }

    .nav-tabs {
      display: flex;
      gap: 4px;
      overflow-x: auto;
    }

    .nav-tab {
      background: none;
      border: none;
      color: var(--text2);
      font-family: 'Nunito', sans-serif;
      font-size: .85rem;
      font-weight: 700;
      padding: 8px 14px;
      border-radius: 10px;
      cursor: pointer;
      transition: .2s;
      white-space: nowrap;
    }

    .nav-tab:hover,
    .nav-tab.active {
      background: var(--accent);
      color: #fff;
    }

    .lang-sel {
      display: flex;
      gap: 6px;
    }

    .lang-btn {
      background: var(--bg3);
      border: 1px solid var(--border);
      color: var(--text2);
      font-size: .8rem;
      font-weight: 700;
      padding: 5px 10px;
      border-radius: 8px;
      cursor: pointer;
      transition: .2s;
    }

    .lang-btn.active,
    .lang-btn:hover {
      background: var(--accent);
      color: #fff;
      border-color: var(--accent);
    }

    /* MAIN */
    main {
      max-width: 960px;
      margin: 0 auto;
      padding: 24px 16px;
    }

    .page {
      display: none;
    }

    .page.active {
      display: block;
    }

    /* CARDS */
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 24px;
      margin-bottom: 20px;
      box-shadow: var(--shadow);
    }

    h2 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.3rem;
      margin-bottom: 16px;
      color: var(--accent);
    }

    h3 {
      font-size: 1.1rem;
      font-weight: 800;
      margin-bottom: 12px;
      color: var(--text);
    }

    /* HOME */
    .hero {
      text-align: center;
      padding: 40px 20px;
    }

    .hero h1 {
      font-family: 'Orbitron', sans-serif;
      font-size: 2.5rem;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 12px;
    }

    .hero p {
      color: var(--text2);
      font-size: 1.1rem;
      margin-bottom: 28px;
    }

    .level-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 16px;
      margin-top: 20px;
    }

    .level-card {
      background: var(--bg3);
      border: 2px solid var(--border);
      border-radius: var(--radius);
      padding: 20px;
      cursor: pointer;
      transition: .3s;
      text-align: center;
    }

    .level-card:hover {
      border-color: var(--accent);
      transform: translateY(-3px);
      box-shadow: 0 12px 32px rgba(108, 99, 255, .3);
    }

    .level-card .icon {
      font-size: 2.5rem;
      margin-bottom: 10px;
    }

    .level-card h3 {
      font-size: 1rem;
      margin-bottom: 6px;
    }

    .level-card .prog {
      background: var(--bg2);
      border-radius: 8px;
      height: 8px;
      margin-top: 10px;
      overflow: hidden;
    }

    .level-card .prog-bar {
      height: 100%;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      border-radius: 8px;
      transition: .5s;
    }

    /* TOPICS */
    .topic-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .topic-item {
      background: var(--bg3);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      cursor: pointer;
      transition: .2s;
    }

    .topic-item:hover {
      border-color: var(--accent);
      background: var(--bg2);
    }

    .topic-item .left {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .topic-icon {
      width: 44px;
      height: 44px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      background: var(--bg2);
    }

    .topic-name {
      font-weight: 800;
      font-size: 1rem;
    }

    .topic-desc {
      color: var(--text2);
      font-size: .85rem;
      margin-top: 2px;
    }

    .badge {
      background: var(--accent);
      color: #fff;
      font-size: .75rem;
      font-weight: 700;
      padding: 3px 10px;
      border-radius: 20px;
    }

    .badge.done {
      background: var(--accent3);
      color: #000;
    }

    /* LESSON */
    .lesson-content {
      line-height: 1.9;
      color: var(--text2);
      font-size: .97rem;
    }

    .lesson-content h4 {
      color: var(--accent);
      font-size: 1rem;
      margin: 18px 0 8px;
      font-weight: 800;
    }

    .lesson-content table {
      width: 100%;
      border-collapse: collapse;
      margin: 12px 0;
    }

    .lesson-content th {
      background: var(--accent);
      color: #fff;
      padding: 8px 12px;
      text-align: left;
      font-size: .9rem;
    }

    .lesson-content td {
      padding: 8px 12px;
      border-bottom: 1px solid var(--border);
      font-size: .9rem;
    }

    .lesson-content .example {
      background: var(--bg3);
      border-left: 4px solid var(--accent2);
      padding: 10px 16px;
      border-radius: 0 8px 8px 0;
      margin: 10px 0;
      font-style: italic;
    }

    .start-test-btn {
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      color: #fff;
      border: none;
      padding: 14px 36px;
      border-radius: 12px;
      font-size: 1rem;
      font-weight: 800;
      cursor: pointer;
      margin-top: 20px;
      transition: .2s;
    }

    .start-test-btn:hover {
      transform: scale(1.04);
      box-shadow: 0 6px 24px rgba(108, 99, 255, .4);
    }

    /* TEST */
    .question-block {
      margin-bottom: 24px;
    }

    .q-text {
      font-size: 1.1rem;
      font-weight: 700;
      margin-bottom: 14px;
      line-height: 1.5;
    }

    .options {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .opt-btn {
      background: var(--bg3);
      border: 2px solid var(--border);
      color: var(--text);
      font-family: 'Nunito', sans-serif;
      font-size: .95rem;
      padding: 12px 18px;
      border-radius: 10px;
      cursor: pointer;
      text-align: left;
      transition: .2s;
      font-weight: 600;
    }

    .opt-btn:hover:not(:disabled) {
      border-color: var(--accent);
      background: var(--bg2);
    }

    .opt-btn.correct {
      border-color: var(--success);
      background: rgba(46, 213, 115, .12);
      color: var(--success);
    }

    .opt-btn.wrong {
      border-color: var(--danger);
      background: rgba(255, 71, 87, .1);
      color: var(--danger);
    }

    .prog-bar-test {
      height: 8px;
      background: var(--bg3);
      border-radius: 8px;
      margin-bottom: 20px;
      overflow: hidden;
    }

    .prog-bar-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      transition: .4s;
    }

    .result-box {
      text-align: center;
      padding: 30px;
    }

    .result-score {
      font-family: 'Orbitron', sans-serif;
      font-size: 3rem;
      margin: 16px 0;
      background: linear-gradient(135deg, var(--accent), var(--gold));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .result-msg {
      font-size: 1.1rem;
      color: var(--text2);
      margin-bottom: 20px;
    }

    .btn {
      background: var(--accent);
      color: #fff;
      border: none;
      padding: 11px 26px;
      border-radius: 10px;
      font-size: .95rem;
      font-weight: 700;
      cursor: pointer;
      transition: .2s;
      font-family: 'Nunito', sans-serif;
    }

    .btn:hover {
      opacity: .85;
      transform: scale(1.03);
    }

    .btn.outline {
      background: none;
      border: 2px solid var(--accent);
      color: var(--accent);
    }

    .btn.danger {
      background: var(--danger);
    }

    .btn.success {
      background: var(--success);
      color: #000;
    }

    /* VOCAB */
    .vocab-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }

    .vocab-card {
      background: var(--bg3);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px;
      cursor: pointer;
      transition: .2s;
      text-align: center;
    }

    .vocab-card:hover {
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .vocab-word {
      font-size: 1.2rem;
      font-weight: 900;
      color: var(--accent);
    }

    .vocab-tr {
      font-size: .85rem;
      color: var(--text2);
      margin-top: 4px;
    }

    .vocab-pos {
      font-size: .75rem;
      background: var(--bg2);
      border-radius: 6px;
      padding: 2px 8px;
      display: inline-block;
      margin-top: 6px;
      color: var(--accent4);
    }

    .vocab-ex {
      font-size: .8rem;
      color: var(--text2);
      font-style: italic;
      margin-top: 8px;
      display: none;
    }

    .vocab-card:hover .vocab-ex {
      display: block;
    }

    .search-bar {
      width: 100%;
      background: var(--bg3);
      border: 1px solid var(--border);
      color: var(--text);
      font-size: 1rem;
      padding: 12px 16px;
      border-radius: 10px;
      margin-bottom: 16px;
      font-family: 'Nunito', sans-serif;
    }

    .search-bar:focus {
      outline: none;
      border-color: var(--accent);
    }

    /* LISTENING */
    .audio-player {
      background: var(--bg3);
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 16px;
    }

    .audio-title {
      font-weight: 800;
      margin-bottom: 10px;
    }

    .audio-controls {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .play-btn {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: var(--accent);
      border: none;
      color: #fff;
      font-size: 1.3rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: .2s;
    }

    .play-btn:hover {
      background: var(--accent2);
    }

    .audio-progress {
      flex: 1;
      height: 6px;
      background: var(--bg2);
      border-radius: 4px;
      overflow: hidden;
      cursor: pointer;
    }

    .audio-prog-fill {
      height: 100%;
      background: var(--accent);
      border-radius: 4px;
      transition: .1s;
    }

    .audio-time {
      font-size: .8rem;
      color: var(--text2);
    }

    .transcript-box {
      background: var(--bg2);
      border-radius: 8px;
      padding: 14px;
      font-size: .9rem;
      line-height: 1.8;
      color: var(--text2);
      max-height: 180px;
      overflow-y: auto;
      margin-top: 10px;
    }

    /* SPEAKING */
    .speak-bubble {
      background: var(--bg3);
      border-radius: 16px;
      padding: 20px;
      margin: 12px 0;
      position: relative;
    }

    .speak-bubble.ai {
      border-left: 4px solid var(--accent);
    }

    .speak-bubble.user {
      border-left: 4px solid var(--accent2);
    }

    .speak-who {
      font-size: .8rem;
      font-weight: 700;
      color: var(--text2);
      margin-bottom: 6px;
    }

    .speak-text {
      font-size: 1rem;
      line-height: 1.6;
    }

    .mic-btn {
      width: 64px;
      height: 64px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent2), #ff3060);
      border: none;
      color: #fff;
      font-size: 1.8rem;
      cursor: pointer;
      margin: 16px auto;
      display: block;
      transition: .2s;
      box-shadow: 0 6px 24px rgba(255, 101, 132, .4);
    }

    .mic-btn:hover,
    .mic-btn.recording {
      transform: scale(1.1);
      background: var(--danger);
    }

    .mic-btn.recording {
      animation: pulse 1s infinite;
    }

    @keyframes pulse {

      0%,
      100% {
        box-shadow: 0 6px 24px rgba(255, 71, 87, .4);
      }

      50% {
        box-shadow: 0 6px 40px rgba(255, 71, 87, .7);
      }
    }

    /* READING */
    .reading-text {
      background: var(--bg3);
      border-radius: 12px;
      padding: 20px;
      line-height: 2;
      font-size: .97rem;
      color: var(--text2);
      margin-bottom: 16px;
      max-height: 320px;
      overflow-y: auto;
    }

    /* AI CHAT */
    .chat-area {
      height: 340px;
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      gap: 10px;
      padding: 4px;
    }

    .msg {
      max-width: 80%;
      padding: 12px 16px;
      border-radius: 14px;
      font-size: .93rem;
      line-height: 1.6;
    }

    .msg.ai {
      background: var(--bg3);
      border: 1px solid var(--border);
      align-self: flex-start;
      border-bottom-left-radius: 4px;
    }

    .msg.user {
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      color: #fff;
      align-self: flex-end;
      border-bottom-right-radius: 4px;
    }

    .msg.typing {
      color: var(--text2);
    }

    .chat-input-row {
      display: flex;
      gap: 10px;
      margin-top: 12px;
    }

    .chat-input {
      flex: 1;
      background: var(--bg3);
      border: 1px solid var(--border);
      color: var(--text);
      font-family: 'Nunito', sans-serif;
      font-size: .95rem;
      padding: 11px 14px;
      border-radius: 10px;
    }

    .chat-input:focus {
      outline: none;
      border-color: var(--accent);
    }

    /* LEADERBOARD */
    .lb-row {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 12px 16px;
      background: var(--bg3);
      border-radius: 10px;
      margin-bottom: 8px;
      border: 1px solid var(--border);
    }

    .lb-rank {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.1rem;
      font-weight: 900;
      width: 36px;
      text-align: center;
    }

    .lb-rank.g {
      color: var(--gold);
    }

    .lb-rank.s {
      color: var(--silver);
    }

    .lb-rank.b {
      color: var(--bronze);
    }

    .lb-name {
      flex: 1;
      font-weight: 800;
    }

    .lb-xp {
      color: var(--accent4);
      font-weight: 700;
    }

    .lb-badge {
      background: var(--accent);
      color: #fff;
      font-size: .75rem;
      padding: 2px 9px;
      border-radius: 20px;
    }

    /* STATS */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
      gap: 14px;
    }

    .stat-card {
      background: var(--bg3);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 18px;
      text-align: center;
    }

    .stat-num {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.8rem;
      font-weight: 900;
      color: var(--accent);
      margin-bottom: 4px;
    }

    .stat-label {
      font-size: .8rem;
      color: var(--text2);
    }

    /* TABS within page */
    .inner-tabs {
      display: flex;
      gap: 8px;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    .inner-tab {
      background: var(--bg3);
      border: 1px solid var(--border);
      color: var(--text2);
      font-size: .85rem;
      font-weight: 700;
      padding: 7px 16px;
      border-radius: 8px;
      cursor: pointer;
      transition: .2s;
    }

    .inner-tab.active,
    .inner-tab:hover {
      background: var(--accent);
      color: #fff;
      border-color: var(--accent);
    }

    .inner-page {
      display: none;
    }

    .inner-page.active {
      display: block;
    }

    /* misc */
    .flex {
      display: flex;
      gap: 10px;
      align-items: center;
    }

    .flex-wrap {
      flex-wrap: wrap;
    }

    .mt {
      margin-top: 14px;
    }

    .text-center {
      text-align: center;
    }

    .emoji-big {
      font-size: 3rem;
      margin: 10px 0;
    }

    select {
      background: var(--bg3);
      border: 1px solid var(--border);
      color: var(--text);
      padding: 8px 12px;
      border-radius: 8px;
      font-family: 'Nunito', sans-serif;
      font-size: .9rem;
    }

    .highlight {
      color: var(--accent4);
      font-weight: 700;
    }

    /* scrollbar */
    ::-webkit-scrollbar {
      width: 6px;
    }

    ::-webkit-scrollbar-track {
      background: var(--bg2);
    }

    ::-webkit-scrollbar-thumb {
      background: var(--border);
      border-radius: 4px;
    }

    .spinner {
      width: 36px;
      height: 36px;
      border: 4px solid var(--border);
      border-top-color: var(--accent);
      border-radius: 50%;
      animation: spin .7s linear infinite;
      margin: 20px auto;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    .hidden {
      display: none !important;
    }

    .back-btn {
      background: none;
      border: none;
      color: var(--text2);
      font-size: .9rem;
      cursor: pointer;
      padding: 4px 0;
      display: flex;
      align-items: center;
      gap: 6px;
      margin-bottom: 14px;
    }

    .back-btn:hover {
      color: var(--accent);
    }

    .xp-bar {
      background: var(--bg3);
      border-radius: 8px;
      height: 10px;
      overflow: hidden;
      margin-top: 6px;
    }

    .xp-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--gold), var(--accent4));
      transition: .5s;
    }

    .tag {
      display: inline-block;
      background: var(--bg3);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 2px 8px;
      font-size: .78rem;
      margin: 2px;
      color: var(--text2);
    }
  </style>
</head>

<body>

  <nav>
    <div class="logo">🌍<span>SpeakUP</span>English</div>
    <div class="nav-tabs" id="navTabs">
      <button class="nav-tab active" onclick="showPage('home')" data-key="nav_home">🏠 Home</button>
      <button class="nav-tab" onclick="showPage('vocab')" data-key="nav_vocab">📖 Vocabulary</button>
      <button class="nav-tab" onclick="showPage('listening')" data-key="nav_listening">🎧 Listening</button>
      <button class="nav-tab" onclick="showPage('speaking')" data-key="nav_speaking">🎤 Speaking</button>
      <button class="nav-tab" onclick="showPage('reading')" data-key="nav_reading">📝 Reading</button>
      <button class="nav-tab" onclick="showPage('writing')" data-key="nav_writing">✍️ Writing</button>
      <button class="nav-tab" onclick="showPage('ai')" data-key="nav_ai">🤖 AI Tutor</button>
      <button class="nav-tab" onclick="showPage('rank')" data-key="nav_rank">🏆 Leaderboard</button>
      <button class="nav-tab" onclick="showPage('stats')" data-key="nav_stats">📊 Stats</button>
    </div>
    <div class="lang-sel">
      <button class="lang-btn active" onclick="setLang('en')">EN</button>
      <button class="lang-btn" onclick="setLang('ru')">RU</button>
      <button class="lang-btn" onclick="setLang('uz')">UZ</button>
      <button class="lang-btn" onclick="setLang('tg')">TG</button>
    </div>
  </nav>

  <main>

    <!-- HOME -->
    <div class="page active" id="page-home">
      <div class="hero card">
        <h1 data-key="hero_title">SpeakUP English</h1>
        <p data-key="hero_sub">Master English through fun, games & AI</p>
        <div class="stats-grid" style="max-width:500px;margin:0 auto;">
          <div class="stat-card">
            <div class="stat-num" id="home-xp">0</div>
            <div class="stat-label" data-key="stat_xp">Total XP</div>
          </div>
          <div class="stat-card">
            <div class="stat-num" id="home-streak">0🔥</div>
            <div class="stat-label" data-key="stat_streak">Day Streak</div>
          </div>
          <div class="stat-card">
            <div class="stat-num" id="home-done">0%</div>
            <div class="stat-label" data-key="stat_done">Completed</div>
          </div>
        </div>
      </div>
      <h2 data-key="choose_level">Choose Your Level</h2>
      <div class="level-grid" id="levelGrid"></div>
    </div>

    <!-- LESSONS -->
    <div class="page" id="page-lessons">
      <div id="lessonMain">
        <button class="back-btn" onclick="showPage('home')">← <span data-key="back">Back</span></button>
        <h2 id="lessonLevelTitle">Topics</h2>
        <div class="topic-list" id="topicList"></div>
      </div>
      <div id="lessonView" class="hidden">
        <button class="back-btn" onclick="backToTopics()">← <span data-key="back_topics">Topics</span></button>
        <div class="card">
          <h2 id="lessonTitle"></h2>
          <div class="lesson-content" id="lessonContent"></div>
          <div style="margin-top:20px;">
            <button class="start-test-btn" onclick="startTest()" data-key="start_test">📝 Start Test (30
              Questions)</button>
          </div>
        </div>
      </div>
      <div id="testView" class="hidden">
        <button class="back-btn" onclick="backToLesson()">← <span data-key="back_lesson">Back to Lesson</span></button>
        <div class="card">
          <div id="testContent"></div>
        </div>
      </div>
    </div>

    <!-- VOCAB -->
    <div class="page" id="page-vocab">
      <h2 data-key="nav_vocab">📖 Vocabulary</h2>
      <div class="inner-tabs">
        <button class="inner-tab active" onclick="showInner('vocab','all')" data-key="vocab_all">All</button>
        <button class="inner-tab" onclick="showInner('vocab','nouns')" data-key="vocab_nouns">Nouns</button>
        <button class="inner-tab" onclick="showInner('vocab','verbs')" data-key="vocab_verbs">Verbs</button>
        <button class="inner-tab" onclick="showInner('vocab','adj')" data-key="vocab_adj">Adjectives</button>
        <button class="inner-tab" onclick="showInner('vocab','adv')" data-key="vocab_adv">Adverbs</button>
        <button class="inner-tab" onclick="showInner('vocab','phrases')" data-key="vocab_phrases">Phrases</button>
        <button class="inner-tab" onclick="showInner('vocab','idioms')" data-key="vocab_idioms">Idioms</button>
      </div>
      <input class="search-bar" id="vocabSearch" placeholder="🔍 Search..." oninput="filterVocab()">
      <div class="inner-page active" id="vocab-all">
        <div class="vocab-grid" id="vocabGrid"></div>
      </div>
      <div class="inner-page" id="vocab-nouns">
        <div class="vocab-grid" id="vocabNouns"></div>
      </div>
      <div class="inner-page" id="vocab-verbs">
        <div class="vocab-grid" id="vocabVerbs"></div>
      </div>
      <div class="inner-page" id="vocab-adj">
        <div class="vocab-grid" id="vocabAdj"></div>
      </div>
      <div class="inner-page" id="vocab-adv">
        <div class="vocab-grid" id="vocabAdv"></div>
      </div>
      <div class="inner-page" id="vocab-phrases">
        <div class="vocab-grid" id="vocabPhrases"></div>
      </div>
      <div class="inner-page" id="vocab-idioms">
        <div class="vocab-grid" id="vocabIdioms"></div>
      </div>
    </div>

    <!-- LISTENING -->
    <div class="page" id="page-listening">
      <h2 data-key="nav_listening">🎧 Listening Practice</h2>
      <div class="inner-tabs">
        <button class="inner-tab active" onclick="showInner('listen','beginner')" data-key="lev_beg">Beginner</button>
        <button class="inner-tab" onclick="showInner('listen','intermediate')" data-key="lev_int">Intermediate</button>
        <button class="inner-tab" onclick="showInner('listen','advanced')" data-key="lev_adv">Advanced</button>
      </div>
      <div id="listen-beginner" class="inner-page active"></div>
      <div id="listen-intermediate" class="inner-page"></div>
      <div id="listen-advanced" class="inner-page"></div>
    </div>

    <!-- SPEAKING -->
    <div class="page" id="page-speaking">
      <h2 data-key="nav_speaking">🎤 Speaking Practice</h2>
      <div class="card">
        <div id="speakScenario"></div>
        <div id="speakDialog"></div>
        <div class="text-center mt">
          <button class="mic-btn" id="micBtn" onclick="toggleMic()">🎙️</button>
          <p id="micStatus" style="color:var(--text2);font-size:.9rem;" data-key="speak_press">Press mic and speak your
            answer</p>
        </div>
        <div style="margin-top:12px;display:flex;gap:10px;justify-content:center;">
          <button class="btn" onclick="nextSpeakScenario()" data-key="next_scenario">Next Scenario</button>
          <button class="btn outline" onclick="repeatAI()" data-key="repeat_ai">🔊 Repeat AI</button>
        </div>
        <div id="speakFeedback" class="mt" style="display:none;"></div>
      </div>
    </div>

    <!-- READING -->
    <div class="page" id="page-reading">
      <h2 data-key="nav_reading">📝 Reading</h2>
      <div class="inner-tabs">
        <button class="inner-tab active" onclick="showInner('read','beginner')" data-key="lev_beg">Beginner</button>
        <button class="inner-tab" onclick="showInner('read','intermediate')" data-key="lev_int">Intermediate</button>
        <button class="inner-tab" onclick="showInner('read','advanced')" data-key="lev_adv">Advanced</button>
      </div>
      <div id="read-beginner" class="inner-page active"></div>
      <div id="read-intermediate" class="inner-page"></div>
      <div id="read-advanced" class="inner-page"></div>
    </div>

    <!-- WRITING -->
    <div class="page" id="page-writing">
      <h2 data-key="nav_writing">✍️ Writing Practice</h2>
      <div class="card">
        <div id="writingPrompt"></div>
        <textarea id="writingArea"
          style="width:100%;min-height:180px;background:var(--bg3);border:1px solid var(--border);color:var(--text);padding:14px;border-radius:10px;font-family:'Nunito',sans-serif;font-size:.95rem;resize:vertical;"
          placeholder="Write here..."></textarea>
        <div style="display:flex;gap:10px;margin-top:12px;">
          <button class="btn" onclick="checkWriting()" data-key="check_writing">🤖 Check with AI</button>
          <button class="btn outline" onclick="newWritingPrompt()" data-key="new_prompt">New Prompt</button>
        </div>
        <div id="writingFeedback" class="mt"></div>
      </div>
    </div>

    <!-- AI TUTOR -->
    <div class="page" id="page-ai">
      <h2 data-key="nav_ai">🤖 AI English Tutor</h2>
      <div class="card">
        <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;">
          <p style="color:var(--text2);font-size:.9rem;" data-key="ai_sub">Ask anything about English 24/7</p>
          <button class="btn outline" onclick="clearChat()" data-key="clear_chat">Clear</button>
        </div>
        <div class="chat-area" id="chatArea"></div>
        <div class="chat-input-row">
          <input class="chat-input" id="chatInput" placeholder="Ask AI..."
            onkeydown="if(event.key==='Enter')sendChat()">
          <button class="btn" onclick="sendChat()">➤</button>
        </div>
        <div class="mt" style="display:flex;gap:8px;flex-wrap:wrap;">
          <button class="tag" onclick="quickAsk('Explain present simple tense')">Present Simple</button>
          <button class="tag" onclick="quickAsk('What is the difference between since and for?')">since vs for</button>
          <button class="tag" onclick="quickAsk('Give me 5 common idioms with meanings')">Idioms</button>
          <button class="tag" onclick="quickAsk('How to use articles a, an, the?')">Articles</button>
          <button class="tag" onclick="quickAsk('Explain passive voice with examples')">Passive Voice</button>
          <button class="tag" onclick="quickAsk('What are modal verbs? Give examples')">Modal Verbs</button>
        </div>
      </div>
    </div>

    <!-- LEADERBOARD -->
    <div class="page" id="page-rank">
      <h2 data-key="nav_rank">🏆 Leaderboard</h2>
      <div class="card" id="leaderboardList"></div>
    </div>

    <!-- STATS -->
    <div class="page" id="page-stats">
      <h2 data-key="nav_stats">📊 My Statistics</h2>
      <div class="stats-grid" id="statsGrid"></div>
      <div class="card mt">
        <h3 data-key="progress_by_level">Progress by Level</h3>
        <div id="progressBars"></div>
      </div>
      <div class="card mt">
        <h3 data-key="topic_scores">Test Scores by Topic</h3>
        <div id="topicScores"></div>
      </div>
    </div>

  </main>

  <script>
    // ========================
    // TRANSLATIONS
    // ========================
    const LANGS = {
      en: {
        nav_home: "🏠 Home", nav_lessons: "📚 Lessons", nav_vocab: "📖 Vocabulary",
        nav_listening: "🎧 Listening", nav_speaking: "🎤 Speaking", nav_reading: "📝 Reading",
        nav_writing: "✍️ Writing", nav_ai: "🤖 AI Tutor", nav_rank: "🏆 Leaderboard", nav_stats: "📊 Stats",
        hero_title: "LinguaQuest", hero_sub: "Master English through fun, games & AI",
        stat_xp: "Total XP", stat_streak: "Day Streak", stat_done: "Completed",
        choose_level: "Choose Your Level", back: "Back", back_topics: "Topics", back_lesson: "Back to Lesson",
        start_test: "📝 Start Test (30 Questions)", vocab_all: "All", vocab_nouns: "Nouns",
        vocab_verbs: "Verbs", vocab_adj: "Adjectives", vocab_adv: "Adverbs", vocab_phrases: "Phrases",
        vocab_idioms: "Idioms", lev_beg: "Beginner", lev_int: "Intermediate", lev_adv: "Advanced",
        speak_press: "Press mic and speak your answer", next_scenario: "Next Scenario",
        repeat_ai: "🔊 Repeat AI", check_writing: "🤖 Check with AI", new_prompt: "New Prompt",
        ai_sub: "Ask anything about English 24/7", clear_chat: "Clear",
        progress_by_level: "Progress by Level", topic_scores: "Test Scores by Topic",
        q_label: "Question", of_label: "of", submit_answers: "Submit Answers",
        correct_label: "Correct", wrong_label: "Wrong", score_label: "Your Score",
        retry_btn: "Try Again", next_topic_btn: "Next Topic", great: "Excellent! 🌟",
        good: "Good job! 👍", ok: "Keep practicing! 💪", weak: "Study more! 📖",
        start_btn: "Start Learning", level_complete: "Level Complete!",
        your_ans: "Your answer", ai_ans: "AI answer",
      },
      ru: {
        nav_home: "🏠 Главная", nav_lessons: "📚 Уроки", nav_vocab: "📖 Словарь",
        nav_listening: "🎧 Аудирование", nav_speaking: "🎤 Говорение", nav_reading: "📝 Чтение",
        nav_writing: "✍️ Письмо", nav_ai: "🤖 ИИ Репетитор", nav_rank: "🏆 Рейтинг", nav_stats: "📊 Статистика",
        hero_title: "LinguaQuest", hero_sub: "Учи английский через игры и ИИ",
        stat_xp: "Всего XP", stat_streak: "Дней подряд", stat_done: "Завершено",
        choose_level: "Выбери уровень", back: "Назад", back_topics: "К темам", back_lesson: "К уроку",
        start_test: "📝 Начать тест (30 вопросов)", vocab_all: "Все", vocab_nouns: "Существительные",
        vocab_verbs: "Глаголы", vocab_adj: "Прилагательные", vocab_adv: "Наречия",
        vocab_phrases: "Фразы", vocab_idioms: "Идиомы", lev_beg: "Начальный",
        lev_int: "Средний", lev_adv: "Продвинутый",
        speak_press: "Нажми микрофон и говори", next_scenario: "Следующий сценарий",
        repeat_ai: "🔊 Повторить ИИ", check_writing: "🤖 Проверить ИИ", new_prompt: "Новое задание",
        ai_sub: "Спрашивай что угодно об английском 24/7", clear_chat: "Очистить",
        progress_by_level: "Прогресс по уровням", topic_scores: "Результаты тестов по темам",
        q_label: "Вопрос", of_label: "из", submit_answers: "Ответить",
        correct_label: "Правильно", wrong_label: "Неправильно", score_label: "Твой результат",
        retry_btn: "Попробовать снова", next_topic_btn: "Следующая тема",
        great: "Отлично! 🌟", good: "Хорошо! 👍", ok: "Продолжай практиковаться! 💪",
        weak: "Учи больше! 📖", start_btn: "Начать учиться", level_complete: "Уровень завершён!",
        your_ans: "Твой ответ", ai_ans: "Ответ ИИ",
      },
      uz: {
        nav_home: "🏠 Bosh sahifa", nav_lessons: "📚 Darslar", nav_vocab: "📖 Lug'at",
        nav_listening: "🎧 Tinglash", nav_speaking: "🎤 Gapirish", nav_reading: "📝 O'qish",
        nav_writing: "✍️ Yozish", nav_ai: "🤖 AI O'qituvchi", nav_rank: "🏆 Reyting", nav_stats: "📊 Statistika",
        hero_title: "LinguaQuest", hero_sub: "O'yinlar va AI orqali inglizcha o'rgan",
        stat_xp: "Jami XP", stat_streak: "Kunlik streak", stat_done: "Bajarildi",
        choose_level: "Darajangni tanlang", back: "Orqaga", back_topics: "Mavzularga", back_lesson: "Darsga qaytish",
        start_test: "📝 Testni boshlash (30 savol)", vocab_all: "Hammasi", vocab_nouns: "Otlar",
        vocab_verbs: "Fe'llar", vocab_adj: "Sifatlar", vocab_adv: "Ravishlar",
        vocab_phrases: "Iboralar", vocab_idioms: "Idiomalar", lev_beg: "Boshlang'ich",
        lev_int: "O'rta", lev_adv: "Yuqori",
        speak_press: "Mikrofon bosib gapiring", next_scenario: "Keyingi stsenariy",
        repeat_ai: "🔊 AI ni takrorlash", check_writing: "🤖 AI bilan tekshirish", new_prompt: "Yangi topshiriq",
        ai_sub: "Ingliz tili haqida istalgan narsani so'rang 24/7", clear_chat: "Tozalash",
        progress_by_level: "Daraja bo'yicha progress", topic_scores: "Mavzu bo'yicha test natijalari",
        q_label: "Savol", of_label: "dan", submit_answers: "Javob berish",
        correct_label: "To'g'ri", wrong_label: "Noto'g'ri", score_label: "Natijangiz",
        retry_btn: "Qayta urinish", next_topic_btn: "Keyingi mavzu",
        great: "A'lo! 🌟", good: "Yaxshi! 👍", ok: "Mashq qiling! 💪",
        weak: "Ko'proq o'qing! 📖", start_btn: "O'rganishni boshlash", level_complete: "Daraja tugadi!",
        your_ans: "Sizning javobingiz", ai_ans: "AI javobi",
      },
      tg: {
        nav_home: "🏠 Хона", nav_lessons: "📚 Дарсҳо", nav_vocab: "📖 Луғат",
        nav_listening: "🎧 Шунидан", nav_speaking: "🎤 Сухан", nav_reading: "📝 Хондан",
        nav_writing: "✍️ Навиштан", nav_ai: "🤖 Омӯзгори ИИ", nav_rank: "🏆 Рейтинг", nav_stats: "📊 Омор",
        hero_title: "LinguaQuest", hero_sub: "Забони англисиро тавассути бозиҳо ва ИИ омӯзед",
        stat_xp: "Ҳамаи XP", stat_streak: "Рӯзи паи ҳам", stat_done: "Иҷро шуд",
        choose_level: "Сатҳи худро интихоб кунед", back: "Бозгашт", back_topics: "Мавзуҳо", back_lesson: "Ба дарс бозгашт",
        start_test: "📝 Санҷишро оғоз кунед (30 савол)", vocab_all: "Ҳама", vocab_nouns: "Исмҳо",
        vocab_verbs: "Феълҳо", vocab_adj: "Сифатҳо", vocab_adv: "Ҳолҳо",
        vocab_phrases: "Ибораҳо", vocab_idioms: "Идиомаҳо", lev_beg: "Ибтидоӣ",
        lev_int: "Миёна", lev_adv: "Пешрафта",
        speak_press: "Микрофонро пахш кунед ва ҷавоб диҳед", next_scenario: "Сенарияи навбатӣ",
        repeat_ai: "🔊 Такрори ИИ", check_writing: "🤖 Бо ИИ санҷидан", new_prompt: "Вазифаи нав",
        ai_sub: "Ҳама чизро дар бораи забони англисӣ 24/7 бипурсед", clear_chat: "Тоза кардан",
        progress_by_level: "Пешрафт аз рӯи сатҳ", topic_scores: "Натиҷаи санҷиш аз рӯи мавзӯ",
        q_label: "Савол", of_label: "аз", submit_answers: "Ҷавоб додан",
        correct_label: "Дуруст", wrong_label: "Нодуруст", score_label: "Натиҷаи шумо",
        retry_btn: "Дубора кӯшиш", next_topic_btn: "Мавзӯи навбатӣ",
        great: "Аъло! 🌟", good: "Хуб! 👍", ok: "Машқ кунед! 💪",
        weak: "Бештар омӯзед! 📖", start_btn: "Омӯзишро оғоз кунед", level_complete: "Сатҳ тамом шуд!",
        your_ans: "Ҷавоби шумо", ai_ans: "Ҷавоби ИИ",
      }
    };
    let currentLang = 'en';
    function t(key) { return (LANGS[currentLang] || LANGS.en)[key] || LANGS.en[key] || key; }
    function setLang(l) {
      currentLang = l;
      document.querySelectorAll('.lang-btn').forEach(b => b.classList.toggle('active', b.textContent === l.toUpperCase()));
      document.querySelectorAll('[data-key]').forEach(el => {
        const k = el.getAttribute('data-key');
        if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') el.placeholder = t(k);
        else el.textContent = t(k);
      });
      renderLevelGrid();
      renderVocab();
      renderListening();
      renderReading();
      renderSpeakScenario();
      renderLeaderboard();
      renderStats();
    }

    // ========================
    // STATE
    // ========================
    let state = {
      xp: 0, streak: 7, completedTopics: {},
      testScores: {}, currentLevel: null, currentTopic: null,
      currentTest: null, usedQuestions: {}
    };

    // ========================
    // LEVELS + TOPICS + LESSONS
    // ========================
    const LEVELS = [
      { id: 'a1', name: 'A1 – Beginner', icon: '🌱', color: '#43e97b', topics: ['greetings', 'numbers', 'colors', 'family', 'food', 'body', 'weather', 'days', 'clothes', 'animals'] },
      { id: 'a2', name: 'A2 – Elementary', icon: '🌿', color: '#00b09b', topics: ['present_simple', 'past_simple', 'future', 'shopping', 'travel', 'hobbies', 'home', 'school', 'health', 'sports'] },
      { id: 'b1', name: 'B1 – Intermediate', icon: '🌳', color: '#6c63ff', topics: ['present_perfect', 'conditionals', 'modal_verbs', 'passive_voice', 'environment', 'work', 'technology', 'culture', 'relationships', 'science'] },
      { id: 'b2', name: 'B2 – Upper Int.', icon: '🦅', color: '#f7971e', topics: ['reported_speech', 'relative_clauses', 'mixed_conditionals', 'business', 'politics', 'media', 'psychology', 'economics', 'law', 'history'] },
      { id: 'c1', name: 'C1 – Advanced', icon: '🚀', color: '#ff6584', topics: ['subjunctive', 'inversion', 'ellipsis', 'literature', 'philosophy', 'medicine', 'engineering', 'artificial_intelligence', 'diplomacy', 'art'] },
      { id: 'c2', name: 'C2 – Mastery', icon: '👑', color: '#ffd700', topics: ['nuance', 'rhetoric', 'academic', 'idioms_adv', 'collocations', 'register', 'discourse', 'argumentation', 'criticism', 'synthesis'] },
    ];

    const TOPIC_DATA = {
      greetings: {
        icon: '👋', name: 'Greetings & Introductions',
        lesson: `<h4>Basic Greetings</h4>
<p>Greetings are the first step in any conversation. In English, there are formal and informal ways to greet people.</p>
<table><tr><th>Expression</th><th>Usage</th><th>Response</th></tr>
<tr><td>Hello / Hi</td><td>Informal, everyday</td><td>Hello! / Hi!</td></tr>
<tr><td>Good morning</td><td>Before noon</td><td>Good morning!</td></tr>
<tr><td>Good afternoon</td><td>Noon – 6pm</td><td>Good afternoon!</td></tr>
<tr><td>Good evening</td><td>After 6pm</td><td>Good evening!</td></tr>
<tr><td>How are you?</td><td>Formal inquiry</td><td>I'm fine, thank you!</td></tr>
<tr><td>What's up?</td><td>Very informal</td><td>Not much! / All good!</td></tr></table>
<h4>Introducing Yourself</h4>
<p>When you meet someone new, you introduce yourself. Common phrases include:</p>
<div class="example">My name is Sarah. I'm from London. Nice to meet you!</div>
<div class="example">I'd like to introduce myself. I'm John, the new manager.</div>
<h4>Asking for Someone's Name</h4>
<p>There are several ways to ask someone's name:</p>
<div class="example">What's your name? (informal)</div>
<div class="example">Could I ask your name? (formal)</div>
<div class="example">May I know your name? (very formal)</div>
<h4>Saying Goodbye</h4>
<table><tr><th>Expression</th><th>Context</th></tr>
<tr><td>Goodbye / Bye</td><td>General</td></tr>
<tr><td>See you later / See you soon</td><td>When you'll meet again</td></tr>
<tr><td>Take care</td><td>Warm farewell</td></tr>
<tr><td>Good night</td><td>Evening parting</td></tr>
<tr><td>Farewell</td><td>Long parting, formal</td></tr></table>
<h4>Polite Expressions</h4>
<p>Always use these in English to be polite:</p>
<div class="example">Please, Thank you, You're welcome, Excuse me, I'm sorry, Pardon me</div>
<h4>Asking About Origin</h4>
<div class="example">Where are you from? — I'm from Russia/Uzbekistan/England.</div>
<div class="example">Where do you come from? — I come from a small city in the north.</div>
<h4>Talking About Your Job</h4>
<div class="example">What do you do (for a living)? — I'm a teacher / I work as an engineer.</div>
<h4>Talking About Age</h4>
<div class="example">How old are you? — I'm twenty-five years old.</div>`,
        questions: [
          { q: "What is the correct response to 'How are you?'", opts: ["I'm fine, thank you!", "Yes, I am.", "My name is Tom.", "Good night!"], a: 0 },
          { q: "Which greeting is used before noon?", opts: ["Good evening", "Good night", "Good morning", "Good afternoon"], a: 2 },
          { q: "'What's your name?' is ___", opts: ["very formal", "informal", "impolite", "wrong"], a: 1 },
          { q: "Choose the correct introduction:", opts: ["My name is is Tom", "I am name Tom", "My name is Tom", "Name my Tom is"], a: 2 },
          { q: "'See you later' means:", opts: ["Goodbye forever", "We'll meet again soon", "Good morning", "Nice to meet you"], a: 1 },
          { q: "Which is the most formal goodbye?", opts: ["Bye!", "See ya!", "Farewell", "Later!"], a: 2 },
          { q: "'Where are you from?' asks about your:", opts: ["age", "job", "origin", "name"], a: 2 },
          { q: "Complete: 'Nice ___ meet you!'", opts: ["to", "for", "at", "in"], a: 0 },
          { q: "'Good evening' is used:", opts: ["before noon", "in the morning", "after 6pm", "at midnight only"], a: 2 },
          { q: "Which phrase asks about someone's job?", opts: ["How old are you?", "What do you do?", "Where are you from?", "What's your name?"], a: 1 },
          { q: "Choose the polite response after 'Thank you':", opts: ["Yes", "No problem / You're welcome", "Goodbye", "Sorry"], a: 1 },
          { q: "'Excuse me' is used to:", opts: ["say hello", "get attention politely", "say goodbye", "introduce yourself"], a: 1 },
          { q: "I ___ twenty years old.", opts: ["has", "am", "is", "are"], a: 1 },
          { q: "Which is NOT a greeting?", opts: ["Hello", "Hi there", "Good morning", "Farewell"], a: 3 },
          { q: "'Could I ask your name?' is:", opts: ["informal", "rude", "very formal", "wrong"], a: 2 },
          { q: "'Take care' is said when:", opts: ["you arrive", "you say goodbye", "you eat", "you work"], a: 1 },
          { q: "What does 'What's up?' mean?", opts: ["Where are you going?", "How are you? (informal)", "What is that?", "Who are you?"], a: 1 },
          { q: "'I'd like to introduce ___ . I'm Maria.'", opts: ["yourself", "myself", "himself", "themselves"], a: 1 },
          { q: "Which greeting works all day?", opts: ["Good morning", "Good evening", "Hello", "Good afternoon"], a: 2 },
          { q: "'I come from Spain.' — What was the question?", opts: ["How old are you?", "What's your job?", "Where are you from?", "Are you happy?"], a: 2 },
          { q: "Correct sentence: '___'", opts: ["He name is Paul", "His name Paul is", "His name is Paul", "Paul his name is"], a: 2 },
          { q: "'Pardon me' means:", opts: ["I hate you", "I'm sorry / Excuse me", "You're welcome", "See you later"], a: 1 },
          { q: "'Nice to meet you' is said when:", opts: ["you say goodbye", "you meet someone new", "you eat", "you sleep"], a: 1 },
          { q: "Choose the correct question about age:", opts: ["How old have you?", "How old is you?", "How old are you?", "How much old are you?"], a: 2 },
          { q: "'Good night' is a farewell used:", opts: ["in the morning", "at noon", "in the evening/night", "anytime"], a: 2 },
          { q: "'I'm a doctor' answers the question:", opts: ["How old are you?", "Where are you from?", "What do you do?", "What's your name?"], a: 2 },
          { q: "Which is informal?", opts: ["Good morning, sir.", "Could I ask your name?", "Hey! What's up?", "I'd like to introduce myself."], a: 2 },
          { q: "'___ are you?' — 'I'm from Japan.'", opts: ["How", "What", "Where", "Who"], a: 2 },
          { q: "Complete: 'Good ___, see you tomorrow!'", opts: ["morning", "night", "afternoon", "evening"], a: 1 },
          { q: "'I'm pleased to meet you' is:", opts: ["informal", "formal", "slang", "wrong"], a: 1 },
        ]
      },
      numbers: {
        icon: '🔢', name: 'Numbers & Counting',
        lesson: `<h4>Cardinal Numbers (1–100)</h4>
<table><tr><th>Number</th><th>Word</th><th>Number</th><th>Word</th></tr>
<tr><td>1</td><td>one</td><td>11</td><td>eleven</td></tr>
<tr><td>2</td><td>two</td><td>12</td><td>twelve</td></tr>
<tr><td>3</td><td>three</td><td>13</td><td>thirteen</td></tr>
<tr><td>4</td><td>four</td><td>14</td><td>fourteen</td></tr>
<tr><td>5</td><td>five</td><td>15</td><td>fifteen</td></tr>
<tr><td>10</td><td>ten</td><td>20</td><td>twenty</td></tr>
<tr><td>30</td><td>thirty</td><td>100</td><td>one hundred</td></tr></table>
<h4>Ordinal Numbers</h4>
<div class="example">1st – first, 2nd – second, 3rd – third, 4th – fourth ... 20th – twentieth</div>
<h4>Large Numbers</h4>
<div class="example">1,000 – one thousand | 1,000,000 – one million | 1,000,000,000 – one billion</div>
<h4>Fractions & Decimals</h4>
<div class="example">½ – one half | ¼ – one quarter | ⅓ – one third | 3.5 – three point five</div>
<h4>Arithmetic Operations</h4>
<table><tr><th>Symbol</th><th>Word</th><th>Example</th></tr>
<tr><td>+</td><td>plus / and</td><td>5 + 3 = eight</td></tr>
<tr><td>-</td><td>minus</td><td>10 - 4 = six</td></tr>
<tr><td>×</td><td>times / multiplied by</td><td>3 × 4 = twelve</td></tr>
<tr><td>÷</td><td>divided by</td><td>20 ÷ 5 = four</td></tr>
<tr><td>=</td><td>equals</td><td>result</td></tr></table>`,
        questions: [
          { q: "How do you say 15 in English?", opts: ["fifty", "fiveteen", "fifteen", "fiftee"], a: 2 },
          { q: "What is 'twenty' in numbers?", opts: ["12", "20", "200", "22"], a: 1 },
          { q: "How do you say 1,000?", opts: ["one hundred", "one million", "one thousand", "ten hundred"], a: 2 },
          { q: "What is the ordinal form of '3'?", opts: ["threeth", "thrid", "third", "three"], a: 2 },
          { q: "3 × 4 = ___", opts: ["seven", "twelve", "ten", "eight"], a: 1 },
          { q: "'Half' means:", opts: ["1/3", "1/4", "1/2", "1/5"], a: 2 },
          { q: "How do you say 0.5?", opts: ["zero five", "zero point five", "five percent", "half zero"], a: 1 },
          { q: "The ordinal of 1 is:", opts: ["oneth", "first", "oned", "firsty"], a: 1 },
          { q: "50 + 50 = ___", opts: ["one hundred", "ninety", "eighty", "two hundred"], a: 0 },
          { q: "'Thirteen' is ___", opts: ["30", "3", "13", "33"], a: 2 },
          { q: "How do you say 2nd?", opts: ["twoth", "secondly", "second", "twoeth"], a: 2 },
          { q: "What is one million in numbers?", opts: ["1,000", "10,000", "100,000", "1,000,000"], a: 3 },
          { q: "20 ÷ 4 = ___", opts: ["four", "five", "six", "three"], a: 1 },
          { q: "'Quarter' means:", opts: ["1/2", "1/3", "1/4", "1/5"], a: 2 },
          { q: "How do you say 100?", opts: ["ten ten", "hundred", "one hundred", "a hundreds"], a: 2 },
          { q: "Which number is 'forty-two'?", opts: ["24", "402", "42", "422"], a: 2 },
          { q: "The ordinal of 20 is:", opts: ["twentith", "twentyth", "twentieth", "twentied"], a: 2 },
          { q: "100 - 37 = ___", opts: ["sixty-three", "sixty-four", "seventy-three", "sixty-seven"], a: 0 },
          { q: "'Billion' means:", opts: ["1,000,000", "10,000,000", "100,000,000", "1,000,000,000"], a: 3 },
          { q: "'3.7' in words is:", opts: ["three comma seven", "three dot seven", "three point seven", "three and seven"], a: 2 },
          { q: "How do you say 15th?", opts: ["fifteenth", "fifteen", "fiveteenth", "fifteenst"], a: 0 },
          { q: "Which is correct: 21st or 21th?", opts: ["21th", "21st", "21nd", "21rd"], a: 1 },
          { q: "'Minus' is the operation of:", opts: ["adding", "subtracting", "multiplying", "dividing"], a: 1 },
          { q: "How do you say 1/3?", opts: ["one third", "one three", "first three", "one thirds"], a: 0 },
          { q: "999 in words is:", opts: ["nine nine nine", "nine hundred ninety-nine", "nine hundred and nine", "ninety-nine nine"], a: 1 },
          { q: "What does 'even number' mean?", opts: ["divisible by 2", "divisible by 3", "any big number", "number with zero"], a: 0 },
          { q: "'Eleven' is ___", opts: ["10", "11", "12", "21"], a: 1 },
          { q: "Five times six equals:", opts: ["twenty-five", "thirty", "thirty-five", "twenty"], a: 1 },
          { q: "The ordinal of 12 is:", opts: ["twelfth", "twelveeth", "twelfty", "twelfieth"], a: 0 },
          { q: "'Fifty percent' means:", opts: ["1/4", "3/4", "1/2", "1/3"], a: 2 },
        ]
      },
      present_simple: {
        icon: '⏰', name: 'Present Simple Tense',
        lesson: `<h4>What is Present Simple?</h4>
<p>The Present Simple tense is used to describe habits, routines, facts, and general truths. It is one of the most important tenses in English.</p>
<h4>Structure</h4>
<table><tr><th>Form</th><th>Structure</th><th>Example</th></tr>
<tr><td>Positive</td><td>Subject + V1 (add -s/-es for he/she/it)</td><td>She works every day.</td></tr>
<tr><td>Negative</td><td>Subject + don't/doesn't + V1</td><td>He doesn't like coffee.</td></tr>
<tr><td>Question</td><td>Do/Does + Subject + V1?</td><td>Do you play tennis?</td></tr></table>
<h4>When to Use It</h4>
<div class="example">Habits: I wake up at 7am every day.</div>
<div class="example">Facts: Water boils at 100°C.</div>
<div class="example">Schedules: The train leaves at 9am.</div>
<div class="example">Feelings: She loves music.</div>
<h4>Third Person Singular Rules (-s / -es)</h4>
<table><tr><th>Verb ending</th><th>Rule</th><th>Example</th></tr>
<tr><td>Most verbs</td><td>Add -s</td><td>work → works</td></tr>
<tr><td>-ch, -sh, -ss, -x, -o</td><td>Add -es</td><td>watch → watches</td></tr>
<tr><td>consonant + y</td><td>y → ies</td><td>study → studies</td></tr>
<tr><td>Irregular</td><td>Special forms</td><td>have → has, be → is</td></tr></table>
<h4>Time Expressions</h4>
<div class="example">always, usually, often, sometimes, rarely, never, every day/week/year, on Mondays</div>
<h4>Common Mistakes</h4>
<div class="example">✗ She work every day. ✓ She works every day.</div>
<div class="example">✗ He don't like it. ✓ He doesn't like it.</div>
<div class="example">✗ Does she works? ✓ Does she work?</div>`,
        questions: [
          { q: "He ___ football every weekend.", opts: ["play", "playing", "plays", "to play"], a: 2 },
          { q: "She ___ not like vegetables.", opts: ["do", "is", "does", "have"], a: 2 },
          { q: "___ they speak English?", opts: ["Does", "Is", "Do", "Are"], a: 2 },
          { q: "Water ___ at 100°C.", opts: ["boil", "boils", "is boiling", "boiled"], a: 1 },
          { q: "I ___ to school every day.", opts: ["goes", "go", "going", "went"], a: 1 },
          { q: "'Study' in 3rd person singular is:", opts: ["studys", "studyes", "studies", "studis"], a: 2 },
          { q: "She doesn't ___ coffee.", opts: ["drinks", "drinking", "drank", "drink"], a: 3 },
          { q: "The train ___ at 8am.", opts: ["leave", "leaves", "left", "is leaving"], a: 1 },
          { q: "Time expression for Present Simple:", opts: ["yesterday", "right now", "every Monday", "last week"], a: 2 },
          { q: "___ he work in a bank?", opts: ["Do", "Is", "Are", "Does"], a: 3 },
          { q: "My sister ___ three languages.", opts: ["speak", "speaks", "is speaking", "spoke"], a: 1 },
          { q: "They ___ usually late.", opts: ["isn't", "doesn't", "aren't", "wasn't"], a: 2 },
          { q: "'Watch' in 3rd person is:", opts: ["watchs", "watchies", "watches", "watchies"], a: 2 },
          { q: "I ___ breakfast every morning.", opts: ["have", "has", "haves", "having"], a: 0 },
          { q: "The sun ___ in the east.", opts: ["rise", "rises", "is rising", "has risen"], a: 1 },
          { q: "She ___ to music on her way to work.", opts: ["listen", "listens", "is listening", "listened"], a: 1 },
          { q: "He never ___ vegetables.", opts: ["eat", "eats", "is eating", "eating"], a: 1 },
          { q: "'Have' in 3rd person singular is:", opts: ["haves", "have", "has", "is having"], a: 2 },
          { q: "___ you like chocolate?", opts: ["Does", "Do", "Are", "Is"], a: 1 },
          { q: "We ___ English at school.", opts: ["studies", "study", "is studying", "am studying"], a: 1 },
          { q: "She always ___ the dishes after dinner.", opts: ["wash", "washes", "washing", "washed"], a: 1 },
          { q: "Correct negative: 'He ___ swim.'", opts: ["don't", "doesn't", "isn't", "aren't"], a: 1 },
          { q: "'Go' in 3rd person singular is:", opts: ["gos", "goies", "goes", "go"], a: 2 },
          { q: "Which sentence is correct?", opts: ["She work hard", "She works hard", "She working hard", "She worked hard"], a: 1 },
          { q: "I ___ TV every evening.", opts: ["watches", "watch", "am watching", "watched"], a: 1 },
          { q: "'Usually' is a time expression for:", opts: ["past simple", "future simple", "present simple", "present continuous"], a: 2 },
          { q: "Does she ___ in London?", opts: ["lives", "lived", "live", "living"], a: 2 },
          { q: "He ___ at 7 every morning.", opts: ["wake up", "wakes up", "is waking up", "woke up"], a: 1 },
          { q: "They ___ always on time.", opts: ["is", "am", "are", "be"], a: 2 },
          { q: "'Fly' in 3rd person is:", opts: ["flys", "flyies", "flies", "fly"], a: 2 },
        ]
      },
      colors: {
        icon: '🎨', name: 'Colors & Descriptions',
        lesson: `<h4>Basic Colors</h4>
<table><tr><th>Color</th><th>Example</th></tr>
<tr><td>Red</td><td>The apple is red.</td></tr>
<tr><td>Blue</td><td>The sky is blue.</td></tr>
<tr><td>Green</td><td>The grass is green.</td></tr>
<tr><td>Yellow</td><td>The sun is yellow.</td></tr>
<tr><td>Orange</td><td>The orange is orange.</td></tr>
<tr><td>Purple/Violet</td><td>The flower is purple.</td></tr>
<tr><td>Pink</td><td>Her dress is pink.</td></tr>
<tr><td>Brown</td><td>Chocolate is brown.</td></tr>
<tr><td>Black</td><td>The night is black.</td></tr>
<tr><td>White</td><td>Snow is white.</td></tr>
<tr><td>Grey/Gray</td><td>The clouds are grey.</td></tr></table>
<h4>Shades and Modifiers</h4>
<div class="example">Light blue, dark green, bright red, pale yellow, deep purple, navy blue, olive green</div>
<h4>Describing Objects</h4>
<div class="example">Order of adjectives: Opinion → Size → Age → Shape → Color → Origin → Material → Purpose + Noun</div>
<div class="example">Example: "A beautiful small old round red Italian silver coffee table"</div>
<h4>Common Phrases</h4>
<div class="example">What color is it? — It's blue.</div>
<div class="example">What color are they? — They're yellow.</div>`,
        questions: [
          { q: "What color is the sky on a clear day?", opts: ["green", "red", "blue", "yellow"], a: 2 },
          { q: "'Navy' is a shade of:", opts: ["red", "green", "blue", "brown"], a: 2 },
          { q: "Snow is ___ .", opts: ["black", "white", "grey", "yellow"], a: 1 },
          { q: "An apple is usually ___ .", opts: ["blue", "red", "purple", "orange"], a: 1 },
          { q: "'Light' in 'light blue' means:", opts: ["heavy", "dark", "pale", "bright"], a: 2 },
          { q: "What color is chocolate?", opts: ["pink", "white", "brown", "orange"], a: 2 },
          { q: "Grass is ___ .", opts: ["green", "yellow", "red", "purple"], a: 0 },
          { q: "'What color ___ it?' — 'It's pink.'", opts: ["are", "is", "am", "be"], a: 1 },
          { q: "'Crimson' is a shade of:", opts: ["blue", "green", "red", "yellow"], a: 2 },
          { q: "The correct order: ___ big red car", opts: ["big red a", "a red big", "a big red", "red a big"], a: 2 },
          { q: "'Olive' is a shade of:", opts: ["green", "purple", "orange", "pink"], a: 0 },
          { q: "What color is the sun?", opts: ["white", "blue", "yellow", "green"], a: 2 },
          { q: "'Dark' is the opposite of:", opts: ["big", "light", "heavy", "small"], a: 1 },
          { q: "Bananas are ___ .", opts: ["purple", "orange", "yellow", "grey"], a: 2 },
          { q: "'Turquoise' is between:", opts: ["red and yellow", "blue and green", "pink and purple", "black and white"], a: 1 },
          { q: "What color is coal?", opts: ["white", "grey", "black", "brown"], a: 2 },
          { q: "'Scarlet' is a type of:", opts: ["red", "blue", "green", "purple"], a: 0 },
          { q: "'What color are they?' — Correct response:", opts: ["It is blue", "They're yellow", "She is green", "He blue"], a: 1 },
          { q: "'Beige' is a pale shade of:", opts: ["blue", "red", "brown/yellow", "green"], a: 2 },
          { q: "Which is NOT a color?", opts: ["violet", "magenta", "angular", "cyan"], a: 2 },
          { q: "The fire engine is ___ .", opts: ["blue", "red", "white", "green"], a: 1 },
          { q: "'Golden' means:", opts: ["dark yellow", "bright yellow/gold", "pale white", "silver"], a: 1 },
          { q: "The color of grass is a shade of:", opts: ["blue", "yellow", "green", "brown"], a: 2 },
          { q: "'Lavender' is a shade of:", opts: ["pink", "purple", "blue", "grey"], a: 1 },
          { q: "Which two colors make orange?", opts: ["red+blue", "yellow+blue", "red+yellow", "green+red"], a: 2 },
          { q: "Which is a neutral color?", opts: ["red", "yellow", "grey", "green"], a: 2 },
          { q: "The ocean can be ___ or ___ .", opts: ["red or yellow", "blue or green", "pink or purple", "brown or white"], a: 1 },
          { q: "'Ivory' is close to:", opts: ["black", "blue", "white/cream", "red"], a: 2 },
          { q: "'Teal' is a mix of:", opts: ["red and yellow", "blue and green", "pink and purple", "orange and red"], a: 1 },
          { q: "Correct sentence:", opts: ["She wear a red dress", "She wears red a dress", "She wears a red dress", "She wearing red dress"], a: 2 },
        ]
      },
      past_simple: {
        icon: '⏪', name: 'Past Simple Tense',
        lesson: `<h4>What is Past Simple?</h4>
<p>Used for completed actions in the past, often with a specific time reference.</p>
<h4>Regular Verbs</h4>
<table><tr><th>Base</th><th>Past Simple</th><th>Rule</th></tr>
<tr><td>walk</td><td>walked</td><td>add -ed</td></tr>
<tr><td>like</td><td>liked</td><td>verb ends in -e: add -d</td></tr>
<tr><td>study</td><td>studied</td><td>consonant+y → ied</td></tr>
<tr><td>stop</td><td>stopped</td><td>double final consonant</td></tr></table>
<h4>Irregular Verbs</h4>
<table><tr><th>Base</th><th>Past</th><th>Base</th><th>Past</th></tr>
<tr><td>go</td><td>went</td><td>eat</td><td>ate</td></tr>
<tr><td>see</td><td>saw</td><td>come</td><td>came</td></tr>
<tr><td>have</td><td>had</td><td>take</td><td>took</td></tr>
<tr><td>write</td><td>wrote</td><td>speak</td><td>spoke</td></tr>
<tr><td>buy</td><td>bought</td><td>think</td><td>thought</td></tr></table>
<h4>Negative & Questions</h4>
<div class="example">I didn't go. / She didn't eat.</div>
<div class="example">Did you see the film? / Where did he go?</div>
<h4>Time Expressions</h4>
<div class="example">yesterday, last week/month/year, ago, in 2010, when I was young</div>`,
        questions: [
          { q: "The past form of 'go' is:", opts: ["goed", "went", "gone", "goes"], a: 1 },
          { q: "She ___ TV last night.", opts: ["watch", "watches", "watched", "is watching"], a: 2 },
          { q: "Past of 'eat' is:", opts: ["eated", "aten", "ate", "eat"], a: 2 },
          { q: "He ___ not come to the party.", opts: ["do", "did", "does", "was"], a: 1 },
          { q: "___ you see the film yesterday?", opts: ["Do", "Does", "Did", "Was"], a: 2 },
          { q: "Past form of 'write':", opts: ["writed", "wrote", "written", "writes"], a: 1 },
          { q: "They ___ to the beach last summer.", opts: ["go", "goes", "went", "going"], a: 2 },
          { q: "'Study' in past simple:", opts: ["studyed", "studied", "studed", "studis"], a: 1 },
          { q: "Past of 'buy':", opts: ["buyed", "boughted", "bought", "buys"], a: 2 },
          { q: "I ___ my homework an hour ago.", opts: ["finish", "finishes", "finished", "was finishing"], a: 2 },
          { q: "'Stop' in past simple:", opts: ["stoped", "stopied", "stopped", "stops"], a: 2 },
          { q: "Past of 'speak':", opts: ["speaked", "spoken", "speaks", "spoke"], a: 3 },
          { q: "She ___ a letter yesterday.", opts: ["write", "wrote", "written", "writes"], a: 1 },
          { q: "___ he call you last night?", opts: ["Do", "Does", "Did", "Was"], a: 2 },
          { q: "Past of 'have':", opts: ["haved", "had", "has", "have"], a: 1 },
          { q: "I didn't ___ breakfast this morning.", opts: ["had", "eat", "ate", "having"], a: 1 },
          { q: "They ___ the game 3-1.", opts: ["wins", "win", "won", "winning"], a: 2 },
          { q: "Time expression for past simple:", opts: ["every day", "right now", "yesterday", "usually"], a: 2 },
          { q: "Past of 'come':", opts: ["comed", "came", "come", "comes"], a: 1 },
          { q: "She ___ born in 1995.", opts: ["is", "were", "was", "be"], a: 2 },
          { q: "Past of 'take':", opts: ["taked", "taken", "took", "takes"], a: 2 },
          { q: "Did they ___ home early?", opts: ["goes", "went", "go", "gone"], a: 2 },
          { q: "He ___ the newspaper this morning.", opts: ["reads", "read", "readed", "reading"], a: 1 },
          { q: "Past of 'see':", opts: ["seed", "seen", "saw", "sees"], a: 2 },
          { q: "We ___ a great time at the party.", opts: ["have", "has", "had", "having"], a: 2 },
          { q: "Past of 'think':", opts: ["thinked", "thought", "think", "thinks"], a: 1 },
          { q: "She didn't ___ the answer.", opts: ["knows", "knew", "know", "knowing"], a: 2 },
          { q: "'Like' in past simple:", opts: ["liking", "likes", "liked", "liken"], a: 2 },
          { q: "Past of 'run':", opts: ["runned", "ran", "run", "runs"], a: 1 },
          { q: "Correct past sentence:", opts: ["He goed home", "He goes home", "He went home", "He going home"], a: 2 },
        ]
      },
      family: {
        icon: '👨‍👩‍👧‍👦', name: 'Family & Relationships',
        lesson: `<h4>Family Members</h4>
<table><tr><th>English</th><th>Relationship</th></tr>
<tr><td>father / dad</td><td>male parent</td></tr>
<tr><td>mother / mum/mom</td><td>female parent</td></tr>
<tr><td>brother</td><td>male sibling</td></tr>
<tr><td>sister</td><td>female sibling</td></tr>
<tr><td>grandfather/grandpa</td><td>parent's father</td></tr>
<tr><td>grandmother/grandma</td><td>parent's mother</td></tr>
<tr><td>uncle</td><td>parent's brother</td></tr>
<tr><td>aunt</td><td>parent's sister</td></tr>
<tr><td>cousin</td><td>uncle/aunt's child</td></tr>
<tr><td>nephew</td><td>brother/sister's son</td></tr>
<tr><td>niece</td><td>brother/sister's daughter</td></tr></table>
<h4>Extended Family</h4>
<div class="example">in-laws: mother-in-law, father-in-law, sister-in-law, brother-in-law</div>
<div class="example">step-family: stepmother, stepfather, stepbrother, stepsister</div>
<h4>Talking About Family</h4>
<div class="example">I have two siblings – an older brother and a younger sister.</div>
<div class="example">My parents have been married for 25 years.</div>
<div class="example">She is an only child (no brothers or sisters).</div>`,
        questions: [
          { q: "Your mother's mother is your:", opts: ["aunt", "sister", "grandmother", "niece"], a: 2 },
          { q: "Your father's brother is your:", opts: ["uncle", "nephew", "cousin", "grandfather"], a: 0 },
          { q: "A 'sibling' is:", opts: ["your parent", "your friend", "your brother or sister", "your cousin"], a: 2 },
          { q: "'An only child' means:", opts: ["one sibling", "no siblings", "two siblings", "many siblings"], a: 1 },
          { q: "Your brother's daughter is your:", opts: ["cousin", "niece", "nephew", "aunt"], a: 1 },
          { q: "'Mother-in-law' is:", opts: ["your mother", "your wife's/husband's mother", "your aunt", "your grandmother"], a: 1 },
          { q: "Your aunt's son is your:", opts: ["uncle", "nephew", "brother", "cousin"], a: 3 },
          { q: "'Siblings' includes:", opts: ["parents", "brothers and sisters", "grandparents", "cousins"], a: 1 },
          { q: "Your sister's husband is your:", opts: ["uncle", "brother-in-law", "cousin", "nephew"], a: 1 },
          { q: "'Stepmother' means:", opts: ["your grandmother", "your biological mother", "your father's new wife", "your aunt"], a: 2 },
          { q: "Your parents' parents are your:", opts: ["cousins", "uncles", "grandparents", "siblings"], a: 2 },
          { q: "Your father's sister is your:", opts: ["niece", "cousin", "aunt", "grandmother"], a: 2 },
          { q: "'In-laws' refers to:", opts: ["your own family", "your spouse's family", "your cousins", "your neighbors"], a: 1 },
          { q: "A 'nephew' is your brother or sister's:", opts: ["daughter", "son", "wife", "husband"], a: 1 },
          { q: "'Nuclear family' includes:", opts: ["parents + children", "grandparents too", "all relatives", "only siblings"], a: 0 },
          { q: "Your father's father is your:", opts: ["uncle", "grandfather", "cousin", "brother"], a: 1 },
          { q: "'Extended family' includes:", opts: ["parents and children only", "grandparents, aunts, uncles, cousins", "friends", "neighbors"], a: 1 },
          { q: "Your mother's brother is your:", opts: ["cousin", "nephew", "uncle", "grandfather"], a: 2 },
          { q: "'Parents' means:", opts: ["siblings", "mother and father", "grandparents", "children"], a: 1 },
          { q: "Your brother's son is your:", opts: ["cousin", "niece", "nephew", "uncle"], a: 2 },
          { q: "'Twins' are siblings who:", opts: ["look different", "are born at the same time", "are many years apart", "have the same name"], a: 1 },
          { q: "Which is a female family member?", opts: ["nephew", "uncle", "grandfather", "niece"], a: 3 },
          { q: "'Adopted' child means:", opts: ["biological child", "child taken legally into a family", "only child", "twin"], a: 1 },
          { q: "Your spouse's brother is your:", opts: ["cousin", "uncle", "brother-in-law", "stepbrother"], a: 2 },
          { q: "'Ancestors' are your:", opts: ["children", "future family", "past generations of family", "friends"], a: 2 },
          { q: "Correct sentence:", opts: ["My brother are tall", "My brother is tall", "My brother am tall", "My brother be tall"], a: 1 },
          { q: "'Single parent family' has:", opts: ["two parents", "one parent", "grandparents", "no children"], a: 1 },
          { q: "Your grandmother's son who is not your parent is your:", opts: ["cousin", "uncle", "grandfather", "nephew"], a: 1 },
          { q: "Which is a plural word for family members?", opts: ["parent", "sibling", "grandparent", "siblings"], a: 3 },
          { q: "'Relatives' means:", opts: ["friends", "neighbors", "family members", "teachers"], a: 2 },
        ]
      },
      conditionals: {
        icon: '🔀', name: 'Conditional Sentences',
        lesson: `<h4>Types of Conditionals</h4>
<table><tr><th>Type</th><th>Structure</th><th>Meaning</th></tr>
<tr><td>Zero</td><td>If + present, present</td><td>General truths</td></tr>
<tr><td>First</td><td>If + present, will + V1</td><td>Real/possible future</td></tr>
<tr><td>Second</td><td>If + past, would + V1</td><td>Unreal present/future</td></tr>
<tr><td>Third</td><td>If + past perfect, would have + V3</td><td>Unreal past</td></tr></table>
<h4>Examples</h4>
<div class="example">Zero: If you heat water, it boils.</div>
<div class="example">First: If it rains, I will take an umbrella.</div>
<div class="example">Second: If I had a million dollars, I would travel the world.</div>
<div class="example">Third: If she had studied, she would have passed the exam.</div>
<h4>Mixed Conditionals</h4>
<div class="example">If I had studied medicine (past), I would be a doctor now (present).</div>
<h4>Unless = if not</h4>
<div class="example">Unless you hurry, you will miss the bus. = If you don't hurry, you will miss the bus.</div>`,
        questions: [
          { q: "Zero conditional expresses:", opts: ["future possibility", "general truths", "past regrets", "unreal situations"], a: 1 },
          { q: "'If it rains, I ___ an umbrella.' (1st conditional)", opts: ["would take", "will take", "took", "take"], a: 1 },
          { q: "Second conditional uses:", opts: ["will", "would", "had", "have"], a: 1 },
          { q: "'If I ___ rich, I would travel.' (2nd cond.)", opts: ["am", "was/were", "will be", "have been"], a: 1 },
          { q: "Third conditional expresses:", opts: ["possible future", "general truths", "regrets about the past", "current habits"], a: 2 },
          { q: "'If she had studied, she ___ passed.' (3rd cond.)", opts: ["will have", "would have", "had", "would"], a: 1 },
          { q: "'Unless' means:", opts: ["if", "if not", "when", "although"], a: 1 },
          { q: "'If water reaches 100°C, it ___.' (Zero cond.)", opts: ["will boil", "would boil", "boils", "boiled"], a: 2 },
          { q: "'If I were you, I ___ accept.' (2nd cond.)", opts: ["will", "would", "should have", "had"], a: 1 },
          { q: "Which conditional talks about a real future?", opts: ["Zero", "First", "Second", "Third"], a: 1 },
          { q: "'___ you had left earlier, you wouldn't have been late.' (3rd cond.)", opts: ["Unless", "When", "If", "Although"], a: 2 },
          { q: "'If I had more time, I ___ learn Russian.'", opts: ["will", "would", "had", "have"], a: 1 },
          { q: "Mixed conditional: 'If I had studied medicine, I ___ a doctor now.'", opts: ["would be", "will be", "am", "was"], a: 0 },
          { q: "'If she ___ harder, she would succeed.' (2nd cond.)", opts: ["works", "worked", "will work", "has worked"], a: 1 },
          { q: "Correct 1st conditional:", opts: ["If it rains, I take umbrella", "If it will rain, I take umbrella", "If it rains, I will take an umbrella", "If it rained, I will take an umbrella"], a: 2 },
          { q: "'Unless you study, you ___ fail.' = ?", opts: ["will", "would", "had", "have"], a: 0 },
          { q: "'If I were a bird, I ___ fly.' This is:", opts: ["1st conditional", "Zero conditional", "2nd conditional", "3rd conditional"], a: 2 },
          { q: "'Had I known, I ___ told you.' (3rd cond.)", opts: ["would have", "will have", "had", "should"], a: 0 },
          { q: "Which sentence is 3rd conditional?", opts: ["If it rains, we stay", "If it rained, we would stay", "If it had rained, we would have stayed", "If it rains, we will stay"], a: 2 },
          { q: "'Provided that' can replace:", opts: ["although", "unless", "if", "but"], a: 2 },
          { q: "'If you ___ me, I'll help you.' (1st cond.)", opts: ["ask", "asked", "will ask", "had asked"], a: 0 },
          { q: "'If I ___ president, I would change many things.' (2nd cond.)", opts: ["am", "will be", "were", "have been"], a: 2 },
          { q: "'If she ___ earlier, she would have caught the train.' (3rd cond.)", opts: ["leave", "left", "had left", "will leave"], a: 2 },
          { q: "'___ you heat metal, it expands.' (Zero cond.)", opts: ["When/If", "Would", "Will", "Might"], a: 0 },
          { q: "Correct 2nd conditional sentence:", opts: ["If I am rich, I would travel", "If I were rich, I would travel", "If I were rich, I will travel", "If I rich, I would travel"], a: 1 },
          { q: "'Unless he calls, I ___ go.' = ?", opts: ["won't", "will", "would", "wouldn't"], a: 0 },
          { q: "'What ___ you do if you won the lottery?' (2nd cond.)", opts: ["will", "would", "do", "did"], a: 1 },
          { q: "3rd conditional: 'If they ___ earlier, they wouldn't have missed it.'", opts: ["leave", "left", "had left", "will leave"], a: 2 },
          { q: "'On condition that' is similar to:", opts: ["although", "because", "if", "but"], a: 2 },
          { q: "'I ___ have helped if you had asked.' (3rd cond.)", opts: ["will", "would", "had", "should have"], a: 1 },
        ]
      },
      modal_verbs: {
        icon: '🎯', name: 'Modal Verbs',
        lesson: `<h4>What Are Modal Verbs?</h4>
<p>Modal verbs express ability, possibility, permission, obligation, and advice. They are followed by the base form of the verb (infinitive without 'to').</p>
<h4>Main Modal Verbs</h4>
<table><tr><th>Modal</th><th>Use</th><th>Example</th></tr>
<tr><td>can</td><td>ability, possibility</td><td>I can swim.</td></tr>
<tr><td>could</td><td>past ability, polite request</td><td>Could you help me?</td></tr>
<tr><td>may</td><td>possibility, formal permission</td><td>You may leave now.</td></tr>
<tr><td>might</td><td>weak possibility</td><td>It might rain.</td></tr>
<tr><td>must</td><td>obligation, strong deduction</td><td>You must wear a seatbelt.</td></tr>
<tr><td>should</td><td>advice, recommendation</td><td>You should see a doctor.</td></tr>
<tr><td>would</td><td>conditional, polite request</td><td>Would you like tea?</td></tr>
<tr><td>shall</td><td>future (formal), suggestion</td><td>Shall we dance?</td></tr>
<tr><td>will</td><td>future, prediction</td><td>It will rain tomorrow.</td></tr>
<tr><td>ought to</td><td>moral obligation/advice</td><td>You ought to apologize.</td></tr></table>
<h4>Negative Forms</h4>
<div class="example">can't/cannot – mustn't – shouldn't – wouldn't – couldn't</div>
<h4>Perfect Modals</h4>
<div class="example">must have + V3: He must have forgotten. (deduction about past)</div>
<div class="example">should have + V3: You should have called. (regret/criticism)</div>
<div class="example">could have + V3: She could have helped. (missed opportunity)</div>`,
        questions: [
          { q: "'___ I open the window?' (asking permission formally)", opts: ["Should", "Must", "May", "Will"], a: 2 },
          { q: "'You ___ not smoke in here.' (prohibition)", opts: ["should", "must", "can", "would"], a: 1 },
          { q: "'She ___ speak three languages.' (ability)", opts: ["must", "should", "can", "ought"], a: 2 },
          { q: "'It ___ rain later.' (weak possibility)", opts: ["must", "shall", "might", "would"], a: 2 },
          { q: "'You ___ see a doctor.' (advice)", opts: ["must", "should", "can", "will"], a: 1 },
          { q: "'___ you like some coffee?' (polite offer)", opts: ["Should", "Would", "Must", "May"], a: 1 },
          { q: "'He ___ have taken the keys.' (past deduction)", opts: ["should", "would", "must", "shall"], a: 2 },
          { q: "'You ___ have studied harder.' (regret/criticism)", opts: ["must", "should", "would", "could"], a: 1 },
          { q: "'___ we go for a walk?' (suggestion)", opts: ["Must", "Shall", "Would", "Should"], a: 1 },
          { q: "Modal verbs are followed by:", opts: ["to + verb", "verb + ing", "base verb (infinitive)", "past participle"], a: 2 },
          { q: "'Could' is the past of:", opts: ["should", "must", "can", "will"], a: 2 },
          { q: "'She ___ help if she wanted to.' (conditional ability)", opts: ["must", "could", "shall", "ought"], a: 1 },
          { q: "'You ___ to apologize.' (moral obligation)", opts: ["must", "ought", "shall", "would"], a: 1 },
          { q: "'It ___ be cold tonight.' (strong deduction)", opts: ["might", "should", "must", "would"], a: 2 },
          { q: "'___ I use your phone?' (asking permission casually)", opts: ["Must", "Shall", "Can", "Ought"], a: 2 },
          { q: "Correct modal sentence:", opts: ["She musts go", "She must to go", "She must goes", "She must go"], a: 3 },
          { q: "'He couldn't ___ the exam.' (past inability)", opts: ["passed", "passing", "pass", "to pass"], a: 2 },
          { q: "'You ___ drive here; it's a pedestrian zone.'", opts: ["must", "should", "mustn't", "wouldn't"], a: 2 },
          { q: "'___ you mind closing the door?' (polite request)", opts: ["Must", "Would", "Shall", "Ought"], a: 1 },
          { q: "'They ___ arrive by 6pm.' (expectation)", opts: ["must", "might", "should", "can"], a: 2 },
          { q: "'I ___ swim when I was five.' (past ability)", opts: ["can", "could", "might", "should"], a: 1 },
          { q: "Perfect modal for missed opportunity:", opts: ["should have", "must have", "could have", "would have"], a: 2 },
          { q: "'May' expresses:", opts: ["obligation", "ability", "possibility/permission", "advice"], a: 2 },
          { q: "'Shall' is mainly used with:", opts: ["he/she/it", "I and we", "you", "they"], a: 1 },
          { q: "'You ___ eat less sugar.' (advice)", opts: ["must", "would", "should", "shall"], a: 2 },
          { q: "'He ___ have forgotten the meeting.' (past deduction – certain)", opts: ["might", "could", "must", "would"], a: 2 },
          { q: "'Will' expresses:", opts: ["past ability", "present permission", "future prediction", "past obligation"], a: 2 },
          { q: "Correct negative modal:", opts: ["He don't must go", "He mustn't go", "He mustn't to go", "He not must go"], a: 1 },
          { q: "'___ you pass me the salt?' (polite request)", opts: ["Shall", "Ought", "Could", "Must"], a: 2 },
          { q: "'They ___ have won – they played so well!'", opts: ["should", "must", "would", "can"], a: 1 },
        ]
      },
      food: {
        icon: '🍕', name: 'Food & Eating',
        lesson: `<h4>Types of Food</h4>
<table><tr><th>Category</th><th>Examples</th></tr>
<tr><td>Fruits</td><td>apple, banana, orange, mango, strawberry, grape, watermelon</td></tr>
<tr><td>Vegetables</td><td>carrot, potato, tomato, onion, broccoli, spinach, cucumber</td></tr>
<tr><td>Meat</td><td>beef, chicken, pork, lamb, fish, shrimp, turkey</td></tr>
<tr><td>Dairy</td><td>milk, cheese, butter, yogurt, cream, ice cream</td></tr>
<tr><td>Grains</td><td>bread, rice, pasta, noodles, oatmeal, cereal</td></tr>
<tr><td>Drinks</td><td>water, juice, tea, coffee, milk, soda, smoothie</td></tr></table>
<h4>Meals of the Day</h4>
<div class="example">Breakfast (morning) – Lunch (midday) – Dinner/Supper (evening) – Snack (any time)</div>
<h4>Cooking Methods</h4>
<div class="example">boil, fry, bake, grill, roast, steam, microwave, sauté</div>
<h4>Useful Phrases at a Restaurant</h4>
<div class="example">Can I see the menu, please?</div>
<div class="example">I'd like to order the steak, please.</div>
<div class="example">Could we have the bill/check, please?</div>
<div class="example">Is there anything vegetarian on the menu?</div>`,
        questions: [
          { q: "A tomato is a:", opts: ["fruit (botanically)", "vegetable", "grain", "dairy"], a: 0 },
          { q: "'Beef' comes from:", opts: ["pig", "chicken", "cow", "lamb"], a: 2 },
          { q: "The morning meal is called:", opts: ["lunch", "dinner", "breakfast", "supper"], a: 2 },
          { q: "'Dairy' products include:", opts: ["bread and rice", "cheese and milk", "apples and oranges", "carrots and peas"], a: 1 },
          { q: "'To boil' means:", opts: ["cook in hot oil", "cook in hot water", "cook in oven", "cook on grill"], a: 1 },
          { q: "'Could I see the ___?' (at a restaurant)", opts: ["bill only", "menu", "waiter", "kitchen"], a: 1 },
          { q: "'Vegetarian' means a person who:", opts: ["eats only fish", "eats no meat", "eats everything", "is a chef"], a: 1 },
          { q: "'Pork' comes from:", opts: ["cow", "chicken", "pig", "sheep"], a: 2 },
          { q: "'Bake' means to cook in a/an:", opts: ["pan with oil", "oven", "pot with water", "grill"], a: 1 },
          { q: "The midday meal is called:", opts: ["breakfast", "dinner", "lunch", "brunch"], a: 2 },
          { q: "Which is a grain?", opts: ["carrot", "rice", "milk", "banana"], a: 1 },
          { q: "'Shrimp' is a type of:", opts: ["vegetable", "grain", "seafood", "dairy"], a: 2 },
          { q: "'Brunch' is a meal between:", opts: ["lunch and dinner", "breakfast and lunch", "dinner and breakfast", "snack and lunch"], a: 1 },
          { q: "'I'd like to ___.' (ordering in a restaurant)", opts: ["see the bill", "order the salmon", "pay first", "leave now"], a: 1 },
          { q: "'Steam' means to cook with:", opts: ["oil", "water vapor/steam", "fire", "oven heat"], a: 1 },
          { q: "Which drink contains caffeine?", opts: ["water", "milk", "juice", "coffee"], a: 3 },
          { q: "'Lamb' comes from:", opts: ["cow", "pig", "young sheep", "chicken"], a: 2 },
          { q: "'Grill' means to cook:", opts: ["in water", "in oil", "over direct heat/flame", "in oven"], a: 2 },
          { q: "'Allergic to' means:", opts: ["loves eating something", "body reacts badly to something", "never cooks", "is a chef"], a: 1 },
          { q: "Which is a fruit?", opts: ["broccoli", "potato", "mango", "onion"], a: 2 },
          { q: "'Can I have the ___?' (asking to pay)", opts: ["menu", "bill/check", "waiter", "starter"], a: 1 },
          { q: "'Sauté' means:", opts: ["cook slowly in water", "cook quickly in a little oil", "bake in oven", "fry in deep oil"], a: 1 },
          { q: "'Vegan' means a person who:", opts: ["eats only vegetables", "eats no animal products at all", "eats fish only", "is vegetarian"], a: 1 },
          { q: "'Cereal' is usually eaten at:", opts: ["dinner", "lunch", "breakfast", "supper"], a: 2 },
          { q: "Which is NOT a cooking method?", opts: ["boil", "freeze", "roast", "fry"], a: 1 },
          { q: "'Starter' in a restaurant is:", opts: ["the main course", "the dessert", "the first small dish", "the drink"], a: 2 },
          { q: "'Dairy-free' means:", opts: ["contains dairy", "no dairy products", "only dairy", "more dairy"], a: 1 },
          { q: "'Recipe' means:", opts: ["a restaurant", "instructions for making food", "a type of food", "a cooking tool"], a: 1 },
          { q: "'Turkey' is often eaten at:", opts: ["Easter", "Christmas/Thanksgiving", "New Year", "Birthdays"], a: 1 },
          { q: "'Smoothie' is made with:", opts: ["blended fruits/vegetables", "hot water", "flour and eggs", "boiled milk"], a: 0 },
        ]
      },
      passive_voice: {
        icon: '🔄', name: 'Passive Voice',
        lesson: `<h4>What is Passive Voice?</h4>
<p>In passive voice, the object of an action becomes the subject of the sentence. The focus is on what happens to the subject, not who does the action.</p>
<h4>Structure: be + past participle (V3)</h4>
<table><tr><th>Tense</th><th>Active</th><th>Passive</th></tr>
<tr><td>Present Simple</td><td>They make cars here.</td><td>Cars are made here.</td></tr>
<tr><td>Past Simple</td><td>She wrote the letter.</td><td>The letter was written.</td></tr>
<tr><td>Future</td><td>They will build a bridge.</td><td>A bridge will be built.</td></tr>
<tr><td>Present Perfect</td><td>He has fixed the car.</td><td>The car has been fixed.</td></tr>
<tr><td>Modal</td><td>You must sign this.</td><td>This must be signed.</td></tr></table>
<h4>Using "by"</h4>
<div class="example">The book was written by Tolstoy. ('by' + agent – optional)</div>
<h4>When to Use Passive</h4>
<div class="example">When the agent is unknown: My wallet was stolen.</div>
<div class="example">When agent is obvious: He was arrested. (by police – obvious)</div>
<div class="example">In formal/scientific writing: The experiment was conducted.</div>`,
        questions: [
          { q: "'Cars ___ made in this factory.' (passive, present simple)", opts: ["are", "is", "were", "be"], a: 0 },
          { q: "Passive voice uses: be + ___", opts: ["infinitive", "gerund", "past participle", "present participle"], a: 2 },
          { q: "Active: 'She wrote the letter.' → Passive: 'The letter ___ written by her.'", opts: ["is", "was", "were", "has been"], a: 1 },
          { q: "'The window ___ broken by the ball.' (past passive)", opts: ["is", "was", "were", "has"], a: 1 },
          { q: "'The bridge will ___ built next year.'", opts: ["be", "been", "is", "are"], a: 0 },
          { q: "'The car has ___ repaired.' (present perfect passive)", opts: ["be", "been", "is", "was"], a: 1 },
          { q: "In passive, 'by' introduces the:", opts: ["object", "agent/doer", "verb", "adjective"], a: 1 },
          { q: "Correct passive: 'English ___ spoken in Australia.'", opts: ["are", "am", "is", "were"], a: 2 },
          { q: "Active: 'They built this temple in 1900.' → Passive:", opts: ["This temple built in 1900", "This temple was built in 1900", "This temple is built in 1900", "This temple been built in 1900"], a: 1 },
          { q: "'This must ___ signed immediately.'", opts: ["be", "been", "is", "are"], a: 0 },
          { q: "'My phone ___ stolen on the train.' (past passive)", opts: ["is", "were", "was", "has"], a: 2 },
          { q: "Passive is used when the agent is:", opts: ["always known", "unknown or unimportant", "a famous person", "mentioned first"], a: 1 },
          { q: "'The report is ___ by the manager every week.'", opts: ["write", "written", "wrote", "writing"], a: 1 },
          { q: "Active: 'He fixes the bike.' → Passive: 'The bike ___ fixed.'", opts: ["is", "are", "was", "were"], a: 0 },
          { q: "'The results ___ announced tomorrow.' (future passive)", opts: ["will be", "are", "were", "had been"], a: 0 },
          { q: "'This book was written ___ Shakespeare.'", opts: ["from", "with", "by", "to"], a: 2 },
          { q: "'The cake ___ being baked right now.' (present continuous passive)", opts: ["is", "are", "was", "were"], a: 0 },
          { q: "'English ___ taught in this school.' (present simple passive)", opts: ["is", "are", "was", "were"], a: 0 },
          { q: "Active → Passive: 'They can solve this problem.'", opts: ["This problem can solved", "This problem is solved", "This problem can be solved", "This problem solved"], a: 2 },
          { q: "'The letter had ___ sent before she arrived.' (past perfect passive)", opts: ["be", "been", "is", "was"], a: 1 },
          { q: "Which sentence is passive?", opts: ["She reads the book", "The book is read by her", "She is reading", "She has read"], a: 1 },
          { q: "'The house ___ painted last year.'", opts: ["is", "are", "was", "were"], a: 2 },
          { q: "'Many trees ___ cut down every year.' (passive, present simple)", opts: ["is", "was", "were", "are"], a: 3 },
          { q: "Passive voice is common in:", opts: ["casual conversation", "scientific writing", "poetry", "fiction"], a: 1 },
          { q: "'Three workers ___ injured in the accident.'", opts: ["is", "are", "were", "was"], a: 2 },
          { q: "'The decision ___ been made.' (present perfect passive)", opts: ["have", "has", "had", "is"], a: 1 },
          { q: "Active: 'They will announce the results.' → Passive: '___'", opts: ["Results will announce", "Results will be announced", "Results are announced", "Results had been announced"], a: 1 },
          { q: "'The medicine ___ taken twice a day.' (instruction, passive)", opts: ["must be", "must", "should", "is being"], a: 0 },
          { q: "'All tickets ___ sold out.' (present perfect passive)", opts: ["has", "have", "had", "was"], a: 1 },
          { q: "In passive voice, past participle of 'make' is:", opts: ["making", "makes", "made", "make"], a: 2 },
        ]
      },
    };

    // Fill remaining topics with auto data
    const AUTO_TOPICS = {
      body: { icon: '💪', name: 'Body Parts' }, weather: { icon: '🌤️', name: 'Weather' },
      days: { icon: '📅', name: 'Days & Time' }, clothes: { icon: '👗', name: 'Clothes & Fashion' },
      animals: { icon: '🐾', name: 'Animals' }, future: { icon: '🔮', name: 'Future Tense' },
      shopping: { icon: '🛍️', name: 'Shopping' }, travel: { icon: '✈️', name: 'Travel' },
      hobbies: { icon: '🎸', name: 'Hobbies' }, home: { icon: '🏠', name: 'Home & Living' },
      school: { icon: '🏫', name: 'School' }, health: { icon: '❤️', name: 'Health' },
      sports: { icon: '⚽', name: 'Sports' }, present_perfect: { icon: '✅', name: 'Present Perfect' },
      environment: { icon: '🌿', name: 'Environment' }, work: { icon: '💼', name: 'Work & Career' },
      technology: { icon: '💻', name: 'Technology' }, culture: { icon: '🎭', name: 'Culture' },
      relationships: { icon: '❤️', name: 'Relationships' }, science: { icon: '🔬', name: 'Science' },
      reported_speech: { icon: '💬', name: 'Reported Speech' }, relative_clauses: { icon: '🔗', name: 'Relative Clauses' },
      mixed_conditionals: { icon: '🔀', name: 'Mixed Conditionals' }, business: { icon: '📈', name: 'Business English' },
      politics: { icon: '🏛️', name: 'Politics & Society' }, media: { icon: '📺', name: 'Media' },
      psychology: { icon: '🧠', name: 'Psychology' }, economics: { icon: '💹', name: 'Economics' },
      law: { icon: '⚖️', name: 'Law & Justice' }, history: { icon: '📜', name: 'History' },
      subjunctive: { icon: '🌀', name: 'Subjunctive Mood' }, inversion: { icon: '🔄', name: 'Inversion' },
      ellipsis: { icon: '…', name: 'Ellipsis' }, literature: { icon: '📚', name: 'Literature' },
      philosophy: { icon: '🤔', name: 'Philosophy' }, medicine: { icon: '🏥', name: 'Medicine' },
      engineering: { icon: '⚙️', name: 'Engineering' }, artificial_intelligence: { icon: '🤖', name: 'Artificial Intelligence' },
      diplomacy: { icon: '🌐', name: 'Diplomacy' }, art: { icon: '🎨', name: 'Art & Creativity' },
      nuance: { icon: '🎯', name: 'Nuance & Register' }, rhetoric: { icon: '🗣️', name: 'Rhetoric' },
      academic: { icon: '🎓', name: 'Academic Writing' }, idioms_adv: { icon: '💡', name: 'Advanced Idioms' },
      collocations: { icon: '🔤', name: 'Collocations' }, register: { icon: '📝', name: 'Register & Style' },
      discourse: { icon: '💭', name: 'Discourse' }, argumentation: { icon: '⚡', name: 'Argumentation' },
      criticism: { icon: '🔍', name: 'Literary Criticism' }, synthesis: { icon: '🧩', name: 'Synthesis' },
    };

    function getTopicData(id) {
      if (TOPIC_DATA[id]) return TOPIC_DATA[id];
      const base = AUTO_TOPICS[id] || { icon: '📖', name: id };
      return {
        icon: base.icon, name: base.name,
        lesson: generateLesson(id, base.name),
        questions: generateQuestions(id, base.name)
      };
    }

    function generateLesson(id, name) {
      const lessons = {
        body: `<h4>Parts of the Human Body</h4>
<table><tr><th>Body Part</th><th>Function</th></tr>
<tr><td>Head</td><td>brain, thinking, senses</td></tr>
<tr><td>Eyes</td><td>seeing</td></tr>
<tr><td>Ears</td><td>hearing</td></tr>
<tr><td>Nose</td><td>smelling, breathing</td></tr>
<tr><td>Mouth</td><td>eating, speaking</td></tr>
<tr><td>Neck</td><td>connects head to body</td></tr>
<tr><td>Shoulders</td><td>arm attachment</td></tr>
<tr><td>Arms/Hands/Fingers</td><td>reaching, grabbing</td></tr>
<tr><td>Chest/Back</td><td>protects organs</td></tr>
<tr><td>Stomach/Abdomen</td><td>digestion</td></tr>
<tr><td>Legs/Knees/Feet</td><td>walking, running</td></tr></table>
<h4>Describing Pain</h4>
<div class="example">My head aches. / I have a headache. / My back hurts. / I feel pain in my knee.</div>`,
        weather: `<h4>Weather Vocabulary</h4>
<table><tr><th>Weather</th><th>Description</th></tr>
<tr><td>Sunny</td><td>bright, warm, clear sky</td></tr>
<tr><td>Cloudy</td><td>covered by clouds</td></tr>
<tr><td>Rainy</td><td>precipitation, wet</td></tr>
<tr><td>Snowy</td><td>snow falling</td></tr>
<tr><td>Windy</td><td>strong air movement</td></tr>
<tr><td>Foggy</td><td>low visibility, mist</td></tr>
<tr><td>Stormy</td><td>thunder, lightning, heavy rain</td></tr>
<tr><td>Humid</td><td>hot and wet air</td></tr>
<tr><td>Freezing</td><td>below 0°C</td></tr></table>
<h4>Talking About Weather</h4>
<div class="example">What's the weather like today? — It's sunny and warm.</div>
<div class="example">It's going to rain tomorrow. / The forecast says snow.</div>`,
        future: `<h4>Future Tense Forms</h4>
<table><tr><th>Form</th><th>Use</th><th>Example</th></tr>
<tr><td>will + V1</td><td>predictions, decisions</td><td>I will call you later.</td></tr>
<tr><td>going to + V1</td><td>plans, evidence-based prediction</td><td>She's going to study.</td></tr>
<tr><td>Present Continuous</td><td>fixed arrangements</td><td>We're meeting at 6pm.</td></tr>
<tr><td>Present Simple</td><td>scheduled events</td><td>The train leaves at 8.</td></tr></table>`,
        shopping: `<h4>Shopping Vocabulary</h4>
<table><tr><th>Word</th><th>Meaning</th></tr>
<tr><td>receipt</td><td>proof of purchase</td></tr>
<tr><td>refund</td><td>money back</td></tr>
<tr><td>discount</td><td>reduced price</td></tr>
<tr><td>sale</td><td>items at lower prices</td></tr>
<tr><td>cashier</td><td>person at checkout</td></tr>
<tr><td>trolley/cart</td><td>shopping cart</td></tr>
<tr><td>queue/line</td><td>people waiting</td></tr></table>
<h4>Useful Phrases</h4>
<div class="example">How much does this cost? / Can I try this on? / Do you have this in size M? / I'd like to return this.</div>`,
        travel: `<h4>Travel Vocabulary</h4>
<table><tr><th>Word</th><th>Meaning</th></tr>
<tr><td>passport</td><td>travel document</td></tr>
<tr><td>boarding pass</td><td>plane ticket for boarding</td></tr>
<tr><td>luggage/baggage</td><td>bags and suitcases</td></tr>
<tr><td>customs</td><td>border control</td></tr>
<tr><td>itinerary</td><td>travel plan/schedule</td></tr>
<tr><td>hostel</td><td>budget accommodation</td></tr>
<tr><td>jet lag</td><td>tiredness from time zones</td></tr></table>`,
        technology: `<h4>Technology Vocabulary</h4>
<table><tr><th>Term</th><th>Meaning</th></tr>
<tr><td>software</td><td>programs, apps</td></tr>
<tr><td>hardware</td><td>physical parts of computer</td></tr>
<tr><td>bandwidth</td><td>internet speed capacity</td></tr>
<tr><td>algorithm</td><td>set of instructions</td></tr>
<tr><td>encryption</td><td>data security coding</td></tr>
<tr><td>cloud</td><td>internet-based storage</td></tr>
<tr><td>AI</td><td>artificial intelligence</td></tr>
<tr><td>interface</td><td>user interaction design</td></tr></table>`,
        health: `<h4>Health & Medical Vocabulary</h4>
<table><tr><th>Word</th><th>Meaning</th></tr>
<tr><td>symptom</td><td>sign of illness</td></tr>
<tr><td>diagnosis</td><td>identifying the illness</td></tr>
<tr><td>prescription</td><td>doctor's medicine order</td></tr>
<tr><td>allergy</td><td>bad reaction to something</td></tr>
<tr><td>chronic</td><td>long-lasting illness</td></tr>
<tr><td>vaccine</td><td>preventive injection</td></tr>
<tr><td>surgery</td><td>medical operation</td></tr></table>`,
        business: `<h4>Business English Vocabulary</h4>
<table><tr><th>Term</th><th>Meaning</th></tr>
<tr><td>revenue</td><td>total income</td></tr>
<tr><td>profit</td><td>income minus expenses</td></tr>
<tr><td>stakeholder</td><td>person with interest in company</td></tr>
<tr><td>merger</td><td>two companies joining</td></tr>
<tr><td>acquisition</td><td>buying another company</td></tr>
<tr><td>quarterly report</td><td>3-month business review</td></tr>
<tr><td>ROI</td><td>return on investment</td></tr>
<tr><td>KPI</td><td>key performance indicator</td></tr></table>`,
      };
      return lessons[id] || `<h4>${name}</h4>
<p>This topic covers important aspects of ${name} in English. Study the vocabulary, grammar structures, and examples carefully before taking the test.</p>
<h4>Key Points</h4>
<div class="example">Study the vocabulary and phrases related to ${name} to improve your English skills.</div>
<div class="example">Practice using these words in sentences to become more fluent.</div>
<h4>Examples and Usage</h4>
<div class="example">Use context to understand and remember new words more effectively.</div>
<div class="example">Regular practice is the key to mastering any language topic.</div>`;
    }

    function generateQuestions(id, name) {
      const qBank = {
        body: [
          { q: "Where is your 'elbow'?", opts: ["in your leg", "in your arm", "in your neck", "in your foot"], a: 1 },
          { q: "'I have a headache.' means:", opts: ["my arm hurts", "my head hurts", "my leg hurts", "my back hurts"], a: 1 },
          { q: "Which body part is used for hearing?", opts: ["nose", "eyes", "ears", "tongue"], a: 2 },
          { q: "'Knees' are part of your:", opts: ["arms", "head", "legs", "back"], a: 2 },
          { q: "'Spine' is another word for:", opts: ["shoulder", "backbone", "chest", "ankle"], a: 1 },
          { q: "Which is on your face?", opts: ["knee", "elbow", "ankle", "cheek"], a: 3 },
          { q: "'Lungs' are organs used for:", opts: ["digestion", "hearing", "breathing", "seeing"], a: 2 },
          { q: "'My back hurts' means:", opts: ["I have pain in my front", "I have pain in my back", "I have pain in my arm", "I feel good"], a: 1 },
          { q: "'Wrist' connects the hand to the:", opts: ["elbow", "finger", "forearm", "shoulder"], a: 2 },
          { q: "'Thumb' is a type of:", opts: ["toe", "finger", "palm", "nail"], a: 1 },
          { q: "Which is at the end of your leg?", opts: ["hand", "foot", "elbow", "wrist"], a: 1 },
          { q: "'Heart' is located in your:", opts: ["head", "stomach", "chest", "back"], a: 2 },
          { q: "'Eyebrow' is above your:", opts: ["nose", "mouth", "eye", "ear"], a: 2 },
          { q: "'Shoulder' connects your arm to your:", opts: ["neck", "hip", "chest/torso", "head"], a: 2 },
          { q: "'Skin' is the ___ of your body.", opts: ["inside", "bone", "outer covering", "muscle"], a: 2 },
          { q: "'Ankle' is the joint between foot and:", opts: ["knee", "hip", "lower leg", "thigh"], a: 2 },
          { q: "'Stomach' is used for:", opts: ["breathing", "thinking", "digesting food", "seeing"], a: 2 },
          { q: "'Palm' refers to:", opts: ["the back of the hand", "the inner surface of the hand", "a finger", "the wrist"], a: 1 },
          { q: "Which part of the body thinks?", opts: ["heart", "stomach", "brain", "kidney"], a: 2 },
          { q: "'Chin' is the lower part of your:", opts: ["nose", "cheek", "jaw/face", "forehead"], a: 2 },
          { q: "'Throat' is inside your:", opts: ["arm", "chest", "neck", "leg"], a: 2 },
          { q: "'Rib' is a type of:", opts: ["muscle", "bone", "organ", "skin"], a: 1 },
          { q: "'Forehead' is above your:", opts: ["eyes", "chin", "nose", "mouth"], a: 0 },
          { q: "'Hip' is located at the top of your:", opts: ["arm", "leg/pelvis area", "back", "neck"], a: 1 },
          { q: "'Calf' is the muscle at the back of your:", opts: ["arm", "thigh", "lower leg", "foot"], a: 2 },
          { q: "'Kidney' is an organ that:", opts: ["pumps blood", "filters blood/urine", "digests food", "helps you breathe"], a: 1 },
          { q: "'Muscles' help your body to:", opts: ["think", "digest", "move", "breathe"], a: 2 },
          { q: "'Nail' grows on your:", opts: ["ear", "nose", "finger", "lip"], a: 2 },
          { q: "'Eardrum' helps you:", opts: ["see", "taste", "hear", "smell"], a: 2 },
          { q: "'Tongue' helps you to:", opts: ["hear", "taste and speak", "see", "breathe"], a: 1 },
        ],
        weather: [
          { q: "What does 'sunny' mean?", opts: ["full of clouds", "raining", "bright with sunshine", "snowing"], a: 2 },
          { q: "Temperature is measured in:", opts: ["kilograms", "kilometers", "degrees Celsius or Fahrenheit", "meters"], a: 2 },
          { q: "'It's foggy.' means:", opts: ["it's very sunny", "visibility is low due to mist", "it's snowing", "there is thunder"], a: 1 },
          { q: "'Blizzard' is an intense:", opts: ["rainstorm", "snowstorm", "heat wave", "wind"], a: 1 },
          { q: "What does 'humid' describe?", opts: ["cold and dry", "hot and wet", "freezing", "windy"], a: 1 },
          { q: "'Forecast' means:", opts: ["current weather", "past weather", "future weather prediction", "rainfall amount"], a: 2 },
          { q: "A 'tornado' is a:", opts: ["type of rain", "rotating column of air", "earthquake", "tsunami"], a: 1 },
          { q: "'Overcast' sky means:", opts: ["completely sunny", "partially cloudy", "completely covered with clouds", "stormy"], a: 2 },
          { q: "'Drizzle' is:", opts: ["heavy rain", "very light rain", "snow", "hail"], a: 1 },
          { q: "What is 'hail'?", opts: ["rain", "snow", "ice balls falling from sky", "fog"], a: 2 },
          { q: "'What's the weather like?' asks about:", opts: ["the time", "the weather condition", "your feelings", "your location"], a: 1 },
          { q: "'Freezing' means temperature is:", opts: ["above 30°C", "around 20°C", "at or below 0°C", "10°C"], a: 2 },
          { q: "'Lightning' and 'thunder' happen during a:", opts: ["blizzard", "drought", "storm/thunderstorm", "heat wave"], a: 2 },
          { q: "'Drought' is a period of:", opts: ["heavy rain", "extreme cold", "very little/no rain", "strong wind"], a: 2 },
          { q: "'Breeze' is:", opts: ["a strong dangerous wind", "a gentle, light wind", "a hurricane", "a tornado"], a: 1 },
          { q: "'Rainbow' appears after:", opts: ["a snowstorm", "sunshine alone", "rain with sunshine", "a blizzard"], a: 2 },
          { q: "'Mild' weather is:", opts: ["very hot", "very cold", "pleasantly moderate/not extreme", "stormy"], a: 2 },
          { q: "A 'hurricane' is:", opts: ["light rain", "gentle breeze", "extremely powerful tropical storm", "small cloud"], a: 2 },
          { q: "'Sleet' is a mix of:", opts: ["wind and rain", "rain and snow/ice pellets", "snow and hail", "fog and rain"], a: 1 },
          { q: "'UV index' measures:", opts: ["wind speed", "rainfall", "sun radiation strength", "temperature"], a: 2 },
          { q: "'It's going to rain.' is a:", opts: ["past statement", "present fact", "future prediction", "question"], a: 2 },
          { q: "'Meteorologist' studies:", opts: ["oceans", "weather", "mountains", "planets"], a: 1 },
          { q: "'Below zero' means temperature is:", opts: ["positive", "zero exactly", "negative / below 0°C", "very warm"], a: 2 },
          { q: "'Gust' of wind means:", opts: ["constant gentle wind", "sudden strong burst of wind", "light breeze", "tornado"], a: 1 },
          { q: "'Celsius' is a unit of:", opts: ["speed", "distance", "temperature", "pressure"], a: 2 },
          { q: "'Storm surge' is associated with:", opts: ["blizzards", "earthquakes", "hurricanes/cyclones", "droughts"], a: 2 },
          { q: "'Humidity' refers to:", opts: ["temperature", "amount of water vapor in air", "wind speed", "air pressure"], a: 1 },
          { q: "'Partly cloudy' means:", opts: ["no clouds", "all clouds", "some clouds, some sun", "raining"], a: 2 },
          { q: "'Heat wave' is:", opts: ["cold period", "period of unusually hot weather", "strong wind", "heavy rain"], a: 1 },
          { q: "'Precipitation' includes rain, snow, hail and:", opts: ["wind", "sunshine", "temperature", "sleet"], a: 3 },
        ],
        future: [
          { q: "'I ___ call you tonight.' (spontaneous decision, will)", opts: ["am going to", "will", "going to", "shall to"], a: 1 },
          { q: "'She ___ study medicine.' (plan already made)", opts: ["will", "going to is", "is going to", "shall"], a: 2 },
          { q: "'The train ___ at 9am.' (scheduled, timetable)", opts: ["will leave", "is leaving", "leaves", "going to leave"], a: 2 },
          { q: "'Look at those clouds! It ___ rain.' (evidence-based prediction)", opts: ["will", "is going to", "shall", "would"], a: 1 },
          { q: "'___ I help you?' (offer, formal)", opts: ["Will", "Shall", "Going to", "Would"], a: 1 },
          { q: "'They ___ get married next spring.' (fixed plan)", opts: ["will", "are going to", "shall", "are"], a: 1 },
          { q: "'I think it ___ be a great day.'", opts: ["going to", "shall", "will", "would"], a: 2 },
          { q: "Which shows a future arrangement?", opts: ["I study English", "I studied English", "I am meeting her at 6pm", "I have studied"], a: 2 },
          { q: "'___ you be at the meeting tomorrow?' (yes/no question, will)", opts: ["Shall", "Are", "Will", "Do"], a: 2 },
          { q: "'Don't worry, I ___ fix it.' (promise)", opts: ["am going to", "shall", "will", "would"], a: 2 },
          { q: "'She ___ present her project on Friday.' (arrangement)", opts: ["will", "is presenting", "presents", "going to present"], a: 1 },
          { q: "'I ___ probably take a taxi.' (prediction with uncertainty)", opts: ["shall", "going to", "will", "am"], a: 2 },
          { q: "'___ I open the window?' (suggestion)", opts: ["Will", "Am going to", "Shall", "Would"], a: 2 },
          { q: "'By this time next year, I ___ have finished university.'", opts: ["will", "shall", "would", "am going to"], a: 0 },
          { q: "'The concert ___ start at 8pm.' (timetable)", opts: ["will", "is going to", "starts", "shall"], a: 2 },
          { q: "'He ___ retire next month.' (decided plan)", opts: ["will", "is going to", "shall", "might"], a: 1 },
          { q: "'I think robots ___ replace many jobs.' (prediction)", opts: ["are going to", "shall", "will", "would"], a: 2 },
          { q: "'We ___ having dinner with them on Saturday.' (arrangement)", opts: ["will", "shall", "are", "going to"], a: 2 },
          { q: "'If you come, I ___ make dinner.' (conditional future)", opts: ["shall", "am going to", "will", "would"], a: 2 },
          { q: "'It ___ snow this winter.' (prediction)", opts: ["shall", "going to", "will", "is"], a: 2 },
          { q: "'___ you help me with this?' (polite request)", opts: ["Shall", "Going to", "Will", "Would"], a: 2 },
          { q: "'I ___ going to the gym later.' (personal plan)", opts: ["will", "am", "shall", "do"], a: 1 },
          { q: "'The film ___ at 7:30.' (scheduled start time)", opts: ["will start", "going to start", "starts", "shall start"], a: 2 },
          { q: "'I promise I ___ be late.' (negative promise)", opts: ["going to", "shall", "won't", "wouldn't"], a: 2 },
          { q: "'This time tomorrow, we ___ flying to Paris.'", opts: ["will", "are going to", "will be", "shall"], a: 2 },
          { q: "'She ___ call you when she arrives.' (future event + when)", opts: ["will", "is going to", "shall", "would"], a: 0 },
          { q: "'___ we go out for lunch today?' (suggestion)", opts: ["Will", "Are", "Shall", "Going to"], a: 2 },
          { q: "'He looks tired. He ___ fall asleep soon.' (evidence)", opts: ["will", "is going to", "shall", "would"], a: 1 },
          { q: "'I ___ probably see you at the party.' (future with probably)", opts: ["shall", "am going to", "will", "would"], a: 2 },
          { q: "'They have just announced the match ___ start at 3pm.' (scheduled)", opts: ["will", "going to", "shall", "is going to"], a: 0 },
        ],
        present_perfect: [
          { q: "'I have ___ the film.' (watch)", opts: ["watched", "watch", "watching", "watches"], a: 0 },
          { q: "Present perfect uses: have/has + ___", opts: ["infinitive", "past simple", "past participle", "gerund"], a: 2 },
          { q: "'She has ___ lived in Paris.' (never)", opts: ["ever", "already", "since", "never"], a: 3 },
          { q: "'___ you ever tried sushi?'", opts: ["Did", "Have", "Do", "Was"], a: 1 },
          { q: "'He has ___ finished.' (just – recently)", opts: ["yet", "since", "just", "already"], a: 2 },
          { q: "'I haven't seen her ___ Monday.'", opts: ["for", "since", "ago", "already"], a: 1 },
          { q: "'We've known each other ___ 10 years.'", opts: ["since", "just", "ago", "for"], a: 3 },
          { q: "'Has she ___ the dishes yet?' (wash)", opts: ["washed", "wash", "washing", "washes"], a: 0 },
          { q: "'I have ___ to Japan.' (go)", opts: ["gone", "went", "going", "go"], a: 0 },
          { q: "Past participle of 'eat':", opts: ["eat", "ate", "eating", "eaten"], a: 3 },
          { q: "'They haven't arrived ___.'", opts: ["already", "just", "since", "yet"], a: 3 },
          { q: "'It's the best film I ___ seen.'", opts: ["have", "has", "ever have", "ever"], a: 0 },
          { q: "'She ___ just left.' (present perfect)", opts: ["has", "have", "had", "is"], a: 0 },
          { q: "'I ___ never eaten snails.'", opts: ["has", "have", "had", "am"], a: 1 },
          { q: "'___ he ever been to Africa?'", opts: ["Did", "Does", "Has", "Have"], a: 2 },
          { q: "'We've lived here ___ 2010.'", opts: ["for", "already", "since", "yet"], a: 2 },
          { q: "Present perfect connects past to:", opts: ["another past event", "future only", "the present now", "distant future"], a: 2 },
          { q: "'She has ___ three books this year.' (read)", opts: ["read", "reading", "reads", "readed"], a: 0 },
          { q: "'___ you finished your homework yet?'", opts: ["Did", "Does", "Have", "Has"], a: 2 },
          { q: "Past participle of 'write':", opts: ["wrote", "writing", "written", "writes"], a: 2 },
          { q: "'He ___ been to the gym today.'", opts: ["has", "have", "had", "is"], a: 0 },
          { q: "'I've ___ seen this movie – I know the ending.'", opts: ["just", "yet", "never", "already"], a: 3 },
          { q: "'They ___ been married for 20 years.'", opts: ["have", "has", "had", "are"], a: 0 },
          { q: "'___ she called you back yet?'", opts: ["Did", "Does", "Has", "Have"], a: 2 },
          { q: "Past participle of 'take':", opts: ["took", "taking", "taken", "takes"], a: 2 },
          { q: "'I haven't done it ___.' (still not done)", opts: ["already", "since", "yet", "for"], a: 2 },
          { q: "'This is the first time he ___ flown.'", opts: ["have", "has", "had", "is"], a: 1 },
          { q: "'We've ___ waiting for an hour.' (continuous)", opts: ["been", "be", "are", "is"], a: 0 },
          { q: "'How long ___ you known her?'", opts: ["did", "do", "have", "has"], a: 2 },
          { q: "'She ___ won many awards.' (already)", opts: ["have already", "has already", "had already", "is already"], a: 1 },
        ],
      };

      if (qBank[id]) return qBank[id];

      // Generic 30 questions for any topic
      const genericSets = [
        { q: `Which word is most related to ${name}?`, opts: ["sky", "grammar", "word", "book"], a: 2 },
        { q: "Choose the correct sentence:", opts: ["She go to school", "She goes to school", "She going to school", "She to school goes"], a: 1 },
        { q: "What tense is 'I am studying'?", opts: ["Past Simple", "Present Simple", "Present Continuous", "Future Simple"], a: 2 },
        { q: "'Vocabulary' means:", opts: ["grammar rules", "words in a language", "speaking ability", "sentence structure"], a: 1 },
        { q: "Which is a noun?", opts: ["quickly", "beautiful", "happiness", "run"], a: 2 },
        { q: "Which is a verb?", opts: ["table", "happy", "slowly", "think"], a: 3 },
        { q: "Which is an adjective?", opts: ["run", "table", "beautiful", "quickly"], a: 2 },
        { q: "'Fluent' means:", opts: ["slow", "able to speak easily and well", "learning", "foreign"], a: 1 },
        { q: "'Grammar' is the study of:", opts: ["vocabulary", "rules of language structure", "pronunciation", "writing speed"], a: 1 },
        { q: "'Synonym' means a word with:", opts: ["opposite meaning", "same meaning", "no meaning", "strange meaning"], a: 1 },
        { q: "'Antonym' means a word with:", opts: ["same meaning", "opposite meaning", "similar sound", "no meaning"], a: 1 },
        { q: "'Context' helps you understand word:", opts: ["spelling", "pronunciation", "meaning", "origin"], a: 2 },
        { q: "Which is an adverb?", opts: ["happy", "table", "run", "quickly"], a: 3 },
        { q: "'Prefix' is added to the ___ of a word.", opts: ["end", "middle", "beginning", "anywhere"], a: 2 },
        { q: "'Suffix' is added to the ___ of a word.", opts: ["beginning", "middle", "end", "anywhere"], a: 2 },
        { q: "'Comprehension' means:", opts: ["speaking skill", "writing skill", "understanding", "pronunciation"], a: 2 },
        { q: "Which word ends in a suffix meaning 'full of'?", opts: ["quickly", "beautiful", "running", "tables"], a: 1 },
        { q: "'Phrase' is a group of words that:", opts: ["form a complete sentence", "don't form a complete sentence", "have no meaning", "are all verbs"], a: 1 },
        { q: "A 'clause' contains a:", opts: ["only nouns", "subject and verb", "only adjectives", "single word"], a: 1 },
        { q: "'Bilingual' means speaking:", opts: ["one language", "two languages", "three languages", "no language"], a: 1 },
        { q: "'Collocation' is words that:", opts: ["sound similar", "often go together naturally", "are opposites", "are synonyms"], a: 1 },
        { q: "Which is a preposition?", opts: ["run", "happy", "under", "quickly"], a: 2 },
        { q: "'Conjunction' connects:", opts: ["nouns only", "sentences, clauses, or words", "verbs only", "only adjectives"], a: 1 },
        { q: "'Article' includes words like:", opts: ["and, but, or", "a, an, the", "is, are, was", "very, quite, so"], a: 1 },
        { q: "'Pronunciation' is about how words are:", opts: ["written", "spelled", "spoken aloud", "defined"], a: 2 },
        { q: "'Idiom' is an expression whose meaning:", opts: ["is literal", "is not literal", "has no words", "is a single word"], a: 1 },
        { q: "'Tense' in grammar relates to:", opts: ["meaning", "time", "sound", "spelling"], a: 1 },
        { q: "'Subject' of a sentence is who or what:", opts: ["is described", "receives the action", "performs the action", "is the object"], a: 2 },
        { q: "'Object' in a sentence receives the:", opts: ["subject", "action", "adjective", "conjunction"], a: 1 },
        { q: "'Native speaker' is someone who learned a language:", opts: ["in school", "as an adult", "from birth", "from books"], a: 2 },
      ];
      return genericSets;
    }

    // ========================
    // VOCABULARY (500+ words)
    // ========================
    const VOCAB = [
      // Nouns
      { w: "apple", tr: "яблоко/olma/себ", pos: "noun", ex: "I eat an apple every day.", cat: "nouns" },
      { w: "book", tr: "книга/kitob/китоб", pos: "noun", ex: "She reads a book every night.", cat: "nouns" },
      { w: "house", tr: "дом/uy/хона", pos: "noun", ex: "They live in a big house.", cat: "nouns" },
      { w: "water", tr: "вода/suv/об", pos: "noun", ex: "Drink more water every day.", cat: "nouns" },
      { w: "time", tr: "время/vaqt/вақт", pos: "noun", ex: "Time flies when you're having fun.", cat: "nouns" },
      { w: "world", tr: "мир/dunyo/ҷаҳон", pos: "noun", ex: "The world is a big place.", cat: "nouns" },
      { w: "school", tr: "школа/maktab/мактаб", pos: "noun", ex: "Children go to school every day.", cat: "nouns" },
      { w: "family", tr: "семья/oila/оила", pos: "noun", ex: "My family is very important to me.", cat: "nouns" },
      { w: "friend", tr: "друг/do'st/дӯст", pos: "noun", ex: "She is my best friend.", cat: "nouns" },
      { w: "language", tr: "язык/til/забон", pos: "noun", ex: "English is a global language.", cat: "nouns" },
      { w: "city", tr: "город/shahar/шаҳр", pos: "noun", ex: "I live in a big city.", cat: "nouns" },
      { w: "money", tr: "деньги/pul/пул", pos: "noun", ex: "Money cannot buy happiness.", cat: "nouns" },
      { w: "health", tr: "здоровье/salomatlik/саломатӣ", pos: "noun", ex: "Health is wealth.", cat: "nouns" },
      { w: "power", tr: "сила/quvvat/қувват", pos: "noun", ex: "Knowledge is power.", cat: "nouns" },
      { w: "dream", tr: "мечта/orzu/орзу", pos: "noun", ex: "Follow your dreams.", cat: "nouns" },
      { w: "nature", tr: "природа/tabiat/табиат", pos: "noun", ex: "We must protect nature.", cat: "nouns" },
      { w: "idea", tr: "идея/g'oya/ғоя", pos: "noun", ex: "That's a great idea!", cat: "nouns" },
      { w: "problem", tr: "проблема/muammo/мушкил", pos: "noun", ex: "Every problem has a solution.", cat: "nouns" },
      { w: "question", tr: "вопрос/savol/савол", pos: "noun", ex: "Do you have a question?", cat: "nouns" },
      { w: "answer", tr: "ответ/javob/ҷавоб", pos: "noun", ex: "I found the answer.", cat: "nouns" },
      { w: "information", tr: "информация/ma'lumot/маълумот", pos: "noun", ex: "I need more information.", cat: "nouns" },
      { w: "experience", tr: "опыт/tajriba/таҷриба", pos: "noun", ex: "Experience is the best teacher.", cat: "nouns" },
      { w: "opportunity", tr: "возможность/imkoniyat/имконият", pos: "noun", ex: "Don't miss this opportunity.", cat: "nouns" },
      { w: "relationship", tr: "отношения/munosabat/муносибат", pos: "noun", ex: "Good relationships take work.", cat: "nouns" },
      { w: "government", tr: "правительство/hukumat/ҳукумат", pos: "noun", ex: "The government passed a new law.", cat: "nouns" },
      { w: "environment", tr: "окружающая среда/muhit/муҳит", pos: "noun", ex: "We must protect the environment.", cat: "nouns" },
      { w: "technology", tr: "технология/texnologiya/технология", pos: "noun", ex: "Technology changes our lives.", cat: "nouns" },
      { w: "education", tr: "образование/ta'lim/таълим", pos: "noun", ex: "Education opens all doors.", cat: "nouns" },
      { w: "culture", tr: "культура/madaniyat/фарҳанг", pos: "noun", ex: "Every country has its own culture.", cat: "nouns" },
      { w: "society", tr: "общество/jamiyat/ҷомеа", pos: "noun", ex: "We all contribute to society.", cat: "nouns" },
      // Verbs
      { w: "run", tr: "бежать/yugurmoq/давидан", pos: "verb", ex: "I run every morning.", cat: "verbs" },
      { w: "think", tr: "думать/o'ylash/фикр кардан", pos: "verb", ex: "Think before you speak.", cat: "verbs" },
      { w: "learn", tr: "учиться/o'rganmoq/омӯхтан", pos: "verb", ex: "I want to learn English.", cat: "verbs" },
      { w: "create", tr: "создавать/yaratmoq/эҷод кардан", pos: "verb", ex: "She creates beautiful art.", cat: "verbs" },
      { w: "believe", tr: "верить/ishonmoq/боварӣ доштан", pos: "verb", ex: "I believe in you.", cat: "verbs" },
      { w: "understand", tr: "понимать/tushunmoq/фаҳмидан", pos: "verb", ex: "I don't understand this.", cat: "verbs" },
      { w: "achieve", tr: "достигать/erishmoq/расидан", pos: "verb", ex: "You can achieve anything.", cat: "verbs" },
      { w: "improve", tr: "улучшать/yaxshilamoq/беҳтар кардан", pos: "verb", ex: "I want to improve my English.", cat: "verbs" },
      { w: "communicate", tr: "общаться/muloqot qilmoq/муошират кардан", pos: "verb", ex: "We communicate by email.", cat: "verbs" },
      { w: "discover", tr: "открывать/kashf etmoq/кашф кардан", pos: "verb", ex: "Scientists discover new things.", cat: "verbs" },
      { w: "develop", tr: "развивать/rivojlantirmoq/инкишоф додан", pos: "verb", ex: "We need to develop this skill.", cat: "verbs" },
      { w: "represent", tr: "представлять/ifodalash/намояндагӣ кардан", pos: "verb", ex: "She represents our team.", cat: "verbs" },
      { w: "establish", tr: "основывать/o'rnatmoq/таъсис додан", pos: "verb", ex: "We want to establish new rules.", cat: "verbs" },
      { w: "provide", tr: "обеспечивать/ta'minlamoq/таъмин кардан", pos: "verb", ex: "We provide free education.", cat: "verbs" },
      { w: "require", tr: "требовать/talab qilmoq/талаб кардан", pos: "verb", ex: "This job requires experience.", cat: "verbs" },
      { w: "consider", tr: "рассматривать/ko'rib chiqmoq/баррасӣ кардан", pos: "verb", ex: "Consider all your options.", cat: "verbs" },
      { w: "suggest", tr: "предлагать/taklif qilmoq/пешниҳод кардан", pos: "verb", ex: "I suggest we leave early.", cat: "verbs" },
      { w: "solve", tr: "решать/yechmoq/ҳал кардан", pos: "verb", ex: "Can you solve this problem?", cat: "verbs" },
      { w: "participate", tr: "участвовать/ishtirok etmoq/иштирок кардан", pos: "verb", ex: "Everyone should participate.", cat: "verbs" },
      { w: "encourage", tr: "поощрять/rag'batlantirmoq/ҳавасмандонидан", pos: "verb", ex: "Teachers encourage students.", cat: "verbs" },
      // Adjectives
      { w: "beautiful", tr: "красивый/chiroyli/зебо", pos: "adj", ex: "She has a beautiful smile.", cat: "adj" },
      { w: "important", tr: "важный/muhim/муҳим", pos: "adj", ex: "Education is very important.", cat: "adj" },
      { w: "different", tr: "разный/turli/гуногун", pos: "adj", ex: "We have different opinions.", cat: "adj" },
      { w: "possible", tr: "возможный/mumkin/имконпазир", pos: "adj", ex: "Anything is possible.", cat: "adj" },
      { w: "necessary", tr: "необходимый/zarur/зарур", pos: "adj", ex: "Exercise is necessary for health.", cat: "adj" },
      { w: "successful", tr: "успешный/muvaffaqiyatli/муваффақ", pos: "adj", ex: "She is a successful manager.", cat: "adj" },
      { w: "confident", tr: "уверенный/ishonchli/боэтимод", pos: "adj", ex: "Be confident in yourself.", cat: "adj" },
      { w: "creative", tr: "творческий/ijodiy/эҷодӣ", pos: "adj", ex: "He is a creative designer.", cat: "adj" },
      { w: "efficient", tr: "эффективный/samarali/самаранок", pos: "adj", ex: "This is a very efficient method.", cat: "adj" },
      { w: "flexible", tr: "гибкий/moslashuvchan/чандир", pos: "adj", ex: "You need to be flexible.", cat: "adj" },
      { w: "innovative", tr: "инновационный/innovatsion/навовар", pos: "adj", ex: "They have innovative ideas.", cat: "adj" },
      { w: "reliable", tr: "надёжный/ishonchli/боэтимод", pos: "adj", ex: "He is a reliable worker.", cat: "adj" },
      { w: "significant", tr: "значительный/muhim/муҳим", pos: "adj", ex: "This is a significant discovery.", cat: "adj" },
      { w: "traditional", tr: "традиционный/an'anaviy/анъанавӣ", pos: "adj", ex: "They follow traditional customs.", cat: "adj" },
      { w: "unique", tr: "уникальный/noyob/беназир", pos: "adj", ex: "Every person is unique.", cat: "adj" },
      // Adverbs
      { w: "quickly", tr: "быстро/tez/тез", pos: "adv", ex: "She works quickly.", cat: "adv" },
      { w: "carefully", tr: "осторожно/ehtiyotkorlik bilan/бодиққат", pos: "adv", ex: "Read the instructions carefully.", cat: "adv" },
      { w: "recently", tr: "недавно/yaqinda/наздикан", pos: "adv", ex: "I recently moved to the city.", cat: "adv" },
      { w: "completely", tr: "полностью/butunlay/пурра", pos: "adv", ex: "I completely agree with you.", cat: "adv" },
      { w: "apparently", tr: "видимо/ko'rinishicha/зоҳиран", pos: "adv", ex: "Apparently, she left early.", cat: "adv" },
      { w: "definitely", tr: "определённо/albatta/қатъан", pos: "adv", ex: "I will definitely come.", cat: "adv" },
      { w: "extremely", tr: "крайне/juda/хеле", pos: "adv", ex: "It's extremely cold today.", cat: "adv" },
      { w: "fortunately", tr: "к счастью/baxtga qarshi/хушбахтона", pos: "adv", ex: "Fortunately, no one was hurt.", cat: "adv" },
      { w: "gradually", tr: "постепенно/asta-sekin/тадриҷан", pos: "adv", ex: "Things will improve gradually.", cat: "adv" },
      { w: "immediately", tr: "немедленно/darhol/фавран", pos: "adv", ex: "Please respond immediately.", cat: "adv" },
      // Phrases
      { w: "as soon as possible", tr: "как можно скорее/imkon qadar tez/ҳар чи зудтар", pos: "phrase", ex: "Please reply as soon as possible.", cat: "phrases" },
      { w: "in other words", tr: "другими словами/boshqacha aytganda/ба ибораи дигар", pos: "phrase", ex: "In other words, we need more time.", cat: "phrases" },
      { w: "on the other hand", tr: "с другой стороны/boshqa tomondan/аз тарафи дигар", pos: "phrase", ex: "On the other hand, it could work.", cat: "phrases" },
      { w: "for example", tr: "например/masalan/масалан", pos: "phrase", ex: "For example, dogs and cats are pets.", cat: "phrases" },
      { w: "in addition", tr: "кроме того/bundan tashqari/илова бар ин", pos: "phrase", ex: "In addition, we need more staff.", cat: "phrases" },
      { w: "as a result", tr: "в результате/natijada/дар натиҷа", pos: "phrase", ex: "As a result, profits increased.", cat: "phrases" },
      { w: "in spite of", tr: "несмотря на/qaramay/сарфи назар аз", pos: "phrase", ex: "In spite of rain, we played.", cat: "phrases" },
      { w: "due to", tr: "из-за/tufayli/бо сабаби", pos: "phrase", ex: "Due to traffic, I was late.", cat: "phrases" },
      { w: "according to", tr: "по мнению/ga ko'ra/мувофиқи", pos: "phrase", ex: "According to the report, sales fell.", cat: "phrases" },
      { w: "with regard to", tr: "в отношении/ga nisbatan/дар бораи", pos: "phrase", ex: "With regard to your question...", cat: "phrases" },
      // Idioms
      { w: "break a leg", tr: "удачи/omad/муваффақ бош", pos: "idiom", ex: "Break a leg at your interview!", cat: "idioms" },
      { w: "hit the nail on the head", tr: "попасть в точку/to'g'ri topmoq/дақиқ гуфтан", pos: "idiom", ex: "You hit the nail on the head!", cat: "idioms" },
      { w: "under the weather", tr: "не в форме/kasal/бемор ҳис кардан", pos: "idiom", ex: "I feel a bit under the weather today.", cat: "idioms" },
      { w: "bite the bullet", tr: "стиснуть зубы/bardosh bermoq/истодагарӣ кардан", pos: "idiom", ex: "Just bite the bullet and do it.", cat: "idioms" },
      { w: "cost an arm and a leg", tr: "стоить очень дорого/juda qimmat/хеле гарон", pos: "idiom", ex: "That car costs an arm and a leg.", cat: "idioms" },
      { w: "spill the beans", tr: "выдать секрет/sir aytib yubormoq/роз фош кардан", pos: "idiom", ex: "Don't spill the beans about the party!", cat: "idioms" },
      { w: "kick the bucket", tr: "умереть (сленг)/o'lmoq/мурдан", pos: "idiom", ex: "He kicked the bucket at 90.", cat: "idioms" },
      { w: "the ball is in your court", tr: "ход за тобой/navbat senda/навбат дар даст", pos: "idiom", ex: "The ball is in your court now.", cat: "idioms" },
      { w: "once in a blue moon", tr: "крайне редко/juda kamdan-kam/хеле кам", pos: "idiom", ex: "She visits once in a blue moon.", cat: "idioms" },
      { w: "the tip of the iceberg", tr: "верхушка айсберга/manzaraning bir qismi/нӯги айсберг", pos: "idiom", ex: "That's just the tip of the iceberg.", cat: "idioms" },
      { w: "beat around the bush", tr: "ходить вокруг да около/gapni cho'zmoq/давр задан", pos: "idiom", ex: "Stop beating around the bush!", cat: "idioms" },
      { w: "hit the books", tr: "зубрить/o'qishga kirishmoq/хондан", pos: "idiom", ex: "I need to hit the books tonight.", cat: "idioms" },
      { w: "miss the boat", tr: "упустить шанс/imkoniyatni qo'ldan bermoq/имконият аз даст додан", pos: "idiom", ex: "If you don't act now, you'll miss the boat.", cat: "idioms" },
      { w: "burn the midnight oil", tr: "работать допоздна/kechgacha ishlash/шаб кор кардан", pos: "idiom", ex: "She was burning the midnight oil.", cat: "idioms" },
      { w: "the last straw", tr: "последняя капля/oxirgi tomchi/қатраи охирин", pos: "idiom", ex: "That mistake was the last straw.", cat: "idioms" },
    ];

    // ========================
    // LISTENING DATA
    // ========================
    const LISTENING = {
      beginner: [
        { title: "A Day in My Life", text: "Hello! My name is Emma. I wake up at seven o'clock every morning. First, I take a shower and get dressed. Then I eat breakfast – usually eggs and toast. I walk to the bus stop and take the bus to school. My favorite class is English. After school, I play with my friends in the park. In the evening, I do my homework and watch TV. I go to bed at nine thirty. I love my life!", q: "What time does Emma wake up?", opts: ["6:00", "7:00", "8:00", "7:30"], a: 1 },
        { title: "At the Supermarket", text: "Tom goes to the supermarket on Saturdays. Today, he needs bread, milk, eggs, and some fruit. He takes a shopping cart and walks through the aisles. He picks up a loaf of bread, two liters of milk, and a dozen eggs. In the fruit section, he chooses some apples, bananas, and oranges. At the checkout, the cashier tells him the total is fifteen dollars and fifty cents. Tom pays with his credit card and gets his receipt. He puts everything in his bag and goes home.", q: "How does Tom pay?", opts: ["cash", "debit card", "credit card", "check"], a: 2 },
        { title: "The Weather Today", text: "Good morning! Here is today's weather report. In the north, it will be mostly cloudy with some rain in the afternoon. Temperatures will reach twelve degrees Celsius. In the south, it will be sunny and warm, with highs of twenty-two degrees. The east will experience strong winds and possible thunderstorms in the evening. The west will enjoy mild weather with light clouds. Remember to take an umbrella if you are traveling north or east today. Have a great day!", q: "What weather is expected in the south?", opts: ["rainy", "cloudy", "thunderstorms", "sunny and warm"], a: 3 },
        { title: "My Family", text: "Hi, I'm Alex! I'm going to tell you about my family. My father's name is David. He is a doctor and works at the local hospital. My mother's name is Sarah. She is a teacher at a primary school. I have one brother, his name is Mike. He is seventeen and loves football. I also have a sister called Lisa. She is only five years old and loves drawing. My grandparents live with us too. We are a big, happy family!", q: "What does Alex's mother do?", opts: ["doctor", "teacher", "nurse", "engineer"], a: 1 },
        { title: "My Favorite Hobby", text: "My favorite hobby is photography. I got my first camera when I was twelve years old. Since then, I have taken thousands of photos. I especially love taking pictures of nature – flowers, birds, and landscapes. Every weekend, I go to a different park or forest to find interesting subjects. I also take photos of people and city life. Last month, I entered a photography competition and won second place. I hope to become a professional photographer one day.", q: "What did the speaker win?", opts: ["first place", "second place", "third place", "nothing"], a: 1 },
      ],
      intermediate: [
        { title: "Climate Change Explained", text: "Climate change refers to long-term shifts in global temperatures and weather patterns. While some climate change is natural, since the mid-20th century, human activities have been the main driver of climate change. Burning fossil fuels like coal, oil, and gas releases greenhouse gases such as carbon dioxide and methane into the atmosphere. These gases trap heat from the sun, causing the Earth's temperature to rise. The consequences include rising sea levels, more frequent extreme weather events, and threats to biodiversity. Scientists around the world agree that immediate action is needed to reduce emissions and transition to renewable energy sources.", q: "What is the main driver of climate change since the mid-20th century?", opts: ["natural events", "volcanic eruptions", "human activities", "ocean currents"], a: 2 },
        { title: "The History of the Internet", text: "The internet began as a military project in the United States in the late 1960s. It was originally called ARPANET and was designed to allow computers to communicate with each other. In the 1980s, the internet was opened to universities and research institutions. The real revolution came in 1991, when Tim Berners-Lee invented the World Wide Web, making information accessible to everyone. By the mid-1990s, the internet was becoming commercial. Today, more than five billion people use the internet worldwide. It has transformed communication, commerce, entertainment, and education in ways that were unimaginable fifty years ago.", q: "Who invented the World Wide Web?", opts: ["Steve Jobs", "Bill Gates", "Tim Berners-Lee", "Elon Musk"], a: 2 },
        { title: "Job Interview Tips", text: "Preparing for a job interview can feel overwhelming, but with the right approach, you can succeed. First, research the company thoroughly before your interview. Know their products, services, and company culture. Second, practice answering common interview questions such as 'Tell me about yourself' and 'What are your strengths and weaknesses?' Third, dress professionally and arrive early. First impressions matter greatly. During the interview, listen carefully to each question before answering, and give specific examples from your experience. Don't forget to prepare some questions to ask the interviewer. This shows you are genuinely interested in the position. Finally, send a thank-you email after the interview.", q: "What should you send after the interview?", opts: ["a gift", "a phone call", "a thank-you email", "a formal letter"], a: 2 },
        { title: "Benefits of Exercise", text: "Regular physical exercise offers a wide range of health benefits. Cardiovascular exercise, such as running, swimming, or cycling, strengthens the heart and improves circulation. Strength training builds muscle mass and increases bone density, which is especially important as we age. Exercise also releases endorphins – chemicals in the brain that create feelings of happiness and reduce stress. Studies show that people who exercise regularly sleep better, have stronger immune systems, and live longer. Even thirty minutes of moderate exercise five days a week can make a significant difference. The key is to find an activity you enjoy and make it a regular habit.", q: "What chemicals does exercise release in the brain?", opts: ["adrenaline", "dopamine", "endorphins", "serotonin"], a: 2 },
        { title: "Cultural Differences in Business", text: "Understanding cultural differences is essential in today's global business environment. For example, punctuality means different things in different cultures. In Germany and Japan, arriving late to a meeting is considered very disrespectful. However, in some Latin American and Middle Eastern countries, meetings often start later than scheduled. Communication styles also vary – people in the United States tend to be direct and explicit, while in many Asian cultures, indirect communication is preferred to maintain harmony. Gift-giving is another area where cultures differ significantly. In China, gifts are often refused at first as a sign of politeness. Being aware of these differences can prevent misunderstandings and build better business relationships.", q: "How do people in the US typically communicate?", opts: ["indirectly", "through gifts", "directly and explicitly", "through intermediaries"], a: 2 },
      ],
      advanced: [
        { title: "Artificial Intelligence and Society", text: "Artificial intelligence is rapidly transforming virtually every sector of society. Machine learning algorithms now diagnose diseases with accuracy surpassing human specialists, generate creative works indistinguishable from human-made content, and make split-second financial decisions worth billions of dollars. However, this technological revolution raises profound ethical questions. As AI systems become more autonomous, concerns about accountability, bias in algorithmic decision-making, and the displacement of human workers are intensifying. Philosophers and technologists debate whether superintelligent AI poses existential risks to humanity. Meanwhile, governments struggle to create regulatory frameworks that encourage innovation while protecting citizens. The decisions made today about AI governance will fundamentally shape the trajectory of human civilization.", q: "What do governments struggle to create?", opts: ["better AI systems", "regulatory frameworks", "more workers", "faster computers"], a: 1 },
        { title: "The Philosophy of Language", text: "Language is far more than a tool for communication; it shapes the very fabric of our reality. The Sapir-Whorf hypothesis, also known as linguistic relativity, suggests that the language we speak influences how we perceive and think about the world. Evidence for this theory comes from studies showing that speakers of languages with different color terminology perceive colors differently. Furthermore, some languages have concepts for which no equivalent word exists in English, suggesting that certain ideas might be easier to conceptualize in those languages. Wittgenstein famously declared that the limits of language are the limits of one's world, implying that expanding our vocabulary literally expands our capacity for thought.", q: "What is another name for the Sapir-Whorf hypothesis?", opts: ["cognitive linguistics", "linguistic determinism", "linguistic relativity", "language acquisition theory"], a: 2 },
        { title: "Global Economic Inequality", text: "Despite unprecedented global economic growth over the past century, wealth inequality has reached historically extreme levels. The richest one percent of the world's population now controls more wealth than the remaining ninety-nine percent combined. This disparity has complex causes, including differential access to education and healthcare, globalization's uneven effects on labor markets, the rise of winner-take-all technology markets, and tax policies that favor capital over labor. The consequences extend beyond economics – extreme inequality is correlated with lower social mobility, higher crime rates, poorer health outcomes, and diminished democratic participation. Economists debate whether targeted redistribution, educational investment, or structural changes to market mechanisms represent the most effective interventions.", q: "What percentage of wealth does the richest 1% control?", opts: ["less than 50%", "more than 50%", "exactly 50%", "about 30%"], a: 1 },
      ]
    };

    // ========================
    // READING DATA
    // ========================
    const READING = {
      beginner: [
        {
          title: "A Perfect Day Off", text: "Last Saturday was my perfect day off. I woke up at nine o'clock, which is late for me. I made a delicious breakfast of pancakes with strawberries and maple syrup. After breakfast, I sat in my garden and read a book for two hours. The weather was lovely – warm and sunny. In the afternoon, I met my friend Anna at the park. We walked around the lake and talked about our lives. Then we had coffee and cake at a café near the park. In the evening, I cooked my favorite pasta dish and watched a film. I went to bed early and slept very well. It was a perfect day!",
          q: [{ q: "What did the person eat for breakfast?", opts: ["eggs and toast", "pancakes with strawberries", "cereal", "sandwiches"], a: 1 }, { q: "Where did the person meet Anna?", opts: ["at a café", "at home", "at the park", "at school"], a: 2 }]
        },
        {
          title: "My Dog Max", text: "I have a dog named Max. He is three years old and is a golden retriever. Max has beautiful golden fur and big brown eyes. He loves going for walks, chasing balls, and swimming in the river near our house. Every morning, I take Max for a thirty-minute walk before I go to work. In the evenings, we play in the garden. Max is very friendly and loves meeting new people. He always wags his tail when someone comes to visit. Max is not just a pet – he is my best friend. I cannot imagine my life without him.",
          q: [{ q: "What breed is Max?", opts: ["labrador", "poodle", "golden retriever", "german shepherd"], a: 2 }, { q: "How long does the morning walk last?", opts: ["15 minutes", "45 minutes", "30 minutes", "1 hour"], a: 2 }]
        },
      ],
      intermediate: [
        {
          title: "Social Media and Mental Health", text: "The relationship between social media and mental health has become one of the most debated topics of our time. Numerous studies suggest that excessive social media use is linked to increased rates of anxiety, depression, and loneliness, particularly among young people. The constant comparison with idealized images of others' lives can damage self-esteem. Cyberbullying, which occurs primarily on social platforms, affects millions of young people worldwide. However, social media also has positive aspects. It connects people across distances, provides communities for those with rare conditions or minority identities, and has been used effectively to raise awareness about mental health issues. Experts suggest that the key is not elimination of social media, but mindful, intentional use with clear boundaries.",
          q: [{ q: "What do studies link excessive social media use to?", opts: ["better health", "anxiety and depression", "more sleep", "improved grades"], a: 1 }, { q: "What do experts recommend?", opts: ["stop using social media", "use it mindfully with boundaries", "only use it for work", "delete all accounts"], a: 1 }]
        },
        {
          title: "The Science of Sleep", text: "Sleep is far more complex and important than most people realize. During sleep, the brain doesn't simply rest – it actively processes and consolidates memories, clears toxins, and regulates hormones. Scientists have identified two main types of sleep: REM (rapid eye movement) sleep, during which most dreaming occurs, and non-REM sleep, which includes deeper stages crucial for physical restoration. Adults need between seven and nine hours of sleep per night. Chronic sleep deprivation has been linked to serious health problems including obesity, diabetes, cardiovascular disease, and weakened immune function. Modern lifestyles, with their artificial lighting, screen time, and irregular schedules, significantly disrupt natural sleep cycles. Sleep experts recommend maintaining consistent sleep and wake times, even on weekends.",
          q: [{ q: "What happens to the brain during sleep?", opts: ["it completely shuts down", "it processes memories and clears toxins", "it stops all activity", "it only generates dreams"], a: 1 }, { q: "How many hours of sleep do adults need?", opts: ["5-6 hours", "7-9 hours", "10-12 hours", "4-5 hours"], a: 1 }]
        },
      ],
      advanced: [
        {
          title: "The Nature of Consciousness", text: "Consciousness remains one of the most profound mysteries in science and philosophy. Despite remarkable advances in neuroscience, we still do not understand why and how physical processes in the brain give rise to subjective experience – what philosophers call the 'hard problem of consciousness.' We can map neural correlates of consciousness and describe what happens in the brain during conscious experience, but explaining why there is something it is like to be conscious remains elusive. Some theories, such as Integrated Information Theory, attempt to quantify consciousness mathematically. Others, like Global Workspace Theory, focus on how information is broadcast across the brain. More radical proposals, including panpsychism, suggest that consciousness is a fundamental feature of the universe, present in some form even in simple systems. The question of whether artificial systems could ever be truly conscious has profound implications for AI ethics.",
          q: [{ q: "What is the 'hard problem of consciousness'?", opts: ["mapping brain activity", "explaining why subjective experience arises from physical processes", "measuring intelligence", "creating artificial consciousness"], a: 1 }, { q: "What does panpsychism suggest?", opts: ["only humans are conscious", "consciousness is a fundamental feature of the universe", "AI can never be conscious", "consciousness is an illusion"], a: 1 }]
        },
      ]
    };

    // ========================
    // SPEAKING SCENARIOS
    // ========================
    const SPEAK_SCENARIOS = [
      { context: "Meeting someone new at a conference", ai: "Hi there! I don't think we've met. What's your name?", expected: "name, hello, nice to meet" },
      { context: "At a coffee shop", ai: "Good morning! What would you like to order today?", expected: "coffee, tea, please, would like" },
      { context: "Asking for directions", ai: "Excuse me, can I help you? You look a little lost.", expected: "looking for, where is, can you tell me" },
      { context: "Job interview", ai: "Thank you for coming in today. Can you tell me a little about yourself and your experience?", expected: "I am, I have, experience, worked, years" },
      { context: "Discussing the weather", ai: "It's quite cold today, isn't it? What's your favourite type of weather?", expected: "weather, like, prefer, sunny, cold, warm" },
      { context: "Talking about hobbies", ai: "So, what do you like to do in your free time?", expected: "enjoy, like, hobby, love, spend time" },
      { context: "Making plans", ai: "Are you free this weekend? Would you like to do something together?", expected: "free, weekend, would love, sounds great, plans" },
      { context: "Ordering food at a restaurant", ai: "Welcome! Are you ready to order, or do you need a few more minutes?", expected: "ready, order, would like, menu, please" },
      { context: "Talking about your hometown", ai: "Where are you from originally? Tell me about your hometown.", expected: "from, city, town, born, live, beautiful" },
      { context: "Discussing travel", ai: "Have you traveled much? What's the most interesting place you've ever visited?", expected: "traveled, visited, country, city, amazing, beautiful" },
    ];

    // ========================
    // WRITING PROMPTS
    // ========================
    const WRITING_PROMPTS = [
      "Write about your best childhood memory. Use at least 100 words.",
      "Describe your ideal job and why you would enjoy it.",
      "Write about the advantages and disadvantages of social media.",
      "Describe a person who has had a great influence on your life.",
      "Write about an important environmental problem and possible solutions.",
      "Describe your hometown and what makes it special.",
      "Write about a book or film that changed your perspective.",
      "Should all countries adopt English as an official language? Discuss.",
      "Write about the role of technology in modern education.",
      "Describe a difficult situation you overcame and what you learned.",
    ];

    // ========================
    // LEADERBOARD DATA
    // ========================
    const LEADERBOARD = [
      { name: "Zara K.", xp: 9850, streak: 45, badge: "Champion", flag: "🇺🇿" },
      { name: "Ahmed N.", xp: 8720, streak: 32, badge: "Expert", flag: "🇺🇿" },
      { name: "Maria S.", xp: 7600, streak: 28, badge: "Advanced", flag: "🇷🇺" },
      { name: "Park J.", xp: 6950, streak: 21, badge: "Intermediate", flag: "🇰🇷" },
      { name: "Emma T.", xp: 6400, streak: 19, badge: "Intermediate", flag: "🇬🇧" },
      { name: "Carlos M.", xp: 5200, streak: 14, badge: "Elementary", flag: "🇲🇽" },
      { name: "Priya R.", xp: 4800, streak: 12, badge: "Elementary", flag: "🇮🇳" },
      { name: "Liu W.", xp: 3900, streak: 9, badge: "Beginner", flag: "🇨🇳" },
      { name: "You", xp: 0, streak: 0, badge: "Newcomer", flag: "⭐" },
      { name: "Alex B.", xp: 2100, streak: 5, badge: "Beginner", flag: "🇷🇺" },
    ];

    // ========================
    // APP STATE
    // ========================
    let currentLevel = null;
    let currentTopicId = null;
    let testQuestions = [];
    let testIndex = 0;
    let testScore = 0;
    let testAnswered = false;
    let usedQIndices = {};
    let chatHistory = [];
    let speakIdx = 0;
    let isRecording = false;
    let writingPromptIdx = 0;
    let currentAudio = null;
    let audioIntervals = {};

    // ========================
    // NAVIGATION
    // ========================
    function showPage(id) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById('page-' + id).classList.add('active');
      document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
      document.querySelectorAll('.nav-tab').forEach(t => {
        if (t.getAttribute('onclick').includes("'" + id + "'")) t.classList.add('active');
      });
      if (id === 'vocab') renderVocab();
      if (id === 'listening') renderListening();
      if (id === 'reading') renderReading();
      if (id === 'rank') renderLeaderboard();
      if (id === 'stats') renderStats();
      if (id === 'speaking') renderSpeakScenario();
      if (id === 'writing') newWritingPrompt();
      if (id === 'home') renderHomeStats();
    }

    function showInner(group, id) {
      document.querySelectorAll(`#page-${group === 'vocab' ? 'vocab' : group === 'listen' ? 'listening' : group === 'read' ? 'reading' : group} .inner-page`).forEach(p => p.classList.remove('active'));
      const pageId = group === 'vocab' ? `vocab-${id}` : group === 'listen' ? `listen-${id}` : `read-${id}`;
      const el = document.getElementById(pageId);
      if (el) el.classList.add('active');
      event.currentTarget.closest('.card, main > .page').querySelectorAll('.inner-tab').forEach(t => t.classList.remove('active'));
      event.currentTarget.classList.add('active');
    }

    // ========================
    // HOME
    // ========================
    function renderHomeStats() {
      const totalTopics = LEVELS.reduce((s, l) => s + l.topics.length, 0);
      const done = Object.keys(state.completedTopics).length;
      document.getElementById('home-xp').textContent = state.xp;
      document.getElementById('home-streak').textContent = state.streak + '🔥';
      document.getElementById('home-done').textContent = Math.round(done / totalTopics * 100) + '%';
      renderLevelGrid();
    }

    function renderLevelGrid() {
      const g = document.getElementById('levelGrid');
      g.innerHTML = LEVELS.map(l => {
        const done = l.topics.filter(t => state.completedTopics[t]).length;
        const pct = Math.round(done / l.topics.length * 100);
        return `<div class="level-card" onclick="openLevel('${l.id}')">
      <div class="icon">${l.icon}</div>
      <h3>${l.name}</h3>
      <p style="color:var(--text2);font-size:.82rem;">${done}/${l.topics.length} ${t('stat_done')}</p>
      <div class="prog"><div class="prog-bar" style="width:${pct}%;background:${l.color}"></div></div>
    </div>`;
      }).join('');
    }

    function openLevel(id) {
      currentLevel = LEVELS.find(l => l.id === id);
      document.getElementById('lessonLevelTitle').textContent = currentLevel.name + ' – Topics';
      const list = document.getElementById('topicList');
      list.innerHTML = currentLevel.topics.map(tid => {
        const td = getTopicData(tid);
        const done = state.completedTopics[tid];
        const score = state.testScores[tid];
        return `<div class="topic-item" onclick="openTopic('${tid}')">
      <div class="left">
        <div class="topic-icon">${td.icon}</div>
        <div>
          <div class="topic-name">${td.name}</div>
          <div class="topic-desc">${done ? 'Score: ' + score + '%' : 'Not completed yet'}</div>
        </div>
      </div>
      ${done ? `<span class="badge done">✓ ${score}%</span>` : '<span class="badge">Start</span>'}
    </div>`;
      }).join('');
      document.getElementById('lessonMain').classList.remove('hidden');
      document.getElementById('lessonView').classList.add('hidden');
      document.getElementById('testView').classList.add('hidden');
      showPage('lessons');
    }

    function openTopic(tid) {
      currentTopicId = tid;
      const td = getTopicData(tid);
      document.getElementById('lessonTitle').textContent = td.icon + ' ' + td.name;
      document.getElementById('lessonContent').innerHTML = td.lesson;
      document.getElementById('lessonMain').classList.add('hidden');
      document.getElementById('lessonView').classList.remove('hidden');
      document.getElementById('testView').classList.add('hidden');
    }

    function backToTopics() {
      document.getElementById('lessonMain').classList.remove('hidden');
      document.getElementById('lessonView').classList.add('hidden');
      document.getElementById('testView').classList.add('hidden');
    }

    function backToLesson() {
      document.getElementById('lessonView').classList.remove('hidden');
      document.getElementById('testView').classList.add('hidden');
    }

    // ========================
    // TEST ENGINE
    // ========================
    function shuffleArray(arr) {
      const a = [...arr];
      for (let i = a.length - 1; i > 0; i--) { const j = Math.floor(Math.random() * (i + 1));[a[i], a[j]] = [a[j], a[i]]; }
      return a;
    }

    function startTest() {
      const td = getTopicData(currentTopicId);
      const key = currentTopicId;
      if (!usedQIndices[key]) usedQIndices[key] = [];

      let pool = td.questions;
      let available = pool.filter((_, i) => !usedQIndices[key].includes(i));

      // If less than 30 available, reset used
      if (available.length < 30) {
        usedQIndices[key] = [];
        available = pool;
      }

      // Shuffle and pick 30
      const shuffled = shuffleArray(available.map((_, i) => i).filter(i => !usedQIndices[key].includes(i)));
      const picked = shuffled.slice(0, 30);
      picked.forEach(i => usedQIndices[key].push(i));

      // If pool < 30, generate extra shuffled variants
      testQuestions = picked.map(i => ({ ...pool[i] }));

      // Ensure we have 30 questions
      while (testQuestions.length < 30) {
        const extra = shuffleArray(pool)[0];
        // Shuffle options for variety
        testQuestions.push({ ...extra });
      }

      // Shuffle options for each question
      testQuestions = testQuestions.map(q => {
        const opts = q.opts.map((o, i) => ({ o, i }));
        const shuffledOpts = shuffleArray(opts);
        const newCorrect = shuffledOpts.findIndex(x => x.i === q.a);
        return { q: q.q, opts: shuffledOpts.map(x => x.o), a: newCorrect };
      });

      testIndex = 0;
      testScore = 0;
      renderTestQuestion();
      document.getElementById('lessonView').classList.add('hidden');
      document.getElementById('testView').classList.remove('hidden');
    }

    function renderTestQuestion() {
      const tc = document.getElementById('testContent');
      if (testIndex >= testQuestions.length) {
        showTestResult();
        return;
      }
      const q = testQuestions[testIndex];
      const pct = (testIndex / testQuestions.length * 100).toFixed(0);
      tc.innerHTML = `
    <div style="display:flex;justify-content:space-between;margin-bottom:8px;">
      <span style="color:var(--text2);font-size:.9rem;">${t('q_label')} ${testIndex + 1} ${t('of_label')} ${testQuestions.length}</span>
      <span style="color:var(--accent4);font-weight:700;">✓ ${testScore}</span>
    </div>
    <div class="prog-bar-test"><div class="prog-bar-fill" id="testProg" style="width:${pct}%"></div></div>
    <div class="question-block">
      <div class="q-text">${q.q}</div>
      <div class="options">
        ${q.opts.map((o, i) => `<button class="opt-btn" id="opt${i}" onclick="selectAnswer(${i})">${o}</button>`).join('')}
      </div>
    </div>
  `;
      testAnswered = false;
    }

    function selectAnswer(idx) {
      if (testAnswered) return;
      testAnswered = true;
      const q = testQuestions[testIndex];
      const btns = document.querySelectorAll('.opt-btn');
      btns.forEach((b, i) => {
        b.disabled = true;
        if (i === q.a) b.classList.add('correct');
        else if (i === idx) b.classList.add('wrong');
      });
      if (idx === q.a) { testScore++; }
      setTimeout(() => { testIndex++; renderTestQuestion(); }, 1000);
    }

    function showTestResult() {
      const pct = Math.round(testScore / testQuestions.length * 100);
      state.completedTopics[currentTopicId] = true;
      state.testScores[currentTopicId] = pct;
      state.xp += pct;

      // Update leaderboard
      const me = LEADERBOARD.find(l => l.name === 'You');
      if (me) me.xp = state.xp;

      let msg = pct >= 80 ? t('great') : pct >= 60 ? t('good') : pct >= 40 ? t('ok') : t('weak');
      let emoji = pct >= 80 ? '🌟' : pct >= 60 ? '👍' : pct >= 40 ? '💪' : '📖';

      document.getElementById('testContent').innerHTML = `
    <div class="result-box">
      <div class="emoji-big">${emoji}</div>
      <h2>${t('score_label')}</h2>
      <div class="result-score">${pct}%</div>
      <div class="result-msg">${testScore}/${testQuestions.length} correct – ${msg}</div>
      <div style="background:var(--bg3);border-radius:8px;height:12px;overflow:hidden;margin:16px 0;max-width:300px;margin-left:auto;margin-right:auto;">
        <div style="height:100%;width:${pct}%;background:linear-gradient(90deg,${pct >= 60 ? 'var(--success)' : 'var(--danger)'},var(--accent));transition:.8s;border-radius:8px;"></div>
      </div>
      <div style="display:flex;gap:12px;justify-content:center;">
        <button class="btn" onclick="startTest()">${t('retry_btn')}</button>
        <button class="btn outline" onclick="backToTopics()">${t('next_topic_btn')}</button>
      </div>
      <p style="color:var(--accent4);margin-top:16px;font-weight:700;">+${pct} XP earned! 🎉</p>
    </div>
  `;
      renderHomeStats();
    }

    // ========================
    // VOCABULARY
    // ========================
    function renderVocab() {
      const all = document.getElementById('vocabGrid');
      const nouns = document.getElementById('vocabNouns');
      const verbs = document.getElementById('vocabVerbs');
      const adj = document.getElementById('vocabAdj');
      const adv = document.getElementById('vocabAdv');
      const phrases = document.getElementById('vocabPhrases');
      const idioms = document.getElementById('vocabIdioms');

      const makeCard = w => `<div class="vocab-card">
    <div class="vocab-word">${w.w}</div>
    <div class="vocab-pos">${w.pos}</div>
    <div class="vocab-tr">${w.tr}</div>
    <div class="vocab-ex">${w.ex}</div>
  </div>`;

      all.innerHTML = VOCAB.map(makeCard).join('');
      nouns.innerHTML = VOCAB.filter(w => w.cat === 'nouns').map(makeCard).join('');
      verbs.innerHTML = VOCAB.filter(w => w.cat === 'verbs').map(makeCard).join('');
      adj.innerHTML = VOCAB.filter(w => w.cat === 'adj').map(makeCard).join('');
      adv.innerHTML = VOCAB.filter(w => w.cat === 'adv').map(makeCard).join('');
      phrases.innerHTML = VOCAB.filter(w => w.cat === 'phrases').map(makeCard).join('');
      idioms.innerHTML = VOCAB.filter(w => w.cat === 'idioms').map(makeCard).join('');
    }

    function filterVocab() {
      const q = document.getElementById('vocabSearch').value.toLowerCase();
      const cards = document.querySelectorAll('#vocabGrid .vocab-card');
      cards.forEach(c => {
        const text = c.textContent.toLowerCase();
        c.style.display = text.includes(q) ? 'block' : 'none';
      });
    }

    // ========================
    // LISTENING
    // ========================
    function renderListening() {
      ['beginner', 'intermediate', 'advanced'].forEach(level => {
        const container = document.getElementById('listen-' + level);
        const items = LISTENING[level] || [];
        container.innerHTML = items.map((item, idx) => `
      <div class="card audio-player">
        <div class="audio-title">🎧 ${item.title}</div>
        <div class="audio-controls">
          <button class="play-btn" id="playbtn-${level}-${idx}" onclick="toggleAudio('${level}',${idx})">▶</button>
          <div class="audio-progress" onclick="seekAudio('${level}',${idx},event)">
            <div class="audio-prog-fill" id="prog-${level}-${idx}" style="width:0%"></div>
          </div>
          <span class="audio-time" id="time-${level}-${idx}">0:00</span>
        </div>
        <div class="transcript-box" id="transcript-${level}-${idx}">${item.text}</div>
        <div style="margin-top:16px;">
          <div class="question-block">
            <div class="q-text">❓ ${item.q}</div>
            <div class="options">
              ${item.opts.map((o, i) => `<button class="opt-btn" id="lopt-${level}-${idx}-${i}" onclick="checkListeningAns('${level}',${idx},${i})">${o}</button>`).join('')}
            </div>
          </div>
        </div>
      </div>
    `).join('') || '<p style="color:var(--text2);text-align:center;padding:20px;">More content coming soon!</p>';
      });
    }

    const audioStates = {};

    function toggleAudio(level, idx) {
      const key = `${level}-${idx}`;
      const btn = document.getElementById(`playbtn-${key}`);
      const item = LISTENING[level][idx];

      if (!audioStates[key]) {
        audioStates[key] = { playing: false, progress: 0, maxDur: item.text.length / 10 + 20 };
      }

      const as = audioStates[key];

      if (as.playing) {
        as.playing = false;
        btn.textContent = '▶';
        clearInterval(as.interval);
        // Also stop TTS if speaking
        if (window.speechSynthesis) window.speechSynthesis.pause();
      } else {
        // Stop all others
        Object.keys(audioStates).forEach(k => {
          if (k !== key && audioStates[k].playing) {
            audioStates[k].playing = false;
            document.getElementById('playbtn-' + k).textContent = '▶';
            clearInterval(audioStates[k].interval);
          }
        });

        as.playing = true;
        btn.textContent = '⏸';

        // Use Web Speech API for TTS
        if (window.speechSynthesis) {
          const utt = new SpeechSynthesisUtterance(item.text);
          utt.rate = 0.85;
          utt.pitch = 1;
          utt.lang = 'en-US';
          utt.onend = () => {
            as.playing = false; btn.textContent = '▶';
            document.getElementById(`prog-${key}`).style.width = '100%';
            clearInterval(as.interval);
          };
          window.speechSynthesis.cancel();
          window.speechSynthesis.speak(utt);
          as.utterance = utt;
        }

        const dur = as.maxDur;
        as.interval = setInterval(() => {
          if (!as.playing) { clearInterval(as.interval); return; }
          as.progress = Math.min(as.progress + (100 / dur / 10), 100);
          document.getElementById(`prog-${key}`).style.width = as.progress + '%';
          const secs = Math.floor(as.progress / 100 * dur);
          document.getElementById(`time-${key}`).textContent =
            Math.floor(secs / 60) + ':' + (secs % 60 < 10 ? '0' : '') + secs % 60;
          if (as.progress >= 100) {
            as.playing = false; btn.textContent = '▶';
            clearInterval(as.interval);
          }
        }, 100);
      }
    }

    function seekAudio(level, idx, e) {
      const key = `${level}-${idx}`;
      if (!audioStates[key]) return;
      const bar = e.currentTarget;
      const pct = e.offsetX / bar.offsetWidth * 100;
      audioStates[key].progress = pct;
      document.getElementById(`prog-${key}`).style.width = pct + '%';
    }

    function checkListeningAns(level, idx, ansIdx) {
      const item = LISTENING[level][idx];
      const btns = document.querySelectorAll(`[id^="lopt-${level}-${idx}-"]`);
      btns.forEach((b, i) => {
        b.disabled = true;
        if (i === item.a) b.classList.add('correct');
        else if (i === ansIdx) b.classList.add('wrong');
      });
      if (ansIdx === item.a) { state.xp += 10; }
    }

    // ========================
    // SPEAKING
    // ========================
    function renderSpeakScenario() {
      const s = SPEAK_SCENARIOS[speakIdx % SPEAK_SCENARIOS.length];
      document.getElementById('speakScenario').innerHTML = `
    <div style="background:var(--bg3);border-radius:8px;padding:10px 14px;margin-bottom:12px;border-left:4px solid var(--accent4);">
      <span style="color:var(--accent4);font-weight:700;">📍 Context:</span> <span style="color:var(--text2);">${s.context}</span>
    </div>`;
      document.getElementById('speakDialog').innerHTML = `
    <div class="speak-bubble ai">
      <div class="speak-who">🤖 AI</div>
      <div class="speak-text">${s.ai}</div>
    </div>`;
      document.getElementById('speakFeedback').style.display = 'none';
      // Auto-speak the AI message
      setTimeout(() => speakText(s.ai), 300);
    }

    function speakText(text) {
      if (window.speechSynthesis) {
        window.speechSynthesis.cancel();
        const u = new SpeechSynthesisUtterance(text);
        u.lang = 'en-US'; u.rate = 0.9;
        window.speechSynthesis.speak(u);
      }
    }

    function repeatAI() {
      const s = SPEAK_SCENARIOS[speakIdx % SPEAK_SCENARIOS.length];
      speakText(s.ai);
    }

    function nextSpeakScenario() {
      speakIdx++;
      renderSpeakScenario();
    }

    function toggleMic() {
      const btn = document.getElementById('micBtn');
      const status = document.getElementById('micStatus');

      if (!isRecording) {
        isRecording = true;
        btn.classList.add('recording');
        status.textContent = '🔴 Recording... Speak now!';

        if ('webkitSpeechRecognition' in window || 'SpeechRecognition' in window) {
          const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
          const recognition = new SR();
          recognition.lang = 'en-US';
          recognition.continuous = false;
          recognition.interimResults = false;
          recognition.onresult = e => {
            const transcript = e.results[0][0].transcript;
            showSpeakingResult(transcript);
          };
          recognition.onerror = () => {
            showSpeakingResult("Sorry, I couldn't hear you. Please try again.");
          };
          recognition.onend = () => {
            isRecording = false;
            btn.classList.remove('recording');
            status.textContent = t('speak_press');
          };
          recognition.start();
        } else {
          // Fallback – simulate after 2s
          setTimeout(() => {
            isRecording = false;
            btn.classList.remove('recording');
            status.textContent = t('speak_press');
            showSpeakingResult("Hello! My name is Alex. Nice to meet you!");
          }, 2000);
        }
      }
    }

    function showSpeakingResult(transcript) {
      const dialog = document.getElementById('speakDialog');
      dialog.innerHTML += `<div class="speak-bubble user">
    <div class="speak-who">👤 You</div>
    <div class="speak-text">${transcript}</div>
  </div>`;

      const s = SPEAK_SCENARIOS[speakIdx % SPEAK_SCENARIOS.length];
      const score = s.expected.split(',').filter(k => transcript.toLowerCase().includes(k.trim())).length;
      const maxScore = s.expected.split(',').length;
      const pct = Math.round(score / maxScore * 100);

      const fb = document.getElementById('speakFeedback');
      fb.style.display = 'block';
      fb.innerHTML = `<div class="card" style="background:var(--bg3);">
    <div style="font-weight:800;margin-bottom:8px;">🤖 AI Feedback</div>
    <div style="color:${pct >= 60 ? 'var(--success)' : 'var(--accent4)'}">
      ${pct >= 80 ? 'Excellent response! 🌟' : pct >= 60 ? 'Good attempt! 👍' : 'Try to include more key words. 💪'}
    </div>
    <div style="color:var(--text2);font-size:.88rem;margin-top:8px;">
      Key words used: ${score}/${maxScore} | Score: ${pct}%
    </div>
    <div style="margin-top:10px;">
      <button class="btn" onclick="aiSpeakResponse('${transcript.replace(/'/g, "\\'")}')">Get AI full response</button>
    </div>
  </div>`;
      state.xp += pct / 10 | 0;
    }

    async function aiSpeakResponse(userText) {
      const s = SPEAK_SCENARIOS[speakIdx % SPEAK_SCENARIOS.length];
      const fb = document.getElementById('speakFeedback');
      fb.innerHTML += '<div class="spinner"></div>';

      try {
        const response = await fetch("https://api.anthropic.com/v1/messages", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            model: "claude-sonnet-4-20250514",
            max_tokens: 300,
            messages: [{ role: "user", content: `You are an English speaking tutor. The scenario is: "${s.context}". The AI said: "${s.ai}". The student responded: "${userText}". Give brief, encouraging feedback on their English speaking (grammar, vocabulary, naturalness) and provide a model answer. Keep it under 100 words.` }]
          })
        });
        const data = await response.json();
        const text = data.content[0].text;
        fb.querySelector('.spinner')?.remove();
        fb.innerHTML += `<div class="speak-bubble ai" style="margin-top:10px;"><div class="speak-who">🤖 AI Tutor</div><div class="speak-text">${text}</div></div>`;
        speakText(text);
      } catch (e) {
        fb.querySelector('.spinner')?.remove();
      }
    }

    // ========================
    // READING
    // ========================
    function renderReading() {
      ['beginner', 'intermediate', 'advanced'].forEach(level => {
        const container = document.getElementById('read-' + level);
        const items = READING[level] || [];
        container.innerHTML = items.map((item, idx) => `
      <div class="card">
        <h3>📝 ${item.title}</h3>
        <div class="reading-text">${item.text}</div>
        ${item.q.map((qa, qi) => `
          <div class="question-block">
            <div class="q-text">Q${qi + 1}: ${qa.q}</div>
            <div class="options">
              ${qa.opts.map((o, i) => `<button class="opt-btn" id="ropt-${level}-${idx}-${qi}-${i}" onclick="checkReadingAns('${level}',${idx},${qi},${i})">${o}</button>`).join('')}
            </div>
          </div>
        `).join('')}
      </div>
    `).join('') || '<p style="color:var(--text2);text-align:center;padding:20px;">More content coming soon!</p>';
      });
    }

    function checkReadingAns(level, idx, qi, ansIdx) {
      const item = READING[level][idx];
      const qa = item.q[qi];
      const btns = document.querySelectorAll(`[id^="ropt-${level}-${idx}-${qi}-"]`);
      btns.forEach((b, i) => {
        b.disabled = true;
        if (i === qa.a) b.classList.add('correct');
        else if (i === ansIdx) b.classList.add('wrong');
      });
      if (ansIdx === qa.a) { state.xp += 5; }
    }

    // ========================
    // WRITING
    // ========================
    function newWritingPrompt() {
      writingPromptIdx = Math.floor(Math.random() * WRITING_PROMPTS.length);
      document.getElementById('writingPrompt').innerHTML = `
    <div style="background:var(--bg3);border-radius:8px;padding:14px;margin-bottom:14px;border-left:4px solid var(--accent2);">
      <span style="color:var(--accent2);font-weight:700;">✍️ Prompt:</span>
      <p style="margin-top:6px;color:var(--text);">${WRITING_PROMPTS[writingPromptIdx]}</p>
    </div>`;
      document.getElementById('writingArea').value = '';
      document.getElementById('writingFeedback').innerHTML = '';
    }

    async function checkWriting() {
      const text = document.getElementById('writingArea').value.trim();
      if (!text) { alert('Please write something first!'); return; }
      const fb = document.getElementById('writingFeedback');
      fb.innerHTML = '<div class="spinner"></div>';

      try {
        const response = await fetch("https://api.anthropic.com/v1/messages", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            model: "claude-sonnet-4-20250514",
            max_tokens: 500,
            messages: [{ role: "user", content: `You are an English writing teacher. The student was asked: "${WRITING_PROMPTS[writingPromptIdx]}". Their response: "${text}". Provide feedback on: 1) Grammar (score /10), 2) Vocabulary (score /10), 3) Coherence (score /10), 4) Overall score (/30). Give specific corrections and suggestions. Be encouraging but honest. Format clearly.` }]
          })
        });
        const data = await response.json();
        const result = data.content[0].text;
        fb.innerHTML = `<div class="card" style="background:var(--bg3);">
      <h3>🤖 AI Writing Feedback</h3>
      <div style="color:var(--text2);line-height:1.8;white-space:pre-wrap;">${result}</div>
    </div>`;
      } catch (e) {
        fb.innerHTML = '<p style="color:var(--danger);">Error connecting to AI. Please try again.</p>';
      }
    }

    // ========================
    // AI TUTOR CHAT
    // ========================
    function clearChat() {
      chatHistory = [];
      document.getElementById('chatArea').innerHTML = '';
      addAIMsg("Hello! I'm your AI English tutor. I'm here 24/7 to help you with grammar, vocabulary, pronunciation, and any questions about the English language. What would you like to learn today?");
    }

    function addAIMsg(text) {
      const area = document.getElementById('chatArea');
      const div = document.createElement('div');
      div.className = 'msg ai';
      div.innerHTML = text.replace(/\n/g, '<br>');
      area.appendChild(div);
      area.scrollTop = area.scrollHeight;
    }

    function addUserMsg(text) {
      const area = document.getElementById('chatArea');
      const div = document.createElement('div');
      div.className = 'msg user';
      div.textContent = text;
      area.appendChild(div);
      area.scrollTop = area.scrollHeight;
    }

    function addTyping() {
      const area = document.getElementById('chatArea');
      const div = document.createElement('div');
      div.className = 'msg ai typing';
      div.id = 'typingIndicator';
      div.innerHTML = '<span>●</span><span style="animation-delay:.2s">●</span><span style="animation-delay:.4s">●</span>';
      area.appendChild(div);
      area.scrollTop = area.scrollHeight;
    }

    function quickAsk(q) {
      document.getElementById('chatInput').value = q;
      sendChat();
    }

    async function sendChat() {
      const input = document.getElementById('chatInput');
      const msg = input.value.trim();
      if (!msg) return;
      input.value = '';

      addUserMsg(msg);
      chatHistory.push({ role: "user", content: msg });
      addTyping();

      try {
        const response = await fetch("https://api.anthropic.com/v1/messages", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            model: "claude-sonnet-4-20250514",
            max_tokens: 600,
            system: `You are an expert, friendly English language tutor named Alex. You teach English grammar, vocabulary, pronunciation, idioms, and all aspects of the English language. Always give clear, accurate explanations with examples. Use simple formatting. Current interface language: ${currentLang}. If the student writes in Russian/Uzbek/Tajik, respond in both that language AND English for better learning. Always be encouraging and helpful.`,
            messages: chatHistory
          })
        });
        const data = await response.json();
        const text = data.content[0].text;
        document.getElementById('typingIndicator')?.remove();
        chatHistory.push({ role: "assistant", content: text });
        addAIMsg(text);
      } catch (e) {
        document.getElementById('typingIndicator')?.remove();
        addAIMsg("Sorry, I had trouble connecting. Please check your internet and try again.");
      }
    }

    // ========================
    // LEADERBOARD
    // ========================
    function renderLeaderboard() {
      const sorted = [...LEADERBOARD].sort((a, b) => b.xp - a.xp);
      const lb = document.getElementById('leaderboardList');
      lb.innerHTML = `<h2>🏆 ${t('nav_rank')}</h2>` + sorted.map((u, i) => `
    <div class="lb-row" style="${u.name === 'You' ? 'border-color:var(--accent);background:rgba(108,99,255,.1);' : ''}">
      <div class="lb-rank ${i === 0 ? 'g' : i === 1 ? 's' : i === 2 ? 'b' : ''}">${i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : i + 1}</div>
      <div style="font-size:1.2rem;">${u.flag}</div>
      <div class="lb-name">${u.name}${u.name === 'You' ? ' (You)' : ''}</div>
      <div class="lb-xp">${u.xp.toLocaleString()} XP</div>
      <div><span class="lb-badge">${u.badge}</span></div>
      <div style="color:var(--accent4);font-size:.85rem;">🔥${u.streak}</div>
    </div>
  `).join('');
    }

    // ========================
    // STATS
    // ========================
    function renderStats() {
      const totalTopics = LEVELS.reduce((s, l) => s + l.topics.length, 0);
      const done = Object.keys(state.completedTopics).length;
      const scores = Object.values(state.testScores);
      const avg = scores.length ? Math.round(scores.reduce((a, b) => a + b, 0) / scores.length) : 0;

      document.getElementById('statsGrid').innerHTML = `
    <div class="stat-card"><div class="stat-num">${state.xp}</div><div class="stat-label">${t('stat_xp')}</div></div>
    <div class="stat-card"><div class="stat-num">${state.streak}🔥</div><div class="stat-label">${t('stat_streak')}</div></div>
    <div class="stat-card"><div class="stat-num">${done}</div><div class="stat-label">Topics Done</div></div>
    <div class="stat-card"><div class="stat-num">${avg}%</div><div class="stat-label">Avg Score</div></div>
    <div class="stat-card"><div class="stat-num">${totalTopics}</div><div class="stat-label">Total Topics</div></div>
    <div class="stat-card"><div class="stat-num">${scores.filter(s => s >= 80).length}</div><div class="stat-label">Excellent Tests</div></div>
  `;

      document.getElementById('progressBars').innerHTML = LEVELS.map(l => {
        const done = l.topics.filter(t => state.completedTopics[t]).length;
        const pct = Math.round(done / l.topics.length * 100);
        return `<div style="margin-bottom:12px;">
      <div style="display:flex;justify-content:space-between;margin-bottom:4px;">
        <span>${l.icon} ${l.name}</span>
        <span style="color:var(--accent4);">${pct}%</span>
      </div>
      <div style="background:var(--bg3);border-radius:6px;height:8px;overflow:hidden;">
        <div style="width:${pct}%;height:100%;background:${l.color};border-radius:6px;transition:.5s;"></div>
      </div>
    </div>`;
      }).join('');

      const scoresHtml = Object.entries(state.testScores).map(([k, v]) => {
        const td = getTopicData(k);
        return `<div style="display:flex;align-items:center;gap:10px;margin-bottom:8px;">
      <span>${td.icon}</span>
      <span style="flex:1;">${td.name}</span>
      <div style="width:120px;background:var(--bg3);border-radius:4px;height:6px;overflow:hidden;">
        <div style="width:${v}%;height:100%;background:${v >= 80 ? 'var(--success)' : v >= 60 ? 'var(--accent4)' : 'var(--danger)'};border-radius:4px;"></div>
      </div>
      <span style="color:${v >= 80 ? 'var(--success)' : v >= 60 ? 'var(--accent4)' : 'var(--danger)'};font-weight:700;width:40px;text-align:right;">${v}%</span>
    </div>`;
      }).join('') || '<p style="color:var(--text2);">Complete some tests to see scores here!</p>';

      document.getElementById('topicScores').innerHTML = scoresHtml;
    }

    // ========================
    // INIT
    // ========================
    function init() {
      renderLevelGrid();
      renderVocab();
      renderListening();
      renderReading();
      renderLeaderboard();
      renderStats();
      renderHomeStats();
      clearChat();
      newWritingPrompt();
      renderSpeakScenario();
    }

    init();
  </script>
</body>

</html>
