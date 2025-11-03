<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>eduCLaaS HR Analytics Dashboards (Demo)</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<style>
/* =====================================================
   🎨  DARK THEME – CINEMATIC MAROON + GLASSY OVERLAY
   ===================================================== */
:root {
  --maroon: #3a0a2a;
  --pink: #e45a84;
  --text-light: #fff;
  --text-muted: #bbb;
  --glass-bg: rgba(255,255,255,0.08);
  --border-glass: rgba(255,255,255,0.15);
}
*{box-sizing:border-box;margin:0;padding:0}
body{
  font-family:'Poppins',sans-serif;
  background:radial-gradient(circle at 30% 20%,#2a0a20,#0e020b 80%);
  color:var(--text-light);
  overflow-x:hidden;
}

/* ===== HEADER ===== */
header{
  text-align:center;
  padding:70px 20px 40px;
  animation:fadeSlideDown 1.5s ease forwards;
  position:relative;
  z-index:10;
}
header h1{
  color:#fff;
  font-size:2.8rem;
  letter-spacing:1px;
  font-weight:700;
  margin-bottom:12px;
}
header p{
  color:var(--pink);
  font-weight:500;
  font-size:1.1rem;
  margin-bottom:15px;
}
.disclaimer{
  display:inline-block;
  background:var(--glass-bg);
  border:1px solid var(--border-glass);
  backdrop-filter:blur(8px);
  padding:10px 18px;
  border-radius:10px;
  font-size:.9rem;
  color:#ffb7d1;
  box-shadow:0 0 10px rgba(228,90,132,.2);
}

/* ===== ANIMATIONS ===== */
@keyframes fadeSlideDown{
  0%{opacity:0;transform:translateY(-40px)}
  100%{opacity:1;transform:translateY(0)}
}
@keyframes fadeInUp{
  0%{opacity:0;transform:translateY(40px) scale(.9)}
  100%{opacity:1;transform:translateY(0) scale(1)}
}

/* ===== GALLERY GRID BASE ===== */
.gallery{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
  gap:28px;
  padding:0 7% 90px;
  position:relative;
  z-index:5;
}
.card{
  position:relative;
  border-radius:14px;
  overflow:hidden;
  cursor:pointer;
  transform:translateY(40px);
  opacity:0;
  animation:fadeInUp 1s ease forwards;
  background:var(--glass-bg);
  border:1px solid var(--border-glass);
  backdrop-filter:blur(10px);
  box-shadow:0 0 20px rgba(0,0,0,.4);
  transition:transform .4s ease,box-shadow .4s ease;
}
.card:hover{
  transform:scale(1.07) translateY(-5px);
  box-shadow:0 0 35px rgba(228,90,132,.5);
}
.card img{
  width:100%;
  height:auto;
  display:block;
  filter:brightness(.9) contrast(1.05);
  transition:filter .5s ease,transform .5s ease;
}
.card:hover img{
  filter:brightness(1.15) contrast(1.15);
  transform:scale(1.12);
}
.caption{
  position:absolute;
  bottom:0;
  width:100%;
  background:linear-gradient(180deg,transparent,rgba(0,0,0,.7));
  text-align:center;
  padding:12px;
  font-size:.95rem;
  color:#fff;
  letter-spacing:.3px;
}

/* ===== LIGHTBOX OVERLAY ===== */
.lightbox{
  display:none;
  align-items:center;
  justify-content:center;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.88);
  backdrop-filter:blur(12px);
  z-index:9999;
  animation:fadeIn .6s ease forwards;
}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
.lightbox.active{display:flex}
.lightbox img{
  max-width:90%;
  max-height:85%;
  border-radius:12px;
  box-shadow:0 0 30px rgba(228,90,132,.6);
  animation:zoomIn .6s ease;
}
@keyframes zoomIn{
  0%{transform:scale(.7);opacity:0}
  100%{transform:scale(1);opacity:1}
}

