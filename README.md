<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HR Dashboards (Demo)</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<style>
:root {
  --maroon:#3a0a2a;
  --pink:#e45a84;
  --text-light:#fff;
  --text-muted:#bbb;
  --glass-bg:rgba(255,255,255,0.08);
  --border-glass:rgba(255,255,255,0.15);
}
*{box-sizing:border-box;margin:0;padding:0}
body{
  font-family:'Poppins',sans-serif;
  background:radial-gradient(circle at 30% 20%,#2a0a20,#0e020b 80%);
  color:var(--text-light);
  overflow-x:hidden;
}

/* ===== HEADER ===== */
header{text-align:center;padding:70px 20px 40px;animation:fadeSlideDown 1.5s ease forwards;position:relative;z-index:10;}
header h1{color:#fff;font-size:2.8rem;letter-spacing:1px;font-weight:700;margin-bottom:12px;}
header p{color:var(--pink);font-weight:500;font-size:1.1rem;margin-bottom:15px;}
.disclaimer{display:inline-block;background:var(--glass-bg);border:1px solid var(--border-glass);backdrop-filter:blur(8px);padding:10px 18px;border-radius:10px;font-size:.9rem;color:#ffb7d1;box-shadow:0 0 10px rgba(228,90,132,.2);}

@keyframes fadeSlideDown{0%{opacity:0;transform:translateY(-40px)}100%{opacity:1;transform:translateY(0)}}
@keyframes fadeInUp{0%{opacity:0;transform:translateY(40px) scale(.9)}100%{opacity:1;transform:translateY(0) scale(1)}}

/* ===== GALLERY GRID ===== */
.gallery{display:grid;grid-template-columns:repeat(auto-fit,minmax(320px,1fr));gap:28px;padding:0 7% 90px;position:relative;z-index:5;}
.card{position:relative;border-radius:14px;overflow:hidden;cursor:pointer;transform:translateY(40px);opacity:0;animation:fadeInUp 1s ease forwards;background:var(--glass-bg);border:1px solid var(--border-glass);backdrop-filter:blur(10px);box-shadow:0 0 20px rgba(0,0,0,.4);transition:transform .4s ease,box-shadow .4s ease;}
.card:hover{transform:scale(1.07) translateY(-5px);box-shadow:0 0 35px rgba(228,90,132,.5);}
.card img{width:100%;height:auto;display:block;filter:brightness(.9) contrast(1.05);transition:filter .5s ease,transform .5s ease;}
.card:hover img{filter:brightness(1.15) contrast(1.15);transform:scale(1.12);}

/* ===== HOVER TEXT OVERLAY ===== */
.card-info{
  position:absolute;
  inset:0;
  background:rgba(0,0,0,0.7);
  backdrop-filter:blur(10px);
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  opacity:0;
  transform:translateY(30px);
  transition:all 0.6s ease;
  padding:25px;
}
.card:hover .card-info{opacity:1;transform:translateY(0);}
.card-info h3{font-size:1.2rem;font-weight:600;margin-bottom:8px;}
.card-info p{font-size:.9rem;color:var(--text-muted);line-height:1.5;max-width:90%;}

/* Color-coded titles */
.card-info[data-color="blue"] h3{color:#3FA9F5;}
.card-info[data-color="green"] h3{color:#00C853;}
.card-info[data-color="orange"] h3{color:#FF9800;}
.card-info[data-color="purple"] h3{color:#BA68C8;}
.card-info[data-color="cyan"] h3{color:#00BCD4;}

/* ===== CAPTION ===== */
.caption{position:absolute;bottom:0;width:100%;background:linear-gradient(180deg,transparent,rgba(0,0,0,.7));text-align:center;padding:12px;font-size:.95rem;color:#fff;letter-spacing:.3px;}

/* ===== LIGHTBOX ===== */
.lightbox{display:none;align-items:center;justify-content:center;position:fixed;inset:0;background:rgba(0,0,0,.9);backdrop-filter:blur(12px);z-index:9999;animation:fadeIn .6s ease forwards;}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
.lightbox.active{display:flex;}
.lightbox img{max-width:90%;max-height:85%;border-radius:12px;box-shadow:0 0 30px rgba(228,90,132,.6);animation:zoomIn .6s ease;}
@keyframes zoomIn{0%{transform:scale(.7);opacity:0}100%{transform:scale(1);opacity:1}}
.lb-controls{position:absolute;width:100%;top:50%;transform:translateY(-50%);display:flex;justify-content:space-between;padding:0 30px;}
.lb-btn{color:#fff;font-size:3rem;cursor:pointer;text-shadow:0 0 15px rgba(228,90,132,.6);transition:transform .3s ease;}
.lb-btn:hover{transform:scale(1.2);}
.lb-close{position:absolute;top:20px;right:30px;color:#fff;font-size:2.2rem;cursor:pointer;text-shadow:0 0 10px rgba(255,255,255,.5);transition:transform .3s ease;}
.lb-close:hover{transform:rotate(90deg);}

/* ===== FOOTER ===== */
footer{text-align:center;padding:35px 15px;color:var(--text-muted);font-size:.9rem;border-top:1px solid rgba(255,255,255,.1);background:rgba(0,0,0,.3);backdrop-filter:blur(10px);}
footer a{color:var(--pink);text-decoration:none;font-weight:600;}
footer a:hover{text-decoration:underline;}
@media(max-width:768px){header h1{font-size:2rem}.lb-btn{font-size:2.2rem}}
</style>
</head>

<body>
<header>
  <h1> HR Dashboards</h1>
  <div class="disclaimer">⚠️ Demo visuals for portfolio – no real data used.</div>
</header>

<section class="gallery">
  <!-- Dashboard 1 -->
  <div class="card" data-index="0">
    <img src="https://github.com/mohamadazlanwork/Lithan_Academy/blob/main/Dashboard%20Az/Hr%20Employee%20Overview.jpg?raw=true" alt="HR Employee Overview">
    <div class="card-info" data-color="blue">
      <h3>HR Employee Overview</h3>
      <p>Summarizes organization-wide employee metrics including headcount, average salary, gender diversity, departmental distribution, and performance trends.</p>
    </div>
    <div class="caption">Dashboard 1 – HR Employee Overview</div>
  </div>

  <!-- Dashboard 2 -->
  <div class="card" data-index="1">
    <img src="https://github.com/mohamadazlanwork/Lithan_Academy/blob/main/Dashboard%20Az/Talent%20Dashboard.jpg?raw=true" alt="Talent Dashboard">
    <div class="card-info" data-color="green">
      <h3>Talent Dashboard</h3>
      <p>Provides insights into candidate demographics, gender ratio, age group trends, course group distribution, and job search activity across programs.</p>
    </div>
    <div class="caption">Dashboard 2 – Talent Dashboard</div>
  </div>

  <!-- Dashboard 3 -->
  <div class="card" data-index="2">
    <img src="https://github.com/mohamadazlanwork/Lithan_Academy/blob/main/Dashboard%20Az/Career%20Goals%20%26%20Placement%20Insights.jpg?raw=true" alt="Career Goals and Placement Insights">
    <div class="card-info" data-color="orange">
      <h3>Career Goals & Placement Insights</h3>
      <p>Analyzes learner readiness, grading distribution, expected salary trends, and common career goals across different course groups and role preferences.</p>
    </div>
    <div class="caption">Dashboard 3 – Career Goals & Placement Insights</div>
  </div>

  <!-- Dashboard 4 -->
  <div class="card" data-index="3">
    <img src="https://github.com/mohamadazlanwork/Lithan_Academy/blob/main/Dashboard%20Az/Resignation%20Trend%20Over%20Time.jpg?raw=true" alt="Resignation Trend Over Time">
    <div class="card-info" data-color="purple">
      <h3>Resignation & Attrition Analysis</h3>
      <p>Examines attrition rates, average tenure, and salary comparisons across departments to identify key patterns behind employee turnover.</p>
    </div>
    <div class="caption">Dashboard 4 – Resignation & Attrition Analysis</div>
  </div>

  <!-- Dashboard 5 -->
  <div class="card" data-index="4">
    <img src="https://github.com/mohamadazlanwork/Logoall/blob/main/Dashboard%20PBI.png?raw=true" alt="Q3 Comparison Dashboard">
    <div class="card-info" data-color="cyan">
      <h3>Q3 Comparison Overview</h3>
      <p>Displays Q3 2025 placement performance comparing Talent and Own Effort outcomes by Specialist Trainer and course type for short-term evaluation.</p>
    </div>
    <div class="caption">Dashboard 5 – Q3 Comparison Overview</div>
  </div>
</section>

<!-- Lightbox -->
<div class="lightbox" id="lightbox">
  <span class="lb-close" id="lbClose">&times;</span>
  <div class="lb-controls">
    <span class="lb-btn" id="lbPrev">&#10094;</span>
    <span class="lb-btn" id="lbNext">&#10095;</span>
  </div>
  <img id="lbImage" src="" alt="Large view">
</div>

<footer>© 2025 Demo Gallery | Created by Azlan</footer>

<script>
document.addEventListener("DOMContentLoaded",()=>{
  const cards=document.querySelectorAll(".card");
  const lightbox=document.getElementById("lightbox");
  const lbImage=document.getElementById("lbImage");
  const lbClose=document.getElementById("lbClose");
  const lbNext=document.getElementById("lbNext");
  const lbPrev=document.getElementById("lbPrev");
  let currentIndex=0;

  cards.forEach((card,i)=>{
    setTimeout(()=>{card.style.opacity="1";card.style.transform="translateY(0)"},i*120);
    card.addEventListener("click",()=>{currentIndex=i;showImage(i);lightbox.classList.add("active");document.body.style.overflow="hidden";});
  });

  function showImage(i){lbImage.src=cards[i].querySelector("img").src;}
  function closeLightbox(){lightbox.classList.remove("active");document.body.style.overflow="auto";}
  lbClose.addEventListener("click",closeLightbox);
  lightbox.addEventListener("click",e=>{if(e.target===lightbox)closeLightbox();});
  lbNext.addEventListener("click",()=>{currentIndex=(currentIndex+1)%cards.length;showImage(currentIndex);});
  lbPrev.addEventListener("click",()=>{currentIndex=(currentIndex-1+cards.length)%cards.length;showImage(currentIndex);});
});
</script>
</body>
</html>
