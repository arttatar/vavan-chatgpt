<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Vavan Beta Sales Map</title>

  <link rel="preconnect" href="https://api.mapbox.com" />
  <link rel="preconnect" href="https://cdn.jsdelivr.net" />
  <link href="https://api.mapbox.com/mapbox-gl-js/v3.2.0/mapbox-gl.css" rel="stylesheet" />
  <script src="https://api.mapbox.com/mapbox-gl-js/v3.2.0/mapbox-gl.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

  <style>
    * { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; height: 100%; font-family: Inter, Arial, sans-serif; background: #07101c; color: #fff; }
    body { overflow: hidden; }

    :root{
      --bg:#07101c;
      --panel:#0f1b2d;
      --panel2:#13233a;
      --line:rgba(255,255,255,.10);
      --muted:rgba(255,255,255,.65);
      --accent:#5d7cff;
      --good:#22c55e;
      --warn:#f59e0b;
      --bad:#ef4444;
    }

    #loader {
      position: fixed; inset: 0; z-index: 9999;
      display: flex; align-items: center; justify-content: center;
      background: radial-gradient(circle at center, #0d1830 0%, #06101b 65%, #03070d 100%);
      padding: 24px;
    }
    .loader-card {
      width: min(460px, 100%);
      background: rgba(17, 28, 47, .95);
      border: 1px solid rgba(255,255,255,.10);
      border-radius: 20px;
      padding: 26px 24px;
      box-shadow: 0 20px 60px rgba(0,0,0,.35);
    }
    .loader-title { font-size: 24px; font-weight: 800; margin-bottom: 6px; }
    .loader-text { color: var(--muted); font-size: 14px; margin-bottom: 14px; }
    .loader-bar {
      height: 8px; width: 100%;
      background: rgba(255,255,255,.08);
      border-radius: 999px; overflow: hidden;
      margin-bottom: 10px;
    }
    .loader-fill {
      height: 100%; width: 0%;
      background: linear-gradient(90deg, #506bff, #7f95ff);
      transition: width .25s ease;
    }
    .loader-error {
      color: #ffb4b4;
      font-size: 13px;
      line-height: 1.5;
      white-space: pre-wrap;
      margin-top: 8px;
      display: none;
    }

    #login {
      position: fixed; inset: 0; z-index: 9000;
      display: none; align-items: center; justify-content: center;
      background: radial-gradient(circle at center, #0d1830 0%, #06101b 65%, #03070d 100%);
      padding: 24px;
    }
    .login-card {
      width: min(420px, 100%);
      background: rgba(17, 28, 47, .96);
      border: 1px solid rgba(255,255,255,.10);
      border-radius: 20px;
      padding: 26px 24px;
      box-shadow: 0 20px 60px rgba(0,0,0,.35);
    }
    .brand { font-size: 32px; font-weight: 800; margin-bottom: 4px; }
    .brand-sub { color: var(--muted); font-size: 14px; margin-bottom: 18px; }
    .field-label { display:block; font-size:12px; color:var(--muted); margin-bottom:6px; }
    .input {
      width:100%; padding:12px 14px; border-radius:12px;
      border:1px solid rgba(255,255,255,.12);
      background:#0b1525; color:#fff; outline:none; margin-bottom:14px;
    }
    .input:focus { border-color:#6f88ff; }
    .btn {
      border:0; border-radius:12px; padding:12px 14px; cursor:pointer;
      font-weight:700; transition:.15s ease; font-size:14px;
    }
    .btn-primary { background:var(--accent); color:#fff; }
    .btn-primary:hover { filter:brightness(1.05); }
    .btn-secondary {
      background: rgba(255,255,255,.08); color:#fff; border:1px solid rgba(255,255,255,.10);
    }
    .btn-secondary:hover { background: rgba(255,255,255,.12); }
    .login-error { color:#ffb4b4; font-size:13px; margin-top:10px; min-height:18px; }

    #app { display:none; width:100%; height:100%; }
    #map { position: fixed; inset: 58px 0 0 0; }

    #topbar {
      position: fixed; top:0; left:0; right:0; height:58px; z-index:1000;
      display:flex; align-items:center; gap:10px;
      padding: 10px 14px;
      background: rgba(7,16,28,.96);
      border-bottom: 1px solid var(--line);
      backdrop-filter: blur(12px);
    }
    .top-title { font-size: 22px; font-weight: 800; }
    .top-sub { color:var(--muted); font-size:12px; }
    .spacer { flex:1; }
    .chip {
      background: rgba(255,255,255,.08);
      border:1px solid rgba(255,255,255,.10);
      color:#fff; border-radius:999px;
      padding:8px 12px; font-size:12px; font-weight:600;
    }
    .mini-btn {
      height:38px; padding:0 14px; border-radius:12px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.08); color:#fff;
      cursor:pointer; font-weight:700;
    }

    #leftPanel {
      position: fixed; top:58px; left:0; bottom:0; width:360px; z-index:900;
      background: rgba(10,19,33,.96);
      border-right:1px solid var(--line);
      display:flex; flex-direction:column;
      backdrop-filter: blur(12px);
    }
    .panel-header {
      padding:14px 14px 10px;
      border-bottom:1px solid var(--line);
    }
    .panel-title { font-size:15px; font-weight:800; }
    .panel-sub { font-size:12px; color:var(--muted); margin-top:3px; }

    .panel-body { padding:14px; overflow:auto; flex:1; }
    .panel-section { margin-bottom:14px; }
    .panel-label {
      display:block; font-size:11px; text-transform:uppercase; letter-spacing:.08em;
      color:var(--muted); margin-bottom:8px; font-weight:700;
    }
    .row { display:flex; gap:8px; }
    .row .input { margin-bottom:0; }
    .panel-actions { display:flex; gap:8px; margin-top:14px; }

    #results {
      margin-top:12px;
      border-top:1px solid var(--line);
      padding-top:12px;
    }
    .result-count { font-size:12px; color:var(--muted); margin-bottom:8px; }
    .biz-list { display:flex; flex-direction:column; gap:8px; }
    .biz-item {
      background: rgba(255,255,255,.05);
      border:1px solid rgba(255,255,255,.07);
      border-radius:14px;
      padding:10px 12px;
      cursor:pointer;
      transition:.15s ease;
    }
    .biz-item:hover { background: rgba(255,255,255,.08); transform: translateY(-1px); }
    .biz-name { font-size:14px; font-weight:800; line-height:1.3; margin-bottom:4px; }
    .biz-meta { font-size:12px; color:var(--muted); line-height:1.45; }
    .biz-phone { font-size:12px; color:#9ab2ff; margin-top:4px; }

    #detail {
      position: fixed; top:72px; right:16px; width:360px; max-width:calc(100vw - 24px);
      z-index:950; display:none;
      background: rgba(14, 24, 40, .97);
      border:1px solid rgba(255,255,255,.10);
      border-radius:18px;
      overflow:hidden;
      box-shadow: 0 20px 60px rgba(0,0,0,.35);
      backdrop-filter: blur(14px);
    }
    .detail-head {
      padding:16px; border-bottom:1px solid var(--line);
      display:flex; align-items:flex-start; gap:10px;
    }
    .detail-title { font-size:18px; font-weight:800; line-height:1.25; }
    .detail-close {
      margin-left:auto; background:rgba(255,255,255,.08); color:#fff;
      border:1px solid rgba(255,255,255,.10); border-radius:10px;
      width:34px; height:34px; cursor:pointer; font-size:18px;
    }
    .detail-body { padding:16px; max-height:75vh; overflow:auto; }
    .kv { margin-bottom:10px; }
    .kv-label { font-size:11px; text-transform:uppercase; letter-spacing:.08em; color:var(--muted); font-weight:700; margin-bottom:4px; }
    .kv-value { font-size:14px; line-height:1.5; }
    .detail-actions { display:flex; gap:8px; margin-top:16px; flex-wrap:wrap; }

    .tag {
      display:inline-flex; align-items:center; gap:6px;
      background:rgba(255,255,255,.08); border:1px solid rgba(255,255,255,.10);
      border-radius:999px; padding:6px 10px; font-size:11px; font-weight:700;
      margin-bottom:10px;
    }

    #fabBar {
      position: fixed; right:16px; bottom:16px; z-index:1000;
      display:flex; flex-direction:column; gap:10px;
    }
    .fab {
      width:58px; height:58px; border-radius:18px; border:0; cursor:pointer;
      box-shadow:0 18px 40px rgba(0,0,0,.35);
      font-size:24px; font-weight:800;
    }
    .fab-primary { background:var(--accent); color:#fff; }
    .fab-dark { background:#10203a; color:#fff; border:1px solid rgba(255,255,255,.10); }

    #addModal, #editModal {
      position: fixed; inset: 0; z-index: 10000; display:none;
      background: rgba(0,0,0,.50);
      align-items:center; justify-content:center;
      padding:20px;
    }
    .modal-card {
      width:min(560px, 100%);
      max-height:90vh; overflow:auto;
      background:#0d182a; color:#fff;
      border:1px solid rgba(255,255,255,.10);
      border-radius:20px;
      padding:18px;
      box-shadow: 0 24px 60px rgba(0,0,0,.42);
    }
    .modal-title { font-size:20px; font-weight:800; margin-bottom:6px; }
    .modal-sub { font-size:13px; color:var(--muted); margin-bottom:16px; }
    .modal-actions { display:flex; gap:8px; margin-top:16px; flex-wrap:wrap; }
    .small-note { font-size:12px; color:var(--muted); line-height:1.45; margin-top:8px; }

    .hidden { display:none !important; }

    @media (max-width: 980px) {
      #leftPanel {
        width:100%;
        max-width:100%;
        transform: translateX(-100%);
        transition: transform .2s ease;
      }
      #leftPanel.open { transform: translateX(0); }
      #detail {
        left:12px; right:12px; top:auto; bottom:90px; width:auto; max-width:none;
      }
      #map { inset: 58px 0 0 0; }
      .top-sub, #signedInText, #resultTotalChip { display:none; }
    }
  </style>
