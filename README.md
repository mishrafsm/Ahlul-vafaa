<!DOCTYPE html>
<html lang="ta">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>அஹ்லுல் வஃபா - اهل الوفاء</title>
    <!-- Google Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Amiri:wght@700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Outlined" rel="stylesheet">
    <style>
        :root {
            --primary: #0D9488;
            --primary-dark: #0F766E;
            --primary-light: #CCFBF1;
            --accent-teal: #14B8A6;
            --bg-main: #0F172A;
            --surface: #FFFFFF;
            --text-main: #0F172A;
            --text-sub: #64748B;
            --border-shading: rgba(13, 148, 136, 0.4);
            --card-shading: 0 10px 30px -5px rgba(13, 148, 136, 0.15), 0 0 0 1.5px rgba(13, 148, 136, 0.25);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: linear-gradient(135deg, #090D16 0%, #0F172A 50%, #134E4A 100%);
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
            background: #F8FAFC;
            display: flex;
            flex-direction: column;
            box-shadow: 0 25px 60px rgba(0, 0, 0, 0.5), 0 0 40px rgba(13, 148, 136, 0.2);
            position: relative;
            overflow: hidden;
            border-radius: 36px;
            border: 2px solid rgba(13, 148, 136, 0.4);
        }

        @media (max-width: 440px) {
            .app-container {
                height: 100vh;
                max-height: 100vh;
                border-radius: 0;
                border: none;
            }
        }

        /* App Bar with Logo & Large Title */
        .app-bar {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            padding: 14px 18px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid rgba(13, 148, 136, 0.25);
            z-index: 20;
            box-shadow: 0 4px 20px rgba(13, 148, 136, 0.08);
        }

        .brand-box {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-circle {
            width: 48px;
            height: 48px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            box-shadow: 0 8px 20px rgba(13, 148, 136, 0.4);
            border: 2px solid #5EEAD4;
            position: relative;
        }

        .logo-circle::after {
            content: '⚖️';
            font-size: 20px;
        }

        .app-title-box {
            display: flex;
            flex-direction: column;
        }

        .decorated-title {
            font-size: 19px;
            font-weight: 800;
            background: linear-gradient(135deg, #0F766E 0%, #0D9488 50%, #14B8A6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.4px;
        }

        .arabic-subtitle {
            font-family: 'Amiri', serif;
            font-size: 13px;
            color: #0D9488;
            font-weight: 700;
            letter-spacing: 0.5px;
            opacity: 0.95;
        }

        /* Content Scroll Area */
        .content {
            flex: 1;
            overflow-y: auto;
            padding: 20px 20px 100px 20px;
            background: #F1F5F9;
        }

        .content::-webkit-scrollbar {
            display: none;
        }

        .tab-content {
            display: none;
            animation: fadeInLux 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeInLux {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Luxury Hero Banner */
        .banner {
            background: linear-gradient(135deg, #0F766E 0%, #0D9488 50%, #042F2E 100%);
            color: white;
            padding: 26px;
            border-radius: 26px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 15px 35px rgba(13, 148, 136, 0.3);
            margin-bottom: 24px;
            position: relative;
            overflow: hidden;
            border: 2px solid rgba(94, 234, 212, 0.4);
        }

        .banner h2 {
            font-size: 18px;
            font-weight: 800;
            margin-bottom: 6px;
        }

        .banner p {
            font-size: 12px;
            opacity: 0.9;
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
        }

        /* Summary Grid */
        .summary-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 14px;
            margin-bottom: 24px;
        }

        .summary-card {
            background: #FFFFFF;
            padding: 18px;
            border-radius: 22px;
            border: 1.5px solid rgba(13, 148, 136, 0.3);
            box-shadow: var(--card-shading);
        }

        .summary-card.full-width {
            grid-column: span 2;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 18px 22px;
            background: linear-gradient(135deg, #FFFFFF 0%, #F0FDFA 100%);
            border: 1.5px solid #5EEAD4;
        }

        .summary-card .icon-box {
            width: 42px;
            height: 42px;
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
            border: 1px solid #5EEAD4;
        }

        .summary-card.pending .icon-box { background: #FEF3C7; color: #D97706; border: 1px solid #FDE68A; }
        .summary-card.completed .icon-box { background: #D1FAE5; color: #059669; border: 1px solid #A7F3D0; }

        .summary-card h3 {
            font-size: 24px;
            font-weight: 800;
        }

        .summary-card.pending h3 { color: #D97706; }
        .summary-card.completed h3 { color: #059669; }
        .summary-card.full-width h3 { color: var(--primary); font-size: 21px; }

        .summary-card p {
            font-size: 12px;
            color: var(--text-sub);
            font-weight: 600;
            margin-top: 2px;
        }

        /* Cards with Admin Action Buttons */
        .card-item {
            background: #FFFFFF;
            padding: 20px;
            border-radius: 22px;
            border: 1.5px solid rgba(13, 148, 136, 0.25);
            margin-bottom: 14px;
            box-shadow: var(--card-shading);
            position: relative;
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
        }

        .card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 12px;
            color: var(--text-sub);
            font-weight: 500;
            border-top: 1px solid rgba(13, 148, 136, 0.15);
            padding-top: 12px;
            margin-top: 4px;
        }

        /* Admin Controls Toolbar inside Cards */
        .admin-toolbar {
            display: flex;
            gap: 6px;
            background: #F8FAFC;
            padding: 6px 10px;
            border-radius: 12px;
            border: 1px solid #CBD5E1;
            margin-top: 12px;
            align-items: center;
            justify-content: flex-end;
        }

        .admin-toolbar button {
            background: white;
            border: 1px solid #CBD5E1;
            padding: 4px 8px;
            border-radius: 8px;
            font-size: 11px;
            font-weight: 700;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 2px;
            color: var(--text-main);
        }

        .admin-toolbar button:hover {
            background: var(--primary-light);
            border-color: var(--primary);
            color: var(--primary);
        }

        .admin-toolbar button.delete-btn:hover {
            background: #FEE2E2;
            border-color: #EF4444;
            color: #EF4444;
        }

        /* Badges */
        .badge {
            padding: 6px 12px;
            border-radius: 30px;
            font-size: 11px;
            font-weight: 700;
        }

        .badge.pending { background: #FEF3C7; color: #B45309; border: 1px solid #FDE68A; }
        .badge.completed { background: #D1FAE5; color: #065F46; border: 1px solid #A7F3D0; }
        .badge.amount { background: #E0F2FE; color: #0369A1; font-size: 13px; font-weight: 800; border: 1px solid #BAE6FD; }
        .badge.admin { background: var(--primary-light); color: var(--primary); border: 1px solid #5EEAD4; }

        /* Bank Box */
        .bank-box {
            background: linear-gradient(135deg, #FFFFFF 0%, #F0FDFA 100%);
            border: 2px solid #5EEAD4;
            padding: 24px;
            border-radius: 26px;
            margin-bottom: 24px;
            box-shadow: 0 15px 35px rgba(13, 148, 136, 0.2);
        }

        .bank-box h3 {
            font-size: 15px;
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

        /* Profile Section */
        .profile-header {
            text-align: center;
            padding: 10px 0 20px 0;
        }

        .avatar-circle {
            width: 88px;
            height: 88px;
            background: linear-gradient(135deg, var(--primary-light), #99F6E4);
            color: var(--primary);
            font-size: 32px;
            font-weight: 800;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 16px;
            box-shadow: 0 12px 30px rgba(13, 148, 136, 0.3);
            border: 3px solid #FFFFFF;
        }

        .profile-tile {
            background: #FFFFFF;
            padding: 16px 20px;
            border-radius: 20px;
            border: 1.5px solid rgba(13, 148, 136, 0.25);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 16px;
            box-shadow: var(--card-shading);
        }

        .profile-tile span.material-icons-outlined {
            color: var(--primary);
            background: var(--primary-light);
            padding: 10px;
            border-radius: 14px;
            border: 1px solid #5EEAD4;
        }

        /* Secret Admin Button & Customization Panel */
        .admin-action-box {
            text-align: center;
            margin-top: 35px;
        }

        .secret-btn {
            background: transparent;
            border: 1.5px dashed rgba(13, 148, 136, 0.4);
            padding: 14px 26px;
            border-radius: 18px;
            color: #64748B;
            font-size: 12px;
            font-weight: 600;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .customization-panel {
            background: #FFFFFF;
            padding: 16px;
            border-radius: 18px;
            border: 1.5px solid var(--primary);
            margin-top: 15px;
            text-align: left;
            display: none;
        }

        .customization-panel h4 {
            font-size: 13px;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--primary);
        }

        /* Bottom Navigation Bar */
        .bottom-nav {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-top: 2px solid rgba(13, 148, 136, 0.2);
            display: flex;
            justify-content: space-around;
            padding: 12px 6px 20px 6px;
            z-index: 20;
            box-shadow: 0 -15px 35px rgba(13, 148, 136, 0.1);
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
            flex: 1;
        }

        .nav-item span.material-icons-outlined {
            font-size: 22px;
        }

        .nav-item.active {
            color: var(--primary);
            font-weight: 800;
        }

        /* FAB */
        .fab {
            position: absolute;
            bottom: 92px;
            right: 20px;
            background: linear-gradient(135deg, var(--primary) 0%, #14B8A6 100%);
            color: white;
            width: 58px;
            height: 58px;
            border-radius: 50%;
            border: none;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 12px 30px rgba(13, 148, 136, 0.5);
            cursor: pointer;
            display: none;
            z-index: 25;
            border: 3px solid #FFFFFF;
        }

        /* Modals */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(8px);
            justify-content: center;
            align-items: center;
            padding: 20px;
            z-index: 100;
        }

        .modal.open { display: flex; }

        .modal-card {
            background: #FFFFFF;
            padding: 28px;
            border-radius: 30px;
            width: 100%;
            max-width: 380px;
            box-shadow: 0 25px 60px rgba(0,0,0,0.3);
            border: 2px solid rgba(13, 148, 136, 0.4);
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
            border: 1.5px solid rgba(13, 148, 136, 0.3);
            border-radius: 14px;
            font-size: 14px;
            outline: none;
            background: #F8FAFC;
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
        }

        .btn-sec { background: #F1F5F9; color: var(--text-main); border: 1.5px solid rgba(13, 148, 136, 0.3); }
        .btn-pri { background: var(--primary); color: white; box-shadow: 0 8px 20px rgba(13, 148, 136, 0.3); }
    </style>
</head>
<body>

<div class="app-container">
    <!-- App Header with Logo & Large Title -->
    <div class="app-bar">
        <div class="brand-box">
            <div class="logo-circle"></div>
            <div class="app-title-box">
                <div class="decorated-title">✦ அஹ்லுல் வஃபா ✦</div>
                <div class="arabic-subtitle">اهل الوفاء - சேவை மையம்</div>
            </div>
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
            
            <!-- Admin Customization & Management Panel -->
            <div class="customization-panel" id="adminPanel" style="display:none;">
                <h4>⚙️ நிர்வாகி எடிட்டிங் கட்டுப்பாடுகள்</h4>
                <div class="form-group" style="margin-bottom: 10px;">
                    <label>தீம் கலர் மாற்ற (Theme Color)</label>
                    <input type="color" id="themeColorPicker" value="#0D9488" onchange="changeThemeColor(this.value)" style="height: 38px; padding: 2px; cursor: pointer;">
                </div>
                <button class="btn btn-sec" onclick="openPasswordModal()" style="width: 100%; margin-bottom: 8px; font-size: 12px;">🔑 கடவுச்சொல்லை மாற்றுக</button>
                <button class="btn btn-sec" onclick="logoutAdmin()" style="width: 100%; color: #EF4444; border-color: #FCA5A5; font-size: 12px;">வெளியேறு (Logout Admin)</button>
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

<!-- Change Password Modal -->
<div class="modal" id="passwordModal">
    <div class="modal-card">
        <h3>புதிய கடவுச்சொல் அமைக்க</h3>
        <div class="form-group">
            <label>புதிய கடவுச்சொல் (New Password)</label>
            <input type="password" id="newPasswordInput" placeholder="புதிய பாஸ்வேர்ட்">
        </div>
        <div class="modal-actions">
            <button class="btn btn-sec" onclick="closePasswordModal()">ரத்து</button>
            <button class="btn btn-pri" onclick="saveNewPassword()">மாற்று</button>
        </div>
    </div>
</div>

<!-- Add/Edit Record Modal -->
<div class="modal" id="addServiceModal">
    <div class="modal-card">
        <h3 id="modalTitle">புதிய பதிவு சேர்த்தல்</h3>
        <input type="hidden" id="editId" value="">
        <div class="form-group" id="typeGroup">
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
            <button class="btn btn-pri" onclick="saveNewEntry()">சேமி</button>
        </div>
    </div>
</div>

<script>
    let isAdmin = false;
    let adminPassword = '12345'; // ஆரம்பகட்ட பாஸ்வேர்ட்

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
        services.slice(0, 2).forEach((s, idx) => { recentHtml += createServiceCardHtml(s, idx, 'service'); });
        document.getElementById('recentServicesList').innerHTML = recentHtml || '<p style="color:var(--text-sub); text-align:center; padding:15px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>';

        let pendingHtml = pending.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        pending.forEach((s, idx) => { pendingHtml += createServiceCardHtml(s, idx, 'service'); });
        document.getElementById('pendingServicesList').innerHTML = pendingHtml;

        let completedHtml = completed.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        completed.forEach((s, idx) => { completedHtml += createServiceCardHtml(s, idx, 'service'); });
        document.getElementById('completedServicesList').innerHTML = completedHtml;

        let donorsHtml = donors.length === 0 ? '<p style="color:var(--text-sub); text-align:center; padding:30px; font-size:13px;">தரவுகள் எதுவும் இல்லை</p>' : '';
        donors.forEach((d, idx) => {
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
                    ${isAdmin ? `
                    <div class="admin-toolbar">
                        <button onclick="moveItem('donor', ${idx}, 'up')"><span class="material-icons-outlined" style="font-size:14px;">arrow_upward</span>மேல்</button>
                        <button onclick="moveItem('donor', ${idx}, 'down')"><span class="material-icons-outlined" style="font-size:14px;">arrow_downward</span>கீழ்</button>
                        <button onclick="editDonor(${d.id})"><span class="material-icons-outlined" style="font-size:14px;">edit</span>மாற்று</button>
                        <button class="delete-btn" onclick="deleteItem('donor', ${d.id})"><span class="material-icons-outlined" style="font-size:14px;">delete</span>அழி</button>
                    </div>` : ''}
                </div>
            `;
        });
        document.getElementById('donorsList').innerHTML = donorsHtml;

        document.getElementById('addFabBtn').style.display = isAdmin ? 'flex' : 'none';
        document.getElementById('adminBadge').style.display = isAdmin ? 'block' : 'none';
        document.getElementById('adminControlSection').style.display = isAdmin ? 'none' : 'block';
        document.getElementById('adminPanel').style.display = isAdmin ? 'block' : 'none';
    }

    function createServiceCardHtml(s, idx, type) {
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
                ${isAdmin ? `
                <div class="admin-toolbar">
                    <button onclick="moveItem('service', ${idx}, 'up')"><span class="material-icons-outlined" style="font-size:14px;">arrow_upward</span>மேல்</button>
                    <button onclick="moveItem('service', ${idx}, 'down')"><span class="material-icons-outlined" style="font-size:14px;">arrow_downward</span>கீழ்</button>
                    <button onclick="editService(${s.id})"><span class="material-icons-outlined" style="font-size:14px;">edit</span>மாற்று</button>
                    <button class="delete-btn" onclick="deleteItem('service', ${s.id})"><span class="material-icons-outlined" style="font-size:14px;">delete</span>அழி</button>
                </div>` : ''}
            </div>
        `;
    }

    // Move items Up/Down
    function moveItem(type, index, direction) {
        let arr = type === 'service' ? services : donors;
        if (direction === 'up' && index > 0) {
            let temp = arr[index];
            arr[index] = arr[index - 1];
            arr[index - 1] = temp;
        } else if (direction === 'down' && index < arr.length - 1) {
            let temp = arr[index];
            arr[index] = arr[index + 1];
            arr[index + 1] = temp;
        }
        renderApp();
    }

    // Delete item
    function deleteItem(type, id) {
        if (confirm('நிச்சயமாக இதை அழிக்க விரும்புகிறீர்களா?')) {
            if (type === 'service') {
                services = services.filter(s => s.id !== id);
            } else {
                donors = donors.filter(d => d.id !== id);
            }
            renderApp();
        }
    }

    // Edit functions
    function editService(id) {
        const s = services.find(item => item.id === id);
        if (s) {
            document.getElementById('editId').value = s.id;
            document.getElementById('modalTitle').innerText = 'சேவையைத் திருத்துக';
            document.getElementById('addType').value = 'service';
            document.getElementById('typeGroup').style.display = 'none';
            document.getElementById('serviceFields').style.display = 'block';
            document.getElementById('donorFields').style.display = 'none';
            document.getElementById('newTitle').value = s.title;
            document.getElementById('newDesc').value = s.description;
            document.getElementById('newDate').value = s.date;
            document.getElementById('addServiceModal').classList.add('open');
        }
    }

    function editDonor(id) {
        const d = donors.find(item => item.id === id);
        if (d) {
            document.getElementById('editId').value = d.id;
            document.getElementById('modalTitle').innerText = 'நன்கொடையாளரைத் திருத்துக';
            document.getElementById('addType').value = 'donor';
            document.getElementById('typeGroup').style.display = 'none';
            document.getElementById('serviceFields').style.display = 'none';
            document.getElementById('donorFields').style.display = 'block';
            document.getElementById('donorName').value = d.name;
            document.getElementById('donorAmount').value = d.amount;
            document.getElementById('donorDate').value = d.date;
            document.getElementById('addServiceModal').classList.add('open');
        }
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
        if(u === 'admin' && p === adminPassword) {
            isAdmin = true;
            closeLoginModal();
            renderApp();
        } else {
            alert('தவறான பயனர் பெயர் அல்லது கடவுச்சொல்!');
        }
    }

    function logoutAdmin() {
        isAdmin = false;
        renderApp();
    }

    // Password Change Functions
    function openPasswordModal() { document.getElementById('passwordModal').classList.add('open'); }
    function closePasswordModal() { document.getElementById('passwordModal').classList.remove('open'); }

    function saveNewPassword() {
        const newPass = document.getElementById('newPasswordInput').value;
        if(newPass.trim() !== '') {
            adminPassword = newPass;
            closePasswordModal();
            document.getElementById('newPasswordInput').value = '';
            alert('கடவுச்சொல் வெற்றிகரமாக மாற்றப்பட்டது!');
        } else {
            alert('சரியான கடவுச்சொல்லை உள்ளிடவும்');
        }
    }

    function openAddModal() {
        document.getElementById('editId').value = '';
        document.getElementById('modalTitle').innerText = 'புதிய பதிவு சேர்த்தல்';
        document.getElementById('typeGroup').style.display = 'block';
        toggleAddFields();
        document.getElementById('addServiceModal').classList.add('open');
    }
    
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
        const editId = document.getElementById('editId').value;
        const type = document.getElementById('addType').value;

        if (editId) {
            if (type === 'service') {
                const s = services.find(item => item.id == editId);
                if (s) {
                    s.title = document.getElementById('newTitle').value;
                    s.description = document.getElementById('newDesc').value;
                    s.date = document.getElementById('newDate').value;
                }
            } else {
                const d = donors.find(item => item.id == editId);
                if (d) {
                    d.name = document.getElementById('donorName').value;
                    d.amount = document.getElementById('donorAmount').value;
                    d.date = document.getElementById('donorDate').value;
                }
            }
        } else {
            if(type === 'service') {
                const title = document.getElementById('newTitle').value;
                const desc = document.getElementById('newDesc').value;
                const date = document.getElementById('newDate').value;
                if(title && desc && date) {
                    services.push({ id: Date.now(), title, description: desc, date, isCompleted: false });
                } else {
                    alert('அனைத்து விவரங்களையும் நிரப்பவும்');
                    return;
                }
            } else {
                const name = document.getElementById('donorName').value;
                const amount = document.getElementById('donorAmount').value;
                const date = document.getElementById('donorDate').value;
                if(name && amount && date) {
                    donors.push({ id: Date.now(), name, amount, date });
                } else {
                    alert('அனைத்து விவரங்களையும் நிரப்பவும்');
                    return;
                }
            }
        }
        closeAddModal();
        renderApp();
    }

    function changeThemeColor(color) {
        document.documentElement.style.setProperty('--primary', color);
    }

    renderApp();
</script>

</body>
</html>
