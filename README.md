<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shahd & Youssef ❤️</title><link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600&display=swap" rel="stylesheet"><style>
body{
margin:0;
font-family:'Cairo',sans-serif;
background:#fff;
color:#c70039;
overflow-x:hidden;
text-align:center;
}

/* floating hearts */
.hearts{
position:fixed;
inset:0;
overflow:hidden;
pointer-events:none;
z-index:0;
}

.hearts span{
position:absolute;
bottom:-50px;
color:#ff3366;
font-size:22px;
animation:floatUp 8s linear infinite;
opacity:0.5;
}

@keyframes floatUp{
0%{transform:translateY(0) scale(0.8);}
100%{transform:translateY(-110vh) scale(1.4);}
}

#lock{
position:fixed;
inset:0;
background:white;
display:flex;
justify-content:center;
align-items:center;
z-index:999;
}

.box{
padding:30px;
border-radius:20px;
border:2px solid #ffd1dc;
box-shadow:0 10px 30px rgba(255,0,80,0.1);
}

input,button{
padding:10px;
border-radius:10px;
border:none;
margin-top:10px;
}

button{
background:#ff2d55;
color:white;
cursor:pointer;
}

.main{display:none;padding:20px;position:relative;z-index:2;}

h1{font-size:40px;}

.timer{
background:#fff5f7;
padding:20px;
border-radius:20px;
margin:20px auto;
max-width:500px;
font-size:22px;
}

textarea{
width:90%;
height:120px;
border:none;
background:#fff5f7;
border-radius:15px;
padding:10px;
font-size:18px;
}

.gallery{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:15px;
margin-top:20px;
}

.card{
background:white;
padding:10px;
border-radius:15px;
box-shadow:0 5px 20px rgba(255,0,80,0.1);
}

.card img{
width:100%;
height:240px;
object-fit:cover;
border-radius:10px;
}

.love{color:#ff004c;font-weight:bold;}

.nav{
margin:20px 0;
}

.nav button{
margin:5px;
}

.section{display:none;}
.active{display:block;}

.memory-card{
background:#fff5f7;
padding:15px;
border-radius:15px;
margin:10px auto;
max-width:600px;
}

</style></head><body><div class="hearts" id="hearts"></div><!-- PASSWORD --><div id="lock">
<div class="box">
<h2>Enter Password ❤️</h2>
<input type="password" id="pass">
<br>
<button onclick="check()">Enter</button>
</div>
</div><!-- MAIN --><div class="main" id="main"><h1>Shahd ❤️ Youssef</h1>
<p>10/9/2025</p><div class="timer" id="timer"></div><div class="nav">
<button onclick="showSection('home')">Home</button>
<button onclick="showSection('memories')">Memories</button>
</div><!-- HOME --><div id="home" class="section active"><h3>💌 Your Message</h3>
<textarea placeholder="Write your love message..."></textarea><h3>📸 Photos</h3>
<input type="file" multiple accept="image/*" onchange="addImgs(event)"><div class="gallery" id="gallery"></div></div><!-- MEMORIES --><div id="memories" class="section">
<h2>Our Memories ❤️</h2><div class="memory-card">First time we met 💕</div>
<div class="memory-card">Our first conversation 💬</div>
<div class="memory-card">Our happiest day ✨</div></div><audio autoplay loop>
<source src="music.mp3">
</audio></div><script>

// password
function check(){
let p=document.getElementById("pass").value;
if(p==="9/10/2025"){
document.getElementById("lock").style.display="none";
document.getElementById("main").style.display="block";
startTimer();
}
}

// timer
let start=new Date("2025-10-09");

function startTimer(){
setInterval(()=>{
let now=new Date();
let diff=now-start;

let d=Math.floor(diff/(1000*60*60*24));
let h=Math.floor(diff/(1000*60*60)%24);
let m=Math.floor(diff/(1000*60)%60);
let s=Math.floor(diff/1000%60);

document.getElementById("timer").innerHTML=
`⏳ ${d} days ${h}h ${m}m ${s}s`;
},1000);
}

// images
function addImgs(e){
let g=document.getElementById("gallery");
for(let f of e.target.files){
let r=new FileReader();
r.onload=function(x){
let div=document.createElement("div");
div.className="card";
div.innerHTML=`<img src="${x.target.result}"><div class='love'>I love you ❤️</div>`;
g.appendChild(div);
}
r.readAsDataURL(f);
}
}

// navigation
function showSection(id){
document.querySelectorAll(".section").forEach(s=>s.classList.remove("active"));
document.getElementById(id).classList.add("active");
}

// floating hearts
function createHearts(){
const hearts=document.getElementById("hearts");
for(let i=0;i<20;i++){
let s=document.createElement("span");
s.innerHTML="❤️";
s.style.left=Math.random()*100+"vw";
s.style.animationDuration=(5+Math.random()*5)+"s";
hearts.appendChild(s);
}
}
createHearts();

</script></body>
</html>
