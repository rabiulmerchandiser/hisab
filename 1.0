<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>হিসাব - আর্থিক ব্যবস্থাপনা</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@300;400;500;600;700;800&family=Sora:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --primary: #2A1F55;
    --primary-mid: #3D2A82;
    --primary-light: #6550C0;
    --accent: #B8A0F8;
    --accent-glow: rgba(184,160,248,0.3);
    --accent-green: #05C98A;
    --accent-red: #F45B6C;
    --accent-orange: #FFA940;
    --accent-blue: #4AABFF;
    --bg: #1C1740;
    --bg2: #221D4A;
    --card: #2A2452;
    --card2: #332C62;
    --text: #EAE4FF;
    --text-muted: #9A8FC8;
    --border: rgba(184,160,248,0.15);
    --shadow: 0 8px 32px rgba(0,0,0,0.35);
    --shadow-sm: 0 2px 12px rgba(0,0,0,0.22);
    --radius: 22px;
    --radius-sm: 14px;
    --glow-green: 0 0 16px rgba(5,201,138,0.28);
    --glow-red: 0 0 16px rgba(244,91,108,0.28);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

  body {
    font-family: 'Noto Sans Bengali', sans-serif;
    background: var(--bg);
    color: var(--text);
    max-width: 430px;
    margin: 0 auto;
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
  }

  /* background grid texture */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(200,180,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(200,180,255,0.03) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
    z-index: 0;
  }

  /* ===== TOP BAR ===== */
  .topbar {
    background: linear-gradient(160deg, #2A1F55 0%, #3D2A82 55%, #2A1F55 100%);
    padding: 52px 22px 30px;
    position: relative;
    overflow: hidden;
    border-radius: 0 0 36px 36px;
    border-bottom: 1px solid rgba(200,180,255,0.15);
    box-shadow: 0 8px 40px rgba(0,0,0,0.6);
  }
  .topbar::before {
    content: '';
    position: absolute;
    width: 280px; height: 280px;
    background: radial-gradient(circle, rgba(200,180,255,0.15) 0%, transparent 70%);
    border-radius: 50%;
    top: -80px; right: -60px;
  }
  .topbar::after {
    content: '';
    position: absolute;
    width: 160px; height: 160px;
    background: radial-gradient(circle, rgba(79,58,158,0.3) 0%, transparent 70%);
    border-radius: 50%;
    bottom: -40px; left: -20px;
  }
  .topbar-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 24px;
    position: relative; z-index: 1;
  }
  .greeting { color: var(--text-muted); font-size: 12px; letter-spacing: 0.5px; }
  .user-name { color: var(--text); font-size: 18px; font-weight: 700; margin-top: 2px; }
  .avatar {
    width: 46px; height: 46px;
    background: linear-gradient(135deg, rgba(200,180,255,0.2), rgba(79,58,158,0.3));
    border-radius: 16px;
    display: flex; align-items: center; justify-content: center;
    font-size: 22px; cursor: pointer;
    border: 1.5px solid rgba(200,180,255,0.3);
    box-shadow: 0 4px 16px rgba(0,0,0,0.3);
  }
  .balance-label {
    color: var(--text-muted);
    font-size: 11px;
    letter-spacing: 1px;
    text-transform: uppercase;
  }
  .balance-amount {
    color: var(--text);
    font-size: 34px;
    font-weight: 800;
    letter-spacing: -1.5px;
    margin: 4px 0 4px;
    text-shadow: 0 0 40px rgba(200,180,255,0.3);
  }
  .balance-change {
    color: var(--text-muted);
    font-size: 11px;
  }
  .balance-change span { color: var(--accent-green); font-weight: 700; }

  /* ===== TOPBAR — centered balance + 2-col pills ===== */
  .topbar-balance-center {
    text-align: center;
    position: relative; z-index: 1;
    margin-bottom: 18px;
  }
  .topbar-pills-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    position: relative; z-index: 1;
  }
  .pill-v {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(255,255,255,0.05);
    border-radius: 12px;
    padding: 7px 10px;
    border: 1px solid var(--border);
    backdrop-filter: blur(10px);
  }
  .pill-v-icon {
    width: 28px; height: 28px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 13px;
    flex-shrink: 0;
  }
  .pill-v-label {
    font-size: 8px;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.3px;
    font-weight: 700;
    line-height: 1;
  }
  .pill-v-value {
    font-size: 13px;
    font-weight: 800;
    line-height: 1.2;
    margin-top: 1px;
  }
  .pill-v-value.income  { color: var(--accent-green); }
  .pill-v-value.expense { color: var(--accent-red); }
  .pill-v-value.loan-out { color: var(--accent-orange); }
  .pill-v-value.loan-in  { color: var(--accent-blue); }

  /* ===== BOTTOM NAV — Modern Floating Pill ===== */
  .bottom-nav {
    position: fixed;
    bottom: 16px; left: 50%;
    transform: translateX(-50%);
    width: calc(100% - 32px);
    max-width: 398px;
    background: rgba(42,36,82,0.96);
    backdrop-filter: blur(28px);
    -webkit-backdrop-filter: blur(28px);
    display: flex;
    align-items: center;
    padding: 8px 6px;
    border-radius: 28px;
    border: 1px solid rgba(184,160,248,0.18);
    z-index: 100;
    gap: 2px;
    box-shadow: 0 8px 32px rgba(0,0,0,0.38), 0 2px 8px rgba(0,0,0,0.2);
  }
  .nav-btn {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
    background: none;
    border: none;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    padding: 6px 2px;
    border-radius: 20px;
    transition: all 0.2s;
    position: relative;
  }
  .nav-btn:active { transform: scale(0.90); }
  .nav-icon-wrap {
    width: 38px; height: 32px;
    border-radius: 16px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    transition: all 0.3s cubic-bezier(0.34,1.56,0.64,1);
    background: transparent;
  }
  .nav-btn.active .nav-icon-wrap {
    background: linear-gradient(135deg, var(--primary-mid), var(--primary-light));
    box-shadow: 0 3px 12px rgba(101,80,192,0.55);
    transform: scale(1.05);
  }
  .nav-label {
    font-size: 9px;
    font-weight: 700;
    color: var(--text-muted);
    letter-spacing: 0.2px;
    transition: color 0.2s;
    line-height: 1;
  }
  .nav-btn.active .nav-label { color: var(--accent); }
  .nav-active-dot {
    display: none;
  }

  /* ===== CONTENT ===== */
  .page { display: none; padding-bottom: 0; }
  .page.active { display: block; }
  .page-content { padding: 18px; padding-bottom: 110px; }

  /* Section title */
  .section-head {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 14px;
  }
  .section-title { font-size: 13px; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px; }
  .view-all { font-size: 12px; color: var(--accent); font-weight: 600; cursor: pointer; opacity: 0.9; }

  /* ===== CARDS ===== */
  .card {
    background: var(--card);
    border-radius: var(--radius);
    box-shadow: var(--shadow-sm);
    padding: 18px;
    margin-bottom: 14px;
    border: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(200,180,255,0.2), transparent);
  }

  /* Quick add buttons */
  .quick-add {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 10px;
    margin-bottom: 18px;
  }
  .quick-btn {
    background: var(--card);
    border-radius: 18px;
    padding: 14px 4px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 7px;
    cursor: pointer;
    box-shadow: var(--shadow-sm);
    border: 1px solid var(--border);
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: transform 0.15s, box-shadow 0.15s;
    position: relative;
    overflow: hidden;
  }
  .quick-btn::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(200,180,255,0.2), transparent);
  }
  .quick-btn:active { transform: scale(0.93); box-shadow: none; }
  .quick-btn .qicon {
    width: 40px; height: 40px;
    border-radius: 13px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
  }
  .quick-btn .qlabel { font-size: 10px; font-weight: 700; color: var(--text-muted); letter-spacing: 0.3px; }
  .qicon.income-c { background: rgba(0,214,143,0.15); }
  .qicon.expense-c { background: rgba(255,92,108,0.15); }
  .qicon.loan-out-c { background: rgba(255,179,71,0.15); }
  .qicon.loan-in-c { background: rgba(77,166,255,0.15); }
  .pill-v-icon.income-c { background: rgba(0,214,143,0.15); }
  .pill-v-icon.expense-c { background: rgba(255,92,108,0.15); }
  .pill-v-icon.loan-out-c { background: rgba(255,179,71,0.15); }
  .pill-v-icon.loan-in-c { background: rgba(77,166,255,0.15); }

  /* Transaction list */
  .tx-item {
    display: flex;
    align-items: center;
    gap: 13px;
    padding: 13px 0;
    border-bottom: 1px solid var(--border);
    cursor: pointer;
    transition: opacity 0.15s;
  }
  .tx-item:active { opacity: 0.7; }
  .tx-item:last-child { border-bottom: none; }
  .tx-icon {
    width: 44px; height: 44px;
    border-radius: 14px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
    border: 1px solid var(--border);
  }
  .tx-info { flex: 1; min-width: 0; }
  .tx-title { font-size: 14px; font-weight: 600; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; color: var(--text); }
  .tx-sub { font-size: 11px; color: var(--text-muted); margin-top: 3px; }
  .tx-amount { font-size: 15px; font-weight: 700; flex-shrink: 0; }
  .tx-amount.positive { color: var(--accent-green); }
  .tx-amount.negative { color: var(--accent-red); }
  .tx-amount.loan-color { color: var(--accent-orange); }
  .tx-amount.repay-color { color: var(--accent-blue); }

  /* ===== DONUT CHART ===== */
  .donut-wrap {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 24px;
    padding: 8px 0;
  }
  .donut-svg { filter: drop-shadow(0 4px 20px rgba(0,0,0,0.4)); }
  .legend { display: flex; flex-direction: column; gap: 9px; }
  .legend-item { display: flex; align-items: center; gap: 9px; }
  .legend-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; box-shadow: 0 0 6px currentColor; }
  .legend-label { font-size: 11px; color: var(--text-muted); }
  .legend-val { font-size: 12px; font-weight: 700; color: var(--text); }

  /* ===== LOAN CARDS ===== */
  .loan-card {
    background: var(--card);
    border-radius: var(--radius);
    padding: 18px;
    margin-bottom: 12px;
    box-shadow: var(--shadow-sm);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent-orange);
    position: relative; overflow: hidden;
  }
  .loan-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,179,71,0.3), transparent);
  }
  .loan-card.received { border-left-color: var(--accent-blue); }
  .loan-card.received::before { background: linear-gradient(90deg, transparent, rgba(77,166,255,0.3), transparent); }
  .loan-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }
  .loan-name { font-size: 15px; font-weight: 700; color: var(--text); }
  .loan-badge {
    font-size: 10px;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 20px;
    background: rgba(255,179,71,0.15);
    color: var(--accent-orange);
    letter-spacing: 0.3px;
  }
  .loan-badge.received { background: rgba(77,166,255,0.15); color: var(--accent-blue); }
  .loan-badge.paid { background: rgba(0,214,143,0.15); color: var(--accent-green); }
  .loan-amount { font-size: 24px; font-weight: 800; color: var(--text); margin-bottom: 5px; }
  .loan-detail { font-size: 12px; color: var(--text-muted); margin-bottom: 12px; }
  .progress-bar {
    height: 6px;
    background: rgba(255,255,255,0.08);
    border-radius: 20px;
    overflow: hidden;
    margin-bottom: 7px;
  }
  .progress-fill { height: 100%; border-radius: 20px; transition: width 0.6s cubic-bezier(0.34,1.56,0.64,1); }
  .progress-fill.orange { background: linear-gradient(90deg, var(--accent-orange), #FFD580); box-shadow: 0 0 8px rgba(255,179,71,0.5); }
  .progress-fill.blue { background: linear-gradient(90deg, var(--accent-blue), #80C6FF); box-shadow: 0 0 8px rgba(77,166,255,0.5); }
  .progress-info {
    display: flex;
    justify-content: space-between;
    font-size: 11px;
    color: var(--text-muted);
  }
  .loan-actions { display: flex; gap: 8px; margin-top: 14px; }
  .btn-pay {
    flex: 1;
    padding: 10px;
    border: none;
    border-radius: 12px;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: all 0.2s;
  }
  .btn-pay:active { transform: scale(0.97); }
  .btn-primary { background: linear-gradient(135deg, var(--primary-mid), var(--primary-light)); color: #fff; box-shadow: 0 4px 12px rgba(79,58,158,0.4); }
  .btn-outline { background: rgba(255,255,255,0.05); border: 1px solid var(--border); color: var(--text-muted); }

  /* ===== MODAL ===== */
  .modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.7);
    backdrop-filter: blur(8px);
    z-index: 200;
    align-items: flex-end;
    justify-content: center;
  }
  .modal-overlay.open { display: flex; animation: fadeIn 0.2s; }
  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
  .modal {
    background: var(--card2);
    border-radius: 30px 30px 0 0;
    padding: 20px 20px 40px;
    width: 100%;
    max-width: 430px;
    animation: slideUp 0.3s cubic-bezier(0.34,1.56,0.64,1);
    border-top: 1px solid var(--border);
    box-shadow: 0 -8px 40px rgba(0,0,0,0.5);
  }
  @keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }
  .modal-handle {
    width: 40px; height: 4px;
    background: rgba(255,255,255,0.15);
    border-radius: 20px;
    margin: 0 auto 18px;
  }
  .modal-title { font-size: 18px; font-weight: 800; margin-bottom: 18px; text-align: center; color: var(--text); }
  .modal-type-tabs {
    display: flex;
    gap: 7px;
    margin-bottom: 18px;
  }
  .mtype-btn {
    flex: 1; padding: 9px 4px; border: 1px solid var(--border);
    border-radius: 12px; font-size: 11px; font-weight: 700;
    background: rgba(255,255,255,0.04); cursor: pointer; color: var(--text-muted);
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: all 0.2s;
  }
  .mtype-btn.active-income { border-color: var(--accent-green); background: rgba(0,214,143,0.12); color: var(--accent-green); }
  .mtype-btn.active-expense { border-color: var(--accent-red); background: rgba(255,92,108,0.12); color: var(--accent-red); }
  .mtype-btn.active-loan-out { border-color: var(--accent-orange); background: rgba(255,179,71,0.12); color: var(--accent-orange); }
  .mtype-btn.active-loan-in { border-color: var(--accent-blue); background: rgba(77,166,255,0.12); color: var(--accent-blue); }
  .mtype-btn.active-repay { border-color: var(--accent); background: rgba(200,180,255,0.12); color: var(--accent); }

  .form-group { margin-bottom: 14px; }
  .form-label { font-size: 11px; font-weight: 700; color: var(--text-muted); margin-bottom: 7px; display: block; letter-spacing: 0.5px; text-transform: uppercase; }
  .form-input {
    width: 100%; padding: 12px 15px;
    border: 1px solid var(--border);
    border-radius: 14px;
    font-size: 15px;
    font-family: 'Noto Sans Bengali', sans-serif;
    color: var(--text);
    background: rgba(255,255,255,0.05);
    outline: none;
    transition: border-color 0.2s, box-shadow 0.2s;
  }
  .form-input:focus { border-color: var(--accent); box-shadow: 0 0 0 3px rgba(200,180,255,0.1); }
  .amount-input {
    font-size: 28px; font-weight: 800;
    text-align: center;
    letter-spacing: -1px;
    color: var(--text);
  }
  .submit-btn {
    width: 100%; padding: 15px;
    background: linear-gradient(135deg, var(--primary-mid) 0%, var(--primary-light) 100%);
    color: #fff; border: none;
    border-radius: 16px;
    font-size: 16px; font-weight: 700;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    margin-top: 8px;
    transition: transform 0.15s, box-shadow 0.15s;
    box-shadow: 0 6px 20px rgba(79,58,158,0.4);
  }
  .submit-btn:active { transform: scale(0.98); box-shadow: none; }

  /* ===== FAB ===== */
  .fab {
    position: fixed;
    bottom: 84px;
    left: 50%;
    transform: translateX(-50%);
    width: 58px; height: 58px;
    background: linear-gradient(135deg, var(--primary-mid), var(--primary-light));
    border-radius: 20px;
    display: flex; align-items: center; justify-content: center;
    font-size: 28px; color: #fff;
    box-shadow: 0 8px 28px rgba(79,58,158,0.6);
    cursor: pointer;
    z-index: 99;
    border: none;
    transition: transform 0.15s;
    font-family: 'Noto Sans Bengali', sans-serif;
  }
  .fab:active { transform: translateX(-50%) scale(0.91); }

  /* nav-icon fallback for non-wrap icons */
  .nav-icon { font-size: 21px; }

  /* ===== REPORT PAGE ===== */
  .month-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 16px;
  }
  .month-nav button {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    width: 38px; height: 38px;
    font-size: 18px;
    cursor: pointer;
    color: var(--text-muted);
  }
  .month-label { font-size: 15px; font-weight: 700; color: var(--text); }

  .report-summary {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 16px;
  }
  .rs-card {
    background: var(--card);
    border-radius: var(--radius-sm);
    padding: 16px;
    box-shadow: var(--shadow-sm);
    border: 1px solid var(--border);
  }
  .rs-label { font-size: 10px; color: var(--text-muted); margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.5px; font-weight: 700; }
  .rs-val { font-size: 20px; font-weight: 800; }
  .rs-val.inc { color: var(--accent-green); }
  .rs-val.exp { color: var(--accent-red); }
  .rs-val.lout { color: var(--accent-orange); }
  .rs-val.lin { color: var(--accent-blue); }

  /* Empty state */
  .empty-state {
    text-align: center;
    padding: 44px 20px;
    color: var(--text-muted);
  }
  .empty-state .ei { font-size: 48px; margin-bottom: 12px; filter: grayscale(0.3); }
  .empty-state p { font-size: 13px; line-height: 1.7; }

  /* Toast */
  .toast {
    position: fixed;
    top: 60px; left: 50%;
    transform: translateX(-50%) translateY(-80px);
    background: var(--card2);
    color: var(--text);
    padding: 11px 22px;
    border-radius: 22px;
    font-size: 13px;
    font-weight: 600;
    z-index: 300;
    transition: transform 0.3s cubic-bezier(0.34,1.56,0.64,1);
    white-space: nowrap;
    border: 1px solid var(--border);
    box-shadow: var(--shadow);
  }
  .toast.show { transform: translateX(-50%) translateY(0); }

  /* Delete btn */
  .delete-btn {
    background: rgba(255,92,108,0.12);
    color: var(--accent-red);
    border: 1px solid rgba(255,92,108,0.2);
    border-radius: 9px;
    padding: 6px 10px;
    font-size: 12px;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
  }
  .filter-row {
    display: flex; gap: 8px; margin-bottom: 14px; overflow-x: auto; padding-bottom: 4px;
  }
  .filter-btn {
    padding: 7px 14px;
    border-radius: 22px;
    border: 1px solid var(--border);
    background: var(--card);
    font-size: 11px; font-weight: 700;
    cursor: pointer; white-space: nowrap;
    color: var(--text-muted);
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: all 0.2s;
  }
  .filter-btn.active { background: var(--primary-light); color: var(--text); border-color: var(--primary-light); box-shadow: 0 4px 12px rgba(79,58,158,0.3); }

  select.form-input { appearance: none; -webkit-appearance: none; background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='14' fill='%239B91C5' viewBox='0 0 16 16'%3E%3Cpath d='M7.247 11.14L2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z'/%3E%3C/svg%3E"); background-repeat: no-repeat; background-position: right 14px center; padding-right: 36px; }

  /* ===== SETTINGS PAGE ===== */
  .settings-header {
    background: linear-gradient(160deg, #2A1F55 0%, #3D2A82 55%, #2A1F55 100%);
    padding: 52px 22px 22px;
    position: relative;
    overflow: hidden;
    border-bottom: 1px solid var(--border);
  }
  .settings-header::before {
    content: '';
    position: absolute;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(200,180,255,0.12) 0%, transparent 70%);
    border-radius: 50%;
    top: -60px; right: -40px;
  }
  .settings-toprow {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative; z-index: 1;
  }
  .settings-toprow .app-title {
    font-size: 20px; font-weight: 800; color: var(--text); letter-spacing: -0.5px;
  }
  .settings-user {
    display: flex; align-items: center; gap: 12px;
    background: rgba(255,255,255,0.06);
    border-radius: 16px;
    padding: 10px 16px;
    margin-top: 16px;
    position: relative; z-index: 1;
    backdrop-filter: blur(12px);
    border: 1px solid var(--border);
  }
  .settings-avatar {
    width: 42px; height: 42px;
    background: rgba(200,180,255,0.15);
    border-radius: 13px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    border: 1px solid rgba(200,180,255,0.2);
  }
  .settings-user-info { flex: 1; }
  .settings-user-name { font-size: 15px; font-weight: 700; color: var(--text); }
  .settings-user-sub { font-size: 11px; color: var(--text-muted); margin-top: 2px; }
  .settings-edit-btn {
    background: rgba(200,180,255,0.12);
    border: 1px solid rgba(200,180,255,0.2);
    border-radius: 11px;
    padding: 7px 13px;
    color: var(--accent);
    font-size: 11px; font-weight: 700;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
  }

  .settings-section-label {
    font-size: 10px; font-weight: 800;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: 20px 0 9px;
  }
  .settings-list {
    background: var(--card);
    border-radius: var(--radius);
    box-shadow: var(--shadow-sm);
    overflow: hidden;
    margin-bottom: 4px;
    border: 1px solid var(--border);
  }
  .settings-item {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 16px;
    border-bottom: 1px solid var(--border);
    cursor: pointer;
    transition: background 0.15s;
    text-decoration: none;
    color: inherit;
  }
  .settings-item:last-child { border-bottom: none; }
  .settings-item:active { background: rgba(255,255,255,0.04); }
  .settings-item-icon {
    width: 40px; height: 40px;
    border-radius: 13px;
    display: flex; align-items: center; justify-content: center;
    font-size: 19px;
    flex-shrink: 0;
  }
  .settings-item-text { flex: 1; }
  .settings-item-title { font-size: 14px; font-weight: 600; color: var(--text); }
  .settings-item-sub { font-size: 11px; color: var(--text-muted); margin-top: 2px; }
  .settings-arrow { font-size: 16px; color: var(--text-muted); opacity: 0.5; }
  .settings-toggle {
    width: 46px; height: 25px;
    background: rgba(255,255,255,0.1);
    border-radius: 20px;
    position: relative;
    cursor: pointer;
    transition: background 0.25s;
    flex-shrink: 0;
    border: none;
  }
  .settings-toggle::after {
    content: '';
    position: absolute;
    width: 19px; height: 19px;
    background: #fff;
    border-radius: 50%;
    top: 3px; left: 3px;
    transition: left 0.25s;
    box-shadow: 0 1px 6px rgba(0,0,0,0.3);
  }
  .settings-toggle.on { background: var(--primary-light); box-shadow: 0 0 10px rgba(79,58,158,0.4); }
  .settings-toggle.on::after { left: 24px; }

  .settings-badge {
    font-size: 10px; font-weight: 700;
    padding: 3px 9px;
    border-radius: 20px;
    background: rgba(200,180,255,0.12);
    color: var(--accent);
    border: 1px solid rgba(200,180,255,0.2);
  }
  .settings-version {
    text-align: center;
    font-size: 11px;
    color: var(--text-muted);
    padding: 24px 0 8px;
    opacity: 0.6;
  }

  /* dark mode — already dark by default, keep for toggle logic */
  body.dark-mode {
    --bg: #131030;
    --bg2: #181440;
    --card: #201C48;
    --card2: #28245A;
    --text: #EDE8FF;
    --text-muted: #8880AA;
    --border: rgba(184,160,248,0.13);
  }
  body.dark-mode .bottom-nav { background: rgba(18,14,42,0.95); }
  body.dark-mode .confirm-box { background: #120F26; }
  body.dark-mode .modal { background: #120F26; }
  body.dark-mode .form-input { background: rgba(0,0,0,0.3); }
  body.dark-mode .settings-item:active { background: rgba(255,255,255,0.02); }
  body.dark-mode .confirm-cancel { background: rgba(255,255,255,0.06); color: var(--text); }

  /* name modal */
  .name-modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.7);
    backdrop-filter: blur(8px);
    z-index: 500;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }
  .name-modal-overlay.open { display: flex; animation: fadeIn 0.2s; }
  .name-modal {
    background: var(--card2);
    border-radius: 26px;
    padding: 26px 22px;
    width: 100%;
    max-width: 340px;
    animation: popIn 0.25s cubic-bezier(0.34,1.56,0.64,1);
    box-shadow: 0 20px 60px rgba(0,0,0,0.5);
    border: 1px solid var(--border);
  }
  .name-modal-title { font-size: 17px; font-weight: 800; margin-bottom: 18px; text-align: center; color: var(--text); }

  /* ===== CONFIRM MODAL ===== */
  .confirm-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.72);
    backdrop-filter: blur(8px);
    z-index: 400;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }
  .confirm-overlay.open { display: flex; animation: fadeIn 0.2s; }
  .confirm-box {
    background: var(--card2);
    border-radius: 26px;
    padding: 30px 24px 24px;
    width: 100%;
    max-width: 340px;
    text-align: center;
    animation: popIn 0.25s cubic-bezier(0.34,1.56,0.64,1);
    box-shadow: 0 24px 60px rgba(0,0,0,0.5);
    border: 1px solid var(--border);
  }
  @keyframes popIn { from { transform: scale(0.8); opacity:0; } to { transform: scale(1); opacity:1; } }
  .confirm-icon { font-size: 48px; margin-bottom: 14px; }
  .confirm-title { font-size: 18px; font-weight: 800; color: var(--text); margin-bottom: 8px; }
  .confirm-msg { font-size: 13px; color: var(--text-muted); margin-bottom: 6px; line-height: 1.6; }
  .confirm-item-name {
    font-size: 13px; font-weight: 700; color: var(--text);
    background: rgba(255,255,255,0.05); border-radius: 12px;
    padding: 9px 16px; margin: 12px 0 22px;
    border: 1px solid var(--border);
  }
  .confirm-btns { display: flex; gap: 10px; }
  .confirm-btn {
    flex: 1; padding: 14px;
    border: none; border-radius: 16px;
    font-size: 14px; font-weight: 700;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: transform 0.15s;
  }
  .confirm-btn:active { transform: scale(0.96); }
  .confirm-cancel { background: rgba(255,255,255,0.07); color: var(--text-muted); border: 1px solid var(--border); }
  .confirm-delete { background: linear-gradient(135deg, #FF5C6C, #E53E50); color: #fff; box-shadow: 0 6px 18px rgba(255,92,108,0.35); }

  /* ===== TX MONTH NAVIGATOR ===== */
  .tx-month-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: var(--card);
    border-radius: 20px;
    padding: 14px 16px;
    margin-bottom: 12px;
    border: 1px solid var(--border);
    box-shadow: var(--shadow-sm);
    position: relative;
    overflow: hidden;
  }
  .tx-month-nav::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(200,180,255,0.25), transparent);
  }
  .tx-month-btn {
    width: 36px; height: 36px;
    background: rgba(200,180,255,0.1);
    border: 1px solid var(--border);
    border-radius: 11px;
    font-size: 20px;
    color: var(--accent);
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: background 0.15s;
    flex-shrink: 0;
  }
  .tx-month-btn:active { background: rgba(200,180,255,0.2); }
  .tx-month-center {
    text-align: center;
    flex: 1;
    cursor: pointer;
    padding: 0 8px;
  }
  .tx-month-label {
    font-size: 16px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -0.5px;
  }
  .tx-month-sub {
    font-size: 10px;
    color: var(--text-muted);
    margin-top: 2px;
    letter-spacing: 0.3px;
  }

  /* Month Summary Bar */
  .tx-month-summary {
    display: flex;
    align-items: center;
    background: var(--card);
    border-radius: 16px;
    padding: 13px 18px;
    margin-bottom: 12px;
    border: 1px solid var(--border);
    box-shadow: var(--shadow-sm);
  }
  .tx-ms-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
  }
  .tx-ms-label {
    font-size: 10px;
    font-weight: 700;
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .tx-ms-val {
    font-size: 15px;
    font-weight: 800;
    color: var(--text);
  }
  .tx-ms-val.tx-ms-inc { color: var(--accent-green); }
  .tx-ms-val.tx-ms-exp { color: var(--accent-red); }
  .tx-ms-sep {
    width: 1px;
    height: 32px;
    background: var(--border);
    margin: 0 4px;
  }

  /* ===== LOGIN SCREEN ===== */
  #loginScreen {
    position: fixed;
    inset: 0;
    background: var(--bg);
    z-index: 9999;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 32px 28px;
    max-width: 430px;
    margin: 0 auto;
  }
  #loginScreen::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(200,180,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(200,180,255,0.03) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
    z-index: 0;
  }
  .login-glow {
    position: absolute;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(200,180,255,0.12) 0%, transparent 70%);
    border-radius: 50%;
    top: -80px; right: -60px;
    pointer-events: none;
  }
  .login-inner {
    width: 100%;
    position: relative;
    z-index: 1;
  }
  .login-logo {
    text-align: center;
    margin-bottom: 36px;
  }
  .login-logo-icon {
    width: 76px; height: 76px;
    background: linear-gradient(135deg, var(--primary-mid), var(--primary-light));
    border-radius: 26px;
    display: flex; align-items: center; justify-content: center;
    font-size: 36px;
    margin: 0 auto 14px;
    box-shadow: 0 12px 36px rgba(79,58,158,0.5);
    border: 1px solid rgba(200,180,255,0.2);
  }
  .login-app-name {
    font-size: 28px;
    font-weight: 800;
    color: var(--text);
    letter-spacing: -1px;
  }
  .login-tagline {
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 4px;
  }
  .login-card {
    background: var(--card);
    border-radius: 28px;
    padding: 28px 24px;
    border: 1px solid var(--border);
    box-shadow: var(--shadow);
    position: relative;
    overflow: hidden;
  }
  .login-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(200,180,255,0.3), transparent);
  }
  .login-step-title {
    font-size: 18px;
    font-weight: 800;
    color: var(--text);
    margin-bottom: 6px;
  }
  .login-step-sub {
    font-size: 13px;
    color: var(--text-muted);
    margin-bottom: 22px;
    line-height: 1.6;
  }
  .phone-input-wrap {
    display: flex;
    align-items: center;
    background: rgba(255,255,255,0.05);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.2s, box-shadow 0.2s;
    margin-bottom: 16px;
  }
  .phone-input-wrap:focus-within {
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(200,180,255,0.1);
  }
  .phone-prefix {
    padding: 14px 14px 14px 16px;
    font-size: 15px;
    font-weight: 700;
    color: var(--text-muted);
    border-right: 1px solid var(--border);
    white-space: nowrap;
    background: rgba(255,255,255,0.03);
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .phone-prefix span { color: var(--text); }
  #phoneInput {
    flex: 1;
    padding: 14px 16px;
    background: none;
    border: none;
    outline: none;
    font-size: 18px;
    font-weight: 700;
    color: var(--text);
    font-family: 'Sora', sans-serif;
    letter-spacing: 1px;
  }
  #phoneInput::placeholder { color: var(--text-muted); font-size: 15px; font-weight: 400; letter-spacing: 0; }
  .otp-row {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
    justify-content: center;
  }
  .otp-digit {
    width: 52px; height: 58px;
    background: rgba(255,255,255,0.05);
    border: 1.5px solid var(--border);
    border-radius: 14px;
    text-align: center;
    font-size: 22px;
    font-weight: 800;
    color: var(--text);
    font-family: 'Sora', sans-serif;
    outline: none;
    transition: all 0.2s;
    caret-color: var(--accent);
  }
  .otp-digit:focus {
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(200,180,255,0.12);
    background: rgba(200,180,255,0.06);
  }
  .login-btn {
    width: 100%;
    padding: 15px;
    background: linear-gradient(135deg, var(--primary-mid) 0%, var(--primary-light) 100%);
    color: #fff;
    border: none;
    border-radius: 16px;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    box-shadow: 0 6px 20px rgba(79,58,158,0.4);
    transition: transform 0.15s, box-shadow 0.15s;
    position: relative;
    overflow: hidden;
  }
  .login-btn:active { transform: scale(0.97); box-shadow: none; }
  .login-btn:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }
  .login-btn-shine {
    position: absolute;
    top: 0; left: -100%;
    width: 60%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
    transform: skewX(-20deg);
    animation: btnShine 2.5s infinite;
  }
  @keyframes btnShine {
    0% { left: -100%; }
    50% { left: 150%; }
    100% { left: 150%; }
  }
  .otp-timer {
    text-align: center;
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 14px;
  }
  .otp-timer span { color: var(--accent); font-weight: 700; cursor: pointer; }
  .login-back-btn {
    display: flex;
    align-items: center;
    gap: 6px;
    background: none;
    border: none;
    color: var(--text-muted);
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    margin-bottom: 18px;
    font-family: 'Noto Sans Bengali', sans-serif;
    padding: 0;
  }
  .login-back-btn:hover { color: var(--text); }
  .otp-note {
    background: rgba(200,180,255,0.07);
    border: 1px solid rgba(200,180,255,0.12);
    border-radius: 12px;
    padding: 12px 14px;
    font-size: 12px;
    color: var(--text-muted);
    margin-bottom: 20px;
    line-height: 1.6;
  }
  .otp-note strong { color: var(--accent); }
  .login-phone-display {
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 2px;
  }
  .login-divider {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 20px 0;
  }
  .login-divider-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }
  .login-divider-text {
    font-size: 11px;
    color: var(--text-muted);
    white-space: nowrap;
  }
  .skip-btn {
    width: 100%;
    padding: 13px;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    border-radius: 14px;
    font-size: 14px;
    font-weight: 600;
    color: var(--text-muted);
    cursor: pointer;
    font-family: 'Noto Sans Bengali', sans-serif;
    transition: all 0.2s;
  }
  .skip-btn:hover { background: rgba(255,255,255,0.07); color: var(--text); }
  #loginStep2 { display: none; }
  .step-dots {
    display: flex;
    justify-content: center;
    gap: 6px;
    margin-top: 24px;
  }
  .step-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--border);
    transition: all 0.3s;
  }
  .step-dot.active { background: var(--accent); width: 20px; border-radius: 4px; }
  .otp-success-icon {
    text-align: center;
    font-size: 48px;
    margin-bottom: 12px;
    animation: popIn 0.4s cubic-bezier(0.34,1.56,0.64,1);
  }
  @keyframes popIn { from { transform: scale(0.5); opacity: 0; } to { transform: scale(1); opacity: 1; } }
  #loginScreen.hidden { display: none; }
