<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VendVerd · Economia Circular para Condomínio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Lato:wght@300;400;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --cream:#f5f0e8;--paper:#ede7d9;--sand:#d4c4a8;--terra:#b5601e;--terra-dk:#8a4012;
  --moss:#3d5a3e;--moss-lt:#5c7d5e;--moss-pale:#e8f0e8;--charcoal:#1e2420;--ink:#2d3b2e;
  --muted:#6b7c6d;--warm-wh:#faf7f2;--accent:#c8773a;--verd-green:#2e7d32;
  --display:'Playfair Display',Georgia,serif;--body:'Lato',sans-serif;--mono:'DM Mono',monospace;
  --r-sm:6px;--r-md:14px;--r-lg:24px;--r-xl:40px;--r-full:999px;
  --shadow-sm:0 2px 8px rgba(30,36,32,.07);--shadow-md:0 6px 24px rgba(30,36,32,.10);--shadow-lg:0 16px 48px rgba(30,36,32,.14);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:var(--body);background:var(--cream);color:var(--ink);line-height:1.6;min-height:100vh;display:flex;flex-direction:column;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3CfeColorMatrix type='saturate' values='0'/%3E%3C/filter%3E%3Crect width='400' height='400' filter='url(%23noise)' opacity='0.035'/%3E%3C/svg%3E")}
