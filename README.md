<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Icha I Love U 💖</title>
<style>
  /* Reset */
  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fad0c4);
    background-size: 400% 400%;
    animation: bgAnim 15s ease infinite;
  }

  @keyframes bgAnim {
    0% {background-position:0% 50%;}
    50% {background-position:100% 50%;}
    100% {background-position:0% 50%;}
  }

  .scene {
    position: relative;
    width: 100%;
    height: 100%;
  }

  /* Particles */
  .particle {
    position: absolute;
    width: 6px;
    height: 6px;
    background: rgba(255,255,255,0.7);
    border-radius: 50%;
    animation: floatUp linear infinite;
  }

  @keyframes floatUp {
    0% { transform: translateY(100vh) scale(0.5); opacity: 0; }
    50% { opacity: 1; }
    100% { transform: translateY(-10vh) scale(1); opacity:0; }
  }

  /* Flower */
  .flower {
    position: absolute;
    bottom:0;
    left:50%;
    transform: translateX(-50%) scale(0);
    width: 0;
    height: 0;
    animation: growFlower 4s forwards;
  }

  @keyframes growFlower {
    0% { transform: translateX(-50%) scale(0); }
    100% { transform: translateX(-50%) scale(1); }
  }

  .stem {
    width:4px;
    height:120px;
    background: #4caf50;
    margin:0 auto;
    border-radius:2px;
  }

  .petal {
    position:absolute;
    width:40px;
    height:60px;
    background: #ff4081;
    border-radius: 50% 50% 0 0;
    top:-60px;
    left:-18px;
    transform-origin: bottom center;
    animation: bloom 2s ease forwards;
  }

  .petal:nth-child(1) { transform: rotate(0deg); animation-delay:0s; }
  .petal:nth-child(2) { transform: rotate(72deg); animation-delay:0.2s; }
  .petal:nth-child(3) { transform: rotate(144deg); animation-delay:0.4s; }
  .petal:nth-child(4) { transform: rotate(216deg); animation-delay:0.6s; }
  .petal:nth-child(5) { transform: rotate(288deg); animation-delay:0.8s; }

  @keyframes bloom {
    0% { transform: scaleY(0) rotate(var(--rotate)); }
    100% { transform: scaleY(1) rotate(var(--rotate)); }
  }

  /* Text */
  .text {
    position: absolute;
    bottom:150px;
    width:100%;
    text-align:center;
    font-size:2.2rem;
    font-weight:700;
    color:#fff;
    text-shadow: 0 0 10px #ff4081, 0 0 20px #ff80ab, 0 0 30px #ff4081;
    opacity:0;
    animation: showText 3s 3s forwards;
  }

  @keyframes showText {
    0% { opacity:0; transform: translateY(20px);}
    100% { opacity:1; transform: translateY(0);}
  }
</style>
</head>
<body>
<div class="scene">
  <!-- Particles -->
  <script>
    for(let i=0;i<80;i++){
      const p = document.createElement('div');
      p.classList.add('particle');
      p.style.left = Math.random()*100+'vw';
      p.style.animationDuration = (4+Math.random()*4)+'s';
      p.style.width = p.style.height = (3+Math.random()*5)+'px';
      document.body.appendChild(p);
    }
  </script>

  <!-- Flower -->
  <div class="flower">
    <div class="stem"></div>
    <div class="petal" style="--rotate:0deg;"></div>
    <div class="petal" style="--rotate:72deg;"></div>
    <div class="petal" style="--rotate:144deg;"></div>
    <div class="petal" style="--rotate:216deg;"></div>
    <div class="petal" style="--rotate:288deg;"></div>
  </div>

  <!-- Text -->
  <div class="text">Icha I Love U 💖</div>
</div>
</body>
</html>
