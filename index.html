<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
  <title>職業治療關懷 — 每日天氣生活板與活力打地鼠</title>

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts for senior legibility -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@500;700;800;900&display=swap" rel="stylesheet">

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['"Noto Sans TC"', '-apple-system', 'sans-serif'],
          },
          colors: {
            board: {
              bg: '#F3EFE0',
              wood: '#8C6239',
              darkwood: '#5C3A21',
              felt: '#2E5B4B',
              cardBg: '#FFFDF7'
            }
          }
        }
      }
    }
  </script>

  <style>
    :root {
      --bg-color: #f0f4f8;
      --card-time-bg: #fff9db; /* 暖黃 - 現實導向區 */
      --card-time-border: #f59f00;
      --card-weather-bg: #e7f5ff; /* 天空藍 - 即時天氣 */
      --card-weather-border: #1c7ed6;
      --card-care-bg: #ebfbee; /* 草綠 - 關懷提示 */
      --card-care-border: #37b24d;
      --card-forecast-bg: #f3f0ff; /* 淡紫 - 未來預測 */
      --card-forecast-border: #748ffc;
      --card-practice-bg: #fffbf0; /* 暖金 - 練習區 */
      --card-practice-border: #d97706;
      --text-main: #121212;
      --text-muted: #333333;
      --alert-bg: #ffe3e3;
      --alert-border: #f03e3e;
      --alert-text: #c92a2a;
    }

    /* 特大字體模式 */
    body.large-font-mode {
      font-size: 120%;
    }
    body.large-font-mode .ro-label { font-size: 35px; }
    body.large-font-mode .ro-value-main { font-size: 46px; }
    body.large-font-mode .ro-value-time { font-size: 52px; }
    body.large-font-mode .temp-display { font-size: 64px; }
    body.large-font-mode .weather-info-text { font-size: 30px; }
    body.large-font-mode .forecast-date { font-size: 30px; }
    body.large-font-mode .forecast-temp { font-size: 48px; }
    body.large-font-mode .care-message-box { font-size: 34px; }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Noto Sans TC', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "PingFang HK", "Microsoft JhengHei", sans-serif;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-main);
      padding: 16px;
      line-height: 1.5;
      -webkit-text-size-adjust: 100%;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    header {
      text-align: center;
      background-color: #1a365d;
      color: #ffffff;
      padding: 20px 16px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }

    header h1 {
      font-size: 32px;
      font-weight: 800;
      letter-spacing: 1px;
    }

    .action-bar {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 14px;
    }

    .action-btn {
      background-color: #ffffff;
      color: #1a365d;
      border: 3px solid #ffffff;
      padding: 10px 20px;
      font-size: 20px;
      font-weight: 800;
      border-radius: 50px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
      transition: all 0.2s ease;
      min-height: 48px;
      touch-action: manipulation;
    }

    .action-btn:hover {
      background-color: #e2e8f0;
      transform: translateY(-2px);
    }

    .action-btn:active {
      transform: translateY(0);
    }

    .card {
      border-radius: 24px;
      padding: 20px;
      border: 4px solid;
      box-shadow: 0 6px 16px rgba(0,0,0,0.08);
      background-color: #ffffff;
    }

    /* 現實導向區 (Reality Orientation) */
    .ro-card {
      background-color: var(--card-time-bg);
      border-color: var(--card-time-border);
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .ro-header-bar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
      background: rgba(255, 255, 255, 0.85);
      padding: 12px 18px;
      border-radius: 16px;
      border: 2px solid var(--card-time-border);
    }

    .ro-title {
      font-size: 26px;
      font-weight: 800;
      color: #d9480f;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .location-setting-box {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .loc-field-group {
      display: flex;
      align-items: center;
      gap: 6px;
      flex-wrap: wrap;
    }

    .loc-field-group label {
      font-size: 20px;
      font-weight: 800;
      color: #2b8a3e;
      white-space: nowrap;
    }

    .fixed-district-badge {
      font-size: 20px;
      font-weight: 900;
      padding: 8px 16px;
      border-radius: 12px;
      background-color: #ffe8cc;
      color: #d9480f;
      border: 2px solid #f59f00;
      display: inline-block;
    }

    .location-input {
      font-size: 20px;
      font-weight: bold;
      padding: 8px 14px;
      border-radius: 12px;
      border: 2px solid #f59f00;
      background-color: #ffffff;
      color: #121212;
      outline: none;
      min-width: 200px;
      flex: 1;
    }

    .location-input:focus {
      border-color: #d9480f;
      box-shadow: 0 0 0 3px rgba(217, 72, 15, 0.2);
    }

    .ro-grid {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 14px;
    }

    .ro-label {
      font-size: 25px;
      font-weight: 800;
      color: #333333;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      width: 100%;
    }

    .ro-block {
      text-align: center;
      padding: 14px 10px;
      background-color: #ffffff;
      border-radius: 16px;
      border: 2px solid rgba(245, 159, 0, 0.5);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      min-height: 125px;
    }

    .col-loc-1 { grid-column: span 6; }
    .col-loc-2 { grid-column: span 6; }
    .col-year  { grid-column: span 3; }
    .col-month { grid-column: span 3; }
    .col-day   { grid-column: span 3; }
    .col-week  { grid-column: span 3; }
    .col-clock { grid-column: span 3; }
    .col-lunar { grid-column: span 3; }
    .col-season{ grid-column: span 3; }
    .col-festi { grid-column: span 3; }

    .ro-value-main {
      font-size: 38px;
      font-weight: 900;
      color: #121212;
      margin: auto 0;
      line-height: 1.1;
    }

    .ro-value-highlight {
      color: #d9480f;
    }

    .ro-value-time {
      font-size: 42px;
      font-weight: 900;
      color: #121212;
      font-family: 'Courier New', Courier, monospace;
      margin: auto 0;
      letter-spacing: 1px;
    }

    .ro-value-sub {
      font-size: 22px;
      font-weight: 800;
      color: #495057;
      margin-top: 4px;
    }

    .weather-card {
      background-color: var(--card-weather-bg);
      border-color: var(--card-weather-border);
    }

    .weather-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 14px;
      margin-bottom: 16px;
      border-bottom: 3px solid var(--card-weather-border);
      padding-bottom: 14px;
    }

    .district-select-container {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .district-select-container label {
      font-size: 24px;
      font-weight: 800;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    select.district-select {
      font-size: 22px;
      font-weight: bold;
      padding: 8px 16px;
      border-radius: 14px;
      border: 3px solid var(--card-weather-border);
      background-color: #ffffff;
      color: #121212;
      cursor: pointer;
      outline: none;
      min-height: 48px;
    }

    .weather-main-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
      text-align: center;
    }

    .weather-box {
      background: #ffffff;
      padding: 16px 12px;
      border-radius: 20px;
      border: 2px solid #a5d8ff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      text-align: center;
      min-height: 180px;
    }

    .weather-emoji-large {
      font-size: 58px;
      line-height: 1;
      margin: 6px auto;
    }

    .temp-display {
      font-size: 48px;
      font-weight: 900;
      color: #c92a2a;
      margin: auto 0;
    }

    .weather-info-text {
      font-size: 22px;
      font-weight: 700;
      margin-top: 4px;
    }

    .alert-container {
      margin-top: 16px;
      padding: 14px 20px;
      background-color: var(--alert-bg);
      border: 3px solid var(--alert-border);
      border-radius: 16px;
      display: none;
      align-items: center;
      justify-content: center;
      gap: 12px;
    }

    .alert-container.active {
      display: flex;
    }

    .alert-icon { font-size: 32px; }
    .alert-text {
      font-size: 22px;
      font-weight: 800;
      color: var(--alert-text);
      text-align: center;
    }

    .forecast-section { margin-top: 20px; }

    .forecast-title {
      font-size: 26px;
      font-weight: 800;
      margin-bottom: 12px;
      color: #3b5bdb;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .forecast-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
    }

    .forecast-card {
      background-color: var(--card-forecast-bg);
      border: 3px solid var(--card-forecast-border);
      border-radius: 20px;
      padding: 16px 12px;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      min-height: 180px;
    }

    .forecast-date {
      font-size: 25px;
      font-weight: 800;
      color: #1c7ed6;
    }

    .forecast-temp {
      font-size: 38px;
      font-weight: 900;
      color: #c92a2a;
      margin: auto 0;
      line-height: 1.1;
    }

    .care-card {
      background-color: var(--card-care-bg);
      border-color: var(--card-care-border);
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .care-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 14px;
    }

    .care-title {
      font-size: 28px;
      font-weight: 800;
      color: #2b8a3e;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .tts-btn {
      background-color: #2f9e44;
      color: #ffffff;
      border: none;
      padding: 14px 28px;
      font-size: 24px;
      font-weight: 900;
      border-radius: 50px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      box-shadow: 0 4px 12px rgba(47, 158, 68, 0.3);
      transition: transform 0.1s, background-color 0.2s;
      min-height: 52px;
      touch-action: manipulation;
    }

    .tts-btn:hover {
      background-color: #2b8a3e;
      transform: scale(1.02);
    }

    .tts-btn:active { transform: scale(0.98); }

    .tts-btn.speaking {
      background-color: #e03131;
      animation: pulse 1.2s infinite;
    }

    .practice-card {
      background-color: var(--card-practice-bg);
      border-color: var(--card-practice-border);
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .card-shadow {
      box-shadow: 0 6px 0px #C8B896, 0 10px 15px rgba(0,0,0,0.15);
    }

    .card-shadow:active, .card-shadow.active-touch {
      box-shadow: 0 2px 0px #C8B896, 0 4px 6px rgba(0,0,0,0.1);
      transform: translateY(4px);
    }

    .slot-shadow {
      box-shadow: inset 0 4px 8px rgba(0,0,0,0.3);
    }

    @keyframes slotPulse {
      0%, 100% { border-color: #3B82F6; box-shadow: 0 0 0 4px rgba(59, 130, 246, 0.4); }
      50% { border-color: #60A5FA; box-shadow: 0 0 0 8px rgba(59, 130, 246, 0.2); }
    }

    .slot-highlight {
      animation: slotPulse 1.5s infinite;
      background-color: #EFF6FF !important;
    }

    /* 打地鼠遊戲專用樣式 */
    .hole-container {
      position: relative;
      overflow: hidden;
      border-radius: 9999px;
      background: linear-gradient(180deg, #3d2314 0%, #653819 70%, #854d27 100%);
      box-shadow: inset 0 10px 15px rgba(0,0,0,0.6), 0 8px 0 #27150b;
    }

    .mole {
      position: absolute;
      left: 50%;
      bottom: -130%;
      transform: translateX(-50%) scale(0.9);
      transition: bottom 0.22s cubic-bezier(0.175, 0.885, 0.32, 1.275), transform 0.22s ease;
      cursor: pointer;
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: clamp(4.5rem, 14vw, 8.5rem);
      line-height: 1;
      filter: drop-shadow(0 6px 8px rgba(0,0,0,0.45));
      user-select: none;
      -webkit-user-select: none;
      touch-action: manipulation;
    }

    .mole.up {
      bottom: 0%;
      transform: translateX(-50%) scale(1.18);
    }

    .btn-3d {
      transition: all 0.1s ease;
      box-shadow: 0 6px 0 rgba(0,0,0,0.2);
    }
    .btn-3d:active {
      transform: translateY(4px);
      box-shadow: 0 2px 0 rgba(0,0,0,0.2);
    }

    @keyframes floatUp {
      0% { opacity: 1; transform: translate(-50%, 0) scale(0.8); }
      50% { transform: translate(-50%, -30px) scale(1.3); }
      100% { opacity: 0; transform: translate(-50%, -60px) scale(1); }
    }

    .score-float {
      position: absolute;
      top: 20%;
      left: 50%;
      color: #f59e0b;
      font-weight: 900;
      font-size: 2.5rem;
      text-shadow: 2px 2px 0 #ffffff, -2px -2px 0 #ffffff, 2px -2px 0 #ffffff, -2px 2px 0 #ffffff;
      pointer-events: none;
      animation: floatUp 0.8s ease-out forwards;
      z-index: 50;
    }

    #confetti-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 100;
    }

    @keyframes pulse {
      0% { opacity: 1; }
      50% { opacity: 0.7; }
      100% { opacity: 1; }
    }

    .care-message-box {
      background-color: #ffffff;
      padding: 20px;
      border-radius: 18px;
      border: 3px dashed var(--card-care-border);
      font-size: 26px;
      font-weight: 800;
      color: #212529;
      line-height: 1.6;
    }

    @media (max-width: 992px) {
      .col-year, .col-month, .col-day, .col-week,
      .col-clock, .col-lunar, .col-season, .col-festi {
        grid-column: span 6;
      }
    }

    @media (max-width: 768px) {
      body { padding: 10px; }
      header { padding: 16px 12px; }
      header h1 { font-size: 24px; }
      
      .action-btn { font-size: 18px; padding: 8px 16px; }
      .ro-header-bar { flex-direction: column; align-items: flex-start; }
      .location-setting-box { width: 100%; }
      .location-input { width: 100%; min-width: 0; }

      .col-loc-1, .col-loc-2 { grid-column: span 12; }
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-clock, .col-lunar { grid-column: span 12; }
      .col-season, .col-festi { grid-column: span 6; }

      .ro-label { font-size: 22px; }
      .ro-value-main { font-size: 32px; }
      .ro-value-time { font-size: 36px; }

      .district-select-container { width: 100%; }
      select.district-select { width: 100%; font-size: 20px; }

      .care-title { font-size: 24px; }
      .care-message-box { font-size: 22px; padding: 16px; }
      .tts-btn { font-size: 20px; width: 100%; }
      .forecast-grid { grid-template-columns: repeat(1, 1fr); }
    }

    @media (max-width: 480px) {
      .col-loc-1, .col-loc-2 { grid-column: span 12; }
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-season, .col-festi { grid-column: span 12; }
      .ro-value-main { font-size: 28px; }
      .ro-value-time { font-size: 30px; }
      .temp-display { font-size: 40px; }
    }
  </style>
</head>
<body>

  <canvas id="confetti-canvas"></canvas>

  <div class="container">
    <header>
      <h1>職業治療關懷 — 每日天氣生活板</h1>
      <div class="action-bar">
        <button class="action-btn" id="refresh-btn" onclick="refreshData()">
          <span id="refresh-icon" style="display:inline-flex;align-items:center;justify-content:center;">🔄</span> <span>開始/更新數據</span>
        </button>
        <button class="action-btn" id="zoom-btn" onclick="toggleFontSize()">
          <span style="display:inline-flex;align-items:center;justify-content:center;">🔍</span> <span id="zoom-text">特大字體</span>
        </button>
      </div>
    </header>

    <!-- 現實導向資訊區 -->
    <section class="card ro-card" aria-label="現實導向資訊">
      <div class="ro-header-bar">
        <div class="ro-title">
          <span>🧠</span>
          <span>現實導向資訊 (Reality Orientation)</span>
        </div>
        <div class="location-setting-box">
          <div class="loc-field-group">
            <label>📍 地區：</label>
            <span class="fixed-district-badge" id="fixed-district-label">深水埗</span>
          </div>
          <div class="loc-field-group" style="flex: 1; min-width: 240px;">
            <label for="location-detail-input">🏢 地點：</label>
            <input type="text" id="location-detail-input" class="location-input" value="社區中心 3樓大堂" placeholder="例如：敬老院 / 3樓大堂" oninput="updateCurrentLocationDisplay()">
          </div>
        </div>
      </div>

      <div class="ro-grid">
        <div class="ro-block col-loc-1">
          <div class="ro-label"><span>📍</span><span>地區</span></div>
          <div class="ro-value-main ro-value-highlight" id="ro-display-district">深水埗</div>
        </div>

        <div class="ro-block col-loc-2">
          <div class="ro-label"><span>🏢</span><span>地點</span></div>
          <div class="ro-value-main" id="ro-display-detail" style="color: #c92a2a;">社區中心 3樓大堂</div>
        </div>

        <div class="ro-block col-year">
          <div class="ro-label"><span>📅</span><span>年份</span></div>
          <div class="ro-value-main" id="ro-year">----年</div>
        </div>

        <div class="ro-block col-month">
          <div class="ro-label"><span>📆</span><span>月份</span></div>
          <div class="ro-value-main" id="ro-month">--月</div>
        </div>

        <div class="ro-block col-day">
          <div class="ro-label"><span>☀️</span><span>日期</span></div>
          <div class="ro-value-main ro-value-highlight" id="ro-date-num">--日</div>
        </div>

        <div class="ro-block col-week">
          <div class="ro-label"><span>🗓️</span><span>星期</span></div>
          <div class="ro-value-main" id="ro-day-of-week" style="color: #1864ab;">星期-</div>
        </div>

        <div class="ro-block col-clock">
          <div class="ro-label"><span>🕒</span><span>時間</span></div>
          <div class="ro-value-time" id="clock-time">--:--</div>
          <div class="ro-value-sub" id="clock-ampm">上午/下午</div>
        </div>

        <div class="ro-block col-lunar">
          <div class="ro-label"><span>🌾</span><span>農曆與節氣</span></div>
          <div class="ro-value-main" id="ro-lunar" style="font-size: 28px;">農曆 --月--</div>
          <div class="ro-value-sub" id="ro-solar-term" style="color: #d9480f;">節氣：--</div>
        </div>

        <div class="ro-block col-season">
          <div class="ro-label"><span>🍂</span><span>季節</span></div>
          <div style="display:flex; align-items:center; justify-content:center; gap:8px; margin: auto 0;">
            <span id="season-icon" style="font-size: 40px; line-height: 1;">🌱</span>
            <span class="ro-value-main" id="season-text" style="color: #2b8a3e;">--</span>
          </div>
        </div>

        <div class="ro-block col-festi">
          <div class="ro-label"><span>🎉</span><span>將到節日</span></div>
          <div class="ro-value-main" id="ro-festival-name" style="color: #c92a2a; font-size: 28px;">--</div>
          <div class="ro-value-sub" id="ro-festival-countdown">--</div>
        </div>
      </div>
    </section>

    <!-- 即時天氣區 -->
    <section class="card weather-card" aria-label="即時天氣">
      <div class="weather-header">
        <div class="district-select-container">
          <label for="district-select"><span>📍</span><span>選擇天氣分區：</span></label>
          <select id="district-select" class="district-select" onchange="onDistrictChange()">
            <option value="深水埗" selected>深水埗</option>
            <option value="沙田">沙田</option>
            <option value="香港天文台">尖沙咀 (天文台)</option>
            <option value="觀塘">觀塘</option>
            <option value="中赤鱲角">機場 (赤鱲角)</option>
            <option value="九龍城">九龍城</option>
            <option value="黃大仙">黃大仙</option>
            <option value="荃灣">荃灣</option>
            <option value="屯門">屯門</option>
            <option value="元朗">元朗</option>
            <option value="大埔">大埔</option>
            <option value="北區">粉嶺/上水</option>
            <option value="西貢">西貢</option>
            <option value="香港仔">香港仔</option>
            <option value="灣仔">灣仔</option>
            <option value="筲箕灣">東區 (筲箕灣)</option>
            <option value="赤柱">赤柱</option>
            <option value="將軍澳">將軍澳</option>
          </select>
        </div>
        <div style="font-size: 18px; color: var(--text-muted); font-weight: bold;">
          數據來源：香港天文台 API
        </div>
      </div>

      <div class="weather-main-grid">
        <div class="weather-box">
          <div class="ro-label"><span>☁️</span><span>天氣狀況</span></div>
          <div class="weather-emoji-large" id="weather-emoji">⛅</div>
          <div class="weather-info-text" id="weather-desc">多雲</div>
        </div>

        <div class="weather-box">
          <div class="ro-label"><span>🌡️</span><span>區域氣溫</span></div>
          <div class="temp-display"><span id="district-temp">--</span>°C</div>
          <div class="weather-info-text">全港平均: <span id="hk-mean-temp">--</span>°C</div>
        </div>

        <div class="weather-box">
          <div class="ro-label"><span>💧</span><span>相對濕度</span></div>
          <div class="temp-display" style="color: #1971c2;"><span id="humidity">--</span>%</div>
          <div class="weather-info-text" id="humidity-desc">舒適</div>
        </div>

        <div class="weather-box">
          <div class="ro-label"><span>☀️</span><span>紫外線指數</span></div>
          <div class="temp-display" style="color: #f59f00;"><span id="uv-index">--</span></div>
          <div class="weather-info-text" id="uv-desc">--</div>
        </div>

        <div class="weather-box" id="warning-weather-box" style="border-color: #2b8a3e;">
          <div class="ro-label"><span>🚨</span><span>極端天氣警告</span></div>
          <div id="warning-box-icon" style="font-size: 40px; margin: auto 0;">✅</div>
          <div class="weather-info-text" id="warning-box-desc" style="color: #2b8a3e; font-size: 20px;">現時無極端天氣警告</div>
        </div>
      </div>

      <div id="alert-container" class="alert-container">
        <div class="alert-icon">⚠️</div>
        <div class="alert-text" id="alert-text">目前生效警告：特別天氣提示</div>
      </div>

      <div class="forecast-section">
        <div class="forecast-title"><span>🔮</span><span>未來3日天氣預測</span></div>
        <div class="forecast-grid" id="forecast-grid">
          <div class="forecast-card">載入中...</div>
        </div>
      </div>
    </section>

    <!-- 關懷提示區 -->
    <section class="card care-card" aria-label="長者關懷提示">
      <div class="care-header">
        <div class="care-title">
          <span>💖 每日溫馨提示</span>
        </div>
        <button id="tts-btn" class="tts-btn" onclick="speakROAndWeather()">
          <span>🔊 聽語音（粵語朗讀）</span>
        </button>
      </div>

      <div class="care-message-box" id="care-message">
        正在為您生成今日天氣與生活關懷提示...
      </div>
    </section>

    <!-- 現實導向練習區 -->
    <section class="card practice-card" aria-label="現實導向練習區">
      <header class="bg-board-darkwood text-white rounded-2xl p-3 sm:p-4 shadow-md">
        <div class="flex flex-wrap items-center justify-between gap-2">
          <div class="flex items-center space-x-2">
            <span class="text-3xl sm:text-4xl">🗓️</span>
            <div>
              <h2 class="text-2xl sm:text-3xl font-black tracking-wide text-amber-200">現實導向練習版</h2>
              <p class="text-xs sm:text-sm text-amber-100 font-medium">看清問題，選擇卡片填入答案</p>
            </div>
          </div>

          <div class="flex items-center space-x-2 sm:space-x-3 text-sm">
            <div class="bg-amber-700/80 text-amber-100 font-bold px-3 py-2 rounded-xl text-sm sm:text-base flex items-center space-x-1 shadow">
              <span>📅 今日真實日期</span>
            </div>
            <button id="btn-audio-toggle" onclick="togglePracticeAudio()" class="bg-emerald-700 hover:bg-emerald-600 text-white font-bold px-3 py-2 rounded-xl text-sm sm:text-base flex items-center space-x-1 shadow transition">
              <span id="audio-icon">🔊</span>
              <span id="audio-label">聲音開</span>
            </button>
          </div>
        </div>
      </header>

      <div class="w-full flex-grow flex flex-col gap-4 mt-2">

        <div class="bg-white rounded-2xl p-3 shadow-md border-2 border-amber-200 flex flex-wrap sm:flex-nowrap justify-between items-center text-center gap-1.5 sm:gap-2">
          <div id="step-tab-1" onclick="goToStep(1)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-blue-500 bg-blue-50 min-w-[70px]">
            <span class="text-xs font-bold text-blue-700 block">第一關</span>
            <span class="text-sm sm:text-lg font-black text-blue-900">1. 月份</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <div id="step-tab-2" onclick="goToStep(2)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第二關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">2. 日期</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <div id="step-tab-3" onclick="goToStep(3)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第三關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">3. 星期</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <div id="step-tab-4" onclick="goToStep(4)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第四關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">4. 季節</span>
          </div>
        </div>

        <div class="bg-amber-100 border-3 border-amber-300 rounded-2xl p-4 shadow-sm flex flex-col sm:flex-row items-center justify-between gap-3 text-center sm:text-left">
          <div>
            <span id="question-badge" class="bg-blue-600 text-white text-xs font-bold px-2.5 py-1 rounded-full uppercase tracking-wider inline-block mb-1">
              第一題
            </span>
            <div id="question-text" class="text-2xl sm:text-3xl font-black text-amber-950">
              現在是幾月？
            </div>
          </div>
          <div class="flex items-center gap-2">
            <button onclick="readCurrentQuestionSpeech()" class="bg-blue-600 hover:bg-blue-700 active:scale-95 text-white font-bold px-4 py-2.5 rounded-xl text-base sm:text-lg flex items-center gap-1.5 shadow transition">
              🔊 語音念題目
            </button>
          </div>
        </div>

        <div class="bg-board-felt border-8 border-board-wood rounded-3xl p-4 sm:p-6 shadow-2xl relative">
          <div class="text-center mb-3">
            <h3 id="board-instruction" class="text-amber-100 text-lg sm:text-xl font-bold tracking-wider">點選或拖曳卡片放到框框內</h3>
          </div>

          <div id="view-step-1" class="flex flex-col items-center justify-center py-4">
            <div class="flex items-center gap-4 bg-board-darkwood/40 p-5 rounded-2xl border border-emerald-600/50 justify-center">
              <div id="slot-month" 
                   onclick="selectSlot('month')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'month')"
                   class="w-28 h-32 sm:w-32 sm:h-36 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative slot-highlight">
                <span class="text-amber-200/40 text-base font-bold pointer-events-none">放月份卡</span>
                <div id="slot-month-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
              <span class="text-5xl sm:text-6xl font-black text-amber-100 drop-shadow">月</span>
            </div>
          </div>

          <div id="view-step-2" class="hidden flex flex-col items-center justify-center py-4">
            <div class="flex items-center gap-4 bg-board-darkwood/40 p-5 rounded-2xl border border-emerald-600/50 justify-center">
              <div id="slot-day" 
                   onclick="selectSlot('day')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'day')"
                   class="w-28 h-32 sm:w-32 sm:h-36 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative">
                <span class="text-amber-200/40 text-base font-bold pointer-events-none">放日期卡</span>
                <div id="slot-day-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
              <span class="text-5xl sm:text-6xl font-black text-amber-100 drop-shadow">日</span>
            </div>
          </div>

          <div id="view-step-3" class="hidden flex flex-col items-center justify-center py-4">
            <div class="flex items-center gap-4 bg-board-darkwood/40 p-5 rounded-2xl border border-emerald-600/50 justify-center">
              <div id="slot-weekday" 
                   onclick="selectSlot('weekday')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'weekday')"
                   class="w-36 h-32 sm:w-44 sm:h-36 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative">
                <span class="text-amber-200/40 text-base font-bold pointer-events-none">放星期卡</span>
                <div id="slot-weekday-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
            </div>
          </div>

          <div id="view-step-4" class="hidden flex flex-col items-center justify-center py-4">
            <div class="flex items-center gap-4 bg-board-darkwood/40 p-5 rounded-2xl border border-emerald-600/50 justify-center">
              <div id="slot-season" 
                   onclick="selectSlot('season')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'season')"
                   class="w-36 h-32 sm:w-44 sm:h-36 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative">
                <span class="text-amber-200/40 text-base font-bold pointer-events-none">放季節卡</span>
                <div id="slot-season-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
            </div>
          </div>

          <div class="mt-6 flex flex-wrap items-center justify-center gap-3">
            <button onclick="checkCurrentStepAnswer()" class="bg-amber-400 hover:bg-amber-300 active:scale-95 text-amber-950 font-black text-xl sm:text-2xl px-8 py-3 rounded-2xl shadow-lg border-2 border-amber-200 flex items-center gap-2 transition">
              <span>✅ 確認答案</span>
            </button>
            <button onclick="resetCurrentStep()" class="bg-red-800/80 hover:bg-red-700 active:scale-95 text-white font-bold text-base sm:text-lg px-4 py-3 rounded-2xl shadow border border-red-500/50 flex items-center gap-1 transition">
              <span>🗑️ 重來</span>
            </button>
          </div>
        </div>

        <div class="bg-board-cardBg border-2 border-amber-200 rounded-3xl p-4 sm:p-5 shadow-lg">
          <div id="deck-header-title" class="text-lg sm:text-xl font-black text-gray-800 mb-3 flex items-center justify-between border-b border-amber-200 pb-2">
            <span>請點選正確答案（三選一）：</span>
            <span class="text-xs font-bold text-gray-500 hidden sm:inline">大字體適老簡化設計</span>
          </div>

          <div id="deck-options" class="grid grid-cols-3 gap-3 sm:gap-6 min-h-[120px]">
          </div>
        </div>

      </div>
    </section>

    <!-- 老友記活力打地鼠區 -->
    <section class="card mole-card bg-amber-50/60 border-amber-400" aria-label="老友記活力打地鼠">
      <header class="bg-gradient-to-r from-amber-600 to-orange-600 text-white rounded-2xl p-3 sm:p-4 shadow-md flex items-center justify-between gap-2 mb-4">
        <div class="flex items-center gap-2">
          <span class="text-3xl sm:text-4xl">🌻</span>
          <div>
            <h2 class="text-2xl sm:text-3xl font-black text-amber-100 leading-tight">老友記活力打地鼠</h2>
            <p class="text-xs sm:text-sm font-bold text-amber-200">放大版圖示，反應與專注力手眼協調訓練</p>
          </div>
        </div>
        <button id="openSettingsBtn" onclick="openMoleSettings()" class="bg-amber-100 hover:bg-amber-200 text-amber-900 px-3 py-2 rounded-xl border-2 border-amber-300 flex items-center gap-1.5 font-extrabold text-sm sm:text-base shadow transition">
          <span>⚙️</span>
          <span>遊戲設定</span>
        </button>
      </header>

      <div class="grid grid-cols-3 gap-2 sm:gap-4 mb-3">
        <div class="bg-gradient-to-br from-amber-400 to-orange-400 rounded-2xl p-2.5 sm:p-3 text-white text-center shadow-md border-b-4 border-orange-600">
          <div class="text-xs sm:text-sm font-extrabold opacity-90">得分</div>
          <div id="mole-scoreDisplay" class="text-3xl sm:text-4xl font-black tracking-wider drop-shadow">0</div>
        </div>

        <div id="mole-targetCard" class="bg-white rounded-2xl p-2.5 sm:p-3 text-center shadow-md border-2 border-emerald-400 flex flex-col justify-center items-center">
          <div class="text-xs sm:text-sm font-extrabold text-emerald-700">目標任務</div>
          <div id="mole-targetText" class="text-base sm:text-xl font-black text-emerald-900 leading-tight">請打地鼠</div>
        </div>

        <div class="bg-gradient-to-br from-sky-400 to-blue-500 rounded-2xl p-2.5 sm:p-3 text-white text-center shadow-md border-b-4 border-blue-700">
          <div class="text-xs sm:text-sm font-extrabold opacity-90">倒數時間</div>
          <div id="mole-timerDisplay" class="text-3xl sm:text-4xl font-black tracking-wider drop-shadow">30s</div>
        </div>
      </div>

      <div id="mole-feedbackBanner" class="bg-emerald-100 border-2 border-emerald-400 text-emerald-800 font-black text-center py-2 px-4 rounded-xl mb-4 text-sm sm:text-lg shadow-sm flex items-center justify-center gap-2 transition-all">
        <span>✨ 動物圖示已放大填滿圓形，點擊「開始遊戲」即可開玩！</span>
      </div>

      <!-- 8個洞口佈局 3 - 2 - 3 -->
      <div class="bg-emerald-700/20 backdrop-blur-sm p-3 sm:p-6 rounded-3xl border-4 border-emerald-500 shadow-inner my-auto flex flex-col gap-3 sm:gap-6 justify-center">
        <!-- Row 1: 3 Holes -->
        <div class="grid grid-cols-3 gap-2 sm:gap-6">
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-0" onclick="handleMoleHit(0, event)" ontouchstart="handleMoleHit(0, event)">🐹</div>
          </div>
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-1" onclick="handleMoleHit(1, event)" ontouchstart="handleMoleHit(1, event)">🐹</div>
          </div>
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-2" onclick="handleMoleHit(2, event)" ontouchstart="handleMoleHit(2, event)">🐹</div>
          </div>
        </div>

        <!-- Row 2: 2 Holes -->
        <div class="flex justify-center gap-3 sm:gap-8 px-6 sm:px-16">
          <div class="hole-container aspect-square w-1/3 relative">
            <div class="mole" id="mole-3" onclick="handleMoleHit(3, event)" ontouchstart="handleMoleHit(3, event)">🐹</div>
          </div>
          <div class="hole-container aspect-square w-1/3 relative">
            <div class="mole" id="mole-4" onclick="handleMoleHit(4, event)" ontouchstart="handleMoleHit(4, event)">🐹</div>
          </div>
        </div>

        <!-- Row 3: 3 Holes -->
        <div class="grid grid-cols-3 gap-2 sm:gap-6">
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-5" onclick="handleMoleHit(5, event)" ontouchstart="handleMoleHit(5, event)">🐹</div>
          </div>
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-6" onclick="handleMoleHit(6, event)" ontouchstart="handleMoleHit(6, event)">🐹</div>
          </div>
          <div class="hole-container aspect-square relative">
            <div class="mole" id="mole-7" onclick="handleMoleHit(7, event)" ontouchstart="handleMoleHit(7, event)">🐹</div>
          </div>
        </div>
      </div>

      <div class="mt-4 flex gap-3 justify-center">
        <button id="mole-startBtn" onclick="toggleStartMoleGame()" class="btn-3d bg-emerald-500 hover:bg-emerald-600 text-white font-black text-xl sm:text-2xl py-3.5 px-8 rounded-2xl border-b-4 border-emerald-700 flex items-center gap-2 shadow-lg w-full sm:w-auto justify-center">
          <span>▶️ 開始遊戲</span>
        </button>
        <button id="mole-speakPromptBtn" onclick="speakMolePrompt()" class="btn-3d bg-sky-500 hover:bg-sky-600 text-white font-black text-xl py-3.5 px-5 rounded-2xl border-b-4 border-sky-700 flex items-center justify-center gap-2 shadow-lg">
          <span>🔊</span>
          <span class="text-base hidden sm:inline">讀出提示</span>
        </button>
      </div>
    </section>

  </div>

  <!-- 練習結果 Modal -->
  <div id="result-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-white border-4 border-amber-400 rounded-3xl max-w-md w-full p-6 text-center shadow-2xl transform transition-all scale-95 opacity-0" id="modal-content">
      <div id="modal-icon" class="text-6xl mb-2">🎉</div>
      <h3 id="modal-title" class="text-3xl font-black text-gray-800 mb-2">好棒！答對了！</h3>
      <p id="modal-body" class="text-xl font-bold text-gray-600 mb-6">您答對了：<span id="modal-result-str" class="text-blue-700 underline">--</span></p>
      
      <div class="flex flex-col gap-3">
        <button id="modal-next-btn" onclick="closeModalAndContinue()" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white font-black text-xl py-3.5 rounded-2xl shadow-lg transition">
          🌟 自動進入下一題
        </button>
      </div>
    </div>
  </div>

  <!-- 打地鼠遊戲設定 Modal -->
  <div id="moleSettingsModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
    <div class="bg-white rounded-3xl p-6 max-w-md w-full shadow-2xl border-4 border-amber-400 space-y-5">
      <div class="flex justify-between items-center border-b pb-3 border-slate-200">
        <h2 class="text-2xl font-black text-amber-800 flex items-center gap-2">
          <span>⚙️</span> 打地鼠遊戲設定
        </h2>
        <button id="closeSettingsBtn" onclick="closeMoleSettings()" class="text-slate-400 hover:text-slate-600 text-2xl font-bold p-1">
          ✕
        </button>
      </div>

      <div>
        <label class="block font-black text-slate-700 text-base mb-2">🎮 選擇主題：</label>
        <div class="grid grid-cols-1 gap-2">
          <button class="mode-select-btn p-3 rounded-xl border-2 border-amber-400 bg-amber-50 font-bold text-left text-amber-900 flex items-center gap-3 transition" data-mode="classic" onclick="selectMoleMode('classic')">
            <span class="text-2xl">🐹</span>
            <div>
              <div>經典打地鼠</div>
              <div class="text-xs text-slate-500 font-normal">練吓反應同眼手協調</div>
            </div>
          </button>
          <button class="mode-select-btn p-3 rounded-xl border-2 border-slate-200 bg-white font-bold text-left text-slate-700 flex items-center gap-3 transition" data-mode="reality" onclick="selectMoleMode('reality')">
            <span class="text-2xl">☀️</span>
            <div>
              <div>現實導向 (天氣與季節)</div>
              <div class="text-xs text-slate-500 font-normal">跟指令搵出相應嘅天氣同季節</div>
            </div>
          </button>
          <button class="mode-select-btn p-3 rounded-xl border-2 border-slate-200 bg-white font-bold text-left text-slate-700 flex items-center gap-3 transition" data-mode="fruit" onclick="selectMoleMode('fruit')">
            <span class="text-2xl">🍎</span>
            <div>
              <div>開心水果派對</div>
              <div class="text-xs text-slate-500 font-normal">認吓同點擊新鮮好食嘅水果</div>
            </div>
          </button>
        </div>
      </div>

      <div>
        <label class="block font-black text-slate-700 text-base mb-2">⚡ 速度 (地鼠停留時間)：</label>
        <div class="grid grid-cols-3 gap-2">
          <button class="speed-btn p-2.5 rounded-xl border-2 border-amber-400 bg-amber-100 font-bold text-amber-900 text-center" data-speed="slow" onclick="selectMoleSpeed('slow')">
            慢速（輕鬆）
          </button>
          <button class="speed-btn p-2.5 rounded-xl border-2 border-slate-200 bg-white font-bold text-slate-700 text-center" data-speed="normal" onclick="selectMoleSpeed('normal')">
            普通
          </button>
          <button class="speed-btn p-2.5 rounded-xl border-2 border-slate-200 bg-white font-bold text-slate-700 text-center" data-speed="fast" onclick="selectMoleSpeed('fast')">
            快速
          </button>
        </div>
      </div>

      <div class="space-y-3 pt-2 border-t border-slate-200">
        <div class="flex items-center justify-between">
          <span class="font-bold text-slate-700">🎵 歡樂背景音樂：</span>
          <input type="checkbox" id="mole-musicToggle" checked class="w-6 h-6 accent-amber-500 cursor-pointer">
        </div>
        <div class="flex items-center justify-between">
          <span class="font-bold text-slate-700">🔊 遊戲點擊音效：</span>
          <input type="checkbox" id="mole-soundToggle" checked class="w-6 h-6 accent-amber-500 cursor-pointer">
        </div>
        <div class="flex items-center justify-between">
          <span class="font-bold text-slate-700">💬 廣東話朗讀同鼓勵：</span>
          <input type="checkbox" id="mole-voiceToggle" checked class="w-6 h-6 accent-amber-500 cursor-pointer">
        </div>
      </div>

      <button id="saveSettingsBtn" onclick="saveMoleSettings()" class="w-full bg-amber-500 hover:bg-amber-600 text-white font-black text-lg py-3 rounded-2xl border-b-4 border-amber-700 mt-2">
        儲存並套用
      </button>
    </div>
  </div>

  <script>
    /* =========================================================
       1. 現實導向與天文台數據 (Reality Orientation & HKO API)
       ========================================================= */

    function updateClockAndDate() {
      const now = new Date();
      
      let hoursInt = now.getHours();
      const ampm = hoursInt >= 12 ? '下午' : '上午';
      const hoursStr = String(hoursInt).padStart(2, '0');
      const minutesStr = String(now.getMinutes()).padStart(2, '0');
      
      document.getElementById('clock-time').textContent = `${hoursStr}:${minutesStr}`;
      document.getElementById('clock-ampm').textContent = `${ampm}`;

      const year = now.getFullYear();
      const month = now.getMonth() + 1;
      const date = now.getDate();
      const days = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
      const dayName = days[now.getDay()];

      document.getElementById('ro-year').textContent = `${year}年`;
      document.getElementById('ro-month').textContent = `${month}月`;
      document.getElementById('ro-date-num').textContent = `${date}日`;
      document.getElementById('ro-day-of-week').textContent = dayName;

      let season = '';
      let seasonIcon = '';
      if (month >= 3 && month <= 5) {
        season = '春季'; seasonIcon = '🌸';
      } else if (month >= 6 && month <= 8) {
        season = '夏季'; seasonIcon = '☀️';
      } else if (month >= 9 && month <= 11) {
        season = '秋季'; seasonIcon = '🍁';
      } else {
        season = '冬季'; seasonIcon = '❄️';
      }
      document.getElementById('season-icon').textContent = seasonIcon;
      document.getElementById('season-text').textContent = season;

      if (!window.lunarUpdatedDate || window.lunarUpdatedDate !== date) {
        updateLunarAndSolarTerm(now);
        updateUpcomingFestivals(now);
        window.lunarUpdatedDate = date;
      }
    }

    function onDistrictChange() {
      const selectedDistrict = document.getElementById('district-select').value;
      document.getElementById('fixed-district-label').textContent = selectedDistrict;
      document.getElementById('ro-display-district').textContent = selectedDistrict;
      updateDistrictTemperature();
    }

    function updateCurrentLocationDisplay() {
      const districtVal = document.getElementById('district-select').value;
      const detailVal = document.getElementById('location-detail-input').value.trim();
      
      document.getElementById('ro-display-district').textContent = districtVal;
      document.getElementById('ro-display-detail').textContent = detailVal || "未輸入地點";
      
      generateCareMessage();
    }

    function updateLunarAndSolarTerm(dateObj) {
      let lunarStr = '';

      try {
        const formatter = new Intl.DateTimeFormat('zh-HK-u-ca-chinese', {
          month: 'long',
          day: 'numeric'
        });
        const parts = formatter.formatToParts(dateObj);
        let mStr = '', dNum = 0;
        
        for (const p of parts) {
          if (p.type === 'month') mStr = p.value;
          if (p.type === 'day') dNum = parseInt(p.value, 10);
        }

        const monthMap = {
          '1': '正', '2': '二', '3': '三', '4': '四', '5': '五', '6': '六',
          '7': '七', '8': '八', '9': '九', '10': '十', '11': '十一', '12': '臘'
        };

        let formattedMonth = mStr;
        const cleanMStr = mStr.replace('月', '');
        if (cleanMStr.startsWith('閏')) {
          const num = cleanMStr.replace('閏', '');
          formattedMonth = '閏' + (monthMap[num] || num) + '月';
        } else if (monthMap[cleanMStr]) {
          formattedMonth = monthMap[cleanMStr] + '月';
        } else if (!formattedMonth.endsWith('月')) {
          formattedMonth += '月';
        }

        const nStr1 = ['日', '一', '二', '三', '四', '五', '六', '七', '八', '九', '十'];
        const nStr2 = ['初', '十', '廿', '卅'];
        let formattedDay = '';
        if (dNum === 10) formattedDay = '初十';
        else if (dNum === 20) formattedDay = '二十';
        else if (dNum === 30) formattedDay = '三十';
        else if (dNum > 0 && dNum <= 30) {
          formattedDay = nStr2[Math.floor(dNum / 10)] + nStr1[dNum % 10];
        } else {
          formattedDay = `${dNum}日`;
        }

        if (formattedMonth && formattedDay) {
          lunarStr = `農曆 ${formattedMonth}${formattedDay}`;
        }
      } catch (err) {
        lunarStr = '農曆 日期獲取中';
      }

      document.getElementById('ro-lunar').textContent = lunarStr;

      const currentTerm = getSolarTermForDate(dateObj);
      document.getElementById('ro-solar-term').textContent = `節氣：${currentTerm}`;
    }

    function getSolarTermForDate(dateObj) {
      const solarTerms = [
        "小寒", "大寒", "立春", "雨水", "驚蟄", "春分",
        "清明", "穀雨", "立夏", "小滿", "芒種", "夏至",
        "小暑", "大暑", "立秋", "處暑", "白露", "秋分",
        "寒露", "霜降", "立冬", "小雪", "大雪", "冬至"
      ];
      
      const m = dateObj.getMonth();
      const d = dateObj.getDate();
      let termIndex = m * 2;
      if (d >= 20) termIndex += 1;
      
      return solarTerms[termIndex % 24];
    }

    function updateUpcomingFestivals(now) {
      const year = now.getFullYear();
      
      const festivalList = [
        { name: "元旦", getTarget: (y) => new Date(y, 0, 1) },
        { name: "農曆新年", getTarget: (y) => new Date(y, 1, 10) },
        { name: "清明節", getTarget: (y) => new Date(y, 3, 4) },
        { name: "勞動節", getTarget: (y) => new Date(y, 4, 1) },
        { name: "端午節", getTarget: (y) => new Date(y, 5, 10) },
        { name: "香港特區成立紀念日", getTarget: (y) => new Date(y, 6, 1) },
        { name: "中秋節", getTarget: (y) => new Date(y, 8, 25) },
        { name: "國慶節", getTarget: (y) => new Date(y, 9, 1) },
        { name: "重陽節", getTarget: (y) => new Date(y, 9, 11) },
        { name: "冬至", getTarget: (y) => new Date(y, 11, 21) },
        { name: "聖誕節", getTarget: (y) => new Date(y, 11, 25) }
      ];

      let nearestFestival = null;
      let minDiffDays = Infinity;

      festivalList.forEach(f => {
        let target = f.getTarget(year);
        if (target - now < -86400000) {
          target = f.getTarget(year + 1);
        }

        const diffTime = target - now;
        const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));

        if (diffDays >= 0 && diffDays < minDiffDays) {
          minDiffDays = diffDays;
          nearestFestival = f.name;
        }
      });

      const nameElem = document.getElementById('ro-festival-name');
      const countElem = document.getElementById('ro-festival-countdown');

      if (nearestFestival) {
        nameElem.textContent = nearestFestival;
        if (minDiffDays === 0) {
          countElem.textContent = "🎉 今日就是節日！";
        } else {
          countElem.textContent = `還有 ${minDiffDays} 天`;
        }
      } else {
        nameElem.textContent = "平安健康";
        countElem.textContent = "每日好心情";
      }
    }

    let currentWeatherData = null;
    let forecastData = null;

    const districtNameMap = {
      "深水埗": ["深水埗", "九龍城"],
      "沙田": ["沙田"],
      "香港天文台": ["香港天文台", "九龍城"],
      "觀塘": ["觀塘"],
      "中赤鱲角": ["赤鱲角", "香港國際機場"],
      "九龍城": ["九龍城"],
      "黃大仙": ["黃大仙"],
      "荃灣": ["荃灣"],
      "屯門": ["屯門"],
      "元朗": ["元朗", "濕地公園"],
      "大埔": ["大埔"],
      "北區": ["上水", "打鼓嶺"],
      "西貢": ["西貢", "將軍澳"],
      "香港仔": ["香港仔", "黃竹坑"],
      "灣仔": ["跑馬地", "灣仔"],
      "筲箕灣": ["筲箕灣", "北角"],
      "赤柱": ["赤柱"],
      "將軍澳": ["將軍澳"]
    };

    async function fetchHKOData() {
      const rhrreadUrl = 'https://data.weather.gov.hk/weatherAPI/opendata/weather.php?dataType=rhrread&lang=tc';
      const fndUrl = 'https://data.weather.gov.hk/weatherAPI/opendata/weather.php?dataType=fnd&lang=tc';

      try {
        const [resRealtime, resForecast] = await Promise.all([
          fetch(rhrreadUrl),
          fetch(fndUrl)
        ]);

        if (!resRealtime.ok || !resForecast.ok) throw new Error('API 回應異常');

        currentWeatherData = await resRealtime.json();
        forecastData = await resForecast.json();

        renderWeatherUI();
        renderForecastUI();
      } catch (err) {
        loadMockData();
      }
    }

    function loadMockData() {
      currentWeatherData = {
        temperature: {
          data: [
            { place: "深水埗", value: 28 },
            { place: "沙田", value: 28 },
            { place: "香港天文台", value: 29 },
            { place: "觀塘", value: 28 },
            { place: "屯門", value: 29 }
          ]
        },
        humidity: { data: [{ value: 78 }] },
        uvindex: { data: [{ value: 6, desc: "高" }] },
        icon: [60],
        warningMessage: []
      };

      const daysOfWeek = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
      const mockForecast = [];
      const today = new Date();

      for (let i = 1; i <= 3; i++) {
        const nextDay = new Date(today);
        nextDay.setDate(today.getDate() + i);

        const yyyy = nextDay.getFullYear();
        const mm = String(nextDay.getMonth() + 1).padStart(2, '0');
        const dd = String(nextDay.getDate()).padStart(2, '0');

        mockForecast.push({
          forecastDate: `${yyyy}${mm}${dd}`,
          week: daysOfWeek[nextDay.getDay()],
          forecastmintemp: { value: 24 + (i % 3) },
          forecastmaxtemp: { value: 29 + (i % 3) },
          ForecastIcon: 50 + (i % 5)
        });
      }

      forecastData = { weatherForecast: mockForecast };

      renderWeatherUI();
      renderForecastUI();
    }

    function renderWeatherUI() {
      if (!currentWeatherData) return;

      if (currentWeatherData.humidity && currentWeatherData.humidity.data.length > 0) {
        const humVal = currentWeatherData.humidity.data[0].value;
        document.getElementById('humidity').textContent = humVal;
        
        let humDesc = '舒適';
        if (humVal > 80) humDesc = '潮濕';
        else if (humVal < 50) humDesc = '乾燥';
        document.getElementById('humidity-desc').textContent = humDesc;
      }

      if (currentWeatherData.uvindex && currentWeatherData.uvindex.data.length > 0) {
        const uvVal = currentWeatherData.uvindex.data[0].value;
        const uvDesc = currentWeatherData.uvindex.data[0].desc || '';
        document.getElementById('uv-index').textContent = uvVal;
        document.getElementById('uv-desc').textContent = uvDesc || '中等';
      } else {
        document.getElementById('uv-index').textContent = '0';
        document.getElementById('uv-desc').textContent = '無';
      }

      if (currentWeatherData.icon && currentWeatherData.icon.length > 0) {
        const mainIcon = currentWeatherData.icon[0];
        document.getElementById('weather-emoji').textContent = getWeatherEmojiByIcon(mainIcon);
        document.getElementById('weather-desc').textContent = getWeatherDescByIcon(mainIcon);
      }

      updateDistrictTemperature();

      const warningBoxIcon = document.getElementById('warning-box-icon');
      const warningBoxDesc = document.getElementById('warning-box-desc');
      const warningBox = document.getElementById('warning-weather-box');
      const alertContainer = document.getElementById('alert-container');
      const alertText = document.getElementById('alert-text');

      if (currentWeatherData.warningMessage && currentWeatherData.warningMessage.length > 0) {
        const msgs = currentWeatherData.warningMessage.join('； ');
        warningBoxIcon.textContent = '⚠️';
        warningBoxDesc.textContent = msgs;
        warningBoxDesc.style.color = '#c92a2a';
        warningBox.style.borderColor = '#f03e3e';

        alertContainer.classList.add('active');
        alertText.textContent = `生效警告：${msgs}`;
      } else {
        warningBoxIcon.textContent = '✅';
        warningBoxDesc.textContent = '現時無極端天氣警告';
        warningBoxDesc.style.color = '#2b8a3e';
        warningBox.style.borderColor = '#2b8a3e';

        alertContainer.classList.remove('active');
      }

      generateCareMessage();
    }

    function updateDistrictTemperature() {
      if (!currentWeatherData || !currentWeatherData.temperature) return;

      const selectedDistrict = document.getElementById('district-select').value;
      const tempDataList = currentWeatherData.temperature.data;

      let meanSum = 0;
      tempDataList.forEach(t => meanSum += t.value);
      const meanTemp = Math.round(meanSum / tempDataList.length);
      document.getElementById('hk-mean-temp').textContent = meanTemp;

      const aliases = districtNameMap[selectedDistrict] || [selectedDistrict];
      let foundTemp = null;

      for (const alias of aliases) {
        const item = tempDataList.find(t => t.place.includes(alias));
        if (item) {
          foundTemp = item.value;
          break;
        }
      }

      if (foundTemp === null) foundTemp = meanTemp;

      document.getElementById('district-temp').textContent = foundTemp;
      generateCareMessage();
    }

    function renderForecastUI() {
      if (!forecastData || !forecastData.weatherForecast) return;

      const grid = document.getElementById('forecast-grid');
      grid.innerHTML = '';

      const list = forecastData.weatherForecast.slice(0, 3);
      list.forEach(item => {
        const rawDate = item.forecastDate;
        const formattedDate = `${parseInt(rawDate.substring(4,6))}月${parseInt(rawDate.substring(6,8))}日`;
        const minTemp = item.forecastmintemp.value;
        const maxTemp = item.forecastmaxtemp.value;
        const icon = item.ForecastIcon;
        const forecastEmoji = getWeatherEmojiByIcon(icon);

        const card = document.createElement('div');
        card.className = 'forecast-card';
        card.innerHTML = `
          <div class="ro-label forecast-date"><span>📅</span><span>${formattedDate} (${item.week})</span></div>
          <div class="weather-emoji-large">${forecastEmoji}</div>
          <div class="forecast-temp">${minTemp}°C - ${maxTemp}°C</div>
        `;
        grid.appendChild(card);
      });
    }

    function getWeatherEmojiByIcon(icon) {
      if (icon >= 50 && icon <= 51) return '☀️';
      if (icon >= 52 && icon <= 54) return '⛅';
      if (icon >= 60 && icon <= 61) return '☁️';
      if (icon >= 62 && icon <= 64) return '🌧️';
      if (icon === 65) return '⛈️';
      if (icon === 70 || icon === 76) return '🌫️';
      if (icon === 80) return '💨';
      return '🌤️';
    }

    function getWeatherDescByIcon(icon) {
      const iconMap = {
        50: "陽光充沛", 51: "陽光璀璨", 52: "短暫陽光", 53: "間中有陽光", 54: "短暫陽光及驟雨",
        60: "多雲", 61: "密雲", 62: "微雨", 63: "雨勢驟降", 64: "大雨", 65: "雷暴",
        70: "乾燥", 76: "潮濕", 80: "大風"
      };
      return iconMap[icon] || "多雲有時有陽光";
    }

    function generateCareMessage() {
      const temp = parseInt(document.getElementById('district-temp').textContent) || 25;
      const humidity = parseInt(document.getElementById('humidity').textContent) || 70;
      const warnings = currentWeatherData?.warningMessage || [];
      const districtName = document.getElementById('district-select').value;
      
      const districtStr = document.getElementById('ro-display-district').textContent;
      const detailStr = document.getElementById('ro-display-detail').textContent;
      const fullLocation = (detailStr && detailStr !== "未輸入地點") ? `${districtStr} ${detailStr}` : districtStr;
      
      const festivalName = document.getElementById('ro-festival-name').textContent;

      let tips = [];

      tips.push(`老人家好，歡迎來到 ${fullLocation}！`);

      if (temp >= 30) {
        tips.push(`今日 ${districtName} 天氣酷熱，氣溫達到 ${temp} 度！記得留在室內，定時補充水分，避免戶外劇烈運動。`);
      } else if (temp <= 16) {
        tips.push(`今日天氣較為寒冷，${districtName} 氣溫只有 ${temp} 度。外出請穿著足夠保暖衣物，注意頭部與頸部保暖。`);
      } else {
        tips.push(`今日 ${districtName} 氣溫約 ${temp} 度，體感舒適宜人。`);
      }

      if (humidity > 85) {
        tips.push(`相對濕度高達 ${humidity}%，地板可能較為濕滑，行走請穿著防滑鞋，格外注意安全。`);
      } else if (humidity < 50) {
        tips.push(`天氣較為乾燥，記得多喝溫水保持滋潤。`);
      }

      if (warnings.some(w => w.includes('暴雨') || w.includes('雷暴'))) {
        tips.push(`目前有雷暴或雨勢警告，外出請務必帶傘，盡量留在安全室內。`);
      }

      if (festivalName && festivalName !== '--' && festivalName !== '平安健康') {
        tips.push(`臨近 ${festivalName}，祝您身體健康，保持愉快心情！`);
      }

      const finalMsg = tips.join(' ');
      document.getElementById('care-message').textContent = finalMsg;
    }

    function speakROAndWeather() {
      if (!('speechSynthesis' in window)) {
        alert('您的瀏覽器不支援語音朗讀功能。');
        return;
      }

      const ttsBtn = document.getElementById('tts-btn');

      if (window.speechSynthesis.speaking) {
        window.speechSynthesis.cancel();
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
        return;
      }

      const districtStr = document.getElementById('ro-display-district').textContent;
      const detailStr = document.getElementById('ro-display-detail').textContent;
      const locationSpeech = (detailStr && detailStr !== "未輸入地點") ? `${districtStr} ${detailStr}` : districtStr;

      const yearStr = document.getElementById('ro-year').textContent;
      const monthStr = document.getElementById('ro-month').textContent;
      const dateStr = document.getElementById('ro-date-num').textContent;
      const dayStr = document.getElementById('ro-day-of-week').textContent;
      const lunarStr = document.getElementById('ro-lunar').textContent;
      const careMsg = document.getElementById('care-message').textContent;

      const fullSpeechText = `早晨！現在地點是${locationSpeech}。今天是${yearStr}${monthStr}${dateStr}，${dayStr}，${lunarStr}。 ${careMsg}`;

      const utterance = new SpeechSynthesisUtterance(fullSpeechText);
      utterance.lang = 'zh-HK';
      utterance.rate = 0.85;

      utterance.onstart = () => {
        ttsBtn.classList.add('speaking');
        ttsBtn.querySelector('span').textContent = '⏹️ 停止朗讀';
      };

      utterance.onend = () => {
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
      };

      utterance.onerror = () => {
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
      };

      window.speechSynthesis.speak(utterance);
    }

    function toggleFontSize() {
      document.body.classList.toggle('large-font-mode');
      const zoomText = document.getElementById('zoom-text');
      if (document.body.classList.contains('large-font-mode')) {
        zoomText.textContent = '還原字體';
      } else {
        zoomText.textContent = '特大字體';
      }
    }

    function refreshData() {
      const icon = document.getElementById('refresh-icon');
      icon.style.transition = 'transform 0.5s';
      icon.style.transform = 'rotate(360deg)';
      
      updateClockAndDate();
      fetchHKOData();

      setTimeout(() => {
        icon.style.transform = 'rotate(0deg)';
      }, 500);
    }

    /* =========================================================
       2. 現實導向練習區 (Reality Orientation Practice)
       ========================================================= */

    const WEEKDAYS_ZH = ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"];
    const SEASONS_DATA = [
      { name: "春天", icon: "🌸", color: "bg-pink-100 border-pink-400 text-pink-900" },
      { name: "夏天", icon: "☀️", color: "bg-amber-100 border-amber-400 text-amber-900" },
      { name: "秋天", icon: "🍁", color: "bg-orange-100 border-orange-400 text-orange-900" },
      { name: "冬天", icon: "❄️", color: "bg-blue-100 border-blue-400 text-blue-900" }
    ];

    function getSeasonIndexByMonth(month) {
      if (month >= 3 && month <= 5) return 0;
      if (month >= 6 && month <= 8) return 1;
      if (month >= 9 && month <= 11) return 2;
      return 3;
    }

    let practiceState = {
      currentStep: 1,
      target: {
        month: 1,
        day: 1,
        weekday: 0,
        season: 0
      },
      currentStepOptions: [],
      selectedSlot: 'month',
      userAnswers: {
        month: null,
        day: null,
        weekday: null,
        season: null
      },
      audioEnabled: true,
      speechSupported: 'speechSynthesis' in window
    };

    let practiceAudioCtx = null;

    function initPracticeAudioContext() {
      if (!practiceAudioCtx) {
        practiceAudioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
      if (practiceAudioCtx.state === 'suspended') {
        practiceAudioCtx.resume();
      }
    }

    function playPopSound() {
      if (!practiceState.audioEnabled) return;
      initPracticeAudioContext();
      try {
        const osc = practiceAudioCtx.createOscillator();
        const gain = practiceAudioCtx.createGain();
        osc.type = 'sine';
        osc.frequency.setValueAtTime(400, practiceAudioCtx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(800, practiceAudioCtx.currentTime + 0.08);
        gain.gain.setValueAtTime(0.3, practiceAudioCtx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, practiceAudioCtx.currentTime + 0.08);
        osc.connect(gain);
        gain.connect(practiceAudioCtx.destination);
        osc.start();
        osc.stop(practiceAudioCtx.currentTime + 0.08);
      } catch (e) {}
    }

    function playSuccessFanfare() {
      if (!practiceState.audioEnabled) return;
      initPracticeAudioContext();
      try {
        const notes = [523.25, 659.25, 783.99, 1046.50];
        notes.forEach((freq, idx) => {
          const osc = practiceAudioCtx.createOscillator();
          const gain = practiceAudioCtx.createGain();
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(freq, practiceAudioCtx.currentTime + idx * 0.12);
          gain.gain.setValueAtTime(0.25, practiceAudioCtx.currentTime + idx * 0.12);
          gain.gain.exponentialRampToValueAtTime(0.001, practiceAudioCtx.currentTime + idx * 0.12 + 0.35);
          osc.connect(gain);
          gain.connect(practiceAudioCtx.destination);
          osc.start(practiceAudioCtx.currentTime + idx * 0.12);
          osc.stop(practiceAudioCtx.currentTime + idx * 0.12 + 0.35);
        });
      } catch (e) {}
    }

    function playErrorSound() {
      if (!practiceState.audioEnabled) return;
      initPracticeAudioContext();
      try {
        const osc = practiceAudioCtx.createOscillator();
        const gain = practiceAudioCtx.createGain();
        osc.type = 'sawtooth';
        osc.frequency.setValueAtTime(220, practiceAudioCtx.currentTime);
        osc.frequency.linearRampToValueAtTime(180, practiceAudioCtx.currentTime + 0.2);
        gain.gain.setValueAtTime(0.2, practiceAudioCtx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, practiceAudioCtx.currentTime + 0.2);
        osc.connect(gain);
        gain.connect(practiceAudioCtx.destination);
        osc.start();
        osc.stop(practiceAudioCtx.currentTime + 0.2);
      } catch (e) {}
    }

    function speakPracticeText(text) {
      if (!practiceState.audioEnabled || !practiceState.speechSupported) return;
      window.speechSynthesis.cancel();
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.lang = 'zh-HK';
      utterance.rate = 0.85;
      utterance.pitch = 1.0;
      window.speechSynthesis.speak(utterance);
    }

    function initTodayTarget() {
      const now = new Date();
      practiceState.target.month = now.getMonth() + 1;
      practiceState.target.day = now.getDate();
      practiceState.target.weekday = now.getDay();
      practiceState.target.season = getSeasonIndexByMonth(practiceState.target.month);
    }

    function togglePracticeAudio() {
      practiceState.audioEnabled = !practiceState.audioEnabled;
      const label = document.getElementById('audio-label');
      const icon = document.getElementById('audio-icon');
      if (practiceState.audioEnabled) {
        label.textContent = '聲音開';
        icon.textContent = '🔊';
        speakPracticeText('聲音已開啟');
      } else {
        label.textContent = '聲音關';
        icon.textContent = '🔇';
        window.speechSynthesis.cancel();
      }
    }

    function goToStep(stepNum) {
      practiceState.currentStep = stepNum;

      for (let i = 1; i <= 4; i++) {
        const tab = document.getElementById(`step-tab-${i}`);
        if (tab) {
          if (i === stepNum) {
            tab.className = "flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-blue-500 bg-blue-50 shadow-sm scale-105 min-w-[70px]";
          } else {
            tab.className = "flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]";
          }
        }
      }

      document.getElementById('view-step-1').classList.add('hidden');
      document.getElementById('view-step-2').classList.add('hidden');
      document.getElementById('view-step-3').classList.add('hidden');
      document.getElementById('view-step-4').classList.add('hidden');

      const badge = document.getElementById('question-badge');
      const qText = document.getElementById('question-text');

      if (stepNum === 1) {
        badge.textContent = "第一題";
        qText.textContent = "現在是幾月？";
        document.getElementById('view-step-1').classList.remove('hidden');
        selectSlot('month');
        speakPracticeText("第一題：現在是幾月？");
      } else if (stepNum === 2) {
        badge.textContent = "第二題";
        qText.textContent = "現在是幾日？";
        document.getElementById('view-step-2').classList.remove('hidden');
        selectSlot('day');
        speakPracticeText("第二題：現在是幾日？");
      } else if (stepNum === 3) {
        badge.textContent = "第三題";
        qText.textContent = "今天是星期幾？";
        document.getElementById('view-step-3').classList.remove('hidden');
        selectSlot('weekday');
        speakPracticeText("第三題：今天是星期幾？");
      } else if (stepNum === 4) {
        badge.textContent = "第四題";
        qText.textContent = "現在是什麼季節？";
        document.getElementById('view-step-4').classList.remove('hidden');
        selectSlot('season');
        speakPracticeText("第四題：現在是什麼季節？");
      }

      renderDeckOptions();
    }

    function selectSlot(slotType) {
      practiceState.selectedSlot = slotType;
      document.querySelectorAll('[id^="slot-"]').forEach(el => {
        el.classList.remove('slot-highlight');
      });
      const targetSlot = document.getElementById(`slot-${slotType}`);
      if (targetSlot) targetSlot.classList.add('slot-highlight');
    }

    function generateThreeOptions(correctVal, min, max, suffix = '') {
      let options = [correctVal];
      while (options.length < 3) {
        let rand = Math.floor(Math.random() * (max - min + 1)) + min;
        if (!options.includes(rand)) {
          options.push(rand);
        }
      }
      options.sort(() => Math.random() - 0.5);
      return options.map(v => ({ value: v, label: `${v}${suffix}` }));
    }

    function renderDeckOptions() {
      const container = document.getElementById('deck-options');
      if (!container) return;
      container.innerHTML = '';

      let options = [];
      const step = practiceState.currentStep;

      if (step === 1) {
        options = generateThreeOptions(practiceState.target.month, 1, 12, '月');
      } else if (step === 2) {
        options = generateThreeOptions(practiceState.target.day, 1, 31, '日');
      } else if (step === 3) {
        let correctW = practiceState.target.weekday;
        let pool = [0, 1, 2, 3, 4, 5, 6].filter(w => w !== correctW);
        pool.sort(() => Math.random() - 0.5);
        let selected = [correctW, pool[0], pool[1]].sort(() => Math.random() - 0.5);
        options = selected.map(w => ({ value: w, label: WEEKDAYS_ZH[w] }));
      } else if (step === 4) {
        let correctS = practiceState.target.season;
        let pool = [0, 1, 2, 3].filter(s => s !== correctS);
        pool.sort(() => Math.random() - 0.5);
        let selected = [correctS, pool[0], pool[1]].sort(() => Math.random() - 0.5);
        options = selected.map(s => ({ value: s, label: `${SEASONS_DATA[s].icon} ${SEASONS_DATA[s].name}` }));
      }

      practiceState.currentStepOptions = options;

      options.forEach(opt => {
        const card = document.createElement('div');
        card.className = "bg-amber-100 border-4 border-amber-300 hover:border-amber-500 rounded-2xl p-4 flex items-center justify-center text-center cursor-pointer card-shadow transition active:scale-95 min-h-[90px]";
        card.setAttribute('draggable', 'true');
        card.onclick = () => selectCardOption(opt);
        card.ondragstart = (e) => handleDragStart(e, JSON.stringify(opt));

        card.innerHTML = `<span class="text-2xl sm:text-3xl font-black text-amber-950">${opt.label}</span>`;
        container.appendChild(card);
      });
    }

    function selectCardOption(opt) {
      playPopSound();
      const step = practiceState.currentStep;
      let slotType = step === 1 ? 'month' : step === 2 ? 'day' : step === 3 ? 'weekday' : 'season';
      
      practiceState.userAnswers[slotType] = opt;
      
      const contentEl = document.getElementById(`slot-${slotType}-content`);
      if (contentEl) {
        contentEl.innerHTML = `<span class="text-2xl sm:text-3xl font-black text-amber-200">${opt.label}</span>`;
      }
    }

    function allowDrop(ev) { ev.preventDefault(); }
    function handleDragStart(ev, dataStr) { ev.dataTransfer.setData("text/plain", dataStr); }
    function handleDrop(ev, slotType) {
      ev.preventDefault();
      const dataStr = ev.dataTransfer.getData("text/plain");
      if (dataStr) {
        try {
          const opt = JSON.parse(dataStr);
          practiceState.currentStep = slotType === 'month' ? 1 : slotType === 'day' ? 2 : slotType === 'weekday' ? 3 : 4;
          selectCardOption(opt);
        } catch(e) {}
      }
    }

    function resetCurrentStep() {
      const step = practiceState.currentStep;
      let slotType = step === 1 ? 'month' : step === 2 ? 'day' : step === 3 ? 'weekday' : 'season';
      practiceState.userAnswers[slotType] = null;
      const contentEl = document.getElementById(`slot-${slotType}-content`);
      if (contentEl) contentEl.innerHTML = '';
      speakPracticeText("已重置答案");
    }

    function readCurrentQuestionSpeech() {
      const step = practiceState.currentStep;
      if (step === 1) speakPracticeText("第一題：現在是幾月？");
      else if (step === 2) speakPracticeText("第二題：現在是幾日？");
      else if (step === 3) speakPracticeText("第三題：今天是星期幾？");
      else if (step === 4) speakPracticeText("第四題：現在是什麼季節？");
    }

    function checkCurrentStepAnswer() {
      const step = practiceState.currentStep;
      let slotType = step === 1 ? 'month' : step === 2 ? 'day' : step === 3 ? 'weekday' : 'season';
      let userAns = practiceState.userAnswers[slotType];

      if (!userAns) {
        playErrorSound();
        speakPracticeText("請先點選卡片填入答案喔！");
        return;
      }

      let isCorrect = false;
      let targetText = "";

      if (step === 1) {
        isCorrect = (userAns.value === practiceState.target.month);
        targetText = `${practiceState.target.month}月`;
      } else if (step === 2) {
        isCorrect = (userAns.value === practiceState.target.day);
        targetText = `${practiceState.target.day}日`;
      } else if (step === 3) {
        isCorrect = (userAns.value === practiceState.target.weekday);
        targetText = WEEKDAYS_ZH[practiceState.target.weekday];
      } else if (step === 4) {
        isCorrect = (userAns.value === practiceState.target.season);
        targetText = SEASONS_DATA[practiceState.target.season].name;
      }

      if (isCorrect) {
        playSuccessFanfare();
        triggerConfetti();
        showModal(true, targetText);
      } else {
        playErrorSound();
        showModal(false, targetText);
      }
    }

    function showModal(isCorrect, targetText) {
      const modal = document.getElementById('result-modal');
      const content = document.getElementById('modal-content');
      const icon = document.getElementById('modal-icon');
      const title = document.getElementById('modal-title');
      const body = document.getElementById('modal-body');

      if (isCorrect) {
        icon.textContent = "🎉";
        title.textContent = "太棒了！答對了！";
        body.innerHTML = `正確答案就是：<span id="modal-result-str" class="text-emerald-700 underline font-black">${targetText}</span>`;
        speakPracticeText(`恭喜答對！答案就是 ${targetText}`);
      } else {
        icon.textContent = "💪";
        title.textContent = "再試一次喔！";
        body.innerHTML = `正確答案應該是：<span id="modal-result-str" class="text-amber-700 underline font-black">${targetText}</span>`;
        speakPracticeText(`加油，正確答案是 ${targetText}，再試看看！`);
      }

      modal.classList.remove('hidden');
      setTimeout(() => {
        content.classList.remove('scale-95', 'opacity-0');
        content.classList.add('scale-100', 'opacity-100');
      }, 10);
    }

    function closeModalAndContinue() {
      const modal = document.getElementById('result-modal');
      const content = document.getElementById('modal-content');
      content.classList.remove('scale-100', 'opacity-100');
      content.classList.add('scale-95', 'opacity-0');

      setTimeout(() => {
        modal.classList.add('hidden');
        if (practiceState.currentStep < 4) {
          goToStep(practiceState.currentStep + 1);
        } else {
          speakPracticeText("太厲害了！你完成所有練習關卡囉！");
        }
      }, 200);
    }

    function triggerConfetti() {
      const canvas = document.getElementById('confetti-canvas');
      if (!canvas) return;
      const ctx = canvas.getContext('2d');
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;

      let particles = [];
      const colors = ['#f59e0b', '#10b981', '#3b82f6', '#ec4899', '#8b5cf6'];

      for (let i = 0; i < 60; i++) {
        particles.push({
          x: Math.random() * canvas.width,
          y: Math.random() * canvas.height * 0.5,
          r: Math.random() * 8 + 4,
          vx: (Math.random() - 0.5) * 6,
          vy: Math.random() * 4 + 2,
          color: colors[Math.floor(Math.random() * colors.length)]
        });
      }

      let frame = 0;
      function render() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        particles.forEach(p => {
          ctx.beginPath();
          ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
          ctx.fillStyle = p.color;
          ctx.fill();
          p.x += p.vx;
          p.y += p.vy;
        });

        frame++;
        if (frame < 60) {
          requestAnimationFrame(render);
        } else {
          ctx.clearRect(0, 0, canvas.width, canvas.height);
        }
      }
      render();
    }

    /* =========================================================
       3. 打地鼠專注力遊戲 (Whack-a-Mole Game)
       ========================================================= */

    let moleState = {
      score: 0,
      timeLeft: 30,
      gameTimer: null,
      countdownTimer: null,
      isPlaying: false,
      activeHole: -1,
      currentMode: 'classic',
      currentSpeed: 'slow',
      soundEnabled: true,
      musicEnabled: true,
      voiceEnabled: true,
      currentRealityTarget: null
    };

    const MOLE_THEMES = {
      classic: {
        name: '經典打地鼠',
        items: ['🐹', '🐭', '🐰', '🦔']
      },
      fruit: {
        name: '開心水果派對',
        items: ['🍎', '🍌', '🍊', '🍇', '🍓', '🍉']
      },
      reality: {
        name: '現實導向認知',
        dataset: [
          { icon: '☀️', label: '晴天大太陽' },
          { icon: '🌧️', label: '落雨天' },
          { icon: '🌸', label: '春天花花' },
          { icon: '🍁', label: '秋天紅葉' },
          { icon: '❄️', label: '冬天雪花' },
          { icon: '🌙', label: '夜晚月亮' }
        ]
      }
    };

    const MOLE_PRAISES = [
      "好厲害！好有專注力！",
      "打得好！手快眼快！",
      "真係精靈！繼續加油！",
      "好嘢！眼手協調一級棒！",
      "好有精神！真係好叻！"
    ];

    let moleAudioCtx = null;
    let moleBgmInterval = null;
    let moleBgmStep = 0;
    const moleBgmNotes = [
      261.63, 329.63, 392.00, 523.25, 392.00, 329.63,
      293.66, 349.23, 440.00, 523.25, 440.00, 349.23,
      261.63, 329.63, 392.00, 440.00, 523.25, 392.00,
      349.23, 329.63, 293.66, 261.63
    ];

    function initMoleAudioContext() {
      if (!moleAudioCtx) {
        moleAudioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
      if (moleAudioCtx.state === 'suspended') {
        moleAudioCtx.resume();
      }
    }

    function playMoleBgmNote() {
      if (!moleState.musicEnabled || !moleState.isPlaying) return;
      try {
        initMoleAudioContext();
        const osc = moleAudioCtx.createOscillator();
        const gain = moleAudioCtx.createGain();
        
        const freq = moleBgmNotes[moleBgmStep % moleBgmNotes.length];
        moleBgmStep++;

        osc.type = 'triangle';
        osc.frequency.setValueAtTime(freq, moleAudioCtx.currentTime);
        
        gain.gain.setValueAtTime(0.04, moleAudioCtx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.001, moleAudioCtx.currentTime + 0.28);
        
        osc.connect(gain);
        gain.connect(moleAudioCtx.destination);
        
        osc.start();
        osc.stop(moleAudioCtx.currentTime + 0.28);
      } catch(e) {}
    }

    function startMoleBgm() {
      stopMoleBgm();
      if (!moleState.musicEnabled) return;
      moleBgmStep = 0;
      moleBgmInterval = setInterval(playMoleBgmNote, 320);
    }

    function stopMoleBgm() {
      if (moleBgmInterval) {
        clearInterval(moleBgmInterval);
        moleBgmInterval = null;
      }
    }

    function playMoleHitSound() {
      if (!moleState.soundEnabled) return;
      try {
        initMoleAudioContext();
        const osc = moleAudioCtx.createOscillator();
        const gain = moleAudioCtx.createGain();
        
        osc.type = 'triangle';
        osc.frequency.setValueAtTime(400, moleAudioCtx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(800, moleAudioCtx.currentTime + 0.15);
        
        gain.gain.setValueAtTime(0.3, moleAudioCtx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, moleAudioCtx.currentTime + 0.15);
        
        osc.connect(gain);
        gain.connect(moleAudioCtx.destination);
        
        osc.start();
        osc.stop(moleAudioCtx.currentTime + 0.15);
      } catch(e) {}
    }

    function playMoleSuccessSound() {
      if (!moleState.soundEnabled) return;
      try {
        initMoleAudioContext();
        const now = moleAudioCtx.currentTime;
        [523.25, 659.25, 783.99, 1046.50].forEach((freq, idx) => {
          const osc = moleAudioCtx.createOscillator();
          const gain = moleAudioCtx.createGain();
          osc.frequency.value = freq;
          gain.gain.setValueAtTime(0.2, now + idx * 0.08);
          gain.gain.exponentialRampToValueAtTime(0.01, now + idx * 0.08 + 0.2);
          osc.connect(gain);
          gain.connect(moleAudioCtx.destination);
          osc.start(now + idx * 0.08);
          osc.stop(now + idx * 0.08 + 0.2);
        });
      } catch(e) {}
    }

    function speakMoleText(text) {
      if (!moleState.voiceEnabled || !('speechSynthesis' in window)) return;
      window.speechSynthesis.cancel();
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.lang = 'zh-HK';
      utterance.rate = 0.85;
      utterance.pitch = 1.0;
      window.speechSynthesis.speak(utterance);
    }

    function getMoleSpeedDuration() {
      switch(moleState.currentSpeed) {
        case 'fast': return 1000;
        case 'normal': return 1600;
        case 'slow': default: return 2400;
      }
    }

    function updateMoleTargetBanner() {
      const targetText = document.getElementById('mole-targetText');
      if (!targetText) return;

      if (moleState.currentMode === 'reality') {
        const data = MOLE_THEMES.reality.dataset;
        moleState.currentRealityTarget = data[Math.floor(Math.random() * data.length)];
        targetText.innerHTML = `搵出 <span class="text-amber-600 font-extrabold underline">${moleState.currentRealityTarget.icon} ${moleState.currentRealityTarget.label}</span>`;
      } else if (moleState.currentMode === 'fruit') {
        targetText.innerHTML = `點擊 <span class="text-rose-600 font-extrabold">新鮮水果 🍎</span>`;
      } else {
        targetText.innerHTML = `打中 <span class="text-amber-600 font-extrabold">放大地鼠 🐹</span>`;
      }
    }

    function popMole() {
      if (!moleState.isPlaying) return;

      if (moleState.activeHole !== -1) {
        const prevMole = document.getElementById(`mole-${moleState.activeHole}`);
        if (prevMole) prevMole.classList.remove('up');
      }

      let nextHole;
      do {
        nextHole = Math.floor(Math.random() * 8);
      } while (nextHole === moleState.activeHole);

      moleState.activeHole = nextHole;
      const moleEl = document.getElementById(`mole-${moleState.activeHole}`);
      if (!moleEl) return;

      let displayEmoji = '🐹';
      if (moleState.currentMode === 'classic') {
        const items = MOLE_THEMES.classic.items;
        displayEmoji = items[Math.floor(Math.random() * items.length)];
      } else if (moleState.currentMode === 'fruit') {
        const items = MOLE_THEMES.fruit.items;
        displayEmoji = items[Math.floor(Math.random() * items.length)];
      } else if (moleState.currentMode === 'reality') {
        const data = MOLE_THEMES.reality.dataset;
        if (Math.random() < 0.6 && moleState.currentRealityTarget) {
          displayEmoji = moleState.currentRealityTarget.icon;
        } else {
          const randObj = data[Math.floor(Math.random() * data.length)];
          displayEmoji = randObj.icon;
        }
      }

      moleEl.textContent = displayEmoji;
      moleEl.dataset.emoji = displayEmoji;
      moleEl.classList.add('up');

      const duration = getMoleSpeedDuration();
      setTimeout(() => {
        if (moleEl.classList.contains('up')) {
          moleEl.classList.remove('up');
        }
      }, duration);
    }

    function handleMoleHit(index, event) {
      if (event) event.preventDefault();
      if (!moleState.isPlaying) return;
      const moleEl = document.getElementById(`mole-${index}`);
      if (!moleEl || !moleEl.classList.contains('up')) return;

      moleEl.classList.remove('up');

      const hitEmoji = moleEl.dataset.emoji;
      let pointsGained = 10;
      let isCorrectHit = true;

      if (moleState.currentMode === 'reality' && moleState.currentRealityTarget) {
        if (hitEmoji === moleState.currentRealityTarget.icon) {
          pointsGained = 20;
          updateMoleTargetBanner();
        } else {
          isCorrectHit = false;
          pointsGained = -5;
        }
      }

      moleState.score += pointsGained;
      if (moleState.score < 0) moleState.score = 0;
      document.getElementById('mole-scoreDisplay').textContent = moleState.score;

      if (isCorrectHit) {
        playMoleHitSound();
        showFloatScore(moleEl, `+${pointsGained}`);
        if (moleState.score > 0 && moleState.score % 50 === 0) {
          const praise = MOLE_PRAISES[Math.floor(Math.random() * MOLE_PRAISES.length)];
          document.getElementById('mole-feedbackBanner').innerHTML = `<span>🌟 ${praise}</span>`;
          speakMoleText(praise);
        }
      } else {
        playErrorSound();
        showFloatScore(moleEl, `${pointsGained}`);
      }
    }

    function showFloatScore(element, text) {
      const parent = element.parentElement;
      if (!parent) return;
      const floatEl = document.createElement('div');
      floatEl.className = 'score-float';
      floatEl.textContent = text;
      parent.appendChild(floatEl);
      setTimeout(() => {
        if (floatEl.parentNode) floatEl.parentNode.removeChild(floatEl);
      }, 800);
    }

    function toggleStartMoleGame() {
      if (moleState.isPlaying) {
        stopMoleGame();
      } else {
        startMoleGame();
      }
    }

    function startMoleGame() {
      initMoleAudioContext();
      moleState.isPlaying = true;
      moleState.score = 0;
      moleState.timeLeft = 30;
      
      document.getElementById('mole-scoreDisplay').textContent = '0';
      document.getElementById('mole-timerDisplay').textContent = '30s';
      
      const startBtn = document.getElementById('mole-startBtn');
      startBtn.innerHTML = `<span>⏹️ 停止遊戲</span>`;
      startBtn.className = startBtn.className.replace('bg-emerald-500 hover:bg-emerald-600 border-emerald-700', 'bg-rose-500 hover:bg-rose-600 border-rose-700');

      updateMoleTargetBanner();
      document.getElementById('mole-feedbackBanner').innerHTML = `<span>🔥 遊戲開始！加油！</span>`;
      
      speakMoleText("遊戲開始！加油！");

      startMoleBgm();

      const speedInterval = getMoleSpeedDuration();
      moleState.gameTimer = setInterval(popMole, speedInterval);

      moleState.countdownTimer = setInterval(() => {
        moleState.timeLeft--;
        document.getElementById('mole-timerDisplay').textContent = `${moleState.timeLeft}s`;

        if (moleState.timeLeft <= 0) {
          stopMoleGame();
          playMoleSuccessSound();
          triggerConfetti();
          document.getElementById('mole-feedbackBanner').innerHTML = `<span>🎉 時間到！您獲得了 ${moleState.score} 分！精靈活潑！</span>`;
          speakMoleText(`時間到！您獲得了 ${moleState.score} 分！太棒了！`);
        }
      }, 1000);
    }

    function stopMoleGame() {
      moleState.isPlaying = false;
      clearInterval(moleState.gameTimer);
      clearInterval(moleState.countdownTimer);
      stopMoleBgm();

      for (let i = 0; i < 8; i++) {
        const moleEl = document.getElementById(`mole-${i}`);
        if (moleEl) moleEl.classList.remove('up');
      }

      const startBtn = document.getElementById('mole-startBtn');
      startBtn.innerHTML = `<span>▶️ 開始遊戲</span>`;
      startBtn.className = startBtn.className.replace('bg-rose-500 hover:bg-rose-600 border-rose-700', 'bg-emerald-500 hover:bg-emerald-600 border-emerald-700');
    }

    function speakMolePrompt() {
      if (moleState.currentMode === 'reality' && moleState.currentRealityTarget) {
        speakMoleText(`請搵出 ${moleState.currentRealityTarget.label}`);
      } else if (moleState.currentMode === 'fruit') {
        speakMoleText("請點擊新鮮水果");
      } else {
        speakMoleText("請打地鼠，練吓手快眼快");
      }
    }

    function openMoleSettings() {
      document.getElementById('moleSettingsModal').classList.remove('hidden');
    }

    function closeMoleSettings() {
      document.getElementById('moleSettingsModal').classList.add('hidden');
    }

    function selectMoleMode(mode) {
      moleState.currentMode = mode;
      document.querySelectorAll('.mode-select-btn').forEach(btn => {
        if (btn.dataset.mode === mode) {
          btn.className = "mode-select-btn p-3 rounded-xl border-2 border-amber-400 bg-amber-50 font-bold text-left text-amber-900 flex items-center gap-3 transition";
        } else {
          btn.className = "mode-select-btn p-3 rounded-xl border-2 border-slate-200 bg-white font-bold text-left text-slate-700 flex items-center gap-3 transition";
        }
      });
    }

    function selectMoleSpeed(speed) {
      moleState.currentSpeed = speed;
      document.querySelectorAll('.speed-btn').forEach(btn => {
        if (btn.dataset.speed === speed) {
          btn.className = "speed-btn p-2.5 rounded-xl border-2 border-amber-400 bg-amber-100 font-bold text-amber-900 text-center";
        } else {
          btn.className = "speed-btn p-2.5 rounded-xl border-2 border-slate-200 bg-white font-bold text-slate-700 text-center";
        }
      });
    }

    function saveMoleSettings() {
      moleState.musicEnabled = document.getElementById('mole-musicToggle').checked;
      moleState.soundEnabled = document.getElementById('mole-soundToggle').checked;
      moleState.voiceEnabled = document.getElementById('mole-voiceToggle').checked;

      closeMoleSettings();
      updateMoleTargetBanner();
      
      if (moleState.isPlaying) {
        stopMoleGame();
      }
    }

    /* =========================================================
       4. 頁面初始化 (DOM Initialization)
       ========================================================= */

    window.addEventListener('DOMContentLoaded', () => {
      // 1. 初始化時間與天文台天氣
      updateClockAndDate();
      setInterval(updateClockAndDate, 10000); // 每10秒更新時鐘
      fetchHKOData();

      // 2. 初始化練習區
      initTodayTarget();
      goToStep(1);

      // 3. 全局用戶第一次觸控/點擊解鎖音效
      window.addEventListener('click', () => {
        initPracticeAudioContext();
        initMoleAudioContext();
      }, { once: true });
    });
  </script>
</body>
</html>