.nav{background:var(--charcoal);padding:0 3rem;display:flex;align-items:center;justify-content:space-between;height:64px;position:sticky;top:0;z-index:200;box-shadow:0 1px 0 rgba(255,255,255,.04),0 4px 24px rgba(0,0,0,.3)}
.nav-logo{display:flex;align-items:baseline;gap:6px;text-decoration:none}
.nav-logo-mark{font-family:var(--display);font-size:1.85rem;font-weight:900;color:var(--cream);letter-spacing:-.04em;line-height:1}
.nav-logo-mark em{color:var(--verd-green);font-style:normal}
.nav-logo-sub{font-family:var(--mono);font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--sand);opacity:.7;padding-bottom:2px}
.nav-links{display:flex;align-items:center;gap:2.2rem}
.nav-links a{font-family:var(--body);font-size:.82rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--sand);text-decoration:none;transition:color .15s;opacity:.8}
.nav-links a:hover{color:var(--cream);opacity:1}
.btn-nav-cta{background:var(--terra);color:var(--cream)!important;padding:.5rem 1.5rem;border-radius:var(--r-full);display:flex;align-items:center;gap:6px;transition:background .15s,transform .1s!important;box-shadow:0 4px 16px rgba(181,96,30,.4);opacity:1!important}
.btn-nav-cta:hover{background:var(--terra-dk)!important;transform:translateY(-1px)}
.nav-icon{font-size:1.1rem;font-weight:400;line-height:1}
.hero{background:var(--moss);padding:4rem 3rem 3.5rem;display:grid;grid-template-columns:1fr auto;align-items:end;gap:3rem;overflow:hidden;position:relative;border-bottom:1px solid rgba(255,255,255,.05)}
.hero::before{content:'';position:absolute;top:-60px;right:-80px;width:360px;height:360px;border-radius:50%;background:radial-gradient(circle,rgba(200,119,58,.18),transparent 70%);pointer-events:none}
.hero::after{content:'';position:absolute;bottom:-60px;left:28%;width:200px;height:200px;border-radius:50%;background:rgba(245,240,232,.04);pointer-events:none}
.hero-eyebrow{font-family:var(--mono);font-size:.68rem;letter-spacing:.24em;text-transform:uppercase;color:var(--sand);margin-bottom:1rem;display:flex;align-items:center;gap:10px;opacity:.85}
.hero-eyebrow::before{content:'';display:inline-block;width:32px;height:1px;background:var(--terra)}
.hero-h1{font-family:var(--display);font-size:clamp(2rem,3.8vw,3rem);font-weight:900;color:var(--cream);line-height:1.12;letter-spacing:-.025em;margin-bottom:1rem}
.hero-h1 em{color:var(--terra);font-style:italic}
.hero-sub{font-size:.97rem;color:var(--sand);max-width:440px;line-height:1.8;opacity:.9}
.hero-stats{display:flex;flex-direction:column;gap:.8rem;align-items:flex-end}
.hero-stat{text-align:right;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.08);border-radius:var(--r-md);padding:.85rem 1.5rem;min-width:130px;transition:background .2s}
.hero-stat:hover{background:rgba(255,255,255,.1)}
.hero-stat-num{font-family:var(--display);font-size:2.1rem;font-weight:700;color:var(--terra);line-height:1}
.hero-stat-lbl{font-family:var(--mono);font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;color:var(--sand);margin-top:3px;opacity:.7}
.wrap{max-width:1280px;margin:0 auto;padding:0 3rem;flex:1}
.filter-bar{background:var(--warm-wh);border:1px solid rgba(212,196,168,.6);border-radius:var(--r-lg);padding:.9rem 1.2rem;margin:2.2rem 0 2rem;display:flex;flex-wrap:wrap;align-items:center;gap:.9rem;box-shadow:var(--shadow-sm)}
.search-box{flex:2;min-width:220px;display:flex;align-items:center;gap:8px;background:var(--cream);border:1.5px solid rgba(212,196,168,.5);border-radius:var(--r-full);padding:.32rem .32rem .32rem 1rem;transition:border-color .15s,box-shadow .15s}
.search-box:focus-within{border-color:var(--moss);box-shadow:0 0 0 3px rgba(61,90,62,.1)}
.search-icon{color:var(--muted);font-size:1.05rem;line-height:1;flex-shrink:0}
.search-box input{border:none;background:transparent;font-family:var(--body);font-size:.93rem;color:var(--ink);width:100%;outline:none}
.search-box input::placeholder{color:var(--muted)}
.btn-filter{background:var(--moss);color:var(--cream);border:none;border-radius:var(--r-full);padding:.6rem 1.5rem;font-family:var(--body);font-weight:700;font-size:.82rem;letter-spacing:.06em;text-transform:uppercase;display:flex;align-items:center;gap:6px;cursor:pointer;transition:background .15s,transform .1s}
.btn-filter:hover{background:var(--terra);transform:translateY(-1px)}
.section-head{display:flex;align-items:baseline;justify-content:space-between;gap:1rem;margin-bottom:1.4rem;flex-wrap:wrap}
.section-head h2{font-family:var(--display);font-size:1.6rem;font-weight:700;color:var(--ink);letter-spacing:-.025em}
.view-toggle{display:flex;gap:3px;background:var(--paper);border-radius:var(--r-full);padding:3px;border:1px solid rgba(212,196,168,.5)}
.vbtn{background:transparent;border:none;border-radius:var(--r-full);width:34px;height:34px;display:flex;align-items:center;justify-content:center;cursor:pointer;color:var(--muted);font-size:.9rem;transition:.15s}
.vbtn.on{background:var(--charcoal);color:var(--cream)}
.cards{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:1.5rem;margin-bottom:3rem}
.cards.list{grid-template-columns:1fr}
.cards.list .card{flex-direction:row}
.cards.list .card-thumb{width:200px;flex-shrink:0;height:auto;min-height:160px}
.card{background:var(--warm-wh);border-radius:var(--r-lg);overflow:hidden;display:flex;flex-direction:column;border:1px solid rgba(237,231,217,.8);box-shadow:var(--shadow-sm);cursor:pointer;transition:transform .2s ease,box-shadow .2s ease,border-color .2s;position:relative}
.card:hover{transform:translateY(-4px);box-shadow:var(--shadow-lg);border-color:rgba(212,196,168,.7)}
.card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--terra),var(--verd-green));opacity:0;transition:opacity .2s;z-index:1}
.card:hover::before{opacity:1}
.card-thumb{height:185px;background:linear-gradient(135deg,var(--paper) 0%,var(--sand) 100%);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.card-thumb img{width:100%;height:100%;object-fit:cover;display:block;transition:transform .4s ease}
.card:hover .card-thumb img{transform:scale(1.03)}
.card-thumb-emoji{font-size:3.8rem;opacity:.6}
.card-badge{position:absolute;top:10px;left:10px;background:rgba(30,36,32,.7);backdrop-filter:blur(8px);color:var(--cream);font-family:var(--mono);font-size:.6rem;letter-spacing:.1em;text-transform:uppercase;padding:.26rem .7rem;border-radius:var(--r-full);display:flex;align-items:center;gap:4px;z-index:2}
.card-photo-count{position:absolute;bottom:10px;right:10px;background:rgba(0,0,0,.48);color:#fff;font-family:var(--mono);font-size:.62rem;padding:.2rem .6rem;border-radius:var(--r-full);backdrop-filter:blur(4px);display:flex;align-items:center;gap:4px;z-index:2}
.card-body{padding:1.1rem 1.2rem 1.3rem;flex:1;display:flex;flex-direction:column}
.card-cat{font-family:var(--mono);font-size:.62rem;letter-spacing:.2em;text-transform:uppercase;color:var(--terra);font-weight:500;margin-bottom:.25rem}
.card-title{font-family:var(--display);font-size:1.1rem;font-weight:700;color:var(--ink);line-height:1.25;margin-bottom:.4rem;letter-spacing:-.01em}
.card-desc{font-size:.85rem;color:var(--muted);line-height:1.65;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden;margin-bottom:auto}
.card-foot{display:flex;align-items:center;justify-content:space-between;margin-top:.8rem;padding-top:.8rem;border-top:1px solid rgba(237,231,217,.9)}
.card-price{font-family:var(--display);font-size:1.25rem;font-weight:700;color:var(--moss)}
.card-local{font-size:.74rem;color:var(--muted);display:flex;align-items:center;gap:3px}
.card-local-icon{font-size:.9rem}
.btn-talk{margin-top:.65rem;background:transparent;border:1.5px solid var(--moss);color:var(--moss);border-radius:var(--r-full);padding:.4rem 1rem;font-family:var(--body);font-weight:700;font-size:.78rem;display:flex;align-items:center;justify-content:center;gap:5px;cursor:pointer;transition:.15s;width:100%}
.btn-talk:hover{background:var(--moss);color:var(--cream)}
.state-box{grid-column:1/-1;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:4rem 2rem;background:var(--warm-wh);border-radius:var(--r-xl);border:1px solid var(--paper);text-align:center;color:var(--muted)}
.state-box .big-icon{font-size:3rem;margin-bottom:1rem;opacity:.5}
.state-box h3{font-family:var(--display);font-size:1.4rem;color:var(--ink);margin-bottom:.4rem}
.state-box p{font-size:.9rem;max-width:320px}
.spinner-ring{width:44px;height:44px;border:3px solid var(--sand);border-top-color:var(--terra);border-radius:50%;animation:spin 1s linear infinite;margin-bottom:1rem}
@keyframes spin{to{transform:rotate(360deg)}}
.overlay{display:none;position:fixed;inset:0;background:rgba(20,28,22,.7);z-index:900;align-items:center;justify-content:center;padding:1.5rem;backdrop-filter:blur(6px)}
.overlay.open{display:flex}
@keyframes modalIn{from{opacity:0;transform:translateY(18px) scale(.97)}to{opacity:1;transform:none}}
.modal-contato-block{display:flex;align-items:center;gap:1rem;background:var(--paper);border:1px solid rgba(212,196,168,.5);border-radius:var(--r-md);padding:.9rem 1.2rem;margin-top:1rem;transition:border-color .15s}
.modal-contato-block:hover{border-color:var(--moss)}
.modal-contato-icon{font-size:1.5rem;line-height:1}
.modal-contato-lbl{font-family:var(--mono);font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);margin-bottom:2px}
.modal-contato-val{font-family:var(--body);font-size:1rem;font-weight:700;color:var(--ink);word-break:break-all}
.form-note{font-family:var(--mono);font-size:.65rem;letter-spacing:.08em;color:rgba(212,196,168,.45);margin-top:.8rem}
.btn-retry{background:var(--terra);color:var(--cream);border:none;border-radius:var(--r-full);padding:.65rem 1.8rem;font-family:var(--body);font-weight:700;font-size:.88rem;cursor:pointer;margin-top:1rem;transition:.15s}
.btn-retry:hover{background:var(--terra-dk)}
.toast{position:fixed;bottom:2rem;right:2rem;background:var(--charcoal);color:var(--cream);padding:.85rem 1.5rem;border-radius:var(--r-full);display:flex;align-items:center;gap:.8rem;font-family:var(--body);font-size:.88rem;font-weight:600;box-shadow:var(--shadow-lg);transform:translateY(120px);transition:transform .3s cubic-bezier(.34,1.56,.64,1);z-index:1100;border-left:3px solid var(--verd-green);max-width:360px}
.toast.show{transform:translateY(0)}
.toast.err{border-left-color:var(--terra)}
.toast-icon{font-size:1rem}
.footer{background:var(--charcoal);color:var(--sand);margin-top:2rem;padding-top:3.5rem;padding-bottom:1.5rem;border-top:1px solid rgba(255,255,255,.04)}
.footer-inner{max-width:1100px;margin:0 auto;padding:0 3rem}
.footer-grid{display:grid;grid-template-columns:1.4fr 1fr 1fr 1fr;gap:2.5rem;margin-bottom:3rem}
.footer-brand-logo{display:flex;align-items:center;gap:10px;margin-bottom:1rem}
.footer-brand-icon{background:var(--moss);border-radius:10px;width:34px;height:34px;display:flex;align-items:center;justify-content:center;font-size:1rem}
.footer-brand-name{font-family:var(--display);font-size:1.25rem;font-weight:900;color:var(--cream);letter-spacing:-.025em}
.footer-brand-name em{color:var(--verd-green);font-style:normal}
.footer-tagline{font-size:.855rem;color:var(--muted);line-height:1.65}
.footer-col-title{font-family:var(--mono);font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;color:var(--cream);font-weight:500;margin-bottom:1rem;opacity:.8}
.footer-links{list-style:none;display:flex;flex-direction:column;gap:.5rem}
.footer-links a{font-size:.855rem;color:var(--muted);text-decoration:none;transition:color .15s}
.footer-links a:hover{color:var(--moss-lt)}
.footer-social{display:flex;gap:.5rem;margin-bottom:1.2rem}
.footer-social-btn{width:34px;height:34px;background:rgba(255,255,255,.05);border-radius:var(--r-sm);display:flex;align-items:center;justify-content:center;text-decoration:none;font-size:.95rem;color:var(--muted);transition:background .15s,color .15s}
.footer-social-btn:hover{background:var(--moss);color:var(--cream)}
.footer-badge{display:flex;align-items:center;gap:6px;background:rgba(46,125,50,.15);border:1px solid rgba(46,125,50,.25);border-radius:8px;padding:.5rem .85rem;font-family:var(--mono);font-size:.62rem;letter-spacing:.08em;color:var(--moss-lt)}
.footer-bottom{border-top:1px solid rgba(255,255,255,.06);padding-top:1.5rem;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem}
.footer-copy{font-family:var(--mono);font-size:.65rem;letter-spacing:.04em;color:var(--muted)}
.footer-made{font-family:var(--mono);font-size:.62rem;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.footer-made em{color:var(--verd-green);font-style:normal}
@media(max-width:860px){.footer-grid{grid-template-columns:1fr 1fr}}
@media(max-width:520px){.footer-grid{grid-template-columns:1fr}.footer-bottom{flex-direction:column;text-align:center}}
.hero-badges{display:flex;flex-wrap:wrap;gap:.7rem;margin-top:1.6rem}
.hero-badge-item{display:flex;align-items:center;gap:10px;background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.08);border-radius:var(--r-md);padding:.7rem 1.1rem;backdrop-filter:blur(6px);transition:background .2s}
.hero-badge-item:hover{background:rgba(255,255,255,.13)}
.hero-badge-icon{font-size:1.25rem;line-height:1}
.hero-badge-title{font-family:var(--body);font-size:.83rem;font-weight:700;color:var(--cream);line-height:1.2}
.hero-badge-sub{font-family:var(--mono);font-size:.58rem;letter-spacing:.14em;text-transform:uppercase;color:var(--sand);margin-top:2px;opacity:.75}
.impact-banner{background:var(--charcoal);border-radius:var(--r-xl);padding:2.6rem 2.5rem;text-align:center;margin-bottom:2.5rem;position:relative;overflow:hidden;border:1px solid rgba(255,255,255,.04)}
.impact-line{position:absolute;top:0;left:50%;transform:translateX(-50%);width:50%;height:1px;background:linear-gradient(90deg,transparent,var(--verd-green),transparent);opacity:.4}
.impact-title{font-family:var(--display);font-size:1.3rem;font-weight:700;color:var(--cream);letter-spacing:-.015em;margin-bottom:2rem;opacity:.95}
.impact-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.5rem}
.impact-num{font-family:var(--display);font-size:2.1rem;font-weight:900;color:var(--moss-lt);line-height:1;margin-bottom:.3rem}
.impact-lbl{font-family:var(--mono);font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;color:var(--muted)}
@media(max-width:600px){.impact-grid{grid-template-columns:repeat(2,1fr)}}
.filter-count{background:var(--cream);color:var(--moss);border-radius:50%;width:18px;height:18px;font-size:.68rem;font-weight:900;display:inline-flex;align-items:center;justify-content:center;margin-left:2px}
.btn-filter-clear{background:transparent;border:1.5px solid rgba(212,196,168,.6);color:var(--muted);border-radius:var(--r-full);width:38px;height:38px;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.82rem;transition:.15s;flex-shrink:0}
.btn-filter-clear:hover{background:var(--terra);color:var(--cream);border-color:var(--terra)}
.fm-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.6);z-index:800;align-items:flex-end;justify-content:center;backdrop-filter:blur(5px);padding:0}
@media(min-width:600px){.fm-overlay{align-items:center;padding:1.5rem}}
.fm-overlay.open{display:flex}
.fm-box{background:var(--warm-wh);width:100%;max-width:500px;border-radius:var(--r-xl) var(--r-xl) 0 0;overflow:hidden;display:flex;flex-direction:column;box-shadow:var(--shadow-lg);animation:fmSlideUp .3s cubic-bezier(.32,1.25,.6,1);max-height:92vh}
@media(min-width:600px){.fm-box{border-radius:var(--r-xl);animation:fmFadeIn .25s ease}}
@keyframes fmSlideUp{from{opacity:0;transform:translateY(40px)}to{opacity:1;transform:none}}
@keyframes fmFadeIn{from{opacity:0;transform:scale(.96) translateY(12px)}to{opacity:1;transform:none}}
.fm-head{display:flex;align-items:center;justify-content:space-between;padding:1.3rem 1.5rem;border-bottom:1px solid var(--paper);flex-shrink:0}
.fm-head-left{display:flex;align-items:center;gap:8px}
.fm-title{font-family:var(--display);font-size:1.25rem;font-weight:700;color:var(--ink);letter-spacing:-.015em}
.fm-reset-btn{background:transparent;border:none;width:28px;height:28px;border-radius:var(--r-sm);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.95rem;color:var(--muted);transition:.15s}
.fm-reset-btn:hover{background:var(--moss-pale);color:var(--moss)}
.fm-close-btn{background:var(--paper);border:1px solid rgba(212,196,168,.5);width:32px;height:32px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.8rem;color:var(--muted);transition:.15s}
.fm-close-btn:hover{background:var(--terra);color:var(--cream);border-color:var(--terra)}
.fm-body{padding:1.3rem 1.5rem;overflow-y:auto;flex:1;display:flex;flex-direction:column;gap:1.6rem}
.fm-condo-row{display:flex;align-items:center;justify-content:space-between;gap:1rem;background:var(--moss-pale);border:1px solid rgba(61,90,62,.15);border-radius:var(--r-md);padding:.95rem 1.1rem}
.fm-condo-title{font-family:var(--body);font-size:.9rem;font-weight:700;color:var(--moss);line-height:1.3}
.fm-condo-sub{font-size:.76rem;color:var(--moss-lt);margin-top:2px}
.fm-toggle{position:relative;width:46px;height:24px;border-radius:var(--r-full);background:var(--sand);border:none;cursor:pointer;transition:background .2s;flex-shrink:0}
.fm-toggle.on{background:var(--verd-green)}
.fm-toggle-knob{position:absolute;top:3px;left:3px;width:18px;height:18px;border-radius:50%;background:var(--warm-wh);box-shadow:0 1px 4px rgba(0,0,0,.2);transition:transform .2s cubic-bezier(.34,1.56,.64,1)}
.fm-toggle.on .fm-toggle-knob{transform:translateX(22px)}
.fm-section-title{font-family:var(--mono);font-size:.63rem;letter-spacing:.2em;text-transform:uppercase;color:var(--muted);font-weight:500;margin-bottom:.7rem}
.fm-chips{display:flex;flex-wrap:wrap;gap:.45rem}
.fm-chips-row{flex-wrap:nowrap}
.fm-chip{background:var(--cream);border:1.5px solid rgba(212,196,168,.6);border-radius:var(--r-md);padding:.42rem .95rem;font-family:var(--body);font-size:.83rem;font-weight:600;color:var(--muted);cursor:pointer;transition:.15s;white-space:nowrap}
.fm-chip:hover{border-color:var(--moss);color:var(--moss);background:var(--moss-pale)}
.fm-chip.on{background:var(--moss);border-color:var(--moss);color:var(--cream);box-shadow:var(--shadow-sm)}
.fm-chips-row .fm-chip{flex:1;text-align:center}
.fm-price-row{display:flex;align-items:flex-end;gap:.8rem}
.fm-price-field{flex:1;display:flex;flex-direction:column;gap:4px}
.fm-price-lbl{font-family:var(--mono);font-size:.6rem;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);font-weight:700}
.fm-price-input-wrap{display:flex;align-items:center;background:var(--cream);border:1.5px solid rgba(212,196,168,.6);border-radius:var(--r-md);overflow:hidden;transition:border-color .15s}
.fm-price-input-wrap:focus-within{border-color:var(--moss);box-shadow:0 0 0 3px rgba(61,90,62,.1)}
.fm-price-prefix{padding:.6rem .7rem .6rem .9rem;font-family:var(--mono);font-size:.7rem;color:var(--muted);font-weight:500;flex-shrink:0}
.fm-price-input-wrap input{border:none;background:transparent;padding:.6rem .8rem .6rem 0;font-family:var(--body);font-size:.9rem;color:var(--ink);outline:none;width:100%}
.fm-price-sep{width:14px;height:1px;background:var(--sand);flex-shrink:0;margin-bottom:18px}
.fm-foot{display:flex;gap:.7rem;padding:1.1rem 1.5rem;border-top:1px solid var(--paper);background:var(--warm-wh);flex-shrink:0}
.fm-btn-cancel{flex:1;padding:.85rem;background:transparent;border:1.5px solid rgba(212,196,168,.6);border-radius:var(--r-lg);font-family:var(--body);font-weight:700;font-size:.88rem;color:var(--muted);cursor:pointer;transition:.15s}
.fm-btn-cancel:hover{background:var(--paper);color:var(--ink)}
.fm-btn-apply{flex:1.6;padding:.85rem;background:var(--moss);border:none;border-radius:var(--r-lg);font-family:var(--body);font-weight:900;font-size:.93rem;color:var(--cream);cursor:pointer;transition:background .15s,transform .1s;display:flex;align-items:center;justify-content:center;gap:6px;box-shadow:0 5px 18px rgba(61,90,62,.22)}
.fm-btn-apply:hover{background:var(--terra);transform:translateY(-1px)}
.card-condition{display:inline-flex;align-items:center;background:rgba(255,255,255,.88);backdrop-filter:blur(4px);padding:.2rem .55rem;border-radius:var(--r-sm);font-family:var(--mono);font-size:.6rem;letter-spacing:.08em;font-weight:700;color:var(--moss);box-shadow:var(--shadow-sm)}
@media(max-width:700px){#modalDetalhes{align-items:flex-end;padding:0}}
.pd-box{background:var(--warm-wh);width:100%;max-width:860px;max-height:90vh;border-radius:var(--r-xl);overflow:hidden;display:flex;flex-direction:row;box-shadow:var(--shadow-lg);animation:modalIn .3s cubic-bezier(.32,1.25,.6,1);position:relative}
.pd-img-col{width:46%;flex-shrink:0;background:var(--paper);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.pd-img-col img{width:100%;height:100%;object-fit:cover;display:block}
.pd-img-placeholder{display:flex;flex-direction:column;align-items:center;gap:.6rem;color:var(--muted)}
.pd-img-placeholder span{font-size:4rem;opacity:.45}
.pd-img-placeholder p{font-family:var(--mono);font-size:.68rem;letter-spacing:.1em}
.pd-close-mobile{display:none;position:absolute;top:1rem;left:1rem;z-index:10;background:rgba(255,255,255,.85);border:none;width:34px;height:34px;border-radius:50%;font-size:.85rem;cursor:pointer;color:var(--ink);box-shadow:var(--shadow-sm);align-items:center;justify-content:center;transition:.15s}
.pd-close-mobile:hover{background:var(--terra);color:var(--cream)}
.pd-info-col{flex:1;display:flex;flex-direction:column;position:relative;min-width:0;overflow:hidden}
.pd-close-desktop{position:absolute;top:1rem;right:1rem;z-index:10;background:var(--paper);border:1px solid rgba(212,196,168,.5);width:32px;height:32px;border-radius:50%;font-size:.78rem;cursor:pointer;color:var(--muted);display:flex;align-items:center;justify-content:center;transition:.15s}
.pd-close-desktop:hover{background:var(--terra);color:var(--cream);border-color:var(--terra)}
.pd-scroll{flex:1;overflow-y:auto;padding:1.8rem 1.6rem 1rem}
.pd-condition-badge{display:inline-block;background:var(--moss-pale);border:1px solid rgba(61,90,62,.15);color:var(--moss);font-family:var(--mono);font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;font-weight:700;padding:.26rem .75rem;border-radius:var(--r-full);margin-bottom:.5rem}
.pd-title{font-family:var(--display);font-size:1.7rem;font-weight:900;color:var(--ink);letter-spacing:-.025em;line-height:1.15;margin-bottom:.2rem}
.pd-price{font-family:var(--display);font-size:1.9rem;font-weight:900;color:var(--moss);letter-spacing:-.02em;margin:.7rem 0 1.2rem}
.pd-section{margin-bottom:1.2rem}
.pd-section-label{font-family:var(--mono);font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--muted);font-weight:700;margin-bottom:.5rem;display:flex;align-items:center;gap:5px}
.pd-seller-card{display:flex;align-items:center;gap:.85rem;background:var(--paper);border-radius:var(--r-md);padding:.85rem .95rem}
.pd-seller-avatar{width:42px;height:42px;border-radius:50%;background:linear-gradient(135deg,var(--moss),var(--moss-lt));display:flex;align-items:center;justify-content:center;font-family:var(--display);font-size:1.05rem;font-weight:700;color:var(--cream);flex-shrink:0}
.pd-seller-name{font-weight:700;font-size:.93rem;color:var(--ink);display:flex;align-items:center;gap:6px}
.pd-seller-rating{background:rgba(245,158,11,.1);border:1px solid rgba(245,158,11,.18);color:#b45309;font-family:var(--mono);font-size:.58rem;font-weight:700;padding:.14rem .42rem;border-radius:var(--r-sm);display:inline-flex;align-items:center;gap:2px}
.pd-seller-local{font-size:.8rem;color:var(--muted);margin-top:2px;display:flex;align-items:center;gap:3px}
.pd-verified{margin-left:auto;color:var(--moss);font-size:1.05rem;flex-shrink:0}
.pd-desc{font-size:.9rem;color:var(--ink);line-height:1.8;white-space:pre-wrap}
.pd-tips-box{background:rgba(245,158,11,.06);border:1px solid rgba(245,158,11,.18);border-radius:var(--r-md);padding:.95rem 1.05rem}
.pd-tips-header{font-family:var(--mono);font-size:.63rem;letter-spacing:.14em;text-transform:uppercase;color:#92400e;font-weight:700;margin-bottom:.65rem;display:flex;align-items:center;gap:5px}
.pd-tips-list{list-style:none;display:flex;flex-direction:column;gap:.42rem}
.pd-tips-list li{font-size:.82rem;color:#92400e;display:flex;align-items:flex-start;gap:6px;line-height:1.5}
.pd-tips-list li::before{content:'›';font-weight:700;font-size:.88rem;flex-shrink:0;margin-top:1px}
.pd-tips-skel{display:flex;flex-direction:column;gap:6px}
.pd-skel-line{height:11px;background:rgba(245,158,11,.18);border-radius:var(--r-sm);animation:skelPulse 1.4s ease-in-out infinite}
@keyframes skelPulse{0%,100%{opacity:1}50%{opacity:.4}}
.pd-foot{padding:.9rem 1.6rem 1.2rem;border-top:1px solid var(--paper);background:var(--warm-wh);flex-shrink:0}
.pd-btn-interest{width:100%;background:var(--moss);color:var(--cream);border:none;border-radius:var(--r-lg);padding:.9rem;font-family:var(--body);font-weight:900;font-size:.97rem;display:flex;align-items:center;justify-content:center;gap:8px;cursor:pointer;transition:background .15s,transform .1s;box-shadow:0 5px 18px rgba(61,90,62,.22)}
.pd-btn-interest:hover{background:var(--terra);transform:translateY(-1px)}
.pd-btn-interest:active{transform:scale(.98)}
@media(max-width:700px){
  .pd-box{flex-direction:column;max-height:95vh;border-radius:var(--r-xl) var(--r-xl) 0 0;align-self:flex-end;max-width:100%}
  .pd-img-col{width:100%;height:230px;flex-shrink:0}
  .pd-close-mobile{display:flex}
  .pd-close-desktop{display:none}
  .pd-scroll{padding:1.3rem 1.3rem .5rem}
  .pd-foot{padding:.75rem 1.3rem 1.1rem}
  .pd-title{font-size:1.35rem}
  .pd-price{font-size:1.55rem;margin:.5rem 0 .9rem}
}
.pf-header-card{background:var(--warm-wh);border:1px solid rgba(237,231,217,.8);border-radius:var(--r-xl);padding:2.2rem 2rem 1.6rem;display:flex;flex-direction:column;align-items:center;text-align:center;margin-top:1.6rem;box-shadow:var(--shadow-md)}
.pf-avatar-wrap{position:relative;margin-bottom:1rem}
.pf-avatar{width:88px;height:88px;border-radius:50%;object-fit:cover;border:3px solid var(--moss-pale);box-shadow:var(--shadow-md);display:block}
.pf-verified-dot{position:absolute;bottom:2px;right:2px;background:var(--verd-green);border:2px solid var(--warm-wh);border-radius:50%;width:24px;height:24px;display:flex;align-items:center;justify-content:center;font-size:.7rem}
.pf-name{font-family:var(--display);font-size:1.5rem;font-weight:900;color:var(--ink);letter-spacing:-.025em;line-height:1.15}
.pf-condo{font-size:.86rem;color:var(--moss-lt);font-weight:600;margin-top:.2rem;margin-bottom:1.4rem}
.pf-stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;width:100%;padding-top:1.2rem;border-top:1px solid rgba(237,231,217,.9)}
.pf-stat{display:flex;flex-direction:column;align-items:center;gap:3px}
.pf-stat-btn{background:transparent;border:none;cursor:pointer;border-radius:var(--r-md);padding:.35rem;transition:background .15s}
.pf-stat-btn:hover{background:var(--moss-pale)}
.pf-stat-num{font-family:var(--display);font-size:1.2rem;font-weight:900;color:var(--moss);line-height:1}
.pf-stat-rating{color:#b45309}
.pf-stat-lbl{font-family:var(--mono);font-size:.56rem;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);font-weight:700}
.pf-tabs{display:flex;background:var(--paper);border-radius:var(--r-lg);padding:.25rem;margin-top:1.2rem;gap:.2rem}
.pf-tab{flex:1;padding:.65rem;background:transparent;border:none;border-radius:var(--r-md);font-family:var(--body);font-weight:700;font-size:.86rem;color:var(--muted);cursor:pointer;transition:background .15s,color .15s,box-shadow .15s}
.pf-tab.on{background:var(--warm-wh);color:var(--moss);box-shadow:var(--shadow-sm)}
.pf-tab:not(.on):hover{color:var(--ink)}
.pf-panel{margin-top:.9rem;animation:pfFadeIn .25s ease}
@keyframes pfFadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.pf-menu{display:flex;flex-direction:column;gap:.4rem}
.pf-menu-item{width:100%;background:var(--warm-wh);border:1px solid rgba(237,231,217,.8);border-radius:var(--r-lg);padding:.95rem 1.15rem;display:flex;align-items:center;gap:.9rem;cursor:pointer;text-align:left;transition:border-color .15s,box-shadow .15s,transform .12s}
.pf-menu-item:hover{border-color:rgba(212,196,168,.7);box-shadow:var(--shadow-sm);transform:translateX(2px)}
.pf-menu-item:hover .pf-menu-icon{transform:scale(1.1)}
.pf-menu-danger .pf-menu-label{color:#dc2626}
.pf-menu-danger:hover{border-color:rgba(220,38,38,.2)}
.pf-menu-icon{width:36px;height:36px;border-radius:var(--r-md);display:flex;align-items:center;justify-content:center;font-size:1.05rem;flex-shrink:0;transition:transform .15s}
.pf-icon-blue{background:rgba(59,130,246,.09)}
.pf-icon-rose{background:rgba(244,63,94,.09)}
.pf-icon-green{background:var(--moss-pale)}
.pf-icon-gray{background:var(--paper)}
.pf-icon-red{background:rgba(220,38,38,.07)}
.pf-menu-label{font-weight:700;font-size:.91rem;color:var(--ink);flex:1}
.pf-menu-arrow{font-size:1.1rem;color:var(--sand);font-weight:700;transition:color .15s}
.pf-menu-item:hover .pf-menu-arrow{color:var(--moss)}
.pf-reviews-head{display:flex;align-items:center;justify-content:space-between;padding:0 .2rem .4rem;margin-bottom:.7rem}
.pf-reviews-title{font-family:var(--display);font-size:1.05rem;font-weight:700;color:var(--ink)}
.pf-stars-display{display:flex;gap:2px;font-size:.82rem}
.pf-reviews-list{display:flex;flex-direction:column;gap:.8rem}
.pf-review-card{background:var(--warm-wh);border:1px solid rgba(237,231,217,.8);border-radius:var(--r-lg);padding:1.1rem 1.2rem}
.pf-review-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:.65rem}
.pf-review-user{display:flex;align-items:center;gap:.55rem}
.pf-review-avatar{width:32px;height:32px;border-radius:50%;object-fit:cover;border:1.5px solid rgba(237,231,217,.9)}
.pf-review-avatar-fallback{width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,var(--moss),var(--moss-lt));display:flex;align-items:center;justify-content:center;font-family:var(--display);font-size:.88rem;font-weight:700;color:var(--cream)}
.pf-reviewer-name{font-weight:700;font-size:.86rem;color:var(--ink);line-height:1.2}
.pf-reviewer-date{font-family:var(--mono);font-size:.58rem;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.pf-review-stars{display:flex;gap:1px;font-size:.68rem}
.pf-review-comment{font-size:.85rem;color:var(--muted);line-height:1.65;font-style:italic;display:flex;gap:6px}
.pf-review-quote{color:var(--sand);font-size:1.05rem;line-height:1;flex-shrink:0}
.pf-footer-note{text-align:center;padding:2rem 0 2.5rem;display:flex;flex-direction:column;gap:.2rem}
.pf-footer-note p{font-family:var(--mono);font-size:.62rem;letter-spacing:.08em;color:var(--muted)}
.nav-tab{position:relative}
.nav-badge{position:absolute;top:-6px;right:-10px;background:var(--terra);color:var(--cream);font-family:var(--mono);font-size:.52rem;font-weight:700;min-width:16px;height:16px;border-radius:var(--r-full);display:inline-flex;align-items:center;justify-content:center;padding:0 3px;border:1.5px solid var(--charcoal)}
.nav-tab.active{color:var(--cream)!important;opacity:1!important}
.nav-tab.active::after{content:'';position:absolute;bottom:-22px;left:50%;transform:translateX(-50%);width:20px;height:2px;background:var(--verd-green);border-radius:var(--r-full)}
.cl-head{display:flex;align-items:flex-end;justify-content:space-between;padding:2rem 0 .4rem;margin-bottom:.4rem}
.cl-title{font-family:var(--display);font-size:1.9rem;font-weight:900;color:var(--ink);letter-spacing:-.025em;line-height:1.1}
.cl-subtitle{font-size:.88rem;color:var(--muted);margin-top:2px}
.cl-shield{background:var(--moss-pale);border:1px solid rgba(61,90,62,.15);border-radius:var(--r-md);width:44px;height:44px;display:flex;align-items:center;justify-content:center;font-size:1.25rem}
.cl-search-wrap{position:relative;margin-bottom:1.2rem}
.cl-search-icon{position:absolute;left:13px;top:50%;transform:translateY(-50%);color:var(--muted);font-size:1.05rem;line-height:1;pointer-events:none}
.cl-search-input{width:100%;padding:.78rem 1rem .78rem 2.5rem;border:1.5px solid rgba(212,196,168,.6);border-radius:var(--r-lg);font-family:var(--body);font-size:.93rem;color:var(--ink);background:var(--warm-wh);outline:none;transition:border-color .15s,box-shadow .15s;box-shadow:var(--shadow-sm)}
.cl-search-input:focus{border-color:var(--moss);box-shadow:0 0 0 3px rgba(61,90,62,.1)}
.cl-search-input::placeholder{color:var(--muted)}
.cl-list{display:flex;flex-direction:column;gap:.65rem;margin-bottom:2rem}
.cl-card{background:var(--warm-wh);border:1px solid rgba(237,231,217,.8);border-radius:var(--r-lg);padding:1rem 1.2rem;display:flex;flex-direction:column;gap:.75rem;cursor:pointer;transition:border-color .15s,box-shadow .15s,transform .12s;position:relative}
.cl-card:hover{border-color:rgba(212,196,168,.7);box-shadow:var(--shadow-md);transform:translateY(-2px)}
.cl-card.unread{border-color:rgba(46,125,50,.25);background:linear-gradient(135deg,var(--warm-wh) 75%,rgba(46,125,50,.04))}
.cl-card-row{display:flex;align-items:center;gap:.9rem}
.cl-avatar-wrap{position:relative;flex-shrink:0}
.cl-avatar{width:50px;height:50px;border-radius:50%;object-fit:cover;border:2px solid var(--warm-wh);box-shadow:var(--shadow-sm);display:block}
.cl-avatar-fallback{width:50px;height:50px;border-radius:50%;background:linear-gradient(135deg,var(--moss),var(--moss-lt));display:flex;align-items:center;justify-content:center;font-family:var(--display);font-size:1.15rem;font-weight:700;color:var(--cream);border:2px solid var(--warm-wh);box-shadow:var(--shadow-sm)}
.cl-unread-dot{position:absolute;top:0;right:0;width:12px;height:12px;background:var(--verd-green);border-radius:50%;border:2px solid var(--warm-wh)}
.cl-info{flex:1;min-width:0}
.cl-info-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:1px}
.cl-name{font-family:var(--body);font-weight:700;font-size:.95rem;color:var(--ink)}
.cl-time{font-family:var(--mono);font-size:.6rem;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);white-space:nowrap}
.cl-item{font-family:var(--mono);font-size:.64rem;letter-spacing:.1em;text-transform:uppercase;color:var(--terra);font-weight:500;margin-bottom:3px}
.cl-msg{font-size:.84rem;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.cl-card-foot{display:flex;justify-content:flex-end;padding-top:.55rem;border-top:1px solid rgba(237,231,217,.9)}
.cl-btn-finish{background:var(--moss-pale);border:1px solid rgba(61,90,62,.15);color:var(--moss);border-radius:var(--r-md);padding:.35rem .85rem;font-family:var(--body);font-weight:700;font-size:.78rem;display:flex;align-items:center;gap:5px;cursor:pointer;transition:.15s}
.cl-btn-finish:hover{background:var(--moss);color:var(--cream);border-color:var(--moss)}
.cl-tag-done{background:var(--paper);border:1px solid rgba(212,196,168,.5);color:var(--muted);border-radius:var(--r-sm);padding:.28rem .7rem;font-family:var(--mono);font-size:.6rem;letter-spacing:.1em;text-transform:uppercase;display:flex;align-items:center;gap:5px}
.cl-star{color:#f59e0b;font-size:.88rem}
.cl-empty{text-align:center;padding:3.5rem 2rem;background:var(--warm-wh);border-radius:var(--r-xl);border:1px solid rgba(237,231,217,.8)}
.cl-empty-icon{font-size:3rem;opacity:.22;margin-bottom:.8rem}
.cl-empty h3{font-family:var(--display);font-size:1.2rem;color:var(--ink);margin-bottom:.3rem}
.cl-empty p{font-size:.85rem;color:var(--muted);max-width:300px;margin:0 auto}
.cl-safety-tip{background:var(--moss);border-radius:var(--r-xl);padding:1.5rem 1.7rem;display:flex;align-items:flex-start;gap:1.1rem;margin-bottom:3rem;box-shadow:0 6px 28px rgba(61,90,62,.22)}
.cl-safety-icon-wrap{background:var(--moss-lt);border-radius:var(--r-md);width:40px;height:40px;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:1.2rem}
.cl-safety-title{font-family:var(--body);font-weight:700;font-size:.97rem;color:var(--cream);margin-bottom:.3rem}
.cl-safety-text{font-size:.84rem;color:rgba(245,240,232,.72);line-height:1.65}
.rm-box{background:var(--warm-wh);width:100%;max-width:420px;border-radius:var(--r-xl);overflow:hidden;box-shadow:var(--shadow-lg);animation:modalIn .3s cubic-bezier(.32,1.25,.6,1)}
.rm-head{display:flex;align-items:center;justify-content:space-between;padding:1.2rem 1.4rem;border-bottom:1px solid var(--paper)}
.rm-head-title{font-family:var(--display);font-size:1.15rem;font-weight:700;color:var(--ink);letter-spacing:-.015em}
.rm-close-btn{width:30px;height:30px;background:var(--paper);border:1px solid rgba(212,196,168,.5);border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.78rem;color:var(--muted);transition:.15s}
.rm-close-btn:hover{background:var(--terra);color:var(--cream);border-color:var(--terra)}
.rm-body{padding:1.7rem 1.4rem;display:flex;flex-direction:column;align-items:center;gap:1.3rem;text-align:center}
.rm-question{font-size:.93rem;color:var(--muted);line-height:1.55}
.rm-target-name{color:var(--moss)}
.rm-stars-row{display:flex;gap:.32rem;justify-content:center}
.rm-star-btn{background:transparent;border:none;cursor:pointer;font-size:2.3rem;line-height:1;color:var(--sand);transition:color .1s,transform .12s;padding:.1rem;user-select:none}
.rm-star-btn:hover{transform:scale(1.15)}
.rm-star-btn.hovered,.rm-star-btn.selected{color:#f59e0b}
.rm-star-btn:active{transform:scale(.9)}
.rm-comment-group{width:100%;display:flex;flex-direction:column;gap:5px;text-align:left}
.rm-comment-label{font-family:var(--mono);font-size:.64rem;letter-spacing:.12em;text-transform:uppercase;color:var(--muted);font-weight:700}
.rm-comment-area{width:100%;border:1.5px solid rgba(212,196,168,.6);border-radius:var(--r-md);padding:.72rem .95rem;font-family:var(--body);font-size:.9rem;color:var(--ink);background:var(--cream);outline:none;resize:none;transition:border-color .15s,box-shadow .15s;line-height:1.55}
.rm-comment-area:focus{border-color:var(--moss);box-shadow:0 0 0 3px rgba(61,90,62,.1)}
.rm-comment-area::placeholder{color:var(--muted)}
.rm-submit-btn{width:100%;background:var(--moss);color:var(--cream);border:none;border-radius:var(--r-lg);padding:.95rem;font-family:var(--body);font-weight:900;font-size:.97rem;cursor:pointer;transition:background .15s,transform .1s;box-shadow:0 5px 18px rgba(61,90,62,.22)}
.rm-submit-btn:not(:disabled):hover{background:var(--terra);transform:translateY(-1px)}
.rm-submit-btn:active:not(:disabled){transform:scale(.98)}
.rm-submit-btn:disabled{background:var(--sand);color:var(--muted);cursor:not-allowed;box-shadow:none;transform:none}
.rm-success{padding:3rem 2rem;display:flex;flex-direction:column;align-items:center;text-align:center;gap:.8rem;animation:rmZoomIn .3s cubic-bezier(.32,1.25,.6,1)}
@keyframes rmZoomIn{from{opacity:0;transform:scale(.88)}to{opacity:1;transform:none}}
.rm-success-icon{width:72px;height:72px;background:var(--moss-pale);color:var(--verd-green);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:2.1rem;font-weight:900;margin-bottom:.6rem;border:2px solid rgba(46,125,50,.15)}
.rm-success-title{font-family:var(--display);font-size:1.55rem;font-weight:900;color:var(--ink);letter-spacing:-.02em}
.rm-success-sub{font-size:.88rem;color:var(--muted);line-height:1.55;max-width:260px}
.sf-wrap{max-width:680px;margin:0 auto;padding:1.2rem 0 3rem}
.sf-header{text-align:center;margin-bottom:1.6rem}
.sf-title{font-family:var(--display);font-size:1.9rem;font-weight:900;color:var(--cream);letter-spacing:-.025em;line-height:1.15;margin-bottom:.4rem}
.sf-subtitle{font-size:.9rem;color:var(--sand);line-height:1.65;max-width:460px;margin:0 auto;opacity:.85}
.sf-card{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.09);border-radius:var(--r-xl);padding:1.8rem 2rem;display:flex;flex-direction:column;gap:1.3rem;box-shadow:0 8px 40px rgba(0,0,0,.22);backdrop-filter:blur(8px)}
.sf-upload-zone{border:2px dashed rgba(245,240,232,.15);border-radius:var(--r-lg);padding:1.6rem 1.4rem;display:flex;flex-direction:column;align-items:center;gap:5px;cursor:pointer;transition:border-color .2s,background .2s;background:rgba(181,96,30,.03)}
.sf-upload-zone:hover{border-color:var(--terra);background:rgba(181,96,30,.07)}
.sf-upload-icon-wrap{width:54px;height:54px;background:rgba(255,255,255,.07);border-radius:50%;display:flex;align-items:center;justify-content:center;margin-bottom:.4rem;font-size:1.5rem;transition:transform .2s;box-shadow:0 2px 12px rgba(0,0,0,.15)}
.sf-upload-zone:hover .sf-upload-icon-wrap{transform:scale(1.08)}
.sf-upload-icon{line-height:1}
.sf-upload-text{font-weight:700;color:var(--terra);font-size:.92rem}
.sf-upload-hint{font-family:var(--mono);font-size:.62rem;letter-spacing:.1em;color:var(--sand)}
.sf-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.1rem}
.sf-card .fg{display:flex;flex-direction:column;gap:5px}
.sf-card .fg label{font-family:var(--mono);font-size:.65rem;letter-spacing:.14em;text-transform:uppercase;color:var(--sand);font-weight:500}
.sf-card .fg input,.sf-card .fg select,.sf-card .fg textarea{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.09);border-radius:var(--r-md);padding:.72rem .95rem;font-family:var(--body);font-size:.93rem;color:var(--cream);outline:none;transition:border-color .15s,box-shadow .15s}
.sf-card .fg input::placeholder,.sf-card .fg textarea::placeholder{color:rgba(245,240,232,.28)}
.sf-card .fg input:focus,.sf-card .fg select:focus,.sf-card .fg textarea:focus{border-color:var(--terra);box-shadow:0 0 0 3px rgba(181,96,30,.18)}
.sf-card .fg select option{background:var(--charcoal);color:var(--cream)}
.sf-card .fg textarea{resize:vertical}
.sf-condition-row{display:flex;background:rgba(0,0,0,.12);border-radius:var(--r-md);padding:3px;gap:2px}
.sf-cond-btn{flex:1;padding:.52rem .4rem;background:transparent;border:none;border-radius:var(--r-sm);font-family:var(--body);font-weight:700;font-size:.78rem;color:var(--sand);cursor:pointer;transition:background .15s,color .15s,box-shadow .15s;line-height:1}
.sf-cond-btn.on{background:var(--warm-wh);color:var(--moss);box-shadow:0 1px 6px rgba(0,0,0,.18)}
.sf-cond-btn:not(.on):hover{color:var(--cream)}
.sf-desc-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:3px}
.sf-ia-btn{display:flex;align-items:center;gap:5px;background:transparent;border:1px solid rgba(181,96,30,.35);border-radius:var(--r-full);padding:.26rem .7rem;font-family:var(--body);font-size:.73rem;font-weight:700;color:var(--terra);cursor:pointer;transition:background .15s,border-color .15s,opacity .15s}
.sf-ia-btn:hover:not(:disabled){background:rgba(181,96,30,.1);border-color:var(--terra)}
.sf-ia-btn:disabled{opacity:.4;cursor:not-allowed}
.sf-ia-spinning{display:inline-block;animation:iaSpin .7s linear infinite}
@keyframes iaSpin{to{transform:rotate(360deg)}}
@keyframes sfDescFadeIn{from{background:rgba(181,96,30,.14)}to{background:transparent}}
.sf-foot{display:flex;flex-direction:column;gap:.85rem;padding-top:.5rem}
.sf-submit-btn{width:100%;background:var(--terra);color:var(--cream);border:none;border-radius:var(--r-full);padding:1.05rem;font-family:var(--body);font-weight:900;font-size:1rem;display:flex;align-items:center;justify-content:center;gap:8px;cursor:pointer;transition:background .15s,transform .12s;box-shadow:0 6px 22px rgba(181,96,30,.38)}
.sf-submit-btn:hover{background:var(--terra-dk);transform:translateY(-2px)}
.sf-submit-btn:active{transform:scale(.98)}
.sf-submit-btn:disabled{opacity:.5;cursor:not-allowed;transform:none!important}
.sf-security-note{text-align:center;font-family:var(--mono);font-size:.65rem;letter-spacing:.08em;color:var(--sand);opacity:.7}
.photo-previews{display:flex;flex-wrap:wrap;gap:9px;margin-top:13px;justify-content:center}
.preview-thumb{width:74px;height:74px;border-radius:var(--r-md);overflow:hidden;border:2px solid rgba(255,255,255,.12);position:relative;box-shadow:0 2px 8px rgba(0,0,0,.2)}
.preview-thumb img{width:100%;height:100%;object-fit:cover;display:block}
.remove-thumb{position:absolute;top:-5px;right:-5px;background:var(--terra);color:white;border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;font-size:.66rem;cursor:pointer;border:1.5px solid var(--charcoal);font-weight:700}
#formPanel{background:var(--charcoal);border-radius:var(--r-xl);margin:2rem 0 3rem;padding:0;border:1px solid rgba(255,255,255,.05);box-shadow:var(--shadow-lg)}
@keyframes slideDown{from{opacity:0;transform:translateY(-14px)}to{opacity:1;transform:none}}
@media(max-width:700px){
  .nav{padding:0 1.2rem}
  .hero{grid-template-columns:1fr;padding:2.5rem 1.5rem 2rem}
  .hero-stats{flex-direction:row;align-items:flex-start;flex-wrap:wrap}
  .hero-stat{text-align:left;flex:1;min-width:100px}
  .wrap{padding:0 1.2rem}
  .filter-bar{flex-direction:column;align-items:stretch}
  .cards.list .card{flex-direction:column}
  .cards.list .card-thumb{width:100%;min-height:160px}
}
@media(max-width:560px){
  .sf-card{padding:1.3rem 1.1rem}
  .sf-grid{grid-template-columns:1fr}
  .sf-title{font-size:1.45rem}
}
</style>
</head>
<body>
<nav class="nav">
  <a href="#" class="nav-logo">
    <span class="nav-logo-mark">Vend<em>Verd</em></span>
    <span class="nav-logo-sub">Vender é viver o ciclo!</span>
  </a>
  <div class="nav-links">
    <a href="javascript:void(0)" class="nav-tab" id="navExplorar" onclick="mostrarView('explorar')">Explorar</a>
    <a href="javascript:void(0)" class="nav-tab" id="navConversas" onclick="mostrarView('conversas')">Conversas<span class="nav-badge" id="navBadge" style="display:none"></span></a>
    <a href="javascript:void(0)" class="nav-tab" id="navPerfil" onclick="mostrarView('perfil')">Perfil</a>
    <a href="#"></a>
    <a href="javascript:void(0)" class="btn-nav-cta" onclick="toggleForm()"><span class="nav-icon">＋</span> Anunciar</a>
  </div>
