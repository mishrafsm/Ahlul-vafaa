<!DOCTYPE html>
<html lang="ta">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>அஹ்லுல் வஃபா - اهل الوفاء</title>
    <!-- Google Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Outlined" rel="stylesheet">
    <style>
        :root {
            --primary: #0F766E;
            --primary-dark: #115E59;
            --primary-light: #CCFBF1;
            --accent-teal: #14B8A6;
            --bg-main: #F4F8FB;
            --surface: #FFFFFF;
            --text-main: #0F172A;
            --text-sub: #64748B;
            --border: #CBD5E1;
            --border-light: #E2E8F0;
            --shadow-premium: 0 25px 50px -12px rgba(15, 23, 42, 0.18), 0 0 0 1px rgba(15, 118, 110, 0.08);
            --card-shadow: 0 10px 25px -5px rgba(15, 23, 42, 0.06), 0 0 0 1px rgba(203, 213, 225, 0.6);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: linear-gradient(135deg, #E2E8F0 0%, #F8FAFC 50%, #E0F2FE 100%);
            color: var(--text-main);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 10px;
        }

        .app-container {
            width: 100%;
            max-width: 440px;
            height: 100vh;
            max-height: 880px;
            background: var(--surface);
            display: flex;
            flex-direction: column;
            box-shadow: var(--shadow-premium);
            position: relative;
            overflow: hidden;
            border-radius: 36px;
            border: 2px solid rgba(255, 255, 255, 0.9);
            outline: 1px solid rgba(15, 118, 110, 0.2);
        }

        @media (max-width: 440px) {
            .app-container {
                height: 100vh;
                max-height: 100vh;
                border-radius: 0;
                border: none;
                outline: none;
            }
        }

        /* High-Class App Bar */
        .app-bar {
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(16px);
            padding: 18px 24px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1.5px solid var(--border-light);
            z-index: 20;
            box-shadow: 0 4px 20px rgba(0,0,0,0.02);
        }

        .app-title h1 {
            font-size: 17px;
            font-weight: 800;
            color: var(--text-main);
            letter-spacing: -0.4px;
        }

        .app-title p {
            font-size: 11px;
            color: var(--text-sub);
            font-weight: 600;
            letter-spacing: 0.2px;
        }

        /* Content Scroll Area */
        .content {
            flex: 1;
            overflow-y: auto;
            padding: 20px 20px 100px 20px;
            background: var(--bg-main);
        }

        .content::-webkit-scrollbar {
            display: none;
        }

        .tab-content {
            display: none;
            animation: slideUp 0.35s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .tab-content.active {
            display: block;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(12px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Premium Hero Banner */
        .banner {
            background: linear-gradient(135deg, #0F766E 0%, #0D9488 50%, #14B8A6 100%);
            color: white;
            padding: 26px;
            border-radius: 24px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 12px 30px rgba(15, 118, 110, 0.25);
            margin-bottom: 24px;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .banner::before {
            content: '';
            position: absolute;
            top: -50px;
            right: -50px;
            width: 140px;
            height: 140px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 50%;
        }

        .banner h2 {
            font-size: 18px;
            font-weight: 800;
            margin-bottom: 6px;
            letter-spacing: -0.3px;
        }

        .banner p {
            font-size: 12px;
            opacity: 0.95;
            font-weight: 500;
        }

        /* Section Header */
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 14px;
        }

        .section-title {
            font-size: 15px;
            font-weight: 700;
            color: var(--text-main);
            letter-spacing: -0.3px;
        }

        /* Summary Grid */
        .summary-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-bottom: 24px;
        }

        .summary-card {
            background: var(--surface);
            padding: 18px;
            border-radius: 20px;
            border: 1.5px solid var(--border);
            box-shadow: var(--card-shadow);
            transition: transform 0.2s ease;
        }

        .summary-card.full-width {
            grid-column: span 2;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 16px 20px;
            background: linear-gradient(135deg, #FFFFFF 0%, #F0FDFA 100%);
            border-color: #5EEAD4;
        }

        .summary-card .icon-box {
            width: 40px;
            height: 40px;
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 12px;
        }

        .summary-card.full-width .icon-box {
            margin-bottom: 0;
            background: #CCFBF1;
            color: var(--primary);
        }

        .summary-card.pending .icon-box { background: #FEF3C7; color: #D97706; }
        .summary-card.completed .icon-box { background: #D1FAE5; color: #059669; }

        .summary-card h3 {
            font-size: 22px;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .summary-card.pending h3 { color: #D97706; }
        .summary-card.completed h3 { color: #059669; }
        .summary-card.full-width h3 { color: var(--primary); font-size: 20px; }

        .summary-card p {
            font-size: 12px;
            color: var(--text-sub);
            font-weight: 600;
            margin-top: 2px;
        }

        /* Cards for Services & Donors */
        .card-item {
            background: var(--surface);
            padding: 20px;
            border-radius: 20px;
            border: 1.5px solid var(--border);
            margin-bottom: 14px;
            box-shadow: var(--card-shadow);
            transition: all 0.2s ease;
        }

        .card-item:hover {
            border-color: var(--primary);
            box-shadow: 0 12px 30px -5px rgba(15, 118, 110, 0.12);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 8px;
        }

        .card-header h4 {
            font-size: 15px;
            font-weight: 700;
            color: var(--text-main);
            line-height: 1.4;
        }

        .card-item p {
            font-size: 13px;
            color: var(--text-sub);
            margin-bottom: 14px;
            line-height: 1.5;
            font-weight: 400;
        }

        .card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 12px;
            color: var(--text-sub);
            font-weight: 500;
            border-top: 1px solid var(--border-light);
            padding-top: 12px;
            margin-top: 4px;
        }

        /* Badges */
        .badge {
            padding: 6px 12px;
            border-radius: 30px;
            font-size: 11px;
            font-weight: 700;
            letter-spacing: 0.2px;
        }

        .badge.pending { background: #FEF3C7; color: #B45309; border: 1px solid #FDE68A; }
        .badge.completed { background: #D1FAE5; color: #065F46; border: 1px solid #A7F3D0; }
        .badge.amount { background: #E0F2FE; color: #0369A1; font-size: 13px; font-weight: 800; border: 1px solid #BAE6FD; }
        .badge.admin { background: var(--primary-light); color: var(--primary); border: 1px solid #5EEAD4; }

        /* Bank Account Glass Box */
        .bank-box {
            background: linear-gradient(135deg, #FFFFFF 0%, #F0FDFA 100%);
            border: 1.5px solid #5EEAD4;
            padding: 22px;
            border-radius: 24px;
            margin-bottom: 24px;
            box-shadow: var(--card-shadow);
        }

        .bank-box h3 {
            font-size: 14px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 14px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .bank-details {
            font-size: 13px;
            color: var(--text-sub);
            line-height: 1.7;
            font-weight: 500;
        }

        .bank-details strong {
            color: var(--text-main);
        }

        /* Profile Section */
        .profile-header {
            text-align: center;
            padding: 10px 0 20px 0;
        }

        .avatar-circle {
            width: 84px;
            height: 84px;
            background: linear-gradient(135deg, var(--primary-light), #99F6E4);
            color: var(--primary);
            font-size: 30px;
            font-weight: 800;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 16px;
            box-shadow: 0 10px 25px rgba(15, 118, 110, 0.2);
            border: 2px solid #FFFFFF;
        }

        .profile-tile {
            background: var(--surface);
            padding: 16px 18px;
            border-radius: 18px;
            border: 1.5px solid var(--border);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 16px;
            box-shadow: var(--card-shadow);
        }

        .profile-tile span.material-icons-outlined {
            color: var(--primary);
            background: var(--primary-light);
            padding: 10px;
            border-radius: 14px;
        }

        /* Secret Admin Button */
        .admin-action-box {
            text-align: center;
            margin-top: 35px;
        }

        .secret-btn {
            background: transparent;
            border: 1.5px dashed var(--border);
            padding: 12px 24px;
            border-radius: 16px;
            color: #64748B;
            font-size: 12px;
            font-weight: 600;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s;
        }

        .secret-btn:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
        }

        /* Bottom Floating Navigation Bar */
        .bottom-nav {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-top: 1.5px solid var(--border-light);
            display: flex;
            justify-content: space-around;
            padding: 12px 6px 18px 6px;
            z-index: 20;
            box-shadow: 0 -10px 30px rgba(0,0,0,0.04);
        }

        .nav-item {
            background: none;
            border: none;
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--text-sub);
            font-size: 10px;
            font-weight: 600;
            cursor: pointer;
            gap: 4px;
            transition: all 0.2s;
            flex: 1;
        }

        .nav-item span.material-icons-outlined {
            font-size: 22px;
            transition: transform 0.2s;
        }

        .nav-item.active {
            color: var(--primary);
            font-weight: 800;
        }

        .nav-item.active span.material-icons-outlined {
            transform: translateY(-2px);
        }

        /* Floating Action Button (FAB) */
        .fab {
            position: absolute;
            bottom: 90px;
            right: 20px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent-teal) 100%);
            color: white;
            width: 56px;
            height: 56px;
            border-radius: 50%;
            border: none;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 25px rgba(15, 118, 110, 0.4);
            cursor: pointer;
            display: none;
            z-index: 25;
            transition: transform 0.2s;
            border: 2px solid #FFFFFF;
        }

        .fab:hover { transform: scale(1.08); }

        /* Modals / Dialogs */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(15, 23, 42, 0.55);
            backdrop-filter: blur(6px);
            justify-content: center;
            align-items: center;
            padding: 20px;
            z-index: 100;
        }

        .modal.open { display: flex; }

        .modal-card {
            background: var(--surface);
            padding: 26px;
            border-radius: 28px;
            width: 100%;
            max-width: 380px;
            box-shadow: 0 25px 50px -12px rgba(15, 23, 42, 0.25);
            border: 1.5px solid var(--border);
            animation: scaleIn 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.92); }
            to { opacity: 1; transform: scale(1); }
        }

        .modal-card h3 {
            font-size: 18px;
            font-weight: 800;
            margin-bottom: 20px;
            color: var(--text-main);
            letter-spacing: -0.3px;
        }

        .form-group {
            margin-bottom: 16px;
        }

        .form-group label {
            display: block;
            font-size: 12px;
            font-weight: 700;
            color: var(--text-sub);
            margin-bottom: 6px;
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 13px 16px;
            border: 1.5px solid var(--border);
            border-radius: 14px;
            font-size: 14px;
            outline: none;
            background: #F8FAFC;
            color: var(--text-main);
            font-weight: 500;
            transition: border-color 0.2s;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            border-color: var(--primary);
            background: #FFFFFF;
        }

        .modal-actions {
            display: flex;
            justify-content: flex-end;
            gap: 10px;
            margin-top: 24px;
        }

        .btn {
            padding: 12px 20px;
            border-radius: 14px;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            transition: opacity 0.2s;
        }

        .btn-sec { background: #F1F5F9; color: var(--text-main); border: 1.5px solid var(--border-light); }
        .btn-pri { background: var(--primary); color: white; box-shadow: 0 4px 12px rgba(15, 118, 110, 0.3); }
    </style>
</head>
<body>

<div class="app-container">
    <!-- App Header -->
    <div class="app-bar">
        <div class="app-title">
            <h1>அஹ்லுல் வஃபா</h1>
            <p>اهل الوفاء - சேவை மையம்</p>
        </div>
        <div id="adminBadge" style="display:none;">
            <span class="badge admin">அட்மின் மோட்</span>
        </div>
    </div>

    <!-- Main Content Body -->
    <div class="content">
        <!-- 1. Dashboard Tab -->
        <div id="tab-dashboard" class="tab-content active">
            <div class="banner">
                <div>
                    <h2>அஸ்ஸலாமு அலைக்கும்!</h2>
                    <p>நன்மையை ஏவுவோம், சேவையே லட்சியம்</p>
                </div>
                <span class="material-icons-outlined" style="font-size: 46px; opacity: 0.95;">volunteer_activism</span>
            </div>

            <div class="section-header">
                <div class="section-title">அமைப்பு சுருக்கம்</div>
            </div>

            <div class="summary-grid">
                <div class="summary-card pending">
                    <div class="icon-box"><span class="material-icons-outlined">hourglass_top</span></div>
                    <h3 id="pendingCount">0</h3>
                    <p>செய்ய வேண்டியவை</p>
                </div>
                <div class="summary-card completed">
                    <div class="icon-box"><span class="material-icons-outlined">check_circle</span></div>
                    <h3 id="completedCount">0</h3>
                    <p>செய்த சேவைகள்</p>
                </div>
                <div class="summary-card full-width">
                    <div>
                        <p>மொத்த நன்கொடை நிதி</p>
                        <h3 id="totalDonation" style="margin-top: 2px;">₹0</h3>
                    </div>
                    <div class="icon-box"><span class="material-icons-outlined">currency_rupee</span></div>
                </div>
            </div>

            <div class="section-header" style="margin-top: 24px;">
                <div class="section-title">சமீபத்திய பணிகள்</div>
            </div>
            <div id="recentServicesList"></div>
        </div>

        <!-- 2. Pending Services Tab -->
        <div id="tab-pending" class="tab-content">
            <div class="section-header">
                <div class="section-title">செய்ய வேண்டிய சேவைகள்</div>
            </div>
            <div id="pendingServicesList"></div>
        </div>

        <!-- 3. Completed Services Tab -->
        <div id="tab-completed" class="tab-content">
            <div class="section-header">
                <div class="section-title">செய்த சேவைகள் (வரலாறு)</div>
            </div>
            <div id="completedServicesList"></div>
        </div>

        <!-- 4. Donations Tab -->
        <div id="tab-donation" class="tab-content">
            <div class="section-header">
                <div class="section-title">நன்கொடை விவரங்கள் & பட்டியல்</div>
            </div>
            
            <div class="bank-box">
                <h3><span class="material-icons-outlined" style="font-size: 20px;">account_balance</span> நேரடி நன்கொடை வழங்க</h3>
                <div class="bank-details">
                    <strong>UPI ID:</strong> ahlulwafa@upi<br>
                    <strong>வங்கி பெயர்:</strong> தமிழ்நாடு கிராம வங்கி<br>
                    <strong>கணக்கு எண்:</strong> XXXXXXXXXXXXXX<br>
                    <strong>IFSC குறியீடு:</strong> TNGB0001234
                </div>
            </div>

            <div class="section-header">
                <div class="section-title">நன்கொடையாளர்கள் பட்டியல்</div>
            </div>
            <div id="donorsList"></div>
        </div>

        <!-- 5. Info & Admin Tab -->
        <div id="tab-info" class="tab-content">
            <div class="profile-header">
                <div class="avatar-circle">اه</div>
                <h2 style="font-size: 18px; font-weight: 800; color: var(--text-main);">அஹ்லுல் வஃபா சேவை அமைப்பு</h2>
                <p style="color: var(--text-sub); font-size: 12px; margin-top: 4px; font-weight: 500;">اهل الوفاء - Verkaadu, Tamil Nadu</p>
            </div>

            <div class="profile-tile">
                <span class="material-icons-outlined">info</span>
                <div>
                    <strong style="font-size: 13px; color: var(--text-main);">அமைப்பின் குறிக்கோள்</strong>
                    <p style="font-size: 12px; color: var(--text-sub); margin-top: 2px;">சமூக சேவை மற்றும் நற்பணிகள்</p>
                </div>
            </div>

            <div class="profile-tile">
                <span class="material-icons-outlined">phone</span>
                <div>
                    <strong style="font-size: 13px; color: var(--text-main);">தொடர்புக்கு / உதவி எண்</strong>
                    <p style="font-size: 12px; color: var(--text-sub); margin-top: 2px;">+91 XXXXXXXXXX</p>
                </div>
            </div>

            <div class="admin-action-box" id="adminControlSection">
                <button class="secret-btn" onclick="openLoginModal()">
                    <span class="material-icons-outlined" style="font-size: 16px;">lock_outline</span>
                    நிர்வாகி பகுதி (Admin Login)
                </button>
            </div>
            <div class="admin-action-box" id="adminLogoutSection" style="display:none;">
                <button class="btn btn-sec" onclick="logoutAdmin()" style="color: #EF4444; border: 1.5px solid #FCA5A5; width: 100%;">
                    வெளியேறு (Logout Admin)
                </button>
            </div>
        </div>
    </div>

    <!-- Admin Floating Add Button -->
    <button class="fab" id="addFabBtn" onclick="openAddModal()">
        <span class="material-icons-outlined" style="font-size: 26px;">add</span>
    </button>

    <!-- Bottom Navigation Bar -->
    <div class="bottom-nav">
        <button class="nav-item active" onclick="switchTab(0, this)">
            <span class="material-icons-outlined">dashboard</span>
            முகப்பு
        </button>
        <button class="nav-item" onclick="switchTab(1, this)">
            <span class="material-icons-outlined">pending_actions</span>
            செயல்முறை
        </button>
        <button class="nav-item" onclick="switchTab(2, this)">
            <span class="material-icons-outlined">task_alt</span>
            முடிந்தது
        </button>
        <button class="nav-item" onclick="switchTab(3, this)">
            <span class="material-icons-outlined">volunteer_activism</span>
            நன்கொடை
        </button>
        <button class="nav-item" onclick="switchTab(4, this)">
            <span class="material-icons-outlined">info</span>
            விபரம்
        </button>
    </div>
</div>

<!-- Login Modal -->
<div class="modal" id="loginModal">
    <div class="modal-card">
        <h3>நிர்வாகி உள்நுழைவு</h3>
        <div class="form-group">
            <label>உபயோகிப்பாளர் பெயர் (Username)</label>
            <input type="text" id="loginUser" placeholder="admin">
        </div>
        <div class="form-group">
            <label>கடவுச்சொல் (Password)</label>
            <input type="password" id="loginPass" placeholder="12345">
        </div>
        <div class="modal-actions">
            <button class="btn btn-sec" onclick="closeLoginModal()">ரத்து</button>
            <button class="btn btn-pri" onclick="verifyLogin()">உள்நுழை</button>
        </div>
    </div>
</div>

<!-- Add Record Modal -->
<div class="modal" id="addServiceModal">
    <div class="modal-card">
        <h3>புதிய பதிவு சேர்த்தல்</h3>
        <div class="form-group">
            <label>பிரிவு</label>
            <select id="addType" onchange="toggleAddFields()">
                <option value="service">சேவை (Service)</option>
                <option value="donor">நன்கொடையாளர் (Donor)</option>
            </select>
        </div>
        
        <div id="serviceFields">
            <div class="form-group">
                <label>சேவையின் தலைப்பு</label>
                <input type="text" id="newTitle" placeholder="தலைப்பு">
            </div>
            <div class="form-group">
                <label>சேவை விவரம்</label>
                <textarea id="newDesc" rows="2" placeholder="விவரம்"></textarea>
            </div>
            <div class="form-group">
                <label>தேதி</label>
                <input type="text" id="newDate" value="2026-10-25">
            </div>
        </div>

        <div id="donorFields" style="display:none;">
            <div class="form-group">
                <label>நன்கொடையாளர் பெயர்</label>
                <input type="text" id="donorName" placeholder="பெயர்">
            </div>
            <div class="form-group">
                <label>வழங்கிய தொகை (₹)</label>
                <input type="number" id="donorAmount" placeholder="5000">
            </div>
            <div class="form-group">
                <label>தேதி</label>
                <input type="text" id="donorDate" value="2026-10-25">
            </div>
        </div>

        <div class="modal-actions">
            <button class="btn btn-sec" onclick="closeAddModal()">ரத்து</button>
            <button class="btn btn-pri" onclick="saveNewEntry()">சேர்</button>
        </div>
    </div>
</div>

<script>
    let isAdmin = false;

    let services = [
        { id: 1, title: 'மருத்துவ உதவி மற்றும் நிதி வழங்கல்', description: 'தேவைப்படும் ஏழை குடும்பத்தின் அவசர மருத்துவச் செலவுக்காக நிதி உதவி.', date: '2026-10-25', isCompleted: false },
        { id: 2, title: 'கல்வி ஊக்கத்தொகை முகாம்', description: 'மாணவர்களுக்கான உயர்கல்வி வழிகாட்டல் மற்றும் கல்வி உபகரணங்கள் வழங்குதல்.', date: '2026-10-28', isCompleted: false },
        { id: 3, title: 'உணவுப் பொதிகள் விநியோகம்', description: 'தேவைப்படுவோருக்கு வீடுகளுக்கே சென்று அத்தியாவசிய உணவுப் பொதிகள் வழங்கப்பட்டது.', date: '2026-10-12', isCompleted: true },
        { id: 4, title: 'சுற்றுப்புறத் தூய்மைப் பணி', description: 'ஊர் பொதுப் பகுதிகள் மற்றும் பள்ளி வளாகம் தூய்மைப்படுத்தப்பட்டது.', date: '2026-10-05', isCompleted: true }
    ];

    let donors = [
        { id: 1, name: 'முஹம்மது அலி', amount: 5000, date: '2026-10-15' },
        { id: 2, name: 'அப்துல் ரஹ்மான்', amount: 3000, date: '2026-10-18' },
        { id: 3, name: 'எஸ்.எம். இப்ராஹிம்', amount: 10000, date: '2026-10-20' }
    ];

    function renderApp() {
        const pending = services.filter(s => !s.isCompleted);
        const completed = services.filter(s => s.isCompleted);

        document.getElementById('pendingCount').innerText = pending.length;
        document.getElementById('completedCount').innerText = completed.length;

        const totalDonationAmount = donors.reduce((sum, d) => sum + Number(d.amount), 0);
        document.getElementById('totalDonation').innerText = '₹' + totalDonationAmount.toLocaleString();

        let recentHtml = '';
        services.slice(0, 2).forEach(s => { recentHtml += createServiceCardHtml(s); });
        document.getElementById('recentServicesList').innerHTML = recentHtml;

        let pendingHtml = pending.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        pending.forEach(s => { pendingHtml += createServiceCardHtml(s); });
        document.getElementById('pendingServicesList').innerHTML = pendingHtml;

        let completedHtml = completed.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        completed.forEach(s => { completedHtml += createServiceCardHtml(s); });
        document.getElementById('completedServicesList').innerHTML = completedHtml;

        let donorsHtml = donors.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        donors.forEach(d => {
            donorsHtml += `
                <div class="card-item">
                    <div class="card-header">
                        <h4>${d.name}</h4>
                        <span class="badge amount">₹${Number(d.amount).toLocaleString()}</span>
                    </div>
                    <div class="card-footer">
                        <span><span class="material-icons-outlined" style="font-size:13px; vertical-align:middle;">calendar_today</span> ${d.date}</span>
                        <span style="color: #059669; font-weight: 700; font-size: 11px;">நன்கொடை பெறப்பட்டது</span>
                    </div>
                </div>
            `;
        });
        document.getElementById('donorsList').innerHTML = donorsHtml;

        document.getElementById('addFabBtn').style.display = isAdmin ? 'flex' : 'none';
        document.getElementById('adminBadge').style.display = isAdmin ? 'block' : 'none';
        document.getElementById('adminControlSection').style.display = isAdmin ? 'none' : 'block';
        document.getElementById('adminLogoutSection').style.display = isAdmin ? 'block' : 'none';
    }

    function createServiceCardHtml(s) {
        return `
            <div class="card-item">
                <div class="card-header">
                    <h4>${s.title}</h4>
                    ${isAdmin ? `<button onclick="toggleStatus(${s.id})" style="background:none; border:none; cursor:pointer; padding: 2px;">
                        <span class="material-icons-outlined" style="font-size: 22px; color: ${s.isCompleted ? '#059669' : '#94A3B8'}">
                            ${s.isCompleted ? 'check_circle' : 'radio_button_unchecked'}
                        </span>
                    </button>` : ''}
                </div>
                <p>${s.description}</p>
                <div class="card-footer">
                    <span><span class="material-icons-outlined" style="font-size:13px; vertical-align:middle; margin-right:2px;">calendar_today</span> ${s.date}</span>
                    <span class="badge ${s.isCompleted ? 'completed' : 'pending'}">${s.isCompleted ? 'முடிந்தது' : 'செயல்முறையில்'}</span>
                </div>
            </div>
        `;
    }

    function toggleStatus(id) {
        const item = services.find(s => s.id === id);
        if(item) {
            item.isCompleted = !item.isCompleted;
            renderApp();
        }
    }

    function switchTab(index, btn) {
        document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
        document.querySelectorAll('.bottom-nav .nav-item').forEach(el => el.classList.remove('active'));

        const tabs = ['tab-dashboard', 'tab-pending', 'tab-completed', 'tab-donation', 'tab-info'];
        document.getElementById(tabs[index]).classList.add('active');
        btn.classList.add('active');
    }

    function openLoginModal() { document.getElementById('loginModal').classList.add('open'); }
    function closeLoginModal() { document.getElementById('loginModal').classList.remove('open'); }
    
    function verifyLogin() {
        const u = document.getElementById('loginUser').value;
        const p = document.getElementById('loginPass').value;
        if(u === 'admin' && p === '12345') {
            isAdmin = true;
            closeLoginModal();
            renderApp();
        } else {
            alert('தவறான கடவுச்சொல்!');
        }
    }

    function logoutAdmin() {
        isAdmin = false;
        renderApp();
    }

    function openAddModal() { document.getElementById('addServiceModal').classList.add('open'); }
    function closeAddModal() { document.getElementById('addServiceModal').classList.remove('open'); }

    function toggleAddFields() {
        const type = document.getElementById('addType').value;
        if(type === 'service') {
            document.getElementById('serviceFields').style.display = 'block';
            document.getElementById('donorFields').style.display = 'none';
        } else {
            document.getElementById('serviceFields').style.display = 'none';
            document.getElementById('donorFields').style.display = 'block';
        }
    }

    function saveNewEntry() {
        const type = document.getElementById('addType').value;
        if(type === 'service') {
            const title = document.getElementById('newTitle').value;
            const desc = document.getElementById('newDesc').value;
            const date = document.getElementById('newDate').value;
            if(title && desc && date) {
                services.push({ id: Date.now(), title, description: desc, date, isCompleted: false });
                closeAddModal();
                renderApp();
                document.getElementById('newTitle').value = '';
                document.getElementById('newDesc').value = '';
            } else {
                alert('அனைத்து விவரங்களையும் நிரப்பவும்');
            }
        } else {
            const name = document.getElementById('donorName').value;
            const amount = document.getElementById('donorAmount').value;
            const date = document.getElementById('donorDate').value;
            if(name && amount && date) {
                donors.push({ id: Date.now(), name, amount, date });
                closeAddModal();
                renderApp();
                document.getElementById('donorName').value = '';
                document.getElementById('donorAmount').value = '';
            } else {
                alert('அனைத்து விவரங்களையும் நிரப்பவும்');
            }
        }
    }

    renderApp();
</script>

</body>
</html>
