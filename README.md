<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<meta name="theme-color" content="#060914">
<meta name="description" content="FINI REWARDS - Gaming Rewards App">
<title>FINI REWARDS</title>

<style>
:root{
  --bg:#060914;
  --bg2:#0a1020;
  --card:rgba(15,22,42,.78);
  --card2:rgba(20,29,54,.9);
  --accent:#00d9ff;
  --accent2:#7c3cff;
  --gold:#ffd54a;
  --danger:#ff3d71;
  --success:#36f59a;
  --text:#f7fbff;
  --muted:#9ba8c7;
  --line:rgba(255,255,255,.09);
  --shadow:0 20px 70px rgba(0,0,0,.35);
  --radius:24px;
  --scale:1;
}

*{
  box-sizing:border-box;
  -webkit-tap-highlight-color:transparent;
}

html{
  scroll-behavior:smooth;
}

body{
  margin:0;
  min-height:100vh;
  color:var(--text);
  background:
    radial-gradient(circle at 10% 10%,rgba(0,217,255,.10),transparent 28%),
    radial-gradient(circle at 90% 10%,rgba(124,60,255,.12),transparent 30%),
    radial-gradient(circle at 50% 100%,rgba(255,61,113,.07),transparent 35%),
    var(--bg);
  font-family:
    Tahoma,
    Arial,
    "Segoe UI",
    sans-serif;
  overflow-x:hidden;
  font-size:calc(16px * var(--scale));
}

body.light{
  --bg:#edf4ff;
  --bg2:#ffffff;
  --card:rgba(255,255,255,.82);
  --card2:#ffffff;
  --text:#10172a;
  --muted:#59657d;
  --line:rgba(0,0,0,.08);
  --shadow:0 20px 60px rgba(30,60,100,.12);
}

body.no-animations *,
body.no-animations *::before,
body.no-animations *::after{
  animation:none!important;
  transition:none!important;
}

button,
input,
select,
textarea{
  font:inherit;
}

button{
  border:0;
  cursor:pointer;
}

a{
  color:inherit;
  text-decoration:none;
}

img{
  max-width:100%;
  display:block;
}

::-webkit-scrollbar{
  width:8px;
}

::-webkit-scrollbar-thumb{
  background:linear-gradient(var(--accent),var(--accent2));
  border-radius:20px;
}

.bg-orb{
  position:fixed;
  width:360px;
  height:360px;
  border-radius:50%;
  filter:blur(80px);
  opacity:.18;
  pointer-events:none;
  z-index:-2;
  animation:orbFloat 12s ease-in-out infinite alternate;
}

.orb1{
  background:var(--accent);
  top:-130px;
  right:-100px;
}

.orb2{
  background:var(--accent2);
  bottom:-150px;
  left:-100px;
  animation-delay:-5s;
}

.grid-bg{
  position:fixed;
  inset:0;
  pointer-events:none;
  z-index:-3;
  opacity:.18;
  background-image:
    linear-gradient(rgba(255,255,255,.035) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,255,255,.035) 1px,transparent 1px);
  background-size:35px 35px;
  mask-image:linear-gradient(to bottom,black,transparent 85%);
}

@keyframes orbFloat{
  from{transform:translate3d(0,0,0) scale(1)}
  to{transform:translate3d(50px,40px,0) scale(1.15)}
}

.app{
  width:min(1450px,100%);
  margin:auto;
  padding:18px;
  padding-bottom:110px;
}

.topbar{
  position:sticky;
  top:10px;
  z-index:100;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
  padding:13px 16px;
  margin-bottom:18px;
  border:1px solid var(--line);
  border-radius:25px;
  background:rgba(7,11,27,.74);
  backdrop-filter:blur(20px);
  box-shadow:var(--shadow);
}

body.light .topbar{
  background:rgba(255,255,255,.78);
}

.brand{
  display:flex;
  align-items:center;
  gap:10px;
}