</style>
</head>
<body>

<!-- ===== LOGIN SCREEN ===== -->
<div id="loginScreen">
  <div class="login-glow"></div>
  <div class="login-inner">
    <div class="login-logo">
      <div class="login-logo-icon">💰</div>
      <div class="login-app-name">হিসাব</div>
      <div class="login-tagline">আপনার আর্থিক সাথী</div>
    </div>

    <div class="login-card">
      <!-- STEP 1: Phone Number -->
      <div id="loginStep1">
        <div class="login-step-title">স্বাগতম! 👋</div>
        <div class="login-step-sub">আপনার মোবাইল নম্বর দিয়ে লগিন করুন</div>
        <div class="phone-input-wrap">
          <div class="phone-prefix">🇧🇩 <span>+880</span></div>
          <input type="tel" id="phoneInput" placeholder="01XXXXXXXXX" maxlength="11" inputmode="numeric">
        </div>
        <button class="login-btn" id="sendOtpBtn" onclick="sendOTP()">
          <div class="login-btn-shine"></div>
          📲 OTP পাঠান
        </button>
        <div class="login-divider">
          <div class="login-divider-line"></div>
          <div class="login-divider-text">অথবা</div>
          <div class="login-divider-line"></div>
        </div>
        <button class="skip-btn" onclick="skipLogin()">অ্যাকাউন্ট ছাড়া ব্যবহার করুন →</button>
      </div>

      <!-- STEP 2: OTP -->
      <div id="loginStep2">
        <button class="login-back-btn" onclick="backToPhone()">← ফিরে যান</button>
        <div class="otp-success-icon" id="otpSentIcon" style="display:none">✅</div>
        <div class="login-step-title">OTP যাচাই করুন</div>
        <div class="login-step-sub">আপনার নম্বরে পাঠানো কোডটি দিন</div>
        <div class="otp-note">
          <strong id="otpPhoneDisplay"></strong> নম্বরে ৬ সংখ্যার OTP পাঠানো হয়েছে।
          <br>ডেমো OTP: <strong>123456</strong>
        </div>
        <div class="otp-row">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp0" oninput="otpInput(0)" onkeydown="otpKeydown(0,event)">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp1" oninput="otpInput(1)" onkeydown="otpKeydown(1,event)">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp2" oninput="otpInput(2)" onkeydown="otpKeydown(2,event)">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp3" oninput="otpInput(3)" onkeydown="otpKeydown(3,event)">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp4" oninput="otpInput(4)" onkeydown="otpKeydown(4,event)">
          <input class="otp-digit" type="tel" maxlength="1" inputmode="numeric" id="otp5" oninput="otpInput(5)" onkeydown="otpKeydown(5,event)">
        </div>
        <button class="login-btn" id="verifyOtpBtn" onclick="verifyOTP()">
          <div class="login-btn-shine"></div>
          ✅ যাচাই করুন ও প্রবেশ করুন
        </button>
        <div class="otp-timer" id="otpTimer">
          <span id="timerText">৩০ সেকেন্ড পর পুনরায় পাঠান</span>
        </div>
      </div>
    </div>

    <div class="step-dots">
      <div class="step-dot active" id="dot1"></div>
      <div class="step-dot" id="dot2"></div>
    </div>
  </div>
