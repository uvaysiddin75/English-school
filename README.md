
<html lang="en" class="h-full">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SpeakUP English</title>
  <link
    href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap"
    rel="stylesheet">
  <style>
    :root {
      --primary: #4f46e5;
      --primary-light: #818cf8;
      --primary-dark: #3730a3;
      --accent: #f59e0b;
      --accent2: #10b981;
      --danger: #ef4444;
      --bg: #0f0f1a;
      --bg2: #161628;
      --bg3: #1e1e38;
      --surface: #252545;
      --surface2: #2e2e55;
      --border: rgba(255, 255, 255, 0.08);
      --text: #f0f0ff;
      --text2: #a0a0c0;
      --text3: #6060a0;
      --radius: 16px;
      --radius-sm: 10px;
      --glow: 0 0 20px rgba(79, 70, 229, 0.3);
    }

    *,
    *::before,
    *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html,
    body {
      height: 100%;
      overflow: hidden;
      font-family: 'Sora', sans-serif;
      background: var(--bg);
      color: var(--text);
    }

    /* SCROLLBAR */
    ::-webkit-scrollbar {
      width: 5px;
    }

    ::-webkit-scrollbar-track {
      background: transparent;
    }

    ::-webkit-scrollbar-thumb {
      background: var(--surface2);
      border-radius: 99px;
    }

    /* LAYOUT */
    #app {
      height: 100vh;
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }

    /* HEADER */
    header {
      background: var(--bg2);
      border-bottom: 1px solid var(--border);
      padding: 12px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-shrink: 0;
      position: relative;
      z-index: 10;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-icon {
      width: 36px;
      height: 36px;
      background: linear-gradient(135deg, var(--primary), var(--primary-light));
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      box-shadow: var(--glow);
    }

    .logo-text {
      font-size: 18px;
      font-weight: 800;
      letter-spacing: -0.5px;
      background: linear-gradient(135deg, #fff 30%, var(--primary-light));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .logo-text span {
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .header-right {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .xp-badge {
      display: flex;
      align-items: center;
      gap: 5px;
      background: rgba(245, 158, 11, 0.15);
      border: 1px solid rgba(245, 158, 11, 0.3);
      border-radius: 99px;
      padding: 5px 12px;
      font-size: 13px;
      font-weight: 700;
      color: var(--accent);
    }

    .streak-badge {
      display: flex;
      align-items: center;
      gap: 5px;
      background: rgba(239, 68, 68, 0.12);
      border: 1px solid rgba(239, 68, 68, 0.25);
      border-radius: 99px;
      padding: 5px 10px;
      font-size: 13px;
      font-weight: 700;
      color: #fc8181;
    }

    select.lang-sel {
      background: var(--surface);
      color: var(--text);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 6px 10px;
      font-size: 12px;
      font-family: 'Sora', sans-serif;
      cursor: pointer;
      outline: none;
    }

    /* NAV */
    nav {
      background: var(--bg2);
      border-bottom: 1px solid var(--border);
      display: flex;
      gap: 4px;
      padding: 8px 12px;
      overflow-x: auto;
      flex-shrink: 0;
    }

    nav::-webkit-scrollbar {
      height: 0;
    }

    .nav-btn {
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 7px 14px;
      border-radius: var(--radius-sm);
      border: none;
      background: transparent;
      color: var(--text2);
      font-family: 'Sora', sans-serif;
      font-size: 12px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s;
      white-space: nowrap;
    }

    .nav-btn:hover {
      background: var(--surface);
      color: var(--text);
    }

    .nav-btn.active {
      background: var(--primary);
      color: #fff;
      box-shadow: var(--glow);
    }

    .nav-btn .nav-icon {
      font-size: 14px;
    }

    /* MAIN */
    main {
      flex: 1;
      overflow-y: auto;
      padding: 20px;
    }

    /* CARDS */
    .card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 20px;
      transition: all 0.2s;
    }

    .card:hover {
      border-color: rgba(79, 70, 229, 0.3);
    }

    .card-sm {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 14px 16px;
      cursor: pointer;
      transition: all 0.2s;
    }

    .card-sm:hover {
      background: var(--surface2);
      border-color: rgba(79, 70, 229, 0.4);
      transform: translateY(-1px);
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
    }

    /* GRID */
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
    }

    @media (max-width: 600px) {

      .grid-2,
      .grid-3 {
        grid-template-columns: 1fr;
      }
    }

    /* SECTION TITLE */
    .section-title {
      font-size: 22px;
      font-weight: 800;
      margin-bottom: 6px;
      letter-spacing: -0.5px;
    }

    .section-sub {
      color: var(--text2);
      font-size: 13px;
      margin-bottom: 20px;
    }

    /* PILL BADGE */
    .pill {
      display: inline-flex;
      align-items: center;
      gap: 4px;
      padding: 3px 10px;
      border-radius: 99px;
      font-size: 11px;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .pill-purple {
      background: rgba(79, 70, 229, 0.2);
      color: var(--primary-light);
    }

    .pill-green {
      background: rgba(16, 185, 129, 0.2);
      color: #34d399;
    }

    .pill-amber {
      background: rgba(245, 158, 11, 0.2);
      color: var(--accent);
    }

    .pill-red {
      background: rgba(239, 68, 68, 0.2);
      color: #fc8181;
    }

    /* BUTTONS */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      padding: 10px 20px;
      border-radius: var(--radius-sm);
      border: none;
      font-family: 'Sora', sans-serif;
      font-weight: 700;
      font-size: 14px;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn-primary {
      background: var(--primary);
      color: #fff;
      box-shadow: var(--glow);
    }

    .btn-primary:hover {
      background: var(--primary-dark);
      transform: translateY(-1px);
    }

    .btn-outline {
      background: transparent;
      color: var(--text2);
      border: 1px solid var(--border);
    }

    .btn-outline:hover {
      background: var(--surface);
      color: var(--text);
    }

    .btn-accent {
      background: var(--accent);
      color: #1a1000;
    }

    .btn-accent:hover {
      filter: brightness(1.1);
    }

    .btn-success {
      background: var(--accent2);
      color: #fff;
    }

    .btn-danger {
      background: var(--danger);
      color: #fff;
    }

    .btn:disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }

    /* QUIZ OPTIONS */
    .quiz-opt {
      width: 100%;
      text-align: left;
      padding: 14px 18px;
      background: var(--surface);
      border: 1.5px solid var(--border);
      border-radius: var(--radius-sm);
      color: var(--text);
      font-family: 'Sora', sans-serif;
      font-size: 14px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.15s;
      margin-bottom: 8px;
    }

    .quiz-opt:hover:not(.disabled) {
      background: var(--surface2);
      border-color: var(--primary-light);
      transform: translateX(4px);
    }

    .quiz-opt.correct {
      background: rgba(16, 185, 129, 0.2) !important;
      border-color: var(--accent2) !important;
      color: #34d399 !important;
    }

    .quiz-opt.wrong {
      background: rgba(239, 68, 68, 0.15) !important;
      border-color: var(--danger) !important;
      color: #fc8181 !important;
    }

    .quiz-opt.disabled {
      pointer-events: none;
    }

    /* PROGRESS */
    .progress-track {
      height: 6px;
      background: var(--surface);
      border-radius: 99px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--primary), var(--primary-light));
      border-radius: 99px;
      transition: width 0.5s ease;
    }

    /* CHAT */
    .chat-wrap {
      display: flex;
      flex-direction: column;
      height: calc(100vh - 160px);
    }

    .chat-msgs {
      flex: 1;
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      gap: 12px;
      padding-bottom: 12px;
    }

    .chat-msg-ai,
    .chat-msg-user {
      max-width: 80%;
      padding: 12px 16px;
      border-radius: 14px;
      font-size: 14px;
      line-height: 1.6;
      animation: msgIn 0.3s ease;
    }

    .chat-msg-ai {
      background: var(--surface);
      border: 1px solid var(--border);
      border-bottom-left-radius: 4px;
      align-self: flex-start;
    }

    .chat-msg-user {
      background: var(--primary);
      border-bottom-right-radius: 4px;
      align-self: flex-end;
    }

    .chat-input-row {
      display: flex;
      gap: 8px;
      margin-top: 12px;
    }

    .chat-input {
      flex: 1;
      background: var(--surface);
      border: 1.5px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 12px 16px;
      color: var(--text);
      font-family: 'Sora', sans-serif;
      font-size: 14px;
      outline: none;
      transition: border-color 0.2s;
    }

    .chat-input:focus {
      border-color: var(--primary);
    }

    /* VOCAB GRID */
    .vocab-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 14px;
      transition: all 0.2s;
    }

    .vocab-card:hover {
      border-color: rgba(79, 70, 229, 0.4);
      transform: translateY(-2px);
    }

    .vocab-en {
      font-size: 16px;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 4px;
    }

    .vocab-tr {
      font-size: 12px;
      color: var(--text2);
    }

    .vocab-cat {
      font-size: 10px;
      color: var(--text3);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      margin-top: 6px;
    }

    /* SCORE SCREEN */
    .score-big {
      font-size: 72px;
      font-weight: 800;
      font-family: 'Space Mono', monospace;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      line-height: 1;
    }

    /* STAT CARD */
    .stat-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 20px;
      text-align: center;
    }

    .stat-num {
      font-size: 36px;
      font-weight: 800;
      font-family: 'Space Mono', monospace;
      color: var(--primary-light);
    }

    .stat-label {
      font-size: 12px;
      color: var(--text2);
      margin-top: 4px;
    }

    /* LOADING DOT */
    .typing-dot {
      display: inline-block;
      width: 6px;
      height: 6px;
      background: var(--primary-light);
      border-radius: 50%;
      animation: typingBounce 1s infinite;
      margin: 0 2px;
    }

    .typing-dot:nth-child(2) {
      animation-delay: 0.2s;
    }

    .typing-dot:nth-child(3) {
      animation-delay: 0.4s;
    }

    @keyframes typingBounce {

      0%,
      80%,
      100% {
        transform: translateY(0);
      }

      40% {
        transform: translateY(-6px);
      }
    }

    /* ANIMATIONS */
    @keyframes msgIn {
      from {
        opacity: 0;
        transform: translateY(8px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(12px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .fade-in {
      animation: fadeIn 0.35s ease forwards;
    }

    /* TOPIC CARD */
    .topic-card {
      background: var(--bg2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 18px;
      cursor: pointer;
      transition: all 0.2s;
      position: relative;
      overflow: hidden;
    }

    .topic-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--primary), var(--primary-light));
      opacity: 0;
      transition: opacity 0.2s;
    }

    .topic-card:hover::before {
      opacity: 1;
    }

    .topic-card:hover {
      border-color: rgba(79, 70, 229, 0.35);
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
    }

    .topic-num {
      font-family: 'Space Mono', monospace;
      font-size: 11px;
      color: var(--text3);
      margin-bottom: 8px;
    }

    .topic-name {
      font-size: 15px;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .topic-bar {
      margin-top: 10px;
    }

    /* LEVEL CHIP */
    .level-chip {
      display: inline-block;
      padding: 2px 8px;
      border-radius: 99px;
      font-size: 10px;
      font-weight: 700;
    }

    .level-0 {
      background: rgba(16, 185, 129, 0.2);
      color: #34d399;
    }

    .level-1 {
      background: rgba(59, 130, 246, 0.2);
      color: #60a5fa;
    }

    .level-2 {
      background: rgba(245, 158, 11, 0.2);
      color: #fbbf24;
    }

    .level-3 {
      background: rgba(239, 68, 68, 0.2);
      color: #f87171;
    }

    .level-4 {
      background: rgba(168, 85, 247, 0.2);
      color: #c084fc;
    }

    /* RESULT ITEM */
    .result-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 16px;
      background: var(--surface);
      border-radius: var(--radius-sm);
      border: 1px solid var(--border);
      margin-bottom: 8px;
      font-size: 13px;
    }

    /* READING */
    .reading-text {
      background: var(--surface);
      border-left: 3px solid var(--primary);
      border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
      padding: 16px 20px;
      font-size: 14px;
      line-height: 1.8;
      color: var(--text2);
      margin-bottom: 20px;
    }

    /* EMPTY STATE */
    .empty-state {
      text-align: center;
      padding: 50px 20px;
      color: var(--text3);
    }

    .empty-state .icon {
      font-size: 48px;
      margin-bottom: 12px;
    }

    /* SEARCH INPUT */
    .search-input {
      width: 100%;
      background: var(--surface);
      border: 1.5px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 11px 16px;
      color: var(--text);
      font-family: 'Sora', sans-serif;
      font-size: 14px;
      outline: none;
      transition: border-color 0.2s;
      margin-bottom: 16px;
    }

    .search-input:focus {
      border-color: var(--primary);
    }

    /* SPEAKING CARD */
    .speak-prompt-box {
      background: linear-gradient(135deg, rgba(79, 70, 229, 0.15), rgba(129, 140, 248, 0.08));
      border: 1px solid rgba(79, 70, 229, 0.3);
      border-radius: var(--radius);
      padding: 24px;
      text-align: center;
      margin-bottom: 20px;
    }

    .speak-prompt-text {
      font-size: 20px;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .speak-hint {
      font-size: 13px;
      color: var(--text2);
    }

    /* WAVE ANIMATION */
    .wave-bars {
      display: flex;
      gap: 3px;
      justify-content: center;
      align-items: center;
      height: 30px;
    }

    .wave-bar {
      width: 4px;
      border-radius: 99px;
      background: var(--primary-light);
      animation: waveBar 0.8s ease-in-out infinite;
    }

    .wave-bar:nth-child(2) {
      animation-delay: 0.1s;
    }

    .wave-bar:nth-child(3) {
      animation-delay: 0.2s;
    }

    .wave-bar:nth-child(4) {
      animation-delay: 0.3s;
    }

    .wave-bar:nth-child(5) {
      animation-delay: 0.2s;
    }

    .wave-bar:nth-child(6) {
      animation-delay: 0.1s;
    }

    @keyframes waveBar {

      0%,
      100% {
        height: 8px;
      }

      50% {
        height: 28px;
      }
    }

    /* LEADERBOARD */
    .lb-row {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 12px 16px;
      background: var(--surface);
      border-radius: var(--radius-sm);
      border: 1px solid var(--border);
      margin-bottom: 8px;
    }

    .lb-rank {
      font-family: 'Space Mono', monospace;
      font-size: 14px;
      font-weight: 700;
      width: 28px;
      text-align: center;
    }

    .lb-name {
      flex: 1;
      font-weight: 600;
      font-size: 14px;
    }

    .lb-score {
      font-family: 'Space Mono', monospace;
      font-size: 13px;
      color: var(--primary-light);
    }
  </style>
</head>

<body>
  <div id="app">
    <header>
      <div class="logo">
        <div class="logo-icon">🗣️</div>
        <div class="logo-text">SpeakUP <span>English</span></div>
      </div>
      <div class="header-right">
        <div class="xp-badge">⚡ <span id="xpCount">0</span> XP</div>
        <div class="streak-badge">🔥 <span id="streakCount">0</span></div>
        <select class="lang-sel" id="langSel" onchange="changeLang(this.value)">
          <option value="en">🇬🇧 EN</option>
          <option value="ru">🇷🇺 RU</option>
          <option value="uz">🇺🇿 UZ</option>
          <option value="tj">🇹🇯 TJ</option>
        </select>
      </div>
    </header>
    <nav id="navBar"></nav>
    <main id="mainContent"></main>
  </div>

  <script>
    // ============================================================
    // DATA
    // ============================================================
    const LANGS = {
      en: {
        tabs: ['Lessons', 'Listening', 'Reading', 'Speaking', 'Vocabulary', 'AI Chat', 'Stats'],
        tabIcons: ['📖', '🎧', '📰', '🎤', '📚', '🤖', '📊'],
        start: 'Start Quiz', back: 'Back', next: 'Next', submit: 'Submit',
        question: 'Question', of: 'of', correct: 'Correct!', wrong: 'Wrong!',
        yourScore: 'Your Score', tryAgain: 'Try Again', listenAgain: 'Listen Again',
        play: 'Play Audio', record: 'Answer', vocabSearch: 'Search words...',
        aiPlaceholder: 'Ask me anything about English...', aiSend: 'Send',
        aiWelcome: "Hi! I'm your English learning assistant. Ask me about grammar, vocabulary, pronunciation, or anything! 🎓",
        statsTitle: 'Your Progress', noStats: 'No results yet. Complete some quizzes!',
        totalTests: 'Tests Done', avgScore: 'Avg Score', bestScore: 'Best Score',
        lessonSelect: 'Choose a topic to practice:', readingSelect: 'Choose a passage to read:',
        listenSelect: 'Choose a listening exercise:',
        speakTitle: 'Speaking Practice', speakInstr: 'Listen to the prompt, then write your answer.',
        levels: ['Beginner', 'Elementary', 'Intermediate', 'Upper-Int', 'Advanced'],
        topics: ['Present Simple', 'Past Simple', 'Future Simple', 'Present Continuous', 'Past Continuous', 'Present Perfect', 'Modal Verbs', 'Conditionals', 'Passive Voice', 'Articles', 'Comparatives', 'Prepositions', 'Reported Speech', 'Relative Clauses', 'Phrasal Verbs'],
        noResults: 'No results',
      },
      ru: {
        tabs: ['Уроки', 'Аудирование', 'Чтение', 'Говорение', 'Словарь', 'ИИ Чат', 'Статистика'],
        tabIcons: ['📖', '🎧', '📰', '🎤', '📚', '🤖', '📊'],
        start: 'Начать тест', back: 'Назад', next: 'Далее', submit: 'Отправить',
        question: 'Вопрос', of: 'из', correct: 'Правильно!', wrong: 'Неправильно!',
        yourScore: 'Ваш балл', tryAgain: 'Попробовать снова', listenAgain: 'Слушать снова',
        play: 'Воспроизвести', record: 'Ответить', vocabSearch: 'Поиск слов...',
        aiPlaceholder: 'Спросите об английском...', aiSend: 'Отправить',
        aiWelcome: 'Привет! Я ваш помощник по английскому. Спрашивайте о грамматике, словах, произношении! 🎓',
        statsTitle: 'Ваш прогресс', noStats: 'Пока нет результатов. Пройдите тесты!',
        totalTests: 'Тестов пройдено', avgScore: 'Средний балл', bestScore: 'Лучший балл',
        lessonSelect: 'Выберите тему:', readingSelect: 'Выберите текст:', listenSelect: 'Выберите упражнение:',
        speakTitle: 'Практика говорения', speakInstr: 'Прослушайте подсказку, затем напишите ответ.',
        levels: ['Начальный', 'Элементарный', 'Средний', 'Выше среднего', 'Продвинутый'],
        topics: ['Настоящее простое', 'Прошедшее простое', 'Будущее простое', 'Наст. длительное', 'Прош. длительное', 'Наст. совершённое', 'Модальные глаголы', 'Условные предложения', 'Страдательный залог', 'Артикли', 'Сравнительные степени', 'Предлоги', 'Косвенная речь', 'Придаточные', 'Фразовые глаголы'],
        noResults: 'Нет результатов',
      },
      uz: {
        tabs: ['Darslar', 'Tinglash', "O'qish", 'Gapirish', "Lug'at", 'AI Chat', 'Statistika'],
        tabIcons: ['📖', '🎧', '📰', '🎤', '📚', '🤖', '📊'],
        start: 'Testni boshlash', back: 'Orqaga', next: 'Keyingi', submit: 'Yuborish',
        question: 'Savol', of: 'dan', correct: "To'g'ri!", wrong: "Noto'g'ri!",
        yourScore: 'Natijangiz', tryAgain: 'Qayta urinish', listenAgain: 'Qayta tinglash',
        play: 'Ijro', record: 'Javob berish', vocabSearch: "So'z qidirish...",
        aiPlaceholder: 'Ingliz tili haqida so\'rang...', aiSend: 'Yuborish',
        aiWelcome: "Salom! Men ingliz tili bo'yicha yordamchingizman. Grammatika, so'zlar haqida so'rang! 🎓",
        statsTitle: 'Sizning taraqqiyotingiz', noStats: "Hali natijalar yo'q. Testlarni bajaring!",
        totalTests: 'Testlar soni', avgScore: 'O\'rtacha ball', bestScore: 'Eng yaxshi ball',
        lessonSelect: 'Mavzuni tanlang:', readingSelect: 'Matnni tanlang:', listenSelect: "Mashqni tanlang:",
        speakTitle: 'Gapirish mashqi', speakInstr: "Savolni tinglang va javobingizni yozing.",
        levels: ["Boshlang'ich", 'Elementar', "O'rta", "Yuqori o'rta", "Ilg'or"],
        topics: ['Present Simple', 'Past Simple', 'Future Simple', 'Present Continuous', 'Past Continuous', 'Present Perfect', 'Modal fe\'llar', 'Shartli gaplar', 'Passiv nisbat', 'Artikllar', 'Qiyoslash darajalari', 'Predloglar', 'Egri nutq', 'Nisbiy ergash gaplar', 'Frazeologik fe\'llar'],
        noResults: 'Natijalar yo\'q',
      },
      tj: {
        tabs: ['Дарсҳо', 'Гӯш кардан', 'Хондан', 'Гуфтугӯ', 'Луғат', 'Чат AI', 'Омор'],
        tabIcons: ['📖', '🎧', '📰', '🎤', '📚', '🤖', '📊'],
        start: 'Санҷишро оғоз кунед', back: 'Бозгашт', next: 'Навбатӣ', submit: 'Фиристодан',
        question: 'Савол', of: 'аз', correct: 'Дуруст!', wrong: 'Нодуруст!',
        yourScore: 'Натиҷаи шумо', tryAgain: 'Аз нав кӯшиш кунед', listenAgain: 'Аз нав гӯш кунед',
        play: 'Пахш кунед', record: 'Ҷавоб диҳед', vocabSearch: 'Ҷустуҷӯи калима...',
        aiPlaceholder: 'Дар бораи забони англисӣ пурсед...', aiSend: 'Фиристодан',
        aiWelcome: 'Салом! Ман ёрдамчии шумо дар омӯзиши забони англисӣ ҳастам. Дар бораи грамматика, калимаҳо пурсед! 🎓',
        statsTitle: 'Пешрафти шумо', noStats: 'Ҳоло натиҷаҳо нест. Санҷишҳоро гузаред!',
        totalTests: 'Санҷишҳои гузашта', avgScore: 'Бали миёна', bestScore: 'Беҳтарин балл',
        lessonSelect: 'Мавзӯро интихоб кунед:', readingSelect: 'Матнро интихоб кунед:', listenSelect: 'Машқро интихоб кунед:',
        speakTitle: 'Машқи гуфтугӯ', speakInstr: 'Саволро гӯш кунед ва ҷавоби худро нависед.',
        levels: ['Ибтидоӣ', 'Элементарӣ', 'Миёна', 'Болои миёна', 'Пешрафта'],
        topics: ['Present Simple', 'Past Simple', 'Future Simple', 'Present Continuous', 'Past Continuous', 'Present Perfect', 'Феълҳои модалӣ', 'Ҷумлаҳои шартӣ', 'Нидои маҷҳул', 'Артиклҳо', 'Дараҷаҳои муқоиса', 'Пешоянд', 'Нутқи ғайримустақим', 'Ҷумлаҳои нисбӣ', 'Феълҳои фразеологӣ'],
        noResults: 'Натиҷаҳо нест',
      }
    };

    // Grammar questions bank
    const QUESTIONS = {
      'Present Simple': [
        { q: "She ___ to school every day.", o: ["go", "goes", "going", "gone"], a: 1 },
        { q: "They ___ football on Sundays.", o: ["plays", "play", "playing", "played"], a: 1 },
        { q: "He ___ not like coffee.", o: ["do", "does", "is", "are"], a: 1 },
        { q: "___ you speak English?", o: ["Do", "Does", "Are", "Is"], a: 0 },
        { q: "The sun ___ in the east.", o: ["rise", "rises", "rising", "rose"], a: 1 },
        { q: "My mother ___ breakfast every morning.", o: ["cook", "cooks", "cooked", "cooking"], a: 1 },
        { q: "Water ___ at 100 degrees Celsius.", o: ["boil", "boils", "boiled", "boiling"], a: 1 },
        { q: "I ___ to music every evening.", o: ["listen", "listens", "listening", "listened"], a: 0 },
        { q: "She ___ three languages fluently.", o: ["speak", "speaks", "spoke", "speaking"], a: 1 },
        { q: "The train ___ at 9 AM.", o: ["leave", "leaves", "leaving", "left"], a: 1 },
        { q: "Dogs ___ faithful animals.", o: ["is", "am", "are", "be"], a: 2 },
        { q: "He always ___ his homework.", o: ["do", "does", "did", "done"], a: 1 },
        { q: "We ___ in a big city.", o: ["live", "lives", "lived", "living"], a: 0 },
        { q: "She ___ TV every evening.", o: ["watch", "watches", "watched", "watching"], a: 1 },
        { q: "It often ___ in London.", o: ["rain", "rains", "rained", "raining"], a: 1 },
        { q: "I ___ tea in the mornings.", o: ["drink", "drinks", "drank", "drinking"], a: 0 },
        { q: "Birds ___ in the sky.", o: ["fly", "flies", "flew", "flying"], a: 0 },
        { q: "He never ___ late.", o: ["arrive", "arrives", "arrived", "arriving"], a: 1 },
        { q: "___ she work here?", o: ["Do", "Does", "Is", "Are"], a: 1 },
        { q: "The Earth ___ around the Sun.", o: ["rotate", "rotates", "rotating", "rotated"], a: 1 },
        { q: "My father ___ a car.", o: ["drive", "drives", "drove", "driving"], a: 1 },
        { q: "Cats ___ milk.", o: ["like", "likes", "liked", "liking"], a: 1 },
        { q: "She ___ her teeth twice a day.", o: ["brush", "brushes", "brushed", "brushing"], a: 1 },
        { q: "We ___ English at school.", o: ["study", "studies", "studied", "studying"], a: 0 },
        { q: "He ___ very fast.", o: ["run", "runs", "running", "ran"], a: 1 },
        { q: "The shop ___ at 9 AM.", o: ["open", "opens", "opening", "opened"], a: 1 },
        { q: "I ___ a student.", o: ["is", "am", "are", "be"], a: 1 },
        { q: "They ___ dinner at 7 PM.", o: ["has", "have", "having", "had"], a: 1 },
        { q: "She ___ beautiful songs.", o: ["sing", "sings", "sang", "singing"], a: 1 },
        { q: "It ___ cold in winter.", o: ["get", "gets", "got", "getting"], a: 1 },
        { q: "He ___ books every week.", o: ["read", "reads", "reading", "red"], a: 1 },
        { q: "We ___ to the gym on Mondays.", o: ["go", "goes", "going", "went"], a: 0 },
        { q: "The baby ___ a lot.", o: ["cry", "cries", "cried", "crying"], a: 1 },
        { q: "I ___ my friends on weekends.", o: ["meet", "meets", "met", "meeting"], a: 0 },
        { q: "She ___ hard every day.", o: ["work", "works", "worked", "working"], a: 1 },
      ],
      'Past Simple': [
        { q: "I ___ to the store yesterday.", o: ["go", "went", "gone", "going"], a: 1 },
        { q: "She ___ a letter last night.", o: ["write", "wrote", "written", "writing"], a: 1 },
        { q: "They ___ football last Sunday.", o: ["play", "played", "playing", "plays"], a: 1 },
        { q: "He ___ the book in two days.", o: ["read", "reads", "reading", "red"], a: 0 },
        { q: "We ___ a great movie last week.", o: ["see", "saw", "seen", "seeing"], a: 1 },
        { q: "She ___ dinner for everyone.", o: ["cook", "cooked", "cooking", "cooks"], a: 1 },
        { q: "The children ___ to the park.", o: ["run", "ran", "running", "runs"], a: 1 },
        { q: "I ___ my keys this morning.", o: ["lose", "lost", "losing", "loses"], a: 1 },
        { q: "He ___ to London last year.", o: ["travel", "travelled", "travelling", "travels"], a: 1 },
        { q: "They ___ the test easily.", o: ["pass", "passed", "passing", "passes"], a: 1 },
        { q: "She ___ the door quietly.", o: ["close", "closed", "closing", "closes"], a: 1 },
        { q: "We ___ breakfast at 7 AM.", o: ["have", "had", "having", "has"], a: 1 },
        { q: "He ___ the answer immediately.", o: ["know", "knew", "known", "knowing"], a: 1 },
        { q: "I ___ English for 5 years.", o: ["study", "studied", "studying", "studies"], a: 1 },
        { q: "She ___ a beautiful dress.", o: ["wear", "wore", "worn", "wearing"], a: 1 },
        { q: "They ___ a house last month.", o: ["buy", "bought", "buying", "buys"], a: 1 },
        { q: "He ___ me the truth.", o: ["tell", "told", "telling", "tells"], a: 1 },
        { q: "We ___ at the hotel.", o: ["stay", "stayed", "staying", "stays"], a: 1 },
        { q: "She ___ the window.", o: ["break", "broke", "broken", "breaking"], a: 1 },
        { q: "I ___ a taxi to work.", o: ["take", "took", "taken", "taking"], a: 1 },
        { q: "The baby ___ all night.", o: ["cry", "cried", "crying", "cries"], a: 1 },
        { q: "He ___ his bike to school.", o: ["ride", "rode", "ridden", "riding"], a: 1 },
        { q: "We ___ goodbye at the airport.", o: ["say", "said", "saying", "says"], a: 1 },
        { q: "She ___ the piano beautifully.", o: ["play", "played", "playing", "plays"], a: 1 },
        { q: "They ___ home at midnight.", o: ["come", "came", "coming", "comes"], a: 1 },
        { q: "I ___ tired after the race.", o: ["feel", "felt", "feeling", "feels"], a: 1 },
        { q: "He ___ the ball very far.", o: ["throw", "threw", "thrown", "throwing"], a: 1 },
        { q: "We ___ in the lake.", o: ["swim", "swam", "swimming", "swims"], a: 1 },
        { q: "She ___ all her exams.", o: ["pass", "passed", "passing", "passes"], a: 1 },
        { q: "The teacher ___ us homework.", o: ["give", "gave", "giving", "gives"], a: 1 },
        { q: "I ___ a strange noise.", o: ["hear", "heard", "hearing", "hears"], a: 1 },
        { q: "He ___ asleep quickly.", o: ["fall", "fell", "fallen", "falling"], a: 1 },
        { q: "We ___ many photos.", o: ["take", "took", "taken", "taking"], a: 1 },
        { q: "She ___ very happy.", o: ["seem", "seemed", "seeming", "seems"], a: 1 },
        { q: "They ___ the project on time.", o: ["finish", "finished", "finishing", "finishes"], a: 1 },
      ],
      'Future Simple': [
        { q: "I ___ call you tomorrow.", o: ["will", "would", "shall", "am going"], a: 0 },
        { q: "She ___ be 18 next month.", o: ["will", "would", "shall", "is"], a: 0 },
        { q: "They ___ travel to Paris next summer.", o: ["will", "would", "shall", "are"], a: 0 },
        { q: "He ___ pass the exam, I'm sure.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "We ___ buy a new car soon.", o: ["will", "would", "shall", "are"], a: 0 },
        { q: "It ___ rain tomorrow.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "I ___ help you with that.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "She ___ be a doctor one day.", o: ["will", "would", "shall", "is"], a: 0 },
        { q: "They ___ arrive at 5 PM.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "We ___ not forget this day.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "He ___ finish work by Friday.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "I think it ___ snow tonight.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "She ___ cook dinner for us.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "The movie ___ start at 8.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "We ___ see each other next week.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "I ___ study harder next semester.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "He ___ probably be late.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "They ___ build a new school here.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "She ___ send the email soon.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "___ you come to the party?", o: ["Will", "Would", "Shall", "Do"], a: 0 },
        { q: "I ___ not tell anyone.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "The price ___ increase next year.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "We ___ miss you a lot.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "He ___ get better soon.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "I ___ always remember this.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "She ___ graduate next June.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "They ___ open a new shop.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "The weather ___ be nice tomorrow.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "I ___ let you know the result.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "We ___ celebrate together.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "He ___ understand eventually.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "She ___ wait for you.", o: ["will", "would", "shall", "does"], a: 0 },
        { q: "I ___ do my best.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "They ___ never forget this.", o: ["will", "would", "shall", "do"], a: 0 },
        { q: "It ___ take about an hour.", o: ["will", "would", "shall", "does"], a: 0 },
      ],
      'Present Continuous': [
        { q: "I ___ reading a book now.", o: ["am", "is", "are", "be"], a: 0 },
        { q: "She ___ cooking dinner.", o: ["am", "is", "are", "be"], a: 1 },
        { q: "They ___ playing outside.", o: ["am", "is", "are", "be"], a: 2 },
        { q: "He ___ watching TV at the moment.", o: ["am", "is", "are", "be"], a: 1 },
        { q: "We ___ preparing for the exam.", o: ["am", "is", "are", "be"], a: 2 },
        { q: "Look! The baby ___ walking!", o: ["am", "is", "are", "be"], a: 1 },
        { q: "I ___ not sleeping, I am awake.", o: ["am", "is", "are", "be"], a: 0 },
        { q: "She ___ wearing a red dress today.", o: ["am", "is", "are", "be"], a: 1 },
        { q: "They ___ building a new house.", o: ["am", "is", "are", "be"], a: 2 },
        { q: "He ___ running in the park.", o: ["am", "is", "are", "be"], a: 1 },
        { q: "What ___ you doing?", o: ["am", "is", "are", "do"], a: 2 },
        { q: "The phone ___ ringing.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "We ___ waiting for the bus.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "She ___ learning to drive.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "I ___ writing an email.", o: ["am", "is", "are", "do"], a: 0 },
        { q: "The children ___ sleeping now.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "He ___ talking on the phone.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "It ___ raining outside.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "We ___ having lunch.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "She ___ listening to music.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "I ___ trying my best.", o: ["am", "is", "are", "do"], a: 0 },
        { q: "They ___ dancing at the party.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "He ___ fixing the car.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "The cat ___ sitting on the roof.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "We ___ moving to a new city.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "She ___ painting a picture.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "I ___ feeling much better now.", o: ["am", "is", "are", "do"], a: 0 },
        { q: "They ___ working on a project.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "He ___ having breakfast.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "Look! She ___ crying.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "We ___ planning a holiday.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "The dog ___ barking loudly.", o: ["am", "is", "are", "do"], a: 1 },
        { q: "I ___ thinking about it.", o: ["am", "is", "are", "do"], a: 0 },
        { q: "They ___ getting ready for the show.", o: ["am", "is", "are", "do"], a: 2 },
        { q: "She ___ smiling at me.", o: ["am", "is", "are", "do"], a: 1 },
      ],
      'Past Continuous': [
        { q: "I ___ sleeping when you called.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ playing when it started to rain.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "She ___ reading at 8 PM.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ watching a movie.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "He ___ driving to work.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "The children ___ running in the garden.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "I ___ cooking when the phone rang.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "She ___ singing beautifully.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ studying all night.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "He ___ waiting for the bus.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ having dinner at 7.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "The dog ___ barking all morning.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "I ___ working when she arrived.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ dancing at the party.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "She ___ wearing a blue coat.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "He ___ cleaning his room.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ talking about you.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "The baby ___ crying loudly.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "I ___ thinking about the problem.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ walking to school.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "She ___ looking out the window.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "He ___ writing a letter.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ sitting in the park.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "The sun ___ shining brightly.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "I ___ having lunch at noon.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ arguing about something.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "She ___ teaching in the classroom.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "He ___ swimming in the pool.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ listening to the radio.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "When I woke up, it ___ snowing.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "I ___ dreaming about vacation.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "They ___ laughing at the joke.", o: ["was", "were", "am", "is"], a: 1 },
        { q: "She ___ drawing a picture.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "He ___ fixing the fence.", o: ["was", "were", "am", "is"], a: 0 },
        { q: "We ___ enjoying the concert.", o: ["was", "were", "am", "is"], a: 1 },
      ],
      'Present Perfect': [
        { q: "I ___ just finished my homework.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "She ___ visited Paris twice.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "They ___ never seen snow.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ lived here for 10 years.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ already had lunch.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "She ___ written three books.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ known him since childhood.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ moved to a new city.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ broken his arm.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ been to Japan.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "She ___ lost her keys.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ not seen this film yet.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ passed the exam.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ already cooked dinner.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ learned a lot today.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "She ___ just arrived.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ bought a new phone.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ cleaned the house.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ studied English for years.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "___ you ever been to London?", o: ["Have", "Has", "Are", "Were"], a: 0 },
        { q: "She ___ taught here since 2010.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ met him before.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ completed the project.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ grown much taller.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ heard the news.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "She ___ taken her medicine.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ forgotten his name.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ opened a new shop.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ chosen the blue one.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ spent all our money.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "She ___ sung this song before.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "I ___ driven this car before.", o: ["have", "has", "am", "was"], a: 0 },
        { q: "They ___ found the answer.", o: ["have", "has", "are", "were"], a: 0 },
        { q: "He ___ won the competition.", o: ["have", "has", "is", "was"], a: 1 },
        { q: "We ___ told them everything.", o: ["have", "has", "are", "were"], a: 0 },
      ],
      'Modal Verbs': [
        { q: "You ___ wear a seatbelt in the car.", o: ["must", "can", "will", "shall"], a: 0 },
        { q: "She ___ speak three languages.", o: ["can", "must", "will", "should"], a: 0 },
        { q: "I ___ help you if you want.", o: ["can", "must", "need", "should"], a: 0 },
        { q: "He ___ be at home. I'm not sure.", o: ["might", "must", "can", "need"], a: 0 },
        { q: "You ___ not park here.", o: ["must", "can", "will", "shall"], a: 0 },
        { q: "___ I borrow your pen?", o: ["Can", "Must", "Need", "Should"], a: 0 },
        { q: "We ___ study hard to pass.", o: ["should", "can", "might", "may"], a: 0 },
        { q: "She ___ swim when she was five.", o: ["could", "can", "must", "should"], a: 0 },
        { q: "You ___ see a doctor.", o: ["should", "can", "might", "may"], a: 0 },
        { q: "He ___ come late tonight.", o: ["might", "must", "can", "may"], a: 0 },
        { q: "Students ___ not cheat on exams.", o: ["must", "can", "will", "shall"], a: 0 },
        { q: "___ you pass the salt, please?", o: ["Could", "Must", "Need", "Should"], a: 0 },
        { q: "I ___ like some water, please.", o: ["would", "must", "should", "can"], a: 0 },
        { q: "She ___ be tired after the long trip.", o: ["must", "might", "will", "can"], a: 0 },
        { q: "We ___ go to the beach tomorrow.", o: ["could", "must", "need", "can"], a: 0 },
        { q: "You ___ eat more vegetables.", o: ["should", "can", "might", "may"], a: 0 },
        { q: "He ___ play the guitar very well.", o: ["can", "must", "will", "should"], a: 0 },
        { q: "___ I open the window?", o: ["Can", "Must", "Need", "Will"], a: 0 },
        { q: "They ___ have left already.", o: ["might", "may", "must", "will"], a: 0 },
        { q: "You ___ not touch that!", o: ["must", "can", "will", "shall"], a: 0 },
        { q: "She ___ dance beautifully.", o: ["can", "must", "will", "should"], a: 0 },
        { q: "We ___ leave now or we'll be late.", o: ["must", "can", "will", "shall"], a: 0 },
        { q: "He ___ come to the party. I'll invite him.", o: ["might", "must", "need", "should"], a: 0 },
        { q: "You ___ always tell the truth.", o: ["should", "can", "might", "may"], a: 0 },
        { q: "I ___ run faster when I was young.", o: ["could", "can", "must", "should"], a: 0 },
        { q: "She ___ not need to work tomorrow.", o: ["may", "must", "can", "might"], a: 0 },
        { q: "___ you help me carry this?", o: ["Could", "Must", "Need", "Should"], a: 0 },
        { q: "He ___ be the new teacher.", o: ["must", "can", "should", "will"], a: 0 },
        { q: "We ___ try the new restaurant.", o: ["should", "must", "need", "can"], a: 0 },
        { q: "They ___ have forgotten the meeting.", o: ["might", "must", "can", "need"], a: 0 },
        { q: "You ___ not worry about it.", o: ["need", "should", "can", "might"], a: 0 },
        { q: "She ___ read before she was four.", o: ["could", "can", "must", "might"], a: 0 },
        { q: "I ___ be going now. Bye!", o: ["must", "can", "would", "might"], a: 0 },
        { q: "___ we begin the lesson?", o: ["Shall", "Should", "Need", "Would"], a: 0 },
        { q: "He ___ have lifted 100 kg.", o: ["could", "must", "would", "will"], a: 0 },
      ],
      'Conditionals': [
        { q: "If it rains, I ___ stay at home.", o: ["will", "would", "was", "is"], a: 0 },
        { q: "If I ___ you, I would apologize.", o: ["were", "am", "be", "was"], a: 0 },
        { q: "If she studies, she ___ pass the exam.", o: ["will", "would", "could", "might"], a: 0 },
        { q: "If I had known, I ___ have helped.", o: ["would", "will", "can", "might"], a: 0 },
        { q: "If you heat water, it ___.", o: ["boils", "would boil", "boiled", "will boil"], a: 0 },
        { q: "If I ___ rich, I would travel the world.", o: ["were", "am", "would be", "was"], a: 0 },
        { q: "If he comes, we ___ start the meeting.", o: ["will", "would", "was", "shall"], a: 0 },
        { q: "If they worked harder, they ___ succeed.", o: ["would", "will", "can", "do"], a: 0 },
        { q: "If I had studied, I ___ have passed.", o: ["would", "will", "can", "shall"], a: 0 },
        { q: "If you mix red and blue, you ___ get purple.", o: ["get", "would get", "got", "will get"], a: 0 },
        { q: "I ___ call you if I have time.", o: ["will", "would", "shall", "can"], a: 0 },
        { q: "If she had come earlier, she ___ have been late.", o: ["would not", "will not", "shall not", "does not"], a: 0 },
        { q: "If we ___ the lottery, we would be rich.", o: ["won", "win", "had won", "wins"], a: 0 },
        { q: "If you press this button, the light ___ on.", o: ["turns", "would turn", "turned", "will turn"], a: 0 },
        { q: "If I were taller, I ___ play basketball.", o: ["would", "will", "can", "do"], a: 0 },
        { q: "If it snows, the children ___ be happy.", o: ["will", "would", "could", "had"], a: 0 },
        { q: "If he ___ me, I would have answered.", o: ["had called", "calls", "will call", "called"], a: 0 },
        { q: "If you eat too much, you ___ feel sick.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If I ___ you, I would take that job.", o: ["were", "am", "would be", "was"], a: 0 },
        { q: "She ___ be happy if she heard this news.", o: ["would", "will", "can", "shall"], a: 0 },
        { q: "If we leave now, we ___ arrive on time.", o: ["will", "would", "could", "should"], a: 0 },
        { q: "If I had a car, I ___ drive to work.", o: ["would", "will", "can", "do"], a: 0 },
        { q: "If they invite us, we ___ go.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If you ___ water them, plants die.", o: ["don't", "didn't", "won't", "wouldn't"], a: 0 },
        { q: "If he had studied medicine, he ___ be a doctor.", o: ["would", "will", "can", "does"], a: 0 },
        { q: "If I see her, I ___ say hello.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If she ___ free, she would come.", o: ["were", "is", "will be", "was"], a: 0 },
        { q: "If you run fast, you ___ catch the bus.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If I ___ the answer, I would tell you.", o: ["knew", "know", "had known", "knows"], a: 0 },
        { q: "If the weather ___ sunny, we will go to the beach.", o: ["is", "was", "will be", "would be"], a: 0 },
        { q: "If he saves money, he ___ buy a car.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If I had wings, I ___ fly.", o: ["would", "will", "can", "shall"], a: 0 },
        { q: "If she exercised more, she ___ get better results.", o: ["would", "will", "can", "does"], a: 0 },
        { q: "If you touch fire, you ___ get burned.", o: ["will", "would", "could", "shall"], a: 0 },
        { q: "If we had hurried, we ___ have caught the train.", o: ["would", "will", "can", "do"], a: 0 },
      ],
      'Passive Voice': [
        { q: "The cake ___ baked by my mother.", o: ["was", "is being", "has", "did"], a: 0 },
        { q: "English ___ spoken all over the world.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The letter ___ written yesterday.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The homework ___ done.", o: ["has been", "is", "was", "did"], a: 0 },
        { q: "The window ___ broken by a ball.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "Cars ___ produced in factories.", o: ["are", "is", "was", "has"], a: 0 },
        { q: "The book ___ published in 2020.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The food ___ being cooked right now.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The test ___ taken by all students.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The house ___ painted blue.", o: ["was", "is being", "has", "does"], a: 0 },
        { q: "The report ___ be finished by Friday.", o: ["will", "is", "was", "has"], a: 0 },
        { q: "These shoes ___ made in Italy.", o: ["are", "is", "was", "has"], a: 0 },
        { q: "The thief ___ caught by the police.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The song ___ sung by the choir.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The building ___ being constructed.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "Rice ___ grown in Asia.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The invitations ___ sent yesterday.", o: ["were", "are", "do", "did"], a: 0 },
        { q: "The meeting ___ cancelled.", o: ["was", "is", "did", "do"], a: 0 },
        { q: "The road ___ repaired last month.", o: ["was", "is", "does", "do"], a: 0 },
        { q: "Coffee ___ served every morning.", o: ["is", "was", "does", "do"], a: 0 },
        { q: "The film ___ seen by millions.", o: ["was", "is", "does", "do"], a: 0 },
        { q: "The trees ___ planted by volunteers.", o: ["were", "was", "is", "does"], a: 0 },
        { q: "The door ___ locked at night.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The prize ___ won by our team.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "Bread ___ baked fresh daily.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The news ___ announced on TV.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "Homework ___ given every day.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "The game ___ played on Saturday.", o: ["is", "was", "has", "does"], a: 0 },
        { q: "Animals ___ protected by law.", o: ["are", "is", "was", "has"], a: 0 },
        { q: "The exam ___ postponed.", o: ["has been", "is", "was", "did"], a: 0 },
        { q: "The car ___ washed yesterday.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "Dinner ___ served at 7 PM.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The bridge ___ built in 1990.", o: ["was", "is", "has", "does"], a: 0 },
        { q: "The letters ___ delivered by the postman.", o: ["are", "is", "was", "has"], a: 0 },
        { q: "The project ___ be completed soon.", o: ["will", "is", "was", "has"], a: 0 },
      ],
      'Articles': [
        { q: "I saw ___ elephant at the zoo.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "She is ___ best student in the class.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "He wants ___ apple.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "___ sun rises in the east.", o: ["The", "A", "An", "—"], a: 0 },
        { q: "She is ___ doctor.", o: ["a", "an", "the", "—"], a: 0 },
        { q: "I need ___ hour to finish.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "___ water is essential for life.", o: ["—", "A", "An", "The"], a: 0 },
        { q: "He plays ___ guitar.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "I bought ___ new book.", o: ["a", "an", "the", "—"], a: 0 },
        { q: "___ moon is beautiful tonight.", o: ["The", "A", "An", "—"], a: 0 },
        { q: "She is ___ honest person.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "We live on ___ Earth.", o: ["—", "a", "an", "the"], a: 0 },
        { q: "I have ___ cat and ___ dog.", o: ["a, a", "an, a", "the, the", "a, an"], a: 0 },
        { q: "He went to ___ hospital.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "___ children love chocolate.", o: ["—", "A", "An", "The"], a: 0 },
        { q: "She gave me ___ umbrella.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "I watched ___ film last night.", o: ["a", "an", "the", "—"], a: 0 },
        { q: "He is ___ engineer.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "___ Atlantic Ocean is very deep.", o: ["The", "A", "An", "—"], a: 0 },
        { q: "She wants ___ cup of tea.", o: ["a", "an", "the", "—"], a: 0 },
        { q: "___ Everest is the highest mountain.", o: ["—", "A", "An", "The"], a: 0 },
        { q: "I need ___ information.", o: ["—", "a", "an", "the"], a: 0 },
        { q: "He is ___ university student.", o: ["a", "an", "the", "—"], a: 0 },
        { q: "___ happiness is important.", o: ["—", "A", "An", "The"], a: 0 },
        { q: "She played ___ piano at the concert.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "I want ___ orange juice.", o: ["—", "a", "an", "the"], a: 0 },
        { q: "He is ___ tallest boy in class.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "We went to ___ park yesterday.", o: ["the", "a", "an", "—"], a: 0 },
        { q: "___ gold is expensive.", o: ["—", "A", "An", "The"], a: 0 },
        { q: "She works at ___ airport.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "I watched ___ interesting film.", o: ["an", "a", "the", "—"], a: 0 },
        { q: "He needs ___ advice.", o: ["—", "a", "an", "the"], a: 0 },
        { q: "___ Pacific Ocean is huge.", o: ["The", "A", "An", "—"], a: 0 },
        { q: "I have ___ idea!", o: ["an", "a", "the", "—"], a: 0 },
        { q: "She is ___ only child.", o: ["the", "a", "an", "—"], a: 0 },
      ],
      'Comparatives': [
        { q: "She is ___ than her sister.", o: ["taller", "tallest", "more tall", "most tall"], a: 0 },
        { q: "This is the ___ book I have ever read.", o: ["best", "better", "gooder", "more good"], a: 0 },
        { q: "He runs ___ than me.", o: ["faster", "fastest", "more fast", "most fast"], a: 0 },
        { q: "She is the ___ girl in the school.", o: ["prettiest", "prettier", "more pretty", "most prettier"], a: 0 },
        { q: "This test is ___ than the last one.", o: ["harder", "hardest", "more hard", "most hard"], a: 0 },
        { q: "He is ___ than his brother.", o: ["smarter", "smartest", "more smart", "most smart"], a: 0 },
        { q: "This is the ___ car here.", o: ["most expensive", "more expensive", "expensivest", "very expensive"], a: 0 },
        { q: "My house is ___ than yours.", o: ["bigger", "biggest", "more big", "most big"], a: 0 },
        { q: "She is the ___ student in class.", o: ["smartest", "smarter", "more smart", "most smarter"], a: 0 },
        { q: "Today is ___ than yesterday.", o: ["colder", "coldest", "more cold", "most cold"], a: 0 },
        { q: "He is ___ than his father.", o: ["younger", "youngest", "more young", "most young"], a: 0 },
        { q: "This is the ___ film in history.", o: ["worst", "worse", "more bad", "most bad"], a: 0 },
        { q: "She sings ___ of all.", o: ["best", "better", "more good", "most good"], a: 0 },
        { q: "This road is ___ than that one.", o: ["longer", "longest", "more long", "most long"], a: 0 },
        { q: "He is the ___ runner on the team.", o: ["fastest", "faster", "more fast", "most fast"], a: 0 },
        { q: "English is ___ for me than math.", o: ["easier", "easiest", "more easy", "most easy"], a: 0 },
        { q: "This is the ___ building in the city.", o: ["tallest", "taller", "more tall", "most tall"], a: 0 },
        { q: "She is ___ than in the photo.", o: ["more beautiful", "most beautiful", "beautifuler", "beautifully"], a: 0 },
        { q: "He is the ___ person I know.", o: ["kindest", "kinder", "more kind", "most kind"], a: 0 },
        { q: "This chair is ___ than that one.", o: ["more comfortable", "most comfortable", "comfortabler", "comfortably"], a: 0 },
        { q: "She works ___ than anyone else.", o: ["harder", "hardest", "more hard", "most hard"], a: 0 },
        { q: "This is the ___ day of my life.", o: ["happiest", "happier", "more happy", "most happy"], a: 0 },
        { q: "He is ___ than his brother.", o: ["more careful", "most careful", "carefuller", "carefully"], a: 0 },
        { q: "This cake is ___ than the pie.", o: ["sweeter", "sweetest", "more sweet", "most sweet"], a: 0 },
        { q: "She is the ___ dancer in the group.", o: ["best", "better", "more good", "most good"], a: 0 },
        { q: "My bag is ___ than yours.", o: ["heavier", "heaviest", "more heavy", "most heavy"], a: 0 },
        { q: "This puzzle is ___ than that one.", o: ["more difficult", "most difficult", "difficulter", "difficultly"], a: 0 },
        { q: "He is the ___ man in the room.", o: ["oldest", "older", "more old", "most old"], a: 0 },
        { q: "Summer is ___ than spring.", o: ["hotter", "hottest", "more hot", "most hot"], a: 0 },
        { q: "This is the ___ story.", o: ["most interesting", "more interesting", "interestingest", "interestingly"], a: 0 },
        { q: "He is ___ than I expected.", o: ["more friendly", "most friendly", "friendlier", "friendlily"], a: 0 },
        { q: "She is ___ than she looks.", o: ["stronger", "strongest", "more strong", "most strong"], a: 0 },
        { q: "This is the ___ room in the house.", o: ["smallest", "smaller", "more small", "most small"], a: 0 },
        { q: "He drives ___ than his wife.", o: ["faster", "fastest", "more fast", "most fast"], a: 0 },
        { q: "This restaurant is ___ than that one.", o: ["more popular", "most popular", "popularer", "popularly"], a: 0 },
      ],
      'Prepositions': [
        { q: "The cat is ___ the table.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "I live ___ New York.", o: ["in", "on", "at", "to"], a: 0 },
        { q: "She arrived ___ Monday.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "The meeting is ___ 3 PM.", o: ["at", "in", "on", "to"], a: 0 },
        { q: "He was born ___ 1995.", o: ["in", "on", "at", "to"], a: 0 },
        { q: "The book is ___ the shelf.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "We went ___ the park.", o: ["to", "in", "on", "at"], a: 0 },
        { q: "She is interested ___ music.", o: ["in", "on", "at", "to"], a: 0 },
        { q: "He is good ___ math.", o: ["at", "in", "on", "to"], a: 0 },
        { q: "The shop is ___ the corner.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "See you ___ Friday.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "She lives ___ the second floor.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "He depends ___ his parents.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "We arrived ___ the airport.", o: ["at", "in", "on", "to"], a: 0 },
        { q: "The picture is ___ the wall.", o: ["on", "in", "at", "to"], a: 0 },
        { q: "I am afraid ___ spiders.", o: ["of", "from", "to", "at"], a: 0 },
        { q: "She is waiting ___ the bus.", o: ["for", "to", "on", "in"], a: 0 },
        { q: "He apologized ___ being late.", o: ["for", "to", "about", "from"], a: 0 },
        { q: "The bird is flying ___ the house.", o: ["over", "on", "in", "at"], a: 0 },
        { q: "She walked ___ the room.", o: ["across", "on", "in", "at"], a: 0 },
        { q: "He sat ___ me and Tom.", o: ["between", "among", "in", "on"], a: 0 },
        { q: "The dog ran ___ the fence.", o: ["through", "on", "in", "at"], a: 0 },
        { q: "She looked ___ the window.", o: ["out of", "on", "in", "at"], a: 0 },
        { q: "He has been here ___ 2010.", o: ["since", "for", "from", "in"], a: 0 },
        { q: "I waited ___ two hours.", o: ["for", "since", "from", "in"], a: 0 },
        { q: "The school is ___ the library.", o: ["next to", "close", "near to", "in"], a: 0 },
        { q: "She hid ___ the bed.", o: ["under", "on", "in", "at"], a: 0 },
        { q: "He is proud ___ his son.", o: ["of", "about", "for", "in"], a: 0 },
        { q: "We drove ___ the tunnel.", o: ["through", "on", "in", "at"], a: 0 },
        { q: "She is married ___ a doctor.", o: ["to", "with", "for", "at"], a: 0 },
        { q: "I agree ___ you.", o: ["with", "to", "for", "on"], a: 0 },
        { q: "He suffers ___ headaches.", o: ["from", "of", "with", "at"], a: 0 },
        { q: "The cat jumped ___ the wall.", o: ["over", "on", "in", "at"], a: 0 },
        { q: "She is responsible ___ the project.", o: ["for", "of", "about", "to"], a: 0 },
        { q: "He succeeded ___ business.", o: ["in", "on", "at", "to"], a: 0 },
      ],
      'Reported Speech': [
        { q: 'She said that she ___ tired.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'He told me that he ___ help.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'They said that they ___ leaving.', o: ["were", "are", "will be", "have been"], a: 0 },
        { q: 'She said that she ___ finished.', o: ["had", "has", "will have", "is"], a: 0 },
        { q: 'He said he ___ the book.', o: ["had read", "reads", "will read", "is reading"], a: 0 },
        { q: 'She asked if I ___ English.', o: ["spoke", "speak", "will speak", "am speaking"], a: 0 },
        { q: 'He said that he ___ go tomorrow.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'They told us that they ___ happy.', o: ["were", "are", "will be", "have been"], a: 0 },
        { q: 'She said that she ___ a new job.', o: ["had found", "finds", "will find", "is finding"], a: 0 },
        { q: 'He asked where I ___.', o: ["lived", "live", "will live", "am living"], a: 0 },
        { q: 'She told me that she ___ cooking.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'He said that he ___ the film.', o: ["had seen", "has seen", "will see", "is seeing"], a: 0 },
        { q: 'They asked if we ___ come.', o: ["could", "can", "will", "shall"], a: 0 },
        { q: 'She said that she ___ to the shop.', o: ["had gone", "goes", "will go", "is going"], a: 0 },
        { q: 'He said that he ___ busy.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'She asked what I ___ doing.', o: ["was", "am", "will be", "have been"], a: 0 },
        { q: 'He said that the weather ___ good.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'They told us that they ___ arrived.', o: ["had", "have", "will have", "are"], a: 0 },
        { q: 'She said that she ___ call later.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'He asked if she ___ come.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'She said that she ___ the answer.', o: ["knew", "knows", "will know", "is knowing"], a: 0 },
        { q: 'He told me that he ___ study more.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'They said that they ___ not understand.', o: ["could", "can", "will", "shall"], a: 0 },
        { q: 'She asked when we ___ leave.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'He said that he ___ never been there.', o: ["had", "has", "will have", "is"], a: 0 },
        { q: 'She told me that she ___ a teacher.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'He said that he ___ his keys.', o: ["had lost", "has lost", "will lose", "is losing"], a: 0 },
        { q: 'They asked if I ___ free.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'She said that the food ___ delicious.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'He told me that he ___ try harder.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'She said that she ___ waiting.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'He asked why I ___ late.', o: ["was", "is", "will be", "has been"], a: 0 },
        { q: 'They said that they ___ help us.', o: ["would", "will", "can", "shall"], a: 0 },
        { q: 'She told me that she ___ heard the news.', o: ["had", "has", "will have", "is"], a: 0 },
        { q: 'He said that he ___ feeling well.', o: ["was", "is", "will be", "has been"], a: 0 },
      ],
      'Relative Clauses': [
        { q: "The man ___ lives next door is a doctor.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The book ___ I read was amazing.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The girl ___ bag was stolen was crying.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The city ___ we visited was beautiful.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The teacher ___ taught us is retired.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The house ___ roof is red is mine.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The film ___ we watched was funny.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The woman ___ called you is my aunt.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The car ___ he bought is expensive.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The boy ___ father is a pilot is my friend.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The restaurant ___ we ate was excellent.", o: ["where", "who", "whose", "whom"], a: 0 },
        { q: "The students ___ passed the exam celebrated.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The dog ___ bit me was black.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The artist ___ paintings are famous died young.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The place ___ we met is special.", o: ["where", "who", "which", "whom"], a: 0 },
        { q: "The day ___ she arrived was rainy.", o: ["when", "who", "which", "whom"], a: 0 },
        { q: "The reason ___ he left is unknown.", o: ["why", "who", "which", "whom"], a: 0 },
        { q: "The people ___ work here are friendly.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The country ___ I was born is small.", o: ["where", "which", "who", "whom"], a: 0 },
        { q: "The time ___ we have is limited.", o: ["which", "who", "whom", "when"], a: 0 },
        { q: "The woman ___ I met was kind.", o: ["whom", "who", "which", "where"], a: 0 },
        { q: "The hotel ___ we stayed was good.", o: ["where", "which", "who", "whom"], a: 0 },
        { q: "The children ___ parents came were happy.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The phone ___ is ringing is mine.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The doctor ___ treated me was gentle.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The garden ___ flowers bloom is beautiful.", o: ["whose", "where", "who", "which"], a: 0 },
        { q: "The song ___ she sang was popular.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The friend ___ helped me is loyal.", o: ["who", "which", "whose", "whom"], a: 0 },
        { q: "The year ___ he graduated was 2020.", o: ["when", "which", "who", "whose"], a: 0 },
        { q: "The company ___ I work for is growing.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The person ___ opinion I trust is you.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The park ___ we play is nearby.", o: ["where", "who", "whose", "which"], a: 0 },
        { q: "The neighbour ___ dog barks is annoying.", o: ["whose", "who", "which", "whom"], a: 0 },
        { q: "The letter ___ arrived today is important.", o: ["which", "who", "whose", "whom"], a: 0 },
        { q: "The city ___ I grew up is quiet.", o: ["where", "who", "whose", "which"], a: 0 },
      ],
      'Phrasal Verbs': [
        { q: "Please ___ your shoes before entering.", o: ["take off", "put on", "pick up", "let in"], a: 0 },
        { q: "I need to ___ this word in the dictionary.", o: ["look up", "look after", "search for", "look into"], a: 0 },
        { q: "She ___ a great idea.", o: ["came up with", "came down", "came in", "came through"], a: 0 },
        { q: "He ___ smoking last year.", o: ["gave up", "gave in", "gave out", "gave away"], a: 0 },
        { q: "We ___ early for the trip.", o: ["set off", "set up", "set in", "set out"], a: 0 },
        { q: "Can you ___ the children while I'm away?", o: ["look after", "look up", "search for", "look into"], a: 0 },
        { q: "The plane ___ on time.", o: ["took off", "took on", "took in", "took up"], a: 0 },
        { q: "I'll ___ you ___ at the airport.", o: ["pick...up", "pick...on", "pick...off", "pick...in"], a: 0 },
        { q: "She ___ well with her colleagues.", o: ["gets along", "gets up", "gets over", "gets out"], a: 0 },
        { q: "He ___ the project alone.", o: ["carried out", "carried on", "carried away", "carried off"], a: 0 },
        { q: "Don't ___! Keep trying!", o: ["give up", "give in", "give away", "give out"], a: 0 },
        { q: "She ___ early every morning.", o: ["gets up", "gets in", "gets off", "gets along"], a: 0 },
        { q: "We need to ___ this problem.", o: ["figure out", "figure in", "work on", "sort out"], a: 0 },
        { q: "He ___ his cold.", o: ["got over", "got into", "got off", "got up"], a: 0 },
        { q: "She ___ the form carefully.", o: ["filled in", "filled out", "filled up", "filled off"], a: 0 },
        { q: "They ___ the meeting until Friday.", o: ["put off", "put on", "put up", "put in"], a: 0 },
        { q: "I can't ___ this noise anymore.", o: ["put up with", "put on", "put off", "put in"], a: 0 },
        { q: "She ___ a new hobby.", o: ["took up", "took off", "took on", "took in"], a: 0 },
        { q: "He ___ his father in many ways.", o: ["takes after", "takes on", "takes off", "takes in"], a: 0 },
        { q: "We ___ of milk. Please buy some.", o: ["ran out", "ran away", "ran off", "ran into"], a: 0 },
        { q: "She ___ the invitation.", o: ["turned down", "turned on", "turned off", "turned up"], a: 0 },
        { q: "He ___ looking for his keys.", o: ["ended up", "turned off", "turned on", "finished off"], a: 0 },
        { q: "Please ___ the light when you leave.", o: ["turn off", "turn on", "turn up", "turn down"], a: 0 },
        { q: "She ___ the truth eventually.", o: ["found out", "found on", "found off", "found in"], a: 0 },
        { q: "He ___ with the flu.", o: ["came down", "came up", "turned off", "turned on"], a: 0 },
        { q: "We need to ___ a solution.", o: ["come up with", "come down with", "turn on", "go in"], a: 0 },
        { q: "She ___ her promise.", o: ["kept to", "kept on", "kept off", "kept up"], a: 0 },
        { q: "He ___ his jacket because it was hot.", o: ["took off", "took on", "took up", "took in"], a: 0 },
        { q: "We should ___ expenses this month.", o: ["cut down on", "cut off", "cut in", "turn on"], a: 0 },
        { q: "She ___ a story for the children.", o: ["made up", "made on", "made off", "made in"], a: 0 },
        { q: "He ___ a joke.", o: ["told off", "went off", "let off", "cracked"], a: 0 },
        { q: "We ___ for dinner at 7.", o: ["went out", "went in", "went up", "went off"], a: 0 },
        { q: "She quickly ___ the mess.", o: ["cleaned up", "cleaned out", "cleaned in", "cleaned off"], a: 0 },
        { q: "He ___ to be a good cook.", o: ["turned out", "turned on", "turned off", "turned up"], a: 0 },
        { q: "We ___ our holiday plans.", o: ["sorted out", "sorted on", "sorted off", "sorted in"], a: 0 },
      ],
    };

    // Vocabulary
    const VOCAB = [
      { en: "hello", ru: "привет", uz: "salom", tj: "салом", cat: "greeting" },
      { en: "goodbye", ru: "до свидания", uz: "xayr", tj: "хайр", cat: "greeting" },
      { en: "thank you", ru: "спасибо", uz: "rahmat", tj: "ташаккур", cat: "greeting" },
      { en: "please", ru: "пожалуйста", uz: "iltimos", tj: "лутфан", cat: "greeting" },
      { en: "yes", ru: "да", uz: "ha", tj: "ҳа", cat: "basic" },
      { en: "no", ru: "нет", uz: "yo'q", tj: "не", cat: "basic" },
      { en: "water", ru: "вода", uz: "suv", tj: "об", cat: "food" },
      { en: "bread", ru: "хлеб", uz: "non", tj: "нон", cat: "food" },
      { en: "milk", ru: "молоко", uz: "sut", tj: "шир", cat: "food" },
      { en: "apple", ru: "яблоко", uz: "olma", tj: "себ", cat: "food" },
      { en: "house", ru: "дом", uz: "uy", tj: "хона", cat: "place" },
      { en: "school", ru: "школа", uz: "maktab", tj: "мактаб", cat: "place" },
      { en: "hospital", ru: "больница", uz: "kasalxona", tj: "беморхона", cat: "place" },
      { en: "book", ru: "книга", uz: "kitob", tj: "китоб", cat: "education" },
      { en: "teacher", ru: "учитель", uz: "o'qituvchi", tj: "муаллим", cat: "education" },
      { en: "student", ru: "студент", uz: "talaba", tj: "донишҷӯ", cat: "education" },
      { en: "mother", ru: "мать", uz: "ona", tj: "модар", cat: "family" },
      { en: "father", ru: "отец", uz: "ota", tj: "падар", cat: "family" },
      { en: "brother", ru: "брат", uz: "aka", tj: "бародар", cat: "family" },
      { en: "sister", ru: "сестра", uz: "opa", tj: "хоҳар", cat: "family" },
      { en: "friend", ru: "друг", uz: "do'st", tj: "дӯст", cat: "people" },
      { en: "child", ru: "ребёнок", uz: "bola", tj: "кӯдак", cat: "people" },
      { en: "man", ru: "мужчина", uz: "erkak", tj: "мард", cat: "people" },
      { en: "woman", ru: "женщина", uz: "ayol", tj: "зан", cat: "people" },
      { en: "day", ru: "день", uz: "kun", tj: "рӯз", cat: "time" },
      { en: "night", ru: "ночь", uz: "tun", tj: "шаб", cat: "time" },
      { en: "morning", ru: "утро", uz: "ertalab", tj: "субҳ", cat: "time" },
      { en: "evening", ru: "вечер", uz: "kechqurun", tj: "бегоҳ", cat: "time" },
      { en: "today", ru: "сегодня", uz: "bugun", tj: "имрӯз", cat: "time" },
      { en: "tomorrow", ru: "завтра", uz: "ertaga", tj: "фардо", cat: "time" },
      { en: "yesterday", ru: "вчера", uz: "kecha", tj: "дирӯз", cat: "time" },
      { en: "big", ru: "большой", uz: "katta", tj: "калон", cat: "adjective" },
      { en: "small", ru: "маленький", uz: "kichik", tj: "хурд", cat: "adjective" },
      { en: "good", ru: "хороший", uz: "yaxshi", tj: "хуб", cat: "adjective" },
      { en: "bad", ru: "плохой", uz: "yomon", tj: "бад", cat: "adjective" },
      { en: "beautiful", ru: "красивый", uz: "chiroyli", tj: "зебо", cat: "adjective" },
      { en: "happy", ru: "счастливый", uz: "baxtli", tj: "хушбахт", cat: "adjective" },
      { en: "sad", ru: "грустный", uz: "g'amgin", tj: "ғамгин", cat: "adjective" },
      { en: "hot", ru: "горячий", uz: "issiq", tj: "гарм", cat: "adjective" },
      { en: "cold", ru: "холодный", uz: "sovuq", tj: "хунук", cat: "adjective" },
      { en: "new", ru: "новый", uz: "yangi", tj: "нав", cat: "adjective" },
      { en: "old", ru: "старый", uz: "eski", tj: "кӯҳна", cat: "adjective" },
      { en: "eat", ru: "есть", uz: "yemoq", tj: "хӯрдан", cat: "verb" },
      { en: "drink", ru: "пить", uz: "ichmoq", tj: "нӯшидан", cat: "verb" },
      { en: "sleep", ru: "спать", uz: "uxlamoq", tj: "хобидан", cat: "verb" },
      { en: "walk", ru: "ходить", uz: "yurmoq", tj: "роҳ рафтан", cat: "verb" },
      { en: "run", ru: "бежать", uz: "yugurmoq", tj: "давидан", cat: "verb" },
      { en: "read", ru: "читать", uz: "o'qimoq", tj: "хондан", cat: "verb" },
      { en: "write", ru: "писать", uz: "yozmoq", tj: "навиштан", cat: "verb" },
      { en: "speak", ru: "говорить", uz: "gapirmoq", tj: "гап задан", cat: "verb" },
      { en: "listen", ru: "слушать", uz: "tinglamoq", tj: "гӯш кардан", cat: "verb" },
      { en: "work", ru: "работать", uz: "ishlamoq", tj: "кор кардан", cat: "verb" },
      { en: "study", ru: "учиться", uz: "o'qimoq", tj: "хондан", cat: "verb" },
      { en: "play", ru: "играть", uz: "o'ynamoq", tj: "бозӣ кардан", cat: "verb" },
      { en: "love", ru: "любить", uz: "sevmoq", tj: "дӯст доштан", cat: "verb" },
      { en: "help", ru: "помогать", uz: "yordam bermoq", tj: "кӯмак кардан", cat: "verb" },
      { en: "buy", ru: "покупать", uz: "sotib olmoq", tj: "харидан", cat: "verb" },
      { en: "sell", ru: "продавать", uz: "sotmoq", tj: "фурӯхтан", cat: "verb" },
      { en: "give", ru: "давать", uz: "bermoq", tj: "додан", cat: "verb" },
      { en: "take", ru: "брать", uz: "olmoq", tj: "гирифтан", cat: "verb" },
      { en: "come", ru: "приходить", uz: "kelmoq", tj: "омадан", cat: "verb" },
      { en: "go", ru: "идти", uz: "bormoq", tj: "рафтан", cat: "verb" },
      { en: "car", ru: "машина", uz: "mashina", tj: "мошин", cat: "transport" },
      { en: "bus", ru: "автобус", uz: "avtobus", tj: "автобус", cat: "transport" },
      { en: "train", ru: "поезд", uz: "poyezd", tj: "поезд", cat: "transport" },
      { en: "airplane", ru: "самолёт", uz: "samolyot", tj: "ҳавопаймо", cat: "transport" },
      { en: "dog", ru: "собака", uz: "it", tj: "саг", cat: "animal" },
      { en: "cat", ru: "кошка", uz: "mushuk", tj: "гурба", cat: "animal" },
      { en: "bird", ru: "птица", uz: "qush", tj: "парранда", cat: "animal" },
      { en: "fish", ru: "рыба", uz: "baliq", tj: "моҳӣ", cat: "animal" },
      { en: "horse", ru: "лошадь", uz: "ot", tj: "асп", cat: "animal" },
      { en: "one", ru: "один", uz: "bir", tj: "як", cat: "number" },
      { en: "two", ru: "два", uz: "ikki", tj: "ду", cat: "number" },
      { en: "three", ru: "три", uz: "uch", tj: "се", cat: "number" },
      { en: "ten", ru: "десять", uz: "o'n", tj: "даҳ", cat: "number" },
      { en: "hundred", ru: "сто", uz: "yuz", tj: "сад", cat: "number" },
      { en: "red", ru: "красный", uz: "qizil", tj: "сурх", cat: "color" },
      { en: "blue", ru: "синий", uz: "ko'k", tj: "кабуд", cat: "color" },
      { en: "green", ru: "зелёный", uz: "yashil", tj: "сабз", cat: "color" },
      { en: "white", ru: "белый", uz: "oq", tj: "сафед", cat: "color" },
      { en: "black", ru: "чёрный", uz: "qora", tj: "сиёҳ", cat: "color" },
      { en: "money", ru: "деньги", uz: "pul", tj: "пул", cat: "basic" },
      { en: "food", ru: "еда", uz: "ovqat", tj: "ғизо", cat: "food" },
      { en: "city", ru: "город", uz: "shahar", tj: "шаҳр", cat: "place" },
      { en: "country", ru: "страна", uz: "mamlakat", tj: "кишвар", cat: "place" },
      { en: "world", ru: "мир", uz: "dunyo", tj: "ҷаҳон", cat: "basic" },
      { en: "life", ru: "жизнь", uz: "hayot", tj: "зиндагӣ", cat: "basic" },
      { en: "time", ru: "время", uz: "vaqt", tj: "вақт", cat: "time" },
      { en: "year", ru: "год", uz: "yil", tj: "сол", cat: "time" },
      { en: "month", ru: "месяц", uz: "oy", tj: "моҳ", cat: "time" },
      { en: "week", ru: "неделя", uz: "hafta", tj: "ҳафта", cat: "time" },
      { en: "sun", ru: "солнце", uz: "quyosh", tj: "офтоб", cat: "nature" },
      { en: "moon", ru: "луна", uz: "oy", tj: "моҳ", cat: "nature" },
      { en: "rain", ru: "дождь", uz: "yomg'ir", tj: "борон", cat: "nature" },
      { en: "snow", ru: "снег", uz: "qor", tj: "барф", cat: "nature" },
      { en: "wind", ru: "ветер", uz: "shamol", tj: "шамол", cat: "nature" },
      { en: "tree", ru: "дерево", uz: "daraxt", tj: "дарахт", cat: "nature" },
      { en: "flower", ru: "цветок", uz: "gul", tj: "гул", cat: "nature" },
      { en: "mountain", ru: "гора", uz: "tog'", tj: "кӯҳ", cat: "nature" },
      { en: "river", ru: "река", uz: "daryo", tj: "дарё", cat: "nature" },
      { en: "sea", ru: "море", uz: "dengiz", tj: "баҳр", cat: "nature" },
      { en: "head", ru: "голова", uz: "bosh", tj: "сар", cat: "body" },
      { en: "hand", ru: "рука", uz: "qo'l", tj: "даст", cat: "body" },
      { en: "eye", ru: "глаз", uz: "ko'z", tj: "чашм", cat: "body" },
      { en: "heart", ru: "сердце", uz: "yurak", tj: "дил", cat: "body" },
      { en: "foot", ru: "нога", uz: "oyoq", tj: "по", cat: "body" },
    ];

    // Reading passages
    const READING = [
      {
        title: "A Day in the Park", text: "Sara woke up early on Saturday morning. The sun was shining brightly, and she decided to go to the park. She took a sandwich, an apple, and a bottle of water in her bag. At the park, she sat under a large oak tree and read her favourite book. Children were playing on the swings and slides. A small dog was running across the grass, chasing a red ball. Sara felt calm and happy. She stayed in the park until the sun began to set, painting the sky in beautiful shades of orange and pink. It was a perfect day.",
        qs: [{ q: "When did Sara wake up?", o: ["Saturday morning", "Sunday morning", "Friday evening", "Monday morning"], a: 0 }, { q: "What did Sara bring?", o: ["Sandwich, apple, water", "Pizza, juice, chips", "Rice, chicken, soda", "Bread, cheese, milk"], a: 0 }, { q: "Where did she sit?", o: ["Under an oak tree", "On a bench", "By a lake", "On the grass"], a: 0 }, { q: "What was the dog chasing?", o: ["A red ball", "A cat", "A bird", "A stick"], a: 0 }, { q: "How did Sara feel?", o: ["Calm and happy", "Tired and bored", "Sad and lonely", "Angry and upset"], a: 0 }]
      },
      {
        title: "The New Student", text: "On his first day at the new school, Tom was nervous. He walked through the big gates and looked around. The building was much bigger than his old school. A friendly boy named Alex came up to him and said, 'Hi! Are you new? I can show you around.' Tom smiled and felt relieved. Alex showed him the classrooms, the library, the canteen, and the sports field. By lunchtime, Tom had already made three new friends. He realized that starting at a new school was not as scary as he had thought. Sometimes changes can be wonderful.",
        qs: [{ q: "How did Tom feel on his first day?", o: ["Nervous", "Excited", "Angry", "Bored"], a: 0 }, { q: "Who helped Tom?", o: ["Alex", "Sam", "Mike", "John"], a: 0 }, { q: "What did Alex show Tom?", o: ["Classrooms, library, canteen, sports field", "Only the classroom", "The car park", "The staff room"], a: 0 }, { q: "How many friends did Tom make by lunch?", o: ["Three", "Two", "Five", "One"], a: 0 }, { q: "What did Tom realise?", o: ["Changes can be wonderful", "School is boring", "He wanted to go home", "He missed his old friends"], a: 0 }]
      },
      {
        title: "The Lost Cat", text: "On Tuesday evening, Mrs Johnson noticed that her cat, Whiskers, was missing. She searched the whole house — under the beds, behind the curtains, in the wardrobes — but Whiskers was nowhere to be found. She put up posters around the neighbourhood with a photo of Whiskers and her phone number. Three days later, a little girl named Emma called. She had found Whiskers hiding in her garden shed. Mrs Johnson was overjoyed. She thanked Emma by giving her a large box of chocolates. Whiskers seemed happy to be home and immediately curled up on his favourite spot on the sofa.",
        qs: [{ q: "When did Mrs Johnson notice Whiskers was missing?", o: ["Tuesday evening", "Monday morning", "Wednesday afternoon", "Friday night"], a: 0 }, { q: "What did she put up around the area?", o: ["Posters", "Reward signs", "Nothing", "Flyers"], a: 0 }, { q: "Who found Whiskers?", o: ["Emma", "Tom", "Alex", "Sara"], a: 0 }, { q: "Where was Whiskers found?", o: ["In a garden shed", "In the park", "At school", "Under a car"], a: 0 }, { q: "What did Mrs Johnson give Emma?", o: ["Chocolates", "Money", "Flowers", "A book"], a: 0 }]
      },
    ];

    // Listening content
    const LISTENING = [
      {
        title: "Self Introduction", text: "Hello! My name is John. I am twenty-five years old. I am from London, England. I work as a software engineer at a technology company. In my free time, I enjoy reading books, playing football, and cooking. I have one brother and one sister. My favourite food is pasta, and I love travelling to new countries. Nice to meet you!",
        qs: [{ q: "What is the speaker's name?", o: ["John", "James", "Jack", "Jake"], a: 0 }, { q: "How old is the speaker?", o: ["25", "30", "20", "35"], a: 0 }, { q: "Where is the speaker from?", o: ["London", "Paris", "New York", "Tokyo"], a: 0 }, { q: "What is the speaker's job?", o: ["Software engineer", "Teacher", "Doctor", "Chef"], a: 0 }, { q: "What is the speaker's favourite food?", o: ["Pasta", "Pizza", "Sushi", "Burger"], a: 0 }]
      },
      {
        title: "At the Restaurant", text: "Good evening! Welcome to The Golden Spoon restaurant. My name is Maria and I will be your server tonight. Today's specials are grilled salmon with vegetables for fifteen dollars, and chicken pasta for twelve dollars. We also have a wonderful chocolate cake for dessert. Would you like to start with something to drink? We have fresh orange juice, lemonade, and various teas. Please take your time with the menu and I will be back shortly to take your order.",
        qs: [{ q: "What is the restaurant called?", o: ["The Golden Spoon", "The Silver Fork", "The Red Plate", "The Blue Cup"], a: 0 }, { q: "What is the server's name?", o: ["Maria", "Anna", "Lisa", "Emma"], a: 0 }, { q: "How much is the grilled salmon?", o: ["$15", "$12", "$20", "$10"], a: 0 }, { q: "What is the dessert?", o: ["Chocolate cake", "Ice cream", "Fruit salad", "Cheesecake"], a: 0 }, { q: "How much is the chicken pasta?", o: ["$12", "$15", "$10", "$20"], a: 0 }]
      },
      {
        title: "Weather Forecast", text: "Good morning everyone! Here is your weather forecast for today. It will be sunny in the morning, with temperatures reaching twenty-three degrees Celsius. However, clouds will move in during the afternoon, and there is a sixty percent chance of rain by the evening. Temperatures will drop to about fifteen degrees at night. We recommend taking an umbrella if you are going out this afternoon. Tomorrow will be mostly cloudy with occasional showers. Have a great day!",
        qs: [{ q: "What will the morning be like?", o: ["Sunny", "Rainy", "Cloudy", "Snowy"], a: 0 }, { q: "What is the morning temperature?", o: ["23°C", "25°C", "20°C", "30°C"], a: 0 }, { q: "What is the chance of rain?", o: ["60%", "40%", "80%", "50%"], a: 0 }, { q: "What should people take?", o: ["An umbrella", "A jacket", "Sunglasses", "A hat"], a: 0 }, { q: "What will tomorrow be like?", o: ["Mostly cloudy with showers", "Sunny", "Very hot", "Snowy"], a: 0 }]
      },
    ];

    // Speaking prompts
    const SPEAKING = [
      { prompt: "What is your name?", hint: "My name is...", example: "My name is Alex." },
      { prompt: "How old are you?", hint: "I am ... years old.", example: "I am twenty years old." },
      { prompt: "Where are you from?", hint: "I am from...", example: "I am from Uzbekistan." },
      { prompt: "What do you do?", hint: "I am a... / I work as...", example: "I am a student." },
      { prompt: "What is your favourite food?", hint: "My favourite food is...", example: "My favourite food is pizza." },
      { prompt: "Do you have any hobbies?", hint: "Yes, I enjoy...", example: "Yes, I enjoy reading and playing football." },
      { prompt: "What time do you wake up?", hint: "I wake up at...", example: "I wake up at seven o'clock." },
      { prompt: "Tell me about your family.", hint: "I have... My mum...", example: "I have a big family. My mum is a teacher." },
      { prompt: "What did you do yesterday?", hint: "Yesterday I...", example: "Yesterday I went to the park with my friends." },
      { prompt: "What are your plans for tomorrow?", hint: "Tomorrow I will...", example: "Tomorrow I will study English and visit my grandmother." },
      { prompt: "Describe your best friend.", hint: "My best friend...", example: "My best friend is kind and funny. We go to school together." },
      { prompt: "What is the weather like today?", hint: "Today the weather is...", example: "Today it is sunny and warm." },
      { prompt: "What do you want to be in the future?", hint: "I want to be...", example: "I want to be a doctor to help people." },
      { prompt: "Tell me about your school.", hint: "My school...", example: "My school is large and has many classrooms." },
      { prompt: "What languages do you speak?", hint: "I speak...", example: "I speak Uzbek, Russian, and I am learning English." },
    ];

    // Lesson info
    const LESSON_INFO = {
      'Present Simple': "Used for habits, routines, general truths and permanent situations.\n\nForm: Subject + base verb (-s/-es for he/she/it)\n\n✓ I work every day.\n✓ She plays tennis.\n✓ Water boils at 100°C.\n\nNegative: Subject + do/does + not + verb\nQuestion: Do/Does + subject + verb?",
      'Past Simple': "Used for completed actions in the past.\n\nForm: Subject + past form of verb\nRegular: add -ed (worked, played)\nIrregular: change form (go→went, eat→ate)\n\n✓ I visited Paris last year.\n✓ She wrote a letter.\n\nNegative: Subject + did not + base verb\nQuestion: Did + subject + base verb?",
      'Future Simple': "Used for predictions, promises, decisions made now.\n\nForm: Subject + will + base verb\n\n✓ I will call you tomorrow.\n✓ She will be a great doctor.\n✓ It will rain tonight.\n\nNegative: Subject + will not (won't) + verb\nQuestion: Will + subject + verb?",
      'Present Continuous': "Used for actions happening now or around now.\n\nForm: Subject + am/is/are + verb-ing\n\n✓ I am reading a book.\n✓ She is cooking dinner.\n✓ They are playing outside.\n\nNegative: Subject + am/is/are + not + verb-ing\nQuestion: Am/Is/Are + subject + verb-ing?",
      'Past Continuous': "Used for actions in progress at a specific past time.\n\nForm: Subject + was/were + verb-ing\n\n✓ I was sleeping when you called.\n✓ They were playing when it rained.\n\nNegative: Subject + was/were + not + verb-ing\nQuestion: Was/Were + subject + verb-ing?",
      'Present Perfect': "Used for past actions with present relevance.\n\nForm: Subject + have/has + past participle\n\n✓ I have just finished.\n✓ She has visited Paris twice.\n✓ They have never seen snow.\n\nNegative: Subject + have/has + not + past participle\nQuestion: Have/Has + subject + past participle?",
      'Modal Verbs': "Modal verbs express ability, permission, obligation, possibility.\n\n• can – ability/permission: I can swim.\n• must – strong obligation: You must stop.\n• should – advice: You should rest.\n• might/may – possibility: It might rain.\n• could – past ability/polite request: Could you help?\n• would – conditional/polite: I would like tea.\n\nForm: Subject + modal + base verb (no 's'!)",
      'Conditionals': "Conditional sentences describe situations and their results.\n\n0 (fact): If water boils, it becomes steam.\n1 (real): If it rains, I will stay home.\n2 (unreal): If I were rich, I would travel.\n3 (past unreal): If I had studied, I would have passed.\n\nKey words: if, unless, when, provided that",
      'Passive Voice': "Used when the action is more important than who does it.\n\nForm: Subject + to be + past participle\n\n✓ The cake was baked by my mother.\n✓ English is spoken worldwide.\n✓ The letter was written yesterday.\n\nBy + agent (optional, says who did the action)",
      'Articles': "a/an – for singular countable nouns (first mention)\n• a book, an apple, a university\n\nthe – for specific nouns (known to both speaker & listener)\n• the sun, the moon, the book I read\n\n— (no article) – plural/uncountable in general\n• Water is life. Dogs are loyal.\n\nNote: an before vowel sounds: an hour, an umbrella",
      'Comparatives': "Comparing two things (comparative) or all in a group (superlative).\n\nShort adjectives:\n• tall → taller → tallest\n• big → bigger → biggest\n\nLong adjectives:\n• beautiful → more beautiful → most beautiful\n\nIrregular:\n• good → better → best\n• bad → worse → worst\n• far → farther/further → farthest/furthest\n\nthan for comparatives: She is taller than me.",
      'Prepositions': "Prepositions show time, place, direction, or manner.\n\nPlace: on (surface), in (inside), at (specific point)\n• The book is on the table.\n• I live in London.\n• She is at the door.\n\nTime: on (days), in (months/years), at (times)\n• on Monday, in March, at 3 PM\n\nOther: for, with, by, from, to, about, of, through",
      'Reported Speech': "Reporting what someone said.\n\nDirect: She said, 'I am tired.'\nReported: She said that she was tired.\n\nTense changes:\nis → was | am → was | are → were\nwill → would | can → could | have → had\ngo → went | do → did\n\nTime changes: now → then | today → that day\ntomorrow → the next day | yesterday → the day before",
      'Relative Clauses': "Relative clauses give more information about a noun.\n\nwho – for people: The man who called is my uncle.\nwhich – for things: The book which I read was great.\nthat – for people or things: The car that I bought is fast.\nwhose – for possession: The girl whose bag was stolen cried.\nwhere – for places: The park where we met is nice.\nwhen – for time: The day when she arrived was rainy.",
      'Phrasal Verbs': "Phrasal verbs = verb + particle (preposition/adverb)\nThey often have idiomatic meanings.\n\nCommon ones:\ngive up – stop trying\nlook up – search for information\nput off – postpone\ntake off – remove / (plane) depart\nget along – have a good relationship\nrun out of – have no more of something\nfigure out – understand / solve\ncame up with – think of an idea\nlook after – take care of",
    };

    // ============================================================
    // STATE
    // ============================================================
    let lang = 'en';
    let tab = 'lessons';
    let xp = 0;
    let streak = 0;
    let results = [];
    let quizState = null;
    let chatHistory = [];

    const TABS = ['lessons', 'listening', 'reading', 'speaking', 'vocabulary', 'ai', 'stats'];

    // ============================================================
    // UTILS
    // ============================================================
    function t() { return LANGS[lang]; }

    function shuffle(arr) {
      const a = [...arr];
      for (let i = a.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [a[i], a[j]] = [a[j], a[i]];
      }
      return a;
    }

    function speak(text) {
      if (!window.speechSynthesis) return;
      speechSynthesis.cancel();
      const u = new SpeechSynthesisUtterance(text);
      u.lang = 'en-US';
      u.rate = 0.9;
      speechSynthesis.speak(u);
    }

    function addXP(n) {
      xp += n;
      document.getElementById('xpCount').textContent = xp;
    }

    function el(id) { return document.getElementById(id); }

    function html(id, content) {
      const e = el(id);
      if (e) e.innerHTML = content;
    }

    // ============================================================
    // LANGUAGE
    // ============================================================
    function changeLang(l) {
      lang = l;
      renderAll();
    }

    // ============================================================
    // NAV
    // ============================================================
    function renderNav() {
      const L = t();
      el('navBar').innerHTML = TABS.map((id, i) => `
    <button class="nav-btn ${tab === id ? 'active' : ''}" onclick="setTab('${id}')">
      <span class="nav-icon">${L.tabIcons[i]}</span>
      ${L.tabs[i]}
    </button>
  `).join('');
    }

    function setTab(id) {
      tab = id;
      quizState = null;
      renderAll();
    }

    // ============================================================
    // RENDER ALL
    // ============================================================
    function renderAll() {
      renderNav();
      const c = el('mainContent');
      c.className = 'flex-1 overflow-y-auto p-4 fade-in';
      switch (tab) {
        case 'lessons': renderLessons(); break;
        case 'listening': renderListening(); break;
        case 'reading': renderReading(); break;
        case 'speaking': renderSpeaking(); break;
        case 'vocabulary': renderVocab(); break;
        case 'ai': renderAI(); break;
        case 'stats': renderStats(); break;
      }
    }

    // ============================================================
    // LESSONS
    // ============================================================
    const TOPIC_KEYS = Object.keys(QUESTIONS);
    const LEVEL_MAP = [0, 0, 0, 1, 1, 2, 2, 3, 3, 3, 4, 4, 3, 4, 4];

    function renderLessons() {
      if (quizState) { renderQuiz(); return; }
      const L = t();
      const topicNames = L.topics;
      let h = `<div class="section-title">📖 ${L.tabs[0]}</div>
    <div class="section-sub">${L.lessonSelect}</div>
    <div class="grid-2">`;
      TOPIC_KEYS.forEach((key, i) => {
        const lvl = LEVEL_MAP[i] || 0;
        const done = results.filter(r => r.topic === key);
        const best = done.length ? Math.max(...done.map(r => r.pct)) : null;
        const progress = best !== null ? best : 0;
        h += `<div class="topic-card" onclick="startLesson('${key}')">
      <div class="topic-num">${String(i + 1).padStart(2, '0')} / ${TOPIC_KEYS.length}</div>
      <div class="topic-name">${topicNames[i] || key}</div>
      <div class="level-chip level-${lvl}">${L.levels[lvl]}</div>
      <div class="topic-bar">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:4px">
          <span style="font-size:11px;color:var(--text3)">${best !== null ? best + '%' : '—'}</span>
          <span style="font-size:11px;color:var(--text3)">${done.length} ${done.length === 1 ? 'test' : 'tests'}</span>
        </div>
        <div class="progress-track">
          <div class="progress-fill" style="width:${progress}%"></div>
        </div>
      </div>
    </div>`;
      });
      h += '</div>';
      html('mainContent', h);
    }

    function startLesson(key) {
      const info = LESSON_INFO[key] || '';
      const L = t();
      const topicIdx = TOPIC_KEYS.indexOf(key);
      const topicName = L.topics[topicIdx] || key;
      html('mainContent', `
    <div class="fade-in">
      <button class="btn btn-outline" style="margin-bottom:16px" onclick="renderLessons()">← ${L.back}</button>
      <div class="section-title">${topicName}</div>
      <div class="card" style="margin-bottom:20px">
        <pre style="white-space:pre-wrap;font-family:'Sora',sans-serif;font-size:14px;line-height:1.8;color:var(--text2)">${info}</pre>
      </div>
      <button class="btn btn-primary" style="width:100%;padding:14px" onclick="beginQuiz('${key}')">
        🚀 ${L.start}
      </button>
    </div>
  `);
    }

    function beginQuiz(key) {
      const pool = QUESTIONS[key];
      const selected = shuffle(pool).slice(0, 30);
      quizState = {
        topic: key,
        questions: selected,
        idx: 0,
        score: 0,
        answered: false,
        done: false,
      };
      renderQuiz();
    }

    function renderQuiz() {
      const Q = quizState;
      const L = t();
      if (Q.done) { renderQuizResult(); return; }
      const q = Q.questions[Q.idx];
      const topicIdx = TOPIC_KEYS.indexOf(Q.topic);
      const topicName = L.topics[topicIdx] || Q.topic;
      const pct = Math.round((Q.idx / Q.questions.length) * 100);

      html('mainContent', `
    <div class="fade-in">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <button class="btn btn-outline" onclick="quizState=null;renderLessons()">← ${L.back}</button>
        <span style="font-size:13px;color:var(--text2)">${topicName}</span>
        <span class="pill pill-purple">${L.question} ${Q.idx + 1} ${L.of} ${Q.questions.length}</span>
      </div>
      <div class="progress-track" style="margin-bottom:20px">
        <div class="progress-fill" style="width:${pct}%"></div>
      </div>
      <div class="card" style="margin-bottom:20px">
        <div style="font-size:17px;font-weight:700;line-height:1.5">${q.q}</div>
      </div>
      <div id="optionsArea">
        ${q.o.map((opt, i) => `
          <button class="quiz-opt" id="opt${i}" onclick="selectOpt(${i})">
            <span style="font-family:'Space Mono',monospace;font-size:12px;color:var(--text3);margin-right:8px">${String.fromCharCode(65 + i)}.</span>
            ${opt}
          </button>
        `).join('')}
      </div>
      <div id="feedbackArea"></div>
    </div>
  `);
    }

    function selectOpt(chosen) {
      if (quizState.answered) return;
      quizState.answered = true;
      const q = quizState.questions[quizState.idx];
      const correct = q.a;
      const L = t();
      const isCorrect = chosen === correct;
      if (isCorrect) { quizState.score++; addXP(10); }

      for (let i = 0; i < q.o.length; i++) {
        const btn = el('opt' + i);
        if (!btn) continue;
        btn.classList.add('disabled');
        if (i === correct) btn.classList.add('correct');
        else if (i === chosen && !isCorrect) btn.classList.add('wrong');
      }

      const fb = el('feedbackArea');
      if (fb) {
        fb.innerHTML = `
      <div style="text-align:center;padding:16px 0">
        <div style="font-size:24px;margin-bottom:4px">${isCorrect ? '✅' : '❌'}</div>
        <div style="font-weight:700;color:${isCorrect ? 'var(--accent2)' : 'var(--danger)'}">${isCorrect ? L.correct : L.wrong}</div>
        ${!isCorrect ? `<div style="font-size:13px;color:var(--text2);margin-top:4px">Answer: ${q.o[correct]}</div>` : ''}
        <button class="btn btn-primary" style="margin-top:12px" onclick="nextQuestion()">${L.next} →</button>
      </div>
    `;
      }
    }

    function nextQuestion() {
      quizState.idx++;
      quizState.answered = false;
      if (quizState.idx >= quizState.questions.length) {
        quizState.done = true;
        const pct = Math.round((quizState.score / quizState.questions.length) * 100);
        results.push({ topic: quizState.topic, score: quizState.score, total: quizState.questions.length, pct, date: new Date().toLocaleDateString() });
        if (pct >= 70) { streak++; el('streakCount').textContent = streak; addXP(50); }
      }
      renderAll();
    }

    function renderQuizResult() {
      const Q = quizState;
      const L = t();
      const pct = Math.round((Q.score / Q.questions.length) * 100);
      const emoji = pct >= 90 ? '🏆' : pct >= 70 ? '🎉' : pct >= 50 ? '👍' : '💪';
      const topicIdx = TOPIC_KEYS.indexOf(Q.topic);
      const topicName = L.topics[topicIdx] || Q.topic;
      html('mainContent', `
    <div class="fade-in" style="text-align:center;padding:20px 0">
      <div style="font-size:48px;margin-bottom:12px">${emoji}</div>
      <div class="section-title">${L.yourScore}</div>
      <div class="score-big" style="margin:12px 0">${pct}%</div>
      <div style="color:var(--text2);margin-bottom:4px">${Q.score} / ${Q.questions.length} ${L.of} ${Q.questions.length}</div>
      <div class="pill pill-purple" style="margin-bottom:24px">${topicName}</div>
      <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap">
        <button class="btn btn-primary" onclick="beginQuiz('${Q.topic}')">🔄 ${L.tryAgain}</button>
        <button class="btn btn-outline" onclick="quizState=null;renderLessons()">← ${L.back}</button>
      </div>
    </div>
  `);
    }

    // ============================================================
    // LISTENING
    // ============================================================
    let listenState = null;

    function renderListening() {
      if (listenState && listenState.quiz) { renderListenQuiz(); return; }
      const L = t();
      let h = `<div class="section-title">🎧 ${L.tabs[1]}</div>
    <div class="section-sub">${L.listenSelect}</div>`;
      LISTENING.forEach((item, i) => {
        h += `<div class="card-sm" style="margin-bottom:12px" onclick="startListening(${i})">
      <div style="font-weight:700;font-size:15px;margin-bottom:4px">${item.title}</div>
      <div style="font-size:12px;color:var(--text3)">${item.qs.length} questions • 🎧 Audio</div>
    </div>`;
      });
      html('mainContent', h);
    }

    function startListening(i) {
      listenState = { idx: i, item: LISTENING[i], qidx: 0, score: 0, quiz: false, answered: false };
      const L = t();
      html('mainContent', `
    <div class="fade-in">
      <button class="btn btn-outline" style="margin-bottom:16px" onclick="listenState=null;renderListening()">← ${L.back}</button>
      <div class="section-title">${listenState.item.title}</div>
      <div class="reading-text">${listenState.item.text}</div>
      <div style="display:flex;gap:10px;margin-bottom:20px;flex-wrap:wrap">
        <button class="btn btn-primary" onclick="speak(LISTENING[${i}].text)">🔊 ${L.play}</button>
        <button class="btn btn-outline" onclick="speechSynthesis.cancel()">⏹ Stop</button>
      </div>
      <button class="btn btn-accent" style="width:100%;padding:14px" onclick="startListenQuiz()">
        📝 ${L.start}
      </button>
    </div>
  `);
    }

    function startListenQuiz() {
      listenState.quiz = true;
      listenState.qidx = 0;
      listenState.score = 0;
      listenState.answered = false;
      renderListenQuiz();
    }

    function renderListenQuiz() {
      const s = listenState;
      const L = t();
      if (s.qidx >= s.item.qs.length) {
        const pct = Math.round((s.score / s.item.qs.length) * 100);
        results.push({ topic: s.item.title, score: s.score, total: s.item.qs.length, pct, date: new Date().toLocaleDateString() });
        addXP(40);
        html('mainContent', `
      <div class="fade-in" style="text-align:center;padding:20px 0">
        <div style="font-size:48px;margin-bottom:12px">${pct >= 70 ? '🎉' : '💪'}</div>
        <div class="section-title">${L.yourScore}</div>
        <div class="score-big" style="margin:12px 0">${pct}%</div>
        <div style="color:var(--text2);margin-bottom:24px">${s.score} / ${s.item.qs.length}</div>
        <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap">
          <button class="btn btn-primary" onclick="startListenQuiz()">🔄 ${L.tryAgain}</button>
          <button class="btn btn-outline" onclick="listenState=null;renderListening()">← ${L.back}</button>
        </div>
      </div>
    `);
        return;
      }
      const q = s.item.qs[s.qidx];
      const pct = Math.round((s.qidx / s.item.qs.length) * 100);
      html('mainContent', `
    <div class="fade-in">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <button class="btn btn-outline" onclick="speechSynthesis.cancel();listenState=null;renderListening()">← ${L.back}</button>
        <span class="pill pill-purple">${L.question} ${s.qidx + 1} ${L.of} ${s.item.qs.length}</span>
      </div>
      <div class="progress-track" style="margin-bottom:16px">
        <div class="progress-fill" style="width:${pct}%"></div>
      </div>
      <div style="text-align:center;margin-bottom:12px">
        <button class="btn btn-outline" onclick="speak(LISTENING[${s.idx}].text)">🔊 ${L.listenAgain}</button>
      </div>
      <div class="card" style="margin-bottom:16px">
        <div style="font-size:16px;font-weight:700">${q.q}</div>
      </div>
      ${q.o.map((opt, i) => `<button class="quiz-opt" id="lopt${i}" onclick="selectListenOpt(${i})">${opt}</button>`).join('')}
      <div id="listenFeedback"></div>
    </div>
  `);
    }

    function selectListenOpt(chosen) {
      if (listenState.answered) return;
      listenState.answered = true;
      const q = listenState.item.qs[listenState.qidx];
      const correct = q.a;
      const L = t();
      const isCorrect = chosen === correct;
      if (isCorrect) { listenState.score++; addXP(10); }
      for (let i = 0; i < q.o.length; i++) {
        const btn = el('lopt' + i);
        if (!btn) continue;
        btn.classList.add('disabled');
        if (i === correct) btn.classList.add('correct');
        else if (i === chosen && !isCorrect) btn.classList.add('wrong');
      }
      el('listenFeedback').innerHTML = `
    <div style="text-align:center;padding:12px 0">
      <div style="font-size:22px">${isCorrect ? '✅' : '❌'}</div>
      <div style="font-weight:700;color:${isCorrect ? 'var(--accent2)' : 'var(--danger)'}">${isCorrect ? L.correct : L.wrong}</div>
      ${!isCorrect ? `<div style="font-size:13px;color:var(--text2)">Answer: ${q.o[correct]}</div>` : ''}
      <button class="btn btn-primary" style="margin-top:10px" onclick="nextListenQ()">${L.next} →</button>
    </div>
  `;
    }

    function nextListenQ() {
      listenState.qidx++;
      listenState.answered = false;
      renderListenQuiz();
    }

    // ============================================================
    // READING
    // ============================================================
    let readState = null;

    function renderReading() {
      if (readState && readState.quiz) { renderReadQuiz(); return; }
      const L = t();
      let h = `<div class="section-title">📰 ${L.tabs[2]}</div>
    <div class="section-sub">${L.readingSelect}</div>`;
      READING.forEach((item, i) => {
        h += `<div class="card-sm" style="margin-bottom:12px" onclick="startReading(${i})">
      <div style="font-weight:700;font-size:15px;margin-bottom:4px">${item.title}</div>
      <div style="font-size:12px;color:var(--text3)">${item.qs.length} questions • 📖 Reading</div>
    </div>`;
      });
      html('mainContent', h);
    }

    function startReading(i) {
      readState = { idx: i, item: READING[i], qidx: 0, score: 0, quiz: false, answered: false };
      const L = t();
      html('mainContent', `
    <div class="fade-in">
      <button class="btn btn-outline" style="margin-bottom:16px" onclick="readState=null;renderReading()">← ${L.back}</button>
      <div class="section-title">${readState.item.title}</div>
      <div class="reading-text">${readState.item.text}</div>
      <button class="btn btn-accent" style="width:100%;padding:14px" onclick="startReadQuiz()">
        📝 ${L.start}
      </button>
    </div>
  `);
    }

    function startReadQuiz() {
      readState.quiz = true;
      readState.qidx = 0;
      readState.score = 0;
      readState.answered = false;
      renderReadQuiz();
    }

    function renderReadQuiz() {
      const s = readState;
      const L = t();
      if (s.qidx >= s.item.qs.length) {
        const pct = Math.round((s.score / s.item.qs.length) * 100);
        results.push({ topic: s.item.title, score: s.score, total: s.item.qs.length, pct, date: new Date().toLocaleDateString() });
        addXP(40);
        html('mainContent', `
      <div class="fade-in" style="text-align:center;padding:20px 0">
        <div style="font-size:48px;margin-bottom:12px">${pct >= 70 ? '🎉' : '💪'}</div>
        <div class="section-title">${L.yourScore}</div>
        <div class="score-big" style="margin:12px 0">${pct}%</div>
        <div style="color:var(--text2);margin-bottom:24px">${s.score} / ${s.item.qs.length}</div>
        <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap">
          <button class="btn btn-primary" onclick="startReadQuiz()">🔄 ${L.tryAgain}</button>
          <button class="btn btn-outline" onclick="readState=null;renderReading()">← ${L.back}</button>
        </div>
      </div>
    `);
        return;
      }
      const q = s.item.qs[s.qidx];
      const pct = Math.round((s.qidx / s.item.qs.length) * 100);
      html('mainContent', `
    <div class="fade-in">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <button class="btn btn-outline" onclick="readState=null;renderReading()">← ${L.back}</button>
        <span class="pill pill-purple">${L.question} ${s.qidx + 1} ${L.of} ${s.item.qs.length}</span>
      </div>
      <div class="progress-track" style="margin-bottom:16px">
        <div class="progress-fill" style="width:${pct}%"></div>
      </div>
      <div class="card" style="margin-bottom:16px">
        <div style="font-size:16px;font-weight:700">${q.q}</div>
      </div>
      ${q.o.map((opt, i) => `<button class="quiz-opt" id="ropt${i}" onclick="selectReadOpt(${i})">${opt}</button>`).join('')}
      <div id="readFeedback"></div>
    </div>
  `);
    }

    function selectReadOpt(chosen) {
      if (readState.answered) return;
      readState.answered = true;
      const q = readState.item.qs[readState.qidx];
      const correct = q.a;
      const L = t();
      const isCorrect = chosen === correct;
      if (isCorrect) { readState.score++; addXP(10); }
      for (let i = 0; i < q.o.length; i++) {
        const btn = el('ropt' + i);
        if (!btn) continue;
        btn.classList.add('disabled');
        if (i === correct) btn.classList.add('correct');
        else if (i === chosen && !isCorrect) btn.classList.add('wrong');
      }
      el('readFeedback').innerHTML = `
    <div style="text-align:center;padding:12px 0">
      <div style="font-size:22px">${isCorrect ? '✅' : '❌'}</div>
      <div style="font-weight:700;color:${isCorrect ? 'var(--accent2)' : 'var(--danger)'}">${isCorrect ? L.correct : L.wrong}</div>
      ${!isCorrect ? `<div style="font-size:13px;color:var(--text2)">Answer: ${q.o[correct]}</div>` : ''}
      <button class="btn btn-primary" style="margin-top:10px" onclick="nextReadQ()">${L.next} →</button>
    </div>
  `;
    }

    function nextReadQ() {
      readState.qidx++;
      readState.answered = false;
      renderReadQuiz();
    }

    // ============================================================
    // SPEAKING
    // ============================================================
    let speakIdx = 0;

    function renderSpeaking() {
      const L = t();
      const prompt = SPEAKING[speakIdx];
      html('mainContent', `
    <div class="fade-in">
      <div class="section-title">🎤 ${L.speakTitle}</div>
      <div class="section-sub">${L.speakInstr}</div>
      <div class="speak-prompt-box">
        <div style="font-size:36px;margin-bottom:8px">❓</div>
        <div class="speak-prompt-text">"${prompt.prompt}"</div>
        <div class="speak-hint" style="margin-top:8px">💡 ${prompt.hint}</div>
        <button class="btn btn-primary" style="margin-top:14px" onclick="speak('${prompt.prompt.replace(/'/g, "\\'")}')">
          🔊 ${L.play}
        </button>
      </div>
      <div style="margin-bottom:12px">
        <div style="font-size:13px;color:var(--text2);margin-bottom:8px">Write your answer:</div>
        <textarea id="speakAnswer" placeholder="${prompt.hint}" style="width:100%;background:var(--surface);border:1.5px solid var(--border);border-radius:var(--radius-sm);padding:12px 14px;color:var(--text);font-family:'Sora',sans-serif;font-size:14px;min-height:80px;outline:none;resize:vertical;transition:border-color 0.2s" onfocus="this.style.borderColor='var(--primary)'" onblur="this.style.borderColor='var(--border)'"></textarea>
      </div>
      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <button class="btn btn-primary" onclick="checkSpeakAnswer()">✅ Check</button>
        <button class="btn btn-outline" onclick="showSpeakExample()">💡 Example</button>
        <button class="btn btn-outline" onclick="nextSpeakPrompt()">→ Next</button>
      </div>
      <div id="speakFeedback" style="margin-top:16px"></div>
      <div style="margin-top:16px;text-align:center;font-size:13px;color:var(--text3)">${speakIdx + 1} / ${SPEAKING.length}</div>
    </div>
  `);
    }

    function checkSpeakAnswer() {
      const ans = el('speakAnswer');
      if (!ans || !ans.value.trim()) return;
      const L = t();
      el('speakFeedback').innerHTML = `
    <div class="card" style="border-color:rgba(79,70,229,0.3)">
      <div style="font-size:13px;color:var(--text2);margin-bottom:6px">Getting AI feedback...</div>
      <div><span class="typing-dot"></span><span class="typing-dot"></span><span class="typing-dot"></span></div>
    </div>
  `;
      getAIFeedback(ans.value.trim(), SPEAKING[speakIdx].prompt);
    }

    async function getAIFeedback(answer, prompt) {
      try {
        const resp = await fetch('https://api.anthropic.com/v1/messages', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({
            model: 'claude-sonnet-4-20250514',
            max_tokens: 1000,
            system: 'You are a friendly English language teacher. Give brief, encouraging feedback on the student\'s answer. Point out what\'s good, what could be improved, and give a corrected version. Keep it short (3-4 sentences max). Always be positive and supportive.',
            messages: [{ role: 'user', content: `Question: "${prompt}"\nStudent's answer: "${answer}"\n\nPlease give feedback on this English answer.` }]
          })
        });
        const data = await resp.json();
        const text = data.content?.[0]?.text || 'Great effort! Keep practising!';
        el('speakFeedback').innerHTML = `
      <div class="card" style="border-color:rgba(16,185,129,0.3)">
        <div style="font-size:13px;color:var(--accent2);font-weight:700;margin-bottom:6px">🤖 AI Feedback</div>
        <div style="font-size:14px;line-height:1.6;color:var(--text)">${text}</div>
      </div>
    `;
        addXP(15);
      } catch (e) {
        el('speakFeedback').innerHTML = `<div class="card"><div style="color:var(--text2)">Good effort! Keep practising your English every day! 🌟</div></div>`;
      }
    }

    function showSpeakExample() {
      const p = SPEAKING[speakIdx];
      el('speakFeedback').innerHTML = `
    <div class="card" style="border-color:rgba(245,158,11,0.3)">
      <div style="font-size:13px;color:var(--accent);font-weight:700;margin-bottom:6px">💡 Example Answer</div>
      <div style="font-size:14px;color:var(--text)">"${p.example}"</div>
    </div>
  `;
    }

    function nextSpeakPrompt() {
      speakIdx = (speakIdx + 1) % SPEAKING.length;
      renderSpeaking();
    }

    // ============================================================
    // VOCABULARY
    // ============================================================
    function renderVocab() {
      const L = t();
      const cats = [...new Set(VOCAB.map(v => v.cat))];
      html('mainContent', `
    <div class="fade-in">
      <div class="section-title">📚 ${L.tabs[4]}</div>
      <input class="search-input" id="vocabSearch" placeholder="${L.vocabSearch}" oninput="filterVocab(this.value)">
      <div style="display:flex;gap:6px;flex-wrap:wrap;margin-bottom:16px" id="catFilters">
        <button class="btn btn-primary" style="padding:5px 12px;font-size:12px" onclick="filterVocab('',null)">All</button>
        ${cats.map(c => `<button class="btn btn-outline" style="padding:5px 12px;font-size:12px" onclick="filterVocab('','${c}')">${c}</button>`).join('')}
      </div>
      <div id="vocabGrid" class="grid-2"></div>
    </div>
  `);
      renderVocabGrid(VOCAB);
    }

    let vocabCatFilter = null;

    function filterVocab(search, cat) {
      if (cat !== undefined) vocabCatFilter = cat;
      const q = (search || el('vocabSearch')?.value || '').toLowerCase();
      const filtered = VOCAB.filter(v => {
        const matchCat = !vocabCatFilter || v.cat === vocabCatFilter;
        const matchQ = !q || v.en.includes(q) || v.ru.includes(q) || v.uz.includes(q) || v.tj.includes(q);
        return matchCat && matchQ;
      });
      renderVocabGrid(filtered);
    }

    function renderVocabGrid(list) {
      const grid = el('vocabGrid');
      if (!grid) return;
      if (!list.length) {
        grid.innerHTML = '<div class="empty-state"><div class="icon">🔍</div><div>No words found</div></div>';
        return;
      }
      grid.innerHTML = list.map(v => `
    <div class="vocab-card" onclick="speak('${v.en.replace(/'/g, "\\'")}')">
      <div class="vocab-en">${v.en}</div>
      <div class="vocab-tr">🇷🇺 ${v.ru}</div>
      <div class="vocab-tr">🇺🇿 ${v.uz}</div>
      <div class="vocab-tr">🇹🇯 ${v.tj}</div>
      <div class="vocab-cat">${v.cat}</div>
    </div>
  `).join('');
    }

    // ============================================================
    // AI CHAT
    // ============================================================
    function renderAI() {
      const L = t();
      html('mainContent', `
    <div class="chat-wrap fade-in">
      <div style="margin-bottom:12px">
        <div class="section-title">🤖 ${L.tabs[5]}</div>
      </div>
      <div class="chat-msgs" id="chatMsgs">
        <div class="chat-msg-ai">${L.aiWelcome}</div>
      </div>
      <div class="chat-input-row">
        <input class="chat-input" id="chatInput" placeholder="${L.aiPlaceholder}" onkeydown="if(event.key==='Enter')sendChat()">
        <button class="btn btn-primary" onclick="sendChat()">
          ${L.aiSend} ↑
        </button>
      </div>
    </div>
  `);
      // Restore history
      if (chatHistory.length) {
        const box = el('chatMsgs');
        chatHistory.forEach(m => {
          const div = document.createElement('div');
          div.className = m.role === 'user' ? 'chat-msg-user' : 'chat-msg-ai';
          div.textContent = m.content;
          box.appendChild(div);
        });
        box.scrollTop = box.scrollHeight;
      }
    }

    async function sendChat() {
      const inp = el('chatInput');
      if (!inp || !inp.value.trim()) return;
      const msg = inp.value.trim();
      inp.value = '';

      const box = el('chatMsgs');
      const userDiv = document.createElement('div');
      userDiv.className = 'chat-msg-user chat-msg';
      userDiv.textContent = msg;
      box.appendChild(userDiv);

      const typingDiv = document.createElement('div');
      typingDiv.className = 'chat-msg-ai chat-msg';
      typingDiv.innerHTML = '<span class="typing-dot"></span><span class="typing-dot"></span><span class="typing-dot"></span>';
      box.appendChild(typingDiv);
      box.scrollTop = box.scrollHeight;

      chatHistory.push({ role: 'user', content: msg });

      try {
        const resp = await fetch('https://api.anthropic.com/v1/messages', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({
            model: 'claude-sonnet-4-20250514',
            max_tokens: 1000,
            system: 'You are a friendly, encouraging English language tutor. Help students learn English grammar, vocabulary, pronunciation, and usage. Give clear, simple explanations with examples. Be concise and engaging. Use emojis occasionally to make learning fun.',
            messages: chatHistory.map(m => ({ role: m.role, content: m.content }))
          })
        });
        const data = await resp.json();
        const reply = data.content?.[0]?.text || 'Sorry, I had trouble answering. Please try again!';
        chatHistory.push({ role: 'assistant', content: reply });
        typingDiv.textContent = reply;
        typingDiv.className = 'chat-msg-ai chat-msg';
        addXP(5);
      } catch (e) {
        typingDiv.textContent = "I'm having connection issues. Please check your internet and try again!";
        chatHistory.push({ role: 'assistant', content: typingDiv.textContent });
      }
      box.scrollTop = box.scrollHeight;
    }

    // ============================================================
    // STATS
    // ============================================================
    function renderStats() {
      const L = t();
      if (!results.length) {
        html('mainContent', `
      <div class="fade-in">
        <div class="section-title">📊 ${L.statsTitle}</div>
        <div class="empty-state">
          <div class="icon">📭</div>
          <div>${L.noStats}</div>
        </div>
      </div>
    `);
        return;
      }
      const total = results.length;
      const avg = Math.round(results.reduce((s, r) => s + r.pct, 0) / total);
      const best = Math.max(...results.map(r => r.pct));

      // Build leaderboard from topics
      const byTopic = {};
      results.forEach(r => {
        if (!byTopic[r.topic] || r.pct > byTopic[r.topic]) byTopic[r.topic] = r.pct;
      });
      const lb = Object.entries(byTopic).sort((a, b) => b[1] - a[1]);

      html('mainContent', `
    <div class="fade-in">
      <div class="section-title">📊 ${L.statsTitle}</div>
      <div class="grid-3" style="margin-bottom:24px">
        <div class="stat-card">
          <div class="stat-num">${total}</div>
          <div class="stat-label">${L.totalTests}</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">${avg}%</div>
          <div class="stat-label">${L.avgScore}</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">${best}%</div>
          <div class="stat-label">${L.bestScore}</div>
        </div>
      </div>
      <div style="font-weight:700;margin-bottom:12px;font-size:15px">🏆 Best Scores by Topic</div>
      ${lb.slice(0, 10).map(([topic, pct], i) => `
        <div class="lb-row">
          <div class="lb-rank" style="color:${i === 0 ? '#fbbf24' : i === 1 ? '#94a3b8' : i === 2 ? '#cd7f32' : 'var(--text3)'}">${i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : i + 1}</div>
          <div class="lb-name">${topic}</div>
          <div class="lb-score">${pct}%</div>
        </div>
      `).join('')}
      <div style="margin-top:24px;font-weight:700;margin-bottom:12px;font-size:15px">📋 Recent Tests</div>
      ${results.slice().reverse().slice(0, 8).map(r => `
        <div class="result-item">
          <div>
            <div style="font-weight:600;font-size:13px">${r.topic}</div>
            <div style="font-size:11px;color:var(--text3)">${r.date}</div>
          </div>
          <div class="pill ${r.pct >= 70 ? 'pill-green' : 'pill-red'}">${r.pct}%</div>
        </div>
      `).join('')}
    </div>
  `);
    }

    // ============================================================
    // INIT
    // ============================================================
    renderAll();
  </script>
</body>

</html>
