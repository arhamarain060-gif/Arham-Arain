<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>YourGoatViper — Links</title>
  <meta name="description" content="YourGoatViper — connect on TikTok, YouTube, Instagram, WhatsApp" />

  <style>
    /* ---- Base / Reset ---- */
    :root{
      --bg1: #4f46e5; /* indigo */
      --bg2: #7c3aed; /* purple */
      --accent: #00d4ff;
      --glass: rgba(255,255,255,0.06);
      --card-bg: rgba(255,255,255,0.06);
      --text: #e8eefc;
      --muted: rgba(232,238,252,0.75);
      --glass-2: rgba(255,255,255,0.04);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      background: linear-gradient(120deg,var(--bg1),var(--bg2));
      display:flex;
      align-items:center;
      justify-content:center;
      padding:32px;
      overflow-y:auto;
    }

    /* Animated gradient overlay */
    .gradient {
      position:fixed;
      inset:0;
      z-index:-2;
      background: linear-gradient(120deg, rgba(79,70,229,0.15), rgba(124,58,237,0.15));
    }
    .animated-gradient {
      position: absolute;
      inset: -20%;
      filter: blur(60px);
      background: conic-gradient(from 180deg at 50% 50%, rgba(0,212,255,0.08), rgba(124,58,237,0.08), rgba(79,70,229,0.08));
      animation: rotate 12s linear infinite;
      z-index:-1;
      mix-blend-mode: screen;
      opacity:0.9;
    }
    @keyframes rotate { to{ transform: rotate(360deg); } }

    /* container */
    .wrap{
      width:100%;
      max-width:420px;
      margin:40px auto;
      text-align:center;
    }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      border-radius:18px;
      padding:28px;
      box-shadow: 0 12px 30px rgba(12,18,30,0.45);
      border: 1px solid rgba(255,255,255,0.04);
      backdrop-filter: blur(8px);
      transition: transform .4s cubic-bezier(.2,.9,.2,1), box-shadow .4s;
    }
    .card:hover{ transform: translateY(-6px); box-shadow:0 20px 45px rgba(12,18,30,0.6); }

    .avatar {
      width:96px;
      height:96px;
      margin:-72px auto 10px;
      border-radius:50%;
      overflow:hidden;
      border:4px solid rgba(255,255,255,0.08);
      box-shadow: 0 6px 18px rgba(0,0,0,0.45);
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
      display:flex;
      align-items:center;
      justify-content:center;
    }
    .avatar img{ width:100%; height:100%; object-fit:cover; display:block; }

    h1{
      margin:12px 0 4px;
      font-size:22px;
      letter-spacing:0.2px;
      color: #ffffff;
    }
    p.lead{
      margin:0 0 18px;
      font-size:13px;
      color:var(--muted);
    }

    /* buttons */
    .links{
      display:flex;
      flex-direction:column;
      gap:12px;
      margin-top:6px;
    }
    .btn {
      display:flex;
      align-items:center;
      gap:12px;
      justify-content:center;
      padding:12px 16px;
      border-radius:12px;
      font-weight:600;
      font-size:15px;
      color:var(--text);
      text-decoration:none;
      background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border: 1px solid rgba(255,255,255,0.05);
      transition: transform .18s ease, box-shadow .18s ease, background .18s;
      position:relative;
      overflow:hidden;
    }
    .btn:hover{ transform: translateY(-3px); box-shadow: 0 10px 24px rgba(12,18,30,0.45); }
    .btn .icon{
      width:22px;height:22px; display:inline-flex; align-items:center; justify-content:center; flex-shrink:0;
      filter: drop-shadow(0 2px 6px rgba(0,0,0,0.35));
    }
    .btn .label{ flex:1; text-align:left; }

    .btn.tiktok { background: linear-gradient(90deg, rgba(0,0,0,0.04), rgba(255,255,255,0.015)); }
    .btn.youtube { background: linear-gradient(90deg, rgba(255,0,0,0.04), rgba(255,255,255,0.015)); }
    .btn.insta { background: linear-gradient(90deg, rgba(252,70,107,0.04), rgba(255,255,255,0.015)); }
    .btn.whatsapp { background: linear-gradient(90deg, rgba(37,211,102,0.06), rgba(255,255,255,0.015)); }

    .btn small{ display:block; color:var(--muted); font-weight:500; font-size:12px; margin-top:2px; }

    /* footer / small note */
    .note{
      margin-top:18px;
      font-size:12px;
      color:var(--muted);
    }

    /* QR modal (optional if image present) */
    .qr-modal {
      position:fixed;
      left:0; right:0; top:0; bottom:0;
      display:flex; align-items:center; justify-content:center;
      background: rgba(2,6,23,0.6);
      z-index:9999;
      opacity:0; pointer-events:none;
      transition: opacity .18s ease;
    }
    .qr-modal.open{ opacity:1; pointer-events:auto; }
    .qr-card{
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px;
      padding:18px;
      width:260px;
      text-align:center;
      box-shadow:0 20px 50px rgba(2,6,23,0.7);
      border:1px solid rgba(255,255,255,0.04);
    }
    .qr-card img{ width:200px; height:200px; object-fit:contain; display:block; margin:0 auto 10px; }

    /* small screens */
    @media (max-width:480px){
      .card{ padding:20px; border-radius:14px; }
      .avatar{ width:86px; height:86px; margin-top:-66px; }
      .btn{ padding:12px; font-size:14px; border-radius:10px; }
      .wrap{ padding:12px; }
    }
  </style>