</div>

<!-- TOP HEADER -->
<!-- HOME PAGE -->
<div class="page active" id="page-home">
  <div class="topbar" id="topbar">
    <div class="topbar-row">
      <div>
        <div class="greeting">আস্সালামু আলাইকুম 👋</div>
        <div class="user-name">আমার হিসাব</div>
      </div>
      <div class="avatar">💰</div>
    </div>

    <!-- Balance centered on top -->
    <div class="topbar-balance-center">
      <div class="balance-label">মোট ব্যালেন্স</div>
      <div class="balance-amount" id="totalBalance">৳০</div>
      <div class="balance-change">এই মাসে <span id="monthChange">+৳০</span></div>
    </div>

    <!-- 2-column pills below balance -->
    <div class="topbar-pills-grid">
      <div class="pill-v">
        <div class="pill-v-icon income-c">📈</div>
        <div>
          <div class="pill-v-label">আয়</div>
          <div class="pill-v-value income" id="totalIncome">৳০</div>
        </div>
      </div>
      <div class="pill-v">
        <div class="pill-v-icon expense-c">📉</div>
        <div>
          <div class="pill-v-label">ব্যয়</div>
          <div class="pill-v-value expense" id="totalExpense">৳০</div>
        </div>
      </div>
      <div class="pill-v">
        <div class="pill-v-icon loan-out-c">🤝</div>
        <div>
          <div class="pill-v-label">ঋণ দেওয়া</div>
          <div class="pill-v-value loan-out" id="totalLoanOut">৳০</div>
        </div>
      </div>
      <div class="pill-v">
        <div class="pill-v-icon loan-in-c">💳</div>
        <div>
          <div class="pill-v-label">ঋণ নেওয়া</div>
          <div class="pill-v-value loan-in" id="totalLoanIn">৳০</div>
        </div>
      </div>
    </div>
  </div>

  <div style="padding: 18px; padding-bottom: 110px;">
    <!-- Recent Transactions -->
    <div class="section-head">
      <span class="section-title">সাম্প্রতিক লেনদেন</span>
      <span class="view-all" onclick="switchTab('transactions');setNavActive(document.getElementById('nav-tx'))">সব দেখুন ›</span>
    </div>
    <div class="card" id="recentTxList">
      <div class="empty-state">
        <div class="ei">📭</div>
        <p>এখনো কোনো লেনদেন নেই<br>নিচের ＋ বোতাম থেকে যোগ করুন</p>
      </div>
    </div>
  </div>
</div>

<!-- TRANSACTIONS PAGE -->
<div class="page" id="page-transactions">
  <div class="page-content">

    <!-- Month/Year Navigator -->
    <div class="tx-month-nav">
      <button class="tx-month-btn" onclick="changeTxMonth(-1)">&#8249;</button>
      <div class="tx-month-center" onclick="resetTxMonth()">
        <div class="tx-month-label" id="txMonthLabel">সব মাস</div>
        <div class="tx-month-sub" id="txMonthSub">ট্যাপ করুন রিসেট করতে</div>
      </div>
      <button class="tx-month-btn" onclick="changeTxMonth(1)">&#8250;</button>
    </div>

    <!-- Month Summary Bar -->
    <div class="tx-month-summary" id="txMonthSummary">
      <div class="tx-ms-item">
        <span class="tx-ms-label">আয়</span>
        <span class="tx-ms-val tx-ms-inc" id="txSumIncome">৳০</span>
      </div>
      <div class="tx-ms-sep"></div>
      <div class="tx-ms-item">
        <span class="tx-ms-label">ব্যয়</span>
        <span class="tx-ms-val tx-ms-exp" id="txSumExpense">৳০</span>
      </div>
      <div class="tx-ms-sep"></div>
      <div class="tx-ms-item">
        <span class="tx-ms-label">নেট</span>
        <span class="tx-ms-val" id="txSumNet">৳০</span>
      </div>
    </div>

    <!-- Type filter -->
    <div class="filter-row">
      <button class="filter-btn active" onclick="filterTx('all',this)">সব</button>
      <button class="filter-btn" onclick="filterTx('income',this)">আয়</button>
      <button class="filter-btn" onclick="filterTx('expense',this)">ব্যয়</button>
    </div>

    <div class="card" id="allTxList">
      <div class="empty-state">
        <div class="ei">&#128205;</div>
        <p>কোনো লেনদেন নেই</p>
      </div>
    </div>
  </div>
</div>

