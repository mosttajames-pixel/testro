<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
  <title>職業治療關懷 — 每日天氣生活板</title>
  <style>
    /* ==================== 基礎與高對比色彩設定 ==================== */
    :root {
      --bg-color: #f0f4f8;
      --card-time-bg: #fff9db; /* 暖黃 - 現實導向區 */
      --card-time-border: #f59f00;
      --card-clock-bg: #e0f2fe; /* 淡天空藍 - 標準大時鐘 (淺色底) */
      --card-clock-border: #0284c7;
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
    body.large-font-mode .big-time-digits { font-size: 92px; }
    body.large-font-mode .temp-display { font-size: 64px; }
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

    /* 頂部主標題 */
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

    /* 手動輸入「現在地方」設定區 */
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

    /* 現實導向網格 - 多欄響應式佈局 */
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

    /* ==================== 插入：香港標準時間大時鐘卡片 (淺色主題) ==================== */
    .standard-clock-card {
      background: linear-gradient(135deg, #e0f2fe 0%, #f0f9ff 100%);
      border-color: var(--card-clock-border);
      color: #0f172a;
      text-align: center;
      box-shadow: 0 6px 18px rgba(2, 132, 199, 0.12);
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    .clock-top-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 2px solid rgba(2, 132, 199, 0.25);
      padding-bottom: 10px;
      flex-wrap: wrap;
      gap: 10px;
    }

    .clock-top-title {
      font-size: 26px;
      font-weight: 900;
      color: #0369a1;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .clock-ref-badge {
      background-color: rgba(2, 132, 199, 0.1);
      color: #0369a1;
      border: 2px solid #0284c7;
      padding: 6px 14px;
      border-radius: 50px;
      font-size: 18px;
      font-weight: 800;
      letter-spacing: 0.5px;
    }

    /* 傳統圓形鐘錶面容器 */
    .big-clock-container {
      background-color: #ffffff;
      border: 3px solid #7dd3fc;
      border-radius: 20px;
      padding: 24px 16px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 18px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    }

    .analog-clock-wrapper {
      position: relative;
      width: 290px;
      height: 290px;
      margin: 0 auto;
    }

    .analog-clock-face {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: radial-gradient(circle, #ffffff 68%, #e2e8f0 100%);
      border: 10px solid #38bdf8;
      box-shadow: 0 0 25px rgba(56, 189, 248, 0.6), inset 0 0 15px rgba(0, 0, 0, 0.2);
      position: relative;
    }

    /* 錶面數字 1-12 */
    .clock-number {
      position: absolute;
      width: 44px;
      height: 44px;
      text-align: center;
      line-height: 44px;
      font-size: 28px;
      font-weight: 900;
      color: #0f172a;
    }

    /* 指針通用設定 */
    .clock-hand {
      position: absolute;
      bottom: 50%;
      left: 50%;
      transform-origin: bottom center;
      border-radius: 10px;
    }

    /* 時針 (深色粗短) */
    .hour-hand {
      width: 10px;
      height: 72px;
      margin-left: -5px;
      background-color: #0f172a;
      z-index: 3;
    }

    /* 分針 (藍色較長) */
    .minute-hand {
      width: 6px;
      height: 100px;
      margin-left: -3px;
      background-color: #0284c7;
      z-index: 4;
    }

    /* 秒針 (鮮紅細長) */
    .second-hand {
      width: 3px;
      height: 115px;
      margin-left: -1.5px;
      background-color: #e03131;
      z-index: 5;
    }

    /* 錶面中心點 */
    .clock-center-pin {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 20px;
      height: 20px;
      margin-top: -10px;
      margin-left: -10px;
      background-color: #e03131;
      border: 3.5px solid #ffffff;
      border-radius: 50%;
      z-index: 6;
      box-shadow: 0 2px 6px rgba(0,0,0,0.4);
    }

    /* 輔助時間與上午/下午顯示列 */
    .digital-sub-display {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      background: #f0f9ff;
      padding: 10px 28px;
      border-radius: 30px;
      border: 2.5px solid #0284c7;
    }

    .big-time-text {
      font-family: 'Courier New', Consolas, Monaco, monospace;
      font-size: 36px;
      font-weight: 900;
      color: #0c4a6e;
      letter-spacing: 2px;
    }

    .big-ampm-tag {
      font-size: 22px;
      font-weight: 900;
      background-color: #d9480f;
      color: #ffffff;
      padding: 4px 14px;
      border-radius: 10px;
      letter-spacing: 1px;
    }

    /* 特大字體模式下適應大時鐘 */
    body.large-font-mode .analog-clock-wrapper {
      width: 330px;
      height: 330px;
    }
    body.large-font-mode .clock-number {
      font-size: 32px;
    }
    body.large-font-mode .hour-hand { height: 85px; }
    body.large-font-mode .minute-hand { height: 118px; }
    body.large-font-mode .second-hand { height: 135px; }

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

    /* ==================== 四、流動裝置響應式設計 (Mobile Responsive) ==================== */
    @media (max-width: 1024px) {
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-clock, .col-lunar, .col-season, .col-festi { grid-column: span 6; }
    }

    @media (max-width: 768px) {
      body { padding: 10px; }
      header { padding: 16px 12px; }
      header h1 { font-size: 24px; }
      
      .action-btn { font-size: 18px; padding: 8px 16px; }
      
      .ro-header-bar { flex-direction: column; align-items: flex-start; }
      .location-setting-box { width: 100%; }
      .location-input { width: 100%; min-width: 0; }

      .ro-grid { gap: 10px; }
      
      .col-loc-1, .col-loc-2 { grid-column: span 6; }
      .col-year, .col-month, .col-day, .col-week { grid-column: span 6; }
      .col-clock, .col-lunar, .col-season, .col-festi { grid-column: span 12; }

      .big-time-digits { font-size: 56px; letter-spacing: 2px; }
      .big-ampm-tag { font-size: 24px; padding: 4px 12px; }
      .big-date-banner { font-size: 20px; }

      .ro-label { font-size: 19px; }
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
      .analog-clock-wrapper { width: 230px; height: 230px; }
      .clock-number { font-size: 22px; width: 34px; height: 34px; line-height: 34px; }
      .hour-hand { height: 55px; width: 8px; margin-left: -4px; }
      .minute-hand { height: 78px; width: 5px; margin-left: -2.5px; }
      .second-hand { height: 90px; }
      .big-time-text { font-size: 24px; }
      .big-ampm-tag { font-size: 18px; }
      .ro-value-main { font-size: 28px; }
      .ro-value-time { font-size: 30px; }
      .temp-display { font-size: 40px; }
      .forecast-grid { grid-template-columns: repeat(2, 1fr); }
    }
  </style>
</head>
<body>

  <div class="container">
    <header>
      <h1>職業治療關懷 — 每日天氣生活板</h1>
      <div class="action-bar">
        <button class="action-btn" id="refresh-btn" onclick="refreshData()">
          <span id="refresh-icon" style="display:inline-flex;align-items:center;justify-content:center;">🔄</span> <span>條目更新</span>
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
        <!-- 第1格：地區 -->
        <div class="ro-block col-loc-1">
          <div class="ro-label"><span>📍</span><span>地區</span></div>
          <div class="ro-value-main ro-value-highlight" id="ro-display-district">深水埗</div>
        </div>

        <!-- 第2格：地點 -->
        <div class="ro-block col-loc-2">
          <div class="ro-label"><span>🏢</span><span>地點</span></div>
          <div class="ro-value-main" id="ro-display-detail" style="color: #c92a2a;">社區中心 3樓大堂</div>
        </div>

        <!-- 年份 -->
        <div class="ro-block col-year">
          <div class="ro-label"><span>📅</span><span>年份</span></div>
          <div class="ro-value-main" id="ro-year">----年</div>
        </div>

        <!-- 月份 -->
        <div class="ro-block col-month">
          <div class="ro-label"><span>📆</span><span>月份</span></div>
          <div class="ro-value-main" id="ro-month">--月</div>
        </div>

        <!-- 日期 -->
        <div class="ro-block col-day">
          <div class="ro-label"><span>☀️</span><span>日期</span></div>
          <div class="ro-value-main ro-value-highlight" id="ro-date-num">--日</div>
        </div>

        <!-- 星期 -->
        <div class="ro-block col-week">
          <div class="ro-label"><span>🗓️</span><span>星期</span></div>
          <div class="ro-value-main" id="ro-day-of-week" style="color: #1864ab;">星期-</div>
        </div>

        <!-- 當前時間簡示 -->
        <div class="ro-block col-clock">
          <div class="ro-label"><span>🕒</span><span>簡要時間</span></div>
          <div class="ro-value-time" id="clock-time">--:--</div>
          <div class="ro-value-sub" id="clock-ampm">上午/下午</div>
        </div>

        <!-- 農曆與節氣 -->
        <div class="ro-block col-lunar">
          <div class="ro-label"><span>🌾</span><span>農曆與節氣</span></div>
          <div class="ro-value-main" id="ro-lunar" style="font-size: 28px;">農曆 --月--</div>
          <div class="ro-value-sub" id="ro-solar-term" style="color: #d9480f;">節氣：--</div>
        </div>

        <!-- 當前季節 -->
        <div class="ro-block col-season">
          <div class="ro-label"><span>🍂</span><span>當前季節</span></div>
          <div style="display:flex; align-items:center; justify-content:center; gap:8px; margin: auto 0;">
            <span id="season-icon" style="font-size: 40px; line-height: 1;">🌱</span>
            <span class="ro-value-main" id="season-text" style="color: #2b8a3e;">--</span>
          </div>
        </div>

        <!-- 將到節日 -->
        <div class="ro-block col-festi">
          <div class="ro-label"><span>🎉</span><span>將到節日</span></div>
          <div class="ro-value-main" id="ro-festival-name" style="color: #c92a2a; font-size: 28px;">--</div>
          <div class="ro-value-sub" id="ro-festival-countdown">--</div>
        </div>
      </div>
    </section>

    <!-- ==================== 新增：香港標準時間大時鐘 (HKO Standard Big Clock) ==================== -->
    <section class="card standard-clock-card" aria-label="香港標準時間大時鐘">
      <div class="clock-top-bar">
        <div class="clock-top-title">
          <span>⏱️</span>
          <span>香港標準時間大時鐘 (Hong Kong Standard Time)</span>
        </div>
        <div class="clock-ref-badge">
          🌐 參考香港天文台傳統鐘錶
        </div>
      </div>

      <div class="big-clock-container">
        <!-- 傳統圓形鐘錶面 -->
        <div class="analog-clock-wrapper">
          <div class="analog-clock-face" id="analog-clock-face">
            <div class="clock-hand hour-hand" id="analog-hour-hand"></div>
            <div class="clock-hand minute-hand" id="analog-minute-hand"></div>
            <div class="clock-hand second-hand" id="analog-second-hand"></div>
            <div class="clock-center-pin"></div>
          </div>
        </div>

        <!-- 輔助數碼與上午/下午對照 (只顯示時分) -->
        <div class="digital-sub-display">
          <div class="big-ampm-tag" id="standard-big-ampm">上午</div>
          <div class="big-time-text" id="standard-big-clock">00:00</div>
        </div>
      </div>
    </section>

    <!-- 二、香港天文台即時天氣與預測區 (藍色部份) -->
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
  </div>

  <script>
    /* ==================== 1. 即時時鐘與日期邏輯 (含傳統鐘錶面) ==================== */
    function renderClockNumbers() {
      const clockFace = document.getElementById('analog-clock-face');
      if (!clockFace || clockFace.querySelector('.clock-number')) return;

      const radius = 115; // 數字環半徑
      const centerX = 145; // 中心 X (基於 290px 寬)
      const centerY = 145; // 中心 Y

      for (let i = 1; i <= 12; i++) {
        const numElem = document.createElement('div');
        numElem.className = 'clock-number';
        numElem.textContent = i;

        // 計算 1-12 數字在圓周上的角度 (以12點鐘方向為起點)
        const angle = (i * 30 - 90) * (Math.PI / 180);
        const x = centerX + radius * Math.cos(angle) - 22;
        const y = centerY + radius * Math.sin(angle) - 22;

        numElem.style.left = `${x}px`;
        numElem.style.top = `${y}px`;

        clockFace.appendChild(numElem);
      }
    }

    function updateClockAndDate() {
      const now = new Date();
      
      // 時間數據
      let hoursInt = now.getHours();
      const minutesInt = now.getMinutes();
      const secondsInt = now.getSeconds();

      const ampm = hoursInt >= 12 ? '下午' : '上午';
      const hoursStr = String(hoursInt).padStart(2, '0');
      const minutesStr = String(minutesInt).padStart(2, '0');
      const secondsStr = String(secondsInt).padStart(2, '0');
      
      // 更新現實導向卡片內的小時鐘
      document.getElementById('clock-time').textContent = `${hoursStr}:${minutesStr}`;
      document.getElementById('clock-ampm').textContent = `${ampm}`;

      // 旋轉傳統鐘錶指針 (計算旋轉角度)
      const secondsDeg = (secondsInt / 60) * 360;
      const minutesDeg = ((minutesInt + secondsInt / 60) / 60) * 360;
      const hoursDeg = (((hoursInt % 12) + minutesInt / 60 + secondsInt / 3600) / 12) * 360;

      const hourHand = document.getElementById('analog-hour-hand');
      const minuteHand = document.getElementById('analog-minute-hand');
      const secondHand = document.getElementById('analog-second-hand');

      if (hourHand) hourHand.style.transform = `rotate(${hoursDeg}deg)`;
      if (minuteHand) minuteHand.style.transform = `rotate(${minutesDeg}deg)`;
      if (secondHand) secondHand.style.transform = `rotate(${secondsDeg}deg)`;

      // 更新下方輔助數碼時間 (不顯示秒數)
      document.getElementById('standard-big-clock').textContent = `${hoursStr}:${minutesStr}`;
      document.getElementById('standard-big-ampm').textContent = ampm;

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

    /* 更新「現在地方」雙格動態顯示 */
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

      tips.push(`老友記好，歡迎來到 ${fullLocation}！`);

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
      utterance.rate = 0.85; // 適中偏慢，利於長者聆聽

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

    /* ==================== 初始化執行 ==================== */
    window.addEventListener('DOMContentLoaded', () => {
      renderClockNumbers();
      updateClockAndDate();
      setInterval(updateClockAndDate, 1000); // 每一秒精確更新大時鐘指針與秒數
      updateCurrentLocationDisplay();
      fetchHKOData();
    });
  </script>
</body>
</html>
