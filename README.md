<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>職業治療關懷 — 每日天氣生活板</title>
  <style>
    /* ==================== 基礎與高對比色彩設定 ==================== */
    :root {
      --bg-color: #f0f4f8;
      --card-time-bg: #fff9db; /* 暖黃 - 時間與現實導向 */
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
    body.large-font-mode .ro-label { font-size: 34px; }
    body.large-font-mode .ro-value-time { font-size: 56px; }
    body.large-font-mode .ro-value-date { font-size: 40px; }
    body.large-font-mode .ro-value-lunar { font-size: 32px; }
    body.large-font-mode .temp-display { font-size: 60px; }
    body.large-font-mode .weather-info-text { font-size: 30px; }
    body.large-font-mode .care-message-box { font-size: 34px; }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "PingFang HK", "Microsoft JhengHei", sans-serif;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-main);
      padding: 20px;
      line-height: 1.5;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 24px;
    }

    /* 頂部主標題 */
    header {
      text-align: center;
      background-color: #1a365d;
      color: #ffffff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }

    header h1 {
      font-size: 38px;
      font-weight: 800;
      letter-spacing: 2px;
    }

    /* 頂部快捷功能按鈕區 */
    .action-bar {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 16px;
      flex-wrap: wrap;
      margin-top: 14px;
    }

    .action-btn {
      background-color: #ffffff;
      color: #1a365d;
      border: 3px solid #ffffff;
      padding: 10px 22px;
      font-size: 22px;
      font-weight: 800;
      border-radius: 50px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
      transition: all 0.2s ease;
    }

    .action-btn:hover {
      background-color: #e2e8f0;
      transform: translateY(-2px);
    }

    .action-btn:active {
      transform: translateY(0);
    }

    .action-btn.active {
      background-color: #ff2d55;
      color: #ffffff;
      border-color: #ff2d55;
    }

    /* 通用卡片樣式 */
    .card {
      border-radius: 24px;
      padding: 24px;
      border: 4px solid;
      box-shadow: 0 6px 16px rgba(0,0,0,0.08);
      background-color: #ffffff;
    }

    /* ==================== 一、現實導向區 (Reality Orientation) ==================== */
    .ro-card {
      background-color: var(--card-time-bg);
      border-color: var(--card-time-border);
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 20px;
      align-items: stretch;
    }

    .ro-block {
      text-align: center;
      padding: 16px 12px;
      background: rgba(255, 255, 255, 0.7);
      border-radius: 16px;
      border: 2px solid rgba(0, 0, 0, 0.05);
      display: flex;
      flex-direction: column;
      justify-content: flex-start; /* 確保內容自頂部開始排列 */
      align-items: center;
      height: 100%;
    }

    .ro-block-half {
      grid-column: span 3;
    }

    .ro-block-third {
      grid-column: span 2;
    }

    .ro-label {
      font-size: 30px;
      font-weight: 700;
      color: #2b8a3e;
      margin-top: 0;
      margin-bottom: 12px;
      text-align: center;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center; /* 置中對齊 */
      gap: 6px;
      align-self: flex-start; /* 確保固定在卡片最頂部 */
    }

    .ro-value-time {
      font-size: 48px;
      font-weight: 900;
      color: #d9480f;
      font-family: monospace;
      margin: auto 0;
      text-align: center;
    }

    .ro-value-date {
      font-size: 34px;
      font-weight: 800;
      color: #121212;
      text-align: center;
    }

    .ro-value-lunar {
      font-size: 28px;
      font-weight: 700;
      color: #862e9c;
      text-align: center;
    }

    .ro-value-season {
      font-size: 30px;
      font-weight: 800;
      color: #2b8a3e;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 6px;
      width: 100%;
      margin: auto 0;
    }

    .ro-block-half {
      grid-column: span 3;
    }

    .ro-block-third {
      grid-column: span 2;
    }

    .ro-label {
      font-size: 30px;
      font-weight: 700;
      color: #2b8a3e;
      margin-bottom: 8px;
      text-align: center;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
    }

    .ro-value-time {
      font-size: 48px;
      font-weight: 900;
      color: #d9480f;
      font-family: monospace;
      margin: auto 0;
      text-align: center;
    }

    .ro-value-date {
      font-size: 34px;
      font-weight: 800;
      color: #121212;
      text-align: center;
    }

    .ro-value-lunar {
      font-size: 28px;
      font-weight: 700;
      color: #862e9c;
      text-align: center;
    }

    .ro-value-season {
      font-size: 30px;
      font-weight: 800;
      color: #2b8a3e;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 6px;
      width: 100%;
    }

    .season-icon-large {
      font-size: 56px;
      line-height: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto;
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
      gap: 16px;
      margin-bottom: 20px;
      border-bottom: 3px solid var(--card-weather-border);
      padding-bottom: 16px;
    }

    .district-select-container {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .district-select-container label {
      font-size: 26px;
      font-weight: 800;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    select.district-select {
      font-size: 26px;
      font-weight: bold;
      padding: 10px 20px;
      border-radius: 16px;
      border: 3px solid var(--card-weather-border);
      background-color: #ffffff;
      color: #121212;
      cursor: pointer;
    }

    .weather-main-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
      gap: 20px;
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
      justify-content: center;
      text-align: center;
      min-height: 190px;
      width: 100%;
      margin: 0 auto;
    }

    /* 統一圖示容器置中設定 */
    .weather-icon-container {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
      text-align: center;
      gap: 12px;
      margin: 8px auto;
      width: 100%;
    }

    .weather-emoji-large {
      font-size: 64px;
      line-height: 1;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
      margin: 0 auto;
    }

    .weather-icon-large {
      width: 90px;
      height: 90px;
      object-fit: contain;
      display: block;
      flex-shrink: 0;
      margin: 0 auto;
    }

    .temp-display {
      font-size: 52px;
      font-weight: 900;
      color: #c92a2a;
      margin: auto 0;
      text-align: center;
    }

    .weather-info-text {
      font-size: 26px;
      font-weight: 700;
      margin-top: 6px;
      text-align: center;
    }

    .warning-icon-large {
      font-size: 52px;
      line-height: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: auto auto;
    }

    .alert-container {
      margin-top: 20px;
      padding: 16px 24px;
      background-color: var(--alert-bg);
      border: 3px solid var(--alert-border);
      border-radius: 16px;
      display: none;
      align-items: center;
      justify-content: center;
      gap: 16px;
    }

    .alert-container.active {
      display: flex;
    }

    .alert-icon {
      font-size: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .alert-text {
      font-size: 26px;
      font-weight: 800;
      color: var(--alert-text);
      text-align: center;
    }

    .forecast-section {
      margin-top: 24px;
    }

    .forecast-title {
      font-size: 28px;
      font-weight: 800;
      margin-bottom: 12px;
      color: #3b5bdb;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .forecast-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 14px;
    }

    .forecast-card {
      background-color: var(--card-forecast-bg);
      border: 3px solid var(--card-forecast-border);
      border-radius: 16px;
      padding: 14px 10px;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
    }

    .forecast-icon-wrapper {
      margin: 8px auto;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 4px;
      width: 100%;
    }

    .forecast-date {
      font-size: 22px;
      font-weight: 800;
      color: #3b5bdb;
      text-align: center;
    }

    .forecast-temp {
      font-size: 24px;
      font-weight: 800;
      color: #e03131;
      margin-top: 6px;
      text-align: center;
    }

    /* ==================== 三、關懷提示與語音朗讀區 ==================== */
    .care-card {
      background-color: var(--card-care-bg);
      border-color: var(--card-care-border);
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .care-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 16px;
    }

    .care-title {
      font-size: 32px;
      font-weight: 800;
      color: #2b8a3e;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .tts-btn {
      background-color: #2f9e44;
      color: #ffffff;
      border: none;
      padding: 16px 32px;
      font-size: 28px;
      font-weight: 900;
      border-radius: 50px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      box-shadow: 0 6px 12px rgba(47, 158, 68, 0.3);
      transition: transform 0.1s, background-color 0.2s;
    }

    .tts-btn:hover {
      background-color: #2b8a3e;
      transform: scale(1.02);
    }

    .tts-btn:active {
      transform: scale(0.98);
    }

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
      padding: 24px;
      border-radius: 20px;
      border: 3px dashed var(--card-care-border);
      font-size: 30px;
      font-weight: 800;
      color: #212529;
      line-height: 1.6;
    }

    @media (max-width: 768px) {
      header h1 { font-size: 28px; }
      .ro-card { grid-template-columns: 1fr; }
      .ro-block-half, .ro-block-third { grid-column: span 1; }
      .ro-value-time { font-size: 38px; }
      .ro-value-date { font-size: 26px; }
      .temp-display { font-size: 40px; }
      .care-message-box { font-size: 22px; }
      .tts-btn { font-size: 22px; width: 100%; justify-content: center; }
    }
  </style>
</head>
<body>

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

    <!-- 一、現實導向區 (Reality Orientation) -->
    <section class="card ro-card" aria-label="現實導向資訊">
      <div class="ro-block ro-block-half">
        <div class="ro-label"><span>📅</span><span>西曆日期</span></div>
        <div class="ro-value-date" id="ro-date">----年--月--日</div>
        <div class="ro-value-date" id="ro-day" style="color: #1864ab; margin-top: 6px;">星期-</div>
      </div>

      <div class="ro-block ro-block-half">
        <div class="ro-label"><span>🕒</span><span>當前時間</span></div>
        <div class="ro-value-time" id="clock-time">--:--:--</div>
      </div>

      <div class="ro-block ro-block-third">
        <div class="ro-label"><span>🌾</span><span>農曆與節氣</span></div>
        <div class="ro-value-lunar" id="ro-lunar">農曆 --月--</div>
        <div class="ro-value-lunar" id="ro-solar-term" style="color: #d9480f; margin-top: 6px;">節氣：--</div>
      </div>

      <div class="ro-block ro-block-third">
        <div class="ro-label"><span>🍂</span><span>當前季節</span></div>
        <div class="ro-value-season" id="ro-season">
          <span id="season-icon" class="season-icon-large">🌱</span>
          <span id="season-text">--</span>
        </div>
      </div>

      <div class="ro-block ro-block-third">
        <div class="ro-label"><span>🎉</span><span>將到節日</span></div>
        <div class="ro-value-lunar" id="ro-festival-name" style="color: #c92a2a; font-size: 30px; font-weight: 900;">--</div>
        <div id="ro-festival-countdown" style="font-size: 22px; font-weight: 800; color: #495057; margin-top: 6px; text-align: center;">--</div>
      </div>
    </section>

    <!-- 二、香港天文台即時天氣與預測區 -->
    <section class="card weather-card" aria-label="即時天氣">
      <div class="weather-header">
        <div class="district-select-container">
          <label for="district-select"><span>📍</span><span>選擇分區：</span></label>
          <select id="district-select" class="district-select" onchange="updateDistrictTemperature()">
            <option value="沙田">沙田</option>
            <option value="香港天文台" selected>尖沙咀 (天文台)</option>
            <option value="觀塘">觀塘</option>
            <option value="中赤鱲角">機場 (赤鱲角)</option>
            <option value="九龍城">九龍城</option>
            <option value="黃大仙">黃大仙</option>
            <option value="深水埗">深水埗</option>
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
        <div style="font-size: 20px; color: var(--text-muted); font-weight: bold;">
          數據來源：香港天文台 API
        </div>
      </div>

      <div class="weather-main-grid">
        <div class="weather-box">
          <div class="ro-label"><span>☁️</span><span>天氣狀況</span></div>
          <div class="weather-icon-container">
            <span id="weather-emoji" class="weather-emoji-large">⛅</span>
          </div>
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
          <div id="warning-box-icon" class="warning-icon-large">✅</div>
          <div class="weather-info-text" id="warning-box-desc" style="color: #2b8a3e; font-size: 22px;">現時無極端天氣警告</div>
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
          <span>🔊 聽語音（粵語）</span>
        </button>
      </div>

      <div class="care-message-box" id="care-message">
        正在為您生成今日天氣與生活關懷提示...
      </div>
    </section>
  </div>

  <script>
    /* ==================== 1. 即時時鐘與日期邏輯 ==================== */
    function updateClock() {
      const now = new Date();
      
      const hours = String(now.getHours()).padStart(2, '0');
      const minutes = String(now.getMinutes()).padStart(2, '0');
      const seconds = String(now.getSeconds()).padStart(2, '0');
      document.getElementById('clock-time').textContent = `${hours}:${minutes}:${seconds}`;

      const year = now.getFullYear();
      const month = now.getMonth() + 1;
      const date = now.getDate();
      document.getElementById('ro-date').textContent = `${year} 年 ${month} 月 ${date} 日`;

      const days = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
      const dayName = days[now.getDay()];
      document.getElementById('ro-day').textContent = dayName;

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
      "沙田": ["沙田"],
      "香港天文台": ["香港天文台", "九龍城"],
      "觀塘": ["觀塘"],
      "中赤鱲角": ["赤鱲角", "香港國際機場"],
      "九龍城": ["九龍城"],
      "黃大仙": ["黃大仙"],
      "深水埗": ["深水埗"],
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
      const weatherIconElem = document.getElementById('weather-icon');
      if (weatherIconElem) {
        weatherIconElem.src = `https://www.hko.gov.hk/images/HKOWEATHER_ICO/pic${iconCode}.png`;
      }
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
          <div style="font-size: 18px; font-weight: bold; color: #495057; text-align: center;">${item.week}</div>
          <div class="forecast-icon-wrapper">
            <span style="font-size: 42px; line-height: 1; display: inline-flex; align-items: center; justify-content: center;">${forecastEmoji}</span>
            <img src="https://www.hko.gov.hk/images/HKOWEATHER_ICO/pic${icon}.png" style="width:68px;height:68px;object-fit:contain;margin:0 auto;display:block;" alt="預測天氣" onerror="this.style.display='none'">
          </div>
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
      const festivalName = document.getElementById('ro-festival-name').textContent;

      let tips = [];

      if (temp >= 30) {
        tips.push(`今日${districtName}天氣酷熱，氣溫達到 ${temp} 度！長者記得要在室內開冷氣，定時補充水分，避免戶外劇烈運動。`);
      } else if (temp <= 16) {
        tips.push(`今日天氣較為寒冷，${districtName}只有 ${temp} 度。外出請穿著足夠保暖衣物，注意頭部與頸部保暖。`);
      } else {
        tips.push(`今日${districtName}氣溫約 ${temp} 度，體感舒適適宜。`);
      }

      if (humidity > 85) {
        tips.push(`相對濕度高達 ${humidity}%，地板可能較為濕滑，長者在家中行走請穿著防滑鞋，注意安全。`);
      } else if (humidity < 50) {
        tips.push(`天氣較為乾燥，記得多喝溫水，並塗抹潤膚膏保持皮膚滋潤。`);
      }

      if (warnings.some(w => w.includes('暴雨') || w.includes('雷暴'))) {
        tips.push(`目前有雨勢或雷暴警告，外出請務必帶傘，儘量留在安全室內。`);
      }

      if (festivalName && festivalName !== '--' && festivalName !== '平安健康') {
        tips.push(`臨近${festivalName}，祝您身體健康，保持愉快的心情！`);
      }

      const finalMsg = tips.join(' ') || `各位老人家好，今日天氣良好，請記得適時喝水，保持規律作息與愉快的心情！`;
      document.getElementById('care-message').textContent = finalMsg;
    }

    /* ==================== 5. 語音朗讀 (TTS) 與互動控制 ==================== */
    function speakROAndWeather() {
      if (!('speechSynthesis' in window)) {
        alert('您的瀏覽器不支援語音朗讀功能。');
        return;
      }

      const ttsBtn = document.getElementById('tts-btn');

      if (window.speechSynthesis.speaking) {
        window.speechSynthesis.cancel();
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語）';
        return;
      }

      const dateStr = document.getElementById('ro-date').textContent;
      const dayStr = document.getElementById('ro-day').textContent;
      const lunarStr = document.getElementById('ro-lunar').textContent;
      const careMsg = document.getElementById('care-message').textContent;

      const fullSpeechText = `早晨！今天是${dateStr}，${dayStr}，${lunarStr}。 ${careMsg}`;

      const utterance = new SpeechSynthesisUtterance(fullSpeechText);
      utterance.lang = 'zh-HK';
      utterance.rate = 0.85; // 專為長者設計的稍慢語速

      utterance.onstart = () => {
        ttsBtn.classList.add('speaking');
        ttsBtn.querySelector('span').textContent = '⏹️ 停止朗讀';
      };

      utterance.onend = () => {
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語）';
      };

      utterance.onerror = () => {
        ttsBtn.classList.remove('speaking');
        ttsBtn.querySelector('span').textContent = '🔊 聽語音（粵語）';
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

    /* ==================== 初始化執行 ==================== */
    window.addEventListener('DOMContentLoaded', () => {
      updateClock();
      setInterval(updateClock, 1000);
      fetchHKOData();
    });
  </script>
</body>
</html>