</head>
<body>
  <div class="gradient" aria-hidden="true">
    <div class="animated-gradient" aria-hidden="true"></div>
  </div>

  <main class="wrap" role="main" aria-labelledby="title">
    <div class="card" role="region" aria-label="YourGoatViper profile links">
      <div class="avatar" aria-hidden="true">
        <!-- Put your avatar image in the same folder named avatar.jpg -->
        <img src="avatar.jpg" alt="YourGoatViper avatar" onerror="this.onerror=null;this.src='data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 width=%2296%22 height=%2296%22><rect fill=%22%233f3caa%22 width=%22100%25%22 height=%22100%25%22 rx=%2218%22/></svg>'">
      </div>

      <h1 id="title">YourGoatViper</h1>
      <p class="lead">Creator — Connect with me</p>

      <div class="links" role="list">
        <!-- TikTok -->
        <a class="btn tiktok" href="https://www.tiktok.com/@yourgoatviper?_t=ZS-90S15LBVKrM&_r=1" target="_blank" rel="noopener" role="listitem" aria-label="Open TikTok">
          <span class="icon" aria-hidden="true">
            <!-- TikTok SVG (minimal) -->
            <svg viewBox="0 0 24 24" width="22" height="22" fill="currentColor" style="color:white">
              <path d="M9 3v10.5A4.5 4.5 0 1 0 13.5 18V8h3.75A6.75 6.75 0 1 1 9 3z"></path>
            </svg>
          </span>
          <span class="label">
            TikTok
            <small>@yourgoatviper</small>
          </span>
        </a>

        <!-- YouTube -->
        <a class="btn youtube" href="https://www.youtube.com/@YourGoatViper" target="_blank" rel="noopener" role="listitem" aria-label="Open YouTube">
          <span class="icon" aria-hidden="true">
            <svg viewBox="0 0 24 24" width="22" height="22" fill="currentColor" style="color:#FF4444">
              <path d="M23.5 6.2s-.2-1.6-.8-2.3c-.8-.9-1.7-.9-2.1-1C17.6 2.5 12 2.5 12 2.5s-5.6 0-8.6.4c-.4.1-1.3.1-2.1 1C.7 4.6.6 6.2.6 6.2S.4 8.3.4 10.4v3.2c0 2.1.2 4.2.2 4.2s.2 1.6.8 2.3c.8.9 1.9.9 2.4 1 1.7.2 7.3.3 7.3.3s5.6 0 8.6-.4c.4-.1 1.3-.1 2.1-1 .6-.7.8-2.3.8-2.3s.2-2.1.2-4.2V10.4c0-2.1-.2-4.2-.2-4.2zM9.6 15.2V7.8l6.3 3.7-6.3 3.7z"></path>
            </svg>
          </span>
          <span class="label">
            YouTube
            <small>@YourGoatViper</small>
          </span>
        </a>

        <!-- Instagram -->
        <a class="btn insta" href="https://www.instagram.com/arham_arain333?igsh=NGhobDk1c29rd3oy&utm_source=qr" target="_blank" rel="noopener" role="listitem" aria-label="Open Instagram">
          <span class="icon" aria-hidden="true">
            <svg viewBox="0 0 24 24" width="22" height="22" fill="currentColor" style="color:#FF7A59">
              <path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5zm5 6.5A3.5 3.5 0 1 0 15.5 12 3.5 3.5 0 0 0 12 8.5zm4.8-3.7a1.15 1.15 0 1 1-1.15 1.15 1.15 1.15 0 0 1 1.15-1.15z"></path>
            </svg>
          </span>
          <span class="label">
            Instagram
            <small>@arham_arain333</small>
          </span>
        </a>

        <!-- WhatsApp: opens direct chat -->
        <a class="btn whatsapp" id="whatsappBtn" href="https://wa.me/923348666640" target="_blank" rel="noopener" role="listitem" aria-label="Message on WhatsApp">
          <span class="icon" aria-hidden="true">
            <svg viewBox="0 0 24 24" width="22" height="22" fill="currentColor" style="color:#25D366">
              <path d="M20.52 3.48A11.93 11.93 0 0 0 12 0C5.373 0 .09 5.283.09 11.91c0 2.103.545 4.155 1.58 5.97L0 24l6.45-1.66A11.877 11.877 0 0 0 12 23.82c6.627 0 11.91-5.283 11.91-11.91 0-3.18-1.238-6.17-3.39-8.43zM12 21.21c-1.36 0-2.695-.35-3.86-.99l-.28-.15-3.83.98.99-3.74L4.6 15.35l-.12-.2A8.06 8.06 0 0 1 3 11.91c0-4.98 4.05-9.03 9.03-9.03 2.41 0 4.68.94 6.39 2.65 1.71 1.71 2.65 3.98 2.65 6.39 0 4.98-4.05 9.03-9.03 9.03z"></path>
            </svg>
          </span>
          <span class="label">
            WhatsApp
            <small>Message me directly</small>
          </span>
        </a>
      </div>

      <p class="note">Clean • Professional • Responsive — Built for creators</p>
    </div>
  </main>

  <!-- Optional QR modal: shows if you add whatsapp_qr.png to folder -->
  <div id="qrModal" class="qr-modal" role="dialog" aria-hidden="true" aria-labelledby="qrTitle" tabindex="-1">
    <div class="qr-card" role="document">
      <h3 id="qrTitle" style="margin:6px 0 10px;color:var(--text);font-size:16px">WhatsApp QR</h3>
      <img id="qrImage" src="whatsapp_qr.png" alt="WhatsApp QR code" onerror="this.style.display='none'">
      <p style="color:var(--muted);font-size:13px;margin:6px 0 0">Scan to open chat</p>
      <div style="margin-top:12px;">
        <button onclick="closeQR()" style="padding:8px 12px;border-radius:10px;border:none;background:rgba(255,255,255,0.04);color:var(--text);cursor:pointer">Close</button>
      </div>
    </div>
  </div>

  <script>
    // Accessible focus ring on keyboard navigation
    (function(){
      function handleFirstTab(e){
        if(e.key === 'Tab'){
          document.body.classList.add('user-is-tabbing');
          window.removeEventListener('keydown', handleFirstTab);
        }
      }
      window.addEventListener('keydown', handleFirstTab);
    })();

    // WhatsApp QR modal behavior:
    // If whatsapp_qr.png exists in folder, clicking the WhatsApp button will open QR modal first on desktop,
    // but keep the normal 'open link' behavior for mobile (small screens) to keep UX consistent.
    const whatsappBtn = document.getElementById('whatsappBtn');
    const qrModal = document.getElementById('qrModal');
    const qrImage = document.getElementById('qrImage');

    function isSmallScreen(){
      return window.matchMedia("(max-width:640px)").matches;
    }

    // Check if QR image loaded successfully (exists)
    qrImage.addEventListener('error', () => { qrImage.dataset.exists = "false"; });
    qrImage.addEventListener('load', () => { qrImage.dataset.exists = "true"; });

    // On click, if QR exists and on desktop, show modal; otherwise go straight to wa.me
    whatsappBtn.addEventListener('click', function(e){
      const qrExists = qrImage.complete && qrImage.naturalWidth !== 0;
      if(qrExists && !isSmallScreen()){
        // prevent opening new tab and show modal
        e.preventDefault();
        openQR();
      } else {
        // no QR or small screen: allow default navigation (open wa.me)
      }
    });

    function openQR(){
      qrModal.classList.add('open');
      qrModal.setAttribute('aria-hidden','false');
      // trap focus briefly
      qrModal.querySelector('button')?.focus();
    }
    function closeQR(){
      qrModal.classList.remove('open');
      qrModal.setAttribute('aria-hidden','true');
      whatsappBtn.focus();
    }
    // close modal when clicking overlay
    qrModal.addEventListener('click', (ev)=>{
      if(ev.target === qrModal) closeQR();
    });

    // small nicety: animate entry
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelector('.card').style.opacity = 0;
      document.querySelector('.card').style.transform = 'translateY(10px)';
      setTimeout(()=> {
        const c = document.querySelector('.card');
        c.style.transition = 'opacity .6s ease, transform .6s cubic-bezier(.2,.9,.2,1)';
        c.style.opacity = 1;
        c.style.transform = 'translateY(0)';
      },80);
    });

  </script>
</body>
</html>
