[Papatya.txt](https://github.com/user-attachments/files/22301796/Papatya.txt)

KOD KISMI :

<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Papatya Animasyonu</title>
<link href="https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap" rel="stylesheet">
<style>
body {
  margin: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  background: linear-gradient(180deg,#a0d8ff,#f7fbff);
  overflow: hidden;
  font-family: 'Patrick Hand', cursive;
}

#message {
  position: absolute;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 28px;
  font-weight: bold;
  color: #333;
  text-align: center;
}

.stem {
  width: 12px;
  height: 0;
  background: linear-gradient(to top,#3b7a0a,#6aa84f);
  border-radius: 6px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.3);
  animation: stemGrow 2s ease-out forwards;
}

@keyframes stemGrow { 
  from { height: 0 } 
  to { height: 300px } 
}

.flower {
  position: absolute;
  bottom: 220px;
  width: 240px;
  height: 240px;
  left: 50%;
  transform: translateX(-50%);
}

.center {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 80px;
  height: 80px;
  margin-left: -40px;
  margin-top: -40px;
  border-radius: 50%;
  background: radial-gradient(circle at 35% 35%, #fff8c0 0%, #ffd600 60%, #ffb600 100%);
  box-shadow: 0 0 20px 4px rgba(255,215,0,0.5), inset 0 4px 10px rgba(255,255,255,0.5);
  opacity: 0;
  animation: centerShow 0.8s forwards;
  animation-delay: 2s;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  z-index: 2;
}

.center:hover {
  transform: scale(1.1) rotate(-3deg);
  box-shadow: 0 0 25px 6px rgba(255,215,0,0.7), inset 0 5px 12px rgba(255,255,255,0.6);
}

@keyframes centerShow { 
  to { opacity: 1 } 
}

.petal-wrap { 
  position: absolute; 
  left: 50%; 
  top: 50%; 
  width: 0; 
  height: 0; 
  transform-origin: 50% 50%; 
}

.petal {
  position: absolute;
  left: -30px;
  top: -50px;
  width: 60px;
  height: 100px;
  background: linear-gradient(to bottom, #fffaf0 0%, #f0f0f0 100%);
  border-radius: 60% 60% 40% 40%;
  box-shadow: 0 5px 15px rgba(0,0,0,0.15);
  transform-origin: center 90%;
  transform: translateY(-20px) scale(0.2) rotate(-2deg);
  opacity: 0;
  animation: petalShow 0.6s forwards;
}

@keyframes petalShow {
  to { 
    transform: translateY(-80px) scale(1) rotate(0deg); 
    opacity: 1; 
  }
}

@keyframes petalFall {
  0% {
    transform: translateY(-80px) scale(1) rotate(0deg);
    opacity: 1;
  }
  100% {
    transform: translateY(400px) rotate(90deg) scale(0.5);
    opacity: 0;
  }
}

.petal.fallen {
  animation: petalFall 1s ease-in-out forwards !important;
}

/* Açılar */
.p1{transform:translate(-50%,-50%) rotate(0deg);}   .p2{transform:translate(-50%,-50%) rotate(30deg);}
.p3{transform:translate(-50%,-50%) rotate(60deg);}  .p4{transform:translate(-50%,-50%) rotate(90deg);}
.p5{transform:translate(-50%,-50%) rotate(120deg);} .p6{transform:translate(-50%,-50%) rotate(150deg);}
.p7{transform:translate(-50%,-50%) rotate(180deg);} .p8{transform:translate(-50%,-50%) rotate(210deg);}
.p9{transform:translate(-50%,-50%) rotate(240deg);} .p10{transform:translate(-50%,-50%) rotate(270deg);}
.p11{transform:translate(-50%,-50%) rotate(300deg);} .p12{transform:translate(-50%,-50%) rotate(330deg);}

/* Gecikmeler */
.p1 .petal{animation-delay:2.5s;} .p2 .petal{animation-delay:2.7s;} .p3 .petal{animation-delay:2.9s;}
.p4 .petal{animation-delay:3.1s;} .p5 .petal{animation-delay:3.3s;} .p6 .petal{animation-delay:3.5s;}
.p7 .petal{animation-delay:3.7s;} .p8 .petal{animation-delay:3.9s;} .p9 .petal{animation-delay:4.1s;}
.p10 .petal{animation-delay:4.3s;} .p11 .petal{animation-delay:4.5s;} .p12 .petal{animation-delay:4.7s;}
</style>
</head>
<body>
<div id="message"></div>
<div class="stem"></div>
<div class="flower">
  <div class="center"></div>
  <div class="petal-wrap p1"><div class="petal"></div></div>
  <div class="petal-wrap p2"><div class="petal"></div></div>
  <div class="petal-wrap p3"><div class="petal"></div></div>
  <div class="petal-wrap p4"><div class="petal"></div></div>
  <div class="petal-wrap p5"><div class="petal"></div></div>
  <div class="petal-wrap p6"><div class="petal"></div></div>
  <div class="petal-wrap p7"><div class="petal"></div></div>
  <div class="petal-wrap p8"><div class="petal"></div></div>
  <div class="petal-wrap p9"><div class="petal"></div></div>
  <div class="petal-wrap p10"><div class="petal"></div></div>
  <div class="petal-wrap p11"><div class="petal"></div></div>
  <div class="petal-wrap p12"><div class="petal"></div></div>
</div>

<script>
const center = document.querySelector('.center');
const petals = document.querySelectorAll('.petal');
const message = document.getElementById('message');

const messages = [
  "seviyorrrr :3","sevmiyorrr :c","Seviyooorrr :3","sevmiyoorr :c",
  "Seviyooorrrrr :3","Sevmiyorrrr :c","Seviyooooorrr:3","Sevmiyooorrr :c",
  "...seviyorr","Sevmiyor","Seviyor >:(","sevmeyor..... (Basmaya devam et)",
  "Ne demek sevmiyor","Bir dakkika...","Bu kodu ben yazdım >:3","hihihi >:)",
  "SEVİYORSEVİYORSEVİYORSEVİYORSEVİYORSEVİYORSEVİYOR"
];

let msgIndex = 0;

function fallPetal(petal) {
  if (petal.classList.contains('fallen')) return;
  
  // Tüm animasyonları sıfırla
  petal.style.animation = 'none';
  petal.offsetHeight; // Yeniden akış
  
  // Düşme animasyonunu uygula
  petal.classList.add('fallen');
  
  petal.addEventListener('animationend', () => {
    petal.style.display = 'none';
  }, {once: true});
}

function restorePetal(petal) {
  // Görünürlüğü ve stilleri geri yükle
  petal.style.display = '';
  petal.style.animation = '';
  petal.classList.remove('fallen');
  
  // Yeni animasyonu başlat
  requestAnimationFrame(() => {
    petal.style.animation = 'petalShow 0.6s forwards';
  });
}

// ...existing code...

center.addEventListener('click', () => {
  const visiblePetals = Array.from(petals).filter(p => !p.classList.contains('fallen'));
  
  if (visiblePetals.length > 0) {
    // Rastgele bir yaprak seç
    const randomIndex = Math.floor(Math.random() * visiblePetals.length);
    fallPetal(visiblePetals[randomIndex]); // Rastgele seçilen yaprağı düşür
  }

  if (msgIndex < messages.length) {
    message.textContent = messages[msgIndex];

    if (msgIndex === 15) {
      const fallenPetals = Array.from(petals).filter(p => p.classList.contains('fallen'));
      if (fallenPetals.length > 0) {
        restorePetal(fallenPetals[0]);
      }
    }
    msgIndex++;
  }
});

// ...existing code...
</script>
</body>
</html>
