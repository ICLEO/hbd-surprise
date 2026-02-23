<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Happy Birthday, Husband! 🎂</title>
<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --pink: #ff6b9d;
    --soft-pink: #ffc2d4;
    --peach: #ffb347;
    --cream: #fff8f0;
    --deep: #3d1c5a;
    --purple: #a855f7;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

  html, body {
    width: 100%;
    height: 100%;
    overflow: hidden;
    touch-action: none;
  }

  body {
    font-family: 'Nunito', sans-serif;
    background: var(--cream);
    min-height: 100dvh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }

  /* Animated background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: 
      radial-gradient(ellipse at 20% 50%, #ffe0f0 0%, transparent 60%),
      radial-gradient(ellipse at 80% 20%, #ffecd2 0%, transparent 50%),
      radial-gradient(ellipse at 60% 80%, #e0d4ff 0%, transparent 50%);
    z-index: 0;
  }

  /* Floating hearts */
  .hearts-bg {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
  }

  .heart-float {
    position: absolute;
    animation: floatUp linear infinite;
    opacity: 0.45;
  }

  @keyframes floatUp {
    0% { transform: translateY(110vh) rotate(0deg); opacity: 0; }
    10% { opacity: 0.45; }
    90% { opacity: 0.45; }
    100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
  }

  /* Main card */
  .card {
    position: relative;
    z-index: 10;
    background: rgba(255,255,255,0.88);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-radius: 40px;
    padding: 2.2rem 1.8rem 2rem;
    width: 88%;
    max-width: 360px;
    text-align: center;
    box-shadow: 
      0 8px 40px rgba(255,107,157,0.25),
      0 0 0 1.5px rgba(255,107,157,0.2);
    animation: cardIn 0.8s cubic-bezier(0.34, 1.56, 0.64, 1) both;
  }

  @keyframes cardIn {
    from { transform: scale(0.7) translateY(40px); opacity: 0; }
    to { transform: scale(1) translateY(0); opacity: 1; }
  }

  .emoji-top {
    font-size: 3.2rem;
    animation: bounce 1.5s ease-in-out infinite;
    display: block;
    margin-bottom: 0.4rem;
    line-height: 1;
  }

  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  h1 {
    font-family: 'Pacifico', cursive;
    font-size: 1.9rem;
    color: var(--pink);
    margin-bottom: 0.4rem;
    text-shadow: 2px 2px 0 rgba(255,107,157,0.15);
  }

  .subtitle {
    font-size: 2rem;
    color: #9c6b8a;
    font-weight: 600;
    margin-bottom: 2rem;
    line-height: 1.6;
  }

  .question-text {
    font-size: 1.20rem;
    font-weight: 800;
    color: var(--deep);
    margin-bottom: 0.4rem;
    line-height: 1.4;
  }

  .question-sub {
    font-size: 1.05rem;
    color: #b08aa0;
    margin-bottom: 1.6rem;
    font-style: italic;
  }

  /* Button container - fixed zone on screen */
  .btn-zone {
    position: relative;
    height: 160px;
    margin: 0 -1rem;
  }

  .btn {
    font-family: 'Nunito', sans-serif;
    font-size: 1.5rem;
    font-weight: 800;
    padding: 0.7rem 1.8rem;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    letter-spacing: 0.03em;
    position: absolute;
    white-space: nowrap;
    user-select: none;
    -webkit-user-select: none;
    transition: transform 0.12s;
  }

  .btn:active { transform: scale(0.94); }

  .btn-yes {
    background: linear-gradient(135deg, var(--pink), #ff4d8d);
    color: white;
    box-shadow: 0 4px 20px rgba(255,107,157,0.5);
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
  }

  .btn-yes:active { transform: translate(-50%, -50%) scale(0.50); }

  .btn-no {
    background: white;
    color: var(--pink);
    border: 2.5px solid var(--soft-pink);
    box-shadow: 0 2px 10px rgba(255,107,157,0.15);
    /* starts near YES */
    left: 60%;
    top: 55%;
    z-index: 1;
    transition: left 0.22s cubic-bezier(0.25, 0.46, 0.45, 0.94), top 0.22s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }

  /* Tease message */
  .tease-msg {
    font-size: 0.82rem;
    color: var(--purple);
    font-weight: 700;
    margin-top: 0.6rem;
    min-height: 1.2em;
    font-style: italic;
    animation: fadeIn 0.3s ease;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(4px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .escape-count {
    font-size: 0.72rem;
    color: var(--peach);
    font-weight: 800;
    margin-top: 0.3rem;
    min-height: 1em;
  }

  /* Celebration */
  .celebration { display: none; }
  .celebration.show {
    display: block;
    animation: cardIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) both;
  }
  .question-section.hide { display: none; }

  .celebrate-emoji {
    font-size: 2.8rem;
    display: block;
    margin-bottom: 1rem;
    animation: spinIn 0.6s ease both;
  }

  @keyframes spinIn {
    from { transform: rotate(-20deg) scale(0); opacity: 0; }
    to { transform: rotate(0deg) scale(1); opacity: 1; }
  }

  .celebrate-title {
    font-family: 'Pacifico', cursive;
    font-size: 1.6rem;
    color: var(--pink);
    margin-bottom: 0.75rem;
  }

  .celebrate-msg {
    font-size: 0.95rem;
    color: var(--deep);
    font-weight: 600;
    line-height: 1.75;
    margin-bottom: 1.4rem;
  }

  .confetti-strip {
    font-size: 1.6rem;
    letter-spacing: 0.15em;
    animation: wiggle 1s ease-in-out infinite;
  }

  @keyframes wiggle {
    0%, 100% { transform: rotate(-3deg); }
    50% { transform: rotate(3deg); }
  }

  /* Sad popup overlay */
  .sad-overlay {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 100;
    background: rgba(61, 28, 90, 0.45);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    align-items: center;
    justify-content: center;
  }
  .sad-overlay.show {
    display: flex;
    animation: fadeIn 0.3s ease;
  }
  .sad-popup {
    background: white;
    border-radius: 24px;
    padding: 2rem 1.8rem;
    width: 82%;
    max-width: 320px;
    text-align: center;
    box-shadow: 0 12px 40px rgba(0,0,0,0.2);
    animation: cardIn 0.4s cubic-bezier(0.34, 1.56, 0.64, 1) both;
  }
  .sad-popup .sad-emoji {
    font-size: 3rem;
    display: block;
    margin-bottom: 0.6rem;
    animation: sadShake 0.5s ease;
  }
  @keyframes sadShake {
    0%, 100% { transform: rotate(0deg); }
    20% { transform: rotate(-10deg); }
    40% { transform: rotate(10deg); }
    60% { transform: rotate(-8deg); }
    80% { transform: rotate(8deg); }
  }
  .sad-popup h3 {
    font-family: 'Pacifico', cursive;
    font-size: 1.3rem;
    color: var(--deep);
    margin-bottom: 0.6rem;
  }
  .sad-popup p {
    font-size: 0.9rem;
    color: #9c6b8a;
    font-weight: 600;
    line-height: 1.65;
    margin-bottom: 1.3rem;
  }
  .sad-close {
    font-family: 'Nunito', sans-serif;
    font-size: 0.95rem;
    font-weight: 800;
    padding: 0.65rem 1.8rem;
    background: linear-gradient(135deg, var(--pink), #ff4d8d);
    color: white;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 4px 16px rgba(255,107,157,0.4);
  }

  /* Confetti pieces */
  .confetti-piece {
    position: fixed;
    pointer-events: none;
    z-index: 999;
    border-radius: 2px;
    animation: confettiFall linear forwards;
  }

  @keyframes confettiFall {
    0% { transform: translateY(0) rotate(0deg); opacity: 1; }
    100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
  }
</style>
</head>
<body>

<div class="hearts-bg" id="heartsContainer"></div>

<div class="card">
  <span class="emoji-top">🎂</span>
  <h1>My Sweet Husband!</h1>

  <div class="question-section" id="questionSection">
    <p class="question-text">Do you feel extra lucky today? 🍀</p>
    <p class="question-sub">...to have a wife as amazing as me? 😇</p>

    <div class="btn-zone" id="btnZone">
      <button class="btn btn-yes" id="yesBtn" onclick="pressYes()">YES!!! 😍</button>
      <button class="btn btn-no" id="noBtn">No...?</button>
    </div>

    <div class="tease-msg" id="teaseMsg"></div>
  </div>

  <div class="celebration" id="celebration">
    <p class="celebrate-msg">
      Happy Birthday, my love!! 🎉<br><br>
      Happy birthday to my man who still gives me butterflies every time, who still makes me laugh until my stomach hurts and my eyes fill with tears, and who still chooses me — every single day — without hesitation. You have no idea how much that means to me.<br><br>
      Life has never been perfect, but it has always been worth it. Through every season, every challenge, every quiet night, and every loud argument, you have shown me what real love looks like. Not the kind from movies, but the kind that shows up — steady, patient, and true.💕<br><br>
      I am so proud of you. So grateful for the life we have built together. And so deeply, endlessly in love with you.
I am the luckiest woman in the world — not because everything is easy, but because I get to do all of it with you.<br><br>Here's to another year of laughing loud, loving deeply, and growing old together — and I wouldn't change a single thing. 🌸
    </p>
    <div class="confetti-strip">🎊 💕 🎁 🎂 💓 ♥️ 🎊</div>
  </div>
</div>

<!-- Sad popup -->
<div class="sad-overlay" id="sadOverlay">
  <div class="sad-popup">
    <span class="sad-emoji">😢</span>
    <h3>You clicked NO?!😭</h3>
    <p>
      I'm so sad when you click NO...<br><br>
      After everything I do for you?<br>
      The cooking... the cuddles...<br>
      the bj to made you sleep well?? 😭💔<br><br>
      <em>Please reconsider.</em> 🥺
    </p>
    <button class="sad-close" onclick="closeSad()">CLICK YES NOW!! 😈</button>
  </div>
</div>

<script>
  // Floating hearts
  const heartsContainer = document.getElementById('heartsContainer');
  const emojis = ['💕','💗','💖','🌸','✨','💝','🎀','💓'];
  for (let i = 0; i < 14; i++) {
    const h = document.createElement('div');
    h.className = 'heart-float';
    h.textContent = emojis[Math.floor(Math.random() * emojis.length)];
    h.style.left = Math.random() * 100 + 'vw';
    h.style.fontSize = (0.9 + Math.random() * 1.2) + 'rem';
    h.style.animationDuration = (7 + Math.random() * 9) + 's';
    h.style.animationDelay = (Math.random() * 12) + 's';
    heartsContainer.appendChild(h);
  }

  // NO button logic — moves within btn-zone on touch
  let noCount = 0;
  const noBtn = document.getElementById('noBtn');
  const btnZone = document.getElementById('btnZone');

  const teaseMsgs = [
    "Nice try! 😜",
    "Nope, not today! 🏃",
    "It knows the truth! 💅",
    "Running away! 😂",
    "You can't escape! 🤭",
    "My love is faster! 💨",
    "Give up yet? 😏",
    "Just press YES!! 😤",
    "Seriously... YES is right there! 👆",
    "Really? NO? 😭",
  ];

  function moveNoBtn() {
    noCount++;
    const zone = btnZone.getBoundingClientRect();
    const btnW = noBtn.offsetWidth;
    const btnH = noBtn.offsetHeight;
    const yesBtn = document.getElementById('yesBtn');
    const yesRect = yesBtn.getBoundingClientRect();
    const yesCX = yesRect.left - zone.left + yesRect.width / 2;
    const yesCY = yesRect.top - zone.top + yesRect.height / 2;

    // Pick position far from YES button (minimum distance enforced)
    let x, y, attempts = 0;
    const minDist = zone.width * 0.42;
    do {
      x = Math.random() * (zone.width - btnW);
      y = Math.random() * (zone.height - btnH);
      const dx = (x + btnW / 2) - yesCX;
      const dy = (y + btnH / 2) - yesCY;
      const dist = Math.sqrt(dx * dx + dy * dy);
      attempts++;
      if (dist >= minDist) break;
    } while (attempts < 30);

    noBtn.style.left = x + 'px';
    noBtn.style.top = y + 'px';

    const msg = teaseMsgs[Math.min(noCount - 1, teaseMsgs.length - 1)];
    const teaseEl = document.getElementById('teaseMsg');
    teaseEl.textContent = msg;
    teaseEl.style.animation = 'none';
    void teaseEl.offsetWidth;
    teaseEl.style.animation = 'fadeIn 0.3s ease';
  }

  // Touch and mouse events — move away on hover/touch
  noBtn.addEventListener('touchstart', (e) => { e.preventDefault(); moveNoBtn(); }, { passive: false });
  noBtn.addEventListener('mouseenter', moveNoBtn);
  // If somehow clicked (slow reaction), show sad popup
  noBtn.addEventListener('click', () => {
    document.getElementById('sadOverlay').classList.add('show');
  });

  function closeSad() {
    document.getElementById('sadOverlay').classList.remove('show');
    pressYes();
  }

  function pressYes() {
    launchConfetti();
    document.getElementById('questionSection').classList.add('hide');
    document.getElementById('celebration').classList.add('show');
    noBtn.style.display = 'none';
  }

  function launchConfetti() {
    const colors = ['#ff6b9d','#ffb347','#a855f7','#34d399','#60a5fa','#fbbf24','#f87171'];
    for (let i = 0; i < 70; i++) {
      setTimeout(() => {
        const c = document.createElement('div');
        c.className = 'confetti-piece';
        c.style.left = (5 + Math.random() * 90) + 'vw';
        c.style.top = '-12px';
        c.style.background = colors[Math.floor(Math.random() * colors.length)];
        c.style.width = (5 + Math.random() * 7) + 'px';
        c.style.height = (5 + Math.random() * 7) + 'px';
        c.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
        c.style.animationDuration = (1.5 + Math.random() * 2.5) + 's';
        document.body.appendChild(c);
        setTimeout(() => c.remove(), 4500);
      }, i * 35);
    }
  }
</script>
</body>
</html>
