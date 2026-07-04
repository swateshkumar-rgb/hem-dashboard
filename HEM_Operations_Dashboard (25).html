<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>HEM Performance Dashboard — CARS24</title>

<!-- Dependencies -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.4.1/papaparse.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>

<!-- Gilroy Font — CARS24's brand typeface -->
<link rel="stylesheet" href="https://gistcdn.githack.com/mfd/09b70eb47474836f25a21660282ce0fd/raw/e06a670afcb2b861ed2ac4a1ef752d062ef6b46b/Gilroy.css"/>

<style>
/* ═══════════════════════════════════════════════
   DESIGN TOKENS — CARS24 Brand System
═══════════════════════════════════════════════ */
:root {
  /* CARS24 Brand Colors */
  --c24-red:       #E52529;
  --c24-red-dark:  #C41E22;
  --c24-red-light: #FFF1F1;
  --c24-black:     #1A1A1A;
  --c24-grey-900:  #2D2D2D;
  --c24-grey-700:  #4A4A4A;
  --c24-grey-500:  #767676;
  --c24-grey-300:  #B8B8B8;
  --c24-grey-100:  #F2F2F2;
  --c24-grey-50:   #F8F8F8;
  --c24-white:     #FFFFFF;

  /* Semantic Colors */
  --green:         #16A34A;
  --green-light:   #EDFAF3;
  --amber:         #D97706;
  --amber-light:   #FFFBEB;
  --blue:          #2563EB;
  --blue-light:    #EFF4FF;
  --purple:        #7C3AED;
  --purple-light:  #F5F3FF;
  --orange:        #EA580C;
  --orange-light:  #FFF7ED;

  /* Layout */
  --sidebar-w: 220px;
  --header-h:  60px;
  --radius:    12px;
  --radius-sm: 7px;
  --shadow-sm: 0 1px 3px rgba(0,0,0,.07);
  --shadow:    0 4px 16px rgba(0,0,0,.08);
  --shadow-lg: 0 8px 32px rgba(0,0,0,.12);

  /* Typography — Gilroy */
  --font: 'Gilroy', 'Segoe UI', system-ui, -apple-system, sans-serif;
}

/* ═══════════════════════════════════════════════
   RESET & BASE
═══════════════════════════════════════════════ */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  font-family: var(--font);
  font-size: 14px;
  color: var(--c24-black);
  background: var(--c24-grey-50);
  line-height: 1.5;
  min-height: 100vh;
}
button { font-family: var(--font); cursor: pointer; }
input, select { font-family: var(--font); }

/* ═══════════════════════════════════════════════
   LAYOUT
═══════════════════════════════════════════════ */
.app-shell { display: flex; min-height: 100vh; }

/* Sidebar */
.sidebar {
  width: var(--sidebar-w);
  background: var(--c24-black);
  display: flex;
  flex-direction: column;
  position: fixed;
  top: 0; left: 0; bottom: 0;
  z-index: 200;
  transition: transform .3s;
}
.sidebar-logo {
  padding: 18px 20px;
  border-bottom: 1px solid rgba(255,255,255,.08);
  display: flex; align-items: center; gap: 10px;
}
.logo-mark {
  background: var(--c24-red);
  color: #fff;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: .5px;
  padding: 5px 8px;
  border-radius: 6px;
}
.logo-text {
  color: #fff;
  font-size: 13px;
  font-weight: 700;
  line-height: 1.2;
  letter-spacing: .3px;
}
.logo-sub { color: rgba(255,255,255,.4); font-size: 10px; font-weight: 500; }

.sidebar-nav { flex: 1; padding: 16px 12px; overflow-y: auto; }
.nav-group-label {
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: .8px;
  color: rgba(255,255,255,.3);
  padding: 8px 8px 6px;
  margin-top: 8px;
}
.nav-item {
  display: flex; align-items: center; gap: 10px;
  padding: 9px 10px;
  border-radius: var(--radius-sm);
  color: rgba(255,255,255,.6);
  font-size: 13px;
  font-weight: 600;
  cursor: pointer;
  transition: all .15s;
  margin-bottom: 2px;
  border: none; background: transparent; width: 100%; text-align: left;
}
.nav-item:hover { background: rgba(255,255,255,.06); color: rgba(255,255,255,.9); }
.nav-item.active { background: var(--c24-red); color: #fff; }
.nav-item .nav-icon { font-size: 16px; flex-shrink: 0; }
.nav-badge {
  margin-left: auto;
  background: rgba(255,255,255,.15);
  color: rgba(255,255,255,.7);
  font-size: 10px;
  font-weight: 700;
  padding: 2px 7px;
  border-radius: 20px;
}
.nav-item.active .nav-badge { background: rgba(255,255,255,.25); color: #fff; }

.sidebar-footer {
  padding: 14px 12px;
  border-top: 1px solid rgba(255,255,255,.08);
}
.sidebar-action {
  display: flex; align-items: center; gap: 8px;
  padding: 8px 10px;
  border-radius: var(--radius-sm);
  color: rgba(255,255,255,.5);
  font-size: 12px;
  font-weight: 600;
  cursor: pointer;
  transition: all .15s;
  border: none; background: transparent; width: 100%; text-align: left;
}
.sidebar-action:hover { background: rgba(255,255,255,.06); color: rgba(255,255,255,.8); }

/* Main Content */
.main-content {
  margin-left: var(--sidebar-w);
  flex: 1;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Top Bar */
.topbar {
  height: var(--header-h);
  background: var(--c24-white);
  border-bottom: 1px solid #EBEBEB;
  display: flex; align-items: center;
  padding: 0 28px;
  gap: 16px;
  position: sticky; top: 0; z-index: 100;
  box-shadow: var(--shadow-sm);
}
.topbar-title {
  flex: 1;
  font-size: 15px;
  font-weight: 700;
  color: var(--c24-black);
  letter-spacing: -.2px;
}
.topbar-badge {
  font-size: 10px;
  font-weight: 700;
  padding: 2px 8px;
  border-radius: 20px;
  background: var(--c24-red-light);
  color: var(--c24-red);
  text-transform: uppercase;
  letter-spacing: .4px;
}

/* Buttons */
.btn {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 8px 16px;
  border-radius: var(--radius-sm);
  font-family: var(--font);
  font-size: 12px;
  font-weight: 700;
  cursor: pointer;
  border: none;
  transition: all .15s;
  letter-spacing: .2px;
  white-space: nowrap;
}
.btn-primary   { background: var(--c24-red); color: #fff; }
.btn-primary:hover { background: var(--c24-red-dark); }
.btn-secondary { background: var(--c24-grey-100); color: var(--c24-grey-700); }
.btn-secondary:hover { background: #E8E8E8; }
.btn-success   { background: var(--green-light); color: var(--green); border: 1px solid #BBF7D0; }
.btn-success:hover { background: #D1FAE5; }
.btn-danger    { background: var(--c24-red-light); color: var(--c24-red); border: 1px solid #FECACA; }
.btn-danger:hover { background: #FEE2E2; }
.btn-ghost     { background: transparent; color: var(--c24-grey-500); border: 1px solid #E5E5E5; }
.btn-ghost:hover { background: var(--c24-grey-50); color: var(--c24-black); }
.btn-sm { padding: 5px 11px; font-size: 11px; }

/* Page Content */
.page-content { padding: 24px 28px 48px; flex: 1; }
.page { display: none; }
.page.active { display: block; animation: fadeIn .2s ease; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

/* ═══════════════════════════════════════════════
   UPLOAD PANEL
═══════════════════════════════════════════════ */
.upload-panel {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 20px 24px;
  display: flex; gap: 20px; align-items: flex-end; flex-wrap: wrap;
  margin-bottom: 20px;
  box-shadow: var(--shadow-sm);
}
.upload-group { flex: 1; min-width: 220px; }
.upload-label {
  display: block;
  font-size: 10px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .7px;
  color: var(--c24-grey-500);
  margin-bottom: 8px;
}
.upload-zone {
  border: 1.5px dashed #D5D5D5;
  border-radius: var(--radius-sm);
  padding: 13px 16px;
  display: flex; align-items: center; gap: 12px;
  cursor: pointer;
  transition: all .18s;
  background: var(--c24-grey-50);
}
.upload-zone:hover { border-color: var(--c24-red); background: var(--c24-red-light); }
.upload-zone.loaded { border-color: var(--green); background: var(--green-light); border-style: solid; }
.upload-zone input[type=file] { display: none; }
.upload-zone-icon { font-size: 22px; flex-shrink: 0; }
.upload-zone-text strong {
  display: block;
  font-size: 12px;
  font-weight: 700;
  color: var(--c24-black);
  margin-bottom: 1px;
}
.upload-zone-text span { font-size: 11px; color: var(--c24-grey-500); }
.upload-actions { display: flex; gap: 8px; flex-wrap: wrap; align-items: center; }

/* ═══════════════════════════════════════════════
   FILTER BAR
═══════════════════════════════════════════════ */
.filter-bar {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 14px 20px;
  display: none;
  gap: 14px;
  align-items: flex-end;
  flex-wrap: wrap;
  margin-bottom: 20px;
  box-shadow: var(--shadow-sm);
}
.filter-bar.visible { display: flex; }
.fg { display: flex; flex-direction: column; gap: 4px; min-width: 150px; }
.fg label {
  font-size: 10px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .6px;
  color: var(--c24-grey-500);
}
.fg select, .fg input[type=date] {
  padding: 7px 10px;
  border: 1px solid #E0E0E0;
  border-radius: var(--radius-sm);
  font-family: var(--font);
  font-size: 12px;
  color: var(--c24-black);
  background: var(--c24-white);
  outline: none;
  transition: border .15s;
  font-weight: 500;
}
.fg select:focus, .fg input[type=date]:focus { border-color: var(--c24-red); }

/* ═══════════════════════════════════════════════
   SECTION HEADINGS
═══════════════════════════════════════════════ */
.section-head {
  display: flex; justify-content: space-between; align-items: center;
  margin: 28px 0 14px;
  flex-wrap: wrap; gap: 8px;
}
.section-title {
  font-size: 15px;
  font-weight: 800;
  color: var(--c24-black);
  letter-spacing: -.3px;
  display: flex; align-items: center; gap: 8px;
}
.section-chip {
  font-size: 10px;
  font-weight: 700;
  padding: 2px 8px;
  border-radius: 20px;
  background: var(--c24-grey-100);
  color: var(--c24-grey-700);
}

/* ═══════════════════════════════════════════════
   KPI CARDS
═══════════════════════════════════════════════ */
.kpi-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(175px, 1fr)); gap: 14px; margin-bottom: 16px; }
.kpi-card {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 18px 20px 16px;
  box-shadow: var(--shadow-sm);
  transition: box-shadow .18s, transform .18s;
  position: relative;
  overflow: hidden;
}
.kpi-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  border-radius: var(--radius) var(--radius) 0 0;
}
.kpi-card.red::before   { background: var(--c24-red); }
.kpi-card.green::before { background: var(--green); }
.kpi-card.amber::before { background: var(--amber); }
.kpi-card.blue::before  { background: var(--blue); }
.kpi-card.purple::before{ background: var(--purple); }
.kpi-card.orange::before{ background: var(--orange); }
.kpi-card:hover { box-shadow: var(--shadow); transform: translateY(-2px); }
.kpi-label {
  font-size: 10px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .6px;
  color: var(--c24-grey-500);
  margin-bottom: 10px;
}
.kpi-value {
  font-size: 30px;
  font-weight: 800;
  line-height: 1;
  letter-spacing: -1px;
  margin-bottom: 6px;
}
.kpi-card.red   .kpi-value { color: var(--c24-red); }
.kpi-card.green .kpi-value { color: var(--green); }
.kpi-card.amber .kpi-value { color: var(--amber); }
.kpi-card.blue  .kpi-value { color: var(--blue); }
.kpi-card.purple.kpi-value { color: var(--purple); }
.kpi-card.orange.kpi-value { color: var(--orange); }
.kpi-sub { font-size: 11px; color: var(--c24-grey-500); font-weight: 500; }

/* ═══════════════════════════════════════════════
   TIME CARDS
═══════════════════════════════════════════════ */
.time-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(210px, 1fr)); gap: 14px; margin-bottom: 20px; }
.time-card {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 16px 18px;
  box-shadow: var(--shadow-sm);
}
.time-card-head {
  font-size: 10px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .6px;
  color: var(--c24-grey-500);
  margin-bottom: 14px;
  display: flex; align-items: center; gap: 6px;
}
.time-card-row {
  display: flex; justify-content: space-between; align-items: center;
  margin-bottom: 8px;
}
.time-card-row:last-child { margin-bottom: 0; }
.time-card-row span { font-size: 12px; color: var(--c24-grey-700); font-weight: 500; }
.time-card-row strong { font-size: 20px; font-weight: 800; letter-spacing: -.5px; }
.time-val-open   { color: var(--c24-red); }
.time-val-prog   { color: var(--amber); }
.time-val-closed { color: var(--green); }

/* ═══════════════════════════════════════════════
   CHARTS
═══════════════════════════════════════════════ */
.chart-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 20px; }
.chart-grid-3 { display: grid; grid-template-columns: 2fr 1fr; gap: 16px; margin-bottom: 20px; }
.chart-card {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 18px 20px;
  box-shadow: var(--shadow-sm);
}
.chart-card-title {
  font-size: 12px;
  font-weight: 800;
  color: var(--c24-black);
  margin-bottom: 16px;
  letter-spacing: -.1px;
}
canvas { max-height: 250px; }

/* ═══════════════════════════════════════════════
   TABLES
═══════════════════════════════════════════════ */
.table-card {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  margin-bottom: 20px;
}
.table-scroll { overflow-x: auto; }
table { width: 100%; border-collapse: collapse; font-size: 12px; }
thead th {
  padding: 10px 14px;
  text-align: left;
  font-size: 10px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .5px;
  color: var(--c24-grey-500);
  background: var(--c24-grey-50);
  border-bottom: 1px solid #EBEBEB;
  white-space: nowrap;
}
tbody td {
  padding: 10px 14px;
  border-bottom: 1px solid #F0F0F0;
  vertical-align: middle;
  font-weight: 500;
}
tbody tr:last-child td { border-bottom: none; }
tbody tr:hover td { background: var(--c24-grey-50); }
.td-muted { color: var(--c24-grey-500); font-size: 11px; }
.td-bold  { font-weight: 800; }
.td-id    { font-weight: 700; color: var(--c24-red); font-size: 11px; }

/* Status Pills */
.pill {
  display: inline-flex; align-items: center; gap: 4px;
  padding: 3px 9px;
  border-radius: 20px;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: .2px;
  white-space: nowrap;
}
.pill-open   { background: var(--c24-red-light); color: var(--c24-red); }
.pill-prog   { background: var(--amber-light); color: var(--amber); }
.pill-closed { background: var(--green-light); color: var(--green); }
.pill-dept   { background: var(--blue-light); color: var(--blue); }
.pill-hem    { background: var(--purple-light); color: var(--purple); }

/* TAT coloring */
.tat { font-weight: 800; font-size: 12px; }
.tat-ok  { color: var(--green); }
.tat-mid { color: var(--amber); }
.tat-hi  { color: var(--c24-red); }

/* Score bars */
.score-wrap { display: flex; align-items: center; gap: 8px; }
.score-bar  { flex: 1; height: 5px; border-radius: 3px; background: #EBEBEB; overflow: hidden; min-width: 60px; }
.score-fill { height: 100%; border-radius: 3px; }
.fill-red    { background: var(--c24-red); }
.fill-purple { background: var(--purple); }

/* Empty / No-data */
.empty-row td { text-align: center; padding: 28px; color: var(--c24-grey-500); font-size: 12px; }
.empty-state {
  text-align: center;
  padding: 64px 20px;
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
}
.empty-state-icon { font-size: 44px; margin-bottom: 14px; }
.empty-state h3 { font-size: 15px; font-weight: 800; margin-bottom: 6px; }
.empty-state p  { font-size: 12px; color: var(--c24-grey-500); }

/* ═══════════════════════════════════════════════
   LOADING OVERLAY
═══════════════════════════════════════════════ */
.loading-overlay {
  position: fixed; inset: 0;
  background: rgba(255,255,255,.85);
  display: flex; flex-direction: column; align-items: center; justify-content: center;
  z-index: 9999; gap: 16px;
  backdrop-filter: blur(2px);
}
.loading-overlay.hidden { display: none; }
.spinner {
  width: 40px; height: 40px;
  border: 3px solid #EBEBEB;
  border-top-color: var(--c24-red);
  border-radius: 50%;
  animation: spin .65s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.loading-text { font-size: 13px; font-weight: 700; color: var(--c24-grey-500); }

/* ═══════════════════════════════════════════════
   DEPARTMENT TIMELINE (Extra Feature)
═══════════════════════════════════════════════ */
.timeline-form {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 20px 24px;
  margin-bottom: 20px;
  box-shadow: var(--shadow-sm);
  display: flex; gap: 14px; align-items: flex-end; flex-wrap: wrap;
}
.timeline-table-wrap {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  margin-bottom: 20px;
}
.revision-history {
  font-size: 10px;
  color: var(--c24-grey-500);
  line-height: 1.8;
}
.revision-item::before { content: '↪ '; }
.timeline-status-bar {
  height: 5px;
  border-radius: 3px;
  background: var(--green);
  transition: width .4s;
}

/* ═══════════════════════════════════════════════
   CHECKLIST PANEL
═══════════════════════════════════════════════ */
.vs-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 20px; }
.vs-card {
  background: var(--c24-white);
  border: 1px solid #EBEBEB;
  border-radius: var(--radius);
  padding: 20px;
  box-shadow: var(--shadow-sm);
  text-align: center;
}
.vs-label { font-size: 10px; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; color: var(--c24-grey-500); margin-bottom: 10px; }
.vs-score { font-size: 44px; font-weight: 900; letter-spacing: -2px; line-height: 1; margin-bottom: 4px; }
.vs-score.hem    { color: var(--c24-red); }
.vs-score.nonhem { color: var(--purple); }
.vs-sub { font-size: 11px; color: var(--c24-grey-500); font-weight: 500; }

/* ═══════════════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════════════ */
@media (max-width: 1024px) {
  .chart-grid, .chart-grid-3 { grid-template-columns: 1fr; }
}
@media (max-width: 768px) {
  .sidebar { transform: translateX(-100%); }
  .main-content { margin-left: 0; }
  .page-content { padding: 16px; }
  .kpi-grid { grid-template-columns: 1fr 1fr; }
  .vs-grid { grid-template-columns: 1fr; }
}

/* Utility */
.mt-4 { margin-top: 16px; }
.flex-row { display: flex; gap: 8px; flex-wrap: wrap; }
.text-right { text-align: right; }
</style>
</head>
<body>

<!-- Loading Overlay -->
<div class="loading-overlay hidden" id="loadingOverlay">
  <div class="spinner"></div>
  <div class="loading-text" id="loadingText">Processing data…</div>
</div>

<!-- App Shell -->
<div class="app-shell">

  <!-- ══ SIDEBAR ══ -->
  <aside class="sidebar">
    <div class="sidebar-logo">
      <!-- CARS24 Logo Mark -->
      <svg width="36" height="36" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect width="36" height="36" rx="7" fill="#E52529"/>
        <text x="18" y="14" text-anchor="middle" fill="white" font-size="7" font-weight="800" font-family="Gilroy,system-ui,sans-serif" letter-spacing="0.5">CARS</text>
        <text x="18" y="27" text-anchor="middle" fill="white" font-size="11" font-weight="900" font-family="Gilroy,system-ui,sans-serif" letter-spacing="-0.5">24</text>
      </svg>
      <div>
        <div class="logo-text">HEM Performance</div>
        <div class="logo-sub">Dashboard · CARS24</div>
      </div>
    </div>

    <nav class="sidebar-nav">
      <div class="nav-group-label">Analytics</div>
      <button class="nav-item active" onclick="navigate('tickets')" id="nav-tickets">
        <span class="nav-icon">🎫</span>
        Ticket Analysis
      </button>
      <button class="nav-item" onclick="navigate('mystery')" id="nav-mystery">
        <span class="nav-icon">🕵️</span>
        Mystery Audit
      </button>
      <button class="nav-item" onclick="navigate('beat')" id="nav-beat">
        <span class="nav-icon">📅</span>
        Beat Audit Plan
      </button>
      <button class="nav-item" onclick="navigate('clreport')" id="nav-clreport">
        <span class="nav-icon">📊</span>
        Checklist Reports
      </button>
      <button class="nav-item" onclick="navigate('hub')" id="nav-hub">
        <span class="nav-icon">🏪</span>
        Hub Performance
      </button>
      <button class="nav-item" onclick="navigate('timeline')" id="nav-timeline">
        <span class="nav-icon">📅</span>
        Dept Timeline
      </button>

      <div class="nav-group-label" style="margin-top:16px">Data</div>
      <button class="nav-item" onclick="navigate('upload')" id="nav-upload">
        <span class="nav-icon">📤</span>
        Upload Files
      </button>
    </nav>

    <div class="sidebar-footer">
      <button class="sidebar-action" onclick="downloadCSV()">
        <span>⬇</span> Export CSV
      </button>
      <button class="sidebar-action" onclick="downloadHTML()">
        <span>⬇</span> Save HTML
      </button>
      <button class="sidebar-action" onclick="clearAll()" style="color:#FF6B6B">
        <span>✕</span> Clear All Data
      </button>
    </div>
  </aside>

  <!-- ══ MAIN CONTENT ══ -->
  <div class="main-content">

    <!-- Top Bar -->
    <div class="topbar">
      <div class="topbar-title" id="topbar-title">Ticket Analysis</div>
      <div id="topbar-meta" style="font-size:11px;color:var(--c24-grey-500);font-weight:600"></div>
      <span class="topbar-badge" id="topbar-badge">LIVE</span>
      <div class="flex-row">
        <button class="btn btn-success btn-sm" onclick="downloadCSV()">⬇ Export</button>
        <button class="btn btn-danger btn-sm" onclick="clearAll()">✕ Clear</button>
      </div>
    </div>

    <!-- Page Content -->
    <div class="page-content">

      <!-- ══ UPLOAD PAGE ══ -->
      <div id="page-upload" class="page">
        <div class="section-head">
          <div class="section-title">📤 Upload Data Files</div>
        </div>

        <div class="upload-panel">
          <div class="upload-group">
            <span class="upload-label">Ticket Data CSV</span>
            <label class="upload-zone" id="zone-tickets">
              <span class="upload-zone-icon">📋</span>
              <div class="upload-zone-text">
                <strong id="fname-tickets">Click to upload Ticket CSV</strong>
                <span>HEM_Tickets file · .csv</span>
              </div>
              <input type="file" id="file-tickets" accept=".csv" onchange="handleTicketFile(event)"/>
            </label>
          </div>
          <div class="upload-group">
            <span class="upload-label">Checklist Submission CSV</span>
            <label class="upload-zone" id="zone-checklist">
              <span class="upload-zone-icon">✅</span>
              <div class="upload-zone-text">
                <strong id="fname-checklist">Click to upload Checklist CSV</strong>
                <span>Checklist_Submission file · .csv</span>
              </div>
              <input type="file" id="file-checklist" accept=".csv" onchange="handleChecklistFile(event)"/>
            </label>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="generateAll()">⚡ Generate Dashboard</button>
          </div>
        </div>

        <div class="empty-state">
          <div class="empty-state-icon">📊</div>
          <h3>Upload your CSV files to get started</h3>
          <p>Upload the Ticket Data CSV and/or Checklist CSV above, then click Generate Dashboard</p>
        </div>
      </div>

      <!-- ══ TICKETS PAGE ══ -->
      <div id="page-tickets" class="page active">

        <!-- Upload Row (compact) -->
        <div class="upload-panel" style="padding:14px 20px">
          <div class="upload-group" style="min-width:200px">
            <label class="upload-zone" id="zone-tickets-2" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:18px">📋</span>
              <div class="upload-zone-text">
                <strong id="fname-tickets-2" style="font-size:11px">Upload Ticket CSV</strong>
                <span>click to change</span>
              </div>
              <input type="file" id="file-tickets-2" accept=".csv" onchange="handleTicketFile(event)"/>
            </label>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="renderTickets()">⚡ Refresh</button>
          </div>
        </div>

        <!-- Filter Bar -->
        <div class="filter-bar" id="ticket-filters">
          <div class="fg">
            <label>Department</label>
            <select id="f-dept" onchange="renderTickets()"><option value="">All Departments</option></select>
          </div>
          <div class="fg">
            <label>HEM</label>
            <select id="f-hem" onchange="renderTickets()"><option value="">All HEMs</option></select>
          </div>
          <div class="fg">
            <label>Store</label>
            <select id="f-store" onchange="renderTickets()"><option value="">All Stores</option></select>
          </div>
          <div class="fg">
            <label>Type</label>
            <select id="f-type" onchange="renderTickets()"><option value="">All Types</option></select>
          </div>
          <div class="fg">
            <label>Raised By</label>
            <select id="f-raised-by" onchange="renderTickets()"><option value="">All (HEM &amp; Hub Head)</option><option value="HEM">HEM</option><option value="Hub Head">Hub Head</option></select>
          </div>
          <div class="fg">
            <label>Zone</label>
            <select id="f-zone" onchange="renderTickets()"><option value="">All Zones</option></select>
          </div>
          <div class="fg">
            <label>Status</label>
            <select id="f-status" onchange="renderTickets()">
              <option value="">All Statuses</option>
              <option>Open</option>
              <option>In Progress</option>
              <option>Closed</option>
            </select>
          </div>
          <div class="fg">
            <label>Sort by TAT</label>
            <select id="f-tat-sort" onchange="renderTickets()">
              <option value="">No Sort</option>
              <option value="asc">↑ TAT: Low → High</option>
              <option value="desc">↓ TAT: High → Low</option>
            </select>
          </div>
          <div class="fg">
            <label>From Date</label>
            <input type="date" id="f-from" onchange="renderTickets()"/>
          </div>
          <div class="fg">
            <label>To Date</label>
            <input type="date" id="f-to" onchange="renderTickets()"/>
          </div>
          <button class="btn btn-ghost btn-sm" onclick="resetTicketFilters()">✕ Reset</button>
        </div>

        <!-- Dashboard Output -->
        <div id="ticket-dashboard">
          <div class="empty-state">
            <div class="empty-state-icon">🎫</div>
            <h3>No ticket data loaded</h3>
            <p>Upload your Ticket CSV file above to see the analysis</p>
          </div>
        </div>

      </div>

      <!-- ══ TIMELINE PAGE ══ -->
      <div id="page-timeline" class="page">

        <div class="section-head">
          <div class="section-title">📅 Department Completion Timeline <span class="section-chip">Track & Revise</span></div>
        </div>

        <!-- Add / Edit Form -->
        <div class="timeline-form">
          <div class="fg" style="flex:2;min-width:180px">
            <label>Department Name</label>
            <select id="tl-dept" style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px">
              <option value="">-- Select Department --</option>
            </select>
          </div>
          <div class="fg" style="flex:1;min-width:150px">
            <label>Completion Date</label>
            <input type="date" id="tl-date" style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px"/>
          </div>
          <div class="fg" style="flex:2;min-width:180px">
            <label>Note / Reason for Revision</label>
            <input type="text" id="tl-note" placeholder="e.g. Delayed due to resource constraints"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;outline:none"/>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="addTimelineEntry()">+ Set Date</button>
            <button class="btn btn-ghost btn-sm" onclick="clearTimeline()">Clear All</button>
          </div>
        </div>

        <!-- Timeline Table -->
        <div class="timeline-table-wrap">
          <div class="table-scroll">
            <table id="timeline-table">
              <thead>
                <tr>
                  <th>Department</th>
                  <th>Current Completion Date</th>
                  <th>Status</th>
                  <th>Total Revisions</th>
                  <th>Revision History</th>
                  <th>Actions</th>
                </tr>
              </thead>
              <tbody id="timeline-body">
                <tr class="empty-row"><td colspan="6">No timeline entries yet. Use the form above to set department completion dates.</td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <!-- Visual Progress -->
        <div class="section-head"><div class="section-title">📊 Timeline Progress View</div></div>
        <div id="timeline-visual" class="table-card">
          <div style="padding:24px;text-align:center;color:var(--c24-grey-500);font-size:12px">No timeline data yet.</div>
        </div>

      </div>

      <!-- ══ HUB PERFORMANCE PAGE ══ -->
      <div id="page-hub" class="page">

        <!-- Compact upload reminder if no data -->
        <div id="hub-no-data" class="empty-state" style="display:none">
          <div class="empty-state-icon">🏪</div>
          <h3>No ticket data loaded</h3>
          <p>Upload your Ticket CSV from the Ticket Analysis page to see Hub Performance</p>
        </div>

        <!-- Filter Bar -->
        <div class="filter-bar visible" id="hub-filters" style="display:none!important">
        </div>

        <!-- Controls bar — shown when data available -->
        <div id="hub-controls" style="display:none;background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 20px;display:none;gap:14px;align-items:flex-end;flex-wrap:wrap;margin-bottom:20px;box-shadow:var(--shadow-sm)">
          <div class="fg">
            <label>Search Hub</label>
            <input type="text" id="hub-search" placeholder="Type hub name…" oninput="renderHubPerformance()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none;min-width:200px"/>
          </div>
          <div class="fg">
            <label>Zone</label>
            <select id="hub-zone" onchange="renderHubPerformance()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All Zones</option>
            </select>
          </div>
          <div class="fg">
            <label>HEM</label>
            <select id="hub-hem" onchange="renderHubPerformance()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All HEMs</option>
            </select>
          </div>
          <div class="fg">
            <label>Performance</label>
            <select id="hub-perf-filter" onchange="renderHubPerformance()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All</option>
              <option value="best">🟢 Best (TAT ≤ 5d)</option>
              <option value="avg">🟡 Average (TAT 6–15d)</option>
              <option value="poor">🔴 Poor (TAT &gt; 15d)</option>
            </select>
          </div>
          <button class="btn btn-ghost btn-sm" onclick="resetHubFilters()">✕ Reset</button>
          <span style="font-size:11px;color:var(--c24-grey-500);font-weight:600;align-self:center">↕ Click any column header to sort</span>
        </div>

        <!-- KPI Summary Cards -->
        <div id="hub-kpi" style="display:none"></div>

        <!-- Chart -->
        <div id="hub-chart-wrap" style="display:none" class="chart-card" style="margin-bottom:20px">
          <div class="chart-card-title">Top 15 Hubs — Open vs Closed Tickets</div>
          <canvas id="hub-bar-chart" height="200"></canvas>
        </div>

        <!-- Main Table -->
        <div id="hub-table-wrap" style="display:none"></div>

      </div>

      <!-- ══ MYSTERY AUDIT PAGE ══ -->
      <div id="page-mystery" class="page">

        <!-- Upload Row -->
        <div class="upload-panel" style="padding:14px 20px;margin-bottom:16px">
          <div class="upload-group" style="min-width:220px">
            <label class="upload-zone" id="zone-mystery" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:18px">🕵️</span>
              <div class="upload-zone-text">
                <strong id="fname-mystery" style="font-size:11px">Upload Mystery Audit CSV</strong>
                <span>Cars24 Reports file · .csv</span>
              </div>
              <input type="file" id="file-mystery" accept=".csv" onchange="handleMysteryFile(event)"/>
            </label>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="renderMysteryAudit()">⚡ Refresh</button>
          </div>
        </div>

        <!-- Controls -->
        <div id="mystery-controls" style="display:none;background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 20px;gap:14px;align-items:flex-end;flex-wrap:wrap;margin-bottom:20px;box-shadow:var(--shadow-sm)">
          <div class="fg">
            <label>Search Hub</label>
            <input type="text" id="ma-search" placeholder="Type hub name…" oninput="renderMysteryAudit()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none;min-width:190px"/>
          </div>
          <div class="fg">
            <label>City</label>
            <select id="ma-city" onchange="renderMysteryAudit()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All Cities</option>
            </select>
          </div>
          <div class="fg">
            <label>Performance</label>
            <select id="ma-perf" onchange="renderMysteryAudit()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All</option>
              <option value="best">🟢 Best (≥85)</option>
              <option value="avg">🟡 Average (70–84)</option>
              <option value="poor">🔴 Poor (&lt;70)</option>
            </select>
          </div>
          <div class="fg">
            <label>Category Focus</label>
            <select id="ma-cat" onchange="renderMysteryAudit()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">Overall Score</option>
              <option value="Discovery">Discovery</option>
              <option value="Arrival">Arrival</option>
              <option value="Entry">Entry</option>
              <option value="Customer Area">Customer Area</option>
              <option value="Movement Across Hub">Movement Across Hub</option>
              <option value="Yard Viewing">Yard Viewing</option>
              <option value="Staff Interaction & Exit">Staff Interaction &amp; Exit</option>
            </select>
          </div>
          <button class="btn btn-ghost btn-sm" onclick="resetMysteryFilters()">✕ Reset</button>
        </div>

        <!-- Dashboard Output -->
        <div id="mystery-dashboard">
          <div class="empty-state">
            <div class="empty-state-icon">🕵️</div>
            <h3>No Mystery Audit data loaded</h3>
            <p>Upload your Mystery Audit CSV file above to see the full performance report</p>
          </div>
        </div>

      </div>

      <!-- ══ BEAT AUDIT PLAN PAGE ══ -->
      <div id="page-beat" class="page">

        <!-- Upload Row -->
        <div class="upload-panel" style="padding:14px 20px;margin-bottom:16px;flex-wrap:wrap">
          <!-- Beat Plan CSV -->
          <div class="upload-group" style="min-width:210px">
            <span class="upload-label">Beat Audit Plan CSV</span>
            <label class="upload-zone" id="zone-beat" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">📅</span>
              <div class="upload-zone-text">
                <strong id="fname-beat" style="font-size:11px">Upload Beat Plan CSV</strong>
                <span>Monthly schedule file</span>
              </div>
              <input type="file" id="file-beat" accept=".csv" onchange="handleBeatFile(event)"/>
            </label>
          </div>
          <!-- HEM Checklist -->
          <div class="upload-group" style="min-width:190px">
            <span class="upload-label">HEM Checklist CSV</span>
            <label class="upload-zone" id="zone-beat-hem" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">📋</span>
              <div class="upload-zone-text">
                <strong id="fname-beat-hem" style="font-size:11px">HEM_Checklist CSV</strong>
                <span>Full checklist submissions</span>
              </div>
              <input type="file" id="file-beat-hem" accept=".csv" onchange="handleBeatClUpload(event,'hem')"/>
            </label>
          </div>
          <!-- Enso Checklist -->
          <div class="upload-group" style="min-width:190px">
            <span class="upload-label">New HEM Enso CSV</span>
            <label class="upload-zone" id="zone-beat-enso" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">🏪</span>
              <div class="upload-zone-text">
                <strong id="fname-beat-enso" style="font-size:11px">New_HEM_Enso CSV</strong>
                <span>Enso hub checklist</span>
              </div>
              <input type="file" id="file-beat-enso" accept=".csv" onchange="handleBeatClUpload(event,'enso')"/>
            </label>
          </div>
          <!-- Infra Checklist -->
          <div class="upload-group" style="min-width:190px">
            <span class="upload-label">Hub Infra Health CSV</span>
            <label class="upload-zone" id="zone-beat-infra" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">🏗️</span>
              <div class="upload-zone-text">
                <strong id="fname-beat-infra" style="font-size:11px">Hub_Infra_Health CSV</strong>
                <span>Infra health checklist</span>
              </div>
              <input type="file" id="file-beat-infra" accept=".csv" onchange="handleBeatClUpload(event,'infra')"/>
            </label>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="renderBeatPlan()">⚡ Refresh</button>
          </div>
        </div>

        <!-- Controls -->
        <div id="beat-controls" style="display:none;background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 20px;gap:14px;align-items:flex-end;flex-wrap:wrap;margin-bottom:20px;box-shadow:var(--shadow-sm)">
          <div class="fg">
            <label>View</label>
            <select id="beat-view" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="week">Week View</option>
              <option value="month">Month View</option>
              <option value="hem">HEM View</option>
            </select>
          </div>
          <div class="fg">
            <label>HEM Filter</label>
            <select id="beat-hem" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All HEMs</option>
            </select>
          </div>
          <div class="fg">
            <label>Week</label>
            <select id="beat-week" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="all">All Weeks</option>
            </select>
          </div>
          <div class="fg">
            <label>Status</label>
            <select id="beat-status" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All</option>
              <option value="done">✅ Completed</option>
              <option value="missed">🔴 Missed / Pending</option>
            </select>
          </div>
          <div class="fg">
            <label>Sort HEM Name</label>
            <select id="beat-sort-hem" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">Default</option>
              <option value="az">A → Z</option>
              <option value="za">Z → A</option>
            </select>
          </div>
          <div class="fg">
            <label>Sort by Score</label>
            <select id="beat-sort-score" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">Default</option>
              <option value="desc">↓ High → Low</option>
              <option value="asc">↑ Low → High</option>
            </select>
          </div>
          <div class="fg">
            <label>Sort Completion %</label>
            <select id="beat-sort-pct" onchange="renderBeatPlan()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">Default</option>
              <option value="desc">↓ High → Low</option>
              <option value="asc">↑ Low → High</option>
            </select>
          </div>
          <button class="btn btn-ghost btn-sm" onclick="resetBeatFilters()">✕ Reset</button>
        </div>

        <!-- KPI Summary -->
        <div id="beat-kpi"></div>

        <!-- Calendar / Dashboard output -->
        <div id="beat-dashboard">
          <div class="empty-state">
            <div class="empty-state-icon">📅</div>
            <h3>No Beat Audit Plan data loaded</h3>
            <p>Upload the Beat Audit Plan CSV above. Optionally upload Checklist Submissions CSV to mark completed audits.</p>
          </div>
        </div>

      </div>

      <!-- ══ CHECKLIST REPORTS PAGE ══ -->
      <div id="page-clreport" class="page">

        <!-- 3 Upload zones -->
        <div class="upload-panel" style="padding:14px 20px;margin-bottom:16px;flex-wrap:wrap">
          <div class="upload-group" style="min-width:220px">
            <span class="upload-label">HEM Checklist CSV</span>
            <label class="upload-zone" id="zone-clr-hem" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">📋</span>
              <div class="upload-zone-text">
                <strong id="fname-clr-hem" style="font-size:11px">HEM_Checklist CSV</strong>
                <span>Full Checklist submissions</span>
              </div>
              <input type="file" id="file-clr-hem" accept=".csv" onchange="handleClrFile(event,'hem')"/>
            </label>
          </div>
          <div class="upload-group" style="min-width:220px">
            <span class="upload-label">New HEM Enso Checklist CSV</span>
            <label class="upload-zone" id="zone-clr-enso" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">🏪</span>
              <div class="upload-zone-text">
                <strong id="fname-clr-enso" style="font-size:11px">New_HEM_Enso CSV</strong>
                <span>Enso Hub Checklist submissions</span>
              </div>
              <input type="file" id="file-clr-enso" accept=".csv" onchange="handleClrFile(event,'enso')"/>
            </label>
          </div>
          <div class="upload-group" style="min-width:220px">
            <span class="upload-label">Hub Infra Health Checklist CSV</span>
            <label class="upload-zone" id="zone-clr-infra" style="padding:10px 14px">
              <span class="upload-zone-icon" style="font-size:16px">🏗️</span>
              <div class="upload-zone-text">
                <strong id="fname-clr-infra" style="font-size:11px">Hub_Infra_Health CSV</strong>
                <span>Infra Health submissions</span>
              </div>
              <input type="file" id="file-clr-infra" accept=".csv" onchange="handleClrFile(event,'infra')"/>
            </label>
          </div>
          <div class="upload-actions">
            <button class="btn btn-primary" onclick="renderClReport()">⚡ Generate</button>
          </div>
        </div>

        <!-- Tabs -->
        <div style="display:flex;gap:0;border-bottom:1px solid #EBEBEB;background:var(--c24-white);border-radius:var(--radius) var(--radius) 0 0;overflow:hidden;margin-bottom:0">
          <button class="clr-tab active" id="clr-tab-hem"   onclick="switchClrTab('hem')"   style="padding:11px 20px;border:none;background:var(--c24-red);font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:#fff">📋 HEM Checklist</button>
          <button class="clr-tab" id="clr-tab-enso"  onclick="switchClrTab('enso')"  style="padding:11px 20px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500)">🏪 Enso Checklist</button>
          <button class="clr-tab" id="clr-tab-infra" onclick="switchClrTab('infra')" style="padding:11px 20px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500)">🏗️ Infra Health</button>
        </div>

        <!-- Filter bar -->
        <div id="clr-filters" style="background:var(--c24-white);border:1px solid #EBEBEB;border-top:none;border-radius:0 0 var(--radius) var(--radius);padding:12px 20px;display:none;gap:12px;align-items:flex-end;flex-wrap:wrap;margin-bottom:16px">
          <div class="fg">
            <label>HEM Filter</label>
            <select id="clr-hem-filter" onchange="renderClReport()" style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none">
              <option value="">All HEMs</option>
            </select>
          </div>
          <div class="fg">
            <label>Search Hub</label>
            <input type="text" id="clr-hub-search" placeholder="Hub name…" oninput="renderClReport()"
              style="padding:7px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);background:var(--c24-white);outline:none;min-width:160px"/>
          </div>
          <button class="btn btn-ghost btn-sm" onclick="resetClrFilters()">✕ Reset</button>
        </div>

        <div id="clr-dashboard">
          <div class="empty-state">
            <div class="empty-state-icon">📊</div>
            <h3>No Checklist data loaded</h3>
            <p>Upload one or more Checklist CSV files above and click Generate</p>
          </div>
        </div>

      </div>

    </div><!-- /page-content -->
  </div><!-- /main-content -->
<!-- ══ TICKET DETAIL MODAL ══ -->
<div id="ticket-modal" style="display:none;position:fixed;inset:0;z-index:9000;background:rgba(0,0,0,.45);backdrop-filter:blur(3px);align-items:center;justify-content:center;padding:20px">
  <div style="background:var(--c24-white);border-radius:var(--radius);width:100%;max-width:960px;max-height:90vh;display:flex;flex-direction:column;box-shadow:var(--shadow-lg);overflow:hidden">

    <!-- Modal Header -->
    <div style="display:flex;align-items:flex-start;justify-content:space-between;padding:16px 22px 12px;border-bottom:1px solid #EBEBEB;flex-shrink:0;gap:16px;flex-wrap:wrap">
      <div style="flex:1;min-width:200px">
        <div id="modal-title" style="font-size:15px;font-weight:800;color:var(--c24-black);letter-spacing:-.2px"></div>
        <div id="modal-sub" style="font-size:11px;color:var(--c24-grey-500);margin-top:3px;font-weight:500"></div>
      </div>
      <!-- HEM Switcher — lets user jump to any HEM without closing -->
      <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap">
        <div id="modal-hem-wrap" style="display:none;align-items:center;gap:6px">
          <span style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500);white-space:nowrap">Switch HEM:</span>
          <select id="modal-hem-select" onchange="switchModalHem()"
            style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;max-width:180px">
          </select>
          <select id="modal-hem-status" onchange="switchModalHem()"
            style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none">
            <option value="open">Open</option>
            <option value="prog">In Progress</option>
          </select>
        </div>
        <!-- Priority filter -->
        <select id="modal-priority" onchange="filterModalTickets()"
          style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none">
          <option value="">All Priorities</option>
          <option value="Urgent">Urgent</option>
          <option value="High">High</option>
          <option value="Medium">Medium</option>
          <option value="Low">Low</option>
        </select>
        <button onclick="closeTicketModal()" style="background:var(--c24-grey-100);border:none;border-radius:var(--radius-sm);width:30px;height:30px;cursor:pointer;font-size:15px;display:flex;align-items:center;justify-content:center;color:var(--c24-grey-700);flex-shrink:0" onmouseover="this.style.background='#E8E8E8'" onmouseout="this.style.background='var(--c24-grey-100)'">✕</button>
      </div>
    </div>

    <!-- Modal Search -->
    <div style="padding:10px 22px;border-bottom:1px solid #F0F0F0;flex-shrink:0">
      <input id="modal-search" type="text" placeholder="🔍 Search by ID, title or description…" oninput="filterModalTickets()"
        style="width:100%;padding:7px 12px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;color:var(--c24-black);outline:none;background:var(--c24-grey-50)"/>
    </div>

    <!-- Modal Body -->
    <div style="overflow-y:auto;flex:1">
      <table style="width:100%;border-collapse:collapse;font-size:12px">
        <thead style="position:sticky;top:0;z-index:1" id="modal-thead">
          <tr id="modal-header-row">
            <!-- headers injected by JS so sort arrows update live -->
          </tr>
        </thead>
        <tbody id="modal-tbody"></tbody>
      </table>
    </div>

  </div>
</div>

<!-- ══ MYSTERY AUDIT DEEP DIVE MODAL ══ -->
<div id="ma-modal" style="display:none;position:fixed;inset:0;z-index:9100;background:rgba(0,0,0,.5);backdrop-filter:blur(3px);align-items:flex-start;justify-content:center;padding:20px;overflow-y:auto">
  <div style="background:var(--c24-white);border-radius:var(--radius);width:100%;max-width:1100px;margin:0 auto;box-shadow:var(--shadow-lg);overflow:hidden">

    <!-- Modal Header -->
    <div style="background:var(--c24-black);padding:16px 22px;display:flex;align-items:flex-start;justify-content:space-between;gap:16px;flex-wrap:wrap">
      <div>
        <div style="display:flex;align-items:center;gap:8px;margin-bottom:4px">
          <span style="font-size:11px;background:var(--c24-red);color:#fff;padding:2px 8px;border-radius:20px;font-weight:800;letter-spacing:.3px">🕵️ DEEP DIVE</span>
          <span id="ma-modal-perf-badge" style="font-size:11px;padding:2px 8px;border-radius:20px;font-weight:800"></span>
        </div>
        <div id="ma-modal-title" style="font-size:16px;font-weight:800;color:#fff;letter-spacing:-.3px"></div>
        <div id="ma-modal-meta" style="font-size:11px;color:rgba(255,255,255,.55);margin-top:3px;font-weight:500"></div>
      </div>
      <button onclick="closeMaModal()" style="background:rgba(255,255,255,.1);border:none;border-radius:var(--radius-sm);width:32px;height:32px;cursor:pointer;font-size:16px;color:#fff;display:flex;align-items:center;justify-content:center;flex-shrink:0" onmouseover="this.style.background='rgba(255,255,255,.2)'" onmouseout="this.style.background='rgba(255,255,255,.1)'">✕</button>
    </div>

    <!-- Summary Score Bar -->
    <div id="ma-modal-scores" style="background:#1A1A1A;padding:12px 22px;display:flex;gap:8px;flex-wrap:wrap;align-items:center;border-bottom:2px solid var(--c24-red)"></div>

    <!-- Tab Bar -->
    <div style="display:flex;gap:0;border-bottom:1px solid #EBEBEB;background:var(--c24-grey-50);padding:0 22px">
      <button class="ma-tab active" id="ma-tab-summary"   onclick="switchMaTab('summary')"   style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-red);border-bottom:2px solid var(--c24-red);margin-bottom:-1px">📊 Summary</button>
      <button class="ma-tab" id="ma-tab-customer" onclick="switchMaTab('customer')" style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">💬 Customer Feedback</button>
      <button class="ma-tab" id="ma-tab-positive"  onclick="switchMaTab('positive')"  style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">✅ Positive Feedback</button>
      <button class="ma-tab" id="ma-tab-negative"  onclick="switchMaTab('negative')"  style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">⚠️ Issues Found</button>
      <button class="ma-tab" id="ma-tab-responses" onclick="switchMaTab('responses')" style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">📋 All Responses</button>
      <button class="ma-tab" id="ma-tab-evals"     onclick="switchMaTab('evals')"     style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">🗂 All Evaluations</button>
    </div>

    <!-- Tab Content -->
    <div id="ma-modal-body" style="max-height:68vh;overflow-y:auto;padding:20px 22px 28px"></div>

  </div>
</div>

<!-- ══ BEAT AUDIT DEEP DIVE MODAL ══ -->
<div id="beat-dd-modal" style="display:none;position:fixed;inset:0;z-index:9200;background:rgba(0,0,0,.5);backdrop-filter:blur(3px);align-items:flex-start;justify-content:center;padding:20px;overflow-y:auto">
  <div style="background:var(--c24-white);border-radius:var(--radius);width:100%;max-width:1000px;margin:0 auto;box-shadow:var(--shadow-lg);overflow:hidden">

    <!-- Header -->
    <div style="background:var(--c24-black);padding:16px 22px;display:flex;align-items:flex-start;justify-content:space-between;gap:16px;flex-wrap:wrap">
      <div>
        <div style="display:flex;align-items:center;gap:8px;margin-bottom:4px">
          <span style="font-size:11px;background:var(--green);color:#fff;padding:2px 8px;border-radius:20px;font-weight:800">✅ COMPLETED AUDIT</span>
          <span id="bdd-score-badge" style="font-size:11px;padding:2px 8px;border-radius:20px;font-weight:800"></span>
        </div>
        <div id="bdd-title" style="font-size:16px;font-weight:800;color:#fff;letter-spacing:-.3px"></div>
        <div id="bdd-meta" style="font-size:11px;color:rgba(255,255,255,.5);margin-top:3px;font-weight:500"></div>
      </div>
      <button onclick="closeBeatDD()" style="background:rgba(255,255,255,.1);border:none;border-radius:var(--radius-sm);width:32px;height:32px;cursor:pointer;font-size:16px;color:#fff;display:flex;align-items:center;justify-content:center;flex-shrink:0" onmouseover="this.style.background='rgba(255,255,255,.2)'" onmouseout="this.style.background='rgba(255,255,255,.1)'">✕</button>
    </div>

    <!-- Score Summary Strip -->
    <div id="bdd-score-strip" style="background:#1A1A1A;padding:12px 22px;display:flex;align-items:center;gap:16px;flex-wrap:wrap;border-bottom:2px solid var(--green)"></div>

    <!-- Tab Bar -->
    <div style="display:flex;gap:0;border-bottom:1px solid #EBEBEB;background:var(--c24-grey-50);padding:0 22px">
      <button id="bdd-tab-summary" onclick="switchBddTab('summary')" style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-red);border-bottom:2px solid var(--c24-red);margin-bottom:-1px">📊 Summary</button>
      <button id="bdd-tab-low"     onclick="switchBddTab('low')"     style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">⚠️ Low Score Items</button>
      <button id="bdd-tab-all"     onclick="switchBddTab('all')"     style="padding:10px 16px;border:none;background:transparent;font-family:var(--font);font-size:12px;font-weight:700;cursor:pointer;color:var(--c24-grey-500);border-bottom:2px solid transparent;margin-bottom:-1px">📋 All Questions</button>
    </div>

    <!-- Body -->
    <div id="bdd-body" style="max-height:70vh;overflow-y:auto;padding:20px 22px 28px"></div>

  </div>
</div>

</div><!-- /app-shell -->


<script>
/* ══════════════════════════════════════════════════════
   HEM OPS DASHBOARD — CARS24
   Full JavaScript: Data, Render, Charts, Export, Timeline
══════════════════════════════════════════════════════ */

'use strict';

// ─── State ───────────────────────────────────────────
const STATE = {
  tickets:   [],
  checklist: [],
  timeline:  {},   // { deptName: { date, notes: [{date, note, setAt}] } }
  charts:    {}    // chart instances keyed by id
};

const TODAY = (() => { const d = new Date(); d.setHours(0,0,0,0); return d; })();

// ─── Navigation ──────────────────────────────────────
function navigate(page) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
  document.getElementById('page-' + page).classList.add('active');
  document.getElementById('nav-' + page).classList.add('active');

  const titles = {
    tickets:   'Ticket Analysis',
    timeline:  'Department Timeline',
    upload:    'Upload Data Files',
    hub:       'Hub Performance',
    mystery:   'Mystery Audit Report',
    beat:      'Beat Audit Plan',
    clreport:  'Checklist Reports'
  };
  document.getElementById('topbar-title').textContent = titles[page] || page;
  updateTopbarMeta();

  if (page === 'hub')      renderHubPerformance();
  if (page === 'mystery')  renderMysteryAudit();
  if (page === 'beat')     renderBeatPlan();
  if (page === 'clreport') renderClReport();
}

function updateTopbarMeta() {
  const t = STATE.tickets.length;
  const c = STATE.checklist.length;
  let s = '';
  if (t) s += `${t} tickets`;
  if (c) s += (s ? ' · ' : '') + `${c} checklists`;
  document.getElementById('topbar-meta').textContent = s;
}

// ─── Utility ─────────────────────────────────────────
function parseDate(str) {
  if (!str) return null;
  const s = str.replace(/,/g, '').trim();
  const d = new Date(s);
  return isNaN(d.getTime()) ? null : d;
}

function daysBetween(a, b) {
  if (!a || !b) return 0;
  return Math.max(0, Math.floor((b - a) / 86400000));
}

function tatClass(d) {
  if (d <= 1) return 'tat-ok';
  if (d <= 5) return 'tat-mid';
  return 'tat-hi';
}

function parsePct(v) {
  if (typeof v === 'string') return parseFloat(v.replace('%', '')) || 0;
  return parseFloat(v) || 0;
}

function showLoading(msg = 'Processing data…') {
  document.getElementById('loadingText').textContent = msg;
  document.getElementById('loadingOverlay').classList.remove('hidden');
}
function hideLoading() {
  document.getElementById('loadingOverlay').classList.add('hidden');
}

function destroyChart(id) {
  if (STATE.charts[id]) {
    try { STATE.charts[id].destroy(); } catch(e) {}
    delete STATE.charts[id];
  }
}

function makeChart(id, config) {
  destroyChart(id);
  const ctx = document.getElementById(id);
  if (!ctx) return;
  STATE.charts[id] = new Chart(ctx, config);
}

// ─── CSV File Handlers ────────────────────────────────
function handleTicketFile(e) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading('Parsing ticket data…');

  // Update both upload zone labels
  ['fname-tickets', 'fname-tickets-2'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.textContent = file.name;
  });
  ['zone-tickets', 'zone-tickets-2'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.classList.add('loaded');
  });

  Papa.parse(file, {
    header: false,
    skipEmptyLines: true,
    complete: (res) => {
      // Find header row (first row with 'ID' in position 0)
      let hIdx = 0;
      for (let i = 0; i < Math.min(6, res.data.length); i++) {
        if (String(res.data[i][0]).trim() === 'ID') { hIdx = i; break; }
      }
      const headers = res.data[hIdx].map(h => String(h).trim());
      STATE.tickets = res.data.slice(hIdx + 1)
        .map(row => {
          const obj = {};
          headers.forEach((h, i) => { obj[h] = String(row[i] || '').trim(); });
          return obj;
        })
        .filter(r => r.ID && r.Status);

      populateTicketFilters();
      populateTimelineDepts();
      renderTickets();
      updateTopbarMeta();
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing ticket CSV.'); }
  });
}

