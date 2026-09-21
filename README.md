<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
  <title>職業治療關懷 — 每日天氣生活板與現實導向練習</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts for legibility -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@500;700;900&display=swap" rel="stylesheet">

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['"Noto Sans TC"', '-apple-system', 'BlinkMacSystemFont', 'sans-serif'],
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
    /* ==================== 基礎與高對比色彩設定 ==================== */
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
    body.large-font-mode .care-message-box { font-size: 34px; }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-main);
      padding: 16px;
      line-height: 1.5;
      font-family: 'Noto Sans TC', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      -webkit-text-size-adjust: 100%;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    /* 頂部主標題 */
    header.main-header {
      text-align: center;
      background-color: #1a365d;
      color: #ffffff;
      padding: 20px 16px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }

    header.main-header h1 {
      font-size: 32px;
      font-weight: 800;
      letter-spacing: 1px;
    }

    /* 頂部快捷功能按鈕區 */
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

    /* 通用卡片樣式 */
    .card {
      border-radius: 24px;
      padding: 20px;
      border: 4px solid;
      box-shadow: 0 6px 16px rgba(0,0,0,0.08);
      background-color: #ffffff;
    }

    /* ==================== 一、黃色部份：現實導向區 (Reality Orientation) ==================== */
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

    .location-setting-box label {
      font-size: 20px;
      font-weight: 800;
      color: #2b8a3e;
      white-space: nowrap;
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

    .loc-field-group {
      display: flex;
      align-items: center;
      gap: 6px;
      flex-wrap: wrap;
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

    /* ==================== 二、即時天氣區 (HKO Weather) ==================== */
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
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      gap: 12px;
    }

    .forecast-card {
      background-color: var(--card-forecast-bg);
      border: 3px solid var(--card-forecast-border);
      border-radius: 16px;
      padding: 12px 8px;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
    }

    .forecast-date {
      font-size: 20px;
      font-weight: 800;
      color: #3b5bdb;
    }

    .forecast-temp {
      font-size: 22px;
      font-weight: 800;
      color: #e03131;
      margin-top: 4px;
    }

    /* ==================== 三、關懷提示與語音朗讀區 ==================== */
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

    /* ==================== 四、現實導向練習版遊戲卡片樣式 ==================== */
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

    /* 流動裝置響應式設計 (Mobile Responsive) */
    @media (max-width: 1024px) {
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-clock, .col-lunar, .col-season, .col-festi { grid-column: span 6; }
    }

    @media (max-width: 768px) {
      body { padding: 10px; }
      header.main-header { padding: 16px 12px; }
      header.main-header h1 { font-size: 24px; }
      
      .action-btn { font-size: 18px; padding: 8px 16px; }
      
      .ro-header-bar { flex-direction: column; align-items: flex-start; }
      .location-setting-box { width: 100%; }
      .location-input { width: 100%; min-width: 0; }

      .ro-grid { gap: 10px; }
      
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
    }

    @media (max-width: 480px) {
      .col-loc-1, .col-loc-2 { grid-column: span 12; }
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-season, .col-festi { grid-column: span 12; }
      .ro-value-main { font-size: 28px; }
      .ro-value-time { font-size: 30px; }
      .temp-display { font-size: 40px; }
      .forecast-grid { grid-template-columns: repeat(2, 1fr); }
    }
  </style>
</head>
<body>

  <canvas id="confetti-canvas"></canvas>

  <div class="container">
    <header class="main-header">
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

        <div class="weather-box" id="warning-weather-box" style="border-color: #f03e3e;">
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
        <div class="forecast-title"><span>🔮</span><span>未來一星期天氣預測</span></div>
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

    <!-- 四、現實導向練習區 (複製新增於最底) -->
    <section class="bg-board-bg rounded-3xl p-4 sm:p-6 shadow-xl border-4 border-amber-800/40 my-4 flex flex-col gap-4">
      
      <!-- 練習頭部導航列 -->
      <header class="bg-board-darkwood text-white shadow-md p-3 sm:p-4 rounded-2xl">
        <div class="max-w-4xl mx-auto flex flex-wrap items-center justify-between gap-2">
          <div class="flex items-center space-x-2">
            <span class="text-3xl sm:text-4xl">🗓️</span>
            <div>
              <h2 class="text-2xl sm:text-3xl font-black tracking-wide text-amber-200">現實導向練習版</h2>
              <p class="text-xs sm:text-sm text-amber-100 font-medium">看清問題，選擇卡片填入答案</p>
            </div>
          </div>

          <!-- Controls: Mode Switch & Speech Toggle -->
          <div class="flex items-center space-x-2 sm:space-x-3 text-sm flex-wrap">
            <button id="btn-today-target" onclick="setMode('today')" class="bg-amber-600 hover:bg-amber-500 active:bg-amber-700 text-white font-bold px-3 py-2 rounded-xl text-sm sm:text-base flex items-center space-x-1 shadow transition">
              <span>🎯 今日現實</span>
            </button>
            <button id="btn-random-target" onclick="setMode('random')" class="bg-amber-700/80 hover:bg-amber-600 text-amber-100 font-bold px-3 py-2 rounded-xl text-sm sm:text-base flex items-center space-x-1 shadow transition">
              <span>🎲 隨機題目</span>
            </button>
            <button id="btn-audio-toggle" onclick="toggleAudio()" class="bg-emerald-700 hover:bg-emerald-600 text-white font-bold px-3 py-2 rounded-xl text-sm sm:text-base flex items-center space-x-1 shadow transition">
              <span id="audio-icon">🔊</span>
              <span id="audio-label">聲音開</span>
            </button>
          </div>
        </div>
      </header>

      <!-- Progress Step Indicators -->
      <section class="bg-white rounded-2xl p-3 shadow-md border-2 border-amber-200 flex flex-wrap sm:flex-nowrap justify-between items-center text-center gap-1.5 sm:gap-2">
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
      </section>

      <!-- Current Question Announcement Box -->
      <section class="bg-amber-100 border-3 border-amber-300 rounded-2xl p-4 shadow-sm flex flex-col sm:flex-row items-center justify-between gap-3 text-center sm:text-left">
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
      </section>

      <!-- REALITY BOARD (Interactive Slots Area) -->
      <section class="bg-board-felt border-8 border-board-wood rounded-3xl p-4 sm:p-6 shadow-2xl relative">
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

        <!-- STEP 2: DAY SLOTS (Tens & Units) -->
        <div id="view-step-2" class="hidden flex flex-col items-center justify-center py-2">
          <div class="flex items-center gap-3 sm:gap-4 bg-board-darkwood/40 p-4 sm:p-5 rounded-2xl border border-emerald-600/50 justify-center">
            <div class="flex flex-col items-center">
              <span class="text-xs text-amber-200 mb-1 font-bold">十位數字</span>
              <div id="slot-day-tens" 
                   onclick="selectSlot('day-tens')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'day-tens')"
                   class="w-22 h-28 sm:w-28 sm:h-32 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative">
                <span class="text-amber-200/40 text-sm font-bold pointer-events-none">0-3</span>
                <div id="slot-day-tens-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
            </div>

            <div class="flex flex-col items-center">
              <span class="text-xs text-amber-200 mb-1 font-bold">個位數字</span>
              <div id="slot-day-units" 
                   onclick="selectSlot('day-units')" 
                   ondragover="allowDrop(event)" 
                   ondrop="handleDrop(event, 'day-units')"
                   class="w-22 h-28 sm:w-28 sm:h-32 bg-board-darkwood/80 border-4 border-dashed border-amber-300/70 rounded-2xl flex flex-col items-center justify-center cursor-pointer transition slot-shadow hover:border-amber-300 relative">
                <span class="text-amber-200/40 text-sm font-bold pointer-events-none">0-9</span>
                <div id="slot-day-units-content" class="w-full h-full flex items-center justify-center"></div>
              </div>
            </div>

            <span class="text-5xl sm:text-6xl font-black text-amber-100 drop-shadow ml-1">日</span>
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
      </section>

      <!-- CARDS DECK SELECTION AREA -->
      <section class="bg-board-cardBg border-2 border-amber-200 rounded-3xl p-4 sm:p-5 shadow-lg">
        <div id="deck-header-title" class="text-lg sm:text-xl font-black text-gray-800 mb-3 flex items-center justify-between border-b border-amber-200 pb-2">
          <span>選取月份卡（點擊或拖曳）：</span>
          <span class="text-xs font-bold text-gray-500 hidden sm:inline">大字體適老設計</span>
        </div>

        <div id="deck-months" class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-6 gap-3"></div>
        <div id="deck-digits" class="hidden grid grid-cols-5 sm:grid-cols-5 md:grid-cols-10 gap-2 sm:gap-3"></div>
        <div id="deck-weekdays" class="hidden grid grid-cols-2 sm:grid-cols-4 md:grid-cols-7 gap-2 sm:gap-3"></div>
        <div id="deck-seasons" class="hidden grid grid-cols-2 sm:grid-cols-4 gap-3"></div>
      </section>
    </section>

  </div>

  <!-- MODAL FOR PRACTICE SUCCESS / FEEDBACK -->
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

  <footer class="text-center text-xs text-gray-500 py-4">
    職業治療關懷 • 每日天氣生活板 & 現實導向長者認知練習
  </footer>

  <script>
    /* ==================== 1. 即時時鐘與日期分離邏輯 ==================== */
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

    function updateCurrentLocationDisplay() {
      const districtVal = "深水埗";
      const detailVal = document.getElementById('location-detail-input').value.trim();
      
      document.getElementById('ro-display-district').textContent = districtVal;
      document.getElementById('ro-display-detail').textContent = detailVal || "未輸入地點";
      
      generateCareMessage();
    }

    /* ==================== 2. 農曆與二十四節氣演算法 ==================== */
    function updateLunarAndSolarTerm(dateObj) {
      const lunarInfo = [
        0x04bd8,0x04ae0,0x0a570,0x054d5,0x0d260,0x0d950,0x16554,0x056a0,0x09ad0,0x055d2,
        0x04ae0,0x0a5b6,0x0a4d0,0x0d250,0x1d255,0x0b540,0x0d6a0,0x0ada2,0x095b0,0x14977,
        0x04970,0x0a4b0,0x0b4b5,0x06a50,0x06d40,0x1ab54,0x02b60,0x09570,0x052f2,0x04970,
        0x06566,0x0d4a0,0x0ea50,0x06e95,0x05ad0,0x02b60,0x186e3,0x092e0,0x1c8d7,0x0c950,
        0x0d4a0,0x1d8a6,0x0b550,0x056a0,0x0a5b4,0x025d0,0x092d0,0x0d2b2,0x0a950,0x0b557,
        0x06ca0,0x0b550,0x15355,0x04da0,0x0a5d0,0x14d54,0x052d0,0x0a9b8,0x0a950,0x0b4a0,
        0x0baa6,0x0ad50,0x055d0,0x0fb0b,0x04da0,0x0a5d0,0x145b0,0x0a2d0,0x0d2b2,0x0a950,
        0x0e79e,0x06ca0,0x0b550,0x15b71,0x04570,0x0a2d0,0x1d258,0x0d950,0x0e540,0x1d4a6,
        0x0a6b0,0x055a0,0x0a4c4,0x04b70,0x0b482,0x06a50,0x06d45,0x0ab50,0x09370,0x049f8,
        0x04970,0x064b0,0x068a6,0x0ea50,0x06b20,0x1a6c4,0x0aaae,0x092e0,0x0d2e3,0x0c960
      ];

      const baseDate = new Date(1900, 0, 31);
      let offset = Math.floor((dateObj - baseDate) / 86400000);

      let i, temp = 0;
      let year, month, day, isLeap = false;

      for (i = 1900; i < 2100 && offset > 0; i++) {
        temp = lYearDays(i);
        offset -= temp;
      }
      if (offset < 0) {
        offset += temp;
        i--;
      }
      year = i;

      let leap = leapMonth(i);
      for (i = 1; i < 13 && offset > 0; i++) {
        if (leap > 0 && i === (leap + 1) && !isLeap) {
          --i;
          isLeap = true;
          temp = leapDays(year);
        } else {
          temp = monthDays(year, i);
        }
        if (isLeap && i === (leap + 1)) isLeap = false;
        offset -= temp;
      }

      if (offset === 0 && leap > 0 && i === leap + 1) {
        if (isLeap) {
          isLeap = false;
        } else {
          isLeap = true;
          --i;
        }
      }
      if (offset < 0) {
        offset += temp;
        --i;
      }

      month = i;
      day = offset + 1;

      const nStr1 = ['日', '一', '二', '三', '四', '五', '六', '七', '八', '九', '十'];
      const nStr2 = ['初', '十', '廿', '卅'];
      const monthNames = ['正', '二', '三', '四', '五', '六', '七', '八', '九', '十', '十一', '臘'];

      let lunarMonthStr = monthNames[month - 1] + '月';
      if (isLeap) lunarMonthStr = '閏' + lunarMonthStr;

      let lunarDayStr = '';
      if (day === 10) lunarDayStr = '初十';
      else if (day === 20) lunarDayStr = '二十';
      else if (day === 30) lunarDayStr = '三十';
      else {
        lunarDayStr = nStr2[Math.floor(day / 10)] + nStr1[day % 10];
      }

      document.getElementById('ro-lunar').textContent = `農曆 ${lunarMonthStr}${lunarDayStr}`;

      const solarTerms = [
        "小寒", "大寒", "立春", "雨水", "驚蟄", "春分",
        "清明", "穀雨", "立夏", "小滿", "芒種", "夏至",
        "小暑", "大暑", "立秋", "處暑", "白露", "秋分",
        "寒露", "霜降", "立冬", "小雪", "大雪", "冬至"
      ];
      
      const m = dateObj.getMonth();
      const d = dateObj.getDate();
      let termIndex = m * 2;
      if (d >= 6 && d < 21) termIndex += 0;
      else if (d >= 21) termIndex += 1;
      
      const currentTerm = solarTerms[(termIndex) % 24];
      document.getElementById('ro-solar-term').textContent = `節氣：${currentTerm}`;

      function lYearDays(y) {
        let sum = 348;
        for (let i = 0x8000; i > 0x8; i >>= 1) sum += (lunarInfo[y - 1900] & i) ? 1 : 0;
        return sum + leapDays(y);
      }
      function leapMonth(y) { return lunarInfo[y - 1900] & 0xf; }
      function leapDays(y) { if (leapMonth(y)) return (lunarInfo[y - 1900] & 0x10000) ? 30 : 29; else return 0; }
      function monthDays(y, m) { return (lunarInfo[y - 1900] & (0x10000 >> m)) ? 30 : 29; }
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

    /* ==================== 3. 香港天文台 API 串接與數據處理 ==================== */
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

      for (let i = 1; i <= 7; i++) {
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

      const humidityVal = currentWeatherData.humidity?.data?.[0]?.value || 75;
      document.getElementById('humidity').textContent = humidityVal;
      let humDesc = "舒適";
      if (humidityVal > 80) humDesc = "相當潮濕";
      else if (humidityVal < 50) humDesc = "乾燥";
      document.getElementById('humidity-desc').textContent = humDesc;

      const uvVal = currentWeatherData.uvindex?.data?.[0]?.value ?? '--';
      const uvDesc = currentWeatherData.uvindex?.data?.[0]?.desc || (uvVal > 5 ? "中等至高" : "低");
      document.getElementById('uv-index').textContent = uvVal;
      document.getElementById('uv-desc').textContent = `強度：${uvDesc}`;

      const iconCode = currentWeatherData.icon?.[0] || 60;
      document.getElementById('weather-desc').textContent = getWeatherDescByIcon(iconCode);
      document.getElementById('weather-emoji').textContent = getWeatherEmojiByIcon(iconCode);

      updateDistrictTemperature();

      const warnings = currentWeatherData.warningMessage || [];
      const alertContainer = document.getElementById('alert-container');
      const alertText = document.getElementById('alert-text');
      const warningBoxIcon = document.getElementById('warning-box-icon');
      const warningBoxDesc = document.getElementById('warning-box-desc');

      if (warnings.length > 0) {
        alertContainer.classList.add('active');
        alertText.textContent = `⚠️ 警告提示：${warnings.join(' | ')}`;
        warningBoxIcon.textContent = '⚠️';
        warningBoxDesc.textContent = warnings[0];
        warningBoxDesc.style.color = '#c92a2a';
      } else {
        alertContainer.classList.remove('active');
        warningBoxIcon.textContent = '✅';
        warningBoxDesc.textContent = '現時無極端天氣警告';
        warningBoxDesc.style.color = '#2b8a3e';
      }

      generateCareMessage();
    }

    function updateDistrictTemperature() {
      if (!currentWeatherData || !currentWeatherData.temperature) return;

      const selectedDistrict = document.getElementById('district-select').value;
      const tempArray = currentWeatherData.temperature.data;

      const avgTemp = Math.round(tempArray.reduce((acc, curr) => acc + curr.value, 0) / tempArray.length);
      document.getElementById('hk-mean-temp').textContent = avgTemp;

      let matchedTemp = avgTemp;
      const targetKeywords = districtNameMap[selectedDistrict] || [selectedDistrict];

      for (let item of tempArray) {
        if (targetKeywords.some(kw => item.place.includes(kw))) {
          matchedTemp = item.value;
          break;
        }
      }

      document.getElementById('district-temp').textContent = matchedTemp;
      generateCareMessage();
    }

    function renderForecastUI() {
      if (!forecastData || !forecastData.weatherForecast) return;

      const grid = document.getElementById('forecast-grid');
      grid.innerHTML = '';

      const list = forecastData.weatherForecast.slice(0, 7);
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
          <div class="forecast-date">${formattedDate}</div>
          <div style="font-size: 16px; font-weight: bold; color: #495057;">${item.week}</div>
          <div style="font-size: 36px; margin: 4px 0;">${forecastEmoji}</div>
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

    /* ==================== 4. 自動生成關懷語句 ==================== */
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

    /* ==================== 5. 語音朗讀與工具按鈕功能 ==================== */
    function speakROAndWeather() {
      const btn = document.getElementById('tts-btn');
      
      if ('speechSynthesis' in window) {
        if (window.speechSynthesis.speaking) {
          window.speechSynthesis.cancel();
          btn.classList.remove('speaking');
          btn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
          return;
        }

        const careText = document.getElementById('care-message').textContent;
        const utterance = new SpeechSynthesisUtterance(careText);
        utterance.lang = 'zh-HK';
        utterance.rate = 0.85;

        utterance.onstart = () => {
          btn.classList.add('speaking');
          btn.querySelector('span').textContent = '⏹️ 停止朗讀';
        };

        utterance.onend = () => {
          btn.classList.remove('speaking');
          btn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
        };

        utterance.onerror = () => {
          btn.classList.remove('speaking');
          btn.querySelector('span').textContent = '🔊 聽語音（粵語朗讀）';
        };

        window.speechSynthesis.speak(utterance);
      } else {
        alert('您的瀏覽器不支援語音朗讀功能。');
      }
    }

    function refreshData() {
      const icon = document.getElementById('refresh-icon');
      icon.style.transform = 'rotate(360deg)';
      icon.style.transition = 'transform 0.5s ease';

      updateClockAndDate();
      fetchHKOData();

      setTimeout(() => {
        icon.style.transform = 'none';
        icon.style.transition = 'none';
      }, 500);
    }

    function toggleFontSize() {
      document.body.classList.toggle('large-font-mode');
      const zoomText = document.getElementById('zoom-text');
      if (document.body.classList.contains('large-font-mode')) {
        zoomText.textContent = '標準字體';
      } else {
        zoomText.textContent = '特大字體';
      }
    }

    /* ==================== 6. 現實導向練習版遊戲邏輯 ==================== */
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

    let gamePracticeState = {
      mode: 'today',
      currentStep: 1,
      target: {
        month: 9,
        day: 17,
        weekday: 4,
        season: 2
      },
      selectedSlot: 'month',
      userAnswers: {
        month: null,
        dayTens: null,
        dayUnits: null,
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
      if (!gamePracticeState.audioEnabled) return;
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
      if (!gamePracticeState.audioEnabled) return;
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
      if (!gamePracticeState.audioEnabled) return;
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

    function speakGameText(text) {
      if (!gamePracticeState.audioEnabled || !gamePracticeState.speechSupported) return;
      window.speechSynthesis.cancel();
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.lang = 'zh-HK';
      utterance.rate = 0.85;
      utterance.pitch = 1.0;
      window.speechSynthesis.speak(utterance);
    }

    function setMode(mode, announce = true) {
      gamePracticeState.mode = mode;
      const todayBtn = document.getElementById('btn-today-target');
      const randomBtn = document.getElementById('btn-random-target');

      if (mode === 'today') {
        const now = new Date();
        gamePracticeState.target.month = now.getMonth() + 1;
        gamePracticeState.target.day = now.getDate();
        gamePracticeState.target.weekday = now.getDay();
        gamePracticeState.target.season = getSeasonIndexByMonth(gamePracticeState.target.month);

        todayBtn.className = "bg-amber-600 text-white font-bold px-3 py-2 rounded-xl text-sm sm:text-base shadow transition border-2 border-amber-300";
        randomBtn.className = "bg-amber-800/60 text-amber-200 font-bold px-3 py-2 rounded-xl text-sm sm:text-base transition";
        if (announce) speakGameText("已設定為今日真實日期練習");
      } else {
        gamePracticeState.target.month = Math.floor(Math.random() * 12) + 1;
        const daysInMonth = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
        gamePracticeState.target.day = Math.floor(Math.random() * daysInMonth[gamePracticeState.target.month - 1]) + 1;
        gamePracticeState.target.weekday = Math.floor(Math.random() * 7);
        gamePracticeState.target.season = getSeasonIndexByMonth(gamePracticeState.target.month);

        randomBtn.className = "bg-amber-600 text-white font-bold px-3 py-2 rounded-xl text-sm sm:text-base shadow transition border-2 border-amber-300";
        todayBtn.className = "bg-amber-800/60 text-amber-200 font-bold px-3 py-2 rounded-xl text-sm sm:text-base transition";
        if (announce) speakGameText("已切換為隨機題目練習");
      }

      resetAllAnswers();
      goToStep(1);
    }

    function toggleAudio() {
      gamePracticeState.audioEnabled = !gamePracticeState.audioEnabled;
      const label = document.getElementById('audio-label');
      const icon = document.getElementById('audio-icon');
      if (gamePracticeState.audioEnabled) {
        label.textContent = '聲音開';
        icon.textContent = '🔊';
        speakGameText('聲音已開啟');
      } else {
        label.textContent = '聲音關';
        icon.textContent = '🔇';
        window.speechSynthesis.cancel();
      }
    }

    function goToStep(stepNum) {
      gamePracticeState.currentStep = stepNum;

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

      const badge = document.getElementById('question-badge');
      const qText = document.getElementById('question-text');
      const deckTitle = document.getElementById('deck-header-title');

      const v1 = document.getElementById('view-step-1');
      const v2 = document.getElementById('view-step-2');
      const v3 = document.getElementById('view-step-3');
      const v4 = document.getElementById('view-step-4');

      const dMonths = document.getElementById('deck-months');
      const dDigits = document.getElementById('deck-digits');
      const dWeekdays = document.getElementById('deck-weekdays');
      const dSeasons = document.getElementById('deck-seasons');

      v1.classList.add('hidden');
      v2.classList.add('hidden');
      v3.classList.add('hidden');
      v4.classList.add('hidden');

      dMonths.classList.add('hidden');
      dDigits.classList.add('hidden');
      dWeekdays.classList.add('hidden');
      dSeasons.classList.add('hidden');

      if (stepNum === 1) {
        badge.textContent = "第一題";
        qText.textContent = "現在是幾月？";
        deckTitle.innerHTML = '<span>選取月份卡 (1-12月)：</span>';
        v1.classList.remove('hidden');
        dMonths.classList.remove('hidden');
        selectSlot('month');
        speakGameText("第一題：現在是幾月？");
      } else if (stepNum === 2) {
        badge.textContent = "第二題";
        qText.textContent = "現在是幾日？";
        deckTitle.innerHTML = '<span>選取數字卡 (0-9)：</span>';
        v2.classList.remove('hidden');
        dDigits.classList.remove('hidden');
        selectSlot('day-tens');
        speakGameText("第二題：現在是幾日？");
      } else if (stepNum === 3) {
        badge.textContent = "第三題";
        qText.textContent = "現在是星期幾？";
        deckTitle.innerHTML = '<span>選取星期卡：</span>';
        v3.classList.remove('hidden');
        dWeekdays.classList.remove('hidden');
        selectSlot('weekday');
        speakGameText("第三題：現在是星期幾？");
      } else if (stepNum === 4) {
        badge.textContent = "第四題";
        qText.textContent = "現在是什麼季節？";
        deckTitle.innerHTML = '<span>選取季節卡：</span>';
        v4.classList.remove('hidden');
        dSeasons.classList.remove('hidden');
        selectSlot('season');
        speakGameText("第四題：現在是什麼季節？");
      }
    }

    function readCurrentQuestionSpeech() {
      if (gamePracticeState.currentStep === 1) {
        speakGameText("第一題：現在是幾月？");
      } else if (gamePracticeState.currentStep === 2) {
        speakGameText("第二題：現在是幾日？");
      } else if (gamePracticeState.currentStep === 3) {
        speakGameText("第三題：現在是星期幾？");
      } else if (gamePracticeState.currentStep === 4) {
        speakGameText("第四題：現在是什麼季節？");
      }
    }

    function renderAllDecks() {
      const monthDeck = document.getElementById('deck-months');
      monthDeck.innerHTML = '';
      for (let m = 1; m <= 12; m++) {
        const card = document.createElement('div');
        card.className = `card-shadow bg-amber-50 border-3 border-amber-300 hover:border-blue-500 rounded-2xl p-3 flex flex-col items-center justify-center cursor-pointer transition transform active:scale-95 select-none`;
        card.draggable = true;
        card.setAttribute('ondragstart', `handleDragStart(event, 'month', ${m})`);
        card.onclick = () => onCardPicked('month', m);
        card.innerHTML = `
          <span class="text-3xl sm:text-4xl font-black text-blue-900 tracking-tight">${m}</span>
          <span class="text-xs sm:text-sm font-bold text-amber-800">月</span>
        `;
        monthDeck.appendChild(card);
      }

      const digitDeck = document.getElementById('deck-digits');
      digitDeck.innerHTML = '';
      for (let d = 0; d <= 9; d++) {
        const card = document.createElement('div');
        card.className = `card-shadow bg-emerald-50 border-3 border-emerald-300 hover:border-blue-500 rounded-2xl p-2 sm:p-3 flex flex-col items-center justify-center cursor-pointer transition transform active:scale-95 select-none`;
        card.draggable = true;
        card.setAttribute('ondragstart', `handleDragStart(event, 'digit', ${d})`);
        card.onclick = () => onCardPicked('digit', d);
        card.innerHTML = `
          <span class="text-4xl sm:text-5xl font-black text-emerald-900 tracking-tight">${d}</span>
        `;
        digitDeck.appendChild(card);
      }

      const weekdayDeck = document.getElementById('deck-weekdays');
      weekdayDeck.innerHTML = '';
      WEEKDAYS_ZH.forEach((wkStr, idx) => {
        const card = document.createElement('div');
        card.className = `card-shadow bg-purple-50 border-3 border-purple-300 hover:border-blue-500 rounded-2xl p-3 flex flex-col items-center justify-center cursor-pointer transition transform active:scale-95 select-none`;
        card.draggable = true;
        card.setAttribute('ondragstart', `handleDragStart(event, 'weekday', ${idx})`);
        card.onclick = () => onCardPicked('weekday', idx);
        card.innerHTML = `
          <span class="text-xl sm:text-2xl font-black text-purple-900 tracking-tight">${wkStr}</span>
        `;
        weekdayDeck.appendChild(card);
      });

      const seasonDeck = document.getElementById('deck-seasons');
      seasonDeck.innerHTML = '';
      SEASONS_DATA.forEach((sData, idx) => {
        const card = document.createElement('div');
        card.className = `card-shadow ${sData.color} border-3 hover:border-blue-500 rounded-2xl p-3 flex flex-col items-center justify-center cursor-pointer transition transform active:scale-95 select-none`;
        card.draggable = true;
        card.setAttribute('ondragstart', `handleDragStart(event, 'season', ${idx})`);
        card.onclick = () => onCardPicked('season', idx);
        card.innerHTML = `
          <span class="text-3xl sm:text-4xl mb-1">${sData.icon}</span>
          <span class="text-xl sm:text-2xl font-black tracking-tight">${sData.name}</span>
        `;
        seasonDeck.appendChild(card);
      });
    }

    function selectSlot(slotName) {
      gamePracticeState.selectedSlot = slotName;
      ['month', 'day-tens', 'day-units', 'weekday', 'season'].forEach(s => {
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
        gamePracticeState.userAnswers.month = value;
        renderSlotContent('month', `${value}`, '月', 'bg-blue-600 text-white');
        speakGameText(`${value}月`);
      } else if (type === 'digit') {
        let targetSlot = gamePracticeState.selectedSlot;
        if (targetSlot !== 'day-tens' && targetSlot !== 'day-units') {
          targetSlot = 'day-tens';
        }

        if (targetSlot === 'day-tens') {
          gamePracticeState.userAnswers.dayTens = value;
          renderSlotContent('day-tens', `${value}`, '', 'bg-emerald-600 text-white');
          speakGameText(`十位：${value}`);
          selectSlot('day-units');
        } else {
          gamePracticeState.userAnswers.dayUnits = value;
          renderSlotContent('day-units', `${value}`, '', 'bg-emerald-600 text-white');
          speakGameText(`個位：${value}`);
        }
      } else if (type === 'weekday') {
        gamePracticeState.userAnswers.weekday = value;
        renderSlotContent('weekday', WEEKDAYS_ZH[value], '', 'bg-purple-700 text-white');
        speakGameText(`${WEEKDAYS_ZH[value]}`);
      } else if (type === 'season') {
        gamePracticeState.userAnswers.season = value;
        const sData = SEASONS_DATA[value];
        renderSlotContent('season', `${sData.icon} ${sData.name}`, '', 'bg-orange-600 text-white');
        speakGameText(`${sData.name}`);
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
      e.stopPropagation();
      if (slotKey === 'month') gamePracticeState.userAnswers.month = null;
      if (slotKey === 'day-tens') gamePracticeState.userAnswers.dayTens = null;
      if (slotKey === 'day-units') gamePracticeState.userAnswers.dayUnits = null;
      if (slotKey === 'weekday') gamePracticeState.userAnswers.weekday = null;
      if (slotKey === 'season') gamePracticeState.userAnswers.season = null;

      document.getElementById(`slot-${slotKey}-content`).innerHTML = '';
      selectSlot(slotKey);
      playPopSound();
    }

    function resetCurrentStep() {
      if (gamePracticeState.currentStep === 1) {
        clearSlot(new Event('click'), 'month');
      } else if (gamePracticeState.currentStep === 2) {
        clearSlot(new Event('click'), 'day-tens');
        clearSlot(new Event('click'), 'day-units');
      } else if (gamePracticeState.currentStep === 3) {
        clearSlot(new Event('click'), 'weekday');
      } else if (gamePracticeState.currentStep === 4) {
        clearSlot(new Event('click'), 'season');
      }
    }

    function resetAllAnswers() {
      gamePracticeState.userAnswers = { month: null, dayTens: null, dayUnits: null, weekday: null, season: null };
      ['month', 'day-tens', 'day-units', 'weekday', 'season'].forEach(s => {
        const el = document.getElementById(`slot-${s}-content`);
        if (el) el.innerHTML = '';
      });
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
        } else if ((targetSlot === 'day-tens' || targetSlot === 'day-units') && data.type === 'digit') {
          selectSlot(targetSlot);
          onCardPicked('digit', data.value);
        } else if (targetSlot === 'weekday' && data.type === 'weekday') {
          onCardPicked('weekday', data.value);
        } else if (targetSlot === 'season' && data.type === 'season') {
          onCardPicked('season', data.value);
        }
      } catch (err) {}
    }

    function checkCurrentStepAnswer() {
      if (gamePracticeState.currentStep === 1) {
        if (gamePracticeState.userAnswers.month === null) {
          speakGameText("請先選擇月份卡");
          return;
        }

        if (gamePracticeState.userAnswers.month === gamePracticeState.target.month) {
          playSuccessFanfare();
          showModal(true, `答對了！現在是 ${gamePracticeState.target.month} 月`, "🌟 自動進入第二題");
          speakGameText(`太棒了！答對了！現在是 ${gamePracticeState.target.month} 月。我們接著做第二題！`);
        } else {
          playErrorSound();
          speakGameText(`再試一次喔！您選的是 ${gamePracticeState.userAnswers.month}月`);
        }

      } else if (gamePracticeState.currentStep === 2) {
        if (gamePracticeState.userAnswers.dayTens === null || gamePracticeState.userAnswers.dayUnits === null) {
          speakGameText("請完成日期的十位與個位數字");
          return;
        }

        const userDay = gamePracticeState.userAnswers.dayTens * 10 + gamePracticeState.userAnswers.dayUnits;
        if (userDay === gamePracticeState.target.day) {
          playSuccessFanfare();
          showModal(true, `答對了！現在是 ${gamePracticeState.target.day} 日`, "🌟 自動進入第三題");
          speakGameText(`真厲害！答對了！現在是 ${gamePracticeState.target.day} 日。我們接著做第三題！`);
        } else {
          playErrorSound();
          speakGameText(`再試一次喔！您組合的是 ${userDay}日`);
        }

      } else if (gamePracticeState.currentStep === 3) {
        if (gamePracticeState.userAnswers.weekday === null) {
          speakGameText("請選擇星期卡");
          return;
        }

        if (gamePracticeState.userAnswers.weekday === gamePracticeState.target.weekday) {
          playSuccessFanfare();
          showModal(true, `答對了！今天是 ${WEEKDAYS_ZH[gamePracticeState.target.weekday]}`, "🌟 自動進入第四題");
          speakGameText(`答對了！今天是 ${WEEKDAYS_ZH[gamePracticeState.target.weekday]}。我們接著做第四題！`);
        } else {
          playErrorSound();
          speakGameText(`再試一次喔！您選的是 ${WEEKDAYS_ZH[gamePracticeState.userAnswers.weekday]}`);
        }

      } else if (gamePracticeState.currentStep === 4) {
        if (gamePracticeState.userAnswers.season === null) {
          speakGameText("請選擇季節卡");
          return;
        }

        if (gamePracticeState.userAnswers.season === gamePracticeState.target.season) {
          playSuccessFanfare();
          triggerConfetti();

          const targetSeasonObj = SEASONS_DATA[gamePracticeState.target.season];
          const fullDateStr = `${gamePracticeState.target.month}月${gamePracticeState.target.day}日 ${WEEKDAYS_ZH[gamePracticeState.target.weekday]} (${targetSeasonObj.name})`;
          showModal(true, `🎉 太厲害了！全對了！<br>今天是 ${fullDateStr}`, "🌟 完成練習 / 再玩一次");
          speakGameText(`恭喜您！四題全部答對！今天是 ${fullDateStr}！`);
        } else {
          playErrorSound();
          const pickedSeasonName = SEASONS_DATA[gamePracticeState.userAnswers.season].name;
          speakGameText(`再試一次喔！您選的是 ${pickedSeasonName}`);
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
        if (gamePracticeState.currentStep === 1) {
          goToStep(2);
        } else if (gamePracticeState.currentStep === 2) {
          goToStep(3);
        } else if (gamePracticeState.currentStep === 3) {
          goToStep(4);
        } else if (gamePracticeState.currentStep === 4) {
          setMode(gamePracticeState.mode, false);
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

    /* 初始化 */
    window.onload = function() {
      // 1. 初始化天氣與時鐘
      updateClockAndDate();
      fetchHKOData();
      setInterval(updateClockAndDate, 1000);

      // 2. 初始化現實導向練習區
      setMode('today', false);
      renderAllDecks();
      goToStep(1);
    };
  </script>
</body>
</html>
