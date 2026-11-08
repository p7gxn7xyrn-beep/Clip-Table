# Clip-Table
这是我的第一个项目，暂时不支持联网更新。该工具是集剪贴板、记事本、计算器为一体的提效工具，旨在提高打工人的工作效率，为自己省下摸鱼的时间和精力。目前剪贴板工具的功能还不够完善，如果在体验过程中遇到bug和你的ideas，欢迎加我的微信或邮箱shuyangli04@126.com交流（仅支持Clip Table的用户反馈和捐赠）。在一切开始前，你可以先下载Clip Tbale的说明书，觉得合适再体验~如果可以的话，可以给我点个star吗 ：）


This is my first project, and it currently does not support online updates. This tool integrates clipboards, notepads, and calculators to enhance efficiency, aiming to improve workers' work efficiency and save time and effort from slacking off. Currently, the clipboard tool's features are not yet fully developed. If you encounter bugs or share your ideas during the experience, feel free to add me on WeChat or email shuyangli04@126.com chat (only user feedback and donations from Clip Table are supported). Before everything begins, you can download Clip Tbale's manual and try it if it suits you~ If possible, could you give me a star rating :)


[给用户的一封信.html](https://github.com/user-attachments/files/34543275/default.html)

<!DOCTYPE html>
<html lang="zh-CN" data-theme="light">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>给用户的一封信 · ClipTable</title>
<style>
:root{
  --paper:#F5F8F2; --card:#FFFFFF; --ink:#15251F; --soft:#53665E; --mute:#869890;
  --brand:#0D6A55; --bright:#17A583; --leaf:#C9E86B; --coral:#FF7A55; --sun:#FFC94A;
  --line:rgba(21,37,31,.10); --shadow:0 18px 48px rgba(21,45,36,.10);
  --serif:"Songti SC","Noto Serif CJK SC","Source Han Serif SC","SimSun",Georgia,serif;
  --sans:"PingFang SC","Microsoft YaHei","Noto Sans CJK SC","Helvetica Neue",Arial,sans-serif;
}
[data-theme="dark"]{
  --paper:#0D1613; --card:#14221D; --ink:#EAF3EC; --soft:#AFC2B8; --mute:#7E958A;
  --brand:#63D6B0; --bright:#7FE3C3; --leaf:#C9E86B; --coral:#FF9373; --sun:#FFD36B;
  --line:rgba(255,255,255,.12); --shadow:0 18px 48px rgba(0,0,0,.35);
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:var(--paper);color:var(--ink);font-family:var(--sans);font-size:16px;line-height:1.9;-webkit-font-smoothing:antialiased;transition:background .4s,color .4s}
::selection{background:var(--leaf);color:#15251F}
a{color:inherit}
.wrap{max-width:1160px;margin:0 auto;padding:0 28px}

/* progress + controls */
#bar{position:fixed;top:0;left:0;height:3px;width:0;background:linear-gradient(90deg,var(--brand),var(--bright),var(--leaf));z-index:99;transition:width .1s}
.controls{position:fixed;top:20px;right:22px;display:flex;gap:8px;z-index:60}
.btn{width:38px;height:38px;border-radius:50%;border:1px solid var(--line);background:var(--card);color:var(--ink);cursor:pointer;display:grid;place-items:center;box-shadow:0 4px 14px rgba(0,0,0,.08);transition:transform .25s,box-shadow .25s}
.btn:hover{transform:translateY(-3px) rotate(8deg);box-shadow:0 10px 22px rgba(0,0,0,.14)}
.btn svg{width:17px;height:17px;stroke:currentColor;fill:none;stroke-width:1.7;stroke-linecap:round;stroke-linejoin:round}
#toTop{opacity:0;pointer-events:none}
#toTop.on{opacity:1;pointer-events:auto}

/* hero */
.hero{position:relative;overflow:hidden;padding:88px 0 66px;background:
  radial-gradient(680px 420px at 88% 12%,rgba(201,232,107,.30),transparent 70%),
  radial-gradient(560px 400px at 6% 88%,rgba(23,165,131,.14),transparent 72%),
  radial-gradient(420px 320px at 62% 100%,rgba(255,201,74,.13),transparent 70%);
  border-bottom:1px solid var(--line)}
.hero:before{content:"";position:absolute;inset:0;background-image:linear-gradient(var(--line) 1px,transparent 1px),linear-gradient(90deg,var(--line) 1px,transparent 1px);background-size:52px 52px;opacity:.35;mask-image:linear-gradient(180deg,#000,transparent 85%);pointer-events:none}
.hero .wrap{position:relative;display:grid;grid-template-columns:1.02fr .98fr;gap:54px;align-items:center}
.eyebrow{display:inline-flex;align-items:center;gap:10px;font-size:12px;letter-spacing:.22em;text-transform:uppercase;color:var(--brand);font-weight:700}
.eyebrow i{width:26px;height:1px;background:var(--brand);display:inline-block}
h1{font-family:var(--serif);font-size:clamp(42px,6.1vw,74px);line-height:1.12;margin:22px 0 18px;letter-spacing:.02em;font-weight:700}
h1 em{font-style:normal;position:relative;white-space:nowrap;background:linear-gradient(180deg,transparent 58%,rgba(201,232,107,.62) 58%);border-radius:4px;padding:0 4px}
.lead{font-size:17px;color:var(--soft);max-width:490px;margin:0 0 26px;line-height:2}
.signature-line{display:flex;align-items:center;gap:12px;color:var(--mute);font-size:13px}
.signature-line span{width:40px;height:1px;background:var(--mute)}
.hero-art{position:relative;height:520px;display:flex;align-items:center;justify-content:center}
.leaf-branch{position:absolute;right:-40px;top:-20px;width:230px;opacity:.75;animation:sway 9s ease-in-out infinite}
@keyframes sway{0%,100%{transform:rotate(0)}50%{transform:rotate(5deg)}}
.app-shot{position:relative;width:250px;border-radius:18px;overflow:hidden;box-shadow:0 30px 70px rgba(9,28,21,.34);transform:rotate(-3deg);animation:float 7s ease-in-out infinite;z-index:2;border:1px solid rgba(255,255,255,.12)}
@keyframes float{0%,100%{transform:rotate(-3deg) translateY(0)}50%{transform:rotate(-2deg) translateY(-12px)}}
.app-shot img{display:block;width:100%}
.mini-shot{position:absolute;left:0;bottom:24px;width:236px;border-radius:14px;overflow:hidden;box-shadow:0 22px 46px rgba(9,28,21,.28);transform:rotate(5deg);animation:float2 8s ease-in-out infinite;z-index:3;border:1px solid rgba(255,255,255,.12)}
@keyframes float2{0%,100%{transform:rotate(5deg) translateY(0)}50%{transform:rotate(4deg) translateY(-9px)}}
.mini-shot img{display:block;width:100%}
.paper-chip{position:absolute;z-index:4;background:var(--card);border:1px solid var(--line);border-radius:10px;padding:9px 13px;font-size:12px;color:var(--soft);box-shadow:var(--shadow);display:flex;align-items:center;gap:8px;font-weight:600}
.paper-chip b{color:var(--brand)}
.chip-1{top:52px;left:2px;transform:rotate(-7deg);animation:float 6s ease-in-out infinite reverse}
.chip-2{right:0;bottom:92px;transform:rotate(6deg);animation:float2 7.5s ease-in-out infinite}
.paper-chip .dot{width:8px;height:8px;border-radius:50%;background:var(--bright);box-shadow:0 0 0 4px rgba(23,165,131,.16)}
.doodle{position:absolute;left:-30px;bottom:60px;width:150px;opacity:.55}

/* quick start */
.quick{position:relative;z-index:5;margin-top:-26px}
.quick-card{background:var(--card);border:1px solid var(--line);border-radius:20px;box-shadow:var(--shadow);padding:26px 30px;display:grid;grid-template-columns:auto 1fr;gap:28px;align-items:center}
.quick-title{font-family:var(--serif);font-size:19px;font-weight:700;white-space:nowrap;line-height:1.5}
.quick-title small{display:block;font-family:var(--sans);font-size:11px;letter-spacing:.16em;color:var(--brand);font-weight:700;margin-bottom:4px}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.step{display:flex;align-items:flex-start;gap:11px;font-size:14px;color:var(--soft);line-height:1.65}
.step .n{flex:none;width:26px;height:26px;border-radius:8px;background:rgba(201,232,107,.34);color:#3D5B18;font-weight:800;font-size:12px;display:grid;place-items:center}
[data-theme="dark"] .step .n{color:#1A2A12}
.step b{color:var(--ink);font-weight:700}

/* letter layout */
.letter{display:grid;grid-template-columns:190px minmax(0,1fr);gap:54px;padding:70px 0 40px;align-items:start}
.toc{position:sticky;top:34px;font-size:13px}
.toc p{font-size:11px;letter-spacing:.2em;color:var(--mute);text-transform:uppercase;margin:0 0 16px;font-weight:700}
.toc a{display:flex;gap:10px;padding:7px 0;color:var(--soft);text-decoration:none;border-left:2px solid transparent;padding-left:12px;transition:.25s}
.toc a span{color:var(--mute);font-variant-numeric:tabular-nums;font-size:11px;min-width:20px}
.toc a:hover,.toc a.active{color:var(--brand);border-left-color:var(--brand);transform:translateX(3px);font-weight:700}
.toc .end{margin-top:22px;padding:14px;border-radius:12px;background:rgba(13,106,85,.06);font-size:12px;line-height:1.75;color:var(--soft)}

article{max-width:760px}
.opener{font-family:var(--serif);font-size:20px;line-height:2.15;margin:0 0 14px}
.opener .salut{display:block;font-size:23px;font-weight:700;color:var(--ink);margin-bottom:20px}
article p{margin:0 0 18px;color:var(--soft)}
article p strong,article li strong{color:var(--ink);font-weight:700}
mark{background:linear-gradient(180deg,transparent 52%,rgba(201,232,107,.62) 52%);color:var(--ink);padding:0 2px;font-weight:600}
kbd{font-family:var(--sans);font-size:12px;background:var(--card);border:1px solid var(--line);border-bottom-width:2px;border-radius:6px;padding:2px 7px;color:var(--brand);font-weight:700;white-space:nowrap;box-shadow:0 1px 0 rgba(0,0,0,.04)}
.divider{display:flex;align-items:center;gap:14px;margin:52px 0 44px;color:var(--mute);font-size:11px;letter-spacing:.2em}
.divider:before,.divider:after{content:"";height:1px;background:var(--line);flex:1}

section{scroll-margin-top:34px;margin-bottom:64px}
html.js-anim section{opacity:0;transform:translateY(22px);transition:opacity .7s,transform .7s}
html.js-anim section.in{opacity:1;transform:none}
.sec-head{display:flex;align-items:flex-start;gap:16px;margin-bottom:18px}
.sec-num{flex:none;width:46px;height:46px;border-radius:14px;background:var(--brand);color:#fff;display:grid;place-items:center;font-family:var(--serif);font-size:18px;font-weight:700;box-shadow:0 8px 18px rgba(13,106,85,.22)}
[data-theme="dark"] .sec-num{color:#0D1613}
.sec-head h2{font-family:var(--serif);font-size:27px;margin:2px 0 0;line-height:1.4;font-weight:700}
.sec-head .sub{display:block;font-family:var(--sans);font-size:12px;letter-spacing:.12em;color:var(--brand);font-weight:700;margin-bottom:3px}
.icon{width:30px;height:30px;stroke:var(--brand);fill:none;stroke-width:1.6;stroke-linecap:round;stroke-linejoin:round;margin-left:auto;opacity:.75;flex:none}
.tip{margin:22px 0 0;padding:14px 18px;border-left:3px solid var(--leaf);background:rgba(201,232,107,.13);border-radius:0 12px 12px 0;font-size:14px;color:var(--ink);line-height:1.8}
.tip b{color:var(--brand)}
ul.clean{list-style:none;padding:0;margin:16px 0 0;display:grid;gap:12px}
ul.clean li{position:relative;padding-left:24px;color:var(--soft);font-size:15px;line-height:1.85}
ul.clean li:before{content:"";position:absolute;left:2px;top:11px;width:8px;height:8px;border-radius:3px;background:var(--bright);transform:rotate(45deg)}
.mode-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin:22px 0}
.mode{border:1px solid var(--line);background:var(--card);border-radius:14px;padding:16px;transition:transform .3s,box-shadow .3s}
.mode:hover{transform:translateY(-5px);box-shadow:var(--shadow)}
.mode .m-ico{width:30px;height:30px;stroke:var(--brand);fill:none;stroke-width:1.6;stroke-linecap:round;stroke-linejoin:round;margin-bottom:10px}
.mode h4{margin:0 0 6px;font-size:15px}
.mode p{margin:0;font-size:13px;line-height:1.7;color:var(--soft)}
.fig{margin:28px 0 8px}
.fig-frame{background:#101A17;border:1px solid rgba(255,255,255,.10);border-radius:16px;padding:14px;box-shadow:var(--shadow);display:flex;gap:14px;justify-content:center;align-items:flex-start;flex-wrap:wrap;overflow:hidden}
.fig-frame img{display:block;max-height:400px;width:auto;max-width:100%;border-radius:10px;transition:transform .45s cubic-bezier(.2,.8,.2,1)}
.fig-frame.two img{max-width:calc(50% - 10px)}
.fig-frame.three img{max-width:calc(33.33% - 12px);max-height:320px}
.fig-frame:hover img{transform:scale(1.025)}
.fig.single .fig-frame img{max-height:420px}
figcaption{font-size:12px;color:var(--mute);margin-top:10px;text-align:center;letter-spacing:.02em}
.privacy{border:1px solid var(--line);background:var(--card);border-radius:18px;padding:26px 28px;box-shadow:var(--shadow);margin:24px 0}
.privacy h3{font-family:var(--serif);font-size:18px;margin:0 0 14px;display:flex;align-items:center;gap:9px}
.privacy h3 svg{width:20px;height:20px;stroke:var(--brand);fill:none;stroke-width:1.7;stroke-linecap:round;stroke-linejoin:round}
.privacy-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.privacy-grid div{border-top:1px solid var(--line);padding-top:12px;font-size:14px;color:var(--soft);line-height:1.75}
.privacy-grid b{display:block;color:var(--ink);font-size:14px;margin-bottom:3px}
.note{font-size:13px;color:var(--mute);border-top:1px dashed var(--line);margin-top:18px;padding-top:14px;line-height:1.8}
.closing{background:linear-gradient(135deg,rgba(13,106,85,.09),rgba(201,232,107,.16));border:1px solid var(--line);border-radius:20px;padding:34px 36px;margin-top:20px;position:relative;overflow:hidden}
.closing:before{content:"";position:absolute;right:-40px;top:-40px;width:180px;height:180px;border-radius:50%;background:rgba(255,201,74,.20)}
.closing p{font-family:var(--serif);font-size:19px;line-height:2;color:var(--ink);margin:0 0 16px;position:relative}
.closing .sign{font-family:var(--serif);text-align:right;font-size:16px;color:var(--brand);font-weight:700;position:relative}
.contact{display:grid;grid-template-columns:1fr auto;gap:26px;align-items:center;margin-top:26px;padding:26px;border:1px solid var(--line);border-radius:18px;background:var(--card)}
.contact h3{font-family:var(--serif);font-size:20px;margin:0 0 8px}
.contact p{font-size:14px;margin:0;color:var(--soft)}
.qr{width:132px;border-radius:12px;overflow:hidden;border:1px solid var(--line);background:#fff;padding:6px}
.qr img{display:block;width:100%}
footer{border-top:1px solid var(--line);padding:30px 0 46px;color:var(--mute);font-size:12px;display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap}
footer b{color:var(--brand)}

@media(max-width:980px){
 .hero .wrap{grid-template-columns:1fr;gap:20px}
 .hero-art{height:430px}
 .letter{grid-template-columns:1fr;gap:0}
 .toc{display:none}
 .quick-card{grid-template-columns:1fr;gap:16px}
}
@media(max-width:640px){
 .wrap{padding:0 18px}
 .hero{padding:66px 0 60px}
 .hero-art{height:390px}
 .app-shot{width:200px}
 .mini-shot{width:190px;left:-6px;bottom:10px}
 .leaf-branch{width:150px;right:-20px}
 .steps,.mode-grid,.privacy-grid{grid-template-columns:1fr}
 .fig-frame.two img,.fig-frame.three img{max-width:100%;max-height:300px}
 .fig-frame.three img:nth-child(n+2){display:none}
 .closing,.contact{padding:24px}
 .contact{grid-template-columns:1fr}
 .qr{width:150px}
 h1{font-size:44px}
}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}section,html.js-anim section{opacity:1;transform:none}}
@media print{
 .controls,#toTop,#bar,.toc{display:none!important}
 body{background:#fff;color:#000}
 .hero{padding:30px 0;background:none}
 section,html.js-anim section{opacity:1;transform:none;break-inside:avoid;margin-bottom:32px}
 .fig-frame{box-shadow:none;border:1px solid #ccc}
 .quick{box-shadow:none}
}

.ctm *{
  box-sizing: border-box;
}
.ctm{
  

  
  --bg: #0b0c0e;

  
  --glass: rgba(var(--glass-tint-rgb), 0.64);
  
  --glass-tint-rgb: 16, 17, 19;
  --glass-dark-rgb: 9, 10, 11;
  --glass-hi-rgb: 232, 236, 240;
  --glass-edge-rgb: 200, 208, 216;
  --glass-strong: rgba(var(--glass-hi-rgb), 0.08);
  --glass-faint: rgba(var(--glass-hi-rgb), 0.05);
  
  --glass-dark: rgba(var(--glass-dark-rgb), 0.36);
  --glass-border: rgba(var(--glass-edge-rgb), 0.2);
  --glass-border-soft: rgba(var(--glass-edge-rgb), 0.1);
  
  --glass-hi: rgba(var(--glass-hi-rgb), 0.28);
  
  --glass-tint-alpha: 1;
  
  --frost-strength: 1;

  
  --text: #eef0f2;
  --text-dim: #aab0b6;
  --text-faint: #7c848b;

  
  --accent: #9aa5ab;
  --accent-strong: #7e878c;
  --accent-soft: rgba(154, 165, 171, 0.28);
  --accent-sel: rgba(154, 165, 171, 0.5);

  
  --danger: #ff6b6b;
  --danger-soft: rgba(255, 107, 107, 0.14);
  --success: #5ad79c;
  --success-soft: rgba(90, 215, 156, 0.22);
  --warning: #ffbf57;

  

  
  --radius: 14px;
  --radius-sm: 10px;
  --radius-xs: 7px;
  --shadow-pop: 0 14px 40px rgba(0, 0, 0, 0.4);
  --shadow-btn: 0 2px 8px rgba(0, 0, 0, 0.25);

  
  --lq-k: 0.55;
  
  --lq-radius-btn: 12px;
  --lq-radius-icon: 10px;
  --lq-radius-seg: 11px;
  --lq-radius-seg-item: 8px;
  --lq-radius-tiny: 6px;

  
  --fs-xs: 11px;
  --fs-sm: 12px;
  --fs-base: 13px;
}
.ctm .btn, .ctm .icon-btn, .ctm .seg-btn.active, .ctm .pad-btn{
  --lq-hb: 1;                                  
  --lq-o: calc(var(--lq-k, 0.55) * var(--lq-hb));
  --lq-ink: 255, 255, 255;                    
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.042) 0%,
    rgba(var(--lq-ink), 0.062) 20%,
    rgba(var(--lq-ink), 0.085) 62%,
    rgba(var(--lq-ink), 0.06) 88%,
    rgba(var(--lq-ink), 0.1) 100%
  );
  --lq-top: 0.95;                              
  --lq-top2: 0.16;                             
  --lq-side: 0.1;                              
  --lq-bottom: 0.34;                           
  --lq-glow: 0.075;                            
  --lq-curve: inset 0 -12px 16px -14px rgba(0, 0, 0, 1);
  --lq-drop: 0 1px 2px rgba(0, 0, 0, 0.6);    
  --lq-radius: var(--lq-radius-btn);
  position: relative;
  isolation: isolate;
  
  border: 1px solid transparent;
  border-radius: var(--lq-radius);
  background-color: transparent; 
  background-image: var(--lq-face);
  transition: transform 0.14s cubic-bezier(0.22, 0.61, 0.36, 1),
    color 0.15s ease;
}
.ctm .btn::before, .ctm .btn::after, .ctm .icon-btn::before, .ctm .icon-btn::after, .ctm .seg-btn.active::before, .ctm .seg-btn.active::after, .ctm .pad-btn::before, .ctm .pad-btn::after{
  content: '';
  position: absolute;
  
  inset: -1px;
  border-radius: inherit;
  pointer-events: none;
  z-index: -1; 
  background: radial-gradient(
    90% 100% at 50% 0%,
    rgba(var(--lq-ink), var(--lq-glow)) 0%,
    rgba(var(--lq-ink), 0.02) 50%,
    rgba(var(--lq-ink), 0) 90%
  );
  box-shadow:
    inset 0 1px 0 rgba(var(--lq-ink), var(--lq-top)),
    inset 0 2px 0 rgba(var(--lq-ink), var(--lq-top2)),
    inset 1px 0 0 rgba(var(--lq-ink), var(--lq-side)),
    inset -1px 0 0 rgba(var(--lq-ink), var(--lq-side)),
    inset 0 -1px 0 rgba(var(--lq-ink), var(--lq-bottom)),
    var(--lq-curve),
    var(--lq-drop);
}
.ctm .btn::before, .ctm .icon-btn::before, .ctm .seg-btn.active::before, .ctm .pad-btn::before{
  opacity: var(--lq-o);
}
.ctm .btn::after, .ctm .icon-btn::after, .ctm .seg-btn.active::after, .ctm .pad-btn::after{
  opacity: calc(var(--lq-o) - 1);
}
.ctm .btn:hover, .ctm .icon-btn:hover, .ctm .seg-btn.active:hover, .ctm .pad-btn:hover{
  --lq-hb: 1.18;
}
.ctm .btn:hover{
  transform: translateY(-1px);
}
.ctm .btn:active, .ctm .icon-btn:active, .ctm .seg-btn.active:active, .ctm .pad-btn:active{
  --lq-hb: 0.62;
}
.ctm .btn:active{
  transform: translateY(0.5px);
}
.ctm .btn:focus-visible, .ctm .icon-btn:focus-visible, .ctm .seg-btn:focus-visible, .ctm .pad-btn:focus-visible{
  outline: 2px solid rgba(var(--glass-hi-rgb), 0.9);
  outline-offset: 2px;
}
.ctm select, .ctm input, .ctm textarea, .ctm button{
  color-scheme: dark;
}
.ctm .app{
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 14px;
  gap: 10px;
  
  
  isolation: isolate;
  
  background-color: rgba(var(--glass-tint-rgb), var(--glass-tint-alpha, 0.96));
  
  border: 1px solid rgba(var(--glass-edge-rgb), 0.24);
  border-radius: var(--radius);
  
  box-shadow:
    inset 0 1px 0 var(--glass-hi),
    inset 1px 0 0 rgba(var(--glass-edge-rgb), 0.1),
    inset -1px 0 0 rgba(var(--glass-edge-rgb), 0.05),
    inset 0 -1px 0 rgba(0, 0, 0, 0.32),
    inset 0 0 0 1px rgba(var(--glass-edge-rgb), 0.05);
  transition: background-color 0.12s ease;
}
.ctm .topbar{
  cursor: grab;
}
.ctm .app.is-dragging .topbar{
  cursor: grabbing;
}
.ctm .app button, .ctm .app a, .ctm .app input, .ctm .app select, .ctm .app textarea, .ctm .app .cell, .ctm .app [role='button'], .ctm .app [contenteditable='true']{
  cursor: pointer;
}
.ctm .app input[type='text'], .ctm .app input[type='number'], .ctm .app textarea{
  cursor: auto;
}
.ctm .icon-pin.active{
  color: var(--accent);
}
.ctm .icon-pin svg{
  width: 16px;
  height: 16px;
  transform: rotate(-42deg); 
  transition: transform 0.18s ease, color 0.15s ease;
}
.ctm .icon-pin.active svg{
  transform: rotate(0deg); 
}
.ctm .app::before{
  content: '';
  position: absolute;
  inset: 0;
  border-radius: var(--radius);
  pointer-events: none;
  z-index: -1;
  background:
    linear-gradient(
      180deg,
      rgba(var(--glass-hi-rgb), 0.09) 0%,
      rgba(var(--glass-hi-rgb), 0.03) 5%,
      rgba(var(--glass-hi-rgb), 0) 17%
    ),
    radial-gradient(
      115% 85% at 16% -10%,
      rgba(var(--glass-hi-rgb), 0.1) 0%,
      rgba(var(--glass-hi-rgb), 0) 56%
    ),
    radial-gradient(
      118% 118% at 50% 50%,
      rgba(var(--glass-hi-rgb), 0) 56%,
      rgba(var(--glass-hi-rgb), calc(0.05 * var(--frost-strength, 0))) 100%
    );
}
.ctm .loading{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  color: var(--text-dim);
  font-size: var(--fs-sm);
}
.ctm .topbar{
  display: flex;
  align-items: center;
  gap: 6px;
}
.ctm .brand{
  display: flex;
  align-items: center;
  gap: 8px;
  flex: 1;
  min-width: 0;
}
.ctm .brand-mark{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 26px;
  height: 26px;
  border-radius: var(--radius-sm);
  background: var(--accent-soft);
  color: var(--accent);
  flex: none;
}
.ctm .brand-name{
  font-weight: 600;
  font-size: var(--fs-base);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .status{
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: var(--fs-xs);
  font-weight: 500;
  padding: 3px 9px 3px 8px;
  border-radius: 999px;
  background: var(--success-soft);
  color: var(--success);
  border: 1px solid rgba(90, 215, 156, 0.3);
  flex: none;
}
.ctm .status.paused{
  background: rgba(255, 255, 255, 0.08);
  color: var(--text-dim);
  border-color: var(--glass-border-soft);
}
.ctm .status.denied{
  background: rgba(255, 191, 87, 0.16);
  color: var(--warning);
  border-color: rgba(255, 191, 87, 0.35);
}
.ctm .status .dot{
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: currentColor;
}
.ctm .status:not(.paused):not(.denied) .dot{
  box-shadow: 0 0 0 0 var(--success);
  animation: pulse 1.8s ease-out infinite;
}
@keyframes pulse{
  0% {
    box-shadow: 0 0 0 0 rgba(90, 215, 156, 0.55);
  }
  70% {
    box-shadow: 0 0 0 6px rgba(90, 215, 156, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(90, 215, 156, 0);
  }
}
.ctm .icon-btn{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 28px;
  padding: 0 8px;
  color: var(--text);
  font-size: var(--fs-sm);
  cursor: pointer;
  flex: none;
  
  --lq-radius: var(--lq-radius-icon);
  --lq-glow: 0;
  --lq-top: 0.85;
  --lq-top2: 0.12;
  --lq-side: 0.1;
  --lq-bottom: 0.3;
  --lq-curve: inset 0 -8px 11px -9px rgba(0, 0, 0, 0.95);
  --lq-drop: 0 1px 1.8px rgba(0, 0, 0, 0.5);
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.035) 0%,
    rgba(var(--lq-ink), 0.05) 22%,
    rgba(var(--lq-ink), 0.068) 64%,
    rgba(var(--lq-ink), 0.05) 88%,
    rgba(var(--lq-ink), 0.085) 100%
  );
}
.ctm .icon-btn:active{
  transform: translateY(0.5px);
}
.ctm .icon-btn.icon-close, .ctm .icon-btn.icon-gear{
  width: 28px;
  padding: 0;
}
.ctm .icon-btn.icon-close svg, .ctm .icon-btn.icon-gear svg{
  width: 15px;
  height: 15px;
}
.ctm .icon-btn.icon-close{
  --lq-radius: 50%;
  --lq-ink: 255, 236, 236;
  --lq-glow: 0.13;
  --lq-top: 0.7;
  --lq-top2: 0.1;
  --lq-bottom: 0.28;
  --lq-curve: inset 0 -3px 5px -4px rgba(0, 0, 0, 0.8);
  --lq-drop: 0 1px 2px rgba(0, 0, 0, 0.55);
  --lq-face:
    radial-gradient(
      96% 82% at 50% -10%,
      rgba(var(--lq-ink), 0.13) 0%,
      rgba(var(--lq-ink), 0) 68%
    ),
    linear-gradient(
      180deg,
      rgba(198, 60, 60, 0.3) 0%,
      rgba(126, 28, 28, 0.22) 52%,
      rgba(176, 48, 48, 0.26) 88%,
      rgba(214, 78, 78, 0.34) 100%
    );
  color: rgba(255, 255, 255, 0.96);
}
.ctm .icon-btn.icon-close svg{
  width: 13px;
  height: 13px;
  transition: opacity 0.15s ease;
}
.ctm .icon-btn.icon-close:hover{
  color: #fff;
}
.ctm .guide{
  position: relative;
  background: rgba(255, 255, 255, 0.045);
  border: 1px solid var(--glass-border);
  border-left: 2px solid rgba(var(--glass-hi-rgb), 0.42);
  border-radius: var(--radius-sm);
  padding: 10px 12px;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
}
.ctm .guide-title{
  font-weight: 600;
  margin-bottom: 4px;
  color: var(--text);
}
.ctm .guide p{
  margin: 0 0 8px;
  color: var(--text-dim);
  line-height: 1.55;
  font-size: var(--fs-sm);
  padding-right: 16px;
}
.ctm .guide-close{
  position: absolute;
  top: 6px;
  right: 8px;
  width: 20px;
  height: 20px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border: none;
  background: transparent;
  color: var(--text-dim);
  font-size: 16px;
  line-height: 1;
  cursor: pointer;
  border-radius: 5px;
}
.ctm .guide-close:hover{
  background: rgba(255, 255, 255, 0.1);
  color: var(--text);
}
.ctm .modebar{
  display: flex;
  align-items: center;
  gap: 10px;
}
.ctm .modebar .calc-toggle{
  margin-left: auto;
  display: flex;
  align-items: center;
  gap: 6px;
  flex: none;
  
  padding-left: 2px;
}
.ctm .modebar .calc-switch{
  flex: none;
}
.ctm .label{
  color: var(--text-dim);
  font-size: var(--fs-sm);
  flex: none;
}
.ctm .seg{
  display: flex;
  flex: 1;
  padding: 3px;
  gap: 3px;
  border-radius: var(--lq-radius-seg);
  
  background: rgba(var(--glass-dark-rgb), 0.55);
  border: 1px solid transparent;
  box-shadow:
    inset 0 1px 2px rgba(0, 0, 0, 0.55),
    inset 0 -1px 0 rgba(255, 255, 255, 0.04);
}
.ctm .seg-btn{
  flex: 1;
  background: transparent;
  color: var(--text-dim);
  border: none;
  padding: 5px 8px;
  border-radius: var(--lq-radius-seg-item);
  cursor: pointer;
  font-size: var(--fs-sm);
  transition: color 0.15s ease;
}
.ctm .seg-btn:hover{
  color: var(--text);
}
.ctm .seg-btn.active{
  
  --lq-radius: var(--lq-radius-seg-item);
  --lq-top: 0.8;
  --lq-top2: 0.12;
  --lq-side: 0.09;
  --lq-bottom: 0.28;
  --lq-glow: 0.05;
  --lq-curve: inset 0 -8px 11px -9px rgba(0, 0, 0, 0.95);
  --lq-drop: 0 1px 2px rgba(0, 0, 0, 0.55);
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.04) 0%,
    rgba(var(--lq-ink), 0.06) 22%,
    rgba(var(--lq-ink), 0.08) 64%,
    rgba(var(--lq-ink), 0.058) 88%,
    rgba(var(--lq-ink), 0.095) 100%
  );
  color: var(--text);
  font-weight: 600;
}
.ctm .set-row{
  display: flex;
  align-items: center;
  gap: 6px;
  color: var(--text-dim);
  font-size: var(--fs-sm);
  cursor: pointer;
}
.ctm .set-row input[type='number']{
  width: 52px;
  background: var(--glass-strong);
  border: 1px solid var(--glass-border);
  color: var(--text);
  border-radius: var(--radius-xs);
  padding: 3px 6px;
  font-size: var(--fs-sm);
}
.ctm .set-row input[type='number']:focus{
  outline: none;
  border-color: var(--accent);
}
.ctm .set-row input[type='checkbox']{
  accent-color: var(--accent);
  width: 14px;
  height: 14px;
  cursor: pointer;
}
.ctm .tablewrap{
  flex: 1;
  overflow: auto;
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-sm);
  background: var(--glass-dark);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.06);
}
.ctm .empty{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  height: 100%;
  color: var(--text-dim);
  padding: 24px;
  text-align: center;
}
.ctm .empty .empty-icon{
  font-size: 30px;
  opacity: 0.6;
}
.ctm .empty .empty-text{
  font-size: var(--fs-sm);
}
.ctm .grid{
  width: 100%;
  border-collapse: collapse;
  font-size: var(--fs-sm);
}
.ctm .grid th, .ctm .grid td{
  border: 1px solid var(--glass-border-soft);
  padding: 6px 8px;
  text-align: left;
  vertical-align: top;
  max-width: 180px;
  line-height: 1.45;
}
.ctm .grid th{
  position: sticky;
  top: 0;
  
  background: rgba(13, 14, 16, 0.92); 
  color: var(--text-dim);
  font-weight: 600;
  font-size: var(--fs-xs);
  z-index: 1;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.06);
}
.ctm .grid td{
  color: var(--text);
  white-space: pre-wrap;
  overflow-wrap: anywhere;
  word-break: break-word;
}
.ctm .grid .ck, .ctm .grid .idx{
  width: 30px;
  text-align: center;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  padding: 6px 4px;
}
.ctm .cell{
  cursor: crosshair;
  min-height: 24px;
  transition: background 0.12s ease;
}
.ctm .cell:hover{
  background: rgba(255, 255, 255, 0.05);
}
.ctm .cell.cursor{
  position: relative;
  background: var(--accent-soft);
  box-shadow: inset 3px 0 0 var(--accent);
}
.ctm .cell.copyable{
  cursor: crosshair;
}
.ctm .cell.copied{
  background: var(--accent-soft);
  box-shadow: inset 0 0 0 1px var(--accent-sel);
}
.ctm .cell.sel{
  background: var(--accent-sel);
  box-shadow: inset 0 0 0 1.5px var(--accent);
}
.ctm .tablewrap.dragging{
  user-select: none;
  -webkit-user-select: none;
}
.ctm .tablewrap.dragging .cell{
  cursor: crosshair;
}
.ctm .tablewrap, .ctm .tablewrap .grid *{
  cursor: crosshair;
}
.ctm .tablewrap.dragging .cell:hover{
  background: inherit;
}
.ctm .cur-tag{
  position: absolute;
  top: 2px;
  right: 2px;
  font-size: 9px;
  line-height: 1;
  background: var(--accent);
  color: #fff;
  border-radius: 4px;
  padding: 2px 4px;
  letter-spacing: 0.3px;
}
.ctm .ph{
  color: var(--text-faint);
}
.ctm .cell-input{
  width: 100%;
  background: var(--glass-strong);
  border: 1px solid var(--accent);
  color: var(--text);
  border-radius: var(--radius-xs);
  padding: 3px 5px;
  font-size: var(--fs-sm);
  outline: none;
  font-family: inherit;
}
.ctm .row.next{
  background: rgba(var(--glass-hi-rgb), 0.09); 
}
.ctm .btn{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 5px;
  height: 34px;
  padding: 0 12px;
  color: var(--text);
  cursor: pointer;
  font-size: var(--fs-sm);
  white-space: nowrap;
}
.ctm .btn.primary{
  --lq-top: 1;
  --lq-top2: 0.22;
  --lq-side: 0.15;
  --lq-bottom: 0.42;
  --lq-glow: 0.1;
  --lq-drop: 0 1px 2.5px rgba(0, 0, 0, 0.68);
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.062) 0%,
    rgba(var(--lq-ink), 0.085) 20%,
    rgba(var(--lq-ink), 0.11) 62%,
    rgba(var(--lq-ink), 0.082) 88%,
    rgba(var(--lq-ink), 0.135) 100%
  );
  color: #fff;
  font-weight: 700;
  letter-spacing: 0.2px;
}
.ctm .btn.ghost{
  --lq-top: 0.6;
  --lq-top2: 0.1;
  --lq-side: 0.07;
  --lq-bottom: 0.24;
  --lq-glow: 0.04;
  --lq-curve: inset 0 -11px 15px -13px rgba(0, 0, 0, 0.95);
  --lq-drop: 0 1px 1.8px rgba(0, 0, 0, 0.55);
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.022) 0%,
    rgba(var(--lq-ink), 0.038) 20%,
    rgba(var(--lq-ink), 0.055) 62%,
    rgba(var(--lq-ink), 0.04) 88%,
    rgba(var(--lq-ink), 0.07) 100%
  );
  color: var(--text-dim);
}
.ctm .btn.ghost:hover{
  color: var(--text);
}
.ctm .btn.danger{
  --lq-ink: 255, 212, 212;
  --lq-top: 0.85;
  --lq-top2: 0.16;
  --lq-side: 0.1;
  --lq-bottom: 0.34;
  --lq-glow: 0.1;
  --lq-curve: inset 0 -11px 15px -13px rgba(0, 0, 0, 0.95);
  --lq-drop: 0 1px 2px rgba(0, 0, 0, 0.6);
  --lq-face: linear-gradient(
    180deg,
    rgba(230, 96, 96, 0.075) 0%,
    rgba(180, 52, 52, 0.1) 22%,
    rgba(180, 52, 52, 0.125) 62%,
    rgba(200, 70, 70, 0.085) 88%,
    rgba(214, 84, 84, 0.14) 100%
  );
  color: #ff9c9c;
}
.ctm .btn.danger:hover{
  color: #ffb4b4;
}
.ctm .btn.sm{
  height: 28px;
  padding: 0 12px;
  flex: none;
  --lq-radius: var(--lq-radius-icon);
}
.ctm .actions{
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.ctm .actions-main{
  display: flex;
  gap: 8px;
}
.ctm .actions-main .btn.primary{
  flex: 1;
  height: 40px;
  font-size: var(--fs-base);
}
.ctm .actions-main .btn.ghost{
  flex: none;
  width: auto;
  min-width: 92px;
}
.ctm .actions-tools{
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.ctm .actions-tools .btn{
  flex: 1 1 calc(33.333% - 6px);
}
.ctm .actions-tools .tip-trigger{
  flex: 1 1 calc(33.333% - 6px);
  display: flex;
}
.ctm .actions-tools .tip-trigger .btn{
  flex: 1 1 auto;
  width: 100%;
}
.ctm .statusbar{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 2px 4px 0;
}
.ctm .count{
  color: var(--text-faint);
  font-size: var(--fs-xs);
}
.ctm .toast{
  position: fixed;
  bottom: 132px;
  left: 50%;
  transform: translateX(-50%) translateY(6px);
  background: rgba(9, 11, 12, 0.78);
  color: #fff;
  padding: 7px 15px;
  border-radius: 999px;
  font-size: var(--fs-sm);
  border: 1px solid var(--glass-border);
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.2s ease, transform 0.2s ease;
  white-space: nowrap;
  z-index: 10;
  box-shadow: var(--shadow-pop), inset 0 1px 0 rgba(255, 255, 255, 0.08);
}
.ctm .toast:not(:empty){
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}
.ctm .brand-mark svg{
  width: 16px;
  height: 16px;
  display: block;
}
.ctm .empty-icon svg{
  width: 34px;
  height: 34px;
  display: block;
}
.ctm .settings-view{
  display: flex;
  flex-direction: column;
  gap: 10px;
  flex: 1;
  min-height: 0;
  overflow: auto;
}
.ctm .settings-view > *{
  flex-shrink: 0;
}
.ctm .settings-view p{
  margin: 0;
}
.ctm .settings-view .back{
  align-self: flex-start;
}
.ctm .sec-title{
  margin: 6px 0 0;
  font-size: var(--fs-sm);
  font-weight: 600;
  color: var(--text);
}
.ctm .ui-unit{
  display: flex;
  flex-direction: column;
  gap: 10px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  padding: 12px;
  cursor: default;
}
.ctm .ui-row{
  display: flex;
  flex-direction: column;
  gap: 6px;
}
.ctm .ui-row + .ui-row{
  padding-top: 10px;
  border-top: 1px solid rgba(var(--glass-edge-rgb), 0.08);
}
.ctm .ui-label{
  color: var(--text-dim);
  font-size: var(--fs-xs);
}
.ctm .ui-ctl{
  display: flex;
  align-items: center;
  gap: 10px;
}
.ctm .ui-ctl input[type='range']{
  flex: 1;
  min-width: 0;
  accent-color: var(--accent);
  cursor: pointer;
  height: 4px;
}
.ctm .ui-val{
  font-size: var(--fs-sm);
  color: var(--text-dim);
  min-width: 38px;
  text-align: right;
  font-variant-numeric: tabular-nums;
}
.ctm .ui-hint{
  font-size: var(--fs-xs);
  color: var(--text-faint);
  min-width: 42px;
  text-align: right;
}
.ctm .ui-note{
  color: var(--text-faint);
  font-size: var(--fs-xs);
  line-height: 1.5;
}
.ctm .ui-unit .theme-row{
  padding: 0;
  gap: 8px;
  flex-wrap: wrap;
}
.ctm .dir-row{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 8px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  padding: 10px 12px;
  cursor: default;
}
.ctm .dir-path{
  flex: 1 1 100%;
  min-width: 0;
  font-size: var(--fs-sm);
  color: var(--text);
  
  overflow-wrap: anywhere;
}
.ctm .dir-ops{
  display: flex;
  align-items: center;
  gap: 6px;
  margin-left: auto;
}
.ctm .dir-note{
  color: var(--text-faint);
  font-size: var(--fs-xs);
  line-height: 1.5;
  margin: 0;
}
.ctm .collect-row{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  padding: 10px 12px;
  cursor: default;
}
.ctm .collect-text{
  display: flex;
  flex-direction: column;
  gap: 2px;
  min-width: 0;
}
.ctm .collect-label{
  font-size: var(--fs-base);
  font-weight: 600;
  color: var(--text);
}
.ctm .collect-desc{
  font-size: var(--fs-xs);
  color: var(--text-dim);
  line-height: 1.45;
}
.ctm .paste-perm{
  margin-top: 8px;
  padding: 10px 12px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
}
.ctm .paste-perm-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
}
.ctm .paste-perm-status{
  font-size: var(--fs-xs);
  font-weight: 600;
}
.ctm .paste-perm-status.ok{
  color: var(--accent, #9aa5ab);
}
.ctm .paste-perm-status.warn{
  color: #e0a35a;
}
.ctm .paste-perm-note{
  margin: 8px 0 0;
  font-size: var(--fs-xs);
  color: var(--text-dim);
  line-height: 1.55;
}
.ctm .paste-perm-note strong{
  color: var(--text);
  font-weight: 600;
}
.ctm .theme-row{
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 2px 2px 6px;
}
.ctm .swatch{
  width: 22px;
  height: 22px;
  border-radius: 50%;
  border: 2px solid transparent;
  padding: 0;
  cursor: pointer;
  transition: transform 0.12s ease, border-color 0.12s ease, box-shadow 0.12s ease;
}
.ctm .swatch:hover{
  transform: scale(1.15);
}
.ctm .swatch.active{
  border-color: #fff;
  box-shadow: 0 0 0 2px rgba(255, 255, 255, 0.25) inset;
}
.ctm .color-picker{
  width: 26px;
  height: 26px;
  padding: 0;
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-xs);
  background: transparent;
  cursor: pointer;
  margin-left: 2px;
}
.ctm .history-list{
  display: flex;
  flex-direction: column;
  gap: 4px;
  background: var(--glass-dark);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  padding: 6px;
  height: 110px;
  overflow: auto;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
}
.ctm .history-item{
  display: grid;
  grid-template-columns: 86px 56px 1fr;
  align-items: center;
  gap: 8px;
  padding: 5px 8px;
  border-radius: var(--radius-xs);
  font-size: var(--fs-xs);
  background: rgba(255, 255, 255, 0.04);
}
.ctm .history-item:hover{
  background: rgba(255, 255, 255, 0.08);
}
.ctm .history-item.clickable{
  cursor: pointer;
}
.ctm .history-item.clickable:active{
  background: rgba(255, 255, 255, 0.12);
}
.ctm .hist-content{
  grid-column: 1 / -1;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding-left: 2px;
}
.ctm .hist-time{
  color: var(--text-faint);
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
.ctm .hist-tag{
  color: var(--accent);
  font-weight: 600;
  white-space: nowrap;
}
.ctm .hist-sum{
  color: var(--text-dim);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .empty-hist{
  color: var(--text-faint);
  font-size: var(--fs-xs);
  text-align: center;
  padding: 14px 0;
}
.ctm .hotkey-group + .hotkey-group{
  margin-top: 14px;
}
.ctm .hotkey-label{
  display: block;
  font-size: var(--fs-xs);
  font-weight: 600;
  color: var(--text);
  opacity: 0.72;
  margin: 0 0 6px;
}
.ctm .hotkey-row{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 10px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  padding: 10px 12px;
  cursor: default;
}
.ctm .settings-view .clear-hist{
  align-self: flex-start;
}
.ctm .wipe-note{
  margin: 0 0 8px;
  font-size: var(--fs-xs);
  line-height: 1.6;
  color: var(--text);
  opacity: 0.66;
}
.ctm .settings-view .wipe-btn{
  align-self: flex-start;
}
.ctm .hotkey-capture{
  font-size: var(--fs-base);
  font-variant-numeric: tabular-nums;
  letter-spacing: 1px;
  color: var(--text);
  background: var(--glass-dark);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-xs);
  padding: 6px 14px;
  min-width: 96px;
  cursor: pointer;
  transition: border-color 0.15s ease;
}
.ctm .hotkey-capture:hover{
  border-color: var(--accent);
}
.ctm .hotkey-capture.capturing{
  cursor: default;
  color: var(--accent);
  border-style: dashed;
  animation: hk-pulse 1.2s ease-in-out infinite;
}
@keyframes hk-pulse{
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}
.ctm .hotkey-actions{
  display: flex;
  gap: 8px;
}
.ctm .hotkey-error{
  color: var(--danger);
  font-size: var(--fs-xs);
  margin: 0;
}
.ctm .hotkey-note{
  color: var(--text-dim);
  font-size: var(--fs-xs);
  margin: 0 0 10px;
  line-height: 1.5;
}
.ctm .col-head{
  display: inline-flex;
  align-items: center;
  gap: 4px;
}
.ctm .col-del, .ctm .row-del{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 16px;
  height: 16px;
  padding: 0;
  border: none;
  border-radius: 4px;
  background: transparent;
  color: var(--text-faint);
  font-size: 14px;
  line-height: 1;
  cursor: pointer;
  opacity: 0;
  transition: opacity 0.12s ease, background 0.12s ease, color 0.12s ease;
}
.ctm .col-del:hover, .ctm .row-del:hover{
  background: var(--danger-soft);
  color: var(--danger);
}
.ctm .grid th:hover .col-del, .ctm .grid tr:hover .row-del{
  opacity: 1;
}
.ctm .grid th.act{
  width: 26px;
  padding: 6px 4px;
}
.ctm .row-act{
  width: 26px;
  text-align: center;
  border-left: 1px solid var(--glass-border-soft);
  padding: 6px 2px;
}
.ctm .ctx-overlay{
  position: fixed;
  inset: 0;
  z-index: 20;
}
.ctm .ctx-menu{
  position: fixed;
  z-index: 21;
  min-width: 118px;
  
  width: max-content;
  
  max-width: calc(100vw - 12px);
  max-height: calc(100vh - 12px);
  overflow: auto;
  background: rgba(13, 15, 16, 0.97);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-sm);
  padding: 4px;
  box-shadow: var(--shadow-pop);
}
.ctm .ctx-item{
  display: block;
  width: 100%;
  text-align: left;
  background: transparent;
  border: none;
  color: var(--text);
  font-size: var(--fs-sm);
  padding: 6px 10px;
  border-radius: var(--radius-xs);
  cursor: pointer;
}
.ctm .ctx-item:hover{
  background: var(--accent-soft);
}
.ctm .ctx-sep{
  height: 1px;
  margin: 4px 2px;
  background: var(--glass-border-soft);
}
.ctm .ctx-batch-input{
  width: 100%;
  margin: 2px 2px 6px;
  box-sizing: border-box;
}
.ctm .ctx-item.danger{
  color: #e07a6a;
}
.ctm .ctx-item.danger:hover{
  background: rgba(224, 122, 106, 0.16);
}
.ctm .modal-overlay{
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.55);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 30;
}
.ctm .modal{
  width: 280px;
  background: rgba(13, 15, 16, 0.98);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-sm);
  padding: 16px;
  box-shadow: var(--shadow-pop);
}
.ctm .modal-title{
  font-weight: 600;
  margin-bottom: 8px;
}
.ctm .modal-desc{
  color: var(--text-dim);
  font-size: var(--fs-sm);
  margin-bottom: 14px;
  line-height: 1.5;
}
.ctm .modal-actions{
  display: flex;
  gap: 8px;
  justify-content: flex-end;
}
.ctm .scroll-area{
  overflow: auto;
  scrollbar-width: thin;
  scrollbar-color: var(--glass-border) transparent;
}
.ctm .scroll-area::-webkit-scrollbar{
  width: 8px;
  height: 8px;
}
.ctm .scroll-area::-webkit-scrollbar-thumb{
  background: var(--glass-border);
  border-radius: 999px;
}
.ctm .scroll-area::-webkit-scrollbar-thumb:hover{
  background: var(--glass-border-soft);
}
.ctm .scroll-area::-webkit-scrollbar-track{
  background: transparent;
}
.ctm .app, .ctm .app *{
  scrollbar-width: thin;
  scrollbar-color: var(--glass-border) transparent;
}
.ctm .app::-webkit-scrollbar, .ctm .app ::-webkit-scrollbar, .ctm ::-webkit-scrollbar{
  width: 8px;
  height: 8px;
}
.ctm .app::-webkit-scrollbar-thumb, .ctm .app ::-webkit-scrollbar-thumb, .ctm ::-webkit-scrollbar-thumb{
  background: var(--glass-border);
  border-radius: 999px;
}
.ctm .app::-webkit-scrollbar-thumb:hover, .ctm .app ::-webkit-scrollbar-thumb:hover, .ctm ::-webkit-scrollbar-thumb:hover{
  background: var(--glass-border-soft);
}
.ctm .app::-webkit-scrollbar-track, .ctm .app ::-webkit-scrollbar-track, .ctm ::-webkit-scrollbar-track{
  background: transparent;
}
.ctm .tip-trigger{
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
.ctm .resize-handles{
  position: absolute;
  inset: 0;
  pointer-events: none; 
  z-index: 60;
}
.ctm .resize-handle{
  position: absolute;
  pointer-events: auto;
  touch-action: none;
}
.ctm .rh-e{
  top: 0;
  right: 0;
  width: 14px;
  height: 100%;
  cursor: ew-resize;
}
.ctm .rh-w{
  top: 0;
  left: 0;
  width: 14px;
  height: 100%;
  cursor: ew-resize;
}
.ctm .rh-s{
  left: 0;
  bottom: 0;
  width: 100%;
  height: 14px;
  cursor: ns-resize;
}
.ctm .rh-se{
  right: 0;
  bottom: 0;
  width: 18px;
  height: 18px;
  cursor: nwse-resize;
}
.ctm .rh-sw{
  left: 0;
  bottom: 0;
  width: 18px;
  height: 18px;
  cursor: nesw-resize;
}
.ctm .app.mini{
  padding: 8px;
  gap: 6px;
}
.ctm .app.mini .grid th.ck, .ctm .app.mini .grid td.ck, .ctm .app.mini .grid th.act, .ctm .app.mini .grid td.row-act{
  display: none;
}
.ctm .app.mini .grid th{
  white-space: nowrap;
}
.ctm .mini-bar{
  display: flex;
  align-items: center;
  gap: 8px;
  height: 30px;
  padding: 0 4px;
  flex: 0 0 auto;
  cursor: grab;
}
.ctm .app.is-dragging .mini-bar{
  cursor: grabbing;
}
.ctm .mini-brand{
  font-weight: 600;
  font-size: var(--fs-sm);
  letter-spacing: 0.02em;
  opacity: 0.85;
  flex: 0 0 auto;
  white-space: nowrap;
}
.ctm .mini-count{
  font-size: var(--fs-xs);
  opacity: 0.6;
  margin-right: auto;
  
  min-width: 0;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .mini-bar .icon-btn{
  flex: 0 0 28px;
  width: 28px;
  padding: 0;
}
.ctm .mini-table{
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  border-radius: var(--radius-xs);
}
.ctm .mini-table .tablewrap{
  flex: 1;
  min-height: 0;
}
.ctm .tooltip{
  position: fixed;
  z-index: 40;
  background: rgba(13, 15, 16, 0.98);
  color: var(--text);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-xs);
  padding: 4px 8px;
  font-size: var(--fs-xs);
  line-height: 1.4;
  max-width: 220px;
  white-space: normal;
  box-shadow: var(--shadow-pop);
  pointer-events: none;
  transform: translateX(-50%);
}
.ctm .tooltip.top{
  transform: translate(-50%, calc(-100% - 6px));
}
.ctm .tooltip.bottom{
  transform: translate(-50%, 6px);
}
.ctm .loading-wrap{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  height: 100%;
  color: var(--text-dim);
}
.ctm .loading-spinner{
  width: 22px;
  height: 22px;
  border: 2px solid var(--glass-border);
  border-top-color: var(--accent);
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}
@keyframes spin{
  to {
    transform: rotate(360deg);
  }
}
.ctm .error-banner{
  display: flex;
  align-items: flex-start;
  gap: 8px;
  background: var(--danger-soft);
  border: 1px solid rgba(255, 107, 107, 0.4);
  color: var(--danger);
  border-radius: var(--radius-sm);
  padding: 8px 10px;
  font-size: var(--fs-sm);
  line-height: 1.5;
}
.ctm .error-banner .err-close{
  margin-left: auto;
  background: transparent;
  border: none;
  color: var(--danger);
  cursor: pointer;
  font-size: 14px;
  line-height: 1;
}
.ctm .perm-banner{
  display: flex;
  align-items: center;
  gap: 10px;
  background: rgba(255, 191, 87, 0.14);
  border: 1px solid rgba(255, 191, 87, 0.35);
  color: var(--warning);
  border-radius: var(--radius-sm);
  padding: 8px 10px;
  font-size: var(--fs-sm);
  line-height: 1.5;
}
.ctm .perm-banner .perm-text{
  flex: 1;
  min-width: 0;
}
.ctm .perm-banner .perm-btn{
  flex: none;
  height: 28px;
  padding: 0 12px;
  border-radius: var(--radius-xs);
  border: 1px solid rgba(255, 191, 87, 0.5);
  background: rgba(255, 191, 87, 0.18);
  color: var(--warning);
  font-size: var(--fs-sm);
  cursor: pointer;
  white-space: nowrap;
}
.ctm .perm-banner .perm-btn:hover{
  background: rgba(255, 191, 87, 0.3);
}
.ctm .notice-bar{
  display: flex;
  align-items: center;
  gap: 8px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  color: var(--text-dim);
  border-radius: var(--radius-xs);
  padding: 6px 10px;
  font-size: var(--fs-xs);
  line-height: 1.45;
}
.ctm .notice-bar .notice-close{
  margin-left: auto;
  background: transparent;
  border: none;
  color: var(--text-faint);
  cursor: pointer;
  font-size: 14px;
  line-height: 1;
}
.ctm .notice-bar .notice-close:hover{
  color: var(--text);
}
.ctm .field-row{
  display: flex;
  align-items: center;
  gap: 8px;
}
.ctm .field-row .field-label{
  color: var(--text-dim);
  font-size: var(--fs-sm);
  flex: none;
}
.ctm .clip-panel{
  display: flex;
  flex-direction: column;
  gap: 10px;
  flex: 1;
  min-height: 0;
  
  overflow-y: auto;
}
.ctm .clip-panel .tablewrap{
  flex: 1;
  min-height: 120px;
  
  flex-shrink: 1;
}
.ctm .app.calc-only{
  
  padding: 0;
  gap: 0;
}
.ctm .calc-desk{
  display: flex;
  flex-direction: column;
  flex: 1;
  min-height: 0;
}
.ctm .calc-bar{
  display: flex;
  flex-direction: column;
  gap: 3px;
  
  flex: none;
  padding: 8px 14px 7px;
  border-radius: var(--radius) var(--radius) 0 0;
  
  cursor: grab;
}
.ctm .app.is-dragging .calc-bar{
  cursor: grabbing;
}
.ctm .calc-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
}
.ctm .calc-head-right{
  display: flex;
  align-items: center;
  gap: 8px;
  flex: none;
}
.ctm .calc-title{
  font-size: var(--fs-xs);
  color: var(--text-faint);
  line-height: 1.3;
  letter-spacing: 0.02em;
}
.ctm .calc-keys{
  flex: none;
  font-size: var(--fs-xs);
  color: var(--text-faint);
  white-space: nowrap;
}
.ctm .calc-close{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 18px;
  height: 18px;
  flex: none;
  padding: 0;
  border: none;
  border-radius: var(--radius-xs);
  background: transparent;
  color: var(--text-faint);
  font-size: 14px;
  line-height: 1;
  cursor: pointer;
  transition: background 0.15s ease, color 0.15s ease;
}
.ctm .calc-close:hover{
  background: rgba(255, 255, 255, 0.1);
  color: var(--text);
}
.ctm .calc-input{
  width: 100%;
  padding: 0;
  border: none;
  outline: none;
  background: transparent;
  color: var(--text);
  font-family: ui-monospace, SFMono-Regular, 'SF Mono', Menlo, monospace;
  font-size: 22px;
  line-height: 1.3;
  letter-spacing: 0.01em;
  white-space: pre;
  overflow-x: auto;
  overflow-y: hidden;
  cursor: text;
}
.ctm .calc-foot{
  display: flex;
  align-items: center;
  gap: 10px;
  min-width: 0;
  
  min-height: 34px;
}
.ctm .calc-preview{
  flex: 1;
  min-width: 0;
  font-family: ui-monospace, SFMono-Regular, 'SF Mono', Menlo, monospace;
  font-size: 28px;
  font-weight: 600;
  font-variant-numeric: tabular-nums;
  line-height: 1.2;
  letter-spacing: -0.01em;
  color: var(--text);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .calc-preview.state-empty{
  color: var(--text-faint);
  font-family: inherit;
  font-size: var(--fs-sm);
  font-weight: 400;
  letter-spacing: 0;
}
.ctm .calc-preview.state-err{
  color: var(--warning);
  font-family: inherit;
  font-size: var(--fs-sm);
  font-weight: 400;
  letter-spacing: 0;
}
.ctm .calc-pad{
  display: flex;
  flex-direction: column;
  gap: 4px;
  flex: 1;
  min-height: 0;
  
  padding: 4px 14px 6px;
  border-top: 1px solid var(--glass-border-soft);
}
.ctm .pad-head{
  display: flex;
  align-items: center;
  gap: 8px;
  height: 20px;
  flex: none;
  cursor: grab;
}
.ctm .app.is-dragging .pad-head{
  cursor: grabbing;
}
.ctm .pad-btn{
  display: inline-flex;
  align-items: center;
  gap: 4px;
  height: 20px;
  padding: 0 7px;
  --lq-radius: var(--lq-radius-tiny);
  --lq-glow: 0;
  --lq-top: 0.55;
  --lq-top2: 0.08;
  --lq-side: 0.06;
  --lq-bottom: 0.2;
  --lq-curve: inset 0 -5px 8px -7px rgba(0, 0, 0, 0.9);
  --lq-drop: 0 1px 1.2px rgba(0, 0, 0, 0.45);
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.02) 0%,
    rgba(var(--lq-ink), 0.045) 60%,
    rgba(var(--lq-ink), 0.07) 100%
  );
  color: var(--text-faint);
  font-size: var(--fs-xs);
  line-height: 1;
  cursor: pointer;
}
.ctm .pad-btn:hover{
  color: var(--text-dim);
}
.ctm .pad-btn.on{
  --lq-top: 0.85;
  --lq-top2: 0.14;
  --lq-side: 0.1;
  --lq-bottom: 0.3;
  --lq-glow: 0.04;
  --lq-face: linear-gradient(
    180deg,
    rgba(var(--lq-ink), 0.035) 0%,
    rgba(var(--lq-ink), 0.062) 60%,
    rgba(var(--lq-ink), 0.095) 100%
  );
  color: var(--text);
}
.ctm .pad-title{
  font-size: var(--fs-xs);
  color: var(--text-faint);
  letter-spacing: 0.02em;
}
.ctm .pad-tools{
  margin-left: auto;
  display: flex;
  align-items: center;
  gap: 2px;
}
.ctm .pad-mini{
  height: 20px;
  padding: 0 6px;
  border: none;
  border-radius: var(--radius-xs);
  background: transparent;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  line-height: 1;
  cursor: pointer;
  transition: background 0.15s ease, color 0.15s ease;
}
.ctm .pad-mini:hover{
  background: rgba(var(--glass-hi-rgb), 0.08);
  color: var(--text);
}
.ctm .pad-text{
  flex: 1;
  min-height: 0;
  width: 100%;
  padding: 4px 6px;
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-xs);
  background: rgba(var(--glass-dark-rgb), 0.28);
  color: var(--text);
  font-family: inherit;
  font-size: var(--fs-sm);
  line-height: 1.5;
  resize: none;
  outline: none;
  transition: border-color 0.15s ease;
}
.ctm .pad-text::placeholder{
  color: var(--text-faint);
}
.ctm .pad-text:focus{
  border-color: var(--accent-sel);
}
.ctm .pad-grid{
  flex: 1;
  min-height: 0;
  overflow: auto;
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-xs);
  background: rgba(var(--glass-dark-rgb), 0.28);
}
.ctm .pad-grid table{
  width: 100%;
  border-collapse: collapse;
  table-layout: fixed;
}
.ctm .pad-grid td{
  padding: 0;
  border-right: 1px solid var(--glass-border-soft);
  border-bottom: 1px solid var(--glass-border-soft);
}
.ctm .pad-grid tr:last-child td{
  border-bottom: none;
}
.ctm .pad-grid td:last-child{
  border-right: none;
}
.ctm .pad-grid .pad-first td{
  background: rgba(var(--glass-hi-rgb), 0.05);
}
.ctm .pad-grid input{
  width: 100%;
  height: 22px;
  padding: 0 6px;
  border: none;
  outline: none;
  background: transparent;
  color: var(--text);
  font-family: inherit;
  font-size: var(--fs-sm);
  line-height: 22px;
}
.ctm .pad-grid input:focus{
  background: rgba(var(--glass-hi-rgb), 0.1);
  box-shadow: inset 0 0 0 1px var(--accent-sel);
}
.ctm .pad-grid input::placeholder{
  color: var(--text-faint);
  opacity: 0.5;
}
.ctm .sec-note{
  margin-left: 6px;
  font-size: var(--fs-xs);
  font-weight: 400;
  color: var(--text-faint);
}
.ctm .calc-hist-list{
  display: flex;
  flex-direction: column;
  gap: 4px;
  height: 110px;
  padding: 6px;
  overflow: auto;
  background: var(--glass-dark);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
}
.ctm .calc-hist-item{
  display: grid;
  grid-template-columns: 86px minmax(0, 1fr) auto;
  align-items: center;
  gap: 8px;
  padding: 5px 8px;
  border-radius: var(--radius-xs);
  font-size: var(--fs-xs);
  background: rgba(255, 255, 255, 0.04);
  cursor: pointer;
}
.ctm .calc-hist-item:hover{
  background: rgba(255, 255, 255, 0.08);
}
.ctm .calc-hist-item:active{
  background: rgba(255, 255, 255, 0.12);
}
.ctm .calc-hist-time{
  color: var(--text-faint);
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
.ctm .calc-hist-expr{
  color: var(--text-dim);
  font-family: ui-monospace, SFMono-Regular, 'SF Mono', Menlo, monospace;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .calc-hist-res{
  color: var(--text);
  font-family: ui-monospace, SFMono-Regular, 'SF Mono', Menlo, monospace;
  font-weight: 600;
  white-space: nowrap;
}
.ctm .ui-select{
  position: relative;
  font-family: inherit;
  font-size: var(--fs-sm);
}
.ctm .ui-select-trigger{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 6px;
  width: 100%;
  padding: 5px 8px 5px 10px;
  background-color: var(--glass-strong);
  color: var(--text);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-xs);
  font-size: var(--fs-sm);
  font-family: inherit;
  text-align: left;
  cursor: pointer;
  outline: none;
  transition: border-color 0.15s ease, background-color 0.15s ease;
}
.ctm .ui-select-trigger:hover{
  border-color: var(--accent);
}
.ctm .ui-select-trigger:focus-visible{
  border-color: var(--accent);
  box-shadow: 0 0 0 2px var(--accent-soft);
}
.ctm .ui-select-value{
  flex: 1;
  min-width: 0;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.ctm .ui-select-chevron{
  flex: none;
  color: #aab4ad;
  transition: transform 0.15s ease;
}
.ctm .ui-select.is-open .ui-select-trigger{
  border-color: var(--accent);
}
.ctm .ui-select.is-open .ui-select-chevron{
  transform: rotate(180deg);
}
.ctm .ui-select-menu{
  position: absolute;
  top: calc(100% + 4px);
  left: 0;
  z-index: 60;
  min-width: 100%;
  max-height: 220px;
  overflow-y: auto;
  margin: 0;
  padding: 4px;
  list-style: none;
  background: rgba(var(--glass-dark-rgb), 0.97);
  border: 1px solid rgba(var(--glass-edge-rgb), 0.22);
  border-radius: var(--radius-xs);
  box-shadow: var(--shadow-pop);
}
.ctm .ui-select-option{
  padding: 5px 8px;
  border-radius: 5px;
  color: var(--text);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  cursor: pointer;
}
.ctm .ui-select-option.is-active{
  background: rgba(var(--glass-hi-rgb), 0.1);
}
.ctm .ui-select-option.is-selected{
  background: rgba(var(--glass-hi-rgb), 0.12);
  font-weight: 600;
  box-shadow: inset 0 0 0 1px var(--accent-sel);
}
.ctm .ui-input{
  background-color: var(--glass-strong);
  color: var(--text);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-xs);
  padding: 4px 8px;
  font-size: var(--fs-sm);
  font-family: inherit;
  outline: none;
  transition: border-color 0.15s ease, box-shadow 0.15s ease;
}
.ctm .ui-input:focus{
  border-color: var(--accent);
  box-shadow: 0 0 0 2px var(--accent-soft);
}
.ctm .ui-input::-webkit-outer-spin-button, .ctm .ui-input::-webkit-inner-spin-button{
  -webkit-appearance: none;
  margin: 0;
}
.ctm .ui-switch{
  position: relative;
  display: inline-flex;
  align-items: center;
  width: 34px;
  height: 18px;
  flex: none;
  padding: 0;
  border-radius: 999px;
  border: 1px solid var(--glass-border);
  background: var(--glass-strong);
  cursor: pointer;
  transition: background 0.16s ease, border-color 0.16s ease;
}
.ctm .ui-switch.is-on{
  background: var(--accent);
  border-color: var(--accent-strong);
}
.ctm .ui-switch:focus-visible{
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}
.ctm .ui-switch-thumb{
  position: absolute;
  left: 2px;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #fff;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.35);
  transition: transform 0.16s ease;
}
.ctm .ui-switch.is-on .ui-switch-thumb{
  transform: translateX(16px);
}
.ctm .ui-checkbox{
  width: 15px;
  height: 15px;
  accent-color: var(--accent);
  cursor: pointer;
  flex: none;
}
.ctm .ui-slider{
  width: 100%;
  accent-color: var(--accent);
  cursor: pointer;
}
.ctm .mode-select{
  width: 120px;
  flex: none;
}
.ctm .colcount-input{
  width: 64px;
  flex: none;
}
.ctm .panel-switch{
  flex: none;
  height: 28px;
  padding: 0 10px;
  border-radius: var(--radius-xs);
  border: 1px solid var(--glass-border);
  background: var(--glass-strong);
  color: var(--text-dim);
  font-size: var(--fs-sm);
  font-family: inherit;
  cursor: pointer;
  transition: background 0.15s ease, color 0.15s ease, border-color 0.15s ease;
}
.ctm .panel-switch:hover{
  background: rgba(var(--glass-hi-rgb), 0.1);
  color: var(--text);
}
.ctm .panel-switch.active{
  background: rgba(var(--glass-hi-rgb), 0.12);
  color: var(--text);
  font-weight: 600;
  box-shadow: inset 0 0 0 1px var(--accent-sel);
}
.ctm .ui-select.is-disabled{
  opacity: 0.4;
}
.ctm .ui-select.is-disabled .ui-select-trigger{
  cursor: not-allowed;
  border-color: var(--glass-border-soft);
}
.ctm .notepad-wrap{
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.ctm .notepad{
  position: relative;
  flex: 1;
  
  min-height: 120px;
  display: flex;
  flex-direction: column;
  padding: 8px 12px 10px;
  background: var(--glass-dark);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-sm);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.06);
  transition: border-color 0.15s ease;
  cursor: text;
}
.ctm .notepad.editing{
  border-color: var(--accent-sel);
}
.ctm .notepad-head{
  flex: none;
  margin-bottom: 4px;
}
.ctm .notepad-label{
  font-size: var(--fs-xs);
  color: var(--text-faint);
  line-height: 1.3;
}
.ctm .notepad-label.editing{
  color: var(--accent);
}
.ctm .notepad-area{
  flex: 1;
  min-height: 0;
  width: 100%;
  padding: 0;
  border: none;
  outline: none;
  resize: none;
  background: transparent;
  color: var(--text);
  font-family: ui-monospace, SFMono-Regular, 'SF Mono', Menlo, monospace;
  font-size: 13px;
  line-height: 1.55;
  
  white-space: pre-wrap;
  overflow-wrap: anywhere;
  overflow-y: auto;
}
.ctm .notepad-area::placeholder{
  color: var(--text-faint);
}
.ctm .notepad-newhint{
  position: absolute;
  right: 12px;
  bottom: 10px;
  padding: 3px 10px;
  border-radius: 999px;
  border: 1px solid var(--glass-border);
  background: rgba(9, 11, 12, 0.86);
  color: var(--text);
  font-size: var(--fs-xs);
  font-family: inherit;
  cursor: pointer;
}
.ctm .notepad-newhint:hover{
  border-color: var(--accent-sel);
}
.ctm .notepad-foot{
  flex: none;
  display: flex;
  justify-content: flex-end;
  padding: 0 4px;
}
.ctm .notepad-count{
  font-size: var(--fs-xs);
  color: var(--text-faint);
}
.ctm .notepad-count.near{
  color: var(--warning);
}
.ctm .notepad-count.full{
  color: var(--danger);
}
.ctm .actions-main .btn.danger{
  flex: none;
  min-width: 76px;
  height: 40px;
}
.ctm .btn:disabled, .ctm .btn:disabled:hover, .ctm .btn:disabled:active{
  --lq-hb: 0.42;
  color: var(--text-faint);
  cursor: not-allowed;
  transform: none;
}
.ctm .seg-bar{
  display: flex;
  flex: none;
}
.ctm .seg{
  display: flex;
  width: 100%;
  gap: 2px;
  padding: 2px;
  border-radius: var(--lq-radius-seg);
  border: 1px solid transparent;
  background: rgba(var(--glass-dark-rgb), 0.55);
  box-shadow:
    inset 0 1px 2px rgba(0, 0, 0, 0.55),
    inset 0 -1px 0 rgba(255, 255, 255, 0.04);
}
.ctm .seg-btn{
  flex: 1;
  height: 26px;
  border: 0;
  border-radius: var(--lq-radius-seg-item);
  background: transparent;
  color: var(--text-dim);
  font-family: inherit;
  font-size: var(--fs-sm);
  cursor: pointer;
  transition: color 0.15s ease;
}
.ctm .seg-btn:hover{
  color: var(--text);
}
.ctm .seg-btn.active{
  color: var(--text);
  font-weight: 600;
}
.ctm .img-board{
  position: relative;
  display: flex;
  flex-direction: column;
  flex: 1;
  
  min-height: 120px;
}
.ctm .img-grid{
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  
  grid-auto-rows: min-content;
  gap: 8px;
  align-content: start;
  flex: 1;
  min-height: 0;
  overflow-y: auto;
  padding-right: 2px;
}
.ctm .img-card{
  position: relative;
  overflow: hidden;
  border-radius: var(--radius-xs);
  border: 1px solid var(--glass-border);
  background: var(--glass-faint);
  cursor: pointer;
  transition: border-color 0.15s ease;
}
.ctm .img-card:hover{
  border-color: var(--accent-sel);
}
.ctm .img-thumb{
  display: block;
  width: 100%;
  aspect-ratio: 16 / 10;
  object-fit: cover;
  background: rgba(0, 0, 0, 0.28);
  user-select: none;
  -webkit-user-drag: none;
}
.ctm .img-meta{
  display: block;
  padding: 3px 6px 4px;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.ctm .img-del{
  position: absolute;
  top: 4px;
  right: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 1px solid var(--glass-border);
  background: rgba(0, 0, 0, 0.48);
  color: var(--text);
  font-size: 13px;
  line-height: 1;
  cursor: pointer;
  opacity: 0;
  transition: opacity 0.12s ease, background 0.12s ease;
}
.ctm .img-card:hover .img-del{
  opacity: 1;
}
.ctm .img-del:hover{
  background: rgba(0, 0, 0, 0.7);
}
.ctm .img-empty{
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 1;
  padding: 0 24px;
  color: var(--text-faint);
  font-size: var(--fs-sm);
  text-align: center;
}
.ctm .img-newhint{
  position: absolute;
  left: 50%;
  bottom: 6px;
  transform: translateX(-50%);
  height: 26px;
  padding: 0 12px;
  border-radius: 13px;
  border: 1px solid var(--glass-border);
  background: rgba(var(--glass-hi-rgb), 0.16);
  color: var(--text);
  font-family: inherit;
  font-size: var(--fs-xs);
  cursor: pointer;
}
.ctm .img-newhint:hover{
  background: rgba(var(--glass-hi-rgb), 0.22);
}
.ctm .img-preview{
  position: fixed;
  inset: 0;
  z-index: 50;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 16px;
  background: rgba(0, 0, 0, 0.72);
}
.ctm .img-preview-img{
  max-width: 92vw;
  max-height: 76vh;
  object-fit: contain;
  border-radius: var(--radius-xs);
  border: 1px solid var(--glass-border);
  background: rgba(0, 0, 0, 0.3);
}
.ctm .img-preview-bar{
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 6px 10px;
  border-radius: var(--radius-sm);
  border: 1px solid var(--glass-border);
  background: rgba(13, 15, 16, 0.86);
}
.ctm .img-preview-meta{
  margin-right: 4px;
  color: var(--text-dim);
  font-size: var(--fs-xs);
}
.ctm .tpl-bar{
  display: flex;
  align-items: center;
  gap: 8px;
  min-height: 26px;
  flex-wrap: nowrap;
}
.ctm .tpl-select{
  flex: 1;
  min-width: 0;
}
.ctm .tpl-bar .btn{
  flex: none;
}
.ctm .tpl-status{
  display: inline-flex;
  align-items: center;
  gap: 5px;
  flex: none;
  color: var(--text);
  font-size: var(--fs-xs);
  letter-spacing: 0.2px;
}
.ctm .tpl-status::before{
  content: '';
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--accent);
}
.ctm .tpl-status.paused{
  color: var(--text-dim);
}
.ctm .tpl-status.paused::before{
  background: transparent;
  box-shadow: inset 0 0 0 1.5px var(--text-faint);
}
.ctm .tpl-name{
  flex: none;
  max-width: 92px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  color: var(--text-dim);
  font-size: var(--fs-xs);
}
.ctm .tpl-ctl{
  flex: none;
  background: transparent;
  border: none;
  color: var(--text-dim);
  font-size: var(--fs-xs);
  padding: 2px 4px;
  border-radius: var(--radius-xs);
  cursor: pointer;
}
.ctm .tpl-ctl:hover{
  color: var(--text);
}
.ctm .tpl-stop:hover{
  color: var(--danger);
}
.ctm .tpl-progress{
  flex: none;
  margin-left: auto;
  color: var(--text-dim);
  font-size: var(--fs-xs);
  font-variant-numeric: tabular-nums;
}
.ctm .tpl-next{
  flex: 0 1 auto;
  max-width: 84px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  color: var(--accent);
  font-size: var(--fs-xs);
}
.ctm .cell.tpl-next{
  position: relative;
  background: rgba(var(--glass-hi-rgb), 0.07);
  box-shadow: inset 0 0 0 1.5px var(--accent);
}
.ctm .cell.tpl-next.sel{
  box-shadow: inset 0 0 0 1.5px var(--accent);
}
.ctm .tpl-view{
  display: flex;
  flex: 1;
  min-height: 0;
  flex-direction: column;
  gap: 8px;
  overflow: auto;
}
.ctm .tpl-head{
  display: flex;
  align-items: center;
  gap: 8px;
  flex: none;
}
.ctm .tpl-back{
  background: transparent;
  border: none;
  color: var(--text-dim);
  font-size: var(--fs-sm);
  padding: 2px 0;
  cursor: pointer;
}
.ctm .tpl-back::before{
  content: '← ';
}
.ctm .tpl-back:hover{
  color: var(--text);
}
.ctm .tpl-head-title{
  color: var(--text);
  font-size: var(--fs-base);
  font-weight: 600;
}
.ctm .tpl-head-count{
  margin-left: auto;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  font-variant-numeric: tabular-nums;
}
.ctm .tpl-head-save{
  margin-left: auto;
  flex: none;
}
.ctm .tpl-note{
  margin: 0;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  line-height: 1.5;
}
.ctm .state-empty-tpl{
  padding: 16px 12px;
  border: 1px dashed var(--glass-border-soft);
  border-radius: var(--radius-sm);
  text-align: center;
}
.ctm .tpl-list{
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 4px;
  min-height: 0;
}
.ctm .tpl-item{
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 7px 8px;
  background: var(--glass-faint);
  border: 1px solid var(--glass-border-soft);
  border-radius: var(--radius-sm);
}
.ctm .tpl-dot{
  flex: none;
  width: 10px;
  height: 10px;
  padding: 0;
  border-radius: 50%;
  background: transparent;
  border: 1.5px solid var(--text-faint);
  cursor: pointer;
}
.ctm .tpl-dot:hover{
  border-color: var(--text-dim);
}
.ctm .tpl-dot.on{
  background: var(--accent);
  border-color: var(--accent);
}
.ctm .tpl-item-name{
  flex: 1;
  min-width: 0;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  color: var(--text);
  font-size: var(--fs-sm);
}
.ctm .tpl-item-meta{
  flex: none;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  font-variant-numeric: tabular-nums;
}
.ctm .tpl-item-ops{
  display: inline-flex;
  gap: 2px;
  flex: none;
}
.ctm .tpl-op{
  background: transparent;
  border: none;
  color: var(--text-dim);
  font-size: var(--fs-xs);
  padding: 2px 4px;
  border-radius: var(--radius-xs);
  cursor: pointer;
}
.ctm .tpl-op:hover:not(:disabled){
  color: var(--text);
}
.ctm .tpl-op.danger:hover:not(:disabled){
  color: var(--danger);
}
.ctm .tpl-op:disabled{
  color: var(--text-faint);
  opacity: 0.4;
  cursor: default;
}
.ctm .tpl-list-actions{
  display: flex;
  align-items: center;
  gap: 8px;
  flex: none;
}
.ctm .tpl-row{
  display: flex;
  align-items: center;
  gap: 8px;
  flex: none;
}
.ctm .tpl-row-label{
  flex: none;
  width: 34px;
  color: var(--text-dim);
  font-size: var(--fs-sm);
}
.ctm .tpl-name-input{
  flex: 1;
  min-width: 0;
}
.ctm .tpl-seg{
  flex: 0 0 132px;
}
.ctm .tpl-seg .seg-btn:disabled{
  opacity: 0.45;
  cursor: default;
}
.ctm .tpl-lock{
  color: var(--text-faint);
  font-size: var(--fs-xs);
}
.ctm .tpl-hint{
  color: var(--text-faint);
  font-size: var(--fs-xs);
}
.ctm .tpl-fields-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex: none;
  color: var(--text-dim);
  font-size: var(--fs-xs);
  padding-top: 2px;
}
.ctm .tpl-fields-count{
  margin-left: auto;
  font-variant-numeric: tabular-nums;
}
.ctm .tpl-grid-wrap{
  
  flex: 0 1 auto;
  min-height: 96px;
  max-height: 260px;
  max-width: 100%;
  overflow: auto;
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-sm);
  background: var(--glass-dark);
}
.ctm .tpl-grid{
  width: 100%;
  table-layout: auto;
  border-collapse: collapse;
}
.ctm .tpl-grid td{
  height: 26px;
  padding: 0;
  border: 1px solid var(--glass-border-soft);
  vertical-align: middle;
  text-align: center;
}
.ctm .tpl-gutter{
  width: 1%;
  padding: 0 5px;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
.ctm .tpl-gutter-locked{
  cursor: help;
}
.ctm .tpl-gutter-locked:hover{
  color: var(--text-dim);
}
.ctm .tpl-hcell{
  min-width: 44px;
  background: rgba(255, 255, 255, 0.05);
}
.ctm .tpl-hinput{
  display: block;
  width: 100%;
  height: 24px;
  box-sizing: border-box;
  padding: 0 4px;
  background: transparent;
  border: none;
  outline: none;
  color: var(--text);
  font-family: inherit;
  
  font-size: var(--fs-xs);
  text-align: center;
}
.ctm .tpl-grid.dir-col .tpl-hcell{
  min-width: 96px;
}
.ctm .tpl-grid.dir-col .tpl-hinput{
  font-size: var(--fs-sm);
  text-align: left;
}
.ctm .tpl-hinput::placeholder{
  color: var(--text-faint);
}
.ctm .tpl-hinput:focus{
  background: var(--accent-soft);
  box-shadow: inset 0 0 0 1.5px var(--accent);
}
.ctm .tpl-gcell::after{
  content: '·';
  color: var(--text-faint);
  font-size: var(--fs-xs);
}
.ctm .tpl-addbtn{
  flex: none;
  margin-left: 4px;
  padding: 0 3px;
  background: transparent;
  border: none;
  color: var(--text-dim);
  font-size: var(--fs-sm);
  line-height: 1;
  cursor: pointer;
}
.ctm .tpl-addbtn:hover:not(:disabled){
  color: var(--text);
}
.ctm .tpl-addbtn:disabled{
  opacity: 0.35;
  cursor: default;
}
.ctm .tpl-rule{
  color: var(--text-dim);
}
.ctm .tpl-modal-cancel{
  display: block;
  width: 100%;
  margin-top: 6px;
  background: transparent;
  border: none;
  color: var(--text-faint);
  font-size: var(--fs-xs);
  padding: 4px;
  cursor: pointer;
}
.ctm .tpl-modal-cancel:hover{
  color: var(--text-dim);
}
/* ===== 信内界面 demo 的搬运层：只负责「放到页面上多大」，其余全部来自 app 自身 CSS ===== */
.mock {
  --k: 1;
  --nw: 384;
  --nh: 580;
  --s0: 1;
  position: relative;
  flex: none;
  width: calc(var(--nw) * 1px);
  height: calc(var(--nh) * 1px);
}
.mock-stage {
  position: relative;
  transform: scale(1);
  transform-origin: 0 0;
  border-radius: 14px;
  /* 应用窗外的一点悬浮感：与信中其它卡片同一套阴影语言 */
  box-shadow: 0 24px 56px rgba(0, 0, 0, 0.42), 0 2px 8px rgba(0, 0, 0, 0.3);
}
.mock .ctm {
  position: relative;
  box-sizing: border-box;
  /* 对应 app 的 body 基线（字体 / 颜色 / 字号在源文件里写在 body 上） */
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC',
    'Microsoft YaHei', sans-serif;
  color: var(--text);
  font-size: var(--fs-base);
  line-height: 1.5;
  user-select: none;
  -webkit-font-smoothing: antialiased;
  overflow: hidden;
  border-radius: 14px;
  /* 应用窗口是透明的，这里用一块深色桌面托底：把「不透明度」滑杆的效果透出来 */
  background:
    radial-gradient(120% 90% at 102% -2%, #16233c 0%, rgba(22, 35, 60, 0) 58%),
    radial-gradient(110% 85% at -4% 102%, #0f2b28 0%, rgba(15, 43, 40, 0) 62%),
    linear-gradient(158deg, #0c1120 0%, #090d15 58%, #0a1017 100%);
}
.mock .app {
  height: 100%;
}
/* 384 宽下顶栏的可用宽度只有 354px，品牌名会被挤掉最后 1px 出现省略号；
   收 1px 栏间距（肉眼不可辨），让「ClipTable」完整显示 */
.mock .topbar {
  gap: 5px;
}
/* 信里不需要呼吸动画（与 ADR-027 的克制口径一致） */
.mock .status:not(.paused):not(.denied) .dot {
  animation: none;
  box-shadow: none;
}
/* 应用内 fixed 定位的元素，在 demo 里要相对窗口定位 */
.mock .toast {
  position: absolute;
  bottom: 116px;
}
.mock .modal-overlay {
  position: absolute;
  border-radius: 14px;
}
/* 三种形态：一次只显示一个（对应 store.panel 的切换） */
.mock .mp {
  display: none;
}
.mock .mp.on {
  display: flex;
  flex-direction: column;
  gap: 10px;
  flex: 1;
  min-height: 0;
}
.mock .mp-tbl {
  display: flex;
  flex-direction: column;
  flex: 1;
  min-height: 0;
}
/* 自绘下拉：菜单只在展开时出现（组件里是 v-if，这里用 CSS 等价表达） */
.mock .ui-select:not(.is-open) .ui-select-menu {
  display: none;
}
.mock .ui-select-menu {
  z-index: 40;
}

/* ==================================================================
   隔离层：信本身的 CSS 与 app 的 CSS 有两处同名冲突，必须按「后来者」压回去。
   冲突清单（用类名求交算出来的，只有这几条）：
     · section        信里给 <section> 加了 opacity:0 的入场动画，app 的面板/分段栏
                      也是 <section>，会被整块藏起来
     · footer         信里的页脚有 border-top + padding:30px 0 46px
     · .btn           信里的主题切换圆按钮是 38px 圆，正好撞 app 的通用按钮类
   `.mock` 前缀让这层始终排在 app 样式之后、且优先级不低于它。
   ================================================================== */
.mock section {
  opacity: 1 !important;
  transform: none !important;
  transition: none !important;
  margin-bottom: 0 !important;
  scroll-margin-top: 0;
}
.mock footer {
  border-top: 0;
  padding: 0;
  color: inherit;
  font-size: var(--fs-base);
  flex-wrap: nowrap;
  gap: 8px;
  justify-content: flex-start;
}
.mock .btn {
  width: auto;
  height: 34px;
  box-shadow: none;
  color: var(--text);
}
.mock .btn.sm {
  height: 28px;
}
.mock .btn.primary {
  color: #fff;
}
.mock .btn.ghost {
  color: var(--text-dim);
}
.mock .btn.danger {
  color: #ff9c9c;
}

/* 一组示意图的并排容器 */
.demo {
  display: flex;
  gap: 14px;
  justify-content: center;
  align-items: flex-start;
  flex-wrap: wrap;
  padding: 20px 16px;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  background:
    radial-gradient(60% 80% at 22% 0%, rgba(90, 168, 130, 0.1), transparent 62%),
    radial-gradient(60% 80% at 84% 100%, rgba(90, 157, 232, 0.1), transparent 62%),
    #0d1412;
  box-shadow: 0 18px 44px rgba(4, 12, 9, 0.34);
  overflow: hidden;
}
.demo-cell {
  flex: 1 1 0;
  min-width: 0;
  display: flex;
  justify-content: center;
}
.demo-cell.solo {
  flex: 0 1 auto;
}
/* 单张时给个上限，别把 384 的窗口拉到 700 宽 */
.demo .mock[data-cap] {
  flex: none;
}
.mock .settings-view {
  display: none;
}
.mock .tpl-view {
  display: none;
}
.mock .tpl-view.on {
  display: flex;
}
.mock [hidden] {
  display: none !important;
}
/* 信里的图片框自带 hover 放大，对可交互 demo 会晃，去掉 */
.fig-frame .mock {
  transition: none;
}
.fig-frame:hover .mock {
  transform: none;
}


/* ==================================================================
   信内可交互界面（截图替代）——样式全部来自 app 自身的 style.css，
   这里只补「信里的容器」与 hero 两张浮窗的尺寸。
   ================================================================== */
.demo-fig .demo {
  margin: 0;
}
/* hero 两张浮窗：原来是 <img>，现在是实时窗口 */
.hero-art .app-shot {
  width: 250px;
  border-radius: 16px;
  background: #0b0c0e;
}
.hero-art .mini-shot {
  width: 236px;
  border-radius: 14px;
  background: #0b0c0e;
}
.hero-art .mock-stage {
  box-shadow: none;
}
.hero-art .mock .ctm {
  border-radius: 16px;
}
/* 可交互的窗口不该在 hover 时缩放 */
.fig-frame:hover img {
  transform: none;
}
/* 首屏两张浮窗带漂浮动画：鼠标进去就停住，方便点按钮 */
.hero-art .app-shot:hover,
.hero-art .mini-shot:hover {
  animation-play-state: paused;
}
/* 微信二维码：原图 592×760（含昵称与底部说明），132px 太小扫不动，放到 186px */
.qr {
  width: 186px;
  padding: 7px;
}
/* 首屏导语：文案缩成 29 字后，原 490px 会把「你。」挤成孤零零的第二行（实测 2 行、
   末行 2 字）。提到 520px 正好一行排完（实测 1 行 29 字）；窄屏仍受容器约束，不受影响 */
.hero .lead {
  max-width: 520px;
}
/* 结尾的「数据与卸载」：比正文低一档的细则块，4 条两列排 */
.fineprint {
  margin-top: 22px;
  padding: 20px 24px 18px;
  border: 1px solid var(--line);
  border-radius: 16px;
  background: rgba(13, 106, 85, 0.035);
}
.fineprint h3 {
  margin: 0 0 12px;
  font-family: var(--serif);
  font-size: 16px;
  color: var(--ink);
}
.fineprint ul {
  margin: 0;
  padding: 0;
  list-style: none;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 11px 24px;
}
.fineprint li {
  position: relative;
  padding-left: 14px;
  font-size: 13px;
  line-height: 1.7;
  color: var(--soft);
}
.fineprint li:before {
  content: "";
  position: absolute;
  left: 0;
  top: 8px;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: var(--bright);
  opacity: 0.65;
}
.fineprint li b {
  display: block;
  font-size: 13px;
  color: var(--ink);
}
.fineprint p {
  margin: 14px 0 0;
  padding-top: 12px;
  border-top: 1px dashed var(--line);
  font-size: 12.5px;
  line-height: 1.8;
  color: var(--mute);
}
/* 版权提示：全信唯一一处红色字样（浅色 #C7391F / 墨色 #FF8574），别扩散到别处 */
:root {
  --warn: #C7391F;
}
[data-theme="dark"] {
  --warn: #FF8574;
}
.fineprint .warn {
  color: var(--warn);
  font-weight: 600;
}
@media (max-width: 640px) {
  .demo {
    padding: 14px 10px;
    gap: 10px;
  }
  .hero-art .app-shot {
    width: 200px;
  }
  .hero-art .mini-shot {
    width: 190px;
  }
  .qr {
    width: 168px;
  }
  .fineprint {
    padding: 18px 18px 16px;
  }
  .fineprint ul {
    grid-template-columns: 1fr;
    gap: 10px;
  }
}
@media print {
  .demo {
    border: 1px solid #ddd;
    break-inside: avoid;
  }
}

</style>
</head>
<body>
<div id="bar"></div>
<div class="controls">
  <button class="btn" id="themeBtn" title="切换浅色 / 墨色" aria-label="切换主题">
    <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="4.2"/><path d="M12 2v2M12 20v2M4.9 4.9l1.4 1.4M17.7 17.7l1.4 1.4M2 12h2M20 12h2M4.9 19.1l1.4-1.4M17.7 6.3l1.4-1.4"/></svg>
  </button>
  <button class="btn" id="toTop" title="回到开头" aria-label="回到开头">
    <svg viewBox="0 0 24 24"><path d="M12 19V5M5 12l7-7 7 7"/></svg>
  </button>
</div>

<header class="hero">
  <div class="wrap">
    <div class="hero-copy">
      <div class="eyebrow"><i></i>A LETTER FOR USERS · ClipTable</div>
      <h1>给用户的一封信<br><em>关于复制这件小事</em></h1>
      <p class="lead">想把那些原要花在来回切换、重复粘贴上的时间，一点点还给你。</p>
      <div class="signature-line"><span></span>写给第一次打开 ClipTable 的你</div>
    </div>
    <div class="hero-art">
      <svg class="leaf-branch" viewBox="0 0 220 260" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M28 250C60 190 70 120 150 24" stroke="#0D6A55" stroke-width="2.4" stroke-linecap="round"/>
        <path d="M70 178C42 172 28 152 26 132c28 2 46 18 44 46Z" fill="#C9E86B" opacity=".75"/>
        <path d="M96 132c-24-16-30-40-26-58 28 8 40 30 26 58Z" fill="#17A583" opacity=".55"/>
        <path d="M126 86c26-6 44-24 48-46-28-2-48 16-48 46Z" fill="#C9E86B" opacity=".8"/>
        <path d="M150 48c14-18 34-26 52-24-6 22-24 36-52 24Z" fill="#17A583" opacity=".5"/>
        <circle cx="150" cy="24" r="6" fill="#FF7A55"/>
      </svg>
      <svg class="doodle" viewBox="0 0 150 120" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 92c30-8 40-48 74-46 22 1 30 20 60 10" stroke="#FFC94A" stroke-width="2" stroke-dasharray="5 7" stroke-linecap="round"/>
        <path d="M132 44l12 12-16 4 4-16Z" fill="#FF7A55"/>
        <circle cx="8" cy="92" r="4" fill="#17A583"/>
      </svg>
      <div class="app-shot"><div class="mock" data-mock="main" data-nw="384" data-nh="580" data-config='{"rows":[["都市系列","88071","23000"],["UR 系列","7237","5787"],["轻商务","5160","3420"],["针织系列","4098","2890"]],"cols":3,"mode":"table"}'></div></div>
      <div class="mini-shot"><div class="mock" data-mock="mini" data-nw="307" data-nh="196" data-config='{"rows":[["都市系列","88071","23000"],["UR 系列","7237","5787"],["轻商务","5160","3420"],["针织系列","4098","2890"]],"cols":3}'></div></div>
      <div class="paper-chip chip-1"><span class="dot"></span>监听中 · <b>正在替你收好</b></div>
      <div class="paper-chip chip-2">✦ <b>一次复制，整段带走</b></div>
    </div>
  </div>
</header>

<div class="quick wrap">
  <div class="quick-card">
    <div class="quick-title"><small>FIRST 30 SECONDS</small>先花 30 秒<br>感受一下</div>
    <div class="steps">
      <div class="step"><span class="n">1</span><span>打开 ClipTable，看到顶部的 <b>「监听中」</b></span></div>
      <div class="step"><span class="n">2</span><span>像平时一样，<b>连续复制</b>几处内容</span></div>
      <div class="step"><span class="n">3</span><span>点 <b>「复制为表格」</b>，一次粘贴到目标处</span></div>
    </div>
  </div>
</div>

<div class="wrap letter">
  <nav class="toc">
    <p>CONTENTS</p>
    <a href="#s1"><span>01</span>一张会自己长出来的表</a>
    <a href="#s2"><span>02</span>三种姿态，轻点 Shift</a>
    <a href="#s3"><span>03</span>顺手算一下</a>
    <a href="#s4"><span>04</span>给数据一个名字</a>
    <a href="#s5"><span>05</span>调成用户的样子</a>
    <a href="#s6"><span>06</span>两个小开关</a>
    <a href="#s7"><span>07</span>关于隐私</a>
    <a href="#s8"><span>08</span>最后，一个小请求</a>
    <div class="end">读完大约 5 分钟。<br>也可以只挑需要的那一节看。</div>
  </nav>

  <article>
    <p class="opener"><span class="salut">致每一位和数据打交道的用户：</span>
    写这封信，是因为我太熟悉那个动作了——在网页和表格之间来回切换，复制一格，切过去，粘贴，再切回来。一天下来，真正留给思考的时间，反倒被这些来回挤得所剩无几。</p>
    <p>做 <strong>ClipTable</strong> 的初心很朴素：<mark>少做重复劳动，多留点时间给自己</mark>。让连续复制的内容自己排好队，让用户少切换一次、少重复一步。它不喧哗，也不替用户做决定，只安静地待在屏幕一角。</p>
    <p>下面每一节都对应一个实际会用到的动作。我们开始吧。</p>

    <div class="divider">✦ &nbsp; THE LETTER &nbsp; ✦</div>

    <section id="s1">
      <div class="sec-head">
        <div class="sec-num">01</div>
        <div><span class="sub">START HERE</span><h2>一张会自己长出来的表</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="16" rx="2"/><path d="M3 9h18M9 9v11M15 9v11"/></svg>
      </div>
      <p>不必先建表，也不必想好要几行几列。用户连续复制的内容，会<strong>依次落进一张临时表格</strong>；格子可以直接改，整张表可以复制、导出，不需要了就清空。从 Excel 或网页框选一整块复制过来，默认的<strong>「整表粘贴」</strong>会原样保留行列。</p>
      <ul class="clean">
        <li>顶部的<strong>「监听中」</strong>表示正在收集；点<strong>「暂停」</strong>就先歇一会儿，不必退出。</li>
        <li><strong>图钉</strong>让窗口始终置顶；旁边的<strong>小窗模式</strong>只留表格，把屏幕还给别的工作。小窗里按清空快捷键会直接清空，省掉一次确认。</li>
        <li>「进表模式」还能改成<strong>每次一行 / 每次一格 / 每次一列</strong>，配合不同的复制习惯。</li>
      </ul>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell"><div class="mock" data-mock="main" data-nw="384" data-nh="580" data-config='{"rows":[["都市系列","88071","23000"],["UR 系列","7237","5787"],["轻商务","5160","3420"],["针织系列","4098","2890"]],"cols":3,"mode":"table"}'></div></div><div class="demo-cell"><div class="mock" data-mock="mini" data-nw="307" data-nh="196" data-config='{"rows":[["都市系列","88071","23000"],["UR 系列","7237","5787"],["轻商务","5160","3420"],["针织系列","4098","2890"]],"cols":3}'></div></div></div>
        <figcaption>左：主面板（点「进表模式」可展开四种模式）　·　右：整块数据原样落表后的小窗</figcaption>
      </figure>
      <div class="tip">复制 → 收好 → 一次带走。中间那些来回切换，可以省了。</div>
    </section>

    <section id="s2">
      <div class="sec-head">
        <div class="sec-num">02</div>
        <div><span class="sub">THREE MODES</span><h2>三种姿态，轻点 Shift 就换</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><path d="M4 7h10M18 7h2M4 12h2M10 12h10M4 17h10M18 17h2"/><circle cx="16" cy="7" r="2"/><circle cx="8" cy="12" r="2"/><circle cx="16" cy="17" r="2"/></svg>
      </div>
      <p>同一份数据、一段灵感、一张截图，值得不同的去处。<kbd>Shift</kbd> 轻点一下，就在三种模式间切换。</p>
      <div class="mode-grid">
        <div class="mode"><svg class="m-ico" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="16" rx="2"/><path d="M3 9h18M9 9v11"/></svg><h4>表格</h4><p>把复制的内容收进临时表格。做报表、填重复数据最顺手。</p></div>
        <div class="mode"><svg class="m-ico" viewBox="0 0 24 24"><path d="M5 4h14v16H5zM8 8h8M8 12h8M8 16h5"/></svg><h4>记事板</h4><p>随手记点东西，用快捷键唤出就能写，不必再开一个笔记 App。</p></div>
        <div class="mode"><svg class="m-ico" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="16" rx="2"/><circle cx="8.5" cy="9" r="1.5"/><path d="M4 17l5-5 4 4 3-3 4 4"/></svg><h4>图片</h4><p>截图和复制的图片都收在这里，不用再去文件夹里翻。</p></div>
      </div>
      <p>一个小提醒：表格和图片里的内容<strong>点一下就能复制</strong>；记事板更适合整段带走。</p>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell solo"><div class="mock" data-mock="main" data-nw="384" data-nh="580" data-config='{"panel":"note","rows":[],"cols":3,"mode":"table","note":"都市系列 88071\nUR 系列 7237\n轻商务 5160\n\n周四那版海报，主色换成湖青试试"}'></div></div></div>
        <figcaption>点「表格 / 记事板 / 图片」三个页签即可切换；记事板里可以直接打字</figcaption>
      </figure>
      <div class="tip">表格装数据，记事板装想法，图片装画面——切换只需要一下 <kbd>Shift</kbd>。</div>
    </section>

    <section id="s3">
      <div class="sec-head">
        <div class="sec-num">03</div>
        <div><span class="sub">CALCULATE</span><h2>顺手算一下，不用另开计算器</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><rect x="4" y="3" width="16" height="18" rx="2"/><path d="M7 7h10M8 12h2M14 12h2M8 16h2M14 16h2"/></svg>
      </div>
      <p>打开<strong>「计算」</strong>开关，在表格里敲数字会自动唤出<strong>计算台</strong>；写一个式子，按 <kbd>Enter</kbd>，结果就已经在剪贴板里了。</p>
      <ul class="clean">
        <li>计算台下方是<strong>速记板</strong>和<strong>速记表</strong>，点一下切换，把要对比的数据先放进去。</li>
        <li>关掉计算台<strong>不会清空</strong>这些内容，下次打开还在。</li>
        <li>不想被自动唤起？关掉「计算」开关，需要时按 <kbd>Ctrl</kbd> + <kbd>=</kbd>（Mac 是 <kbd>⌘</kbd> + <kbd>=</kbd>）手动打开。</li>
      </ul>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell"><div class="mock" data-mock="calc" data-nw="420" data-nh="260" data-config='{}'></div></div><div class="demo-cell"><div class="mock" data-mock="calc" data-nw="420" data-nh="260" data-config='{"padTable":true}'></div></div></div>
        <figcaption>左：输入式子，回车即得结果　·　右：点左下角「表格」换成速记表</figcaption>
      </figure>
      <div class="tip">数字落表的那一刻，算式和结果都提前准备好了。</div>
    </section>

    <section id="s4">
      <div class="sec-head">
        <div class="sec-num">04</div>
        <div><span class="sub">TEMPLATES</span><h2>给数据一个名字</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><path d="M4 5h16v14H4zM4 10h16M10 10v9M15 5v5"/><path d="M6 14h2M12 14h2"/></svg>
      </div>
      <p>从十几个地方各复制一个数字，回头最容易搞混的不是数字，而是「这格是谁」。先建一个<strong>模板</strong>，按行或按列排好字段名，激活之后，每复制一次就自动填进下一格，光标跟着走；一轮填完自动换行或换列，中途也能改。</p>
      <p>填好后复制整张表，粘到要用的地方就行。点主界面的<strong>「管理」</strong>新建和编辑；保存会生成一个 <strong>.xlsx</strong> 文件，默认放在「下载 / ClipTable」，也能自己选目录，下次打开「管理」会自动读回。主界面的模板下拉框只用来<strong>开始填充</strong>，改字段还要回「管理」。</p>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell solo"><div class="mock" data-mock="main" data-nw="384" data-nh="580" data-config='{"rows":[["CPM","CTR","GMV"],["","",""]],"cols":3,"mode":"table","tplName":"日报一"}'></div></div></div>
        <figcaption>点「管理」进模板、点「开始填充」看逐格落表（示意图，数据不会真的变化）</figcaption>
      </figure>
      <div class="tip">先给表格写好表头，剩下的重复动作交给 ClipTable。</div>
    </section>

    <section id="s5">
      <div class="sec-head">
        <div class="sec-num">05</div>
        <div><span class="sub">MAKE IT YOURS</span><h2>把它调成用户的样子</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><circle cx="8" cy="9" r="1.6"/><circle cx="15" cy="8" r="1.6"/><circle cx="16.5" cy="14" r="1.6"/><circle cx="9" cy="15.5" r="1.6"/></svg>
      </div>
      <p>工具要顺手，也得顺眼。设置里可以调<strong>窗口不透明度</strong>、<strong>主题色</strong>（整窗玻璃和按钮的色调），以及<strong>按钮反光强度</strong>——按自己看着舒服来就好，拖动时即时预览，松手后记住。</p>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell solo"><div class="mock" data-mock="settings" data-nw="384" data-nh="580" data-sec="ui" data-config='{}'></div></div></div>
        <figcaption>三处滑杆都能拖：不透明度、主题色、按钮反光会实时作用在这个窗口上</figcaption>
      </figure>
      <div class="tip">它应该长在用户的工作流里，而不是让用户去适应它。</div>
    </section>

    <section id="s6">
      <div class="sec-head">
        <div class="sec-num">06</div>
        <div><span class="sub">TWO SWITCHES</span><h2>两个小开关，一点小偏好</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><rect x="2" y="7" width="20" height="10" rx="5"/><circle cx="16" cy="12" r="3"/></svg>
      </div>
      <ul class="clean">
        <li><strong>重复内容也收录：</strong>关着时，连续复制相同内容只记一条；打开后，复制几次就记几条——需要反复收同一个数字时很好用。</li>
        <li><strong>点选即贴：</strong>光标停在某个 App 的输入框里，点一下表格里的格子，内容就直接输进去，省掉粘贴这一步。它也可能误触、改掉表格里的数据，是否开启看使用习惯。</li>
      </ul>
      <p>设置里还能查到<strong>「历史记录」</strong>（收过的内容）和<strong>「计算记录」</strong>（算过的式子），都只存在本次运行的内存里，退出 ClipTable 就清空。</p>
      <figure class="fig demo-fig">
        <div class="demo"><div class="demo-cell solo"><div class="mock" data-mock="settings" data-nw="384" data-nh="580" data-sec="collect" data-config='{}'></div></div></div>
        <figcaption>两个开关都在设置页的「收集」一节；往下滚就是历史与计算记录（可上下滚动）</figcaption>
      </figure>
      <div class="tip">默认就很克制，想更顺手时再打开那两个开关。</div>
    </section>

    <section id="s7">
      <div class="sec-head">
        <div class="sec-num">07</div>
        <div><span class="sub">PRIVACY, CLEARLY</span><h2>关于隐私，我想说清楚</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><path d="M12 3l8 3v6c0 5-3.5 8-8 9-4.5-1-8-4-8-9V6l8-3Z"/><path d="M9 12l2 2 4-4"/></svg>
      </div>
      <p>这一节不修辞，只讲事实。用户复制了什么，是用户自己的事，不该变成别人服务器上的一行日志。</p>
      <div class="privacy">
        <h3><svg viewBox="0 0 24 24"><path d="M12 3l8 3v6c0 5-3.5 8-8 9-4.5-1-8-4-8-9V6l8-3Z"/><path d="M9 12l2 2 4-4"/></svg>ClipTable 的边界</h3>
        <div class="privacy-grid">
          <div><b>不联网</b>代码里没有任何网络请求，数据不出这台机器。</div>
          <div><b>不上传</b>没有账号、没有云端，自然也没有「同步」这一步。</div>
          <div><b>不收集</b>不统计、不埋点，不打听用户复制了什么。</div>
          <div><b>不自启</b>不写开机启动项，不会开机就常驻后台。</div>
        </div>
      </div>
      <div class="tip">它记得住这次的操作，也忘得干净退出后的痕迹。</div>
    </section>

    <section id="s8">
      <div class="sec-head">
        <div class="sec-num">08</div>
        <div><span class="sub">ONE LAST THING</span><h2>最后，一个小请求</h2></div>
        <svg class="icon" viewBox="0 0 24 24"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="M3 7l9 6 9-6"/></svg>
      </div>
      <p>ClipTable 是实习时，把自己踩过的坑和用过的工具攒起来做的小东西。它不追求功能清单有多长，只希望每次伸手去按复制时，能少一点机械、多一点从容。</p>
      <p>遇到 bug，或者想到什么新功能，欢迎扫码告诉我（仅用于 ClipTable 的问题和建议）。每个想法我都会认真看，也常常因此改出更好的版本。</p>
      <div class="closing">
        <p>愿这封信之后，今天能少按几次 <strong>Ctrl + V</strong>，<br>把省下的时间，花在真正值得的地方。</p>
        <div class="sign">—— 一个也曾在表格里加班的人<br><span style="font-size:13px;font-weight:400;color:var(--soft)">ClipTable 作者 · 敬上</span></div>
      </div>
      <div class="fineprint">
        <h3>数据与卸载</h3>
        <ul>
          <li><b>只留在内存</b>复制的内容、表格与历史，退出即清空。</li>
          <li><b>写盘极简</b>只有一个几百字节的界面偏好文件，保存你改过的界面与功能设置（下次打开还是你的样子），不含任何隐私内容。</li>
          <li><b>用户保存的不动</b>模板与导出的表格留在所选文件夹，卸载不会删。</li>
          <li><b>卸载会清理</b>安装目录与应用数据目录；浏览器组件缓存偶因进程占用残留，属系统缓存。</li>
        </ul>
        <p>如果觉得好用，欢迎推荐给朋友；<span class="warn">未经作者允许禁止商用</span>。</p>
      </div>
      <div class="contact">
        <div>
          <h3>保持联系 ✦</h3>
          <p>反馈问题、提议功能，或只是打个招呼，都欢迎。<br>这扇门一直开着。</p>
        </div>
        <div class="qr"><img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgFBgcGBQgHBgcJCAgJDBMMDAsLDBgREg4THBgdHRsYGxofIywlHyEqIRobJjQnKi4vMTIxHiU2OjYwOiwwMTD/2wBDAQgJCQwKDBcMDBcwIBsgMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDD/wAARCAL4AlADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD3+iiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiijNABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFADaKDRSAKKKKACiiigAooooAKKKKAHCigUHpTA8z8YXfxSXxFdp4X061m0kFPJkkaIMfkXdncwP3s9RXmPhfUPiR/wnOq/2VE0+rgS/abed18qP94u/blgvDYAwTx04r0v4seMNa8OeJfDdlpVwsUF9LtnUxq2750HUgkcE9KwJPEUmmfHnVjf6ncR6VaQNI8RlYxqBbqeEzjOemB196AOY+Jl/8Svsdn/wlEQsoRKwj+yOgLtj+Ly2J6evFdnot58Yt9itxp1qbTKeY5aDd5fGT9/Oce1ee/2z4p1jxHq/j7RyLO2tpMCa4dAqLt2rHtY4dguOADzz1Ir0DwRqnxP1e906+nvbC70R5l8+SFoD+7z8w+XkHHbqKAOn+MPji+8D6RZ3OnWtvPJdSmP9/kquBnOARn8646L4q+PZIUb/AIQSeVWA+ZLafBz3HB/nXofxC8F2PjXS4oL+S6RrYvJCLd1Xc5XAB3KePyrz62k+NtvbRQR2FsUiUIuWts4A4z81AHN+EfFHxE8PX15cS6BrWprdgAx3sFy/lkEkFSQT0JHv+FbOrfGPxppkEc954SWwhMgUyXVvOqtwTtBOMMQOOvTpVHRfHXxT13VrzTNKS2uLyy3efHsgXZtbaeSQDzxwTW0PDnxB8aX9npnxCtBDoayNO8ltJAHVxG4T7pJ6tjpQB614fvm1PQtO1CRQj3dtFOVHQFkDED860apaZYx6ZplrYW5JhtIUhjLnLFVU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eOWOzjDK4wRx3FAHm3hT4N6noXgrxVp+q6vYRyatBGqSJuMcQjJfc7EDAJOOnA556VyvgD4VSW/jTSLo+LPDV19luUuPJs73zpZNh3bVXAznHPPA5r2f4xQTXHwy1+K2ieWQ2+dqDJwGBP5AE/QV8t/DCCaf4h+Hkto2kcX8MhCAkhVcMx47BQSfagD7BvPFGg2F01rfa1ptrOgG6Ka7jjcZGeVJBrg/jN8PL34jWukXGh6hZp9lEjDzidkiSbCGVlB/u+nOetfP3xVt57f4keIkuUeNmvpZFD8EozFlI9iCCPavp34Kwz2/ww0GK5jeNxAzbXBBwzsynnsVII9qAOb+C/wx1L4f32o3+tX1nIbiERBYCxVVB3FizAY6en416Ba+KNAu50t7TXNLuJ5DhIoryN2Y+gAOTVT4m28114A16G2jeSZ7GUIsYJZjt6ADrXyD4It5rjxhosdtG0spvISEQZPDgn9BmgD1X4p/DJtR8danfDxX4csftTLN5N/eeTKmVA5XB444Pet3U/hBf6x8MPDuj6ZrGmz3FhJLOZssYJVlOTtZQc47HHPtXlXxthmg+J+ufaI3TzJg6bxjcpUYI9q+hPgHBPb/AAs0lbiNoyTK6qwIyjSMVPPYggj2oA5P4bfBnVvDcmttq2p2J/tHTJtPj+zBn2eZjLncF6Y6d/UV59YfB2S61GG3PjTwuRJII8Q3vmSnn+FMDJ9sj619KeMYpbjwjrUFvG8k0lhOiIi5ZmMbAAD1zXxLZWlzdXsNrZxSS3UjiOOKMEuWJwAAO+aAPvWiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooASloooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKM0UAFFGaKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAa7hFLMcAdajtrqG6i8yBw6ZxkVR1m8uLZdtvZvOGRssM/L+hrL8Nyzy2Rs/IdYZNw88Z+Ukf570AdRRWF/wjrf9BGf/P41Rmsm07WrFftckquw++ffpQB1dFV7xJJbZ0gfy5CMK3pWSNM1n/oK/wDjtAG9RWD/AGZrP/QU/wDHauaZZ39vKzXl59oUrgDGMH1oA0qht7qK5TfA4kX1Bql4hvBaac4H+tl+RAOp9f0qtY3NtpMAspN3mRx+bKQMhSecE/kB+FAGqLy3LSL5qbouXGfu/WnwTxzxCSFw6N0IrkdJuL1xeSwWYuVnJ3lj9eP1qXQLvUo7Py7W0E0Qc8k4x6igDq8/Sk3r/eX86w/FVlDJavdys/mIoVQDxyf/AK9Jo2hW6QQXTGTzWTJG7jkfT3oA2vtVv/z3i/77FEV1BK5SOaN2HZXBNYFlpumXV9dW4tmAtyAW80nJ+n4UuhWscXiC78gYihXyxznnI/wNAHSUUUUAFFFFADJZI49vmMF3HAycZNNkkSP/AFjKmfU4qhrVvbXaxwTSiKZj+6Oec/4VQvntbe0t7TXC80oG4FM49OTkZoA3Ptdv/wA94v8Avsf405LiKRsJLG59FYGuJ36UdSLMsv2MLwOck/nWnp9zocN5E9skqysdqls4549fegDp81Fa3UN1GXgkDqDgketUNW1Q2Unli3kl3JncvQdaw9F1g2GnMn2VpR5hO4HC84GM4NAHY0Vz+o6reF7JbFI910gYBz69s0QX+pR6vBa3whVZQThB25759qAOgqGe7gt8CaVEJ6BmxWZrhgkeKOXUTasASVX+MH/9VYekxaYby6+2SiSNW/dFifmGTzx+FAHXfaoftP2bzF84jds74qSKZJV3RsGHqDXMy3tm3iSKXzkaAwlGbt0PBqWz+xWuprJY6giwPw0Iyck9AP8A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RQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH//2RM2BgEAAAAArez3zhaDgJLa1M4xLbWbIg==" alt="反馈二维码"></div>
      </div>
    </section>
  </article>
</div>

<footer class="wrap">
  <span><b>ClipTable</b> · 给用户的一封信</span>
  <span>少做重复劳动，多留点时间给自己</span>
</footer>

<script>
(function(){
  var bar=document.getElementById('bar'),toTop=document.getElementById('toTop');
  function onScroll(){
    var h=document.documentElement.scrollHeight-window.innerHeight;
    bar.style.width=(h>0?(window.scrollY/h*100):0)+'%';
    toTop.classList.toggle('on',window.scrollY>500);
  }
  window.addEventListener('scroll',onScroll,{passive:true});onScroll();
  toTop.addEventListener('click',function(){window.scrollTo({top:0,behavior:'smooth'})});
  var themeBtn=document.getElementById('themeBtn');
  themeBtn.addEventListener('click',function(){
    var root=document.documentElement;
    root.dataset.theme=root.dataset.theme==='dark'?'light':'dark';
  });
  if('IntersectionObserver' in window){
    document.documentElement.classList.add('js-anim');
    var io=new IntersectionObserver(function(es){
      es.forEach(function(e){if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target)}})
    },{threshold:.08});
    document.querySelectorAll('section').forEach(function(s){io.observe(s)});
    var links=[].slice.call(document.querySelectorAll('.toc a')),
        secs=links.map(function(a){return document.querySelector(a.getAttribute('href'))});
    var spy=new IntersectionObserver(function(es){
      es.forEach(function(e){
        if(e.isIntersecting){
          links.forEach(function(a,i){a.classList.toggle('active',secs[i]===e.target)});
        }
      })
    },{rootMargin:'-20% 0px -70% 0px'});
    secs.forEach(function(s){if(s)spy.observe(s)});
  }
})();
</script>
<script>
/* ================================================================
   ClipTable 信内可用界面 demo（纯前端示意，不含任何真实功能）
   与 app 共用同源 CSS（已作用域化到 .ctm），标记结构照抄 Vue 组件。
   ================================================================ */
(function () {
  'use strict';

  /* ---------------- 图标（与组件内 SVG 完全一致） ---------------- */
  var ICON = {
    brand:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">' +
      '<rect x="5" y="4.5" width="14" height="16.5" rx="2.5"/><rect x="9" y="2.4" width="6" height="3.4" rx="1.5"/>' +
      '<line x1="12" y1="8.6" x2="12" y2="21"/><line x1="5" y1="13" x2="19" y2="13"/></svg>',
    pin:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" width="16" height="16" aria-hidden="true">' +
      '<circle cx="12" cy="6" r="3.4"/><path d="M9.5 9.7h5"/><path d="M12 9.7V21"/></svg>',
    mini:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" width="16" height="16" aria-hidden="true">' +
      '<path d="M4 9V4h5"/><path d="M20 9V4h-5"/><path d="M4 15v5h5"/><path d="M20 15v5h-5"/></svg>',
    miniOut:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" width="16" height="16" aria-hidden="true">' +
      '<path d="M9 3H3v6"/><path d="M3 3l7 7"/><path d="M15 21h6v-6"/><path d="M21 21l-7-7"/></svg>',
    gear:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">' +
      '<circle cx="12" cy="12" r="3.2"/><path d="M19.4 15a1.7 1.7 0 0 0 .34 1.87l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06A1.7 1.7 0 0 0 15 19.4a1.7 1.7 0 0 0-1 1.55V21a2 2 0 1 1-4 0v-.09A1.7 1.7 0 0 0 9 19.4a1.7 1.7 0 0 0-1.87.34l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06A1.7 1.7 0 0 0 4.6 15a1.7 1.7 0 0 0-1.55-1H3a2 2 0 1 1 0-4h.09A1.7 1.7 0 0 0 4.6 9a1.7 1.7 0 0 0-.34-1.87l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06A1.7 1.7 0 0 0 9 4.6a1.7 1.7 0 0 0 1-1.55V3a2 2 0 1 1 4 0v.09A1.7 1.7 0 0 0 15 4.6a1.7 1.7 0 0 0 1.87-.34l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06A1.7 1.7 0 0 0 19.4 9v.09a1.7 1.7 0 0 0 1.55 1H21a2 2 0 1 1 0 4h-.09a1.7 1.7 0 0 0-1.51 1Z"/></svg>',
    close:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" aria-hidden="true">' +
      '<line x1="6" y1="6" x2="18" y2="18"/><line x1="18" y1="6" x2="6" y2="18"/></svg>',
    chev:
      '<svg class="ui-select-chevron" width="10" height="6" viewBox="0 0 10 6" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M1 1l4 4 4-4"/></svg>',
    emptyDown:
      '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">' +
      '<path d="M12 4v9"/><path d="M8 9.5 12 13l4-3.5"/><path d="M5 19h14"/></svg>',
    padTable:
      '<svg viewBox="0 0 16 16" width="12" height="12" aria-hidden="true">' +
      '<rect x="1.5" y="2.5" width="13" height="11" rx="2" fill="none" stroke="currentColor" stroke-width="1.2"/>' +
      '<path d="M1.5 6.2h13M6 6.2v7.3M10.2 6.2v7.3" fill="none" stroke="currentColor" stroke-width="1.2"/></svg>'
  };

  function esc(s) {
    return String(s == null ? '' : s)
      .replace(/&/g, '&amp;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;');
  }

  /* ---------------- 顶栏 ---------------- */
  function topbar(o) {
    o = o || {};
    var paused = !!o.paused;
    var head =
      '<header class="topbar" data-drag-region>' +
      '<div class="brand"><span class="brand-mark">' +
      ICON.brand +
      '</span><span class="brand-name">ClipTable</span></div>';
    if (o.settings) {
      return head + '<button class="icon-btn icon-close" data-act="backclip" aria-label="关闭面板">' + ICON.close + '</button></header>';
    }
    head +=
      '<div class="' + (paused ? 'status paused' : 'status') + '" data-status><span class="dot"></span>' +
      (paused ? '已暂停' : '监听中') +
      '</div>' +
      '<button class="icon-btn" data-act="pause" aria-label="暂停监听">' + (paused ? '继续' : '暂停') + '</button>' +
      '<button class="icon-btn icon-pin" data-act="pin" aria-label="始终置顶">' + ICON.pin + '</button>' +
      '<button class="icon-btn icon-mini" data-act="mini" aria-label="小窗模式">' + ICON.mini + '</button>' +
      '<button class="icon-btn icon-gear" data-act="gear" aria-label="打开设置">' + ICON.gear + '</button>' +
      '<button class="icon-btn icon-close" data-act="close" aria-label="关闭面板">' + ICON.close + '</button>' +
      '</header>';
    return head;
  }

  /* ---------------- 自绘下拉 ---------------- */
  function select(o) {
    var opts = o.options || [];
    var cur = opts.filter(function (x) { return x.value === o.value; })[0] || opts[0] || { label: '', value: '' };
    var lis = opts
      .map(function (x) {
        return (
          '<li role="option" class="ui-select-option' +
          (x.value === o.value ? ' is-selected' : '') +
          '" data-value="' + esc(x.value) + '">' + esc(x.label) + '</li>'
        );
      })
      .join('');
    return (
      '<div class="ui-select ' + (o.cls || '') + (o.open ? ' is-open' : '') + '">' +
      '<button type="button" class="ui-select-trigger" aria-haspopup="listbox" aria-expanded="' + (o.open ? 'true' : 'false') + '">' +
      '<span class="ui-select-value">' + esc(cur.label) + '</span>' + ICON.chev + '</button>' +
      '<ul class="ui-select-menu" role="listbox">' + lis + '</ul></div>'
    );
  }

  /* ---------------- 形态分段 ---------------- */
  var PANELS = [
    { key: 'table', label: '表格' },
    { key: 'note', label: '记事板' },
    { key: 'image', label: '图片' }
  ];
  function segBar(active) {
    var btns = PANELS.map(function (p) {
      return (
        '<button type="button" role="tab" class="seg-btn' + (p.key === active ? ' active' : '') +
        '" data-panel-tab="' + p.key + '">' + p.label + '</button>'
      );
    }).join('');
    return '<section class="seg-bar"><div class="seg" role="tablist" aria-label="收集形态">' + btns + '</div></section>';
  }

  var MODE_OPTIONS = [
    { label: '每次一行', value: 'row' },
    { label: '每次一格', value: 'cell' },
    { label: '每次一列', value: 'col' },
    { label: '整表粘贴', value: 'table' }
  ];

  function modebar(o) {
    o = o || {};
    return (
      '<section class="modebar">' +
      '<span class="label">进表模式</span>' +
      select({ cls: 'mode-select', value: o.mode || 'table', options: MODE_OPTIONS, open: o.open }) +
      '<span class="calc-toggle"><span class="label">计算</span>' +
      '<button type="button" role="switch" class="ui-switch' + (o.calcOn ? ' is-on' : '') +
      '" data-act="calcswitch" aria-checked="' + (o.calcOn ? 'true' : 'false') + '"><span class="ui-switch-thumb"></span></button>' +
      '</span></section>'
    );
  }

  /* ---------------- 模板栏 ---------------- */
  function tplBarFilling(o) {
    o = o || {};
    {
      return (
        '<section class="tpl-bar">' +
        '<span class="tpl-status' + (o.pausedTpl ? ' paused' : '') + '">' + (o.pausedTpl ? '已暂停' : '填充中') + '</span>' +
        '<span class="tpl-name">' + esc(o.tplName || '日报一') + '</span>' +
        '<button class="tpl-ctl" data-act="tplpause">' + (o.pausedTpl ? '继续' : '暂停') + '</button>' +
        '<button class="tpl-ctl tpl-stop" data-act="tplstop">结束</button>' +
        '<span class="tpl-progress">' + esc(o.progress || '本轮 1/3 · 已填 0 轮') + '</span>' +
        '<span class="tpl-next">下一格 ' + esc(o.next || 'CPM') + '</span>' +
        '<button class="tpl-ctl" data-act="tplmanage">模板</button>' +
        '</section>'
      );
    }
  }

  function tplBar(o) {
    o = o || {};
    var opts = [{ label: o.tplName ? o.tplName + '（按行·3 字段）' : '暂无模板', value: o.tplName ? 't1' : '' }];
    return (
      '<section class="tpl-bar">' +
      select({ cls: 'tpl-select', value: o.tplName ? 't1' : '', options: opts }) +
      '<button class="btn sm" data-act="tplstart"' + (o.tplName ? '' : ' disabled') + '>开始填充</button>' +
      '<button class="btn ghost sm" data-act="tplmanage">管理</button>' +
      '</section>'
    );
  }

  /* ---------------- 表格 ---------------- */
  function cellHTML(v, r, c, o) {
    var cls = 'cell';
    if (v) cls += ' copyable';
    if (o.cursor && o.cursor.r === r && o.cursor.c === c) cls += ' cursor';
    if (o.tplNext && o.tplNext.r === r && o.tplNext.c === c) cls += ' tpl-next';
    var inner = v
      ? '<span>' + esc(v) + '</span>'
      : '<span class="ph">—</span>';
    if (o.cursor && o.cursor.r === r && o.cursor.c === c) inner += '<span class="cur-tag">下一个</span>';
    return '<td class="' + cls + '" data-cell="' + r + ':' + c + '">' + inner + '</td>';
  }

  function gridHTML(o) {
    var rows = o.rows || [];
    var cols = o.cols || 3;
    var html = '';
    if (!rows.length) {
      html +=
        '<div class="empty">' +
        '<span class="empty-icon">' + ICON.emptyDown + '</span>' +
        '<span class="empty-text">' +
        (o.mode === 'table' || !o.mode
          ? '复制整张表格（Excel / 网页），行列原样粘贴进来'
          : '暂无数据，复制内容会自动收集到这里') +
        '</span></div>';
      return '<div class="scroll-area tablewrap" data-tablewrap>' + html + '</div>';
    }
    var head =
      '<thead><tr><th class="ck" aria-label="选择"><span class="ck-ph">#</span></th><th class="idx">行</th>';
    for (var c = 0; c < cols; c++) {
      head +=
        '<th><span class="col-head"><span>列' + (c + 1) + '</span>' +
        '<button class="col-del" title="删除此列" aria-label="删除此列" data-col="' + c + '">×</button></span></th>';
    }
    head += '<th class="act"></th></tr></thead>';
    var body = '<tbody>';
    rows.forEach(function (row, r) {
      body += '<tr' + (o.nextRow === r ? ' class="row next"' : '') + '>' +
        '<td class="ck"><input type="checkbox" class="ui-checkbox" aria-label="选择第 ' + (r + 1) + ' 行"></td>' +
        '<td class="idx">' + (r + 1) + '</td>';
      for (var c2 = 0; c2 < cols; c2++) body += cellHTML(row[c2] || '', r, c2, o);
      body += '<td class="row-act"><button class="row-del" title="删除此行" aria-label="删除此行">×</button></td></tr>';
    });
    body += '</tbody>';
    html = '<table class="grid">' + head + body + '</table>';
    return '<div class="scroll-area tablewrap" data-tablewrap>' + html + '</div>';
  }

  /* ---------------- 底部操作区 ---------------- */
  function footer(panel, o) {
    o = o || {};
    var main = '',
      tools = '',
      status = '';
    if (panel === 'note') {
      main =
        '<div class="actions-main"><button class="btn primary" data-act="copynote">复制全部</button>' +
        '<button class="btn danger" data-act="clearnote">清空</button></div>';
      status = '<span class="count" data-count>0 段</span>';
    } else if (panel === 'image') {
      main = '<div class="actions-main"><button class="btn danger" data-act="clearimg">清空图片</button></div>';
      status = '<span class="count" data-count>共 2 张 · 1.8 MB</span>';
    } else {
      main =
        '<div class="actions-main"><button class="btn primary" data-act="copytable">复制为表格</button>' +
        '<button class="btn ghost" data-act="copycsv">复制为 CSV</button></div>';
      tools =
        '<div class="actions-tools"><button class="btn" data-act="undo">撤销</button>' +
        '<button class="btn" data-act="dedupe">去重</button>' +
        '<button class="btn" data-act="delrow">删除行</button>' +
        '<button class="btn danger" data-act="clear">清空</button></div>';
      status =
        '<span class="count" data-count>' + (o.rows ? o.rows.length : 0) + ' 行 · ' + Math.max(1, o.cols || 1) + ' 列</span>';
    }
    return (
      '<footer class="actions">' + main + tools +
      '<div class="statusbar">' + status + '</div></footer>'
    );
  }

  /* ---------------- 记事板 ---------------- */
  function notepadHTML(text) {
    return (
      '<div class="notepad-wrap"><div class="notepad" data-notepad>' +
      '<div class="notepad-head"><span class="notepad-label">记事板</span></div>' +
      '<textarea class="notepad-area" spellcheck="false" placeholder="复制任意内容会出现在这里；单击可编辑" aria-label="记事板">' +
      esc(text || '') +
      '</textarea></div>' +
      '<div class="notepad-foot"><span class="notepad-count" data-note-count>0 字 · 上限 200,000</span></div></div>'
    );
  }

  /* ---------------- 图片板 ---------------- */
  function thumb(a, b) {
    var svg =
      '<svg xmlns="http://www.w3.org/2000/svg" width="120" height="80">' +
      '<defs><linearGradient id="g" x1="0" y1="0" x2="1" y2="1">' +
      '<stop offset="0" stop-color="' + a + '"/><stop offset="1" stop-color="' + b + '"/></linearGradient></defs>' +
      '<rect width="120" height="80" fill="url(#g)"/>' +
      '<rect x="10" y="52" width="44" height="4" rx="2" fill="rgba(255,255,255,.5)"/>' +
      '<rect x="10" y="62" width="72" height="4" rx="2" fill="rgba(255,255,255,.28)"/></svg>';
    return 'data:image/svg+xml;charset=utf-8,' + encodeURIComponent(svg);
  }
  function imageBoardHTML() {
    var cards = [
      { src: thumb('#3b4a6b', '#8fb0d8'), cap: '1920×1080 · 842 KB' },
      { src: thumb('#4a3b5b', '#c79fd8'), cap: '1280×720 · 411 KB' }
    ]
      .map(function (c) {
        return (
          '<div class="img-card" title="单击复制 · 双击看大图">' +
          '<img class="img-thumb" src="' + c.src + '" alt="" draggable="false">' +
          '<button class="img-del" title="删除这张" aria-label="删除这张图片">×</button>' +
          '<span class="img-meta">' + c.cap + '</span></div>'
        );
      })
      .join('');
    return '<div class="img-board"><div class="img-grid">' + cards + '</div></div>';
  }

  /* ---------------- 模板管理（列表 / 编辑） ---------------- */
  function tplViewHTML(mode) {
    if (mode === 'edit') {
      var fields = ['CPM', 'CTR', 'GMV'];
      var hcells = fields
        .map(function (f) {
          return '<td class="tpl-hcell"><input class="tpl-hinput" value="' + f + '" aria-label="字段"></td>';
        })
        .join('');
      var g1 = fields.map(function () { return '<td class="tpl-gcell"></td>'; }).join('');
      var g2 = g1;
      return (
        '<section class="tpl-view" data-tplview="edit">' +
        '<header class="tpl-head"><button class="tpl-back" data-act="tplback">返回</button>' +
        '<span class="tpl-head-title">编辑模板</span>' +
        '<button class="btn sm primary tpl-head-save" data-act="tplsave">保存</button></header>' +
        '<label class="tpl-row"><span class="tpl-row-label">名称</span>' +
        '<input class="ui-input tpl-name-input" value="日报一" aria-label="模板名称"></label>' +
        '<div class="tpl-row"><span class="tpl-row-label">方向</span>' +
        '<div class="seg tpl-seg"><button type="button" class="seg-btn active">按行</button>' +
        '<button type="button" class="seg-btn">按列</button></div></div>' +
        '<div class="tpl-fields-head"><span>字段（顺序即落格顺序）</span>' +
        '<span class="tpl-fields-count">3/50</span>' +
        '<button class="tpl-addbtn" title="添加字段" aria-label="添加字段" data-act="tpladd">＋</button></div>' +
        '<p class="tpl-note tpl-rule">字段写在首行，数据逐行往下；填满一轮自动换行继续。</p>' +
        '<div class="tpl-grid-wrap"><table class="tpl-grid dir-row"><tbody>' +
        '<tr><td class="tpl-gutter">#</td>' + hcells + '</tr>' +
        '<tr class="tpl-grow"><td class="tpl-gutter">1</td>' + g1 + '</tr>' +
        '<tr class="tpl-grow"><td class="tpl-gutter">2</td>' + g2 + '</tr>' +
        '</tbody></table></div>' +
        '<p class="tpl-note">⌥←/→ 调序 · Enter 追加字段 · 清空字段名即删除该字段</p>' +
        '</section>'
      );
    }
    return (
      '<section class="tpl-view" data-tplview="list">' +
      '<header class="tpl-head"><button class="tpl-back" data-act="tplback">返回</button>' +
      '<span class="tpl-head-title">模板管理</span><span class="tpl-head-count">1/20</span></header>' +
      '<ul class="tpl-list"><li class="tpl-item">' +
      '<button class="tpl-dot on" title="当前模板"></button>' +
      '<span class="tpl-item-name">日报一</span>' +
      '<span class="tpl-item-meta">按行 · 3 字段 · 已存文件</span>' +
      '<span class="tpl-item-ops"><button class="tpl-op" data-act="tpledit">编辑</button>' +
      '<button class="tpl-op">导出</button>' +
      '<button class="tpl-op danger">删除</button></span></li></ul>' +
      '<div class="tpl-list-actions"><button class="btn sm primary" data-act="tplnew">新建模板</button>' +
      '<button class="btn sm ghost">导入模板</button></div>' +
      '<p class="tpl-note">模板保存在 下载\\ClipTable，每个模板一个 Excel 文件（.xlsx），双击就能用 Excel / Numbers 打开核对。</p>' +
      '</section>'
    );
  }

  /* ---------------- 设置页 ---------------- */
  var PRESETS = ['#9aa5ab', '#5aa882', '#5a9de8', '#8a7be0', '#e08a5a', '#e05a8a', '#d7b95a', '#4ac0c7'];

  function settingsHTML(o) {
    o = o || {};
    var swatches = PRESETS.map(function (c) {
      return (
        '<button type="button" class="swatch' + (c === '#9aa5ab' ? ' active' : '') +
        '" style="background:' + c + '" data-accent="' + c + '" aria-label="切换主题色 ' + c + '"></button>'
      );
    }).join('');

    return (
      '<section class="settings-view" data-settings>' +
      '<button class="btn ghost sm back" data-act="backclip">← 返回剪贴板</button>' +

      '<h3 class="sec-title" data-sec="ui">UI 界面设置</h3>' +
      '<div class="ui-unit">' +
      '<div class="ui-row"><span class="ui-label">窗口不透明度</span>' +
      '<div class="ui-ctl"><input type="range" class="ui-slider" min="40" max="100" step="2" value="100" data-slider="opacity" aria-label="窗口不透明度">' +
      '<span class="ui-val" data-val="opacity">100%</span></div></div>' +
      '<div class="ui-row"><span class="ui-label">主题色</span>' +
      '<div class="ui-ctl theme-row">' + swatches +
      '<input type="color" class="color-picker" value="#9aa5ab" aria-label="自定义主题色" title="自定义颜色"></div></div>' +
      '<div class="ui-row"><span class="ui-label">按钮反光</span>' +
      '<div class="ui-ctl"><input type="range" class="ui-slider" min="0" max="150" step="5" value="55" data-slider="glass" aria-label="按钮反光强度">' +
      '<span class="ui-val" data-val="glass">55%</span>' +
      '<span class="ui-hint" data-hint="glass">克制</span></div></div>' +
      '<p class="ui-note">反光只作用于按钮的边缘切线与液面光带，底板、表格、面板保持原样。拖动即时预览，停手后记住。</p>' +
      '</div>' +

      '<h3 class="sec-title" data-sec="collect">收集</h3>' +
      '<div class="collect-row"><div class="collect-text">' +
      '<span class="collect-label">重复内容也收录</span>' +
      '<span class="collect-desc">连续复制相同内容时，每次都加入表格（适合反复收集同一个数字）</span></div>' +
      '<button type="button" role="switch" class="ui-switch" data-act="dup" aria-checked="false"><span class="ui-switch-thumb"></span></button></div>' +
      '<div class="collect-row"><div class="collect-text">' +
      '<span class="collect-label">点选即贴（直接粘贴）</span>' +
      '<span class="collect-desc">在 Excel 等应用里点好光标，唤出剪贴板后单击数据即直接粘贴到该位置；关闭则单击只复制、不自动粘贴</span></div>' +
      '<button type="button" role="switch" class="ui-switch is-on" data-act="direct" aria-checked="true"><span class="ui-switch-thumb"></span></button></div>' +

      '<h3 class="sec-title" data-sec="dir">文件保存位置</h3>' +
      '<div class="dir-row"><span class="dir-path" title="C:\\Users\\you\\Downloads\\ClipTable"> Downloads\\ClipTable</span>' +
      '<div class="dir-ops"><button class="btn sm">更改…</button>' +
      '<button class="btn sm ghost">恢复默认</button><button class="btn sm ghost">打开</button></div></div>' +
      '<p class="dir-note">模板等文件保存到这里。默认在「下载」文件夹下的 ClipTable 文件夹；换目录后新保存的文件写进新目录，旧文件不搬。</p>' +

      '<h3 class="sec-title" data-sec="history">历史记录</h3>' +
      '<div class="scroll-area history-list">' +
      (o.emptyHist
        ? '<div class="empty-hist">暂无历史</div>'
        : '<div class="history-item clickable" role="button"><span class="hist-time">11-07 20:12</span>' +
          '<span class="hist-tag">表格</span><span class="hist-sum">5 行 × 5 列</span>' +
          '<span class="hist-content">都市系列 88071 都市系列——UR绵羊毛皮休闲外套 …</span></div>' +
          '<div class="history-item clickable" role="button"><span class="hist-time">11-07 20:09</span>' +
          '<span class="hist-tag">文本</span><span class="hist-sum">单值</span>' +
          '<span class="hist-content">Jasean hh 23000 5787</span></div>') +
      '</div>' +

      '<h3 class="sec-title" data-sec="calchist">计算记录<span class="sec-note">仅本次运行，退出后清空</span></h3>' +
      '<div class="scroll-area calc-hist-list">' +
      '<div class="calc-hist-item" role="button"><span class="calc-hist-time">11-07 18:09</span>' +
      '<span class="calc-hist-expr">1024+1</span><span class="calc-hist-res">= 1025</span></div>' +
      '<div class="calc-hist-item" role="button"><span class="calc-hist-time">11-07 18:02</span>' +
      '<span class="calc-hist-expr">23000*0.3</span><span class="calc-hist-res">= 6900</span></div></div>' +
      '<button class="btn danger sm clear-hist" data-act="clearhist">清空计算记录</button>' +

      '<h3 class="sec-title" data-sec="hotkey">全局快捷键</h3>' +
      '<p class="hotkey-note">点击按键框后按下含修饰键的组合键即可改键；「恢复默认」还原初始值，「清除」后该组不再生效。三组不能重复。</p>' +
      '<div class="hotkey-group"><span class="hotkey-label">唤出 / 隐藏面板</span>' +
      '<div class="hotkey-row"><span class="hotkey-capture" tabindex="0" role="button">Shift+Z</span>' +
      '<div class="hotkey-actions"><button class="btn ghost sm">恢复默认</button><button class="btn ghost sm">清除</button></div></div></div>' +
      '</section>'
    );
  }

  /* ---------------- 一个小窗 ---------------- */
  function miniWindow(o) {
    o = o || {};
    return (
      '<div class="app mini">' +
      '<div class="mini-bar" data-drag-region>' +
      '<span class="mini-brand">ClipTable</span>' +
      '<span class="mini-count">' + (o.rows ? o.rows.length : 0) + ' 行 · ' + (o.cols || 3) + ' 列</span>' +
      '<button class="icon-btn icon-pin' + (o.pinned ? ' active' : '') + '" data-act="pin">' + ICON.pin + '</button>' +
      '<button class="icon-btn" data-act="miniout">' + ICON.miniOut + '</button>' +
      '<button class="icon-btn icon-close" data-act="close">' + ICON.close + '</button>' +
      '</div>' +
      '<div class="mini-table">' + gridHTML(o) + '</div>' +
      '</div>'
    );
  }

  /* ---------------- 计算台（420×260） ---------------- */
  function calcDesk(o) {
    o = o || {};
    var expr = o.expr == null ? '1024+1' : o.expr;
    var padTable = o.padTable
      ? '<div class="pad-grid"><table><tbody>' +
        '<tr class="pad-first"><td><input value="列 1" placeholder="列 1"></td><td><input value="列 2" placeholder="列 2"></td>' +
        '<td><input value="列 3" placeholder="列 3"></td></tr>' +
        '<tr><td><input value="1025"></td><td><input value=""></td><td><input value=""></td></tr>' +
        '<tr><td><input value=""></td><td><input value=""></td><td><input value=""></td></tr>' +
        '</tbody></table></div>'
      : '<textarea class="pad-text" spellcheck="false" placeholder="记点东西 —— 算完的数只进剪贴板，要不要记下来由你决定">' +
        esc(o.padText || '') + '</textarea>';
    return (
      '<div class="app calc-only">' +
      '<div class="calc-desk">' +
      '<section class="calc-bar" aria-label="计算栏" data-drag-region>' +
      '<div class="calc-head"><span class="calc-title">计算</span>' +
      '<div class="calc-head-right"><span class="calc-keys">Enter 复制并继续 · Esc 关闭</span>' +
      '<button class="calc-close" type="button" title="关闭计算器">×</button></div></div>' +
      '<input class="calc-input" type="text" value="' + esc(expr) + '" spellcheck="false" aria-label="算式" data-calc-input>' +
      '<div class="calc-foot"><span class="calc-preview state-ok" data-calc-preview>= 1025</span></div>' +
      '</section>' +
      '<section class="calc-pad" aria-label="速记板">' +
      '<div class="pad-head" data-drag-region>' +
      '<button type="button" class="pad-btn' + (o.padTable ? ' on' : '') + '" data-act="padtoggle">' + ICON.padTable + '<span>表格</span></button>' +
      '<span class="pad-title">' + (o.padTable ? '速记表' : '记事板') + '</span>' +
      (o.padTable
        ? '<div class="pad-tools"><button type="button" class="pad-mini">＋行</button>' +
          '<button type="button" class="pad-mini">＋列</button>' +
          '<button type="button" class="pad-mini">复制</button>' +
          '<button type="button" class="pad-mini">清空</button></div>'
        : '') +
      '</div>' + padTable +
      '</section></div></div>'
    );
  }

  /* ---------------- 主窗口 ---------------- */
  function mainWindow(o) {
    o = o || {};
    var panel = o.panel || 'table';
    return (
      topbar(o) +
      '<section class="clip-panel">' +
      segBar(panel) +
      '<div class="mp' + (panel === 'table' ? ' on' : '') + '" data-mp="table">' +
      modebar(o) + tplBar(o) +
      '<div class="mp-tbl">' + gridHTML(o) + '</div>' +
      footer('table', o) +
      '</div>' +
      '<div class="mp' + (panel === 'note' ? ' on' : '') + '" data-mp="note">' +
      notepadHTML(o.note) + footer('note', o) +
      '</div>' +
      '<div class="mp' + (panel === 'image' ? ' on' : '') + '" data-mp="image">' +
      imageBoardHTML() + footer('image', o) +
      '</div>' +
      '</section>' +
      settingsHTML(o) +
      '<div class="toast" data-toast></div>' +
      '<div class="modal-overlay" data-modal hidden><div class="modal" role="alertdialog">' +
      '<div class="modal-title">清空临时表格</div>' +
      '<p class="modal-desc">此操作不可撤销（已保存文件不受影响）。确定清空？</p>' +
      '<div class="modal-actions"><button class="btn ghost sm" data-modal-cancel>取消</button>' +
      '<button class="btn danger sm" data-modal-ok>清空</button></div></div></div>'
    );
  }

  /* ================= 交互 ================= */
  function toast(ctm, msg) {
    var t = ctm.querySelector('[data-toast]');
    if (!t) return;
    t.textContent = msg;
    clearTimeout(t._timer);
    t._timer = setTimeout(function () { t.textContent = ''; }, 1600);
  }

  function refreshCount(ctm) {
    var wrap = ctm.querySelector('[data-mp="table"] [data-tablewrap]');
    var label = ctm.querySelector('[data-mp="table"] [data-count]');
    if (!wrap || !label) return;
    var tb = wrap.querySelector('tbody');
    if (!tb) { label.textContent = '0 行 · 0 列'; return; }
    var rows = tb.querySelectorAll('tr').length;
    var cols = wrap.querySelectorAll('thead th:not(.ck):not(.idx):not(.act)').length;
    label.textContent = rows + ' 行 · ' + cols + ' 列';
  }

  function setPanel(ctm, key) {
    ctm.querySelectorAll('[data-panel-tab]').forEach(function (b) {
      b.classList.toggle('active', b.getAttribute('data-panel-tab') === key);
    });
    ctm.querySelectorAll('[data-mp]').forEach(function (p) {
      p.classList.toggle('on', p.getAttribute('data-mp') === key);
    });
  }

  function noteCount(ctm) {
    var ta = ctm.querySelector('.notepad-area');
    var out = ctm.querySelector('[data-note-count]');
    var seg = ctm.querySelector('[data-mp="note"] [data-count]');
    if (!ta) return;
    var n = ta.value.length;
    if (out) out.textContent = n.toLocaleString('en-US') + ' 字 · 上限 200,000';
    if (seg) seg.textContent = (ta.value.trim() ? ta.value.trim().split(/\n+/).length : 0) + ' 段';
  }

  function calcPreview(input) {
    var wrap = input.closest('.calc-bar');
    var out = wrap.querySelector('[data-calc-preview]');
    var raw = input.value.trim();
    if (!raw) {
      out.className = 'calc-preview state-empty';
      out.textContent = '输入算式，回车复制结果';
      return;
    }
    var safe = raw.replace(/[^0-9+\-*/().%\s]/g, '');
    var val;
    try {
      val = Function('"use strict";return (' + safe + ')')();
    } catch (e) {
      val = null;
    }
    if (typeof val !== 'number' || !isFinite(val)) {
      out.className = 'calc-preview state-err';
      out.textContent = '算式无法计算';
      return;
    }
    var txt = String(Math.round(val * 1e10) / 1e10);
    out.className = 'calc-preview state-ok';
    out.textContent = '= ' + txt;
  }

  /* 主题色：与 core/table.ts 的 glassRgb / accentVars 同一算法 */
  function hexRgb(hex) {
    var m = /^#?([0-9a-f]{6})$/i.exec(hex || '');
    if (!m) return null;
    var n = parseInt(m[1], 16);
    return { r: (n >> 16) & 255, g: (n >> 8) & 255, b: n & 255 };
  }
  function applyAccent(ctm, hex) {
    var c = hexRgb(hex);
    if (!c) return;
    var cl = function (v) { return Math.max(0, Math.min(255, Math.round(v))); };
    var st = ctm.style;
    st.setProperty('--accent', hex.toLowerCase());
    st.setProperty('--accent-strong', '#' + [cl(c.r * 0.82), cl(c.g * 0.82), cl(c.b * 0.82)]
      .map(function (v) { return v.toString(16).padStart(2, '0'); }).join(''));
    st.setProperty('--accent-soft', 'rgba(' + c.r + ', ' + c.g + ', ' + c.b + ', 0.28)');
    st.setProperty('--accent-sel', 'rgba(' + c.r + ', ' + c.g + ', ' + c.b + ', 0.5)');
    st.setProperty('--glass-tint-rgb',
      [cl(13 + c.r * 0.02), cl(14 + c.g * 0.02), cl(16 + c.b * 0.02)].join(', '));
    st.setProperty('--glass-dark-rgb',
      [cl(7 + c.r * 0.01), cl(8 + c.g * 0.01), cl(9 + c.b * 0.01)].join(', '));
  }

  /* 不透明度：与 App.vue 的 glass 映射一致（40~100% → alpha 0.05~1） */
  function applyOpacity(ctm, pct) {
    var t = Math.min(1, Math.max(0, (pct / 100 - 0.4) / 0.6));
    var e = Math.pow(t, 1.4);
    ctm.style.setProperty('--glass-tint-alpha', (0.05 + 0.95 * e).toFixed(4));
    ctm.style.setProperty('--frost-strength', (t * t).toFixed(4));
    var dark = (0.08 + 0.28 * e).toFixed(4);
    var rgb = (getComputedStyle(ctm).getPropertyValue('--glass-dark-rgb') || '9, 10, 11').trim();
    ctm.style.setProperty('--glass-dark', 'rgba(' + rgb + ', ' + dark + ')');
  }

  function bind(ctm) {
    ctm.addEventListener('click', function (e) {
      var t = e.target;

      /* 下拉 */
      var opt = t.closest('.ui-select-option');
      if (opt) {
        var sel = opt.closest('.ui-select');
        sel.querySelector('.ui-select-value').textContent = opt.textContent;
        sel.querySelectorAll('.ui-select-option').forEach(function (o) {
          o.classList.toggle('is-selected', o === opt);
        });
        sel.classList.remove('is-open');
        return;
      }
      var trig = t.closest('.ui-select-trigger');
      if (trig) {
        var root = trig.closest('.ui-select');
        var was = root.classList.contains('is-open');
        ctm.querySelectorAll('.ui-select.is-open').forEach(function (s) { s.classList.remove('is-open'); });
        root.classList.toggle('is-open', !was);
        return;
      }
      if (!t.closest('.ui-select')) {
        ctm.querySelectorAll('.ui-select.is-open').forEach(function (s) { s.classList.remove('is-open'); });
      }

      /* 形态切换 */
      var tab = t.closest('[data-panel-tab]');
      if (tab) { setPanel(ctm, tab.getAttribute('data-panel-tab')); return; }

      /* 方向分段（模板编辑） */
      var segb = t.closest('.tpl-seg .seg-btn');
      if (segb) {
        segb.parentNode.querySelectorAll('.seg-btn').forEach(function (b) { b.classList.remove('active'); });
        segb.classList.add('active');
        return;
      }

      /* 顶栏 */
      if (t.closest('[data-act="pause"]')) {
        var btn = t.closest('[data-act="pause"]');
        var status = ctm.querySelector('[data-status]');
        var paused = status && status.classList.contains('paused');
        if (status) {
          status.classList.toggle('paused', !paused);
          status.innerHTML = '<span class="dot"></span>' + (!paused ? '已暂停' : '监听中');
        }
        btn.textContent = !paused ? '继续' : '暂停';
        toast(ctm, !paused ? '已暂停收集（示意）' : '继续监听（示意）');
        return;
      }
      if (t.closest('[data-act="pin"]')) {
        t.closest('[data-act="pin"]').classList.toggle('active');
        return;
      }
      if (t.closest('[data-act="gear"]')) {
        /* 对应 store.setView('settings')：整页换成设置页，顶栏只留品牌名与关闭 */
        var cp = ctm.querySelector('.clip-panel');
        var sv = ctm.querySelector('[data-settings]');
        if (!sv) return;
        cp.style.display = 'none';
        sv.style.display = 'flex';
        sv.scrollTop = 0;
        var tb0 = ctm.querySelector('.topbar');
        tb0.querySelectorAll('.status, [data-act="pause"], .icon-pin, .icon-mini, .icon-gear')
          .forEach(function (n) { n.remove(); });
        return;
      }
      if (t.closest('[data-act="backclip"]')) {
        var cp2 = ctm.querySelector('.clip-panel');
        var sv2 = ctm.querySelector('[data-settings]');
        if (cp2 && sv2) {
          sv2.style.display = 'none'; cp2.style.display = 'flex';
          var tb = ctm.querySelector('.topbar');
          tb.outerHTML = topbar({});
        }
        return;
      }
      if (t.closest('[data-act="close"]') || t.closest('[data-act="mini"]') || t.closest('[data-act="miniout"]')) {
        toast(ctm, t.closest('[data-act="mini"]') || t.closest('[data-act="miniout"]') ? '小窗模式（示意）' : '已隐藏到托盘（示意）');
        return;
      }

      /* 开关 */
      if (t.closest('.ui-switch')) {
        var sw = t.closest('.ui-switch');
        sw.classList.toggle('is-on');
        sw.setAttribute('aria-checked', sw.classList.contains('is-on') ? 'true' : 'false');
        return;
      }

      /* 表格：单元格点击 = 复制反馈；双击 = 编辑 */
      var cell = t.closest('.cell');
      if (cell) {
        ctm.querySelectorAll('.cell.copied').forEach(function (c) { c.classList.remove('copied'); });
        cell.classList.add('copied');
        setTimeout(function () { cell.classList.remove('copied'); }, 600);
        toast(ctm, '已复制该单元格（示意）');
        return;
      }
      if (t.closest('.row-del')) {
        var tr = t.closest('tr');
        if (tr) { tr.remove(); refreshCount(ctm); toast(ctm, '已删除该行（示意）'); }
        return;
      }
      if (t.closest('.col-del')) {
        var ci = Number(t.closest('.col-del').getAttribute('data-col'));
        ctm.querySelectorAll('[data-cell]').forEach(function (c) {
          var rc = c.getAttribute('data-cell').split(':');
          if (Number(rc[1]) === ci) c.remove();
        });
        toast(ctm, '已删除该列（示意）');
        return;
      }
      if (t.closest('.img-del')) {
        var card = t.closest('.img-card');
        if (card) card.remove();
        toast(ctm, '已删除这张图（示意）');
        return;
      }

      /* 模板面板 */
      if (t.closest('[data-act="tplmanage"]')) {
        var mp = ctm.querySelector('[data-mp="table"]');
        if (!mp) return;
        mp.querySelector('.mp-tbl').style.display = 'none';
        mp.querySelector('.tpl-bar').style.display = 'none';
        mp.querySelector('footer').style.display = 'none';
        if (!mp.querySelector('[data-tplview="list"]')) {
          var d0 = document.createElement('div');
          d0.innerHTML = tplViewHTML('list');
          mp.appendChild(d0.firstChild);
        }
        mp.querySelector('[data-tplview="list"]').classList.add('on');
        return;
      }
      if (t.closest('[data-act="tplback"]')) {
        var mp2 = ctm.querySelector('[data-mp="table"]');
        var ev0 = t.closest('[data-tplview="edit"]');
        if (ev0) ev0.remove();
        var lv = mp2 && mp2.querySelector('[data-tplview="list"]');
        if (lv) { lv.classList.remove('on'); lv.remove(); }
        if (mp2) {
          mp2.querySelector('.mp-tbl').style.display = '';
          mp2.querySelector('.tpl-bar').style.display = '';
          mp2.querySelector('footer').style.display = '';
        }
        return;
      }
      if (t.closest('[data-act="tpledit"]') || t.closest('[data-act="tplnew"]')) {
        var host2 = ctm.querySelector('[data-mp="table"]');
        var list2 = host2.querySelector('[data-tplview="list"]');
        if (list2) {
          list2.classList.remove('on');
          var div = document.createElement('div');
          div.innerHTML = tplViewHTML('edit');
          list2.insertAdjacentElement('afterend', div.firstChild);
        }
        return;
      }
      if (t.closest('[data-act="tplsave"]')) {
        toast(ctm, '模板已保存（示意）');
        var ev = ctm.querySelector('[data-tplview="edit"]');
        if (ev) ev.remove();
        var l2 = ctm.querySelector('[data-tplview="list"]');
        if (l2) l2.classList.add('on');
        return;
      }
      if (t.closest('[data-act="tplstart"]')) {
        var bar = t.closest('.tpl-bar');
        if (bar) {
          bar.outerHTML = tplBarFilling({ tplName: '日报一' });
          toast(ctm, '开始填充：以后每次复制都会落进下一格（示意）');
        }
        return;
      }
      if (t.closest('[data-act="tplpause"]')) {
        var pb = t.closest('.tpl-bar');
        var st = pb.querySelector('.tpl-status');
        var pausedNow = st.classList.toggle('paused');
        st.textContent = pausedNow ? '已暂停' : '填充中';
        pb.querySelector('[data-act="tplpause"]').textContent = pausedNow ? '继续' : '暂停';
        return;
      }
      if (t.closest('[data-act="tplstop"]')) {
        var sb = t.closest('.tpl-bar');
        if (sb) sb.outerHTML = tplBar({ tplName: '日报一' });
        toast(ctm, '已结束填充，表格数据保留（示意）');
        return;
      }
      if (t.closest('[data-act="tpladd"]')) { toast(ctm, '已追加一个字段（示意）'); return; }

      /* 计算台 */
      if (t.closest('[data-act="padtoggle"]')) {
        toast(ctm, '记事板 / 速记表切换（示意）');
        return;
      }

      /* 主题色 */
      var swatch = t.closest('[data-accent]');
      if (swatch) {
        applyAccent(ctm, swatch.getAttribute('data-accent'));
        ctm.querySelectorAll('[data-accent]').forEach(function (b) {
          b.classList.toggle('active', b === swatch);
        });
        return;
      }

      /* 底部按钮 */
      if (t.closest('[data-act="copytable"]')) { toast(ctm, '已复制整表，可直接粘贴（示意）'); return; }
      if (t.closest('[data-act="copycsv"]')) { toast(ctm, '已复制为 CSV（示意）'); return; }
      if (t.closest('[data-act="copynote"]')) { toast(ctm, '记事板内容已复制（示意）'); return; }
      if (t.closest('[data-act="undo"]')) { toast(ctm, '已撤销上一步（示意）'); return; }
      if (t.closest('[data-act="dedupe"]')) { toast(ctm, '已按行去重（示意）'); return; }
      if (t.closest('[data-act="delrow"]')) { toast(ctm, '选中行已删除（示意）'); return; }
      if (t.closest('[data-act="clearhist"]')) { toast(ctm, '计算记录已清空（示意）'); return; }
      if (t.closest('[data-act="clear"]')) {
        var mo = ctm.querySelector('[data-modal]');
        if (mo) mo.hidden = false;
        return;
      }
      if (t.closest('[data-modal-cancel]')) {
        ctm.querySelector('[data-modal]').hidden = true;
        return;
      }
      if (t.closest('[data-modal-ok]')) {
        var m = ctm.querySelector('[data-modal]');
        if (m) m.hidden = true;
        var w = ctm.querySelector('[data-mp="table"] [data-tablewrap]');
        if (w) {
          w.innerHTML =
            '<div class="empty"><span class="empty-icon">' + ICON.emptyDown +
            '</span><span class="empty-text">复制整张表格（Excel / 网页），行列原样粘贴进来</span></div>';
        }
        refreshCount(ctm);
        toast(ctm, '已清空（示意）');
        return;
      }
      if (t.closest('.history-item') || t.closest('.calc-hist-item')) {
        toast(ctm, '已复制这条记录（示意）');
        return;
      }
      if (t.closest('.hotkey-capture')) {
        var hk = t.closest('.hotkey-capture');
        hk.classList.toggle('capturing');
        hk.textContent = hk.classList.contains('capturing') ? '请按键…' : 'Shift+Z';
        return;
      }
    });

    /* 滑块 */
    ctm.addEventListener('input', function (e) {
      var t = e.target;
      if (t.matches('[data-slider="opacity"]')) {
        ctm.querySelector('[data-val="opacity"]').textContent = t.value + '%';
        applyOpacity(ctm, Number(t.value));
        return;
      }
      if (t.matches('[data-slider="glass"]')) {
        ctm.querySelector('[data-val="glass"]').textContent = t.value + '%';
        ctm.style.setProperty('--lq-k', String(Number(t.value) / 100));
        var hint = ctm.querySelector('[data-hint="glass"]');
        var k = Number(t.value) / 100;
        if (hint) hint.textContent = k < 0.4 ? '几乎无' : k < 0.8 ? '克制' : k < 1.2 ? '标准' : '明显';
        return;
      }
      if (t.matches('[data-calc-input]')) { calcPreview(t); return; }
      if (t.matches('.notepad-area')) { noteCount(ctm); return; }
    });

    /* 计算栏回车 */
    ctm.addEventListener('keydown', function (e) {
      if (e.target.matches('[data-calc-input]') && e.key === 'Enter') {
        e.preventDefault();
        var out = ctm.querySelector('[data-calc-preview]');
        toast(ctm, '结果已在剪贴板：' + String(out.textContent).replace('= ', '') + '（示意）');
        e.target.select();
      }
      if (e.target.matches('.calc-input') && e.key === 'Escape') {
        toast(ctm, 'Esc 收起计算台（示意）');
      }
    });

    noteCount(ctm);
    var ci = ctm.querySelector('[data-calc-input]');
    if (ci) calcPreview(ci);
  }

  /* ---------------- 自适应缩放：窗口按容器宽度等比缩，1:1 展示 ---------------- */
  var fits = [];
  function layoutAll() {
    /* 可见宽度取自 .demo（并排容器的真实宽度），再按格子数均分；
       不能取 .demo-cell —— 单张时它是 shrink-to-fit，宽度由 host 反推，会绕成死循环。 */
    /* 散装窗口（首屏那两张浮窗）：可用宽度就是外壳的宽度 */
    document.querySelectorAll('.mock').forEach(function (host) {
      if (host.closest('.demo')) return;
      var nw = Number(host.style.getPropertyValue('--nw')) || 384;
      var nh = Number(host.style.getPropertyValue('--nh')) || 580;
      var shell = host.parentElement;
      var avail = shell ? shell.clientWidth : nw;
      var sc = avail > 0 ? Math.min(1, avail / nw) : 1;
      var stage0 = host.querySelector('.mock-stage');
      if (stage0) stage0.style.transform = 'scale(' + sc + ')';
      host.style.width = Math.round(nw * sc) + 'px';
      host.style.height = Math.round(nh * sc) + 'px';
    });

    document.querySelectorAll('.demo').forEach(function (box) {
      var cells = box.querySelectorAll('.demo-cell');
      if (!cells.length) return;
      var cs = getComputedStyle(box);
      var inner =
        box.clientWidth -
        parseFloat(cs.paddingLeft || 0) -
        parseFloat(cs.paddingRight || 0);
      var col = cs.flexDirection.indexOf('column') === 0;
      var gap = parseFloat((col ? cs.rowGap : cs.columnGap) || cs.gap || 0) || 0;
      var each = (inner - gap * (cells.length - 1)) / cells.length;
      cells.forEach(function (cell) {
        var host = cell.querySelector('.mock');
        if (!host) return;
        var cap = Number(host.getAttribute('data-cap') || 0);
        var nw = Number(host.style.getPropertyValue('--nw')) || 384;
        var nh = Number(host.style.getPropertyValue('--nh')) || 580;
        var avail = cap ? Math.min(each, cap) : each;
        var sc = avail > 0 ? Math.min(1, avail / nw) : 1;
        var stage = host.querySelector('.mock-stage');
        if (stage) stage.style.transform = 'scale(' + sc + ')';
        host.style.width = Math.round(nw * sc) + 'px';
        host.style.height = Math.round(nh * sc) + 'px';
      });
    });
  }
  var rzTimer = null;
  window.addEventListener('resize', function () {
    clearTimeout(rzTimer);
    rzTimer = setTimeout(layoutAll, 120);
  });

  /* ---------------- 挂载 ---------------- */
  function mount() {
    document.querySelectorAll('.mock').forEach(function (host) {
      var kind = host.getAttribute('data-mock');
      var nw = Number(host.getAttribute('data-nw') || 384);
      var nh = Number(host.getAttribute('data-nh') || 580);
      var html = '';
      if (kind === 'main') html = mainWindow(windowMockConfig(host));
      else if (kind === 'mini') html = miniWindow(windowMockConfig(host));
      else if (kind === 'calc') html = calcDesk(windowMockConfig(host));
      else if (kind === 'settings') html = mainWindow(Object.assign({ withSettings: true, settingsOnly: true }, windowMockConfig(host)));
      else return;

      host.style.setProperty('--nw', String(nw));
      host.style.setProperty('--nh', String(nh));
      var stage = document.createElement('div');
      stage.className = 'mock-stage';
      stage.style.width = nw + 'px';
      stage.style.height = nh + 'px';
      var ctm = document.createElement('div');
      ctm.className = 'ctm';
      ctm.style.width = nw + 'px';
      ctm.style.height = nh + 'px';
      ctm.innerHTML = kind === 'main' || kind === 'settings'
        ? '<div class="app">' + html + '</div>'
        : html;
      stage.appendChild(ctm);
      host.appendChild(stage);

      if (kind === 'settings') {
        /* 对应 TopBar.vue：设置页里 status / 暂停 / 图钉 / 小窗 / 齿轮 都不渲染 */
        var tbS = ctm.querySelector('.topbar');
        if (tbS) {
          tbS.querySelectorAll('.status, [data-act="pause"], .icon-pin, .icon-mini, .icon-gear')
            .forEach(function (n) { n.remove(); });
        }
        var sv = ctm.querySelector('[data-settings]');
        var cp = ctm.querySelector('.clip-panel');
        if (sv && cp) { cp.style.display = 'none'; sv.style.display = 'flex'; }
        var sec = host.getAttribute('data-sec');
        var box = ctm.querySelector('[data-settings]');
        if (sec && box) {
          var target = box.querySelector('[data-sec="' + sec + '"]');
          if (target) {
            /* 滚到该区块顶端。跑两次：0ms 时中文字体可能还没落位，行高会变，
               一次算出的 dy 会差出半行，顶部就漏出上一段文字。 */
            var seek = function () {
              /* getBoundingClientRect 给的是**缩放后**的像素，scrollTop 要的是布局像素，
                 两窗并排（scale<1）时不除回去会滚过头，所以先还原。 */
              var st = box.closest('.mock').querySelector('.mock-stage');
              var m = /scale\(([\d.]+)\)/.exec(st ? st.style.transform : '');
              var sc = m ? parseFloat(m[1]) || 1 : 1;
              var dy =
                (target.getBoundingClientRect().top - box.getBoundingClientRect().top) / sc;
              box.scrollTop = Math.max(0, box.scrollTop + dy - 1);
            };
            setTimeout(seek, 0);
            setTimeout(seek, 350);
          }
        }
      }

      bind(ctm);

      /* 公式演示：填充中的待填格 */
      var cur = host.getAttribute('data-cursor');
      if (cur) {
        var parts = cur.split(',');
        var c0 = ctm.querySelector('[data-cell="' + parts[0] + ':' + parts[1] + '"]');
        if (c0) c0.classList.add('cursor');
      }
    });
    layoutAll();
  }

  function windowMockConfig(host) {
    var cfg = {};
    try {
      cfg = JSON.parse(host.getAttribute('data-config') || '{}');
    } catch (e) {
      cfg = {};
    }
    return cfg;
  }

  if (document.readyState === 'loading') document.addEventListener('DOMContentLoaded', mount);
  else mount();
})();

</script>
</body>
</html>