/* ===== LIGHTBOX CONTROLS ===== */
.lb-controls{
  position:absolute;
  width:100%;
  top:50%;
  transform:translateY(-50%);
  display:flex;
  justify-content:space-between;
  padding:0 30px;
}
.lb-btn{
  color:#fff;
  font-size:3rem;
  user-select:none;
  cursor:pointer;
  text-shadow:0 0 15px rgba(228,90,132,.6);
  transition:transform .3s ease;
}
.lb-btn:hover{transform:scale(1.2)}
.lb-close{
  position:absolute;
  top:20px;
  right:30px;
  color:#fff;
  font-size:2.2rem;
  cursor:pointer;
  text-shadow:0 0 10px rgba(255,255,255,.5);
  transition:transform .3s ease;
}
.lb-close:hover{transform:rotate(90deg)}

/* ===== FOOTER ===== */
footer{
  text-align:center;
  padding:35px 15px;
  color:var(--text-muted);
  font-size:.9rem;
  border-top:1px solid rgba(255,255,255,.1);
  background:rgba(0,0,0,.3);
  backdrop-filter:blur(10px);
}
footer a{
  color:var(--pink);
  text-decoration:none;
  font-weight:600;
}
footer a:hover{text-decoration:underline}

/* ===== RESPONSIVE ===== */
@media(max-width:768px){
  header h1{font-size:2rem}
  .lb-btn{font-size:2.2rem}
}
</style>
</head>

<body>
<header>
  <h1>eduCLaaS HR Analytics Dashboards</h1>
  <p>Created by Azlan · Lithan Academy</p>
  <div class="disclaimer">⚠️ For demo purposes only. No actual records used.</div>
</header>

<section class="gallery">
  <!-- ===== DASHBOARD CARDS ===== -->
  <div class="card" data-index="0">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dahsboard%201.jpg?raw=true" alt="Dashboard 1">
    <div class="caption">Dashboard 1 – Placement Summary</div>
  </div>

  <div class="card" data-index="1">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashbaord%202.jpg?raw=true" alt="Dashboard 2">
    <div class="caption">Dashboard 2 – FACT Index Performance</div>
  </div>

  <div class="card" data-index="2">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%203.jpg?raw=true" alt="Dashboard 3">
    <div class="caption">Dashboard 3 – Program Performance Insights</div>
  </div>

  <div class="card" data-index="3">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%204.jpg?raw=true" alt="Dashboard 4">
    <div class="caption">Dashboard 4 – Learner Activity Tracking</div>
  </div>

  <div class="card" data-index="4">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%205.jpg?raw=true" alt="Dashboard 5">
    <div class="caption">Dashboard 5 – Interview Conversion Rate</div>
  </div>

  <div class="card" data-index="5">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%206.jpg?raw=true" alt="Dashboard 6">
    <div class="caption">Dashboard 6 – Candidate Readiness Analytics</div>
  </div>

  <div class="card" data-index="6">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%207.jpg?raw=true" alt="Dashboard 7">
    <div class="caption">Dashboard 7 – Program Completion Rates</div>
  </div>

  <div class="card" data-index="7">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%20PBI.png?raw=true" alt="Dashboard 8">
    <div class="caption">Dashboard 8 – Power BI Overview</div>
  </div>

  <div class="card" data-index="8">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashbaord%20PBI%203.png?raw=true" alt="Dashboard 9">
    <div class="caption">Dashboard 9 – HR Analytics Report 2025</div>
  </div>
</section>

<!-- ===== LIGHTBOX OVERLAY STRUCTURE ===== -->
<div class="lightbox" id="lightbox">
  <span class="lb-close" id="lbClose">&times;</span>
  <div class="lb-controls">
    <span class="lb-btn" id="lbPrev">&#10094;</span>
    <span class="lb-btn" id="lbNext">&#10095;</span>
  </div>
  <img id="lbImage" src="" alt="Large view">
</div>

<footer>
  © 2025 Lithan Academy Demo Gallery | Created by Azlan
</footer>

<script>
/* =====================================================
   🖼️  LIGHTBOX + INTERACTIVE DASHBOARD VIEWER LOGIC
   ===================================================== */
