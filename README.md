<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>eduCLaaS HR Analytics & Placement Dashboard (Demo Data)</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<style>
:root {
  --maroon: #7d145a;
  --pink: #b22e7a;
  --light-bg: #faf7fa;
  --soft-bg: #fff0fa;
  --border: #f1d3e8;
}
body {
  font-family: 'Poppins', sans-serif;
  background-color: var(--light-bg);
  color: #3a2b3e;
  margin: 0;
  line-height: 1.7;
  overflow-x: hidden;
}
@keyframes slideFade {0%{opacity:0;transform:translateY(-20px);}100%{opacity:1;transform:translateY(0);}}

/* === Header Titles === */
.animated-title {
  text-align:center;color:var(--maroon);
  font-size:42px;font-weight:700;
  animation:slideFade 1.5s ease forwards;
}
.sub-title {
  text-align:center;color:var(--pink);
  font-size:22px;font-weight:500;
  margin-top:-10px;animation:slideFade 2s ease forwards;
}
.disclaimer {
  text-align:center;background:var(--soft-bg);
  color:var(--maroon);font-size:14px;font-weight:500;
  padding:10px 15px;border-radius:8px;
  border-left:4px solid var(--pink);
  box-shadow:0 4px 12px rgba(125,20,90,0.1);
  margin:20px auto;max-width:600px;
  animation:slideFade 2.5s ease forwards;
}
.content-box {
  background:#fff;border-left:6px solid var(--maroon);
  padding:25px;border-radius:12px;
  box-shadow:0 6px 18px rgba(125,20,90,0.1);
  margin:25px auto;max-width:1100px;
}
.content-box h2 {color:var(--maroon);}
hr {border:0;border-top:2px solid var(--border);margin:30px 0;}
img {
  border-radius:10px;
  box-shadow:0 4px 15px rgba(125,20,90,0.15);
  transition:transform 0.3s ease,box-shadow 0.3s ease;
}
img:hover {transform:scale(1.03);box-shadow:0 6px 20px rgba(125,20,90,0.25);}
.kpi-table {width:100%;border-collapse:collapse;margin-top:15px;font-size:15px;}
.kpi-table th,.kpi-table td {
  padding:10px 12px;border:1px solid #e8cde0;text-align:center;
}
.kpi-table th {background-color:#fdf1f8;color:var(--maroon);}
.kpi-table td {color:#4a3a47;}

/* === Dashboard === */
.dashboard-container {
  background:#ffffff;padding:30px;border-radius:12px;
  box-shadow:0 4px 12px rgba(0,0,0,0.05);
}
header {
  display:flex;align-items:center;justify-content:space-between;
  padding:15px 25px;border-bottom:4px solid var(--maroon);
  background-color:#fafafa;border-radius:12px 12px 0 0;
}
header img {height:60px;}
header h1 {color:var(--maroon);font-size:22px;margin:0;}
header span {font-size:14px;color:var(--pink);}

.main {display:grid;grid-template-columns:75% 25%;gap:25px;}
.filter-panel {
  background:#f9f2f8;border:1px solid #ecd8eb;border-radius:12px;
  padding:15px;box-shadow:0 2px 6px rgba(0,0,0,0.05);
  height:fit-content;
}
.filter-panel h3 {text-align:center;color:var(--maroon);margin-top:0;}
.filter-section {margin-bottom:15px;}
.filter-section label {
  display:block;font-weight:600;margin-bottom:5px;color:var(--maroon);
}
.filter-section select {
  width:100%;padding:8px;border-radius:6px;border:1px solid #ccc;
  font-family:'Poppins';font-size:13px;
}
button#resetFilters {
  width:100%;padding:10px;background:var(--maroon);
  color:white;border:none;border-radius:8px;
  font-weight:600;cursor:pointer;margin-top:10px;
  transition:background 0.3s;
}
button#resetFilters:hover {background:var(--pink);}

.kpi-container {
  display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:15px;margin-top:25px;
}
.kpi {
  background:#f3e5f5;border-left:6px solid var(--maroon);
  border-radius:10px;padding:15px;text-align:center;
  box-shadow:0 2px 5px rgba(0,0,0,0.1);
}
.kpi h3 {color:var(--maroon);margin:5px 0;font-size:15px;}
.kpi p {color:var(--pink);font-weight:700;font-size:32px;margin:0;}

.chart-grid {
  display:grid;grid-template-columns:repeat(auto-fit,minmax(380px,1fr));
  gap:20px;margin-top:25px;
}
.chart-card {
  background:#fafafa;border:1px solid #e0e0e0;
  border-radius:12px;padding:15px 20px;
  box-shadow:0 2px 8px rgba(0,0,0,0.05);
}
.chart-card h4 {
  text-align:center;color:var(--maroon);
  font-size:15px;margin-bottom:10px;
}
.fact-card {
  margin-top:25px;padding:15px;background:#fafafa;
  border:1px solid #e0e0e0;border-radius:10px;
}
.fact-bar {margin-bottom:12px;}
.fact-label {font-weight:600;color:var(--maroon);margin-bottom:5px;}
.fact-outer {background:#eee;height:22px;border-radius:20px;overflow:hidden;}
.fact-inner {
  height:100%;background:linear-gradient(90deg,var(--maroon),var(--pink));
  text-align:right;color:#fff;padding-right:10px;
  line-height:22px;font-size:12px;
}
footer {text-align:center;font-size:13px;color:gray;padding:25px 0;}
</style>
</head>

<body>

<h1 class="animated-title">eduCLaaS HR Analytics & Power BI Dashboards</h1>
<h2 class="sub-title">📊 Data-Driven Insights & Placement Metrics (Demo Data)</h2>
<div class="disclaimer">⚠️ All data below is simulated and for demonstration only. No confidential or real data is displayed.</div>

<!-- === HR ANALYTICS FIRST === -->
<div class="content-box" id="project1">
  <h2>📊 HR Analytics & Power BI Dashboards</h2>
  <p>Visualizations showcasing learner progress, placement KPIs, and specialist performance trends.</p>

  <div style="display:flex;flex-wrap:wrap;justify-content:center;gap:20px;margin-top:20px;">
    <img src="https://github.com/mohamadazlanwork/Powerbi_Dashboard/blob/main/Lithan/Dashboard%20PBI.png?raw=true" width="45%">
    <img src="https://github.com/mohamadazlanwork/Powerbi_Dashboard/blob/main/Lithan/Dashboard%20PBI%202.png?raw=true" width="45%">
  </div>

  <h3 style="color:#7d145a;margin-top:25px;">📈 Sample Key Performance Indicators</h3>
  <table class="kpi-table">
    <tr><th>KPI</th><th>Value</th><th>Remarks</th></tr>
    <tr><td>Total Learners (Active)</td><td>482</td><td>Across 6 programs</td></tr>
    <tr><td>Placement Conversion Rate</td><td>72%</td><td>Talent + Own Effort</td></tr>
    <tr><td>Average FACT Score</td><td>3.1 / 5</td><td>Based on 320 graded candidates</td></tr>
    <tr><td>Highest Performing Program</td><td>Cloud Admin</td><td>Avg FACT: 3.6</td></tr>
    <tr><td>Top Specialist (Placements)</td><td>Azlan (62)</td><td>Followed by Drake (47)</td></tr>
  </table>
</div>

<hr>

<!-- === LITHAN PLACEMENT DASHBOARD === -->
<div id="placement" class="content-box dashboard-container">
  <header>
    <h1>Lithan Academy Placement Dashboard<br><span>(Demo Data)</span></h1>
  </header>

  <div class="main">
    <!-- Left Charts -->
    <div>
      <div class="kpi-container">
        <div class="kpi"><h3>Talent Placement (D1)</h3><p id="kpiTalentD1">3</p></div>
        <div class="kpi"><h3>Talent Placement (D2)</h3><p id="kpiTalentD2">38</p></div>
        <div class="kpi"><h3>Own Effort (D1)</h3><p id="kpiOwnD1">4</p></div>
        <div class="kpi"><h3>Own Effort (D2)</h3><p id="kpiOwnD2">91</p></div>
      </div>

      <div class="fact-card">
        <h4 style="text-align:center;color:var(--maroon);margin-bottom:10px;">Average F.A.C.T Scores</h4>
        <div class="fact-bar"><div class="fact-label">Flexibility</div><div class="fact-outer"><div class="fact-inner" style="width:85%;">3.4</div></div></div>
        <div class="fact-bar"><div class="fact-label">Articulation</div><div class="fact-outer"><div class="fact-inner" style="width:82%;">3.3</div></div></div>
        <div class="fact-bar"><div class="fact-label">Confidence</div><div class="fact-outer"><div class="fact-inner" style="width:80%;">3.2</div></div></div>
        <div class="fact-bar"><div class="fact-label">Technical</div><div class="fact-outer"><div class="fact-inner" style="width:65%;">2.6</div></div></div>
      </div>
    </div>

    <!-- Right Filters -->
    <aside class="filter-panel">
      <h3>Filters</h3>
      <div class="filter-section">
        <label for="categorySelect">Category</label>
        <select id="categorySelect">
          <option value="all">All</option>
          <option value="Talent">Talent</option>
          <option value="OwnEffort">Own Effort</option>
        </select>
      </div>
      <div class="filter-section">
        <label for="specialistSelect">Specialist</label>
        <select id="specialistSelect">
          <option value="all">All</option>
          <option value="Azlan">Azlan</option>
          <option value="Drake">Drake</option>
          <option value="Selena">Selena</option>
          <option value="Justin Bieber">Justin Bieber</option>
        </select>
      </div>
      <div class="filter-section">
        <label for="courseSelect">Course</label>
        <select id="courseSelect">
          <option value="all">All</option>
          <option value="EIT">EIT</option>
          <option value="PDCA">PDCA</option>
          <option value="PDDS">PDDS</option>
          <option value="PDOM">PDOM</option>
          <option value="PDAI">PDAI</option>
          <option value="POWD">POWD</option>
        </select>
      </div>
      <button id="resetFilters">Clear Filters</button>
    </aside>
  </div>
</div>

<footer>⚠️ All dashboards use simulated demo data. No confidential information is included.</footer>

<script>
const data = [
  { specialist:"Azlan", course:"EIT", category:"Talent", value:15 },
  { specialist:"Drake", course:"PDCA", category:"Talent", value:12 },
  { specialist:"Selena", course:"PDDS", category:"Talent", value:9 },
  { specialist:"Justin Bieber", course:"PDOM", category:"Talent", value:2 },
  { specialist:"Azlan", course:"PDCA", category:"OwnEffort", value:42 },
  { specialist:"Drake", course:"PDDS", category:"OwnEffort", value:35 },
  { specialist:"Selena", course:"PDAI", category:"OwnEffort", value:14 },
  { specialist:"Justin Bieber", course:"POWD", category:"OwnEffort", value:0 }
];

let chartSpecialist, chartCourse, chartRatio, chartGrade;

function groupBy(arr,key){return arr.reduce((acc,cur)=>{acc[cur[key]]=(acc[cur[key]]||0)+cur.value;return acc;},{});}
function renderCharts(filtered=data){
  const bySpec=groupBy(filtered,"specialist");
  const byCourse=groupBy(filtered,"course");
  const talentTotal=filtered.filter(d=>d.category==="Talent").reduce((a,b)=>a+b.value,0);
  const ownTotal=filtered.filter(d=>d.category==="OwnEffort").reduce((a,b)=>a+b.value,0);

  if(chartSpecialist) chartSpecialist.destroy();
  if(chartCourse) chartCourse.destroy();
  if(chartRatio) chartRatio.destroy();
  if(chartGrade) chartGrade.destroy();

  chartSpecialist=new Chart(document.getElementById("chartSpecialist"),{type:"bar",data:{labels:Object.keys(bySpec),datasets:[{data:Object.values(bySpec),backgroundColor:"#7d145a"}]},options:{plugins:{legend:{display:false}},scales:{y:{beginAtZero:true}}}});
  chartCourse=new Chart(document.getElementById("chartCourse"),{type:"bar",data:{labels:Object.keys(byCourse),datasets:[{data:Object.values(byCourse),backgroundColor:"#b22e7a"}]},options:{plugins:{legend:{display:false}},scales:{y:{beginAtZero:true}}}});
  chartRatio=new Chart(document.getElementById("chartRatio"),{type:"doughnut",data:{labels:["Talent","Own Effort"],datasets:[{data:[talentTotal,ownTotal],backgroundColor:["#7d145a","#b22e7a"]}]},options:{plugins:{legend:{position:"bottom"}}}});
  chartGrade=new Chart(document.getElementById("chartGrade"),{type:"bar",data:{labels:["A","B","C","D"],datasets:[{data:[8,6,3,1],backgroundColor:["#7d145a","#b22e7a","#d47bab","#f2c3e0"]}]},options:{plugins:{legend:{display:false}},scales:{y:{beginAtZero:true}}}});

  // Update visible numbers
  document.getElementById("kpiTalentD1").textContent=filtered.filter(d=>d.category==="Talent").length;
  document.getElementById("kpiTalentD2").textContent=talentTotal;
  document.getElementById("kpiOwnD1").textContent=filtered.filter(d=>d.category==="OwnEffort").length;
  document.getElementById("kpiOwnD2").textContent=ownTotal;
}

// Filter Controls
const categorySelect=document.getElementById("categorySelect");
const specialistSelect=document.getElementById("specialistSelect");
const courseSelect=document.getElementById("courseSelect");
const resetBtn=document.getElementById("resetFilters");

function applyFilters(){
  const cat=categorySelect.value,spec=specialistSelect.value,course=courseSelect.value;
  const filtered=data.filter(d=>
    (cat==="all"||d.category===cat)&&
    (spec==="all"||d.specialist===spec)&&
    (course==="all"||d.course===course)
  );
  renderCharts(filtered);
}
categorySelect.onchange=applyFilters;
specialistSelect.onchange=applyFilters;
courseSelect.onchange=applyFilters;
resetBtn.onclick=()=>{categorySelect.value="all";specialistSelect.value="all";courseSelect.value="all";renderCharts(data);};

// Initialize
window.onload=()=>renderCharts(data);
</script>
</body>
</html>
