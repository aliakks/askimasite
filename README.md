# askimasite
askimasite
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Nur — Seni Seviyorum</title>
  <style>
    :root{
      --bg1:#0f172a; /* gece mavisi */
      --bg2:#1e293b;
      --accent:#ff6b81; /* pembe/mercandan ton */
      --glass: rgba(255,255,255,0.06);
      --glass-2: rgba(255,255,255,0.04);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0}
    body{
      display:flex;align-items:center;justify-content:center;
      background: radial-gradient(1200px 600px at 10% 20%, rgba(255,107,129,0.06), transparent),
                  radial-gradient(1000px 500px at 90% 80%, rgba(99,102,241,0.06), transparent),
                  linear-gradient(180deg,var(--bg1),var(--bg2));
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:32px;
    }

    .card{
      width:min(920px,96vw);
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:20px;
      padding:28px;
      display:grid;grid-template-columns:360px 1fr;gap:24px;
      box-shadow: 0 10px 30px rgba(2,6,23,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
      align-items:center;
      backdrop-filter: blur(6px) saturate(110%);
    }

    @media (max-width:860px){
      .card{grid-template-columns:1fr; padding:20px}
    }

    /* Kalp bölümü */
    .heart-wrap{
      display:flex;flex-direction:column;align-items:center;gap:16px;padding:18px;
    }
    .heart{
      width:260px;height:260px;display:flex;align-items:center;justify-content:center;
      position:relative;cursor:pointer;transition:transform .18s ease;
    }
    .heart svg{width:100%;height:100%;filter:drop-shadow(0 10px 30px rgba(255,107,129,0.18));}
    .heart.pulse{animation:pop .9s ease infinite}
    @keyframes pop{
      0%{transform:scale(1)}
      30%{transform:scale(1.06)}
      60%{transform:scale(0.98)}
      100%{transform:scale(1)}
    }

    .name{
      font-size:28px;font-weight:700;color:var(--accent);letter-spacing:0.6px;
    }

    .sub{color:#d1e6ff88;font-size:13px}

    /* Sağ taraf: mesaj ve düğmeler */
    .content{
      padding:16px 8px;
    }
    .headline{
      font-size:28px;margin:0 0 8px 0;line-height:1.05;color:#fff;
    }
    .message{
      color:#dbe9ff;opacity:0.95;font-size:15px;line-height:1.6;margin-bottom:18px;
    }

    .cta-row{display:flex;gap:12px;flex-wrap:wrap}
    .btn{
      display:inline-flex;align-items:center;gap:10px;padding:10px 14px;border-radius:12px;border:1px solid rgba(255,255,255,0.04);
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      color:#fff;text-decoration:none;font-weight:600;font-size:14px;backdrop-filter: blur(4px);
      transition:transform .12s ease, box-shadow .12s ease;
    }
    .btn:active{transform:translateY(1px)}
    .btn .icon{width:18px;height:18px;display:inline-block}

    .small{font-size:12px;color:#bcd7ff88;margin-top:12px}

    footer{margin-top:18px;font-size:12px;color:#a9c9ff66}

    /* İnteraktif kalp animasyon için alt-lights */
    .glow{
      position:absolute;inset:0;border-radius:50%;pointer-events:none;mix-blend-mode:screen;opacity:0.9;
      background: radial-gradient(circle at 30% 35%, rgba(255,107,129,0.12), transparent 18%),
                  radial-gradient(circle at 70% 70%, rgba(99,102,241,0.08), transparent 20%);
    }

    /* İçteki yazı kutusu */
    .poem{
      background:var(--glass);padding:16px;border-radius:12px;border:1px solid rgba(255,255,255,0.02);
    }

  </style>
</head>
<body>
  <div class="card" role="main">
    <div class="heart-wrap">
      <div class="heart" id="heartBtn" title="Kalbe tıkla!">
        <!-- Büyük vektör kalp -->
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <defs>
            <linearGradient id="g1" x1="0" x2="1">
              <stop offset="0" stop-color="#ff7a95" />
              <stop offset="1" stop-color="#ff4d6d" />
            </linearGradient>
          </defs>
          <path d="M12 21s-7.5-4.6-10-7.4C-0.1 9.1 3.1 4 7.8 6.5 9.9 7.7 12 10 12 10s2.1-2.3 4.2-3.5C20.9 4 24.1 9.1 22 13.6 19.5 16.4 12 21 12 21z" fill="url(#g1)" />
        </svg>
        <div class="glow"></div>
      </div>

      <div style="text-align:center;">
        <div class="name">Nur</div>
        <div class="sub">Bu sayfa sadece ikimiz için — kalbim sana ait.</div>
      </div>

      <div style="font-size:12px;color:#cbe6ff66;text-align:center;padding:6px 10px;">Kalbe tıkla veya dokun — sana olan hislerimi gösterir.</div>
    </div>

    <div class="content">
      <h1 class="headline">Nur, her anımda seninle.</h1>
      <div class="message poem">
        Hayatımın en güzel sürprizisin. Gülüşün bir sabah güneşi gibi içimi ısıtırken, sesin en zor günümde bile umut veriyor.
        Seninle küçük anlar büyük anlamlar kazanıyor — ve ben her anı seninle paylaşmak istiyorum.
        <br/><br/>
        "Seni seviyorum" demek burada kelimeden öte; her nefeste, her düşüncede sen varsın.
      </div>

      <div class="cta-row">
        <!-- Düzenleyebileceğiniz Instagram linkleri: aşağıdaki href'leri kendi kullanıcı adlarınıza göre değiştirin -->
        <a class="btn" id="myIg" href="https://instagram.com/_aliakkus0_" target="_blank" rel="noopener noreferrer">
          <span class="icon" aria-hidden="true">
            <!-- Instagram küçük SVG ikonu -->
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.2">
              <rect x="3" y="3" width="18" height="18" rx="5" ry="5"></rect>
              <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
              <line x1="17.5" y1="6.5" x2="17.5" y2="6.5"></line>
            </svg>
          </span>
          Benim Instagramım
        </a>

        <a class="btn" id="nurIg" href="https://instagram.com/nurrysl__" target="_blank" rel="noopener noreferrer">
          <span class="icon" aria-hidden="true">
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.2">
              <rect x="3" y="3" width="18" height="18" rx="5" ry="5"></rect>
              <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
              <line x1="17.5" y1="6.5" x2="17.5" y2="6.5"></line>
            </svg>
          </span>
          Nur'un Instagramı
        </a>

        <a class="btn" href="#" id="downloadBtn" title="Sayfayı .html olarak indir">
          <span class="icon" aria-hidden="true">📥</span>
          Sayfayı İndir
        </a>

      </div>

      <div class="small">Not: Linkleri kendi Instagram kullanıcı adınıza göre güncelleyin.</div>

      <footer>Hazırlayan: Ali Akkuş Tanıyana :D </footer>
    </div>
  </div>

<script>
  // Kalp etkileşimi
  const heart = document.getElementById('heartBtn');
  let pulse = false;
  heart.addEventListener('click', ()=>{
    pulse = !pulse;
    if(pulse) heart.classList.add('pulse'); else heart.classList.remove('pulse');
  });

  // Sayfayı HTML dosyası olarak indirme
  document.getElementById('downloadBtn').addEventListener('click', async (e)=>{
    e.preventDefault();
    const html = `<!DOCTYPE html>\n${document.documentElement.outerHTML}`;
    const blob = new Blob([html], {type:'text/html'});
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url; a.download = 'nur-sevgi-sayfasi.html';
    document.body.appendChild(a); a.click(); a.remove();
    URL.revokeObjectURL(url);
  });

  // Küçük erişilebilirlik: Enter veya Space ile de çalışsın
  heart.setAttribute('tabindex','0');
  heart.addEventListener('keydown', (ev)=>{ if(ev.key === 'Enter' || ev.key === ' ') { ev.preventDefault(); heart.click(); } });
</script>
</body>
</html>