</head>
<body>

  <div id="loader">
    <div class="loader-card">
      <div class="loader-title">Vavan Beta</div>
      <div class="loader-text" id="loaderText">Starting sales map...</div>
      <div class="loader-bar"><div class="loader-fill" id="loaderFill"></div></div>
      <div class="loader-text">Beta build · Las Vegas market · field sales version</div>
      <div class="loader-error" id="loaderError"></div>
    </div>
  </div>

  <div id="login">
    <div class="login-card">
      <div class="brand">Vavan Beta</div>
      <div class="brand-sub">Private field sales map</div>

      <label class="field-label">Email</label>
      <input id="loginEmail" class="input" type="email" placeholder="you@company.com" />

      <label class="field-label">Password</label>
      <input id="loginPassword" class="input" type="password" placeholder="••••••••" />

      <button id="loginBtn" class="btn btn-primary" style="width:100%;">Sign in</button>
      <div class="login-error" id="loginError"></div>
    </div>
  </div>

  <div id="app">
    <div id="topbar">
      <div>
        <div class="top-title">Vavan</div>
        <div class="top-sub">Beta sales map</div>
      </div>

      <div class="chip" id="marketChip">Las Vegas</div>
      <div class="chip" id="resultTotalChip">0 businesses</div>

      <div class="spacer"></div>

      <div class="chip" id="signedInText">Signed in</div>
      <button class="mini-btn" id="locateBtn">Locate Me</button>
      <button class="mini-btn" id="menuBtn">Menu</button>
      <button class="mini-btn" id="signOutBtn">Sign Out</button>
    </div>

    <div id="leftPanel">
      <div class="panel-header">
        <div class="panel-title">Search & Filters</div>
        <div class="panel-sub">Fast beta version built for reps on the road</div>
      </div>

      <div class="panel-body">
        <div class="panel-section">
          <label class="panel-label">Business Name</label>
          <input id="filterName" class="input" type="text" placeholder="Search business name..." />
        </div>

        <div class="panel-section">
          <label class="panel-label">Industry</label>
          <select id="filterIndustry" class="input">
            <option value="">All industries</option>
            <option value="Automotive">Automotive</option>
            <option value="Agribusiness">Agribusiness</option>
            <option value="Transportation">Transportation</option>
            <option value="Transport">Transport</option>
            <option value="Construction">Construction</option>
            <option value="Infrastructure">Infrastructure</option>
            <option value="Industrial">Industrial</option>
            <option value="Services">Services</option>
            <option value="Hospitality">Hospitality</option>
            <option value="Government">Government</option>
            <option value="Energy">Energy</option>
            <option value="RealEstate">Real Estate</option>
            <option value="Competitors">Competitors</option>
          </select>
        </div>

        <div class="panel-section">
          <label class="panel-label">City / ZIP</label>
          <div class="row">
            <input id="filterCity" class="input" type="text" placeholder="City" />
            <input id="filterZip" class="input" type="text" placeholder="ZIP" />
          </div>
        </div>

        <div class="panel-section">
          <label class="panel-label">Only Show</label>
          <select id="filterHas" class="input">
            <option value="">Everything</option>
            <option value="phone">Has phone</option>
            <option value="website">Has website</option>
            <option value="both">Phone + website</option>
          </select>
        </div>

        <div class="panel-actions">
          <button class="btn btn-primary" id="applyBtn">Apply</button>
          <button class="btn btn-secondary" id="clearBtn">Clear</button>
        </div>

        <div id="results">
          <div class="result-count" id="resultCount">0 results</div>
          <div class="biz-list" id="bizList"></div>
        </div>
      </div>
    </div>

    <div id="map"></div>

    <div id="detail">
      <div class="detail-head">
        <div>
          <div class="detail-title" id="detailName">Business</div>
        </div>
        <button class="detail-close" id="detailCloseBtn">×</button>
      </div>
      <div class="detail-body" id="detailBody"></div>
    </div>

    <div id="fabBar">
      <button class="fab fab-dark" id="listFab" title="Open filters">☰</button>
      <button class="fab fab-primary" id="addFab" title="Add business">＋</button>
    </div>
  </div>

  <div id="addModal">
    <div class="modal-card">
      <div class="modal-title">Add Business</div>
      <div class="modal-sub">Creates a new business and drops a new pin on the map.</div>

      <label class="field-label">Business Name</label>
      <input id="addName" class="input" type="text" placeholder="Business name" />

      <label class="field-label">Street Address</label>
      <input id="addStreet" class="input" type="text" placeholder="Street address" />

      <div class="row">
        <div style="flex:1;">
          <label class="field-label">City</label>
          <input id="addCity" class="input" type="text" placeholder="Las Vegas" />
        </div>
        <div style="width:110px;">
          <label class="field-label">State</label>
          <input id="addState" class="input" type="text" placeholder="NV" value="NV" />
        </div>
        <div style="width:130px;">
          <label class="field-label">ZIP</label>
          <input id="addZip" class="input" type="text" placeholder="89118" />
        </div>
      </div>

      <div class="row">
        <div style="flex:1;">
          <label class="field-label">Phone</label>
          <input id="addPhone" class="input" type="text" placeholder="(702) 555-1234" />
        </div>
        <div style="flex:1;">
          <label class="field-label">Website</label>
          <input id="addWebsite" class="input" type="text" placeholder="https://example.com" />
        </div>
      </div>

      <label class="field-label">Industry</label>
      <select id="addIndustry" class="input">
        <option value="">Select industry</option>
        <option value="Automotive">Automotive</option>
        <option value="Agribusiness">Agribusiness</option>
        <option value="Transportation">Transportation</option>
        <option value="Transport">Transport</option>
        <option value="Construction">Construction</option>
        <option value="Infrastructure">Infrastructure</option>
        <option value="Industrial">Industrial</option>
        <option value="Services">Services</option>
        <option value="Hospitality">Hospitality</option>
        <option value="Government">Government</option>
        <option value="Energy">Energy</option>
        <option value="RealEstate">Real Estate</option>
        <option value="Competitors">Competitors</option>
      </select>

      <div class="small-note">Address will be geocoded automatically before save.</div>

      <div class="modal-actions">
        <button class="btn btn-primary" id="saveAddBtn">Save Business</button>
        <button class="btn btn-secondary" id="closeAddBtn">Cancel</button>
      </div>
    </div>
  </div>

  <div id="editModal">
    <div class="modal-card">
      <div class="modal-title">Edit Business</div>
      <div class="modal-sub">Update the selected business live during the blitz.</div>

      <input id="editId" type="hidden" />

      <label class="field-label">Business Name</label>
      <input id="editName" class="input" type="text" />

      <label class="field-label">Street Address</label>
      <input id="editStreet" class="input" type="text" />

      <div class="row">
        <div style="flex:1;">
          <label class="field-label">City</label>
          <input id="editCity" class="input" type="text" />
        </div>
        <div style="width:110px;">
          <label class="field-label">State</label>
          <input id="editState" class="input" type="text" />
        </div>
        <div style="width:130px;">
          <label class="field-label">ZIP</label>
          <input id="editZip" class="input" type="text" />
        </div>
      </div>

      <div class="row">
        <div style="flex:1;">
          <label class="field-label">Phone</label>
          <input id="editPhone" class="input" type="text" />
        </div>
        <div style="flex:1;">
          <label class="field-label">Website</label>
          <input id="editWebsite" class="input" type="text" />
        </div>
      </div>

      <label class="field-label">Industry</label>
      <select id="editIndustry" class="input">
        <option value="">Select industry</option>
        <option value="Automotive">Automotive</option>
        <option value="Agribusiness">Agribusiness</option>
        <option value="Transportation">Transportation</option>
        <option value="Transport">Transport</option>
        <option value="Construction">Construction</option>
        <option value="Infrastructure">Infrastructure</option>
        <option value="Industrial">Industrial</option>
        <option value="Services">Services</option>
        <option value="Hospitality">Hospitality</option>
        <option value="Government">Government</option>
        <option value="Energy">Energy</option>
        <option value="RealEstate">Real Estate</option>
        <option value="Competitors">Competitors</option>
      </select>

      <div class="modal-actions">
        <button class="btn btn-primary" id="saveEditBtn">Save Changes</button>
        <button class="btn btn-secondary" id="closeEditBtn">Cancel</button>
      </div>
    </div>
  </div>

  <script>
    /***********************
     * CONFIG
     ***********************/
    const SUPABASE_URL = 'https://gcylhmxrzhbkaqkcovct.supabase.co';
    const SUPABASE_ANON_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImdjeWxobXhyemhia2Fxa2NvdmN0Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzM0MDg4MDMsImV4cCI6MjA4ODk4NDgwM30.aGoL_gr4XXX-sefNLAWf1bgZnqVPgUyCY7GImpQhq9U';
    const MAPBOX_TOKEN = 'pk.eyJ1IjoiYXJ0dGF0YXIiLCJhIjoiY21pdWppYThlMjEzcjNxb3JjaDZkdWs4dyJ9.d-lDV_T6-_T2_10CHxfvVg';
    const DEFAULT_MARKET = 'Las Vegas';

    /***********************
     * SAFETY CHECKS
     ***********************/
    function assertConfig() {
      if (!SUPABASE_URL || !/^https?:\/\//i.test(SUPABASE_URL)) {
        throw new Error('Supabase URL is invalid. Check SUPABASE_URL.');
      }
      if (!SUPABASE_ANON_KEY || SUPABASE_ANON_KEY.length < 20) {
        throw new Error('Supabase anon key is invalid. Check SUPABASE_ANON_KEY.');
      }
      if (!MAPBOX_TOKEN || MAPBOX_TOKEN.length < 20) {
        throw new Error('Mapbox token is invalid. Check MAPBOX_TOKEN.');
      }
    }

    /***********************
     * GLOBALS
     ***********************/
    let sb = null;
    let map = null;
    let allBusinesses = [];
    let filteredBusinesses = [];
    let selectedBusiness = null;
    let currentUser = null;
    let userMarker = null;
    let panelOpen = window.innerWidth > 980;

    const ui = {
      loader: document.getElementById('loader'),
      loaderText: document.getElementById('loaderText'),
      loaderFill: document.getElementById('loaderFill'),
      loaderError: document.getElementById('loaderError'),

      login: document.getElementById('login'),
      loginEmail: document.getElementById('loginEmail'),
      loginPassword: document.getElementById('loginPassword'),
      loginBtn: document.getElementById('loginBtn'),
      loginError: document.getElementById('loginError'),

      app: document.getElementById('app'),
      leftPanel: document.getElementById('leftPanel'),
      menuBtn: document.getElementById('menuBtn'),
      signOutBtn: document.getElementById('signOutBtn'),
      locateBtn: document.getElementById('locateBtn'),
      marketChip: document.getElementById('marketChip'),
      resultTotalChip: document.getElementById('resultTotalChip'),
      signedInText: document.getElementById('signedInText'),

      filterName: document.getElementById('filterName'),
      filterIndustry: document.getElementById('filterIndustry'),
      filterCity: document.getElementById('filterCity'),
      filterZip: document.getElementById('filterZip'),
      filterHas: document.getElementById('filterHas'),
      applyBtn: document.getElementById('applyBtn'),
      clearBtn: document.getElementById('clearBtn'),
      resultCount: document.getElementById('resultCount'),
      bizList: document.getElementById('bizList'),

      detail: document.getElementById('detail'),
      detailName: document.getElementById('detailName'),
      detailBody: document.getElementById('detailBody'),
      detailCloseBtn: document.getElementById('detailCloseBtn'),

      listFab: document.getElementById('listFab'),
      addFab: document.getElementById('addFab'),

      addModal: document.getElementById('addModal'),
      addName: document.getElementById('addName'),
      addStreet: document.getElementById('addStreet'),
      addCity: document.getElementById('addCity'),
      addState: document.getElementById('addState'),
      addZip: document.getElementById('addZip'),
      addPhone: document.getElementById('addPhone'),
      addWebsite: document.getElementById('addWebsite'),
      addIndustry: document.getElementById('addIndustry'),
      saveAddBtn: document.getElementById('saveAddBtn'),
      closeAddBtn: document.getElementById('closeAddBtn'),

      editModal: document.getElementById('editModal'),
      editId: document.getElementById('editId'),
      editName: document.getElementById('editName'),
      editStreet: document.getElementById('editStreet'),
      editCity: document.getElementById('editCity'),
      editState: document.getElementById('editState'),
      editZip: document.getElementById('editZip'),
      editPhone: document.getElementById('editPhone'),
      editWebsite: document.getElementById('editWebsite'),
      editIndustry: document.getElementById('editIndustry'),
      saveEditBtn: document.getElementById('saveEditBtn'),
      closeEditBtn: document.getElementById('closeEditBtn'),
    };

    /***********************
     * LOADER
     ***********************/
    function setProgress(percent, text) {
      ui.loaderFill.style.width = percent + '%';
      ui.loaderText.textContent = text;
    }

    function showLoaderError(message) {
      ui.loaderError.style.display = 'block';
      ui.loaderError.textContent = message;
    }

    function hideLoader() {
      ui.loader.style.display = 'none';
    }

    function showLogin() {
      ui.login.style.display = 'flex';
    }

    function hideLogin() {
      ui.login.style.display = 'none';
    }

    function showApp() {
      ui.app.style.display = 'block';
    }

    /***********************
     * HELPERS
     ***********************/
    function escapeHtml(value) {
      return String(value ?? '')
        .replaceAll('&', '&amp;')
        .replaceAll('<', '&lt;')
        .replaceAll('>', '&gt;')
        .replaceAll('"', '&quot;')
        .replaceAll("'", '&#039;');
    }

    function normalizeUrl(url) {
      if (!url) return '';
      const clean = url.trim();
      if (!clean) return '';
      if (/^https?:\/\//i.test(clean)) return clean;
      return 'https://' + clean;
    }

    function phoneHref(phone) {
      return 'tel:' + String(phone || '').replace(/\D/g, '');
    }

    function businessColor(b) {
      const ind = String(b.industry || '').trim();
      if (b.is_competitor) return '#ef4444';
      if (ind === 'Automotive') return '#3B82F6';
      if (ind === 'Agribusiness') return '#84CC16';
      if (ind === 'Transportation' || ind === 'Transport') return '#F97316';
      if (ind === 'Construction' || ind === 'Infrastructure') return '#D97706';
      if (ind === 'Industrial') return '#6B7280';
      if (ind === 'Services') return '#8B5CF6';
      if (ind === 'Hospitality') return '#EC4899';
      if (ind === 'Government') return '#0EA5E9';
      if (ind === 'Energy') return '#EAB308';
      if (ind === 'RealEstate') return '#14B8A6';
      if (ind === 'Competitors') return '#EF4444';
      return '#6f88ff';
    }

    function getLocalityParts(b) {
      const raw = String(b.locality || '').trim();
      if (!raw) return { city: '', state: '', zip: '' };

      const parts = raw.split(',').map(x => x.trim());
      const city = parts[0] || '';
      let state = '';
      let zip = '';

      if (parts[1]) {
        const rest = parts[1].split(/\s+/).filter(Boolean);
        state = rest[0] || '';
        zip = rest[1] || '';
      }

      return { city, state, zip };
    }

    function buildLocality(city, state, zip) {
      const c = (city || '').trim();
      const s = (state || '').trim();
      const z = (zip || '').trim();
      if (!c && !s && !z) return '';
      if (c && s && z) return `${c}, ${s} ${z}`;
      if (c && s) return `${c}, ${s}`;
      return [c, s, z].filter(Boolean).join(' ');
    }

    function buildFullAddress(street, city, state, zip) {
      return [street, buildLocality(city, state, zip)].filter(Boolean).join(', ');
    }

    function scoreBusiness(b) {
      let score = 50;
      if (b.phone) score += 15;
      if (b.website) score += 15;
      if (/truck|fleet|diesel|fuel|oil|lube|repair|shop|farm|construction|industrial|transport|logistic/i.test(String(b.name || ''))) score += 20;
      return Math.min(score, 100);
    }

    async function geocodeAddress(fullAddress) {
      const url = `https://api.mapbox.com/geocoding/v5/mapbox.places/${encodeURIComponent(fullAddress)}.json?limit=1&access_token=${MAPBOX_TOKEN}`;
      const res = await fetch(url);
      if (!res.ok) throw new Error('Address geocoding failed.');
      const json = await res.json();
      if (!json.features || !json.features.length) throw new Error('Could not find this address on the map.');
      const feature = json.features[0];
      return {
        lon: feature.center[0],
        lat: feature.center[1]
      };
    }

    /***********************
     * STARTUP
     ***********************/
    async function boot() {
      try {
        setProgress(10, 'Checking configuration...');
        assertConfig();

        setProgress(20, 'Connecting to Supabase...');
        sb = window.supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

        mapboxgl.accessToken = MAPBOX_TOKEN;

        setProgress(30, 'Checking session...');
        const { data, error } = await sb.auth.getSession();
        if (error) throw error;

        if (data?.session?.user) {
          currentUser = data.session.user;
          await startApp();
        } else {
          hideLoader();
          showLogin();
        }
      } catch (err) {
        console.error(err);
        setProgress(100, 'Startup failed');
        showLoaderError(err.message || String(err));
      }
    }

    /***********************
     * AUTH
     ***********************/
    async function doLogin() {
      ui.loginError.textContent = '';
      const email = ui.loginEmail.value.trim();
      const password = ui.loginPassword.value;

      if (!email || !password) {
        ui.loginError.textContent = 'Enter email and password.';
        return;
      }

      ui.loginBtn.disabled = true;
      ui.loginBtn.textContent = 'Signing in...';

      try {
        const { data, error } = await sb.auth.signInWithPassword({ email, password });
        if (error) throw error;
        currentUser = data.user;
        hideLogin();
        ui.loader.style.display = 'flex';
        ui.loaderError.style.display = 'none';
        await startApp();
      } catch (err) {
        console.error(err);
        ui.loginError.textContent = err.message || 'Sign-in failed.';
      } finally {
        ui.loginBtn.disabled = false;
        ui.loginBtn.textContent = 'Sign in';
      }
    }

    async function doSignOut() {
      try {
        await sb.auth.signOut();
      } catch (err) {
        console.error(err);
      }
      location.reload();
    }

    /***********************
     * APP
     ***********************/
    async function startApp() {
      try {
        setProgress(40, 'Opening map...');
        showApp();
        initMap();

        setProgress(60, 'Loading businesses...');
        await loadBusinesses();

        setProgress(80, 'Rendering pins...');
        renderAll();

        setProgress(100, 'Ready');
        ui.signedInText.textContent = currentUser?.email || 'Signed in';
        ui.marketChip.textContent = DEFAULT_MARKET;

        setTimeout(() => hideLoader(), 350);
      } catch (err) {
        console.error(err);
        setProgress(100, 'App failed');
        showLoaderError(err.message || String(err));
      }
    }

    function initMap() {
      if (map) return;

      map = new mapboxgl.Map({
        container: 'map',
        style: 'mapbox://styles/mapbox/dark-v11',
        center: [-115.1398, 36.1699],
        zoom: 10
      });

      map.addControl(new mapboxgl.NavigationControl(), 'top-right');

      map.on('load', () => {
        map.addSource('businesses', {
          type: 'geojson',
          cluster: true,
          clusterMaxZoom: 13,
          clusterRadius: 44,
          data: { type: 'FeatureCollection', features: [] }
        });

        map.addLayer({
          id: 'clusters',
          type: 'circle',
          source: 'businesses',
          filter: ['has', 'point_count'],
          paint: {
            'circle-color': '#5d7cff',
            'circle-radius': [
              'step',
              ['get', 'point_count'],
              18,
              15, 22,
              50, 28,
              100, 34
            ],
            'circle-opacity': 0.9
          }
        });

        map.addLayer({
          id: 'cluster-count',
          type: 'symbol',
          source: 'businesses',
          filter: ['has', 'point_count'],
          layout: {
            'text-field': '{point_count_abbreviated}',
            'text-size': 12,
            'text-font': ['Open Sans Bold', 'Arial Unicode MS Bold']
          },
          paint: {
            'text-color': '#ffffff'
          }
        });

        map.addLayer({
          id: 'unclustered-point',
          type: 'circle',
          source: 'businesses',
          filter: ['!', ['has', 'point_count']],
          paint: {
            'circle-radius': 7,
            'circle-color': [
              'coalesce',
              ['get', 'pinColor'],
              '#6f88ff'
            ],
            'circle-stroke-width': 2,
            'circle-stroke-color': '#ffffff'
          }
        });

        map.addLayer({
          id: 'selected-point',
          type: 'circle',
          source: 'businesses',
          filter: ['==', ['get', 'selected'], 1],
          paint: {
            'circle-radius': 13,
            'circle-color': [
              'coalesce',
              ['get', 'pinColor'],
              '#6f88ff'
            ],
            'circle-opacity': 0.25,
            'circle-stroke-width': 0
          }
        });

        map.on('click', 'clusters', (e) => {
          const features = map.queryRenderedFeatures(e.point, { layers: ['clusters'] });
          const clusterId = features[0].properties.cluster_id;
          map.getSource('businesses').getClusterExpansionZoom(clusterId, (err, zoom) => {
            if (err) return;
            map.easeTo({
              center: features[0].geometry.coordinates,
              zoom
            });
          });
        });

        map.on('click', 'unclustered-point', (e) => {
          const id = e.features[0].properties.id;
          const biz = allBusinesses.find(x => String(x.id) === String(id));
          if (biz) openDetail(biz);
        });

        map.on('mouseenter', 'clusters', () => map.getCanvas().style.cursor = 'pointer');
        map.on('mouseleave', 'clusters', () => map.getCanvas().style.cursor = '');
        map.on('mouseenter', 'unclustered-point', () => map.getCanvas().style.cursor = 'pointer');
        map.on('mouseleave', 'unclustered-point', () => map.getCanvas().style.cursor = '');

        renderAll();
      });
    }

    async function loadBusinesses() {
      let from = 0;
      const chunk = 1000;
      const rows = [];

      while (true) {
        const { data, error } = await sb
          .from('businesses')
          .select('*')
          .eq('market', DEFAULT_MARKET)
          .range(from, from + chunk - 1);

        if (error) throw error;
        if (!data || !data.length) break;

        rows.push(...data);

        if (data.length < chunk) break;
        from += chunk;
      }

      allBusinesses = rows.map(b => ({
        ...b,
        score: scoreBusiness(b)
      }));

      filteredBusinesses = [...allBusinesses];
    }

    function applyFilters() {
      const name = ui.filterName.value.trim().toLowerCase();
      const industry = ui.filterIndustry.value.trim().toLowerCase();
      const city = ui.filterCity.value.trim().toLowerCase();
      const zip = ui.filterZip.value.trim();
      const has = ui.filterHas.value;

      filteredBusinesses = allBusinesses.filter(b => {
        if (!b.lat || !b.lon) return false;

        const bName = String(b.name || '').toLowerCase();
        const bIndustry = String(b.industry || '').toLowerCase();
        const bStreet = String(b.street || '').toLowerCase();
        const bLocality = String(b.locality || '').toLowerCase();
        const bPhone = String(b.phone || '').trim();
        const bWebsite = String(b.website || '').trim();

        if (name && !bName.includes(name)) return false;
        if (industry && bIndustry !== industry) return false;
        if (city && !(bLocality.includes(city) || bStreet.includes(city))) return false;
        if (zip && !(bLocality.includes(zip) || String(b.full_address || '').includes(zip))) return false;
        if (has === 'phone' && !bPhone) return false;
        if (has === 'website' && !bWebsite) return false;
        if (has === 'both' && !(bPhone && bWebsite)) return false;

        return true;
      });

      renderAll();
    }

    function clearFilters() {
      ui.filterName.value = '';
      ui.filterIndustry.value = '';
      ui.filterCity.value = '';
      ui.filterZip.value = '';
      ui.filterHas.value = '';
      filteredBusinesses = [...allBusinesses];
      renderAll();
    }

    function makeGeoJson(list) {
      return {
        type: 'FeatureCollection',
        features: list
          .filter(b => b.lat && b.lon)
          .map(b => ({
            type: 'Feature',
            geometry: {
              type: 'Point',
              coordinates: [Number(b.lon), Number(b.lat)]
            },
            properties: {
              id: b.id,
              name: b.name || '',
              pinColor: businessColor(b),
              selected: selectedBusiness && String(selectedBusiness.id) === String(b.id) ? 1 : 0
            }
          }))
      };
    }

    function renderMap() {
      if (!map || !map.isStyleLoaded() || !map.getSource('businesses')) return;
      map.getSource('businesses').setData(makeGeoJson(filteredBusinesses));
    }

    function renderList() {
      ui.resultCount.textContent = `${filteredBusinesses.length.toLocaleString()} results`;
      ui.resultTotalChip.textContent = `${filteredBusinesses.length.toLocaleString()} businesses`;

      const visible = filteredBusinesses.slice(0, 150);

      ui.bizList.innerHTML = visible.map(b => {
        const color = businessColor(b);
        return `
          <div class="biz-item" data-id="${escapeHtml(b.id)}">
            <div class="biz-name" style="display:flex;align-items:center;gap:8px;">
              <span style="width:10px;height:10px;border-radius:50%;background:${color};display:inline-block;flex-shrink:0;"></span>
              <span>${escapeHtml(b.name || 'Unnamed Business')}</span>
            </div>
            <div class="biz-meta">${escapeHtml(b.street || '')}${b.locality ? '<br>' + escapeHtml(b.locality) : ''}</div>
            ${b.phone ? `<div class="biz-phone">${escapeHtml(b.phone)}</div>` : ''}
          </div>
        `;
      }).join('');

      Array.from(ui.bizList.querySelectorAll('.biz-item')).forEach(el => {
        el.addEventListener('click', () => {
          const id = el.getAttribute('data-id');
          const biz = filteredBusinesses.find(x => String(x.id) === String(id));
          if (biz) openDetail(biz);
          if (window.innerWidth <= 980) closePanel();
        });
      });
    }

    function renderAll() {
      renderList();
      renderMap();
    }

    function openDetail(b) {
      selectedBusiness = b;
      renderMap();

      const parts = getLocalityParts(b);
      ui.detailName.textContent = b.name || 'Business';

      ui.detailBody.innerHTML = `
        <div class="tag" style="background:${businessColor(b)}22;border-color:${businessColor(b)}55;">
          <span style="width:8px;height:8px;border-radius:50%;background:${businessColor(b)};display:inline-block;"></span>
          ${escapeHtml(b.industry || 'Business')}
        </div>

        <div class="kv">
          <div class="kv-label">Address</div>
          <div class="kv-value">${escapeHtml(buildFullAddress(b.street || '', parts.city, parts.state, parts.zip) || b.full_address || '')}</div>
        </div>

        <div class="kv">
          <div class="kv-label">Phone</div>
          <div class="kv-value">
            ${b.phone ? `<a href="${phoneHref(b.phone)}" style="color:#9ab2ff;text-decoration:none;">${escapeHtml(b.phone)}</a>` : '—'}
          </div>
        </div>

        <div class="kv">
          <div class="kv-label">Website</div>
          <div class="kv-value">
            ${b.website ? `<a href="${escapeHtml(normalizeUrl(b.website))}" target="_blank" style="color:#9ab2ff;text-decoration:none;">${escapeHtml(b.website)}</a>` : '—'}
          </div>
        </div>

        <div class="kv">
          <div class="kv-label">Opportunity Score</div>
          <div class="kv-value">${escapeHtml(b.score || scoreBusiness(b))}/100</div>
        </div>

        <div class="detail-actions">
          <button class="btn btn-primary" id="navBtn">Navigate</button>
          <button class="btn btn-secondary" id="editBtn">Edit</button>
          <button class="btn btn-secondary" id="websiteBtn" ${b.website ? '' : 'disabled'}>Website</button>
        </div>
      `;

      ui.detail.style.display = 'block';

      if (b.lat && b.lon) {
        map.flyTo({
          center: [Number(b.lon), Number(b.lat)],
          zoom: 15,
          speed: 1.2
        });
      }

      const navBtn = document.getElementById('navBtn');
      const editBtn = document.getElementById('editBtn');
      const websiteBtn = document.getElementById('websiteBtn');

      navBtn.addEventListener('click', () => {
        const address = buildFullAddress(b.street || '', parts.city, parts.state, parts.zip) || b.full_address || '';
        const url = `https://www.google.com/maps/dir/?api=1&destination=${encodeURIComponent(address)}`;
        window.open(url, '_blank');
      });

      editBtn.addEventListener('click', () => openEditModal(b));

      if (websiteBtn && b.website) {
        websiteBtn.addEventListener('click', () => {
          window.open(normalizeUrl(b.website), '_blank');
        });
      }
    }

    function closeDetail() {
      selectedBusiness = null;
      ui.detail.style.display = 'none';
      renderMap();
    }

    /***********************
     * ADD BUSINESS
     ***********************/
    function openAddModal() {
      ui.addName.value = '';
      ui.addStreet.value = '';
      ui.addCity.value = 'Las Vegas';
      ui.addState.value = 'NV';
      ui.addZip.value = '';
      ui.addPhone.value = '';
      ui.addWebsite.value = '';
      ui.addIndustry.value = '';
      ui.addModal.style.display = 'flex';
    }

    function closeAddModal() {
      ui.addModal.style.display = 'none';
    }

    async function saveNewBusiness() {
      const name = ui.addName.value.trim();
      const street = ui.addStreet.value.trim();
      const city = ui.addCity.value.trim();
      const state = ui.addState.value.trim();
      const zip = ui.addZip.value.trim();
      const phone = ui.addPhone.value.trim();
      const website = ui.addWebsite.value.trim();
      const industry = ui.addIndustry.value.trim();

      if (!name) return alert('Enter business name.');
      if (!street || !city || !state) return alert('Enter full address.');

      const locality = buildLocality(city, state, zip);
      const fullAddress = buildFullAddress(street, city, state, zip);

      ui.saveAddBtn.disabled = true;
      ui.saveAddBtn.textContent = 'Saving...';

      try {
        const geo = await geocodeAddress(fullAddress);

        const payload = {
          name,
          street,
          locality,
          full_address: fullAddress,
          phone: phone || null,
          website: website || null,
          industry: industry || null,
          market: DEFAULT_MARKET,
          lat: geo.lat,
          lon: geo.lon
        };

        const { data, error } = await sb
          .from('businesses')
          .insert(payload)
          .select()
          .single();

        if (error) throw error;

        allBusinesses.unshift({
          ...data,
          score: scoreBusiness(data)
        });

        applyFilters();
        closeAddModal();

        const inserted = allBusinesses.find(x => String(x.id) === String(data.id));
        if (inserted) openDetail(inserted);
      } catch (err) {
        console.error(err);
        alert(err.message || 'Could not save business.');
      } finally {
        ui.saveAddBtn.disabled = false;
        ui.saveAddBtn.textContent = 'Save Business';
      }
    }

    /***********************
     * EDIT BUSINESS
     ***********************/
    function openEditModal(b) {
      const parts = getLocalityParts(b);

      ui.editId.value = b.id || '';
      ui.editName.value = b.name || '';
      ui.editStreet.value = b.street || '';
      ui.editCity.value = parts.city || '';
      ui.editState.value = parts.state || '';
      ui.editZip.value = parts.zip || '';
      ui.editPhone.value = b.phone || '';
      ui.editWebsite.value = b.website || '';
      ui.editIndustry.value = b.industry || '';

      ui.editModal.style.display = 'flex';
    }

    function closeEditModal() {
      ui.editModal.style.display = 'none';
    }

    async function saveEditBusiness() {
      const id = ui.editId.value;
      const name = ui.editName.value.trim();
      const street = ui.editStreet.value.trim();
      const city = ui.editCity.value.trim();
      const state = ui.editState.value.trim();
      const zip = ui.editZip.value.trim();
      const phone = ui.editPhone.value.trim();
      const website = ui.editWebsite.value.trim();
      const industry = ui.editIndustry.value.trim();

      if (!id) return alert('Missing business ID.');
      if (!name) return alert('Enter business name.');
      if (!street || !city || !state) return alert('Enter full address.');

      const locality = buildLocality(city, state, zip);
      const fullAddress = buildFullAddress(street, city, state, zip);

      ui.saveEditBtn.disabled = true;
      ui.saveEditBtn.textContent = 'Saving...';

      try {
        const geo = await geocodeAddress(fullAddress);

        const updates = {
          name,
          street,
          locality,
          full_address: fullAddress,
          phone: phone || null,
          website: website || null,
          industry: industry || null,
          lat: geo.lat,
          lon: geo.lon
        };

        const { data, error } = await sb
          .from('businesses')
          .update(updates)
          .eq('id', id)
          .select()
          .single();

        if (error) throw error;

        const idx = allBusinesses.findIndex(x => String(x.id) === String(id));
        if (idx > -1) {
          allBusinesses[idx] = {
            ...allBusinesses[idx],
            ...data,
            score: scoreBusiness({ ...allBusinesses[idx], ...data })
          };
        }

        applyFilters();
        closeEditModal();

        const updated = allBusinesses.find(x => String(x.id) === String(id));
        if (updated) openDetail(updated);
      } catch (err) {
        console.error(err);
        alert(err.message || 'Could not update business.');
      } finally {
        ui.saveEditBtn.disabled = false;
        ui.saveEditBtn.textContent = 'Save Changes';
      }
    }

    /***********************
     * PANEL
     ***********************/
    function openPanel() {
      panelOpen = true;
      if (window.innerWidth <= 980) ui.leftPanel.classList.add('open');
    }

    function closePanel() {
      panelOpen = false;
      if (window.innerWidth <= 980) ui.leftPanel.classList.remove('open');
    }

    function togglePanel() {
      if (window.innerWidth > 980) return;
      if (ui.leftPanel.classList.contains('open')) closePanel();
      else openPanel();
    }

    /***********************
     * GEOLOCATION
     ***********************/
    function locateMe() {
      if (!navigator.geolocation) {
        alert('Geolocation is not supported on this device.');
        return;
      }

      navigator.geolocation.getCurrentPosition((pos) => {
        const lng = pos.coords.longitude;
        const lat = pos.coords.latitude;

        map.flyTo({
          center: [lng, lat],
          zoom: 14,
          speed: 1.2
        });

        if (userMarker) userMarker.remove();

        const el = document.createElement('div');
        el.style.width = '18px';
        el.style.height = '18px';
        el.style.borderRadius = '50%';
        el.style.background = '#4da3ff';
        el.style.border = '3px solid #ffffff';
        el.style.boxShadow = '0 0 0 10px rgba(77,163,255,.18)';

        userMarker = new mapboxgl.Marker(el)
          .setLngLat([lng, lat])
          .addTo(map);
      }, (err) => {
        console.error(err);
        alert('Could not get your location.');
      }, {
        enableHighAccuracy: true,
        timeout: 10000
      });
    }

    /***********************
     * EVENTS
     ***********************/
    ui.loginBtn.addEventListener('click', doLogin);
    ui.loginPassword.addEventListener('keydown', (e) => {
      if (e.key === 'Enter') doLogin();
    });

    ui.signOutBtn.addEventListener('click', doSignOut);
    ui.locateBtn.addEventListener('click', locateMe);
    ui.menuBtn.addEventListener('click', togglePanel);
    ui.listFab.addEventListener('click', togglePanel);
    ui.addFab.addEventListener('click', openAddModal);

    ui.applyBtn.addEventListener('click', () => {
      applyFilters();
      if (window.innerWidth <= 980) closePanel();
    });
    ui.clearBtn.addEventListener('click', clearFilters);

    ui.detailCloseBtn.addEventListener('click', closeDetail);

    ui.closeAddBtn.addEventListener('click', closeAddModal);
    ui.saveAddBtn.addEventListener('click', saveNewBusiness);

    ui.closeEditBtn.addEventListener('click', closeEditModal);
    ui.saveEditBtn.addEventListener('click', saveEditBusiness);

    ui.addModal.addEventListener('click', (e) => {
      if (e.target === ui.addModal) closeAddModal();
    });
    ui.editModal.addEventListener('click', (e) => {
      if (e.target === ui.editModal) closeEditModal();
    });

    window.addEventListener('resize', () => {
      if (window.innerWidth > 980) {
        ui.leftPanel.classList.remove('open');
      }
    });

    /***********************
     * BOOT
     ***********************/
    boot();
  </script>
</body>
</html>