</nav>
<section class="hero" id="heroSection">
  <div class="hero-left">
    <div class="hero-eyebrow">⚡ Economia Circular no Seu Condomínio</div>
    <h1 class="hero-h1">Nada termina. Tudo se transforma.<br><em>Cada venda é um novo começo.</em></h1>
    <p class="hero-sub">Transformamos condomínios em hubs vivos de economia circular. O que não serve mais para você gera valor para outra pessoa — com segurança e sustentabilidade.</p>
    <div class="hero-badges">
      <div class="hero-badge-item"><span class="hero-badge-icon">🛡</span><div><div class="hero-badge-title">Transação Segura</div><div class="hero-badge-sub">Ponto físico dentro do residencial</div></div></div>
      <div class="hero-badge-item"><span class="hero-badge-icon">🌎</span><div><div class="hero-badge-title">Alcance Ampliado</div><div class="hero-badge-sub">Visível para público externo</div></div></div>
    </div>
  </div>
  <div class="hero-stats">
    <div class="hero-stat"><div class="hero-stat-num" id="totalAnuncios">0</div><div class="hero-stat-lbl">itens</div></div>
    <div class="hero-stat"><div class="hero-stat-num" id="totalCondominios">0</div><div class="hero-stat-lbl">condomínios</div></div>
    <div class="hero-stat"><div class="hero-stat-num" id="totalCategorias">0</div><div class="hero-stat-lbl">categorias</div></div>
  </div>