.logo{
  width:45px;
  height:45px;
  display:grid;
  place-items:center;
  border-radius:15px;
  font-size:24px;
  font-weight:1000;
  background:
    linear-gradient(145deg,#fff,#00d9ff 35%,#7c3cff 80%);
  color:#07101d;
  box-shadow:
    0 0 18px rgba(0,217,255,.65),
    0 0 45px rgba(124,60,255,.35);
}

.brand-text h1{
  margin:0;
  font-size:17px;
  font-weight:1000;
  letter-spacing:.5px;
}

.brand-text span{
  color:var(--muted);
  font-size:11px;
}

.top-actions{
  display:flex;
  gap:8px;
}

.icon-btn{
  width:42px;
  height:42px;
  border-radius:14px;
  color:var(--text);
  background:rgba(255,255,255,.06);
  border:1px solid var(--line);
  transition:.2s;
}

.icon-btn:hover{
  transform:translateY(-2px);
  border-color:rgba(0,217,255,.4);
}

.page{
  display:none;
  animation:pageIn .35s ease both;
}

.page.active{
  display:block;
}

@keyframes pageIn{
  from{
    opacity:0;
    transform:translateY(10px);
  }
  to{
    opacity:1;
    transform:none;
  }
}

.hero{
  position:relative;
  overflow:hidden;
  min-height:280px;
  padding:28px;
  border:1px solid var(--line);
  border-radius:34px;
  background:
    linear-gradient(135deg,
      rgba(0,217,255,.11),
      rgba(124,60,255,.14) 50%,
      rgba(255,61,113,.08));
  box-shadow:var(--shadow);
}

.hero::before{
  content:"";
  position:absolute;
  width:280px;
  height:280px;
  border-radius:50%;
  background:rgba(0,217,255,.16);
  filter:blur(60px);
  right:-80px;
  top:-100px;
}

.hero-content{
  position:relative;
  z-index:2;
  max-width:760px;
}

.kicker{
  color:var(--accent);
  font-size:12px;
  font-weight:900;
  text-transform:uppercase;
  letter-spacing:2px;
}

.hero h2{
  margin:8px 0;
  font-size:clamp(30px,5vw,58px);
  line-height:1;
  font-weight:1000;
}

.gradient-text{
  background:linear-gradient(90deg,var(--accent),#fff,var(--accent2),var(--gold));
  -webkit-background-clip:text;
  color:transparent;
  background-size:250% auto;
  animation:textFlow 5s linear infinite;
}

@keyframes textFlow{
  to{background-position:250% center}
}

.hero p{
  color:var(--muted);
  max-width:700px;
  line-height:1.8;
}

.hero-actions{
  display:flex;
  flex-wrap:wrap;
  gap:10px;
  margin-top:20px;
}

.btn{
  min-height:44px;
  padding:11px 17px;
  border-radius:15px;
  color:white;
  font-weight:900;
  border:1px solid var(--line);
  background:rgba(255,255,255,.07);
  transition:.2s;
}

.btn:hover{
  transform:translateY(-2px);
}

.btn.primary{
  background:linear-gradient(135deg,var(--accent),var(--accent2));
  box-shadow:0 12px 30px rgba(0,217,255,.18);
}

.btn.gold{
  color:#111;
  background:linear-gradient(135deg,#fff,var(--gold));
}

.btn.danger{
  background:linear-gradient(135deg,#ff3d71,#ff1744);
}

.btn.success{
  background:linear-gradient(135deg,#00c896,var(--success));
  color:#06130e;
}

.btn.small{
  min-height:36px;
  padding:7px 11px;
  font-size:12px;
}

.btn.full{
  width:100%;
}

.section-title{
  display:flex;
  align-items:end;
  justify-content:space-between;
  gap:10px;
  margin:25px 0 13px;
}

.section-title h2,
.section-title h3{
  margin:0;
  font-size:20px;
}

.section-title span{
  color:var(--muted);
  font-size:12px;
}

.grid{
  display:grid;
  gap:14px;
}

.grid-2{
  grid-template-columns:repeat(2,minmax(0,1fr));
}

.grid-3{
  grid-template-columns:repeat(3,minmax(0,1fr));
}

.grid-4{
  grid-template-columns:repeat(4,minmax(0,1fr));
}

@media(max-width:1000px){
  .grid-4{grid-template-columns:repeat(2,minmax(0,1fr))}
}

@media(max-width:700px){
  .app{
    padding:10px;
    padding-bottom:100px;
  }

  .topbar{
    top:5px;
  }

  .brand-text{
    display:none;
  }

  .hero{
    padding:22px;
    border-radius:26px;
  }

  .grid-2,
  .grid-3,
  .grid-4{
    grid-template-columns:1fr;
  }
}

.card{
  position:relative;
  overflow:hidden;
  border:1px solid var(--line);
  border-radius:var(--radius);
  padding:17px;
  background:var(--card);
  backdrop-filter:blur(18px);
  box-shadow:var(--shadow);
}

.card::after{
  content:"";
  position:absolute;
  width:100px;
  height:100px;
  border-radius:50%;
  right:-45px;
  top:-50px;
  background:rgba(0,217,255,.07);
  filter:blur(20px);
  pointer-events:none;
}

.stat{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
}

.stat strong{
  display:block;
  font-size:25px;
  font-weight:1000;
}

.stat span{
  color:var(--muted);
  font-size:12px;
}

.stat-icon{
  width:48px;
  height:48px;
  display:grid;
  place-items:center;
  border-radius:17px;
  background:linear-gradient(145deg,rgba(0,217,255,.18),rgba(124,60,255,.2));
  font-size:25px;
}

.points-card{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:15px;
}

.points-main{
  display:flex;
  align-items:center;
  gap:10px;
}

.points-main strong{
  font-size:31px;
}

.points-pill{
  display:flex;
  align-items:center;
  gap:9px;
  padding:7px 12px;
  border-radius:17px;
  background:rgba(0,217,255,.09);
  border:1px solid rgba(0,217,255,.2);
}

.big-diamond{
  width:28px;
  height:28px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:18px;
  border-radius:16px;
  background:linear-gradient(135deg,#ffffff,#7ff7ff,#00d9ff,#582ae2);
  box-shadow:0 0 12px #00d9ff,0 0 25px rgba(0,217,255,.7);
  animation:diamondRotate 3s linear infinite;
  transform-style:preserve-3d;
}

@keyframes diamondRotate{
  from{transform:rotate(0deg);}
  to{transform:rotate(360deg);}
}

.home-streak{
  display:flex;
  align-items:center;
  gap:12px;
}

.home-streak>div{
  display:flex;
  flex-direction:column;
}

.home-streak strong{
  font-size:20px;
}

.home-streak small{
  color:var(--muted);
}

.jewel-3d-wrap{
  width:100px;
  height:100px;
  display:grid;
  place-items:center;
  perspective:500px;
}

.jewel-3d{
  font-size:70px;
  animation:jewel360 3s linear infinite;
  transform-style:preserve-3d;
  filter:
    drop-shadow(0 0 8px #fff)
    drop-shadow(0 0 25px #00d9ff)
    drop-shadow(0 0 40px rgba(124,60,255,.8));
}

@keyframes jewel360{
  from{
    transform:rotateY(0deg) rotateX(0deg);
  }
  to{
    transform:rotateY(360deg) rotateX(360deg);
  }
}

.task-card,
.reward-card,
.game-card,
.store-card,
.badge-card,
.friend-card{
  transition:.25s;
}

.task-card:hover,
.reward-card:hover,
.game-card:hover,
.store-card:hover,
.badge-card:hover,
.friend-card:hover{
  transform:translateY(-4px);
  border-color:rgba(0,217,255,.35);
}

.task-top{
  display:flex;
  align-items:center;
  gap:12px;
}

.task-icon,
.game-icon,
.reward-icon{
  width:52px;
  height:52px;
  border-radius:17px;
  display:grid;
  place-items:center;
  font-size:26px;
  background:linear-gradient(145deg,rgba(0,217,255,.13),rgba(124,60,255,.2));
  border:1px solid var(--line);
}

.task-info{
  flex:1;
}

.task-info strong{
  display:block;
}

.task-info span{
  color:var(--muted);
  font-size:11px;
}

.reward-points{
  color:var(--gold);
  font-weight:1000;
  white-space:nowrap;
}

.progress{
  height:8px;
  margin:12px 0;
  overflow:hidden;
  border-radius:20px;
  background:rgba(255,255,255,.08);
}

.progress>i{
  display:block;
  height:100%;
  width:0;
  border-radius:inherit;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
  transition:.4s;
}

.input,
.select,
.textarea{
  width:100%;
  color:var(--text);
  background:rgba(255,255,255,.055);
  border:1px solid var(--line);
  border-radius:14px;
  outline:none;
  padding:11px 13px;
}

.input:focus,
.select:focus,
.textarea:focus{
  border-color:rgba(0,217,255,.5);
  box-shadow:0 0 0 3px rgba(0,217,255,.07);
}

.textarea{
  min-height:110px;
  resize:vertical;
}

label.field{
  display:block;
  margin-bottom:12px;
}

label.field span{
  display:block;
  color:var(--muted);
  font-size:12px;
  margin-bottom:6px;
}

.switch-row{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:15px;
  padding:12px 0;
  border-bottom:1px solid var(--line);
}

.switch{
  position:relative;
  width:50px;
  height:28px;
  flex:none;
}

.switch input{
  display:none;
}

.switch i{
  position:absolute;
  inset:0;
  border-radius:30px;
  background:#30384d;
  transition:.2s;
}

.switch i::after{
  content:"";
  position:absolute;
  width:20px;
  height:20px;
  top:4px;
  right:26px;
  border-radius:50%;
  background:#fff;
  transition:.2s;
}

.switch input:checked+i{
  background:linear-gradient(90deg,var(--accent),var(--accent2));
}

.switch input:checked+i::after{
  right:4px;
}

.bottom-nav{
  position:fixed;
  z-index:120;
  bottom:10px;
  left:50%;
  transform:translateX(-50%);
  width:min(760px,calc(100% - 20px));
  display:flex;
  justify-content:space-around;
  gap:5px;
  padding:8px;
  border:1px solid var(--line);
  border-radius:24px;
  background:rgba(6,9,20,.86);
  backdrop-filter:blur(22px);
  box-shadow:0 20px 80px rgba(0,0,0,.5);
}

body.light .bottom-nav{
  background:rgba(255,255,255,.9);
}

.nav-btn{
  min-width:58px;
  flex:1;
  padding:8px 5px;
  color:var(--muted);
  background:transparent;
  border-radius:16px;
  font-size:10px;
  transition:.2s;
}

.nav-btn b{
  display:block;
  font-size:20px;
  margin-bottom:3px;
}

.nav-btn.active{
  color:var(--text);
  background:linear-gradient(135deg,rgba(0,217,255,.15),rgba(124,60,255,.18));
}

.toast{
  position:fixed;
  z-index:9999;
  top:25px;
  left:50%;
  transform:translate(-50%,-150px);
  opacity:0;
  padding:13px 18px;
  border-radius:16px;
  color:white;
  background:linear-gradient(135deg,#111a31,#17213c);
  border:1px solid rgba(0,217,255,.3);
  box-shadow:0 15px 50px rgba(0,0,0,.4);
  transition:.3s;
  pointer-events:none;
}

.toast.show{
  transform:translate(-50%,0);
  opacity:1;
}

.modal{
  position:fixed;
  z-index:1000;
  inset:0;
  display:none;
  align-items:center;
  justify-content:center;
  padding:15px;
  background:rgba(0,0,0,.72);
  backdrop-filter:blur(12px);
}

.modal.show{
  display:flex;
}

.modal-box{
  width:min(900px,100%);
  max-height:90vh;
  overflow:auto;
  border:1px solid var(--line);
  border-radius:28px;
  padding:20px;
  background:var(--card2);
  box-shadow:0 30px 100px rgba(0,0,0,.6);
  animation:modalIn .25s ease;
}

@keyframes modalIn{
  from{
    opacity:0;
    transform:scale(.94) translateY(15px);
  }
  to{
    opacity:1;
    transform:none;
  }
}

.modal-head{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  margin-bottom:16px;
}

.modal-head h2{
  margin:0;
}

.close{
  width:38px;
  height:38px;
  border-radius:13px;
  color:var(--text);
  background:rgba(255,255,255,.07);
}

.tabs{
  display:flex;
  gap:8px;
  overflow:auto;
  padding-bottom:4px;
  margin-bottom:15px;
}

.tab{
  white-space:nowrap;
  padding:9px 13px;
  border-radius:13px;
  color:var(--muted);
  background:rgba(255,255,255,.05);
  border:1px solid var(--line);
}

.tab.active{
  color:white;
  background:linear-gradient(135deg,var(--accent),var(--accent2));
}

.game-cover,
.store-cover{
  height:130px;
  overflow:hidden;
  border-radius:18px;
  margin:-3px -3px 13px;
  background:
    linear-gradient(135deg,rgba(0,217,255,.15),rgba(124,60,255,.25)),
    #0c1327;
}

.game-cover img,
.store-cover img{
  width:100%;
  height:100%;
  object-fit:cover;
}

.game-meta{
  display:flex;
  justify-content:space-between;
  gap:8px;
  color:var(--muted);
  font-size:11px;
  margin:8px 0;
}

.game-actions{
  display:flex;
  gap:7px;
}

.game-actions .btn{
  flex:1;
}

.badge{
  display:inline-flex;
  align-items:center;
  gap:6px;
  padding:6px 9px;
  border-radius:12px;
  background:rgba(255,255,255,.06);
  border:1px solid var(--line);
  font-size:11px;
}

.badge.unlocked{
  border-color:rgba(255,213,74,.45);
  box-shadow:0 0 20px rgba(255,213,74,.08);
}

.badge.locked{
  opacity:.45;
  filter:grayscale(1);
}

.avatar{
  width:58px;
  height:58px;
  border-radius:19px;
  object-fit:cover;
  border:2px solid rgba(0,217,255,.35);
}

.avatar.big{
  width:100px;
  height:100px;
  border-radius:30px;
}

.profile-head{
  display:flex;
  align-items:center;
  gap:18px;
}

.profile-head h2{
  margin:0 0 4px;
}

.muted{
  color:var(--muted);
}

.small{
  font-size:12px;
}

.chat{
  display:grid;
  grid-template-columns:280px 1fr;
  min-height:620px;
}

.chat-list{
  border-left:1px solid var(--line);
  padding-left:12px;
  max-height:620px;
  overflow:auto;
}

.chat-window{
  display:flex;
  flex-direction:column;
  min-width:0;
}

.chat-header{
  padding:10px 15px;
  border-bottom:1px solid var(--line);
}

.messages{
  flex:1;
  min-height:420px;
  max-height:520px;
  overflow:auto;
  padding:15px;
}

.msg{
  max-width:75%;
  padding:10px 13px;
  border-radius:17px;
  margin:7px 0;
  line-height:1.6;
  font-size:13px;
}

.msg.me{
  margin-right:auto;
  background:linear-gradient(135deg,rgba(0,217,255,.18),rgba(124,60,255,.2));
  border:1px solid rgba(0,217,255,.15);
  border-bottom-right-radius:5px;
}

.msg.bot,
.msg.other{
  margin-left:auto;
  background:rgba(255,255,255,.06);
  border:1px solid var(--line);
  border-bottom-left-radius:5px;
}

.chat-input{
  display:flex;
  gap:8px;
  padding:12px;
  border-top:1px solid var(--line);
}

.chat-input input{
  flex:1;
}

.online-dot{
  display:inline-block;
  width:8px;
  height:8px;
  border-radius:50%;
  background:var(--success);
  box-shadow:0 0 10px var(--success);
}

.wheel{
  width:min(320px,80vw);
  aspect-ratio:1;
  position:relative;
  margin:20px auto;
  border-radius:50%;
  border:8px solid rgba(255,255,255,.1);
  box-shadow:
    0 0 0 3px rgba(0,217,255,.15),
    0 0 60px rgba(0,217,255,.18);
  overflow:hidden;
}

.wheel-inner{
  width:100%;
  height:100%;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:
    conic-gradient(
      #00d9ff 0deg 45deg,
      #7c3cff 45deg 90deg,
      #ff3d71 90deg 135deg,
      #ffd54a 135deg 180deg,
      #36f59a 180deg 225deg,
      #00a6ff 225deg 270deg,
      #9b59ff 270deg 315deg,
      #ff7a18 315deg 360deg
    );
  transition:transform 4s cubic-bezier(.12,.72,.18,1);
}

.wheel-inner::before{
  content:"";
  width:75px;
  height:75px;
  border-radius:50%;
  background:#07101e;
  border:4px solid white;
  box-shadow:0 0 30px rgba(255,255,255,.35);
}

.wheel-pointer{
  position:absolute;
  z-index:2;
  top:-3px;
  left:50%;
  transform:translateX(-50%);
  width:0;
  height:0;
  border-left:14px solid transparent;
  border-right:14px solid transparent;
  border-top:30px solid white;
  filter:drop-shadow(0 0 8px #00d9ff);
}

.admin-nav{
  display:flex;
  flex-wrap:wrap;
  gap:7px;
  margin-bottom:15px;
}

.admin-tab{
  padding:8px 11px;
  border-radius:12px;
  background:rgba(255,61,113,.07);
  border:1px solid rgba(255,61,113,.18);
  color:#ffb3c5;
}

.admin-tab.active{
  color:#fff;
  background:linear-gradient(135deg,#ff3d71,#a9003d);
}

.dev{
  border-color:rgba(255,61,113,.25);
  background:
    radial-gradient(circle at top right,rgba(255,61,113,.10),transparent 30%),
    var(--card);
}

.dev-title{
  color:#ff6b91;
}

.table-wrap{
  width:100%;
  overflow:auto;
}

table{
  width:100%;
  border-collapse:collapse;
  min-width:650px;
}

th,
td{
  text-align:right;
  padding:10px;
  border-bottom:1px solid var(--line);
  font-size:12px;
}

th{
  color:var(--accent);
}

.alert{
  padding:12px 14px;
  border-radius:15px;
  border:1px solid var(--line);
  background:rgba(255,255,255,.045);
  color:var(--muted);
  line-height:1.7;
}

.alert.warning{
  border-color:rgba(255,213,74,.2);
  color:#ffe991;
}

.alert.success{
  border-color:rgba(54,245,154,.2);
  color:#a6ffd1;
}

.alert.danger{
  border-color:rgba(255,61,113,.25);
  color:#ffb2c6;
}

.stat-big{
  font-size:38px;
  font-weight:1000;
}

.fire{
  animation:firePulse 1.3s ease-in-out infinite alternate;
}

@keyframes firePulse{
  from{
    filter:drop-shadow(0 0 4px #ff7a00);
    transform:scale(1);
  }
  to{
    filter:drop-shadow(0 0 18px #ff3d00);
    transform:scale(1.08);
  }
}

.lock-card{
  position:relative;
  overflow:hidden;
}

.lock-overlay{
  position:absolute;
  inset:0;
  z-index:3;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:25px;
  background:rgba(4,7,18,.78);
  backdrop-filter:blur(8px);
}

.lock-overlay strong{
  font-size:24px;
}

.ai-preview{
  min-height:220px;
  display:grid;
  place-items:center;
  text-align:center;
  border-radius:22px;
  border:1px dashed rgba(0,217,255,.35);
  background:
    linear-gradient(135deg,rgba(0,217,255,.06),rgba(124,60,255,.09));
}

.file-drop{
  display:grid;
  place-items:center;
  min-height:140px;
  text-align:center;
  border:1px dashed rgba(255,255,255,.18);
  border-radius:20px;
  background:rgba(255,255,255,.035);
  cursor:pointer;
}

.file-drop input{
  display:none;
}

.timeline{
  display:flex;
  flex-direction:column;
  gap:10px;
}

.timeline-item{
  display:flex;
  gap:12px;
}

.timeline-dot{
  width:12px;
  height:12px;
  margin-top:6px;
  border-radius:50%;
  background:var(--accent);
  box-shadow:0 0 15px var(--accent);
  flex:none;
}

.search-box{
  position:relative;
}

.search-box input{
  padding-right:42px;
}

.search-box b{
  position:absolute;
  right:14px;
  top:10px;
}

.filter-row{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  margin-bottom:14px;
}

.chip{
  padding:7px 10px;
  border-radius:12px;
  background:rgba(255,255,255,.05);
  border:1px solid var(--line);
  color:var(--muted);
  cursor:pointer;
}

.chip.active{
  color:white;
  border-color:rgba(0,217,255,.35);
  background:rgba(0,217,255,.10);
}

.level-ring{
  width:90px;
  height:90px;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:
    radial-gradient(circle,var(--bg) 58%,transparent 60%),
    conic-gradient(var(--accent) 0 72%,rgba(255,255,255,.08) 72%);
}

.level-ring strong{
  font-size:22px;
}

.tournament-bracket{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:10px;
  overflow:auto;
}

.round{
  min-width:180px;
}

.match{
  padding:11px;
  margin:8px 0;
  border-radius:14px;
  background:rgba(255,255,255,.045);
  border:1px solid var(--line);
}

.match small{
  color:var(--muted);
}

.game-board{
  min-height:430px;
  position:relative;
  overflow:hidden;
  border-radius:25px;
  border:1px solid var(--line);
  background:#050a16;
}

.target{
  position:absolute;
  width:50px;
  height:50px;
  border-radius:50%;
  display:grid;
  place-items:center;
  background:radial-gradient(circle at 35% 30%,#fff,var(--accent),var(--accent2));
  box-shadow:0 0 30px rgba(0,217,255,.7);
  cursor:pointer;
  user-select:none;
}

.memory-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:9px;
  max-width:430px;
  margin:auto;
}

.memory-card{
  aspect-ratio:1;
  display:grid;
  place-items:center;
  border-radius:15px;
  font-size:25px;
  background:linear-gradient(135deg,#111b36,#18254a);
  border:1px solid var(--line);
}

.memory-card.open{
  background:linear-gradient(135deg,rgba(0,217,255,.22),rgba(124,60,255,.28));
}

.tic{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  max-width:330px;
  margin:auto;
}

.tic button{
  aspect-ratio:1;
  color:white;
  font-size:40px;
  background:rgba(255,255,255,.04);
  border:1px solid var(--line);
}

.snake-board{
  position:relative;
  width:min(400px,100%);
  aspect-ratio:1;
  margin:auto;
  background:
    linear-gradient(rgba(255,255,255,.04) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,255,255,.04) 1px,transparent 1px),
    #050b18;
  background-size:20px 20px;
}

.snake-cell{
  position:absolute;
  width:20px;
  height:20px;
  background:var(--accent);
  box-shadow:0 0 10px var(--accent);
}

.mini-keypad{
  display:grid;
  grid-template-columns:repeat(3,70px);
  justify-content:center;
  gap:8px;
}

.mini-keypad button{
  height:55px;
  border-radius:14px;
  color:white;
  background:rgba(255,255,255,.07);
  border:1px solid var(--line);
}

.typing-text{
  padding:18px;
  border-radius:18px;
  background:rgba(255,255,255,.04);
  line-height:2;
  font-size:18px;
}

.footer{
  margin-top:35px;
  text-align:center;
  color:var(--muted);
  font-size:11px;
  line-height:1.8;
}

.hidden{
  display:none!important;
}

@media(max-width:750px){
  .chat{
    grid-template-columns:1fr;
  }

  .chat-list{
    border-left:0;
    border-bottom:1px solid var(--line);
    padding:0 0 10px;
    max-height:130px;
  }

  .tournament-bracket{
    grid-template-columns:repeat(4,180px);
  }
}
</style>
</head>

<body>

<div class="bg-orb orb1"></div>
<div class="bg-orb orb2"></div>
<div class="grid-bg"></div>

<div class="toast" id="toast">🎉 تم!</div>

<div class="app">

<header class="topbar">
  <div class="brand">
    <div class="logo">F</div>
    <div class="brand-text">
      <h1>FINI REWARDS</h1>
      <span>Gaming • Rewards • AI • Esport</span>
    </div>
  </div>

  <div class="points-pill">
    <div class="big-diamond">💎</div>
    <strong id="topPoints">100</strong>
    <span>PTS</span>
  </div>

  <div class="top-actions">
    <button class="icon-btn" onclick="navigate('notifications')" title="Notifications">🔔</button>
    <button class="icon-btn" onclick="navigate('settings')" title="Settings">⚙️</button>
  </div>
</header>

<!-- HOME -->
<section class="page active" id="page-home">

  <div class="hero">
    <div class="hero-content">
      <div class="kicker">FINI GAMING ECOSYSTEM</div>
      <h2>
        مرحبا بك في
        <span class="gradient-text">FINI</span>
      </h2>
      <p>
        جمع النقاط، لعب الألعاب، تدوير العجلة، شارك في البطولات،
        استعمل FINI AI، تواصل مع أصدقائك وبدّل نقاطك بمكافآت.
      </p>

      <div class="hero-actions">
        <button class="btn primary" onclick="navigate('tasks')">🎯 جمع النقاط</button>
        <button class="btn gold" onclick="navigate('games')">🎮 العب الآن</button>
        <button class="btn" onclick="navigate('rewards')">🎁 المكافآت</button>
      </div>
    </div>

    <div style="
      position:absolute;
      left:30px;
      bottom:10px;
      opacity:.95;
    ">
      <div class="jewel-3d-wrap">
        <div class="jewel-3d">💎</div>
      </div>
    </div>
  </div>

  <div class="grid grid-4" style="margin-top:14px">

    <div class="card">
      <div class="stat">
        <div>
          <span>FINI Points</span>
          <strong id="homePoints">100</strong>
        </div>
        <div class="stat-icon">💎</div>
      </div>
    </div>

    <div class="card">
      <div class="stat">
        <div>
          <span>Level</span>
          <strong id="homeLevel">1</strong>
        </div>
        <div class="stat-icon">⭐</div>
      </div>
    </div>

    <div class="card">
      <div class="stat">
        <div>
          <span>الألعاب</span>
          <strong id="gameCountStat">100+</strong>
        </div>
        <div class="stat-icon">🎮</div>
      </div>
    </div>

    <div class="card">
      <div class="stat">
        <div>
          <span>Ads</span>
          <strong id="homeAds">0</strong>
        </div>
        <div class="stat-icon">📺</div>
      </div>
    </div>

  </div>

  <div class="grid grid-2" style="margin-top:14px">

    <div class="card points-card">
      <div>
        <span class="muted small">رصيدك الحالي</span>

        <div class="points-main">
          <strong id="pointsLarge">100</strong>
          <div class="big-diamond">💎</div>
          <span class="muted">FINI</span>
        </div>

        <div class="progress">
          <i id="xpProgress" style="width:10%"></i>
        </div>

        <span class="muted small" id="xpText">XP 100 / 1000</span>
      </div>

      <div class="home-streak">
        🔥
        <div>
          <strong id="streakHome">7 أيام</strong>
          <small>Streak ديالك</small>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="section-title" style="margin-top:0">
        <h3>⚡ Quick Actions</h3>
      </div>

      <div class="grid grid-2">
        <button class="btn" onclick="watchRewardedAd()">📺 إعلان +25</button>
        <button class="btn" onclick="openPromo()">🎟️ Promo</button>
        <button class="btn" onclick="navigate('wheel')">🎡 Wheel</button>
        <button class="btn" onclick="navigate('esport')">🏆 Esport</button>
      </div>
    </div>

  </div>

  <div class="section-title">
    <div>
      <h2>🚀 FINI Ecosystem</h2>
      <span>كلشي فبلاصة وحدة</span>
    </div>
  </div>

  <div class="grid grid-4">

    <button class="card" onclick="navigate('ai')" style="text-align:right">
      <div class="stat-icon">🤖</div>
      <h3>FINI AI</h3>
      <span class="muted">AI Assistant + Screenshot</span>
    </button>

    <button class="card" onclick="navigate('video')" style="text-align:right">
      <div class="stat-icon">🎬</div>
      <h3>AI Video</h3>
      <span class="muted">7000 PTS + 20 Ads</span>
    </button>

    <button class="card" onclick="navigate('voice')" style="text-align:right">
      <div class="stat-icon">🎙️</div>
      <h3>AI Voice</h3>
      <span class="muted">Text → Voice</span>
    </button>

    <button class="card" onclick="navigate('chat')" style="text-align:right">
      <div class="stat-icon">💬</div>
      <h3>FINI Chat</h3>
      <span class="muted">Friends + Groups + Bot</span>
    </button>

  </div>

</section>

<!-- TASKS -->
<section class="page" id="page-tasks">

  <div class="section-title">
    <div>
      <h2>🎯 Tasks Center</h2>
      <span>جمع النقاط من المهام</span>
    </div>

    <button class="btn small primary" onclick="watchRewardedAd()">📺 إعلان +25</button>
  </div>

  <div class="grid grid-3" id="tasksGrid"></div>

</section>

<!-- GAMES -->
<section class="page" id="page-games">

  <div class="section-title">
    <div>
      <h2>🎮 FINI Games</h2>
      <span id="gamesSubtitle">100+ لعبة قابلة للعب</span>
    </div>

    <div class="search-box">
      <b>🔎</b>
      <input
        id="gameSearch"
        class="input"
        placeholder="قلب على لعبة..."
        oninput="renderGames()">
    </div>
  </div>

  <div class="filter-row" id="gameFilters"></div>

  <div class="grid grid-4" id="gamesGrid"></div>

</section>

<!-- WHEEL -->
<section class="page" id="page-wheel">

  <div class="section-title">
    <div>
      <h2>🎡 FINI Lucky Wheel</h2>
      <span>5 Spins كل نهار</span>
    </div>

    <div class="badge">
      🎟️ <b id="spinsLeft">5</b>
    </div>
  </div>

  <div class="grid grid-2">

    <div class="card">
      <div class="wheel">
        <div class="wheel-pointer"></div>
        <div class="wheel-inner" id="wheelInner"></div>
      </div>

      <button
        id="spinButton"
        class="btn primary full"
        onclick="spinWheel()">
        🎡 DORE LA ROUE
      </button>

      <button
        class="btn full"
        style="margin-top:8px"
        onclick="watchAdForSpin()">
        📺 شاهد إعلان وخذ Spin إضافي
      </button>
    </div>

    <div class="card">
      <h3>🎁 الجوائز</h3>

      <div class="timeline">
        <div class="timeline-item">
          <i class="timeline-dot"></i>
          <div><b>+10 PTS</b><br><span class="muted">جائزة صغيرة</span></div>
        </div>

        <div class="timeline-item">
          <i class="timeline-dot"></i>
          <div><b>+25 PTS</b><br><span class="muted">Bonus</span></div>
        </div>

        <div class="timeline-item">
          <i class="timeline-dot"></i>
          <div><b>+50 PTS</b><br><span class="muted">Rare</span></div>
        </div>

        <div class="timeline-item">
          <i class="timeline-dot"></i>
          <div><b>+100 PTS</b><br><span class="muted">Epic</span></div>
        </div>

        <div class="timeline-item">
          <i class="timeline-dot"></i>
          <div><b>+250 PTS</b><br><span class="muted">Legendary</span></div>
        </div>
      </div>
    </div>

  </div>

</section>

<!-- REWARDS -->
<section class="page" id="page-rewards">

  <div class="section-title">
    <div>
      <h2>🎁 Rewards</h2>
      <span>بدّل نقاطك</span>
    </div>
  </div>

  <div class="grid grid-3" id="rewardsGrid"></div>

</section>

<!-- STORE -->
<section class="page" id="page-store">

  <div class="section-title">
    <div>
      <h2>🛒 FINI Store</h2>
      <span>Game Top-Up & Packages</span>
    </div>
  </div>

  <div class="alert success">
    📱 الطلبات الحقيقية يمكن ربطها بواتساب:
    <b>+212 634 840119</b>
  </div>

  <div class="grid grid-3" id="storeGrid" style="margin-top:14px"></div>

</section>

<!-- ESPORT -->
<section class="page" id="page-esport">

  <div class="section-title">
    <div>
      <h2>🏆 FINI ESPORT</h2>
      <span>بطولات وتنظيم تلقائي للمباريات</span>
    </div>
  </div>

  <div class="grid grid-2">

    <div class="card">
      <h3>⚙️ Tournament Setup</h3>

      <label class="field">
        <span>عدد اللاعبين</span>
        <select class="select" id="tourPlayers">
          <option value="100">100 Players</option>
          <option value="1000">1000 Players</option>
          <option value="2000">2000 Players</option>
        </select>
      </label>

      <label class="field">
        <span>وقت أول Match</span>
        <input class="input" type="datetime-local" id="tourStart">
      </label>

      <label class="field">
        <span>المدة بين المباريات بالدقائق</span>
        <input class="input" type="number" id="tourInterval" value="15" min="1">
      </label>

      <label class="field">
        <span>إعلانات قبل اللعب</span>
        <input class="input" type="number" id="tourAds" value="3" min="0">
      </label>

      <button class="btn primary full" onclick="generateTournament()">
        🏆 Generate Tournament
      </button>
    </div>

    <div class="card">
      <h3>📊 Tournament Status</h3>
      <div id="tourStats" class="alert">
        مازال ما كاين حتى Tournament.
      </div>
    </div>

  </div>

  <div class="card" style="margin-top:14px">
    <h3>🎯 Bracket</h3>
    <div id="bracket" class="tournament-bracket">
      <div class="muted">Generate Tournament باش يبان الـBracket.</div>
    </div>
  </div>

</section>

<!-- AI -->
<section class="page" id="page-ai">

  <div class="hero" style="min-height:220px">
    <div class="hero-content">
      <div class="kicker">FINI ARTIFICIAL INTELLIGENCE</div>
      <h2><span class="gradient-text">FINI AI</span></h2>
      <p>
        مساعد AI تجريبي داخل التطبيق + Screenshot Evaluator.
        الربط مع API حقيقي يمكن إضافته من Developer Panel.
      </p>
    </div>
  </div>

  <div class="grid grid-2" style="margin-top:14px">

    <div class="card">
      <h3>🤖 AI Assistant</h3>

      <label class="field">
        <span>شنو بغيتي تسول FINI AI؟</span>
        <textarea
          class="textarea"
          id="aiPrompt"
          placeholder="مثلاً: عطيني فكرة لمهمة جديدة..."></textarea>
      </label>

      <button class="btn primary full" onclick="askFiniAI()">
        🤖 Ask FINI AI
      </button>

      <div id="aiResponse" class="alert" style="margin-top:12px">
        FINI AI واجد يسمع ليك.
      </div>
    </div>

    <div class="card">
      <h3>📸 Screenshot Evaluator</h3>

      <label class="file-drop">
        <input type="file" accept="image/*" onchange="handleAIScreenshot(this)">
        <div>
          <div style="font-size:40px">📸</div>
          <b>اضغط واختار Screenshot</b>
          <div class="muted small">Demo evaluator</div>
        </div>
      </label>

      <div id="aiScreenshotResult" class="alert" style="margin-top:12px">
        مازال ما رفعت حتى صورة.
      </div>
    </div>

  </div>

</section>

<!-- AI VIDEO -->
<section class="page" id="page-video">

  <div class="section-title">
    <div>
      <h2>🎬 FINI AI VIDEO</h2>
      <span>Video Generator</span>
    </div>
  </div>

  <div id="videoLockArea"></div>

  <div id="videoStudio" class="hidden">

    <div class="grid grid-2">

      <div class="card">
        <h3>🎬 Create Video</h3>

        <label class="field">
          <span>Prompt</span>
          <textarea
            class="textarea"
            id="videoPrompt"
            placeholder="مثلاً: Free Fire cinematic gaming intro..."></textarea>
        </label>

        <label class="field">
          <span>Style</span>
          <select class="select" id="videoStyle">
            <option>Gaming Cinematic</option>
            <option>Luxury</option>
            <option>Anime</option>
            <option>Cyberpunk</option>
            <option>Realistic</option>
            <option>3D</option>
          </select>
        </label>

        <div class="grid grid-2">
          <label class="field">
            <span>Duration</span>
            <select class="select" id="videoDuration">
              <option>5s</option>
              <option>10s</option>
              <option>15s</option>
              <option>30s</option>
            </select>
          </label>

          <label class="field">
            <span>Aspect Ratio</span>
            <select class="select" id="videoRatio">
              <option>16:9</option>
              <option>9:16</option>
              <option>1:1</option>
            </select>
          </label>
        </div>

        <label class="file-drop">
          <input type="file" accept="image/*" onchange="previewVideoImage(this)">
          <div>
            🖼️
            <br>
            Upload Reference Image
          </div>
        </label>

        <button
          class="btn primary full"
          style="margin-top:12px"
          onclick="generateVideoDemo()">
          ✨ Generate Video
        </button>
      </div>

      <div class="card">
        <h3>🎞️ Preview</h3>

        <div id="videoPreview" class="ai-preview">
          <div>
            <div style="font-size:55px">🎬</div>
            <b>Video Preview</b>
            <p class="muted small">
              Generation هنا Demo فقط.
            </p>
          </div>
        </div>

        <div class="progress">
          <i id="videoProgress"></i>
        </div>

        <div id="videoStatus" class="muted small">
          جاهز.
        </div>
      </div>

    </div>

    <div class="card" style="margin-top:14px">
      <h3>🕘 Generation History</h3>
      <div id="videoHistory"></div>
    </div>

  </div>

</section>

<!-- AI VOICE -->
<section class="page" id="page-voice">

  <div class="section-title">
    <div>
      <h2>🎙️ FINI AI VOICE</h2>
      <span>Text → Voice</span>
    </div>
  </div>

  <div class="grid grid-2">

    <div class="card">
      <h3>🎙️ Voice Studio</h3>

      <label class="field">
        <span>النص</span>
        <textarea
          id="voiceText"
          class="textarea"
          placeholder="كتب النص اللي بغيتي تسمعو..."></textarea>
      </label>

      <div class="grid grid-2">

        <label class="field">
          <span>Voice</span>
          <select id="voiceSelect" class="select">
            <option>FINI Male</option>
            <option>FINI Female</option>
            <option>Gaming Voice</option>
            <option>Cinematic Voice</option>
          </select>
        </label>

        <label class="field">
          <span>Language</span>
          <select id="voiceLanguage" class="select">
            <option>Arabic</option>
            <option>French</option>
            <option>English</option>
            <option>Darija</option>
          </select>
        </label>

        <label class="field">
          <span>Speed</span>
          <input id="voiceSpeed" class="input" type="range" min=".5" max="2" step=".1" value="1">
        </label>

        <label class="field">
          <span>Pitch</span>
          <input id="voicePitch" class="input" type="range" min=".5" max="2" step=".1" value="1">
        </label>

      </div>

      <div class="grid grid-2">
        <button class="btn primary" onclick="generateVoiceDemo()">🎙️ Generate</button>
        <button class="btn" onclick="speakVoice()">🔊 Preview</button>
      </div>

      <div id="voiceStatus" class="alert" style="margin-top:12px">
        جاهز.
      </div>

    </div>

    <div class="card">
      <h3>🕘 Voice History</h3>
      <div id="voiceHistory"></div>
    </div>

  </div>

</section>

<!-- PROFILE -->
<section class="page" id="page-profile">

  <div class="card">

    <div class="profile-head">
      <img
        id="profileAvatar"
        class="avatar big"
        src="https://picsum.photos/300/300?random=77"
        alt="profile">

      <div style="flex:1">
        <h2 id="profileName">AMINE</h2>
        <div class="muted">FINI Member • <span class="online-dot"></span> Online</div>

        <div style="margin-top:8px">
          <span class="badge unlocked">👑 VIP+</span>
          <span class="badge">🎮 Gamer</span>
        </div>
      </div>

      <div class="level-ring">
        <strong id="profileLevel">1</strong>
      </div>
    </div>

    <div class="grid grid-4" style="margin-top:20px">

      <div>
        <span class="muted small">Points</span>
        <div class="stat-big" id="profilePoints">100</div>
      </div>

      <div>
        <span class="muted small">XP</span>
        <div class="stat-big" id="profileXP">100</div>
      </div>

      <div>
        <span class="muted small">Streak</span>
        <div class="stat-big">🔥7</div>
      </div>

      <div>
        <span class="muted small">Badges</span>
        <div class="stat-big" id="badgeCount">4</div>
      </div>

    </div>

    <div class="hero-actions">
      <button class="btn" onclick="changeAvatar()">🖼️ Change Photo</button>
      <button class="btn primary" onclick="navigate('ai')">🤖 FINI AI</button>
      <button class="btn gold" onclick="navigate('vip')">👑 VIP+</button>
    </div>

  </div>

  <div class="section-title">
    <div>
      <h2>🏅 Badges</h2>
      <span>Achievements</span>
    </div>
  </div>

  <div class="grid grid-4" id="badgesGrid"></div>

</section>

<!-- VIP -->
<section class="page" id="page-vip">

  <div class="section-title">
    <div>
      <h2>👑 FINI VIP</h2>
      <span>Premium Membership</span>
    </div>
  </div>

  <div class="grid grid-2">

    <div class="card">
      <div class="badge unlocked">⭐ VIP</div>
      <h2>FINI VIP</h2>

      <ul class="muted">
        <li>+20% Task Bonus</li>
        <li>+1 Daily Wheel Spin</li>
        <li>VIP Profile Frame</li>
        <li>Exclusive Tasks</li>
        <li>VIP Badge</li>
      </ul>

      <button class="btn gold full" onclick="activateVip('VIP')">
        💳 Activate VIP
      </button>
    </div>

    <div class="card" style="
      background:
        radial-gradient(circle at top right,rgba(255,213,74,.15),transparent 35%),
        radial-gradient(circle at bottom left,rgba(124,60,255,.16),transparent 35%),
        var(--card);
    ">
      <div class="badge unlocked">👑 VIP+</div>
      <h2>FINI VIP+</h2>

      <ul class="muted">
        <li>+50% Task Bonus</li>
        <li>+3 Wheel Spins</li>
        <li>Exclusive Aura</li>
        <li>Priority Rewards</li>
        <li>👑 VIP+ Badge</li>
      </ul>

      <button class="btn gold full" onclick="activateVip('VIP+')">
        👑 Activate VIP+
      </button>
    </div>

  </div>

</section>

<!-- CHAT -->
<section class="page" id="page-chat">

  <div class="section-title">
    <div>
      <h2>💬 FINI Chat</h2>
      <span>Friends • Groups • FINI Bot</span>
    </div>
  </div>

  <div class="card chat">

    <aside class="chat-list">

      <div class="tabs">
        <button class="tab active" onclick="chatTab(this,'friends')">Friends</button>
        <button class="tab" onclick="chatTab(this,'groups')">Groups</button>
        <button class="tab" onclick="chatTab(this,'bot')">🤖 Bot</button>
      </div>

      <div id="chatContacts"></div>

    </aside>

    <main class="chat-window">

      <div class="chat-header">
        <b id="chatTitle">FINI Bot 🤖</b>
        <div class="muted small">Online • Typing enabled</div>
      </div>

      <div class="messages" id="messages"></div>

      <div class="chat-input">
        <input
          class="input"
          id="chatInput"
          placeholder="كتب رسالة أو @fini ..."
          onkeydown="if(event.key==='Enter')sendChat()">

        <button class="btn primary" onclick="sendChat()">➤</button>
        <button class="btn" onclick="sendBotCommand()">🤖</button>
      </div>

    </main>

  </div>

</section>

<!-- FRIENDS -->
<section class="page" id="page-friends">

  <div class="section-title">
    <div>
      <h2>👥 Friends & Groups</h2>
      <span>Network</span>
    </div>
  </div>

  <div class="tabs">
    <button class="tab active" onclick="friendsTab(this,'friends')">Friends</button>
    <button class="tab" onclick="friendsTab(this,'requests')">Requests</button>
    <button class="tab" onclick="friendsTab(this,'groups')">Groups</button>
  </div>

  <div class="grid grid-3" id="friendsGrid"></div>

</section>

<!-- SETTINGS -->
<section class="page" id="page-settings">

  <div class="section-title">
    <div>
      <h2>⚙️ Settings</h2>
      <span>كل الإعدادات</span>
    </div>
  </div>

  <div class="grid grid-2">

    <div class="card">

      <h3>🎨 Appearance</h3>

      <div class="switch-row">
        <div>
          <b>Dark Mode</b>
          <div class="muted small">المظهر الليلي</div>
        </div>

        <label class="switch">
          <input
            id="darkMode"
            type="checkbox"
            checked
            onchange="toggleDark(this.checked)">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Animations</b>
          <div class="muted small">3D + Aura + Effects</div>
        </div>

        <label class="switch">
          <input
            id="animations"
            type="checkbox"
            checked
            onchange="toggleAnimations(this.checked)">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Notifications</b>
          <div class="muted small">الإشعارات</div>
        </div>

        <label class="switch">
          <input
            id="notifications"
            type="checkbox"
            checked
            onchange="setSetting('notifications',this.checked)">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Sounds</b>
          <div class="muted small">أصوات التفاعل</div>
        </div>

        <label class="switch">
          <input
            id="sounds"
            type="checkbox"
            checked
            onchange="setSetting('sounds',this.checked)">
          <i></i>
        </label>
      </div>

      <label class="field" style="margin-top:15px">
        <span>Font Size</span>
        <input
          id="fontSize"
          type="range"
          min=".85"
          max="1.2"
          step=".05"
          value="1"
          onchange="setScale(this.value)">
      </label>

    </div>

    <div class="card">

      <h3>🌍 Language</h3>

      <label class="field">
        <span>Language</span>
        <select
          class="select"
          id="languageSelect"
          onchange="changeLanguage(this.value)">
          <option value="ar">العربية</option>
          <option value="fr">Français</option>
          <option value="en">English</option>
        </select>
      </label>

      <div class="alert">
        بعض الصفحات تعتمد حالياً على واجهة عربية، ويمكن إضافة ترجمة كاملة
        من Developer Panel.
      </div>

      <h3 style="margin-top:20px">🔐 Account</h3>

      <button class="btn full" onclick="openAccountModal()">👤 Account Settings</button>

      <button
        class="btn full"
        style="margin-top:8px"
        onclick="exportData()">
        💾 Export Data
      </button>

      <button
        class="btn full"
        style="margin-top:8px"
        onclick="importData()">
        📥 Import Data
      </button>

    </div>

    <div class="card">

      <h3>🛡️ Privacy & Security</h3>

      <div class="switch-row">
        <div>
          <b>Online Status</b>
          <div class="muted small">إظهار Online</div>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            checked
            onchange="setSetting('online',this.checked)">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Typing Status</b>
          <div class="muted small">إظهار Typing</div>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            checked
            onchange="setSetting('typing',this.checked)">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Confirm Actions</b>
          <div class="muted small">تأكيد العمليات المهمة</div>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            checked
            onchange="setSetting('confirm',this.checked)">
          <i></i>
        </label>
      </div>

    </div>

    <div class="card">

      <h3>📦 Data & Storage</h3>

      <div class="alert">
        بيانات هذا الإصدار التجريبي مخزنة محلياً في المتصفح.
      </div>

      <button
        class="btn danger full"
        style="margin-top:10px"
        onclick="resetData()">
        🗑️ Reset Demo Data
      </button>

      <button
        class="btn full"
        style="margin-top:8px"
        onclick="requestPersistentStorage()">
        💾 Request Persistent Storage
      </button>

    </div>

  </div>

</section>

<!-- NOTIFICATIONS -->
<section class="page" id="page-notifications">

  <div class="section-title">
    <div>
      <h2>🔔 Notifications</h2>
      <span>آخر النشاطات</span>
    </div>
  </div>

  <div class="card">
    <div class="timeline">

      <div class="timeline-item">
        <i class="timeline-dot"></i>
        <div>
          <b>🎉 مرحبا بك في FINI!</b>
          <div class="muted small">ربحت 100 PTS من Promo amine.</div>
        </div>
      </div>

      <div class="timeline-item">
        <i class="timeline-dot"></i>
        <div>
          <b>🎮 Games Updated</b>
          <div class="muted small">100+ ألعاب جاهزة.</div>
        </div>
      </div>

      <div class="timeline-item">
        <i class="timeline-dot"></i>
        <div>
          <b>🤖 FINI AI</b>
          <div class="muted small">AI Assistant جاهز.</div>
        </div>
      </div>

    </div>
  </div>

</section>

<!-- DEVELOPER -->
<section class="page" id="page-developer">

  <div id="developerGate" class="card dev">

    <div class="section-title" style="margin-top:0">
      <div>
        <h2 class="dev-title">🛠️ Developer Panel</h2>
        <span>Protected Area</span>
      </div>
    </div>

    <div class="alert danger">
      🔒 هذا القسم مخصص للمطور.
    </div>

    <label class="field" style="margin-top:14px">
      <span>Developer Code</span>
      <input
        class="input"
        id="developerCode"
        type="password"
        placeholder="أدخل الكود">
    </label>

    <button class="btn danger full" onclick="unlockDeveloper()">
      🔓 Unlock Developer Panel
    </button>

  </div>

  <div id="developerPanel" class="hidden">

    <div class="card dev">

      <div class="section-title" style="margin-top:0">
        <div>
          <h2 class="dev-title">🛠️ FINI Developer</h2>
          <span>AMINE2010 • Local Admin Console</span>
        </div>

        <button class="btn danger small" onclick="lockDeveloper()">🔒 Lock</button>
      </div>

      <div class="admin-nav" id="adminNav"></div>

      <div id="adminContent"></div>

    </div>

  </div>

</section>

<!-- AUTH -->
<section class="page" id="page-account">

  <div class="hero">
    <div class="hero-content">
      <div class="kicker">FINI ACCOUNT</div>
      <h2>👤 Account</h2>
      <p>
        هذا الإصدار فيه Auth محلي للتجربة.
        Google/Facebook/Phone/Email الحقيقيين يحتاجون Firebase أو Backend.
      </p>

      <div class="hero-actions">
        <button class="btn primary" onclick="openAccountModal()">🔐 Login</button>
        <button class="btn" onclick="openAccountModal(true)">➕ Create Account</button>
      </div>
    </div>
  </div>

</section>

<footer class="footer">
  FINI REWARDS • Gaming • Rewards • AI • Esport<br>
  WhatsApp News:
  <a href="https://whatsapp.com/channel/0029Vb92w7UFnSzEmCy4MP3o" target="_blank">
    Channel
  </a>
  • Instagram:
  <a href="https://www.instagram.com/fini_app_2k" target="_blank">
    @fini_app_2k
  </a>
  • YouTube:
  <a href="https://youtube.com/@fini_app" target="_blank">
    FINI APP
  </a>
</footer>

</div>

<!-- BOTTOM NAV -->
<nav class="bottom-nav">

  <button class="nav-btn active" data-page="home" onclick="navigate('home')">
    <b>🏠</b>
    Home
  </button>

  <button class="nav-btn" data-page="tasks" onclick="navigate('tasks')">
    <b>🎯</b>
    Tasks
  </button>

  <button class="nav-btn" data-page="games" onclick="navigate('games')">
    <b>🎮</b>
    Games
  </button>

  <button class="nav-btn" data-page="rewards" onclick="navigate('rewards')">
    <b>🎁</b>
    Rewards
  </button>

  <button class="nav-btn" data-page="profile" onclick="navigate('profile')">
    <b>👤</b>
    Profile
  </button>

</nav>

<!-- MODAL -->
<div class="modal" id="modal">
  <div class="modal-box" id="modalContent"></div>
</div>

<script>
"use strict";

/* =========================================================
   FINI REWARDS
   SINGLE FILE APP
   Developer Code: AMINE2010
   Promo: amine = 100 points once
   AI Video: 7000 points + 20 ads
========================================================= */

const APP_KEY = "FINI_REWARDS_SINGLE_FILE_V1";
const DEV_CODE = "AMINE2010";
const PROMO_CODE = "amine";
const AI_VIDEO_POINTS = 7000;
const AI_VIDEO_ADS = 20;

const WA_ORDER = "https://wa.me/212634840119?s=t";
const WA_CHANNEL = "https://whatsapp.com/channel/0029Vb92w7UFnSzEmCy4MP3o";
const INSTAGRAM = "https://www.instagram.com/fini_app_2k";
const YOUTUBE = "https://youtube.com/@fini_app";

let state = {
  points:100,
  xp:100,
  level:1,
  ads:0,
  streak:7,
  promoUsed:false,

  spins:5,
  bonusSpins:0,
  lastSpinDay:"",
  wheelRotation:0,

  vip:false,
  vipPlus:false,

  developer:false,

  settings:{
    dark:true,
    animations:true,
    notifications:true,
    sounds:true,
    online:true,
    typing:true,
    confirm:true,
    language:"ar",
    scale:1
  },

  tasksDone:{},
  messages:[],
  videoHistory:[],
  voiceHistory:[],
  badges:[],
  friends:[],
  requests:[],
  groups:[],

  tournament:null,

  customTasks:[],
  customRewards:[],
  customStore:[],
  customGames:[],

  logs:[],

  ai:{
    botName:"FINI Bot",
    welcome:"سلام! أنا FINI Bot 🤖 كيفاش نقدر نعاونك؟",
    enabled:true
  }
};

function safeLoad(){
  try{
    const raw=localStorage.getItem(APP_KEY);
    if(raw){
      const parsed=JSON.parse(raw);
      state={...state,...parsed};
      state.settings={...{
        dark:true,
        animations:true,
        notifications:true,
        sounds:true,
        online:true,
        typing:true,
        confirm:true,
        language:"ar",
        scale:1
      },...(parsed.settings||{})};
    }
  }catch(e){
    console.warn("Storage unavailable",e);
  }
}

function save(){
  try{
    localStorage.setItem(APP_KEY,JSON.stringify(state));
  }catch(e){
    console.warn("Could not save",e);
  }
}

function log(action,data={}){
  state.logs.unshift({
    time:new Date().toISOString(),
    action,
    data
  });

  state.logs=state.logs.slice(0,300);
  save();
}

function esc(value){
  return String(value ?? "")
    .replaceAll("&","&amp;")
    .replaceAll("<","&lt;")
    .replaceAll(">","&gt;")
    .replaceAll('"',"&quot;")
    .replaceAll("'","&#039;");
}

function showToast(text){
  const t=document.getElementById("toast");
  t.textContent=text;
  t.classList.add("show");

  clearTimeout(showToast.timer);

  showToast.timer=setTimeout(()=>{
    t.classList.remove("show");
  },2200);
}

function navigate(page){

  document.querySelectorAll(".page").forEach(p=>{
    p.classList.remove("active");
  });

  const target=document.getElementById("page-"+page);

  if(target){
    target.classList.add("active");
  }

  document.querySelectorAll(".nav-btn").forEach(b=>{
    b.classList.toggle(
      "active",
      b.dataset.page===page
    );
  });

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });

  if(page==="tasks")renderTasks();
  if(page==="games")renderGames();
  if(page==="rewards")renderRewards();
  if(page==="store")renderStore();
  if(page==="profile")renderProfile();
  if(page==="friends")renderFriends();
  if(page==="chat")renderChat();
  if(page==="wheel")updateWheel();
  if(page==="video")renderVideoLock();
  if(page==="voice")renderVoiceHistory();
  if(page==="developer")renderAdmin();
}

/* =========================================================
   POINTS
========================================================= */

function addPoints(amount,reason=""){
  amount=Number(amount)||0;

  if(amount<=0)return;

  state.points+=amount;
  state.xp+=amount;

  updateLevel();

  log("ADD_POINTS",{
    amount,
    reason
  });

  save();
  updateUI();

  showToast(`💎 +${amount} PTS${reason?` • ${reason}`:""}`);
}

function removePoints(amount,reason=""){
  amount=Number(amount)||0;

  if(amount<=0)return false;

  if(state.points<amount){
    showToast("❌ ماعندكش نقاط كافية");
    return false;
  }

  state.points-=amount;

  log("REMOVE_POINTS",{
    amount,
    reason
  });

  save();
  updateUI();

  return true;
}

function updateLevel(){

  state.level=Math.max(
    1,
    Math.floor(state.xp/1000)+1
  );
}

function updateUI(){

  const ids=[
    ["topPoints",state.points],
    ["homePoints",state.points],
    ["pointsLarge",state.points],
    ["profilePoints",state.points],
    ["profileXP",state.xp],
    ["homeLevel",state.level],
    ["profileLevel",state.level],
    ["homeAds",state.ads],
    ["streakHome",state.streak+" أيام"]
  ];

  ids.forEach(([id,value])=>{
    const el=document.getElementById(id);
    if(el)el.textContent=value;
  });

  const xpInLevel=state.xp%1000;
  const xpPercent=Math.min(100,xpInLevel/10);

  const xpBar=document.getElementById("xpProgress");

  if(xpBar){
    xpBar.style.width=xpPercent+"%";
  }

  const xpText=document.getElementById("xpText");

  if(xpText){
    xpText.textContent=
      `XP ${xpInLevel} / 1000`;
  }

  const badgeCount=document.getElementById("badgeCount");

  if(badgeCount){
    badgeCount.textContent=
      getBadges().filter(b=>b.unlocked).length;
  }

  save();
}

/* =========================================================
   ADS
========================================================= */

function watchRewardedAd(){

  showToast("📺 تشغيل Rewarded Ad تجريبي...");

  setTimeout(()=>{
    state.ads++;
    addPoints(
      state.vipPlus?38:state.vip?30:25,
      "Rewarded Ad"
    );

    showToast("🎁 الإعلان تسالى + نقاط!");

    renderVideoLock();
  },1100);
}

function watchAdForSpin(){

  showToast("📺 شاهد الإعلان...");

  setTimeout(()=>{
    state.ads++;
    state.bonusSpins++;

    save();
    updateWheel();

    showToast("🎡 خديتي Spin إضافي!");
  },1000);
}

/* =========================================================
   PROMO
========================================================= */

function openPromo(){

  openModal(`
    <div class="modal-head">
      <h2>🎟️ Promo Code</h2>
      <button class="close" onclick="closeModal()">×</button>
    </div>

    <label class="field">
      <span>Code</span>
      <input
        class="input"
        id="promoInput"
        placeholder="دخل الكود">
    </label>

    <button
      class="btn primary full"
      onclick="redeemPromo()">
      🎁 Redeem
    </button>

    <div class="alert" style="margin-top:12px">
      Promo الحالي: <b>amine</b> → 100 PTS مرة واحدة.
    </div>
  `);
}

function redeemPromo(){

  const code=
    document.getElementById("promoInput")
    ?.value
    .trim()
    .toLowerCase();

  if(code!==PROMO_CODE){
    showToast("❌ Promo غير صحيح");
    return;
  }

  if(state.promoUsed){
    showToast("⚠️ استعملتي Promo من قبل");
    return;
  }

  state.promoUsed=true;

  addPoints(100,"Promo amine");

  closeModal();
}

/* =========================================================
   TASKS
========================================================= */

const baseTasks=[
  {
    id:"ad1",
    icon:"📺",
    title:"Rewarded Ad",
    desc:"شاهد إعلان كامل",
    points:25,
    action:"ad"
  },
  {
    id:"daily",
    icon:"🔥",
    title:"Daily Login",
    desc:"دخل اليوم للتطبيق",
    points:30,
    action:"daily"
  },
  {
    id:"youtube",
    icon:"▶️",
    title:"YouTube",
    desc:"Subscribe / Watch",
    points:30,
    action:"social"
  },
  {
    id:"instagram",
    icon:"📸",
    title:"Instagram",
    desc:"Follow FINI",
    points:25,
    action:"social"
  },
  {
    id:"facebook",
    icon:"📘",
    title:"Facebook",
    desc:"Follow FINI",
    points:25,
    action:"social"
  },
  {
    id:"whatsapp",
    icon:"🟢",
    title:"WhatsApp",
    desc:"Join channel",
    points:30,
    action:"social"
  },
  {
    id:"game",
    icon:"🎮",
    title:"Play Game",
    desc:"العب لعبة واحدة",
    points:20,
    action:"game"
  },
  {
    id:"wheel",
    icon:"🎡",
    title:"Wheel",
    desc:"دور العجلة",
    points:20,
    action:"wheel"
  },
  {
    id:"profile",
    icon:"👤",
    title:"Complete Profile",
    desc:"كمل البروفايل",
    points:40,
    action:"profile"
  },
  {
    id:"share",
    icon:"📤",
    title:"Share FINI",
    desc:"شارك التطبيق",
    points:30,
    action:"share"
  },
  {
    id:"friend",
    icon:"👥",
    title:"Add Friend",
    desc:"ضيف Friend",
    points:20,
    action:"friend"
  },
  {
    id:"ai",
    icon:"🤖",
    title:"Ask FINI AI",
    desc:"جرب AI",
    points:20,
    action:"ai"
  }
];

function allTasks(){
  return [
    ...baseTasks,
    ...state.customTasks
  ];
}

function renderTasks(){

  const grid=document.getElementById("tasksGrid");

  if(!grid)return;

  grid.innerHTML=allTasks().map(task=>{

    const done=!!state.tasksDone[task.id];

    return `
      <div class="card task-card">

        <div class="task-top">

          <div class="task-icon">
            ${task.icon||"🎯"}
          </div>

          <div class="task-info">
            <strong>${esc(task.title)}</strong>
            <span>${esc(task.desc)}</span>
          </div>

          <div class="reward-points">
            +${task.points}
          </div>

        </div>

        <div class="progress">
          <i style="width:${done?100:0}%"></i>
        </div>

        <button
          class="btn ${done?"":"primary"} full"
          ${done?"disabled":""}
          onclick="runTask('${esc(task.id)}')">

          ${done?"✅ Completed":"🚀 Start Task"}

        </button>

      </div>
    `;
  }).join("");
}

function runTask(id){

  const task=allTasks().find(x=>x.id===id);

  if(!task)return;

  if(state.tasksDone[id]){
    showToast("✅ هاد المهمة تسالات");
    return;
  }

  if(task.action==="ad"){
    watchRewardedAd();
  }

  else if(task.action==="daily"){
    addPoints(task.points,"Daily Login");
  }

  else if(task.action==="social"){

    const links={
      youtube:YOUTUBE,
      instagram:INSTAGRAM,
      whatsapp:WA_CHANNEL
    };

    const url=links[task.id];

    if(url){
      window.open(url,"_blank");
    }

    addPoints(task.points,task.title);
  }

  else if(task.action==="game"){
    navigate("games");
  }

  else if(task.action==="wheel"){
    navigate("wheel");
  }

  else if(task.action==="ai"){
    navigate("ai");
  }

  else{
    addPoints(task.points,task.title);
  }

  state.tasksDone[id]=true;

  save();
  renderTasks();
}

/* =========================================================
   GAMES
========================================================= */

const gameTypes=[
  "reaction",
  "target",
  "memory",
  "math",
  "color",
  "typing",
  "tic",
  "snake",
  "aim",
  "dodge",
  "click",
  "sequence",
  "number",
  "word",
  "speed",
  "catch",
  "avoid",
  "pong",
  "breakout",
  "flappy",
  "maze",
  "mines",
  "2048",
  "connect4",
  "simon"
];

const gameNames=[
  "Neon Reflex",
  "Cyber Aim",
  "Memory Rush",
  "Math Blast",
  "Color Storm",
  "Typing Fury",
  "Tic Tac Arena",
  "Snake Neon",
  "Headshot Trainer",
  "Dodge Laser",
  "Click Master",
  "Sequence X",
  "Number Hunter",
  "Word Scramble",
  "Speed Tap",
  "Catch Diamonds",
  "Avoid Bombs",
  "Mini Pong",
  "Brick Breaker",
  "Flappy Jet",
  "Neon Maze",
  "Mine Hunter",
  "2048 Rush",
  "Connect Arena",
  "Simon Pulse",
  "Diamond Dash",
  "Cyber Runner",
  "Pixel Fighter",
  "Rocket Escape",
  "Laser Dodge",
  "Coin Hunter",
  "Ghost Chase",
  "Zombie Tap",
  "Ninja Reflex",
  "Samurai Strike",
  "Space Shooter",
  "Galaxy Aim",
  "Football Penalty",
  "Goal Keeper",
  "Basket Shot",
  "Boxing Punch",
  "Kart Sprint",
  "Drift Master",
  "Bike Rush",
  "Car Dodge",
  "Plane Escape",
  "Helicopter",
  "Jet Fighter",
  "Astro Jump",
  "Moon Hopper",
  "Star Catch",
  "Fire Ring",
  "Ice Ring",
  "Thunder Tap",
  "Shadow Run",
  "Cyber Snake",
  "Golden Coins",
  "Treasure Hunt",
  "Dungeon Escape",
  "Castle Defense",
  "Robot Fight",
  "Alien Attack",
  "Meteor Dodge",
  "Solar Rush",
  "Lava Jump",
  "Ocean Catch",
  "Fish Escape",
  "Shark Dodge",
  "Pirate Gold",
  "Magic Cards",
  "Card Match",
  "Chess Mini",
  "Checkers Mini",
  "Four In Row",
  "Dots Connect",
  "Quick Sudoku",
  "Word Master",
  "Letter Rush",
  "Emoji Match",
  "Emoji Memory",
  "Pattern Lock",
  "Code Breaker",
  "Safe Cracker",
  "Reaction Pro",
  "Reflex X",
  "Tap Frenzy",
  "Turbo Click",
  "Power Up",
  "Energy Rush",
  "Rocket Tap",
  "Space Tap",
  "Galaxy Defender",
  "Cyber Defender",
  "Fire Defender",
  "Ice Defender",
  "Final Boss",
  "Legend Arena",
  "FINI Challenge"
];

const gameEmojis=[
  "⚡","🎯","🧠","➗","🎨","⌨️","⭕","🐍","🔥","💥",
  "👆","🔢","🔟","🔤","🚀","💎","💣","🏓","🧱","🪽",
  "🧩","💣","🔢","🔴","🎵","💎","🏃","🤖","🚀","⚡",
  "🪙","👻","🧟","🥷","⚔️","🚀","🌌","⚽","🥅","🏀",
  "🥊","🏎️","🏁","🏍️","🚗","✈️","🚁","🛩️","🌙","🌕",
  "⭐","🔥","❄️","⚡","🌑","🐍","🪙","💰","🏰","🛡️",
  "🤖","👽","☄️","☀️","🌋","🌊","🐟","🦈","🏴‍☠️","✨",
  "🃏","🧠","♟️","🔴","4️⃣","🔵","🔢","🔤","🔠","😊",
  "🧠","🔐","🔓","💼","⚡","🎯","👆","🔥","⚡","🚀",
  "🌌","🛡️","🔥","❄️","👹","🏆","🎮"
];

const gameImages=[
  "https://picsum.photos/700/400?random=101",
  "https://picsum.photos/700/400?random=102",
  "https://picsum.photos/700/400?random=103",
  "https://picsum.photos/700/400?random=104",
  "https://picsum.photos/700/400?random=105",
  "https://picsum.photos/700/400?random=106",
  "https://picsum.photos/700/400?random=107",
  "https://picsum.photos/700/400?random=108",
  "https://picsum.photos/700/400?random=109",
  "https://picsum.photos/700/400?random=110"
];

let games=[];

function buildGames(){

  games=[];

  for(let i=0;i<100;i++){

    games.push({
      id:"g"+(i+1),
      index:i,
      name:gameNames[i]||`FINI Game ${i+1}`,
      type:gameTypes[i%gameTypes.length],
      icon:gameEmojis[i%gameEmojis.length],
      image:gameImages[i%gameImages.length],
      reward:10+(i%6)*5,
      category:
        i%5===0?"Action":
        i%5===1?"Arcade":
        i%5===2?"Puzzle":
        i%5===3?"Sports":
        "Skill"
    });
  }

  games=[
    ...games,
    ...state.customGames
  ];

  const stat=document.getElementById("gameCountStat");

  if(stat){
    stat.textContent=games.length+"+";
  }

  const sub=document.getElementById("gamesSubtitle");

  if(sub){
    sub.textContent=
      games.length+"+ لعبة قابلة للعب";
  }
}

function renderGameFilters(){

  const box=document.getElementById("gameFilters");

  if(!box)return;

  const cats=["All","Action","Arcade","Puzzle","Sports","Skill"];

  box.innerHTML=cats.map((cat,i)=>`
    <button
      class="chip ${i===0?"active":""}"
      onclick="filterGames('${cat}',this)">
      ${cat}
    </button>
  `).join("");
}

let activeGameFilter="All";

function filterGames(category,button){

  activeGameFilter=category;

  document.querySelectorAll("#gameFilters .chip")
    .forEach(x=>x.classList.remove("active"));

  button.classList.add("active");

  renderGames();
}

function renderGames(){

  buildGames();

  const grid=document.getElementById("gamesGrid");

  if(!grid)return;

  const search=
    (document.getElementById("gameSearch")?.value||"")
    .trim()
    .toLowerCase();

  const filtered=games.filter(game=>{

    const categoryOk=
      activeGameFilter==="All" ||
      game.category===activeGameFilter;

    const searchOk=
      !search ||
      game.name.toLowerCase().includes(search) ||
      game.type.toLowerCase().includes(search);

    return categoryOk&&searchOk;
  });

  grid.innerHTML=filtered.map(game=>`

    <div class="card game-card">

      <div class="game-cover">
        <img
          src="${esc(game.image)}"
          alt="${esc(game.name)}"
          loading="lazy"
          onerror="this.src='https://picsum.photos/700/400?random=${game.index+500}'">
      </div>

      <div class="task-top">
        <div class="game-icon">${game.icon}</div>

        <div class="task-info">
          <strong>${esc(game.name)}</strong>
          <span>${esc(game.category)} • ${esc(game.type)}</span>
        </div>
      </div>

      <div class="game-meta">
        <span>🏆 +${game.reward} PTS</span>
        <span>🎮 Playable</span>
      </div>

      <div class="game-actions">
        <button
          class="btn primary"
          onclick="playGame('${esc(game.id)}')">
          ▶️ Play
        </button>

        <button
          class="btn"
          onclick="showGameInfo('${esc(game.id)}')">
          ℹ️
        </button>
      </div>

    </div>

  `).join("");

  if(!filtered.length){
    grid.innerHTML=`
      <div class="card" style="grid-column:1/-1;text-align:center">
        ❌ ما لقيتش اللعبة.
      </div>
    `;
  }
}

function showGameInfo(id){

  const game=games.find(g=>g.id===id);

  if(!game)return;

  openModal(`
    <div class="modal-head">
      <h2>${game.icon} ${esc(game.name)}</h2>
      <button class="close" onclick="closeModal()">×</button>
    </div>

    <div class="alert">
      🎮 النوع: <b>${esc(game.type)}</b><br>
      🏆 الربح: <b>+${game.reward} PTS</b><br>
      🧩 Category: <b>${esc(game.category)}</b>
    </div>

    <button
      class="btn primary full"
      style="margin-top:12px"
      onclick="playGame('${esc(game.id)}')">
      ▶️ Play Now
    </button>
  `);
}

function playGame(id){

  const game=games.find(g=>g.id===id);

  if(!game)return;

  openGameModal(game);
}

function openGameModal(game){

  closeModal();

  setTimeout(()=>{

    openModal(`
      <div class="modal-head">
        <h2>${game.icon} ${esc(game.name)}</h2>
        <button class="close" onclick="closeModal()">×</button>
      </div>

      <div class="alert success">
        🎮 لعبة حقيقية داخل الصفحة • ${esc(game.type)}
      </div>

      <div id="gameArea" style="margin-top:12px"></div>
    `);

    initGameEngine(game);

  },50);
}

/* =========================================================
   MINI GAME ENGINE
========================================================= */

function gameWin(game,bonus=0){

  const amount=game.reward+(Number(bonus)||0);

  addPoints(amount,`Played ${game.name}`);

  showToast(`🏆 فزتي فـ ${game.name} +${amount} PTS`);

  setTimeout(closeModal,800);
}

function initGameEngine(game){

  const area=document.getElementById("gameArea");

  if(!area)return;

  switch(game.type){

    case "reaction":
      initReactionGame(area,game);
      break;

    case "target":
    case "aim":
    case "click":
    case "speed":
    case "catch":
      initTargetGame(area,game);
      break;

    case "memory":
      initMemoryGame(area,game);
      break;

    case "math":
    case "number":
      initMathGame(area,game);
      break;

    case "color":
      initColorGame(area,game);
      break;

    case "typing":
    case "word":
      initTypingGame(area,game);
      break;

    case "tic":
      initTicGame(area,game);
      break;

    case "snake":
      initSnakeGame(area,game);
      break;

    case "dodge":
    case "avoid":
      initDodgeGame(area,game);
      break;

    case "sequence":
    case "simon":
      initSequenceGame(area,game);
      break;

    case "maze":
      initMazeGame(area,game);
      break;

    case "2048":
      init2048Game(area,game);
      break;

    case "connect4":
      initConnect4Game(area,game);
      break;

    case "pong":
      initPongGame(area,game);
      break;

    case "breakout":
      initBreakoutGame(area,game);
      break;

    case "flappy":
      initFlappyGame(area,game);
      break;

    default:
      initReactionGame(area,game);
  }
}

/* ---------- Reaction ---------- */

function initReactionGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>⚡ Reaction Test</h3>
      <p class="muted">ضغط ملي يتحول الزر للأخضر.</p>

      <button
        id="reactionBtn"
        class="btn danger full"
        style="height:180px;font-size:28px"
        onclick="reactionClick()">
        WAIT...
      </button>

      <div id="reactionResult" class="alert" style="margin-top:10px">
        جاهز.
      </div>
    </div>
  `;

  let ready=false;
  let started=performance.now();

  const timer=setTimeout(()=>{

    const btn=document.getElementById("reactionBtn");

    if(!btn)return;

    ready=true;
    started=performance.now();

    btn.className="btn success full";
    btn.textContent="CLICK NOW!";

  },1000+Math.random()*2500);

  window.reactionClick=function(){

    const btn=document.getElementById("reactionBtn");
    const result=document.getElementById("reactionResult");

    if(!btn)return;

    if(!ready){

      clearTimeout(timer);

      result.textContent="❌ بكريتي! عاود.";
      return;
    }

    const ms=Math.round(performance.now()-started);

    result.textContent=`⚡ Reaction: ${ms}ms`;

    gameWin(game,ms<250?20:ms<450?10:0);
  };
}

/* ---------- Target ---------- */

function initTargetGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🎯 Target Rush</h3>
      <p class="muted">صيد 10 targets بسرعة.</p>

      <div
        id="targetBoard"
        class="game-board">
      </div>

      <div
        class="alert"
        style="margin-top:10px">
        Targets: <b id="targetScore">0</b>/10
      </div>
    </div>
  `;

  let score=0;

  function spawn(){

    const board=document.getElementById("targetBoard");

    if(!board)return;

    const target=document.createElement("div");

    target.className="target";

    target.style.left=
      Math.random()*(board.clientWidth-55)+"px";

    target.style.top=
      Math.random()*(board.clientHeight-55)+"px";

    target.textContent="💎";

    target.onclick=()=>{

      score++;

      document.getElementById("targetScore").textContent=score;

      target.remove();

      if(score>=10){
        gameWin(game);
      }else{
        spawn();
      }
    };

    board.appendChild(target);
  }

  spawn();
}

/* ---------- Memory ---------- */

function initMemoryGame(area,game){

  const symbols=[
    "🔥","💎","⚡","🎮",
    "🚀","👑","🎯","🧠"
  ];

  const cards=[...symbols,...symbols]
    .sort(()=>Math.random()-.5);

  area.innerHTML=`
    <div class="card">
      <h3>🧠 Memory Match</h3>

      <div
        class="memory-grid"
        id="memoryGrid">
      </div>
    </div>
  `;

  const grid=document.getElementById("memoryGrid");

  let opened=[];
  let matched=0;

  cards.forEach((symbol,index)=>{

    const button=document.createElement("button");

    button.className="memory-card";
    button.textContent="❓";

    button.onclick=()=>{

      if(button.classList.contains("open"))return;

      if(opened.length>=2)return;

      button.classList.add("open");
      button.textContent=symbol;

      opened.push({
        button,
        symbol
      });

      if(opened.length===2){

        const [a,b]=opened;

        if(a.symbol===b.symbol){

          matched+=2;
          opened=[];

          if(matched===cards.length){
            gameWin(game);
          }

        }else{

          setTimeout(()=>{

            a.button.classList.remove("open");
            b.button.classList.remove("open");

            a.button.textContent="❓";
            b.button.textContent="❓";

            opened=[];

          },650);
        }
      }
    };

    grid.appendChild(button);
  });
}

/* ---------- Math ---------- */

function initMathGame(area,game){

  let score=0;
  let question=0;

  area.innerHTML=`
    <div class="card">
      <h3>➗ Math Rush</h3>

      <div
        class="ai-preview"
        id="mathQuestion"
        style="font-size:30px">
      </div>

      <input
        id="mathAnswer"
        class="input"
        type="number"
        placeholder="الجواب">

      <button
        class="btn primary full"
        style="margin-top:8px"
        onclick="answerMath()">
        Check
      </button>

      <div
        class="alert"
        id="mathResult"
        style="margin-top:8px">
        0 / 5
      </div>
    </div>
  `;

  let correct=0;

  function next(){

    const a=1+Math.floor(Math.random()*20);
    const b=1+Math.floor(Math.random()*20);
    const op=["+","-","×"][Math.floor(Math.random()*3)];

    let answer;

    if(op==="+")answer=a+b;
    if(op==="-")answer=a-b;
    if(op==="×")answer=a*b;

    window.currentMathAnswer=answer;

    document.getElementById("mathQuestion").textContent=
      `${a} ${op} ${b} = ?`;

    document.getElementById("mathAnswer").value="";
  }

  window.answerMath=function(){

    const input=
      Number(document.getElementById("mathAnswer").value);

    if(input===window.currentMathAnswer){
      correct++;
      score+=10;
    }

    question++;

    document.getElementById("mathResult").textContent=
      `${correct} / 5`;

    if(question>=5){
      gameWin(game,score);
      return;
    }

    next();
  };

  next();
}

/* ---------- Color ---------- */

function initColorGame(area,game){

  const colors=[
    "RED","BLUE","GREEN","YELLOW",
    "PURPLE","ORANGE"
  ];

  let round=0;
  let good=0;

  area.innerHTML=`
    <div class="card">
      <h3>🎨 Color Match</h3>
      <div id="colorQuestion"
        class="ai-preview"
        style="font-size:35px">
      </div>

      <div
        id="colorButtons"
        class="grid grid-3"
        style="margin-top:10px">
      </div>

      <div class="alert" id="colorResult">
        0 / 5
      </div>
    </div>
  `;

  const buttons=document.getElementById("colorButtons");

  colors.forEach(color=>{

    const b=document.createElement("button");

    b.className="btn";

    b.textContent=color;

    b.onclick=()=>{

      if(color===window.colorAnswer)good++;

      round++;

      document.getElementById("colorResult").textContent=
        `${good} / 5`;

      if(round>=5){
        gameWin(game,good*5);
      }else{
        next();
      }
    };

    buttons.appendChild(b);
  });

  function next(){

    const answer=
      colors[Math.floor(Math.random()*colors.length)];

    window.colorAnswer=answer;

    const text=
      colors[Math.floor(Math.random()*colors.length)];

    const q=document.getElementById("colorQuestion");

    q.textContent=text;

    q.style.color=
      answer==="RED"?"#ff3d71":
      answer==="BLUE"?"#00d9ff":
      answer==="GREEN"?"#36f59a":
      answer==="YELLOW"?"#ffd54a":
      answer==="PURPLE"?"#a56cff":
      "#ff8b2c";
  }

  next();
}

/* ---------- Typing ---------- */

function initTypingGame(area,game){

  const text=
    "FINI rewards gaming AI esport and fun";

  area.innerHTML=`
    <div class="card">
      <h3>⌨️ Typing Fury</h3>

      <div class="typing-text">
        ${text}
      </div>

      <textarea
        id="typingInput"
        class="textarea"
        placeholder="كتب النص هنا..."></textarea>

      <button
        class="btn primary full"
        onclick="checkTyping()">
        Check
      </button>

      <div id="typingResult" class="alert">
        جاهز.
      </div>
    </div>
  `;

  window.checkTyping=function(){

    const value=
      document.getElementById("typingInput").value.trim();

    const score=
      value===text ? 30 :
      value.length>text.length*.7 ? 10 : 0;

    document.getElementById("typingResult").textContent=
      `Score: ${score}`;

    if(score>0)gameWin(game,score);
  };
}

/* ---------- Tic Tac Toe ---------- */

function initTicGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>⭕ Tic Tac Toe</h3>
      <div class="tic" id="ticBoard"></div>
      <div id="ticStatus" class="alert" style="margin-top:10px">
        دورك: X
      </div>
    </div>
  `;

  const board=document.getElementById("ticBoard");
  const cells=Array(9).fill("");
  let turn="X";
  let over=false;

  function render(){

    board.innerHTML="";

    cells.forEach((value,i)=>{

      const b=document.createElement("button");

      b.textContent=value;

      b.onclick=()=>{

        if(over||cells[i])return;

        cells[i]=turn;

        if(checkWin(turn)){

          over=true;

          document.getElementById("ticStatus")
            .textContent=turn==="X"
              ?"🏆 فزتي!"
              :"🤖 Bot فاز";

          if(turn==="X")gameWin(game);

          return;
        }

        if(cells.every(Boolean)){

          over=true;

          document.getElementById("ticStatus")
            .textContent="🤝 Draw";

          return;
        }

        turn="O";

        render();

        setTimeout(bot,300);
      };

      board.appendChild(b);
    });
  }

  function bot(){

    if(over)return;

    const empty=cells
      .map((v,i)=>v?null:i)
      .filter(v=>v!==null);

    if(!empty.length)return;

    const i=empty[Math.floor(Math.random()*empty.length)];

    cells[i]="O";

    if(checkWin("O")){

      over=true;

      document.getElementById("ticStatus")
        .textContent="🤖 Bot فاز";

      render();

      return;
    }

    turn="X";

    render();
  }

  function checkWin(p){

    const combos=[
      [0,1,2],
      [3,4,5],
      [6,7,8],
      [0,3,6],
      [1,4,7],
      [2,5,8],
      [0,4,8],
      [2,4,6]
    ];

    return combos.some(c=>
      c.every(i=>cells[i]===p)
    );
  }

  render();
}

/* ---------- Snake ---------- */

function initSnakeGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🐍 Snake Neon</h3>

      <div
        class="snake-board"
        id="snakeBoard">
      </div>

      <div
        class="mini-keypad"
        style="margin-top:10px">

        <span></span>

        <button onclick="snakeDir(0,-1)">⬆️</button>

        <span></span>

        <button onclick="snakeDir(-1,0)">⬅️</button>
        <button onclick="snakeDir(0,1)">⬇️</button>
        <button onclick="snakeDir(1,0)">➡️</button>

      </div>

      <div id="snakeScore" class="alert">
        Score: 0
      </div>
    </div>
  `;

  const board=document.getElementById("snakeBoard");

  let snake=[
    {x:10,y:10},
    {x:9,y:10},
    {x:8,y:10}
  ];

  let food={
    x:15,
    y:15
  };

  let dir={
    x:1,
    y:0
  };

  let score=0;
  let running=true;

  window.snakeDir=function(x,y){

    if(x===-dir.x&&y===-dir.y)return;

    dir={x,y};
  };

  function draw(){

    board.innerHTML="";

    snake.forEach(part=>{

      const d=document.createElement("i");

      d.className="snake-cell";

      d.style.left=(part.x*20)+"px";
      d.style.top=(part.y*20)+"px";

      board.appendChild(d);
    });

    const f=document.createElement("i");

    f.className="snake-cell";

    f.style.background="#ff3d71";
    f.style.boxShadow="0 0 15px #ff3d71";
    f.style.left=(food.x*20)+"px";
    f.style.top=(food.y*20)+"px";

    board.appendChild(f);
  }

  function loop(){

    if(!running)return;

    const head={
      x:snake[0].x+dir.x,
      y:snake[0].y+dir.y
    };

    if(
      head.x<0 ||
      head.y<0 ||
      head.x>=20 ||
      head.y>=20 ||
      snake.some(s=>s.x===head.x&&s.y===head.y)
    ){

      running=false;

      if(score>=3){
        gameWin(game,score*3);
      }else{
        showToast("💥 Game Over");
      }

      return;
    }

    snake.unshift(head);

    if(head.x===food.x&&head.y===food.y){

      score++;

      document.getElementById("snakeScore")
        .textContent=`Score: ${score}`;

      food={
        x:Math.floor(Math.random()*20),
        y:Math.floor(Math.random()*20)
      };

      if(score>=10){
        running=false;
        gameWin(game,30);
        return;
      }

    }else{
      snake.pop();
    }

    draw();
  }

  document.addEventListener("keydown",window.__snakeKey=(e)=>{

    if(e.key==="ArrowUp")snakeDir(0,-1);
    if(e.key==="ArrowDown")snakeDir(0,1);
    if(e.key==="ArrowLeft")snakeDir(-1,0);
    if(e.key==="ArrowRight")snakeDir(1,0);

  });

  draw();

  window.__snakeTimer=setInterval(loop,120);
}

/* ---------- Dodge ---------- */

function initDodgeGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>💥 Dodge Arena</h3>

      <div
        class="game-board"
        id="dodgeBoard">

        <div
          id="dodgePlayer"
          style="
            position:absolute;
            bottom:20px;
            left:50%;
            width:45px;
            height:45px;
            border-radius:14px;
            background:linear-gradient(135deg,#00d9ff,#7c3cff);
            box-shadow:0 0 25px #00d9ff;
          ">
          🧍
        </div>

      </div>

      <div class="mini-keypad" style="margin-top:10px">
        <span></span>
        <button onclick="moveDodge(-1)">⬅️</button>
        <button onclick="moveDodge(1)">➡️</button>
      </div>

      <div class="alert" id="dodgeScore">
        Survive 10 seconds.
      </div>
    </div>
  `;

  const board=document.getElementById("dodgeBoard");
  const player=document.getElementById("dodgePlayer");

  let pos=50;
  let seconds=0;
  let running=true;

  window.moveDodge=function(direction){

    pos+=direction*8;

    pos=Math.max(5,Math.min(90,pos));

    player.style.left=pos+"%";
  };

  const spawn=setInterval(()=>{

    if(!running)return;

    const bomb=document.createElement("div");

    bomb.textContent="💣";

    bomb.style.position="absolute";
    bomb.style.top="-30px";
    bomb.style.left=Math.random()*90+"%";
    bomb.style.fontSize="28px";

    board.appendChild(bomb);

    let top=-30;

    const fall=setInterval(()=>{

      top+=7;

      bomb.style.top=top+"px";

      if(top>board.clientHeight){

        clearInterval(fall);
        bomb.remove();

      }

      const pr=player.getBoundingClientRect();
      const br=bomb.getBoundingClientRect();

      if(
        pr.left<br.right &&
        pr.right>br.left &&
        pr.top<br.bottom &&
        pr.bottom>br.top
      ){

        running=false;

        clearInterval(fall);
        clearInterval(spawn);

        showToast("💥 Hit!");

      }

    },70);

  },500);

  const timer=setInterval(()=>{

    if(!running){
      clearInterval(timer);
      return;
    }

    seconds++;

    document.getElementById("dodgeScore")
      .textContent=`Survived: ${seconds}s`;

    if(seconds>=10){

      running=false;

      clearInterval(timer);
      clearInterval(spawn);

      gameWin(game,15);
    }

  },1000);
}

/* ---------- Sequence ---------- */

function initSequenceGame(area,game){

  let sequence=[];
  let user=[];
  let round=0;

  area.innerHTML=`
    <div class="card">
      <h3>🔢 Sequence Memory</h3>

      <div id="sequenceBox"
        class="ai-preview"
        style="font-size:38px">
      </div>

      <div
        class="grid grid-3"
        id="sequenceButtons"
        style="margin-top:10px">
      </div>

      <div id="sequenceStatus"
        class="alert">
        شوف السلسلة وحاول تعاودها.
      </div>
    </div>
  `;

  const box=document.getElementById("sequenceBox");
  const buttons=document.getElementById("sequenceButtons");

  for(let i=1;i<=6;i++){

    const b=document.createElement("button");

    b.className="btn";
    b.textContent=i;

    b.onclick=()=>{

      user.push(i);

      const index=user.length-1;

      if(user[index]!==sequence[index]){

        document.getElementById("sequenceStatus")
          .textContent="❌ غلط";

        return;
      }

      if(user.length===sequence.length){

        round++;

        if(round>=4){

          gameWin(game,20);

          return;
        }

        setTimeout(next,500);
      }
    };

    buttons.appendChild(b);
  }

  function next(){

    user=[];

    sequence.push(
      1+Math.floor(Math.random()*6)
    );

    box.textContent=sequence.join(" ");

    setTimeout(()=>{
      box.textContent="❓";
    },1200+round*150);
  }

  next();
}

/* ---------- Maze ---------- */

function initMazeGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🧩 Neon Maze</h3>

      <div
        class="game-board"
        id="mazeBoard"
        style="display:grid;place-items:center">

        <div
          id="mazePlayer"
          style="
            width:35px;
            height:35px;
            background:#00d9ff;
            box-shadow:0 0 20px #00d9ff;
            border-radius:10px;
            position:absolute;
            left:15px;
            top:15px;
          ">
          🟦
        </div>

        <div
          style="
            width:70%;
            height:70%;
            border:15px solid #7c3cff;
            border-right-color:transparent;
            border-bottom-color:transparent;
            border-radius:30px;
            pointer-events:none;
          ">
        </div>

        <div
          id="mazeGoal"
          style="
            position:absolute;
            right:20px;
            bottom:20px;
            font-size:40px;
          ">
          🏆
        </div>

      </div>

      <div class="mini-keypad" style="margin-top:10px">
        <span></span>
        <button onclick="mazeMove(0,-1)">⬆️</button>
        <span></span>
        <button onclick="mazeMove(-1,0)">⬅️</button>
        <button onclick="mazeMove(0,1)">⬇️</button>
        <button onclick="mazeMove(1,0)">➡️</button>
      </div>
    </div>
  `;

  let x=15;
  let y=15;

  window.mazeMove=function(dx,dy){

    x+=dx*18;
    y+=dy*18;

    x=Math.max(15,Math.min(85,x));
    y=Math.max(15,Math.min(85,y));

    const p=document.getElementById("mazePlayer");

    p.style.left=x+"%";
    p.style.top=y+"%";

    if(x>78&&y>78){
      gameWin(game,20);
    }
  };
}

/* ---------- 2048 ---------- */

function init2048Game(area,game){

  let grid=Array(16).fill(0);

  function add(){
    const empty=grid
      .map((v,i)=>v?null:i)
      .filter(v=>v!==null);

    if(!empty.length)return;

    grid[
      empty[Math.floor(Math.random()*empty.length)]
    ]=
      Math.random()<.9?2:4;
  }

  add();
  add();

  area.innerHTML=`
    <div class="card">
      <h3>🔢 2048 Mini</h3>

      <div
        id="g2048"
        style="
          display:grid;
          grid-template-columns:repeat(4,1fr);
          gap:7px;
          max-width:400px;
          margin:auto;
        ">
      </div>

      <div class="mini-keypad" style="margin-top:10px">
        <span></span>
        <button onclick="move2048(0,-1)">⬆️</button>
        <span></span>
        <button onclick="move2048(-1,0)">⬅️</button>
        <button onclick="move2048(0,1)">⬇️</button>
        <button onclick="move2048(1,0)">➡️</button>
      </div>
    </div>
  `;

  function render(){

    const box=document.getElementById("g2048");

    box.innerHTML=grid.map(v=>`
      <div style="
        aspect-ratio:1;
        display:grid;
        place-items:center;
        border-radius:13px;
        background:${v
          ?"linear-gradient(135deg,#00d9ff,#7c3cff)"
          :"rgba(255,255,255,.05)"};
        font-size:24px;
        font-weight:1000;">
        ${v||""}
      </div>
    `).join("");
  }

  window.move2048=function(dx,dy){

    if(dx!==0){

      const rows=[];

      for(let r=0;r<4;r++){

        let row=grid.slice(r*4,r*4+4);

        if(dx>0)row.reverse();

        row=row.filter(Boolean);

        for(let i=0;i<row.length-1;i++){

          if(row[i]===row[i+1]){
            row[i]*=2;
            row.splice(i+1,1);
          }
        }

        while(row.length<4)row.push(0);

        if(dx>0)row.reverse();

        rows.push(row);
      }

      grid=rows.flat();

    }else{

      const cols=[];

      for(let c=0;c<4;c++){

        let col=[
          grid[c],
          grid[c+4],
          grid[c+8],
          grid[c+12]
        ];

        if(dy>0)col.reverse();

        col=col.filter(Boolean);

        for(let i=0;i<col.length-1;i++){

          if(col[i]===col[i+1]){
            col[i]*=2;
            col.splice(i+1,1);
          }
        }

        while(col.length<4)col.push(0);

        if(dy>0)col.reverse();

        cols.push(col);
      }

      for(let c=0;c<4;c++){
        for(let r=0;r<4;r++){
          grid[r*4+c]=cols[c][r];
        }
      }
    }

    add();
    render();

    if(grid.some(v=>v>=64)){
      gameWin(game,25);
    }
  };

  render();
}

/* ---------- Connect 4 ---------- */

function initConnect4Game(area,game){

  let board=Array(42).fill("");

  area.innerHTML=`
    <div class="card">
      <h3>🔴 Connect 4</h3>

      <div
        id="connectBoard"
        style="
          display:grid;
          grid-template-columns:repeat(7,1fr);
          max-width:420px;
          margin:auto;
          gap:5px;
        ">
      </div>

      <div id="connectStatus" class="alert">
        دورك 🔴
      </div>
    </div>
  `;

  const box=document.getElementById("connectBoard");

  function render(){

    box.innerHTML="";

    board.forEach((v,i)=>{

      const b=document.createElement("button");

      b.style.aspectRatio="1";
      b.style.borderRadius="50%";
      b.style.border="1px solid rgba(255,255,255,.1)";
      b.style.background=
        v==="R"?"#ff3d71":
        v==="Y"?"#ffd54a":
        "#14213c";

      b.onclick=()=>drop(i%7,"R");

      box.appendChild(b);
    });
  }

  function drop(col,piece){

    for(let row=5;row>=0;row--){

      const index=row*7+col;

      if(!board[index]){

        board[index]=piece;

        if(check(piece)){

          document.getElementById("connectStatus")
            .textContent="🏆 فزتي!";

          render();

          gameWin(game,25);

          return;
        }

        bot();

        return;
      }
    }
  }

  function bot(){

    const cols=
      [...Array(7).keys()]
      .filter(c=>!board[c]);

    if(!cols.length)return;

    const c=cols[Math.floor(Math.random()*cols.length)];

    for(let row=5;row>=0;row--){

      const index=row*7+c;

      if(!board[index]){

        board[index]="Y";

        break;
      }
    }

    if(check("Y")){

      document.getElementById("connectStatus")
        .textContent="🤖 Bot فاز";

    }else{

      document.getElementById("connectStatus")
        .textContent="دورك 🔴";
    }

    render();
  }

  function check(piece){

    const dirs=[
      [1,0],
      [0,1],
      [1,1],
      [1,-1]
    ];

    for(let r=0;r<6;r++){
      for(let c=0;c<7;c++){

        for(const [dx,dy] of dirs){

          let count=0;

          for(let n=0;n<4;n++){

            const rr=r+dy*n;
            const cc=c+dx*n;

            if(
              rr>=0&&
              rr<6&&
              cc>=0&&
              cc<7&&
              board[rr*7+cc]===piece
            ){
              count++;
            }
          }

          if(count===4)return true;
        }
      }
    }

    return false;
  }

  render();
}

/* ---------- Pong ---------- */

function initPongGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🏓 Mini Pong</h3>

      <canvas
        id="pongCanvas"
        width="700"
        height="400"
        style="
          width:100%;
          border-radius:20px;
          background:#030713;
          border:1px solid rgba(0,217,255,.25);
        ">
      </canvas>

      <div class="mini-keypad" style="margin-top:10px">
        <button onclick="pongUp()">⬆️</button>
        <button onclick="pongDown()">⬇️</button>
      </div>
    </div>
  `;

  const canvas=document.getElementById("pongCanvas");
  const ctx=canvas.getContext("2d");

  let py=170;
  let by=150;
  let ball={
    x:350,
    y:200,
    dx:5,
    dy:3
  };

  let score=0;

  window.pongUp=()=>{
    py=Math.max(0,py-25);
  };

  window.pongDown=()=>{
    py=Math.min(330,py+25);
  };

  function loop(){

    ctx.clearRect(0,0,700,400);

    ctx.fillStyle="#00d9ff";
    ctx.fillRect(20,py,14,70);

    ctx.fillStyle="#7c3cff";
    ctx.fillRect(666,by,14,70);

    ctx.beginPath();
    ctx.arc(ball.x,ball.y,9,0,Math.PI*2);
    ctx.fillStyle="#fff";
    ctx.shadowBlur=20;
    ctx.shadowColor="#00d9ff";
    ctx.fill();
    ctx.shadowBlur=0;

    ball.x+=ball.dx;
    ball.y+=ball.dy;

    if(ball.y<9||ball.y>391){
      ball.dy*=-1;
    }

    by+=(ball.y-by-35)*.06;

    if(
      ball.x<45 &&
      ball.y>py &&
      ball.y<py+70
    ){
      ball.dx=Math.abs(ball.dx);
      score++;
    }

    if(ball.x>650){

      if(
        ball.y>by &&
        ball.y<by+70
      ){
        ball.dx=-Math.abs(ball.dx);
      }else{

        ball={
          x:350,
          y:200,
          dx:-5,
          dy:3
        };
      }
    }

    if(score>=5){
      gameWin(game,20);
      return;
    }

    requestAnimationFrame(loop);
  }

  loop();
}

/* ---------- Breakout ---------- */

function initBreakoutGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🧱 Brick Breaker</h3>

      <canvas
        id="brickCanvas"
        width="700"
        height="420"
        style="
          width:100%;
          border-radius:20px;
          background:#030713;
        ">
      </canvas>

      <button
        class="btn primary full"
        style="margin-top:8px"
        onclick="moveBrickPaddle()">
        ➡️ Move Paddle
      </button>
    </div>
  `;

  const canvas=document.getElementById("brickCanvas");
  const ctx=canvas.getContext("2d");

  let paddle=300;
  let ball={
    x:350,
    y:360,
    dx:4,
    dy:-4
  };

  const bricks=[];

  for(let r=0;r<4;r++){
    for(let c=0;c<10;c++){
      bricks.push({
        x:c*68+2,
        y:r*25+10,
        alive:true
      });
    }
  }

  let score=0;

  window.moveBrickPaddle=()=>{
    paddle+=60;

    if(paddle>580)paddle=0;
  };

  function loop(){

    ctx.clearRect(0,0,700,420);

    ctx.fillStyle="#00d9ff";
    ctx.fillRect(paddle,390,110,15);

    bricks.forEach(b=>{

      if(!b.alive)return;

      ctx.fillStyle="#7c3cff";
      ctx.fillRect(b.x,b.y,64,20);

      if(
        ball.x>b.x &&
        ball.x<b.x+64 &&
        ball.y>b.y &&
        ball.y<b.y+20
      ){

        b.alive=false;
        ball.dy*=-1;
        score++;
      }
    });

    ctx.beginPath();
    ctx.arc(ball.x,ball.y,8,0,Math.PI*2);
    ctx.fillStyle="#fff";
    ctx.fill();

    ball.x+=ball.dx;
    ball.y+=ball.dy;

    if(ball.x<8||ball.x>692)ball.dx*=-1;
    if(ball.y<8)ball.dy*=-1;

    if(
      ball.y>375 &&
      ball.x>paddle &&
      ball.x<paddle+110
    ){
      ball.dy=-Math.abs(ball.dy);
    }

    if(score>=40){

      gameWin(game,30);
      return;
    }

    if(ball.y>420){

      showToast("💥 Game Over");
      return;
    }

    requestAnimationFrame(loop);
  }

  loop();
}

/* ---------- Flappy ---------- */

function initFlappyGame(area,game){

  area.innerHTML=`
    <div class="card">
      <h3>🪽 Flappy Jet</h3>

      <div
        id="flappyBoard"
        class="game-board">

        <div
          id="flappyPlayer"
          style="
            position:absolute;
            left:70px;
            top:180px;
            font-size:35px;
          ">
          🚀
        </div>

      </div>

      <button
        class="btn primary full"
        onclick="flap()"
        style="margin-top:8px">
        🚀 FLAP
      </button>

      <div id="flappyScore" class="alert">
        Score: 0
      </div>
    </div>
  `;

  const board=document.getElementById("flappyBoard");
  const player=document.getElementById("flappyPlayer");

  let y=180;
  let velocity=0;
  let score=0;
  let running=true;

  window.flap=()=>{
    velocity=-8;
  };

  const pipeTimer=setInterval(()=>{

    if(!running)return;

    const gapTop=
      50+Math.random()*(board.clientHeight-220);

    const topPipe=document.createElement("div");
    const bottomPipe=document.createElement("div");

    [topPipe,bottomPipe].forEach(p=>{

      p.style.position="absolute";
      p.style.width="55px";
      p.style.background="#36f59a";
      p.style.right="-60px";

    });

    topPipe.style.height=gapTop+"px";
    topPipe.style.top="0";

    bottomPipe.style.height=
      (board.clientHeight-gapTop-130)+"px";

    bottomPipe.style.bottom="0";

    board.appendChild(topPipe);
    board.appendChild(bottomPipe);

    let x=-60;

    const move=setInterval(()=>{

      if(!running){
        clearInterval(move);
        return;
      }

      x+=4;

      topPipe.style.right=(-x)+"px";
      bottomPipe.style.right=(-x)+"px";

      if(x>board.clientWidth+80){

        clearInterval(move);

        topPipe.remove();
        bottomPipe.remove();

        score++;

        document.getElementById("flappyScore")
          .textContent=`Score: ${score}`;

        if(score>=5){

          running=false;
          clearInterval(pipeTimer);

          gameWin(game,25);
        }
      }

    },40);

  },1300);

  const loop=setInterval(()=>{

    if(!running){
      clearInterval(loop);
      return;
    }

    velocity+=.5;
    y+=velocity;

    player.style.top=y+"px";

    if(y<0||y>board.clientHeight-45){

      running=false;
      clearInterval(pipeTimer);

      showToast("💥 Game Over");
    }

  },40);
}

/* =========================================================
   REWARDS
========================================================= */

const baseRewards=[
  {
    id:"ff100",
    game:"Free Fire",
    icon:"🔥",
    amount:"100 Diamonds",
    cost:1000
  },
  {
    id:"ff310",
    game:"Free Fire",
    icon:"🔥",
    amount:"310 Diamonds",
    cost:2800
  },
  {
    id:"pubg60",
    game:"PUBG Mobile",
    icon:"🔫",
    amount:"60 UC",
    cost:800
  },
  {
    id:"efootball",
    game:"eFootball",
    icon:"⚽",
    amount:"100 Coins",
    cost:900
  },
  {
    id:"robux",
    game:"Roblox",
    icon:"🟥",
    amount:"80 Robux",
    cost:1200
  },
  {
    id:"cod",
    game:"Call of Duty",
    icon:"🎯",
    amount:"CP Pack",
    cost:1500
  }
];

function renderRewards(){

  const grid=document.getElementById("rewardsGrid");

  if(!grid)return;

  const rewards=[
    ...baseRewards,
    ...state.customRewards
  ];

  grid.innerHTML=rewards.map(r=>`

    <div class="card reward-card">

      <div class="task-top">
        <div class="reward-icon">${r.icon}</div>

        <div class="task-info">
          <strong>${esc(r.game)}</strong>
          <span>${esc(r.amount)}</span>
        </div>

        <div class="reward-points">
          ${r.cost} 💎
        </div>
      </div>

      <div class="progress">
        <i style="width:${Math.min(100,state.points/r.cost*100)}%"></i>
      </div>

      <button
        class="btn primary full"
        onclick="redeemReward('${esc(r.id)}')">
        🎁 Redeem
      </button>

    </div>

  `).join("");
}

function redeemReward(id){

  const reward=[
    ...baseRewards,
    ...state.customRewards
  ].find(r=>r.id===id);

  if(!reward)return;

  if(!removePoints(reward.cost,`Redeem ${reward.game}`)){
    return;
  }

  const message=
    `سلام، بغيت نطلب ${reward.game} - ${reward.amount}. `+
    `FINI ID: AMINE`;

  window.open(
    WA_ORDER+
    "&text="+
    encodeURIComponent(message),
    "_blank"
  );

  showToast("📱 الطلب تفتح فواتساب");
}

/* =========================================================
   STORE
========================================================= */

const baseStore=[
  {
    id:"store-ff",
    game:"Free Fire",
    package:"100 Diamonds",
    price:10,
    image:"https://picsum.photos/700/400?random=201"
  },
  {
    id:"store-pubg",
    game:"PUBG Mobile",
    package:"60 UC",
    price:10,
    image:"https://picsum.photos/700/400?random=202"
  },
  {
    id:"store-roblox",
    game:"Roblox",
    package:"80 Robux",
    price:10,
    image:"https://picsum.photos/700/400?random=203"
  },
  {
    id:"store-efootball",
    game:"eFootball",
    package:"100 Coins",
    price:10,
    image:"https://picsum.photos/700/400?random=204"
  },
  {
    id:"store-cod",
    game:"Call of Duty",
    package:"CP Pack",
    price:15,
    image:"https://picsum.photos/700/400?random=205"
  },
  {
    id:"store-brawl",
    game:"Brawl Stars",
    package:"Gems",
    price:12,
    image:"https://picsum.photos/700/400?random=206"
  }
];

function renderStore(){

  const grid=document.getElementById("storeGrid");

  if(!grid)return;

  const items=[
    ...baseStore,
    ...state.customStore
  ];

  grid.innerHTML=items.map(item=>`

    <div class="card store-card">

      <div class="store-cover">
        <img
          src="${esc(item.image)}"
          alt="${esc(item.game)}"
          loading="lazy">
      </div>

      <div class="task-top">

        <div class="task-info">
          <strong>${esc(item.game)}</strong>
          <span>${esc(item.package)}</span>
        </div>

        <div class="reward-points">
          ${item.price} DH
        </div>

      </div>

      <button
        class="btn primary full"
        style="margin-top:10px"
        onclick="orderStore('${esc(item.id)}')">
        🛒 اطلب الآن
      </button>

    </div>

  `).join("");
}

function orderStore(id){

  const item=[
    ...baseStore,
    ...state.customStore
  ].find(x=>x.id===id);

  if(!item)return;

  const message=
    `🛒 FINI STORE ORDER\n`+
    `Game: ${item.game}\n`+
    `Package: ${item.package}\n`+
    `Price: ${item.price} DH`;

  window.open(
    WA_ORDER+
    "&text="+
    encodeURIComponent(message),
    "_blank"
  );
}

/* =========================================================
   WHEEL
========================================================= */

const wheelRewards=[
  10,
  25,
  50,
  100,
  250,
  20,
  35,
  75
];

function getToday(){

  return new Date().toISOString().slice(0,10);
}

function resetDailySpins(){

  const today=getToday();

  if(state.lastSpinDay!==today){

    state.lastSpinDay=today;
    state.spins=5;

    save();
  }
}

function updateWheel(){

  resetDailySpins();

  const left=
    state.spins+
    state.bonusSpins;

  const el=document.getElementById("spinsLeft");

  if(el)el.textContent=left;
}

function spinWheel(){

  resetDailySpins();

  if(state.spins<=0 && state.bonusSpins<=0){

    showToast("❌ سالاو Spins ديال اليوم");
    return;
  }

  if(state.spins>0){
    state.spins--;
  }else{
    state.bonusSpins--;
  }

  const index=
    Math.floor(Math.random()*wheelRewards.length);

  const reward=wheelRewards[index];

  state.wheelRotation+=
    1440+
    index*45;

  const wheel=
    document.getElementById("wheelInner");

  if(wheel){
    wheel.style.transform=
      `rotate(${state.wheelRotation}deg)`;
  }

  save();
  updateWheel();

  setTimeout(()=>{

    addPoints(reward,"Wheel Reward");

  },4000);
}

/* =========================================================
   PROFILE / BADGES
========================================================= */

function getBadges(){

  const arr=[
    {
      name:"First Steps",
      icon:"🎮",
      category:"Gaming",
      unlocked:state.xp>=100
    },
    {
      name:"Point Hunter",
      icon:"💎",
      category:"Points",
      unlocked:state.points>=500
    },
    {
      name:"Streak 7",
      icon:"🔥",
      category:"Streak",
      unlocked:state.streak>=7
    },
    {
      name:"Wheel Master",
      icon:"🎡",
      category:"Wheel",
      unlocked:state.spins<=3
    },
    {
      name:"Reward Hunter",
      icon:"🎁",
      category:"Rewards",
      unlocked:false
    },
    {
      name:"Speed",
      icon:"⚡",
      category:"Speed",
      unlocked:false
    },
    {
      name:"Puzzle",
      icon:"🧩",
      category:"Puzzle",
      unlocked:false
    },
    {
      name:"VIP",
      icon:"👑",
      category:"VIP",
      unlocked:state.vip
    },
    {
      name:"Elite",
      icon:"💠",
      category:"Elite",
      unlocked:state.vipPlus
    },
    {
      name:"Achievement",
      icon:"🏆",
      category:"Achievement",
      unlocked:state.level>=5
    },
    {
      name:"Referral",
      icon:"👥",
      category:"Referral",
      unlocked:state.friends.length>=3
    },
    {
      name:"Skill",
      icon:"🧠",
      category:"Skill",
      unlocked:state.xp>=2000
    }
  ];

  return arr;
}

function renderProfile(){

  updateUI();

  const avatar=
    document.getElementById("profileAvatar");

  if(avatar && state.avatar){
    avatar.src=state.avatar;
  }

  const grid=document.getElementById("badgesGrid");

  if(!grid)return;

  grid.innerHTML=getBadges().map(b=>`

    <div class="card badge-card ${b.unlocked?"":"locked"}">

      <div style="font-size:35px">
        ${b.icon}
      </div>

      <h3>${esc(b.name)}</h3>

      <span class="badge ${b.unlocked?"unlocked":"locked"}">
        ${esc(b.category)}
      </span>

      <p class="muted small">
        ${b.unlocked?"Unlocked":"Locked"}
      </p>

    </div>

  `).join("");
}

function changeAvatar(){

  openModal(`
    <div class="modal-head">
      <h2>🖼️ Change Profile Photo</h2>
      <button class="close" onclick="closeModal()">×</button>
    </div>

    <label class="file-drop">
      <input
        type="file"
        accept="image/*"
        onchange="saveAvatarFile(this)">
      <div>
        🖼️
        <br>
        اختار صورة
      </div>
    </label>

    <label class="field" style="margin-top:12px">
      <span>أو URL</span>
      <input
        id="avatarUrl"
        class="input"
        placeholder="https://...">
    </label>

    <button
      class="btn primary full"
      onclick="saveAvatarUrl()">
      Save
    </button>
  `);
}

function saveAvatarUrl(){

  const url=
    document.getElementById("avatarUrl").value.trim();

  if(!url)return;

  state.avatar=url;

  save();
  renderProfile();
  closeModal();

  showToast("🖼️ تبدلات الصورة");
}

function saveAvatarFile(input){

  const file=input.files?.[0];

  if(!file)return;

  const reader=new FileReader();

  reader.onload=()=>{

    state.avatar=reader.result;

    save();
    renderProfile();

    closeModal();

    showToast("🖼️ Photo Updated");
  };

  reader.readAsDataURL(file);
}

/* =========================================================
   VIP
========================================================= */

function activateVip(type){

  if(type==="VIP"){
    state.vip=true;
    addPoints(0,"VIP");
    showToast("⭐ VIP Activated");
  }

  if(type==="VIP+"){
    state.vipPlus=true;
    state.vip=true;
    addPoints(0,"VIP+");
    showToast("👑 VIP+ Activated");
  }

  save();
  renderProfile();
}

/* =========================================================
   FRIENDS
========================================================= */

function seedFriends(){

  if(state.friends.length)return;

  state.friends=[
    {
      id:"f1",
      name:"OTMAN",
      avatar:"https://picsum.photos/100/100?random=301",
      online:true,
      vip:true
    },
    {
      id:"f2",
      name:"GHOST FF",
      avatar:"https://picsum.photos/100/100?random=302",
      online:true,
      vip:false
    },
    {
      id:"f3",
      name:"FINI Bot",
      avatar:"https://picsum.photos/100/100?random=303",
      online:true,
      bot:true
    }
  ];

  state.groups=[
    {
      id:"grp1",
      name:"FINI Gaming Squad",
      members:27
    },
    {
      id:"grp2",
      name:"Free Fire Players",
      members:103
    }
  ];

  state.requests=[
    {
      id:"req1",
      name:"Player X",
      avatar:"https://picsum.photos/100/100?random=304"
    }
  ];

  save();
}

function renderFriends(){

  seedFriends();

  const grid=document.getElementById("friendsGrid");

  if(!grid)return;

  grid.innerHTML=state.friends.map(f=>`

    <div class="card friend-card">

      <div class="task-top">

        <img
          class="avatar"
          src="${esc(f.avatar)}">

        <div class="task-info">

          <strong>
            ${esc(f.name)}
            ${f.bot?"🤖":""}
          </strong>

          <span>
            <span class="online-dot"></span>
            ${f.online?"Online":"Offline"}
          </span>

        </div>

        ${f.vip?`<span class="badge unlocked">👑 VIP</span>`:""}

      </div>

      <div class="hero-actions">
        <button
          class="btn primary small"
          onclick="openFriend('${esc(f.id)}')">
          👤 Profile
        </button>

        <button
          class="btn small"
          onclick="openFriendChat('${esc(f.id)}')">
          💬 Message
        </button>
      </div>

    </div>

  `).join("");
}

function friendsTab(button,type){

  document.querySelectorAll("#page-friends .tab")
    .forEach(x=>x.classList.remove("active"));

  button.classList.add("active");

  const grid=document.getElementById("friendsGrid");

  if(type==="friends"){

    renderFriends();
    return;
  }

  if(type==="requests"){

    grid.innerHTML=state.requests.map(r=>`

      <div class="card">
        <div class="task-top">

          <img class="avatar" src="${esc(r.avatar)}">

          <div class="task-info">
            <strong>${esc(r.name)}</strong>
            <span>Friend Request</span>
          </div>

        </div>

        <div class="hero-actions">
          <button class="btn success" onclick="acceptRequest('${esc(r.id)}')">
            ✅ Accept
          </button>

          <button class="btn danger" onclick="rejectRequest('${esc(r.id)}')">
            ❌ Reject
          </button>
        </div>
      </div>

    `).join("");

    return;
  }

  if(type==="groups"){

    grid.innerHTML=state.groups.map(g=>`

      <div class="card">
        <div class="stat">
          <div>
            <span>Group</span>
            <strong>${esc(g.name)}</strong>
          </div>
          <div class="stat-icon">👥</div>
        </div>

        <div class="muted small" style="margin-top:10px">
          ${g.members} members
        </div>

        <button
          class="btn primary full"
          style="margin-top:10px"
          onclick="navigate('chat')">
          💬 Open Group
        </button>
      </div>

    `).join("");
  }
}

function acceptRequest(id){

  const request=state.requests.find(r=>r.id===id);

  if(!request)return;

  state.friends.push({
    id:"friend-"+Date.now(),
    name:request.name,
    avatar:request.avatar,
    online:false
  });

  state.requests=
    state.requests.filter(r=>r.id!==id);

  addPoints(20,"Friend Added");

  save();

  renderFriends();
}

function rejectRequest(id){

  state.requests=
    state.requests.filter(r=>r.id!==id);

  save();

  renderFriends();
}

function openFriend(id){

  const friend=
    state.friends.find(f=>f.id===id);

  if(!friend)return;

  openModal(`
    <div class="modal-head">
      <h2>👤 ${esc(friend.name)}</h2>
      <button class="close" onclick="closeModal()">×</button>
    </div>

    <div class="profile-head">

      <img
        class="avatar big"
        src="${esc(friend.avatar)}">

      <div>
        <h2>${esc(friend.name)}</h2>

        <div class="muted">
          <span class="online-dot"></span>
          ${friend.online?"Online":"Offline"}
        </div>

        <div style="margin-top:8px">
          <span class="badge">🎮 Gamer</span>
          ${friend.vip?`<span class="badge unlocked">👑 VIP</span>`:""}
          ${friend.bot?`<span class="badge unlocked">🤖 FINI Bot</span>`:""}
        </div>
      </div>

    </div>

    <div class="hero-actions">
      <button
        class="btn primary"
        onclick="openFriendChat('${esc(friend.id)}')">
        💬 Message
      </button>

      <button
        class="btn"
        onclick="navigate('ai');closeModal()">
        🤖 FINI AI
      </button>
    </div>
  `);
}

function openFriendChat(id){

  closeModal();

  navigate("chat");

  setTimeout(()=>{

    const friend=
      state.friends.find(f=>f.id===id);

    if(friend){

      document.getElementById("chatTitle").textContent=
        friend.name+
        (friend.bot?" 🤖":"");

      if(friend.bot){
        addBotMessage("أنا FINI Bot 🤖 متاح!");
      }
    }

  },100);
}

/* =========================================================
   CHAT
========================================================= */

function renderChat(){

  seedFriends();

  const contacts=document.getElementById("chatContacts");

  if(!contacts)return;

  contacts.innerHTML=[
    ...state.friends,
    ...state.groups.map(g=>({
      id:g.id,
      name:g.name,
      avatar:"https://picsum.photos/100/100?random=399",
      group:true,
      online:true
    }))
  ].map(c=>`

    <button
      class="card"
      style="
        width:100%;
        text-align:right;
        margin-bottom:7px;
        padding:10px;
      "
      onclick="selectChat('${esc(c.id)}')">

      <div class="task-top">

        <img
          class="avatar"
          style="width:45px;height:45px"
          src="${esc(c.avatar)}">

        <div class="task-info">
          <strong>
            ${esc(c.name)}
            ${c.bot?" 🤖":""}
          </strong>

          <span>
            ${c.group?"👥 Group":
              c.online?"🟢 Online":"Offline"}
          </span>
        </div>

      </div>

    </button>

  `).join("");

  renderMessages();
}

function chatTab(button,type){

  document.querySelectorAll("#page-chat .tab")
    .forEach(x=>x.classList.remove("active"));

  button.classList.add("active");

  const contacts=document.getElementById("chatContacts");

  if(type==="bot"){

    contacts.innerHTML=`
      <button
        class="card"
        style="width:100%;text-align:right"
        onclick="selectChat('bot')">

        <div class="task-top">
          <div class="avatar"
            style="
              display:grid;
              place-items:center;
              background:linear-gradient(135deg,#00d9ff,#7c3cff);
              font-size:25px">
            🤖
          </div>

          <div class="task-info">
            <strong>FINI Bot</strong>
            <span>🟢 Online • AI</span>
          </div>
        </div>

      </button>
    `;

  }else if(type==="groups"){

    contacts.innerHTML=state.groups.map(g=>`

      <button
        class="card"
        style="width:100%;text-align:right;margin-bottom:7px"
        onclick="selectChat('${esc(g.id)}')">

        <div class="task-top">
          <div class="avatar"
            style="
              display:grid;
              place-items:center;
              background:rgba(124,60,255,.2)">
            👥
          </div>

          <div class="task-info">
            <strong>${esc(g.name)}</strong>
            <span>${g.members} members</span>
          </div>
        </div>

      </button>

    `).join("");

  }else{

    renderChat();
  }
}

function selectChat(id){

  if(id==="bot"){

    document.getElementById("chatTitle").textContent=
      "FINI Bot 🤖";

    if(!state.messages.length){
      addBotMessage(state.ai.welcome);
    }

    renderMessages();

    return;
  }

  const friend=state.friends.find(f=>f.id===id);

  const group=state.groups.find(g=>g.id===id);

  document.getElementById("chatTitle").textContent=
    friend?.name||
    group?.name||
    "Chat";

  renderMessages();
}

function renderMessages(){

  const box=document.getElementById("messages");

  if(!box)return;

  if(!state.messages.length){

    box.innerHTML=`
      <div class="alert">
        🤖 كتب <b>@fini</b> باش تنادي FINI Bot.
      </div>
    `;

    return;
  }

  box.innerHTML=state.messages.map(m=>`

    <div class="msg ${m.from==="me"?"me":m.from==="bot"?"bot":"other"}">
      ${m.from==="bot"?"🤖 ":""}${esc(m.text)}
      <div class="muted" style="font-size:9px;margin-top:4px">
        ${new Date(m.time).toLocaleTimeString()}
      </div>
    </div>

  `).join("");

  box.scrollTop=box.scrollHeight;
}

function addBotMessage(text){

  state.messages.push({
    from:"bot",
    text,
    time:Date.now()
  });

  save();
  renderMessages();
}

function sendChat(){

  const input=document.getElementById("chatInput");

  if(!input)return;

  const text=input.value.trim();

  if(!text)return;

  state.messages.push({
    from:"me",
    text,
    time:Date.now()
  });

  input.value="";

  save();
  renderMessages();

  if(
    text.toLowerCase().includes("@fini") ||
    text.startsWith("/fini")
  ){

    setTimeout(()=>{
      botReply(text);
    },600);

  }else{

    setTimeout(()=>{
      state.messages.push({
        from:"other",
        text:"وصلاتني الرسالة 👌",
        time:Date.now()
      });

      save();
      renderMessages();

    },700);
  }
}

function sendBotCommand(){

  const input=document.getElementById("chatInput");

  input.value="@fini ";

  input.focus();
}

function botReply(text){

  const lower=text.toLowerCase();

  let response=
    "أنا FINI Bot 🤖. نقدر نعاونك فـFINI.";

  if(lower.includes("point")||lower.includes("نقط")){
    response=
      `عندك دابا ${state.points} FINI Points 💎`;
  }

  else if(lower.includes("game")||lower.includes("لعب")){
    response=
      `عندنا ${games.length} لعبة قابلة للعب 🎮`;
  }

  else if(lower.includes("video")){
    response=
      `AI Video كيتفتح من ${AI_VIDEO_POINTS} PTS + ${AI_VIDEO_ADS} Ads 🎬`;
  }

  else if(lower.includes("help")||lower.includes("مساعدة")){
    response=
      "جرب: @fini points / @fini games / @fini video";
  }

  addBotMessage(response);
}

/* =========================================================
   AI
========================================================= */

function askFiniAI(){

  const prompt=
    document.getElementById("aiPrompt")
    ?.value
    .trim();

  const response=
    document.getElementById("aiResponse");

  if(!prompt){

    response.textContent=
      "كتب سؤال أولاً.";

    return;
  }

  response.innerHTML=`
    🤖 FINI AI كيعالج السؤال...<br>
    <span class="muted small">
      Demo response — ربط API حقيقي يمكن إضافته لاحقاً.
    </span>
  `;

  setTimeout(()=>{

    response.innerHTML=`
      🤖 <b>FINI AI:</b><br>
      الفكرة ديالك هي:
      <b>${esc(prompt)}</b><br><br>

      💡 اقتراح:
      حولها لمهمة أو لعبة أو محتوى داخل FINI.
    `;

    addPoints(20,"FINI AI Task");

  },800);
}

function handleAIScreenshot(input){

  const file=input.files?.[0];

  if(!file)return;

  const result=
    document.getElementById("aiScreenshotResult");

  result.textContent=
    "🤖 FINI AI كيحلل الصورة...";

  setTimeout(()=>{

    const reward=
      20+
      Math.floor(Math.random()*31);

    addPoints(reward,"AI Screenshot Evaluation");

    result.innerHTML=
      `✅ Screenshot مقبولة.<br>
       🎁 +${reward} PTS`;
  },1200);
}

/* =========================================================
   VIDEO
========================================================= */

function renderVideoLock(){

  const lock=document.getElementById("videoLockArea");
  const studio=document.getElementById("videoStudio");

  if(!lock||!studio)return;

  const pointsPercent=
    Math.min(
      100,
      state.points/AI_VIDEO_POINTS*100
    );

  const adsPercent=
    Math.min(
      100,
      state.ads/AI_VIDEO_ADS*100
    );

  const unlocked=
    state.points>=AI_VIDEO_POINTS &&
    state.ads>=AI_VIDEO_ADS;

  if(unlocked){

    lock.innerHTML=`
      <div class="alert success">
        🔓 AI VIDEO مفتوح!
      </div>
    `;

    studio.classList.remove("hidden");

  }else{

    studio.classList.add("hidden");

    lock.innerHTML=`
      <div class="card lock-card">

        <div class="lock-overlay">

          <div style="font-size:50px">🔒</div>

          <strong>AI VIDEO LOCKED</strong>

          <p class="muted">
            خاصك ${AI_VIDEO_POINTS} PTS + ${AI_VIDEO_ADS} Ads
          </p>

        </div>

        <h3>🎬 Unlock Progress</h3>

        <p>
          💎 Points:
          <b>${state.points}</b>
          / ${AI_VIDEO_POINTS}
        </p>

        <div class="progress">
          <i style="width:${pointsPercent}%"></i>
        </div>

        <p>
          📺 Ads:
          <b>${state.ads}</b>
          / ${AI_VIDEO_ADS}
        </p>

        <div class="progress">
          <i style="width:${adsPercent}%"></i>
        </div>

        <button
          class="btn primary full"
          onclick="watchRewardedAd()">
          📺 Watch Ad
        </button>

      </div>
    `;
  }
}

function previewVideoImage(input){

  const file=input.files?.[0];

  if(!file)return;

  const reader=new FileReader();

  reader.onload=()=>{

    document.getElementById("videoPreview")
      .innerHTML=`
        <img
          src="${reader.result}"
          style="
            width:100%;
            max-height:300px;
            object-fit:cover;
            border-radius:20px">
      `;
  };

  reader.readAsDataURL(file);
}

function generateVideoDemo(){

  const prompt=
    document.getElementById("videoPrompt").value.trim();

  if(!prompt){

    showToast("⚠️ كتب Prompt");
    return;
  }

  const progress=
    document.getElementById("videoProgress");

  const status=
    document.getElementById("videoStatus");

  let value=0;

  status.textContent=
    "🎬 Generating...";

  const timer=setInterval(()=>{

    value+=10;

    progress.style.width=value+"%";

    if(value>=100){

      clearInterval(timer);

      status.innerHTML=
        "✅ Demo Video Generated";

      state.videoHistory.unshift({
        prompt,
        style:document.getElementById("videoStyle").value,
        time:Date.now()
      });

      save();
      renderVideoHistory();

      showToast("🎬 Video جاهز!");

    }

  },250);
}

function renderVideoHistory(){

  const box=document.getElementById("videoHistory");

  if(!box)return;

  if(!state.videoHistory.length){

    box.innerHTML=
      `<div class="muted">No videos yet.</div>`;

    return;
  }

  box.innerHTML=
    state.videoHistory.slice(0,10).map(v=>`

      <div class="alert" style="margin-bottom:8px">
        🎬 ${esc(v.style)}<br>
        <span class="muted">
          ${esc(v.prompt)}
        </span>
      </div>

    `).join("");
}

/* =========================================================
   VOICE
========================================================= */

function speakVoice(){

  const text=
    document.getElementById("voiceText")
    ?.value
    .trim();

  if(!text){

    showToast("⚠️ كتب النص");
    return;
  }

  if(!("speechSynthesis" in window)){

    showToast("❌ Speech غير متوفر");
    return;
  }

  const utter=
    new SpeechSynthesisUtterance(text);

  utter.rate=
    Number(document.getElementById("voiceSpeed").value);

  utter.pitch=
    Number(document.getElementById("voicePitch").value);

  speechSynthesis.cancel();
  speechSynthesis.speak(utter);

  document.getElementById("voiceStatus")
    .textContent=
      "🔊 Preview كيتشغل...";
}

function generateVoiceDemo(){

  const text=
    document.getElementById("voiceText")
    ?.value
    .trim();

  if(!text){

    showToast("⚠️ كتب النص");
    return;
  }

  state.voiceHistory.unshift({
    text,
    voice:document.getElementById("voiceSelect").value,
    language:document.getElementById("voiceLanguage").value,
    time:Date.now()
  });

  save();

  document.getElementById("voiceStatus")
    .innerHTML=
      "✅ Voice generated (browser demo).";

  renderVoiceHistory();

  speakVoice();
}

function renderVoiceHistory(){

  const box=document.getElementById("voiceHistory");

  if(!box)return;

  if(!state.voiceHistory.length){

    box.innerHTML=
      `<div class="muted">No voice generations yet.</div>`;

    return;
  }

  box.innerHTML=
    state.voiceHistory.slice(0,10).map(v=>`

      <div class="alert" style="margin-bottom:8px">
        🎙️ ${esc(v.voice)} • ${esc(v.language)}<br>
        <span class="muted">
          ${esc(v.text)}
        </span>
      </div>

    `).join("");
}

/* =========================================================
   ESPORT
========================================================= */

function generateTournament(){

  const players=
    Number(document.getElementById("tourPlayers").value);

  const startValue=
    document.getElementById("tourStart").value;

  const interval=
    Number(document.getElementById("tourInterval").value)||15;

  const ads=
    Number(document.getElementById("tourAds").value)||3;

  const start=
    startValue
      ? new Date(startValue)
      : new Date();

  const rounds=[];

  let count=players;
  let roundNumber=1;

  while(count>1){

    const matches=Math.ceil(count/2);

    rounds.push({
      round:roundNumber,
      players:count,
      matches,
      time:new Date(
        start.getTime()+
        (roundNumber-1)*interval*60000
      )
    });

    count=matches;
    roundNumber++;
  }

  state.tournament={
    players,
    ads,
    interval,
    start:start.toISOString(),
    rounds
  };

  save();

  renderTournament();

  showToast("🏆 Tournament generated");
}

function renderTournament(){

  const data=state.tournament;

  const stats=document.getElementById("tourStats");
  const bracket=document.getElementById("bracket");

  if(!stats||!bracket)return;

  if(!data){

    stats.textContent=
      "مازال ما كاين حتى Tournament.";

    return;
  }

  stats.innerHTML=`
    👥 Players:
    <b>${data.players}</b><br>
    📺 Ads:
    <b>${data.ads}</b><br>
    ⏱️ Interval:
    <b>${data.interval} min</b><br>
    🏆 Rounds:
    <b>${data.rounds.length}</b>
  `;

  bracket.innerHTML=data.rounds.map(round=>`

    <div class="round">

      <h3>
        Round ${round.round}
      </h3>

      <div class="muted small">
        ${round.matches} Matches
      </div>

      ${Array.from({
        length:Math.min(round.matches,12)
      }).map((_,i)=>`

        <div class="match">
          <b>Match ${i+1}</b><br>
          <small>
            ${new Date(round.time)
              .toLocaleTimeString()}
          </small><br>
          <small>
            📺 ${data.ads} ads
          </small>
        </div>

      `).join("")}

      ${
        round.matches>12
        ? `<div class="muted small">+ ${round.matches-12} more...</div>`
        :""
      }

    </div>

  `).join("");
}

/* =========================================================
   SETTINGS
========================================================= */

function toggleDark(enabled){

  state.settings.dark=enabled;

  document.body.classList.toggle(
    "light",
    !enabled
  );

  save();
}

function toggleAnimations(enabled){

  state.settings.animations=enabled;

  document.body.classList.toggle(
    "no-animations",
    !enabled
  );

  save();
}

function setSetting(key,value){

  state.settings[key]=value;

  save();

  showToast("⚙️ Settings updated");
}

function setScale(value){

  state.settings.scale=Number(value)||1;

  document.documentElement.style
    .setProperty(
      "--scale",
      state.settings.scale
    );

  save();
}

function changeLanguage(lang){

  state.settings.language=lang;

  save();

  showToast(
    lang==="ar"
      ?"🇲🇦 العربية"
      :lang==="fr"
        ?"🇫🇷 Français"
        :"🇬🇧 English"
  );
}

function requestPersistentStorage(){

  if(
    navigator.storage &&
    navigator.storage.persist
  ){

    navigator.storage.persist()
      .then(ok=>{
        showToast(
          ok
            ?"💾 Storage persistent"
            :"ℹ️ Browser ماعطاش persistence"
        );
      });

  }else{

    showToast("ℹ️ Storage API غير متوفر");
  }
}

/* =========================================================
   ACCOUNT
========================================================= */

function openAccountModal(create=false){

  openModal(`
    <div class="modal-head">
      <h2>${create?"➕ Create Account":"🔐 Login"}</h2>
      <button class="close" onclick="closeModal()">×</button>
    </div>

    <label class="field">
      <span>Email</span>
      <input
        class="input"
        id="accountEmail"
        type="email"
        placeholder="name@example.com">
    </label>

    <label class="field">
      <span>Password</span>
      <input
        class="input"
        id="accountPassword"
        type="password"
        placeholder="••••••••">
    </label>

    ${
      create
      ? `
        <label class="field">
          <span>Username</span>
          <input
            class="input"
            id="accountName"
            placeholder="AMINE">
        </label>
      `
      :""
    }

    <button
      class="btn primary full"
      onclick="demoAuth(${create})">
      ${create?"Create Account":"Login"}
    </button>

    <div class="grid grid-3" style="margin-top:10px">

      <button class="btn" onclick="demoProvider('Google')">
        Google
      </button>

      <button class="btn" onclick="demoProvider('Facebook')">
        Facebook
      </button>

      <button class="btn" onclick="demoProvider('Phone')">
        Phone
      </button>

    </div>

    <div class="alert warning" style="margin-top:12px">
      Demo Auth فقط. الربط الحقيقي يحتاج Firebase/Auth Backend.
    </div>
  `);
}

function demoAuth(create){

  const email=
    document.getElementById("accountEmail").value.trim();

  if(!email){

    showToast("⚠️ دخل Email");
    return;
  }

  if(create){

    const name=
      document.getElementById("accountName").value.trim();

    if(name){
      state.name=name;
    }
  }

  state.email=email;

  save();

  closeModal();

  showToast(
    create
      ?"🎉 Account created"
      :"✅ Login successful"
  );

  renderProfile();
}

function demoProvider(provider){

  state.provider=provider;

  save();

  closeModal();

  showToast(`🔐 ${provider} Auth Demo`);
}

/* =========================================================
   MODALS
========================================================= */

function openModal(html){

  const modal=document.getElementById("modal");
  const content=document.getElementById("modalContent");

  content.innerHTML=html;

  modal.classList.add("show");
}

function closeModal(){

  document.getElementById("modal")
    .classList.remove("show");
}

document.getElementById("modal")
  .addEventListener("click",e=>{

    if(e.target.id==="modal"){
      closeModal();
    }

  });

/* =========================================================
   DEVELOPER PANEL
========================================================= */

const adminTabs=[
  ["dashboard","📊 Dashboard"],
  ["users","👥 Users"],
  ["points","💎 Points"],
  ["tasks","🎯 Tasks"],
  ["rewards","🎁 Rewards"],
  ["store","🛒 Store"],
  ["ads","📺 Ads"],
  ["wheel","🎡 Wheel"],
  ["vip","👑 VIP"],
  ["esport","🏆 Esport"],
  ["ai","🤖 AI"],
  ["video","🎬 AI Video"],
  ["voice","🎙️ AI Voice"],
  ["chat","💬 Chat"],
  ["groups","👥 Groups"],
  ["badges","🏅 Badges"],
  ["aura","✨ Aura"],
  ["notifications","🔔 Notifications"],
  ["announcements","📢 Announcements"],
  ["promo","🎟️ Promo Codes"],
  ["images","🖼️ Images"],
  ["social","🔗 Social Links"],
  ["settings","⚙️ App Settings"],
  ["security","🛡️ Security"],
  ["analytics","📈 Analytics"],
  ["debug","🐞 Debug"],
  ["backup","💾 Backup"]
];

let activeAdminTab="dashboard";

function unlockDeveloper(){

  const input=
    document.getElementById("developerCode");

  if(input.value!==DEV_CODE){

    showToast("❌ Wrong Developer Code");
    return;
  }

  state.developer=true;

  save();

  document.getElementById("developerGate")
    .classList.add("hidden");

  document.getElementById("developerPanel")
    .classList.remove("hidden");

  renderAdmin();

  showToast("🛠️ Developer unlocked");
}

function lockDeveloper(){

  state.developer=false;

  save();

  document.getElementById("developerPanel")
    .classList.add("hidden");

  document.getElementById("developerGate")
    .classList.remove("hidden");
}

function renderAdmin(){

  if(!state.developer)return;

  const nav=document.getElementById("adminNav");

  nav.innerHTML=adminTabs.map(([id,label])=>`

    <button
      class="admin-tab ${activeAdminTab===id?"active":""}"
      onclick="adminNavigate('${id}')">
      ${label}
    </button>

  `).join("");

  renderAdminContent();
}

function adminNavigate(tab){

  activeAdminTab=tab;

  renderAdmin();
}

function renderAdminContent(){

  const box=document.getElementById("adminContent");

  if(!box)return;

  const renderers={
    dashboard:adminDashboard,
    users:adminUsers,
    points:adminPoints,
    tasks:adminTasks,
    rewards:adminRewards,
    store:adminStore,
    ads:adminAds,
    wheel:adminWheel,
    vip:adminVip,
    esport:adminEsport,
    ai:adminAI,
    video:adminVideo,
    voice:adminVoice,
    chat:adminChat,
    groups:adminGroups,
    badges:adminBadges,
    aura:adminAura,
    notifications:adminNotifications,
    announcements:adminAnnouncements,
    promo:adminPromo,
    images:adminImages,
    social:adminSocial,
    settings:adminSettings,
    security:adminSecurity,
    analytics:adminAnalytics,
    debug:adminDebug,
    backup:adminBackup
  };

  box.innerHTML=
    (renderers[activeAdminTab]||adminDashboard)();
}

/* ---------- Dashboard ---------- */

function adminDashboard(){

  return `
    <div class="grid grid-4">

      <div class="card">
        <span class="muted">Points</span>
        <div class="stat-big">${state.points}</div>
      </div>

      <div class="card">
        <span class="muted">Ads</span>
        <div class="stat-big">${state.ads}</div>
      </div>

      <div class="card">
        <span class="muted">Games</span>
        <div class="stat-big">${games.length}</div>
      </div>

      <div class="card">
        <span class="muted">Logs</span>
        <div class="stat-big">${state.logs.length}</div>
      </div>

    </div>

    <div class="card" style="margin-top:12px">
      <h3>⚡ Quick Developer Actions</h3>

      <div class="grid grid-3">

        <button
          class="btn primary"
          onclick="adminNavigate('points')">
          + Points
        </button>

        <button
          class="btn"
          onclick="adminNavigate('tasks')">
          Manage Tasks
        </button>

        <button
          class="btn"
          onclick="adminNavigate('store')">
          Manage Store
        </button>

      </div>
    </div>
  `;
}

/* ---------- Users ---------- */

function adminUsers(){

  return `
    <div class="card">
      <h3>👥 Users</h3>

      <div class="table-wrap">
        <table>
          <thead>
            <tr>
              <th>User</th>
              <th>Points</th>
              <th>Level</th>
              <th>Status</th>
            </tr>
          </thead>

          <tbody>

            <tr>
              <td>AMINE</td>
              <td>${state.points}</td>
              <td>${state.level}</td>
              <td>🟢 Active</td>
            </tr>

            <tr>
              <td>FINI Bot</td>
              <td>∞</td>
              <td>AI</td>
              <td>🤖 Online</td>
            </tr>

          </tbody>
        </table>
      </div>
    </div>
  `;
}

/* ---------- Points ---------- */

function adminPoints(){

  return `
    <div class="card">

      <h3>💎 Points Manager</h3>

      <label class="field">
        <span>Amount</span>
        <input
          class="input"
          id="adminPointAmount"
          type="number"
          value="100">
      </label>

      <label class="field">
        <span>Reason</span>
        <input
          class="input"
          id="adminPointReason"
          value="Developer Adjustment">
      </label>

      <div class="grid grid-2">

        <button
          class="btn success"
          onclick="adminAddPoints()">
          ➕ Add Points
        </button>

        <button
          class="btn danger"
          onclick="adminRemovePoints()">
          ➖ Remove Points
        </button>

      </div>

      <div class="alert" style="margin-top:12px">
        Current:
        <b>${state.points} PTS</b>
      </div>

    </div>
  `;
}

function adminAddPoints(){

  const amount=
    Number(document.getElementById("adminPointAmount").value);

  const reason=
    document.getElementById("adminPointReason").value;

  addPoints(amount,reason);

  renderAdmin();
}

function adminRemovePoints(){

  const amount=
    Number(document.getElementById("adminPointAmount").value);

  const reason=
    document.getElementById("adminPointReason").value;

  removePoints(amount,reason);

  renderAdmin();
}

/* ---------- Tasks ---------- */

function adminTasks(){

  return `
    <div class="grid grid-2">

      <div class="card">

        <h3>➕ Add Task</h3>

        <label class="field">
          <span>Title</span>
          <input id="newTaskTitle" class="input">
        </label>

        <label class="field">
          <span>Description</span>
          <input id="newTaskDesc" class="input">
        </label>

        <label class="field">
          <span>Points</span>
          <input id="newTaskPoints" class="input" type="number" value="25">
        </label>

        <label class="field">
          <span>Icon</span>
          <input id="newTaskIcon" class="input" value="🎯">
        </label>

        <button class="btn primary full" onclick="adminAddTask()">
          Add Task
        </button>

      </div>

      <div class="card">
        <h3>🎯 Current Tasks</h3>

        ${allTasks().map(t=>`

          <div class="alert" style="margin-bottom:7px">
            ${t.icon} <b>${esc(t.title)}</b>
            • ${t.points} PTS
            ${
              state.customTasks.some(x=>x.id===t.id)
              ? `
                <button
                  class="btn danger small"
                  onclick="adminDeleteTask('${esc(t.id)}')">
                  Delete
                </button>
              `
              :""
            }
          </div>

        `).join("")}

      </div>

    </div>
  `;
}

function adminAddTask(){

  const title=
    document.getElementById("newTaskTitle").value.trim();

  if(!title){
    showToast("⚠️ Task title");
    return;
  }

  state.customTasks.push({
    id:"custom-task-"+Date.now(),
    title,
    desc:
      document.getElementById("newTaskDesc").value,
    points:
      Number(document.getElementById("newTaskPoints").value)||10,
    icon:
      document.getElementById("newTaskIcon").value||"🎯",
    action:"custom"
  });

  save();
  renderTasks();
  renderAdmin();

  showToast("🎯 Task added");
}

function adminDeleteTask(id){

  state.customTasks=
    state.customTasks.filter(t=>t.id!==id);

  save();

  renderTasks();
  renderAdmin();
}

/* ---------- Rewards ---------- */

function adminRewards(){

  return `
    <div class="card">

      <h3>🎁 Rewards Manager</h3>

      <div class="grid grid-2">

        <label class="field">
          <span>Game</span>
          <input id="newRewardGame" class="input">
        </label>

        <label class="field">
          <span>Package</span>
          <input id="newRewardAmount" class="input">
        </label>

        <label class="field">
          <span>Cost</span>
          <input id="newRewardCost" class="input" type="number" value="1000">
        </label>

        <label class="field">
          <span>Icon</span>
          <input id="newRewardIcon" class="input" value="🎁">
        </label>

      </div>

      <button
        class="btn primary full"
        onclick="adminAddReward()">
        Add Reward
      </button>

      <div style="margin-top:14px">
        ${[
          ...baseRewards,
          ...state.customRewards
        ].map(r=>`

          <div class="alert" style="margin-bottom:7px">
            ${r.icon} ${esc(r.game)}
            • ${esc(r.amount)}
            • ${r.cost} PTS
          </div>

        `).join("")}
      </div>

    </div>
  `;
}

function adminAddReward(){

  const game=
    document.getElementById("newRewardGame").value.trim();

  if(!game)return;

  state.customRewards.push({
    id:"custom-reward-"+Date.now(),
    game,
    amount:
      document.getElementById("newRewardAmount").value,
    cost:
      Number(document.getElementById("newRewardCost").value)||100,
    icon:
      document.getElementById("newRewardIcon").value||"🎁"
  });

  save();
  renderRewards();
  renderAdmin();

  showToast("🎁 Reward added");
}

/* ---------- Store ---------- */

function adminStore(){

  return `
    <div class="card">

      <h3>🛒 Store Manager</h3>

      <div class="grid grid-2">

        <label class="field">
          <span>Game</span>
          <input id="newStoreGame" class="input">
        </label>

        <label class="field">
          <span>Package</span>
          <input id="newStorePackage" class="input">
        </label>

        <label class="field">
          <span>Price DH</span>
          <input id="newStorePrice" class="input" type="number" value="10">
        </label>

        <label class="field">
          <span>Image URL</span>
          <input
            id="newStoreImage"
            class="input"
            value="https://picsum.photos/700/400?random=900">
        </label>

      </div>

      <button
        class="btn primary full"
        onclick="adminAddStore()">
        Add Store Item
      </button>

      <div style="margin-top:14px">
        ${[
          ...baseStore,
          ...state.customStore
        ].map(i=>`

          <div class="alert" style="margin-bottom:7px">
            🎮 ${esc(i.game)}
            • ${esc(i.package)}
            • ${i.price} DH
          </div>

        `).join("")}
      </div>

    </div>
  `;
}

function adminAddStore(){

  const game=
    document.getElementById("newStoreGame").value.trim();

  if(!game)return;

  state.customStore.push({
    id:"custom-store-"+Date.now(),
    game,
    package:
      document.getElementById("newStorePackage").value,
    price:
      Number(document.getElementById("newStorePrice").value)||10,
    image:
      document.getElementById("newStoreImage").value
  });

  save();
  renderStore();
  renderAdmin();

  showToast("🛒 Store item added");
}

/* ---------- Ads ---------- */

function adminAds(){

  return `
    <div class="card">

      <h3>📺 Ads Manager</h3>

      <div class="grid grid-3">

        <div class="card">
          <span class="muted">Watched</span>
          <div class="stat-big">${state.ads}</div>
        </div>

        <div class="card">
          <span class="muted">AI Video Need</span>
          <div class="stat-big">${AI_VIDEO_ADS}</div>
        </div>

        <div class="card">
          <span class="muted">Demo Reward</span>
          <div class="stat-big">25</div>
        </div>

      </div>

      <div class="alert warning" style="margin-top:12px">
        AdMob الحقيقي يحتاج Native Android integration.
      </div>

      <button
        class="btn primary"
        onclick="watchRewardedAd()">
        Test Rewarded Ad
      </button>

    </div>
  `;
}

/* ---------- Wheel ---------- */

function adminWheel(){

  return `
    <div class="card">

      <h3>🎡 Wheel Manager</h3>

      <label class="field">
        <span>Daily Spins</span>
        <input
          id="adminDailySpins"
          class="input"
          type="number"
          value="5">
      </label>

      <button
        class="btn primary"
        onclick="adminSetSpins()">
        Save Spins
      </button>

      <div class="alert" style="margin-top:12px">
        Current Spins:
        <b>${state.spins}</b>
      </div>

    </div>
  `;
}

function adminSetSpins(){

  const amount=
    Number(document.getElementById("adminDailySpins").value)||5;

  state.spins=amount;

  save();

  updateWheel();
  renderAdmin();

  showToast("🎡 Spins updated");
}

/* ---------- VIP ---------- */

function adminVip(){

  return `
    <div class="card">

      <h3>👑 VIP Manager</h3>

      <div class="switch-row">
        <div>
          <b>VIP</b>
          <div class="muted">Current: ${state.vip}</div>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            ${state.vip?"checked":""}
            onchange="state.vip=this.checked;save();renderProfile();">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>VIP+</b>
          <div class="muted">Current: ${state.vipPlus}</div>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            ${state.vipPlus?"checked":""}
            onchange="state.vipPlus=this.checked;save();renderProfile();">
          <i></i>
        </label>
      </div>

    </div>
  `;
}

/* ---------- Esport ---------- */

function adminEsport(){

  return `
    <div class="card">

      <h3>🏆 Esport Manager</h3>

      <div class="alert">
        ${state.tournament
          ?`Tournament: ${state.tournament.players} players`
          :"No active tournament"}
      </div>

      <button
        class="btn primary"
        onclick="navigate('esport')">
        Open Tournament
      </button>

    </div>
  `;
}

/* ---------- AI ---------- */

function adminAI(){

  return `
    <div class="card">

      <h3>🤖 AI Manager</h3>

      <label class="field">
        <span>Bot Name</span>
        <input
          id="adminBotName"
          class="input"
          value="${esc(state.ai.botName)}">
      </label>

      <label class="field">
        <span>Welcome Message</span>
        <textarea
          id="adminBotWelcome"
          class="textarea">${esc(state.ai.welcome)}</textarea>
      </label>

      <div class="switch-row">
        <div>
          <b>Bot Enabled</b>
        </div>

        <label class="switch">
          <input
            id="adminBotEnabled"
            type="checkbox"
            ${state.ai.enabled?"checked":""}>
          <i></i>
        </label>
      </div>

      <button
        class="btn primary full"
        onclick="saveAISettings()">
        Save AI
      </button>

      <div class="alert warning" style="margin-top:12px">
        API URL placeholder:
        <input
          class="input"
          placeholder="https://your-backend.example/api/ai">
      </div>

    </div>
  `;
}

function saveAISettings(){

  state.ai.botName=
    document.getElementById("adminBotName").value;

  state.ai.welcome=
    document.getElementById("adminBotWelcome").value;

  state.ai.enabled=
    document.getElementById("adminBotEnabled").checked;

  save();

  renderAdmin();

  showToast("🤖 AI settings saved");
}

/* ---------- Video ---------- */

function adminVideo(){

  return `
    <div class="card">

      <h3>🎬 AI Video Manager</h3>

      <div class="grid grid-2">

        <div>
          <span class="muted">Required Points</span>
          <div class="stat-big">${AI_VIDEO_POINTS}</div>
        </div>

        <div>
          <span class="muted">Required Ads</span>
          <div class="stat-big">${AI_VIDEO_ADS}</div>
        </div>

      </div>

      <div class="alert warning" style="margin-top:12px">
        Real generation requires an external AI Video API/backend.
      </div>

    </div>
  `;
}

/* ---------- Voice ---------- */

function adminVoice(){

  return `
    <div class="card">

      <h3>🎙️ AI Voice Manager</h3>

      <div class="grid grid-3">

        <div class="badge unlocked">Arabic</div>
        <div class="badge unlocked">French</div>
        <div class="badge unlocked">English</div>

      </div>

      <div class="alert" style="margin-top:12px">
        Browser SpeechSynthesis is used for this demo.
        External TTS API can be connected later.
      </div>

    </div>
  `;
}

/* ---------- Chat ---------- */

function adminChat(){

  return `
    <div class="card">

      <h3>💬 Chat Manager</h3>

      <div class="grid grid-3">

        <div>
          <span class="muted">Messages</span>
          <div class="stat-big">${state.messages.length}</div>
        </div>

        <div>
          <span class="muted">Friends</span>
          <div class="stat-big">${state.friends.length}</div>
        </div>

        <div>
          <span class="muted">Groups</span>
          <div class="stat-big">${state.groups.length}</div>
        </div>

      </div>

      <button
        class="btn danger"
        onclick="state.messages=[];save();renderChat();renderAdmin()">
        🗑️ Clear Chat
      </button>

    </div>
  `;
}

/* ---------- Groups ---------- */

function adminGroups(){

  return `
    <div class="card">

      <h3>👥 Groups Manager</h3>

      ${state.groups.map(g=>`

        <div class="alert" style="margin-bottom:7px">
          👥 <b>${esc(g.name)}</b>
          • ${g.members} members
        </div>

      `).join("")}

    </div>
  `;
}

/* ---------- Badges ---------- */

function adminBadges(){

  return `
    <div class="card">

      <h3>🏅 Badges Manager</h3>

      <div class="grid grid-4">
        ${getBadges().map(b=>`

          <div class="badge-card card">
            ${b.icon}
            <b>${esc(b.name)}</b>
            <span class="muted">${esc(b.category)}</span>
          </div>

        `).join("")}
      </div>

    </div>
  `;
}

/* ---------- Aura ---------- */

function adminAura(){

  return `
    <div class="card">

      <h3>✨ Aura Manager</h3>

      <div class="grid grid-4">

        <button class="card" onclick="showToast('💙 Cyan Aura')">
          💙 Cyan
        </button>

        <button class="card" onclick="showToast('💜 Purple Aura')">
          💜 Purple
        </button>

        <button class="card" onclick="showToast('💛 Gold Aura')">
          💛 Gold
        </button>

        <button class="card" onclick="showToast('❤️ Fire Aura')">
          ❤️ Fire
        </button>

      </div>

    </div>
  `;
}

/* ---------- Notifications ---------- */

function adminNotifications(){

  return `
    <div class="card">

      <h3>🔔 Notifications Manager</h3>

      <label class="field">
        <span>Notification Text</span>
        <input id="adminNotifText" class="input">
      </label>

      <button
        class="btn primary"
        onclick="adminSendNotification()">
        Send Notification
      </button>

    </div>
  `;
}

function adminSendNotification(){

  const text=
    document.getElementById("adminNotifText").value.trim();

  if(!text)return;

  showToast("🔔 "+text);

  log("NOTIFICATION",{
    text
  });

  renderAdmin();
}

/* ---------- Announcements ---------- */

function adminAnnouncements(){

  return `
    <div class="card">

      <h3>📢 Announcements</h3>

      <label class="field">
        <span>Announcement</span>
        <textarea
          id="announcement"
          class="textarea"></textarea>
      </label>

      <button
        class="btn primary"
        onclick="sendAnnouncement()">
        Publish
      </button>

    </div>
  `;
}

function sendAnnouncement(){

  const text=
    document.getElementById("announcement").value.trim();

  if(!text)return;

  showToast("📢 "+text);

  log("ANNOUNCEMENT",{
    text
  });

  renderAdmin();
}

/* ---------- Promo ---------- */

function adminPromo(){

  return `
    <div class="card">

      <h3>🎟️ Promo Codes</h3>

      <div class="alert">
        Current code:
        <b>amine</b>
        → 100 PTS once
      </div>

      <label class="field">
        <span>Developer New Code</span>
        <input
          id="newPromoCode"
          class="input"
          placeholder="NEWCODE">
      </label>

      <button
        class="btn"
        onclick="showToast('ℹ️ Promo system حاليا ثابت: amine')">
        Configure
      </button>

    </div>
  `;
}

/* ---------- Images ---------- */

function adminImages(){

  return `
    <div class="card">

      <h3>🖼️ Images</h3>

      <div class="alert">
        صور الألعاب والـStore قابلة للتغيير من arrays داخل نفس
        index.html.
      </div>

      <label class="field">
        <span>Test Image URL</span>
        <input
          id="testImage"
          class="input"
          value="https://picsum.photos/700/400?random=999">
      </label>

      <button
        class="btn primary"
        onclick="previewAdminImage()">
        Preview
      </button>

      <div id="adminImagePreview" class="ai-preview" style="margin-top:10px"></div>

    </div>
  `;
}

function previewAdminImage(){

  const url=
    document.getElementById("testImage").value;

  document.getElementById("adminImagePreview")
    .innerHTML=`
      <img
        src="${esc(url)}"
        style="
          max-height:240px;
          border-radius:18px">
    `;
}

/* ---------- Social ---------- */

function adminSocial(){

  return `
    <div class="card">

      <h3>🔗 Social Links</h3>

      <div class="alert">
        <b>WhatsApp Channel</b><br>
        ${WA_CHANNEL}
      </div>

      <div class="alert">
        <b>Instagram</b><br>
        ${INSTAGRAM}
      </div>

      <div class="alert">
        <b>YouTube</b><br>
        ${YOUTUBE}
      </div>

      <div class="alert">
        <b>WhatsApp Orders</b><br>
        +212634840119
      </div>

    </div>
  `;
}

/* ---------- Settings ---------- */

function adminSettings(){

  return `
    <div class="card">

      <h3>⚙️ App Settings</h3>

      <div class="switch-row">
        <div>
          <b>Maintenance Mode</b>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            onchange="showToast(this.checked?'🔧 Maintenance ON':'✅ Maintenance OFF')">
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>New Registrations</b>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            checked>
          <i></i>
        </label>
      </div>

      <div class="switch-row">
        <div>
          <b>Chat Enabled</b>
        </div>

        <label class="switch">
          <input
            type="checkbox"
            checked>
          <i></i>
        </label>
      </div>

    </div>
  `;
}

/* ---------- Security ---------- */

function adminSecurity(){

  return `
    <div class="card">

      <h3>🛡️ Security</h3>

      <div class="alert warning">
        Developer Code الحالي:
        <b>AMINE2010</b>
      </div>

      <label class="field">
        <span>New Developer Code</span>
        <input
          class="input"
          id="newDevCode"
          placeholder="غير الكود">
      </label>

      <button
        class="btn danger"
        onclick="changeDevCode()">
        Change Code
      </button>

      <div class="alert" style="margin-top:12px">
        ⚠️ هذا Demo code موجود داخل JavaScript.
        Security حقيقي خاصو Backend.
      </div>

    </div>
  `;
}

function changeDevCode(){

  showToast(
    "ℹ️ فهاد النسخة DEV_CODE ثابت: AMINE2010"
  );
}

/* ---------- Analytics ---------- */

function adminAnalytics(){

  const taskCount=
    Object.keys(state.tasksDone).length;

  return `
    <div class="grid grid-3">

      <div class="card">
        <span class="muted">Tasks Completed</span>
        <div class="stat-big">${taskCount}</div>
      </div>

      <div class="card">
        <span class="muted">Games Played</span>
        <div class="stat-big">${state.logs.filter(l=>l.action==="ADD_POINTS").length}</div>
      </div>

      <div class="card">
        <span class="muted">Ads</span>
        <div class="stat-big">${state.ads}</div>
      </div>

    </div>

    <div class="card" style="margin-top:12px">
      <h3>📈 Activity</h3>

      ${state.logs.slice(0,20).map(l=>`

        <div class="alert" style="margin-bottom:6px">
          <b>${esc(l.action)}</b>
          <span class="muted">
            ${new Date(l.time).toLocaleString()}
          </span>
        </div>

      `).join("")}

    </div>
  `;
}

/* ---------- Debug ---------- */

function adminDebug(){

  return `
    <div class="card">

      <h3>🐞 Debug Console</h3>

      <div class="alert">
        State size:
        ${JSON.stringify(state).length}
        chars
      </div>

      <button
        class="btn danger"
        onclick="console.log(state);showToast('🐞 State logged to console')">
        console.log State
      </button>

      <button
        class="btn"
        onclick="showToast('✅ No known runtime error')">
        Run Diagnostics
      </button>

    </div>
  `;
}

/* ---------- Backup ---------- */

function adminBackup(){

  return `
    <div class="card">

      <h3>💾 Backup / Restore</h3>

      <button
        class="btn primary"
        onclick="exportData()">
        💾 Export JSON
      </button>

      <button
        class="btn"
        onclick="importData()">
        📥 Import JSON
      </button>

      <div class="alert warning" style="margin-top:12px">
        Backup يحتوي state المحلي ديال التطبيق.
      </div>

    </div>
  `;
}

/* =========================================================
   IMPORT / EXPORT
========================================================= */

function exportData(){

  const blob=new Blob(
    [JSON.stringify(state,null,2)],
    {
      type:"application/json"
    }
  );

  const url=URL.createObjectURL(blob);

  const a=document.createElement("a");

  a.href=url;
  a.download="fini-rewards-backup.json";

  a.click();

  URL.revokeObjectURL(url);

  showToast("💾 Backup downloaded");
}

function importData(){

  const input=document.createElement("input");

  input.type="file";
  input.accept=".json,application/json";

  input.onchange=()=>{

    const file=input.files?.[0];

    if(!file)return;

    const reader=new FileReader();

    reader.onload=()=>{

      try{

        const imported=
          JSON.parse(reader.result);

        state={
          ...state,
          ...imported,
          settings:{
            ...state.settings,
            ...(imported.settings||{})
          }
        };

        save();
        updateUI();
        renderAll();

        showToast("📥 Backup restored");

      }catch(e){

        showToast("❌ Invalid JSON");
      }
    };

    reader.readAsText(file);
  };

  input.click();
}

function resetData(){

  if(
    state.settings.confirm &&
    !confirm("متأكد بغيتي تمسح Demo Data؟")
  ){
    return;
  }

  try{
    localStorage.removeItem(APP_KEY);
  }catch(e){}

  location.reload();
}

/* =========================================================
   INIT
========================================================= */

function renderAll(){

  buildGames();
  renderGameFilters();
  renderTasks();
  renderGames();
  renderRewards();
  renderStore();
  renderProfile();
  renderFriends();
  renderChat();
  updateWheel();
  renderTournament();
  renderVideoLock();
  renderVideoHistory();
  renderVoiceHistory();
  updateUI();
}

function applySettings(){

  document.body.classList.toggle(
    "light",
    !state.settings.dark
  );

  document.body.classList.toggle(
    "no-animations",
    !state.settings.animations
  );

  document.documentElement.style
    .setProperty(
      "--scale",
      state.settings.scale||1
    );

  const dark=
    document.getElementById("darkMode");

  if(dark){
    dark.checked=state.settings.dark;
  }

  const animations=
    document.getElementById("animations");

  if(animations){
    animations.checked=state.settings.animations;
  }

  const notifications=
    document.getElementById("notifications");

  if(notifications){
    notifications.checked=
      state.settings.notifications;
  }

  const sounds=
    document.getElementById("sounds");

  if(sounds){
    sounds.checked=state.settings.sounds;
  }

  const language=
    document.getElementById("languageSelect");

  if(language){
    language.value=state.settings.language;
  }

  const scale=
    document.getElementById("fontSize");

  if(scale){
    scale.value=state.settings.scale||1;
  }
}

safeLoad();

seedFriends();

buildGames();

renderAll();

applySettings();

/* Set default tournament time */
const tourStart=document.getElementById("tourStart");

if(tourStart && !tourStart.value){

  const d=new Date();

  d.setMinutes(
    d.getMinutes()+15
  );

  d.setSeconds(0);

  tourStart.value=
    new Date(
      d.getTime()-
      d.getTimezoneOffset()*60000
    )
    .toISOString()
    .slice(0,16);
}

/* keyboard escape */
document.addEventListener("keydown",e=>{

  if(e.key==="Escape"){
    closeModal();
  }

});

/* prevent accidental form reload */
document.addEventListener("submit",e=>{
  e.preventDefault();
});

/* Developer shortcut */
document.addEventListener("keydown",e=>{

  if(
    e.ctrlKey &&
    e.shiftKey &&
    e.key.toLowerCase()==="d"
  ){

    navigate("developer");

  }

});

</script>

</body>
</html>