<!-- LOANS PAGE -->
<div class="page" id="page-loans">
  <div class="page-content">

    <!-- Month/Year Navigator -->
    <div class="tx-month-nav">
      <button class="tx-month-btn" onclick="changeLoanMonth(-1)">&#8249;</button>
      <div class="tx-month-center" onclick="resetLoanMonth()">
        <div class="tx-month-label" id="loanMonthLabel">সব মাস</div>
        <div class="tx-month-sub" id="loanMonthSub">ট্যাপ করুন রিসেট করতে</div>
      </div>
      <button class="tx-month-btn" onclick="changeLoanMonth(1)">&#8250;</button>
    </div>

    <!-- Loan Summary Bar -->
    <div class="tx-month-summary" id="loanMonthSummary">
      <div class="tx-ms-item">
        <span class="tx-ms-label">দেওয়া</span>
        <span class="tx-ms-val" style="color:var(--accent-orange)" id="loanSumOut">৳০</span>
      </div>
      <div class="tx-ms-sep"></div>
      <div class="tx-ms-item">
        <span class="tx-ms-label">নেওয়া</span>
        <span class="tx-ms-val" style="color:var(--accent-blue)" id="loanSumIn">৳০</span>
      </div>
      <div class="tx-ms-sep"></div>
      <div class="tx-ms-item">
        <span class="tx-ms-label">বকেয়া</span>
        <span class="tx-ms-val" id="loanSumPending">৳০</span>
      </div>
    </div>

    <!-- Type filter -->
    <div class="filter-row">
      <button class="filter-btn active" onclick="filterLoans('all',this)">সব</button>
      <button class="filter-btn" onclick="filterLoans('given',this)">ঋণ দেওয়া</button>
      <button class="filter-btn" onclick="filterLoans('taken',this)">ঋণ নেওয়া</button>
      <button class="filter-btn" onclick="filterLoans('repay',this)">ঋণ পরিশোধ</button>
      <button class="filter-btn" onclick="filterLoans('pending',this)">বকেয়া</button>
      <button class="filter-btn" onclick="filterLoans('paid',this)">পরিশোধিত</button>
    </div>

    <div id="loansList">
      <div class="empty-state">
        <div class="ei">🤝</div>
        <p>কোনো ঋণের তথ্য নেই<br>নিচের ＋ বোতাম থেকে যোগ করুন</p>
      </div>
    </div>
  </div>
</div>

<!-- REPORT PAGE -->
<div class="page" id="page-report">
  <div class="page-content">
    <div class="month-nav">
      <button onclick="changeMonth(-1)">‹</button>
      <span class="month-label" id="reportMonth">মে ২০২৬</span>
      <button onclick="changeMonth(1)">›</button>
    </div>
    <div class="report-summary">
      <div class="rs-card">
        <div class="rs-label">আয়</div>
        <div class="rs-val inc" id="rIncome">৳০</div>
      </div>
      <div class="rs-card">
        <div class="rs-label">ব্যয়</div>
        <div class="rs-val exp" id="rExpense">৳০</div>
      </div>
      <div class="rs-card">
        <div class="rs-label">ঋণ দেওয়া</div>
        <div class="rs-val lout" id="rLoanOut">৳০</div>
      </div>
      <div class="rs-card">
        <div class="rs-label">ঋণ পরিশোধ</div>
        <div class="rs-val lin" id="rRepay">৳০</div>
      </div>
    </div>
    <div class="section-head" style="margin-top:4px;">
      <span class="section-title">ব্যয়ের বিশ্লেষণ</span>
    </div>
    <div class="card">
      <div class="donut-wrap">
        <svg class="donut-svg" width="150" height="150" viewBox="0 0 150 150" id="donutChart">
          <circle cx="75" cy="75" r="55" fill="#F9FAFB"/>
          <text x="75" y="71" text-anchor="middle" font-size="11" fill="#6B7280" font-family="Noto Sans Bengali">মোট ব্যয়</text>
          <text x="75" y="88" text-anchor="middle" font-size="13" font-weight="800" fill="#1E1B4B" font-family="Noto Sans Bengali" id="donutCenter">৳০</text>
        </svg>
        <div class="legend" id="chartLegend">
          <div class="legend-item"><div class="legend-dot" style="background:#6C3FC5"></div><div><div class="legend-label">কোনো ডেটা নেই</div></div></div>
        </div>
      </div>
    </div>
    <div class="section-head">
      <span class="section-title">এই মাসের লেনদেন</span>
    </div>
    <div class="card" id="reportTxList">
      <div class="empty-state"><div class="ei">📊</div><p>এই মাসে কোনো লেনদেন নেই</p></div>
    </div>
  </div>
</div>

<!-- SETTINGS PAGE -->
<div class="page" id="page-settings">
  <div class="settings-header">
    <div class="settings-toprow">
      <div class="app-title">⚙️ সেটিংস</div>
      <div style="color:rgba(255,255,255,0.7);font-size:13px;font-weight:600;">হিসাব v১.০</div>
    </div>
    <div class="settings-user">
      <div class="settings-avatar">👤</div>
      <div class="settings-user-info">
        <div class="settings-user-name" id="settingsUserName">আমার হিসাব</div>
        <div class="settings-user-sub" id="settingsUserSub">ব্যক্তিগত অ্যাকাউন্ট</div>
      </div>
      <button class="settings-edit-btn" onclick="openNameModal()">✏️ এডিট</button>
    </div>
  </div>

  <div style="padding: 0 18px 95px;">

    <div class="settings-section-label">সাধারণ</div>
    <div class="settings-list">
      <div class="settings-item" onclick="toggleDark()">
        <div class="settings-item-icon" style="background:rgba(200,180,255,0.12);border:1px solid rgba(200,180,255,0.15);">🌙</div>
        <div class="settings-item-text">
          <div class="settings-item-title">ডার্ক মোড</div>
          <div class="settings-item-sub">রাতের জন্য গাঢ় থিম</div>
        </div>
        <button class="settings-toggle" id="darkToggle"></button>
      </div>
    </div>

    <div class="settings-section-label">ডেটা ও ব্যাকআপ</div>
    <div class="settings-list">
      <div class="settings-item" onclick="exportMonthlyPDF()">
        <div class="settings-item-icon" style="background:rgba(255,92,108,0.12);border:1px solid rgba(255,92,108,0.15);">📄</div>
        <div class="settings-item-text">
          <div class="settings-item-title">মাসিক PDF রিপোর্ট</div>
          <div class="settings-item-sub">এই মাসের হিসাব PDF-এ নামান</div>
        </div>
        <span class="settings-arrow">›</span>
      </div>
      <div class="settings-item" onclick="exportJSON()">
        <div class="settings-item-icon" style="background:rgba(0,214,143,0.12);border:1px solid rgba(0,214,143,0.15);">💾</div>
        <div class="settings-item-text">
          <div class="settings-item-title">ব্যাকআপ তৈরি করুন</div>
          <div class="settings-item-sub">JSON ফাইলে ডেটা সেভ করুন</div>
        </div>
        <span class="settings-arrow">›</span>
      </div>
      <div class="settings-item" onclick="document.getElementById('importFile').click()">
        <div class="settings-item-icon" style="background:rgba(77,166,255,0.12);border:1px solid rgba(77,166,255,0.15);">📂</div>
        <div class="settings-item-text">
          <div class="settings-item-title">ব্যাকআপ রিস্টোর করুন</div>
          <div class="settings-item-sub">আগের ডেটা ফিরিয়ে আনুন</div>
        </div>
        <span class="settings-arrow">›</span>
      </div>
      <input type="file" id="importFile" accept=".json" style="display:none" onchange="importJSON(event)">
      <div class="settings-item" onclick="exportCSV()">
        <div class="settings-item-icon" style="background:rgba(255,179,71,0.12);border:1px solid rgba(255,179,71,0.15);">📋</div>
        <div class="settings-item-text">
          <div class="settings-item-title">এক্সেল ডাউনলোড</div>
          <div class="settings-item-sub">CSV ফরম্যাটে রিপোর্ট নামান</div>
        </div>
        <span class="settings-arrow">›</span>
      </div>
    </div>

    <div class="settings-section-label">বিপদজনক</div>
    <div class="settings-list">
      <div class="settings-item" onclick="confirmClearAll()" style="color:var(--accent-red)">
        <div class="settings-item-icon" style="background:rgba(255,92,108,0.12);border:1px solid rgba(255,92,108,0.15);">🗑️</div>
        <div class="settings-item-text">
          <div class="settings-item-title" style="color:var(--accent-red)">সব ডেটা মুছুন</div>
          <div class="settings-item-sub">সমস্ত তথ্য স্থায়ীভাবে মুছে যাবে</div>
        </div>
        <span class="settings-arrow" style="color:#FCA5A5;">›</span>
      </div>
    </div>

    <div class="settings-section-label">অ্যাকাউন্ট</div>
    <div class="settings-list">
      <div class="settings-item" id="currentAccountInfo">
        <div class="settings-item-icon" style="background:rgba(200,180,255,0.12);border:1px solid rgba(200,180,255,0.15);">📱</div>
        <div class="settings-item-text">
          <div class="settings-item-title">বর্তমান অ্যাকাউন্ট</div>
          <div class="settings-item-sub" id="currentPhoneDisplay">—</div>
        </div>
      </div>
      <div class="settings-item" onclick="logoutUser()">
        <div class="settings-item-icon" style="background:rgba(255,179,71,0.12);border:1px solid rgba(255,179,71,0.15);">🔄</div>
        <div class="settings-item-text">
          <div class="settings-item-title">অ্যাকাউন্ট পরিবর্তন করুন</div>
          <div class="settings-item-sub">অন্য মোবাইল নম্বরে লগিন করুন</div>
        </div>
        <span class="settings-arrow">›</span>
      </div>
    </div>

    <div class="settings-version">হিসাব অ্যাপ v১.০ • প্রতিটি অ্যাকাউন্টের হিসাব আলাদাভাবে সংরক্ষিত</div>
  </div>
</div>

<!-- NAME EDIT MODAL -->
<div class="name-modal-overlay" id="nameModalOverlay" onclick="if(event.target===this)this.classList.remove('open')">
  <div class="name-modal">
    <div class="name-modal-title">👤 নাম পরিবর্তন করুন</div>
    <div class="form-group">
      <label class="form-label">আপনার নাম</label>
      <input class="form-input" type="text" id="inputUserName" placeholder="নাম লিখুন...">
    </div>
    <div class="form-group">
      <label class="form-label">অ্যাকাউন্টের ধরন</label>
      <input class="form-input" type="text" id="inputUserSub" placeholder="যেমন: ব্যক্তিগত, ব্যবসায়িক...">
    </div>
    <button class="submit-btn" onclick="saveUserName()">✅ সংরক্ষণ করুন</button>
  </div>
</div>

<!-- FAB -->
<button class="fab" onclick="openModal('expense')">＋</button>

<!-- BOTTOM NAV -->
<div class="bottom-nav">
  <button class="nav-btn active" id="nav-home" onclick="switchTab('home');setNavActive(this)">
    <div class="nav-icon-wrap">🏠</div>
    <span class="nav-label">হোম</span>
    <div class="nav-active-dot"></div>
  </button>
  <button class="nav-btn" id="nav-tx" onclick="switchTab('transactions');setNavActive(this)">
    <div class="nav-icon-wrap">📋</div>
    <span class="nav-label">লেনদেন</span>
    <div class="nav-active-dot"></div>
  </button>
  <button class="nav-btn" id="nav-loans" onclick="switchTab('loans');setNavActive(this)">
    <div class="nav-icon-wrap">🤝</div>
    <span class="nav-label">ঋণ</span>
    <div class="nav-active-dot"></div>
  </button>
  <button class="nav-btn" id="nav-report" onclick="switchTab('report');setNavActive(this)">
    <div class="nav-icon-wrap">📊</div>
    <span class="nav-label">রিপোর্ট</span>
    <div class="nav-active-dot"></div>
  </button>
  <button class="nav-btn" id="nav-settings" onclick="switchTab('settings');setNavActive(this)">
    <div class="nav-icon-wrap">⚙️</div>
    <span class="nav-label">সেটিংস</span>
    <div class="nav-active-dot"></div>
  </button>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<!-- CONFIRM DELETE MODAL -->
<div class="confirm-overlay" id="confirmOverlay">
  <div class="confirm-box">
    <div class="confirm-icon">🗑️</div>
    <div class="confirm-title">মুছে ফেলবেন?</div>
    <div class="confirm-msg">এই লেনদেনটি স্থায়ীভাবে মুছে যাবে এবং আর ফিরিয়ে আনা যাবে না।</div>
    <div class="confirm-item-name" id="confirmItemName">—</div>
    <div class="confirm-btns">
      <button class="confirm-btn confirm-cancel" onclick="closeConfirm()">❌ বাতিল</button>
      <button class="confirm-btn confirm-delete" onclick="confirmDelete()">🗑️ হ্যাঁ, মুছুন</button>
    </div>
  </div>
</div>

