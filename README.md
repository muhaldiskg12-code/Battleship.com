# Battleship.com
Website
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Battleship.com</title>
  <meta name="description" content="Sejarah singkat, spesifikasi, dan galeri KMS Bismarck — salah satu battleship paling terkenal pada Perang Dunia II." />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='0.9em' font-size='90'%3E⚓%3C/text%3E%3C/svg%3E" />
  <style>
    /* Reset ringan */
    :root{
      --bg:#071428;
      --card:#0d2540;
      --accent:#c77b3d;
      --muted:#9fb2c8;
      --glass: rgba(255,255,255,0.04);
      --radius:12px;
      --maxw:1100px;
      font-family: Inter, ui-sans-serif, system-ui, "Helvetica Neue", Arial;
      color-scheme: dark;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background:linear-gradient(180deg,var(--bg) 0%, #031622 70%);
      color:#e6f0f6;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      padding:24px;
      display:flex;
      justify-content:center;
      font-size:16px;
    }
    .site{
      width:100%;
      max-width:var(--maxw);
    }

    header{
      display:flex;
      gap:16px;
      align-items:center;
      justify-content:space-between;
      margin-bottom:18px;
    }
    .brand{
      display:flex;
      gap:12px;
      align-items:center;
    }
    .logo{
      width:56px;height:56px;
      background:linear-gradient(135deg,#152b3f,#0b1a2b);
      border-radius:10px;
      display:grid;
      place-items:center;
      box-shadow:0 6px 18px rgba(0,0,0,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
      font-weight:700;
      font-size:20px;
    }
    .brand h1{
      margin:0;
      font-size:18px;
      letter-spacing:0.3px;
    }
    .nav{
      display:flex;
      gap:12px;
      align-items:center;
    }
    .nav a{
      color:var(--muted);
      text-decoration:none;
      font-size:14px;
      padding:8px 12px;
      border-radius:8px;
    }
    .nav a:hover{color:#fff;background:rgba(255,255,255,0.03)}

    main{display:grid;grid-template-columns:1fr;gap:18px}

    .hero{
      background: linear-gradient(90deg, rgba(7,20,40,0.6), rgba(3,10,18,0.6)), url('images/bismarck.jpg') center/cover no-repeat;
      border-radius:var(--radius);
      padding:28px;
      min-height:320px;
      display:flex;
      gap:24px;
      align-items:flex-end;
      position:relative;
      overflow:hidden;
    }
    .hero::after{
      content:"";
      position:absolute;
      inset:0;
      background: linear-gradient(180deg, transparent 30%, rgba(3,6,10,0.6) 100%);
      pointer-events:none;
    }
    .hero .intro{
      position:relative;
      z-index:2;
      max-width:680px;
      backdrop-filter: blur(4px) saturate(80%);
    }
    .kicker{
      display:inline-block;
      background:var(--glass);
      padding:6px 10px;
      border-radius:999px;
      color:var(--muted);
      font-weight:600;
      font-size:13px;
      margin-bottom:12px;
      border:1px solid rgba(255,255,255,0.03);
    }
    .hero h2{
      margin:6px 0 10px;
      font-size:28px;
      line-height:1.05;
    }
    .hero p{margin:0;color:var(--muted)}
    .cta{
      margin-top:14px;
      display:flex;gap:10px;
    }
    .btn{
      background:linear-gradient(90deg,var(--accent), #a65f2d);
      color:#041018;
      padding:10px 14px;
      border-radius:10px;
      font-weight:700;
      border:none;
      cursor:pointer;
      box-shadow:0 6px 20px rgba(199,123,61,0.18);
    }
    .btn.ghost{
      background:transparent;color:var(--muted);border:1px solid rgba(255,255,255,0.04)
    }

    .cards{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px;
      padding:16px;
      border:1px solid rgba(255,255,255,0.03);
      box-shadow:0 8px 20px rgba(2,6,10,0.6);
    }
    .card h3{margin:0 0 8px;font-size:15px}
    .specs{display:flex;flex-direction:column;gap:8px;font-size:14px;color:var(--muted)}

    section.info{
      display:grid;
      grid-template-columns:1fr 360px;
      gap:18px;
      align-items:start;
    }
    .article{
      background:var(--card);
      padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);
    }
    .timeline{
      list-style:none;padding:0;margin:0;color:var(--muted);
      display:flex;flex-direction:column;gap:12px;
    }
    .timeline li{background:rgba(255,255,255,0.02);padding:10px;border-radius:10px;font-size:14px}

    .side{
      position:relative;
    }
    .gallery{
      display:grid;grid-template-columns:1fr 1fr;gap:8px;
    }
    .gallery img{width:100%;height:140px;object-fit:cover;border-radius:10px;display:block}

    footer{
      margin-top:18px;color:var(--muted);font-size:14px;padding:12px;text-align:center;
    }

    /* responsive */
    @media (max-width:980px){
      .cards{grid-template-columns:repeat(2,1fr)}
      section.info{grid-template-columns:1fr}
      .hero{min-height:380px;background-position:top}
    }
    @media (max-width:640px){
      body{padding:12px}
      header{flex-direction:column;align-items:flex-start;gap:12px}
      .cards{grid-template-columns:1fr}
      .gallery img{height:120px}
      .hero h2{font-size:22px}
    }

    /* subtle animation */
    .hero{transform-origin:center;animation:float 8s ease-in-out infinite}
    @keyframes float{
      0%{transform:translateY(0px)}
      50%{transform:translateY(-6px)}
      100%{transform:translateY(0px)}
    }
    /* accessible focus */
    a:focus, button:focus{outline:3px solid rgba(200,160,100,0.18);outline-offset:3px}
  </style>
</head>
<body>
  <div class="site" role="document">
    <header>
      <div class="brand" aria-label="Brand">
        <div class="logo" aria-hidden="true">⚓</div>
        <div>
          <h1>Battleship — Perang Dunia II</h1>
          <div style="font-size:13px;color:var(--muted)">Fokus: <strong>KMS Bismarck</strong></div>
        </div>
      </div>

      <nav class="nav" aria-label="Navigasi utama">
        <a href="#overview">Overview</a>
        <a href="#specs">Spesifikasi</a>
        <a href="#timeline">Timeline</a>
        <a href="#gallery">Galeri</a>
      </nav>
    </header>

    <main>
      <!-- HERO -->
      <section class="hero" role="banner" aria-label="KMS Bismarck hero image">
        <div class="intro" aria-hidden="false">
          <div class="kicker">Battleship • WWII</div>
          <h2>KMS Bismarck — Raksasa Perang Laut Jerman</h2>
          <p>
            <div class="bismarck-image-wrapper">
    <img src="images/bismarck.png" alt="KMS Bismarck" class="bismarck-image">
</div>
            KMS Bismarck adalah salah satu kapal perang paling terkenal pada Perang Dunia II.
            Dibangun untuk menjadi simbol kekuatan laut, Bismarck terlibat dalam peristiwa dramatis yang mengubah strategi laut Atlantik.
          </p>
          <div class="cta">
            <button class="btn" onclick="document.getElementById('timeline').scrollIntoView({behavior:'smooth'})">Lihat Timeline</button>
            <button class="btn ghost" onclick="document.getElementById('gallery').scrollIntoView({behavior:'smooth'})">Lihat Galeri</button>
          </div>
        </div>
      </section>

      <!-- KARTU / FAKTA -->
      <div class="cards" aria-hidden="false">
        <article class="card" role="article" aria-label="Ringkasan">
          <h3>Ringkasan</h3>
          <p style="color:var(--muted);margin:0">Kapal perang kelas battleship/battlecruiser milik Kriegsmarine Jerman, terkenal karena keterlibatannya dalam pengejaran dan tenggelamannya di perairan Atlantik Utara.</p>
        </article>

        <aside class="card" role="complementary" aria-label="Spesifikasi singkat">
          <h3>Spesifikasi singkat</h3>
          <div class="specs">
            <div><strong>Berat penuh:</strong> ~50.000 ton (dep. muatan dan versi)</div>
            <div><strong>Panjang:</strong> ~251 m</div>
            <div><strong>Kecepatan:</strong> ~30 knot</div>
            <div><strong>Bersenjata utama:</strong> 8 × 38 cm (15 inch) meriam utama</div>
          </div>
        </aside>

        <div class="card" role="note" aria-label="Fakta menarik">
          <h3>Fakta menarik</h3>
          <ul style="margin:0;color:var(--muted);padding-left:18px">
            <li>Dirancang sebagai simbol kekuatan laut Jerman.</li>
            <li>Mengalami pengejaran besar oleh Angkatan Laut Inggris.</li>
            <li>Gambar dan cerita Bismarck sering dijadikan studi taktik laut modern.</li>
          </ul>
        </div>
      </div>

      <!-- INFO + TIMELINE + GALLERY -->
      <section class="info" aria-label="Informasi dan timeline">
        <article class="article" id="overview" aria-labelledby="ov-title">
          <h2 id="ov-title" style="margin-top:0">Overview & Sejarah</h2>
          <p style="color:var(--muted)">
            KMS Bismarck adalah kapal perang yang dibangun oleh Jerman pada akhir 1930-an — awal 1940-an. Dikenal karena campuran kecepatan, daya tembak, dan lapisan pelindung yang membuatnya sangat berbahaya bagi konvoi kapal musuh.
          </p>

          <h3 style="margin-bottom:8px">Ringkasan tindakan</h3>
          <ul style="color:var(--muted);padding-left:18px">
            <li>Terlibat dalam operasi laut di Atlantik.</li>
            <li>Menghadapi kapal-perang Inggris dan kapal perusak pendukung.</li>
            <li>Berakhir dalam pengejaran besar dan tenggelam pada bulan Mei 1941.</li>
          </ul>

          <h3 style="margin-top:14px">Sumber & Rekomendasi bacaan</h3>
          <p style="color:var(--muted)">Untuk foto berkualitas tinggi (public domain / commons) dan kronologi resmi, cari arsip foto laut dan Wikimedia Commons, atau buku sejarah maritim Perang Dunia II.</p>
        </article>

        <aside class="side" aria-label="Sidebar">
          <div class="article" id="specs" aria-labelledby="spec-title">
            <h3 id="spec-title">Spesifikasi lengkap (ringkas)</h3>
            <div style="color:var(--muted);font-size:14px">
              <strong>Peluncuran:</strong> 1939–1940 (variasi deploy).<br/>
              <strong>Mesin:</strong> Turbin uap, beberapa ruang mesin.<br/>
              <strong>Awak:</strong> Ribuan (tergantung kru & misi).<br/>
              <strong>Peran:</strong> Kapal perang utama / penyerang konvoi.
            </div>
          </div>

          <div style="height:14px"></div>

          <div class="article" id="timeline" aria-labelledby="tl-title">
            <h3 id="tl-title">Timeline singkat</h3>
            <ul class="timeline" aria-hidden="false">
              <li><strong>1936–1939:</strong> Desain & pembangunan.</li>
              <li><strong>1940:</strong> Penempatan pertama dan latihan tempur.</li>
              <li><strong>Mei 1941:</strong> Pengejaran & tenggelam (peristiwa terkenal).</li>
            </ul>
          </div>
        </aside>
      </section>

      <!-- GALLERY -->
      <section class="article" id="gallery" aria-labelledby="gal-title" style="margin-top:6px">
        <h2 id="gal-title" style="margin-top:0">Galeri & Foto</h2>
        <p style="color:var(--muted);margin-top:0"> Dan ini adalah Gambar dari Kapal Bismarck Buatan German<code> </code>.</p>
        <div class="gallery" aria-hidden="false">
          <!-- GANTI Sumber gambar sesuai file Anda -->
          <img src="images/bismarck-1.jpg" alt="KMS Bismarck — tampak samping (ganti dengan foto asli di folder images/)" />
          <img src="images/bismarck-2.jpg" alt="KMS Bismarck — detail meriam (opsional)" />
          <img src="images/engagement.jpg" alt="Ilustrasi pertempuran laut (opsional)" />
          <img src="images/blueprint.jpg" alt="Skematik/blueprint (opsional)" />
        </div>
      </section>

      <footer>
        <div style="max-width:900px;margin:0 auto">
          <div style="display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;align-items:center">
            <div>© <strong>Battleship — Perang Dunia II</strong> — creat by Ahmad Noval Fahri</div>
            <div style="color:var(--muted)">Sumber gambar: Wikimedia Commons / arsip publik (direkomendasikan)</div>
          </div>
        </div>
      
<div style="margin-top:14px; padding-top:10px; border-top:1px solid rgba(255,255,255,0.06);">
  <div style="font-size:15px; color:var(--muted);">
    <strong>Contact:</strong><br>
    Instagram: 
    <a href="https://www.instagram.com/deutschland_de?igsh=cG5ta2wwbWJ2Zmli" target="_blank" style="color:#fff;">
      @deutschland_de
    </a><br>
    WhatsApp: 
    <a href="https://wa.me/6285341629123" target="_blank" style="color:#fff;">
      0853-4162-9123
    </a>
  </div>
</div>

</footer>
    </main>
  </div>

  <script>
    // small JS enhancements
    // keyboard-friendly: press "g" to go to gallery
    document.addEventListener('keydown', function(e){
      if(e.key.toLowerCase() === 'g'){
        const gal = document.getElementById('gallery');
        if(gal) gal.scrollIntoView({behavior:'smooth'});
      }
    });

    // lazy load fallback
    document.querySelectorAll('img').forEach(img=>{
      if('loading' in HTMLImageElement.prototype){
        img.loading = 'lazy';
      }
    });
  </script>
  <link rel="stylesheet" href="style.css">
<!-- OCEAN PARALLAX (place near top of body) -->
<div class="ocean" aria-hidden="true">
  <div class="wave w1"></div>
  <div class="wave w2"></div>
  <div class="wave w3"></div>
</div>

<!-- HERO (example) -->
<section class="hero" role="banner" aria-label="KMS Bismarck hero image">
  <div class="searchlight" aria-hidden="true"></div> <!-- searchlight -->
  <div class="overlay-grain" aria-hidden="true"></div>
  <div class="flak" aria-hidden="true">
    <i></i><i></i><i></i><i></i>
  </div>
  <div class="smoke" aria-hidden="true">
    <div class="p p1"></div>
    <div class="p p2"></div>
  </div>

  <div class="intro">
    <div class="kicker doc-label">Battleship • WWII</div>
    <h2 class="gun-flash">KMS Bismarck — Raksasa Perang Laut</h2>
    <p class="lead">Deskripsi singkat ...</p>
    <div style="margin-top:14px">
      <button class="btn btn-primary">Lihat Timeline</button>
      <button class="btn btn-ghost">Lihat Galeri</button>
    </div>
  </div>
</section>

<!-- RADAR (sidebar example) -->
<aside>
  <div class="radar" aria-hidden="true">
    <div class="grid" aria-hidden="true"></div>
    <div class="sweep"></div>
    <div class="ring r1"></div>
    <div class="ring r2"></div>
    <div class="ring r3"></div>
    <div class="ping" aria-hidden="true"></div>
  </div>
</aside>

<!-- SONAR loader -->
<div class="sonar" role="status" aria-label="sonar loading"><div></div></div>

<!-- CCTV vintage overlay (global film effect) -->
<div class="cctv" aria-hidden="true">
  <div class="scanline"></div>
</div>
</body>
</html>