document.addEventListener("DOMContentLoaded", () => {
  const cards = document.querySelectorAll(".card");
  const lightbox = document.getElementById("lightbox");
  const lbImage = document.getElementById("lbImage");
  const lbClose = document.getElementById("lbClose");
  const lbNext = document.getElementById("lbNext");
  const lbPrev = document.getElementById("lbPrev");
  let currentIndex = 0;

  cards.forEach((card,i)=>{
    setTimeout(()=>{card.style.opacity="1";card.style.transform="translateY(0)"},i*120);
  });

  cards.forEach((card,index)=>{
    card.addEventListener("click",()=>{
      currentIndex=index;
      showImage(index);
      lightbox.classList.add("active");
      document.body.style.overflow="hidden";
    });
  });

  lbClose.addEventListener("click",closeLightbox);
  lightbox.addEventListener("click",e=>{if(e.target===lightbox)closeLightbox()});
  function closeLightbox(){
    lightbox.classList.remove("active");
    document.body.style.overflow="auto";
  }
  function showImage(index){
    const img=cards[index].querySelector("img");
    lbImage.src=img.src;
    lbImage.alt=img.alt;
  }

  lbNext.addEventListener("click",()=>{currentIndex=(currentIndex+1)%cards.length;animateTransition()});
  lbPrev.addEventListener("click",()=>{currentIndex=(currentIndex-1+cards.length)%cards.length;animateTransition()});

  document.addEventListener("keydown",e=>{
    if(!lightbox.classList.contains("active"))return;
    if(e.key==="ArrowRight"){currentIndex=(currentIndex+1)%cards.length;animateTransition()}
    else if(e.key==="ArrowLeft"){currentIndex=(currentIndex-1+cards.length)%cards.length;animateTransition()}
    else if(e.key==="Escape"){closeLightbox()}
  });

  function animateTransition(){
    lbImage.classList.add("fade-out");
    setTimeout(()=>{
      showImage(currentIndex);
      lbImage.classList.remove("fade-out");
      lbImage.classList.add("fade-in");
      setTimeout(()=>lbImage.classList.remove("fade-in"),400);
    },300);
  }
});

const style=document.createElement('style');
style.innerHTML=`
.fade-out{opacity:0;transform:scale(.95);transition:opacity .3s,transform .3s;}
.fade-in{opacity:1;transform:scale(1);transition:opacity .4s,transform .4s;}
`;
document.head.appendChild(style);
</script>

<!-- =====================================================
     🌌  PART 4 – BACKGROUND LIGHT ANIMATION
===================================================== -->
<style>
#bgCanvas {
  position: fixed;
  inset: 0;
  z-index: 0;
  background: radial-gradient(circle at center, #1a0210 0%, #0b0106 100%);
  overflow: hidden;
}
.orb {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(228,90,132,0.6) 0%, rgba(228,90,132,0) 70%);
  filter: blur(40px);
  opacity: 0.5;
  animation: floaty 30s infinite ease-in-out;
}
@keyframes floaty {
  0%{transform:translateY(0)translateX(0)scale(1);opacity:.6}
  25%{transform:translateY(-40px)translateX(50px)scale(1.1);opacity:.8}
  50%{transform:translateY(60px)translateX(-60px)scale(.9);opacity:.5}
  75%{transform:translateY(-30px)translateX(70px)scale(1.15);opacity:.7}
  100%{transform:translateY(0)translateX(0)scale(1);opacity:.6}
}
</style>

<div id="bgCanvas"></div>

<script>
document.addEventListener("DOMContentLoaded",()=>{
  const bg=document.getElementById("bgCanvas");
  const orbColors=[
    "rgba(228,90,132,0.5)",
    "rgba(179,46,122,0.4)",
    "rgba(255,120,180,0.25)"
  ];
  const orbCount=25;
  for(let i=0;i<orbCount;i++){
    const orb=document.createElement("div");
    orb.classList.add("orb");
    const size=Math.random()*220+80;
    orb.style.width=`${size}px`;
    orb.style.height=`${size}px`;
    orb.style.left=`${Math.random()*100}%`;
    orb.style.top=`${Math.random()*100}%`;
    orb.style.background=`radial-gradient(circle, ${orbColors[Math.floor(Math.random()*orbColors.length)]} 0%, transparent 70%)`;
    orb.style.animationDelay=`${Math.random()*-20}s`;
    orb.style.animationDuration=`${25+Math.random()*20}s`;
    bg.appendChild(orb);
  }
  document.addEventListener("mousemove",e=>{
    const x=(e.clientX/window.innerWidth-0.5)*30;
    const y=(e.clientY/window.innerHeight-0.5)*30;
    bg.style.transform=`translate(${x}px,${y}px) scale(1.02)`;
  });
});
</script>

</body>
</html>