<!-- PHONE VERIFY MODAL — সব ডেটা মুছুন -->
<div class="name-modal-overlay" id="clearVerifyOverlay" onclick="if(event.target===this)closeClearVerify()">
  <div class="name-modal" style="max-width:360px">
    <div style="text-align:center;font-size:44px;margin-bottom:10px">🔐</div>
    <div class="name-modal-title">নিরাপত্তা যাচাই</div>
    <p style="font-size:12px;color:var(--text-muted);text-align:center;margin-bottom:18px;line-height:1.6">সব ডেটা স্থায়ীভাবে মুছে যাবে।<br>নিশ্চিত করতে আপনার <strong style="color:var(--accent)">রেজিস্টার্ড মোবাইল নম্বর</strong> দিন।</p>
    <div class="form-group">
      <label class="form-label">মোবাইল নম্বর</label>
      <div class="phone-input-wrap" style="margin-bottom:0">
        <div class="phone-prefix">🇧🇩 <span>+880</span></div>
        <input type="tel" id="clearVerifyPhone" placeholder="01XXXXXXXXX" maxlength="11" inputmode="numeric"
          style="flex:1;padding:12px 14px;background:none;border:none;outline:none;font-size:16px;font-weight:700;color:var(--text);font-family:'Sora',sans-serif">
      </div>
      <div id="clearVerifyError" style="color:var(--accent-red);font-size:12px;font-weight:600;margin-top:8px;min-height:18px"></div>
    </div>
    <div style="display:flex;gap:10px;margin-top:6px">
      <button class="confirm-btn confirm-cancel" style="flex:1;padding:13px;border-radius:14px" onclick="closeClearVerify()">বাতিল</button>
      <button class="confirm-btn confirm-delete" style="flex:1;padding:13px;border-radius:14px" onclick="executeClearAll()">🗑️ মুছুন</button>
    </div>
  </div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modalOverlay" onclick="closeModalOutside(event)">
  <div class="modal">
    <div class="modal-handle"></div>
    <div class="modal-title" id="modalTitle">নতুন লেনদেন</div>

    <div class="modal-type-tabs" id="typeTabsWrap">
      <button class="mtype-btn" id="btn-income" onclick="setModalType('income')">💚 আয়</button>
      <button class="mtype-btn" id="btn-expense" onclick="setModalType('expense')">❤️ ব্যয়</button>
      <button class="mtype-btn" id="btn-loan-out" onclick="setModalType('loan-out')">🤝 ঋণ দেওয়া</button>
      <button class="mtype-btn" id="btn-loan-in" onclick="setModalType('loan-in')">💳 ঋণ নেওয়া</button>
    </div>

    <div class="form-group">
      <label class="form-label">পরিমাণ (৳)</label>
      <input class="form-input amount-input" type="number" id="inputAmount" placeholder="০" inputmode="decimal">
    </div>
    <div class="form-group">
      <label class="form-label">বিবরণ / নাম</label>
      <input class="form-input" type="text" id="inputNote" placeholder="যেমন: বেতন, বাজার, রহিম ভাই...">
    </div>
    <!-- আয়ের ক্যাটাগরি -->
    <div class="form-group" id="categoryGroupIncome" style="display:none">
      <label class="form-label">ক্যাটাগরি</label>
      <select class="form-input" id="inputCategoryIncome">
        <option value="বেতন">💼 বেতন</option>
        <option value="ব্যবসা">🏪 ব্যবসা</option>
        <option value="ফ্রিল্যান্স">💻 ফ্রিল্যান্স</option>
        <option value="বিনিয়োগ">📈 বিনিয়োগ</option>
        <option value="উপহার">🎁 উপহার</option>
        <option value="ভাড়া">🏠 ভাড়া</option>
        <option value="কৃষি">🌾 কৃষি</option>
        <option value="অন্যান্য আয়">📦 অন্যান্য</option>
      </select>
    </div>

    <!-- ব্যয়ের ক্যাটাগরি -->
    <div class="form-group" id="categoryGroupExpense" style="display:none">
      <label class="form-label">ক্যাটাগরি</label>
      <select class="form-input" id="inputCategoryExpense">
        <option value="খাবার">🍚 খাবার</option>
        <option value="পরিবহন">🚌 পরিবহন</option>
        <option value="শিক্ষা">📚 শিক্ষা</option>
        <option value="স্বাস্থ্য">🏥 স্বাস্থ্য</option>
        <option value="বিনোদন">🎮 বিনোদন</option>
        <option value="কেনাকাটা">🛍️ কেনাকাটা</option>
        <option value="ইউটিলিটি">💡 ইউটিলিটি</option>
        <option value="বাড়িভাড়া">🏠 বাড়িভাড়া</option>
        <option value="পোশাক">👗 পোশাক</option>
        <option value="অন্যান্য">📦 অন্যান্য</option>
      </select>
    </div>

    <!-- ঋণ দেওয়ার ক্যাটাগরি -->
    <div class="form-group" id="categoryGroupLoanOut" style="display:none">
      <label class="form-label">ক্যাটাগরি</label>
      <select class="form-input" id="inputCategoryLoanOut">
        <option value="ব্যক্তিগত ঋণ">👤 ব্যক্তিগত ঋণ</option>
        <option value="ব্যবসায়িক ঋণ">🏪 ব্যবসায়িক ঋণ</option>
        <option value="জরুরি সাহায্য">🆘 জরুরি সাহায্য</option>
        <option value="পারিবারিক">👨‍👩‍👧 পারিবারিক</option>
        <option value="বন্ধুকে">🤝 বন্ধুকে</option>
        <option value="অন্যান্য">📦 অন্যান্য</option>
      </select>
    </div>

    <!-- ঋণ নেওয়ার ক্যাটাগরি -->
    <div class="form-group" id="categoryGroupLoanIn" style="display:none">
      <label class="form-label">ক্যাটাগরি</label>
      <select class="form-input" id="inputCategoryLoanIn">
        <option value="ব্যক্তিগত ঋণ">👤 ব্যক্তিগত ঋণ</option>
        <option value="ব্যবসায়িক ঋণ">🏪 ব্যবসায়িক ঋণ</option>
        <option value="জরুরি প্রয়োজন">🆘 জরুরি প্রয়োজন</option>
        <option value="পারিবারিক">👨‍👩‍👧 পারিবারিক</option>
        <option value="বন্ধু থেকে">🤝 বন্ধু থেকে</option>
        <option value="ব্যাংক/প্রতিষ্ঠান">🏦 ব্যাংক/প্রতিষ্ঠান</option>
        <option value="অন্যান্য">📦 অন্যান্য</option>
      </select>
    </div>

    <!-- hidden input to hold final category value -->
    <input type="hidden" id="inputCategory">
    <div class="form-group" id="loanPersonGroup" style="display:none">
      <label class="form-label">কার সাথে?</label>
      <input class="form-input" type="text" id="inputPerson" placeholder="ব্যক্তির নাম">
    </div>
    <div class="form-group" id="dueDateGroup" style="display:none">
      <label class="form-label">পরিশোধের তারিখ (ঐচ্ছিক)</label>
      <input class="form-input" type="date" id="inputDueDate">
    </div>
    <div class="form-group">
      <label class="form-label">তারিখ</label>
      <input class="form-input" type="date" id="inputDate">
    </div>
    <button class="submit-btn" id="submitBtn" onclick="submitTransaction()">✅ সংরক্ষণ করুন</button>
  </div>
</div>

<!-- REPAY MODAL -->
<div class="modal-overlay" id="repayModalOverlay" onclick="closeRepayOutside(event)">
  <div class="modal">
    <div class="modal-handle"></div>
    <div class="modal-title">ঋণ পরিশোধ</div>
    <div class="form-group">
      <label class="form-label">পরিশোধের পরিমাণ (৳)</label>
      <input class="form-input amount-input" type="number" id="repayAmount" placeholder="০" inputmode="decimal">
    </div>
    <div class="form-group">
      <label class="form-label">নোট</label>
      <input class="form-input" type="text" id="repayNote" placeholder="আংশিক / পূর্ণ পরিশোধ">
    </div>
    <div class="form-group">
      <label class="form-label">তারিখ</label>
      <input class="form-input" type="date" id="repayDate">
    </div>
    <button class="submit-btn" onclick="submitRepay()">✅ পরিশোধ নিশ্চিত করুন</button>
  </div>
</div>

<script>
// ===== DATA — প্রতিটি ফোন নম্বরের আলাদা হিসাব =====
function getDataKey() {
  const phone = localStorage.getItem('hisab_phone') || 'guest';
  return 'hisab_data_' + phone;
}
function getUserKey() {
  const phone = localStorage.getItem('hisab_phone') || 'guest';
  return 'hisab_user_' + phone;
}

let data = JSON.parse(localStorage.getItem(getDataKey()) || '{"transactions":[],"loans":[]}');
let currentType = 'expense';
let currentFilter = 'all';
let currentLoanFilter = 'all';
let reportYear = new Date().getFullYear();
let reportMonth = new Date().getMonth();
let currentRepayLoanId = null;
let txFilterYear = null;
let txFilterMonth = null; // null = সব মাস
let loanFilterYear = null;
let loanFilterMonth = null; // null = সব মাস

const BN_MONTHS = ['জানুয়ারি','ফেব্রুয়ারি','মার্চ','এপ্রিল','মে','জুন','জুলাই','আগস্ট','সেপ্টেম্বর','অক্টোবর','নভেম্বর','ডিসেম্বর'];

function toBn(n) {
  const bnDigits = ['০','১','২','৩','৪','৫','৬','৭','৮','৯'];
  return String(n).replace(/[0-9]/g, d => bnDigits[d]);
}

function fmtAmt(n) {
  return '৳' + toBn(Number(n).toLocaleString('en-IN', {minimumFractionDigits: 0, maximumFractionDigits: 2}));
}

function save() {
  localStorage.setItem(getDataKey(), JSON.stringify(data));
}

function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2500);
}

// ===== NAVIGATION =====
function switchTab(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-' + name).classList.add('active');
  if (name === 'report') renderReport();
  if (name === 'loans') { updateLoanMonthUI(); renderLoans(); }
  if (name === 'transactions') { updateTxMonthUI(); renderAllTx(); }
}

function setNavActive(el) {
  document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active');
}

// ===== MODAL =====
function openModal(type) {
  currentType = type;
  setModalType(type);
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('inputDate').value = today;
  document.getElementById('inputAmount').value = '';
  document.getElementById('inputNote').value = '';
  document.getElementById('inputPerson').value = '';
  document.getElementById('inputDueDate').value = '';
  document.getElementById('modalOverlay').classList.add('open');
  document.getElementById('inputAmount').focus();
}

function setModalType(type) {
  currentType = type;
  const types = ['income','expense','loan-out','loan-in'];
  types.forEach(t => {
    const btn = document.getElementById('btn-' + t);
    if (btn) btn.className = 'mtype-btn';
  });
  const activeClass = 'active-' + type;
  if (document.getElementById('btn-' + type))
    document.getElementById('btn-' + type).className = 'mtype-btn ' + activeClass;

  const showLoan = type === 'loan-out' || type === 'loan-in';
  document.getElementById('loanPersonGroup').style.display = showLoan ? 'block' : 'none';
  document.getElementById('dueDateGroup').style.display = showLoan ? 'block' : 'none';

  // Show the right category group
  document.getElementById('categoryGroupIncome').style.display  = (type === 'income')   ? 'block' : 'none';
  document.getElementById('categoryGroupExpense').style.display = (type === 'expense')   ? 'block' : 'none';
  document.getElementById('categoryGroupLoanOut').style.display = (type === 'loan-out') ? 'block' : 'none';
  document.getElementById('categoryGroupLoanIn').style.display  = (type === 'loan-in')  ? 'block' : 'none';

  const titles = {
    income: '💚 আয় যোগ করুন',
    expense: '❤️ ব্যয় যোগ করুন',
    'loan-out': '🤝 ঋণ দেওয়া',
    'loan-in': '💳 ঋণ নেওয়া'
  };
  document.getElementById('modalTitle').textContent = titles[type] || 'লেনদেন';
}

function closeModalOutside(e) {
  if (e.target === document.getElementById('modalOverlay'))
    document.getElementById('modalOverlay').classList.remove('open');
}

function closeRepayOutside(e) {
  if (e.target === document.getElementById('repayModalOverlay'))
    document.getElementById('repayModalOverlay').classList.remove('open');
}

function submitTransaction() {
  const amount = parseFloat(document.getElementById('inputAmount').value);
  const note = document.getElementById('inputNote').value.trim();
  const date = document.getElementById('inputDate').value;
  if (!amount || amount <= 0) { showToast('⚠️ সঠিক পরিমাণ দিন'); return; }
  if (!note) { showToast('⚠️ বিবরণ দিন'); return; }
  if (!date) { showToast('⚠️ তারিখ দিন'); return; }

  // Read category from the visible select based on type
  const catSelMap = {
    'income':   'inputCategoryIncome',
    'expense':  'inputCategoryExpense',
    'loan-out': 'inputCategoryLoanOut',
    'loan-in':  'inputCategoryLoanIn'
  };
  const catSel = catSelMap[currentType];
  const category = catSel ? (document.getElementById(catSel).value || '') : '';

  const tx = {
    id: Date.now(),
    type: currentType,
    amount,
    note,
    date,
    category,
    person: document.getElementById('inputPerson').value.trim(),
    dueDate: document.getElementById('inputDueDate').value,
    paidAmount: 0,
    status: 'pending'
  };

  data.transactions.unshift(tx);

  // If loan, also add to loans list
  if (currentType === 'loan-out' || currentType === 'loan-in') {
    data.loans.unshift({
      id: tx.id,
      type: currentType,
      amount,
      note,
      date,
      person: tx.person || note,
      dueDate: tx.dueDate,
      paidAmount: 0,
      status: 'pending'
    });
  }

  save();
  updateSummary();
  renderRecentTx();
  document.getElementById('modalOverlay').classList.remove('open');
  showToast('✅ সফলভাবে সংরক্ষিত!');
}

// ===== REPAY =====
function openRepayModal(loanId) {
  currentRepayLoanId = loanId;
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('repayDate').value = today;
  document.getElementById('repayAmount').value = '';
  document.getElementById('repayNote').value = 'পরিশোধ';
  document.getElementById('repayModalOverlay').classList.add('open');
}

function submitRepay() {
  const amount = parseFloat(document.getElementById('repayAmount').value);
  const note = document.getElementById('repayNote').value;
  const date = document.getElementById('repayDate').value;
  if (!amount || amount <= 0) { showToast('⚠️ পরিমাণ দিন'); return; }

  const loan = data.loans.find(l => l.id === currentRepayLoanId);
  if (!loan) return;

  loan.paidAmount = (loan.paidAmount || 0) + amount;
  if (loan.paidAmount >= loan.amount) {
    loan.paidAmount = loan.amount;
    loan.status = 'paid';
  }

  // Add repay transaction
  data.transactions.unshift({
    id: Date.now(),
    type: 'repay',
    amount,
    note: `পরিশোধ: ${loan.person || loan.note} - ${note}`,
    date,
    loanId: loan.id,
    loanType: loan.type
  });

  save();
  updateSummary();
  renderLoans();
  renderRecentTx();
  document.getElementById('repayModalOverlay').classList.remove('open');
  showToast('✅ পরিশোধ রেকর্ড হয়েছে!');
}

// ===== DELETE WITH CONFIRMATION =====
let pendingDeleteId = null;

function deleteTx(id) {
  const tx = data.transactions.find(t => t.id === id) || data.loans.find(l => l.id === id);
  if (!tx) return;
  pendingDeleteId = id;
  document.getElementById('confirmItemName').textContent = tx.note || tx.person || '—';
  document.getElementById('confirmOverlay').classList.add('open');
}

function closeConfirm() {
  pendingDeleteId = null;
  document.getElementById('confirmOverlay').classList.remove('open');
}