function handleChecklistFile(e) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading('Parsing checklist data…');

  ['fname-checklist', 'fname-cl-2'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.textContent = file.name;
  });
  ['zone-checklist', 'zone-cl-2'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.classList.add('loaded');
  });

  Papa.parse(file, {
    header: true,
    skipEmptyLines: true,
    complete: (res) => {
      STATE.checklist = res.data.filter(r => r.ID || r['Audit Scoe']);
      populateChecklistFilters();
      renderChecklist();
      updateTopbarMeta();
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing checklist CSV.'); }
  });
}

function generateAll() {
  if (STATE.tickets.length) renderTickets();
  if (STATE.checklist.length) renderChecklist();
  navigate('tickets');
}

// ─── Filters: Populate ────────────────────────────────
function populateTicketFilters() {
  const depts  = [...new Set(STATE.tickets.map(r => r.Department).filter(Boolean))].sort();
  const hems   = [...new Set(STATE.tickets.map(r => r['HEM NAME']).filter(Boolean))].sort();
  const stores = [...new Set(STATE.tickets.map(r => r.Store).filter(Boolean))].sort();
  const types  = [...new Set(STATE.tickets.map(r => r.Type).filter(Boolean))].sort();
  const zones  = [...new Set(STATE.tickets.map(r => r.Zone).filter(Boolean))].sort();

  const dSel = document.getElementById('f-dept');
  const hSel = document.getElementById('f-hem');
  const sSel = document.getElementById('f-store');
  const tSel = document.getElementById('f-type');
  const zSel = document.getElementById('f-zone');
  dSel.innerHTML = '<option value="">All Departments</option>' + depts.map(d => `<option>${d}</option>`).join('');
  hSel.innerHTML = '<option value="">All HEMs</option>' + hems.map(h => `<option>${h}</option>`).join('');
  sSel.innerHTML = '<option value="">All Stores</option>' + stores.map(s => `<option>${s}</option>`).join('');
  tSel.innerHTML = '<option value="">All Types</option>' + types.map(t => `<option>${t}</option>`).join('');
  zSel.innerHTML = '<option value="">All Zones</option>' + zones.map(z => `<option>${z}</option>`).join('');

  document.getElementById('ticket-filters').classList.add('visible');
}

function populateChecklistFilters() {
  const hubs = [...new Set(STATE.checklist.map(r => r.Store || r['Store']).filter(Boolean))].sort();
  const hSel = document.getElementById('f-hub');
  hSel.innerHTML = '<option value="">All Hubs</option>' + hubs.map(h => `<option>${h}</option>`).join('');
}

function populateTimelineDepts() {
  const depts = [...new Set(STATE.tickets.map(r => r.Department).filter(Boolean))].sort();
  const sel = document.getElementById('tl-dept');
  sel.innerHTML = '<option value="">-- Select Department --</option>' + depts.map(d => `<option>${d}</option>`).join('');
}

function resetTicketFilters() {
  ['f-dept','f-hem','f-store','f-type','f-raised-by','f-zone','f-status','f-tat-sort','f-from','f-to'].forEach(id => {
    document.getElementById(id).value = '';
  });
  renderTickets();
}

// ─── Get Filtered Tickets ─────────────────────────────
function getFilteredTickets() {
  const dept     = document.getElementById('f-dept').value;
  const hem      = document.getElementById('f-hem').value;
  const store    = document.getElementById('f-store').value;
  const type     = document.getElementById('f-type').value;
  const raisedBy = document.getElementById('f-raised-by').value;
  const zone     = document.getElementById('f-zone').value;
  const status   = document.getElementById('f-status').value;
  const tatSort  = document.getElementById('f-tat-sort').value;
  const from     = document.getElementById('f-from').value;
  const to       = document.getElementById('f-to').value;

  let result = STATE.tickets.filter(r => {
    if (dept     && r.Department !== dept) return false;
    if (hem      && r['HEM NAME'] !== hem) return false;
    if (store    && r.Store !== store) return false;
    if (type     && r.Type !== type) return false;
    if (raisedBy && r['Raised BY'] !== raisedBy) return false;
    if (zone     && r.Zone !== zone) return false;
    if (status   && r.Status.toLowerCase() !== status.toLowerCase()) return false;
    const cd = parseDate(r['Created At']);
    if (from && cd && cd < new Date(from)) return false;
    if (to   && cd && cd > new Date(to + 'T23:59:59')) return false;
    return true;
  });

  // TAT sort — computed per-row at sort time
  if (tatSort === 'asc') {
    result = result.slice().sort((a, b) => calcTAT(a) - calcTAT(b));
  } else if (tatSort === 'desc') {
    result = result.slice().sort((a, b) => calcTAT(b) - calcTAT(a));
  }

  return result;
}

// ─── TAT Calculator ──────────────────────────────────
function calcTAT(r) {
  const cd = parseDate(r['Created At']);
  if (!cd) return 0;
  const st = r.Status.toLowerCase();
  if (st === 'closed') {
    const ud = parseDate(r['Updated At']);
    return ud ? daysBetween(cd, ud) : daysBetween(cd, new Date());
  }
  return daysBetween(cd, new Date());
}

function avgTAT(arr) {
  if (!arr.length) return '–';
  const sum = arr.reduce((s, r) => s + calcTAT(r), 0);
  return (sum / arr.length).toFixed(1);
}

// ─── TAT Sort Helper ─────────────────────────────────
// Sorts [key, {open:[],prog:[],closed:[]}] entry pairs by avg TAT of open tickets
function tatSortRows(rows, direction) {
  if (!direction) return rows;
  const getAvg = d => {
    if (!d.open.length) return direction === 'asc' ? Infinity : -Infinity;
    return d.open.reduce((s, r) => s + calcTAT(r), 0) / d.open.length;
  };
  return rows.slice().sort((a, b) =>
    direction === 'asc' ? getAvg(a[1]) - getAvg(b[1]) : getAvg(b[1]) - getAvg(a[1])
  );
}

// ─── RENDER: TICKETS ─────────────────────────────────
function renderTickets() {
  if (!STATE.tickets.length) return;

  const data   = getFilteredTickets();
  const now    = new Date();
  const yesterday = new Date(TODAY); yesterday.setDate(yesterday.getDate() - 1);
  const last15    = new Date(TODAY); last15.setDate(last15.getDate() - 15);
  const last3m    = new Date(TODAY); last3m.setMonth(last3m.getMonth() - 3);

  const open   = data.filter(r => r.Status === 'Open');
  const prog   = data.filter(r => r.Status === 'In Progress' || r.Status === 'In-Progress');
  const closed = data.filter(r => r.Status === 'Closed');

  // Time buckets
  const inRange = (r, from, to) => {
    const d = parseDate(r['Created At']);
    return d && d >= from && (!to || d < to);
  };

  const todayOpen  = open.filter(r => inRange(r, TODAY));
  const todayProg  = prog.filter(r => inRange(r, TODAY));
  const yestOpen   = open.filter(r => inRange(r, yesterday, TODAY));
  const yestProg   = prog.filter(r => inRange(r, yesterday, TODAY));
  const l15Open    = data.filter(r => (r.Status==='Open'||r.Status==='In Progress') && inRange(r, last15));
  const l15Closed  = data.filter(r => r.Status==='Closed' && inRange(r, last15));
  const l3mOpen    = data.filter(r => (r.Status==='Open'||r.Status==='In Progress') && inRange(r, last3m));
  const l3mClosed  = data.filter(r => r.Status==='Closed' && inRange(r, last3m));

  // Dept map
  const deptMap = {};
  data.forEach(r => {
    const d = r.Department || 'Unknown';
    if (!deptMap[d]) deptMap[d] = { open:[], prog:[], closed:[], hems: new Set() };
    if (r.Status==='Open') deptMap[d].open.push(r);
    else if (r.Status==='In Progress'||r.Status==='In-Progress') deptMap[d].prog.push(r);
    else if (r.Status==='Closed') deptMap[d].closed.push(r);
    if (r['HEM NAME']) deptMap[d].hems.add(r['HEM NAME']);
  });

  // HEM map
  const hemMap = {};
  data.forEach(r => {
    const h = r['HEM NAME'] || 'Unassigned';
    if (!hemMap[h]) hemMap[h] = { open:[], prog:[], closed:[] };
    if (r.Status==='Open') hemMap[h].open.push(r);
    else if (r.Status==='In Progress'||r.Status==='In-Progress') hemMap[h].prog.push(r);
    else if (r.Status==='Closed') hemMap[h].closed.push(r);
  });

  // Build HTML
  let html = '';

  // ── KPI Overview
  html += `<div class="section-head">
    <div class="section-title">📊 Overview <span class="section-chip">${data.length} total tickets</span></div>
    <div style="font-size:11px;color:var(--c24-grey-500);font-weight:600">
      Filtered view · ${new Date().toLocaleDateString('en-IN', {day:'2-digit',month:'short',year:'numeric'})}
    </div>
  </div>`;

  html += `<div class="kpi-grid">
    <div class="kpi-card red">
      <div class="kpi-label">Open Tickets</div>
      <div class="kpi-value">${open.length}</div>
      <div class="kpi-sub">Avg TAT: ${avgTAT(open)} days</div>
    </div>
    <div class="kpi-card amber">
      <div class="kpi-label">In Progress</div>
      <div class="kpi-value">${prog.length}</div>
      <div class="kpi-sub">Avg TAT: ${avgTAT(prog)} days</div>
    </div>
    <div class="kpi-card green">
      <div class="kpi-label">Closed Tickets</div>
      <div class="kpi-value">${closed.length}</div>
      <div class="kpi-sub">Avg TAT: ${avgTAT(closed)} days</div>
    </div>
    <div class="kpi-card blue">
      <div class="kpi-label">High Priority</div>
      <div class="kpi-value">${open.filter(r=>r.Priority==='High').length}</div>
      <div class="kpi-sub">Open + High Priority</div>
    </div>
    <div class="kpi-card purple">
      <div class="kpi-label">Departments</div>
      <div class="kpi-value">${Object.keys(deptMap).length}</div>
      <div class="kpi-sub">Active departments</div>
    </div>
    <div class="kpi-card orange">
      <div class="kpi-label">Active HEMs</div>
      <div class="kpi-value">${Object.keys(hemMap).filter(h=>h!=='Unassigned').length}</div>
      <div class="kpi-sub">Assigned to tickets</div>
    </div>
  </div>`;

  // ── Time Analysis
  html += `<div class="section-head"><div class="section-title">⏱ Time-Based Analysis</div></div>`;
  html += `<div class="time-grid">
    <div class="time-card">
      <div class="time-card-head">📅 Today</div>
      <div class="time-card-row"><span>Open</span><strong class="time-val-open">${todayOpen.length}</strong></div>
      <div class="time-card-row"><span>In Progress</span><strong class="time-val-prog">${todayProg.length}</strong></div>
    </div>
    <div class="time-card">
      <div class="time-card-head">🕐 Yesterday</div>
      <div class="time-card-row"><span>Open</span><strong class="time-val-open">${yestOpen.length}</strong></div>
      <div class="time-card-row"><span>In Progress</span><strong class="time-val-prog">${yestProg.length}</strong></div>
    </div>
    <div class="time-card">
      <div class="time-card-head">📆 Last 15 Days</div>
      <div class="time-card-row"><span>Open + In Progress</span><strong class="time-val-open">${l15Open.length}</strong></div>
      <div class="time-card-row"><span>Closed</span><strong class="time-val-closed">${l15Closed.length}</strong></div>
    </div>
    <div class="time-card">
      <div class="time-card-head">🗓 Last 3 Months</div>
      <div class="time-card-row"><span>Open + In Progress</span><strong class="time-val-open">${l3mOpen.length}</strong></div>
      <div class="time-card-row"><span>Closed</span><strong class="time-val-closed">${l3mClosed.length}</strong></div>
    </div>
  </div>`;

  // ── Charts
  html += `<div class="chart-grid">
    <div class="chart-card">
      <div class="chart-card-title">Department-wise Ticket Status</div>
      <canvas id="chart-dept"></canvas>
    </div>
    <div class="chart-card">
      <div class="chart-card-title">HEM-wise Open vs In Progress vs Closed</div>
      <canvas id="chart-hem"></canvas>
    </div>
  </div>`;

  // ── Dept Table
  const deptRowsBase = Object.entries(deptMap).sort((a,b)=>(b[1].open.length+b[1].prog.length)-(a[1].open.length+a[1].prog.length));
  // Apply TAT-open sort if selected (reads live select value each render)
  const deptTatSort = (document.getElementById('dept-tat-sort')||{}).value || '';
  const deptRows = tatSortRows(deptRowsBase, deptTatSort);

  html += `<div class="section-head">
    <div class="section-title">🏢 Department-wise Breakdown <span class="section-chip">${deptRows.length} depts</span></div>
    <div style="display:flex;align-items:center;gap:6px">
      <span style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500)">Avg TAT (Open):</span>
      <select id="dept-tat-sort" onchange="renderTickets()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;">
        <option value="" ${deptTatSort===''?'selected':''}>Default</option>
        <option value="asc"  ${deptTatSort==='asc'?'selected':''}>↑ Low → High</option>
        <option value="desc" ${deptTatSort==='desc'?'selected':''}>↓ High → Low</option>
      </select>
    </div>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table>
    <thead><tr>
      <th>Department</th><th>Open</th><th>In Progress</th><th>Closed</th>
      <th>Avg TAT (Open)</th><th>Avg TAT (In Progress)</th><th>HEMs</th>
    </tr></thead>
    <tbody>`;
  if (!deptRows.length) html += `<tr class="empty-row"><td colspan="7">No data</td></tr>`;
  deptRows.forEach(([dept, d]) => {
    const to = avgTAT(d.open), tp = avgTAT(d.prog);
    const deptKey = encodeURIComponent(dept);
    html += `<tr>
      <td><span class="pill pill-dept">${dept}</span></td>
      <td><span class="pill pill-open" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openDeptTicketModal('${deptKey}','open')" title="Click to view open tickets">${d.open.length}</span></td>
      <td><span class="pill pill-prog" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openDeptTicketModal('${deptKey}','prog')" title="Click to view in-progress tickets">${d.prog.length}</span></td>
      <td><span class="pill pill-closed">${d.closed.length}</span></td>
      <td class="tat ${tatClass(parseFloat(to))}">${to}</td>
      <td class="tat ${tatClass(parseFloat(tp))}">${tp}</td>
      <td class="td-muted" style="max-width:180px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">${[...d.hems].join(', ')||'—'}</td>
    </tr>`;
  });
  html += `</tbody></table></div></div>`;

  // ── HEM Table
  const hemRowsBase = Object.entries(hemMap).sort((a,b)=>(b[1].open.length+b[1].prog.length)-(a[1].open.length+a[1].prog.length));

  // Column sort state — persists across re-renders
  if (!STATE.hemSort) STATE.hemSort = { col: 'open', dir: 'desc' };
  const hemSortCol = STATE.hemSort.col;
  const hemSortDir = STATE.hemSort.dir;

  // Apply sort
  const hemFlip = hemSortDir === 'asc' ? 1 : -1;
  const hemRows = hemRowsBase.slice().sort((a, b) => {
    const [,da] = a; const [,db] = b;
    const tatOpenA  = da.open.length  ? da.open.reduce((s,r)=>s+calcTAT(r),0)/da.open.length   : (hemSortDir==='asc'?Infinity:-Infinity);
    const tatOpenB  = db.open.length  ? db.open.reduce((s,r)=>s+calcTAT(r),0)/db.open.length   : (hemSortDir==='asc'?Infinity:-Infinity);
    const tatProgA  = da.prog.length  ? da.prog.reduce((s,r)=>s+calcTAT(r),0)/da.prog.length   : (hemSortDir==='asc'?Infinity:-Infinity);
    const tatProgB  = db.prog.length  ? db.prog.reduce((s,r)=>s+calcTAT(r),0)/db.prog.length   : (hemSortDir==='asc'?Infinity:-Infinity);
    switch(hemSortCol) {
      case 'name':    return hemFlip * a[0].localeCompare(b[0]);
      case 'open':    return hemFlip * (da.open.length   - db.open.length);
      case 'prog':    return hemFlip * (da.prog.length   - db.prog.length);
      case 'closed':  return hemFlip * (da.closed.length - db.closed.length);
      case 'tatOpen': return hemFlip * (tatOpenA - tatOpenB);
      case 'tatProg': return hemFlip * (tatProgA - tatProgB);
      default:        return hemFlip * (da.open.length   - db.open.length);
    }
  });

  // Helper: sortable <th> for HEM table
  const hemTh = (label, col) => {
    const active = hemSortCol === col;
    const arrow  = active ? (hemSortDir === 'asc' ? ' ↑' : ' ↓') : ' ↕';
    const color  = active ? 'color:var(--c24-red);' : 'color:var(--c24-grey-500);';
    return `<th onclick="hemSortBy('${col}')" style="padding:10px 14px;text-align:left;font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;cursor:pointer;user-select:none;white-space:nowrap;${color}">${label}<span style="font-size:9px;margin-left:2px">${arrow}</span></th>`;
  };

  html += `<div class="section-head">
    <div class="section-title">👤 HEM-wise Analysis <span class="section-chip">${hemRows.length} HEMs</span></div>
    <span style="font-size:11px;color:var(--c24-grey-500);font-weight:600">↕ Click any column header to sort</span>
  </div>`;

  // ── TAT Warning Banner — HEMs with Avg TAT (Open) > 7 days
  const TAT_WARN_THRESHOLD = 7;
  const warnHems = hemRows.filter(([, d]) => {
    if (!d.open.length) return false;
    const avg = d.open.reduce((s, r) => s + calcTAT(r), 0) / d.open.length;
    return avg > TAT_WARN_THRESHOLD;
  });

  if (warnHems.length) {
    html += `<div style="
      background:#FFF1F1;
      border:1.5px solid #FECACA;
      border-left:4px solid var(--c24-red);
      border-radius:var(--radius);
      padding:14px 18px;
      margin-bottom:14px;
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:16px;
      flex-wrap:wrap;
    ">
      <div style="flex:1">
        <div style="font-size:13px;font-weight:800;color:var(--c24-red);margin-bottom:4px;display:flex;align-items:center;gap:6px">
          ⚠️ TAT Warning — HEMs exceeding ${TAT_WARN_THRESHOLD}-day Open TAT threshold
        </div>
        <div style="font-size:11px;color:#9B1C1C;margin-bottom:10px;font-weight:500">
          The following HEMs have open tickets with average TAT above ${TAT_WARN_THRESHOLD} days. Immediate attention required.
        </div>
        <div style="display:flex;gap:8px;flex-wrap:wrap">
          ${warnHems.map(([hem, d]) => {
            const avg = (d.open.reduce((s, r) => s + calcTAT(r), 0) / d.open.length).toFixed(1);
            const key = encodeURIComponent(hem);
            return `<div style="
              background:#fff;
              border:1px solid #FECACA;
              border-radius:var(--radius-sm);
              padding:8px 12px;
              min-width:160px;
              cursor:pointer;
            " onclick="openHemTicketModal('${key}','open')" title="Click to view open tickets">
              <div style="font-size:12px;font-weight:800;color:var(--c24-black);margin-bottom:2px">${hem}</div>
              <div style="display:flex;align-items:center;gap:6px;flex-wrap:wrap">
                <span style="font-size:18px;font-weight:900;color:var(--c24-red)">${avg}</span>
                <span style="font-size:10px;color:#9B1C1C;font-weight:600">days avg TAT</span>
                <span style="font-size:10px;background:var(--c24-red-light);color:var(--c24-red);padding:1px 6px;border-radius:10px;font-weight:700">${d.open.length} open</span>
              </div>
            </div>`;
          }).join('')}
        </div>
      </div>
      <div style="font-size:22px;font-weight:900;color:var(--c24-red);white-space:nowrap;text-align:right;flex-shrink:0">
        ${warnHems.length} <span style="font-size:11px;font-weight:700;display:block;color:#9B1C1C">HEM${warnHems.length > 1 ? 's' : ''} at risk</span>
      </div>
    </div>`;
  }

  html += `<div class="table-card"><div class="table-scroll"><table>
    <thead><tr>
      ${hemTh('HEM Name','name')}
      ${hemTh('Open','open')}
      ${hemTh('In Progress','prog')}
      ${hemTh('Closed','closed')}
      ${hemTh('Avg TAT (Open)','tatOpen')}
      ${hemTh('Avg TAT (In Progress)','tatProg')}
    </tr></thead>
    <tbody>`;
  if (!hemRows.length) html += `<tr class="empty-row"><td colspan="6">No data</td></tr>`;
  hemRows.forEach(([hem, d]) => {
    const to = avgTAT(d.open), tp = avgTAT(d.prog);
    const openKey = encodeURIComponent(hem);
    // Row warning: highlight if avg TAT (open) > threshold
    const avgTATOpen = d.open.length ? d.open.reduce((s, r) => s + calcTAT(r), 0) / d.open.length : 0;
    const isWarning  = d.open.length > 0 && avgTATOpen > TAT_WARN_THRESHOLD;
    const rowBg      = isWarning ? 'background:#FFF8F8;' : '';
    const rowBorder  = isWarning ? 'border-left:3px solid var(--c24-red);' : '';
    const warnIcon   = isWarning ? `<span style="color:var(--c24-red);font-size:12px;margin-left:4px" title="Avg TAT exceeds ${TAT_WARN_THRESHOLD} days">⚠️</span>` : '';
    html += `<tr style="${rowBg}${rowBorder}">
      <td style="${rowBorder}"><strong class="td-bold">${hem}</strong>${warnIcon}</td>
      <td><span class="pill pill-open" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openHemTicketModal('${openKey}','open')" title="Click to view open tickets">${d.open.length}</span></td>
      <td><span class="pill pill-prog" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openHemTicketModal('${openKey}','prog')" title="Click to view in-progress tickets">${d.prog.length}</span></td>
      <td><span class="pill pill-closed">${d.closed.length}</span></td>
      <td class="tat ${tatClass(parseFloat(to))}">${to}${isWarning ? ` <span style="font-size:9px;background:var(--c24-red);color:#fff;padding:1px 5px;border-radius:8px;font-weight:700;margin-left:3px">⚠ HIGH</span>` : ''}</td>
      <td class="tat ${tatClass(parseFloat(tp))}">${tp}</td>
    </tr>`;
  });
  html += `</tbody></table></div></div>`;

  // ── Full Ticket List
  const allTicketsTatSort = (document.getElementById('all-tickets-tat-sort')||{}).value || '';
  const allTicketsData = allTicketsTatSort
    ? data.slice().sort((a, b) => allTicketsTatSort === 'asc' ? calcTAT(a) - calcTAT(b) : calcTAT(b) - calcTAT(a))
    : data;

  html += `<div class="section-head">
    <div class="section-title">📋 All Tickets <span class="section-chip">${data.length} records</span></div>
    <div style="display:flex;align-items:center;gap:6px">
      <span style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500)">TAT (Days):</span>
      <select id="all-tickets-tat-sort" onchange="renderTickets()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;">
        <option value=""   ${allTicketsTatSort===''?'selected':''}>Default</option>
        <option value="asc"  ${allTicketsTatSort==='asc'?'selected':''}>↑ Low → High</option>
        <option value="desc" ${allTicketsTatSort==='desc'?'selected':''}>↓ High → Low</option>
      </select>
      ${data.length > 500 ? `<span style="font-size:11px;color:var(--c24-grey-500)">Showing first 500</span>` : ''}
    </div>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table>
    <thead><tr>
      <th>ID</th><th>Title</th><th>Status</th><th>Priority</th>
      <th>Department</th><th>Store</th><th>HEM</th><th>Created</th><th>TAT (days)</th>
    </tr></thead>
    <tbody>`;
  if (!allTicketsData.length) html += `<tr class="empty-row"><td colspan="9">No tickets match current filters</td></tr>`;
  allTicketsData.slice(0, 500).forEach(r => {
    const t = calcTAT(r);
    const stPill = r.Status === 'Open' ? 'pill-open' : (r.Status === 'Closed' ? 'pill-closed' : 'pill-prog');
    html += `<tr>
      <td class="td-id">#${r.ID}</td>
      <td style="max-width:200px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;font-weight:600" title="${(r.Title||'').replace(/"/g,'')}">${r.Title||'—'}</td>
      <td><span class="pill ${stPill}">${r.Status}</span></td>
      <td class="td-muted">${r.Priority||'—'}</td>
      <td><span class="pill pill-dept" style="font-size:9px">${r.Department||'—'}</span></td>
      <td class="td-muted" style="max-width:140px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">${r.Store||'—'}</td>
      <td class="td-muted">${r['HEM NAME']||'—'}</td>
      <td class="td-muted">${r['Created At']||'—'}</td>
      <td class="tat ${tatClass(t)}">${t}</td>
    </tr>`;
  });
  html += `</tbody></table></div></div>`;

  document.getElementById('ticket-dashboard').innerHTML = html;

  // ── Render Charts (after DOM update)
  setTimeout(() => {
    // Dept chart
    const topDepts = deptRows.slice(0, 12);
    makeChart('chart-dept', {
      type: 'bar',
      data: {
        labels: topDepts.map(([d]) => d),
        datasets: [
          { label: 'Open',        data: topDepts.map(([,d])=>d.open.length),   backgroundColor: '#E5252966', borderColor: '#E52529', borderWidth: 1.5, borderRadius: 4 },
          { label: 'In Progress', data: topDepts.map(([,d])=>d.prog.length),   backgroundColor: '#D9770666', borderColor: '#D97706', borderWidth: 1.5, borderRadius: 4 },
          { label: 'Closed',      data: topDepts.map(([,d])=>d.closed.length), backgroundColor: '#16A34A66', borderColor: '#16A34A', borderWidth: 1.5, borderRadius: 4 }
        ]
      },
      options: {
        responsive: true,
        plugins: { legend: { position: 'top', labels: { font: { family: 'Gilroy', weight: '700', size: 11 } } } },
        scales: {
          x: { ticks: { font: { family: 'Gilroy', size: 10 }, maxRotation: 45 } },
          y: { beginAtZero: true, ticks: { stepSize: 1, font: { family: 'Gilroy', size: 10 } } }
        }
      }
    });

    // HEM chart
    const topHems = hemRows.filter(([h]) => h !== 'Unassigned').slice(0, 14);
    makeChart('chart-hem', {
      type: 'bar',
      data: {
        labels: topHems.map(([h]) => h),
        datasets: [
          { label: 'Open',        data: topHems.map(([,d])=>d.open.length),   backgroundColor: '#E5252966', borderColor: '#E52529', borderWidth: 1.5, borderRadius: 4 },
          { label: 'In Progress', data: topHems.map(([,d])=>d.prog.length),   backgroundColor: '#D9770666', borderColor: '#D97706', borderWidth: 1.5, borderRadius: 4 },
          { label: 'Closed',      data: topHems.map(([,d])=>d.closed.length), backgroundColor: '#16A34A66', borderColor: '#16A34A', borderWidth: 1.5, borderRadius: 4 }
        ]
      },
      options: {
        responsive: true,
        plugins: { legend: { position: 'top', labels: { font: { family: 'Gilroy', weight: '700', size: 11 } } } },
        scales: {
          x: { ticks: { font: { family: 'Gilroy', size: 10 }, maxRotation: 45 } },
          y: { beginAtZero: true, ticks: { stepSize: 1, font: { family: 'Gilroy', size: 10 } } }
        }
      }
    });
  }, 50);
}

