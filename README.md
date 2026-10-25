<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
  <title>অ্যাডমিন প্যানেল - শৈলী ফ্যাশন কন্ট্রোল রুম</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@300;400;500;600;700&family=Outfit:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #0B4F37;
      --primary-dark: #073827;
      --primary-light: #EBF7F2;
      --gold: #D4AF37;
      --gold-dark: #B8860B;
      --gold-light: #FFF9E6;
      --accent-red: #D9383A;
      --bg-body: #F4F7F5;
      --bg-surface: #FFFFFF;
      --text-main: #142921;
      --text-muted: #5F736A;
      --border-color: #E2ECE6;
      --shadow-sm: 0 2px 8px rgba(11, 79, 55, 0.06);
      --shadow-md: 0 6px 18px rgba(11, 79, 55, 0.10);
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-lg: 20px;
      --radius-full: 9999px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
      font-family: 'Hind Siliguri', 'Outfit', sans-serif;
    }

    body {
      background-color: var(--bg-body);
      color: var(--text-main);
      line-height: 1.5;
      font-size: 14px;
      min-height: 100vh;
      padding-bottom: 50px;
    }

    .admin-container {
      max-width: 600px;
      margin: 0 auto;
      background: var(--bg-body);
      min-height: 100vh;
      box-shadow: 0 0 25px rgba(0,0,0,0.05);
      position: relative;
    }

    /* Header */
    .admin-header {
      background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
      color: #fff;
      padding: 16px 20px;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: var(--shadow-sm);
    }

    .header-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .admin-badge {
      background: var(--gold);
      color: var(--primary-dark);
      font-weight: 800;
      font-size: 10px;
      padding: 2px 8px;
      border-radius: var(--radius-full);
      text-transform: uppercase;
    }

    .store-view-btn {
      background: rgba(255, 255, 255, 0.15);
      color: #fff;
      border: 1px solid rgba(255, 255, 255, 0.3);
      padding: 6px 14px;
      border-radius: var(--radius-full);
      font-size: 12px;
      font-weight: 600;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    /* Tabs */
    .admin-nav-tabs {
      display: flex;
      background: var(--bg-surface);
      border-bottom: 1px solid var(--border-color);
      overflow-x: auto;
      scrollbar-width: none;
      position: sticky;
      top: 67px;
      z-index: 90;
    }

    .admin-nav-tabs::-webkit-scrollbar {
      display: none;
    }

    .nav-tab-item {
      padding: 12px 16px;
      font-size: 13px;
      font-weight: 600;
      color: var(--text-muted);
      border: none;
      background: none;
      white-space: nowrap;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .nav-tab-item.active {
      color: var(--primary);
      border-bottom-color: var(--primary);
      background: var(--primary-light);
      font-weight: 700;
    }

    .tab-badge {
      background: var(--accent-red);
      color: #fff;
      font-size: 10px;
      font-weight: 700;
      padding: 1px 6px;
      border-radius: 10px;
    }

    .admin-content {
      padding: 16px;
    }

    .tab-section {
      display: none;
      animation: fadeIn 0.2s ease;
    }

    .tab-section.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(4px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* Stat Cards */
    .stat-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      margin-bottom: 18px;
    }

    .stat-card {
      background: var(--bg-surface);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 16px 14px;
      box-shadow: var(--shadow-sm);
    }

    .stat-icon {
      width: 36px;
      height: 36px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      margin-bottom: 10px;
    }

    .icon-revenue { background: #E6F4EA; color: #137333; }
    .icon-orders { background: #E8F0FE; color: #1A73E8; }
    .icon-pending { background: #FEF7E0; color: #B06000; }
    .icon-products { background: #FCE8E6; color: #C5221F; }

    .stat-title {
      font-size: 11px;
      color: var(--text-muted);
      font-weight: 600;
      margin-bottom: 2px;
    }

    .stat-val {
      font-size: 19px;
      font-weight: 800;
      color: var(--text-main);
    }

    .admin-card {
      background: var(--bg-surface);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 16px;
      margin-bottom: 16px;
      box-shadow: var(--shadow-sm);
    }

    .card-title-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 14px;
    }

    .card-title {
      font-size: 15px;
      font-weight: 700;
      color: var(--primary);
      display: flex;
      align-items: center;
      gap: 6px;
    }

    /* Buttons */
    .btn-primary {
      background: var(--primary);
      color: #fff;
      border: none;
      padding: 10px 18px;
      border-radius: var(--radius-sm);
      font-size: 13px;
      font-weight: 700;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
    }

    .btn-secondary {
      background: var(--primary-light);
      color: var(--primary);
      border: 1px solid rgba(11, 79, 55, 0.2);
      padding: 8px 14px;
      border-radius: var(--radius-sm);
      font-size: 12px;
      font-weight: 600;
      cursor: pointer;
    }

    .btn-danger {
      background: #FCE8E6;
      color: var(--accent-red);
      border: 1px solid rgba(217, 56, 58, 0.3);
      padding: 6px 12px;
      border-radius: var(--radius-sm);
      font-size: 11px;
      font-weight: 700;
      cursor: pointer;
    }

    /* Forms */
    .form-group {
      margin-bottom: 14px;
    }

    .form-label {
      display: block;
      font-size: 12px;
      font-weight: 700;
      margin-bottom: 6px;
      color: var(--text-main);
    }

    .form-input, .form-select, .form-textarea {
      width: 100%;
      padding: 10px 12px;
      border: 1.5px solid var(--border-color);
      border-radius: var(--radius-sm);
      background: #FAFBFB;
      font-size: 13px;
      outline: none;
    }

    .form-input:focus, .form-select:focus, .form-textarea:focus {
      border-color: var(--primary);
      background: #fff;
    }

    /* Product Item */
    .admin-prod-item {
      display: flex;
      gap: 12px;
      padding: 12px;
      border: 1px solid var(--border-color);
      border-radius: var(--radius-sm);
      margin-bottom: 10px;
      background: var(--bg-surface);
      align-items: center;
    }

    .admin-prod-thumb {
      width: 60px;
      height: 75px;
      border-radius: 6px;
      object-fit: cover;
      background: #F0F4F2;
      flex-shrink: 0;
    }

    .admin-prod-info {
      flex: 1;
      min-width: 0;
    }

    .admin-prod-title {
      font-size: 13px;
      font-weight: 700;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      margin-bottom: 2px;
    }

    .stock-badge {
      display: inline-block;
      font-size: 10px;
      font-weight: 700;
      padding: 2px 7px;
      border-radius: 4px;
      cursor: pointer;
    }

    .badge-in-stock { background: #E6F4EA; color: #137333; }
    .badge-out-stock { background: #FCE8E6; color: #C5221F; }

    .admin-prod-actions {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    /* Orders Item */
    .admin-order-item {
      border: 1.5px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 14px;
      margin-bottom: 12px;
      background: var(--bg-surface);
      box-shadow: var(--shadow-sm);
    }

    .order-head-line {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 8px;
      margin-bottom: 8px;
    }

    .order-cust-box {
      background: #F7FAF8;
      border-radius: var(--radius-sm);
      padding: 8px 10px;
      font-size: 12px;
      margin-bottom: 8px;
      line-height: 1.4;
    }

    .status-select {
      height: 32px;
      padding: 0 8px;
      border-radius: var(--radius-sm);
      font-size: 12px;
      font-weight: 700;
      border: 1.5px solid var(--border-color);
      background: #fff;
      cursor: pointer;
    }

    .order-filter-bar {
      display: flex;
      gap: 8px;
      overflow-x: auto;
      scrollbar-width: none;
      margin-bottom: 14px;
    }

    .order-filter-bar::-webkit-scrollbar {
      display: none;
    }

    .filter-chip {
      padding: 6px 12px;
      border-radius: var(--radius-full);
      font-size: 11px;
      font-weight: 700;
      border: 1px solid var(--border-color);
      background: var(--bg-surface);
      color: var(--text-muted);
      white-space: nowrap;
      cursor: pointer;
    }

    .filter-chip.active {
      background: var(--primary);
      color: #fff;
      border-color: var(--primary);
    }

    /* Modal Overlay */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.6);
      backdrop-filter: blur(3px);
      z-index: 200;
      display: none;
      align-items: flex-end;
      justify-content: center;
    }

    .modal-overlay.show {
      display: flex;
    }

    .modal-card {
      width: 100%;
      max-width: 600px;
      max-height: 90vh;
      background: var(--bg-surface);
      border-radius: 20px 20px 0 0;
      overflow-y: auto;
      padding: 20px 20px 60px 20px;
      position: relative;
    }

    .modal-close-btn {
      position: absolute;
      top: 14px;
      right: 14px;
      width: 32px;
      height: 32px;
      border-radius: 50%;
      background: #F0F4F2;
      border: none;
      cursor: pointer;
      font-size: 16px;
    }

    /* Lock Screen */
    .lock-screen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: var(--bg-body);
      z-index: 999;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .lock-box {
      width: 100%;
      max-width: 380px;
      background: var(--bg-surface);
      border-radius: var(--radius-lg);
      padding: 28px 24px;
      text-align: center;
      box-shadow: var(--shadow-md);
      border: 1px solid var(--border-color);
    }

    .pin-input {
      letter-spacing: 12px;
      font-size: 24px;
      text-align: center;
      font-weight: 800;
      width: 180px;
      margin: 16px auto;
      display: block;
      border: 2px solid var(--primary);
      border-radius: var(--radius-sm);
      padding: 8px;
    }

    .toast-box {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(11, 79, 55, 0.95);
      color: #fff;
      padding: 10px 18px;
      border-radius: var(--radius-full);
      font-size: 13px;
      font-weight: 600;
      z-index: 1000;
      display: none;
    }

    @media print {
      body * { visibility: hidden; }
      #printArea, #printArea * { visibility: visible; }
      #printArea { position: absolute; left: 0; top: 0; width: 100%; }
    }
  </style>
</head>
<body>

  <!-- 1. PIN LOCK SCREEN -->
  <div class="lock-screen" id="lockScreen">
    <div class="lock-box">
      <div style="width: 56px; height: 56px; border-radius: 50%; background: var(--primary-light); color: var(--primary); font-size: 26px; display: flex; align-items: center; justify-content: center; margin: 0 auto 14px auto;">
        🔐
      </div>
      <h2 style="font-size: 18px; font-weight: 700; color: var(--text-main);">স্টোর অ্যাডমিন ভেরিফিকেশন</h2>
      <p style="font-size: 12px; color: var(--text-muted); margin-top: 4px;">দোকান নিয়ন্ত্রণ করতে আপনার ৪ ডিজিটের সিক্রেট পিন দিন</p>
      
      <input type="password" id="adminPinInput" class="pin-input" maxlength="4" placeholder="••••" autofocus onkeydown="if(event.key==='Enter') verifyAdminPin()">
      
      <p style="font-size: 11px; color: var(--gold-dark); margin-bottom: 16px;">(ডিফল্ট টেস্ট পিন: <strong>1234</strong>)</p>
      
      <button class="btn-primary" style="width: 100%; height: 44px;" onclick="verifyAdminPin()">
        প্রবেশ করুন ➔
      </button>

      <a href="index.html" style="display: block; margin-top: 14px; font-size: 12px; color: var(--text-muted); text-decoration: none;">
        ⬅️ কাস্টমার স্টোরে ফিরে যান
      </a>
    </div>
  </div>

  <!-- 2. ADMIN DASHBOARD -->
  <div class="admin-container" id="adminDashboard" style="display: none;">
    
    <header class="admin-header">
      <div class="header-top">
        <div class="header-branding">
          <div>
            <h1 style="font-size: 17px; font-weight: 800; line-height: 1.2;" id="headerStoreName">শৈলী ফ্যাশন</h1>
            <div style="display: flex; align-items: center; gap: 6px; margin-top: 2px;">
              <span class="admin-badge">মাস্টার অ্যাডমিন</span>
              <span style="font-size: 10px; opacity: 0.8;">কন্ট্রোল রুম</span>
            </div>
          </div>
        </div>
        <a href="index.html" class="store-view-btn">
          <span>🛍️</span> কাস্টমার শপ
        </a>
      </div>
    </header>

    <nav class="admin-nav-tabs">
      <button class="nav-tab-item active" onclick="switchTab('dashboard', this)">
        <span>📊</span> ড্যাশবোর্ড
      </button>
      <button class="nav-tab-item" onclick="switchTab('orders', this)">
        <span>📋</span> অর্ডার সমূহ <span class="tab-badge" id="pendingBadge">০</span>
      </button>
      <button class="nav-tab-item" onclick="switchTab('products', this)">
        <span>👗</span> পোশাক ম্যানেজমেন্ট
      </button>
      <button class="nav-tab-item" onclick="switchTab('settings', this)">
        <span>⚙️</span> স্টোর সেটিংস
      </button>
    </nav>

    <main class="admin-content">

      <!-- TAB 1: DASHBOARD OVERVIEW -->
      <section id="tabDashboard" class="tab-section active">
        <div class="stat-grid">
          <div class="stat-card">
            <div class="stat-icon icon-revenue">৳</div>
            <span class="stat-title">মোট বিক্রি (Revenue)</span>
            <span class="stat-val" id="statTotalRevenue">৳০</span>
          </div>
          <div class="stat-card">
            <div class="stat-icon icon-orders">📦</div>
            <span class="stat-title">মোট প্রাপ্ত অর্ডার</span>
            <span class="stat-val" id="statTotalOrders">০</span>
          </div>
          <div class="stat-card">
            <div class="stat-icon icon-pending">⏳</div>
            <span class="stat-title">পেন্ডিং অর্ডার</span>
            <span class="stat-val" style="color: var(--accent-red);" id="statPendingOrders">০</span>
          </div>
          <div class="stat-card">
            <div class="stat-icon icon-products">🧵</div>
            <span class="stat-title">মোট পোশাক সংখ্যা</span>
            <span class="stat-val" id="statTotalProducts">০</span>
          </div>
        </div>

        <div class="admin-card" style="background: linear-gradient(135deg, var(--primary-light) 0%, #FFFFFF 100%);">
          <h3 style="font-size: 14px; font-weight: 700; color: var(--primary); margin-bottom: 6px;">দ্রুত অ্যাকশন</h3>
          <p style="font-size: 12px; color: var(--text-muted); margin-bottom: 12px;">দোকানে নতুন কালেকশন যুক্ত করুন অথবা নতুন আসা কাস্টমার অর্ডার প্রসেস করুন।</p>
          <div style="display: flex; gap: 8px;">
            <button class="btn-primary" onclick="openAddProductModal()">
              <span>➕</span> নতুন পোশাক যোগ
            </button>
            <button class="btn-secondary" onclick="switchTabById('orders')">
              <span>📋</span> পেন্ডিং অর্ডার দেখুন
            </button>
          </div>
        </div>

        <div class="admin-card">
          <div class="card-title-row">
            <h3 class="card-title"><span>⚡</span> সর্বশেষ অর্ডারসমূহ</h3>
            <a href="javascript:void(0)" onclick="switchTabById('orders')" style="font-size: 12px; color: var(--primary); font-weight: 700; text-decoration: none;">সবগুলো দেখুন ➔</a>
          </div>
          <div id="recentOrdersContainer"></div>
        </div>
      </section>

      <!-- TAB 2: ORDERS MANAGEMENT -->
      <section id="tabOrders" class="tab-section">
        <div class="card-title-row">
          <h3 class="card-title"><span>📋</span> গ্রাহকের অর্ডার তালিকা</h3>
          <span style="font-size: 12px; color: var(--text-muted);">মোট: <strong id="orderCountDisplay">০</strong></span>
        </div>

        <div class="order-filter-bar">
          <button class="filter-chip active" onclick="filterAdminOrders('all', this)">সব অর্ডার</button>
          <button class="filter-chip" onclick="filterAdminOrders('পেন্ডিং', this)">পেন্ডিং</button>
          <button class="filter-chip" onclick="filterAdminOrders('কনফার্মড', this)">কনফার্মড</button>
          <button class="filter-chip" onclick="filterAdminOrders('শিপড', this)">শিপড</button>
          <button class="filter-chip" onclick="filterAdminOrders('ডেলিভার্ড', this)">ডেলিভার্ড</button>
          <button class="filter-chip" onclick="filterAdminOrders('বাতিল', this)">বাতিল</button>
        </div>

        <div id="adminOrdersFullList"></div>
      </section>

      <!-- TAB 3: PRODUCTS MANAGEMENT -->
      <section id="tabProducts" class="tab-section">
        <div class="card-title-row">
          <h3 class="card-title"><span>👗</span> পোশাক তালিকা ও স্টক</h3>
          <button class="btn-primary" onclick="openAddProductModal()">
            <span>➕</span> নতুন পোশাক যোগ
          </button>
        </div>

        <div style="margin-bottom: 14px;">
          <input type="text" class="form-input" id="adminProdSearch" placeholder="নাম বা ক্যাটাগরি দিয়ে খুঁজুন..." oninput="handleAdminProductSearch(this.value)">
        </div>

        <div id="adminProductList"></div>
      </section>

      <!-- TAB 4: STORE SETTINGS -->
      <section id="tabSettings" class="tab-section">
        <div class="admin-card">
          <h3 class="card-title" style="margin-bottom: 12px;"><span>🏪</span> দোকানের মূল তথ্য</h3>
          <div class="form-group"><label class="form-label">দোকানের নাম (বাংলায়)</label><input type="text" class="form-input" id="setStoreName"></div>
          <div class="form-group"><label class="form-label">লোগো মনোগ্রাম (১-২ অক্ষর)</label><input type="text" class="form-input" id="setStoreLogo" maxlength="3"></div>
          <button class="btn-primary" style="width: 100%;" onclick="saveStoreGeneralSettings()">সংরক্ষণ করুন</button>
        </div>

        <div class="admin-card">
          <h3 class="card-title" style="margin-bottom: 12px;"><span>🚚</span> ডেলিভারি চার্জ নির্ধারণ</h3>
          <div style="display: flex; gap: 10px;">
            <div class="form-group" style="flex: 1;"><label class="form-label">ঢাকা সিটি (৳)</label><input type="number" class="form-input" id="setDhakaFee"></div>
            <div class="form-group" style="flex: 1;"><label class="form-label">ঢাকার বাইরে (৳)</label><input type="number" class="form-input" id="setOutsideFee"></div>
          </div>
          <button class="btn-primary" s
