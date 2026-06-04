<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>FRANZZ SHOP ID - Digital Store</title>
  <style>
    :root {
      --bg: #0b0c10; --card: #15171c; --card-hover: #1c1f26;
      --gold: #ffd700; --gold-dark: #b8860b; --text: #e0e0e0;
      --border: #2a2d35; --text-muted: #a0a0b0;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', system-ui, sans-serif; }
    body { background: var(--bg); color: var(--text); }
    a { text-decoration: none; color: inherit; }

    header {
      padding: 1rem 5%; background: rgba(11,12,16,0.95);
      display: flex; justify-content: space-between; align-items: center;
      position: sticky; top: 0; z-index: 110; border-bottom: 1px solid var(--border);
      backdrop-filter: blur(10px);
    }
    .logo-container { display: flex; align-items: center; gap: 10px; }
    .logo-img { height: 45px; width: auto; object-fit: contain; border-radius: 8px; }
    .logo-text { font-size: 1.5rem; font-weight: 800; color: var(--gold); text-transform: uppercase; letter-spacing: 1px; }
    .contact-btn {
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      color: #000; padding: 0.5rem 1rem; border-radius: 8px; font-weight: 700; border: none; cursor: pointer;
    }

    .hero { text-align: center; padding: 3rem 1rem 2rem; background: radial-gradient(circle, rgba(255,215,0,0.1) 0%, transparent 70%); }
    .hero h1 { font-size: 2.5rem; color: var(--gold); margin-bottom: 0.5rem; text-shadow: 0 0 10px rgba(255,215,0,0.3); }
    .hero p { color: var(--text-muted); }

    .main-nav {
      display: flex; gap: 0.5rem; padding: 0.8rem 5%; overflow-x: auto;
      background: rgba(11,12,16,0.98); border-bottom: 1px solid var(--border);
      position: sticky; top: 0; z-index: 100; scrollbar-width: none;
      backdrop-filter: blur(10px);
    }
    .main-nav::-webkit-scrollbar { display: none; }
    .main-btn {
      background: var(--card); color: var(--text-muted); border: 1px solid var(--border);
      padding: 0.6rem 1rem; border-radius: 20px; cursor: pointer;
      white-space: nowrap; font-size: 0.9rem; font-weight: 600; transition: 0.2s;
    }
    .main-btn.active {
      background: var(--gold); color: #000; border-color: var(--gold);
      box-shadow: 0 4px 12px rgba(255,215,0,0.3);
    }

    .sub-nav {
      display: none; gap: 0.5rem; padding: 0.7rem 5%; overflow-x: auto;
      background: rgba(21,23,28,0.95); border-bottom: 1px solid var(--gold-dark);
      position: sticky; top: 56px; z-index: 95; scrollbar-width: none;
      animation: slideDown 0.3s ease;
    }
    .sub-nav.active { display: flex; }
    .sub-nav::-webkit-scrollbar { display: none; }
    @keyframes slideDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }
    .sub-btn {
      background: rgba(255,215,0,0.08); color: var(--text-muted); border: 1px solid var(--border);
      padding: 0.5rem 0.9rem; border-radius: 15px; cursor: pointer;
      white-space: nowrap; font-size: 0.8rem; font-weight: 600; transition: 0.2s;
    }
    .sub-btn.active {
      background: var(--gold); color: #000; border-color: var(--gold);
      transform: scale(1.05); box-shadow: 0 4px 10px rgba(255,215,0,0.2);
    }

    .container { max-width: 1200px; margin: 0 auto; padding: 1.5rem 1rem; min-height: 60vh; }
    .section { display: none; animation: fadeIn 0.3s ease; }
    .section.active { display: block; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

    .section-header { margin-bottom: 1.2rem; border-left: 4px solid var(--gold); padding-left: 1rem; }
    .section-title { font-size: 1.4rem; color: #fff; font-weight: 700; }

    .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 1rem; }
    .card {
      background: var(--card); border: 1px solid var(--border); border-radius: 12px;
      padding: 1rem; transition: 0.3s; display: flex; flex-direction: column;
    }
    .card:hover { border-color: var(--gold); transform: translateY(-5px); box-shadow: 0 5px 15px rgba(0,0,0,0.5); }
    .product-img { width: 100%; height: 110px; object-fit: cover; border-radius: 8px; margin-bottom: 0.6rem; background: rgba(0,0,0,0.3); border: 1px solid var(--border); }
    .card h3 { font-size: 0.95rem; margin-bottom: 0.5rem; color: #fff; line-height: 1.3; }
    .price { font-size: 1.1rem; font-weight: 700; color: var(--gold); margin-bottom: 1rem; }
    .buy-btn {
      margin-top: auto; background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      color: #000; border: none; padding: 0.5rem; border-radius: 6px; cursor: pointer;
      font-weight: 600; transition: 0.2s; text-align: center;
    }
    .buy-btn:hover { filter: brightness(1.1); transform: scale(1.02); }

    /* TOMBOL CS FLOATING */
    .cs-float-btn-wrap { position: fixed; bottom: 25px; right: 25px; z-index: 9999; text-align: center; }
    .cs-float-btn {
      width: 60px; height: 60px;
      background: linear-gradient(135deg, #128c7e, #25d366);
      color: #fff; border: none; border-radius: 50%;
      cursor: pointer; font-size: 1.1rem; font-weight: 800; letter-spacing: 1px;
      box-shadow: 0 6px 20px rgba(37,211,102,0.5);
      display: flex; align-items: center; justify-content: center;
      text-decoration: none;
      animation: pulseCS 2s infinite;
      transition: all 0.3s ease;
    }
    .cs-float-btn:hover {
      transform: translateY(-4px) scale(1.1);
      box-shadow: 0 10px 25px rgba(37,211,102,0.7);
    }
    @keyframes pulseCS {
      0% { box-shadow: 0 6px 20px rgba(37,211,102,0.5), 0 0 0 0 rgba(37,211,102,0.7); }
      50% { box-shadow: 0 6px 30px rgba(37,211,102,0.9), 0 0 0 15px rgba(37,211,102,0); }
      100% { box-shadow: 0 6px 20px rgba(37,211,102,0.5), 0 0 0 0 rgba(37,211,102,0); }
    }
    .cs-label {
      display: block; margin-top: 6px;
      background: #fff; color: #128c7e;
      padding: 3px 10px; border-radius: 12px;
      font-size: 0.7rem; font-weight: 700;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
    }

    /* POPUP PILIHAN WA / TELEGRAM / CHANNEL */
    .cs-popup-overlay {
      display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.6); z-index: 9998; backdrop-filter: blur(3px);
    }
    .cs-popup-overlay.active { display: block; animation: fadeIn 0.2s ease; }
    .cs-popup {
      position: fixed; bottom: 110px; right: 25px;
      background: var(--card); border: 1px solid var(--gold-dark);
      border-radius: 16px; padding: 16px; z-index: 9999;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
      min-width: 240px;
      animation: popUp 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    @keyframes popUp {
      from { opacity: 0; transform: translateY(20px) scale(0.9); }
      to { opacity: 1; transform: translateY(0) scale(1); }
    }
    .cs-popup-title {
      color: var(--gold); font-size: 0.95rem; font-weight: 700;
      text-align: center; margin-bottom: 12px;
    }
    .cs-popup-btn {
      display: flex; align-items: center; gap: 10px;
      width: 100%; padding: 10px 14px;
      border-radius: 10px; border: none; cursor: pointer;
      color: #fff; font-size: 0.9rem; font-weight: 600;
      margin-bottom: 8px; text-decoration: none;
      transition: transform 0.2s;
    }
    .cs-popup-btn:last-child { margin-bottom: 0; }
    .cs-popup-btn:hover { transform: scale(1.03); }
    .cs-btn-wa { background: linear-gradient(135deg, #128c7e, #25d366); }
    .cs-btn-tg { background: linear-gradient(135deg, #0088cc, #229ED9); }
    /* ✅ TOMBOL CHANNEL BARU */
    .cs-btn-channel { background: linear-gradient(135deg, #f59e0b, #fbbf24); color: #000; }
    .cs-popup-btn img { width: 22px; height: 22px; filter: brightness(0) invert(1); }
    .cs-btn-channel img { filter: brightness(0); } /* Ikon channel hitam agar kontras */
    .cs-popup-close {
      position: absolute; top: 6px; right: 10px;
      background: transparent; border: none; color: var(--text-muted);
      font-size: 1.2rem; cursor: pointer;
    }
    .cs-popup-close:hover { color: #fff; }

    /* MODAL INPUT DATA */
    .input-overlay {
      display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.85); z-index: 2000; justify-content: center; align-items: center;
      padding: 1rem; backdrop-filter: blur(5px);
    }
    .input-overlay.active { display: flex; animation: fadeIn 0.2s ease; }
    .input-modal {
      background: var(--card); border: 1px solid var(--gold-dark); border-radius: 16px;
      width: 100%; max-width: 420px; padding: 1.5rem; box-shadow: 0 0 40px rgba(255,215,0,0.2);
    }
    .input-title { color: var(--gold); font-size: 1.2rem; font-weight: 800; margin-bottom: 0.5rem; text-align: center; }
    .input-subtitle { color: var(--text-muted); font-size: 0.85rem; text-align: center; margin-bottom: 1rem; }
    .input-field {
      width: 100%; background: rgba(0,0,0,0.3); border: 1px solid var(--border);
      color: #fff; padding: 0.8rem; border-radius: 8px; font-size: 1rem; margin-bottom: 1rem;
      outline: none; text-align: center;
    }
    .input-field:focus { border-color: var(--gold); }
    .input-actions { display: flex; gap: 10px; }
    .btn-cancel {
      flex: 1; background: transparent; border: 1px solid var(--text-muted); color: var(--text-muted);
      padding: 0.7rem; border-radius: 8px; cursor: pointer; font-weight: 600;
    }
    .btn-confirm {
      flex: 1; background: linear-gradient(135deg, var(--gold-dark), var(--gold)); color: #000;
      border: none; padding: 0.7rem; border-radius: 8px; cursor: pointer; font-weight: 700;
    }

    .duration-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-top: 1rem; }
    .duration-btn {
      background: rgba(0,0,0,0.3); border: 1px solid var(--border);
      color: #fff; padding: 0.8rem 0.5rem; border-radius: 10px;
      cursor: pointer; transition: 0.2s; text-align: center;
    }
    .duration-btn:hover { border-color: var(--gold); background: rgba(255,215,0,0.1); transform: scale(1.03); }
    .duration-btn .dur-time { font-size: 1rem; font-weight: 700; color: var(--gold); display: block; }
    .duration-btn .dur-price { font-size: 0.85rem; color: var(--text-muted); margin-top: 3px; display: block; }

    /* MODAL PEMBAYARAN */
    .payment-overlay {
      display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.85); z-index: 2000; justify-content: center; align-items: center;
      padding: 1rem; backdrop-filter: blur(5px);
    }
    .payment-overlay.active { display: flex; animation: fadeIn 0.2s ease; }
    .payment-modal {
      background: var(--card); border: 1px solid var(--gold-dark); border-radius: 16px;
      width: 100%; max-width: 450px; max-height: 90vh; overflow-y: auto;
      box-shadow: 0 0 40px rgba(255,215,0,0.2); position: relative;
    }
    .payment-header {
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      padding: 1rem; text-align: center; border-radius: 16px 16px 0 0;
    }
    .payment-header h2 { color: #000; font-size: 1.2rem; margin: 0; font-weight: 800; }
    .payment-close {
      position: absolute; top: 10px; right: 15px; background: rgba(0,0,0,0.3);
      border: none; color: #000; width: 30px; height: 30px; border-radius: 50%;
      cursor: pointer; font-size: 1.2rem; transition: 0.2s;
    }
    .payment-close:hover { background: rgba(0,0,0,0.5); transform: rotate(90deg); }
    .payment-body { padding: 1.5rem; }
    
    .product-info {
      background: rgba(255,215,0,0.05); border: 1px solid rgba(255,215,0,0.2);
      padding: 1rem; border-radius: 10px; text-align: center; margin-bottom: 1.5rem;
    }
    .product-name { font-size: 1rem; color: #fff; margin-bottom: 0.3rem; }
    .product-price { font-size: 1.5rem; color: var(--gold); font-weight: 800; }
    .product-data { font-size: 0.85rem; color: var(--gold); margin-top: 5px; font-weight: 600; display: none; }

    .payment-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; margin-bottom: 1.5rem; }
    .payment-option {
      background: rgba(21,23,28,0.8); border: 1px solid var(--border); border-radius: 12px;
      padding: 1rem; text-align: center; cursor: pointer; transition: 0.3s;
    }
    .payment-option:hover { border-color: var(--gold); transform: translateY(-3px); box-shadow: 0 5px 15px rgba(255,215,0,0.2); }
    .payment-option-icon {
      width: 50px; height: 50px; background: #fff; border-radius: 10px;
      display: flex; align-items: center; justify-content: center; margin: 0 auto 0.5rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
    }
    .payment-option-icon img { width: 35px; height: 35px; object-fit: contain; }
    .payment-option-name { font-size: 0.9rem; font-weight: 700; color: #fff; margin-bottom: 0.2rem; }
    .payment-option-number { font-size: 0.75rem; color: var(--text-muted); }

    .qris-display { display: none; text-align: center; padding: 1rem; background: rgba(21,23,28,0.8); border-radius: 12px; margin-bottom: 1rem; }
    .qris-display.active { display: block; animation: fadeIn 0.3s ease; }
    .qris-display img { max-width: 200px; width: 100%; border-radius: 10px; border: 2px solid var(--gold); margin: 0.5rem 0; }
    
    .ewallet-detail { display: none; text-align: center; padding: 1rem; background: rgba(21,23,28,0.8); border-radius: 12px; margin-bottom: 1rem; }
    .ewallet-detail.active { display: block; animation: fadeIn 0.3s ease; }
    .ewallet-detail .number { font-size: 1.8rem; font-weight: 800; margin: 0.5rem 0; letter-spacing: 1px; }
    
    .copy-btn {
      background: linear-gradient(135deg, var(--gold-dark), var(--gold)); color: #000;
      border: none; padding: 0.7rem 1.5rem; border-radius: 8px; font-weight: 700;
      cursor: pointer; width: 100%; margin-top: 0.5rem; transition: 0.2s;
    }
    .copy-btn:hover { filter: brightness(1.1); transform: scale(0.98); }
    .back-btn {
      background: transparent; border: 1px solid var(--border); color: var(--text-muted);
      padding: 0.6rem 1rem; border-radius: 8px; cursor: pointer; width: 100%;
      margin-top: 0.5rem; transition: 0.2s; font-size: 0.85rem;
    }
    .back-btn:hover { border-color: var(--gold); color: var(--text); }
    
    .wa-confirm-btn {
      display: flex; align-items: center; justify-content: center; gap: 8px;
      color: #fff; border: none; padding: 0.8rem; border-radius: 10px; font-weight: 700;
      cursor: pointer; width: 100%; margin-top: 1rem; font-size: 0.95rem;
      transition: 0.2s; text-decoration: none;
    }
    .wa-confirm-btn:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(0,0,0,0.3); }
    .wa-confirm-btn img { width: 22px; height: 22px; filter: brightness(0) invert(1); }

    footer { text-align: center; padding: 2rem; color: var(--text-muted); border-top: 1px solid var(--border); margin-top: 2rem; }

    @media (max-width: 768px) {
      .hero h1 { font-size: 1.8rem; }
      .grid { grid-template-columns: repeat(2, 1fr); }
      .payment-grid { grid-template-columns: 1fr; }
      .cs-float-btn-wrap { bottom: 20px; right: 20px; }
      .cs-float-btn { width: 55px; height: 55px; font-size: 1rem; }
      .cs-popup { bottom: 90px; right: 20px; min-width: 220px; }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo-container">
      <img src="https://cdn.phototourl.com/free/2026-06-03-527a85f3-1011-4350-b468-2d83126e5be1.png" alt="Franzz Shop Logo" class="logo-img">
      <div class="logo-text">FRANZZ SHOP ID</div>
    </div>
    <button class="contact-btn" onclick="openWA('Info', 'Menu')">💬 Hubungi WA</button>
  </header>

  <section class="hero">
    <h1>🛒 Toko Digital Terpercaya</h1>
    <p>Top Up • Akun • Tools • Reseller • Support 24 Jam</p>
  </section>

  <nav class="main-nav">
    <button class="main-btn active" data-category="topup">🎮 Top Up</button>
    <button class="main-btn" data-category="akun">👤 Akun</button>
    <button class="main-btn" data-category="key">🔑 Key Client</button>
    <button class="main-btn" data-category="tools">🛠️ Tools FF</button>
    <button class="main-btn" data-category="apk">📱 APK Bug</button>
    <button class="main-btn" data-category="rental">👤 Rental Akun</button>
    <button class="main-btn" data-category="lain">📦 Lainnya</button>
  </nav>

  <nav class="sub-nav" id="subNav"></nav>

  <div class="container">
    <div id="contentArea"></div>
  </div>

  <!-- POPUP PILIHAN WA / TELEGRAM / CHANNEL -->
  <div class="cs-popup-overlay" id="csPopupOverlay" onclick="closeCSPopup()"></div>
  <div class="cs-popup" id="csPopup" style="display:none;">
    <button class="cs-popup-close" onclick="closeCSPopup()">×</button>
    <div class="cs-popup-title">💬 Hubungi Customer Service</div>
    <a href="https://wa.me/6285134598480?text=Halo%20Admin%20Franzz%20Shop,%20saya%20butuh%20bantuan." 
       target="_blank" class="cs-popup-btn cs-btn-wa">
      <img src="https://cdn.phototourl.com/free/2026-06-03-291d35d6-ebbd-4d9e-8f5c-1ac6bde619c0.jpg" alt="WA">
      WhatsApp
    </a>
    <a href="https://t.me/Customerservicesfranzz" 
       target="_blank" class="cs-popup-btn cs-btn-tg">
      <img src="https://cdn.phototourl.com/free/2026-06-03-be1a7986-aea1-4fdd-9cc9-317b213bdb66.png" alt="TG">
      Telegram
    </a>
    <!-- ✅ TOMBOL SALURAN WA BARU -->
    <a href="https://whatsapp.com/channel/0029VbCNqba2P59gttAYbv1Q" 
       target="_blank" class="cs-popup-btn cs-btn-channel">
      <img src="https://cdn.phototourl.com/free/2026-06-03-291d35d6-ebbd-4d9e-8f5c-1ac6bde619c0.jpg" alt="Channel">
      Saluran WA
    </a>
  </div>

  <!-- MODAL PILIHAN DURASI RENTAL -->
  <div class="input-overlay" id="durationOverlay">
    <div class="input-modal">
      <h3 class="input-title" id="durationTitle">Pilih Durasi Rental</h3>
      <p class="input-subtitle">Pilih berapa lama Anda ingin menyewa akun ini.</p>
      <div class="duration-grid" id="durationGrid"></div>
      <button class="btn-cancel" style="width:100%; margin-top:1rem;" onclick="closeDurationModal()">Batal</button>
    </div>
  </div>

  <!-- MODAL INPUT DATA -->
  <div class="input-overlay" id="inputOverlay">
    <div class="input-modal">
      <h3 class="input-title" id="inputModalTitle">Masukkan Data</h3>
      <p class="input-subtitle" id="inputModalSubtitle">Data ini akan dikirim ke admin untuk diproses.</p>
      <input type="text" id="dataInput" class="input-field" placeholder="Masukkan...">
      <div class="input-actions">
        <button class="btn-cancel" onclick="closeInputModal()">Batal</button>
        <button class="btn-confirm" onclick="submitData()">Lanjut Bayar</button>
      </div>
    </div>
  </div>

  <!-- MODAL PEMBAYARAN -->
  <div class="payment-overlay" id="paymentOverlay">
    <div class="payment-modal">
      <div class="payment-header">
        <h2>💳 Pilih Pembayaran</h2>
        <button class="payment-close" onclick="closePayment()">×</button>
      </div>
      <div class="payment-body">
        <div class="product-info">
          <div class="product-name" id="payProductName">-</div>
          <div class="product-price" id="payProductPrice">-</div>
          <div class="product-data" id="payDataDisplay"></div>
        </div>

        <div id="paymentOptions">
          <div class="payment-grid">
            <div class="payment-option" onclick="showQRIS()">
              <div class="payment-option-icon"><img src="https://cdn.phototourl.com/free/2026-06-03-f8204b5b-a56a-46b5-8e17-aebb24a61364.png" alt="QRIS"></div>
              <div class="payment-option-name">QRIS</div>
              <div class="payment-option-number">Scan QR Code</div>
            </div>
            <div class="payment-option" onclick="showDana()">
              <div class="payment-option-icon"><img src="https://cdn.phototourl.com/free/2026-06-03-ac7fcbb0-f1a3-4c9d-9fce-205cea80fa23.png" alt="Dana"></div>
              <div class="payment-option-name">Dana</div>
              <div class="payment-option-number">083128534802</div>
            </div>
            <div class="payment-option" onclick="showGoPay()">
              <div class="payment-option-icon"><img src="https://cdn.phototourl.com/free/2026-06-03-807c33b1-6958-495a-9d39-c453b8e71b94.png" alt="GoPay"></div>
              <div class="payment-option-name">GoPay</div>
              <div class="payment-option-number">083128534802</div>
            </div>
            <div class="payment-option" onclick="showShopeePay()">
              <div class="payment-option-icon"><img src="https://cdn.phototourl.com/free/2026-06-03-c8b10948-da2d-4327-abae-8fd8d464673e.png" alt="ShopeePay"></div>
              <div class="payment-option-name">ShopeePay</div>
              <div class="payment-option-number">083128534802</div>
            </div>
            <div class="payment-option" onclick="showOVO()" style="grid-column: span 2;">
              <div class="payment-option-icon"><img src="https://cdn.phototourl.com/free/2026-06-03-72abc78a-24af-47c1-a81f-29edca733016.png" alt="OVO"></div>
              <div class="payment-option-name">OVO</div>
              <div class="payment-option-number">083128534802</div>
            </div>
          </div>
        </div>

        <div class="qris-display" id="qrisDisplay">
          <h3 style="color:var(--gold); margin-bottom:10px;">📱 QRIS Payment</h3>
          <img src="https://cdn.phototourl.com/free/2026-06-03-d47ae092-eb92-4f86-ada1-859bbf9a7697.jpg" alt="QRIS Code">
          <p style="font-size:0.8rem; color:var(--text-muted); margin-top:10px;">Scan QR di atas dengan aplikasi e-wallet favorit Anda</p>
          <button class="back-btn" onclick="backToOptions()">⬅ Kembali</button>
        </div>

        <div class="ewallet-detail" id="danaDisplay">
          <h3 style="color:#0068ff; margin-bottom:10px;">💙 Dana</h3>
          <div class="number" style="color:#0068ff;">083128534802</div>
          <p style="font-size:0.8rem; color:var(--text-muted);">a.n. FRANZZ STORE</p>
          <button class="copy-btn" onclick="copyNumber('083128534802')">📋 Salin Nomor</button>
          <button class="back-btn" onclick="backToOptions()">⬅ Kembali</button>
        </div>

        <div class="ewallet-detail" id="gopayDisplay">
          <h3 style="color:#00aed6; margin-bottom:10px;">💚 GoPay</h3>
          <div class="number" style="color:#00aed6;">083128534802</div>
          <p style="font-size:0.8rem; color:var(--text-muted);">a.n. FRANZZ STORE</p>
          <button class="copy-btn" onclick="copyNumber('083128534802')">📋 Salin Nomor</button>
          <button class="back-btn" onclick="backToOptions()">⬅ Kembali</button>
        </div>

        <div class="ewallet-detail" id="shopeeDisplay">
          <h3 style="color:#ee4d2d; margin-bottom:10px;">🧡 ShopeePay</h3>
          <div class="number" style="color:#ee4d2d;">083128534802</div>
          <p style="font-size:0.8rem; color:var(--text-muted);">a.n. FRANZZ STORE</p>
          <button class="copy-btn" onclick="copyNumber('083128534802')">📋 Salin Nomor</button>
          <button class="back-btn" onclick="backToOptions()">⬅ Kembali</button>
        </div>

        <div class="ewallet-detail" id="ovoDisplay">
          <h3 style="color:#4C3494; margin-bottom:10px;">💜 OVO</h3>
          <div class="number" style="color:#4C3494;">083128534802</div>
          <p style="font-size:0.8rem; color:var(--text-muted);">a.n. FRANZZ STORE</p>
          <button class="copy-btn" onclick="copyNumber('083128534802')">📋 Salin Nomor</button>
          <button class="back-btn" onclick="backToOptions()">⬅ Kembali</button>
        </div>

        <div style="background:rgba(255,215,0,0.05); border-left:3px solid var(--gold); padding:0.8rem; border-radius:6px; font-size:0.8rem; color:var(--text-muted); margin-top:1rem;">
          <strong>⚠️ Penting:</strong> Setelah transfer, kirim bukti pembayaran ke WhatsApp atau Telegram admin.
        </div>

        <div style="display:flex; flex-direction:column; gap:0.8rem; margin-top:1rem;">
          <a href="#" target="_blank" class="wa-confirm-btn" id="waConfirmBtn" style="background:linear-gradient(135deg, #128c7e, #25d366);">
            <img src="https://cdn.phototourl.com/free/2026-06-03-291d35d6-ebbd-4d9e-8f5c-1ac6bde619c0.jpg" alt="WA">
            Kirim Bukti TF via WhatsApp
          </a>
          <a href="#" target="_blank" class="wa-confirm-btn" id="tgConfirmBtn" style="background:linear-gradient(135deg, #0077b5, #0088cc);">
            <img src="https://cdn.phototourl.com/free/2026-06-03-be1a7986-aea1-4fdd-9cc9-317b213bdb66.png" alt="TG">
            Kirim Bukti TF via Telegram
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- TOMBOL CS (HANYA TULISAN "CS") -->
  <div class="cs-float-btn-wrap">
    <button class="cs-float-btn" onclick="showCSPopup()" aria-label="Customer Service">CS</button>
    <span class="cs-label">CS 24 Jam</span>
  </div>

  <footer>
    <p>&copy; 2026 FRANZZ SHOP ID. All Rights Reserved.</p>
    <p style="font-size:0.8rem; color:#666;">Harga dapat berubah sewaktu-waktu.</p>
  </footer>
  <script>
    const WA_NUMBER = "6283874575892";
    const CS_NUMBER = "6285134598480";
    let tempProductData = {}; 

    const rentalDurations = [
      { label: "1 Jam", price: "Rp5.000" },
      { label: "2 Jam", price: "Rp10.000" },
      { label: "3 Jam", price: "Rp15.000" },
      { label: "5 Jam", price: "Rp25.000" },
      { label: "10 Jam", price: "Rp50.000" },
      { label: "24 Jam", price: "Rp100.000" }
    ];

    const catalog = {
      "topup-ff": [{ name: "1 DM", price: "Rp135" }, { name: "5 DM", price: "Rp800" }, { name: "12 DM", price: "Rp1.800" }, { name: "50 DM", price: "Rp6.500" }, { name: "70 DM", price: "Rp8.600" }, { name: "100 DM", price: "Rp13.500" }, { name: "140 DM", price: "Rp17.300" }, { name: "210 DM", price: "Rp26.000" }, { name: "355 DM", price: "Rp43.000" }, { name: "500 DM", price: "Rp61.500" }, { name: "720 DM", price: "Rp86.700" }, { name: "1000 DM", price: "Rp121.000" }, { name: "1450 DM", price: "Rp175.000" }, { name: "2180 DM", price: "Rp263.000" }],
      "topup-ml": [{ name: "12 DM", price: "Rp3.500" }, { name: "28 DM", price: "Rp8.000" }, { name: "36 DM", price: "Rp10.000" }, { name: "56 DM", price: "Rp15.000" }, { name: "86 DM", price: "Rp22.000" }, { name: "172 DM", price: "Rp44.000" }, { name: "257 DM", price: "Rp65.000" }, { name: "344 DM", price: "Rp88.000" }, { name: "514 DM", price: "Rp130.000" }, { name: "706 DM", price: "Rp175.000" }, { name: "878 DM", price: "Rp220.000" }, { name: "963 DM", price: "Rp240.000" }, { name: "1050 DM", price: "Rp260.000" }],
      "topup-hok": [{ name: "80 Token", price: "Rp15.000" }, { name: "240 Token", price: "Rp45.000" }, { name: "400 Token", price: "Rp75.000" }, { name: "800 Token", price: "Rp145.000" }],
      "topup-pubg": [{ name: "60 UC", price: "Rp15.000" }, { name: "120 UC", price: "Rp31.000" }, { name: "325 UC", price: "Rp78.000" }, { name: "660 UC", price: "Rp156.000" }, { name: "1500 UC", price: "Rp394.000" }],
      "topup-bs": [{ name: "100 + 5", price: "Rp12.000" }, { name: "300 + 20", price: "Rp36.000" }, { name: "500 + 40", price: "Rp60.000" }, { name: "1000 + 100", price: "Rp120.000" }, { name: "2000 + 260", price: "Rp240.000" }],
      "topup-roblox": [{ name: "100 Robux", price: "Rp10.600" }, { name: "400 Robux", price: "Rp47.500" }, { name: "500 Robux", price: "Rp55.000" }, { name: "800 Robux", price: "Rp95.000" }, { name: "1000 Robux", price: "Rp110.000" }, { name: "1700 Robux", price: "Rp190.000" }, { name: "2000 Robux", price: "Rp240.000" }, { name: "2500 Robux", price: "Rp270.000" }],
      
      "akun-ff": [{ name: "Akun Free Fire", price: "Rp15.000" }, { name: "Akun Free Fire", price: "Rp25.000" }, { name: "Akun Free Fire", price: "Rp50.000" }, { name: "Akun Free Fire", price: "Rp100.000" }, { name: "Akun Free Fire", price: "Rp150.000" }, { name: "Akun Free Fire", price: "Rp200.000" }, { name: "Akun Free Fire", price: "Rp250.000" }, { name: "Akun Free Fire", price: "Rp300.000" }],
      "akun-ml": [{ name: "Akun Mobile Legends", price: "Rp35.000" }, { name: "Akun Mobile Legends", price: "Rp55.000" }, { name: "Akun Mobile Legends", price: "Rp95.000" }, { name: "Akun Mobile Legends", price: "Rp100.000" }, { name: "Akun Mobile Legends", price: "Rp150.000" }],
      "akun-roblox": [{ name: "Akun Roblox", price: "Rp15.000" }, { name: "Akun Roblox", price: "Rp25.000" }, { name: "Akun Roblox", price: "Rp35.000" }, { name: "Akun Roblox", price: "Rp55.000" }],
      
      "key-franzz-modzz": [{ name: "FRANZZ X MODZZ (1 Hari)", price: "Rp10.000" }, { name: "FRANZZ X MODZZ (3 Hari)", price: "Rp25.000" }, { name: "FRANZZ X MODZZ (7 Hari)", price: "Rp50.000" }, { name: "FRANZZ X MODZZ (Permanen)", price: "Rp100.000" }],
      "key-drip": [{ name: "Key Drip Client (1 Hari)", price: "Rp15.000" }, { name: "Key Drip Client (3 Hari)", price: "Rp35.000" }, { name: "Key Drip Client (7 Hari)", price: "Rp65.000" }, { name: "Key Drip Client (30 Hari)", price: "Rp150.000" }],
      "key-pato": [{ name: "Key Pato Team (3 Hari)", price: "Rp50.000" }, { name: "Key Pato Team (7 Hari)", price: "Rp125.000" }, { name: "Key Pato Team (15 Hari)", price: "Rp200.000" }, { name: "Key Pato Team (30 Hari)", price: "Rp300.000" }],
      "key-br": [{ name: "Key BR MODS (1 Hari)", price: "Rp15.000" }, { name: "Key BR MODS (7 Hari)", price: "Rp50.000" }, { name: "Key BR MODS (15 Hari)", price: "Rp80.000" }, { name: "Key BR MODS (30 Hari)", price: "Rp150.000" }],
      "hg-cheat": [{ name: "HG Cheat (1 Hari)", price: "Rp25.000" }, { name: "HG Cheat (7 Hari)", price: "Rp50.000" }, { name: "HG Cheat (10 Hari)", price: "Rp65.000" }, { name: "HG Cheat (30 Hari)", price: "Rp141.000" }],
      "prime-hook": [{ name: "Prime Hook (1 Hari)", price: "Rp10.000" }, { name: "Prime Hook (3 Hari)", price: "Rp25.000" }, { name: "Prime Hook (7 Hari)", price: "Rp50.000" }],
      
      "tools-drag": [{ name: "Easy Drag SMG/SG", price: "Rp5.000" }, { name: "Infinity Drag V2", price: "Rp5.000" }, { name: "Easy Drag 2.3 VVIP", price: "Rp10.000" }, { name: "Easy Drag 2.5 VVIP", price: "Rp15.000" }, { name: "Easy Drag 2.10 VVIP", price: "Rp25.000" }, { name: "Easy Drag 95%", price: "Rp45.000" }, { name: "Drag HS No Recoil SG V3", price: "Rp15.000" }, { name: "Drag HS No Recoil SG V4", price: "Rp25.000" }],
      "tools-aim": [{ name: "Aimlock Best Seller", price: "Rp5.000" }, { name: "Aimlock Gen 1", price: "Rp10.000" }, { name: "Aimlock Data V1", price: "Rp10.000" }, { name: "Aimlock Head V2", price: "Rp20.000" }, { name: "Aimlock X Rege Gen 2", price: "Rp25.000" }, { name: "Aimlock Head V3", price: "Rp30.000" }, { name: "Aimlock X Rege Gen 4", price: "Rp45.000" }, { name: "Aimlock Infernus Gen 5", price: "Rp55.000" }],
      "tools-stab": [{ name: "Stabili Smoot Prem v1", price: "Rp5.000" }, { name: "Stabili Smoot Prem v2", price: "Rp10.000" }, { name: "Stabili Smoot Prem v3", price: "Rp15.000" }, { name: "Stabilizer Super V1", price: "Rp5.000" }, { name: "Aimlock X Stabilizer", price: "Rp15.000" }, { name: "Stabilizer Head", price: "Rp25.000" }, { name: "Stabilizer King", price: "Rp35.000" }, { name: "Stabilizer 80% Holo", price: "Rp45.000" }, { name: "Stabilizer Data VVIP", price: "Rp55.000" }, { name: "Stabilizer Aimbot All tab", price: "Rp65.000" }, { name: "Stabilizer super lock Setting", price: "Rp75.000" }, { name: "Stabilizer x ff hack", price: "Rp85.000" }],
      "tools-aimbot": [{ name: "AimBot best seller", price: "Rp5.000" }, { name: "One tab god v1", price: "Rp5.000" }, { name: "Aimbot Legit", price: "Rp5.000" }, { name: "Aimbot Legit 2.2", price: "Rp10.000" }, { name: "Aimbot Legit 3.3", price: "Rp15.000" }, { name: "Aimbot Legit 4.4", price: "Rp20.000" }, { name: "Glowal mini + Legit", price: "Rp15.000" }, { name: "Glowal gepeng v3 + holo", price: "Rp25.000" }, { name: "Aimbot Config HS", price: "Rp15.000" }, { name: "Aimbot Super", price: "Rp5.000" }, { name: "Aimbot X Aimlock Super", price: "Rp15.000" }, { name: "Aimbot Drag Head 70%", price: "Rp25.000" }, { name: "OBB Aimbot 60%", price: "Rp5.000" }, { name: "OBB Aimbot 70%", price: "Rp10.000" }],
      
      "apk-trapenden": [{ name: "Trapenden Member 1 Bulan", price: "Rp15.000" }, { name: "Trapenden Perma", price: "Rp25.000" }, { name: "Trapenden Reseller 1 Bulan", price: "Rp35.000" }, { name: "Trapenden Res Perma", price: "Rp45.000" }, { name: "Trapenden Owner", price: "Rp70.000" }, { name: "Trapenden High", price: "Rp100.000" }, { name: "Trapenden Mod", price: "Rp150.000" }],
      "apk-manta": [{ name: "Manta 1 Hari", price: "Rp5.000" }, { name: "Manta 30 Hari", price: "Rp40.000" }, { name: "Manta Permanent", price: "Rp60.000" }, { name: "Manta Reseller", price: "Rp80.000" }, { name: "Manta Partner", price: "Rp100.000" }],
      "apk-otax": [{ name: "OTAX 1 Hari", price: "Rp5.000" }, { name: "OTAX 30 Hari", price: "Rp40.000" }, { name: "OTAX Permanent", price: "Rp60.000" }, { name: "OTAX Reseller", price: "Rp80.000" }, { name: "OTAX Partner", price: "Rp100.000" }],
      "apk-ppl": [{ name: "PPL Member 1 Bulan", price: "Rp35.000" }, { name: "PPL Permainan", price: "Rp50.000" }, { name: "PPL VIP 1 Bulan", price: "Rp50.000" }, { name: "PPL VIP Permanent", price: "Rp80.000" }, { name: "PPL Reseller 1 Bulan", price: "Rp100.000" }, { name: "PPL Reseller Permanent", price: "Rp200.000" }],
      "apk-franzv6": [{ name: "Franzz V6 Harian", price: "Rp3.000" }, { name: "Franzz V6 Member 1 Bulan", price: "Rp15.000" }, { name: "Franzz V6 Permanent", price: "Rp25.000" }, { name: "Franzz V6 Reseller 1 Bulan", price: "Rp25.000" }, { name: "Franzz V6 Reseller Permanent", price: "Rp35.000" }, { name: "Franzz V6 VIP 1 Bulan", price: "Rp35.000" }, { name: "Franzz V6 VIP Permanent", price: "Rp50.000" }, { name: "Franzz V6 Owner", price: "Rp60.000" }],
      "apk-darkverse": [{ name: "Darkverse Full Update (Permanen)", price: "Rp100.000" }],
      "apk-nexus": [{ name: "Nexus 1 Hari", price: "Rp5.000" }, { name: "Nexus 7 Hari", price: "Rp30.000" }, { name: "Nexus Full Update", price: "Rp50.000" }, { name: "Nexus Reseller", price: "Rp70.000" }],
      "apk-kentod": [{ name: "Kentod 30 Hari", price: "Rp15.000" }, { name: "Kentod Full Update", price: "Rp35.000" }, { name: "Kentod Reseller 1 Bulan", price: "Rp45.000" }, { name: "Kentod Reseller", price: "Rp55.000" }],
      "apk-darkness": [{ name: "Darkness 30 Hari", price: "Rp20.000" }, { name: "Darkness Full Update", price: "Rp35.000" }, { name: "Darkness Reseller 1 Bulan", price: "Rp35.000" }, { name: "Darkness Reseller Permanent", price: "Rp55.000" }, { name: "Darkness VIP", price: "Rp65.000" }, { name: "Darkness Admin", price: "Rp80.000" }],
      "apk-xfar": [{ name: "X•Far Full Update", price: "Rp15.000" }, { name: "X•Far VIP 30 Hari", price: "Rp30.000" }, { name: "X•Far VIP Permanent", price: "Rp50.000" }, { name: "X•Far Reseller 1 Bulan", price: "Rp60.000" }, { name: "X•Far Reseller Permanent", price: "Rp80.000" }],
      "apk-ovalium": [{ name: "Ovalium Ghost Full Update", price: "Rp35.000" }, { name: "Ovalium Ghost Reseller", price: "Rp50.000" }],
      "apk-n1ghtx": [{ name: "N1ghtx 30 Hari", price: "Rp15.000" }, { name: "N1ghtx Full Update", price: "Rp35.000" }],
      "apk-sunci": [{ name: "Sunci Crasher Harian", price: "Rp5.000" }, { name: "Sunci Crasher Full Update", price: "Rp10.000" }, { name: "Sunci Crasher Reseller", price: "Rp15.000" }, { name: "Sunci Crasher Partner", price: "Rp20.000" }, { name: "Sunci Crasher Tangan Kanan", price: "Rp35.000" }, { name: "Sunci Crasher CEO", price: "Rp40.000" }, { name: "Sunci Crasher MODZ", price: "Rp45.000" }, { name: "Sunci Crasher Owner", price: "Rp50.000" }],
      
      "rental-ff": [
        { name: "Akun FF Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-7b629a59-4642-4371-8c1a-4a9e51fd8e9e.jpg", durations: rentalDurations },
        { name: "Akun FF Spek Gacor", image: "https://cdn.phototourl.com/free/2026-06-03-92df8cb9-554f-4b84-9bed-4a148cf8430d.jpg", durations: rentalDurations },
        { name: "Akun FF Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-39629ef8-63af-4bc4-99d4-096f444827ec.jpg", durations: rentalDurations },
        { name: "Akun FF Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-f5e4369a-324b-4dab-aee3-376cf5c28999.jpg", durations: rentalDurations },
        { name: "Akun FF Sultan ", image: "https://cdn.phototourl.com/free/2026-06-03-3f3dee95-08c8-4031-b7b0-a4f9a5bd728c.jpg", durations: rentalDurations }
      ],
      "rental-ml": [
        { name: "Akun ML Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-27d617b4-cd5d-440c-859f-900d73d7b20a.jpg", durations: rentalDurations },
        { name: "Akun ML Mythic Glory", image: "https://cdn.phototourl.com/free/2026-06-03-664b3582-e2cc-4315-9aaf-9ca62c1f9abc.jpg", durations: rentalDurations },
        { name: "Akun ML Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-00538d88-7cee-4de4-aec3-1e8571eab3da.jpg", durations: rentalDurations },
        { name: "Akun ML Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-40c9d941-d71f-45f8-bed7-e9f71ed3cbe5.jpg", durations: rentalDurations },
        { name: "Akun ML Sultan", image: "https://cdn.phototourl.com/free/2026-06-03-0543bb80-3f67-4a11-adef-0ab8a901be37.jpg", durations: rentalDurations }
      ],
      
      "lain-jpm": [{ name: "JPM 10 Member", price: "Rp10.000" }, { name: "JPM 20 Member", price: "Rp20.000" }, { name: "JPM 30 Member", price: "Rp30.000" }, { name: "JPM 40 Member", price: "Rp40.000" }, { name: "JPM 50 Member", price: "Rp50.000" }, { name: "JPM 60 Member", price: "Rp60.000" }, { name: "JPM 70 Member", price: "Rp70.000" }, { name: "JPM 80 Member", price: "Rp80.000" }, { name: "JPM 90 Member", price: "Rp90.000" }, { name: "JPM 100 Member", price: "Rp100.000" }],
      "lain-suntik": [{ name: "SL WA 100 Anggota", price: "Rp5.000" }, { name: "TikTok 100 Followers", price: "Rp4.000" }, { name: "Like 1.000", price: "Rp2.000" }, { name: "IG 100 Followers", price: "Rp5.000" }],
      "lain-bandunband": [{ name: "Band WhatsApp", price: "Rp10.000" }, { name: "Band Permanen", price: "Rp20.000" }, { name: "Unband WhatsApp", price: "Rp10.000" }],
      "lain-bug": [{ name: "Jasa Bug", price: "Rp2.000" }]
    };

    const categories = {
      "topup": { name: "🎮 Top Up Game", subCategories: { "topup-ff": "🔥 Free Fire", "topup-ml": "💎 Mobile Legends", "topup-hok": "👑 Honor of Kings", "topup-pubg": "🎯 PUBG Mobile", "topup-bs": "🔫 Blood Strike", "topup-roblox": "🟥 Roblox" } },
      "akun": { name: "👤 Akun Game", subCategories: { "akun-ff": "🔥 Akun FF", "akun-ml": "💎 Akun ML", "akun-roblox": "🟥 Akun Roblox" } },
      "key": { name: "🔑 Key Client", subCategories: { "key-franzz-modzz": "Franzz X Modzz", "key-drip": "Key Drip", "key-pato": "Key Pato Team", "key-br": "Key BR MODS", "hg-cheat": "HG Cheat", "prime-hook": "Prime Hook" } },
      "tools": { name: "🛠️ Tools FF", subCategories: { "tools-drag": "Easy Drag", "tools-aim": "Aimlock", "tools-stab": "Stabilizer", "tools-aimbot": "Aimbot" } },
      "apk": { name: "📱 APK Bug", subCategories: { "apk-trapenden": "Trapenden", "apk-manta": "Manta", "apk-otax": "OTAX", "apk-ppl": "PPL Project", "apk-franzv6": "Franz V6", "apk-darkverse": "Darkverse", "apk-nexus": "Nexus", "apk-kentod": "Kentod Crash", "apk-darkness": "Darkness", "apk-xfar": "X•Far", "apk-ovalium": "Ovalium Ghost", "apk-n1ghtx": "N1ghtx", "apk-sunci": "Sunci Crasher" } },
      "rental": { name: "👤 Rental Akun", subCategories: { "rental-ff": "🔥 Rental Akun Free Fire", "rental-ml": "💎 Rental Akun Mobile Legends" } },
      "lain": { name: "📦 Lainnya", subCategories: { "lain-jpm": "JPM", "lain-suntik": "Suntik Sosmed", "lain-bandunband": "Band/Unband", "lain-bug": "Jasa Bug" } }
    };
let currentCategory = 'topup';

    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('.main-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          document.querySelectorAll('.main-btn').forEach(b => b.classList.remove('active'));
          btn.classList.add('active');
          currentCategory = btn.dataset.category;
          showSubCategories(currentCategory);
        });
      });
      showSubCategories('topup');
    });

    function showSubCategories(category) {
      const subNav = document.getElementById('subNav');
      const contentArea = document.getElementById('contentArea');
      const catData = categories[category];
      
      subNav.innerHTML = '';
      contentArea.innerHTML = '';
      
      Object.keys(catData.subCategories).forEach(subKey => {
        const btn = document.createElement('button');
        btn.className = 'sub-btn';
        btn.textContent = catData.subCategories[subKey];
        btn.onclick = () => {
          document.querySelectorAll('.sub-btn').forEach(b => b.classList.remove('active'));
          btn.classList.add('active');
          showProducts(subKey);
        };
        subNav.appendChild(btn);
      });
      
      subNav.classList.add('active');
      if (subNav.firstChild) {
        subNav.firstChild.classList.add('active');
        showProducts(Object.keys(catData.subCategories)[0]);
      }
    }

    function showProducts(subKey) {
      const contentArea = document.getElementById('contentArea');
      const products = catalog[subKey];
      const catData = categories[currentCategory];
      const subName = catData.subCategories[subKey];
      
      let html = `<div class="section active"><div class="section-header"><h2 class="section-title">${subName}</h2></div><div class="grid" id="grid-${subKey}"></div></div>`;
      contentArea.innerHTML = html;
      
      const grid = document.getElementById(`grid-${subKey}`);
      products.forEach(item => {
        const card = document.createElement('div');
        card.className = 'card';
        const imgHtml = item.image ? `<img src="${item.image}" class="product-img" loading="lazy" alt="${item.name}">` : '';
        const priceLabel = item.durations ? "Mulai Rp5.000" : item.price;
        card.innerHTML = `${imgHtml}<h3>${item.name}</h3><div class="price">${priceLabel}</div>
          <button class="buy-btn" onclick="handleBuyClick('${item.name}', '${subKey}')">🛒 Beli Sekarang</button>`;
        grid.appendChild(card);
      });
    }

    function handleBuyClick(name, subKey) {
      const product = catalog[subKey].find(p => p.name === name);
      
      if (product && product.durations) {
        showDurationModal(name, product.durations);
      } else {
        tempProductData = { name, price: product.price, subKey };
        const titleEl = document.getElementById('inputModalTitle');
        const subEl = document.getElementById('inputModalSubtitle');
        const inputEl = document.getElementById('dataInput');
        
        let needsInput = false;

        if (subKey.startsWith('topup-')) {
          needsInput = true;
          titleEl.textContent = subKey === 'topup-roblox' ? 'Masukkan Username Roblox' : 'Masukkan ID Game';
          subEl.textContent = 'Pastikan ID/Username sudah benar.';
          inputEl.placeholder = subKey === 'topup-roblox' ? 'cth: PlayerFranzz' : 'cth: 123456789';
        } 
        else if (subKey === 'lain-jpm' || subKey === 'lain-bandunband' || subKey === 'lain-bug') {
          needsInput = true;
          titleEl.textContent = 'Masukkan Nomor WhatsApp';
          subEl.textContent = 'Nomor WA target yang akan diproses.';
          inputEl.placeholder = 'cth: 081234567890';
        } 
        else if (subKey === 'lain-suntik') {
          needsInput = true;
          titleEl.textContent = 'Masukkan URL Profil/Grup';
          subEl.textContent = 'Link target untuk suntik followers/like.';
          inputEl.placeholder = 'cth: https://tiktok.com/@user';
        }

        if (needsInput) {
          inputEl.value = '';
          document.getElementById('inputOverlay').classList.add('active');
          inputEl.focus();
        } else {
          openPayment(name, product.price, null);
        }
      }
    }

    function showDurationModal(productName, durations) {
      document.getElementById('durationTitle').textContent = `Pilih Durasi - ${productName}`;
      const grid = document.getElementById('durationGrid');
      grid.innerHTML = '';
      
      durations.forEach(dur => {
        const btn = document.createElement('button');
        btn.className = 'duration-btn';
        btn.innerHTML = `<span class="dur-time">⏱️ ${dur.label}</span><span class="dur-price">${dur.price}</span>`;
        btn.onclick = () => {
          closeDurationModal();
          tempProductData = { 
            name: `${productName} (${dur.label})`, 
            price: dur.price 
          };
          openPayment(tempProductData.name, tempProductData.price, null);
        };
        grid.appendChild(btn);
      });
      
      document.getElementById('durationOverlay').classList.add('active');
    }

    function showCSPopup() {
      document.getElementById('csPopup').style.display = 'block';
      document.getElementById('csPopupOverlay').classList.add('active');
    }
    function closeCSPopup() {
      document.getElementById('csPopup').style.display = 'none';
      document.getElementById('csPopupOverlay').classList.remove('active');
    }

    function closeDurationModal() { document.getElementById('durationOverlay').classList.remove('active'); }
    function closeInputModal() { document.getElementById('inputOverlay').classList.remove('active'); }
    function submitData() {
      const val = document.getElementById('dataInput').value.trim();
      if (!val) { alert('⚠️ Mohon isi data terlebih dahulu!'); return; }
      closeInputModal();
      openPayment(tempProductData.name, tempProductData.price, val);
    }

    function openPayment(name, price, dataValue) {
      document.getElementById('payProductName').textContent = name;
      document.getElementById('payProductPrice').textContent = price;
      const dataDisplay = document.getElementById('payDataDisplay');
      if (dataValue) { dataDisplay.textContent = `📝 Data: ${dataValue}`; dataDisplay.style.display = 'block'; } 
      else { dataDisplay.style.display = 'none'; }
      
      document.getElementById('paymentOverlay').classList.add('active');
      backToOptions();
      updateContactLinks(name, price, dataValue);
    }
    
    function closePayment() { document.getElementById('paymentOverlay').classList.remove('active'); }
    function backToOptions() {
      document.getElementById('paymentOptions').style.display = 'block';
      ['qrisDisplay','danaDisplay','gopayDisplay','shopeeDisplay','ovoDisplay'].forEach(id => document.getElementById(id).classList.remove('active'));
    }
    
    function showQRIS() { hideAll(); document.getElementById('qrisDisplay').classList.add('active'); }
    function showDana() { hideAll(); document.getElementById('danaDisplay').classList.add('active'); }
    function showGoPay() { hideAll(); document.getElementById('gopayDisplay').classList.add('active'); }
    function showShopeePay() { hideAll(); document.getElementById('shopeeDisplay').classList.add('active'); }
    function showOVO() { hideAll(); document.getElementById('ovoDisplay').classList.add('active'); }
    function hideAll() { document.getElementById('paymentOptions').style.display = 'none'; }

    function copyNumber(number) { navigator.clipboard.writeText(number).then(() => alert('✅ Disalin: ' + number)); }

    function updateContactLinks(name, price, dataValue) {
      let msg = `Halo Admin Franz Shop, saya sudah transfer:%0A%0A📦 Produk: ${encodeURIComponent(name)}%0A💰 Harga: ${encodeURIComponent(price)}`;
      if (dataValue) msg += `%0A📝 Data: ${encodeURIComponent(dataValue)}`;
      msg += `%0A%0AMohon diproses. Terima kasih!`;
      document.getElementById('waConfirmBtn').href = `https://wa.me/${WA_NUMBER}?text=${msg}`;
      document.getElementById('tgConfirmBtn').href = `https://t.me/FranzzOnly?text=${msg}`;
    }

    function openWA(name, price) {
      const msg = `Halo FRANZZ SHOP ID, saya ingin order:%0A📦 Produk: ${name}%0A💰 Harga: ${price}`;
      window.open(`https://wa.me/${CS_NUMBER}?text=${encodeURIComponent(msg)}`, '_blank');
    }

    document.getElementById('paymentOverlay').addEventListener('click', function(e) { if (e.target === this) closePayment(); });
    document.getElementById('dataInput').addEventListener('keypress', function(e) { if (e.key === 'Enter') submitData(); });
  </script>
</body>
</html>