// ─── RENDER: CHECKLIST ────────────────────────────────
function renderChecklist() {
  if (!STATE.checklist.length) return;

  const fb  = document.getElementById('f-filledby').value;
  const hub = document.getElementById('f-hub').value;
  const data = STATE.checklist.filter(r => {
    if (fb  && r['Filled By'] !== fb) return false;
    if (hub && (r.Store || '') !== hub) return false;
    return true;
  });

  const hem    = data.filter(r => r['Filled By'] === 'HEM');
  const nonHem = data.filter(r => r['Filled By'] === 'Non HEM');

  const avgScore = arr => {
    const v = arr.map(r => parsePct(r['Audit Scoe'])).filter(x => x > 0);
    return v.length ? (v.reduce((s,x)=>s+x,0)/v.length).toFixed(1) : '–';
  };

  const hemAvg    = avgScore(hem);
  const nonHemAvg = avgScore(nonHem);

  // Hub map
  const hubMap = {};
  data.forEach(r => {
    const store = r.Store || 'Unknown';
    if (!hubMap[store]) hubMap[store] = { hem: [], nonHem: [] };
    const s = parsePct(r['Audit Scoe']);
    if (r['Filled By'] === 'HEM') hubMap[store].hem.push(s);
    else if (r['Filled By'] === 'Non HEM') hubMap[store].nonHem.push(s);
  });

  let html = '';

  // Overview cards
  html += `<div class="section-head">
    <div class="section-title">✅ Checklist Overview <span class="section-chip">${data.length} submissions</span></div>
  </div>`;

  html += `<div class="vs-grid">
    <div class="vs-card">
      <div class="vs-label">🔴 HEM Average Score</div>
      <div class="vs-score hem">${hemAvg !== '–' ? hemAvg + '%' : '—'}</div>
      <div class="vs-sub">${hem.length} HEM submissions</div>
    </div>
    <div class="vs-card">
      <div class="vs-label">🟣 Non-HEM Average Score</div>
      <div class="vs-score nonhem">${nonHemAvg !== '–' ? nonHemAvg + '%' : '—'}</div>
      <div class="vs-sub">${nonHem.length} Non-HEM submissions</div>
    </div>
  </div>`;

  html += `<div class="kpi-grid">
    <div class="kpi-card red">
      <div class="kpi-label">HEM Submissions</div>
      <div class="kpi-value">${hem.length}</div>
      <div class="kpi-sub">Filled by HEM</div>
    </div>
    <div class="kpi-card purple">
      <div class="kpi-label">Non-HEM Submissions</div>
      <div class="kpi-value">${nonHem.length}</div>
      <div class="kpi-sub">Filled by Non-HEM</div>
    </div>
    <div class="kpi-card green">
      <div class="kpi-label">HEM Avg Score</div>
      <div class="kpi-value" style="font-size:22px">${hemAvg !== '–' ? hemAvg+'%' : '—'}</div>
      <div class="kpi-sub">Audit score</div>
    </div>
    <div class="kpi-card amber">
      <div class="kpi-label">Non-HEM Avg Score</div>
      <div class="kpi-value" style="font-size:22px">${nonHemAvg !== '–' ? nonHemAvg+'%' : '—'}</div>
      <div class="kpi-sub">Audit score</div>
    </div>
    <div class="kpi-card blue">
      <div class="kpi-label">Total Hubs</div>
      <div class="kpi-value">${Object.keys(hubMap).length}</div>
      <div class="kpi-sub">Unique hubs</div>
    </div>
  </div>`;

  // Charts
  html += `<div class="chart-grid">
    <div class="chart-card">
      <div class="chart-card-title">HEM vs Non-HEM Score by Hub (Top 15 dual-reported)</div>
      <canvas id="chart-cl-hub"></canvas>
    </div>
    <div class="chart-card">
      <div class="chart-card-title">Score Distribution</div>
      <canvas id="chart-cl-dist"></canvas>
    </div>
  </div>`;

  // Hub table
  const hubRowsBase = Object.entries(hubMap).sort((a,b) => {
    const aH = a[1].hem.length ? a[1].hem.reduce((s,v)=>s+v,0)/a[1].hem.length : 0;
    const bH = b[1].hem.length ? b[1].hem.reduce((s,v)=>s+v,0)/b[1].hem.length : 0;
    return bH - aH;
  });

  // Read hub filter controls (rendered into DOM on previous pass, safe with ||{})
  const hubNameFilter  = (document.getElementById('cl-hub-name')||{}).value  || '';
  const hubHemSort     = (document.getElementById('cl-hem-sort')||{}).value   || '';
  const hubNonHemSort  = (document.getElementById('cl-nonhem-sort')||{}).value|| '';

  // Apply hub name filter
  let hubRows = hubNameFilter
    ? hubRowsBase.filter(([h]) => h.toLowerCase().includes(hubNameFilter.toLowerCase()))
    : hubRowsBase;

  // Apply HEM score sort (takes priority over Non-HEM if both set)
  if (hubHemSort) {
    const avg = d => d.hem.length ? d.hem.reduce((s,v)=>s+v,0)/d.hem.length : (hubHemSort==='asc'?Infinity:-Infinity);
    hubRows = hubRows.slice().sort((a,b) => hubHemSort==='asc' ? avg(a[1])-avg(b[1]) : avg(b[1])-avg(a[1]));
  } else if (hubNonHemSort) {
    const avg = d => d.nonHem.length ? d.nonHem.reduce((s,v)=>s+v,0)/d.nonHem.length : (hubNonHemSort==='asc'?Infinity:-Infinity);
    hubRows = hubRows.slice().sort((a,b) => hubNonHemSort==='asc' ? avg(a[1])-avg(b[1]) : avg(b[1])-avg(a[1]));
  }

  html += `<div class="section-head">
    <div class="section-title">🏢 Hub-wise Score Comparison</div>
    <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap">
      <input id="cl-hub-name" type="text" placeholder="🔍 Search hub…" value="${hubNameFilter.replace(/"/g,'&quot;')}"
        oninput="renderChecklist()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:500;color:var(--c24-black);background:var(--c24-white);outline:none;width:160px"/>
      <select id="cl-hem-sort" onchange="renderChecklist()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;">
        <option value=""   ${hubHemSort===''   ?'selected':''}>HEM Score: Default</option>
        <option value="desc" ${hubHemSort==='desc'?'selected':''}>HEM ↓ High → Low</option>
        <option value="asc"  ${hubHemSort==='asc' ?'selected':''}>HEM ↑ Low → High</option>
      </select>
      <select id="cl-nonhem-sort" onchange="renderChecklist()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;">
        <option value=""   ${hubNonHemSort===''   ?'selected':''}>Non-HEM Score: Default</option>
        <option value="desc" ${hubNonHemSort==='desc'?'selected':''}>Non-HEM ↓ High → Low</option>
        <option value="asc"  ${hubNonHemSort==='asc' ?'selected':''}>Non-HEM ↑ Low → High</option>
      </select>
    </div>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table>
    <thead><tr>
      <th>Hub / Store</th><th>HEM Submissions</th><th>HEM Avg Score</th>
      <th>Non-HEM Submissions</th><th>Non-HEM Avg Score</th><th>Difference</th>
    </tr></thead>
    <tbody>`;
  if (!hubRows.length) html += `<tr class="empty-row"><td colspan="6">No data</td></tr>`;
  hubRows.forEach(([hub, d]) => {
    const hA = d.hem.length    ? (d.hem.reduce((s,v)=>s+v,0)/d.hem.length).toFixed(1)       : null;
    const nA = d.nonHem.length ? (d.nonHem.reduce((s,v)=>s+v,0)/d.nonHem.length).toFixed(1) : null;
    const diff = (hA && nA) ? (parseFloat(hA) - parseFloat(nA)).toFixed(1) : null;
    const diffColor = diff ? (parseFloat(diff) >= 0 ? 'var(--green)' : 'var(--c24-red)') : 'var(--c24-grey-500)';
    html += `<tr>
      <td style="font-size:11px;font-weight:600">${hub}</td>
      <td class="td-muted">${d.hem.length}</td>
      <td>${hA ? `<div class="score-wrap"><strong>${hA}%</strong><div class="score-bar"><div class="score-fill fill-red" style="width:${Math.min(hA,100)}%"></div></div></div>` : '—'}</td>
      <td class="td-muted">${d.nonHem.length}</td>
      <td>${nA ? `<div class="score-wrap"><strong>${nA}%</strong><div class="score-bar"><div class="score-fill fill-purple" style="width:${Math.min(nA,100)}%"></div></div></div>` : '—'}</td>
      <td style="font-weight:800;color:${diffColor}">${diff !== null ? (parseFloat(diff)>=0?'+':'')+diff+'%' : '—'}</td>
    </tr>`;
  });
  html += `</tbody></table></div></div>`;

  // Full submission list
  const subScoreSort = (document.getElementById('cl-sub-score-sort')||{}).value || '';
  const subData = subScoreSort
    ? data.slice().sort((a,b) => subScoreSort==='asc'
        ? parsePct(a['Audit Scoe']) - parsePct(b['Audit Scoe'])
        : parsePct(b['Audit Scoe']) - parsePct(a['Audit Scoe']))
    : data;

  html += `<div class="section-head">
    <div class="section-title">📋 All Submissions <span class="section-chip">${data.length}</span></div>
    <div style="display:flex;align-items:center;gap:6px">
      <span style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500)">Score:</span>
      <select id="cl-sub-score-sort" onchange="renderChecklist()"
        style="padding:5px 10px;border:1px solid #E0E0E0;border-radius:var(--radius-sm);font-family:var(--font);font-size:12px;font-weight:600;color:var(--c24-black);background:var(--c24-white);cursor:pointer;outline:none;">
        <option value=""    ${subScoreSort===''    ?'selected':''}>Default</option>
        <option value="desc"  ${subScoreSort==='desc' ?'selected':''}>↓ High → Low</option>
        <option value="asc"   ${subScoreSort==='asc'  ?'selected':''}>↑ Low → High</option>
      </select>
    </div>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table>
    <thead><tr><th>ID</th><th>Store</th><th>Employee</th><th>Score</th><th>Filled By</th><th>Started</th><th>Completed</th></tr></thead>
    <tbody>`;
  if (!subData.length) html += `<tr class="empty-row"><td colspan="7">No data</td></tr>`;
  subData.slice(0,300).forEach(r => {
    const s = parsePct(r['Audit Scoe']);
    const sc = s >= 75 ? 'var(--green)' : s >= 60 ? 'var(--amber)' : 'var(--c24-red)';
    const fbPill = r['Filled By']==='HEM' ? 'pill-closed' : 'pill-open';
    html += `<tr>
      <td class="td-id">#${r.ID}</td>
      <td style="font-size:11px">${r.Store||'—'}</td>
      <td style="font-weight:600">${r.Employee||'—'}</td>
      <td style="font-weight:800;color:${sc}">${r['Audit Scoe']||'—'}</td>
      <td><span class="pill ${fbPill}">${r['Filled By']||'—'}</span></td>
      <td class="td-muted">${r['Starting At']||'—'}</td>
      <td class="td-muted">${r['Completed At']||'—'}</td>
    </tr>`;
  });
  if (subData.length > 300) html += `<tr class="empty-row"><td colspan="7">Showing 300 of ${subData.length} records</td></tr>`;
  html += `</tbody></table></div></div>`;

  document.getElementById('checklist-dashboard').innerHTML = html;

  // Charts
  setTimeout(() => {
    // Dual-hub chart
    const dual = hubRows.filter(([,d])=>d.hem.length>0&&d.nonHem.length>0).slice(0,15);
    const chartSrc = dual.length > 0 ? dual : hubRows.slice(0,15);
    const lbls   = chartSrc.map(([h])=>h.replace(/CARS24 Hub, |Cars24 Hub, /gi,''));
    const hemV   = chartSrc.map(([,d])=>d.hem.length?(d.hem.reduce((s,v)=>s+v,0)/d.hem.length).toFixed(1):null);
    const nonHV  = chartSrc.map(([,d])=>d.nonHem.length?(d.nonHem.reduce((s,v)=>s+v,0)/d.nonHem.length).toFixed(1):null);

    makeChart('chart-cl-hub', {
      type: 'bar',
      data: {
        labels: lbls,
        datasets: [
          { label: 'HEM Score',     data: hemV,  backgroundColor: '#E5252966', borderColor: '#E52529', borderWidth:1.5, borderRadius:4 },
          { label: 'Non-HEM Score', data: nonHV, backgroundColor: '#7C3AED66', borderColor: '#7C3AED', borderWidth:1.5, borderRadius:4 }
        ]
      },
      options: {
        responsive:true,
        plugins: { legend:{ position:'top', labels:{ font:{ family:'Gilroy', weight:'700', size:11 } } } },
        scales: {
          x: { ticks:{ font:{ family:'Gilroy', size:9 }, maxRotation:50 } },
          y: { beginAtZero:true, max:100, ticks:{ font:{ family:'Gilroy', size:10 }, callback: v=>v+'%' } }
        }
      }
    });

    // Score distribution
    const buckets = {'< 50':0,'50–59':0,'60–69':0,'70–79':0,'80–89':0,'90+':0};
    data.forEach(r => {
      const s = parsePct(r['Audit Scoe']);
      if (s<50) buckets['< 50']++;
      else if (s<60) buckets['50–59']++;
      else if (s<70) buckets['60–69']++;
      else if (s<80) buckets['70–79']++;
      else if (s<90) buckets['80–89']++;
      else buckets['90+']++;
    });
    makeChart('chart-cl-dist', {
      type: 'doughnut',
      data: {
        labels: Object.keys(buckets),
        datasets: [{ data: Object.values(buckets), backgroundColor:['#E52529','#EA580C','#D97706','#2563EB','#16A34A','#7C3AED'], borderWidth:2 }]
      },
      options: {
        responsive:true,
        plugins:{ legend:{ position:'right', labels:{ font:{ family:'Gilroy', weight:'700', size:11 } } } }
      }
    });
  }, 50);
}

// ─── TIMELINE FEATURE ─────────────────────────────────
function addTimelineEntry() {
  const dept = document.getElementById('tl-dept').value;
  const date = document.getElementById('tl-date').value;
  const note = document.getElementById('tl-note').value.trim();

  if (!dept) { alert('Please select a department.'); return; }
  if (!date) { alert('Please select a completion date.'); return; }

  const existing = STATE.timeline[dept];
  if (existing) {
    // Revision
    existing.history.push({ date: existing.date, note: existing.note || '(initial)', setAt: existing.setAt });
    existing.date  = date;
    existing.note  = note || 'Revised';
    existing.setAt = new Date().toISOString();
  } else {
    STATE.timeline[dept] = {
      date,
      note: note || 'Initial entry',
      setAt: new Date().toISOString(),
      history: []
    };
  }

  // Reset form
  document.getElementById('tl-dept').value = '';
  document.getElementById('tl-date').value = '';
  document.getElementById('tl-note').value = '';

  renderTimeline();
}

function deleteTimelineEntry(dept) {
  if (!confirm(`Remove timeline entry for "${dept}"?`)) return;
  delete STATE.timeline[dept];
  renderTimeline();
}

function clearTimeline() {
  if (!Object.keys(STATE.timeline).length) return;
  if (!confirm('Clear all timeline entries?')) return;
  STATE.timeline = {};
  renderTimeline();
}

function renderTimeline() {
  const entries = Object.entries(STATE.timeline);
  const tbody   = document.getElementById('timeline-body');

  if (!entries.length) {
    tbody.innerHTML = `<tr class="empty-row"><td colspan="6">No timeline entries yet. Use the form above to set department completion dates.</td></tr>`;
    document.getElementById('timeline-visual').innerHTML = '<div style="padding:24px;text-align:center;color:var(--c24-grey-500);font-size:12px">No timeline data yet.</div>';
    return;
  }

  const now = new Date();
  tbody.innerHTML = entries.map(([dept, e]) => {
    const dDate  = new Date(e.date);
    const isPast = dDate < now;
    const dDiff  = Math.abs(daysBetween(now, dDate));
    const status = isPast ? `<span class="pill pill-closed">✓ Completed</span>` : `<span class="pill pill-prog">⏳ ${dDiff}d remaining</span>`;
    const revHist = e.history.length
      ? `<div class="revision-history">${e.history.map((h,i) => `<span class="revision-item">Rev ${i+1}: ${h.date} — ${h.note}</span>`).join('<br>')}</div>`
      : '<span style="color:var(--c24-grey-300);font-size:11px">No revisions</span>';

    return `<tr>
      <td><strong>${dept}</strong></td>
      <td style="font-weight:700">${new Date(e.date).toLocaleDateString('en-IN',{day:'2-digit',month:'short',year:'numeric'})}</td>
      <td>${status}</td>
      <td style="text-align:center;font-weight:800">${e.history.length}</td>
      <td>${revHist}</td>
      <td>
        <button class="btn btn-ghost btn-sm" onclick="prefillTimeline('${dept}')">✏ Revise</button>
        <button class="btn btn-danger btn-sm" onclick="deleteTimelineEntry('${dept}')">✕</button>
      </td>
    </tr>`;
  }).join('');

  // Visual timeline
  const sorted = [...entries].sort((a,b) => new Date(a[1].date) - new Date(b[1].date));
  const minD = new Date(sorted[0][1].date);
  const maxD = new Date(sorted[sorted.length-1][1].date);
  const range = Math.max(daysBetween(minD, maxD), 1);

  let visual = `<div style="padding:20px 24px">`;
  sorted.forEach(([dept, e]) => {
    const d    = new Date(e.date);
    const pct  = Math.min(100, Math.round(daysBetween(minD, d) / range * 100));
    const past = d < now;
    const col  = past ? '#16A34A' : '#E52529';
    visual += `
      <div style="margin-bottom:14px">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:4px">
          <span style="font-size:12px;font-weight:700">${dept}</span>
          <span style="font-size:11px;font-weight:600;color:${col}">${d.toLocaleDateString('en-IN',{day:'2-digit',month:'short',year:'numeric'})}</span>
        </div>
        <div style="height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden">
          <div style="height:100%;width:${pct}%;background:${col};border-radius:3px;transition:width .4s"></div>
        </div>
        <div style="font-size:10px;color:var(--c24-grey-500);margin-top:3px">${e.note || ''} · Revisions: ${e.history.length}</div>
      </div>`;
  });
  visual += `</div>`;
  document.getElementById('timeline-visual').innerHTML = visual;
}

function prefillTimeline(dept) {
  document.getElementById('tl-dept').value = dept;
  document.getElementById('tl-date').value = STATE.timeline[dept]?.date || '';
  document.getElementById('tl-note').value = '';
  document.getElementById('tl-dept').scrollIntoView({ behavior:'smooth', block:'center' });
}

// ─── HUB PERFORMANCE ─────────────────────────────────
function renderHubPerformance() {
  const noData   = document.getElementById('hub-no-data');
  const controls = document.getElementById('hub-controls');
  const kpiWrap  = document.getElementById('hub-kpi');
  const chartWrap= document.getElementById('hub-chart-wrap');
  const tableWrap= document.getElementById('hub-table-wrap');

  if (!STATE.tickets.length) {
    noData.style.display    = 'block';
    controls.style.display  = 'none';
    kpiWrap.style.display   = 'none';
    chartWrap.style.display = 'none';
    tableWrap.style.display = 'none';
    return;
  }

  noData.style.display    = 'none';
  controls.style.display  = 'flex';
  kpiWrap.style.display   = 'block';
  chartWrap.style.display = 'block';
  tableWrap.style.display = 'block';

  // Populate zone & HEM dropdowns once (if empty)
  const zoneSel = document.getElementById('hub-zone');
  const hemSel  = document.getElementById('hub-hem');
  if (zoneSel.options.length <= 1) {
    const zones = [...new Set(STATE.tickets.map(r => r.Zone).filter(Boolean))].sort();
    zoneSel.innerHTML = '<option value="">All Zones</option>' + zones.map(z => `<option>${z}</option>`).join('');
  }
  if (hemSel.options.length <= 1) {
    const hems = [...new Set(STATE.tickets.map(r => r['HEM NAME']).filter(Boolean))].sort();
    hemSel.innerHTML = '<option value="">All HEMs</option>' + hems.map(h => `<option>${h}</option>`).join('');
  }

  // Read filter values
  const search = (document.getElementById('hub-search').value || '').toLowerCase();
  const zoneF  = document.getElementById('hub-zone').value;
  const hemF   = document.getElementById('hub-hem').value;
  const perfF  = document.getElementById('hub-perf-filter').value;
  // Column sort state stored on STATE object (persists across re-renders)
  if (!STATE.hubSort) STATE.hubSort = { col: 'open', dir: 'desc' };
  const hubSortCol = STATE.hubSort.col;
  const hubSortDir = STATE.hubSort.dir;

  // Build hub map from ALL tickets (not filtered by ticket-page filters)
  const hubMap = {};
  STATE.tickets.forEach(r => {
    const store = r.Store || 'Unknown';
    if (!hubMap[store]) hubMap[store] = { open: [], inProg: [], closed: [], hems: new Set(), zones: new Set() };
    const d = hubMap[store];
    const st = (r.Status || '').toLowerCase();
    if (st === 'open')                               d.open.push(r);
    else if (st === 'in progress' || st === 'in-progress') d.inProg.push(r);
    else if (st === 'closed')                        d.closed.push(r);
    if (r['HEM NAME']) d.hems.add(r['HEM NAME']);
    if (r.Zone)        d.zones.add(r.Zone);
  });

  // Helper — avg TAT of open+inprog tickets
  const hubAvgTAT = d => {
    const all = [...d.open, ...d.inProg];
    if (!all.length) return null;
    return all.reduce((s, r) => s + calcTAT(r), 0) / all.length;
  };

  // Performance label
  const perfLabel = tat => {
    if (tat === null) return { label: '—', color: 'var(--c24-grey-300)', cls: '' };
    if (tat <= 5)  return { label: '🟢 Best',    color: 'var(--green)', cls: 'tat-ok' };
    if (tat <= 15) return { label: '🟡 Average', color: 'var(--amber)', cls: 'tat-mid' };
    return            { label: '🔴 Poor',     color: 'var(--c24-red)', cls: 'tat-hi' };
  };

  // Build rows array
  let rows = Object.entries(hubMap).map(([store, d]) => {
    const tat = hubAvgTAT(d);
    return { store, d, tat, perf: perfLabel(tat) };
  });

  // Apply filters
  if (search) rows = rows.filter(r => r.store.toLowerCase().includes(search));
  if (zoneF)  rows = rows.filter(r => r.d.zones.has(zoneF));
  if (hemF)   rows = rows.filter(r => r.d.hems.has(hemF));
  if (perfF === 'best') rows = rows.filter(r => r.tat !== null && r.tat <= 5);
  else if (perfF === 'avg') rows = rows.filter(r => r.tat !== null && r.tat > 5 && r.tat <= 15);
  else if (perfF === 'poor') rows = rows.filter(r => r.tat !== null && r.tat > 15);

  // Apply column sort based on STATE.hubSort
  const _asc = hubSortDir === 'asc';
  const _flip = _asc ? 1 : -1;
  rows.sort((a, b) => {
    switch (hubSortCol) {
      case 'store':   return _flip * a.store.localeCompare(b.store);
      case 'zone':    return _flip * ([...a.d.zones].join('') || '').localeCompare([...b.d.zones].join('') || '');
      case 'hem':     return _flip * ([...a.d.hems].join('') || '').localeCompare([...b.d.hems].join('') || '');
      case 'open':    return _flip * (a.d.open.length - b.d.open.length);
      case 'inprog':  return _flip * (a.d.inProg.length - b.d.inProg.length);
      case 'closed':  return _flip * (a.d.closed.length - b.d.closed.length);
      case 'total':   return _flip * ((a.d.open.length+a.d.inProg.length+a.d.closed.length) - (b.d.open.length+b.d.inProg.length+b.d.closed.length));
      case 'tat':     return _flip * ((a.tat ?? (hubSortDir==='asc'?Infinity:-Infinity)) - (b.tat ?? (hubSortDir==='asc'?Infinity:-Infinity)));
      case 'perf':    return _flip * ((a.tat ?? 999) - (b.tat ?? 999));
      default:        return _flip * (b.d.open.length - a.d.open.length);
    }
  });

  // ── KPI summary cards
  const totalHubs   = rows.length;
  const bestHubs    = rows.filter(r => r.tat !== null && r.tat <= 5).length;
  const avgHubs     = rows.filter(r => r.tat !== null && r.tat > 5 && r.tat <= 15).length;
  const poorHubs    = rows.filter(r => r.tat !== null && r.tat > 15).length;
  const totalOpen   = rows.reduce((s, r) => s + r.d.open.length, 0);
  const totalClosed = rows.reduce((s, r) => s + r.d.closed.length, 0);
  const totalInProg = rows.reduce((s, r) => s + r.d.inProg.length, 0);
  const allTATs     = rows.filter(r => r.tat !== null).map(r => r.tat);
  const overallTAT  = allTATs.length ? (allTATs.reduce((s,v)=>s+v,0)/allTATs.length).toFixed(1) : '—';

  kpiWrap.innerHTML = `<div class="section-head">
    <div class="section-title">🏪 Hub Performance Overview <span class="section-chip">${totalHubs} hubs</span></div>
  </div>
  <div class="kpi-grid" style="margin-bottom:20px">
    <div class="kpi-card blue"><div class="kpi-label">Total Hubs</div><div class="kpi-value">${totalHubs}</div><div class="kpi-sub">In filtered view</div></div>
    <div class="kpi-card red"><div class="kpi-label">Total Open</div><div class="kpi-value">${totalOpen}</div><div class="kpi-sub">Open tickets</div></div>
    <div class="kpi-card amber"><div class="kpi-label">In Progress</div><div class="kpi-value">${totalInProg}</div><div class="kpi-sub">Being worked on</div></div>
    <div class="kpi-card green"><div class="kpi-label">Total Closed</div><div class="kpi-value">${totalClosed}</div><div class="kpi-sub">Resolved tickets</div></div>
    <div class="kpi-card green"><div class="kpi-label">🟢 Best Hubs</div><div class="kpi-value">${bestHubs}</div><div class="kpi-sub">TAT ≤ 5 days</div></div>
    <div class="kpi-card amber"><div class="kpi-label">🟡 Avg Hubs</div><div class="kpi-value">${avgHubs}</div><div class="kpi-sub">TAT 6–15 days</div></div>
    <div class="kpi-card red"><div class="kpi-label">🔴 Poor Hubs</div><div class="kpi-value">${poorHubs}</div><div class="kpi-sub">TAT &gt; 15 days</div></div>
    <div class="kpi-card orange"><div class="kpi-label">Overall Avg TAT</div><div class="kpi-value" style="font-size:22px">${overallTAT}</div><div class="kpi-sub">Days (open+in-progress)</div></div>
  </div>`;

  // ── Chart — top 15 by open count
  const top15 = [...rows].sort((a,b)=>b.d.open.length-a.d.open.length).slice(0,15);
  chartWrap.innerHTML = `<div class="chart-card" style="margin-bottom:20px">
    <div class="chart-card-title">Top 15 Hubs — Open vs In Progress vs Closed Tickets</div>
    <canvas id="hub-bar-chart" height="220"></canvas>
  </div>`;
  setTimeout(() => {
    makeChart('hub-bar-chart', {
      type: 'bar',
      data: {
        labels: top15.map(r => r.store.replace(/CARS24 Hub, |Cars24 Hub, /gi, '')),
        datasets: [
          { label: 'Open',        data: top15.map(r=>r.d.open.length),   backgroundColor:'#E5252966', borderColor:'#E52529', borderWidth:1.5, borderRadius:4 },
          { label: 'In Progress', data: top15.map(r=>r.d.inProg.length), backgroundColor:'#D9770666', borderColor:'#D97706', borderWidth:1.5, borderRadius:4 },
          { label: 'Closed',      data: top15.map(r=>r.d.closed.length), backgroundColor:'#16A34A66', borderColor:'#16A34A', borderWidth:1.5, borderRadius:4 }
        ]
      },
      options: {
        responsive: true,
        plugins: { legend: { position:'top', labels:{ font:{ family:'Gilroy', weight:'700', size:11 } } } },
        scales: {
          x: { ticks: { font:{ family:'Gilroy', size:9 }, maxRotation:45 } },
          y: { beginAtZero:true, ticks:{ stepSize:1, font:{ family:'Gilroy', size:10 } } }
        }
      }
    });
  }, 50);

  // ── Main table — build sortable column headers
  // Helper: renders a <th> with sort arrow and click handler
  const thSort = (label, col) => {
    const isActive = hubSortCol === col;
    const arrow = isActive ? (hubSortDir === 'asc' ? ' ↑' : ' ↓') : ' ↕';
    const color = isActive ? 'color:var(--c24-red);' : 'color:var(--c24-grey-500);';
    return `<th onclick="hubSortBy('${col}')" style="cursor:pointer;user-select:none;white-space:nowrap;${color}">${label}<span style="font-size:10px;margin-left:3px">${arrow}</span></th>`;
  };

  let tHtml = `<div class="section-head">
    <div class="section-title">📋 Hub-wise Breakdown <span class="section-chip">${rows.length} hubs</span></div>
  </div>
  <div class="table-card"><div class="table-scroll"><table>
    <thead><tr>
      <th style="color:var(--c24-grey-500)">#</th>
      ${thSort('Hub / Store','store')}
      ${thSort('Zone','zone')}
      ${thSort('HEM(s)','hem')}
      ${thSort('Open','open')}
      ${thSort('In Progress','inprog')}
      ${thSort('Closed','closed')}
      ${thSort('Total Tickets','total')}
      ${thSort('Avg TAT (Open+InProg)','tat')}
      ${thSort('Performance','perf')}
    </tr></thead>
    <tbody>`;

  if (!rows.length) {
    tHtml += `<tr class="empty-row"><td colspan="10">No hubs match current filters</td></tr>`;
  }

  rows.forEach((r, idx) => {
    const tatDisplay = r.tat !== null ? r.tat.toFixed(1) : '—';
    const total = r.d.open.length + r.d.inProg.length + r.d.closed.length;
    const hemList = [...r.d.hems].join(', ') || '—';
    const zoneList = [...r.d.zones].filter(Boolean).join(', ') || '—';
    const storeKey = encodeURIComponent(r.store);
    tHtml += `<tr>
      <td class="td-muted" style="font-weight:700">${idx + 1}</td>
      <td style="font-weight:600;font-size:12px;max-width:240px">${r.store}</td>
      <td><span class="pill pill-dept" style="font-size:9px">${zoneList}</span></td>
      <td class="td-muted" style="font-size:11px;max-width:160px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="${hemList}">${hemList}</td>
      <td><span class="pill pill-open" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openHubTicketModal('${storeKey}','open')" title="Click to view open tickets">${r.d.open.length}</span></td>
      <td><span class="pill pill-prog" style="cursor:pointer;text-decoration:underline;text-underline-offset:2px" onclick="openHubTicketModal('${storeKey}','prog')" title="Click to view in-progress tickets">${r.d.inProg.length}</span></td>
      <td><span class="pill pill-closed">${r.d.closed.length}</span></td>
      <td style="font-weight:700">${total}</td>
      <td class="tat ${r.perf.cls}">${tatDisplay}</td>
      <td><span style="font-size:11px;font-weight:700;color:${r.perf.color}">${r.perf.label}</span></td>
    </tr>`;
  });

  tHtml += `</tbody></table></div></div>`;
  tableWrap.innerHTML = tHtml;
}