// ===== SUMMARY =====
function updateSummary() {
  let income = 0, expense = 0, loanOut = 0, loanIn = 0, repay = 0;
  data.transactions.forEach(t => {
    if (t.type === 'income') income += t.amount;
    else if (t.type === 'expense') expense += t.amount;
    else if (t.type === 'loan-out') loanOut += t.amount;
    else if (t.type === 'loan-in') loanIn += t.amount;
    else if (t.type === 'repay') repay += t.amount;
  });
  // balance: শুধু আয় − ব্যয় (ঋণ ব্যালেন্সে যোগ/বিয়োগ হবে না)
  const bal = income - expense;
  document.getElementById('totalBalance').textContent = fmtAmt(bal);
  document.getElementById('totalBalance').style.color = bal >= 0 ? 'var(--text)' : 'var(--accent-red)';
  document.getElementById('totalIncome').textContent = fmtAmt(income);
  document.getElementById('totalExpense').textContent = fmtAmt(expense);
  document.getElementById('totalLoanOut').textContent = fmtAmt(loanOut);
  document.getElementById('totalLoanIn').textContent = fmtAmt(loanIn);

  // Month change
  const now = new Date();
  const mIncome = data.transactions.filter(t => {
    const d = new Date(t.date);
    return t.type === 'income' && d.getMonth() === now.getMonth() && d.getFullYear() === now.getFullYear();
  }).reduce((s,t) => s + t.amount, 0);
  const mExpense = data.transactions.filter(t => {
    const d = new Date(t.date);
    return t.type === 'expense' && d.getMonth() === now.getMonth() && d.getFullYear() === now.getFullYear();
  }).reduce((s,t) => s + t.amount, 0);
  const mDiff = mIncome - mExpense;
  const changeEl = document.getElementById('monthChange');
  changeEl.textContent = (mDiff >= 0 ? '+' : '') + fmtAmt(mDiff);
  changeEl.style.color = mDiff >= 0 ? '#6EE7B7' : '#FCA5A5';
}

// ===== TX ICONS =====
function txIcon(type, category) {
  if (type === 'income') {
    const cats = { বেতন:'💼', ব্যবসা:'🏪', ফ্রিল্যান্স:'💻', বিনিয়োগ:'📈', উপহার:'🎁', ভাড়া:'🏠', কৃষি:'🌾' };
    return { bg: 'rgba(0,214,143,0.15)', icon: cats[category] || '💚' };
  }
  if (type === 'expense') {
    const cats = { খাবার:'🍚', পরিবহন:'🚌', শিক্ষা:'📚', স্বাস্থ্য:'🏥', বিনোদন:'🎮', কেনাকাটা:'🛍️', ইউটিলিটি:'💡', বাড়িভাড়া:'🏠', পোশাক:'👗', অন্যান্য:'📦' };
    return { bg: 'rgba(255,92,108,0.15)', icon: cats[category] || '❤️' };
  }
  if (type === 'loan-out') {
    const cats = { 'ব্যক্তিগত ঋণ':'👤', 'ব্যবসায়িক ঋণ':'🏪', 'জরুরি সাহায্য':'🆘', পারিবারিক:'👨‍👩‍👧', বন্ধুকে:'🤝' };
    return { bg: 'rgba(255,179,71,0.15)', icon: cats[category] || '🤝' };
  }
  if (type === 'loan-in') {
    const cats = { 'ব্যক্তিগত ঋণ':'👤', 'ব্যবসায়িক ঋণ':'🏪', 'জরুরি প্রয়োজন':'🆘', পারিবারিক:'👨‍👩‍👧', 'বন্ধু থেকে':'🤝', 'ব্যাংক/প্রতিষ্ঠান':'🏦' };
    return { bg: 'rgba(77,166,255,0.15)', icon: cats[category] || '💳' };
  }
  if (type === 'repay') return { bg: 'rgba(200,180,255,0.15)', icon: '✅' };
  return { bg: 'rgba(255,255,255,0.08)', icon: '💰' };
}

function txAmountClass(type) {
  if (type === 'income') return 'positive';
  if (type === 'expense') return 'negative';
  if (type === 'loan-out') return 'loan-color';
  if (type === 'loan-in') return 'repay-color';
  if (type === 'repay') return 'repay-color';
  return '';
}

function txAmountSign(type) {
  if (type === 'income') return '+';
  if (type === 'expense') return '-';
  if (type === 'loan-out') return '↑';
  if (type === 'loan-in') return '↓';
  if (type === 'repay') return '↩';
  return '';
}

function typeLabel(type) {
  const labels = { income:'আয়', expense:'ব্যয়', 'loan-out':'ঋণ দেওয়া', 'loan-in':'ঋণ নেওয়া', repay:'পরিশোধ' };
  return labels[type] || type;
}

function renderTxItem(tx, showDelete = true) {
  const ic = txIcon(tx.type, tx.category);
  const ac = txAmountClass(tx.type);
  const sign = txAmountSign(tx.type);
  const d = new Date(tx.date);
  const dateStr = `${toBn(d.getDate())} ${BN_MONTHS[d.getMonth()]}`;
  return `<div class="tx-item">
    <div class="tx-icon" style="background:${ic.bg}">${ic.icon}</div>
    <div class="tx-info">
      <div class="tx-title">${tx.note}</div>
      <div class="tx-sub">${typeLabel(tx.type)}${tx.category ? ' • ' + tx.category : ''} • ${dateStr}</div>
    </div>
    <div style="display:flex;flex-direction:column;align-items:flex-end;gap:4px">
      <div class="tx-amount ${ac}">${sign}${fmtAmt(tx.amount)}</div>
      ${showDelete ? `<button class="delete-btn" onclick="deleteTx(${tx.id})">মুছুন</button>` : ''}
    </div>
  </div>`;
}

function renderRecentTx() {
  const el = document.getElementById('recentTxList');
  const sorted = [...data.transactions]
    .filter(t => t.type !== 'loan-out' && t.type !== 'loan-in')
    .sort((a, b) => new Date(b.date) - new Date(a.date));
  const recent = sorted.slice(0, 8);
  if (!recent.length) {
    el.innerHTML = '<div class="empty-state"><div class="ei">📭</div><p>এখনো কোনো লেনদেন নেই<br>নিচের ＋ বোতাম থেকে যোগ করুন</p></div>';
  } else {
    el.innerHTML = recent.map(t => renderTxItem(t)).join('');
  }
}

