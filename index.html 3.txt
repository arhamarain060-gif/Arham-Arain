<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>YourGoatViper | Links</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    /* ===== Global Styles ===== */
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(-45deg, #6a11cb, #2575fc, #6a11cb, #2575fc);
      background-size: 400% 400%;
      animation: gradientBG 10s ease infinite;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }

    @keyframes gradientBG {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    h1 {
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .card {
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(20px);
      border-radius: 20px;
      padding: 40px 30px;
      text-align: center;
      box-shadow: 0 8px 32px rgba(0,0,0,0.2);
      width: 90%;
      max-width: 400px;
      margin-top: 30px;
    }

    /* ===== Logo ===== */
    .logo {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      border: 3px solid rgba(255,255,255,0.4);
      overflow: hidden;
      margin: 0 auto 20px;
      box-shadow: 0 0 20px rgba(255,255,255,0.2);
      transition: all 0.4s ease;
    }

    .logo:hover {
      transform: scale(1.08);
      box-shadow: 0 0 30px rgba(255,255,255,0.5);
    }

    .logo img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    /* ===== Buttons ===== */
    .link-btn {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 14px 20px;
      margin: 12px 0;
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.12);
      color: #fff;
      text-decoration: none;
      font-weight: 500;
      transition: all 0.3s ease;
    }

    .link-btn:hover {
      background: rgba(255, 255, 255, 0.25);
      transform: translateY(-3px);
    }

    .link-btn i {
      font-size: 1.3rem;
    }

    .footer {
      margin-top: 15px;
      font-size: 0.8rem;
      opacity: 0.8;
    }

  </style>

  <!-- Font Awesome for icons -->
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
</head>

<body>

  <!-- Logo -->
  <div class="logo">
    <img src="logo.png" alt="YourGoatViper Logo">
  </div>

  <!-- Card -->
  <div class="card">
    <h1>YourGoatViper</h1>
    <p>Creator — Connect with me</p>
    <hr style="border: 1px solid rgba(255,255,255,0.2); margin: 15px 0;">

    <a href="https://www.tiktok.com/@yourgoatviper?_t=ZS-90S15LBVKrM&_r=1" target="_blank" class="link-btn">
      <span><i class="fab fa-tiktok"></i> TikTok</span>
      <span>@yourgoatviper</span>
    </a>

    <a href="https://www.youtube.com/@YourGoatViper" target="_blank" class="link-btn">
      <span><i class="fab fa-youtube"></i> YouTube</span>
      <span>@YourGoatViper</span>
    </a>

    <a href="https://www.instagram.com/arham_arain333?igsh=NGhobDk1c29rd3oy&utm_source=qr" target="_blank" class="link-btn">
      <span><i class="fab fa-instagram"></i> Instagram</span>
      <span>@arham_arain333</span>
    </a>

    <a href="https://wa.me/923348666640" target="_blank" class="link-btn">
      <span><i class="fab fa-whatsapp"></i> WhatsApp</span>
      <span>Message me</span>
    </a>

    <p class="footer">Clean • Professional • Built for creators 🚀</p>
  </div>

</body>
</html>
