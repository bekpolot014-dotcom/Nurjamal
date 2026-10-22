<!DOCTYPE html>
<html lang="ky">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover,user-scalable=no">
<meta name="theme-color" content="#03041a">
<title>Нуржамал ❤️</title>
<style>
:root{
  --pink:#ff5c9d; --rose:#ff8fb8; --gold:#ffd27a; --blush:#ffeaf2; --hw:300px;
  --serif:Georgia,'Palatino Linotype','Book Antiqua',Palatino,'Noto Serif','DejaVu Serif','Times New Roman',serif;
}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
html,body{height:100%;background:#02030a;overflow:hidden;overscroll-behavior:none;touch-action:manipulation;
  font-family:var(--serif);color:var(--blush);-webkit-font-smoothing:antialiased;-webkit-user-select:none;user-select:none}
#stage{position:fixed;inset:0;height:100vh;height:100dvh;overflow:hidden;
  background:radial-gradient(120% 90% at 50% 0%,#0d1448 0%,#070b2b 38%,#03041a 70%,#010208 100%)}
canvas{position:absolute;inset:0;width:100%;height:100%;display:block}
#sky{z-index:0}
#fx{z-index:3;pointer-events:none}

/* Moon */
#moon{position:absolute;z-index:1;top:calc(env(safe-area-inset-top,0px) + 8vh);right:8vw;width:clamp(64px,17vmin,150px);aspect-ratio:1/1;border-radius:50%;
  background:radial-gradient(circle at 34% 30%,#fffef6 0%,#fff4d2 35%,#f6dfa6 68%,#e2bf7c 100%);
  box-shadow:0 0 30px 6px rgba(255,232,170,.45),0 0 90px 28px rgba(255,190,200,.22),inset -10px -8px 20px rgba(190,140,70,.32);
  opacity:0;transform:translateY(-24px) scale(.82);transition:opacity 3.2s ease,transform 3.2s ease}
#moon::before{content:'';position:absolute;inset:0;border-radius:50%;
  background:
  radial-gradient(circle at 62% 30%,rgba(170,125,70,.28) 0 9%,transparent 10%),
  radial-gradient(circle at 36% 58%,rgba(170,125,70,.22) 0 13%,transparent 14%),
  radial-gradient(circle at 70% 66%,rgba(170,125,70,.24) 0 7%,transparent 8%),
  radial-gradient(circle at 26% 28%,rgba(170,125,70,.18) 0 6%,transparent 7%)}
#moon::after{content:'';position:absolute;inset:-60%;border-radius:50%;z-index:-1;
  background:radial-gradient(circle,rgba(255,225,170,.30) 0%,rgba(255,170,200,.10) 40%,transparent 68%);
  animation:halo 6s ease-in-out infinite}
.night #moon{opacity:1;transform:none}
@keyframes halo{0%,100%{transform:scale(1);opacity:.8}50%{transform:scale(1.1);opacity:1}}

/* Hills */
#hills{position:absolute;z-index:2;left:0;bottom:0;width:100%;height:20vh;opacity:0;transition:opacity 3s ease;pointer-events:none}
.night #hills{opacity:1}

#vig{position:absolute;inset:0;z-index:4;pointer-events:none;background:radial-gradient(ellipse at 50% 45%,transparent 52%,rgba(0,0,0,.55) 100%)}
#flash{position:absolute;inset:0;z-index:4;pointer-events:none;opacity:0;background:radial-gradient(circle at 50% 80%,rgba(255,110,170,.28),rgba(255,110,170,0) 60%)}
#flash.pop{animation:flashPop 1.3s ease-out}
@keyframes flashPop{0%{opacity:0}18%{opacity:1}100%{opacity:0}}

/* Cinematic bars (landscape only) */
.bar{position:absolute;left:0;right:0;height:0;background:#000;z-index:5;transition:height 2.6s ease;pointer-events:none}
.bar.top{top:0}.bar.bot{bottom:0}
@media (min-aspect-ratio:11/10){.night .bar{height:5.5vh}}

/* UI */
#ui{position:absolute;inset:0;z-index:6;pointer-events:none}
#ui button{pointer-events:auto}
#music{position:absolute;top:calc(env(safe-area-inset-top,0px) + 2.2vh);left:14px;width:44px;height:44px;border-radius:50%;
  border:1px solid rgba(255,210,122,.4);background:rgba(10,12,40,.55);color:var(--gold);display:flex;align-items:center;justify-content:center;
  cursor:pointer;transition:box-shadow .4s,border-color .4s,transform .2s}
#music:active{transform:scale(.92)}
#music .slash{opacity:1;transition:opacity .3s}
#music.on .slash{opacity:0}
#music.on{box-shadow:0 0 16px rgba(255,200,120,.5);border-color:rgba(255,210,122,.8)}

#header{position:absolute;top:calc(env(safe-area-inset-top,0px) + 3.4vh);left:0;right:0;text-align:center;font-style:italic;
  font-size:clamp(1rem,3.8vw,1.35rem);letter-spacing:.14em;color:#ffe6bf;opacity:0;transition:opacity 2s ease;
  text-shadow:0 0 10px rgba(255,200,120,.75),0 0 28px rgba(255,92,157,.5)}
.night #header{opacity:.85}
.final #header{opacity:0}

/* Intro */
#intro{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;padding-bottom:14vh;
  transition:opacity 1.3s ease,transform 1.3s ease,filter 1.3s ease}
#intro.gone{opacity:0;transform:scale(1.08);filter:blur(8px);pointer-events:none}
#heartSlot{width:min(48vw,26vh,230px);aspect-ratio:1.14/1;margin-bottom:3vh}
#introName{font-style:italic;font-weight:400;white-space:nowrap;font-size:clamp(2.6rem,13vw,6rem);letter-spacing:.02em;color:#fff3da;
  line-height:1.15;animation:glowName 3.6s ease-in-out infinite}
.ch{display:inline-block;opacity:0;transform:translateY(24px) scale(.9);filter:blur(12px)}
.play .ch{animation:chIn 1.4s cubic-bezier(.2,.7,.2,1) forwards;animation-delay:calc(1.7s + var(--i) * .13s)}
.emoin{display:inline-block;margin-left:.12em;animation:emoBeat 1.15s ease-in-out infinite}
#introSub{opacity:0;font-style:italic;letter-spacing:.14em;font-size:clamp(.95rem,3.6vw,1.25rem);color:#ffd9e6;margin-top:1.6vh;
  text-shadow:0 0 12px rgba(255,120,175,.6)}
.play #introSub{animation:fade 1.8s ease 3.4s forwards}
@keyframes chIn{to{opacity:1;transform:none;filter:blur(0)}}
@keyframes fade{to{opacity:.95}}
@keyframes emoBeat{0%,100%{transform:scale(1)}12%{transform:scale(1.22)}26%{transform:scale(1)}38%{transform:scale(1.14)}52%{transform:scale(1)}}
@keyframes glowName{
  0%,100%{text-shadow:0 0 6px rgba(255,235,200,.95),0 0 18px rgba(255,190,110,.75),0 0 44px rgba(255,92,157,.65),0 0 90px rgba(255,60,140,.45)}
  50%{text-shadow:0 0 10px rgba(255,245,220,1),0 0 28px rgba(255,200,120,.9),0 0 64px rgba(255,92,157,.85),0 0 120px rgba(255,60,140,.6)}}

/* Messages */
#msgWrap{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;
  padding:16vh 7vw 22vh;pointer-events:none}
#msgWrap.low{padding-top:52vh}
.orn{width:min(56vw,240px);height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent);opacity:0;transform:scaleX(.15);
  transition:opacity 1.2s ease,transform 1.6s ease;margin:0 auto}
.orn.show{opacity:.85;transform:none}
#orn1{margin-bottom:3.2vh}#orn2{margin-top:3.2vh}
#msg{max-width:min(92vw,760px);text-align:center;font-style:italic;font-weight:400;font-size:clamp(1.45rem,5.8vw,2.7rem);line-height:1.45;
  color:var(--blush);letter-spacing:.01em;text-shadow:0 0 14px rgba(255,120,175,.65),0 0 40px rgba(255,92,157,.35)}
