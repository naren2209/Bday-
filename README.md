<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Chotu ❤️</title>
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Fredoka:wght@400;600&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; user-select: none; }
    body {
      background-color: #fce4ec;
      background-image: repeating-linear-gradient(45deg, #f8bbd0 0, #f8bbd0 20px, #fce4ec 20px, #fce4ec 40px);
      font-family: 'Nunito', sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 15px;
    }
    .container {
      width: 100%;
      max-width: 440px;
      min-height: 560px;
      background: rgba(255, 255, 255, 0.96);
      border-radius: 28px;
      border: 4px solid #f48fb1;
      box-shadow: 0 15px 35px rgba(233, 30, 99, 0.2);
      padding: 24px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
    }
    .screen { display: none; width: 100%; flex-direction: column; align-items: center; }
    .screen.active { display: flex; animation: pop 0.3s ease; }
    @keyframes pop { from { opacity: 0; transform: scale(0.96); } to { opacity: 1; transform: scale(1); } }
    h1, h2 { font-family: 'Fredoka', cursive; color: #d81b60; margin-bottom: 12px; }
    .btn {
      background: linear-gradient(135deg, #ff4081, #f50057);
      color: white; border: none; padding: 12px 28px;
      border-radius: 25px; font-size: 1.05rem; font-weight: 700;
      cursor: pointer; box-shadow: 0 5px 15px rgba(245, 0, 87, 0.3);
      margin: 8px; transition: transform 0.15s;
    }
    .btn:active { transform: scale(0.95); }
    .btn-gray { background: #ab47bc; }
    .keypad-display {
      width: 190px; height: 42px; border: 2px dashed #f48fb1;
      border-radius: 12px; background: #fff; display: flex;
      align-items: center; justify-content: center; font-size: 1.4rem;
      letter-spacing: 6px; font-weight: bold; color: #e91e63; margin-bottom: 16px;
    }
    .keypad-grid {
      display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; width: 220px;
    }
    .key-btn {
      width: 58px; height: 58px; border-radius: 50%; border: 2px solid #f8bbd0;
      background: #fff0f5; color: #d81b60; font-size: 1.3rem; font-weight: bold;
      display: flex; align-items: center; justify-content: center; cursor: pointer;
    }
    .polaroid {
      background: #fff; padding: 10px 10px 22px 10px; border-radius: 8px;
      box-shadow: 0 8px 18px rgba(0,0,0,0.12); border: 1px solid #eee; margin-bottom: 15px;
    }
    .letter-paper {
      background: #fffdf7; border: 2px dashed #f8bbd0; border-radius: 15px;
      padding: 18px; font-family: 'Caveat', cursive; font-size: 1.35rem;
      line-height: 1.45; color: #4a154b; text-align: left; max-height: 350px;
      overflow-y: auto; margin-bottom: 15px;
    }
    .gallery-container {
      width: 100%;
      max-height: 350px;
      overflow-y: auto;
      padding-right: 4px;
      margin: 8px 0;
    }
    .gallery-container::-webkit-scrollbar {
      width: 5px;
    }
    .gallery-container::-webkit-scrollbar-thumb {
      background: #f48fb1;
      border-radius: 10px;
    }
    .scrapbook-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      width: 100%;
    }
    .scrapbook-img {
      width: 100%;
      aspect-ratio: 1 / 1;
      object-fit: cover;
      object-position: center;
      border-radius: 12px;
      border: 3px solid #fff;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.12);
      display: block;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- 1. Surprise -->
    <div class="screen active" id="s1">
      <div style="font-size: 4rem; margin-bottom: 10px;">🎁✨</div>
      <h2>DO YOU WANT A SURPRISE?? 💕</h2>
      <div>
        <button class="btn" onclick="go('s2')">YES !!</button>
        <button class="btn btn-gray" onclick="go('s-no')">NO !!</button>
      </div>
    </div>

    <!-- No screen -->
    <div class="screen" id="s-no">
      <div style="font-size: 4.5rem; margin-bottom: 10px;">😾</div>
      <h2>NOOOO!!!<br>TRY AGAIN!</h2>
      <p style="color: #666; margin-bottom: 15px;">Itni aasani se No nahi bol sakti! 😜</p>
      <button class="btn" onclick="go('s1')">&lt;&lt; BACK</button>
    </div>

    <!-- 2. Passcode -->
    <div class="screen" id="s2">
      <h2>ENTER PASSCODE 🔒</h2>
      <div class="keypad-display" id="disp">__</div>
      <div class="keypad-grid">
        <div class="key-btn" onclick="pk('1')">1</div>
        <div class="key-btn" onclick="pk('2')">2</div>
        <div class="key-btn" onclick="pk('3')">3</div>
        <div class="key-btn" onclick="pk('4')">4</div>
        <div class="key-btn" onclick="pk('5')">5</div>
        <div class="key-btn" onclick="pk('6')">6</div>
        <div class="key-btn" onclick="pk('7')">7</div>
        <div class="key-btn" onclick="pk('8')">8</div>
        <div class="key-btn" onclick="pk('9')">9</div>
        <div class="key-btn" onclick="clr()">C</div>
        <div class="key-btn" onclick="pk('0')">0</div>
        <div class="key-btn" onclick="chk()">#</div>
      </div>
      <p id="err" style="color: red; font-size: 0.85rem; margin-top: 8px; display: none;">Wrong Code! Try Again 💕</p>
    </div>

    <!-- 3. Polaroid -->
    <div class="screen" id="s3">
      <h2>HAPPY BIRTHDAY! 🎂</h2>
      <div class="polaroid" style="width: 220px;">
        <img src="https://i.ibb.co/4g7c6Prj/IMG-20251030-WA0023.jpg" style="width:100%; height:180px; object-fit:cover; border-radius:4px;">
        <p style="font-family:'Caveat'; font-size:1.2rem; color:#555; margin-top:8px;">My favorite person ✨</p>
      </div>
      <button class="btn" onclick="go('s4')">Next &gt;&gt;</button>
    </div>

    <!-- 4. Envelope -->
    <div class="screen" id="s4">
      <h2>A LETTER FOR YOU 💌</h2>
      <div style="font-size: 5rem; cursor: pointer; margin: 15px 0;" onclick="go('s5')">✉️</div>
      <p style="color: #d81b60; font-weight: bold;">Tap on the envelope to open!</p>
    </div>

    <!-- 5. Message Letter -->
    <div class="screen" id="s5">
      <h2>For Chotu ❤️</h2>
      <div class="letter-paper">
        Happy Birthday, Chotu! ❤️🎂<br><br>
        Maana main tumse din-raat ladta rehta hu, par sach bolu toh tumhe irritate karne ka maza hi alag hai... tumhara wo gusse wala chehra dekhne mein jo sukoon milta hai na, uska koi match nahi! 😜<br><br>
        Waise nautanki toh tum poori ho, aur haan, thodi si sundar bhi lag leti ho (jyada nahi, toh please abhi se khud ko koi heroine mat samajhne lagna 💅😂).<br><br>
        Lekin jo bhi ho, pyaar tumse bohot karta hu. Hamesha aise hi hasti raho aur mera dimaag khati raho.<br><br>
        Love you always, Happy Birthday! ✨🎉
      </div>
      <button class="btn" onclick="go('s6')">One More Surprise &gt;&gt;</button>
    </div>

    <!-- 6. Gallery -->
    <div class="screen" id="s6">
      <h2>MY PRETTY GIRL ✨</h2>
      <div class="gallery-container">
        <div class="scrapbook-grid">
          <img src="https://i.ibb.co/4g7c6Prj/IMG-20251030-WA0023.jpg" alt="Photo 1" class="scrapbook-img">
          <img src="https://i.ibb.co/cMRD2gC/IMG-20251002-WA0035.jpg" alt="Photo 2" class="scrapbook-img">
          <img src="https://i.ibb.co/jkwDYC8B/IMG-20250826-WA0009.jpg" alt="Photo 3" class="scrapbook-img">
          <img src="https://i.ibb.co/d4FwzjBR/IMG-20250809-WA0038.jpg" alt="Photo 4" class="scrapbook-img">
          <img src="https://i.ibb.co/tpGNyWZD/IMG-20250503-165835.jpg" alt="Photo 5" class="scrapbook-img">
          <img src="https://i.ibb.co/WWkCDvFK/IMG-20250417-190456.jpg" alt="Photo 6" class="scrapbook-img">
        </div>
      </div>
      <p style="font-family: 'Caveat'; font-size: 1.4rem; color: #d81b60; margin: 8px 0;">
        I love you, forever and always! ❤️
      </p>
      <button class="btn" onclick="go('s1')">Replay ↺</button>
    </div>
  </div>

  <script>
    let code = "";
    const target = "301099";
    function go(id) {
      document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }
    function pk(n) {
      if (code.length < 6) {
        code += n;
        upd();
        if (code.length === 6) setTimeout(chk, 200);
      }
    }
    function clr() { code = ""; upd(); document.getElementById('err').style.display = 'none'; }
    function upd() {
      document.getElementById('disp').innerText = "•".repeat(code.length) + "_".repeat(6 - code.length);
    }
    function chk() {
      if (code === target) { go('s3'); clr(); }
      else { document.getElementById('err').style.display = 'block'; clr(); }
    }
  </script>
</body>
</html>
