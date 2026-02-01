<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💝 Ma Valentine</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Georgia,serif;background:linear-gradient(135deg,#ff9a9e 0%,#fecfef 50%,#ffecd2 100%);min-height:100vh;display:flex;align-items:center;justify-content:center;overflow:hidden;position:relative}
.big-heart{position:absolute;font-size:20rem;opacity:.1;z-index:0;color:#ff69b4;animation:heartbeat 3s infinite;user-select:none}
@keyframes heartbeat{0%,100%{transform:scale(1)}50%{transform:scale(1.05)}}
.initials{position:absolute;top:1.5rem;display:flex;gap:.8rem;z-index:2;font-size:2.5rem;font-weight:bold;color:#e91e63;text-shadow:2px 2px 4px rgba(0,0,0,.1)}
.initial{width:60px;height:60px;background:linear-gradient(135deg,#f093fb 0%,#f5576c 100%);color:white;border-radius:50%;display:flex;align-items:center;justify-content:center;box-shadow:0 5px 15px rgba(245,87,108,.3)}
.heart{position:absolute;font-size:1.5rem;opacity:.3;animation:float 6s infinite}
@keyframes float{0%,100%{transform:translateY(0) rotate(0)}50%{transform:translateY(-30px) rotate(10deg)}}
.container{text-align:center;background:rgba(255,255,255,.95);padding:2rem 1.5rem;border-radius:30px;box-shadow:0 20px 60px rgba(255,105,135,.3);max-width:90%;max-height:80vh;overflow-y:auto;position:relative;z-index:1;margin:7rem 1rem 2rem}
h1{color:#e91e63;font-size:1.8rem;margin-bottom:1rem;animation:pulse 2s infinite}
@keyframes pulse{0%,100%{transform:scale(1)}50%{transform:scale(1.05)}}
.message{color:#555;font-size:1rem;margin-bottom:1.5rem;line-height:1.4}
.buttons{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;margin-top:1rem}
button{padding:.9rem 1.8rem;font-size:1rem;border:none;border-radius:50px;cursor:pointer;transition:all .3s;font-weight:bold}
.yes-btn{background:linear-gradient(135deg,#f093fb 0%,#f5576c 100%);color:white}
.yes-btn:hover{transform:scale(1.1);box-shadow:0 10px 30px rgba(245,87,108,.4)}
.no-btn{background:#e0e0e0;color:#666}
.response{margin-top:1.5rem;font-size:1.3rem;color:#e91e63;font-weight:bold;animation:fadeIn .5s;display:none}
@keyframes fadeIn{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
.celebration{font-size:2.5rem;margin-top:1rem;display:none}
.date-info{margin-top:1.5rem;padding:1.2rem;background:linear-gradient(135deg,#fff5f7 0%,#ffe8f0 100%);border-radius:20px;border:2px solid #f5576c;display:none;animation:fadeIn .8s}
.date-info h2{color:#e91e63;margin-bottom:.8rem;font-size:1.5rem}
.date-info p{color:#555;font-size:1rem;line-height:1.5}
@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-10px)}75%{transform:translateX(10px)}}
.shake{animation:shake .5s}
.firework{position:absolute;width:4px;height:4px;border-radius:50%;animation:explode 1s ease-out forwards}
@keyframes explode{0%{transform:translate(0,0) scale(1);opacity:1}100%{transform:translate(var(--tx),var(--ty)) scale(0);opacity:0}}
</style>
</head>
<body>
<div class="big-heart">❤️</div>
<div class="initials">
<div class="initial">E</div>
<div style="font-size:2rem;color:#e91e63;display:flex;align-items:center">💕</div>
<div class="initial">P</div>
</div>
<div class="container">
<h1>Veux-tu être ma Valentine? 💝</h1>
<p class="message">Mon cœur grâce a toi j'ai trouvé un but a ma vie, tu es ma muse, mon inspiration, ma joie de vivre sans toi je ne saurai comment trouver une chose pour me motiver ainsi. On dit que le Bonheur est éphémère mais avec toi il est éternel c'est donc sur que je te demande. Aurais tu le plaisir de me donner encore de joie devenant ma Valentine?<br><br>Alors... qu'en dis-tu? 💕</p>
<div class="buttons">
<button class="yes-btn" onclick="handleYes()">Oui! 💕</button>
<button class="no-btn" id="noBtn" onclick="handleNo()">Non</button>
</div>
<div class="response" id="response"></div>
<div class="celebration" id="celebration"></div>
<div class="date-info" id="dateInfo">
<h2>🎬 Notre Rendez-vous! 🍿</h2>
<p><strong>Date:</strong> 14 Février 2026<br><strong>Activité:</strong> Soirée Cinéma Romantique 🎥<br><strong>Où:</strong> Chez nous, confortablement installés ensemble<br><strong>Programme:</strong> Un film, toi et moi a travers nos écrans 💑<br><br>J'ai hâte de passer ce moment magique avec toi bb! ✨</p>
</div>
</div>
<script>
function createHeart(){const h=document.createElement('div');h.className='heart';h.textContent='💖';h.style.left=Math.random()*100+'vw';h.style.top=Math.random()*100+'vh';h.style.animationDelay=Math.random()*3+'s';document.body.appendChild(h)}
for(let i=0;i<15;i++)createHeart();
function createFirework(x,y){const colors=['#ff6b6b','#f06595','#cc5de8','#845ef7','#5c7cfa','#339af0','#22b8cf','#20c997','#51cf66','#ffd43b','#ff922b'];for(let i=0;i<30;i++){const f=document.createElement('div');f.className='firework';f.style.backgroundColor=colors[Math.floor(Math.random()*colors.length)];f.style.left=x+'px';f.style.top=y+'px';const angle=(Math.PI*2*i)/30;const velocity=100+Math.random()*100;f.style.setProperty('--tx',Math.cos(angle)*velocity+'px');f.style.setProperty('--ty',Math.sin(angle)*velocity+'px');document.body.appendChild(f);setTimeout(()=>f.remove(),1000)}}
function launchFireworks(){const c=document.querySelector('.container');const r=c.getBoundingClientRect();for(let i=0;i<8;i++)setTimeout(()=>createFirework(r.left+Math.random()*r.width,r.top+Math.random()*r.height),i*200)}
function handleYes(){const res=document.getElementById('response');const cel=document.getElementById('celebration');const btns=document.querySelector('.buttons');const msg=document.querySelector('.message');const info=document.getElementById('dateInfo');launchFireworks();msg.textContent="Je savais que tu dirais oui comment ne pas dire oui ptdr 💖";res.textContent="Je t'aime ma princesse 😍🥰";res.style.display='block';cel.textContent='🎉 ❤️ 🎊 💕 🎉 ✨ 💖 🌹';cel.style.display='block';btns.style.display='none';setTimeout(()=>info.style.display='block',1500);for(let i=0;i<30;i++)setTimeout(createHeart,i*100);setTimeout(launchFireworks,3600)}
function handleNo(){const btn=document.getElementById('noBtn');const c=document.querySelector('.container');c.classList.add('shake');setTimeout(()=>c.classList.remove('shake'),500);btn.textContent="Oui! 💕";btn.className="yes-btn";btn.onclick=handleYes;const res=document.getElementById('response');res.textContent="haha... mdr ta pas le choix enft ressaye. 😊";res.style.display='block';setTimeout(()=>res.style.display='none',3000)}
</script>
</body>
</html>