function filterTx(type, btn) {
  currentFilter = type;
  document.querySelectorAll('#page-transactions .filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderAllTx();
}

function changeTxMonth(dir) {
  const now = new Date();
  // Initialize if null
  if (txFilterMonth === null) {
    txFilterYear = now.getFullYear();
    txFilterMonth = now.getMonth();
  }
  txFilterMonth += dir;
  if (txFilterMonth > 11) { txFilterMonth = 0; txFilterYear++; }
  if (txFilterMonth < 0)  { txFilterMonth = 11; txFilterYear--; }
  updateTxMonthUI();
  renderAllTx();
}

function resetTxMonth() {
  txFilterMonth = null;
  txFilterYear = null;
  updateTxMonthUI();
  renderAllTx();
}

function updateTxMonthUI() {
  const labelEl   = document.getElementById('txMonthLabel');
  const subEl     = document.getElementById('txMonthSub');
  const summaryEl = document.getElementById('txMonthSummary');

  if (txFilterMonth === null) {
    labelEl.textContent = 'সব মাস';
    subEl.textContent   = 'মাস বেছে নিতে তীর চাপুন';
  } else {
    labelEl.textContent = BN_MONTHS[txFilterMonth] + ' ' + toBn(txFilterYear);
    subEl.textContent   = 'ট্যাপ করুন রিসেট করতে';
  }

  // সামারি সবসময় দেখাবে — মাস সিলেক্ট না থাকলে সব সময়ের মোট
  summaryEl.style.display = 'flex';
  const txs = txFilterMonth === null
    ? data.transactions
    : data.transactions.filter(t => {
        const d = new Date(t.date);
        return d.getMonth() === txFilterMonth && d.getFullYear() === txFilterYear;
      });

  const inc = txs.filter(t => t.type === 'income').reduce((s,t) => s + t.amount, 0);
  const exp = txs.filter(t => t.type === 'expense').reduce((s,t) => s + t.amount, 0);
  const net = inc - exp;
  document.getElementById('txSumIncome').textContent  = fmtAmt(inc);
  document.getElementById('txSumExpense').textContent = fmtAmt(exp);
  const netEl = document.getElementById('txSumNet');
  netEl.textContent = (net >= 0 ? '+' : '') + fmtAmt(net);
  netEl.style.color = net >= 0 ? 'var(--accent-green)' : 'var(--accent-red)';
}

function renderAllTx() {
  const el = document.getElementById('allTxList');
  // loan-out ও loan-in লেনদেনে দেখাবে না, ঋণ পেজে থাকবে
  let txs = [...data.transactions].filter(t => t.type !== 'loan-out' && t.type !== 'loan-in');
  // Month filter
  if (txFilterMonth !== null) {
    txs = txs.filter(t => {
      const d = new Date(t.date);
      return d.getMonth() === txFilterMonth && d.getFullYear() === txFilterYear;
    });
  }
  // Type filter
  if (currentFilter !== 'all') txs = txs.filter(t => t.type === currentFilter);
  // Sort by date descending
  txs.sort((a, b) => new Date(b.date) - new Date(a.date));
  if (!txs.length) {
    el.innerHTML = '<div class="empty-state"><div class="ei">📭</div><p>এই সময়ে কোনো লেনদেন নেই</p></div>';
  } else {
    el.innerHTML = txs.map(t => renderTxItem(t, true)).join('');
  }
}

// ===== LOANS =====
function changeLoanMonth(dir) {
  const now = new Date();
  if (loanFilterMonth === null) {
    loanFilterYear = now.getFullYear();
    loanFilterMonth = now.getMonth();
  }
  loanFilterMonth += dir;
  if (loanFilterMonth > 11) { loanFilterMonth = 0; loanFilterYear++; }
  if (loanFilterMonth < 0)  { loanFilterMonth = 11; loanFilterYear--; }
  updateLoanMonthUI();
  renderLoans();
}

function resetLoanMonth() {
  loanFilterMonth = null;
  loanFilterYear = null;
  updateLoanMonthUI();
  renderLoans();
}

function updateLoanMonthUI() {
  const labelEl   = document.getElementById('loanMonthLabel');
  const subEl     = document.getElementById('loanMonthSub');
  const summaryEl = document.getElementById('loanMonthSummary');

  if (loanFilterMonth === null) {
    labelEl.textContent = 'সব মাস';
    subEl.textContent   = 'মাস বেছে নিতে তীর চাপুন';
  } else {
    labelEl.textContent = BN_MONTHS[loanFilterMonth] + ' ' + toBn(loanFilterYear);
    subEl.textContent   = 'ট্যাপ করুন রিসেট করতে';
  }

  // সামারি সবসময় দেখাবে
  summaryEl.style.display = 'flex';
  const loans = loanFilterMonth === null
    ? data.loans
    : data.loans.filter(l => {
        const d = new Date(l.date);
        return d.getMonth() === loanFilterMonth && d.getFullYear() === loanFilterYear;
      });

  const out     = loans.filter(l => l.type === 'loan-out').reduce((s,l) => s + l.amount, 0);
  const inp     = loans.filter(l => l.type === 'loan-in').reduce((s,l) => s + l.amount, 0);
  const pending = loans.filter(l => l.status !== 'paid').reduce((s,l) => s + (l.amount - (l.paidAmount||0)), 0);
  document.getElementById('loanSumOut').textContent = fmtAmt(out);
  document.getElementById('loanSumIn').textContent  = fmtAmt(inp);
  const pendEl = document.getElementById('loanSumPending');
  pendEl.textContent = fmtAmt(pending);
  pendEl.style.color = pending > 0 ? 'var(--accent-red)' : 'var(--accent-green)';
}

function filterLoans(type, btn) {
  currentLoanFilter = type;
  document.querySelectorAll('#page-loans .filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderLoans();
}

function renderLoans() {
  const el = document.getElementById('loansList');
  let loans = [...data.loans];

  // মাস ফিল্টার
  if (loanFilterMonth !== null) {
    loans = loans.filter(l => {
      const d = new Date(l.date);
      return d.getMonth() === loanFilterMonth && d.getFullYear() === loanFilterYear;
    });
  }

  if (currentLoanFilter === 'given') loans = loans.filter(l => l.type === 'loan-out');
  else if (currentLoanFilter === 'taken') loans = loans.filter(l => l.type === 'loan-in');
  else if (currentLoanFilter === 'repay') loans = loans.filter(l => l.status === 'paid' || (l.paidAmount||0) > 0);
  else if (currentLoanFilter === 'pending') loans = loans.filter(l => l.status !== 'paid');
  else if (currentLoanFilter === 'paid') loans = loans.filter(l => l.status === 'paid');

  if (!loans.length) {
    el.innerHTML = '<div class="empty-state"><div class="ei">🤝</div><p>কোনো ঋণের তথ্য নেই</p></div>';
    return;
  }
  el.innerHTML = loans.map(loan => {
    const isGiven = loan.type === 'loan-out';
    const paid = loan.paidAmount || 0;
    const pct = Math.min(100, Math.round((paid / loan.amount) * 100));
    const remaining = loan.amount - paid;
    const isPaid = loan.status === 'paid';
    const d = new Date(loan.date);
    const dateStr = `${toBn(d.getDate())} ${BN_MONTHS[d.getMonth()]}, ${toBn(d.getFullYear())}`;
    const dueTxt = loan.dueDate ? `পরিশোধের তারিখ: ${(() => { const dd = new Date(loan.dueDate); return toBn(dd.getDate()) + ' ' + BN_MONTHS[dd.getMonth()] + ' ' + toBn(dd.getFullYear()); })()}` : '';
    return `<div class="loan-card ${isGiven ? '' : 'received'}">
      <div class="loan-top">
        <div>
          <div class="loan-name">${loan.person || loan.note}</div>
          <div style="font-size:12px;color:#6B7280;margin-top:2px">${dateStr}${dueTxt ? ' • ' + dueTxt : ''}</div>
        </div>
        <span class="loan-badge ${isGiven ? '' : 'received'} ${isPaid ? 'paid' : ''}">${isPaid ? '✅ পরিশোধিত' : isGiven ? '↑ দেওয়া' : '↓ নেওয়া'}</span>
      </div>
      <div class="loan-amount">${fmtAmt(loan.amount)}</div>
      <div class="loan-detail">${loan.note}${isPaid ? '' : ` • বকেয়া: ${fmtAmt(remaining)}`}</div>
      <div class="progress-bar"><div class="progress-fill ${isGiven ? 'orange' : 'blue'}" style="width:${pct}%"></div></div>
      <div class="progress-info"><span>${toBn(pct)}% পরিশোধিত</span><span>${isPaid ? 'সম্পূর্ণ পরিশোধ' : fmtAmt(remaining) + ' বাকি'}</span></div>
      ${!isPaid ? `<div class="loan-actions">
        <button class="btn-pay btn-primary" onclick="openRepayModal(${loan.id})">💳 পরিশোধ করুন</button>
        <button class="btn-pay btn-outline" onclick="deleteTx(${loan.id})">🗑️ মুছুন</button>
      </div>` : `<div class="loan-actions"><button class="btn-pay btn-outline" onclick="deleteTx(${loan.id})">🗑️ মুছুন</button></div>`}
    </div>`;
  }).join('');
}

// ===== REPORT =====
function changeMonth(dir) {
  reportMonth += dir;
  if (reportMonth > 11) { reportMonth = 0; reportYear++; }
  if (reportMonth < 0) { reportMonth = 11; reportYear--; }
  renderReport();
}

function renderReport() {
  document.getElementById('reportMonth').textContent = BN_MONTHS[reportMonth] + ' ' + toBn(reportYear);
  const txs = data.transactions.filter(t => {
    const d = new Date(t.date);
    return d.getMonth() === reportMonth && d.getFullYear() === reportYear;
  });
  const inc = txs.filter(t => t.type === 'income').reduce((s,t) => s + t.amount, 0);
  const exp = txs.filter(t => t.type === 'expense').reduce((s,t) => s + t.amount, 0);
  const lout = txs.filter(t => t.type === 'loan-out').reduce((s,t) => s + t.amount, 0);
  const repay = txs.filter(t => t.type === 'repay').reduce((s,t) => s + t.amount, 0);

  document.getElementById('rIncome').textContent = fmtAmt(inc);
  document.getElementById('rExpense').textContent = fmtAmt(exp);
  document.getElementById('rLoanOut').textContent = fmtAmt(lout);
  document.getElementById('rRepay').textContent = fmtAmt(repay);

  // Donut
  renderDonut(txs);

  // Tx list
  const rList = document.getElementById('reportTxList');
  if (!txs.length) {
    rList.innerHTML = '<div class="empty-state"><div class="ei">📊</div><p>এই মাসে কোনো লেনদেন নেই</p></div>';
  } else {
    rList.innerHTML = txs.map(t => renderTxItem(t, false)).join('');
  }
}

function renderDonut(txs) {
  const cats = {};
  txs.filter(t => t.type === 'expense').forEach(t => {
    const c = t.category || 'অন্যান্য';
    cats[c] = (cats[c] || 0) + t.amount;
  });
  const total = Object.values(cats).reduce((s,v) => s+v, 0);

  const colors = ['#6C3FC5','#10B981','#F59E0B','#EF4444','#3B82F6','#EC4899','#14B8A6','#8B5CF6'];
  const entries = Object.entries(cats).sort((a,b) => b[1]-a[1]);

  if (!entries.length) {
    document.getElementById('donutChart').innerHTML = `
      <circle cx="75" cy="75" r="55" fill="#F9FAFB"/>
      <circle cx="75" cy="75" r="55" fill="none" stroke="#E5E7EB" stroke-width="20"/>
      <text x="75" y="71" text-anchor="middle" font-size="11" fill="#6B7280" font-family="Noto Sans Bengali">মোট ব্যয়</text>
      <text x="75" y="88" text-anchor="middle" font-size="13" font-weight="800" fill="#1E1B4B" font-family="Noto Sans Bengali">৳০</text>`;
    document.getElementById('chartLegend').innerHTML = '<div class="legend-item"><div class="legend-dot" style="background:#E5E7EB"></div><div><div class="legend-label">কোনো ব্যয় নেই</div></div></div>';
    return;
  }

  let svgPaths = '';
  let legendHTML = '';
  let startAngle = -Math.PI / 2;
  const cx = 75, cy = 75, r = 55, iR = 35;

  entries.forEach(([ cat, val ], i) => {
    const pct = val / total;
    const angle = pct * 2 * Math.PI;
    const endAngle = startAngle + angle;
    const x1 = cx + r * Math.cos(startAngle);
    const y1 = cy + r * Math.sin(startAngle);
    const x2 = cx + r * Math.cos(endAngle);
    const y2 = cy + r * Math.sin(endAngle);
    const ix1 = cx + iR * Math.cos(startAngle);
    const iy1 = cy + iR * Math.sin(startAngle);
    const ix2 = cx + iR * Math.cos(endAngle);
    const iy2 = cy + iR * Math.sin(endAngle);
    const largeArc = angle > Math.PI ? 1 : 0;
    const color = colors[i % colors.length];
    svgPaths += `<path d="M${ix1},${iy1} L${x1},${y1} A${r},${r} 0 ${largeArc},1 ${x2},${y2} L${ix2},${iy2} A${iR},${iR} 0 ${largeArc},0 ${ix1},${iy1}" fill="${color}" opacity="0.9"/>`;
    legendHTML += `<div class="legend-item"><div class="legend-dot" style="background:${color}"></div><div><div class="legend-label">${cat}</div><div class="legend-val">${fmtAmt(val)}</div></div></div>`;
    startAngle = endAngle;
  });

  document.getElementById('donutChart').innerHTML = `
    <circle cx="75" cy="75" r="55" fill="#F9FAFB"/>
    ${svgPaths}
    <circle cx="75" cy="75" r="35" fill="white"/>
    <text x="75" y="71" text-anchor="middle" font-size="10" fill="#6B7280" font-family="Noto Sans Bengali">মোট ব্যয়</text>
    <text x="75" y="87" text-anchor="middle" font-size="12" font-weight="800" fill="#1E1B4B" font-family="Noto Sans Bengali">${fmtAmt(total)}</text>`;
  document.getElementById('chartLegend').innerHTML = legendHTML;
}

// ===== SETTINGS =====
function toggleDark() {
  document.body.classList.toggle('dark-mode');
  const on = document.body.classList.contains('dark-mode');
  document.getElementById('darkToggle').classList.toggle('on', on);
  localStorage.setItem('hisab_dark', on ? '1' : '');
}

function openNameModal() {
  const ud = JSON.parse(localStorage.getItem(getUserKey()) || '{}');
  document.getElementById('inputUserName').value = ud.name || '';
  document.getElementById('inputUserSub').value = ud.sub || '';
  document.getElementById('nameModalOverlay').classList.add('open');
}

function saveUserName() {
  const name = document.getElementById('inputUserName').value.trim() || 'আমার হিসাব';
  const sub  = document.getElementById('inputUserSub').value.trim()  || 'ব্যক্তিগত অ্যাকাউন্ট';
  localStorage.setItem(getUserKey(), JSON.stringify({ name, sub }));
  document.getElementById('settingsUserName').textContent = name;
  document.getElementById('settingsUserSub').textContent  = sub;
  // topbar-এও নাম আপডেট করো
  const topName = document.querySelector('.user-name');
  if (topName) topName.textContent = name;
  document.getElementById('nameModalOverlay').classList.remove('open');
  showToast('✅ নাম সংরক্ষিত হয়েছে!');
}

function exportJSON() {
  const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'hisab_backup_' + new Date().toISOString().slice(0,10) + '.json';
  a.click();
  showToast('💾 ব্যাকআপ ডাউনলোড হচ্ছে...');
}

function importJSON(e) {
  const file = e.target.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = (ev) => {
    try {
      const imported = JSON.parse(ev.target.result);
      if (imported.transactions && imported.loans) {
        data = imported;
        save();
        updateSummary();
        renderRecentTx();
        showToast('✅ ডেটা রিস্টোর হয়েছে!');
      } else { showToast('⚠️ ফাইলটি সঠিক নয়'); }
    } catch { showToast('⚠️ ফাইল পড়তে সমস্যা হয়েছে'); }
  };
  reader.readAsText(file);
  e.target.value = '';
}

function exportCSV() {
  const rows = [['তারিখ','ধরন','বিবরণ','ক্যাটাগরি','ব্যক্তি','পরিমাণ']];
  data.transactions.forEach(t => {
    const typeMap = { income:'আয়', expense:'ব্যয়', 'loan-out':'ঋণ দেওয়া', 'loan-in':'ঋণ নেওয়া', repay:'পরিশোধ' };
    rows.push([t.date, typeMap[t.type]||t.type, t.note, t.category||'', t.person||'', t.amount]);
  });
  const csv = rows.map(r => r.map(c => `"${c}"`).join(',')).join('\n');
  const blob = new Blob(['\uFEFF'+csv], { type: 'text/csv;charset=utf-8;' });
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'hisab_report_' + new Date().toISOString().slice(0,10) + '.csv';
  a.click();
  showToast('📋 CSV ডাউনলোড হচ্ছে...');
}

function confirmClearAll() {
  // গেস্ট মোডে সরাসরি confirm modal দেখাও
  const phone = localStorage.getItem('hisab_phone');
  if (!phone) {
    pendingDeleteId = '__ALL__';
    document.getElementById('confirmItemName').textContent = 'সমস্ত লেনদেন ও ঋণ';
    document.querySelector('.confirm-title').textContent = 'সব ডেটা মুছবেন?';
    document.querySelector('.confirm-msg').textContent = 'সমস্ত তথ্য স্থায়ীভাবে মুছে যাবে এবং আর ফিরিয়ে আনা যাবে না।';
    document.getElementById('confirmOverlay').classList.add('open');
    return;
  }
  // লগিন করা থাকলে phone verify modal দেখাও
  document.getElementById('clearVerifyPhone').value = '';
  document.getElementById('clearVerifyError').textContent = '';
  document.getElementById('clearVerifyOverlay').classList.add('open');
}

function closeClearVerify() {
  document.getElementById('clearVerifyOverlay').classList.remove('open');
}

function executeClearAll() {
  const phone = localStorage.getItem('hisab_phone') || '';
  const entered = document.getElementById('clearVerifyPhone').value.trim();
  if (entered !== phone) {
    const errEl = document.getElementById('clearVerifyError');
    errEl.textContent = '❌ নম্বর মিলছে না। সঠিক নম্বর দিন।';
    const inp = document.getElementById('clearVerifyPhone');
    inp.style.animation = 'shake 0.4s';
    setTimeout(() => { inp.style.animation = ''; errEl.textContent = ''; }, 2500);
    return;
  }
  // ভেরিফাই সফল — ডেটা মুছুন
  closeClearVerify();
  data = { transactions: [], loans: [] };
  save();
  updateSummary();
  renderRecentTx();
  renderAllTx();
  renderLoans();
  showToast('🗑️ সব ডেটা মুছে ফেলা হয়েছে');
}

function confirmDelete() {
  if (!pendingDeleteId) return;
  // সব ডেটা মুছুন (গেস্ট মোড থেকে)
  if (pendingDeleteId === '__ALL__') {
    data = { transactions: [], loans: [] };
    save();
    updateSummary();
    renderRecentTx();
    renderAllTx();
    renderLoans();
    // Reset confirm modal texts
    document.querySelector('.confirm-title').textContent = 'মুছে ফেলবেন?';
    document.querySelector('.confirm-msg').textContent = 'এই লেনদেনটি স্থায়ীভাবে মুছে যাবে এবং আর ফিরিয়ে আনা যাবে না।';
    closeConfirm();
    showToast('🗑️ সব ডেটা মুছে ফেলা হয়েছে');
    return;
  }
  // repay হলে সংশ্লিষ্ট loan এর paidAmount ঠিক করো
  const tx = data.transactions.find(t => t.id === pendingDeleteId);
  if (tx && tx.type === 'repay' && tx.loanId) {
    const loan = data.loans.find(l => l.id === tx.loanId);
    if (loan) {
      loan.paidAmount = Math.max(0, (loan.paidAmount || 0) - tx.amount);
      if (loan.status === 'paid') loan.status = 'pending';
    }
  }
  data.transactions = data.transactions.filter(t => t.id !== pendingDeleteId);
  data.loans = data.loans.filter(l => l.id !== pendingDeleteId);
  save();
  updateSummary();
  renderRecentTx();
  renderAllTx();
  renderLoans();
  closeConfirm();
  showToast('🗑️ মুছে ফেলা হয়েছে');
}
// Check login state first
(function initLoginCheck() {
  const loggedIn = localStorage.getItem('hisab_logged_in');
  if (loggedIn) {
    document.getElementById('loginScreen').classList.add('hidden');
    // Reload data for this user
    data = JSON.parse(localStorage.getItem(getDataKey()) || '{"transactions":[],"loans":[]}');
    restoreUserOnLogin();
  }
})();

updateSummary();
renderRecentTx();

// Restore dark mode
if (localStorage.getItem('hisab_dark')) {
  document.body.classList.add('dark-mode');
  document.getElementById('darkToggle').classList.add('on');
}

function restoreUserOnLogin() {
  // Reload data for current phone
  data = JSON.parse(localStorage.getItem(getDataKey()) || '{"transactions":[],"loans":[]}');
  const _ud2 = JSON.parse(localStorage.getItem(getUserKey()) || '{}');
  const phone = localStorage.getItem('hisab_phone') || '';
  // সেটিংস থেকে দেওয়া নাম থাকলে সেটাই দেখাও, না থাকলে ফোন নম্বর
  const displayName = _ud2.name || (phone ? '+880 ' + phone : 'আমার হিসাব');
  const displaySub  = _ud2.sub  || (phone ? 'মোবাইল অ্যাকাউন্ট' : 'ব্যক্তিগত অ্যাকাউন্ট');
  document.getElementById('settingsUserName').textContent = displayName;
  document.getElementById('settingsUserSub').textContent  = displaySub;
  // topbar-এ কাস্টম নাম দেখাও
  const topName = document.querySelector('.user-name');
  if (topName) topName.textContent = _ud2.name || 'আমার হিসাব';
  // Update settings phone display
  const phoneDisp = document.getElementById('currentPhoneDisplay');
  if (phoneDisp) phoneDisp.textContent = phone ? '+880 ' + phone : 'অ্যাকাউন্ট ছাড়া ব্যবহার';
  // Refresh UI
  updateSummary();
  renderRecentTx();
}

// ===== LOGOUT / ACCOUNT SWITCH =====
function logoutUser() {
  localStorage.removeItem('hisab_logged_in');
  localStorage.removeItem('hisab_phone');
  // Reset data in memory (not deleting saved data)
  data = { transactions: [], loans: [] };
  // Show login screen again
  const ls = document.getElementById('loginScreen');
  ls.classList.remove('hidden');
  ls.style.opacity = '0';
  ls.style.transform = 'scale(0.97)';
  // Reset login form
  document.getElementById('loginStep1').style.display = 'block';
  document.getElementById('loginStep2').style.display = 'none';
  document.getElementById('phoneInput').value = '';
  document.getElementById('dot1').classList.add('active');
  document.getElementById('dot2').classList.remove('active');
  requestAnimationFrame(() => {
    ls.style.transition = 'opacity 0.3s, transform 0.3s';
    ls.style.opacity = '1';
    ls.style.transform = 'scale(1)';
  });
  // Reset UI summary
  updateSummary();
  renderRecentTx();
  // Switch to home tab
  switchTab('home');
  setNavActive(document.getElementById('nav-home'));
}

// ===== LOGIN FUNCTIONS =====
let loginPhone = '';
let otpTimerInterval = null;
let currentOTP = '123456'; // Demo OTP

function sendOTP() {
  const raw = document.getElementById('phoneInput').value.trim();
  // Validate BD number: 01XXXXXXXXX (11 digits)
  if (!/^01[3-9]\d{8}$/.test(raw)) {
    shakeInput();
    showLoginError('সঠিক মোবাইল নম্বর দিন (যেমন: 01712345678)');
    return;
  }
  loginPhone = raw;
  // Show step 2
  document.getElementById('loginStep1').style.display = 'none';
  document.getElementById('loginStep2').style.display = 'block';
  document.getElementById('dot1').classList.remove('active');
  document.getElementById('dot2').classList.add('active');
  document.getElementById('otpPhoneDisplay').textContent = '+880 ' + loginPhone;
  document.getElementById('otpSentIcon').style.display = 'block';
  setTimeout(() => { document.getElementById('otpSentIcon').style.display = 'none'; }, 1500);
  // Clear OTP fields
  for (let i = 0; i < 6; i++) document.getElementById('otp'+i).value = '';
  document.getElementById('otp0').focus();
  startOTPTimer();
}

function shakeInput() {
  const wrap = document.querySelector('.phone-input-wrap');
  wrap.style.animation = 'shake 0.4s';
  setTimeout(() => { wrap.style.animation = ''; }, 400);
}

function showLoginError(msg) {
  let err = document.getElementById('loginError');
  if (!err) {
    err = document.createElement('div');
    err.id = 'loginError';
    err.style.cssText = 'color:#FF5C6C;font-size:12px;font-weight:600;margin-top:10px;text-align:center;';
    document.querySelector('.phone-input-wrap').after(err);
  }
  err.textContent = msg;
  setTimeout(() => { if (err) err.textContent = ''; }, 3000);
}

function backToPhone() {
  document.getElementById('loginStep2').style.display = 'none';
  document.getElementById('loginStep1').style.display = 'block';
  document.getElementById('dot2').classList.remove('active');
  document.getElementById('dot1').classList.add('active');
  if (otpTimerInterval) { clearInterval(otpTimerInterval); otpTimerInterval = null; }
}

function otpInput(idx) {
  const el = document.getElementById('otp'+idx);
  const val = el.value.replace(/\D/g, '');
  el.value = val.slice(-1);
  if (val && idx < 5) document.getElementById('otp'+(idx+1)).focus();
  // Auto verify if all filled
  const full = Array.from({length:6}, (_,i) => document.getElementById('otp'+i).value).join('');
  if (full.length === 6) setTimeout(verifyOTP, 300);
}

function otpKeydown(idx, e) {
  if (e.key === 'Backspace' && !document.getElementById('otp'+idx).value && idx > 0) {
    document.getElementById('otp'+(idx-1)).focus();
  }
}

function verifyOTP() {
  const entered = Array.from({length:6}, (_,i) => document.getElementById('otp'+i).value).join('');
  if (entered.length < 6) { showOTPError('৬ সংখ্যার OTP দিন'); return; }
  if (entered === currentOTP) {
    // Success!
    doLogin();
  } else {
    showOTPError('OTP সঠিক নয়। আবার চেষ্টা করুন।');
    // Shake OTP row
    const row = document.querySelector('.otp-row');
    row.style.animation = 'shake 0.4s';
    setTimeout(() => { row.style.animation = ''; }, 400);
  }
}

function showOTPError(msg) {
  let err = document.getElementById('otpError');
  if (!err) {
    err = document.createElement('div');
    err.id = 'otpError';
    err.style.cssText = 'color:#FF5C6C;font-size:12px;font-weight:600;margin-top:10px;text-align:center;';
    document.getElementById('verifyOtpBtn').after(err);
  }
  err.textContent = msg;
  setTimeout(() => { if (err) err.textContent = ''; }, 3000);
}

function doLogin() {
  const phone = loginPhone;
  // Save login state
  localStorage.setItem('hisab_logged_in', '1');
  localStorage.setItem('hisab_phone', phone);
  // Set user name from phone if not set for this number
  const userKey = 'hisab_user_' + phone;
  const ud = JSON.parse(localStorage.getItem(userKey) || '{}');
  if (!ud.name) {
    const shortPhone = '+880 ' + phone;
    localStorage.setItem(userKey, JSON.stringify({ name: shortPhone, sub: 'মোবাইল অ্যাকাউন্ট' }));
  }
  // Restore this user's data and UI
  restoreUserOnLogin();

  // Animate out login screen
  const ls = document.getElementById('loginScreen');
  ls.style.transition = 'opacity 0.35s, transform 0.35s';
  ls.style.opacity = '0';
  ls.style.transform = 'scale(0.97)';
  setTimeout(() => { ls.classList.add('hidden'); }, 350);

  if (otpTimerInterval) clearInterval(otpTimerInterval);
  showToast('✅ লগিন সফল! স্বাগতম 👋');
}

function skipLogin() {
  localStorage.setItem('hisab_logged_in', '1');
  localStorage.removeItem('hisab_phone'); // guest মোড
  restoreUserOnLogin();
  const ls = document.getElementById('loginScreen');
  ls.style.transition = 'opacity 0.3s';
  ls.style.opacity = '0';
  setTimeout(() => { ls.classList.add('hidden'); }, 300);
  showToast('👋 স্বাগতম! অ্যাকাউন্ট ছাড়া ব্যবহার করছেন।');
}

function startOTPTimer() {
  if (otpTimerInterval) clearInterval(otpTimerInterval);
  let secs = 30;
  const timerEl = document.getElementById('timerText');
  updateTimerText(timerEl, secs);
  otpTimerInterval = setInterval(() => {
    secs--;
    if (secs <= 0) {
      clearInterval(otpTimerInterval);
      timerEl.innerHTML = '<span onclick="resendOTP()">পুনরায় OTP পাঠান</span>';
    } else {
      updateTimerText(timerEl, secs);
    }
  }, 1000);
}

function updateTimerText(el, s) {
  // Convert to Bengali digits
  const bn = String(s).split('').map(d => '০১২৩৪৫৬৭৮৯'[d] || d).join('');
  el.textContent = bn + ' সেকেন্ড পর পুনরায় পাঠান';
}

function resendOTP() {
  document.getElementById('timerText').textContent = 'OTP পাঠানো হচ্ছে...';
  setTimeout(() => { startOTPTimer(); }, 500);
  for (let i = 0; i < 6; i++) document.getElementById('otp'+i).value = '';
  document.getElementById('otp0').focus();
}

// ===== PDF EXPORT =====
function exportMonthlyPDF() {
  const now = new Date();
  const month = now.getMonth();
  const year = now.getFullYear();
  const monthName = BN_MONTHS[month] + ' ' + toBn(year);

  const txs = data.transactions.filter(t => {
    const d = new Date(t.date);
    return d.getMonth() === month && d.getFullYear() === year;
  });

  const inc  = txs.filter(t => t.type === 'income').reduce((s,t) => s+t.amount, 0);
  const exp  = txs.filter(t => t.type === 'expense').reduce((s,t) => s+t.amount, 0);
  const lout = txs.filter(t => t.type === 'loan-out').reduce((s,t) => s+t.amount, 0);
  const lin  = txs.filter(t => t.type === 'loan-in').reduce((s,t) => s+t.amount, 0);
  const net  = inc - exp;

  const ud = JSON.parse(localStorage.getItem(getUserKey()) || '{}');
  const userName = ud.name || 'আমার হিসাব';

  const typeLabel = { income:'আয়', expense:'ব্যয়', 'loan-out':'ঋণ দেওয়া', 'loan-in':'ঋণ নেওয়া', repay:'পরিশোধ' };
  const typeColor = { income:'#00D68F', expense:'#FF5C6C', 'loan-out':'#FFB347', 'loan-in':'#4DA6FF', repay:'#C8B4FF' };

  const txRows = txs.length ? txs.map(t => {
    const d = new Date(t.date);
    const dateStr = toBn(d.getDate()) + ' ' + BN_MONTHS[d.getMonth()];
    const color = typeColor[t.type] || '#9B91C5';
    const sign = { income:'+', expense:'-', 'loan-out':'↑', 'loan-in':'↓', repay:'↩' }[t.type] || '';
    return `<tr>
      <td style="padding:10px 12px;border-bottom:1px solid #f0f0f0;font-size:13px;color:#333">${dateStr}</td>
      <td style="padding:10px 12px;border-bottom:1px solid #f0f0f0;font-size:13px;color:#333">${t.note}</td>
      <td style="padding:10px 12px;border-bottom:1px solid #f0f0f0;text-align:center">
        <span style="background:${color}22;color:${color};padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700">${typeLabel[t.type]||t.type}</span>
      </td>
      <td style="padding:10px 12px;border-bottom:1px solid #f0f0f0;text-align:right;font-weight:700;font-size:13px;color:${color}">${sign}${fmtAmt(t.amount)}</td>
    </tr>`;
  }).join('') : `<tr><td colspan="4" style="text-align:center;padding:30px;color:#999;font-size:13px">এই মাসে কোনো লেনদেন নেই</td></tr>`;

  const html = `<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  * { margin:0; padding:0; box-sizing:border-box; }
  body { font-family:'Noto Sans Bengali',sans-serif; background:#f8f7ff; color:#1A1035; }
  .header { background:linear-gradient(135deg,#1A1035,#4F3A9E); color:#fff; padding:32px 36px 28px; }
  .app-name { font-size:13px; letter-spacing:2px; text-transform:uppercase; opacity:0.6; margin-bottom:6px; }
  .report-title { font-size:28px; font-weight:800; margin-bottom:4px; }
  .report-sub { font-size:13px; opacity:0.7; }
  .user-line { margin-top:12px; font-size:13px; opacity:0.8; }
  .summary { display:grid; grid-template-columns:repeat(4,1fr); gap:14px; padding:24px 36px; }
  .s-card { background:#fff; border-radius:14px; padding:16px; box-shadow:0 2px 12px rgba(0,0,0,0.06); }
  .s-label { font-size:11px; color:#9B91C5; text-transform:uppercase; letter-spacing:0.5px; font-weight:700; margin-bottom:6px; }
  .s-val { font-size:20px; font-weight:800; }
  .s-inc { color:#00D68F; } .s-exp { color:#FF5C6C; } .s-lout { color:#FFB347; } .s-net { color:#4F3A9E; }
  .net-bar { margin:0 36px 24px; background:#fff; border-radius:14px; padding:16px 20px; display:flex; align-items:center; justify-content:space-between; box-shadow:0 2px 12px rgba(0,0,0,0.06); }
  .net-label { font-size:13px; color:#9B91C5; font-weight:700; }
  .net-val { font-size:22px; font-weight:800; }
  .section-title { padding:0 36px 12px; font-size:11px; text-transform:uppercase; letter-spacing:1px; color:#9B91C5; font-weight:700; }
  table { width:calc(100% - 72px); margin:0 36px 32px; border-collapse:collapse; background:#fff; border-radius:14px; overflow:hidden; box-shadow:0 2px 12px rgba(0,0,0,0.06); }
  thead { background:#1A1035; color:#fff; }
  thead th { padding:12px 12px; text-align:left; font-size:11px; font-weight:700; letter-spacing:0.5px; }
  thead th:last-child { text-align:right; }
  .footer { text-align:center; padding:20px; font-size:11px; color:#C8B4FF; border-top:1px solid #f0f0f0; }
  @media print { body{background:#fff} }
</style>
</head>
<body>
<div class="header">
  <div class="app-name">হিসাব অ্যাপ</div>
  <div class="report-title">মাসিক হিসাব রিপোর্ট</div>
  <div class="report-sub">${monthName}</div>
  <div class="user-line">👤 ${userName}</div>
</div>
<div class="summary">
  <div class="s-card"><div class="s-label">মোট আয়</div><div class="s-val s-inc">${fmtAmt(inc)}</div></div>
  <div class="s-card"><div class="s-label">মোট ব্যয়</div><div class="s-val s-exp">${fmtAmt(exp)}</div></div>
  <div class="s-card"><div class="s-label">ঋণ দেওয়া</div><div class="s-val s-lout">${fmtAmt(lout)}</div></div>
  <div class="s-card"><div class="s-label">ঋণ নেওয়া</div><div class="s-val s-lout" style="color:#4DA6FF">${fmtAmt(lin)}</div></div>
</div>
<div class="net-bar">
  <span class="net-label">নেট সঞ্চয় (আয় − ব্যয়)</span>
  <span class="net-val s-net" style="color:${net>=0?'#00D68F':'#FF5C6C'}">${net>=0?'+':''}${fmtAmt(net)}</span>
</div>
<div class="section-title">লেনদেনের বিবরণ (${toBn(txs.length)}টি)</div>
<table>
  <thead><tr>
    <th>তারিখ</th><th>বিবরণ</th><th style="text-align:center">ধরন</th><th style="text-align:right">পরিমাণ</th>
  </tr></thead>
  <tbody>${txRows}</tbody>
</table>
<div class="footer">হিসাব অ্যাপ • রিপোর্ট তৈরি: ${new Date().toLocaleDateString('bn-BD')}</div>
</body></html>`;

  const w = window.open('', '_blank');
  w.document.write(html);
  w.document.close();
  w.onload = () => {
    setTimeout(() => { w.print(); }, 600);
  };
  showToast('📄 PDF রিপোর্ট তৈরি হচ্ছে...');
}

// Add shake animation
const shakeStyle = document.createElement('style');
shakeStyle.textContent = `@keyframes shake { 0%,100%{transform:translateX(0)} 20%{transform:translateX(-8px)} 40%{transform:translateX(8px)} 60%{transform:translateX(-5px)} 80%{transform:translateX(5px)} }`;
document.head.appendChild(shakeStyle);

// Phone input: only allow numbers
document.getElementById('phoneInput').addEventListener('input', function() {
  this.value = this.value.replace(/\D/g, '').slice(0, 11);
});
document.getElementById('phoneInput').addEventListener('keydown', function(e) {
  if (e.key === 'Enter') sendOTP();
});
</script>
</body>
</html>