#msg .w{display:inline-block;opacity:0;transform:translateY(22px) scale(.96);filter:blur(10px);
  animation:wIn 1.3s cubic-bezier(.2,.7,.2,1) forwards;animation-delay:calc(var(--i) * .16s)}
#msg .w.gold{color:var(--gold);text-shadow:0 0 14px rgba(255,190,90,.85),0 0 40px rgba(255,160,60,.45)}
#msg.out .w{animation:wOut .9s ease forwards;animation-delay:calc(var(--i) * .03s)}
@keyframes wIn{to{opacity:1;transform:none;filter:blur(0)}}
@keyframes wOut{from{opacity:1;transform:none;filter:blur(0)}to{opacity:0;transform:translateY(-18px) scale(1.03);filter:blur(10px)}}

/* Final */
#finalWrap{position:absolute;left:0;right:0;top:44%;transform:translateY(-50%);display:flex;justify-content:center;opacity:0;pointer-events:none;
  transition:opacity 1.4s ease}
#finalWrap.show{opacity:1}
#finalBox{width:calc(var(--hw) * .68);text-align:center;will-change:transform}
.f1{font-style:italic;font-size:max(15px,calc(var(--hw) * .072));line-height:1.35;color:#fff3f7;
  text-shadow:0 0 12px rgba(255,255,255,.55),0 2px 16px rgba(120,0,50,.8),0 0 36px rgba(255,92,157,.6)}
.f2{margin-top:.45em;font-style:italic;font-weight:700;font-size:max(20px,calc(var(--hw) * .105));line-height:1.15;color:#ffe3a8;
  text-shadow:0 0 10px rgba(255,214,130,.9),0 2px 14px rgba(120,0,50,.85),0 0 40px rgba(255,170,70,.55)}
.fw{display:inline-block;opacity:0;transform:translateY(14px) scale(.94);filter:blur(8px)}
.show .fw{animation:wIn 1.4s cubic-bezier(.2,.7,.2,1) forwards;animation-delay:calc(var(--i) * .2s + .6s)}