function hubSortBy(col) {
  if (!STATE.hubSort) STATE.hubSort = { col: 'open', dir: 'desc' };
  if (STATE.hubSort.col === col) {
    // Toggle direction if same column clicked again
    STATE.hubSort.dir = STATE.hubSort.dir === 'asc' ? 'desc' : 'asc';
  } else {
    // New column: default to desc for numbers, asc for text
    const textCols = ['store', 'zone', 'hem'];
    STATE.hubSort = { col, dir: textCols.includes(col) ? 'asc' : 'desc' };
  }
  renderHubPerformance();
}

function resetHubFilters() {
  ['hub-search','hub-zone','hub-hem','hub-perf-filter'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.value = '';
  });
  STATE.hubSort = { col: 'open', dir: 'desc' };
  renderHubPerformance();
}

// ── HEM table column sort toggle
function hemSortBy(col) {
  if (!STATE.hemSort) STATE.hemSort = { col: 'open', dir: 'desc' };
  if (STATE.hemSort.col === col) {
    STATE.hemSort.dir = STATE.hemSort.dir === 'asc' ? 'desc' : 'asc';
  } else {
    STATE.hemSort = { col, dir: col === 'name' ? 'asc' : 'desc' };
  }
  renderTickets();
}

// ─── BEAT AUDIT DEEP DIVE ────────────────────────────
// Raw CSV data store — populated by handleClrFile
STATE.clrRawData = [];

/* ── Answer scoring classification ──────────────────────
   Each answer text from the checklist CSV is classified as:
   'good'   → green  → HEM scored well on this point
   'medium' → amber  → Partial / needs improvement
   'bad'    → red    → Issue identified, action needed
   'neutral'→ grey   → N/A or informational (photo/video)
*/
const CLR_BAD = [
  'bad condition','damaged','broken','dirty mat','faded color','faded colour',
  'faded paint','faded/damaged','not available','not placed','not working',
  'not functional','not installed','loose wiring','lose wiring',
  'more than 5','more than 6','more than 10%','<90%','<95%','<150','<200',
  'old photos','wrong photo','wrong video','video not available',
  'call not connected','fungus','floor machine/handles/glass damaged',
  'hinge/lock broken','hinge/handles broken','fix with tape',
  'loose mounting','inaccurate','not as per layout',
  'available but not working','available but damaged',
  '1-2 not working','1-2 lights not','1-2 cameras not',
  'car not cleaning','not properly cleaned','not arranged',
  'cars have dust','cars was not clean','cec not cleaned',
  'missing','no jet','no drainage provision','damaged / not available',
  'branding damaged','worn','scratches','upto 30%','0%',
  'not maintain','torn','crack','leaking',
  'not damaged but upto 2 stains','dust, scattered',
  'more than 100 mtr','upto 100 mtr inaccurate','up to 100 mtr',
  'not allowed/applicable','average cleaning','available but not as per',
  'not as per old standards','90-99% staff','<90% staff',
  'printed / non-light','1 - 2 cameras not','some cctv not',
  'not in good condition','below','no water','no signal',
  'pcc flooring not','no slot','upto 5 scattered litter',
  'dust/ upto 2 stains','not cleaned properly','not maintained'
];

const CLR_MEDIUM = [
  'upto 5 scattered litter','not damaged but upto 2 stains',
  '90-99%','200 to 300','150-200','50-70 mbps','80-90 mbps',
  'available as per old standards','available but not as per layout',
  'not as per standard','some cctv','1-2 cameras not working',
  '1-2 lights not working','1-2 furniture','up to 100 mtr',
  'upto 100 mtr','partial','partially','all furniture in good condition but not as per standard',
  'upto 10% deviation','within 15 mins','1-2 not',
  'loose mounting','fix with tape/clamp but not conduit'
];

const CLR_GOOD = [
  '100%','good condition','in perfect condition','working condition',
  'working properly','properly installed','properly fixed',
  'as per layout','as per standard','no odour','no wire visible',
  'no crack','fresh and neutral','all in good condition',
  'available in good condition','installed and working',
  'callback','address correctly provided','placed in good condition',
  'litter, dust not present','fixed with proper conduit pipe',
  'not damaged, cleaned and working properly','came within 1 min',
  'fully covered','arrange as layout','antiskid floor',
  '>300','>200','>99%','>400','key record maintained',
  '100 % stock','all maintain','all okay','all well','all good',
  'cec in good condition','cec is in good condition','delivery area in good',
  'all 2 cars are clean','4 cars are clean','all cars',
  'all keys','all cctv','all lights','all ac','all furniture',
  'all screens','all chairs','all conduits','all grids','all joints',
  'all letters','all tables','all employees','all bins','all corners',
  'all areas','drain pipe is securely','facade is in good',
  'it is working as expected','yes','all assets are in good',
  'all branding are in good','all walls are in good',
  'all lights are in working','all ac are in working',
  'all inventory matched','no loose mounted','no visible wiring',
  'properly and kept in storage','no dirt','no stain','no cobweb',
  'clean and well-organized','clean and tidy','no dust',
  'coverage 95%','all slots marked','no damage',
  'all cars arranged','clean glass door','working condition',
  'no water pooling','no odour','no wire'
];

function clrScoreAnswer(ans) {
  if (!ans) return 'neutral';
  const a = ans.toLowerCase().trim();
  // Skip photo/video URLs
  if (a.startsWith('http') || a.length > 150) return 'neutral';
  // Check bad first (most specific)
  if (CLR_BAD.some(p => a.includes(p))) return 'bad';
  // Check medium
  if (CLR_MEDIUM.some(p => a.includes(p))) return 'medium';
  // Check good
  if (CLR_GOOD.some(p => a.includes(p))) return 'good';
  return 'neutral';
}

function clrExtractAnswer(rawCell) {
  if (!rawCell) return '';
  const parts = rawCell.split('\n');
  // Take last non-URL line
  for (let i = parts.length - 1; i >= 0; i--) {
    const t = parts[i].trim();
    if (t && !t.startsWith('http') && !t.startsWith('se=') && t.length > 1) return t;
  }
  return '';
}

// Section groupings for all 3 checklist types
const CLR_SECTIONS_HEM = {
  '🗺 Discovery / GMB': ['Navigation using Google','GMB navigation mockup video','Address correctness','Photos updated','Cars24 App GMB navigation','Call confirmation'],
  '🏷 External Branding': ['Branding/Signboards at turn/Entry','Signboards at parking','Signboards at mall entrance','Security guard queries','Signage for CEC','Signage inside the Hub','Signage before 10-15 m','Signage at CEC entrance'],
  '🏢 CEC Exterior': ['Cleanliness outside CEC','Standee placement Outside CEC','Cars24 board placement','Colour of branding on CEC Wall','Camera Condition: Outside CEC','Wires near entrance','Floor mat','CEC entrance door condition','Wall condition: Outside CEC','Pull/Push stickers','Door glass clean','Door handles condition','Door lock condition','Outside Lighting CEC'],
  '🛋 CEC Interior': ['CEC according to the standard layout','Cash Deposit Machine','Cash deposit machine wiring','Smell/odor inside CEC','Cleanliness inside CEC','Reception table','Biometric machine','Dress of staff','Grooming of staff','Promptness of housekeeping','Taste the coffee','Taste of water','Air purifier','Corner cleaning','Water Dispenser','Coffee machine','Logo on Cash deposit','Surrounding walls painting','Surrounding walls condition','Cooling of AC','Cleanliness of AC','AC drain point','Placement of fire extinguisher','Pressure of fire extinguisher','Service of fire extinguisher','Furniture cleanliness','Ceiling condition','Dustbin condition','Inside CEC Light Lux','Is music system','Fragrance dispenser'],
  '🚻 Washroom': ['Washroom signboards','Washroom Asset','Washroom door','Condition of mirror in washroom','Dustbin condition in washroom'],
  '🔧 Utilities': ['Trade license','WiFi Working','Meeting Room','Pantry'],
  '🚗 Yard': ['Direction board for Hub','Branding/Standees/Posters in yard','Yard paving','Slot marking','Hub entry door','Handles of entry gate','Branding outside the yard','Branding at entry gate','Customer parking','Signboards for customer parking','Drainage provision for rain water','Cleanliness outside yard gate','Flagpoles','Smell/odor in yard','Water access for car washing','Cars arrangement','Safety feeling inside yard','Cleanliness of yard floor','Validation of yard layout','Dress code Ops','Lighting Lux','Cars should be well arranged','Signal/network'],
  '🧹 Washing Area': ['car washing area cover','Drainage provision','Water connection','Water tank','Flooring (Antiskid','Lighting in the Car washing','Jet pump condition','Shed condition','Washing area signboard','WiFi availability','PCC Flooring','Cars cleanliness','PQI Area signboard'],
  '📦 Delivery Area': ['Carpet colour','Carpet condition','Barricading availability','Surrounding walls','Delivery area cleanliness','Delivery area as per standard'],
  '🖥 Ops Room': ['Key cupboard','Random check of key','Availability of water','Cleanliness of Ops room','Wires on walls','Wall condition','Wall colour','Light condition','CCTV display monitor','Cleanliness of room','Inventory reconciliation'],
  '📢 Mall Branding': ['Branding on lifts','Branding on F1','Branding on F2','Branding on F3','Branding on food court','Branding near movie hall','Branding']
};

const CLR_SECTIONS_INFRA = {
  '🗺 Discovery / GMB': ['Navigation using Google','Cars24 App GMB navigation','Media (photos','Branding asset'],
  '🏢 CEC Exterior': ['CEC facade','facade logo','CEC Main Gate','walls inside the CEC','CCTV cameras are working','Wi-Fi is working','employees are wearing','music is playing','Fragrance dispenser','CEC interior','Inside CEC lights','ACs in working','Furniture condition','Branding Including Vinyl','Cleaning condition','smell in the CEC','CEC condition'],
  '🛋 Customer Lounge': ['customer lounge','Describe the customer lounge'],
  '🖥 Ops Room': ['OPS facade','walls inside the OPS','employees are wearing Cars24 T-shirts. (2)','Car Keys','CCTV cameras are working. (2)','Inside Ops - Lights','Inside Ops - ACs','Wi-Fi is working. (2)','Inside Ops - Furniture','Inside Ops - Cleaning','ops interior','ops office condition'],
  '🚻 Washroom': ['Washroom Gate','walls inside the Washroom','Washroom Basin','Inside Washroom - Cleaning','washroom interior','washroom condition'],
  '📦 Delivery Area': ['Delivery facade','walls inside the Delivery','Inside Delivery Area - Lights','Inside Delivery','Delivery Areas','carpet in the delivery','delivery area condition','fuel stored','fuel rack'],
  '🚗 Yard': ['Branding condition in Yard','Yard Areas - Cleaning','Yard Areas - Lights','All cars are arrange','Yard Area interior','Car cleanliness audit','yard condition'],
  '🧹 Washing Area': ['drain line','Washing Areas','washing area interior','car washing area condition']
};

// Parse a raw CSV row (from STATE.clrRawData) into scored items
function parseClrRow(rawRow) {
  const meta = ['ID','Store','Employee','Score (%)','Started At','Completed At'];
  const items = [];
  const type = rawRow.__type || 'hem';

  // Detect section map
  const sectionMap = type === 'infra' ? CLR_SECTIONS_INFRA : CLR_SECTIONS_HEM;

  Object.keys(rawRow).forEach(col => {
    if (meta.includes(col) || col === '__type') return;
    const raw = rawRow[col] || '';
    const ans = clrExtractAnswer(raw);
    if (!ans) return;
    const score = clrScoreAnswer(ans);

    // Find section
    let section = 'Other';
    for (const [sec, keys] of Object.entries(sectionMap)) {
      if (keys.some(k => col.toLowerCase().includes(k.toLowerCase().slice(0, 18)))) {
        section = sec; break;
      }
    }

    items.push({
      question: col.replace(/\([^)]*\)$/, '').replace(/\s*\(\d+\)\s*$/, '').trim(),
      answer:   ans,
      score,    // 'good' | 'medium' | 'bad' | 'neutral'
      section
    });
  });
  return items;
}

/* ── SHARED DEEP DIVE MODAL RENDERER ─────────────────── */
let _ddModalData = null; // { store, employee, score, completedAt, items[], type }
let _ddTab = 'summary';

function openDeepDiveById(rowId) {
  // Find the raw row by ID
  const raw = STATE.clrRawData.find(r => String(r.ID) === String(rowId));
  if (!raw) {
    alert('Detailed data not found. Make sure the CSV is uploaded in the Checklist Reports tab.');
    return;
  }
  const items = parseClrRow(raw);
  _ddModalData = {
    store:       (raw.Store || '').trim(),
    employee:    (raw.Employee || '').trim(),
    score:       parseFloat(raw['Score (%)']) || 0,
    completedAt: (raw['Completed At'] || raw['Started At'] || '').slice(0,10),
    items,
    type:        raw.__type || 'hem'
  };
  _ddTab = 'summary';
  renderDeepDiveModal();
  const modal = document.getElementById('beat-dd-modal');
  modal.style.display = 'flex';
  modal.scrollTop = 0;
  modal.onclick = e => { if (e.target === modal) closeBeatDD(); };
  document.addEventListener('keydown', _bddEscHandler);
}

function openBeatDeepDive(encodedStore, dateKey) {
  // Match by store + date from checklist raw data
  const store = decodeURIComponent(encodedStore);
  const sl    = store.toLowerCase();

  // Find best matching row in clrRawData
  let match = null;
  // 1. Try exact store + date
  match = STATE.clrRawData.find(r => {
    const rs = (r.Store||'').trim().toLowerCase();
    const dateStr = (r['Completed At']||r['Started At']||'').slice(0,10);
    return (rs === sl || rs.includes(sl.slice(0,18)) || sl.includes(rs.slice(0,18))) && dateStr === dateKey;
  });
  // 2. Fallback: most recent submission for this store
  if (!match) {
    const candidates = STATE.clrRawData
      .filter(r => {
        const rs = (r.Store||'').trim().toLowerCase();
        return rs.includes(sl.slice(0,18)) || sl.includes(rs.slice(0,18));
      })
      .sort((a,b) => (b['Completed At']||'').localeCompare(a['Completed At']||''));
    match = candidates[0];
  }

  if (!match) {
    alert('No checklist submission found for:\n' + store + '\n\nUpload the Checklist CSV in "Checklist Reports" tab first.');
    return;
  }
  openDeepDiveById(match.ID);
}

function closeBeatDD() {
  document.getElementById('beat-dd-modal').style.display = 'none';
  document.removeEventListener('keydown', _bddEscHandler);
}
function _bddEscHandler(e) { if (e.key === 'Escape') closeBeatDD(); }

function switchBddTab(tab) {
  _ddTab = tab;
  ['summary','low','all'].forEach(t => {
    const btn = document.getElementById('bdd-tab-' + t);
    if (!btn) return;
    const isActive = t === tab;
    btn.style.color        = isActive ? 'var(--c24-red)' : 'var(--c24-grey-500)';
    btn.style.borderBottom = isActive ? '2px solid var(--c24-red)' : '2px solid transparent';
  });
  renderDeepDiveBody();
}

function renderDeepDiveModal() {
  if (!_ddModalData) return;
  const { store, employee, score, completedAt, items, type } = _ddModalData;

  // Header
  document.getElementById('bdd-title').textContent = store;
  const scoreColor = score >= 80 ? 'var(--green)' : score >= 65 ? 'var(--amber)' : 'var(--c24-red)';
  const sb = document.getElementById('bdd-score-badge');
  sb.textContent = score.toFixed(1) + '%';
  sb.style.background = score >= 80 ? '#DCFCE7' : score >= 65 ? '#FEF3C7' : '#FEE2E2';
  sb.style.color = scoreColor;

  const bad    = items.filter(i => i.score === 'bad');
  const medium = items.filter(i => i.score === 'medium');
  const good   = items.filter(i => i.score === 'good');

  document.getElementById('bdd-meta').textContent =
    `${employee} · ${completedAt} · ${type.toUpperCase()} Checklist · ${items.length} questions answered`;

  // Score strip
  document.getElementById('bdd-score-strip').innerHTML = `
    <span style="font-size:22px;font-weight:900;color:${scoreColor}">${score.toFixed(1)}%</span>
    <span style="font-size:10px;color:rgba(255,255,255,.35);font-weight:600;margin-left:4px">SCORE</span>
    <span style="width:1px;height:20px;background:rgba(255,255,255,.12);margin:0 10px"></span>
    <span style="font-size:12px;font-weight:800;color:#FF6B6B">⚠️ ${bad.length} issues</span>
    <span style="font-size:12px;font-weight:800;color:#FCD34D;margin-left:10px">🟡 ${medium.length} partial</span>
    <span style="font-size:12px;font-weight:800;color:#6EE7B7;margin-left:10px">✅ ${good.length} good</span>
    <span style="font-size:11px;color:rgba(255,255,255,.3);margin-left:10px">· ${items.length} total</span>
  `;

  switchBddTab('summary');
}

function renderDeepDiveBody() {
  const body = document.getElementById('bdd-body');
  if (!_ddModalData) return;
  const { items, score, employee } = _ddModalData;
  const tab = _ddTab;

  if (!items.length) {
    body.innerHTML = `<div style="text-align:center;padding:40px 20px">
      <div style="font-size:36px;margin-bottom:12px">📋</div>
      <div style="font-size:14px;font-weight:800;margin-bottom:8px">No question data available</div>
      <div style="font-size:12px;color:var(--c24-grey-500)">Upload the matching Checklist CSV in the <strong>Checklist Reports</strong> tab to see deep dive scoring.</div>
    </div>`;
    return;
  }

  if (tab === 'summary')  { renderDdSummary(body, items, score, employee); return; }
  if (tab === 'low')      { renderDdLow(body, items); return; }
  renderDdAll(body, items);
}

function renderDdSummary(body, items, score, employee) {
  const bad    = items.filter(i => i.score === 'bad');
  const medium = items.filter(i => i.score === 'medium');
  const good   = items.filter(i => i.score === 'good');

  // Section aggregates
  const secs = {};
  items.forEach(it => {
    if (!secs[it.section]) secs[it.section] = { bad:[], medium:[], good:[], neutral:[] };
    secs[it.section][it.score].push(it);
  });

  let html = `
  <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:12px;margin-bottom:22px">
    <div style="background:#FEF2F2;border:1px solid #FECACA;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:30px;font-weight:900;color:var(--c24-red)">${bad.length}</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-red)">⚠️ Issues Found</div>
    </div>
    <div style="background:#FFFBEB;border:1px solid #FDE68A;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:30px;font-weight:900;color:var(--amber)">${medium.length}</div>
      <div style="font-size:11px;font-weight:700;color:var(--amber)">🟡 Partial / Improve</div>
    </div>
    <div style="background:#F0FDF4;border:1px solid #BBF7D0;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:30px;font-weight:900;color:var(--green)">${good.length}</div>
      <div style="font-size:11px;font-weight:700;color:var(--green)">✅ Good / Compliant</div>
    </div>
    <div style="background:${score>=80?'#F0FDF4':score>=65?'#FFFBEB':'#FEF2F2'};border:1px solid ${score>=80?'#BBF7D0':score>=65?'#FDE68A':'#FECACA'};border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:30px;font-weight:900;color:${score>=80?'var(--green)':score>=65?'var(--amber)':'var(--c24-red)'}">${score.toFixed(1)}%</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-grey-500)">Overall Score</div>
    </div>
  </div>`;

  // Section-wise breakdown
  html += `<div style="font-size:13px;font-weight:800;color:var(--c24-black);margin-bottom:14px">📊 Section-wise Performance</div>`;

  Object.entries(secs)
    .sort((a,b) => b[1].bad.length - a[1].bad.length)
    .forEach(([sec, d]) => {
      const total = d.bad.length + d.medium.length + d.good.length + d.neutral.length;
      const scored = d.bad.length + d.medium.length + d.good.length;
      if (!scored) return;
      const pct = Math.round(d.good.length / scored * 100);
      const barC = pct >= 75 ? 'var(--green)' : pct >= 50 ? 'var(--amber)' : 'var(--c24-red)';
      const hasBad = d.bad.length > 0;

      html += `<div style="padding:12px 14px;border-radius:var(--radius-sm);margin-bottom:8px;
        border-left:4px solid ${hasBad ? 'var(--c24-red)' : d.medium.length > 0 ? 'var(--amber)' : 'var(--green)'};
        background:${hasBad ? '#FFF8F8' : '#FAFFFE'}">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:6px">
          <span style="font-size:12px;font-weight:800;color:var(--c24-black)">${sec}</span>
          <div style="display:flex;gap:10px;align-items:center;flex-shrink:0">
            ${d.bad.length > 0    ? `<span style="font-size:10px;font-weight:800;color:var(--c24-red)">⚠️ ${d.bad.length}</span>` : ''}
            ${d.medium.length > 0 ? `<span style="font-size:10px;font-weight:800;color:var(--amber)">🟡 ${d.medium.length}</span>` : ''}
            ${d.good.length > 0   ? `<span style="font-size:10px;font-weight:800;color:var(--green)">✅ ${d.good.length}</span>` : ''}
            <span style="font-size:12px;font-weight:900;color:${barC}">${pct}%</span>
          </div>
        </div>
        <div style="height:5px;border-radius:3px;background:#E8E8E8;overflow:hidden;margin-bottom:${hasBad ? '8px' : '0'}">
          <div style="height:100%;width:${pct}%;background:${barC};border-radius:3px"></div>
        </div>
        ${hasBad ? `<div>
          ${d.bad.slice(0,4).map(it => `<div style="display:flex;gap:6px;align-items:flex-start;margin-top:4px">
            <span style="color:var(--c24-red);font-size:10px;margin-top:1px;flex-shrink:0">⚠</span>
            <span style="font-size:10px;color:var(--c24-grey-700);line-height:1.4">
              <strong>${it.question.slice(0,55)}${it.question.length>55?'…':''}</strong>
              → <span style="color:var(--c24-red);font-weight:700">${it.answer.slice(0,60)}${it.answer.length>60?'…':''}</span>
            </span>
          </div>`).join('')}
          ${d.bad.length > 4 ? `<div style="font-size:10px;color:var(--c24-grey-400);margin-top:3px;font-style:italic">+${d.bad.length-4} more issues in this section…</div>` : ''}
        </div>` : ''}
      </div>`;
    });

  body.innerHTML = html;
}

function renderDdLow(body, items) {
  const actionable = items.filter(i => i.score === 'bad' || i.score === 'medium');
  if (!actionable.length) {
    body.innerHTML = `<div style="text-align:center;padding:48px">
      <div style="font-size:40px;margin-bottom:14px">🎉</div>
      <div style="font-size:15px;font-weight:800;color:var(--green);margin-bottom:6px">No issues found!</div>
      <div style="font-size:12px;color:var(--c24-grey-500)">All checklist points are compliant.</div>
    </div>`;
    return;
  }

  // Group by section
  const secs = {};
  actionable.forEach(it => {
    if (!secs[it.section]) secs[it.section] = [];
    secs[it.section].push(it);
  });

  const bad    = actionable.filter(i => i.score === 'bad');
  const medium = actionable.filter(i => i.score === 'medium');

  let html = `<div style="padding:12px 16px;background:#FEF2F2;border:1.5px solid #FECACA;border-radius:var(--radius);margin-bottom:18px;display:flex;align-items:center;gap:12px;flex-wrap:wrap">
    <div>
      <div style="font-size:13px;font-weight:800;color:var(--c24-red);margin-bottom:2px">⚠️ ${bad.length} issue${bad.length!==1?'s':''} + 🟡 ${medium.length} partial item${medium.length!==1?'s':''} identified</div>
      <div style="font-size:11px;color:#9B1C1C;font-weight:500">Fix these before the next audit to improve the hub score.</div>
    </div>
  </div>`;

  Object.entries(secs).forEach(([sec, secItems]) => {
    const badItems = secItems.filter(i => i.score === 'bad');
    const medItems = secItems.filter(i => i.score === 'medium');
    html += `<div style="margin-bottom:16px">
      <div style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.6px;color:var(--c24-grey-500);margin-bottom:8px;display:flex;align-items:center;gap:8px">
        ${sec}
        ${badItems.length ? `<span style="background:#FEF2F2;color:var(--c24-red);padding:1px 7px;border-radius:10px;font-size:10px">⚠️ ${badItems.length}</span>` : ''}
        ${medItems.length ? `<span style="background:#FFFBEB;color:var(--amber);padding:1px 7px;border-radius:10px;font-size:10px">🟡 ${medItems.length}</span>` : ''}
      </div>
      ${secItems.map(it => {
        const isBad = it.score === 'bad';
        return `<div style="padding:10px 14px;border-radius:var(--radius-sm);margin-bottom:6px;
          border:1px solid ${isBad ? '#FECACA' : '#FDE68A'};
          border-left:4px solid ${isBad ? 'var(--c24-red)' : 'var(--amber)'};
          background:#fff">
          <div style="font-size:11px;font-weight:700;color:var(--c24-black);margin-bottom:5px;line-height:1.4">${it.question}</div>
          <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap">
            <span style="font-size:11px;font-weight:800;padding:3px 10px;border-radius:20px;
              background:${isBad ? '#FEF2F2' : '#FFFBEB'};
              color:${isBad ? 'var(--c24-red)' : 'var(--amber)'}">
              ${isBad ? '⚠' : '🟡'} ${it.answer}
            </span>
            <span style="font-size:10px;color:var(--c24-grey-400)">→ Action: ${isBad ? 'Fix immediately' : 'Needs improvement'}</span>
          </div>
        </div>`;
      }).join('')}
    </div>`;
  });

  body.innerHTML = html;
}

function renderDdAll(body, items) {
  const secs = {};
  items.forEach(it => {
    if (!secs[it.section]) secs[it.section] = [];
    secs[it.section].push(it);
  });

  let html = `<div style="margin-bottom:12px;font-size:11px;color:var(--c24-grey-500);font-weight:600">
    ${items.length} questions · ⚠️ Red = Issue · 🟡 Amber = Partial · ✅ Green = Good · ⚪ Grey = N/A
  </div>`;

  Object.entries(secs).forEach(([sec, secItems]) => {
    const badCount = secItems.filter(i=>i.score==='bad').length;
    const medCount = secItems.filter(i=>i.score==='medium').length;
    const goodCount= secItems.filter(i=>i.score==='good').length;
    html += `<details open style="margin-bottom:12px;border:1px solid #EBEBEB;border-radius:var(--radius);overflow:hidden">
      <summary style="padding:10px 14px;cursor:pointer;background:var(--c24-grey-50);display:flex;align-items:center;gap:8px;list-style:none">
        <span style="font-size:12px;font-weight:800;color:var(--c24-black);flex:1">${sec}</span>
        ${badCount  ? `<span style="font-size:9px;font-weight:800;background:#FEF2F2;color:var(--c24-red);padding:2px 7px;border-radius:10px">⚠️ ${badCount}</span>` : ''}
        ${medCount  ? `<span style="font-size:9px;font-weight:800;background:#FFFBEB;color:var(--amber);padding:2px 7px;border-radius:10px">🟡 ${medCount}</span>` : ''}
        ${goodCount ? `<span style="font-size:9px;font-weight:800;background:#F0FDF4;color:var(--green);padding:2px 7px;border-radius:10px">✅ ${goodCount}</span>` : ''}
        <span style="color:var(--c24-grey-400);font-size:12px">▼</span>
      </summary>
      <div>
        ${secItems.map(it => {
          const bg  = it.score==='bad'?'#FFF8F8':it.score==='medium'?'#FFFDF0':it.score==='good'?'#FAFFFC':'#FAFAFA';
          const bc  = it.score==='bad'?'var(--c24-red)':it.score==='medium'?'var(--amber)':it.score==='good'?'var(--green)':'#CCCCCC';
          const ico = it.score==='bad'?'⚠️':it.score==='medium'?'🟡':it.score==='good'?'✅':'·';
          const tc  = it.score==='bad'?'var(--c24-red)':it.score==='medium'?'var(--amber)':it.score==='good'?'var(--green)':'var(--c24-grey-500)';
          return `<div style="padding:8px 14px;border-bottom:1px solid #F0F0F0;background:${bg};display:flex;align-items:flex-start;gap:10px">
            <span style="font-size:13px;flex-shrink:0;margin-top:1px">${ico}</span>
            <div style="flex:1;min-width:0">
              <div style="font-size:11px;font-weight:600;color:var(--c24-grey-700);margin-bottom:3px;line-height:1.4">${it.question}</div>
              <span style="font-size:11px;font-weight:800;padding:2px 9px;border-radius:20px;background:${bc}18;border:1px solid ${bc}40;color:${tc}">${it.answer}</span>
            </div>
          </div>`;
        }).join('')}
      </div>
    </details>`;
  });

  body.innerHTML = html;
}


// ─── CHECKLIST REPORTS ───────────────────────────────
STATE.clrData = { hem: [], enso: [], infra: [] };
STATE.clrTab  = 'hem';

// Official HEM names list for classification
const CLR_HEM_NAMES = [
  'Ish Kartikesh','Vyramudi 1','Ravi Ram','rishabh singh','Himanshu 1',
  'Gautam Viswanath Kotra','Binshanth S P','Vimal Kumar','Amritanshu Pandey',
  'Kartik jaskalyan','Bishwanath Pandey'
];
const CLR_HEM_LOWER = CLR_HEM_NAMES.map(h => h.toLowerCase().trim());

function clrIsHem(name) {
  const n = (name||'').toLowerCase().trim();
  return CLR_HEM_LOWER.some(h => h === n || n.includes(h.split(' ')[0].toLowerCase()) && n.includes(h.split(' ').pop().toLowerCase()));
}

function clrNormalizeHem(name) {
  const n = (name||'').toLowerCase().trim();
  for (let i = 0; i < CLR_HEM_LOWER.length; i++) {
    const h = CLR_HEM_LOWER[i];
    const parts = h.split(' ');
    if (n === h || (parts.length > 1 && n.includes(parts[0]) && n.includes(parts[parts.length-1]))) {
      return CLR_HEM_NAMES[i];
    }
    if (n === parts[0] || n.startsWith(parts[0] + ' ')) return CLR_HEM_NAMES[i];
  }
  return name.trim();
}

function handleClrFile(e, type) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading(`Parsing ${type.toUpperCase()} Checklist…`);
  document.getElementById(`fname-clr-${type}`).textContent = file.name;
  document.getElementById(`zone-clr-${type}`).classList.add('loaded');

  Papa.parse(file, {
    header: true,
    skipEmptyLines: true,
    complete: (res) => {
      // Store raw rows with type tag for deep dive
      if (!STATE.clrRawData) STATE.clrRawData = [];
      res.data.forEach(r => {
        if (r['Score (%)'] && r['Store']) {
          r.__type = type; // tag so deep dive knows which section map to use
          STATE.clrRawData.push(r);
        }
      });
      STATE.clrData[type] = res.data
        .filter(r => r['Score (%)'] && r['Store'])
        .map(r => ({
          id:       r['ID']||'',
          store:    (r['Store']||'').trim(),
          employee: (r['Employee']||'').trim(),
          score:    parseFloat(r['Score (%)'])||0,
          startedAt:   r['Started At']||'',
          completedAt: r['Completed At']||'',
          isHem:    clrIsHem(r['Employee']||''),
          hemName:  clrNormalizeHem(r['Employee']||''),
          type
        }));
      // Populate filters
      clrPopulateFilters();
      document.getElementById('clr-filters').style.display = 'flex';
      // Switch to this tab
      switchClrTab(type);
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing CSV.'); }
  });
}

function clrPopulateFilters() {
  const all = [...STATE.clrData.hem, ...STATE.clrData.enso, ...STATE.clrData.infra];
  const hems = [...new Set(all.filter(r=>r.isHem).map(r=>r.hemName).filter(Boolean))].sort();
  const sel = document.getElementById('clr-hem-filter');
  sel.innerHTML = '<option value="">All HEMs</option>' + hems.map(h=>`<option>${h}</option>`).join('');
}

function switchClrTab(tab) {
  STATE.clrTab = tab;
  ['hem','enso','infra'].forEach(t => {
    const btn = document.getElementById('clr-tab-' + t);
    btn.style.background    = t === tab ? 'var(--c24-red)' : 'transparent';
    btn.style.color         = t === tab ? '#fff' : 'var(--c24-grey-500)';
  });
  renderClReport();
}

function resetClrFilters() {
  document.getElementById('clr-hem-filter').value = '';
  document.getElementById('clr-hub-search').value = '';
  renderClReport();
}

