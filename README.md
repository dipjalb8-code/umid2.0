<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>TEAM APEX — Certificate Showcase</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@400;600;700;900&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
:root{--fire:#FF3D00;--gold:#FFD600;--neon:#00E5FF;--dark:#0A0A0F;--dark2:#12121A;--mid:#1C1C28;--text:#F0F0F5;--muted:#6B6B80;}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--dark);color:var(--text);font-family:'Barlow',sans-serif;overflow-x:hidden;cursor:none;}
.cursor{width:10px;height:10px;background:var(--fire);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .2s,height .2s,background .2s;}
.cursor-ring{width:32px;height:32px;border:2px solid rgba(255,61,0,.55);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:border-color .3s;}
body::before{content:'';position:fixed;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.04'/%3E%3C/svg%3E");pointer-events:none;z-index:0;opacity:.35;}

#syncBadge{position:fixed;bottom:1.2rem;left:1.2rem;z-index:9000;display:flex;align-items:center;gap:6px;background:rgba(10,10,15,.92);border:1px solid rgba(0,229,255,.25);padding:6px 12px;font-family:'Barlow Condensed',sans-serif;font-size:.72rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--neon);backdrop-filter:blur(8px);}
.sync-dot{width:7px;height:7px;border-radius:50%;background:var(--neon);animation:syncPulse 1.8s ease-in-out infinite;}
@keyframes syncPulse{0%,100%{opacity:1;}50%{opacity:.2;}}
.sync-dot.err{background:#f87171;animation:none;}
.sync-dot.idle{background:var(--muted);animation:none;}

nav{position:fixed;top:0;left:0;right:0;z-index:200;display:flex;justify-content:space-between;align-items:center;padding:1rem 2.5rem;background:rgba(10,10,15,.92);backdrop-filter:blur(14px);border-bottom:1px solid rgba(255,61,0,.15);}
.nav-logo{font-family:'Bebas Neue',sans-serif;font-size:1.6rem;letter-spacing:.1em;}
.nav-logo span{color:var(--fire);}
.nav-links{display:flex;gap:.8rem;list-style:none;align-items:center;flex-wrap:wrap;}
.nav-links a{font-family:'Barlow Condensed',sans-serif;font-size:.85rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;color:var(--muted);text-decoration:none;transition:color .2s;}
.nav-links a:hover{color:var(--fire);}
.nav-btn{font-family:'Barlow Condensed',sans-serif;font-size:.78rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:7px 14px;border:none;cursor:none;display:flex;align-items:center;gap:5px;transition:opacity .2s;}
#adminToggleBtn{background:var(--fire);color:#fff;}
#adminToggleBtn:hover{opacity:.85;}
#routeMapBtn{background:var(--neon);color:#000;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);}
#routeMapBtn:hover{opacity:.85;}
.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;position:relative;padding:5rem 2rem 4rem;overflow:hidden;}
.hero-grid{position:absolute;inset:0;background-image:repeating-linear-gradient(0deg,transparent,transparent 59px,rgba(255,61,0,.07) 60px),repeating-linear-gradient(90deg,transparent,transparent 59px,rgba(255,61,0,.04) 60px);animation:gMove 18s linear infinite;}
@keyframes gMove{to{transform:translateY(60px);}}
.hero-glow{position:absolute;width:700px;height:700px;background:radial-gradient(circle,rgba(255,61,0,.15) 0%,transparent 65%);border-radius:50%;top:50%;left:50%;transform:translate(-50%,-50%);animation:hPulse 4s ease-in-out infinite;}
@keyframes hPulse{0%,100%{opacity:.6;transform:translate(-50%,-50%) scale(1);}50%{opacity:1;transform:translate(-50%,-50%) scale(1.12);}}
.badge-hero{display:inline-block;background:var(--fire);color:#fff;font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:.72rem;letter-spacing:.3em;text-transform:uppercase;padding:6px 18px;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);margin-bottom:1.5rem;animation:fD .7s ease both;}
h1.hero-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(5rem,13vw,10.5rem);line-height:.9;letter-spacing:-.02em;animation:fD .85s ease .1s both;}
h1.hero-title .outline{-webkit-text-stroke:2px var(--text);color:transparent;}
h1.hero-title .fire{color:var(--fire);}
.hero-sub{font-family:'Barlow Condensed',sans-serif;font-size:clamp(1rem,2.5vw,1.5rem);font-weight:600;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);margin-top:.8rem;animation:fD 1s ease .2s both;}
.hero-sub span{color:var(--gold);}
@keyframes fD{from{opacity:0;transform:translateY(-18px);}to{opacity:1;transform:translateY(0);}}
.hero-stats{display:flex;gap:3rem;margin-top:2.5rem;animation:fD 1.1s ease .35s both;}
.stat-num{font-family:'Bebas Neue',sans-serif;font-size:3.2rem;color:var(--fire);line-height:1;}
.stat-label{font-family:'Barlow Condensed',sans-serif;font-size:.7rem;letter-spacing:.2em;text-transform:uppercase;color:var(--muted);margin-top:3px;}
.btn-hero{display:inline-flex;align-items:center;gap:8px;background:var(--fire);color:#fff;font-family:'Barlow Condensed',sans-serif;font-size:.9rem;font-weight:700;letter-spacing:.18em;text-transform:uppercase;padding:13px 30px;border:none;cursor:none;clip-path:polygon(12px 0%,100% 0%,calc(100% - 12px) 100%,0% 100%);transition:background .2s,transform .15s;text-decoration:none;margin-top:1.8rem;animation:fD 1.1s ease .45s both;}
.btn-hero:hover{background:#ff5520;transform:scale(1.04);}
.scroll-hint{position:absolute;bottom:1.8rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:6px;animation:fD 1.2s ease .6s both;}
.scroll-hint span{font-family:'Barlow Condensed',sans-serif;font-size:.65rem;letter-spacing:.25em;text-transform:uppercase;color:var(--muted);}
.s-arrow{width:20px;height:20px;border-right:2px solid var(--fire);border-bottom:2px solid var(--fire);transform:rotate(45deg);animation:sBounce 1.5s infinite;}
@keyframes sBounce{0%,100%{transform:rotate(45deg) translateY(0);}50%{transform:rotate(45deg) translateY(5px);}}
section{position:relative;z-index:1;padding:5rem 2rem;}
.inner{max-width:1200px;margin:0 auto;}
.section-label{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:.68rem;letter-spacing:.4em;text-transform:uppercase;color:var(--fire);margin-bottom:.4rem;}
.section-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.5rem,6vw,5rem);line-height:1;margin-bottom:.4rem;}
.section-title span{color:var(--fire);}
.section-desc{color:var(--muted);font-size:.9rem;max-width:480px;line-height:1.7;margin-bottom:1.5rem;}
#adminPanel{display:none;margin-bottom:2rem;}
.admin-tabs{display:flex;gap:0;border-bottom:1px solid rgba(255,214,0,.2);}
.admin-tab{font-family:'Barlow Condensed',sans-serif;font-size:.8rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:10px 20px;border:none;background:transparent;color:var(--muted);cursor:none;border-bottom:2px solid transparent;margin-bottom:-1px;transition:color .2s,border-color .2s;}
.admin-tab.active{color:var(--gold);border-bottom-color:var(--gold);}
.admin-tab:hover{color:var(--text);}
.admin-pane{display:none;background:rgba(255,214,0,.04);border:1px solid rgba(255,214,0,.15);border-top:none;padding:1.5rem;}
.admin-pane.active{display:block;}
.admin-title{font-family:'Bebas Neue',sans-serif;font-size:1.3rem;color:var(--gold);letter-spacing:.05em;margin-bottom:1rem;}
.admin-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1rem;}
.admin-grid-3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:1rem;margin-bottom:1rem;}
.field-group{display:flex;flex-direction:column;gap:5px;}
.field-group label{font-family:'Barlow Condensed',sans-serif;font-size:.7rem;font-weight:700;letter-spacing:.2em;text-transform:uppercase;color:var(--muted);}
.field-group input,.field-group select{background:var(--dark);border:1px solid rgba(255,255,255,.1);color:var(--text);font-family:'Barlow',sans-serif;font-size:.9rem;padding:9px 12px;outline:none;transition:border-color .2s;width:100%;}
.field-group input:focus,.field-group select:focus{border-color:var(--fire);}
.field-group select option{background:var(--dark2);}
.drop-zone{border:2px dashed rgba(255,61,0,.3);padding:1.5rem;text-align:center;background:rgba(255,61,0,.03);transition:border-color .3s,background .3s;cursor:none;margin-bottom:1rem;}
.drop-zone.drag-over{border-color:var(--fire);background:rgba(255,61,0,.08);}
.drop-zone p{font-family:'Barlow Condensed',sans-serif;font-size:.85rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);}
input[type=file]{display:none;}
.admin-actions{display:flex;gap:.8rem;align-items:center;flex-wrap:wrap;margin-top:.5rem;}
.btn-add{background:var(--fire);color:#fff;font-family:'Barlow Condensed',sans-serif;font-size:.82rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:10px 22px;border:none;cursor:none;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:background .2s;}
.btn-add:hover{background:#ff5520;}
.btn-add.gold{background:var(--gold);color:#000;clip-path:none;}
.btn-add.gold:hover{opacity:.85;}
.btn-add.neon{background:var(--neon);color:#000;clip-path:none;}
.btn-add.neon:hover{opacity:.85;}
.btn-sm{background:transparent;border:1px solid rgba(255,61,0,.3);color:var(--fire);font-family:'Barlow Condensed',sans-serif;font-size:.72rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:6px 12px;cursor:none;transition:background .2s;}
.btn-sm:hover{background:rgba(255,61,0,.1);}
.btn-sm.edit{border-color:rgba(0,229,255,.4);color:var(--neon);}
.btn-sm.edit:hover{background:rgba(0,229,255,.08);}
.btn-sm.up-dn{border-color:rgba(255,255,255,.15);color:var(--muted);padding:5px 8px;}
.stats-row{display:flex;gap:1rem;align-items:flex-end;flex-wrap:wrap;padding-top:1rem;margin-top:1rem;border-top:1px solid rgba(255,255,255,.06);}
.stats-row .field-group{flex:1;min-width:80px;}
.btn-save-stats{background:var(--gold);color:#000;font-family:'Barlow Condensed',sans-serif;font-size:.8rem;font-weight:900;letter-spacing:.15em;text-transform:uppercase;padding:10px 20px;border:none;cursor:none;transition:opacity .2s;white-space:nowrap;}
.btn-save-stats:hover{opacity:.85;}
.edit-list{display:flex;flex-direction:column;gap:.55rem;margin-bottom:1rem;max-height:300px;overflow-y:auto;padding-right:4px;}
.edit-list::-webkit-scrollbar{width:4px;}
.edit-list::-webkit-scrollbar-thumb{background:rgba(255,61,0,.3);}
.edit-row{display:flex;align-items:center;gap:.7rem;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);padding:.55rem .8rem;}
.edit-row .er-info{flex:1;min-width:0;}
.edit-row .er-title{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.9rem;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.edit-row .er-sub{font-size:.75rem;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.edit-row .er-dot{width:12px;height:12px;border-radius:50%;flex-shrink:0;}
.edit-row .er-avatar{width:34px;height:34px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;font-size:1rem;color:#fff;flex-shrink:0;}
.edit-row .er-btns{display:flex;gap:.35rem;flex-shrink:0;}
.pane-divider{border-top:1px solid rgba(255,255,255,.06);padding-top:1rem;margin-top:.8rem;}
.sub-title{font-family:'Barlow Condensed',sans-serif;font-size:.95rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin-bottom:.8rem;}
#pwModal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.88);z-index:5000;align-items:center;justify-content:center;}
.pw-box{background:var(--dark2);border:1px solid rgba(255,61,0,.25);padding:2.5rem;width:100%;max-width:360px;}
.pw-box h2{font-family:'Bebas Neue',sans-serif;font-size:2rem;color:var(--fire);margin-bottom:.3rem;}
.pw-box p{font-size:.82rem;color:var(--muted);margin-bottom:1.4rem;}
.pw-input{width:100%;background:var(--dark);border:1px solid rgba(255,255,255,.1);color:var(--text);font-family:'Barlow',sans-serif;font-size:1rem;padding:11px 14px;outline:none;margin-bottom:.75rem;transition:border-color .2s;}
.pw-input:focus{border-color:var(--fire);}
.pw-submit{width:100%;background:var(--fire);color:#fff;font-family:'Barlow Condensed',sans-serif;font-size:.95rem;font-weight:700;letter-spacing:.2em;text-transform:uppercase;padding:12px;border:none;cursor:none;transition:background .2s;}
.pw-submit:hover{background:#ff5520;}
.pw-cancel{background:none;border:none;color:var(--muted);font-family:'Barlow Condensed',sans-serif;font-size:.78rem;letter-spacing:.12em;text-transform:uppercase;cursor:none;margin-top:.75rem;display:block;text-align:center;width:100%;}
.pw-error{color:#f87171;font-size:.8rem;font-family:'Barlow Condensed',sans-serif;letter-spacing:.08em;display:none;margin-bottom:.5rem;}
#editModal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.88);z-index:5000;align-items:center;justify-content:center;padding:1rem;}
#editModal.open{display:flex;}
.em-box{background:var(--dark2);border:1px solid rgba(0,229,255,.25);padding:2rem;width:100%;max-width:480px;max-height:90vh;overflow-y:auto;}
.em-title{font-family:'Bebas Neue',sans-serif;font-size:1.6rem;color:var(--neon);margin-bottom:1.2rem;}
.em-actions{display:flex;gap:.8rem;margin-top:1.2rem;}
.btn-save{background:var(--neon);color:#000;font-family:'Barlow Condensed',sans-serif;font-size:.85rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:10px 22px;border:none;cursor:none;transition:opacity .2s;}
.btn-save:hover{opacity:.85;}
.btn-cancel-em{background:transparent;border:1px solid rgba(255,255,255,.15);color:var(--muted);font-family:'Barlow Condensed',sans-serif;font-size:.8rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:9px 18px;cursor:none;}
#lightbox{position:fixed;inset:0;background:rgba(0,0,0,.93);z-index:10000;display:none;align-items:center;justify-content:center;padding:2rem;}
#lightbox.open{display:flex;}
#lbImg{max-width:90vw;max-height:88vh;object-fit:contain;box-shadow:0 0 80px rgba(255,61,0,.25);}
.lb-close{position:absolute;top:1.5rem;right:2rem;font-family:'Bebas Neue',sans-serif;font-size:2.2rem;color:var(--fire);cursor:none;background:none;border:none;line-height:1;}
.certs-section{background:var(--dark2);}
.certs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1.8rem;margin-top:2rem;}
.cert-card{background:var(--mid);border:1px solid rgba(255,61,0,.1);position:relative;overflow:hidden;transition:transform .3s cubic-bezier(.23,1,.32,1),border-color .3s,box-shadow .3s;animation:cIn .5s ease both;cursor:none;}
.cert-card:hover{transform:translateY(-7px) scale(1.015);border-color:var(--fire);box-shadow:0 18px 50px rgba(255,61,0,.18);}
.cert-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--fire),var(--gold));transform:scaleX(0);transform-origin:left;transition:transform .35s;}
.cert-card:hover::before{transform:scaleX(1);}
@keyframes cIn{from{opacity:0;transform:translateY(25px);}to{opacity:1;transform:translateY(0);}}
.cert-img-wrap{width:100%;aspect-ratio:4/3;overflow:hidden;position:relative;cursor:none;}
.cert-img-wrap img{width:100%;height:100%;object-fit:cover;transition:transform .5s;filter:brightness(.92);}
.cert-card:hover .cert-img-wrap img{transform:scale(1.06);filter:brightness(1);}
.img-overlay{position:absolute;inset:0;background:rgba(0,0,0,.5);display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity .3s;}
.img-overlay span{font-family:'Barlow Condensed',sans-serif;font-size:.9rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;color:#fff;}
.cert-card:hover .img-overlay{opacity:1;}
.cert-placeholder-img{width:100%;aspect-ratio:4/3;display:flex;flex-direction:column;align-items:center;justify-content:center;background:linear-gradient(135deg,#1a1a28,#0f0f1a);position:relative;}
.cert-placeholder-img::before{content:'';position:absolute;inset:14px;border:1px solid rgba(255,214,0,.15);}
.cert-placeholder-img .ph-icon{font-size:2.8rem;margin-bottom:.5rem;}
.cert-placeholder-img .ph-rank{font-family:'Bebas Neue',sans-serif;font-size:1.6rem;color:var(--fire);}
.cert-body{padding:1.1rem 1.3rem 1.3rem;}
.cert-event{font-family:'Barlow Condensed',sans-serif;font-size:.68rem;font-weight:700;letter-spacing:.28em;text-transform:uppercase;color:var(--fire);margin-bottom:.25rem;}
.cert-name{font-family:'Bebas Neue',sans-serif;font-size:1.5rem;line-height:1.05;margin-bottom:.5rem;}
.cert-meta{display:flex;gap:.8rem;align-items:center;flex-wrap:wrap;}
.cert-winner{display:inline-flex;align-items:center;gap:4px;background:rgba(255,214,0,.1);border:1px solid rgba(255,214,0,.28);color:var(--gold);font-family:'Barlow Condensed',sans-serif;font-size:.68rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:3px 9px;}
.cert-date{font-size:.76rem;color:var(--muted);}
.cert-card-btns{display:none;gap:.4rem;margin-top:.75rem;}
.admin-active .cert-card-btns{display:flex;}
.empty-state{grid-column:1/-1;text-align:center;padding:4rem;color:var(--muted);}
.empty-state .e-icon{font-size:3rem;margin-bottom:.75rem;}
.empty-state p{font-family:'Barlow Condensed',sans-serif;font-size:1rem;letter-spacing:.1em;text-transform:uppercase;}
.team-section{background:var(--dark);}
.team-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:1.3rem;margin-top:2rem;}
.member-card{text-align:center;padding:1.8rem 1rem 1.4rem;background:var(--mid);border:1px solid rgba(255,255,255,.06);position:relative;overflow:hidden;transition:transform .3s,border-color .3s;cursor:none;}
.member-card:hover{transform:translateY(-6px);border-color:rgba(255,61,0,.4);}
.member-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--fire),var(--gold));transform:scaleX(0);transform-origin:left;transition:transform .3s;}
.member-card:hover::after{transform:scaleX(1);}
.m-avatar{width:66px;height:66px;border-radius:50%;margin:0 auto .9rem;display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;font-size:1.7rem;color:#fff;}
.m-name{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:1rem;text-transform:uppercase;letter-spacing:.1em;margin-bottom:.2rem;}
.m-role{font-size:.76rem;color:var(--muted);}
.m-wins{margin-top:.65rem;font-family:'Bebas Neue',sans-serif;font-size:1.2rem;color:var(--fire);}
.m-wins span{font-size:.6rem;font-family:'Barlow Condensed',sans-serif;color:var(--muted);letter-spacing:.1em;display:block;}
.m-edit-btn{display:none;margin-top:.8rem;background:rgba(0,229,255,.08);border:1px solid rgba(0,229,255,.25);color:var(--neon);font-family:'Barlow Condensed',sans-serif;font-size:.68rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:5px 14px;cursor:none;transition:background .2s;width:100%;}
.m-edit-btn:hover{background:rgba(0,229,255,.18);}
.admin-active-members .m-edit-btn{display:block;}
footer{background:#060609;border-top:1px solid rgba(255,61,0,.12);padding:2.5rem 2rem;text-align:center;position:relative;z-index:1;}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:2.5rem;letter-spacing:.1em;margin-bottom:.3rem;}
.footer-logo span{color:var(--fire);}
.footer-tag{font-family:'Barlow Condensed',sans-serif;font-size:.75rem;letter-spacing:.28em;text-transform:uppercase;color:var(--muted);}
.footer-line{width:50px;height:2px;background:linear-gradient(90deg,var(--fire),var(--gold));margin:1.2rem auto;}
.footer-copy{font-size:.75rem;color:var(--muted);}
#toastBox{position:fixed;bottom:2rem;right:2rem;z-index:9999;display:flex;flex-direction:column;gap:.5rem;}
.toast{font-family:'Barlow Condensed',sans-serif;font-size:.85rem;font-weight:600;letter-spacing:.08em;padding:11px 18px;border-left:3px solid;animation:tIn .3s ease both;max-width:280px;}
.toast.ok{background:#0a1a10;border-color:#22c55e;color:#4ade80;}
.toast.err{background:#1a0808;border-color:var(--fire);color:#f87171;}
.toast.info{background:#0a0f1a;border-color:var(--neon);color:var(--neon);}
@keyframes tIn{from{opacity:0;transform:translateX(16px);}to{opacity:1;transform:translateX(0);}}
#routePage{display:none;position:fixed;inset:0;z-index:3000;background:var(--dark);flex-direction:column;}
#routePage.open{display:flex;}
.rp-header{display:flex;align-items:center;gap:1rem;flex-shrink:0;padding:.85rem 2rem;background:rgba(10,10,15,.97);border-bottom:1px solid rgba(0,229,255,.22);}
.rp-back{background:transparent;border:1px solid rgba(0,229,255,.4);color:var(--neon);font-family:'Barlow Condensed',sans-serif;font-size:.78rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;padding:7px 15px;cursor:none;transition:background .2s;}
.rp-back:hover{background:rgba(0,229,255,.1);}
.rp-title{font-family:'Bebas Neue',sans-serif;font-size:1.7rem;letter-spacing:.06em;}
.rp-title span{color:var(--neon);}
.rp-sub{font-family:'Barlow Condensed',sans-serif;font-size:.72rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);margin-left:auto;}
.map-wrap{flex:1;position:relative;overflow:hidden;}
#mapCanvas{display:block;width:100%;height:100%;}
.prog-track{position:absolute;top:1rem;left:50%;transform:translateX(-50%);width:min(520px,88vw);height:5px;background:rgba(255,255,255,.07);border-radius:3px;}
.prog-fill{height:100%;width:0%;background:linear-gradient(90deg,var(--neon),var(--gold));transition:width .12s linear;border-radius:3px;}
.rm-controls{position:absolute;bottom:1.6rem;left:50%;transform:translateX(-50%);display:flex;gap:.8rem;align-items:center;background:rgba(10,10,15,.9);border:1px solid rgba(0,229,255,.2);padding:.6rem 1.2rem;backdrop-filter:blur(10px);}
.ctrl-btn{font-family:'Barlow Condensed',sans-serif;font-size:.8rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:8px 18px;border:none;cursor:none;transition:opacity .2s;}
#rmPlayBtn{background:var(--neon);color:#000;}
#rmResetBtn{background:transparent;border:1px solid rgba(0,229,255,.4);color:var(--neon);}
#rmPlayBtn:hover,#rmResetBtn:hover{opacity:.8;}
.spd-wrap{display:flex;align-items:center;gap:.5rem;font-family:'Barlow Condensed',sans-serif;font-size:.7rem;letter-spacing:.12em;text-transform:uppercase;color:var(--muted);}
#spdSlider{width:70px;accent-color:var(--neon);}
.cp-popup{position:absolute;pointer-events:none;background:rgba(10,10,15,.96);border:1px solid var(--gold);padding:.7rem 1rem;max-width:220px;opacity:0;transition:opacity .3s;}
.cp-popup.show{opacity:1;}
.cp-ev{font-family:'Barlow Condensed',sans-serif;font-size:.65rem;letter-spacing:.28em;text-transform:uppercase;color:var(--fire);}
.cp-nm{font-family:'Bebas Neue',sans-serif;font-size:1.2rem;line-height:1.1;margin-top:.1rem;}
.cp-rk{font-size:.72rem;color:var(--gold);margin-top:.2rem;}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>
<div id="syncBadge"><div class="sync-dot idle" id="syncDot"></div><span id="syncLabel">Loading…</span></div>

<div id="lightbox">
  <button class="lb-close" onclick="closeLB()">✕</button>
  <img id="lbImg" src="" alt="Certificate"/>
</div>

<div id="pwModal">
  <div class="pw-box">
    <h2>🔐 Admin Access</h2>
    <p>Enter the admin password to manage everything.</p>
    <div class="pw-error" id="pwError">❌ Wrong password, try again.</div>
    <input class="pw-input" type="password" id="pwInput" placeholder="Enter password…" onkeydown="if(event.key==='Enter')checkPw()"/>
    <button class="pw-submit" onclick="checkPw()">Unlock Admin</button>
    <button class="pw-cancel" onclick="closePwModal()">Cancel</button>
  </div>
</div>

<div id="editModal">
  <div class="em-box">
    <div class="em-title" id="emTitle">Edit</div>
    <div id="emBody"></div>
    <div class="em-actions">
      <button class="btn-save" id="emSaveBtn">💾 Save Changes</button>
      <button class="btn-cancel-em" onclick="closeEditModal()">Cancel</button>
    </div>
  </div>
</div>

<div id="routePage">
  <div class="rp-header">
    <button class="rp-back" onclick="closeRoute()">← Back</button>
    <div class="rp-title">VICTORY <span>ROUTE</span></div>
    <div class="rp-sub">Team Apex — Journey of Wins</div>
  </div>
  <div class="map-wrap">
    <canvas id="mapCanvas"></canvas>
    <div class="prog-track"><div class="prog-fill" id="progFill"></div></div>
    <div class="rm-controls">
      <button class="ctrl-btn" id="rmPlayBtn" onclick="rmTogglePlay()">▶ Play</button>
      <button class="ctrl-btn" id="rmResetBtn" onclick="rmReset()">↺ Reset</button>
      <div class="spd-wrap">
        <span>Speed</span>
        <input type="range" id="spdSlider" min="0.3" max="3" step="0.1" value="1" oninput="document.getElementById('spdLabel').textContent=parseFloat(this.value).toFixed(1)+'x'">
        <span id="spdLabel">1.0x</span>
      </div>
    </div>
    <div class="cp-popup" id="cpPopup">
      <div class="cp-ev" id="cpEv"></div>
      <div class="cp-nm" id="cpNm"></div>
      <div class="cp-rk" id="cpRk"></div>
    </div>
  </div>
</div>

<nav>
  <div class="nav-logo">TEAM <span>APEX</span></div>
  <ul class="nav-links">
    <li><a href="#certs">Certificates</a></li>
    <li><a href="#team">Team</a></li>
    <li><button id="routeMapBtn" class="nav-btn" onclick="openRoute()">🗺 Route Map</button></li>
    <li><button id="adminToggleBtn" class="nav-btn" onclick="handleAdminBtn()">🛡 Admin</button></li>
  </ul>
</nav>

<section class="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="badge-hero">🔥 Hackathon Champions</div>
  <h1 class="hero-title"><span class="outline">WE</span><br><span class="fire">WIN.</span><br><span>ALWAYS.</span></h1>
  <p class="hero-sub">Team <span>APEX</span> &mdash; Turning Ideas Into <span>Victories</span></p>
  <div class="hero-stats">
    <div class="stat"><div class="stat-num" id="cntH">0</div><div class="stat-label">Hackathons</div></div>
    <div class="stat"><div class="stat-num" id="cntW">0</div><div class="stat-label">Wins</div></div>
    <div class="stat"><div class="stat-num" id="cntC">0</div><div class="stat-label">Certificates</div></div>
  </div>
  <a href="#certs" class="btn-hero">🏆 View Certificates</a>
  <div class="scroll-hint"><span>Scroll</span><div class="s-arrow"></div></div>
</section>

<section class="certs-section" id="certs">
  <div class="inner">
    <div class="section-label">Our Victories</div>
    <h2 class="section-title">CERTIFICATE<span>S</span></h2>
    <p class="section-desc">Every certificate tells a story — of late nights, bold ideas, and relentless execution.</p>

    <div id="adminPanel">
      <div class="admin-tabs">
        <button class="admin-tab active" onclick="switchTab('certs')">🏆 Certificates</button>
        <button class="admin-tab" onclick="switchTab('route')">🗺 Route Map</button>
        <button class="admin-tab" onclick="switchTab('members')">👥 Members</button>
        <button class="admin-tab" onclick="switchTab('stats')">📊 Stats</button>
      </div>
      <div class="admin-pane active" id="pane-certs">
        <div class="admin-title">➕ Add New Certificate</div>
        <div class="admin-grid">
          <div class="field-group"><label>Certificate Title *</label><input type="text" id="fTitle" placeholder="Best Overall Project"/></div>
          <div class="field-group"><label>Hackathon / Event Name *</label><input type="text" id="fEvent" placeholder="HackIIT 2024"/></div>
          <div class="field-group"><label>Rank / Award *</label><input type="text" id="fRank" placeholder="🏆 1st Place"/></div>
          <div class="field-group"><label>Date</label><input type="text" id="fDate" placeholder="March 2025"/></div>
        </div>
        <label class="drop-zone" id="dropZone" for="certFile">
          <p style="font-size:1.5rem;margin-bottom:.3rem">📂</p>
          <p id="dzText">Click or drag &amp; drop certificate image here</p>
          <p style="font-size:.75rem;margin-top:.3rem;color:var(--muted)">PNG, JPG — max 3MB</p>
        </label>
        <input type="file" id="certFile" accept="image/*"/>
        <div class="admin-actions">
          <button class="btn-add" onclick="addCert()">📤 Add Certificate</button>
          <button class="btn-sm" onclick="confirmClearAll()">🗑 Clear All</button>
          <button class="btn-sm" style="border-color:rgba(255,255,255,.15);color:var(--muted)" onclick="lockAdmin()">🔒 Lock Admin</button>
        </div>
      </div>
      <div class="admin-pane" id="pane-route">
        <div class="admin-title">🗺 Route Map Events</div>
        <p style="font-size:.82rem;color:var(--muted);margin-bottom:.8rem">Edit, reorder or remove events.</p>
        <div class="edit-list" id="routeList"></div>
        <div class="pane-divider">
          <div class="sub-title">➕ Add New Event</div>
          <div class="admin-grid-3">
            <div class="field-group"><label>Short Label *</label><input type="text" id="rlLabel" placeholder="HackIIT 2024"/></div>
            <div class="field-group"><label>Full Event Name *</label><input type="text" id="rlEvent" placeholder="HackIIT Spring 2024"/></div>
            <div class="field-group"><label>Award / Rank *</label><input type="text" id="rlRank" placeholder="🥇 1st Place"/></div>
          </div>
          <div class="field-group" style="margin-bottom:1rem;max-width:340px">
            <label>Dot Color</label>
            <select id="rlColor">
              <option value="#00E5FF">🔵 Cyan — Start / Neutral</option>
              <option value="#FFD600" selected>🟡 Gold — Win / Achievement</option>
              <option value="#FF3D00">🔴 Red — Finish / Major Win</option>
              <option value="#22c55e">🟢 Green — Participation</option>
            </select>
          </div>
          <div class="admin-actions"><button class="btn-add neon" onclick="addRouteEvent()">➕ Add to Route</button></div>
        </div>
      </div>
      <div class="admin-pane" id="pane-members">
        <div class="admin-title">👥 Team Members</div>
        <p style="font-size:.82rem;color:var(--muted);margin-bottom:.8rem">Click ✏️ Edit to update any member.</p>
        <div class="edit-list" id="memberList"></div>
        <div class="pane-divider">
          <div class="sub-title">➕ Add New Member</div>
          <div class="admin-grid">
            <div class="field-group"><label>Full Name *</label><input type="text" id="nmName" placeholder="Arjun Sharma"/></div>
            <div class="field-group"><label>Role / Position *</label><input type="text" id="nmRole" placeholder="Team Lead / Full Stack"/></div>
            <div class="field-group"><label>Awards Won</label><input type="text" id="nmWins" placeholder="3"/></div>
            <div class="field-group"><label>Avatar Letter</label><input type="text" id="nmLetter" placeholder="A" maxlength="2"/></div>
          </div>
          <div class="field-group" style="margin-bottom:1rem;max-width:340px">
            <label>Avatar Color</label>
            <select id="nmColor">
              <option value="linear-gradient(135deg,#FF3D00,#FF8C00)">🔴 Fire Orange</option>
              <option value="linear-gradient(135deg,#00E5FF,#0077B6)">🔵 Neon Blue</option>
              <option value="linear-gradient(135deg,#FFD600,#FF6D00)">🟡 Gold Flame</option>
              <option value="linear-gradient(135deg,#7B2FFF,#FF3D00)">🟣 Purple Fire</option>
              <option value="linear-gradient(135deg,#22c55e,#0077B6)">🟢 Teal Green</option>
              <option value="linear-gradient(135deg,#f472b6,#7B2FFF)">🌸 Pink Purple</option>
            </select>
          </div>
          <div class="admin-actions"><button class="btn-add gold" onclick="addMember()">➕ Add Member</button></div>
        </div>
      </div>
      <div class="admin-pane" id="pane-stats">
        <div class="admin-title">📊 Hero Stats</div>
        <p style="font-size:.82rem;color:var(--muted);margin-bottom:1rem">These numbers animate on the homepage hero.</p>
        <div class="stats-row">
          <div class="field-group"><label>Hackathons #</label><input type="number" id="sH" min="0"/></div>
          <div class="field-group"><label>Wins #</label><input type="number" id="sW" min="0"/></div>
          <div class="field-group"><label>Certificates #</label><input type="number" id="sC" min="0"/></div>
          <button class="btn-save-stats" onclick="saveStats()">💾 Save</button>
        </div>
        <div style="margin-top:1.5rem;padding-top:1rem;border-top:1px solid rgba(255,255,255,.06)">
          <button class="btn-sm" style="border-color:rgba(255,255,255,.15);color:var(--muted)" onclick="lockAdmin()">🔒 Lock &amp; Exit Admin</button>
        </div>
      </div>
    </div>

    <div class="certs-grid" id="certsGrid"></div>
  </div>
</section>

<section class="team-section" id="team">
  <div class="inner">
    <div class="section-label">The Squad</div>
    <h2 class="section-title">MEET THE<span> TEAM</span></h2>
    <div class="team-grid" id="teamGrid"></div>
  </div>
</section>

<footer>
  <div class="footer-logo">TEAM <span>APEX</span></div>
  <div class="footer-tag">Built to win. Coded to inspire.</div>
  <div class="footer-line"></div>
  <div class="footer-copy">© 2025 Team Apex</div>
</footer>
<div id="toastBox"></div>

<script>
/* ══════════════════════════════
   HARDCODED CONFIG — no setup needed for anyone
══════════════════════════════ */
const ADMIN_PASSWORD  = "team2025";
const JB_KEY          = "$2a$10$jkxQQMtF94a1X0WXnq5jmurA/oHlnAy3iO7cbtCSaM2Z1IRBTPU6i";
const JB_BIN_STORAGE  = "apex_bin_id"; // localStorage key to remember the bin
const JSONBIN_BASE    = "https://api.jsonbin.io/v3";

const DEFAULT_STATS   = {h:8,w:5,c:12};
const DEFAULT_MEMBERS = [
  {id:'m1',name:'Member 1',role:'Team Lead / Full Stack',wins:'—',letter:'A',color:'linear-gradient(135deg,#FF3D00,#FF8C00)'},
  {id:'m2',name:'Member 2',role:'AI / ML Engineer',wins:'—',letter:'B',color:'linear-gradient(135deg,#00E5FF,#0077B6)'},
  {id:'m3',name:'Member 3',role:'UI / UX Designer',wins:'—',letter:'C',color:'linear-gradient(135deg,#FFD600,#FF6D00)'},
  {id:'m4',name:'Member 4',role:'Backend / DevOps',wins:'—',letter:'D',color:'linear-gradient(135deg,#7B2FFF,#FF3D00)'},
];
const DEFAULT_ROUTE = [
  {id:'r0',label:'Start',event:'Team Formed',rank:'Ready to win',color:'#00E5FF'},
  {id:'r1',label:'HackIIT 2024',event:'HackIIT 2024',rank:'🥇 1st Place',color:'#FFD600'},
  {id:'r2',label:'CodeBee 2.26',event:'CodeBee 2.26',rank:'🥈 2nd Place',color:'#FFD600'},
  {id:'r3',label:'BuildFest',event:'BuildFest Spring',rank:'🥇 1st Place',color:'#FFD600'},
  {id:'r4',label:'TechSprint',event:'TechSprint National',rank:'🏆 Best UI',color:'#FFD600'},
  {id:'r5',label:'DataJam 2025',event:'DataJam 2025',rank:'🥇 1st Place',color:'#FFD600'},
  {id:'r6',label:'OpenHack Global',event:'OpenHack Global',rank:'🥈 2nd Place',color:'#FFD600'},
  {id:'r7',label:'FINISH 🏁',event:'Season Complete',rank:'Champions',color:'#FF3D00'},
];

/* ══════════════════════════════
   CLOUD ENGINE
══════════════════════════════ */
let BIN_ID = localStorage.getItem(JB_BIN_STORAGE) || '';

function setSyncUI(state, label){
  const dot = document.getElementById('syncDot');
  dot.className = 'sync-dot' + (state==='ok'?'':state==='err'?' err':' idle');
  document.getElementById('syncLabel').textContent = label;
}

async function jbGet(){
  const r = await fetch(`${JSONBIN_BASE}/b/${BIN_ID}/latest`,{
    headers:{'X-Master-Key':JB_KEY}
  });
  if(!r.ok) throw new Error('get failed');
  return (await r.json()).record;
}

async function jbPut(data){
  setSyncUI('','Saving…');
  const r = await fetch(`${JSONBIN_BASE}/b/${BIN_ID}`,{
    method:'PUT',
    headers:{'Content-Type':'application/json','X-Master-Key':JB_KEY},
    body:JSON.stringify(data)
  });
  if(!r.ok) throw new Error('put failed');
  setSyncUI('ok','Synced ✓');
  setTimeout(()=>setSyncUI('ok','☁️ Live'),2000);
}

async function jbCreate(){
  const payload = {certs:[],stats:DEFAULT_STATS,members:DEFAULT_MEMBERS,route:DEFAULT_ROUTE};
  const r = await fetch(`${JSONBIN_BASE}/b`,{
    method:'POST',
    headers:{'Content-Type':'application/json','X-Master-Key':JB_KEY,'X-Bin-Name':'TeamApex'},
    body:JSON.stringify(payload)
  });
  if(!r.ok) throw new Error('create failed');
  const j = await r.json();
  BIN_ID = j.metadata.id;
  localStorage.setItem(JB_BIN_STORAGE, BIN_ID);
  return payload;
}

async function masterSave(){
  try{
    await jbPut({certs,stats,members,route});
  }catch(e){
    setSyncUI('err','Save failed!');
    toast('❌ Cloud save failed','err');
  }
}

async function initApp(){
  setSyncUI('','Connecting…');
  try{
    let data;
    if(BIN_ID){
      // returning visitor — fetch live data
      data = await jbGet();
    } else {
      // very first time ever — create the shared bin
      data = await jbCreate();
      toast('☁️ Cloud database created! Share this page with friends.','ok');
    }
    applyData(data);
    setSyncUI('ok','☁️ Live');
    renderAll();
  }catch(e){
    setSyncUI('err','Offline');
    toast('⚠️ Cloud unreachable — check internet','err');
    // fallback: show defaults so page isn't blank
    applyData(null);
    renderAll();
  }
}

function applyData(data){
  certs   = data?.certs   || [];
  stats   = data?.stats   || DEFAULT_STATS;
  members = data?.members || DEFAULT_MEMBERS;
  route   = data?.route   || DEFAULT_ROUTE;
}

/* ══════════════════════════════
   STATE
══════════════════════════════ */
let certs=[], stats={}, members=[], route=[];
let isAdmin=false, pendingFileData=null;

/* ══════════════════════════════
   ADMIN
══════════════════════════════ */
function handleAdminBtn(){isAdmin?lockAdmin():openPwModal();}
function openPwModal(){document.getElementById('pwModal').style.display='flex';document.getElementById('pwInput').value='';document.getElementById('pwError').style.display='none';setTimeout(()=>document.getElementById('pwInput').focus(),100);}
function closePwModal(){document.getElementById('pwModal').style.display='none';}
function checkPw(){
  if(document.getElementById('pwInput').value===ADMIN_PASSWORD){
    isAdmin=true;closePwModal();
    document.getElementById('adminPanel').style.display='block';
    document.getElementById('adminToggleBtn').textContent='🔓 Exit Admin';
    document.getElementById('adminToggleBtn').style.background='var(--gold)';
    document.getElementById('adminToggleBtn').style.color='#000';
    renderAll();toast('👋 Admin mode ON!','ok');
  }else{
    document.getElementById('pwError').style.display='block';
    document.getElementById('pwInput').value='';document.getElementById('pwInput').focus();
  }
}
function lockAdmin(){
  isAdmin=false;document.getElementById('adminPanel').style.display='none';
  document.getElementById('adminToggleBtn').textContent='🛡 Admin';
  document.getElementById('adminToggleBtn').style.background='var(--fire)';
  document.getElementById('adminToggleBtn').style.color='#fff';
  renderAll();toast('🔒 Admin locked','info');
}
document.getElementById('pwModal').addEventListener('click',e=>{if(e.target.id==='pwModal')closePwModal();});

function switchTab(tab){
  const keys=['certs','route','members','stats'];
  document.querySelectorAll('.admin-tab').forEach((t,i)=>t.classList.toggle('active',keys[i]===tab));
  document.querySelectorAll('.admin-pane').forEach(p=>p.classList.remove('active'));
  document.getElementById('pane-'+tab).classList.add('active');
}

function closeEditModal(){document.getElementById('editModal').classList.remove('open');}
document.getElementById('editModal').addEventListener('click',e=>{if(e.target.id==='editModal')closeEditModal();});
function openEditModal(title,bodyHtml,onSave){
  document.getElementById('emTitle').textContent=title;
  document.getElementById('emBody').innerHTML=bodyHtml;
  document.getElementById('emSaveBtn').onclick=onSave;
  document.getElementById('editModal').classList.add('open');
}

/* ── STATS ── */
function renderStats(){
  animCount('cntH',stats.h);animCount('cntW',stats.w);animCount('cntC',stats.c);
  document.getElementById('sH').value=stats.h;
  document.getElementById('sW').value=stats.w;
  document.getElementById('sC').value=stats.c;
}
async function saveStats(){
  stats={h:+document.getElementById('sH').value||0,w:+document.getElementById('sW').value||0,c:+document.getElementById('sC').value||0};
  await masterSave();renderStats();toast('✅ Stats saved!','ok');
}

/* ── CERTIFICATES ── */
function renderCerts(){
  const grid=document.getElementById('certsGrid');
  isAdmin?grid.classList.add('admin-active'):grid.classList.remove('admin-active');
  if(!certs.length){grid.innerHTML=`<div class="empty-state"><div class="e-icon">🏆</div><p>${isAdmin?'No certificates yet — add your first win above!':'Certificates coming soon!'}</p></div>`;return;}
  grid.innerHTML='';
  certs.forEach((c,i)=>{
    const card=document.createElement('div');card.className='cert-card';card.style.animationDelay=(i*.07)+'s';
    const imgHtml=c.image
      ?`<div class="cert-img-wrap" onclick="openLB('${c.id}')"><img src="${c.image}" alt="${esc(c.title)}" loading="lazy"/><div class="img-overlay"><span>🔍 View Full</span></div></div>`
      :`<div class="cert-placeholder-img"><div class="ph-icon">${rankIcon(c.rank)}</div><div class="ph-rank">${esc(c.rank)}</div></div>`;
    card.innerHTML=`${imgHtml}<div class="cert-body"><div class="cert-event">${esc(c.eventName)}</div><div class="cert-name">${esc(c.title)}</div><div class="cert-meta"><span class="cert-winner">${esc(c.rank)}</span><span class="cert-date">${esc(c.date)}</span></div><div class="cert-card-btns"><button class="btn-sm edit" onclick="editCert('${c.id}')">✏️ Edit</button><button class="btn-sm" onclick="deleteCert('${c.id}')">🗑 Delete</button></div></div>`;
    grid.appendChild(card);
  });
}
async function addCert(){
  const title=document.getElementById('fTitle').value.trim(),event=document.getElementById('fEvent').value.trim(),rank=document.getElementById('fRank').value.trim(),date=document.getElementById('fDate').value.trim();
  if(!title||!event||!rank){toast('❌ Fill Title, Event & Rank!','err');return;}
  certs.unshift({id:Date.now().toString(),title,eventName:event,rank,date:date||new Date().getFullYear().toString(),image:pendingFileData||null,createdAt:Date.now()});
  await masterSave();renderCerts();
  ['fTitle','fEvent','fRank','fDate'].forEach(id=>document.getElementById(id).value='');
  pendingFileData=null;document.getElementById('dzText').textContent='Click or drag & drop certificate image here';document.getElementById('certFile').value='';
  toast('🏆 Certificate added & synced to all!','ok');
}
function editCert(id){
  const c=certs.find(x=>x.id===id);if(!c)return;
  openEditModal('✏️ Edit Certificate',`<div class="admin-grid"><div class="field-group"><label>Certificate Title *</label><input type="text" id="ec_title" value="${esc(c.title)}"/></div><div class="field-group"><label>Event Name *</label><input type="text" id="ec_event" value="${esc(c.eventName)}"/></div><div class="field-group"><label>Rank / Award *</label><input type="text" id="ec_rank" value="${esc(c.rank)}"/></div><div class="field-group"><label>Date</label><input type="text" id="ec_date" value="${esc(c.date)}"/></div></div>`,async()=>{
    const title=document.getElementById('ec_title').value.trim(),event=document.getElementById('ec_event').value.trim(),rank=document.getElementById('ec_rank').value.trim();
    if(!title||!event||!rank){toast('❌ Fill required fields!','err');return;}
    c.title=title;c.eventName=event;c.rank=rank;c.date=document.getElementById('ec_date').value.trim();
    await masterSave();renderCerts();closeEditModal();toast('✅ Updated & synced!','ok');
  });
}
async function deleteCert(id){if(!confirm('Delete this certificate?'))return;certs=certs.filter(c=>c.id!==id);await masterSave();renderCerts();toast('🗑 Deleted','info');}
async function confirmClearAll(){if(!confirm('Delete ALL certificates?'))return;certs=[];await masterSave();renderCerts();toast('🗑 All cleared','info');}

const certFileInput=document.getElementById('certFile'),dropZone=document.getElementById('dropZone');
certFileInput.addEventListener('change',e=>{if(e.target.files[0])processFile(e.target.files[0]);});
['dragover','dragleave','drop'].forEach(evt=>{dropZone.addEventListener(evt,e=>{e.preventDefault();dropZone.classList.toggle('drag-over',evt==='dragover');if(evt==='drop'&&e.dataTransfer.files[0])processFile(e.dataTransfer.files[0]);});});
function processFile(file){if(!file.type.startsWith('image/')){toast('❌ Use an image file','err');return;}if(file.size>3*1024*1024){toast('⚠️ Image over 3MB','err');return;}const reader=new FileReader();reader.onload=e=>{pendingFileData=e.target.result;document.getElementById('dzText').textContent='✅ '+file.name;};reader.readAsDataURL(file);}
function openLB(id){const c=certs.find(x=>x.id===id);if(!c||!c.image)return;document.getElementById('lbImg').src=c.image;document.getElementById('lightbox').classList.add('open');}
function closeLB(){document.getElementById('lightbox').classList.remove('open');}
document.getElementById('lightbox').addEventListener('click',e=>{if(e.target.id==='lightbox')closeLB();});

/* ── ROUTE ── */
function renderRouteList(){
  const list=document.getElementById('routeList');
  if(!route.length){list.innerHTML='<p style="color:var(--muted);font-size:.85rem;padding:.5rem 0">No events yet.</p>';return;}
  list.innerHTML='';
  route.forEach((r,i)=>{
    const row=document.createElement('div');row.className='edit-row';
    row.innerHTML=`<div class="er-dot" style="background:${r.color}"></div><div class="er-info"><div class="er-title">${esc(r.label)}</div><div class="er-sub">${esc(r.event)} &nbsp;·&nbsp; ${esc(r.rank)}</div></div><div class="er-btns"><button class="btn-sm up-dn" onclick="moveRoute(${i},-1)" ${i===0?'disabled style="opacity:.3"':''}>↑</button><button class="btn-sm up-dn" onclick="moveRoute(${i},1)" ${i===route.length-1?'disabled style="opacity:.3"':''}>↓</button><button class="btn-sm edit" onclick="editRouteEvent('${r.id}')">✏️</button><button class="btn-sm" onclick="deleteRouteEvent('${r.id}')">🗑</button></div>`;
    list.appendChild(row);
  });
}
async function addRouteEvent(){
  const label=document.getElementById('rlLabel').value.trim(),event=document.getElementById('rlEvent').value.trim(),rank=document.getElementById('rlRank').value.trim(),color=document.getElementById('rlColor').value;
  if(!label||!event||!rank){toast('❌ Fill all route event fields!','err');return;}
  route.push({id:'r'+Date.now(),label,event,rank,color});
  await masterSave();renderRouteList();
  ['rlLabel','rlEvent','rlRank'].forEach(id=>document.getElementById(id).value='');
  toast('✅ Event added & synced!','ok');
}
function editRouteEvent(id){
  const r=route.find(x=>x.id===id);if(!r)return;
  openEditModal('✏️ Edit Route Event',`<div class="admin-grid"><div class="field-group"><label>Short Label *</label><input type="text" id="er_label" value="${esc(r.label)}"/></div><div class="field-group"><label>Full Event Name *</label><input type="text" id="er_event" value="${esc(r.event)}"/></div><div class="field-group"><label>Award / Rank *</label><input type="text" id="er_rank" value="${esc(r.rank)}"/></div><div class="field-group"><label>Dot Color</label><select id="er_color"><option value="#00E5FF" ${r.color==='#00E5FF'?'selected':''}>🔵 Cyan</option><option value="#FFD600" ${r.color==='#FFD600'?'selected':''}>🟡 Gold</option><option value="#FF3D00" ${r.color==='#FF3D00'?'selected':''}>🔴 Red</option><option value="#22c55e" ${r.color==='#22c55e'?'selected':''}>🟢 Green</option></select></div></div>`,async()=>{
    const label=document.getElementById('er_label').value.trim(),event=document.getElementById('er_event').value.trim(),rank=document.getElementById('er_rank').value.trim();
    if(!label||!event||!rank){toast('❌ Fill all fields!','err');return;}
    r.label=label;r.event=event;r.rank=rank;r.color=document.getElementById('er_color').value;
    await masterSave();renderRouteList();closeEditModal();toast('✅ Updated & synced!','ok');
  });
}
async function deleteRouteEvent(id){if(!confirm('Remove this route event?'))return;route=route.filter(r=>r.id!==id);await masterSave();renderRouteList();toast('🗑 Removed','info');}
async function moveRoute(idx,dir){const ni=idx+dir;if(ni<0||ni>=route.length)return;[route[idx],route[ni]]=[route[ni],route[idx]];await masterSave();renderRouteList();}

/* ── MEMBERS ── */
function renderMemberList(){
  const list=document.getElementById('memberList');list.innerHTML='';
  if(!members.length){list.innerHTML='<p style="color:var(--muted);font-size:.85rem;padding:.5rem 0">No members yet.</p>';return;}
  members.forEach(m=>{
    const row=document.createElement('div');row.className='edit-row';
    row.innerHTML=`<div class="er-avatar" style="background:${m.color}">${esc(m.letter)}</div><div class="er-info"><div class="er-title">${esc(m.name)}</div><div class="er-sub">${esc(m.role)} &nbsp;·&nbsp; ${esc(m.wins)} awards</div></div><div class="er-btns"><button class="btn-sm edit" onclick="editMember('${m.id}')">✏️ Edit</button><button class="btn-sm" onclick="deleteMember('${m.id}')">🗑</button></div>`;
    list.appendChild(row);
  });
}
function renderTeamGrid(){
  const grid=document.getElementById('teamGrid');grid.innerHTML='';
  isAdmin?grid.classList.add('admin-active-members'):grid.classList.remove('admin-active-members');
  if(!members.length){grid.innerHTML='<p style="color:var(--muted);font-family:\'Barlow Condensed\',sans-serif;letter-spacing:.1em">No members yet.</p>';return;}
  members.forEach(m=>{
    const card=document.createElement('div');card.className='member-card';
    card.innerHTML=`<div class="m-avatar" style="background:${m.color}">${esc(m.letter)}</div><div class="m-name">${esc(m.name)}</div><div class="m-role">${esc(m.role)}</div><div class="m-wins">${esc(m.wins)}<span>Awards Won</span></div><button class="m-edit-btn" onclick="editMember('${m.id}')">✏️ Edit Member</button>`;
    grid.appendChild(card);
  });
}
const COLOR_OPTIONS=[{v:'linear-gradient(135deg,#FF3D00,#FF8C00)',l:'🔴 Fire Orange'},{v:'linear-gradient(135deg,#00E5FF,#0077B6)',l:'🔵 Neon Blue'},{v:'linear-gradient(135deg,#FFD600,#FF6D00)',l:'🟡 Gold Flame'},{v:'linear-gradient(135deg,#7B2FFF,#FF3D00)',l:'🟣 Purple Fire'},{v:'linear-gradient(135deg,#22c55e,#0077B6)',l:'🟢 Teal Green'},{v:'linear-gradient(135deg,#f472b6,#7B2FFF)',l:'🌸 Pink Purple'}];
async function addMember(){
  const name=document.getElementById('nmName').value.trim(),role=document.getElementById('nmRole').value.trim(),wins=document.getElementById('nmWins').value.trim()||'—',letter=(document.getElementById('nmLetter').value.trim().toUpperCase()||name[0]||'?'),color=document.getElementById('nmColor').value;
  if(!name||!role){toast('❌ Name and Role required!','err');return;}
  members.push({id:'m'+Date.now(),name,role,wins,letter,color});
  await masterSave();renderMemberList();renderTeamGrid();
  ['nmName','nmRole','nmWins','nmLetter'].forEach(id=>document.getElementById(id).value='');
  toast('✅ Member added & synced!','ok');
}
function editMember(id){
  const m=members.find(x=>x.id===id);if(!m)return;
  const opts=COLOR_OPTIONS.map(o=>`<option value="${o.v}" ${m.color===o.v?'selected':''}>${o.l}</option>`).join('');
  openEditModal('✏️ Edit Member',`<div class="admin-grid"><div class="field-group"><label>Full Name *</label><input type="text" id="em_name" value="${esc(m.name)}"/></div><div class="field-group"><label>Role / Position *</label><input type="text" id="em_role" value="${esc(m.role)}"/></div><div class="field-group"><label>Awards Won</label><input type="text" id="em_wins" value="${esc(m.wins)}"/></div><div class="field-group"><label>Avatar Letter</label><input type="text" id="em_letter" value="${esc(m.letter)}" maxlength="2"/></div></div><div class="field-group" style="margin-bottom:.5rem;max-width:340px"><label>Avatar Color</label><select id="em_color">${opts}</select></div>`,async()=>{
    const name=document.getElementById('em_name').value.trim(),role=document.getElementById('em_role').value.trim();
    if(!name||!role){toast('❌ Name and Role required!','err');return;}
    m.name=name;m.role=role;m.wins=document.getElementById('em_wins').value.trim()||'—';m.letter=(document.getElementById('em_letter').value.trim().toUpperCase()||name[0]||'?');m.color=document.getElementById('em_color').value;
    await masterSave();renderMemberList();renderTeamGrid();closeEditModal();toast('✅ Updated & synced!','ok');
  });
}
async function deleteMember(id){if(!confirm('Remove this member?'))return;members=members.filter(m=>m.id!==id);await masterSave();renderMemberList();renderTeamGrid();toast('🗑 Removed','info');}

function renderAll(){renderStats();renderCerts();renderTeamGrid();if(isAdmin){renderRouteList();renderMemberList();}}

/* ══════════════════════════════
   ROUTE MAP ENGINE
══════════════════════════════ */
const rmCanvas=document.getElementById('mapCanvas'),rmCtx=rmCanvas.getContext('2d');
let rmW=0,rmH=0,rmPts=[],rmPath=[];
let rmProgress=0,rmPlaying=false,rmLastT=null,rmRaf=null,rmReached=new Set(),rmCpTimer=null;
function rmResize(){const w=rmCanvas.parentElement;rmW=rmCanvas.width=w.clientWidth*devicePixelRatio;rmH=rmCanvas.height=w.clientHeight*devicePixelRatio;rmCanvas.style.width=w.clientWidth+'px';rmCanvas.style.height=w.clientHeight+'px';rmBuildPath();rmDraw();}
function rmBuildPath(){const n=route.length;rmPts=route.map((_,i)=>{const t=i/(n-1||1);return{x:(i%2===0)?rmW*.18:rmW*.80,y:rmH*.07+t*(rmH*.86)};});rmPath=[];const S=1400;for(let s=0;s<=S;s++){const t=s/S,idx=t*(rmPts.length-1),i1=Math.floor(idx);const i0=Math.max(0,i1-1),i2=Math.min(rmPts.length-1,i1+1),i3=Math.min(rmPts.length-1,i1+2);rmPath.push(rmCatmull(rmPts[i0],rmPts[i1],rmPts[i2],rmPts[i3],idx-i1));}for(let i=0;i<rmPath.length;i++){const nx=rmPath[Math.min(i+1,rmPath.length-1)],pv=rmPath[Math.max(i-1,0)];rmPath[i].angle=Math.atan2(nx.y-pv.y,nx.x-pv.x);}}
function rmCatmull(p0,p1,p2,p3,t){const t2=t*t,t3=t2*t;return{x:.5*((-p0.x+3*p1.x-3*p2.x+p3.x)*t3+(2*p0.x-5*p1.x+4*p2.x-p3.x)*t2+(-p0.x+p2.x)*t+2*p1.x),y:.5*((-p0.y+3*p1.y-3*p2.y+p3.y)*t3+(2*p0.y-5*p1.y+4*p2.y-p3.y)*t2+(-p0.y+p2.y)*t+2*p1.y)};}
function rmDraw(){rmCtx.clearRect(0,0,rmW,rmH);const dpr=devicePixelRatio;rmCtx.save();rmCtx.strokeStyle='rgba(255,255,255,.04)';rmCtx.lineWidth=1;const G=60*dpr;for(let x=0;x<rmW;x+=G){rmCtx.beginPath();rmCtx.moveTo(x,0);rmCtx.lineTo(x,rmH);rmCtx.stroke();}for(let y=0;y<rmH;y+=G){rmCtx.beginPath();rmCtx.moveTo(0,y);rmCtx.lineTo(rmW,y);rmCtx.stroke();}rmCtx.restore();if(rmPath.length<2)return;rmCtx.save();rmCtx.lineWidth=22*dpr;rmCtx.lineCap='round';rmCtx.lineJoin='round';rmCtx.strokeStyle='rgba(255,255,255,.06)';rmCtx.beginPath();rmCtx.moveTo(rmPath[0].x,rmPath[0].y);for(let i=1;i<rmPath.length;i++)rmCtx.lineTo(rmPath[i].x,rmPath[i].y);rmCtx.stroke();rmCtx.setLineDash([14*dpr,18*dpr]);rmCtx.lineWidth=2*dpr;rmCtx.strokeStyle='rgba(255,255,255,.1)';rmCtx.stroke();rmCtx.setLineDash([]);rmCtx.restore();const curIdx=Math.floor(rmProgress*(rmPath.length-1));if(curIdx>0){rmCtx.save();rmCtx.lineWidth=5*dpr;rmCtx.lineCap='round';rmCtx.lineJoin='round';rmCtx.strokeStyle='#00E5FF';rmCtx.shadowColor='#00E5FF';rmCtx.shadowBlur=14*dpr;rmCtx.beginPath();rmCtx.moveTo(rmPath[0].x,rmPath[0].y);for(let i=1;i<=curIdx;i++)rmCtx.lineTo(rmPath[i].x,rmPath[i].y);rmCtx.stroke();rmCtx.restore();}route.forEach((cp,i)=>{const t=i/(route.length-1||1),pi=Math.round(t*(rmPath.length-1)),pp=rmPath[pi]||rmPts[i];const r=16*dpr,reached=rmProgress>=t-.002;rmCtx.save();if(reached){rmCtx.shadowColor=cp.color;rmCtx.shadowBlur=20*dpr;}rmCtx.beginPath();rmCtx.arc(pp.x,pp.y,r,0,Math.PI*2);rmCtx.strokeStyle=reached?cp.color:'rgba(255,255,255,.18)';rmCtx.lineWidth=2.5*dpr;rmCtx.stroke();rmCtx.beginPath();rmCtx.arc(pp.x,pp.y,r-2*dpr,0,Math.PI*2);rmCtx.fillStyle=reached?(i===route.length-1?'rgba(255,61,0,.35)':'rgba(0,229,255,.18)'):'rgba(10,10,15,.75)';rmCtx.fill();rmCtx.shadowBlur=0;rmCtx.font=`${Math.round(12*dpr)}px sans-serif`;rmCtx.textAlign='center';rmCtx.textBaseline='middle';rmCtx.fillStyle=reached?'#fff':'rgba(255,255,255,.28)';rmCtx.fillText(i===route.length-1?'🏁':(reached?'★':String(i)),pp.x,pp.y);const lx=pp.x>rmW*.5?pp.x-r-8*dpr:pp.x+r+8*dpr,align=pp.x>rmW*.5?'right':'left';rmCtx.font=`bold ${Math.round(11*dpr)}px 'Barlow Condensed',sans-serif`;rmCtx.textAlign=align;rmCtx.fillStyle=reached?'#F0F0F5':'rgba(255,255,255,.22)';rmCtx.fillText(cp.label,lx,pp.y-7*dpr);if(cp.rank&&reached){rmCtx.font=`${Math.round(10*dpr)}px 'Barlow Condensed',sans-serif`;rmCtx.fillStyle='#FFD600';rmCtx.fillText(cp.rank,lx,pp.y+9*dpr);}rmCtx.restore();});const cp=rmPath[curIdx]||rmPath[0];rmDrawCar(cp.x,cp.y,cp.angle||0);}
function rmDrawCar(x,y,angle){const ctx=rmCtx,dpr=devicePixelRatio,s=2.8*dpr;ctx.save();ctx.translate(x,y);ctx.rotate(angle+Math.PI/2);ctx.shadowColor='#FF3D00';ctx.shadowBlur=22*dpr;ctx.fillStyle='#FF3D00';rrect(ctx,-7*s,-11*s,14*s,22*s,3*s);ctx.fill();ctx.fillStyle='#cc2a00';rrect(ctx,-5*s,-7.5*s,10*s,13*s,2*s);ctx.fill();ctx.fillStyle='rgba(0,229,255,.75)';rrect(ctx,-4*s,-6.5*s,8*s,5*s,1.2*s);ctx.fill();ctx.shadowBlur=0;ctx.fillStyle='#1a1a1a';[[-9*s,-7*s],[9*s,-7*s],[-9*s,7*s],[9*s,7*s]].forEach(([wx,wy])=>{ctx.beginPath();ctx.ellipse(wx,wy,3.5*s,2.5*s,Math.PI/2,0,Math.PI*2);ctx.fill();});ctx.fillStyle='#FFD600';[[-4*s,-11*s],[4*s,-11*s]].forEach(([lx,ly])=>{ctx.beginPath();ctx.arc(lx,ly,1.8*s,0,Math.PI*2);ctx.fill();});ctx.restore();}
function rrect(ctx,x,y,w,h,r){ctx.beginPath();ctx.moveTo(x+r,y);ctx.lineTo(x+w-r,y);ctx.quadraticCurveTo(x+w,y,x+w,y+r);ctx.lineTo(x+w,y+h-r);ctx.quadraticCurveTo(x+w,y+h,x+w-r,y+h);ctx.lineTo(x+r,y+h);ctx.quadraticCurveTo(x,y+h,x,y+h-r);ctx.lineTo(x,y+r);ctx.quadraticCurveTo(x,y,x+r,y);ctx.closePath();}
function rmShowCP(i){const cp=route[i],t=i/(route.length-1||1),pi=Math.round(t*(rmPath.length-1)),pp=rmPath[pi]||rmPts[i];const popup=document.getElementById('cpPopup'),wrap=rmCanvas.parentElement.getBoundingClientRect(),dpr=devicePixelRatio;let lx=pp.x/dpr+(pp.x>rmW*.5?-230:22),ly=pp.y/dpr-65;lx=Math.max(8,Math.min(lx,wrap.width-240));ly=Math.max(8,Math.min(ly,wrap.height-110));popup.style.left=lx+'px';popup.style.top=ly+'px';document.getElementById('cpEv').textContent=cp.event;document.getElementById('cpNm').textContent=cp.label;document.getElementById('cpRk').textContent=cp.rank;popup.classList.add('show');clearTimeout(rmCpTimer);rmCpTimer=setTimeout(()=>popup.classList.remove('show'),3500);}
function rmLoop(ts){if(rmLastT===null)rmLastT=ts;const dt=(ts-rmLastT)/1000;rmLastT=ts;const spd=parseFloat(document.getElementById('spdSlider').value);rmProgress=Math.min(1,rmProgress+dt*spd*0.055);route.forEach((_,i)=>{const t=i/(route.length-1||1);if(rmProgress>=t&&!rmReached.has(i)){rmReached.add(i);if(i>0)rmShowCP(i);}});document.getElementById('progFill').style.width=(rmProgress*100).toFixed(1)+'%';rmDraw();if(rmProgress<1&&rmPlaying)rmRaf=requestAnimationFrame(rmLoop);else if(rmProgress>=1){rmPlaying=false;document.getElementById('rmPlayBtn').textContent='✔ Done';rmDraw();}}
function rmTogglePlay(){if(rmProgress>=1){rmReset();return;}rmPlaying=!rmPlaying;document.getElementById('rmPlayBtn').textContent=rmPlaying?'⏸ Pause':'▶ Play';if(rmPlaying){rmLastT=null;rmRaf=requestAnimationFrame(rmLoop);}else cancelAnimationFrame(rmRaf);}
function rmReset(){cancelAnimationFrame(rmRaf);rmProgress=0;rmPlaying=false;rmLastT=null;rmReached.clear();document.getElementById('rmPlayBtn').textContent='▶ Play';document.getElementById('progFill').style.width='0%';document.getElementById('cpPopup').classList.remove('show');rmDraw();}
function openRoute(){document.getElementById('routePage').classList.add('open');document.body.style.overflow='hidden';setTimeout(()=>{rmResize();rmDraw();},60);}
function closeRoute(){document.getElementById('routePage').classList.remove('open');document.body.style.overflow='';cancelAnimationFrame(rmRaf);rmPlaying=false;document.getElementById('rmPlayBtn').textContent='▶ Play';}
window.addEventListener('resize',()=>{if(document.getElementById('routePage').classList.contains('open'))rmResize();});

/* ── HELPERS ── */
function rankIcon(rank=''){const r=rank.toLowerCase();if(r.includes('1st')||r.includes('first')||r.includes('gold'))return'🥇';if(r.includes('2nd')||r.includes('second')||r.includes('silver'))return'🥈';if(r.includes('3rd')||r.includes('third')||r.includes('bronze'))return'🥉';return'🏆';}
function esc(s=''){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}
function toast(msg,type='info',dur=3000){const el=document.createElement('div');el.className=`toast ${type}`;el.textContent=msg;document.getElementById('toastBox').appendChild(el);setTimeout(()=>{el.style.opacity='0';el.style.transition='.3s';setTimeout(()=>el.remove(),300);},dur);}
function animCount(id,target){const el=document.getElementById(id);let v=0;const step=Math.max(1,target/40);const t=setInterval(()=>{v=Math.min(v+step,target);el.textContent=Math.floor(v);if(v>=target)clearInterval(t);},28);}

/* cursor */
const cur=document.getElementById('cursor'),ring=document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px';});
(function loop(){rx+=(mx-rx)*.12;ry+=(my-ry)*.12;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(loop);})();
document.querySelectorAll('a,button,label,.cert-card,.member-card').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur.style.width='18px';cur.style.height='18px';cur.style.background='var(--gold)';ring.style.borderColor='rgba(255,214,0,.6)';});
  el.addEventListener('mouseleave',()=>{cur.style.width='10px';cur.style.height='10px';cur.style.background='var(--fire)';ring.style.borderColor='rgba(255,61,0,.55)';});
});

/* ── INIT ── */
initApp();
</script>
</body>
</html>