</section>
<div class="wrap" id="viewExplorar">
  <div class="filter-bar">
    <div class="search-box"><span class="search-icon">⌕</span><input type="text" id="inputBusca" placeholder="O que você está procurando no seu condomínio?"></div>
    <button class="btn-filter" id="btnAbrirFiltros"><span>⊟</span> Filtros<span class="filter-count" id="filterCount" style="display:none"></span></button>
    <button class="btn-filter-clear" id="btnLimparFiltros" style="display:none" title="Limpar filtros">✕</button>
  </div>
  <div class="fm-overlay" id="filterModal">
    <div class="fm-box" id="filterModalBox">
      <div class="fm-head"><div class="fm-head-left"><span class="fm-title">Filtros</span><button class="fm-reset-btn" id="btnResetFiltros" title="Resetar filtros">↺</button></div><button class="fm-close-btn" id="btnFecharFiltros">✕</button></div>
      <div class="fm-body">
        <div class="fm-condo-row"><div><div class="fm-condo-title">Apenas meu condomínio</div><div class="fm-condo-sub">Ver itens sem precisar sair de casa</div></div><button class="fm-toggle" id="toggleMeuCondo" data-on="false" aria-label="Filtrar por meu condomínio"><div class="fm-toggle-knob"></div></button></div>
        <div class="fm-section"><div class="fm-section-title">Categorias</div><div class="fm-chips" id="chipsCategorias"><button class="fm-chip on" data-val="todas">Todas</button><button class="fm-chip" data-val="moveis">🪑 Móveis</button><button class="fm-chip" data-val="eletro">🔌 Eletro</button><button class="fm-chip" data-val="brinquedos">🧸 Brinquedos</button><button class="fm-chip" data-val="livros">📚 Livros</button><button class="fm-chip" data-val="moda">👗 Moda</button><button class="fm-chip" data-val="jardinagem">🌱 Jardinagem</button><button class="fm-chip" data-val="esporte">⚽ Esporte</button></div></div>
        <div class="fm-section"><div class="fm-section-title">Condição</div><div class="fm-chips fm-chips-row" id="chipsCondicao"><button class="fm-chip on" data-val="todas">Todas</button><button class="fm-chip" data-val="novo">Novo</button><button class="fm-chip" data-val="seminovo">Seminovo</button><button class="fm-chip" data-val="usado">Usado</button></div></div>
        <div class="fm-section"><div class="fm-section-title">Faixa de Preço</div><div class="fm-price-row"><div class="fm-price-field"><span class="fm-price-lbl">Mín</span><div class="fm-price-input-wrap"><span class="fm-price-prefix">R$</span><input type="number" id="fmPrecoMin" placeholder="0" min="0" step="0.01"></div></div><div class="fm-price-sep"></div><div class="fm-price-field"><span class="fm-price-lbl">Máx</span><div class="fm-price-input-wrap"><span class="fm-price-prefix">R$</span><input type="number" id="fmPrecoMax" placeholder="0" min="0" step="0.01"></div></div></div></div>
      </div>
      <div class="fm-foot"><button class="fm-btn-cancel" id="btnCancelarFiltros">Cancelar</button><button class="fm-btn-apply" id="btnAplicarFiltros">✓ Aplicar Filtros</button></div>
    </div>
  </div>
  <input type="hidden" id="selectCategoria" value="todas">
  <input type="hidden" id="selectCondicao" value="todas">
  <input type="hidden" id="precoMin" value="">
  <input type="hidden" id="precoMax" value="">
  <input type="hidden" id="checkMeuCondoVal" value="0">
  <div class="section-head"><h2>Anúncios recentes</h2><div class="view-toggle"><button class="vbtn on" id="viewGrid" title="Grade">⊞</button><button class="vbtn" id="viewList" title="Lista">☰</button></div></div>
  <div class="cards" id="cardsContainer"><div class="state-box"><div class="spinner-ring"></div><p>Carregando anúncios…</p></div></div>
  <section class="impact-banner" id="impactBanner">
    <div class="impact-line"></div>
    <h3 class="impact-title">Nossa Comunidade Circular</h3>
    <div class="impact-grid">
      <div class="impact-item"><div class="impact-num">452</div><div class="impact-lbl">Itens Circulados</div></div>
      <div class="impact-item"><div class="impact-num">1.2t</div><div class="impact-lbl">CO₂ Reduzido</div></div>
      <div class="impact-item"><div class="impact-num">R$ 15k</div><div class="impact-lbl">Economia Total</div></div>
      <div class="impact-item"><div class="impact-num" id="impactCondos">12</div><div class="impact-lbl">Condomínios</div></div>
    </div>
  </section>
  <div id="formPanel" style="display:none">
    <div class="sf-wrap">
      <div class="sf-header"><h2 class="sf-title">Venda com Segurança Total</h2><p class="sf-subtitle">Seu anúncio será visível para o público externo, mas a entrega ocorre dentro do seu condomínio.</p></div>
      <div class="sf-card">
        <div class="sf-upload-zone" id="uploadArea" onclick="document.getElementById('uploadFotos').click()">
          <input type="file" id="uploadFotos" accept="image/jpeg,image/png,image/webp" multiple style="display:none">
          <div class="sf-upload-icon-wrap"><span class="sf-upload-icon">📷</span></div>
          <span class="sf-upload-text">Adicionar Fotos</span>
          <span class="sf-upload-hint">Até 5 fotos (JPG, PNG · máx 5 MB cada)</span>
          <div class="photo-previews" id="previewFotos"></div>
        </div>
        <div class="sf-grid">
          <div class="fg"><label>Título do Anúncio *</label><input type="text" id="novoTitulo" placeholder="Ex: Cafeteira Expresso 110v" maxlength="100" required></div>
          <div class="fg"><label>Preço (R$) *</label><input type="number" id="novoPreco" placeholder="0,00" min="0.01" step="0.01" required></div>
        </div>
        <div class="sf-grid">
          <div class="fg"><label>Categoria *</label><select id="novaCategoria" required><option value="eletro">Eletrônicos</option><option value="moveis">Casa e Jardim</option><option value="esporte">Esportes</option><option value="brinquedos">Infantil</option><option value="livros">Livros</option><option value="moda">Moda</option></select></div>
          <div class="fg"><label>Condição *</label><div class="sf-condition-row" id="sfConditionRow"><button type="button" class="sf-cond-btn on" data-val="Novo">Novo</button><button type="button" class="sf-cond-btn" data-val="Seminovo">Seminovo</button><button type="button" class="sf-cond-btn" data-val="Usado">Usado</button></div><input type="hidden" id="novaCondicao" value="Novo"></div>
        </div>
        <div class="sf-grid">
          <div class="fg"><label>Tipo de contato *</label><select id="novoTipoContato" required><option value="whatsapp">WhatsApp</option><option value="telefone">Telefone</option><option value="email">E-mail</option></select></div>
          <div class="fg"><label>Contato *</label><input type="text" id="novoContato" placeholder="(11) 91234-5678" maxlength="120" required></div>
        </div>
        <div class="fg"><label>Condomínio / Bairro *</label><input type="text" id="novoLocal" placeholder="ex: Residencial Aurora, Vila Mariana" maxlength="100" required></div>
        <div class="fg">
          <div class="sf-desc-header"><label>Descrição *</label><button type="button" class="sf-ia-btn" id="sfIaBtn" onclick="sfGerarDescricao()"><span id="sfIaIcon">✦</span><span id="sfIaLabel">Gerar com IA</span></button></div>
          <textarea id="novaDesc" rows="4" placeholder="Conte mais sobre o estado do item e por que está vendendo…" maxlength="1000" required></textarea>
        </div>
        <div class="sf-foot"><button class="sf-submit-btn" id="btnAdicionarAnuncio">Publicar Agora →</button><div class="sf-security-note">🛡 Venda protegida: compradores externos encontram você no condomínio.</div></div>
        <p class="form-note">* campos obrigatórios</p>
      </div>
    </div>
  </div>
