<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Yashasvibe — Portfolio</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600;700&family=Inter:wght@300;400;500;700;800&display=swap" rel="stylesheet">

  <style>

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      scroll-behavior:smooth;
    }

    body{
      background:#050505;
      color:white;
      font-family:'Inter',sans-serif;
      overflow-x:hidden;
      cursor:none;
    }

    body::before{
      content:"";
      position:fixed;
      inset:0;
      background:
      radial-gradient(circle at top,#7a0000 0%,transparent 40%),
      radial-gradient(circle at bottom,#300000 0%,transparent 40%);
      opacity:.8;
      z-index:-2;
    }

    body::after{
      content:"";
      position:fixed;
      inset:0;
      background:url('https://www.transparenttextures.com/patterns/asfalt-dark.png');
      opacity:.15;
      z-index:-1;
    }

    .cursor{
      width:20px;
      height:20px;
      border:1px solid white;
      border-radius:50%;
      position:fixed;
      transform:translate(-50%,-50%);
      pointer-events:none;
      z-index:9999;
      mix-blend-mode:difference;
    }

    .container{
      display:flex;
    }

    .sidebar{
      width:120px;
      height:100vh;
      border-right:1px solid rgba(255,255,255,.08);
      padding:30px 20px;
      position:fixed;
      left:0;
      top:0;
      background:rgba(0,0,0,.6);
      backdrop-filter:blur(20px);
    }

    .logo{
      font-size:2rem;
      color:#ff2d2d;
      font-weight:800;
      margin-bottom:5px;
    }

    .logo-small{
      font-size:.8rem;
      color:#fff;
      margin-bottom:50px;
    }

    .nav{
      display:flex;
      flex-direction:column;
      gap:20px;
    }

    .nav a{
      color:#ddd;
      text-decoration:none;
      font-size:.85rem;
      transition:.3s;
    }

    .nav a:hover{
      color:#ff3b3b;
      transform:translateX(5px);
    }

    .main{
      margin-left:120px;
      width:calc(100% - 120px);
      padding:40px;
    }

    .hero{
      min-height:100vh;
      position:relative;
      display:flex;
      align-items:center;
      overflow:hidden;
    }

    .portfolio-bg{
      position:absolute;
      top:-20px;
      left:0;
      font-size:15vw;
      font-family:'Cormorant Garamond',serif;
      color:rgba(255,0,0,.25);
      z-index:0;
      line-height:.8;
    }

    .hero-content{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:40px;
      align-items:center;
      width:100%;
      position:relative;
      z-index:2;
    }

    .left h1{
      font-size:6rem;
      line-height:.9;
      margin-bottom:20px;
      color:#fff;
      font-weight:800;
    }

    .left .stack{
      font-size:5rem;
      font-weight:800;
      line-height:.9;
      margin-bottom:25px;
    }

    .left p{
      max-width:500px;
      color:#d6d6d6;
      line-height:1.8;
      margin-bottom:30px;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      gap:10px;
      background:#b40000;
      padding:15px 28px;
      border-radius:999px;
      color:white;
      text-decoration:none;
      border:1px solid rgba(255,255,255,.1);
      transition:.3s;
    }

    .btn:hover{
      transform:translateY(-5px);
      background:#d30000;
    }

    .hero-image{
      position:relative;
      display:flex;
      justify-content:center;
      align-items:center;
    }

    .hero-image img{
      width:100%;
      max-width:650px;
      object-fit:contain;
      filter:drop-shadow(0 20px 80px rgba(255,0,0,.35));
    }

    .side-character{
      position:absolute;
      right:-40px;
      bottom:0;
      width:260px;
      z-index:3;
    }

    .section{
      margin-top:80px;
      padding:40px;
      border:1px solid rgba(255,255,255,.08);
      border-radius:30px;
      background:rgba(255,255,255,.03);
      backdrop-filter:blur(20px);
    }

    .section-title{
      font-size:2.2rem;
      margin-bottom:30px;
      color:#ff4040;
      font-weight:800;
    }

    .cards{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
      gap:25px;
    }

    .card{
      background:#0e0e0e;
      border:1px solid rgba(255,255,255,.06);
      border-radius:25px;
      overflow:hidden;
      transition:.4s;
    }

    .card:hover{
      transform:translateY(-8px);
      border-color:#ff2d2d;
    }

    .card img{
      width:100%;
      height:220px;
      object-fit:cover;
    }

    .card-content{
      padding:25px;
    }

    .card h3{
      margin-bottom:10px;
      font-size:1.5rem;
    }

    .card p{
      color:#ccc;
      line-height:1.7;
      font-size:.95rem;
    }

    .skills{
      display:grid;
      grid-template-columns:1fr 120px;
      gap:15px;
    }

    .skill{
      padding:15px;
      border-bottom:1px solid rgba(255,255,255,.06);
    }

    .contact-box{
      margin-top:40px;
      padding:35px;
      border-radius:30px;
      background:linear-gradient(135deg,#220000,#090909);
      border:1px solid rgba(255,255,255,.08);
    }

    .contact-box h2{
      font-size:3rem;
      margin-bottom:20px;
    }

    .email{
      font-size:1.2rem;
      margin-bottom:25px;
      color:#ffb3b3;
    }

    footer{
      margin-top:100px;
      text-align:center;
      padding:60px 0;
      color:#ddd;
    }

    footer h2{
      font-size:4rem;
      line-height:1;
      margin-bottom:20px;
      font-family:'Cormorant Garamond',serif;
    }

    .socials{
      display:flex;
      gap:20px;
      flex-wrap:wrap;
      margin-top:30px;
    }

    .socials a{
      color:white;
      text-decoration:none;
      padding:14px 20px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.08);
      transition:.3s;
    }

    .socials a:hover{
      background:#b40000;
    }

    @media(max-width:1100px){

      .hero-content{
        grid-template-columns:1fr;
      }

      .side-character{
        display:none;
      }

      .left h1{
        font-size:4rem;
      }

      .left .stack{
        font-size:3rem;
      }

      .sidebar{
        display:none;
      }

      .main{
        margin-left:0;
        width:100%;
        padding:20px;
      }

      body{
        cursor:auto;
      }

      .cursor{
        display:none;
      }

    }

  </style>
</head>

<body>

<div class="cursor"></div>

<div class="container">

  <aside class="sidebar">

    <div class="logo">YV</div>
    <div class="logo-small">by Yashasvi</div>

    <nav class="nav">
      <a href="#about">ABOUT</a>
      <a href="#campaigns">CAMPAIGNS</a>
      <a href="#workflows">WORKFLOWS</a>
      <a href="#skills">SKILLS</a>
      <a href="#content">CONTENT</a>
      <a href="#contact">CONTACT</a>
    </nav>

  </aside>

  <main class="main">

    <section class="hero">

      <div class="portfolio-bg">Portfolio</div>

      <div class="hero-content">

        <div class="left">

          <h1>Yashasvibe</h1>

          <div class="stack">
            UI<br>
            UGC TECH
          </div>

          <p>
            UGC creator, founder, and visual storyteller building cinematic content,
            emotional interfaces, aesthetic-first campaigns, and digital experiences
            inspired by fashion, technology, and internet culture.
          </p>

          <a href="#campaigns" class="btn">
            View Portfolio →
          </a>

        </div>

        <div class="hero-image">

          <!-- MAIN FACE -->
          <img src="YOUR_3D_FACE_IMAGE.png" alt="3D portrait">

          <!-- SIDE FULL BODY -->
          <img class="side-character" src="YOUR_FULL_BODY_IMAGE.png" alt="Yashasvi">

        </div>

      </div>

    </section>

    <section class="section" id="about">

      <div class="section-title">About Me</div>

      <p style="line-height:2;color:#ddd;font-size:1.05rem;">
        I create cinematic internet experiences blending storytelling,
        luxury aesthetics, UGC strategy, and emotional branding.
        My work explores the intersection of creator culture,
        AI tools, futuristic interfaces, and immersive visual identities.
      </p>

    </section>

    <section class="section" id="campaigns">

      <div class="section-title">UGC + Brand Campaigns</div>

      <div class="cards">

        <a class="card" href="https://clove.created.app/account/signin">

          <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=1200&auto=format&fit=crop">

          <div class="card-content">
            <h3>Lovable AI</h3>
            <p>UGC creator campaign visuals and emotional branding systems.</p>
          </div>

        </a>

        <div class="card">

          <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop">

          <div class="card-content">
            <h3>Poppy AI</h3>
            <p>Experimental AI aesthetic storytelling and creator-focused visuals.</p>
          </div>

        </div>

        <div class="card">

          <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=1200&auto=format&fit=crop">

          <div class="card-content">
            <h3>Picsart</h3>
            <p>Creative visual concepts and aesthetic content direction.</p>
          </div>

        </div>

      </div>

    </section>

    <section class="section" id="workflows">

      <div class="section-title">Creative Workflows</div>

      <div class="cards">

        <a class="card" href="https://www.morphic.com/en/workflows/019dcaad-49cb-74cc-a990-6da92ec7fa27/clove-caf-emotion-scene">

          <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?q=80&w=1200&auto=format&fit=crop">

          <div class="card-content">
            <h3>C.Love Café Emotion Scene</h3>
            <p>Morphic workflow concept for cinematic storytelling.</p>
          </div>

        </a>

        <a class="card" href="https://app.fuser.studio/view/878a7c66-2e24-49b5-bf1a-347b8b12aadd">

          <img src="https://images.unsplash.com/photo-1516321497487-e288fb19713f?q=80&w=1200&auto=format&fit=crop">

          <div class="card-content">
            <h3>Fuser Studio Concept</h3>
            <p>Experimental AI interface and futuristic creator workflow.</p>
          </div>

        </a>

      </div>

    </section>

    <section class="section" id="skills">

      <div class="section-title">Skills & Software</div>

      <div class="skills">

        <div class="skill">Photoshop</div><div class="skill">9.5/10</div>
        <div class="skill">After Effects</div><div class="skill">9/10</div>
        <div class="skill">Premiere Pro</div><div class="skill">8.5/10</div>
        <div class="skill">Poppy AI</div><div class="skill">9/10</div>
        <div class="skill">Lovable AI</div><div class="skill">9.5/10</div>
        <div class="skill">UGC Storytelling</div><div class="skill">9.8/10</div>

      </div>

    </section>

    <section class="section" id="content">

      <div class="section-title">Content Showcase</div>

      <div class="socials">

        <a href="https://www.instagram.com/p/DYMv_2AsijG/?utm_source=ig_web_copy_link&igsh=MzRlODBiNWFlZA==">Instagram Post</a>

        <a href="https://www.instagram.com/reel/DX6t6_qo99P/?utm_source=ig_web_copy_link&igsh=MzRlODBiNWFlZA==">Reel 1</a>

        <a href="https://www.instagram.com/reel/DXe5JqMiDn7/?utm_source=ig_web_copy_link&igsh=MzRlODBiNWFlZA==">Reel 2</a>

        <a href="https://www.instagram.com/reel/DYLrZnIM-HV/?utm_source=ig_web_copy_link&igsh=MzRlODBiNWFlZA==">Reel 3</a>

      </div>

    </section>

    <section class="contact-box" id="contact">

      <h2>Let's Work Together</h2>

      <div class="email">
        ugcyashasvi@gmail.com
      </div>

      <a href="mailto:ugcyashasvi@gmail.com" class="btn">
        let's build Thing how u wish existed
      </a>

      <div class="socials">

        <a href="https://www.instagram.com/yashasvibe/">Instagram</a>

        <a href="https://www.linkedin.com/in/yashasvisoni">LinkedIn</a>

        <a href="https://x.com/yashasvibe">Twitter/X</a>

        <a href="https://www.youtube.com/@yashasvibe">YouTube</a>

        <a href="https://www.tiktok.com/@yashasvibe">TikTok</a>

      </div>

    </section>

    <footer>

      <h2>
        Building and creating<br>
        what I wish existed.
      </h2>

    </footer>

  </main>

</div>

<script>

const cursor = document.querySelector(".cursor");

document.addEventListener("mousemove",(e)=>{

  cursor.style.left = e.clientX + "px";
  cursor.style.top = e.clientY + "px";

});

</script>

</body>
</html>
