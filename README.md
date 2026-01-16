<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For Morenikeji 💖</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff4d6d, #ff8fab);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      text-align: center;
      overflow: hidden;
    }

    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.8);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 10;
    }

    .overlay button {
      padding: 20px 40px;
      font-size: 1.3em;
      border-radius: 40px;
      border: none;
      cursor: pointer;
      color: #ff4d6d;
    }

    .card {
      background: rgba(255,255,255,0.15);
      padding: 35px;
      border-radius: 25px;
      max-width: 420px;
      box-shadow: 0 15px 40px rgba(0,0,0,0.3);
      animation: float 4s ease-in-out infinite;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0); }
    }

    button {
      background: white;
      color: #ff4d6d;
      border: none;
      padding: 15px 32px;
      font-size: 1.1em;
      border-radius: 40px;
      cursor: pointer;
      margin: 10px;
      transition: 0.3s;
    }

    #noBtn {
      position: absolute;
    }

    #yesMessage {
      display: none;
      font-size: 1.4em;
      margin-top: 25px;
    }

    .countdown {
      margin: 15px 0;
      font-size: 1.1em;
    }

    .hearts span {
      position: fixed;
      top: -10px;
      font-size: 20px;
      animation: fall 6s linear infinite;
      opacity: 0.7;
    }

    @keyframes fall {
      to { transform: translateY(110vh); }
    }
  </style>
</head>
<body>

<!-- Intro Screen -->
<div class="overlay" id="intro">
  <button onclick="enterSite()">For Morenikeji only 💝</button>
</div>

<!-- Music -->
<audio id="music" loop>
  <source src="my-heart-asake.mp3" type="audio/mpeg">
</audio>

<!-- Hearts -->
<div class="hearts">
  <span style="left:10%">❤️</span>
  <span style="left:30%">💖</span>
  <span style="left:50%">💕</span>
  <span style="left:70%">💘</span>
  <span style="left:90%">❤️</span>
</div>

<div class="card">
  <h1>Morenikeji 💕</h1>

  <p>
    Loving you feels effortless.<br>
    You’re my calm, my joy, my favorite miracle.<br><br>
    Every beat of my heart whispers your name ❤️
  </p>

  <div class="countdown" id="countdown"></div>

  <h2>Will you be my Valentine?</h2>

  <button onclick="sayYes()">YES 💖</button>
  <button id="noBtn" onmouseover="runAway()">NO 🙈</button>

  <div id="yesMessage">
    Yessss!! 🎉💘<br>
    You chose me and I choose you every time.<br><br>
    Happy Valentine’s Day ❤️<br>
    — Love, David 💌
  </div>
</div>

<script>
  function enterSite() {
    document.getElementById("intro").style.display = "none";
    document.getElementById("music").play();
    alert("David is smiling right now 😊");
  }

  function runAway() {
    const btn = document.getElementById("noBtn");
    btn.style.top = Math.random() * 80 + "%";
    btn.style.left = Math.random() * 80 + "%";
  }

  function sayYes() {
    localStorage.setItem("valentineYes", "true");
    document.getElementById("yesMessage").style.display = "block";
  }

  if (localStorage.getItem("valentineYes")) {
    document.getElementById("yesMessage").style.display = "block";
  }

  // Countdown
  const valDate = new Date("Feb 14, 2026 00:00:00").getTime();
  setInterval(() => {
    const now = new Date().getTime();
    const diff = valDate - now;
    if (diff > 0) {
      const d = Math.floor(diff / (1000 * 60 * 60 * 24));
      const h = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const m = Math.floor((diff / (1000 * 60)) % 60);
      document.getElementById("countdown").innerHTML =
        `⏳ Valentine’s Day in ${d}d ${h}h ${m}m`;
    }
  }, 1000);
</script>

</body>
</html>
