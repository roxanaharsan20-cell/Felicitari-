<!doctype html>
<html lang="ro">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Demo de securitate — Ai câștigat!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600&display=swap');
    *{box-sizing:border-box;margin:0;padding:0}
    body{
      font-family:'Fredoka',sans-serif;
      height:100vh;display:flex;align-items:center;justify-content:center;
      overflow:hidden;
      background-image:url("https://wallpaperchain.com/download/roblox/roblox-wallpaper-2.jpg");
      background-size:cover;
      background-position:center;
      background-repeat:no-repeat;
      transition:background-image 0.5s ease-in-out, filter 0.5s ease-in-out;
    }

    body.changed-bg{
      background-image:url("https://www.payrollmedics.com/blog/wp-content/uploads/2021/03/Depositphotos_65076917_s-2019.jpg");
      filter:brightness(0.85);
    }

    .fade-overlay{
      position:absolute;inset:0;
      background:white;
      opacity:0;
      pointer-events:none;
      transition:opacity 0.8s ease;
      z-index:30;
    }
    .fade-overlay.active{
      opacity:0.9;
    }

    .container{
      text-align:center;
      background:rgba(255,255,255,0.15);
      border-radius:20px;
      padding:40px;
      color:white;
      width:90%;
      max-width:600px;
      backdrop-filter:blur(8px);
      box-shadow:0 10px 30px rgba(0,0,0,0.3);
      position:relative;
      overflow:hidden;
      z-index:10;
      transition:opacity 0.5s ease;
    }
    .container.hidden{
      opacity:0;
      pointer-events:none;
    }

    h1{
      font-size:2.3rem;
      background:linear-gradient(90deg,#ff4d4d,#ff9900,#ffff00,#33cc33,#33cccc,#3366ff,#cc33ff);
      background-size:400%;
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      animation:rainbowText 5s linear infinite;
    }
    @keyframes rainbowText{
      0%{background-position:0%;}
      100%{background-position:100%;}
    }

    .btn{
      background:linear-gradient(90deg,#ff6a00,#ffcc00,#ff6a00);
      color:#fff;
      font-size:1.2rem;
      border:none;
      padding:14px 30px;
      border-radius:14px;
      cursor:pointer;
      margin-top:20px;
      font-weight:600;
      box-shadow:0 4px 15px rgba(255,255,255,0.3);
      animation:pulse 1.5s infinite alternate;
      transition:transform .2s;
    }
    @keyframes pulse{
      from{transform:scale(1);}
      to{transform:scale(1.08);}
    }

    .confetti{
      position:absolute;
      opacity:0.9;
      animation:fall 3s linear forwards;
    }
    @keyframes fall{
      0%{transform:translateY(0) rotate(0deg);}
      100%{transform:translateY(700px) rotate(720deg);}
    }

    .alert{
      position:absolute;inset:0;
      background:linear-gradient(180deg,rgba(0,0,0,0.9),rgba(255,0,0,0.8));
      display:flex;flex-direction:column;align-items:center;justify-content:center;
      color:white;text-align:center;
      opacity:0;pointer-events:none;
      transition:opacity 1s;
      z-index:20;
    }
    .alert.visible{opacity:1;pointer-events:auto;}

    .alert h2{
      font-size:2.2rem;
      line-height:1.3;
      background:linear-gradient(90deg,#ff0000,#ff9900,#ffff00,#ff66cc,#33ccff);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      background-size:300%;
      animation:rainbowText 3s linear infinite;
      text-align:center;
      padding:0 20px;
    }

    .info{
      background:rgba(255,255,255,0.15);
      padding:24px;
      border-radius:14px;
      margin-top:20px;
      max-width:90%;
      font-size:1.1rem;
      line-height:1.5;
    }
    .ok{
      margin-top:24px;
      background:linear-gradient(90deg,#00cc66,#33ff99,#00cc66);
      color:white;
      padding:12px 22px;border:none;border-radius:10px;
      font-weight:600;font-size:1rem;
      cursor:pointer;
      animation:pulse 1.5s infinite alternate;
    }
  </style>
</head>
<body>
  <div class="fade-overlay" id="fadeOverlay"></div>

  <div class="container" id="main">
    <h1>🎉 Felicitări! Ai câștigat un premiu misterios! 🌈</h1>
    <p>Apasă butonul pentru a-l descoperi 👇</p>
    <button class="btn" id="claimBtn">Ridică premiul</button>
  </div>

  <div class="alert" id="alertBox">
    <h2>⚠️ Ai fost păcălit! Informațiile tale secrete tocmai au fost descoperite! ⚡💥</h2>
    <div class="info">
      <p>⚠️ <strong>Este doar o demonstrație!</strong></p>
      <p>Aceasta este o lecție despre siguranța online 🌐🛡️:</p>
      <ul style="text-align:left;margin-top:10px;font-size:1.2rem;line-height:1.6;">
        <li>❌ Nu deschide linkuri care promit premii miraculoase 🎁✨.</li>
        <li>🔑 Nu introduce parola după un link necunoscut 🔒.</li>
        <li>👨‍👩‍👧 Întreabă un adult dacă nu ești sigur 🧑‍🏫👩‍🏫.</li>
      </ul>
    </div>
    <button class="ok" id="okBtn">Am înțeles ✅</button>
  </div>

  <script>
    const claimBtn = document.getElementById('claimBtn');
    const alertBox = document.getElementById('alertBox');
    const okBtn = document.getElementById('okBtn');
    const mainContainer = document.getElementById('main');
    const fadeOverlay = document.getElementById('fadeOverlay');

    function launchConfetti(){
      for(let i=0;i<200;i++){
        const conf = document.createElement('div');
        conf.className='confetti';
        conf.style.left = Math.random() * window.innerWidth + 'px';
        conf.style.width = 12 + Math.random() * 8 + 'px';
        conf.style.height = 12 + Math.random() * 8 + 'px';
        conf.style.backgroundColor = `hsl(${Math.random()*360}, 100%, 60%)`;
        const rotate = Math.random()*360;
        conf.style.transform = `rotate(${rotate}deg)`;
        conf.style.animationDuration = (2 + Math.random()*2) + 's';
        conf.style.borderRadius = Math.random() < 0.5 ? '50%' : '20%';
        document.body.appendChild(conf);
        setTimeout(()=>conf.remove(), 4000);
      }
    }

    claimBtn.addEventListener('click', () => {
      fadeOverlay.classList.add('active');
      launchConfetti();

      setTimeout(()=>{
        mainContainer.classList.add('hidden');
        document.body.classList.add('changed-bg');
        alertBox.classList.add('visible');
        fadeOverlay.classList.remove('active');
      }, 800);
    });

    okBtn.addEventListener('click', () => {
      alertBox.classList.remove('visible');
      mainContainer.classList.remove('hidden');
      document.body.classList.remove('changed-bg');
    });
  </script>
</body>
</html>
