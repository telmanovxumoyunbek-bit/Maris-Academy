<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Maris Academy</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/tabler-icons.min.css">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
:root{--gold:#F5C518;--gold-dark:#D4A800;--gold-light:#FFF8D6;--black:#1a1a1a;--gray:#f5f5f0;}
body{font-family:Arial,sans-serif;background:#fff;overflow-x:hidden;}
nav{display:flex;align-items:center;justify-content:space-between;padding:12px 28px;border-bottom:2px solid var(--gold);background:#fff;position:sticky;top:0;z-index:100;box-shadow:0 2px 12px rgba(0,0,0,0.06);}
.logo{display:flex;align-items:center;gap:10px;}
.logo-m{width:38px;height:38px;background:var(--gold);border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:700;color:#1a1a1a;}
.logo-text .m{font-size:18px;font-weight:700;color:#1a1a1a;letter-spacing:2px;display:block;}
.logo-text .a{font-size:10px;color:#888;letter-spacing:3px;display:block;}
.nav-links{display:flex;gap:4px;flex-wrap:wrap;}
.nav-links a{font-size:12px;padding:6px 10px;border-radius:6px;color:#555;text-decoration:none;cursor:pointer;font-weight:500;transition:all 0.2s;}
.nav-links a:hover{background:var(--gold-light);color:#1a1a1a;}
.nav-links a.active{background:var(--gold);color:#1a1a1a;font-weight:700;}
.page-wrapper{overflow:hidden;}
section{display:none;animation:slideDown 0.45s cubic-bezier(0.22,1,0.36,1);}
section.active{display:block;}
@keyframes slideDown{from{opacity:0;transform:translateY(-32px);}to{opacity:1;transform:translateY(0);}}
.hero{padding:56px 32px;text-align:center;background:linear-gradient(135deg,#1a1a1a 0%,#2d2d2d 100%);color:#fff;}
.hero-badge{display:inline-block;background:var(--gold);color:#1a1a1a;font-size:11px;font-weight:700;padding:4px 14px;border-radius:20px;letter-spacing:1px;margin-bottom:16px;}
.hero h1{font-size:34px;font-weight:700;margin-bottom:10px;}
.hero h1 span{color:var(--gold);}
.hero p{font-size:15px;color:#ccc;max-width:480px;margin:0 auto 28px;line-height:1.6;}
.hero-btns{display:flex;gap:12px;justify-content:center;}
.btn-gold{padding:11px 26px;background:var(--gold);color:#1a1a1a;border:none;border-radius:8px;font-size:14px;cursor:pointer;font-weight:700;transition:all 0.2s;}
.btn-outline{padding:11px 26px;background:transparent;color:#fff;border:1.5px solid #fff;border-radius:8px;font-size:14px;cursor:pointer;transition:all 0.2s;}
.btn-gold:hover{background:var(--gold-dark);transform:translateY(-2px);box-shadow:0 6px 20px rgba(245,197,24,0.4);}
.btn-outline:hover{background:rgba(255,255,255,0.1);}
.stats{display:grid;grid-template-columns:repeat(4,1fr);background:#1a1a1a;}
.stat{text-align:center;padding:20px 12px;border-right:1px solid #333;transition:background 0.2s;}
.stat:hover{background:#222;}
.stat:last-child{border-right:none;}
.stat .num{font-size:26px;font-weight:700;color:var(--gold);}
.stat .lbl{font-size:11px;color:#aaa;margin-top:3px;}
.page-content{padding:40px 32px;background:#fff;min-height:300px;}
.section-header{text-align:center;margin-bottom:32px;}
.section-title{font-size:22px;font-weight:700;color:#1a1a1a;margin-bottom:6px;}
.section-sub{font-size:13px;color:#888;margin-bottom:12px;}
.gold-line{width:48px;height:3px;background:var(--gold);border-radius:2px;margin:10px auto 0;}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:14px;}
.card{background:#fff;border:1px solid #eee;border-radius:12px;padding:18px;transition:all 0.25s;box-shadow:0 1px 4px rgba(0,0,0,0.04);}
.card:hover{border-color:var(--gold);transform:translateY(-4px);box-shadow:0 8px 24px rgba(245,197,24,0.15);}
.card .icon{width:40px;height:40px;background:var(--gold-light);border-radius:8px;display:flex;align-items:center;justify-content:center;margin-bottom:12px;}
.card .icon i{font-size:20px;color:#b8860b;}
.card h3{font-size:14px;font-weight:600;color:#1a1a1a;margin-bottom:5px;}
.card p{font-size:12px;color:#888;line-height:1.5;}
.teachers-main{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:14px;margin-bottom:20px;}
.teacher{background:#fff;border:1px solid #eee;border-radius:12px;padding:18px;text-align:center;transition:all 0.25s;box-shadow:0 1px 4px rgba(0,0,0,0.04);}
.teacher:hover{border-color:var(--gold);transform:translateY(-4px);box-shadow:0 8px 24px rgba(245,197,24,0.15);}
.avatar{width:52px;height:52px;border-radius:50%;background:var(--gold);display:flex;align-items:center;justify-content:center;margin:0 auto 10px;font-size:15px;font-weight:700;color:#1a1a1a;transition:transform 0.2s;}
.teacher:hover .avatar{transform:scale(1.08);}
.teacher h3{font-size:13px;font-weight:600;color:#1a1a1a;margin-bottom:3px;}
.teacher p{font-size:11px;color:#888;}
.teacher .badge{display:inline-block;margin-top:6px;background:#1a1a1a;color:var(--gold);font-size:10px;padding:2px 8px;border-radius:20px;font-weight:600;}
.assistants{background:#f9f9f7;border:1px solid #eee;border-radius:12px;padding:18px;}
.assistants h3{font-size:14px;font-weight:600;color:#1a1a1a;margin-bottom:12px;}
.ass-list{display:flex;flex-wrap:wrap;gap:8px;}
.ass-tag{display:flex;align-items:center;gap:6px;background:var(--gold-light);border-radius:20px;padding:5px 12px;transition:all 0.2s;cursor:default;}
.ass-tag:hover{background:var(--gold);transform:translateY(-1px);}
.ass-av{width:24px;height:24px;border-radius:50%;background:var(--gold);font-size:9px;font-weight:700;display:flex;align-items:center;justify-content:center;color:#1a1a1a;}
.ass-tag span{font-size:12px;color:#1a1a1a;}
.prices{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;}
.price-card{background:#fff;border:1.5px solid #eee;border-radius:14px;padding:24px;transition:all 0.25s;box-shadow:0 1px 4px rgba(0,0,0,0.04);}
.price-card:hover{transform:translateY(-4px);box-shadow:0 10px 30px rgba(0,0,0,0.08);}
.price-card.featured{border:2px solid var(--gold);background:#fffbeb;}
.price-card.featured:hover{box-shadow:0 10px 30px rgba(245,197,24,0.25);}
.price-card .tag{font-size:10px;font-weight:700;background:var(--gold);color:#1a1a1a;padding:3px 10px;border-radius:20px;display:inline-block;margin-bottom:10px;}
.price-card h3{font-size:16px;font-weight:700;color:#1a1a1a;margin-bottom:6px;}
.price-card .price{font-size:26px;font-weight:700;color:#1a1a1a;margin-bottom:2px;}
.price-card .price span{font-size:13px;color:#888;font-weight:400;}
.price-card .per{font-size:12px;color:#aaa;margin-bottom:16px;}
.price-card ul{list-style:none;}
.price-card ul li{font-size:12px;color:#555;padding:4px 0;display:flex;align-items:center;gap:6px;border-bottom:0.5px solid #f0f0f0;}
.price-card ul li:last-child{border-bottom:none;}
.price-card ul li i{color:#b8860b;font-size:13px;}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.about-text p{font-size:13px;color:#555;line-height:1.7;margin-bottom:10px;}
.vals{display:flex;flex-direction:column;gap:10px;}
.val{display:flex;align-items:flex-start;gap:12px;padding:14px;background:#f9f9f7;border-radius:10px;border-left:3px solid var(--gold);transition:all 0.2s;}
.val:hover{background:var(--gold-light);transform:translateX(4px);}
.val i{font-size:18px;color:#b8860b;margin-top:1px;}
.val h4{font-size:13px;font-weight:600;color:#1a1a1a;}
.val p{font-size:11px;color:#888;margin-top:2px;}
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.contact-info{display:flex;flex-direction:column;gap:10px;}
.contact-item{display:flex;align-items:center;gap:12px;padding:14px;background:#f9f9f7;border-radius:10px;border-left:3px solid var(--gold);transition:all 0.2s;}
.contact-item:hover{background:var(--gold-light);transform:translateX(4px);}
.contact-item i{font-size:20px;color:#b8860b;}
.contact-item .label{font-size:11px;color:#aaa;}
.contact-item .value{font-size:13px;font-weight:600;color:#1a1a1a;}
.contact-form{display:flex;flex-direction:column;gap:10px;}
.contact-form input,.contact-form textarea{width:100%;padding:10px 12px;border:1px solid #ddd;border-radius:8px;font-size:13px;font-family:Arial,sans-serif;background:#fff;color:#1a1a1a;transition:border-color 0.2s;}
.contact-form input:focus,.contact-form textarea:focus{outline:none;border-color:var(--gold);box-shadow:0 0 0 3px rgba(245,197,24,0.12);}
.contact-form textarea{height:90px;resize:none;}
.contact-form button{padding:11px;background:var(--gold);color:#1a1a1a;border:none;border-radius:8px;font-size:14px;cursor:pointer;font-weight:700;transition:all 0.2s;}
.contact-form button:hover{background:var(--gold-dark);transform:translateY(-2px);box-shadow:0 6px 20px rgba(245,197,24,0.35);}
footer{padding:16px 28px;background:#1a1a1a;text-align:center;font-size:12px;color:#888;}
footer span{color:var(--gold);}
</style>
</head>
<body>
<nav>
  <div class="logo">
    <div class="logo-m">M</div>
    <div class="logo-text"><span class="m">MARIS</span><span class="a">ACADEMY</span></div>
  </div>
  <div class="nav-links">
    <a class="active" onclick="show('home',this)">Bosh sahifa</a>
    <a onclick="show('about',this)">Haqimizda</a>
    <a onclick="show('services',this)">Xizmatlar</a>
    <a onclick="show('teachers',this)">O'qituvchilar</a>
    <a onclick="show('prices',this)">Narxlar</a>
    <a onclick="show('contact',this)">Bog'lanish</a>
  </div>
</nav>
<div class="page-wrapper">
<section id="home" class="active">
  <div class="hero">
    <div class="hero-badge">✦ 2026-yildan buyon ishlamoqda</div>
    <h1>Bilim — <span>Kelajak</span> Kaliti</h1>
    <p>Maris Academy — Gazalkentdagi eng sifatli o'quv markazi. 15+ kurs, kichik guruhlar va tajribali o'qituvchilar bilan muvaffaqiyatga erishing.</p>
    <div class="hero-btns">
      <button class="btn-gold" onclick="show('services',document.querySelectorAll('.nav-links a')[2])">Kurslarni ko'rish</button>
      <button class="btn-outline" onclick="show('contact',document.querySelectorAll('.nav-links a')[5])">Bog'lanish</button>
    </div>
  </div>
  <div class="stats">
    <div class="stat"><div class="num">15+</div><div class="lbl">Kurslar</div></div>
    <div class="stat"><div class="num">10–15</div><div class="lbl">Guruh hajmi</div></div>
    <div class="stat"><div class="num">8+</div><div class="lbl">O'qituvchilar</div></div>
    <div class="stat"><div class="num">2026</div><div class="lbl">Ochilgan yil</div></div>
  </div>
</section>
<section id="about">
  <div class="page-content">
    <div class="section-header"><div class="section-title">Biz haqimizda</div><div class="gold-line"></div></div>
    <div class="about-grid">
      <div class="about-text">
        <p>Maris Academy — 2026-yilda Toshkent viloyati, Gazalkent shahrida tashkil etilgan zamonaviy o'quv markazi.</p>
        <p>Biz 15+ kurs yo'nalishi bo'yicha ta'lim beramiz. Har bir guruhda 10 dan 15 gacha o'quvchi bo'lib, har bir o'quvchiga individual yondashuv ta'minlanadi.</p>
        <p>Zamonaviy sinf xonalari, qulay muhit va tajribali jamoamiz bilan sizni muvaffaqiyatga olib chiqamiz.</p>
      </div>
      <div class="vals">
        <div class="val"><i class="ti ti-users"></i><div><h4>Kichik guruhlar</h4><p>Guruhda 10–15 nafar, individual diqqat</p></div></div>
        <div class="val"><i class="ti ti-award"></i><div><h4>Sifat kafolati</h4><p>Natijaga yo'naltirilgan o'qitish</p></div></div>
        <div class="val"><i class="ti ti-certificate"></i><div><h4>Sertifikat</h4><p>Kurs yakunida rasmiy sertifikat</p></div></div>
        <div class="val"><i class="ti ti-map-pin"></i><div><h4>Qulay joylashuv</h4><p>Gazalkent shahri markazida</p></div></div>
      </div>
    </div>
  </div>
</section>
<section id="services">
  <div class="page-content">
    <div class="section-header"><div class="section-title">Bizning kurslar</div><div class="section-sub">Faqat siz tanlagan yo'nalishlar</div><div class="gold-line"></div></div>
    <div class="cards">
      <div class="card"><div class="icon"><i class="ti ti-language"></i></div><h3>Ingliz tili</h3><p>Boshlang'ich dan IELTS/CEFR darajasigacha</p></div>
      <div class="card"><div class="icon"><i class="ti ti-brain"></i></div><h3>Mental arifmetika</h3><p>Tez hisoblash va xotira rivojlantirish</p></div>
      <div class="card"><div class="icon"><i class="ti ti-flag"></i></div><h3>Turk tili</h3><p>Boshlang'ich dan yuqori darajagacha</p></div>
      <div class="card"><div class="icon"><i class="ti ti-flag-2"></i></div><h3>Rus tili</h3><p>Grammatika, so'zlashuv va yozuv</p></div>
      <div class="card"><div class="icon"><i class="ti ti-seeding"></i></div><h3>Koreys tili</h3><p>Hangul, so'zlashuv va madaniyat</p></div>
    </div>
  </div>
</section>
<section id="teachers">
  <div class="page-content">
    <div class="section-header"><div class="section-title">O'qituvchilarimiz</div><div class="gold-line"></div></div>
    <div class="teachers-main">
      <div class="teacher"><div class="avatar">BS</div><h3>Botirov Shoxruz</h3><p>Ingliz tili</p><span class="badge">Asosiy ustoz</span></div>
      <div class="teacher"><div class="avatar">EA</div><h3>Elnur Amirgaliyev</h3><p>Ingliz tili</p><span class="badge">Asosiy ustoz</span></div>
      <div class="teacher"><div class="avatar">AJ</div><h3>Abdurashidov Javohir</h3><p>Ingliz tili</p><span class="badge">Asosiy ustoz</span></div>
      <div class="teacher"><div class="avatar">TO</div><h3>Toirov Odil</h3><p>Ingliz tili</p><span class="badge">Asosiy ustoz</span></div>
      <div class="teacher"><div class="avatar">RS</div><h3>Riskimbekov Samandar</h3><p>Mental arifmetika</p><span class="badge">Asosiy ustoz</span></div>
      <div class="teacher"><div class="avatar">HS</div><h3>Holmirzayeva Shodiya</h3><p>Ingliz tili</p><span class="badge">Asosiy ustoz</span></div>
    </div>
    <div class="assistants">
      <h3><i class="ti ti-users-group" style="font-size:16px;vertical-align:-2px;margin-right:6px;color:#b8860b;"></i>Assistent o'qituvchilar</h3>
      <div class="ass-list">
        <div class="ass-tag"><div class="ass-av">A1</div><span>Assistent 1</span></div>
        <div class="ass-tag"><div class="ass-av">A2</div><span>Assistent 2</span></div>
        <div class="ass-tag"><div class="ass-av">A3</div><span>Assistent 3</span></div>
        <div class="ass-tag" style="background:#f0f0f0;"><div class="ass-av" style="background:#ccc;color:#555;">+</div><span style="color:#888;">Va boshqalar</span></div>
      </div>
    </div>
  </div>
</section>
<section id="prices">
  <div class="page-content">
    <div class="section-header"><div class="section-title">Narxlar</div><div class="gold-line"></div></div>
    <div class="prices">
      <div class="price-card">
        <h3>Kids</h3>
        <div class="price">290 000 <span>so'm</span></div>
        <div class="per">oyiga / 1 kurs</div>
        <ul>
          <li><i class="ti ti-check"></i>Haftada 3 marta dars</li>
          <li><i class="ti ti-check"></i>O'yin orqali o'rganish</li>
          <li><i class="ti ti-check"></i>Guruhda 10–15 o'quvchi</li>
          <li><i class="ti ti-check"></i>Ota-onaga hisobot</li>
        </ul>
      </div>
      <div class="price-card featured">
        <div class="tag">★ MASHHUR</div>
        <h3>Standart</h3>
        <div class="price">350 000 <span>so'm</span></div>
        <div class="per">oyiga / 1 kurs</div>
        <ul>
          <li><i class="ti ti-check"></i>Haftada 3 marta dars</li>
          <li><i class="ti ti-check"></i>O'quv materiallari</li>
          <li><i class="ti ti-check"></i>Guruhda 10–15 o'quvchi</li>
          <li><i class="ti ti-check"></i>Test sinovlar</li>
          <li><i class="ti ti-check"></i>Kurs sertifikati</li>
        </ul>
      </div>
      <div class="price-card">
        <h3>IELTS / CEFR</h3>
        <div class="price">450 000 <span>so'm</span></div>
        <div class="per">oyiga / 1 kurs</div>
        <ul>
          <li><i class="ti ti-check"></i>Intensiv tayyorgarlik</li>
          <li><i class="ti ti-check"></i>Mock testlar</li>
          <li><i class="ti ti-check"></i>Kichik guruh (10 nafar)</li>
          <li><i class="ti ti-check"></i>Band/daraja kafolati</li>
          <li><i class="ti ti-check"></i>Sertifikat + portfolio</li>
        </ul>
      </div>
    </div>
  </div>
</section>
<section id="contact">
  <div class="page-content">
    <div class="section-header"><div class="section-title">Bog'lanish</div><div class="gold-line"></div></div>
    <div class="contact-grid">
      <div class="contact-info">
        <div class="contact-item"><i class="ti ti-phone"></i><div><div class="label">Telefon</div><div class="value">+998 77 720 40 40</div></div></div>
        <div class="contact-item"><i class="ti ti-map-pin"></i><div><div class="label">Manzil</div><div class="value">Toshkent vil., Gazalkent shahri</div></div></div>
        <div class="contact-item"><i class="ti ti-clock"></i><div><div class="label">Ish vaqti</div><div class="value">Du–Sha: 8:00 – 20:00</div></div></div>
        <div class="contact-item"><i class="ti ti-brand-telegram"></i><div><div class="label">Telegram</div><div class="value">@maris_academy</div></div></div>
        <div class="contact-item"><i class="ti ti-brand-instagram"></i><div><div class="label">Instagram</div><div class="value">@maris_academy</div></div></div>
      </div>
      <div class="contact-form">
        <input type="text" placeholder="Ismingiz">
        <input type="text" placeholder="Telefon raqamingiz">
        <input type="text" placeholder="Qaysi kurs qiziqtiradi?">
        <textarea placeholder="Qo'shimcha savollar..."></textarea>
        <button>📩 Murojaat yuborish</button>
      </div>
    </div>
  </div>
</section>
</div>
<footer>© 2026 <span>Maris Academy</span> — Toshkent vil., Gazalkent shahri &nbsp;|&nbsp; +998 77 720 40 40</footer>
<script>
function show(id, el) {
  document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  if (el) el.classList.add('active');
}
</script>
</body>
</html>
 