function renderClReport() {
  const dash    = document.getElementById('clr-dashboard');
  const tab     = STATE.clrTab;
  const hemF    = document.getElementById('clr-hem-filter').value;
  const hubSrch = (document.getElementById('clr-hub-search').value||'').toLowerCase();

  let data = [...STATE.clrData[tab]];
  if (!data.length) {
    dash.innerHTML = `<div class="empty-state"><div class="empty-state-icon">${tab==='hem'?'📋':tab==='enso'?'🏪':'🏗️'}</div><h3>No ${tab.toUpperCase()} data loaded</h3><p>Upload the ${tab==='hem'?'HEM Checklist':tab==='enso'?'New HEM Enso':'Hub Infra Health'} CSV above</p></div>`;
    return;
  }

  if (hemF)    data = data.filter(r => r.isHem && r.hemName === hemF);
  if (hubSrch) data = data.filter(r => r.store.toLowerCase().includes(hubSrch));

  if (tab === 'infra') { renderInfraReport(data, dash); return; }

  // ── HEM / ENSO REPORT
  // Sort all by score
  const sorted = [...data].sort((a,b) => b.score - a.score);
  const top10  = sorted.slice(0, 10);
  const bot10  = [...sorted].reverse().slice(0, 10);

  // HEM-wise aggregates
  const hemMap = {};
  data.filter(r=>r.isHem).forEach(r => {
    if (!hemMap[r.hemName]) hemMap[r.hemName] = { scores:[], hubs:[] };
    hemMap[r.hemName].scores.push(r.score);
    hemMap[r.hemName].hubs.push(r.store);
  });
  const hemRows = Object.entries(hemMap).map(([hem,d])=>({
    hem,
    avg: d.scores.reduce((s,v)=>s+v,0)/d.scores.length,
    count: d.scores.length,
    max: Math.max(...d.scores),
    min: Math.min(...d.scores),
    hubs: [...new Set(d.hubs)]
  })).sort((a,b)=>b.avg-a.avg);

  const total = data.length;
  const avg   = total ? data.reduce((s,r)=>s+r.score,0)/total : 0;

  let html = '';

  // KPI
  html += `<div class="kpi-grid" style="margin-bottom:20px">
    <div class="kpi-card blue"><div class="kpi-label">Total Submissions</div><div class="kpi-value">${total}</div><div class="kpi-sub">This checklist type</div></div>
    <div class="kpi-card ${avg>=80?'green':avg>=65?'amber':'red'}"><div class="kpi-label">Overall Avg Score</div><div class="kpi-value" style="font-size:24px">${avg.toFixed(1)}%</div><div class="kpi-sub">All hubs combined</div></div>
    <div class="kpi-card green"><div class="kpi-label">🏆 Top Score</div><div class="kpi-value" style="font-size:20px">${sorted[0]?.score.toFixed(1)||'—'}%</div><div class="kpi-sub">${sorted[0]?.store.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0]||''}</div></div>
    <div class="kpi-card red"><div class="kpi-label">⚠️ Lowest Score</div><div class="kpi-value" style="font-size:20px">${sorted[sorted.length-1]?.score.toFixed(1)||'—'}%</div><div class="kpi-sub">${sorted[sorted.length-1]?.store.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0]||''}</div></div>
    <div class="kpi-card purple"><div class="kpi-label">HEM Auditors</div><div class="kpi-value">${hemRows.length}</div><div class="kpi-sub">Distinct HEMs</div></div>
  </div>`;

  // Charts row
  html += `<div class="chart-grid" style="margin-bottom:20px">
    <div class="chart-card"><div class="chart-card-title">All Hub Scores — Distribution</div><canvas id="clr-chart-all" height="220"></canvas></div>
    <div class="chart-card"><div class="chart-card-title">HEM-wise Average Score</div><canvas id="clr-chart-hem" height="220"></canvas></div>
  </div>`;

  // Top 10 Best Hubs
  html += `<div class="section-head"><div class="section-title" style="color:var(--green)">🏆 Top 10 Hubs — Best Performance</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F0FDF4;border-bottom:2px solid var(--green)">#</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F0FDF4;border-bottom:2px solid var(--green)">Hub / Store</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F0FDF4;border-bottom:2px solid var(--green)">HEM</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F0FDF4;border-bottom:2px solid var(--green)">Score</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F0FDF4;border-bottom:2px solid var(--green)">Completed</th>
    </tr></thead>
    <tbody>
      ${top10.map((r,i)=>`<tr style="background:${i<3?'#F0FDF4':''}">
        <td style="padding:9px 14px;font-weight:800;color:var(--green)">${i===0?'🥇':i===1?'🥈':i===2?'🥉':i+1}</td>
        <td style="padding:9px 14px;font-weight:600">${r.store}</td>
        <td style="padding:9px 14px;color:var(--purple);font-weight:600">${r.hemName}</td>
        <td style="padding:9px 14px">
          <div style="display:flex;align-items:center;gap:8px">
            <span style="font-size:15px;font-weight:900;color:var(--green)">${r.score.toFixed(1)}%</span>
            <div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:60px"><div style="height:100%;width:${Math.min(r.score,100)}%;background:var(--green);border-radius:3px"></div></div>
          </div>
        </td>
        <td style="padding:9px 14px;color:var(--c24-grey-500);font-size:11px">${r.completedAt.split(' ')[0]||'—'}</td>
      </tr>`).join('')}
    </tbody>
  </table></div></div>`;

  // Bottom 10 Low Hubs
  html += `<div class="section-head"><div class="section-title" style="color:var(--c24-red)">⚠️ Bottom 10 Hubs — Needs Improvement</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFF1F1;border-bottom:2px solid var(--c24-red)">#</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFF1F1;border-bottom:2px solid var(--c24-red)">Hub / Store</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFF1F1;border-bottom:2px solid var(--c24-red)">HEM</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFF1F1;border-bottom:2px solid var(--c24-red)">Score</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFF1F1;border-bottom:2px solid var(--c24-red)">Completed</th>
    </tr></thead>
    <tbody>
      ${bot10.map((r,i)=>`<tr style="background:${i<3?'#FFF1F1':''}">
        <td style="padding:9px 14px;font-weight:800;color:var(--c24-red)">${i+1}</td>
        <td style="padding:9px 14px;font-weight:600">${r.store}</td>
        <td style="padding:9px 14px;color:var(--purple);font-weight:600">${r.hemName}</td>
        <td style="padding:9px 14px">
          <div style="display:flex;align-items:center;gap:8px">
            <span style="font-size:15px;font-weight:900;color:var(--c24-red)">${r.score.toFixed(1)}%</span>
            <div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:60px"><div style="height:100%;width:${Math.min(r.score,100)}%;background:var(--c24-red);border-radius:3px"></div></div>
          </div>
        </td>
        <td style="padding:9px 14px;color:var(--c24-grey-500);font-size:11px">${r.completedAt.split(' ')[0]||'—'}</td>
      </tr>`).join('')}
    </tbody>
  </table></div></div>`;

  // HEM-wise Summary
  html += `<div class="section-head"><div class="section-title">👤 HEM-wise Performance Summary</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">HEM Name</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Audits</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Avg Score</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Best</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Lowest</th>
      <th style="padding:9px 14px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Hubs Audited</th>
    </tr></thead>
    <tbody>
      ${hemRows.map((r,i)=>{
        const barC = r.avg>=80?'var(--green)':r.avg>=65?'var(--amber)':'var(--c24-red)';
        const isTop = i===0, isBot = i===hemRows.length-1;
        return `<tr style="background:${isTop?'#F0FDF4':isBot?'#FFF8F8':''}">
          <td style="padding:9px 14px;font-weight:800">${r.hem}${isTop?' 🏆':isBot?' ⚠️':''}</td>
          <td style="padding:9px 14px;text-align:center;font-weight:700">${r.count}</td>
          <td style="padding:9px 14px">
            <div style="display:flex;align-items:center;gap:8px">
              <span style="font-size:14px;font-weight:900;color:${barC}">${r.avg.toFixed(1)}%</span>
              <div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:80px"><div style="height:100%;width:${Math.min(r.avg,100)}%;background:${barC};border-radius:3px"></div></div>
            </div>
          </td>
          <td style="padding:9px 14px;font-weight:700;color:var(--green)">${r.max.toFixed(1)}%</td>
          <td style="padding:9px 14px;font-weight:700;color:var(--c24-red)">${r.min.toFixed(1)}%</td>
          <td style="padding:9px 14px;font-size:11px;color:var(--c24-grey-600)">${r.hubs.map(h=>h.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0].trim()).join(' · ')}</td>
        </tr>`;
      }).join('')}
    </tbody>
  </table></div></div>`;

  // Full list — clickable rows for deep dive
  html += `<div class="section-head">
    <div class="section-title">📋 All Submissions <span class="section-chip">${data.length}</span></div>
    <span style="font-size:11px;color:var(--c24-grey-500);font-weight:600">🔍 Click any row to view deep dive score</span>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Hub</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Employee</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Type</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Score</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Completed</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Deep Dive</th>
    </tr></thead>
    <tbody>
      ${[...data].sort((a,b)=>b.score-a.score).map(r=>{
        const barC = r.score>=80?'var(--green)':r.score>=65?'var(--amber)':'var(--c24-red)';
        const rowBg = r.score < 65 ? '#FFF8F8' : '';
        return '<tr style="cursor:pointer;background:' + rowBg + '" '
          + 'onclick="openDeepDiveById(' + "'" + r.id + "'" + ')" '
          + 'onmouseover="this.style.background=\'var(--c24-grey-50)\'" '
          + 'onmouseout="this.style.background=\'' + rowBg + '\'">'
          + '<td style="padding:9px 14px;font-weight:600;font-size:11px">' + r.store + '</td>'
          + '<td style="padding:9px 14px;font-weight:600;color:' + (r.isHem?'var(--purple)':'var(--c24-grey-700)') + '">'
          + r.hemName
          + (r.isHem ? '<span style="font-size:9px;background:var(--purple-light);color:var(--purple);padding:1px 5px;border-radius:8px;margin-left:4px;font-weight:700">HEM</span>'
                     : '<span style="font-size:9px;background:var(--c24-grey-100);color:var(--c24-grey-500);padding:1px 5px;border-radius:8px;margin-left:4px;font-weight:700">NON</span>')
          + '</td>'
          + '<td style="padding:9px 14px;font-size:10px;color:var(--c24-grey-500)">' + r.type.toUpperCase() + '</td>'
          + '<td style="padding:9px 14px"><div style="display:flex;align-items:center;gap:6px">'
          + '<span style="font-size:13px;font-weight:900;color:' + barC + '">' + r.score.toFixed(1) + '%</span>'
          + '<div style="flex:1;height:4px;border-radius:2px;background:#EBEBEB;overflow:hidden;min-width:50px">'
          + '<div style="height:100%;width:' + Math.min(r.score,100) + '%;background:' + barC + ';border-radius:2px"></div></div>'
          + '</div></td>'
          + '<td style="padding:9px 14px;font-size:11px;color:var(--c24-grey-500)">' + (r.completedAt.split(' ')[0]||'—') + '</td>'
          + '<td style="padding:9px 14px"><span style="font-size:10px;font-weight:700;color:var(--blue)">🔍 View</span></td>'
          + '</tr>';
      }).join('')}
    </tbody>
  </table></div></div>`;

  dash.innerHTML = html;

  // Charts
  setTimeout(() => {
    const allSorted = [...data].sort((a,b)=>b.score-a.score);
    const top20 = allSorted.slice(0,20);
    makeChart('clr-chart-all', {
      type: 'bar',
      data: {
        labels: top20.map(r => r.store.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0].trim()),
        datasets: [{ label:'Score %', data: top20.map(r=>r.score.toFixed(1)),
          backgroundColor: top20.map(r=>r.score>=80?'#16A34A99':r.score>=65?'#D9770699':'#E5252999'),
          borderColor:     top20.map(r=>r.score>=80?'#16A34A':r.score>=65?'#D97706':'#E52529'),
          borderWidth:1.5, borderRadius:4 }]
      },
      options:{ responsive:true, plugins:{legend:{display:false}},
        scales:{ x:{ticks:{font:{family:'Gilroy',size:9},maxRotation:45}},
                 y:{min:40,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}} } }
    });
    makeChart('clr-chart-hem', {
      type: 'bar',
      data: {
        labels: hemRows.map(r=>r.hem),
        datasets: [{ label:'Avg Score %', data: hemRows.map(r=>r.avg.toFixed(1)),
          backgroundColor: hemRows.map(r=>r.avg>=80?'#16A34A99':r.avg>=65?'#D9770699':'#E5252999'),
          borderColor:     hemRows.map(r=>r.avg>=80?'#16A34A':r.avg>=65?'#D97706':'#E52529'),
          borderWidth:1.5, borderRadius:4 }]
      },
      options:{ responsive:true, plugins:{legend:{display:false}},
        scales:{ x:{ticks:{font:{family:'Gilroy',size:10},maxRotation:30}},
                 y:{min:40,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}} } }
    });
  }, 50);
}

// ── Infra Health: HEM vs Non-HEM comparison
function renderInfraReport(data, dash) {
  const hem    = data.filter(r=>r.isHem);
  const nonHem = data.filter(r=>!r.isHem);
  const avg    = arr => arr.length ? arr.reduce((s,r)=>s+r.score,0)/arr.length : 0;

  // Per-hub comparison: hub -> {hem scores, nonHem scores, people}
  const hubMap = {};
  data.forEach(r => {
    if (!hubMap[r.store]) hubMap[r.store] = { hem:[], nonHem:[], all:[] };
    if (r.isHem) hubMap[r.store].hem.push(r);
    else hubMap[r.store].nonHem.push(r);
    hubMap[r.store].all.push(r);
  });

  // HEM-wise totals
  const hemPersonMap = {};
  hem.forEach(r => {
    if (!hemPersonMap[r.hemName]) hemPersonMap[r.hemName] = [];
    hemPersonMap[r.hemName].push(r);
  });
  const hemPersonRows = Object.entries(hemPersonMap).map(([name, rows])=>({
    name, avg: avg(rows), count: rows.length, max: Math.max(...rows.map(r=>r.score)),
    min: Math.min(...rows.map(r=>r.score)), hubs: rows.map(r=>r.store)
  })).sort((a,b)=>b.avg-a.avg);

  // Non-HEM people rows
  const nonHemPersonMap = {};
  nonHem.forEach(r => {
    if (!nonHemPersonMap[r.employee]) nonHemPersonMap[r.employee] = [];
    nonHemPersonMap[r.employee].push(r);
  });
  const nonHemRows = Object.entries(nonHemPersonMap).map(([name,rows])=>({
    name, avg: avg(rows), count: rows.length, hubs: rows.map(r=>r.store)
  })).sort((a,b)=>b.avg-a.avg);

  const hubRows = Object.entries(hubMap).map(([store,d])=>({
    store,
    hemAvg:    d.hem.length    ? avg(d.hem)    : null,
    nonHemAvg: d.nonHem.length ? avg(d.nonHem) : null,
    hemPeople: [...new Set(d.hem.map(r=>r.hemName))].join(', ')||'—',
    nonHemPeople: [...new Set(d.nonHem.map(r=>r.employee))].join(', ')||'—',
    all: d.all
  })).sort((a,b)=>(b.hemAvg??-1)-(a.hemAvg??-1));

  let html = '';

  // KPI
  html += `<div class="kpi-grid" style="margin-bottom:20px">
    <div class="kpi-card blue"><div class="kpi-label">Total Submissions</div><div class="kpi-value">${data.length}</div><div class="kpi-sub">Hub Infra Health</div></div>
    <div class="kpi-card purple"><div class="kpi-label">HEM Submissions</div><div class="kpi-value">${hem.length}</div><div class="kpi-sub">By official HEMs</div></div>
    <div class="kpi-card amber"><div class="kpi-label">Non-HEM Submissions</div><div class="kpi-value">${nonHem.length}</div><div class="kpi-sub">By other staff</div></div>
    <div class="kpi-card ${avg(hem)>=avg(nonHem)?'green':'red'}"><div class="kpi-label">HEM Avg Score</div><div class="kpi-value" style="font-size:22px">${avg(hem).toFixed(1)}%</div><div class="kpi-sub">vs Non-HEM: ${avg(nonHem).toFixed(1)}%</div></div>
    <div class="kpi-card blue"><div class="kpi-label">Hubs Covered</div><div class="kpi-value">${hubRows.length}</div><div class="kpi-sub">Unique hubs</div></div>
    <div class="kpi-card ${avg(hem)>=60?'green':'red'}"><div class="kpi-label">Overall Avg</div><div class="kpi-value" style="font-size:22px">${avg(data).toFixed(1)}%</div><div class="kpi-sub">All submissions</div></div>
  </div>`;

  // VS Cards
  html += `<div style="display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:20px">
    <div style="background:var(--purple-light);border:1.5px solid var(--purple);border-radius:var(--radius);padding:20px;text-align:center">
      <div style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.6px;color:var(--purple);margin-bottom:8px">👤 HEM Auditors</div>
      <div style="font-size:44px;font-weight:900;color:var(--purple);letter-spacing:-2px;line-height:1">${avg(hem).toFixed(1)}<span style="font-size:20px">%</span></div>
      <div style="font-size:11px;color:var(--purple);font-weight:600;margin-top:4px">${hem.length} submissions · ${hemPersonRows.length} HEMs</div>
    </div>
    <div style="background:var(--amber-light);border:1.5px solid var(--amber);border-radius:var(--radius);padding:20px;text-align:center">
      <div style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.6px;color:var(--amber);margin-bottom:8px">👥 Non-HEM Auditors</div>
      <div style="font-size:44px;font-weight:900;color:var(--amber);letter-spacing:-2px;line-height:1">${avg(nonHem).toFixed(1)}<span style="font-size:20px">%</span></div>
      <div style="font-size:11px;color:var(--amber);font-weight:600;margin-top:4px">${nonHem.length} submissions · ${nonHemRows.length} people</div>
    </div>
  </div>`;

  // Charts
  html += `<div class="chart-grid" style="margin-bottom:20px">
    <div class="chart-card"><div class="chart-card-title">HEM-wise Infra Score</div><canvas id="infra-chart-hem" height="240"></canvas></div>
    <div class="chart-card"><div class="chart-card-title">Hub-wise HEM vs Non-HEM</div><canvas id="infra-chart-hub" height="240"></canvas></div>
  </div>`;

  // HEM-wise breakdown
  html += `<div class="section-head"><div class="section-title" style="color:var(--purple)">👤 HEM-wise Infra Score</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">HEM Name</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">Audits</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">Avg Score</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">Best</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">Lowest</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#F5F3FF;border-bottom:2px solid var(--purple)">Hubs</th>
    </tr></thead>
    <tbody>
      ${hemPersonRows.map((r,i)=>{
        const barC=r.avg>=60?'var(--green)':r.avg>=50?'var(--amber)':'var(--c24-red)';
        return `<tr style="background:${i===0?'#F5F3FF':''}">
          <td style="padding:9px 14px;font-weight:800;color:var(--purple)">${r.name}${i===0?' 🏆':''}</td>
          <td style="padding:9px 14px;text-align:center;font-weight:700">${r.count}</td>
          <td style="padding:9px 14px">
            <div style="display:flex;align-items:center;gap:8px">
              <span style="font-size:14px;font-weight:900;color:${barC}">${r.avg.toFixed(1)}%</span>
              <div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:80px"><div style="height:100%;width:${Math.min(r.avg,100)}%;background:${barC};border-radius:3px"></div></div>
            </div>
          </td>
          <td style="padding:9px 14px;font-weight:700;color:var(--green)">${r.max.toFixed(1)}%</td>
          <td style="padding:9px 14px;font-weight:700;color:var(--c24-red)">${r.min.toFixed(1)}%</td>
          <td style="padding:9px 14px;font-size:10px;color:var(--c24-grey-600)">${r.hubs.map(h=>h.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0]).join(' · ')}</td>
        </tr>`;
      }).join('')}
    </tbody>
  </table></div></div>`;

  // Non-HEM people
  html += `<div class="section-head"><div class="section-title" style="color:var(--amber)">👥 Non-HEM Auditors Score</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFFBEB;border-bottom:2px solid var(--amber)">Name</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFFBEB;border-bottom:2px solid var(--amber)">Audits</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFFBEB;border-bottom:2px solid var(--amber)">Avg Score</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:#FFFBEB;border-bottom:2px solid var(--amber)">Hubs Audited</th>
    </tr></thead>
    <tbody>
      ${nonHemRows.map((r,i)=>{
        const barC=r.avg>=60?'var(--green)':r.avg>=50?'var(--amber)':'var(--c24-red)';
        return `<tr>
          <td style="padding:9px 14px;font-weight:700">${r.name}</td>
          <td style="padding:9px 14px;text-align:center;font-weight:700">${r.count}</td>
          <td style="padding:9px 14px">
            <div style="display:flex;align-items:center;gap:8px">
              <span style="font-size:14px;font-weight:900;color:${barC}">${r.avg.toFixed(1)}%</span>
              <div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:80px"><div style="height:100%;width:${Math.min(r.avg,100)}%;background:${barC};border-radius:3px"></div></div>
            </div>
          </td>
          <td style="padding:9px 14px;font-size:10px;color:var(--c24-grey-600)">${r.hubs.map(h=>h.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0]).join(' · ')}</td>
        </tr>`;
      }).join('')}
    </tbody>
  </table></div></div>`;

  // Hub-wise HEM vs Non-HEM comparison
  html += `<div class="section-head"><div class="section-title">🏪 Hub-wise: HEM vs Non-HEM Score Comparison</div></div>`;
  html += `<div class="table-card" style="margin-bottom:20px"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Hub / Store</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--purple);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">HEM Auditor</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--purple);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">HEM Score</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--amber);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Non-HEM Auditor</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--amber);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Non-HEM Score</th>
      <th style="padding:9px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB">Difference</th>
    </tr></thead>
    <tbody>
      ${hubRows.map(r=>{
        const hS = r.hemAvg, nS = r.nonHemAvg;
        const diff = (hS!==null && nS!==null) ? (hS-nS) : null;
        const diffC = diff===null?'var(--c24-grey-400)':diff>0?'var(--green)':'var(--c24-red)';
        const rowBg = diff===null?'':diff>5?'#F0FDF4':diff<-5?'#FFF8F8':'';
        const sBar = (v,col)=>v!==null?`<div style="display:flex;align-items:center;gap:6px"><span style="font-size:13px;font-weight:900;color:${col};min-width:36px">${v.toFixed(1)}%</span><div style="flex:1;height:4px;border-radius:2px;background:#EBEBEB;overflow:hidden;min-width:50px"><div style="height:100%;width:${Math.min(v,100)}%;background:${col};border-radius:2px"></div></div></div>`:'<span style="color:var(--c24-grey-300)">—</span>';
        return `<tr style="background:${rowBg}">
          <td style="padding:9px 14px;font-weight:600;font-size:11px;max-width:200px">${r.store}</td>
          <td style="padding:9px 14px;color:var(--purple);font-weight:600;font-size:11px">${r.hemPeople}</td>
          <td style="padding:9px 14px;min-width:110px">${sBar(hS,'var(--purple)')}</td>
          <td style="padding:9px 14px;color:var(--amber);font-weight:600;font-size:11px">${r.nonHemPeople}</td>
          <td style="padding:9px 14px;min-width:110px">${sBar(nS,'var(--amber)')}</td>
          <td style="padding:9px 14px;font-weight:900;font-size:13px;color:${diffC}">${diff!==null?(diff>0?'+':'')+diff.toFixed(1)+'%':'—'}</td>
        </tr>`;
      }).join('')}
    </tbody>
  </table></div></div>`;

  dash.innerHTML = html;

  // Charts
  setTimeout(()=>{
    makeChart('infra-chart-hem',{
      type:'bar',
      data:{ labels:hemPersonRows.map(r=>r.name),
        datasets:[{label:'HEM Avg Score',data:hemPersonRows.map(r=>r.avg.toFixed(1)),
          backgroundColor:'#7C3AED99',borderColor:'#7C3AED',borderWidth:1.5,borderRadius:4}]},
      options:{responsive:true,plugins:{legend:{display:false}},
        scales:{x:{ticks:{font:{family:'Gilroy',size:10},maxRotation:30}},
                y:{min:20,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}}}}
    });
    const dualHubs = hubRows.filter(r=>r.hemAvg!==null && r.nonHemAvg!==null).slice(0,15);
    makeChart('infra-chart-hub',{
      type:'bar',
      data:{ labels:dualHubs.map(r=>r.store.replace(/Cars24 Hub, |CARS24 Hub, /gi,'').split(',')[0].trim()),
        datasets:[
          {label:'HEM Score',data:dualHubs.map(r=>r.hemAvg.toFixed(1)),backgroundColor:'#7C3AED99',borderColor:'#7C3AED',borderWidth:1.5,borderRadius:4},
          {label:'Non-HEM Score',data:dualHubs.map(r=>r.nonHemAvg.toFixed(1)),backgroundColor:'#D9770699',borderColor:'#D97706',borderWidth:1.5,borderRadius:4}
        ]},
      options:{responsive:true,plugins:{legend:{position:'top',labels:{font:{family:'Gilroy',size:11}}}},
        scales:{x:{ticks:{font:{family:'Gilroy',size:9},maxRotation:45}},
                y:{min:20,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}}}}
    });
  },50);
}

// ─── BEAT AUDIT PLAN ─────────────────────────────────
STATE.beatData    = [];
STATE.beatDone    = new Set();
STATE.beatScores  = {};

function parseBeatDate(str) {
  if (!str) return null;
  const s = str.trim().replace(/\\/g, '/');
  const m = s.match(/^(\d{1,2})[\/\-](\d{1,2})[\/\-](\d{2,4})$/);
  if (m) {
    let [, d, mo, y] = m;
    if (y.length === 2) y = '20' + y;
    return new Date(parseInt(y), parseInt(mo)-1, parseInt(d));
  }
  return null;
}
function fmtBeatDate(d) {
  if (!d) return '';
  return d.toLocaleDateString('en-IN', { day:'2-digit', month:'short', year:'numeric' });
}
function isoDate(d) {
  if (!d) return '';
  return `${d.getFullYear()}-${String(d.getMonth()+1).padStart(2,'0')}-${String(d.getDate()).padStart(2,'0')}`;
}

// Fuzzy store match
function storeMatch(s1, s2) {
  const clean = s => s.toLowerCase().replace(/cars24 hub,?\s*/gi,'').replace(/cars24,?\s*/gi,'').trim();
  const a = clean(s1), b = clean(s2);
  if (a === b) return true;
  const short = s => s.split(',')[0].trim().slice(0,18);
  return short(a) === short(b) || a.includes(short(b)) || b.includes(short(a));
}

// Beat Plan CSV upload
function handleBeatFile(e) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading('Parsing Beat Audit Plan...');
  document.getElementById('fname-beat').textContent = file.name;
  document.getElementById('zone-beat').classList.add('loaded');
  Papa.parse(file, {
    header: true,
    skipEmptyLines: true,
    complete: (res) => {
      const dateField = 'scheduled_date ( Sunday Working )';
      STATE.beatData = res.data
        .filter(r => r[dateField] && r['name'])
        .map(r => ({
          store:      (r['name']||'').trim(),
          hem:        (r['HEM Name']||'').trim(),
          rawDate:    (r[dateField]||'').trim(),
          parsedDate: parseBeatDate((r[dateField]||'').trim()),
          checklist:  (r['Checklist Name']||'').trim()
        }))
        .filter(r => r.parsedDate);
      populateBeatControls();
      syncBeatDoneFromClrData();
      renderBeatPlan();
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing Beat Plan CSV.'); }
  });
}

// Checklist CSV upload (hem / enso / infra)
function handleBeatClUpload(e, clType) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading('Parsing ' + clType.toUpperCase() + ' Checklist...');
  document.getElementById('fname-beat-' + clType).textContent = file.name;
  document.getElementById('zone-beat-' + clType).classList.add('loaded');
  Papa.parse(file, {
    header: true,
    skipEmptyLines: true,
    complete: (res) => {
      res.data.forEach(r => {
        const store = (r['Store'] || '').trim();
        const rawDt = r['Completed At'] || r['Starting At'] || r['Started At'] || '';
        const score = parseFloat(r['Score (%)']) || 0;
        if (!store || !rawDt) return;
        const d = parseDate(rawDt);
        if (!d) return;
        const dk  = isoDate(d);
        const key = store.toLowerCase() + '||' + dk;
        STATE.beatDone.add(key);
        if (!STATE.beatScores[key] || STATE.beatScores[key].score < score) {
          STATE.beatScores[key] = { score, employee: (r['Employee']||'').trim(), id: (r['ID']||'').trim(), clType };
        }
        // Also save raw row for deep dive
        if (!STATE.clrRawData) STATE.clrRawData = [];
        r.__type = clType;
        if (!STATE.clrRawData.find(x => x.ID === r.ID)) STATE.clrRawData.push(r);
      });
      // Sync into STATE.clrData for Checklist Reports tab
      if (!STATE.clrData) STATE.clrData = { hem:[], enso:[], infra:[] };
      const parsed = res.data
        .filter(r2 => r2['Score (%)'] && r2['Store'])
        .map(r2 => ({
          id: r2['ID']||'', store:(r2['Store']||'').trim(),
          employee:(r2['Employee']||'').trim(),
          score: parseFloat(r2['Score (%)'])||0,
          startedAt: r2['Started At']||'', completedAt: r2['Completed At']||'',
          isHem: clrIsHem(r2['Employee']||''),
          hemName: clrNormalizeHem(r2['Employee']||''),
          type: clType
        }));
      STATE.clrData[clType] = [...(STATE.clrData[clType]||[]).filter(x => !parsed.find(p=>p.id===x.id)), ...parsed];
      renderBeatPlan();
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing ' + clType + ' CSV.'); }
  });
}

// Sync beatDone from clrData if checklists already loaded in Checklist Reports tab
function syncBeatDoneFromClrData() {
  if (!STATE.clrData) return;
  const all = [...(STATE.clrData.hem||[]), ...(STATE.clrData.enso||[]), ...(STATE.clrData.infra||[])];
  all.forEach(r => {
    const store = (r.store||'').trim();
    const rawDt = r.completedAt || r.startedAt || '';
    if (!store || !rawDt) return;
    const d = parseDate(rawDt);
    if (!d) return;
    const dk = isoDate(d);
    const key = store.toLowerCase() + '||' + dk;
    STATE.beatDone.add(key);
    if (!STATE.beatScores[key]) {
      STATE.beatScores[key] = { score: r.score, employee: r.employee, id: r.id, clType: r.type };
    }
  });
}

// Check if a beat entry is done
function isBeatDone(store, date) {
  if (!date) return false;
  const dk = isoDate(date);
  const sl = store.toLowerCase();
  if (STATE.beatDone.has(sl + '||' + dk)) return true;
  for (const key of STATE.beatDone) {
    const [ks, kd] = key.split('||');
    if (kd === dk && storeMatch(sl, ks)) return true;
  }
  return false;
}

// Get score info for a completed entry
function getBeatScore(store, date) {
  if (!date) return null;
  const dk = isoDate(date);
  const sl = store.toLowerCase();
  const direct = sl + '||' + dk;
  if (STATE.beatScores[direct]) return STATE.beatScores[direct];
  for (const [key, val] of Object.entries(STATE.beatScores)) {
    const [ks, kd] = key.split('||');
    if (kd === dk && storeMatch(sl, ks)) return val;
  }
  return null;
}

// Populate filter controls
function populateBeatControls() {
  const hems = [...new Set(STATE.beatData.map(r => r.hem).filter(Boolean))].sort();
  const hemSel = document.getElementById('beat-hem');
  hemSel.innerHTML = '<option value="">All HEMs</option>' + hems.map(h => `<option>${h}</option>`).join('');

  const dates = STATE.beatData.map(r => r.parsedDate).filter(Boolean).sort((a,b)=>a-b);
  if (!dates.length) return;
  const weeks = [];
  let wS = new Date(dates[0]);
  wS.setDate(wS.getDate() - wS.getDay() + 1);
  while (wS <= dates[dates.length-1]) {
    const wE = new Date(wS); wE.setDate(wE.getDate() + 6);
    weeks.push({ start: new Date(wS), end: new Date(wE) });
    wS.setDate(wS.getDate() + 7);
  }
  const weekSel = document.getElementById('beat-week');
  weekSel.innerHTML = '<option value="all">All Weeks</option>' +
    weeks.map((w,i) => `<option value="${i}">${fmtBeatDate(w.start)} – ${fmtBeatDate(w.end)}</option>`).join('');

  document.getElementById('beat-controls').style.display = 'flex';
}

function resetBeatFilters() {
  ['beat-view','beat-hem','beat-week','beat-status','beat-sort-hem','beat-sort-score','beat-sort-pct'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.value = el.id === 'beat-view' ? 'week' : '';
  });
  renderBeatPlan();
}

// Main render
function renderBeatPlan() {
  if (!STATE.beatData.length) return;
  syncBeatDoneFromClrData();

  const viewMode  = document.getElementById('beat-view').value    || 'week';
  const hemFilter = document.getElementById('beat-hem').value     || '';
  const weekIdx   = document.getElementById('beat-week').value;
  const statusF   = document.getElementById('beat-status').value  || '';
  const sortHem   = document.getElementById('beat-sort-hem').value   || '';
  const sortScore = document.getElementById('beat-sort-score').value || '';
  const sortPct   = document.getElementById('beat-sort-pct').value   || '';

  const today = new Date(); today.setHours(0,0,0,0);

  let data = STATE.beatData.map(r => {
    const done    = isBeatDone(r.store, r.parsedDate);
    const past    = r.parsedDate < today;
    const isToday = isoDate(r.parsedDate) === isoDate(today);
    const scoreInfo = done ? getBeatScore(r.store, r.parsedDate) : null;
    const status  = done ? 'done' : past ? 'missed' : isToday ? 'today' : 'upcoming';
    return { ...r, done, past, isToday, status, scoreInfo };
  });

  if (hemFilter)            data = data.filter(r => r.hem === hemFilter);
  if (statusF === 'done')   data = data.filter(r => r.status === 'done');
  if (statusF === 'missed') data = data.filter(r => r.status === 'missed' || r.status === 'today');

  let weekStart = null, weekEnd = null;
  if (weekIdx !== 'all' && weekIdx !== '') {
    const allDates = STATE.beatData.map(r => r.parsedDate).filter(Boolean).sort((a,b)=>a-b);
    let wS = new Date(allDates[0]); wS.setDate(wS.getDate() - wS.getDay() + 1);
    for (let i = 0; i <= parseInt(weekIdx); i++) {
      weekStart = new Date(wS); weekEnd = new Date(wS); weekEnd.setDate(weekEnd.getDate() + 6);
      wS.setDate(wS.getDate() + 7);
    }
    data = data.filter(r => r.parsedDate >= weekStart && r.parsedDate <= weekEnd);
  }

  const total    = data.length;
  const doneC    = data.filter(r => r.status === 'done').length;
  const missedC  = data.filter(r => r.status === 'missed').length;
  const upcomingC= data.filter(r => r.status === 'upcoming').length;
  const todayC   = data.filter(r => r.status === 'today').length;
  const pct      = total ? Math.round(doneC/total*100) : 0;
  const scoreArr = data.filter(r=>r.scoreInfo).map(r=>r.scoreInfo.score);
  const avgScore = scoreArr.length ? (scoreArr.reduce((s,v)=>s+v,0)/scoreArr.length).toFixed(1) : '—';

  document.getElementById('beat-kpi').innerHTML = `
    <div class="kpi-grid" style="margin-bottom:20px">
      <div class="kpi-card blue"><div class="kpi-label">Total Planned</div><div class="kpi-value">${total}</div><div class="kpi-sub">Beat plan audits</div></div>
      <div class="kpi-card green"><div class="kpi-label">✅ Completed</div><div class="kpi-value">${doneC}</div><div class="kpi-sub">${pct}% rate</div></div>
      <div class="kpi-card red"><div class="kpi-label">🔴 Miss the Audit</div><div class="kpi-value">${missedC}</div><div class="kpi-sub">Past + not done</div></div>
      <div class="kpi-card amber"><div class="kpi-label">📅 Today</div><div class="kpi-value">${todayC}</div><div class="kpi-sub">Due today</div></div>
      <div class="kpi-card purple"><div class="kpi-label">⏳ Upcoming</div><div class="kpi-value">${upcomingC}</div><div class="kpi-sub">Future planned</div></div>
      <div class="kpi-card ${pct>=80?'green':pct>=50?'amber':'red'}"><div class="kpi-label">Completion %</div><div class="kpi-value">${pct}%</div>
        <div class="kpi-sub"><div style="height:4px;border-radius:2px;background:#EBEBEB;margin-top:6px;overflow:hidden"><div style="height:100%;width:${pct}%;background:${pct>=80?'var(--green)':pct>=50?'var(--amber)':'var(--c24-red)'};border-radius:2px"></div></div></div>
      </div>
      <div class="kpi-card ${avgScore!=='—'&&parseFloat(avgScore)>=75?'green':avgScore!=='—'&&parseFloat(avgScore)>=60?'amber':'red'}">
        <div class="kpi-label">Avg Score</div>
        <div class="kpi-value" style="font-size:22px">${avgScore !== '—' ? avgScore + '%' : '—'}</div>
        <div class="kpi-sub">Completed audits</div>
      </div>
    </div>`;

  if (viewMode === 'week')       renderBeatWeekView(data, weekStart, weekEnd, today, sortHem);
  else if (viewMode === 'month') renderBeatMonthView(data, today);
  else                           renderBeatHemView(data, today, sortHem, sortScore, sortPct);
}