</div>
<div class="wrap" id="viewConversas" style="display:none">
  <div class="cl-head"><div><h2 class="cl-title">Conversas</h2><p class="cl-subtitle">Negocie com compradores interessados</p></div><div class="cl-shield">🛡</div></div>
  <div class="cl-search-wrap"><span class="cl-search-icon">⌕</span><input type="text" id="chatBusca" class="cl-search-input" placeholder="Buscar conversas…"></div>
  <div id="chatList" class="cl-list"></div>
  <div class="cl-safety-tip"><div class="cl-safety-icon-wrap">⏱</div><div><div class="cl-safety-title">Ponto de Encontro no Condomínio</div><p class="cl-safety-text">Receba compradores externos com segurança. Agende a entrega no lobby, guarita ou áreas monitoradas do seu residencial.</p></div></div>
</div>
<div class="wrap" id="viewPerfil" style="display:none">
  <div class="pf-header-card">
    <div class="pf-avatar-wrap"><img class="pf-avatar" id="pfAvatar" src="https://picsum.photos/seed/user/200/200" alt="Foto de perfil"><span class="pf-verified-dot">🛡</span></div>
    <div class="pf-name" id="pfName">Morador VendVerd</div>
    <div class="pf-condo" id="pfCondo">Residencial Aurora</div>
    <div class="pf-stats-row">
      <div class="pf-stat"><div class="pf-stat-num">12</div><div class="pf-stat-lbl">Itens Vendidos</div></div>
      <button class="pf-stat pf-stat-btn" id="pfStatRating" onclick="setProfileTab('reviews')"><div class="pf-stat-num pf-stat-rating">4.9 ★</div><div class="pf-stat-lbl">12 Avaliações</div></button>
      <div class="pf-stat"><div class="pf-stat-num">R$ 2.4k</div><div class="pf-stat-lbl">Economizado</div></div>
    </div>
  </div>
  <div class="pf-tabs" id="pfTabs"><button class="pf-tab on" id="pfTabInfo" onclick="setProfileTab('info')">Opções</button><button class="pf-tab" id="pfTabReviews" onclick="setProfileTab('reviews')">Reputação</button></div>
  <div id="pfPanelInfo" class="pf-panel">
    <div class="pf-menu">
      <button class="pf-menu-item" onclick="toast('Em breve: Meus Anúncios')"><span class="pf-menu-icon pf-icon-blue">🛍</span><span class="pf-menu-label">Meus Anúncios</span><span class="pf-menu-arrow">›</span></button>
      <button class="pf-menu-item" onclick="toast('Em breve: Itens Favoritos')"><span class="pf-menu-icon pf-icon-rose">♡</span><span class="pf-menu-label">Itens Favoritos</span><span class="pf-menu-arrow">›</span></button>
      <button class="pf-menu-item" onclick="toast('Em breve: Pegada Ecológica')"><span class="pf-menu-icon pf-icon-green">🌱</span><span class="pf-menu-label">Minha Pegada Ecológica</span><span class="pf-menu-arrow">›</span></button>
      <button class="pf-menu-item" onclick="toast('Em breve: Configurações')"><span class="pf-menu-icon pf-icon-gray">⚙</span><span class="pf-menu-label">Configurações de Conta</span><span class="pf-menu-arrow">›</span></button>
      <button class="pf-menu-item pf-menu-danger" onclick="toast('Saindo da conta…')"><span class="pf-menu-icon pf-icon-red">↩</span><span class="pf-menu-label">Sair da Conta</span><span class="pf-menu-arrow">›</span></button>
    </div>
  </div>
  <div id="pfPanelReviews" class="pf-panel" style="display:none"><div class="pf-reviews-head"><span class="pf-reviews-title">Avaliações Recentes</span><span class="pf-stars-display" id="pfStarsDisplay"></span></div><div id="pfReviewsList" class="pf-reviews-list"></div></div>
  <div class="pf-footer-note"><p>Versão 1.0.4 Beta</p><p>VendVerd © 2025 · Todos os direitos reservados</p></div>
