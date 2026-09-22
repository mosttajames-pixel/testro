<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
  <title>職業治療關懷 — 每日天氣生活板</title>

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

    /* 一、黃色部份：現實導向區 (Reality Orientation) */
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

    /* 現實導向練習版專用樣式 */
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

<!-- Gemini Debug Panel -->
<div id="gemini-debug-panel"
     style="
       margin-top:12px;
       padding:14px;
       background:#f8f9fa;
       border:2px solid #6c757d;
       border-radius:12px;
       font-family:monospace;
       font-size:14px;
       line-height:1.5;
       white-space:pre-wrap;
       word-break:break-word;
       color:#212529;
     ">
  Gemini Debug:
  尚未開始
</div>
<br>

  <div class="container">
    <header>
      <h1>職業治療關懷 — 每日天氣生活板</h1>
      <div class="action-bar">
        <button class="action-btn" id="refresh-btn" onclick="refreshData()">
          <span id="refresh-icon" style="display:inline-flex;align-items:center;justify-content:center;">🔄</span> <span>立即更新</span>
        </button>
        <button class="action-btn" id="zoom-btn" onclick="toggleFontSize()">
          <span style="display:inline-flex;align-items:center;justify-content:center;">🔍</span> <span id="zoom-text">特大字體</span>
        </button>
      </div>
    </header>

    <!-- 一、黃色部份：現實導向區 (Reality Orientation) -->
    <section class="card ro-card" aria-label="現實導向資訊">
      <div class="ro-header-bar">
        <div class="ro-title">
          <span>🧠</span>
          <span>現實導向資訊 (Reality Orientation)</span>
        </div>
        <div class="location-setting-box">
          <div class="loc-field-group">
            <label>📍 地區：</label>
            <span class="fixed-district-badge">深水埗</span>
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

    <!-- 二、香港天文台即時天氣與預測區 -->
    <section class="card weather-card" aria-label="即時天氣">
      <div class="weather-header">
        <div class="district-select-container">
          <label for="district-select"><span>📍</span><span>選擇天氣分區：</span></label>
          <select id="district-select" class="district-select" onchange="updateDistrictTemperature()">
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

    <!-- 三、長者關懷提示與語音朗讀 -->
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

    <!-- 四、現實導向練習版 (互動練習區) -->
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

          <!-- Controls: Mode Switch & Speech Toggle -->
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

        <!-- Progress Step Indicators -->
        <div class="bg-white rounded-2xl p-3 shadow-md border-2 border-amber-200 flex flex-wrap sm:flex-nowrap justify-between items-center text-center gap-1.5 sm:gap-2">
          <!-- Step 1 Indicator -->
          <div id="step-tab-1" onclick="goToStep(1)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-blue-500 bg-blue-50 min-w-[70px]">
            <span class="text-xs font-bold text-blue-700 block">第一關</span>
            <span class="text-sm sm:text-lg font-black text-blue-900">1. 月份</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <!-- Step 2 Indicator -->
          <div id="step-tab-2" onclick="goToStep(2)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第二關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">2. 日期</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <!-- Step 3 Indicator -->
          <div id="step-tab-3" onclick="goToStep(3)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第三關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">3. 星期</span>
          </div>

          <div class="text-gray-300 font-bold hidden sm:block">➔</div>

          <!-- Step 4 Indicator -->
          <div id="step-tab-4" onclick="goToStep(4)" class="flex-1 py-2 px-1 rounded-xl cursor-pointer transition border-2 border-gray-200 bg-gray-50 opacity-60 min-w-[70px]">
            <span class="text-xs font-bold text-gray-500 block">第四關</span>
            <span class="text-sm sm:text-lg font-black text-gray-700">4. 季節</span>
          </div>
        </div>

        <!-- Current Question Announcement Box -->
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

        <!-- REALITY BOARD (Interactive Slots Area) -->
        <div class="bg-board-felt border-8 border-board-wood rounded-3xl p-4 sm:p-6 shadow-2xl relative">
          <div class="text-center mb-3">
            <h3 id="board-instruction" class="text-amber-100 text-lg sm:text-xl font-bold tracking-wider">點選或拖曳卡片放到框框內</h3>
          </div>

          <!-- STEP 1: MONTH SLOT -->
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

          <!-- STEP 2: DAY SLOT -->
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

          <!-- STEP 3: WEEKDAY SLOT -->
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

          <!-- STEP 4: SEASON SLOT -->
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

          <!-- Control Buttons -->
          <div class="mt-6 flex flex-wrap items-center justify-center gap-3">
            <button onclick="checkCurrentStepAnswer()" class="bg-amber-400 hover:bg-amber-300 active:scale-95 text-amber-950 font-black text-xl sm:text-2xl px-8 py-3 rounded-2xl shadow-lg border-2 border-amber-200 flex items-center gap-2 transition">
              <span>✅ 確認答案</span>
            </button>
            <button onclick="resetCurrentStep()" class="bg-red-800/80 hover:bg-red-700 active:scale-95 text-white font-bold text-base sm:text-lg px-4 py-3 rounded-2xl shadow border border-red-500/50 flex items-center gap-1 transition">
              <span>🗑️ 重來</span>
            </button>
          </div>
        </div>

        <!-- CARDS DECK SELECTION AREA (3 OPTIONS PER QUESTION) -->
        <div class="bg-board-cardBg border-2 border-amber-200 rounded-3xl p-4 sm:p-5 shadow-lg">
          <div id="deck-header-title" class="text-lg sm:text-xl font-black text-gray-800 mb-3 flex items-center justify-between border-b border-amber-200 pb-2">
            <span>請點選正確答案（三選一）：</span>
            <span class="text-xs font-bold text-gray-500 hidden sm:inline">大字體適老簡化設計</span>
          </div>

          <!-- 3 Choice Cards Display Grid -->
          <div id="deck-options" class="grid grid-cols-3 gap-3 sm:gap-6 min-h-[120px]">
            <!-- Generated by JS: 3 Options -->
          </div>
        </div>

      </div>
    </section>

  </div>

  <!-- MODAL FOR SUCCESS / FEEDBACK (Practice Game) -->
  <div id="result-modal" class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-white border-4 border-amber-400 rounded-3xl max-w-md w-full p-6 text-center shadow-2xl transform transition-all scale-95 opacity-0" id="modal-content">
      <div id="modal-icon" class="text-6xl mb-2">🎉</div>
      <h3 id="modal-title" class="text-3xl font-black text-gray-800 mb-2">好棒！答對了！</h3>
      <p id="modal-body" class="text-xl font-bold text-gray-600 mb-6">您答對了：<span id="modal-result-str" class="text-blue-700 underline">9月</span></p>
      
      <div class="flex flex-col gap-3">
        <button id="modal-next-btn" onclick="closeModalAndContinue()" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white font-black text-xl py-3.5 rounded-2xl shadow-lg transition">
          🌟 自動進入下一題
        </button>
      </div>
    </div>
  </div>

  <script>
    /* ========================================================
       一、現實導向與天氣生活板 (Main Application Logic)
       ======================================================== */
    function updateClockAndDate() {
      const now = new Date();
      
      // 時鐘數據 (只顯示時與分，顏色黑色)
      let hoursInt = now.getHours();
      const ampm = hoursInt >= 12 ? '下午' : '上午';
      const hoursStr = String(hoursInt).padStart(2, '0');
      const minutesStr = String(now.getMinutes()).padStart(2, '0');
      
      document.getElementById('clock-time').textContent = `${hoursStr}:${minutesStr}`;
      document.getElementById('clock-ampm').textContent = `${ampm}`;

      // 日期數據 - 分開顯示：年、月、日、星期
      const year = now.getFullYear();
      const month = now.getMonth() + 1;
      const date = now.getDate();
      const days = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
      const dayName = days[now.getDay()];

      document.getElementById('ro-year').textContent = `${year}年`;
      document.getElementById('ro-month').textContent = `${month}月`;
      document.getElementById('ro-date-num').textContent = `${date}日`;
      document.getElementById('ro-day-of-week').textContent = dayName;

      // 季節判斷
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

      // 農曆與節氣 (每日更新一次)
      if (!window.lunarUpdatedDate || window.lunarUpdatedDate !== date) {
        updateLunarAndSolarTerm(now);
        updateUpcomingFestivals(now);
        window.lunarUpdatedDate = date;
      }
    }

    function updateCurrentLocationDisplay() {
      const districtVal = "深水埗";
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
        console.warn('Intl 農曆計算異常:', err);
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
      if (d >= 5 && d < 20) termIndex += 0;
      else if (d >= 20) termIndex += 1;
      
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
        console.warn('天文台 API 連線失敗，啟動備援 (Mock) 資料:', err);
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
          forecastMintemp: { value: 24 + (i % 3) },
          forecastMaxtemp: { value: 29 + (i % 3) },
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

      generateCareMessage(true);
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
        const minTemp = item.forecastMintemp.value;
        const maxTemp = item.forecastMaxtemp.value;
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

    //function generateCareMessage() {
      /* ========================================================
   每日溫馨提示 — Gemini AI 動態生成
   ======================================================== */

// ========================================================
// 1. Gemini 設定
// ========================================================



const GEMINI_MODEL = 'qwen/qwen3.8-flash';

//const GEMINI_MODEL = 'qwen/qwen3.8-27b:free';

const GEMINI_API_URL =
  `https://openrouter.ai/api/v1/chat/completions`;

// ========================================================
// ⚠️ 把你自己的新 Gemini API Key 放在這裡
// ========================================================

const GEMINI_API_KEY = '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';

// ========================================================
// 2. Gemini API Key
// ========================================================

function getGeminiApiKey() {
  return GEMINI_API_KEY.trim();
}

// ========================================================
// 3. 收集目前頁面的資料
// ========================================================

function getCareContext() {
  const now = new Date();

  const tempText =
    document.getElementById('district-temp')?.textContent.trim() || '';

  const humidityText =
    document.getElementById('humidity')?.textContent.trim() || '';

  const uvText =
    document.getElementById('uv-index')?.textContent.trim() || '';

  const districtName =
    document.getElementById('district-select')?.value || '深水埗';

  const districtStr =
    document.getElementById('ro-display-district')?.textContent.trim() || districtName;

  const detailStr =
    document.getElementById('ro-display-detail')?.textContent.trim() || '';

  const fullLocation =
    detailStr && detailStr !== '未輸入地點'
      ? `${districtStr} ${detailStr}`
      : districtStr;

  // 香港天文台警告
  const warningList = Array.isArray(currentWeatherData?.warningMessage)
    ? currentWeatherData.warningMessage
        .map(w => String(w).trim())
        .filter(Boolean)
    : [];

  return {
    date:
      `${now.getFullYear()}年${now.getMonth() + 1}月${now.getDate()}日`,

    weekday:
      document.getElementById('ro-day-of-week')?.textContent.trim() || '',

    timeOfDay:
      now.getHours() >= 12 ? '下午' : '上午',

    location:
      fullLocation,

    weatherDistrict:
      districtName,

    weatherDescription:
      document.getElementById('weather-desc')?.textContent.trim() ||
      '天氣資料載入中',

    temperatureC:
      Number.isFinite(parseInt(tempText, 10))
        ? parseInt(tempText, 10)
        : null,

    humidityPercent:
      Number.isFinite(parseInt(humidityText, 10))
        ? parseInt(humidityText, 10)
        : null,

    uvIndex:
      Number.isFinite(parseFloat(uvText))
        ? parseFloat(uvText)
        : null,

    uvDescription:
      document.getElementById('uv-desc')?.textContent.trim() || '',

    humidityDescription:
      document.getElementById('humidity-desc')?.textContent.trim() || '',

    weatherWarnings:
      warningList,

    season:
      document.getElementById('season-text')?.textContent.trim() || '',

    lunar:
      document.getElementById('ro-lunar')?.textContent.trim() || '',

    solarTerm:
      document.getElementById('ro-solar-term')?.textContent.trim() || '',

    upcomingFestival:
      document.getElementById('ro-festival-name')?.textContent.trim() || '',

    festivalCountdown:
      document.getElementById('ro-festival-countdown')?.textContent.trim() || ''
  };
}


// ========================================================
// 4. 建立 Context Signature
//    避免每分鐘更新時都呼叫 Gemini
// ========================================================

function getCareContextSignature(context) {

  return JSON.stringify({
    date: context.date,
    weekday: context.weekday,
    location: context.location,

    weatherDistrict:
      context.weatherDistrict,

    weatherDescription:
      context.weatherDescription,

    temperatureC:
      context.temperatureC,

    humidityPercent:
      context.humidityPercent,

    uvIndex:
      context.uvIndex,

    uvDescription:
      context.uvDescription,

    humidityDescription:
      context.humidityDescription,

    weatherWarnings:
      context.weatherWarnings,

    season:
      context.season,

    lunar:
      context.lunar,

    solarTerm:
      context.solarTerm,

    upcomingFestival:
      context.upcomingFestival,

    festivalCountdown:
      context.festivalCountdown
  });
}


// ========================================================
// 5. Gemini 失敗時的後備訊息
// ========================================================

function buildFallbackCareMessage(context) {

  // 天氣警告優先
  if (context.weatherWarnings.length > 0) {

    return `目前有「${context.weatherWarnings.join('、')}」，外出請小心，按需要留在安全地方。`;
  }

  // 炎熱
  if (
    typeof context.temperatureC === 'number' &&
    context.temperatureC >= 30
  ) {

    return '今日較炎熱，記得多喝水，避免長時間在戶外。';
  }

  // 寒冷
  if (
    typeof context.temperatureC === 'number' &&
    context.temperatureC <= 16
  ) {

    return '今日較寒冷，外出記得穿暖一點。';
  }

  // UV
  if (
    typeof context.uvIndex === 'number' &&
    context.uvIndex >= 6
  ) {

    return '今日紫外線較高TEST，外出可選擇有遮蔭地方，避免長時間暴曬。';
  }

  // 高濕度
  if (
    typeof context.humidityPercent === 'number' &&
    context.humidityPercent >= 85
  ) {

    return '今日天氣較潮濕，行路時記得慢慢走，小心地面濕滑。';
  }

  // 一般情況
  if (
    typeof context.temperatureC === 'number'
  ) {

    return `今日${context.weatherDistrict}約${context.temperatureC}°C，外出活動可按自己的步伐適量進行。`;
  }

  return '今日記得按自己的步伐生活，適量活動，保持心情輕鬆。';
}


// ========================================================
// 6. 清理 Gemini 回覆
// ========================================================

function cleanGeminiCareMessage(text) {

  return String(text || '')
    .replace(/```[\s\S]*?```/g, '')
    .replace(/^[「"]|[」"]$/g, '')
    .replace(/\*\*/g, '')
    .replace(/\n+/g, ' ')
    .replace(/\s{2,}/g, ' ')
    .trim();
}


// ========================================================
// 7. 真正呼叫 Gemini API
// ========================================================

function geminiDebug(message) {

  const debugBox =
    document.getElementById('gemini-debug-panel');

  if (!debugBox) return;

  const time =
    new Date().toLocaleTimeString('zh-HK');

  debugBox.textContent +=
    `\n[${time}] ${message}`;
}



async function generateCareMessageWithGemini(context) {

  geminiDebug('========== Gemini 開始 ==========');

  const apiKey = getGeminiApiKey();


  geminiDebug(
    `API Key: ${apiKey ? '已設定' : '沒有 API Key'}`
  );

  if (!apiKey) {
    throw new Error('Gemini API Key 未設定。');
  }

  geminiDebug(
    `Model: ${GEMINI_MODEL}`
  );

  geminiDebug(
    `Location: ${context.location}`
  );

  geminiDebug(
    `Weather: ${context.weatherDescription}`
  );

  geminiDebug(
    `Temperature: ${context.temperatureC}°C`
  );

  geminiDebug(
    `Humidity: ${context.humidityPercent}%`
  );

  geminiDebug(
    '正在發送 Gemini API request...'
  );
  
  
  
  
  
  

  if (!apiKey) {

    throw new Error('Gemini API Key 未設定。');
  }

  // 用隨機 seed 讓每次重新生成時，
  // 即使天氣資料沒有改變，措辭也可以不同。

  const variationSeed =
    `${Date.now()}-${Math.random().toString(36).slice(2, 8)}`;


  // ======================================================
  // Gemini Prompt
  // ======================================================

                  const prompt = `
                你是香港長者服務中心的「每日溫馨提示」助手。

                請根據以下即時資料，為長者寫一段簡短、自然、實用的每日生活提醒。

                【今日資料】

                日期：
                ${context.date}

                星期：
                ${context.weekday}

                時段：
                ${context.timeOfDay}

                地點：
                ${context.location}

                天氣分區：
                ${context.weatherDistrict}

                天氣：
                ${context.weatherDescription}

                氣溫：
                ${context.temperatureC ?? '未知'}°C

                濕度：
                ${context.humidityPercent ?? '未知'}%

                濕度描述：
                ${context.humidityDescription || '未知'}

                紫外線：
                ${context.uvIndex ?? '未知'}

                紫外線描述：
                ${context.uvDescription || '未知'}

                天氣警告：
                ${context.weatherWarnings.length > 0
                  ? context.weatherWarnings.join('、')
                  : '目前沒有天氣警告'}

                季節：
                ${context.season || '未知'}

                農曆：
                ${context.lunar || '未知'}

                節氣：
                ${context.solarTerm || '未知'}

                將到節日：
                ${context.upcomingFestival || '沒有特別節日'}

                節日倒數：
                ${context.festivalCountdown || ''}


                  【寫作要求】

                  1. 只輸出每日溫馨提示正文。
                  2. 不要輸出標題。
                  3. 不要解釋你如何生成。
                  4. 不要列點。
                  5. 最多 2 句。
                  6. 約 30–50 個繁體中文字。
                  7. 要非常簡潔。
                  8. 只選擇今天最值得提醒的 1–2 個重點。
                  9. 優先考慮：
                    - 天氣警告
                    - 酷熱
                    - 寒冷
                    - 大雨
                    - 雷暴
                    - 高濕度
                    - 紫外線
                    - 外出安全
                  10. 如果有特別天氣警告必須提示，例如颱風警告、暴雨警告、酷熱天氣警告等。
                      如果沒有特別天氣風險，可以提供簡單的日常生活提醒。
                  11. 使用香港長者容易理解的繁體中文。
                  12. 語氣親切、自然、尊重。
                  13. 不要過度說教。
                  14. 不要虛構不存在的天氣警告。
                  15. 不要虛構醫療診斷、病情或個人資料。
                  16. 不要每次都使用相同句式。
                  17. 可以自然使用「今日」、「外出」、「行路」、「飲水」等生活用語。
                  18. 不需要把所有天氣資料全部重複一次。


                  【變化要求】

                  這次生成可以使用不同的句式和措辭，
                  但資訊必須與今日的實際情況相關。

                  變化參考：
                  ${variationSeed}

                  只返回最終給長者看的提示文字。
                  `.trim();


  // ======================================================
  // Gemini REST API request
  // ======================================================

  const response = await fetch(GEMINI_API_URL, {

    method: 'POST',

    headers: {
      'Content-Type': 'application/json',
      'Authorization': `Bearer ${apiKey}`
    },

body: JSON.stringify({
  model: GEMINI_MODEL,
  messages: [
    {
      role: 'user',
      content: prompt
    }
  ],
  temperature: 0.65,
  top_p: 0.9,
  max_tokens: 150,
  reasoning: {
    enabled: false
  },
  stream: false
})

    });

geminiDebug(
  `HTTP Status: ${response.status}`
);

geminiDebug(
  `HTTP OK: ${response.ok}`
);


  // ======================================================
  // API Error handling
  // ======================================================

  if (!response.ok) {

    const errorText =
      await response.text().catch(() => '');

    throw new Error(
      `Gemini API ${response.status}: ${errorText.slice(0, 500)}`
    );
  }


  // ======================================================
  // 讀取 Gemini response
  // ======================================================

  const data =
    await response.json();


    geminiDebug(
  'Gemini JSON response received.'
);

geminiDebug(
  `Response finish_reason: ${data?.choices?.[0]?.finish_reason || 'unknown'}`
);

geminiDebug(
  `Response content: ${data?.choices?.[0]?.message?.content ? '有文字' : '空白'}`
);

const generatedText =
  data?.choices?.[0]?.message?.content?.trim();


  const cleaned =
    cleanGeminiCareMessage(generatedText);

    geminiDebug(
  `Generated message: ${cleaned}`
);

  if (!cleaned) {

    throw new Error(
      'Gemini 沒有返回有效的文字。'
    );
  }


  return cleaned;
}


// ========================================================
// 8. 生成中的 UI
// ========================================================

function setCareGeneratingState(isGenerating) {

  const el =
    document.getElementById('care-message');

  if (!el) return;


  if (isGenerating) {

    el.textContent =
      '正在為你準備今日的溫馨提示…';

    el.style.opacity = '0.7';

  } else {

    el.style.opacity = '1';
  }
}


// ========================================================
// 9. 防止短時間內重複呼叫 Gemini
// ========================================================

let careGenerationTimer = null;

let lastCareContextSignature = '';

let careGenerationRequestId = 0;

let isCareGenerating = false;


// ========================================================
// 10. Schedule Gemini generation
// ========================================================

function scheduleCareMessageGeneration({
  force = false,
  delay = 700
} = {}) {

  clearTimeout(careGenerationTimer);


  careGenerationTimer = setTimeout(async () => {

    const context =
      getCareContext();


    const signature =
      getCareContextSignature(context);


    // 如果不是強制重新生成，
    // 而且資料完全沒有改變，就不用重新 call API。

    if (
      !force &&
      signature === lastCareContextSignature &&
      !isCareGenerating
    ) {

      return;
    }


    lastCareContextSignature =
      signature;


    careGenerationRequestId++;

    const requestId =
      careGenerationRequestId;


    const messageElement =
      document.getElementById('care-message');


    // 沒有 API key
if (!getGeminiApiKey()) {

  const fallbackMessage =
    buildFallbackCareMessage(context);

  messageElement.textContent =
    fallbackMessage;

  const todayKey =
    new Date().toISOString().slice(0, 10);

  const cacheKey =
    'ro_care_message_' + todayKey;

  localStorage.setItem(
    cacheKey,
    fallbackMessage
  );

  return;
}


    isCareGenerating = true;

    setCareGeneratingState(true);


    try {

      const aiMessage =
        await generateCareMessageWithGemini(context);


      // 防止舊 API request 回來後，
      // 覆蓋較新的結果。

      if (
        requestId !== careGenerationRequestId
      ) {

        return;
      }


        const finalMessage =
          aiMessage ||
          buildFallbackCareMessage(context);

        messageElement.textContent = finalMessage;

        // 保存今天的 Gemini 結果
        const todayKey = new Date().toISOString().slice(0, 10);
        const cacheKey = 'ro_care_message_' + todayKey;

        localStorage.setItem(cacheKey, finalMessage);


    } catch (error) {

      console.warn(
        ' AI 溫馨提示生成失敗，使用後備提示:',
        error
      );


      if (
        requestId !== careGenerationRequestId
      ) {

        return;
      }


      messageElement.textContent =
        buildFallbackCareMessage(context);


    } finally {

      if (
        requestId === careGenerationRequestId
      ) {

        isCareGenerating = false;

        setCareGeneratingState(false);
      }

    }

  }, delay);
}


// ========================================================
// 11. 保留原本函數名稱
// ========================================================
//
function generateCareMessage(force = false) {

  const todayKey = new Date().toISOString().slice(0, 10);
  const cacheKey = 'ro_care_message_' + todayKey;

  // 如果今天已經生成過，而且不是強制重新生成
  if (!force) {
    const cachedMessage = localStorage.getItem(cacheKey);

    if (cachedMessage) {
      document.getElementById('care-message').textContent =
        cachedMessage;
      return;
    }
  }

  // 今日第一次才真正呼叫 Gemini
  scheduleCareMessageGeneration({
    force: force,
    delay: 700
  });
}





    //}

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

  fetchHKOData();

  setTimeout(() => {
    icon.style.transform = 'rotate(0deg)';
  }, 500);
}

    /* ========================================================
       二、現實導向練習版 (Practice Game Logic)
       ======================================================== */
    const WEEKDAYS_ZH = ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"];
    const SEASONS_DATA = [
      { name: "春天", icon: "🌸", color: "bg-pink-100 border-pink-400 text-pink-900" },
      { name: "夏天", icon: "☀️", color: "bg-amber-100 border-amber-400 text-amber-900" },
      { name: "秋天", icon: "🍁", color: "bg-orange-100 border-orange-400 text-orange-900" },
      { name: "冬天", icon: "❄️", color: "bg-blue-100 border-blue-400 text-blue-900" }
    ];

    function getSeasonIndexByMonth(month) {
      if (month >= 3 && month <= 5) return 0; // 春天
      if (month >= 6 && month <= 8) return 1; // 夏天
      if (month >= 9 && month <= 11) return 2; // 秋天
      return 3; // 冬天
    }

    let practiceState = {
      currentStep: 1, // 1: Month, 2: Day, 3: Weekday, 4: Season
      target: {
        month: 9,      // 1-12
        day: 17,       // 1-31
        weekday: 4,    // 0-6
        season: 2      // 0-3
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

      // Update Step Indicators
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

      // Hide all slot views
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
        qText.textContent = "現在是星期幾？";
        document.getElementById('view-step-3').classList.remove('hidden');
        selectSlot('weekday');
        speakPracticeText("第三題：現在是星期幾？");
      } else if (stepNum === 4) {
        badge.textContent = "第四題";
        qText.textContent = "現在是什麼季節？";
        document.getElementById('view-step-4').classList.remove('hidden');
        selectSlot('season');
        speakPracticeText("第四題：現在是什麼季節？");
      }

      // Generate & Render 3 options for current step
      generateThreeOptions(stepNum);
      renderCurrentDeck();
    }

    function readCurrentQuestionSpeech() {
      const qText = document.getElementById('question-text').textContent.trim();
      speakPracticeText(qText);
    }

    function generateThreeOptions(stepNum) {
      let options = [];
      if (stepNum === 1) {
        const targetVal = practiceState.target.month;
        let d1 = (targetVal + 3) % 12 || 12;
        let d2 = (targetVal + 7) % 12 || 12;
        if (d1 === targetVal) d1 = (targetVal % 12) + 1;
        if (d2 === targetVal || d2 === d1) d2 = ((d1 + 2) % 12) || 12;
        options = [targetVal, d1, d2];
      } else if (stepNum === 2) {
        const targetVal = practiceState.target.day;
        let d1 = targetVal - 4 > 0 ? targetVal - 4 : targetVal + 5;
        let d2 = targetVal + 4 <= 31 ? targetVal + 4 : targetVal - 5;
        if (d1 === targetVal) d1 = targetVal === 1 ? 2 : 1;
        if (d2 === targetVal || d2 === d1) d2 = targetVal === 31 ? 30 : 28;
        options = [targetVal, d1, d2];
      } else if (stepNum === 3) {
        const targetVal = practiceState.target.weekday; // 0-6
        let d1 = (targetVal + 2) % 7;
        let d2 = (targetVal + 4) % 7;
        options = [targetVal, d1, d2];
      } else if (stepNum === 4) {
        const targetVal = practiceState.target.season; // 0-3
        let d1 = (targetVal + 1) % 4;
        let d2 = (targetVal + 2) % 4;
        options = [targetVal, d1, d2];
      }

      options.sort(() => Math.random() - 0.5);
      practiceState.currentStepOptions = options;
    }

    function renderCurrentDeck() {
      const deckContainer = document.getElementById('deck-options');
      deckContainer.innerHTML = '';

      practiceState.currentStepOptions.forEach(val => {
        const card = document.createElement('div');
        card.className = `card-shadow bg-amber-50 border-4 border-amber-300 hover:border-blue-500 rounded-3xl p-4 sm:p-6 flex flex-col items-center justify-center cursor-pointer transition transform active:scale-95 select-none min-h-[110px]`;
        card.draggable = true;

        if (practiceState.currentStep === 1) {
          card.setAttribute('ondragstart', `handleDragStart(event, 'month', ${val})`);
          card.onclick = () => onCardPicked('month', val);
          card.innerHTML = `
            <span class="text-4xl sm:text-5xl font-black text-blue-900 tracking-tight">${val}</span>
            <span class="text-base sm:text-lg font-bold text-amber-800">月</span>
          `;
        } else if (practiceState.currentStep === 2) {
          card.setAttribute('ondragstart', `handleDragStart(event, 'day', ${val})`);
          card.onclick = () => onCardPicked('day', val);
          card.innerHTML = `
            <span class="text-4xl sm:text-5xl font-black text-emerald-900 tracking-tight">${val}</span>
            <span class="text-base sm:text-lg font-bold text-emerald-800">日</span>
          `;
        } else if (practiceState.currentStep === 3) {
          card.setAttribute('ondragstart', `handleDragStart(event, 'weekday', ${val})`);
          card.onclick = () => onCardPicked('weekday', val);
          card.innerHTML = `
            <span class="text-2xl sm:text-3xl font-black text-purple-900 tracking-tight">${WEEKDAYS_ZH[val]}</span>
          `;
        } else if (practiceState.currentStep === 4) {
          const sData = SEASONS_DATA[val];
          card.setAttribute('ondragstart', `handleDragStart(event, 'season', ${val})`);
          card.onclick = () => onCardPicked('season', val);
          card.innerHTML = `
            <span class="text-4xl sm:text-5xl mb-1">${sData.icon}</span>
            <span class="text-2xl sm:text-3xl font-black text-amber-950 tracking-tight">${sData.name}</span>
          `;
        }

        deckContainer.appendChild(card);
      });
    }

    function selectSlot(slotName) {
      practiceState.selectedSlot = slotName;
      ['month', 'day', 'weekday', 'season'].forEach(s => {
        const el = document.getElementById(`slot-${s}`);
        if (el) {
          if (s === slotName) el.classList.add('slot-highlight');
          else el.classList.remove('slot-highlight');
        }
      });
      playPopSound();
    }

    function onCardPicked(type, value) {
      playPopSound();

      if (type === 'month') {
        practiceState.userAnswers.month = value;
        renderSlotContent('month', `${value}`, '月', 'bg-blue-600 text-white');
        speakPracticeText(`${value}月`);
      } else if (type === 'day') {
        practiceState.userAnswers.day = value;
        renderSlotContent('day', `${value}`, '日', 'bg-emerald-600 text-white');
        speakPracticeText(`${value}日`);
      } else if (type === 'weekday') {
        practiceState.userAnswers.weekday = value;
        renderSlotContent('weekday', WEEKDAYS_ZH[value], '', 'bg-purple-700 text-white');
        speakPracticeText(`${WEEKDAYS_ZH[value]}`);
      } else if (type === 'season') {
        practiceState.userAnswers.season = value;
        const sData = SEASONS_DATA[value];
        renderSlotContent('season', `${sData.icon} ${sData.name}`, '', 'bg-orange-600 text-white');
        speakPracticeText(`${sData.name}`);
      }
    }

    function renderSlotContent(slotKey, mainText, subText = '', colorClass = '') {
      const container = document.getElementById(`slot-${slotKey}-content`);
      if (!container) return;
      container.innerHTML = `
        <div class="w-full h-full p-1 flex flex-col items-center justify-center">
          <div class="w-full h-full ${colorClass} rounded-xl flex flex-col items-center justify-center shadow-md relative group">
            <span class="text-2xl sm:text-3xl font-black">${mainText}</span>
            ${subText ? `<span class="text-xs font-bold">${subText}</span>` : ''}
            <button onclick="clearSlot(event, '${slotKey}')" title="移除" class="absolute -top-2 -right-2 bg-red-600 text-white text-xs w-6 h-6 rounded-full flex items-center justify-center font-bold shadow hover:bg-red-700">✕</button>
          </div>
        </div>
      `;
    }

    function clearSlot(e, slotKey) {
      if (e) e.stopPropagation();
      if (slotKey === 'month') practiceState.userAnswers.month = null;
      if (slotKey === 'day') practiceState.userAnswers.day = null;
      if (slotKey === 'weekday') practiceState.userAnswers.weekday = null;
      if (slotKey === 'season') practiceState.userAnswers.season = null;

      const container = document.getElementById(`slot-${slotKey}-content`);
      if (container) container.innerHTML = '';
      selectSlot(slotKey);
      playPopSound();
    }

    function resetCurrentStep() {
      if (practiceState.currentStep === 1) clearSlot(null, 'month');
      else if (practiceState.currentStep === 2) clearSlot(null, 'day');
      else if (practiceState.currentStep === 3) clearSlot(null, 'weekday');
      else if (practiceState.currentStep === 4) clearSlot(null, 'season');
    }

    function handleDragStart(e, type, value) {
      e.dataTransfer.setData('text/plain', JSON.stringify({ type, value }));
      playPopSound();
    }

    function allowDrop(e) {
      e.preventDefault();
    }

    function handleDrop(e, targetSlot) {
      e.preventDefault();
      try {
        const data = JSON.parse(e.dataTransfer.getData('text/plain'));
        if (!data) return;
        if (targetSlot === 'month' && data.type === 'month') {
          onCardPicked('month', data.value);
        } else if (targetSlot === 'day' && data.type === 'day') {
          onCardPicked('day', data.value);
        } else if (targetSlot === 'weekday' && data.type === 'weekday') {
          onCardPicked('weekday', data.value);
        } else if (targetSlot === 'season' && data.type === 'season') {
          onCardPicked('season', data.value);
        }
      } catch (err) {}
    }

    function checkCurrentStepAnswer() {
      if (practiceState.currentStep === 1) {
        if (practiceState.userAnswers.month === null) {
          speakPracticeText("請先選擇月份卡");
          return;
        }

        if (practiceState.userAnswers.month === practiceState.target.month) {
          playSuccessFanfare();
          showModal(true, `答對了！現在是 ${practiceState.target.month} 月`, "🌟 自動進入第二題");
          speakPracticeText(`太棒了！答對了！現在是 ${practiceState.target.month} 月。我們接著做第二題！`);
        } else {
          playErrorSound();
          speakPracticeText(`再試一次喔！您選的是 ${practiceState.userAnswers.month}月`);
        }

      } else if (practiceState.currentStep === 2) {
        if (practiceState.userAnswers.day === null) {
          speakPracticeText("請先選擇日期卡");
          return;
        }

        if (practiceState.userAnswers.day === practiceState.target.day) {
          playSuccessFanfare();
          showModal(true, `答對了！現在是 ${practiceState.target.day} 日`, "🌟 自動進入第三題");
          speakPracticeText(`真厲害！答對了！現在是 ${practiceState.target.day} 日。我們接著做第三題！`);
        } else {
          playErrorSound();
          speakPracticeText(`再試一次喔！您選的是 ${practiceState.userAnswers.day}日`);
        }

      } else if (practiceState.currentStep === 3) {
        if (practiceState.userAnswers.weekday === null) {
          speakPracticeText("請先選擇星期卡");
          return;
        }

        if (practiceState.userAnswers.weekday === practiceState.target.weekday) {
          playSuccessFanfare();
          showModal(true, `答對了！今天是 ${WEEKDAYS_ZH[practiceState.target.weekday]}`, "🌟 自動進入第四題");
          speakPracticeText(`答對了！今天是 ${WEEKDAYS_ZH[practiceState.target.weekday]}。我們接著做第四題！`);
        } else {
          playErrorSound();
          speakPracticeText(`再試一次喔！您選的是 ${WEEKDAYS_ZH[practiceState.userAnswers.weekday]}`);
        }

      } else if (practiceState.currentStep === 4) {
        if (practiceState.userAnswers.season === null) {
          speakPracticeText("請先選擇季節卡");
          return;
        }

        if (practiceState.userAnswers.season === practiceState.target.season) {
          playSuccessFanfare();
          triggerConfetti();

          const targetSeasonObj = SEASONS_DATA[practiceState.target.season];
          const fullDateStr = `${practiceState.target.month}月${practiceState.target.day}日 ${WEEKDAYS_ZH[practiceState.target.weekday]} (${targetSeasonObj.name})`;
          showModal(true, `🎉 太厲害了！全對了！<br>今天是 ${fullDateStr}`, "🌟 完成練習 / 再玩一次");
          speakPracticeText(`恭喜您！四題全部答對！今天是 ${fullDateStr}！`);
        } else {
          playErrorSound();
          const pickedSeasonName = SEASONS_DATA[practiceState.userAnswers.season].name;
          speakPracticeText(`再試一次喔！您選的是 ${pickedSeasonName}`);
        }
      }
    }

    function showModal(isSuccess, resultText, btnLabel) {
      const modal = document.getElementById('result-modal');
      const modalContent = document.getElementById('modal-content');
      const resultStr = document.getElementById('modal-result-str');
      const nextBtn = document.getElementById('modal-next-btn');

      resultStr.innerHTML = resultText;
      nextBtn.textContent = btnLabel;

      modal.classList.remove('hidden');
      setTimeout(() => {
        modalContent.classList.remove('scale-95', 'opacity-0');
        modalContent.classList.add('scale-100', 'opacity-100');
      }, 20);
    }

    function closeModalAndContinue() {
      const modal = document.getElementById('result-modal');
      const modalContent = document.getElementById('modal-content');

      modalContent.classList.remove('scale-100', 'opacity-100');
      modalContent.classList.add('scale-95', 'opacity-0');

      setTimeout(() => {
        modal.classList.add('hidden');
        if (practiceState.currentStep === 1) {
          goToStep(2);
        } else if (practiceState.currentStep === 2) {
          goToStep(3);
        } else if (practiceState.currentStep === 3) {
          goToStep(4);
        } else if (practiceState.currentStep === 4) {
          initTodayTarget();
          practiceState.userAnswers = { month: null, day: null, weekday: null, season: null };
          ['month', 'day', 'weekday', 'season'].forEach(s => clearSlot(null, s));
          goToStep(1);
        }
      }, 200);
    }

    function triggerConfetti() {
      const canvas = document.getElementById('confetti-canvas');
      const ctx = canvas.getContext('2d');
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;

      const particles = [];
      const colors = ['#FBBF24', '#3B82F6', '#10B981', '#EC4899', '#8B5CF6'];

      for (let i = 0; i < 90; i++) {
        particles.push({
          x: canvas.width / 2,
          y: canvas.height / 2,
          vx: (Math.random() - 0.5) * 14,
          vy: (Math.random() - 0.7) * 16,
          size: Math.random() * 10 + 6,
          color: colors[Math.floor(Math.random() * colors.length)],
          gravity: 0.2,
          alpha: 1
        });
      }

      function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        let alive = false;

        particles.forEach(p => {
          p.x += p.vx;
          p.y += p.vy;
          p.vy += p.gravity;
          p.alpha -= 0.015;

          if (p.alpha > 0) {
            alive = true;
            ctx.globalAlpha = p.alpha;
            ctx.fillStyle = p.color;
            ctx.fillRect(p.x, p.y, p.size, p.size);
          }
        });

        if (alive) {
          requestAnimationFrame(animate);
        } else {
          ctx.clearRect(0, 0, canvas.width, canvas.height);
        }
      }

      animate();
    }

    /* ========================================================
       DOMContentLoaded Initialization
       ======================================================== */
    window.addEventListener('DOMContentLoaded', () => {
      // 初始化現實導向與天氣生活板
      updateClockAndDate();
      setInterval(updateClockAndDate, 1000);
      updateCurrentLocationDisplay();
      fetchHKOData();

      // 初始化現實導向練習版
      initTodayTarget();
      goToStep(1);
    });
  </script>
</body>
</html>