/* Controls */
#controls{position:absolute;left:0;right:0;bottom:calc(env(safe-area-inset-bottom,0px) + 4.5vh);display:flex;flex-direction:column;align-items:center;gap:16px}
.cta{position:relative;appearance:none;-webkit-appearance:none;border:1px solid rgba(255,210,122,.6);color:#fff6e6;
  font:600 1.12rem/1 var(--serif);letter-spacing:.06em;padding:17px 40px;min-width:200px;min-height:54px;border-radius:999px;cursor:pointer;
  background:
    linear-gradient(105deg,transparent 35%,rgba(255,255,255,.38) 50%,transparent 65%) -150% 0/60% 100% no-repeat,
    linear-gradient(135deg,#ff5c9d 0%,#c2185b 55%,#ff8a5c 100%);
  box-shadow:0 0 22px rgba(255,92,157,.55),0 0 60px rgba(255,92,157,.25),inset 0 0 18px rgba(255,255,255,.18);
  text-shadow:0 0 10px rgba(255,255,255,.55);
  opacity:0;transform:translateY(14px);pointer-events:none;
  transition:transform .25s ease,opacity .9s ease;animation:shine 3.6s ease-in-out infinite}
.cta.show{opacity:1;transform:none;pointer-events:auto}
.cta.show:active{transform:scale(.95)}
.cta::before{content:'';position:absolute;inset:-2px;border-radius:inherit;border:1px solid rgba(255,140,190,.75);animation:ring 2.6s ease-out infinite;pointer-events:none}
.cta:focus-visible{outline:2px solid var(--gold);outline-offset:4px}
@keyframes ring{0%{transform:scale(1);opacity:.75}100%{transform:scale(1.22,1.55);opacity:0}}
@keyframes shine{0%,35%{background-position:-150% 0,0 0}80%,100%{background-position:250% 0,0 0}}
#dots{display:flex;gap:9px;opacity:0;transition:opacity 2s ease}
.night #dots{opacity:1}
#dots i{display:block;width:6px;height:6px;border-radius:50%;background:rgba(255,255,255,.22);transition:all .7s ease}
#dots i.on{background:var(--gold);box-shadow:0 0 9px var(--gold);transform:scale(1.4)}
#dots i.done{background:rgba(255,143,184,.75)}

@media (max-height:480px){
  #msg{font-size:clamp(1.05rem,4.4vh,1.7rem)}
  #msgWrap{padding-top:12vh;padding-bottom:24vh}
  #msgWrap.low{padding-top:50vh}
  .cta{padding:12px 32px;min-height:46px;font-size:1rem}
}
@media (prefers-reduced-motion:reduce){.cta,.cta::before{animation:none}}
</style>
</head>
<body>
<div id="stage">
  <canvas id="sky"></canvas>
  <div id="moon"></div>
  <svg id="hills" viewBox="0 0 1000 220" preserveAspectRatio="none" aria-hidden="true">
    <defs><linearGradient id="hg" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#1a1244"/><stop offset="1" stop-color="#03040f"/></linearGradient></defs>
    <path d="M0 120 C120 70 240 90 360 118 C480 146 560 70 700 82 C820 92 900 130 1000 100 L1000 220 L0 220Z" fill="#0a0d2e" opacity=".85"/>
    <path d="M0 160 C140 120 260 150 400 150 C540 150 640 110 780 126 C880 138 940 150 1000 140 L1000 220 L0 220Z" fill="url(#hg)"/>
  </svg>
  <canvas id="fx"></canvas>
  <div id="vig"></div>
  <div id="flash"></div>
  <div class="bar top"></div><div class="bar bot"></div>

  <div id="ui">
    <button id="music" type="button" aria-label="Музыка">
      <svg viewBox="0 0 24 24" width="22" height="22" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
        <path d="M9 18V5l11-2v13"/><circle cx="6.5" cy="18" r="2.5"/><circle cx="17.5" cy="16" r="2.5"/><line class="slash" x1="3" y1="3" x2="21" y2="21"/>
      </svg>
    </button>
    <div id="header">Нуржамал ❤️</div>

    <div id="intro">
      <div id="heartSlot"></div>
      <h1 id="introName" aria-label="Нуржамал ❤️"></h1>
      <p id="introSub">Бул сен үчүн…</p>
    </div>

    <div id="msgWrap">
      <div class="orn" id="orn1"></div>
      <div id="msg" aria-live="polite"></div>
      <div class="orn" id="orn2"></div>
    </div>

    <div id="finalWrap"><div id="finalBox"><p class="f1" id="f1"></p><p class="f2" id="f2"></p></div></div>

    <div id="controls">
      <button id="go" class="cta" type="button" disabled><span id="goText">Баштоо ❤️</span></button>
      <div id="dots"></div>
    </div>
  </div>
</div>

<script>
(function(){
'use strict';

/* ================= helpers ================= */
var $=function(s){return document.querySelector(s)};
var TAU=Math.PI*2, PI=Math.PI;
var rand=function(a,b){return a+Math.random()*(b-a)};
var pick=function(a){return a[(Math.random()*a.length)|0]};
var clamp=function(v,a,b){return v<a?a:v>b?b:v};
var lerp=function(a,b,t){return a+(b-a)*t};
var ease=function(t){return t<.5?4*t*t*t:1-Math.pow(-2*t+2,3)/2};
var easeOut=function(t){return 1-Math.pow(1-t,3)};
var easeBack=function(t){var c1=1.70158,c3=c1+1;return 1+c3*Math.pow(t-1,3)+c1*Math.pow(t-1,2)};
var sleep=function(ms){return new Promise(function(r){setTimeout(r,ms)})};
var vib=function(p){try{if(navigator.vibrate)navigator.vibrate(p)}catch(e){}};
var mk=function(w,h){var c=document.createElement('canvas');c.width=w;c.height=h;return c};
function mulberry32(a){return function(){a|=0;a=a+0x6D2B79F5|0;var t=Math.imul(a^a>>>15,1|a);t=t+Math.imul(t^t>>>7,61|t)^t;return((t^t>>>14)>>>0)/4294967296}}

/* ================= texts ================= */
var MSG=[
  "Нуржамал, сен менин жүрөгүмдүн эң кооз бөлүгүсүң.",
  "Сен бар үчүн дүйнөм жарык.",
  "Кандай күн болбосун, кандай сыноо келбесин, мен сени сүйүүнү тандайм.",
  "Сенин күлкүң — менин бактым.",
  "Менин кыялдарымда да, келечегимде да сен барсың.",
  "Бул сүйүүмдүн чеги жок. Мен сени чын жүрөгүмдөн сүйөм."
];
var FIN1="Мен сени чексиз сүйөм,", FIN2="Нуржамал ❤️";

/* ================= elements ================= */
var stage=$('#stage'), sky=$('#sky'), fx=$('#fx');
var sctx=sky.getContext('2d'), fctx=fx.getContext('2d');
var el={
  intro:$('#intro'), introName:$('#introName'), slot:$('#heartSlot'),
  go:$('#go'), goText:$('#goText'), msg:$('#msg'), msgWrap:$('#msgWrap'),
  orn1:$('#orn1'), orn2:$('#orn2'), music:$('#music'), dots:$('#dots'),
  finalWrap:$('#finalWrap'), finalBox:$('#finalBox'), f1:$('#f1'), f2:$('#f2'), flash:$('#flash')
};

/* ================= state ================= */
var W=0,H=0,DPR=1,small=false;
var scene=0, busy=false, Q=1;
var SKY={a:0};
var par={x:0,y:0,tx:0,ty:0};
var F={galaxy:0,petals:0,hearts:0,bfly:0,spark:0,shoot:0};
var T={galaxy:0,petals:0,hearts:0,bfly:0,spark:0,shoot:0};
var BH={x:0,y:0,w:100,alpha:0,sc:1,lastBi:-1,slot:{x:0,y:0,w:100},fin:{x:0,y:0,w:300}};
var INF={a:200,cx:0,cy:0,form:0,alpha:0,parts:[]};
var LN=600, LUT=[];
var STARS=[], SHOOT=[], petals=[], hearts=[], sparks=[], flies=[], ripples=[], HP=[];
var acc={petals:0,hearts:0,spark:0,shoot:0,fly:0};
var galaxy=null, finalBeats=0;
var SPR={};
var BEAT=1.15;

/* ================= sprites ================= */
function glowDot(rgb){
  var s=64,c=mk(s,s),g=c.getContext('2d');
  var gr=g.createRadialGradient(32,32,0,32,32,32);
  gr.addColorStop(0,'rgba(255,255,255,1)');
  gr.addColorStop(.18,'rgba('+rgb+',.95)');
  gr.addColorStop(.5,'rgba('+rgb+',.28)');
  gr.addColorStop(1,'rgba('+rgb+',0)');
  g.fillStyle=gr;g.fillRect(0,0,s,s);return c;
}
function heartPath(g,cx,cy,s,N){
  N=N||90;g.beginPath();
  for(var i=0;i<=N;i++){
    var t=i/N*TAU,st=Math.sin(t);
    var x=16*st*st*st;
    var y=-(13*Math.cos(t)-5*Math.cos(2*t)-2*Math.cos(3*t)-Math.cos(4*t))-2.95;
    if(i)g.lineTo(cx+x*s,cy+y*s);else g.moveTo(cx+x*s,cy+y*s);
  }
  g.closePath();
}
function makeHeart(SZ,hw,stops,glow,blur){
  var c=mk(SZ,SZ),g=c.getContext('2d'),s=hw/32,cx=SZ/2,cy=SZ/2;
  g.save();g.shadowColor=glow;g.shadowBlur=blur;
  heartPath(g,cx,cy,s);
  var gr=g.createRadialGradient(cx-hw*.16,cy-hw*.2,hw*.02,cx,cy,hw*.7);
  stops.forEach(function(a){gr.addColorStop(a[0],a[1])});
  g.fillStyle=gr;g.fill();g.restore();
  g.save();heartPath(g,cx,cy,s);g.clip();
  var h=g.createRadialGradient(cx-hw*.2,cy-hw*.22,0,cx-hw*.2,cy-hw*.22,hw*.38);
  h.addColorStop(0,'rgba(255,255,255,.55)');h.addColorStop(1,'rgba(255,255,255,0)');
  g.fillStyle=h;g.fillRect(0,0,SZ,SZ);g.restore();
  heartPath(g,cx,cy,s);g.lineWidth=Math.max(1,hw*.012);g.strokeStyle='rgba(255,215,230,.5)';g.stroke();
  return c;
}
function petalSprite(cols){
  var w=56,h=72,c=mk(w,h),g=c.getContext('2d');
  g.translate(w/2,h/2);
  g.beginPath();
  g.moveTo(0,h*.46);
  g.bezierCurveTo(w*.62,h*.28,w*.58,-h*.28,w*.1,-h*.46);
  g.quadraticCurveTo(0,-h*.36,-w*.1,-h*.46);
  g.bezierCurveTo(-w*.58,-h*.28,-w*.62,h*.28,0,h*.46);
  g.closePath();
  var gr=g.createLinearGradient(0,-h*.46,0,h*.46);
  gr.addColorStop(0,cols[0]);gr.addColorStop(.55,cols[1]);gr.addColorStop(1,cols[2]);
  g.fillStyle=gr;g.fill();
  g.strokeStyle='rgba(255,255,255,.22)';g.lineWidth=1.2;
  g.beginPath();g.moveTo(0,h*.4);g.quadraticCurveTo(w*.06,0,0,-h*.38);g.stroke();
  return c;
}
function butterflySprite(p){
  var w=150,h=120,c=mk(w,h),g=c.getContext('2d');
  g.translate(w/2,h/2+4);
  g.shadowColor=p[3];g.shadowBlur=14;
  function wing(m){
    g.save();g.scale(m,1);
    g.beginPath();g.moveTo(2,-2);g.bezierCurveTo(8,-42,50,-56,56,-30);g.bezierCurveTo(60,-10,32,-2,2,3);g.closePath();
    var gr=g.createRadialGradient(18,-18,2,26,-14,46);
    gr.addColorStop(0,p[0]);gr.addColorStop(.5,p[1]);gr.addColorStop(1,p[2]);
    g.fillStyle=gr;g.fill();
    g.beginPath();g.moveTo(2,3);g.bezierCurveTo(30,6,46,24,36,36);g.bezierCurveTo(24,46,6,32,2,8);g.closePath();
    var g2=g.createRadialGradient(14,18,2,20,20,28);
    g2.addColorStop(0,p[0]);g2.addColorStop(.55,p[1]);g2.addColorStop(1,p[2]);
    g.fillStyle=g2;g.fill();
    g.restore();
  }
  wing(1);wing(-1);
  g.shadowBlur=0;
  [1,-1].forEach(function(m){
    g.save();g.scale(m,1);
    g.fillStyle='rgba(255,255,255,.75)';
    [[38,-30,2.6],[46,-21,1.8],[28,-40,1.8],[26,26,2.2],[18,34,1.4]].forEach(function(d){g.beginPath();g.arc(d[0],d[1],d[2],0,TAU);g.fill()});
    g.strokeStyle='rgba(255,230,160,.55)';g.lineWidth=1;
    g.beginPath();g.moveTo(3,-1);g.quadraticCurveTo(30,-30,52,-30);g.moveTo(3,0);g.quadraticCurveTo(28,-8,56,-30);g.moveTo(3,5);g.quadraticCurveTo(28,10,36,34);g.stroke();
    g.restore();
  });
  return c;
}
function buildSprites(){
  SPR.dotPink=glowDot('255,110,170');SPR.dotGold=glowDot('255,205,120');
  SPR.dotWhite=glowDot('255,240,250');SPR.dotBlue=glowDot('150,180,255');
  SPR.dots=[SPR.dotPink,SPR.dotGold,SPR.dotGold,SPR.dotWhite,SPR.dotPink];
  var gl=mk(256,256),g=gl.getContext('2d');
  var gr=g.createRadialGradient(128,128,0,128,128,128);
  gr.addColorStop(0,'rgba(255,80,150,.85)');gr.addColorStop(.35,'rgba(255,60,140,.35)');gr.addColorStop(1,'rgba(255,40,120,0)');
  g.fillStyle=gr;g.fillRect(0,0,256,256);SPR.glow=gl;
  SPR.petals=[['#ff9ec0','#e0245e','#7a0c35'],['#ffb3cc','#f0457f','#8d1244'],['#ffd0dd','#ff6f9c','#b02156']].map(petalSprite);
  SPR.hearts=[
    makeHeart(96,54,[[0,'#ffc0d6'],[.5,'#ff5c9d'],[1,'#c2185b']],'rgba(255,90,160,.9)',14),
    makeHeart(96,54,[[0,'#fff1c9'],[.5,'#ffc65a'],[1,'#e08a1e']],'rgba(255,200,100,.9)',14),
    makeHeart(96,54,[[0,'#ffffff'],[.5,'#ffc9dc'],[1,'#ff7aa8']],'rgba(255,170,210,.9)',14)
  ];
  SPR.bigHeart=makeHeart(640,400,[[0,'#ff9fc0'],[.45,'#ff3f7f'],[1,'#a3104a']],'rgba(255,60,130,.9)',70);
  SPR.bf=[
    ['#fff0cf','#ff7eb6','#a23cc4','rgba(255,130,190,.9)'],
    ['#e8f0ff','#8fa8ff','#6a3fd0','rgba(150,170,255,.9)'],
    ['#fff7e0','#ffc766','#ff6f91','rgba(255,200,120,.9)']
  ].map(butterflySprite);
}

/* ================= galaxy & stars ================= */
function buildGalaxy(){
  var s=.5,gw=Math.max(8,Math.round((W+40)*s)),gh=Math.max(8,Math.round((H+40)*s));
  var c=mk(gw,gh),g=c.getContext('2d'),rnd=mulberry32(11);
  var gs=function(){return(rnd()+rnd()+rnd()+rnd()-2)/2};
  var diag=Math.hypot(gw,gh),ang=-.62,dx=Math.cos(ang),dy=Math.sin(ang),nx=-dy,ny=dx;
  var cx=gw*.5,cy=gh*.46,i,u,off,x,y;
  g.globalCompositeOperation='lighter';
  var pal=['255,86,160','170,90,255','90,120,255','255,190,110','255,120,200'];
  for(i=0;i<64;i++){
    u=(rnd()-.5)*1.25;off=gs()*diag*.07;
    x=cx+dx*u*diag+nx*off;y=cy+dy*u*diag+ny*off;
    var r=diag*(.07+rnd()*.15),col=pal[Math.floor(rnd()*pal.length)],al=(.035+rnd()*.06).toFixed(3);
    var gr=g.createRadialGradient(x,y,0,x,y,r);
    gr.addColorStop(0,'rgba('+col+','+al+')');gr.addColorStop(1,'rgba('+col+',0)');
    g.fillStyle=gr;g.fillRect(x-r,y-r,r*2,r*2);
  }
  var cr=diag*.2,cg=g.createRadialGradient(cx,cy,0,cx,cy,cr);
  cg.addColorStop(0,'rgba(255,214,150,.20)');cg.addColorStop(.5,'rgba(255,120,190,.07)');cg.addColorStop(1,'rgba(255,120,190,0)');
  g.fillStyle=cg;g.fillRect(cx-cr,cy-cr,cr*2,cr*2);
  for(i=0;i<1500;i++){
    u=(rnd()-.5)*1.3;off=gs()*diag*.05*(1+.5*Math.abs(u));
    x=cx+dx*u*diag+nx*off;y=cy+dy*u*diag+ny*off;
    var a=(.12+rnd()*.5).toFixed(2),sz=.4+rnd()*.9,q=rnd();
    g.fillStyle='rgba('+(q<.5?'255,235,245':q<.75?'190,210,255':'255,210,160')+','+a+')';
    g.fillRect(x,y,sz,sz);
  }
  galaxy=c;
}
function buildStars(){
  STARS.length=0;
  var n=Math.round(clamp(W*H/4200,140,420));
  var cols=['255,255,255','255,240,245','255,226,170','200,220,255','255,200,225'];
  for(var i=0;i<n;i++){
    var l=Math.random();
    STARS.push({x:Math.random(),y:Math.random(),l:l,
      r:(.35+Math.pow(Math.random(),3)*1.5)*(.6+l*.7),a:rand(.35,1),f:rand(.6,2.6),p:rand(0,TAU),
      v:.0003+l*.0012,col:'rgb('+pick(cols)+')'});
  }
}

/* ================= music ================= */
var Music=(function(){
  var ctx=null,master=null,bus=null,dry=null,timer=null,nextT=0,step=0,running=false,touched=false;
  var BPM=62,EIGHTH=60/BPM/2;
  var mf=function(m){return 440*Math.pow(2,(m-69)/12)};
  var CH=[
    {bass:45,arp:[57,60,64,69],pad:[57,60,64]},
    {bass:41,arp:[53,57,60,65],pad:[53,57,60]},
    {bass:48,arp:[55,60,64,67],pad:[55,60,64]},
    {bass:43,arp:[55,59,62,67],pad:[55,59,62]}
  ];
  var MEL=[
    [[0,76],[2,79],[3,81],[4,79],[6,76]],
    [[0,77],[2,81],[4,79],[5,77],[6,76]],
    [[0,72],[2,76],[3,79],[4,84],[6,79]],
    [[0,79],[2,74],[3,76],[4,74],[6,71]],
    [[0,81],[3,79],[4,76],[6,79]],
    [[0,77],[2,81],[4,84],[6,81]],
    [[0,79],[2,76],[3,72],[4,76],[6,79]],
    [[0,74],[3,71],[4,67]]
  ];
  var ARP=[0,1,2,3,2,1,2,1];

  function impulse(sec,decay){
    var rate=ctx.sampleRate,len=Math.floor(rate*sec),buf=ctx.createBuffer(2,len,rate);
    for(var c=0;c<2;c++){var d=buf.getChannelData(c);for(var i=0;i<len;i++){d[i]=(Math.random()*2-1)*Math.pow(1-i/len,decay)}}
    return buf;
  }
  function init(){
    var AC=window.AudioContext||window.webkitAudioContext;
    if(!AC)return false;
    try{
      ctx=new AC();
      master=ctx.createGain();master.gain.value=0;
      var comp=ctx.createDynamicsCompressor();comp.threshold.value=-18;comp.ratio.value=3;
      bus=ctx.createGain();dry=ctx.createGain();dry.gain.value=.8;
      var conv=ctx.createConvolver();conv.buffer=impulse(2.8,2.4);
      var lp=ctx.createBiquadFilter();lp.type='lowpass';lp.frequency.value=3200;
      var wet=ctx.createGain();wet.gain.value=.55;
      bus.connect(dry);bus.connect(wet);wet.connect(conv);conv.connect(lp);lp.connect(master);
      dry.connect(master);master.connect(comp);comp.connect(ctx.destination);
      return true;
    }catch(e){ctx=null;return false}
  }
  function pluck(t,m,vol,dur){
    var o=ctx.createOscillator(),o2=ctx.createOscillator(),g=ctx.createGain(),g2=ctx.createGain();
    o.type='sine';o.frequency.value=mf(m);
    o2.type='triangle';o2.frequency.value=mf(m)*2;g2.gain.value=.22;
    o.connect(g);o2.connect(g2);g2.connect(g);
    g.gain.setValueAtTime(0,t);
    g.gain.linearRampToValueAtTime(vol,t+.012);
    g.gain.exponentialRampToValueAtTime(.0001,t+dur);
    g.connect(bus);
    o.start(t);o2.start(t);o.stop(t+dur+.05);o2.stop(t+dur+.05);
  }
  function padNote(t,m,dur,vol){
    var lp=ctx.createBiquadFilter();lp.type='lowpass';lp.frequency.value=900;
    var g=ctx.createGain();
    g.gain.setValueAtTime(0,t);
    g.gain.linearRampToValueAtTime(vol,t+1.4);
    g.gain.setValueAtTime(vol,t+dur-1.4);
    g.gain.linearRampToValueAtTime(0,t+dur);
    lp.connect(g);g.connect(bus);
    [-7,7].forEach(function(det){
      var o=ctx.createOscillator();o.type='triangle';o.frequency.value=mf(m);o.detune.value=det;
      o.connect(lp);o.start(t);o.stop(t+dur+.1);
    });
  }
  function bass(t,m,vol,dur){
    var o=ctx.createOscillator(),g=ctx.createGain();
    o.type='sine';o.frequency.value=mf(m);
    g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(vol,t+.05);
    g.gain.exponentialRampToValueAtTime(.0001,t+dur);
    o.connect(g);g.connect(bus);o.start(t);o.stop(t+dur+.05);
  }
  function schedule(){
    if(!ctx||!running)return;
    var horizon=ctx.currentTime+.6;
    while(nextT<horizon){
      var bar=Math.floor(step/8)%8,slot=step%8,ch=CH[bar%4];
      if(slot===0){
        bass(nextT,ch.bass,.17,EIGHTH*8);
        ch.pad.forEach(function(m){padNote(nextT,m,EIGHTH*8*1.08,.026)});
      }
      pluck(nextT,ch.arp[ARP[slot]],slot%2?.05:.068,1.7);
      var mel=MEL[bar];
      for(var i=0;i<mel.length;i++){if(mel[i][0]===slot)pluck(nextT,mel[i][1],.08,2.6)}
      nextT+=EIGHTH;step++;
    }
  }
  return{
    isOn:function(){return running},
    isTouched:function(){return touched},
    available:function(){return !!(window.AudioContext||window.webkitAudioContext)},
    enable:function(){
      touched=true;
      if(!ctx&&!init())return Promise.resolve(false);
      var p=ctx.resume();
      if(!running){
        running=true;nextT=ctx.currentTime+.15;
        clearInterval(timer);timer=setInterval(schedule,110);schedule();
        master.gain.cancelScheduledValues(ctx.currentTime);
        master.gain.setValueAtTime(master.gain.value,ctx.currentTime);
        master.gain.linearRampToValueAtTime(.85,ctx.currentTime+3.5);
      }
      return Promise.resolve(p).then(function(){return true},function(){return true});
    },
    disable:function(){
      if(!ctx)return;
      running=false;clearInterval(timer);
      master.gain.cancelScheduledValues(ctx.currentTime);
      master.gain.setValueAtTime(master.gain.value,ctx.currentTime);
      master.gain.linearRampToValueAtTime(0,ctx.currentTime+.5);
      setTimeout(function(){if(!running&&ctx&&ctx.suspend)ctx.suspend()},650);
    },
    pause:function(){if(ctx&&running&&ctx.suspend)ctx.suspend()},
    resume:function(){if(ctx&&running&&ctx.resume)ctx.resume()},
    thump:function(delay,vol){
      if(!ctx||!running)return;
      var t=ctx.currentTime+(delay||0),o=ctx.createOscillator(),g=ctx.createGain();
      o.type='sine';o.frequency.setValueAtTime(95,t);o.frequency.exponentialRampToValueAtTime(42,t+.2);
      g.gain.setValueAtTime(0,t);g.gain.linearRampToValueAtTime(vol||.4,t+.012);g.gain.exponentialRampToValueAtTime(.0001,t+.3);
      o.connect(g);g.connect(dry);o.start(t);o.stop(t+.35);
    }
  };
})();

/* ================= tweens ================= */
var tweens=[];
function tween(o,k,to,ms,ez){
  ez=ez||ease;
  return new Promise(function(res){
    for(var i=tweens.length-1;i>=0;i--){if(tweens[i].o===o&&tweens[i].k===k){tweens[i].res();tweens.splice(i,1)}}
    tweens.push({o:o,k:k,from:o[k],to:to,t0:performance.now(),ms:ms,ez:ez,res:res});
  });
}
function runTweens(now){
  for(var i=tweens.length-1;i>=0;i--){
    var w=tweens[i],p=clamp((now-w.t0)/w.ms,0,1);
    w.o[w.k]=w.from+(w.to-w.from)*w.ez(p);
    if(p>=1){tweens.splice(i,1);w.res()}
  }
}

/* ================= particles ================= */
function maxSp(){return Math.round((small?220:380)*Q)}
function addPetal(x,y,vy){
  petals.push({x:x==null?rand(-20,W+20):x,y:y==null?rand(-50,-10):y,vx:rand(-14,14),vy:vy||rand(34,78),
    sw:rand(18,46),sf:rand(.6,1.4),sp:rand(0,TAU),rot:rand(0,TAU),vr:rand(-1.4,1.4),fl:rand(0,TAU),vf:rand(1.2,3.2),
    sz:rand(14,28)*(small?.9:1),a:rand(.7,.95),s:Math.floor(rand(0,3))});
}
function addHeart(x,y){
  var vy=rand(40,95),yy=y==null?H+30:y;
  hearts.push({x:x==null?rand(W*.05,W*.95):x,y:yy,vy:vy,vx:rand(-10,10),sw:rand(10,28),sf:rand(.5,1.3),sp:rand(0,TAU),
    sz:rand(11,30),k:Math.floor(rand(0,3)),a0:rand(.55,.95),rot:rand(-.4,.4),life:0,max:(yy+40)/vy});
}
function addSpark(x,y,o){
  if(sparks.length>maxSp())return;
  var s={x:x,y:y,vx:rand(-8,8),vy:rand(-22,-6),g:-4,dr:.6,life:0,max:rand(1.2,2.6),sz:rand(7,15),a:rand(.6,1),ph:rand(0,TAU),kind:'dot',spr:pick(SPR.dots)};
  if(o)for(var k in o)s[k]=o[k];
  sparks.push(s);
}
function burst(x,y,n,o){
  o=o||{};
  for(var i=0;i<n&&sparks.length<maxSp()+200;i++){
    var a=rand(0,TAU),sp=rand(30,o.speed||260)*(.4+Math.random()*.6),heart=Math.random()<(o.heart||0);
    sparks.push({x:x,y:y,vx:Math.cos(a)*sp,vy:Math.sin(a)*sp-(o.up||0),g:o.g!=null?o.g:80,dr:.32,life:0,max:rand(1.1,2.4),
      sz:heart?rand(9,20):rand(8,22),a:rand(.7,1),ph:rand(0,TAU),kind:heart?'heart':'dot',spr:heart?pick(SPR.hearts):pick(SPR.dots)});
  }
}
function addFly(){
  var e=Math.floor(rand(0,4)),x,y,th;
  if(e===0){x=-30;y=rand(H*.2,H*.8);th=rand(-.5,.5)}
  else if(e===1){x=W+30;y=rand(H*.2,H*.8);th=PI+rand(-.5,.5)}
  else if(e===2){x=rand(W*.2,W*.8);y=-30;th=PI/2+rand(-.5,.5)}
  else{x=rand(W*.2,W*.8);y=H+30;th=-PI/2+rand(-.5,.5)}
  flies.push({x:x,y:y,th:th,v:rand(34,62),sz:rand(34,56)*(small?.9:1),ph:rand(0,TAU),fr:rand(14,24),n1:rand(.4,.9),n2:rand(1,1.9),
    p1:rand(0,TAU),p2:rand(0,TAU),amp:rand(.8,1.7),spr:Math.floor(rand(0,3)),leave:false,age:0,tr:0,la:0});
}

/* infinity */
function buildInf(){
  INF.a=Math.min(W*.41,300,H*.5);
  INF.cx=W/2;INF.cy=H*.34;
  LUT.length=0;
  for(var i=0;i<LN;i++){
    var t=i/LN*TAU,d=1+Math.sin(t)*Math.sin(t);
    var x=Math.cos(t)/d,y=Math.sin(t)*Math.cos(t)/d;
    var t2=t+.002,d2=1+Math.sin(t2)*Math.sin(t2);
    var x2=Math.cos(t2)/d2,y2=Math.sin(t2)*Math.cos(t2)/d2;
    var tx=x2-x,ty=y2-y,l=Math.hypot(tx,ty)||1;
    LUT.push({x:x,y:y,nx:-ty/l,ny:tx/l});
  }
  var n=small?230:400;
  INF.parts=[];
  for(var j=0;j<n;j++){
    var r=Math.random(),ang=rand(0,TAU),R=Math.max(W,H)*rand(.35,.75);
    INF.parts.push({u:j/n+rand(-.4,.4)/n,spd:rand(.75,1.25),off:(Math.random()+Math.random()+Math.random()-1.5)*INF.a*.045,
      sz:rand(8,20),spr:r<.5?SPR.dotPink:r<.82?SPR.dotGold:SPR.dotWhite,ph:rand(0,TAU),dl:rand(0,.4),
      sx:INF.cx+Math.cos(ang)*R,sy:INF.cy+Math.sin(ang)*R});
  }
}
function buildHP(){
  HP.length=0;
  var n=small?150:260;
  for(var i=0;i<n;i++){
    var r=Math.random();
    HP.push({t:rand(0,TAU),v:rand(.12,.42)*(Math.random()<.5?1:-1),r:rand(.97,1.1),sz:rand(8,19),ph:rand(0,TAU),
      spr:r<.55?SPR.dotPink:r<.85?SPR.dotGold:SPR.dotWhite});
  }
}

/* ================= layout ================= */
function layout(){
  var r=el.slot.getBoundingClientRect();
  BH.slot={x:r.left+r.width/2,y:r.top+r.height/2,w:r.width};
  var fw=Math.min(W*.96,H*.58*1.139,880);
  BH.fin={x:W/2,y:H*.44,w:fw};
  document.documentElement.style.setProperty('--hw',fw+'px');
  if(scene===0){BH.x=BH.slot.x;BH.y=BH.slot.y;BH.w=BH.slot.w}
  else if(scene===7){BH.x=BH.fin.x;BH.y=BH.fin.y;BH.w=BH.fin.w}
  buildInf();
}
function resize(){
  W=window.innerWidth;H=window.innerHeight;
  DPR=Math.min(window.devicePixelRatio||1,2);
  small=Math.min(W,H)<600;
  [sky,fx].forEach(function(c){c.width=Math.max(1,Math.round(W*DPR));c.height=Math.max(1,Math.round(H*DPR))});
  buildStars();buildGalaxy();layout();
}
var rzT=null;
function onResize(){clearTimeout(rzT);rzT=setTimeout(resize,120)}

/* ================= drawing ================= */
function beatVal(t){
  var p=(t%BEAT)/BEAT;
  var g=function(c,w){return Math.exp(-((p-c)*(p-c))/(w*w))};
  return Math.min(1,g(.10,.045)+.62*g(.30,.05));
}

function drawSky(t,dt){
  var c=sctx,i;
  c.setTransform(DPR,0,0,DPR,0,0);c.clearRect(0,0,W,H);
  c.globalCompositeOperation='source-over';
  if(galaxy&&F.galaxy>.01){
    c.globalAlpha=clamp(F.galaxy,0,1)*(.92+.08*Math.sin(t*.4));
    c.drawImage(galaxy,-20+par.x*.5,-20+par.y*.5,W+40,H+40);
  }
  var sa=SKY.a;
  for(i=0;i<STARS.length;i++){
    var s=STARS[i],x=(s.x+t*s.v)%1;
    var px=x*W+par.x*(.3+s.l),py=s.y*H+par.y*(.3+s.l);
    var a=s.a*(.55+.45*Math.sin(t*s.f+s.p))*sa;
    if(a<.02)continue;
    c.globalAlpha=a;c.fillStyle=s.col;
    c.beginPath();c.arc(px,py,s.r,0,TAU);c.fill();
    if(s.r>1.15){c.globalAlpha=a*.4;c.drawImage(SPR.dotWhite,px-s.r*5,py-s.r*5,s.r*10,s.r*10)}
  }
  // shooting stars
  acc.shoot+=F.shoot*dt;
  if(acc.shoot>=1){acc.shoot=0;if(SHOOT.length<2)SHOOT.push({x:rand(W*.35,W*1.05),y:rand(0,H*.4),vx:-rand(500,820),vy:rand(240,420),life:0,max:rand(.6,1)})}
  c.globalCompositeOperation='lighter';
  for(i=SHOOT.length-1;i>=0;i--){
    var h=SHOOT[i];h.life+=dt;if(h.life>h.max){SHOOT.splice(i,1);continue}
    h.x+=h.vx*dt;h.y+=h.vy*dt;
    var f=1-h.life/h.max,tx=h.x-h.vx*.14,ty=h.y-h.vy*.14;
    var lg=c.createLinearGradient(h.x,h.y,tx,ty);
    lg.addColorStop(0,'rgba(255,245,235,'+(f*.95).toFixed(3)+')');lg.addColorStop(1,'rgba(255,170,210,0)');
    c.globalAlpha=1;c.strokeStyle=lg;c.lineWidth=1.7;c.lineCap='round';
    c.beginPath();c.moveTo(h.x,h.y);c.lineTo(tx,ty);c.stroke();
  }
  c.globalAlpha=1;c.globalCompositeOperation='source-over';
}

function drawFx(t,dt){
  var c=fctx,i;
  c.setTransform(DPR,0,0,DPR,0,0);c.clearRect(0,0,W,H);
  var rs=Q*(small?.8:1);

  /* spawns */
  acc.petals+=F.petals*rs*dt;
  while(acc.petals>=1){acc.petals-=1;if(petals.length<(small?46:80))addPetal()}
  acc.hearts+=F.hearts*rs*dt;
  while(acc.hearts>=1){acc.hearts-=1;if(hearts.length<(small?22:40))addHeart()}
  acc.spark+=F.spark*rs*dt;
  while(acc.spark>=1){acc.spark-=1;addSpark(rand(0,W),rand(H*.1,H*.95))}
  var tgt=Math.round(T.bfly*(small?.8:1)),active=0;
  for(i=0;i<flies.length;i++)if(!flies[i].leave)active++;
  acc.fly-=dt;
  if(acc.fly<=0){
    acc.fly=rand(.7,1.6);
    if(active<tgt)addFly();
    else if(active>tgt){for(i=0;i<flies.length;i++){if(!flies[i].leave){flies[i].leave=true;flies[i].la=Math.atan2(flies[i].y-H/2,flies[i].x-W/2);break}}}
  }

  /* ---- big heart ---- */
  if(BH.alpha>.01){
    var bi=Math.floor(t/BEAT);
    if(bi!==BH.lastBi){
      BH.lastBi=bi;
      if(BH.alpha>.2){
        ripples.push({t0:t+.10*BEAT});
        if(scene===7&&BH.alpha>.6){
          Music.thump(.10*BEAT,.42);Music.thump(.30*BEAT,.26);
          if(finalBeats++<4)vib([22,70,16]);
          addHeart(BH.x+rand(-BH.w*.4,BH.w*.4),BH.y+rand(-BH.w*.1,BH.w*.3));
        }
      }
    }
    var b=beatVal(t),sc=BH.sc*(1+.15*b),w=BH.w*sc;
    c.globalCompositeOperation='lighter';
    var gw=w*2.3;c.globalAlpha=BH.alpha*(.30+.5*b);
    c.drawImage(SPR.glow,BH.x-gw/2,BH.y-gw/2,gw,gw);
    c.globalCompositeOperation='source-over';
    var k=w/400,S=640*k;
    c.globalAlpha=BH.alpha;c.drawImage(SPR.bigHeart,BH.x-S/2,BH.y-S/2,S,S);
    c.globalCompositeOperation='lighter';
    for(i=ripples.length-1;i>=0;i--){
      var rp=ripples[i],age=t-rp.t0;
      if(age>1.8){ripples.splice(i,1);continue}
      if(age<0)continue;
      c.globalAlpha=BH.alpha*(1-age/1.8)*.55;
      c.strokeStyle='rgb(255,130,180)';c.lineWidth=2;
      heartPath(c,BH.x,BH.y,(BH.w*BH.sc*(1.05+age*.6))/32,70);c.stroke();
    }
    if(scene===7&&HP.length){
      var s32=w/32;
      for(i=0;i<HP.length;i++){
        var p=HP[i];p.t+=p.v*dt;
        var st=Math.sin(p.t);
        var hx=BH.x+16*st*st*st*s32*p.r,hy=BH.y+(-(13*Math.cos(p.t)-5*Math.cos(2*p.t)-2*Math.cos(3*p.t)-Math.cos(4*p.t))-2.95)*s32*p.r;
        c.globalAlpha=BH.alpha*(.5+.5*Math.sin(t*3+p.ph))*.9;
        var ps=p.sz*(.8+.5*b);c.drawImage(p.spr,hx-ps/2,hy-ps/2,ps,ps);
      }
    }
    if(scene===7){el.finalBox.style.transform='scale('+(1+.028*b).toFixed(4)+')'}
  }

  /* ---- infinity ---- */
  if(INF.alpha>.01){
    c.globalCompositeOperation='lighter';
    var a=INF.a,cx=INF.cx,cy=INF.cy,form=INF.form,j;
    var lineA=INF.alpha*clamp((form-.5)*2,0,1);
    if(lineA>.01){
      c.lineJoin='round';
      var ws=[7,1.4],als=[.07,.3];
      for(var q=0;q<2;q++){
        c.globalAlpha=lineA*als[q];c.strokeStyle='rgb(255,150,200)';c.lineWidth=ws[q];
        c.beginPath();
        for(j=0;j<LN;j+=4){var e=LUT[j];if(j)c.lineTo(cx+e.x*a,cy+e.y*a);else c.moveTo(cx+e.x*a,cy+e.y*a)}
        c.closePath();c.stroke();
      }
    }
    var n=Math.floor(INF.parts.length*Math.min(1,Q+.15));
    for(i=0;i<n;i++){
      var pp=INF.parts[i];
      var kk=easeOut(clamp((form-pp.dl)/.6,0,1));
      pp.u+=dt*.045*pp.spd;
      var idx=(((pp.u%1)+1)%1*LN)|0,le=LUT[idx];
      var wob=1+.6*Math.sin(t*2.2+pp.ph);
      var ex=cx+le.x*a+le.nx*pp.off*wob,ey=cy+le.y*a+le.ny*pp.off*wob;
      var x=pp.sx+(ex-pp.sx)*kk,y=pp.sy+(ey-pp.sy)*kk;
      c.globalAlpha=INF.alpha*(.55+.45*Math.sin(t*3+pp.ph*3))*(.25+.75*kk);
      var ss=pp.sz*(.8+.4*kk);
      c.drawImage(pp.spr,x-ss/2,y-ss/2,ss,ss);
    }
    for(var hh=0;hh<2;hh++){
      var hu=t*.09+hh*.5;
      for(j=0;j<26;j++){
        var uu=hu-j*.0045,le2=LUT[(((uu%1)+1)%1*LN)|0],f=1-j/26;
        c.globalAlpha=INF.alpha*clamp(form*1.4-.3,0,1)*f*f;
        var cs=10+34*f*f;
        c.drawImage(j<3?SPR.dotWhite:SPR.dotGold,cx+le2.x*a-cs/2,cy+le2.y*a-cs/2,cs,cs);
      }
    }
  }

  /* ---- floating hearts ---- */
  c.globalCompositeOperation='source-over';
  for(i=hearts.length-1;i>=0;i--){
    var hr=hearts[i];hr.life+=dt;
    if(hr.life>=hr.max){hearts.splice(i,1);continue}
    hr.y-=hr.vy*dt;hr.x+=(hr.vx+Math.sin(t*hr.sf+hr.sp)*hr.sw)*dt;
    var al=hr.a0*Math.pow(Math.sin(PI*clamp(hr.life/hr.max,0,1)),.6);
    c.globalAlpha=al;
    c.save();c.translate(hr.x,hr.y);c.rotate(hr.rot+Math.sin(t*hr.sf+hr.sp)*.25);
    var hk=hr.sz/54;c.drawImage(SPR.hearts[hr.k],-48*hk,-48*hk,96*hk,96*hk);c.restore();
  }

  /* ---- petals ---- */
  var wind=Math.sin(t*.2)*12;
  for(i=petals.length-1;i>=0;i--){
    var pt=petals[i];
    pt.y+=pt.vy*dt;pt.x+=(pt.vx+wind+Math.sin(t*pt.sf+pt.sp)*pt.sw)*dt;pt.rot+=pt.vr*dt;pt.fl+=pt.vf*dt;
    if(pt.y>H+40||pt.x<-80||pt.x>W+80){petals.splice(i,1);continue}
    c.globalAlpha=pt.a;
    c.save();c.translate(pt.x,pt.y);c.rotate(pt.rot);c.scale(1,.3+.7*Math.abs(Math.cos(pt.fl)));
    var psh=pt.sz,psw=pt.sz*.78;c.drawImage(SPR.petals[pt.s],-psw/2,-psh/2,psw,psh);c.restore();
  }

  /* ---- butterflies ---- */
  for(i=flies.length-1;i>=0;i--){
    var f2=flies[i];f2.age+=dt;
    var turn=(Math.sin(t*f2.n1+f2.p1)+.6*Math.sin(t*f2.n2+f2.p2))*f2.amp;
    if(f2.leave){
      var dd=f2.la-f2.th;dd=Math.atan2(Math.sin(dd),Math.cos(dd));turn+=dd*2;
      if(f2.x<-90||f2.x>W+90||f2.y<-90||f2.y>H+90){flies.splice(i,1);continue}
    }else if(f2.age>3&&(f2.x<60||f2.x>W-60||f2.y<60||f2.y>H-60)){
      var tg=Math.atan2(H/2-f2.y,W/2-f2.x),d2=tg-f2.th;d2=Math.atan2(Math.sin(d2),Math.cos(d2));turn+=d2*2.2;
    }
    f2.th+=turn*dt;
    f2.x+=Math.cos(f2.th)*f2.v*dt;
    f2.y+=Math.sin(f2.th)*f2.v*dt+Math.sin(t*3+f2.ph)*10*dt;
    f2.ph+=dt*f2.fr;
    f2.tr-=dt;
    if(f2.tr<=0){f2.tr=.08;addSpark(f2.x-Math.cos(f2.th)*8,f2.y-Math.sin(f2.th)*8,{max:rand(.8,1.3),sz:rand(5,10),vy:rand(-10,4),g:6})}
    c.globalCompositeOperation='lighter';
    var hrad=f2.sz*.75;c.globalAlpha=.35;c.drawImage(SPR.dotPink,f2.x-hrad,f2.y-hrad,hrad*2,hrad*2);
    c.globalCompositeOperation='source-over';
    c.save();c.translate(f2.x,f2.y);c.rotate(f2.th+PI/2);
    var bk=f2.sz/120,flap=.22+.78*Math.abs(Math.cos(f2.ph));
    c.globalAlpha=.95;
    c.save();c.scale(bk*flap,bk);c.drawImage(SPR.bf[f2.spr],-75,-64,150,120);c.restore();
    c.scale(bk,bk);c.fillStyle='#ffe7b8';c.beginPath();c.ellipse(0,2,2.4,15,0,0,TAU);c.fill();
    c.strokeStyle='rgba(255,231,184,.9)';c.lineWidth=1;c.beginPath();c.moveTo(0,-12);c.lineTo(-7,-26);c.moveTo(0,-12);c.lineTo(7,-26);c.stroke();
    c.restore();
  }

  /* ---- sparks ---- */
  c.globalCompositeOperation='lighter';
  for(i=sparks.length-1;i>=0;i--){
    var sp=sparks[i];sp.life+=dt;
    if(sp.life>=sp.max){sparks.splice(i,1);continue}
    var dk=Math.pow(sp.dr,dt);
    sp.vx*=dk;sp.vy*=dk;sp.vy+=sp.g*dt;sp.x+=sp.vx*dt;sp.y+=sp.vy*dt;
    var pr=sp.life/sp.max;
    c.globalAlpha=Math.min(1,sp.life*6)*(1-pr)*(.7+.3*Math.sin(t*14+sp.ph))*sp.a;
    var sz=sp.kind==='heart'?sp.sz*1.78:sp.sz*(1+.4*(1-pr));
    c.drawImage(sp.spr,sp.x-sz/2,sp.y-sz/2,sz,sz);
  }
  c.globalAlpha=1;c.globalCompositeOperation='source-over';
}

/* ================= main loop ================= */
var last=performance.now(),T0=last,ema=.016,lastQ=0;
function frame(now){
  requestAnimationFrame(frame);
  var dt=(now-last)/1000;last=now;
  if(dt<=0)return;
  if(dt>.1)dt=.1;
  var t=(now-T0)/1000;
  ema=ema*.95+dt*.05;
  if(ema>.027&&Q>.45&&now-lastQ>2500){Q=Math.max(.45,Q-.15);lastQ=now}
  runTweens(now);
  par.x+=(par.tx-par.x)*Math.min(1,dt*3);par.y+=(par.ty-par.y)*Math.min(1,dt*3);
  var k=1-Math.exp(-dt*1.0);
  for(var key in F)F[key]+=(T[key]-F[key])*k;
  drawSky(t,dt);
  drawFx(t,dt);
}

/* ================= UI flow ================= */
var SCN=[null,
  {fx:{galaxy:.55,petals:2.2,hearts:.5,bfly:0,spark:6,shoot:0}},
  {fx:{galaxy:.7,petals:3.5,hearts:.8,bfly:3,spark:9,shoot:.08}},
  {fx:{galaxy:.8,petals:4.5,hearts:1.1,bfly:4,spark:11,shoot:.1}},
  {fx:{galaxy:.9,petals:5,hearts:1.4,bfly:5,spark:16,shoot:.1}},
  {fx:{galaxy:1,petals:5.5,hearts:1.8,bfly:6,spark:14,shoot:.12}},
  {fx:{galaxy:1,petals:2.5,hearts:.6,bfly:4,spark:8,shoot:.1}},
  {fx:{galaxy:1,petals:6,hearts:3,bfly:6,spark:14,shoot:.1}}
];
function setFx(p){for(var k in p)T[k]=p[k]}

function buildName(){
  el.introName.innerHTML='';
  var name='Нуржамал',i=0,ch=Array.from(name);
  ch.forEach(function(c,idx){
    var s=document.createElement('span');s.className='ch';s.style.setProperty('--i',idx);s.textContent=c;el.introName.appendChild(s);i=idx+1;
  });
  var sp=document.createElement('span');sp.className='ch';sp.style.setProperty('--i',i);
  var em=document.createElement('span');em.className='emoin';em.textContent='\u2764\uFE0F';sp.appendChild(em);
  el.introName.appendChild(sp);
}
function buildDots(){
  el.dots.innerHTML='';
  for(var i=0;i<7;i++)el.dots.appendChild(document.createElement('i'));
}
function updateDots(){
  var d=el.dots.children;
  for(var i=0;i<d.length;i++){var n=i+1;d[i].className=scene===n?'on':(scene>n?'done':'')}
}
function setBtn(show,label){
  if(label)el.goText.textContent=label;
  el.go.disabled=!show;
  if(show)el.go.classList.add('show');else el.go.classList.remove('show');
}
function syncMusic(){
  var on=Music.isOn();
  if(on)el.music.classList.add('on');else el.music.classList.remove('on');
  el.music.setAttribute('aria-pressed',on?'true':'false');
}
function flash(){el.flash.classList.remove('pop');void el.flash.offsetWidth;el.flash.classList.add('pop')}
function buttonSparkle(){
  var r=el.go.getBoundingClientRect();
  burst(r.left+r.width/2,r.top+r.height/2,22,{speed:200,g:-30,heart:.25,up:60});
}
function words(target,text,startIdx,cls){
  var arr=text.split(' ');
  arr.forEach(function(w,i){
    var s=document.createElement('span');
    s.className=cls+(/Нуржамал/.test(w)?' gold':'');
    s.style.setProperty('--i',startIdx+i);
    s.textContent=w;target.appendChild(s);
    if(i<arr.length-1)target.appendChild(document.createTextNode(' '));
  });
  return arr.length;
}
async function showMsg(text){
  el.msg.className='';el.msg.innerHTML='';
  var n=words(el.msg,text,0,'w');
  el.orn1.classList.add('show');el.orn2.classList.add('show');
  await sleep(n*160+1300);
}
async function hideMsg(){
  el.msg.classList.add('out');
  el.orn1.classList.remove('show');el.orn2.classList.remove('show');
  await sleep(1000);
  el.msg.innerHTML='';el.msg.className='';
}

async function playIntro(){
  scene=0;updateDots();
  stage.classList.remove('night','final');
  el.msgWrap.classList.remove('low');
  setFx({galaxy:0,petals:0,hearts:0,bfly:0,spark:3,shoot:0});
  BH.alpha=0;BH.sc=.5;
  el.intro.style.transition='none';
  el.intro.classList.remove('gone');
  layout();
  void el.intro.offsetWidth;
  el.intro.style.transition='';
  tween(SKY,'a',1,2400);
  el.intro.classList.remove('play');void el.intro.offsetWidth;el.intro.classList.add('play');
  await sleep(700);
  tween(BH,'alpha',1,1800,easeOut);tween(BH,'sc',1,2200,easeBack);
  await sleep(4200);
  setBtn(true,'Баштоо ❤️');
}
async function leaveIntro(){
  el.intro.classList.add('gone');
  burst(BH.x,BH.y,70,{speed:340,heart:.35,g:40});
  tween(BH,'sc',1.7,1300,easeOut);tween(BH,'alpha',0,1100);
  stage.classList.add('night');
  await sleep(1500);
}
async function leaveScene(n){
  if(n===6)tween(INF,'alpha',0,1300);
  await hideMsg();
}
async function finalScene(){
  stage.classList.add('final');
  el.msgWrap.classList.remove('low');
  BH.x=BH.fin.x;BH.y=BH.fin.y;BH.w=BH.fin.w;BH.sc=.2;BH.alpha=0;finalBeats=0;
  buildHP();
  tween(BH,'alpha',1,1400,easeOut);tween(BH,'sc',1,2200,easeBack);
  burst(BH.x,BH.y,80,{speed:460,heart:.5,g:30});
  var np=small?36:64;
  for(var i=0;i<np;i++)addPetal(rand(0,W),rand(-H*.6,-10),rand(60,140));
  vib([40,80,40,80,60]);
  await sleep(900);
  el.f1.innerHTML='';el.f2.innerHTML='';
  var n1=words(el.f1,FIN1,0,'fw');
  words(el.f2,FIN2,n1,'fw');
  el.finalWrap.classList.add('show');
  await sleep(4000);
  setBtn(true,'Кайра көрүү ↻');
}
async function enterScene(n){
  updateDots();
  setFx(SCN[n].fx);
  if(n>=1&&n<=5){
    el.msgWrap.classList.remove('low');
    await showMsg(MSG[n-1]);
    setBtn(true,'Улантуу ❤️');
  }else if(n===6){
    el.msgWrap.classList.add('low');
    INF.form=0;
    tween(INF,'alpha',1,1200);tween(INF,'form',1,3600,ease);
    await sleep(1800);
    await showMsg(MSG[5]);
    setBtn(true,'Улантуу ❤️');
  }else if(n===7){
    await finalScene();
  }
}
async function replay(){
  el.finalWrap.classList.remove('show');
  el.finalBox.style.transform='';
  tween(BH,'alpha',0,1400);tween(BH,'sc',.4,1400,ease);
  stage.classList.remove('night','final');
  setFx({galaxy:0,petals:0,hearts:0,bfly:0,spark:2,shoot:0});
  await sleep(1800);
  HP.length=0;
  await playIntro();
}
async function advance(){
  if(busy)return;
  busy=true;
  try{
    setBtn(false);vib(18);buttonSparkle();flash();
    if(!Music.isTouched()&&Music.available()){Music.enable().then(syncMusic)}
    if(scene===7){await replay()}
    else{
      if(scene===0)await leaveIntro();else await leaveScene(scene);
      scene++;
      await enterScene(scene);
    }
  }catch(e){
    if(window.console)console.error(e);
    setBtn(true);
  }finally{
    busy=false;
  }
}

/* ================= events ================= */
el.go.addEventListener('click',advance);
el.music.addEventListener('click',function(){
  vib(10);
  if(Music.isOn()){Music.disable();syncMusic()}
  else{Music.enable().then(syncMusic);syncMusic()}
});
if(!Music.available())el.music.style.display='none';
document.addEventListener('keydown',function(e){
  if((e.key==='Enter'||e.key===' '||e.key==='ArrowRight')&&!el.go.disabled){e.preventDefault();advance()}
});
window.addEventListener('pointermove',function(e){par.tx=(.5-e.clientX/W)*16;par.ty=(.5-e.clientY/H)*10},{passive:true});
window.addEventListener('resize',onResize);
window.addEventListener('orientationchange',onResize);
document.addEventListener('visibilitychange',function(){if(document.hidden)Music.pause();else Music.resume()});

/* ================= boot ================= */
buildSprites();
buildName();
buildDots();
resize();
syncMusic();
requestAnimationFrame(frame);
busy=true;
playIntro().then(function(){busy=false});
})();
</script>
</body>
</html>