</div>
<div class="overlay" id="reviewOverlay">
  <div class="rm-box" id="rmBox">
    <div id="rmStateNormal">
      <div class="rm-head"><span class="rm-head-title">Avaliar Negociação</span><button class="rm-close-btn" onclick="fecharReviewModal()">✕</button></div>
      <div class="rm-body">
        <p class="rm-question">Como foi negociar com <strong id="rmTargetName" class="rm-target-name"></strong>?</p>
        <div class="rm-stars-row" id="rmStarsRow"><button class="rm-star-btn" data-val="1" aria-label="1 estrela">★</button><button class="rm-star-btn" data-val="2" aria-label="2 estrelas">★</button><button class="rm-star-btn" data-val="3" aria-label="3 estrelas">★</button><button class="rm-star-btn" data-val="4" aria-label="4 estrelas">★</button><button class="rm-star-btn" data-val="5" aria-label="5 estrelas">★</button></div>
        <div class="rm-comment-group"><label class="rm-comment-label">Comentário (opcional)</label><textarea id="rmComment" class="rm-comment-area" rows="3" placeholder="Ex: Entrega pontual, produto em ótimo estado…"></textarea></div>
        <button class="rm-submit-btn" id="rmSubmitBtn" onclick="enviarReview()" disabled>Enviar Avaliação</button>
      </div>
    </div>
    <div id="rmStateSuccess" style="display:none" class="rm-success"><div class="rm-success-icon">✓</div><h2 class="rm-success-title">Avaliação Enviada!</h2><p class="rm-success-sub">Obrigado por ajudar a construir uma comunidade mais segura.</p></div>
  </div>
</div>
<div class="overlay" id="modalDetalhes">
  <div class="pd-box">
    <div class="pd-img-col" id="pdImgCol"><button class="pd-close-mobile" onclick="fecharModal()">✕</button></div>
    <div class="pd-info-col" id="pdInfoCol"><button class="pd-close-desktop" onclick="fecharModal()">✕</button><div id="modalConteudo" class="pd-scroll"></div><div class="pd-foot"><button class="pd-btn-interest" id="pdBtnInterest">💬 Tenho Interesse</button></div></div>
  </div>
</div>
<div class="toast" id="toast"><span class="toast-icon" id="toastIcon">✓</span><span id="toastMessage">Feito!</span></div>
<footer class="footer">
  <div class="footer-inner">
    <div class="footer-grid">
      <div><div class="footer-brand-logo"><div class="footer-brand-icon">♻</div><span class="footer-brand-name">Vend<em>Verd</em></span></div><p class="footer-tagline">Transformando condomínios em centros de economia circular segura e sustentável.</p></div>
      <div><div class="footer-col-title">Plataforma</div><ul class="footer-links"><li><a href="#">Como Funciona</a></li><li><a href="#">Segurança</a></li><li><a href="#">Sustentabilidade</a></li><li><a href="#">Meetup Points</a></li></ul></div>
      <div><div class="footer-col-title">Institucional</div><ul class="footer-links"><li><a href="#">Termos de Uso</a></li><li><a href="#">Privacidade</a></li><li><a href="#">Ajuda &amp; Suporte</a></li><li><a href="#">Fale Conosco</a></li></ul></div>
      <div><div class="footer-col-title">Social</div><div class="footer-social"><a href="#" class="footer-social-btn" title="Instagram">&#x1F4F8;</a><a href="#" class="footer-social-btn" title="Twitter / X">&#x1D54F;</a><a href="#" class="footer-social-btn" title="WhatsApp">&#x1F4AC;</a></div><div class="footer-badge">🛡 Plataforma Auditada 2025</div></div>
    </div>
    <div class="footer-bottom"><span class="footer-copy">© 2025 VendVerd Mercado de Economia Circular para Condomínios. Todos os direitos reservados.</span><span class="footer-made">Feito com <em>♻</em> para sua comunidade</span></div>
  </div>