function statusStyle(status) {
  switch(status) {
    case 'done':     return { bg:'#DCFCE7', border:'#16A34A', text:'var(--green)',   icon:'✅' };
    case 'missed':   return { bg:'#FEE2E2', border:'#E52529', text:'var(--c24-red)', icon:'🔴' };
    case 'today':    return { bg:'#FEF3C7', border:'#D97706', text:'var(--amber)',   icon:'📅' };
    case 'upcoming': return { bg:'#EFF6FF', border:'#2563EB', text:'var(--blue)',    icon:'⏳' };
    default:         return { bg:'#F5F5F5', border:'#CCCCCC', text:'#666',           icon:'·' };
  }
}

// Week Calendar View
function renderBeatWeekView(data, weekStart, weekEnd, today, sortHem) {
  let hems = [...new Set(data.map(r => r.hem).filter(Boolean))];
  if (sortHem === 'az')      hems.sort((a,b) => a.localeCompare(b));
  else if (sortHem === 'za') hems.sort((a,b) => b.localeCompare(a));
  else                       hems.sort((a,b) => a.localeCompare(b));

  const dates = [...new Set(data.map(r => isoDate(r.parsedDate)).filter(Boolean))].sort();
  let allDates = dates.map(d => new Date(d + 'T00:00:00'));
  if (weekStart && weekEnd) allDates = allDates.filter(d => d >= weekStart && d <= weekEnd);

  const weekGroups = [];
  let wk = [];
  allDates.forEach((d, i) => {
    wk.push(d);
    if (wk.length === 7 || i === allDates.length - 1) { weekGroups.push([...wk]); wk = []; }
  });

  const DAY_S  = ['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
  const MON_S  = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const idx = {};
  data.forEach(r => {
    if (!idx[r.hem]) idx[r.hem] = {};
    const dk = isoDate(r.parsedDate);
    if (!idx[r.hem][dk]) idx[r.hem][dk] = [];
    idx[r.hem][dk].push(r);
  });

  let html = '';
  weekGroups.forEach((wDates, wi) => {
    const wLabel = `${wDates[0].getDate()} ${MON_S[wDates[0].getMonth()]} – ${wDates[wDates.length-1].getDate()} ${MON_S[wDates[wDates.length-1].getMonth()]}`;
    html += '<div style="margin-bottom:28px">'
      + '<div style="font-size:13px;font-weight:800;color:var(--c24-black);margin-bottom:10px">📆 Week ' + (wi+1) + ' &nbsp;<span style="font-weight:500;color:var(--c24-grey-500);font-size:12px">' + wLabel + '</span></div>'
      + '<div style="overflow-x:auto"><table style="width:100%;border-collapse:collapse;min-width:700px;font-size:12px"><thead><tr style="background:var(--c24-grey-50)">'
      + '<th style="padding:10px 14px;text-align:left;font-size:11px;font-weight:800;color:var(--c24-grey-500);border-bottom:2px solid #EBEBEB;min-width:160px;position:sticky;left:0;background:var(--c24-grey-50)">HEM</th>'
      + wDates.map(d => {
          const iso = isoDate(d);
          const isT = iso === isoDate(today);
          return '<th style="padding:10px 8px;text-align:center;font-size:11px;font-weight:800;border-bottom:2px solid ' + (isT?'var(--c24-red)':'#EBEBEB') + ';color:' + (isT?'var(--c24-red)':'var(--c24-grey-500)') + ';min-width:130px"><div>' + DAY_S[d.getDay()] + '</div><div style="font-size:16px;font-weight:900;color:' + (isT?'var(--c24-red)':'var(--c24-black)') + '">' + d.getDate() + '</div></th>';
        }).join('')
      + '</tr></thead><tbody>';

    hems.forEach(hem => {
      const hasEntry = wDates.some(d => (idx[hem]?.[isoDate(d)]||[]).length > 0);
      if (!hasEntry) return;
      html += '<tr><td style="padding:10px 14px;font-weight:700;font-size:12px;border-bottom:1px solid #F0F0F0;vertical-align:top;position:sticky;left:0;background:white;border-right:1px solid #EBEBEB"><div>' + hem + '</div><div style="font-size:10px;color:var(--c24-grey-500)">HEM</div></td>'
        + wDates.map(d => {
            const dk      = isoDate(d);
            const entries = idx[hem]?.[dk] || [];
            if (!entries.length) return '<td style="padding:6px;border-bottom:1px solid #F0F0F0;border-left:1px solid #F5F5F5;background:#FAFAFA"></td>';
            return '<td style="padding:6px;border-bottom:1px solid #F0F0F0;border-left:1px solid #F5F5F5;vertical-align:top">'
              + entries.map(en => {
                  const st  = statusStyle(en.status);
                  const si  = en.scoreInfo;
                  const isDone = en.status === 'done';
                  const sk  = encodeURIComponent(en.store);
                  const clk = isDone ? 'onclick="openBeatDeepDive(\'' + sk + '\',\'' + dk + '\')" title="Click to view deep dive score"' : '';
                  const scoreTag = si
                    ? '<span style="font-size:9px;font-weight:800;color:' + (si.score>=75?'var(--green)':si.score>=60?'var(--amber)':'var(--c24-red)') + ';display:block;margin-top:2px">' + si.score.toFixed(1) + '% · ' + si.clType.toUpperCase() + '</span>'
                    : (en.status === 'missed' ? '<span style="font-size:9px;font-weight:800;color:var(--c24-red);display:block;margin-top:2px">Miss the audit</span>' : '');
                  return '<div ' + clk + ' style="background:' + st.bg + ';border-left:3px solid ' + st.border + ';border-radius:5px;padding:5px 8px;margin-bottom:4px;cursor:' + (isDone?'pointer':'default') + '"'
                    + (isDone ? ' onmouseover="this.style.opacity=\'.8\'" onmouseout="this.style.opacity=\'1\'"' : '')
                    + '><div style="font-size:10px;font-weight:700;color:' + st.text + ';margin-bottom:1px">' + st.icon + ' ' + en.checklist + (isDone?' 🔍':'') + '</div>'
                    + '<div style="font-size:10px;color:var(--c24-black);font-weight:600;line-height:1.3">' + en.store.replace(/CARS24 Hub, |Cars24 Hub, |Cars24 /gi,'').split(',')[0].trim() + '</div>'
                    + scoreTag + '</div>';
                }).join('')
              + '</td>';
          }).join('')
        + '</tr>';
    });

    html += '</tbody></table></div></div>';
  });

  html += '<div style="display:flex;gap:14px;flex-wrap:wrap;margin-top:8px;font-size:11px;font-weight:700;align-items:center">'
    + '<span style="color:var(--c24-grey-500)">Legend:</span>'
    + '<span style="background:#DCFCE7;border-left:3px solid #16A34A;padding:3px 10px;border-radius:4px;color:var(--green)">✅ Completed (click for score)</span>'
    + '<span style="background:#FEE2E2;border-left:3px solid #E52529;padding:3px 10px;border-radius:4px;color:var(--c24-red)">🔴 Miss the audit</span>'
    + '<span style="background:#FEF3C7;border-left:3px solid #D97706;padding:3px 10px;border-radius:4px;color:var(--amber)">📅 Today</span>'
    + '<span style="background:#EFF6FF;border-left:3px solid #2563EB;padding:3px 10px;border-radius:4px;color:var(--blue)">⏳ Upcoming</span>'
    + '</div>';

  document.getElementById('beat-dashboard').innerHTML = html;
}

// Month Grid View
function renderBeatMonthView(data, today) {
  const monthDates = [...new Set(data.map(r => isoDate(r.parsedDate)).filter(Boolean))].sort();
  if (!monthDates.length) { document.getElementById('beat-dashboard').innerHTML = '<div class="empty-state"><div class="empty-state-icon">📅</div><h3>No data</h3></div>'; return; }

  const firstDate = new Date(monthDates[0] + 'T00:00:00');
  const month = firstDate.getMonth(), year = firstDate.getFullYear();
  const DAYS = ['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
  const MONTHS = ['January','February','March','April','May','June','July','August','September','October','November','December'];
  const idx = {};
  data.forEach(r => { const dk = isoDate(r.parsedDate); if (!idx[dk]) idx[dk]=[]; idx[dk].push(r); });

  const firstOfMonth = new Date(year, month, 1);
  const startPad = firstOfMonth.getDay();
  const daysInMonth = new Date(year, month+1, 0).getDate();

  let html = '<div style="background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow-sm)">'
    + '<div style="padding:16px 20px;border-bottom:1px solid #EBEBEB;display:flex;align-items:center;justify-content:space-between">'
    + '<div style="font-size:15px;font-weight:800;color:var(--c24-black)">' + MONTHS[month] + ' ' + year + '</div>'
    + '<div style="font-size:11px;color:var(--c24-grey-500);font-weight:600">🟢 Done · 🔴 Miss the audit · 📅 Today</div></div>'
    + '<div style="display:grid;grid-template-columns:repeat(7,1fr);border-bottom:1px solid #EBEBEB">'
    + DAYS.map(d => '<div style="padding:8px;text-align:center;font-size:10px;font-weight:800;text-transform:uppercase;color:var(--c24-grey-500)">' + d + '</div>').join('')
    + '</div><div style="display:grid;grid-template-columns:repeat(7,1fr)">';

  for (let p = 0; p < startPad; p++) html += '<div style="min-height:90px;border-right:1px solid #F0F0F0;border-bottom:1px solid #F0F0F0;background:#FAFAFA"></div>';

  for (let day = 1; day <= daysInMonth; day++) {
    const d = new Date(year, month, day);
    const dk = isoDate(d);
    const entries = idx[dk] || [];
    const isToday = dk === isoDate(today);
    const isSun = d.getDay() === 0;
    const doneC = entries.filter(e=>e.status==='done').length;
    const missedC = entries.filter(e=>e.status==='missed').length;
    const cellBg = !entries.length?'':missedC>0&&doneC===0?'#FFF4F4':doneC>0&&missedC===0?'#F0FDF4':'#FFFDF0';
    html += '<div style="min-height:90px;border-right:1px solid #F0F0F0;border-bottom:1px solid #F0F0F0;padding:5px;background:' + (isToday?'#FFF7ED':cellBg) + ';' + (isToday?'outline:2px solid var(--amber);outline-offset:-2px;':'') + '">'
      + '<div style="font-size:13px;font-weight:' + (isToday?'900':'700') + ';color:' + (isToday?'var(--c24-red)':isSun?'var(--c24-red)':'var(--c24-black)') + ';margin-bottom:3px">' + day + '</div>'
      + entries.slice(0,3).map(en => {
          const st = statusStyle(en.status);
          const si = en.scoreInfo;
          return '<div style="background:' + st.bg + ';border-left:2px solid ' + st.border + ';border-radius:3px;padding:2px 5px;margin-bottom:2px;font-size:8px;font-weight:700;color:' + st.text + ';overflow:hidden;text-overflow:ellipsis;white-space:nowrap">'
            + st.icon + ' ' + en.hem.split(' ')[0] + ': ' + en.store.replace(/CARS24 Hub, |Cars24 Hub, /gi,'').split(',')[0].trim().slice(0,14)
            + (si?' · '+si.score.toFixed(0)+'%':en.status==='missed'?' · Miss the audit':'')
            + '</div>';
        }).join('')
      + (entries.length>3?'<div style="font-size:8px;color:var(--c24-grey-400);font-weight:700">+' + (entries.length-3) + ' more</div>':'')
      + (entries.length?'<div style="display:flex;gap:2px;margin-top:2px">'
        + (doneC?'<span style="font-size:7px;background:var(--green-light);color:var(--green);padding:1px 3px;border-radius:2px;font-weight:700">✅' + doneC + '</span>':'')
        + (missedC?'<span style="font-size:7px;background:var(--c24-red-light);color:var(--c24-red);padding:1px 3px;border-radius:2px;font-weight:700">🔴' + missedC + '</span>':'')
        + '</div>':'')
      + '</div>';
  }
  html += '</div></div>';
  document.getElementById('beat-dashboard').innerHTML = html;
}

// HEM Summary View with sorting
function renderBeatHemView(data, today, sortHem, sortScore, sortPct) {
  const idx = {};
  data.forEach(r => { if (!idx[r.hem]) idx[r.hem]=[]; idx[r.hem].push(r); });
  const avg = arr => arr.length ? arr.reduce((s,v)=>s+v,0)/arr.length : 0;

  let hemRows = Object.entries(idx).map(([hem, entries]) => {
    const done     = entries.filter(e=>e.status==='done');
    const missed   = entries.filter(e=>e.status==='missed');
    const todayE   = entries.filter(e=>e.status==='today');
    const upcoming = entries.filter(e=>e.status==='upcoming');
    const pct      = entries.length ? Math.round(done.length/entries.length*100) : 0;
    const scores   = done.filter(e=>e.scoreInfo).map(e=>e.scoreInfo.score);
    const avgScoreV= scores.length ? avg(scores) : null;
    return { hem, entries, done, missed, todayE, upcoming, pct, avgScoreV };
  });

  if (sortHem === 'az')        hemRows.sort((a,b) => a.hem.localeCompare(b.hem));
  else if (sortHem === 'za')   hemRows.sort((a,b) => b.hem.localeCompare(a.hem));
  if (sortScore === 'desc')    hemRows.sort((a,b) => (b.avgScoreV??-1)-(a.avgScoreV??-1));
  else if (sortScore === 'asc')hemRows.sort((a,b) => (a.avgScoreV??999)-(b.avgScoreV??999));
  if (sortPct === 'desc')      hemRows.sort((a,b) => b.pct-a.pct);
  else if (sortPct === 'asc')  hemRows.sort((a,b) => a.pct-b.pct);

  let html = '<div class="section-head"><div class="section-title">👤 HEM-wise Beat Plan Summary</div></div>';

  hemRows.forEach(({ hem, entries, done, missed, todayE, upcoming, pct, avgScoreV }) => {
    const barC   = pct>=80?'var(--green)':pct>=50?'var(--amber)':'var(--c24-red)';
    const scoreC = avgScoreV===null?'var(--c24-grey-400)':avgScoreV>=75?'var(--green)':avgScoreV>=60?'var(--amber)':'var(--c24-red)';

    html += '<div style="background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);overflow:hidden;margin-bottom:16px;box-shadow:var(--shadow-sm)">'
      + '<div style="padding:14px 18px;border-bottom:1px solid #EBEBEB;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px">'
      + '<div><div style="font-size:14px;font-weight:800;color:var(--c24-black)">' + hem + '</div>'
      + '<div style="font-size:11px;color:var(--c24-grey-500);margin-top:2px">' + entries.length + ' planned · ' + [...new Set(entries.map(e=>e.store))].length + ' hubs</div></div>'
      + '<div style="display:flex;align-items:center;gap:14px;flex-wrap:wrap">'
      + '<span style="font-size:11px;font-weight:700;color:var(--green)">✅ ' + done.length + '</span>'
      + '<span style="font-size:11px;font-weight:700;color:var(--c24-red)">🔴 ' + missed.length + (missed.length?' Miss the audit':'')+' </span>'
      + (todayE.length?'<span style="font-size:11px;font-weight:700;color:var(--amber)">📅 ' + todayE.length + ' today</span>':'')
      + '<span style="font-size:11px;font-weight:700;color:var(--blue)">⏳ ' + upcoming.length + '</span>'
      + '<div style="display:flex;align-items:center;gap:6px"><div style="width:70px;height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden"><div style="height:100%;width:' + pct + '%;background:' + barC + ';border-radius:3px"></div></div><span style="font-size:12px;font-weight:800;color:' + barC + '">' + pct + '%</span></div>'
      + (avgScoreV!==null?'<span style="font-size:12px;font-weight:800;color:' + scoreC + '">📊 ' + avgScoreV.toFixed(1) + '%</span>':'')
      + '</div></div>'
      // Table
      + '<div style="overflow-x:auto"><table style="width:100%;border-collapse:collapse;font-size:12px">'
      + '<thead><tr style="background:var(--c24-grey-50)">'
      + '<th style="padding:8px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);border-bottom:1px solid #EBEBEB">Hub / Store</th>'
      + '<th style="padding:8px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);border-bottom:1px solid #EBEBEB;white-space:nowrap">Scheduled Date</th>'
      + '<th style="padding:8px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);border-bottom:1px solid #EBEBEB">Checklist</th>'
      + '<th style="padding:8px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);border-bottom:1px solid #EBEBEB">Score</th>'
      + '<th style="padding:8px 14px;font-size:10px;font-weight:800;color:var(--c24-grey-500);border-bottom:1px solid #EBEBEB">Status</th>'
      + '</tr></thead><tbody>'
      + entries.sort((a,b)=>a.parsedDate-b.parsedDate).map(en => {
          const st  = statusStyle(en.status);
          const si  = en.scoreInfo;
          const isDone = en.status === 'done';
          const dk2 = isoDate(en.parsedDate);
          const sk  = encodeURIComponent(en.store);
          const rowBg = en.status==='missed'?'#FFF4F4':isDone?'#F0FDF4':'';
          const clk = isDone ? 'onclick="openBeatDeepDive(\'' + sk + '\',\'' + dk2 + '\')" title="Click for Deep Dive"' : '';
          return '<tr style="background:' + rowBg + ';cursor:' + (isDone?'pointer':'default') + '" '
            + 'onmouseover="this.style.background=\'var(--c24-grey-50)\'" '
            + 'onmouseout="this.style.background=\'' + rowBg + '\'" ' + clk + '>'
            + '<td style="padding:9px 14px;font-weight:600;border-bottom:1px solid #F5F5F5">' + en.store + (isDone?' <span style="font-size:9px;color:var(--green);font-weight:700">🔍</span>':'') + '</td>'
            + '<td style="padding:9px 14px;border-bottom:1px solid #F5F5F5;white-space:nowrap;font-weight:700;color:' + (en.isToday?'var(--amber)':'') + '">' + fmtBeatDate(en.parsedDate) + '</td>'
            + '<td style="padding:9px 14px;border-bottom:1px solid #F5F5F5;color:var(--c24-grey-600)">' + en.checklist + '</td>'
            + '<td style="padding:9px 14px;border-bottom:1px solid #F5F5F5">'
            + (si?'<span style="font-size:13px;font-weight:900;color:' + (si.score>=75?'var(--green)':si.score>=60?'var(--amber)':'var(--c24-red)') + '">' + si.score.toFixed(1) + '%</span> <span style="font-size:9px;color:var(--c24-grey-400)">' + si.clType.toUpperCase() + '</span>'
              :(en.status==='missed'?'<span style="font-size:10px;font-weight:700;color:var(--c24-red)">Miss the audit</span>':'<span style="color:var(--c24-grey-300)">—</span>'))
            + '</td>'
            + '<td style="padding:9px 14px;border-bottom:1px solid #F5F5F5"><span style="font-size:11px;font-weight:800;padding:3px 10px;border-radius:20px;background:' + st.bg + ';color:' + st.text + '">'
            + st.icon + ' ' + (isDone?'Completed':en.status==='missed'?'🔴 Miss the audit':en.status==='today'?'Due Today':'Upcoming')
            + '</span></td></tr>';
        }).join('')
      + '</tbody></table></div></div>';
  });

  document.getElementById('beat-dashboard').innerHTML = html;
}


// ─── MYSTERY AUDIT ───────────────────────────────────
const MA_CATS = ['Discovery','Arrival','Entry','Customer Area','Movement Across Hub','Yard Viewing','Staff Interaction & Exit'];
STATE.mysteryData  = [];
STATE.mysterySort  = { col: 'score', dir: 'desc' };

function handleMysteryFile(e) {
  const file = e.target.files[0];
  if (!file) return;
  showLoading('Parsing mystery audit data…');
  document.getElementById('fname-mystery').textContent = file.name;
  document.getElementById('zone-mystery').classList.add('loaded');

  Papa.parse(file, {
    header: true,
    skipEmptyLines: true,
    complete: (res) => {
      STATE.mysteryData = res.data.filter(r => r['Evaluation Score'] && r['Location Name']);
      // Populate city dropdown
      const cities = [...new Set(STATE.mysteryData.map(r => (r['Location City']||'').trim()).filter(Boolean))].sort();
      const cSel = document.getElementById('ma-city');
      cSel.innerHTML = '<option value="">All Cities</option>' + cities.map(c=>`<option>${c}</option>`).join('');
      document.getElementById('mystery-controls').style.display = 'flex';
      renderMysteryAudit();
      updateTopbarMeta();
      hideLoading();
    },
    error: () => { hideLoading(); alert('Error parsing mystery audit CSV.'); }
  });
}

function resetMysteryFilters() {
  ['ma-search','ma-city','ma-perf','ma-cat'].forEach(id => { const el=document.getElementById(id); if(el) el.value=''; });
  STATE.mysterySort = { col:'score', dir:'desc' };
  renderMysteryAudit();
}

function maSortBy(col) {
  if (STATE.mysterySort.col === col) {
    STATE.mysterySort.dir = STATE.mysterySort.dir === 'asc' ? 'desc' : 'asc';
  } else {
    STATE.mysterySort = { col, dir: col === 'hub' || col === 'city' ? 'asc' : 'desc' };
  }
  renderMysteryAudit();
}

function renderMysteryAudit() {
  const dash = document.getElementById('mystery-dashboard');
  if (!STATE.mysteryData || !STATE.mysteryData.length) {
    dash.innerHTML = `<div class="empty-state"><div class="empty-state-icon">🕵️</div><h3>No Mystery Audit data loaded</h3><p>Upload your Mystery Audit CSV file above to see the full performance report</p></div>`;
    return;
  }

  // Read filters
  const search  = (document.getElementById('ma-search').value || '').toLowerCase();
  const city    = document.getElementById('ma-city').value;
  const perf    = document.getElementById('ma-perf').value;
  const catFocus= document.getElementById('ma-cat').value;

  // Build hub-level aggregates
  const hubMap = {};
  STATE.mysteryData.forEach(r => {
    const hub   = (r['Location Name']||'').trim();
    const c     = (r['Location City']||'').trim();
    const score = parseFloat(r['Evaluation Score']) || 0;
    if (!hubMap[hub]) hubMap[hub] = { hub, city: c, scores: [], cats: {} };
    hubMap[hub].scores.push(score);
    MA_CATS.forEach(cat => {
      const v = parseFloat(r[cat]);
      if (!isNaN(v)) {
        if (!hubMap[hub].cats[cat]) hubMap[hub].cats[cat] = [];
        hubMap[hub].cats[cat].push(v);
      }
    });
  });

  // Compute averages per hub
  let rows = Object.values(hubMap).map(h => {
    const avgScore = h.scores.reduce((s,v)=>s+v,0) / h.scores.length;
    const catAvgs  = {};
    MA_CATS.forEach(c => { catAvgs[c] = h.cats[c]?.length ? h.cats[c].reduce((s,v)=>s+v,0)/h.cats[c].length : null; });
    const focusScore = catFocus && catAvgs[catFocus] !== null ? catAvgs[catFocus] : avgScore;
    return { ...h, avgScore, catAvgs, focusScore, evals: h.scores.length };
  });

  // Apply filters
  if (search) rows = rows.filter(r => r.hub.toLowerCase().includes(search));
  if (city)   rows = rows.filter(r => r.city === city);
  if (perf === 'best') rows = rows.filter(r => r.focusScore >= 85);
  else if (perf === 'avg')  rows = rows.filter(r => r.focusScore >= 70 && r.focusScore < 85);
  else if (perf === 'poor') rows = rows.filter(r => r.focusScore < 70);

  // Sort
  const { col, dir } = STATE.mysterySort;
  const flip = dir === 'asc' ? 1 : -1;
  rows.sort((a, b) => {
    if (col === 'hub')    return flip * a.hub.localeCompare(b.hub);
    if (col === 'city')   return flip * a.city.localeCompare(b.city);
    if (col === 'evals')  return flip * (a.evals - b.evals);
    if (col === 'score')  return flip * (a.focusScore - b.focusScore);
    if (MA_CATS.includes(col)) return flip * ((a.catAvgs[col]??-1) - (b.catAvgs[col]??-1));
    return flip * (a.focusScore - b.focusScore);
  });

  // Match hubs to HEM names from ticket data (by partial store name)
  const hemLookup = {};
  STATE.tickets.forEach(t => {
    if (t.Store && t['HEM NAME']) hemLookup[t.Store.trim()] = t['HEM NAME'].trim();
  });
  const getHEM = (hubName) => {
    if (hemLookup[hubName]) return hemLookup[hubName];
    // fuzzy: try if hub name contains or is contained in a ticket store name
    const h = hubName.toLowerCase();
    for (const [store, hem] of Object.entries(hemLookup)) {
      const s = store.toLowerCase();
      if (h.includes(s.slice(0,20)) || s.includes(h.slice(0,20))) return hem;
    }
    return '—';
  };

  // Overall stats
  const allScores = rows.map(r => r.focusScore);
  const totalEvals = rows.reduce((s,r)=>s+r.evals,0);
  const overallAvg = allScores.length ? allScores.reduce((s,v)=>s+v,0)/allScores.length : 0;
  const bestHub    = [...rows].sort((a,b)=>b.focusScore-a.focusScore)[0];
  const worstHub   = [...rows].sort((a,b)=>a.focusScore-b.focusScore)[0];

  // Overall category averages
  const catOverall = {};
  MA_CATS.forEach(cat => {
    const vals = STATE.mysteryData.map(r=>parseFloat(r[cat])).filter(v=>!isNaN(v));
    catOverall[cat] = vals.length ? vals.reduce((s,v)=>s+v,0)/vals.length : 0;
  });
  const bestCat  = MA_CATS.reduce((a,b) => catOverall[a]>catOverall[b]?a:b);
  const worstCat = MA_CATS.reduce((a,b) => catOverall[a]<catOverall[b]?a:b);

  // Warning: hubs with score < 70
  const warnHubs = rows.filter(r => r.focusScore < 70);

  // Performance label
  const perfBadge = (score) => {
    if (score >= 85) return { label:'🟢 Best',    color:'var(--green)',    bg:'var(--green-light)' };
    if (score >= 70) return { label:'🟡 Average', color:'var(--amber)',    bg:'var(--amber-light)' };
    return              { label:'🔴 Poor',     color:'var(--c24-red)',  bg:'var(--c24-red-light)' };
  };

  // Score bar helper
  const sBar = (v, col='var(--c24-red)') => v !== null
    ? `<div style="display:flex;align-items:center;gap:6px"><span style="font-weight:700;font-size:12px;min-width:32px">${v.toFixed(0)}</span><div style="flex:1;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden;min-width:50px"><div style="height:100%;width:${Math.min(v,100)}%;background:${col};border-radius:3px"></div></div></div>`
    : '<span style="color:var(--c24-grey-300)">—</span>';

  // Sortable th helper
  const maTh = (label, col, style='') => {
    const active = STATE.mysterySort.col === col;
    const arrow  = active ? (STATE.mysterySort.dir === 'asc' ? ' ↑' : ' ↓') : ' ↕';
    const color  = active ? 'color:var(--c24-red);' : 'color:var(--c24-grey-500);';
    return `<th onclick="maSortBy('${col}')" style="padding:9px 12px;text-align:left;font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.4px;background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;cursor:pointer;user-select:none;white-space:nowrap;${color}${style}">${label}<span style="font-size:9px;margin-left:2px">${arrow}</span></th>`;
  };

  let html = '';

  // ── KPI Overview Cards
  html += `<div class="section-head"><div class="section-title">🕵️ Mystery Audit Overview <span class="section-chip">${rows.length} hubs · ${totalEvals} evaluations</span></div></div>`;
  html += `<div class="kpi-grid" style="margin-bottom:16px">
    <div class="kpi-card blue"><div class="kpi-label">Hubs Audited</div><div class="kpi-value">${rows.length}</div><div class="kpi-sub">In filtered view</div></div>
    <div class="kpi-card green"><div class="kpi-label">Overall Avg Score</div><div class="kpi-value" style="font-size:24px">${overallAvg.toFixed(1)}</div><div class="kpi-sub">All hubs combined</div></div>
    <div class="kpi-card green"><div class="kpi-label">🏆 Best Hub</div><div class="kpi-value" style="font-size:14px;letter-spacing:0;line-height:1.3">${bestHub?.hub.replace(/CARS24 Hub, |Cars24 Hub, |Cars24, /gi,'').split(',')[0]||'—'}</div><div class="kpi-sub">${bestHub?.focusScore.toFixed(1)} score · ${getHEM(bestHub?.hub||'')}</div></div>
    <div class="kpi-card red"><div class="kpi-label">⚠️ Lowest Hub</div><div class="kpi-value" style="font-size:14px;letter-spacing:0;line-height:1.3">${worstHub?.hub.replace(/CARS24 Hub, |Cars24 Hub, |Cars24, /gi,'').split(',')[0]||'—'}</div><div class="kpi-sub">${worstHub?.focusScore.toFixed(1)} score · ${getHEM(worstHub?.hub||'')}</div></div>
    <div class="kpi-card green"><div class="kpi-label">✅ Best Category</div><div class="kpi-value" style="font-size:14px;letter-spacing:0;line-height:1.3">${bestCat}</div><div class="kpi-sub">Avg ${catOverall[bestCat].toFixed(1)}</div></div>
    <div class="kpi-card red"><div class="kpi-label">❌ Weak Category</div><div class="kpi-value" style="font-size:14px;letter-spacing:0;line-height:1.3">${worstCat}</div><div class="kpi-sub">Avg ${catOverall[worstCat].toFixed(1)}</div></div>
    <div class="kpi-card green"><div class="kpi-label">🟢 Best Hubs (≥85)</div><div class="kpi-value">${rows.filter(r=>r.focusScore>=85).length}</div><div class="kpi-sub">High performers</div></div>
    <div class="kpi-card red"><div class="kpi-label">🔴 Poor Hubs (&lt;70)</div><div class="kpi-value">${rows.filter(r=>r.focusScore<70).length}</div><div class="kpi-sub">Need attention</div></div>
  </div>`;

  // ── Warning Banner for Poor Hubs
  if (warnHubs.length) {
    html += `<div style="background:#FFF1F1;border:1.5px solid #FECACA;border-left:4px solid var(--c24-red);border-radius:var(--radius);padding:14px 18px;margin-bottom:16px;display:flex;align-items:flex-start;justify-content:space-between;gap:16px;flex-wrap:wrap">
      <div style="flex:1">
        <div style="font-size:13px;font-weight:800;color:var(--c24-red);margin-bottom:4px">⚠️ Low Performance Alert — Hubs scoring below 70</div>
        <div style="font-size:11px;color:#9B1C1C;margin-bottom:10px;font-weight:500">These hubs require immediate HEM review and corrective action.</div>
        <div style="display:flex;gap:8px;flex-wrap:wrap">
          ${warnHubs.map(r => {
            const hem = getHEM(r.hub);
            return `<div style="background:#fff;border:1px solid #FECACA;border-radius:var(--radius-sm);padding:8px 12px;min-width:170px">
              <div style="font-size:11px;font-weight:800;color:var(--c24-black);margin-bottom:2px">${r.hub.replace(/CARS24 Hub, |Cars24 Hub, |Cars24, /gi,'')}</div>
              <div style="font-size:18px;font-weight:900;color:var(--c24-red);line-height:1.2">${r.focusScore.toFixed(1)}</div>
              <div style="font-size:10px;color:#9B1C1C;font-weight:600">HEM: ${hem}</div>
            </div>`;
          }).join('')}
        </div>
      </div>
      <div style="font-size:22px;font-weight:900;color:var(--c24-red);text-align:right;flex-shrink:0">${warnHubs.length}<span style="font-size:11px;font-weight:700;display:block;color:#9B1C1C">at risk</span></div>
    </div>`;
  }

  // ── Category Overview Cards (overall averages)
  html += `<div class="section-head"><div class="section-title">📊 Category-wise Overall Scores</div></div>`;
  html += `<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:12px;margin-bottom:20px">`;
  MA_CATS.forEach(cat => {
    const v = catOverall[cat];
    const isBest  = cat === bestCat;
    const isWorst = cat === worstCat;
    const barColor = v >= 85 ? 'var(--green)' : v >= 70 ? 'var(--amber)' : 'var(--c24-red)';
    const border   = isBest ? '2px solid var(--green)' : isWorst ? '2px solid var(--c24-red)' : '1px solid #EBEBEB';
    html += `<div style="background:var(--c24-white);border:${border};border-radius:var(--radius);padding:14px 16px;box-shadow:var(--shadow-sm)">
      <div style="font-size:9px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500);margin-bottom:6px">${cat}${isBest?' ✅':isWorst?' ❌':''}</div>
      <div style="font-size:26px;font-weight:900;color:${barColor};letter-spacing:-1px;line-height:1">${v.toFixed(1)}</div>
      <div style="height:4px;border-radius:2px;background:#EBEBEB;margin-top:8px;overflow:hidden"><div style="height:100%;width:${Math.min(v,100)}%;background:${barColor};border-radius:2px"></div></div>
    </div>`;
  });
  html += `</div>`;

  // ── Chart
  html += `<div class="chart-grid" style="margin-bottom:20px">
    <div class="chart-card">
      <div class="chart-card-title">${catFocus ? catFocus + ' Score' : 'Overall Score'} — Top 15 Hubs</div>
      <canvas id="ma-chart-top" height="240"></canvas>
    </div>
    <div class="chart-card">
      <div class="chart-card-title">Category Score Breakdown (All Hubs Avg)</div>
      <canvas id="ma-chart-cat" height="240"></canvas>
    </div>
  </div>`;

  // ── Hub Table
  const focusLabel = catFocus || 'Overall Score';

  // ── Customer Feedback Analytics (all hubs)
  const allEvals2 = STATE.mysteryData.filter(r => r['Location Name'] && parseFloat(r['Evaluation Score']));
  const cfAll    = buildCFAnalysis(allEvals2);
  const cfSortedIssues = Object.entries(cfAll.issues).sort((a,b)=>b[1].count-a[1].count);
  const cfSortedPos    = Object.entries(cfAll.positives).sort((a,b)=>b[1].count-a[1].count);
  const totalEvalsAll  = cfAll.byEval.length;
  const overallAllDist = {};
  cfAll.byEval.forEach(e => { if(e.overall) overallAllDist[e.overall]=(overallAllDist[e.overall]||0)+1; });
  const satisfiedAllPct = totalEvalsAll ? Math.round(((overallAllDist['Excellent']||0)+(overallAllDist['Good']||0))/totalEvalsAll*100) : 0;

  html += `<div class="section-head"><div class="section-title">💬 Customer Feedback Analytics <span class="section-chip">All ${totalEvalsAll} evaluations</span></div></div>`;
  html += `<div class="kpi-grid" style="margin-bottom:16px">
    <div class="kpi-card blue"><div class="kpi-label">Total Evaluations</div><div class="kpi-value">${totalEvalsAll}</div><div class="kpi-sub">Mystery audit visits</div></div>
    <div class="kpi-card red"><div class="kpi-label">🔴 Total Issues</div><div class="kpi-value">${cfAll.totalIssues}</div><div class="kpi-sub">Customer-reported</div></div>
    <div class="kpi-card green"><div class="kpi-label">✅ Positives</div><div class="kpi-value">${cfAll.totalPositives}</div><div class="kpi-sub">Good experiences</div></div>
    <div class="kpi-card ${satisfiedAllPct>=70?'green':'red'}"><div class="kpi-label">Satisfaction Rate</div><div class="kpi-value">${satisfiedAllPct}%</div><div class="kpi-sub">Good + Excellent</div></div>
    <div class="kpi-card amber"><div class="kpi-label">Top Issue</div><div class="kpi-value" style="font-size:13px;letter-spacing:0;line-height:1.3">${cfAll.topIssue?cfAll.topIssue[0].replace(/[^\w\s]/g,"").trim().slice(0,18):"—"}</div><div class="kpi-sub">${cfAll.topIssue?cfAll.topIssue[1].count+" occurrences":""}</div></div>
    <div class="kpi-card green"><div class="kpi-label">Most Praised</div><div class="kpi-value" style="font-size:13px;letter-spacing:0;line-height:1.3">${cfAll.topPositive?cfAll.topPositive[0].replace(/[^\w\s]/g,"").trim().slice(0,18):"—"}</div><div class="kpi-sub">${cfAll.topPositive?cfAll.topPositive[1].count+" instances":""}</div></div>
  </div>`;

  html += `<div class="chart-grid" style="margin-bottom:20px">
    <div class="chart-card"><div class="chart-card-title">🔴 Most Common Customer Issues</div>
      ${cfSortedIssues.map(([cat,d]) => {
        const st = CF_SEVERITY_STYLE[CF_SEVERITY[cat]||"medium"];
        const pct = totalEvalsAll?Math.round(d.count/totalEvalsAll*100):0;
        return `<div style="display:flex;align-items:center;gap:8px;margin-bottom:7px"><span style="font-size:11px;font-weight:700;min-width:155px;color:var(--c24-black)">${cat}</span><div style="flex:1;height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden"><div style="height:100%;width:${Math.min(pct*3,100)}%;background:${st.color};border-radius:3px"></div></div><span style="font-size:12px;font-weight:900;color:${st.color};min-width:26px;text-align:right">${d.count}</span></div>`;
      }).join("")}
    </div>
    <div class="chart-card"><div class="chart-card-title">✅ Most Appreciated by Customers</div>
      ${cfSortedPos.map(([cat,d]) => {
        const pct = totalEvalsAll?Math.round(d.count/totalEvalsAll*100):0;
        return `<div style="display:flex;align-items:center;gap:8px;margin-bottom:7px"><span style="font-size:11px;font-weight:700;min-width:155px;color:var(--c24-black)">${cat}</span><div style="flex:1;height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden"><div style="height:100%;width:${Math.min(pct*3,100)}%;background:var(--green);border-radius:3px"></div></div><span style="font-size:12px;font-weight:900;color:var(--green);min-width:26px;text-align:right">${d.count}</span></div>`;
      }).join("")}
    </div>
  </div>`;

  html += `<div class="section-head"><div class="section-title">🏪 Hub-wise Mystery Audit Performance <span class="section-chip">${rows.length} hubs</span></div>
    <span style="font-size:11px;color:var(--c24-grey-500);font-weight:600">↕ Click any column header to sort</span>
  </div>`;
  html += `<div class="table-card"><div class="table-scroll"><table style="font-size:12px">
    <thead><tr>
      <th style="padding:9px 12px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;white-space:nowrap">#</th>
      ${maTh('Hub / Store','hub')}
      ${maTh('City','city')}
      <th style="padding:9px 12px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;white-space:nowrap">HEM</th>
      ${maTh('Evals','evals')}
      ${maTh(focusLabel,'score')}
      ${MA_CATS.map(c => maTh(c, c)).join('')}
      <th style="padding:9px 12px;text-align:left;font-size:10px;font-weight:800;color:var(--c24-grey-500);background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;white-space:nowrap">Performance</th>
    </tr></thead>
    <tbody>`;

  if (!rows.length) html += `<tr class="empty-row"><td colspan="${7+MA_CATS.length}">No hubs match current filters</td></tr>`;
  rows.forEach((r, idx) => {
    const hem   = getHEM(r.hub);
    const badge = perfBadge(r.focusScore);
    const isPoor = r.focusScore < 70;
    const rowBg  = isPoor ? 'background:#FFF8F8;border-left:3px solid var(--c24-red);' : r.focusScore>=85 ? 'background:#F0FDF4;border-left:3px solid var(--green);' : '';
    const hubKey = encodeURIComponent(r.hub);
    html += `<tr style="${rowBg}cursor:pointer" onclick="openMaModal('${hubKey}')" title="Click to view deep dive feedback for this hub" onmouseover="this.style.opacity='.88'" onmouseout="this.style.opacity='1'">
      <td style="padding:9px 12px;font-weight:700;color:var(--c24-grey-500)">${idx+1}</td>
      <td style="padding:9px 12px;font-weight:700;font-size:11px;max-width:220px"><span style="color:var(--blue);text-decoration:underline;text-underline-offset:2px">${r.hub}</span></td>
      <td style="padding:9px 12px;font-size:11px;color:var(--c24-grey-500);white-space:nowrap">${r.city}</td>
      <td style="padding:9px 12px;font-size:11px;font-weight:600;white-space:nowrap">${hem !== '—' ? `<span style="color:var(--purple)">${hem}</span>` : '<span style="color:var(--c24-grey-300)">—</span>'}</td>
      <td style="padding:9px 12px;text-align:center;font-weight:700">${r.evals}</td>
      <td style="padding:9px 12px;min-width:100px">${sBar(r.focusScore, isPoor ? 'var(--c24-red)' : r.focusScore>=85 ? 'var(--green)' : 'var(--amber)')}</td>
      ${MA_CATS.map(cat => {
        const v = r.catAvgs[cat];
        const barC = v === null ? '' : v >= 85 ? 'var(--green)' : v >= 70 ? 'var(--amber)' : 'var(--c24-red)';
        return `<td style="padding:9px 12px;min-width:90px">${sBar(v, barC)}</td>`;
      }).join('')}
      <td style="padding:9px 12px;white-space:nowrap"><span style="font-size:11px;font-weight:800;color:${badge.color}">${badge.label}</span></td>
    </tr>`;
  });
  html += `</tbody></table></div></div>`;

  document.getElementById('mystery-dashboard').innerHTML = html;

  // ── Render Charts
  setTimeout(() => {
    const top15 = [...rows].sort((a,b)=>b.focusScore-a.focusScore).slice(0,15);
    const bottom = [...rows].sort((a,b)=>a.focusScore-b.focusScore).slice(0,5);

    makeChart('ma-chart-top', {
      type: 'bar',
      data: {
        labels: top15.map(r=>r.hub.replace(/CARS24 Hub, |Cars24 Hub, |Cars24, /gi,'').split(',')[0].trim()),
        datasets: [{
          label: focusLabel,
          data: top15.map(r=>r.focusScore.toFixed(1)),
          backgroundColor: top15.map(r => r.focusScore>=85?'#16A34A99':r.focusScore>=70?'#D9770699':'#E5252999'),
          borderColor:     top15.map(r => r.focusScore>=85?'#16A34A':r.focusScore>=70?'#D97706':'#E52529'),
          borderWidth: 1.5, borderRadius: 4
        }]
      },
      options: {
        responsive:true,
        plugins:{ legend:{display:false} },
        scales:{
          x:{ticks:{font:{family:'Gilroy',size:9},maxRotation:45}},
          y:{beginAtZero:false,min:40,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}}
        }
      }
    });

    makeChart('ma-chart-cat', {
      type: 'bar',
      data: {
        labels: MA_CATS,
        datasets: [{
          label: 'Avg Score',
          data: MA_CATS.map(c=>catOverall[c].toFixed(1)),
          backgroundColor: MA_CATS.map(c=>catOverall[c]>=85?'#16A34A99':catOverall[c]>=70?'#D9770699':'#E5252999'),
          borderColor:     MA_CATS.map(c=>catOverall[c]>=85?'#16A34A':catOverall[c]>=70?'#D97706':'#E52529'),
          borderWidth:1.5, borderRadius:4
        }]
      },
      options:{
        indexAxis:'y',
        responsive:true,
        plugins:{legend:{display:false}},
        scales:{
          x:{beginAtZero:false,min:50,max:100,ticks:{font:{family:'Gilroy',size:10},callback:v=>v+'%'}},
          y:{ticks:{font:{family:'Gilroy',size:10}}}
        }
      }
    });
  }, 50);
}

// ─── CUSTOMER FEEDBACK ENGINE ────────────────────────
// Maps question keys to column name substrings
const CF_QUESTIONS = {
  wait_time:         'How much time does the sales staff take to attend you?',
  proactive:         'Was the first interaction initiated proactively by staff?',
  ownership:         'Did one specific staff member clearly take ownership',
  lack_ownership:    'At any point, did you feel your case lacked clear ownership',
  repeat:            'Did you have to repeat your requirement to multiple staff members?',
  process_explain:   'Did the CA clearly explain the end-to-end process',
  clear_nextsteps:   'Did you leave with clear next steps?',
  timelines:         'Were timelines (delivery / booking / documentation) clearly communicated?',
  followup:          'Did staff provide structured follow-up information',
  pricing:           'Were pricing components (vehicle cost, add-ons, taxes) explained transparently?',
  booking_attempt:   'Did the CA attempt to convert the visit into a booking?',
  booking_policy:    'Was booking policy (token / refund / process) clearly explained?',
  pressured:         'Did you feel pressured to book?',
  would_book:        'Would you consider booking after this visit?',
  listen:            'Did staff actively listen to your requirements?',
  product_knowledge: 'Did the CA demonstrate strong product knowledge?',
  coordination:      'Did you observe coordination issues among staff',
  overall_rating:    'Based on your entire interaction (excluding infra), how would you rate the overall service experience?',
  test_drive_guided: 'Did staff accompany and guide during the test drive',
  respectful:        'Was the CA respectful and patient throughout the interaction?',
};

// Issue categories with their trigger questions
const CF_CATEGORIES = {
  '👤 Staff Behaviour':        ['proactive','ownership','lack_ownership','respectful','listen','coordination','repeat'],
  '⏱ Waiting Time':           ['wait_time'],
  '💬 Communication':          ['process_explain','timelines','followup','clear_nextsteps','pricing'],
  '🚗 Test Drive Experience':  ['test_drive_guided'],
  '📄 Documentation/Process':  ['booking_policy','booking_attempt'],
  '⭐ Overall Experience':     ['overall_rating','would_book','pressured','product_knowledge'],
};

// Negative answer patterns per question
const CF_NEG = {
  wait_time:         ['10 to 15 mins','15 to 20 mins','20 to 30 mins','> 30 mins'],
  proactive:         ['No'],
  ownership:         ['No'],
  lack_ownership:    ['Yes'],
  repeat:            ['Yes'],
  process_explain:   ['No'],
  clear_nextsteps:   ['No'],
  timelines:         ['Vague','Not discussed','Not communicated'],
  followup:          ['No'],
  pricing:           ['Partially explained','Not explained'],
  booking_attempt:   ['No'],
  booking_policy:    ['No','Not explained'],
  pressured:         ['Yes'],
  would_book:        ['No','Maybe'],
  listen:            ['No'],
  product_knowledge: ['No','Weak'],
  coordination:      ['Yes'],
  overall_rating:    ['Poor','Average'],
  test_drive_guided: ['No'],
  respectful:        ['No'],
};

const CF_POS = {
  wait_time:         ['< 5 mins','5 to 10 mins','Immediately'],
  proactive:         ['Yes'],
  ownership:         ['Yes'],
  lack_ownership:    ['No'],
  repeat:            ['No'],
  process_explain:   ['Yes'],
  clear_nextsteps:   ['Yes'],
  timelines:         ['Clearly communicated'],
  followup:          ['Yes'],
  pricing:           ['Fully explained'],
  booking_attempt:   ['Yes'],
  pressured:         ['No'],
  would_book:        ['Yes','Definitely'],
  listen:            ['Yes'],
  product_knowledge: ['Yes','Strong'],
  coordination:      ['No'],
  overall_rating:    ['Excellent','Good'],
  test_drive_guided: ['Yes'],
  respectful:        ['Yes'],
};

// Severity of each issue category
const CF_SEVERITY = {
  '👤 Staff Behaviour':       'critical',
  '⏱ Waiting Time':          'medium',
  '💬 Communication':         'medium',
  '🚗 Test Drive Experience': 'medium',
  '📄 Documentation/Process': 'medium',
  '⭐ Overall Experience':    'critical',
};

const CF_SEVERITY_STYLE = {
  critical: { bg:'#FEE2E2', color:'var(--c24-red)',    badge:'🔴 Critical',  border:'#FECACA' },
  medium:   { bg:'#FFF7ED', color:'#EA580C',           badge:'🟠 Medium',    border:'#FED7AA' },
  positive: { bg:'#F0FDF4', color:'var(--green)',      badge:'🟢 Positive',  border:'#BBF7D0' },
};

// Find column name in a row by partial match
function cfFindCol(row, qText) {
  return Object.keys(row).find(k => k.toLowerCase().includes(qText.toLowerCase().slice(0,30)));
}

// Build customer feedback analysis from mystery audit evals
function buildCFAnalysis(evals) {
  const issues    = {};   // category -> { count, items: [{q, ans, eval_id, date}] }
  const positives = {};   // category -> { count, items }
  const byEval    = [];   // per-evaluation summary

  evals.forEach((r, ei) => {
    const evalIssues   = [];
    const evalPositives= [];

    Object.entries(CF_CATEGORIES).forEach(([cat, keys]) => {
      keys.forEach(key => {
        const qText = CF_QUESTIONS[key];
        if (!qText) return;
        const col = cfFindCol(r, qText);
        if (!col) return;
        const ans = (r[col] || '').trim();
        if (!ans || ans === '0') return;

        const isNeg = (CF_NEG[key] || []).some(n => ans.toLowerCase().includes(n.toLowerCase()));
        const isPos = (CF_POS[key] || []).some(p => ans.toLowerCase().includes(p.toLowerCase()));

        if (isNeg) {
          if (!issues[cat]) issues[cat] = { count:0, items:[] };
          issues[cat].count++;
          issues[cat].items.push({ key, q: qText, ans, date: r['Evaluation Date']||'' });
          evalIssues.push({ cat, q: qText, ans });
        }
        if (isPos) {
          if (!positives[cat]) positives[cat] = { count:0, items:[] };
          positives[cat].count++;
          positives[cat].items.push({ key, q: qText, ans, date: r['Evaluation Date']||'' });
          evalPositives.push({ cat, q: qText, ans });
        }
      });
    });

    // Collect (Comments) for this eval
    const comments = [];
    Object.keys(r).forEach(col => {
      if (!col.includes('(Comments)')) return;
      const val = (r[col]||'').trim();
      if (val && val.length > 30 && !val.startsWith('http')) {
        comments.push({ topic: col.replace('(Comments) ',''), text: val });
      }
    });

    byEval.push({
      id:        r['Evaluation ID']||ei,
      date:      r['Evaluation Date']||'',
      score:     parseFloat(r['Evaluation Score'])||0,
      overall:   cfFindCol(r, 'how would you rate the overall service experience') ?
                 r[cfFindCol(r,'how would you rate the overall service experience')]||'' : '',
      waitTime:  cfFindCol(r, 'How much time does the sales staff') ?
                 r[cfFindCol(r,'How much time does the sales staff')]||'' : '',
      issueCount: evalIssues.length,
      posCount:   evalPositives.length,
      issues:     evalIssues,
      positives:  evalPositives,
      comments
    });
  });

  const totalIssues    = Object.values(issues).reduce((s,v)=>s+v.count,0);
  const totalPositives = Object.values(positives).reduce((s,v)=>s+v.count,0);
  const criticalCats   = Object.keys(issues).filter(c => CF_SEVERITY[c]==='critical');
  const topIssue       = Object.entries(issues).sort((a,b)=>b[1].count-a[1].count)[0];
  const topPositive    = Object.entries(positives).sort((a,b)=>b[1].count-a[1].count)[0];

  return { issues, positives, byEval, totalIssues, totalPositives, criticalCats, topIssue, topPositive };
}

function renderMaCustomerFeedback(evals, hubName) {
  const cf = buildCFAnalysis(evals);
  const { issues, positives, byEval, totalIssues, totalPositives } = cf;

  const overallDist = {};
  byEval.forEach(e => { if(e.overall) overallDist[e.overall] = (overallDist[e.overall]||0)+1; });
  const waitDist = {};
  byEval.forEach(e => { if(e.waitTime) waitDist[e.waitTime] = (waitDist[e.waitTime]||0)+1; });

  const satisfiedCount = (overallDist['Excellent']||0) + (overallDist['Good']||0);
  const unhappyCount   = (overallDist['Poor']||0) + (overallDist['Average']||0);
  const satPct = evals.length ? Math.round(satisfiedCount/evals.length*100) : 0;

  let html = '';

  // ── Summary Cards
  html += `<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:12px;margin-bottom:22px">
    <div style="background:#EFF6FF;border:1px solid #BFDBFE;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--blue)">${evals.length}</div>
      <div style="font-size:11px;font-weight:700;color:var(--blue)">Evaluations</div>
    </div>
    <div style="background:#FEF2F2;border:1px solid #FECACA;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--c24-red)">${totalIssues}</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-red)">🔴 Issues Found</div>
    </div>
    <div style="background:#F0FDF4;border:1px solid #BBF7D0;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--green)">${totalPositives}</div>
      <div style="font-size:11px;font-weight:700;color:var(--green)">✅ Positives</div>
    </div>
    <div style="background:${satPct>=70?'#F0FDF4':'#FEF2F2'};border:1px solid ${satPct>=70?'#BBF7D0':'#FECACA'};border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:${satPct>=70?'var(--green)':'var(--c24-red)'}">${satPct}%</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-grey-500)">Satisfied</div>
    </div>
    <div style="background:#FFF7ED;border:1px solid #FED7AA;border-radius:var(--radius);padding:14px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:#EA580C">${unhappyCount}</div>
      <div style="font-size:11px;font-weight:700;color:#EA580C">🟠 Unhappy</div>
    </div>
  </div>`;

  // ── Top Customer Issues (Key Issues at a Glance)
  const sortedIssues = Object.entries(issues).sort((a,b) => b[1].count - a[1].count);
  if (sortedIssues.length) {
    html += `<div style="background:#FEF2F2;border:1.5px solid #FECACA;border-left:4px solid var(--c24-red);border-radius:var(--radius);padding:16px 18px;margin-bottom:18px">
      <div style="font-size:13px;font-weight:800;color:var(--c24-red);margin-bottom:12px">🔴 Top Customer Issues — Quick View</div>
      <div style="display:flex;flex-direction:column;gap:8px">
        ${sortedIssues.map(([cat, d]) => {
          const sev = CF_SEVERITY[cat] || 'medium';
          const st  = CF_SEVERITY_STYLE[sev];
          const pct = evals.length ? Math.round(d.count/evals.length*100) : 0;
          return `<div style="display:flex;align-items:center;gap:10px;padding:8px 12px;background:#fff;border-radius:var(--radius-sm);border:1px solid #FECACA">
            <span style="font-size:12px;font-weight:800;flex:1;color:var(--c24-black)">${cat}</span>
            <div style="width:80px;height:5px;border-radius:3px;background:#EBEBEB;overflow:hidden">
              <div style="height:100%;width:${Math.min(pct*2,100)}%;background:${st.color};border-radius:3px"></div>
            </div>
            <span style="font-size:12px;font-weight:900;color:${st.color};min-width:28px;text-align:right">${d.count}</span>
            <span style="font-size:10px;font-weight:800;padding:2px 8px;border-radius:20px;background:${st.bg};color:${st.color};white-space:nowrap">${st.badge}</span>
          </div>`;
        }).join('')}
      </div>
    </div>`;
  }

  // ── Overall Experience Distribution
  html += `<div style="display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:18px">
    <div style="background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 16px">
      <div style="font-size:11px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500);margin-bottom:12px">⭐ Overall Experience Ratings</div>
      ${Object.entries(overallDist).sort((a,b)=>b[1]-a[1]).map(([rating, cnt]) => {
        const c = rating==='Excellent'?'var(--green)':rating==='Good'?'var(--blue)':rating==='Average'?'var(--amber)':'var(--c24-red)';
        const pct = evals.length ? Math.round(cnt/evals.length*100) : 0;
        return `<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px">
          <span style="font-size:11px;font-weight:700;min-width:70px;color:${c}">${rating}</span>
          <div style="flex:1;height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden">
            <div style="height:100%;width:${pct}%;background:${c};border-radius:3px"></div>
          </div>
          <span style="font-size:11px;font-weight:800;color:${c};min-width:30px;text-align:right">${cnt}</span>
        </div>`;
      }).join('')}
    </div>
    <div style="background:var(--c24-white);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 16px">
      <div style="font-size:11px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-grey-500);margin-bottom:12px">⏱ Wait Time Distribution</div>
      ${Object.entries(waitDist).sort((a,b)=>b[1]-a[1]).map(([wt, cnt]) => {
        const c = wt.includes('5 to 10')||wt.includes('< 5')?'var(--green)':wt.includes('10 to 15')?'var(--amber)':'var(--c24-red)';
        const pct = evals.length ? Math.round(cnt/evals.length*100) : 0;
        return `<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px">
          <span style="font-size:10px;font-weight:700;min-width:85px;color:${c}">${wt}</span>
          <div style="flex:1;height:6px;border-radius:3px;background:#EBEBEB;overflow:hidden">
            <div style="height:100%;width:${pct}%;background:${c};border-radius:3px"></div>
          </div>
          <span style="font-size:11px;font-weight:800;color:${c};min-width:24px;text-align:right">${cnt}</span>
        </div>`;
      }).join('')}
    </div>
  </div>`;

  // ── Category-wise Issue Breakdown
  html += `<div style="font-size:13px;font-weight:800;color:var(--c24-black);margin-bottom:12px">📊 Category-wise Feedback Breakdown</div>`;

  Object.entries(CF_CATEGORIES).forEach(([cat, keys]) => {
    const catIssues = issues[cat] || { count:0, items:[] };
    const catPos    = positives[cat] || { count:0, items:[] };
    const total     = catIssues.count + catPos.count;
    if (!total) return;
    const sev = CF_SEVERITY[cat] || 'medium';
    const st  = catIssues.count > catPos.count ? CF_SEVERITY_STYLE[sev] : CF_SEVERITY_STYLE.positive;
    const posPct = total ? Math.round(catPos.count/total*100) : 0;

    html += `<details style="margin-bottom:10px;border:1px solid ${catIssues.count?'#FECACA':'#BBF7D0'};border-left:4px solid ${catIssues.count?st.color:'var(--green)'};border-radius:var(--radius);overflow:hidden">
      <summary style="padding:10px 14px;cursor:pointer;background:${catIssues.count?'#FFF8F8':'#F9FFF9'};display:flex;align-items:center;gap:10px;list-style:none">
        <span style="font-size:12px;font-weight:800;color:var(--c24-black);flex:1">${cat}</span>
        ${catIssues.count?`<span style="font-size:10px;font-weight:800;background:#FEF2F2;color:var(--c24-red);padding:2px 8px;border-radius:10px">${st.badge} ${catIssues.count}</span>`:''}
        ${catPos.count?`<span style="font-size:10px;font-weight:800;background:#F0FDF4;color:var(--green);padding:2px 8px;border-radius:10px">✅ ${catPos.count}</span>`:''}
        <span style="font-size:10px;font-weight:800;color:${posPct>=70?'var(--green)':posPct>=40?'var(--amber)':'var(--c24-red)'}">${posPct}% positive</span>
        <span style="color:var(--c24-grey-400);font-size:12px">▼</span>
      </summary>
      <div style="padding:10px 14px;background:#fff">
        ${catIssues.items.length?`<div style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--c24-red);margin-bottom:6px">Issues (${catIssues.items.length})</div>`:''}
        ${catIssues.items.map(it => `<div style="display:flex;align-items:flex-start;gap:8px;padding:6px 10px;background:#FFF8F8;border-radius:var(--radius-sm);margin-bottom:4px;border-left:3px solid var(--c24-red)">
          <span style="font-size:10px;flex-shrink:0;margin-top:1px">⚠️</span>
          <div><div style="font-size:10px;font-weight:600;color:var(--c24-grey-700);margin-bottom:2px">${it.q.slice(0,70)}</div>
          <span style="font-size:11px;font-weight:800;color:var(--c24-red);padding:1px 8px;border-radius:20px;background:#FEF2F2">${it.ans}</span>
          <span style="font-size:10px;color:var(--c24-grey-400);margin-left:8px">${it.date}</span></div>
        </div>`).join('')}
        ${catPos.items.length?`<div style="font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--green);margin:8px 0 6px">Positives (${catPos.items.length})</div>`:''}
        ${catPos.items.map(it => `<div style="display:flex;align-items:flex-start;gap:8px;padding:6px 10px;background:#F0FDF4;border-radius:var(--radius-sm);margin-bottom:4px;border-left:3px solid var(--green)">
          <span style="font-size:10px;flex-shrink:0;margin-top:1px">✅</span>
          <div><div style="font-size:10px;font-weight:600;color:var(--c24-grey-700);margin-bottom:2px">${it.q.slice(0,70)}</div>
          <span style="font-size:11px;font-weight:800;color:var(--green);padding:1px 8px;border-radius:20px;background:#DCFCE7">${it.ans}</span>
          <span style="font-size:10px;color:var(--c24-grey-400);margin-left:8px">${it.date}</span></div>
        </div>`).join('')}
      </div>
    </details>`;
  });

  // ── Customer Comments Section
  const allComments = byEval.flatMap(e => e.comments.map(c => ({...c, date:e.date, evalId:e.id})));
  if (allComments.length) {
    // Categorize comments by operational keywords
    const opKeywords = {
      '👤 Staff Behaviour':    ['staff','employee','associate','rude','helpful','professional','behaviour','attitude'],
      '⏱ Waiting Time':       ['wait','time','delay','slow','quick','fast','immediate','long'],
      '🧹 Cleanliness':        ['clean','dirty','hygiene','dust','odour','smell','fresh','maintain'],
      '🅿 Parking':            ['parking','park','space','car','vehicle','area'],
      '🔍 Vehicle Inspection': ['inspection','quality','check','condition','damage','assess'],
      '📄 Documentation':      ['document','paper','process','form','sign','delay'],
      '💬 Communication':      ['communic','explain','inform','clear','vague','told','update','follow'],
      '💳 Payment':            ['payment','price','cost','fee','charge','refund','token'],
    };

    const categComments = {};
    allComments.forEach(c => {
      const txt = c.text.toLowerCase();
      let matched = false;
      for (const [cat, words] of Object.entries(opKeywords)) {
        if (words.some(w => txt.includes(w))) {
          if (!categComments[cat]) categComments[cat] = [];
          categComments[cat].push(c);
          matched = true;
          break;
        }
      }
      if (!matched) {
        if (!categComments['📝 General']) categComments['📝 General'] = [];
        categComments['📝 General'].push(c);
      }
    });

    html += `<div style="font-size:13px;font-weight:800;color:var(--c24-black);margin-top:20px;margin-bottom:12px">💬 Customer Comments & Observations (${allComments.length})</div>`;

    Object.entries(categComments).sort((a,b)=>b[1].length-a[1].length).forEach(([cat, comments]) => {
      html += `<details style="margin-bottom:10px;border:1px solid #EBEBEB;border-radius:var(--radius);overflow:hidden">
        <summary style="padding:10px 14px;cursor:pointer;background:var(--c24-grey-50);display:flex;align-items:center;gap:8px;list-style:none">
          <span style="font-size:12px;font-weight:800;color:var(--c24-black);flex:1">${cat}</span>
          <span style="font-size:10px;background:#EFF6FF;color:var(--blue);padding:2px 8px;border-radius:10px;font-weight:700">${comments.length} comments</span>
          <span style="color:var(--c24-grey-400);font-size:12px">▼</span>
        </summary>
        <div style="padding:10px 14px;background:#fff">
          ${comments.slice(0,5).map(c => {
            const txt = c.text.toLowerCase();
            const isNeg = ['not','issue','problem','poor','bad','dirty','delay','rude','fail','broken','missing','absent'].some(w=>txt.includes(w));
            const isPos = ['excellent','good','great','well','clean','professional','helpful','quick','clear','prompt'].some(w=>txt.includes(w));
            const borderC = isNeg ? 'var(--c24-red)' : isPos ? 'var(--green)' : 'var(--blue)';
            const bgC     = isNeg ? '#FFF8F8' : isPos ? '#F0FDF4' : '#F8FAFF';
            const badge   = isNeg ? '🔴' : isPos ? '🟢' : '🔵';
            return `<div style="padding:8px 12px;border-left:3px solid ${borderC};background:${bgC};border-radius:var(--radius-sm);margin-bottom:6px">
              <div style="display:flex;align-items:center;gap:6px;margin-bottom:4px">
                <span>${badge}</span>
                <span style="font-size:10px;font-weight:700;color:var(--c24-grey-500)">${c.topic.slice(0,50)} · ${c.date}</span>
              </div>
              <div style="font-size:11px;color:var(--c24-grey-700);line-height:1.6">"${c.text.slice(0,200)}${c.text.length>200?'…':''}"</div>
            </div>`;
          }).join('')}
          ${comments.length > 5 ? `<div style="font-size:10px;color:var(--c24-grey-400);font-style:italic;padding:4px 0">+${comments.length-5} more comments…</div>` : ''}
        </div>
      </details>`;
    });
  }

  // ── Per-Evaluation Feedback Summary
  html += `<div style="font-size:13px;font-weight:800;color:var(--c24-black);margin-top:20px;margin-bottom:12px">📋 Per-Visit Customer Experience</div>`;
  byEval.sort((a,b) => b.issueCount - a.issueCount).forEach(ev => {
    const scoreC = ev.score>=85?'var(--green)':ev.score>=70?'var(--amber)':'var(--c24-red)';
    const overallC = ev.overall==='Excellent'?'var(--green)':ev.overall==='Good'?'var(--blue)':ev.overall==='Average'?'var(--amber)':'var(--c24-red)';
    html += `<div style="background:#fff;border:1px solid #EBEBEB;border-left:3px solid ${ev.issueCount>3?'var(--c24-red)':ev.issueCount>1?'var(--amber)':'var(--green)'};border-radius:var(--radius-sm);padding:10px 14px;margin-bottom:8px">
      <div style="display:flex;align-items:center;gap:10px;flex-wrap:wrap;margin-bottom:${ev.issues.length||ev.positives.length?'8px':'0'}">
        <span style="font-size:13px;font-weight:900;color:${scoreC}">${ev.score.toFixed(1)}%</span>
        <span style="font-size:11px;font-weight:700;color:var(--c24-grey-500)">Eval #${ev.id} · ${ev.date}</span>
        <span style="font-size:11px;font-weight:700;color:${overallC}">${ev.overall}</span>
        <span style="font-size:10px;color:var(--c24-grey-400)">⏱ ${ev.waitTime}</span>
        ${ev.issueCount?`<span style="font-size:10px;font-weight:800;color:var(--c24-red);background:#FEF2F2;padding:2px 7px;border-radius:10px">⚠️ ${ev.issueCount} issues</span>`:''}
        ${ev.posCount?`<span style="font-size:10px;font-weight:800;color:var(--green);background:#F0FDF4;padding:2px 7px;border-radius:10px">✅ ${ev.posCount} positives</span>`:''}
      </div>
      ${ev.issues.length?`<div style="font-size:10px;color:var(--c24-red);line-height:1.8">${ev.issues.slice(0,3).map(i=>`⚠ ${i.cat}: <strong>${i.ans}</strong>`).join(' · ')}</div>`:''}
      ${ev.positives.length?`<div style="font-size:10px;color:var(--green);line-height:1.8;margin-top:2px">${ev.positives.slice(0,2).map(i=>`✅ ${i.cat}: <strong>${i.ans}</strong>`).join(' · ')}</div>`:''}
    </div>`;
  });

  return html;
}

// ─── MYSTERY AUDIT DEEP DIVE MODAL ───────────────────

// Q&A structure — define all question/comment pairs with polarity
const MA_QA = [
  // ENGAGEMENT
  { q: 'How much time does the sales staff take to attend you?', ci: '(Comments) How much time does the sales staff take to attend you?', group: 'Initial Engagement & Ownership', polarity: 'time' },
  { q: 'Was the first interaction initiated proactively by staff?', ci: '(Comments) Was the first interaction initiated proactively by staff?', group: 'Initial Engagement & Ownership', polarity: 'positive' },
  { q: 'Did one specific staff member clearly take ownership of your case?', ci: '(Comments) Did one specific staff member clearly take ownership of your case?', group: 'Initial Engagement & Ownership', polarity: 'positive' },
  { q: 'At any point, did you feel your case lacked clear ownership', ci: '(Comments) At any point, did you feel your case lacked clear ownership', group: 'Initial Engagement & Ownership', polarity: 'negative' },
  { q: 'Did you have to repeat your requirement to multiple staff members?', ci: '(Comments) Did you have to repeat your requirement to multiple staff members?', group: 'Initial Engagement & Ownership', polarity: 'negative' },
  // COMMUNICATION
  { q: 'Did the CA clearly explain the end-to-end process (selection to delivery)?', ci: '(Comments) Did the CA clearly explain the end-to-end process (selection to delivery)?', group: 'Communication & Process Clarity', polarity: 'positive' },
  { q: 'Did you leave with clear next steps?', ci: '(Comments) Did you leave with clear next steps?', group: 'Communication & Process Clarity', polarity: 'positive' },
  { q: 'Were timelines (delivery / booking / documentation) clearly communicated?', ci: '(Comments) Were timelines (delivery / booking / documentation) clearly communicated?', group: 'Communication & Process Clarity', polarity: 'positive' },
  { q: 'Did staff provide structured follow-up information (WhatsApp / SMS / call)?', ci: '(Comments) Did staff provide structured follow-up information (WhatsApp / SMS / call)?', group: 'Communication & Process Clarity', polarity: 'positive' },
  { q: 'Were pricing components (vehicle cost, add-ons, taxes) explained transparently?', ci: '(Comments) Were pricing components (vehicle cost, add-ons, taxes) explained transparently?', group: 'Communication & Process Clarity', polarity: 'positive' },
  // BOOKING
  { q: 'Did the CA attempt to convert the visit into a booking?', ci: '(Comments) Did the CA attempt to convert the visit into a booking?', group: 'Booking & Conversion Behaviour', polarity: 'positive' },
  { q: 'Did the CA mention vehicle availability status or urgency', ci: '(Comments) Did the CA mention vehicle availability status or urgency', group: 'Booking & Conversion Behaviour', polarity: 'positive' },
  { q: 'Was booking policy (token / refund / process) clearly explained?', ci: '(Comments) Was booking policy (token / refund / process) clearly explained?', group: 'Booking & Conversion Behaviour', polarity: 'positive' },
  { q: 'Did you feel pressured to book?', ci: '(Comments) Did you feel pressured to book?', group: 'Booking & Conversion Behaviour', polarity: 'negative' },
  { q: 'Would you consider booking after this visit?', ci: '(Comments) Would you consider booking after this visit?', group: 'Booking & Conversion Behaviour', polarity: 'positive' },
  // TEST DRIVE
  { q: 'Was the preferred car available?', ci: '(Comments) Was the preferred car available?', group: 'Test Drive Experience', polarity: 'positive' },
  { q: 'Time taken to arrange a test drive?', ci: '(Comments) Time taken to arrange a test drive?', group: 'Test Drive Experience', polarity: 'time' },
  { q: 'Did staff accompany and guide during the test drive', ci: '(Comments) Did staff accompany and guide during the test drive', group: 'Test Drive Experience', polarity: 'positive' },
  { q: 'After the test drive, was there a structured closure discussion?', ci: '(Comments) After the test drive, was there a structured closure discussion?', group: 'Test Drive Experience', polarity: 'positive' },
  // PROFESSIONALISM
  { q: 'Was the CA respectful and patient throughout the interaction?', ci: '(Comments) Was the CA respectful and patient throughout the interaction?', group: 'Professionalism & Behavioural Signals', polarity: 'positive' },
  { q: 'Did staff actively listen to your requirements?', ci: '(Comments) Did staff actively listen to your requirements?', group: 'Professionalism & Behavioural Signals', polarity: 'positive' },
  { q: 'Did the CA demonstrate strong product knowledge?', ci: '(Comments) Did the CA demonstrate strong product knowledge?', group: 'Professionalism & Behavioural Signals', polarity: 'positive' },
  { q: 'Did you observe coordination issues among staff', ci: '(Comments) Did you observe coordination issues among staff', group: 'Professionalism & Behavioural Signals', polarity: 'negative' },
  { q: 'Based on your entire interaction (excluding infra), how would you rate the overall service experience?', ci: '(Comments) Based on your entire interaction (excluding infra), how would you rate the overall service experience?', group: 'Overall Experience Reflection', polarity: 'positive' },
  // INFRA - DISCOVERY
  { q: 'Google Listing & New Logo Accuracy', ci: '(Comments) Google Listing & New Logo Accuracy', group: 'Discovery', polarity: 'infra' },
  { q: 'Exterior Branding & New Logo Visibility', ci: '(Comments) Exterior Branding & New Logo Visibility', group: 'Discovery', polarity: 'infra' },
  // INFRA - ENTRY / CUSTOMER AREA
  { q: 'Entry Accessibility & Wheelchair Readiness', ci: '(Comments) Entry Accessibility & Wheelchair Readiness', group: 'Entry', polarity: 'infra' },
  { q: 'Music & Ambient Environment', ci: '(Comments) Music & Ambient Environment', group: 'Customer Area', polarity: 'infra' },
  { q: 'Diffuser & Fragrance Control', ci: '(Comments) Diffuser & Fragrance Control', group: 'Customer Area', polarity: 'infra' },
  { q: 'Customer Area Operational Condition.', ci: '(Comments) Customer Area Operational Condition.', group: 'Customer Area', polarity: 'infra' },
  { q: 'Odour & Air Quality', ci: '(Comments) Odour & Air Quality', group: 'Customer Area', polarity: 'infra' },
  { q: 'Car Cleaning Area Maintenance', ci: '(Comments) Car Cleaning Area Maintenance', group: 'Movement Across Hub', polarity: 'infra' },
  { q: 'Yard Discipline & Vehicle Display', ci: '(Comments) Yard Discipline & Vehicle Display', group: 'Yard Viewing', polarity: 'infra' },
  { q: 'Customer Associate Professionalism & Communication', ci: '(Comments) Customer Associate Professionalism & Communication', group: 'Staff Interaction & Exit', polarity: 'infra' },
];

// Classify an answer as positive / negative / neutral
function classifyAnswer(answer, polarity) {
  const a = (answer || '').toLowerCase().trim();
  if (!a || a === '-' || a === 'n/a' || a === 'na' || a === 'not applicable') return 'neutral';
  if (polarity === 'negative') {
    // For negative questions: YES = bad, NO = good
    if (a === 'yes') return 'negative';
    if (a === 'no')  return 'positive';
    return 'neutral';
  }
  if (polarity === 'time') return 'neutral';
  if (polarity === 'infra') {
    const pos = ['yes','excellent','good','strong','clearly communicated','clearly explained','fully explained','definitely'];
    const neg = ['no','poor','weak','not explained','not discussed','not available','vague','partial','partially','partially explained','no attempt','na (incase of booked visits)'];
    if (pos.some(p => a.includes(p))) return 'positive';
    if (neg.some(p => a.includes(p))) return 'negative';
    return 'neutral';
  }
  // positive polarity
  const posWords = ['yes','excellent','good','strong','strong attempt','definitely','clearly communicated','clearly explained','fully explained','moderate attempt','maybe','alternative offered'];
  const negWords = ['no','poor','weak','vague','not explained','not discussed','not available','no attempt','partial','partially','partially explained'];
  if (posWords.some(p => a.includes(p))) return 'positive';
  if (negWords.some(p => a.includes(p))) return 'negative';
  return 'neutral';
}

let _maModalHub = '';
let _maModalTab = 'summary';

function openMaModal(encodedHub) {
  _maModalHub = decodeURIComponent(encodedHub);
  _maModalTab = 'summary';
  const modal = document.getElementById('ma-modal');
  modal.style.display = 'flex';
  modal.onclick = e => { if (e.target === modal) closeMaModal(); };
  document.addEventListener('keydown', _maEscHandler);
  renderMaModal();
}

function _maEscHandler(e) { if (e.key === 'Escape') closeMaModal(); }
function closeMaModal() {
  document.getElementById('ma-modal').style.display = 'none';
  document.removeEventListener('keydown', _maEscHandler);
}

function switchMaTab(tab) {
  _maModalTab = tab;
  document.querySelectorAll('.ma-tab').forEach(t => {
    const isActive = t.id === 'ma-tab-' + tab;
    t.style.color       = isActive ? 'var(--c24-red)' : 'var(--c24-grey-500)';
    t.style.borderBottom= isActive ? '2px solid var(--c24-red)' : '2px solid transparent';
  });
  renderMaModalBody();
}

function renderMaModal() {
  const hub   = _maModalHub;
  const evals = STATE.mysteryData.filter(r => (r['Location Name']||'').trim() === hub);
  if (!evals.length) return;

  const scores = evals.map(r => parseFloat(r['Evaluation Score'])||0);
  const avgScore = scores.reduce((s,v)=>s+v,0)/scores.length;
  const city  = evals[0]['Location City'] || '';

  // HEM lookup
  const hemLookup = {};
  STATE.tickets.forEach(t => { if (t.Store && t['HEM NAME']) hemLookup[t.Store.trim()] = t['HEM NAME'].trim(); });
  const getHEM = (h) => {
    if (hemLookup[h]) return hemLookup[h];
    const hl = h.toLowerCase();
    for (const [s, hem] of Object.entries(hemLookup)) {
      const sl = s.toLowerCase();
      if (hl.includes(sl.slice(0,20)) || sl.includes(hl.slice(0,20))) return hem;
    }
    return '—';
  };
  const hem = getHEM(hub);
  const perf = avgScore >= 85 ? { label:'🟢 Best', color:'#16A34A', bg:'#DCFCE7' } : avgScore >= 70 ? { label:'🟡 Average', color:'#D97706', bg:'#FEF3C7' } : { label:'🔴 Poor', color:'#E52529', bg:'#FEE2E2' };

  // Update header
  document.getElementById('ma-modal-title').textContent = hub;
  document.getElementById('ma-modal-meta').textContent = `${city} · ${evals.length} evaluation${evals.length>1?'s':''} · HEM: ${hem}`;
  const pb = document.getElementById('ma-modal-perf-badge');
  pb.textContent = perf.label + ' · ' + avgScore.toFixed(1);
  pb.style.background = perf.bg; pb.style.color = perf.color;

  // Category score bar strip
  const catAvgs = {};
  MA_CATS.forEach(cat => {
    const vals = evals.map(r => parseFloat(r[cat])).filter(v => !isNaN(v));
    catAvgs[cat] = vals.length ? vals.reduce((s,v)=>s+v,0)/vals.length : null;
  });
  document.getElementById('ma-modal-scores').innerHTML = [
    `<span style="font-size:18px;font-weight:900;color:${perf.color};margin-right:8px">${avgScore.toFixed(1)}</span>`,
    `<span style="font-size:10px;color:rgba(255,255,255,.4);font-weight:600;margin-right:12px;white-space:nowrap">OVERALL</span>`,
    ...MA_CATS.map(cat => {
      const v = catAvgs[cat];
      const c = v===null?'#555': v>=85?'#16A34A':v>=70?'#D97706':'#E52529';
      return `<div style="display:flex;flex-direction:column;align-items:center;gap:2px;min-width:70px">
        <span style="font-size:15px;font-weight:800;color:${c}">${v!==null?v.toFixed(0):'—'}</span>
        <span style="font-size:8px;color:rgba(255,255,255,.4);text-align:center;line-height:1.2;max-width:70px">${cat}</span>
      </div>`;
    })
  ].join('');

  // Set tab state and render body
  switchMaTab('summary');
}

function renderMaModalBody() {
  const hub   = _maModalHub;
  const evals = STATE.mysteryData.filter(r => (r['Location Name']||'').trim() === hub);
  const body  = document.getElementById('ma-modal-body');
  const tab   = _maModalTab;

  if (tab === 'summary')   { body.innerHTML = renderMaSummary(evals); return; }
  if (tab === 'customer')  { body.innerHTML = renderMaCustomerFeedback(evals, _maModalHub); return; }
  if (tab === 'positive')  { body.innerHTML = renderMaFeedback(evals, 'positive'); return; }
  if (tab === 'negative')  { body.innerHTML = renderMaFeedback(evals, 'negative'); return; }
  if (tab === 'responses') { body.innerHTML = renderMaAllResponses(evals); return; }
  if (tab === 'evals')     { body.innerHTML = renderMaEvalList(evals); return; }
}

function renderMaSummary(evals) {
  // Count positive/negative per question across all evals
  const qStats = MA_QA.map(qa => {
    let pos=0, neg=0, neu=0, comments=[];
    evals.forEach(r => {
      const ans = (r[qa.q] || '').trim();
      const com = (r[qa.ci] || '').trim();
      const cls = classifyAnswer(ans, qa.polarity);
      if (cls==='positive') pos++;
      else if (cls==='negative') neg++;
      else neu++;
      if (com && com.length > 3 && !/^(https?:|WhatsApp)/i.test(com)) comments.push(com);
    });
    return { ...qa, pos, neg, neu, total: evals.length, comments };
  });

  // Group by category
  const groups = {};
  qStats.forEach(s => {
    if (!groups[s.group]) groups[s.group] = [];
    groups[s.group].push(s);
  });

  let html = '';

  // Quick stats row
  const totalPos = qStats.reduce((s,q)=>s+q.pos,0);
  const totalNeg = qStats.reduce((s,q)=>s+q.neg,0);
  const totalQs  = qStats.reduce((s,q)=>s+q.total,0);
  html += `<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:12px;margin-bottom:20px">
    <div style="background:var(--green-light);border:1px solid #BBF7D0;border-radius:var(--radius);padding:14px 16px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--green)">${totalPos}</div>
      <div style="font-size:11px;font-weight:700;color:var(--green)">✅ Positive Responses</div>
    </div>
    <div style="background:var(--c24-red-light);border:1px solid #FECACA;border-radius:var(--radius);padding:14px 16px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--c24-red)">${totalNeg}</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-red)">⚠️ Issues Found</div>
    </div>
    <div style="background:var(--c24-grey-50);border:1px solid #EBEBEB;border-radius:var(--radius);padding:14px 16px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--c24-grey-700)">${evals.length}</div>
      <div style="font-size:11px;font-weight:700;color:var(--c24-grey-500)">Evaluations</div>
    </div>
    <div style="background:var(--blue-light);border:1px solid #BFDBFE;border-radius:var(--radius);padding:14px 16px;text-align:center">
      <div style="font-size:28px;font-weight:900;color:var(--blue)">${totalQs}</div>
      <div style="font-size:11px;font-weight:700;color:var(--blue)">Total Responses</div>
    </div>
  </div>`;

  // Per category summary
  Object.entries(groups).forEach(([grp, qs]) => {
    const grpPos = qs.reduce((s,q)=>s+q.pos,0);
    const grpNeg = qs.reduce((s,q)=>s+q.neg,0);
    const grpTotal = qs.reduce((s,q)=>s+q.total,0);
    const pct = grpTotal ? Math.round(grpPos/grpTotal*100) : 0;
    const barC = pct>=75?'var(--green)':pct>=50?'var(--amber)':'var(--c24-red)';
    html += `<div style="margin-bottom:20px">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:8px;gap:8px">
        <div style="font-size:12px;font-weight:800;color:var(--c24-black)">${grp}</div>
        <div style="display:flex;align-items:center;gap:6px;flex-shrink:0">
          <span style="font-size:10px;font-weight:700;color:var(--green)">✅ ${grpPos}</span>
          <span style="font-size:10px;color:var(--c24-grey-300)">|</span>
          <span style="font-size:10px;font-weight:700;color:var(--c24-red)">⚠️ ${grpNeg}</span>
          <span style="font-size:11px;font-weight:800;color:${barC};margin-left:4px">${pct}%</span>
        </div>
      </div>`;
    qs.forEach(q => {
      const pctQ = q.total ? Math.round(q.pos/q.total*100) : 0;
      const qBar = pctQ>=75?'var(--green)':pctQ>=50?'var(--amber)':'var(--c24-red)';
      html += `<div style="padding:8px 12px;background:var(--c24-grey-50);border-radius:var(--radius-sm);margin-bottom:6px;border-left:3px solid ${q.neg>q.pos?'var(--c24-red)':q.pos>0?'var(--green)':'#EBEBEB'}">
        <div style="display:flex;justify-content:space-between;align-items:flex-start;gap:8px;margin-bottom:4px">
          <span style="font-size:11px;font-weight:600;color:var(--c24-black);flex:1;line-height:1.3">${q.q}</span>
          <span style="font-size:10px;font-weight:800;color:${qBar};white-space:nowrap">${pctQ}% positive</span>
        </div>
        <div style="display:flex;gap:12px;align-items:center">
          <div style="flex:1;height:4px;border-radius:2px;background:#EBEBEB;overflow:hidden">
            <div style="height:100%;width:${pctQ}%;background:${qBar};border-radius:2px"></div>
          </div>
          <span style="font-size:10px;color:var(--green);font-weight:700">✅${q.pos}</span>
          <span style="font-size:10px;color:var(--c24-red);font-weight:700">⚠️${q.neg}</span>
          <span style="font-size:10px;color:var(--c24-grey-400);font-weight:600">~${q.neu}</span>
        </div>
        ${q.comments.length ? `<div style="margin-top:6px;font-size:10px;color:var(--c24-grey-600);font-style:italic;line-height:1.5;border-top:1px solid #E8E8E8;padding-top:4px">"${q.comments[0].slice(0,160)}${q.comments[0].length>160?'…':''}"</div>` : ''}
      </div>`;
    });
    html += `</div>`;
  });
  return html;
}

function renderMaFeedback(evals, type) {
  // Collect all instances where answer was positive/negative, with comments
  const items = [];
  MA_QA.forEach(qa => {
    evals.forEach((r, ei) => {
      const ans = (r[qa.q] || '').trim();
      const com = (r[qa.ci] || '').trim();
      const cls = classifyAnswer(ans, qa.polarity);
      if (cls !== type) return;
      // Filter out URL-only comments
      const cleanCom = com.replace(/https?:\/\/\S+/g,'').replace(/\s+/g,' ').trim();
      items.push({
        q: qa.q, group: qa.group, answer: ans,
        comment: cleanCom.length > 3 ? cleanCom : '',
        date: r['Evaluation Date'] || '', evalId: r['Evaluation ID'] || ''
      });
    });
  });

  if (!items.length) {
    return `<div style="text-align:center;padding:40px;color:var(--c24-grey-500);font-size:13px">
      ${type==='positive'?'No positive responses recorded yet.':'No issues found — great hub! ✅'}
    </div>`;
  }

  // Group by question
  const byQ = {};
  items.forEach(it => {
    if (!byQ[it.q]) byQ[it.q] = { group: it.group, items: [] };
    byQ[it.q].items.push(it);
  });

  const accent = type === 'positive' ? 'var(--green)' : 'var(--c24-red)';
  const bgCol  = type === 'positive' ? '#F0FDF4' : '#FFF8F8';
  const icon   = type === 'positive' ? '✅' : '⚠️';

  let html = `<div style="margin-bottom:12px;font-size:11px;font-weight:700;color:var(--c24-grey-500)">${icon} ${items.length} ${type} response${items.length!==1?'s':''} across ${Object.keys(byQ).length} questions</div>`;

  Object.entries(byQ).forEach(([q, data]) => {
    html += `<div style="margin-bottom:16px;border-radius:var(--radius);overflow:hidden;border:1px solid ${type==='positive'?'#BBF7D0':'#FECACA'}">
      <div style="background:${bgCol};padding:10px 14px;display:flex;align-items:flex-start;justify-content:space-between;gap:8px;border-bottom:1px solid ${type==='positive'?'#BBF7D0':'#FECACA'}">
        <div>
          <div style="font-size:9px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:${accent};margin-bottom:2px">${data.group}</div>
          <div style="font-size:12px;font-weight:700;color:var(--c24-black);line-height:1.3">${q}</div>
        </div>
        <span style="background:${accent};color:#fff;font-size:11px;font-weight:800;padding:2px 9px;border-radius:20px;flex-shrink:0">${data.items.length}×</span>
      </div>
      <div style="background:#fff">`;
    data.items.forEach((it, i) => {
      html += `<div style="padding:8px 14px;${i<data.items.length-1?'border-bottom:1px solid #F5F5F5':''}">
        <div style="display:flex;align-items:center;gap:8px;flex-wrap:wrap">
          <span style="font-size:10px;font-weight:800;color:${accent};background:${bgCol};padding:2px 8px;border-radius:20px">${it.answer}</span>
          <span style="font-size:10px;color:var(--c24-grey-400)">Eval #${it.evalId} · ${it.date}</span>
        </div>
        ${it.comment ? `<div style="font-size:11px;color:var(--c24-grey-700);margin-top:5px;line-height:1.6;font-style:italic;padding:6px 10px;background:var(--c24-grey-50);border-radius:6px;border-left:2px solid ${accent}">"${it.comment}"</div>` : ''}
      </div>`;
    });
    html += `</div></div>`;
  });
  return html;
}

function renderMaAllResponses(evals) {
  let html = `<div style="margin-bottom:12px;font-size:11px;font-weight:700;color:var(--c24-grey-500)">${evals.length} evaluation${evals.length!==1?'s':''} · All customer Q&A responses with comments</div>`;

  MA_QA.forEach(qa => {
    // Collect answers across all evals
    const answers = evals.map(r => ({
      answer: (r[qa.q]||'').trim(),
      comment: (r[qa.ci]||'').replace(/https?:\/\/\S+/g,'').replace(/\s+/g,' ').trim(),
      date: r['Evaluation Date']||'', evalId: r['Evaluation ID']||''
    })).filter(a => a.answer && a.answer !== '-');

    if (!answers.length) return;

    // Tally
    const pos = answers.filter(a => classifyAnswer(a.answer, qa.polarity)==='positive').length;
    const neg = answers.filter(a => classifyAnswer(a.answer, qa.polarity)==='negative').length;
    const borderC = neg > pos ? 'var(--c24-red)' : pos > 0 ? 'var(--green)' : '#EBEBEB';

    html += `<div style="margin-bottom:14px;border:1px solid #EBEBEB;border-left:3px solid ${borderC};border-radius:var(--radius-sm);overflow:hidden">
      <div style="padding:8px 12px;background:var(--c24-grey-50);display:flex;justify-content:space-between;align-items:flex-start;gap:8px;border-bottom:1px solid #EBEBEB">
        <div>
          <div style="font-size:9px;font-weight:800;text-transform:uppercase;letter-spacing:.4px;color:var(--c24-grey-500);margin-bottom:1px">${qa.group}</div>
          <div style="font-size:11px;font-weight:700;color:var(--c24-black);line-height:1.3">${qa.q}</div>
        </div>
        <div style="display:flex;gap:6px;flex-shrink:0">
          ${pos>0?`<span style="font-size:9px;font-weight:800;color:var(--green)">✅${pos}</span>`:''}
          ${neg>0?`<span style="font-size:9px;font-weight:800;color:var(--c24-red)">⚠️${neg}</span>`:''}
        </div>
      </div>
      <div style="padding:0">`;
    answers.forEach((a, i) => {
      const cls = classifyAnswer(a.answer, qa.polarity);
      const aColor = cls==='positive'?'var(--green)':cls==='negative'?'var(--c24-red)':'var(--c24-grey-500)';
      const aBg    = cls==='positive'?'var(--green-light)':cls==='negative'?'var(--c24-red-light)':'var(--c24-grey-100)';
      html += `<div style="padding:7px 12px;${i<answers.length-1?'border-bottom:1px solid #F5F5F5':''}">
        <div style="display:flex;align-items:flex-start;gap:8px;flex-wrap:wrap">
          <span style="font-size:10px;font-weight:800;padding:2px 8px;border-radius:20px;background:${aBg};color:${aColor};white-space:nowrap">${a.answer}</span>
          <span style="font-size:10px;color:var(--c24-grey-400)">Eval #${a.evalId} · ${a.date}</span>
        </div>
        ${a.comment&&a.comment.length>3?`<div style="font-size:11px;color:var(--c24-grey-700);margin-top:4px;line-height:1.5;font-style:italic">"${a.comment}"</div>`:''}
      </div>`;
    });
    html += `</div></div>`;
  });
  return html;
}

function renderMaEvalList(evals) {
  let html = `<div style="margin-bottom:12px;font-size:11px;font-weight:700;color:var(--c24-grey-500)">${evals.length} individual evaluation${evals.length!==1?'s':''} — click to expand</div>`;

  evals.forEach((r, ei) => {
    const score = parseFloat(r['Evaluation Score'])||0;
    const perf  = score>=85?{c:'var(--green)',bg:'var(--green-light)'}:score>=70?{c:'var(--amber)',bg:'var(--amber-light)'}:{c:'var(--c24-red)',bg:'var(--c24-red-light)'};
    const posCount = MA_QA.filter(qa => classifyAnswer((r[qa.q]||'').trim(), qa.polarity)==='positive').length;
    const negCount = MA_QA.filter(qa => classifyAnswer((r[qa.q]||'').trim(), qa.polarity)==='negative').length;

    html += `<details style="margin-bottom:10px;border:1px solid #EBEBEB;border-radius:var(--radius);overflow:hidden">
      <summary style="padding:12px 16px;cursor:pointer;display:flex;align-items:center;gap:10px;flex-wrap:wrap;list-style:none;background:var(--c24-grey-50)">
        <span style="font-weight:900;font-size:15px;color:${perf.c}">${score}</span>
        <span style="font-size:12px;font-weight:700;flex:1">Eval #${r['Evaluation ID']} · ${r['Evaluation Date']}</span>
        <span style="font-size:10px;color:var(--c24-grey-500)">${r['Day']||''} · ${r['Gender']||''} · ${r['Visit type']||r['Visit type']||''}</span>
        <span style="font-size:10px;font-weight:700;color:var(--green)">✅${posCount}</span>
        <span style="font-size:10px;font-weight:700;color:var(--c24-red)">⚠️${negCount}</span>
        <span style="font-size:10px;color:var(--c24-grey-400)">▼</span>
      </summary>
      <div style="padding:12px 16px">
        ${MA_QA.map(qa => {
          const ans = (r[qa.q]||'').trim();
          const com = (r[qa.ci]||'').replace(/https?:\/\/\S+/g,'').replace(/\s+/g,' ').trim();
          if (!ans || ans==='-') return '';
          const cls = classifyAnswer(ans, qa.polarity);
          const ac  = cls==='positive'?'var(--green)':cls==='negative'?'var(--c24-red)':'var(--c24-grey-500)';
          const ab  = cls==='positive'?'var(--green-light)':cls==='negative'?'var(--c24-red-light)':'var(--c24-grey-100)';
          const icon= cls==='positive'?'✅':cls==='negative'?'⚠️':'·';
          return `<div style="display:flex;align-items:flex-start;gap:8px;padding:5px 0;border-bottom:1px solid #F5F5F5;flex-wrap:wrap">
            <span style="font-size:10px;min-width:14px">${icon}</span>
            <span style="font-size:11px;color:var(--c24-grey-700);flex:1;line-height:1.4">${qa.q}</span>
            <span style="font-size:10px;font-weight:700;padding:1px 7px;border-radius:20px;background:${ab};color:${ac};white-space:nowrap">${ans}</span>
            ${com&&com.length>3?`<div style="width:100%;font-size:10px;color:var(--c24-grey-500);font-style:italic;padding-left:22px;line-height:1.5">"${com.slice(0,200)}${com.length>200?'…':''}"</div>`:''}
          </div>`;
        }).join('')}
      </div>
    </details>`;
  });
  return html;
}

// ─── EXPORT ───────────────────────────────────────────
function downloadCSV() {
  if (!STATE.tickets.length && !STATE.checklist.length) { alert('No data to export.'); return; }

  let csv = '';
  if (STATE.tickets.length) {
    const data = getFilteredTickets();
    csv += 'Ticket Report\n';
    csv += 'ID,Title,Status,Priority,Department,Store,HEM NAME,Created At,TAT_Days\n';
    data.forEach(r => {
      const t = calcTAT(r);
      csv += [r.ID, `"${(r.Title||'').replace(/"/g,'""')}"`, r.Status, r.Priority, r.Department, `"${(r.Store||'').replace(/"/g,'""')}"`, r['HEM NAME']||'', r['Created At']||'', t].join(',') + '\n';
    });
  }
  if (STATE.checklist.length) {
    csv += '\nChecklist Report\n';
    csv += 'ID,Store,Employee,Audit Score,Filled By,Starting At,Completed At\n';
    STATE.checklist.forEach(r => {
      csv += [r.ID, `"${(r.Store||'').replace(/"/g,'""')}"`, `"${(r.Employee||'').replace(/"/g,'""')}"`, r['Audit Scoe']||'', r['Filled By']||'', r['Starting At']||'', r['Completed At']||''].join(',') + '\n';
    });
  }

  const blob = new Blob([csv], { type: 'text/csv' });
  const a    = Object.assign(document.createElement('a'), { href: URL.createObjectURL(blob), download: `HEM_Report_${new Date().toISOString().slice(0,10)}.csv` });
  a.click();
}

function downloadHTML() {
  const clone = document.documentElement.outerHTML;
  const blob  = new Blob([clone], { type: 'text/html' });
  const a     = Object.assign(document.createElement('a'), { href: URL.createObjectURL(blob), download: `HEM_Dashboard_${new Date().toISOString().slice(0,10)}.html` });
  a.click();
}

function clearAll() {
  if (!confirm('Clear all uploaded data and reset the dashboard?')) return;

  STATE.tickets   = [];
  STATE.checklist = [];

  // Reset upload zones
  ['zone-tickets','zone-tickets-2'].forEach(id => { const z = document.getElementById(id); if(z) z.classList.remove('loaded'); });
  ['zone-checklist','zone-cl-2'].forEach(id => { const z = document.getElementById(id); if(z) z.classList.remove('loaded'); });
  ['fname-tickets','fname-tickets-2'].forEach(id => { const z = document.getElementById(id); if(z) z.textContent = 'Upload Ticket CSV'; });
  ['fname-checklist','fname-cl-2'].forEach(id => { const z = document.getElementById(id); if(z) z.textContent = 'Upload Checklist CSV'; });
  ['file-tickets','file-tickets-2','file-checklist','file-checklist-2'].forEach(id => { const f = document.getElementById(id); if(f) f.value=''; });

  // Reset dashboards
  document.getElementById('ticket-dashboard').innerHTML = `<div class="empty-state"><div class="empty-state-icon">🎫</div><h3>No ticket data loaded</h3><p>Upload your Ticket CSV file above to see the analysis</p></div>`;
  document.getElementById('checklist-dashboard').innerHTML = `<div class="empty-state"><div class="empty-state-icon">✅</div><h3>No checklist data loaded</h3><p>Upload your Checklist CSV file above to see the comparison</p></div>`;

  // Destroy charts
  Object.keys(STATE.charts).forEach(destroyChart);

  // Reset filters
  document.getElementById('ticket-filters').classList.remove('visible');
  ['f-dept','f-hem','f-store','f-type','f-raised-by','f-zone','f-status','f-tat-sort','f-from','f-to'].forEach(id => { const el = document.getElementById(id); if(el) el.value=''; });

  updateTopbarMeta();
}

// ─── INIT ─────────────────────────────────────────────
document.addEventListener('DOMContentLoaded', () => {
  // Set today's date as default
  const td = TODAY.toISOString().slice(0,10);
  document.getElementById('f-to').value = td;
  renderTimeline();
});

// ─── TICKET DETAIL MODAL ─────────────────────────────
let _modalTickets  = [];   // all tickets for current view (pre-filter)
let _modalSort     = { col: 'tat', dir: 'desc' }; // default: highest TAT first
let _modalContext  = { type: 'hem', key: '' };     // tracks what opened the modal

// ── Column definitions for modal table
const MODAL_COLS = [
  { key: 'id',       label: 'ID',         style: 'white-space:nowrap' },
  { key: 'title',    label: 'Title',      style: '' },
  { key: 'priority', label: 'Priority',   style: 'white-space:nowrap' },
  { key: 'store',    label: 'Store',      style: 'white-space:nowrap' },
  { key: 'created',  label: 'Created',    style: 'white-space:nowrap' },
  { key: 'tat',      label: 'TAT (Days)', style: 'white-space:nowrap' },
];

// ── Populate HEM switcher dropdown
function populateModalHemSelect(currentHem, currentType) {
  const hems = [...new Set(STATE.tickets.map(r => r['HEM NAME']).filter(Boolean))].sort();
  const sel  = document.getElementById('modal-hem-select');
  sel.innerHTML = hems.map(h => `<option value="${h}" ${h === currentHem ? 'selected' : ''}>${h}</option>`).join('');
  document.getElementById('modal-hem-status').value = currentType || 'open';
  document.getElementById('modal-hem-wrap').style.display = 'flex';
}

// ── Called when HEM switcher changes
function switchModalHem() {
  const hem    = document.getElementById('modal-hem-select').value;
  const type   = document.getElementById('modal-hem-status').value;
  const status = type === 'open' ? 'Open' : ['In Progress','In-Progress'];
  const tickets = STATE.tickets.filter(r => {
    if (r['HEM NAME'] !== hem) return false;
    return Array.isArray(status) ? status.includes(r.Status) : r.Status === status;
  });
  const label = type === 'open' ? 'Open' : 'In Progress';
  _modalContext = { type: 'hem', key: hem };
  _modalTickets = tickets;
  document.getElementById('modal-title').textContent = `${label} Tickets — ${hem}`;
  document.getElementById('modal-search').value = '';
  document.getElementById('modal-priority').value = '';
  _modalSort = { col: 'tat', dir: 'desc' };
  renderModalHeader();
  filterModalTickets();
}

// ── Open from Hub table
function openHubTicketModal(encodedStore, type) {
  const store = decodeURIComponent(encodedStore);
  const status = type === 'open' ? 'Open' : ['In Progress','In-Progress'];
  const tickets = STATE.tickets.filter(r => {
    if (r.Store !== store) return false;
    return Array.isArray(status) ? status.includes(r.Status) : r.Status === status;
  });
  const label = type === 'open' ? 'Open' : 'In Progress';
  _modalContext = { type: 'store', key: store };
  showTicketModal(tickets, `${label} Tickets — ${store}`, false);
}

// ── Open from HEM-wise table
function openHemTicketModal(encodedHem, type) {
  const hem    = decodeURIComponent(encodedHem);
  const status = type === 'open' ? 'Open' : ['In Progress','In-Progress'];
  const tickets = STATE.tickets.filter(r => {
    if (r['HEM NAME'] !== hem) return false;
    return Array.isArray(status) ? status.includes(r.Status) : r.Status === status;
  });
  const label = type === 'open' ? 'Open' : 'In Progress';
  _modalContext = { type: 'hem', key: hem };
  showTicketModal(tickets, `${label} Tickets — ${hem}`, true, hem, type);
}

// ── Open from Dept-wise table
function openDeptTicketModal(encodedDept, type) {
  const dept   = decodeURIComponent(encodedDept);
  const status = type === 'open' ? 'Open' : ['In Progress','In-Progress'];
  const tickets = STATE.tickets.filter(r => {
    if (r.Department !== dept) return false;
    return Array.isArray(status) ? status.includes(r.Status) : r.Status === status;
  });
  const label = type === 'open' ? 'Open' : 'In Progress';
  _modalContext = { type: 'dept', key: dept };
  showTicketModal(tickets, `${label} Tickets — ${dept}`, false);
}

// ── Core: open modal
function showTicketModal(tickets, title, showHemSwitch = false, currentHem = '', currentType = 'open') {
  _modalTickets = tickets;
  _modalSort    = { col: 'tat', dir: 'desc' };   // reset sort each open
  document.getElementById('modal-title').textContent = title;
  document.getElementById('modal-search').value = '';
  document.getElementById('modal-priority').value = '';

  // HEM switcher visibility
  if (showHemSwitch) {
    populateModalHemSelect(currentHem, currentType);
  } else {
    document.getElementById('modal-hem-wrap').style.display = 'none';
  }

  renderModalHeader();
  filterModalTickets();

  const modal = document.getElementById('ticket-modal');
  modal.style.display = 'flex';
  modal.onclick = e => { if (e.target === modal) closeTicketModal(); };
  document.addEventListener('keydown', _modalEscHandler);
}

function _modalEscHandler(e) { if (e.key === 'Escape') closeTicketModal(); }

function closeTicketModal() {
  document.getElementById('ticket-modal').style.display = 'none';
  document.removeEventListener('keydown', _modalEscHandler);
}

// ── Render sticky sortable column headers
function renderModalHeader() {
  const thBase = 'padding:10px 14px;text-align:left;font-size:10px;font-weight:800;text-transform:uppercase;letter-spacing:.5px;background:var(--c24-grey-50);border-bottom:1px solid #EBEBEB;cursor:pointer;user-select:none;white-space:nowrap;';
  document.getElementById('modal-header-row').innerHTML = MODAL_COLS.map(c => {
    const active = _modalSort.col === c.key;
    const arrow  = active ? (_modalSort.dir === 'asc' ? ' ↑' : ' ↓') : ' ↕';
    const color  = active ? 'color:var(--c24-red);' : 'color:var(--c24-grey-500);';
    return `<th onclick="modalSortBy('${c.key}')" style="${thBase}${color}">${c.label}<span style="font-size:9px;margin-left:2px">${arrow}</span></th>`;
  }).join('');
}

// ── Column sort toggle
function modalSortBy(col) {
  if (_modalSort.col === col) {
    _modalSort.dir = _modalSort.dir === 'asc' ? 'desc' : 'asc';
  } else {
    _modalSort = { col, dir: col === 'tat' ? 'desc' : 'asc' };
  }
  renderModalHeader();
  filterModalTickets();
}

// ── Filter (search + priority) then sort then render
function filterModalTickets() {
  const q    = (document.getElementById('modal-search').value || '').toLowerCase();
  const pri  = document.getElementById('modal-priority').value;

  let filtered = _modalTickets;
  if (q)   filtered = filtered.filter(r => (r.ID||'').toLowerCase().includes(q) || (r.Title||'').toLowerCase().includes(q) || (r.Description||'').toLowerCase().includes(q));
  if (pri) filtered = filtered.filter(r => r.Priority === pri);

  document.getElementById('modal-sub').textContent =
    `${filtered.length}${filtered.length !== _modalTickets.length ? ' of ' + _modalTickets.length : ''} ticket${_modalTickets.length !== 1 ? 's' : ''}`;

  renderModalRows(filtered);
}

// ── Priority sort order for sorting
const PRIO_ORDER = { Urgent: 0, High: 1, Medium: 2, Low: 3 };

function renderModalRows(tickets) {
  const tbody = document.getElementById('modal-tbody');
  if (!tickets.length) {
    tbody.innerHTML = `<tr><td colspan="6" style="padding:32px;text-align:center;color:var(--c24-grey-500);font-size:12px;font-weight:600">No tickets match your search</td></tr>`;
    return;
  }

  // Apply column sort
  const { col, dir } = _modalSort;
  const flip = dir === 'asc' ? 1 : -1;
  const sorted = tickets.slice().sort((a, b) => {
    switch (col) {
      case 'id':       return flip * (parseInt(a.ID||0) - parseInt(b.ID||0));
      case 'title':    return flip * (a.Title||'').localeCompare(b.Title||'');
      case 'priority': return flip * ((PRIO_ORDER[a.Priority]??99) - (PRIO_ORDER[b.Priority]??99));
      case 'store':    return flip * (a.Store||'').localeCompare(b.Store||'');
      case 'created':  return flip * ((parseDate(a['Created At'])?.getTime()||0) - (parseDate(b['Created At'])?.getTime()||0));
      case 'tat':      return flip * (calcTAT(a) - calcTAT(b));
      default:         return flip * (calcTAT(a) - calcTAT(b));
    }
  });

  tbody.innerHTML = sorted.map(r => {
    const tat  = calcTAT(r);
    const tatC = tat <= 1 ? 'var(--green)' : tat <= 5 ? 'var(--amber)' : 'var(--c24-red)';
    const desc = (r.Description || '').replace(/</g,'&lt;').replace(/>/g,'&gt;');
    const shortDesc = desc.length > 140 ? desc.slice(0,140) + '…' : desc;
    const priColor = r.Priority==='High' ? 'background:var(--c24-red-light);color:var(--c24-red)' : r.Priority==='Urgent' ? 'background:#FFF7ED;color:var(--orange)' : 'background:var(--c24-grey-100);color:var(--c24-grey-700)';
    // Ticket-level TAT warning: > 7 days
    const ticketWarn = tat > 7;
    const rowStyle   = ticketWarn ? 'border-bottom:1px solid #FECACA;background:#FFF8F8;border-left:3px solid var(--c24-red);' : 'border-bottom:1px solid #F0F0F0;';
    return `<tr style="${rowStyle}" onmouseover="this.style.background='${ticketWarn ? '#FEF2F2' : 'var(--c24-grey-50)'}'" onmouseout="this.style.background='${ticketWarn ? '#FFF8F8' : ''}'">
      <td style="padding:10px 14px;font-weight:800;color:var(--c24-red);font-size:11px;white-space:nowrap">#${r.ID}${ticketWarn ? ' <span title="TAT exceeds 7 days" style="font-size:10px">⚠️</span>' : ''}</td>
      <td style="padding:10px 14px;max-width:300px">
        <div style="font-weight:700;font-size:12px;color:var(--c24-black);margin-bottom:3px;line-height:1.3">${(r.Title||'—').replace(/</g,'&lt;')}</div>
        ${shortDesc ? `<div style="font-size:11px;color:var(--c24-grey-500);line-height:1.5">${shortDesc}</div>` : ''}
      </td>
      <td style="padding:10px 14px;white-space:nowrap"><span style="font-size:10px;font-weight:800;padding:3px 9px;border-radius:20px;${priColor}">${r.Priority||'—'}</span></td>
      <td style="padding:10px 14px;font-size:11px;color:var(--c24-grey-700);max-width:160px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="${(r.Store||'').replace(/"/g,'')}">${r.Store||'—'}</td>
      <td style="padding:10px 14px;font-size:11px;color:var(--c24-grey-500);white-space:nowrap">${r['Created At']||'—'}</td>
      <td style="padding:10px 14px;font-weight:800;font-size:14px;color:${tatC};white-space:nowrap">${tat}${ticketWarn ? ' <span style="font-size:9px;background:var(--c24-red);color:#fff;padding:1px 5px;border-radius:8px;font-weight:700;margin-left:2px">HIGH</span>' : ''}</td>
    </tr>`;
  }).join('');
}
</script>
</body>
</html>