</footer>
<script>
const API='http://localhost/pithub/api';
let isGrid=true,anunciosCache=new Map(),fotosSelected=[];
const cardsEl=document.getElementById('cardsContainer'),inputBusca=document.getElementById('inputBusca'),btnPublicar=document.getElementById('btnAdicionarAnuncio'),vGrid=document.getElementById('viewGrid'),vList=document.getElementById('viewList'),overlay=document.getElementById('modalDetalhes'),modalConteudo=document.getElementById('modalConteudo'),toastEl=document.getElementById('toast'),toastMsg=document.getElementById('toastMessage'),toastIcon=document.getElementById('toastIcon'),uploadInput=document.getElementById('uploadFotos'),previewBox=document.getElementById('previewFotos');
const hidCat=document.getElementById('selectCategoria'),hidCond=document.getElementById('selectCondicao'),hidMin=document.getElementById('precoMin'),hidMax=document.getElementById('precoMax'),hidMyCondo=document.getElementById('checkMeuCondoVal');
const btnLimpar=document.getElementById('btnLimparFiltros'),filterCount=document.getElementById('filterCount');
const fTitulo=document.getElementById('novoTitulo'),fCat=document.getElementById('novaCategoria'),fPreco=document.getElementById('novoPreco'),fLocal=document.getElementById('novoLocal'),fDesc=document.getElementById('novaDesc'),fTipoContato=document.getElementById('novoTipoContato'),fContato=document.getElementById('novoContato'),fCondicao=document.getElementById('novaCondicao');
let fmState={category:'todas',condition:'todas',minPrice:'',maxPrice:'',onlyMyCondo:false};
let filtersApplied={...fmState};
const fmOverlay=document.getElementById('filterModal');
function abrirFilterModal(){fmState={...filtersApplied};renderFmState();fmOverlay.classList.add('open');document.body.style.overflow='hidden'}
function fecharFilterModal(){fmOverlay.classList.remove('open');document.body.style.overflow=''}
function renderFmState(){const tog=document.getElementById('toggleMeuCondo');tog.classList.toggle('on',fmState.onlyMyCondo);tog.dataset.on=fmState.onlyMyCondo?'true':'false';document.querySelectorAll('#chipsCategorias .fm-chip').forEach(b=>b.classList.toggle('on',b.dataset.val===fmState.category));document.querySelectorAll('#chipsCondicao .fm-chip').forEach(b=>b.classList.toggle('on',b.dataset.val===fmState.condition));document.getElementById('fmPrecoMin').value=fmState.minPrice;document.getElementById('fmPrecoMax').value=fmState.maxPrice}
function contarFiltrosAtivos(){let n=0;if(filtersApplied.category!=='todas')n++;if(filtersApplied.condition!=='todas')n++;if(filtersApplied.minPrice||filtersApplied.maxPrice)n++;if(filtersApplied.onlyMyCondo)n++;return n}
function atualizarBotaoFiltros(){const n=contarFiltrosAtivos();if(n>0){filterCount.textContent=n;filterCount.style.display='inline-flex';btnLimpar.style.display='flex'}else{filterCount.style.display='none';btnLimpar.style.display='none'}}
function aplicarFiltros(){filtersApplied={...fmState};hidCat.value=filtersApplied.category;hidCond.value=filtersApplied.condition;hidMin.value=filtersApplied.minPrice;hidMax.value=filtersApplied.maxPrice;hidMyCondo.value=filtersApplied.onlyMyCondo?'1':'0';fecharFilterModal();atualizarBotaoFiltros();carregarAnuncios()}
function limparFiltros(){const zero={category:'todas',condition:'todas',minPrice:'',maxPrice:'',onlyMyCondo:false};fmState={...zero};filtersApplied={...zero};hidCat.value='todas';hidCond.value='todas';hidMin.value='';hidMax.value='';hidMyCondo.value='0';atualizarBotaoFiltros();carregarAnuncios()}
document.getElementById('btnAbrirFiltros').addEventListener('click',abrirFilterModal);
document.getElementById('btnFecharFiltros').addEventListener('click',fecharFilterModal);
document.getElementById('btnCancelarFiltros').addEventListener('click',fecharFilterModal);
document.getElementById('btnAplicarFiltros').addEventListener('click',aplicarFiltros);
document.getElementById('btnLimparFiltros').addEventListener('click',e=>{e.preventDefault();limparFiltros()});
document.getElementById('btnResetFiltros').addEventListener('click',()=>{fmState={category:'todas',condition:'todas',minPrice:'',maxPrice:'',onlyMyCondo:false};renderFmState()});
fmOverlay.addEventListener('click',e=>{if(e.target===fmOverlay)fecharFilterModal()});
document.getElementById('toggleMeuCondo').addEventListener('click',function(){fmState.onlyMyCondo=!fmState.onlyMyCondo;this.classList.toggle('on',fmState.onlyMyCondo);this.dataset.on=fmState.onlyMyCondo?'true':'false'});
document.querySelectorAll('#chipsCategorias .fm-chip').forEach(btn=>{btn.addEventListener('click',function(){fmState.category=this.dataset.val;document.querySelectorAll('#chipsCategorias .fm-chip').forEach(b=>b.classList.remove('on'));this.classList.add('on')})});
document.querySelectorAll('#chipsCondicao .fm-chip').forEach(btn=>{btn.addEventListener('click',function(){fmState.condition=this.dataset.val;document.querySelectorAll('#chipsCondicao .fm-chip').forEach(b=>b.classList.remove('on'));this.classList.add('on')})});
document.getElementById('fmPrecoMin').addEventListener('input',function(){fmState.minPrice=this.value});
document.getElementById('fmPrecoMax').addEventListener('input',function(){fmState.maxPrice=this.value});
document.addEventListener('keydown',e=>{if(e.key==='Escape'){if(reviewOverlay&&reviewOverlay.classList.contains('open')){fecharReviewModal();return}if(fmOverlay.classList.contains('open')){fecharFilterModal();return}if(overlay.classList.contains('open'))fecharModal()}});
function esc(str){if(!str)return '';return String(str).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;').replace(/'/g,'&#039;')}
function validUrl(url){if(!url||typeof url!=='string')return false;try{const p=new URL(url);return p.protocol==='http:'||p.protocol==='https:'}catch{return false}}
function validarContato(tipo,valor){const v=valor.trim();if(!v)return 'Contato é obrigatório';if(v.length>120)return 'Contato muito longo (máx 120 caracteres)';if(tipo==='email'){if(!/^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/.test(v))return 'E-mail inválido'}if(tipo==='whatsapp'||tipo==='telefone'){const digits=v.replace(/\D/g,'');if(digits.length<8)return 'Número de telefone inválido'}return null}
function toast(msg,ok=true){toastMsg.textContent=msg;toastIcon.textContent=ok?'✓':'⚠';toastEl.classList.remove('show','err');void toastEl.offsetWidth;toastEl.classList.add('show');if(!ok)toastEl.classList.add('err');clearTimeout(toastEl._t);toastEl._t=setTimeout(()=>{toastEl.classList.remove('show','err')},3200)}
function loading(){cardsEl.innerHTML='<div class="state-box"><div class="spinner-ring"></div><p>Carregando anúncios…</p></div>'}
const CAT_LABELS={moveis:'MÓVEIS',eletro:'ELETRO',brinquedos:'BRINQUEDOS',livros:'LIVROS',moda:'MODA',jardinagem:'JARDINAGEM',esporte:'ESPORTE'};
const CAT_EMOJI={moveis:'🪑',eletro:'🔌',brinquedos:'🧸',livros:'📚',moda:'👗',jardinagem:'🌱',esporte:'⚽'};
function catLabel(c){return CAT_LABELS[c]||String(c).toUpperCase()}
function catEmoji(c){return CAT_EMOJI[c]||'📦'}
async function carregarAnuncios(){try{loading();const busca=encodeURIComponent(inputBusca.value.trim()),cat=hidCat.value||'todas',cond=hidCond.value||'todas',min=hidMin.value?parseFloat(hidMin.value):0,max=hidMax.value?parseFloat(hidMax.value):999999,myCondo=hidMyCondo.value==='1';const url=new URL(`${API}/listar_anuncios.php`);if(busca)url.searchParams.append('busca',busca);if(cat!=='todas')url.searchParams.append('categoria',cat);if(cond!=='todas')url.searchParams.append('condicao',cond);url.searchParams.append('preco_min',min);url.searchParams.append('preco_max',max);if(myCondo)url.searchParams.append('meu_condo','1');const res=await fetch(url,{headers:{'Accept':'application/json','X-Requested-With':'XMLHttpRequest'},credentials:'same-origin'});if(!res.ok)throw new Error(`HTTP ${res.status}`);const data=await res.json();if(data.success){data.data.forEach(a=>anunciosCache.set(String(a.id),a));renderCards(data.data);updateStats(data.data)}else throw new Error(data.message||'Erro ao carregar')}catch(err){console.error(err);cardsEl.innerHTML=`<div class="state-box"><div class="big-icon">⚠</div><h3>Algo deu errado</h3><p>${esc(err.message)}</p><button class="btn-retry" onclick="carregarAnuncios()">Tentar novamente</button></div>`}}
async function publicarAnuncio(dados){if(!dados.titulo||dados.titulo.length<3)throw new Error('Título deve ter pelo menos 3 caracteres');if(dados.titulo.length>100)throw new Error('Título muito longo (máx 100 caracteres)');if(!dados.descricao||dados.descricao.length<10)throw new Error('Descrição deve ter pelo menos 10 caracteres');if(dados.descricao.length>1000)throw new Error('Descrição muito longa (máx 1000 caracteres)');if(dados.preco<=0)throw new Error('Preço deve ser maior que zero');if(!dados.local||dados.local.length<3)throw new Error('Local inválido');const erroC=validarContato(dados.tipo_contato||'',dados.contato||'');if(erroC)throw new Error(erroC);const res=await fetch(`${API}/criar_anuncio.php`,{method:'POST',headers:{'Content-Type':'application/json','Accept':'application/json','X-Requested-With':'XMLHttpRequest'},credentials:'same-origin',body:JSON.stringify(dados)});if(!res.ok)throw new Error(`HTTP ${res.status}`);const result=await res.json();if(!result.success)throw new Error(result.message||'Erro ao publicar');return true}
async function uploadFoto(file){if(!file.type.startsWith('image/'))throw new Error(`${file.name}: não é imagem`);if(file.size>5*1024*1024)throw new Error(`${file.name}: excede 5MB`);await new Promise((resolve,reject)=>{const reader=new FileReader();reader.onloadend=()=>{const arr=new Uint8Array(reader.result);const isJpeg=arr[0]===0xFF&&arr[1]===0xD8;const isPng=arr[0]===0x89&&arr[1]===0x50&&arr[2]===0x4E&&arr[3]===0x47;const isWebp=arr[8]===0x57&&arr[9]===0x45&&arr[10]===0x42&&arr[11]===0x50;if(isJpeg||isPng||isWebp)resolve();else reject(new Error(`${file.name}: formato de imagem inválido`))};reader.onerror=()=>reject(new Error(`${file.name}: erro ao ler arquivo`));reader.readAsArrayBuffer(file.slice(0,12))});const fd=new FormData();fd.append('foto',file);const res=await fetch(`${API}/upload_foto.php`,{method:'POST',body:fd,credentials:'same-origin'});if(!res.ok)throw new Error(`HTTP ${res.status}`);const r=await res.json();if(!r.success)throw new Error(r.message||'Erro no upload');return r.url}
function renderCards(list){if(!list||list.length===0){const temFiltros=contarFiltrosAtivos()>0||inputBusca.value.trim()!=='';cardsEl.innerHTML=`<div class="state-box"><div class="big-icon">◯</div><h3>Nenhum item encontrado</h3><p>Tente ajustar seus filtros ou buscar em outro condomínio próximo.</p>${temFiltros?`<button class="btn-retry" onclick="limparFiltros()">Resetar Filtros</button>`:''}</div>`;return}cardsEl.innerHTML=list.map(a=>{const titulo=esc(a.titulo),descricao=esc(a.descricao),local=esc(a.local),cat=esc(a.categoria),condicao=esc(a.condicao||''),fotoOk=a.fotos&&a.fotos.length>0&&validUrl(a.fotos[0]),fotoCount=a.fotos?a.fotos.length:0,id=esc(String(a.id)),preco=esc(String(a.preco));const thumbHtml=fotoOk?`<img src="${a.fotos[0]}" alt="${titulo}" loading="lazy">`:`<span class="card-thumb-emoji">${catEmoji(cat)}</span>`;const condicaoBadge=condicao?`<span class="card-condition">${condicao}</span>`:'';return`<article class="card" onclick="abrirModal('${id}')"><div class="card-thumb">${thumbHtml}<span class="card-badge">🏢 condomínio</span>${condicaoBadge?`<span style="position:absolute;bottom:10px;left:10px;z-index:2;">${condicaoBadge}</span>`:''} ${fotoCount>0?`<span class="card-photo-count">📷 ${fotoCount}</span>`:''}</div><div class="card-body"><div class="card-cat">${catLabel(cat)}</div><div class="card-title">${titulo}</div><div class="card-desc">${descricao}</div><div class="card-foot"><span class="card-price">R$ ${preco}</span><span class="card-local"><span class="card-local-icon">◎</span>${local.substring(0,22)}${local.length>22?'…':''}</span></div><button class="btn-talk" onclick="event.stopPropagation();contatoAnunciante('${id}')">💬 Conversar</button></div></article>`}).join('');cardsEl.className=isGrid?'cards':'cards list'}
function updateStats(list){document.getElementById('totalAnuncios').textContent=list.length;const condCount=[...new Set(list.map(a=>a.condominio||a.local.split(' ')[0]))].length;document.getElementById('totalCondominios').textContent=condCount;document.getElementById('totalCategorias').textContent=[...new Set(list.map(a=>a.categoria))].length;const ic=document.getElementById('impactCondos');if(ic&&condCount>0)ic.textContent=Math.max(condCount,12)}
async function getSafetyTips(itemTitle){try{const res=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-5-20250929',max_tokens:300,messages:[{role:'user',content:`Gere exatamente 3 dicas curtas e práticas de segurança para negociar a compra de "${itemTitle}" em um condomínio residencial. Responda APENAS com um array JSON de strings, sem markdown, sem texto extra. Exemplo: ["dica 1","dica 2","dica 3"]`}]})});if(!res.ok)throw new Error('API error');const data=await res.json();const raw=data.content?.[0]?.text||'[]';const clean=raw.replace(/```json|```/g,'').trim();return JSON.parse(clean)}catch{return['Combine a entrega na guarita ou lobby do condomínio.','Não realize transferências antes de inspecionar o item pessoalmente.','Avise o porteiro sobre a visita do comprador externo.']}}
window.abrirModal=async function(id){const a=anunciosCache.get(String(id));if(!a)return;const titulo=esc(a.titulo),descricao=esc(a.descricao||''),local=esc(a.local),cat=esc(a.categoria),condicao=esc(a.condicao||''),vendedor=esc(a.vendedor||a.nome_vendedor||'Vendedor'),preco=Number(a.preco).toLocaleString('pt-BR',{minimumFractionDigits:2});const fotosValidas=(a.fotos||[]).filter(validUrl);const pdImgCol=document.getElementById('pdImgCol');if(fotosValidas.length>0){pdImgCol.innerHTML=`<button class="pd-close-mobile" onclick="fecharModal()">✕</button><img src="${fotosValidas[0]}" alt="${titulo}" loading="lazy">`}else{pdImgCol.innerHTML=`<button class="pd-close-mobile" onclick="fecharModal()">✕</button><div class="pd-img-placeholder"><span>${catEmoji(cat)}</span><p>Sem fotos</p></div>`}const condicaoBadgeHtml=condicao?`<span class="pd-condition-badge">${condicao}</span><br>`:'';const contatoIconMap={whatsapp:'📱',telefone:'📞',email:'✉️'};const contatoIcon=contatoIconMap[a.tipo_contato]||'💬';const contatoLabel={whatsapp:'WhatsApp',telefone:'Telefone',email:'E-mail'}[a.tipo_contato]||'Contato';const contatoVal=esc(a.contato||'');document.getElementById('modalConteudo').innerHTML=`<div>${condicaoBadgeHtml}<div class="pd-title">${titulo}</div><div class="pd-price">R$ ${preco}</div><div class="pd-section"><div class="pd-section-label">👤 Vendedor e Local</div><div class="pd-seller-card"><div class="pd-seller-avatar">${vendedor.charAt(0).toUpperCase()}</div><div style="flex:1;min-width:0"><div class="pd-seller-name">${vendedor}<span class="pd-seller-rating">4.9 ★</span></div><div class="pd-seller-local">◎ ${local}</div></div><span class="pd-verified" title="Verificado">🛡</span></div></div><div class="pd-section"><div class="pd-section-label">📋 Descrição</div><p class="pd-desc">${descricao.replace(/\n/g,'<br>')}</p></div><div class="pd-section"><div class="pd-tips-box"><div class="pd-tips-header">🛡 Dicas de Segurança do PitHub</div><div id="pdTipsContent"><div class="pd-tips-skel"><div class="pd-skel-line" style="width:100%"></div><div class="pd-skel-line" style="width:78%"></div><div class="pd-skel-line" style="width:88%"></div></div></div></div></div>${contatoVal?`<div class="modal-contato-block"><span class="modal-contato-icon">${contatoIcon}</span><div><div class="modal-contato-lbl">${contatoLabel}</div><div class="modal-contato-val">${contatoVal}</div></div></div>`:''}</div>`;document.getElementById('pdBtnInterest').onclick=()=>contatoAnunciante(String(a.id));overlay.classList.add('open');document.body.style.overflow='hidden';fetch(`${API}/visualizar_anuncio.php`,{method:'POST',headers:{'Content-Type':'application/json','X-Requested-With':'XMLHttpRequest'},credentials:'same-origin',body:JSON.stringify({id:a.id})}).catch(()=>{});const tips=await getSafetyTips(a.titulo);const tipsEl=document.getElementById('pdTipsContent');if(tipsEl)tipsEl.innerHTML=`<ul class="pd-tips-list">${tips.map(t=>`<li>${esc(String(t))}</li>`).join('')}</ul>`};
window.fecharModal=function(){overlay.classList.remove('open');document.body.style.overflow=''};
window.contatoAnunciante=function(id){const a=anunciosCache.get(String(id));if(a&&a.contato)toast(`${a.tipo_contato==='email'?'✉️':'📱'} ${a.contato}`);else toast('Informação de contato não disponível')};
function refreshPreviews(){previewBox.innerHTML='';fotosSelected.forEach((f,i)=>{const wrap=document.createElement('div');wrap.className='preview-thumb';const img=document.createElement('img');img.src=f.url;img.alt='Preview';const rm=document.createElement('span');rm.className='remove-thumb';rm.textContent='✕';rm.onclick=e=>{e.stopPropagation();e.preventDefault();URL.revokeObjectURL(f.url);fotosSelected.splice(i,1);refreshPreviews()};wrap.appendChild(img);wrap.appendChild(rm);previewBox.appendChild(wrap)})}
uploadInput.addEventListener('change',e=>{e.preventDefault();const files=[...e.target.files];if(fotosSelected.length+files.length>5){toast('Máximo de 5 fotos permitidas!',false);return}files.forEach(file=>{if(!file.type.startsWith('image/')){toast(`${file.name}: não é imagem válida`,false);return}if(file.size>5*1024*1024){toast(`${file.name}: excede 5MB`,false);return}fotosSelected.push({file,url:URL.createObjectURL(file)})});refreshPreviews();uploadInput.value=''});
async function adicionarAnuncio(){try{const titulo=fTitulo.value.trim(),cat=fCat.value,preco=parseFloat(fPreco.value),local=fLocal.value.trim(),desc=fDesc.value.trim(),tipoContato=fTipoContato.value,contato=fContato.value.trim(),condicao=fCondicao?fCondicao.value:'Seminovo';if(!titulo)throw new Error('Título é obrigatório');if(titulo.length<3)throw new Error('Título deve ter pelo menos 3 caracteres');if(!desc)throw new Error('Descrição é obrigatória');if(desc.length<10)throw new Error('Descrição: mínimo 10 caracteres');if(!local)throw new Error('Local é obrigatório');if(isNaN(preco)||preco<=0)throw new Error('Preço deve ser maior que zero');const erroContato=validarContato(tipoContato,contato);if(erroContato)throw new Error(erroContato);btnPublicar.disabled=true;btnPublicar.textContent='⏳ Publicando…';const fotosUrls=[];for(const f of fotosSelected){try{const url=await uploadFoto(f.file);if(url)fotosUrls.push(url)}catch(err){toast(err.message,false)}}await publicarAnuncio({titulo,descricao:desc,preco,categoria:cat,condicao,local,condominio:local.split(' ')[0],tipo_contato:tipoContato,contato,fotos:fotosUrls});toast('Anúncio publicado com sucesso! 🎉');await carregarAnuncios();fTitulo.value='';fPreco.value='';fDesc.value='';fLocal.value='';fCat.value='eletro';fContato.value='';fTipoContato.value='whatsapp';if(fCondicao)fCondicao.value='Novo';document.querySelectorAll('#sfConditionRow .sf-cond-btn').forEach((b,i)=>{b.classList.toggle('on',i===0)});fotosSelected.forEach(f=>URL.revokeObjectURL(f.url));fotosSelected=[];refreshPreviews();setTimeout(()=>{document.getElementById('formPanel').style.display='none';btnPublicar.textContent='Publicar Agora →'},2000)}catch(err){toast(err.message,false)}finally{btnPublicar.disabled=false;if(btnPublicar.textContent==='⏳ Publicando…')btnPublicar.textContent='Publicar Agora →'}}
document.querySelectorAll('#sfConditionRow .sf-cond-btn').forEach(btn=>{btn.addEventListener('click',function(){document.querySelectorAll('#sfConditionRow .sf-cond-btn').forEach(b=>b.classList.remove('on'));this.classList.add('on');fCondicao.value=this.dataset.val})});
async function sfGerarDescricao(){const titulo=fTitulo.value.trim();if(!titulo){toast('Digite o título do item primeiro',false);return}const btn=document.getElementById('sfIaBtn'),icon=document.getElementById('sfIaIcon'),label=document.getElementById('sfIaLabel');btn.disabled=true;icon.className='sf-ia-spinning';icon.textContent='↻';label.textContent='Gerando…';try{const cat=fCat.options[fCat.selectedIndex]?.text||fCat.value;const res=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-5-20250929',max_tokens:200,messages:[{role:'user',content:`Escreva uma descrição curta e convincente (máx 3 frases) para um anúncio de venda de "${titulo}" na categoria "${cat}" em um marketplace de condomínio. Tom informal, honesto, destacando bom estado e facilidade de entrega segura. Responda APENAS com o texto da descrição, sem aspas nem explicações.`}]})});if(!res.ok)throw new Error('API error');const data=await res.json();const desc=data.content?.[0]?.text?.trim()||'';if(desc){fDesc.value=desc;fDesc.style.animation='none';requestAnimationFrame(()=>{fDesc.style.animation='sfDescFadeIn .4s ease'});toast('Descrição gerada com IA ✦')}}catch{toast('Não foi possível gerar a descrição. Tente novamente.',false)}finally{btn.disabled=false;icon.className='';icon.textContent='✦';label.textContent='Gerar com IA'}}
function toggleForm(){mostrarView('explorar');const panel=document.getElementById('formPanel');if(!panel)return;const isHidden=panel.style.display==='none'||panel.style.display==='';if(isHidden){panel.style.display='block';panel.style.animation='slideDown .35s ease';setTimeout(()=>panel.scrollIntoView({behavior:'smooth',block:'start'}),80)}else{panel.style.display='none'}}
inputBusca.addEventListener('keyup',e=>{if(e.key==='Enter')carregarAnuncios()});
inputBusca.addEventListener('input',()=>{clearTimeout(inputBusca._t);inputBusca._t=setTimeout(carregarAnuncios,400)});
btnPublicar.addEventListener('click',e=>{e.preventDefault();adicionarAnuncio()});
const CONTATO_PLACEHOLDERS={whatsapp:'(11) 91234-5678',telefone:'(11) 3456-7890',email:'seu@email.com'};
fTipoContato.addEventListener('change',()=>{fContato.placeholder=CONTATO_PLACEHOLDERS[fTipoContato.value]||'';fContato.value=''});
vGrid.addEventListener('click',()=>{isGrid=true;vGrid.classList.add('on');vList.classList.remove('on');cardsEl.classList.remove('list')});
vList.addEventListener('click',()=>{isGrid=false;vList.classList.add('on');vGrid.classList.remove('on');cardsEl.classList.add('list')});
overlay.addEventListener('click',e=>{if(e.target===overlay)fecharModal()});
window.addEventListener('beforeunload',()=>{fotosSelected.forEach(f=>URL.revokeObjectURL(f.url))});
const elViewExplorar=document.getElementById('viewExplorar'),elViewHero=document.getElementById('heroSection'),elViewConversas=document.getElementById('viewConversas'),elViewPerfil=document.getElementById('viewPerfil'),navExplorar=document.getElementById('navExplorar'),navConversas=document.getElementById('navConversas'),navPerfil=document.getElementById('navPerfil');
function mostrarView(view){elViewExplorar.style.display='none';elViewHero.style.display='none';elViewConversas.style.display='none';elViewPerfil.style.display='none';[navExplorar,navConversas,navPerfil].forEach(n=>n&&n.classList.remove('active'));if(view==='conversas'){elViewConversas.style.display='block';navConversas.classList.add('active');renderChatList()}else if(view==='perfil'){elViewPerfil.style.display='block';navPerfil.classList.add('active');renderProfile()}else{elViewExplorar.style.display='';elViewHero.style.display='';navExplorar.classList.add('active')}}
window.carregarAnuncios=carregarAnuncios;window.sfGerarDescricao=sfGerarDescricao;window.limparFiltros=limparFiltros;
const profileData={name:'Morador PitHub',condoName:'Residencial Aurora',avatar:'https://picsum.photos/seed/user/200/200',reputation:{averageRating:4.9,totalReviews:12,reviews:[{id:'rev1',reviewerName:'Alice Mendes',reviewerAvatar:'https://picsum.photos/seed/alice/50/50',rating:5,comment:'Vendedor super atencioso! O monitor estava impecável e a entrega na portaria foi muito rápida.',date:'Há 2 semanas'},{id:'rev2',reviewerName:'Marcos Silva',reviewerAvatar:'https://picsum.photos/seed/marcos/50/50',rating:4,comment:'Tudo certo com a cafeteira. Recomendo!',date:'Há 1 mês'}]}};
let profileActiveTab='info';
function renderProfile(){const pfAvatar=document.getElementById('pfAvatar'),pfName=document.getElementById('pfName'),pfCondo=document.getElementById('pfCondo'),pfStat=document.getElementById('pfStatRating');if(pfAvatar)pfAvatar.src=profileData.avatar;if(pfName)pfName.textContent=profileData.name;if(pfCondo)pfCondo.textContent='Morador do '+profileData.condoName;if(pfStat){pfStat.querySelector('.pf-stat-num').textContent=profileData.reputation.averageRating+' ★';pfStat.querySelector('.pf-stat-lbl').textContent=profileData.reputation.totalReviews+' Avaliações'}const starsDisp=document.getElementById('pfStarsDisplay');if(starsDisp){const avg=Math.floor(profileData.reputation.averageRating);starsDisp.textContent=[1,2,3,4,5].map(s=>s<=avg?'★':'☆').join('');starsDisp.style.color='#f59e0b'}renderProfileReviews();setProfileTab(profileActiveTab,false)}
function renderProfileReviews(){const listEl=document.getElementById('pfReviewsList');if(!listEl)return;listEl.innerHTML=profileData.reputation.reviews.map(rv=>{const stars=[1,2,3,4,5].map(s=>`<span style="color:${s<=rv.rating?'#f59e0b':'var(--sand)'}">★</span>`).join('');const avatarHtml=rv.reviewerAvatar?`<img class="pf-review-avatar" src="${esc(rv.reviewerAvatar)}" alt="" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="pf-review-avatar-fallback" style="display:none">${esc(rv.reviewerName.charAt(0))}</div>`:`<div class="pf-review-avatar-fallback">${esc(rv.reviewerName.charAt(0))}</div>`;return`<div class="pf-review-card"><div class="pf-review-top"><div class="pf-review-user">${avatarHtml}<div><div class="pf-reviewer-name">${esc(rv.reviewerName)}</div><div class="pf-reviewer-date">${esc(rv.date)}</div></div></div><div class="pf-review-stars">${stars}</div></div><p class="pf-review-comment"><span class="pf-review-quote">"</span>${esc(rv.comment)}</p></div>`}).join('')}
window.setProfileTab=function(tab,doRender=true){profileActiveTab=tab;const panelInfo=document.getElementById('pfPanelInfo'),panelReviews=document.getElementById('pfPanelReviews'),tabInfo=document.getElementById('pfTabInfo'),tabReviews=document.getElementById('pfTabReviews');if(!panelInfo)return;if(tab==='reviews'){panelInfo.style.display='none';panelReviews.style.display='';tabInfo.classList.remove('on');tabReviews.classList.add('on');panelReviews.style.animation='none';requestAnimationFrame(()=>{panelReviews.style.animation=''})}else{panelReviews.style.display='none';panelInfo.style.display='';tabReviews.classList.remove('on');tabInfo.classList.add('on');panelInfo.style.animation='none';requestAnimationFrame(()=>{panelInfo.style.animation=''})}};
let chatsData=[{id:'c1',name:'Ana Cláudia',lastMessage:'Oi! O monitor ainda está disponível? Posso ver hoje?',time:'14:20',item:'Monitor Dell 24"',avatar:'https://picsum.photos/seed/ana/100/100',unread:true,status:'active'},{id:'c2',name:'Roberto',lastMessage:'Combinado, te encontro na portaria do Aurora às 18h.',time:'Ontem',item:'Bicicleta Caloi',avatar:'https://picsum.photos/seed/roberto/100/100',unread:false,status:'active'}];
let chatBuscaTerm='';
function atualizarNavBadge(){const badge=document.getElementById('navBadge'),nUnread=chatsData.filter(c=>c.unread).length;if(nUnread>0){badge.textContent=nUnread;badge.style.display='inline-flex'}else badge.style.display='none'}
function renderChatList(){const el=document.getElementById('chatList');if(!el)return;const term=chatBuscaTerm.toLowerCase(),filtered=chatsData.filter(c=>c.name.toLowerCase().includes(term)||c.item.toLowerCase().includes(term)||c.lastMessage.toLowerCase().includes(term));if(filtered.length===0){el.innerHTML='<div class="cl-empty"><div class="cl-empty-icon">💬</div><h3>Nenhuma conversa por aqui</h3><p>Seus chats aparecerão aqui quando alguém se interessar pelo seu item.</p></div>';return}el.innerHTML=filtered.map(chat=>{const avatarHtml=chat.avatar?`<img class="cl-avatar" src="${esc(chat.avatar)}" alt="${esc(chat.name)}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="cl-avatar-fallback" style="display:none">${esc(chat.name.charAt(0))}</div>`:`<div class="cl-avatar-fallback">${esc(chat.name.charAt(0))}</div>`;const unreadDot=chat.unread?'<span class="cl-unread-dot"></span>':'';const footerHtml=chat.status==='completed'?`<div class="cl-card-foot"><span class="cl-tag-done"><span class="cl-star">★</span> Negócio Concluído</span></div>`:`<div class="cl-card-foot"><button class="cl-btn-finish" onclick="abrirReviewModal(event,'${esc(chat.id)}')">✓ Finalizar Negócio</button></div>`;return`<div class="cl-card${chat.unread?' unread':''}" id="chat-${esc(chat.id)}" onclick="marcarLido('${esc(chat.id)}')"><div class="cl-card-row"><div class="cl-avatar-wrap">${avatarHtml}${unreadDot}</div><div class="cl-info"><div class="cl-info-top"><span class="cl-name">${esc(chat.name)}</span><span class="cl-time">${esc(chat.time)}</span></div><div class="cl-item">${esc(chat.item)}</div><div class="cl-msg">${esc(chat.lastMessage)}</div></div></div>${footerHtml}</div>`}).join('')}
window.marcarLido=function(id){chatsData=chatsData.map(c=>c.id===id?{...c,unread:false}:c);atualizarNavBadge();renderChatList()};
document.getElementById('chatBusca').addEventListener('input',function(){chatBuscaTerm=this.value;renderChatList()});
let reviewingChatId=null,reviewRating=0,reviewHover=0;
const reviewOverlay=document.getElementById('reviewOverlay');
function rmUpdateStars(){document.querySelectorAll('.rm-star-btn').forEach(btn=>{const v=Number(btn.dataset.val);btn.classList.toggle('hovered',v<=reviewHover&&reviewHover>0);btn.classList.toggle('selected',v<=reviewRating&&reviewHover===0);btn.style.color=(reviewHover>0?v<=reviewHover:v<=reviewRating)?'#f59e0b':'var(--sand)'});const btn=document.getElementById('rmSubmitBtn');if(btn)btn.disabled=reviewRating===0}
window.abrirReviewModal=function(e,chatId){e.stopPropagation();reviewingChatId=chatId;reviewRating=0;reviewHover=0;const chat=chatsData.find(c=>c.id===chatId);if(!chat)return;const nameEl=document.getElementById('rmTargetName'),comment=document.getElementById('rmComment');if(nameEl)nameEl.textContent=chat.name;if(comment)comment.value='';document.getElementById('rmStateNormal').style.display='';document.getElementById('rmStateSuccess').style.display='none';rmUpdateStars();reviewOverlay.classList.add('open');document.body.style.overflow='hidden'};
window.fecharReviewModal=function(){reviewOverlay.classList.remove('open');document.body.style.overflow='';reviewingChatId=null;reviewRating=0;reviewHover=0};
document.querySelectorAll('.rm-star-btn').forEach(btn=>{const val=Number(btn.dataset.val);btn.addEventListener('mouseenter',()=>{reviewHover=val;rmUpdateStars()});btn.addEventListener('mouseleave',()=>{reviewHover=0;rmUpdateStars()});btn.addEventListener('click',()=>{reviewRating=val;reviewHover=0;rmUpdateStars()})});
window.enviarReview=function(){if(reviewRating===0||!reviewingChatId)return;const comment=document.getElementById('rmComment')?.value.trim()||'',chat=chatsData.find(c=>c.id===reviewingChatId);console.log(`Review: ${chat?.name} — ${reviewRating}★ — "${comment}"`);document.getElementById('rmStateNormal').style.display='none';document.getElementById('rmStateSuccess').style.display='';chatsData=chatsData.map(c=>c.id===reviewingChatId?{...c,status:'completed',unread:false}:c);setTimeout(()=>{fecharReviewModal();atualizarNavBadge();renderChatList();if(chat){profileData.reputation.reviews.unshift({id:'rev_'+Date.now(),reviewerName:'Você',reviewerAvatar:'',rating:reviewRating,comment:comment||'Negócio concluído com sucesso!',date:'Agora mesmo'});profileData.reputation.totalReviews++}toast(`Negócio com ${chat?.name} avaliado! ${reviewRating}★`)},2000)};
reviewOverlay.addEventListener('click',e=>{if(e.target===reviewOverlay)fecharReviewModal()});
navExplorar.classList.add('active');
atualizarNavBadge();
carregarAnuncios();
</script>
</body>
</html>
