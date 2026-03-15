<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AUTONIX — README</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;900&family=Rajdhani:wght@300;400;500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --r:#ff0033;--r2:#cc0028;
  --glow:rgba(255,0,51,.55);--glow2:rgba(255,0,51,.2);
  --bg:#050505;--bg2:#090909;--bg3:#0d0d0d;
  --w:#ffffff;--g:#999;--g2:#555;
  --bd:rgba(255,0,51,.25);--bd2:rgba(255,0,51,.1);
  --cyan:#00e5ff;--green:#22c55e;--gold:#f59e0b;
}
html{scroll-behavior:smooth}
body{font-family:'Rajdhani',sans-serif;background:var(--bg);color:var(--w);overflow-x:hidden;line-height:1.7}

/* SCROLLBAR */
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--r);border-radius:3px}

/* GRID BG */
body::before{content:'';position:fixed;inset:0;z-index:-2;
  background:linear-gradient(90deg,transparent 49%,var(--bd) 50%,transparent 51%) 0 0/44px 44px,
             linear-gradient(0deg,transparent 49%,var(--bd) 50%,transparent 51%) 0 0/44px 44px;
  opacity:.05;animation:gdrift 25s linear infinite;pointer-events:none}
@keyframes gdrift{to{transform:translate(44px,44px)}}

/* SCAN LINE */
body::after{content:'';position:fixed;top:0;left:0;width:100%;height:3px;z-index:9999;pointer-events:none;
  background:linear-gradient(90deg,transparent,var(--r),transparent);
  box-shadow:0 0 18px var(--glow);animation:scan 5s linear infinite}
@keyframes scan{0%{transform:translateY(-4px);opacity:0}5%{opacity:1}95%{opacity:.6}100%{transform:translateY(100vh);opacity:0}}

/* CORNER BRACKETS */
.crn{position:fixed;width:55px;height:55px;z-index:9998;pointer-events:none}
.crn::before,.crn::after{content:'';position:absolute;background:var(--r)}
.crn::before{width:100%;height:2px}.crn::after{width:2px;height:100%}
.crn.tl{top:0;left:0}.crn.tr{top:0;right:0;transform:scaleX(-1)}
.crn.bl{bottom:0;left:0;transform:scaleY(-1)}.crn.br{bottom:0;right:0;transform:scale(-1)}

/* NAV */
nav{position:fixed;top:0;left:0;width:100%;z-index:9000;
  background:rgba(5,5,5,.96);backdrop-filter:blur(12px);
  border-bottom:1px solid var(--bd);box-shadow:0 0 18px var(--glow2);padding:.85rem 0}
.nav-inner{max-width:1100px;margin:0 auto;padding:0 2rem;display:flex;align-items:center;justify-content:space-between;gap:1rem}
.nav-brand{font-family:'Orbitron',sans-serif;font-size:1.35rem;font-weight:700;letter-spacing:3px;color:var(--w);text-decoration:none;display:flex;align-items:center;gap:.6rem;flex-shrink:0}
.nav-brand i{color:var(--r);animation:ipulse 2s ease-in-out infinite}
@keyframes ipulse{0%,100%{filter:drop-shadow(0 0 5px var(--glow))}50%{filter:drop-shadow(0 0 15px var(--r))}}
.nav-tag{font-family:'Orbitron',sans-serif;font-size:.58rem;letter-spacing:3px;color:var(--g);background:rgba(255,0,51,.07);border:1px solid var(--bd2);border-radius:3px;padding:.18rem .55rem}
.nav-links{display:flex;gap:1.8rem;list-style:none}
.nav-links a{font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:2px;color:var(--g);text-decoration:none;text-transform:uppercase;transition:all .3s;position:relative}
.nav-links a::after{content:'';position:absolute;bottom:-4px;left:0;width:0;height:1px;background:var(--r);transition:width .3s;box-shadow:0 0 6px var(--glow)}
.nav-links a:hover{color:var(--r)}.nav-links a:hover::after{width:100%}
.nav-cta{font-family:'Orbitron',sans-serif;font-size:.65rem;letter-spacing:2px;padding:.45rem 1.1rem;background:var(--r);color:var(--w);text-decoration:none;border-radius:4px;clip-path:polygon(6px 0,100% 0,100% calc(100% - 6px),calc(100% - 6px) 100%,0 100%,0 6px);transition:all .3s;flex-shrink:0}
.nav-cta:hover{background:var(--r2);box-shadow:0 0 18px var(--glow)}

/* MAIN */
main{max-width:1100px;margin:0 auto;padding:110px 2rem 80px}

/* ── HERO ── */
.hero{text-align:center;padding:4rem 0 2.5rem;position:relative}
.hero-eye{font-family:'Share Tech Mono',monospace;font-size:.78rem;color:var(--r);letter-spacing:4px;text-transform:uppercase;margin-bottom:1.5rem;opacity:.7}
.hero-title{font-family:'Orbitron',sans-serif;font-size:clamp(3.8rem,10vw,8rem);font-weight:900;letter-spacing:clamp(6px,2vw,18px);line-height:1;margin-bottom:1.2rem;background:linear-gradient(135deg,#fff 15%,#ff6688 48%,var(--r) 68%);background-size:200%;-webkit-background-clip:text;-webkit-text-fill-color:transparent;animation:tsh 4s linear infinite}
@keyframes tsh{0%,100%{background-position:100% center}50%{background-position:0% center}}
.hero-sub{font-family:'Orbitron',sans-serif;font-size:clamp(.65rem,1.4vw,.88rem);letter-spacing:5px;color:var(--g);margin-bottom:.9rem}
.hero-tag{font-size:1.1rem;color:var(--g);letter-spacing:2px;margin-bottom:2.2rem}
.hero-tag span{color:var(--r);font-weight:700}
.hero-div{width:180px;height:1px;background:linear-gradient(90deg,transparent,var(--r),transparent);box-shadow:0 0 12px var(--glow);margin:0 auto 2.2rem}

/* BADGES */
.badge-row{display:flex;flex-wrap:wrap;gap:.55rem;justify-content:center;margin-bottom:1.8rem}
.badge{display:inline-flex;align-items:center;gap:.38rem;padding:.3rem .85rem;border-radius:4px;font-family:'Share Tech Mono',monospace;font-size:.7rem;letter-spacing:1px;text-decoration:none;transition:all .25s;white-space:nowrap;cursor:default}
.badge:hover{transform:translateY(-2px)}
.b-green{background:rgba(34,197,94,.1);border:1px solid rgba(34,197,94,.3);color:#22c55e}
.b-purple{background:rgba(127,82,255,.1);border:1px solid rgba(127,82,255,.3);color:#a78bfa}
.b-gold{background:rgba(255,202,40,.08);border:1px solid rgba(255,202,40,.25);color:#fbbf24}
.b-droid{background:rgba(61,220,132,.08);border:1px solid rgba(61,220,132,.25);color:#3ddc84}
.b-cyan{background:rgba(0,229,255,.08);border:1px solid rgba(0,229,255,.22);color:var(--cyan)}

/* LINK ROW */
.link-row{display:flex;flex-wrap:wrap;gap:.8rem;justify-content:center}
.slink{display:inline-flex;align-items:center;gap:.45rem;font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:1.5px;color:var(--r);text-decoration:none;border:1px solid var(--bd);padding:.42rem 1.1rem;border-radius:4px;transition:all .3s;clip-path:polygon(6px 0,100% 0,100% calc(100% - 6px),calc(100% - 6px) 100%,0 100%,0 6px)}
.slink:hover{background:rgba(255,0,51,.1);box-shadow:0 0 14px var(--glow2);transform:translateY(-2px)}
.slink.primary{background:rgba(255,0,51,.12)}

/* SECTION */
section{margin-bottom:3.5rem}
.sh{display:flex;align-items:center;gap:.9rem;margin-bottom:1.8rem;padding-bottom:.9rem;border-bottom:1px solid var(--bd2)}
.si{width:38px;height:38px;background:rgba(255,0,51,.1);border:1px solid var(--bd);border-radius:8px;display:flex;align-items:center;justify-content:center;color:var(--r);font-size:1rem;flex-shrink:0}
.stit{font-family:'Orbitron',sans-serif;font-size:1.2rem;font-weight:700;letter-spacing:3px}
.stit .hl{color:var(--r)}

/* OVERVIEW */
.ocard{background:var(--bg2);border:1px solid var(--bd);border-radius:12px;padding:2rem;position:relative;overflow:hidden;clip-path:polygon(0 0,calc(100% - 20px) 0,100% 20px,100% 100%,20px 100%,0 calc(100% - 20px))}
.ocard::before{content:'';position:absolute;top:0;left:0;width:100%;height:2px;background:linear-gradient(90deg,transparent,var(--r),transparent)}
.ocard p{font-size:1.02rem;color:#ccc;line-height:1.9;margin-bottom:1.1rem}
.ocard p:last-child{margin-bottom:0}
.ocard strong{color:var(--w)}
.mbox{margin-top:1.5rem;background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:1.2rem;font-family:'Share Tech Mono',monospace;font-size:.8rem;color:var(--r);text-align:center;letter-spacing:1.5px}
.mbox-label{font-size:.6rem;letter-spacing:3px;color:rgba(255,0,51,.45);margin-bottom:.7rem;font-family:'Orbitron',sans-serif}
.mflow span{color:var(--r)}.mflow .arr{color:rgba(255,0,51,.35)}

/* OBJ GRID */
.obj-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.1rem}
.obc{background:var(--bg2);border:1px solid var(--bd2);border-radius:10px;padding:1.5rem;transition:all .3s;position:relative;overflow:hidden}
.obc::after{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--r);transition:width .4s}
.obc:hover{border-color:var(--r);box-shadow:0 0 22px var(--glow2);transform:translateY(-4px)}.obc:hover::after{width:100%}
.obt{font-family:'Orbitron',sans-serif;font-size:.78rem;font-weight:600;letter-spacing:2px;color:var(--r);margin-bottom:.9rem;display:flex;align-items:center;gap:.55rem}
.obc ul{list-style:none;display:flex;flex-direction:column;gap:.38rem}
.obc ul li{font-size:.93rem;color:var(--g);display:flex;align-items:flex-start;gap:.55rem}
.obc ul li::before{content:'▸';color:var(--r);flex-shrink:0;margin-top:2px}

/* FEAT TABLE */
.ftbl{width:100%;border-collapse:separate;border-spacing:0;background:var(--bg2);border:1px solid var(--bd);border-radius:12px;overflow:hidden}
.ftbl thead tr{background:rgba(255,0,51,.07)}
.ftbl thead th{font-family:'Orbitron',sans-serif;font-size:.67rem;letter-spacing:2px;color:var(--r);padding:.85rem 1.1rem;text-align:left;border-bottom:1px solid var(--bd)}
.ftbl tbody tr{border-bottom:1px solid var(--bd2);transition:background .2s}
.ftbl tbody tr:last-child{border-bottom:none}
.ftbl tbody tr:hover{background:rgba(255,0,51,.04)}
.ftbl td{padding:.85rem 1.1rem;font-size:.93rem;vertical-align:top}
.ftbl td:first-child{font-family:'Orbitron',sans-serif;font-size:.72rem;letter-spacing:1px;color:var(--w);font-weight:600;white-space:nowrap}
.ftbl td:nth-child(2){color:#bbb}
.ftbl td:last-child{font-family:'Share Tech Mono',monospace;font-size:.7rem;color:var(--r);opacity:.85}
.wip{font-size:.58rem;background:rgba(245,158,11,.1);border:1px solid rgba(245,158,11,.28);color:#f59e0b;border-radius:20px;padding:.1rem .45rem;margin-left:.4rem;font-family:'Orbitron',sans-serif;letter-spacing:1px;vertical-align:middle}

/* TECH STACK */
.sg{margin-bottom:1.4rem}
.sgt{font-family:'Orbitron',sans-serif;font-size:.7rem;letter-spacing:3px;color:var(--g2);margin-bottom:.8rem;display:flex;align-items:center;gap:.55rem}
.sgt i{color:var(--r)}
.sp-row{display:flex;flex-wrap:wrap;gap:.65rem}
.sp{display:inline-flex;align-items:center;gap:.45rem;padding:.4rem .95rem;border-radius:6px;font-family:'Share Tech Mono',monospace;font-size:.72rem;letter-spacing:1px;transition:all .25s;cursor:default}
.sp:hover{transform:translateY(-3px)}
.spg{background:rgba(61,220,132,.07);border:1px solid rgba(61,220,132,.22);color:#3ddc84}
.spp{background:rgba(127,82,255,.07);border:1px solid rgba(127,82,255,.22);color:#a78bfa}
.spo{background:rgba(255,102,0,.07);border:1px solid rgba(255,102,0,.22);color:#fb923c}
.spau{background:rgba(255,202,40,.07);border:1px solid rgba(255,202,40,.22);color:#fbbf24}
.spb{background:rgba(66,133,244,.07);border:1px solid rgba(66,133,244,.22);color:#60a5fa}
.spr{background:rgba(234,67,53,.07);border:1px solid rgba(234,67,53,.22);color:#f87171}
.spt{background:rgba(0,137,123,.07);border:1px solid rgba(0,137,123,.28);color:#2dd4bf}
.spm{background:rgba(126,188,111,.07);border:1px solid rgba(126,188,111,.28);color:#86efac}
.spdk{background:rgba(20,20,20,.9);border:1px solid #2a2a2a;color:#9ca3af}
.spbr{background:rgba(2,48,58,.5);border:1px solid #02303a99;color:#5eead4}
.spfr{background:rgba(240,83,50,.07);border:1px solid rgba(240,83,50,.22);color:#fb923c}

/* ARCH */
.arch-wrap{background:var(--bg2);border:1px solid var(--bd);border-radius:12px;padding:2rem;overflow-x:auto}
.arch{display:flex;flex-direction:column;align-items:center;gap:.9rem;min-width:580px}
.ar{display:flex;gap:.8rem;justify-content:center;align-items:center;flex-wrap:wrap}
.an{background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:.55rem 1.1rem;font-family:'Orbitron',sans-serif;font-size:.65rem;letter-spacing:1.5px;color:var(--w);text-align:center;white-space:nowrap;transition:all .3s}
.an:hover{border-color:var(--r);box-shadow:0 0 12px var(--glow2)}
.an.main{background:rgba(255,0,51,.1);border-color:var(--r);color:var(--r);font-size:.72rem;padding:.65rem 1.5rem}
.an.cloud{background:rgba(0,229,255,.05);border-color:rgba(0,229,255,.25);color:var(--cyan)}
.an.alert{background:rgba(245,158,11,.07);border-color:rgba(245,158,11,.28);color:#fbbf24}
.aarw{color:rgba(255,0,51,.55);font-size:.85rem;display:flex;justify-content:center}

.mod-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin-top:1.4rem}
.mc{background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:1.1rem;transition:all .3s}
.mc:hover{border-color:var(--bd);transform:translateY(-3px)}
.mct{font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:2px;color:var(--r);margin-bottom:.75rem;display:flex;align-items:center;gap:.45rem}
.mc ul{list-style:none;display:flex;flex-direction:column;gap:.28rem}
.mc ul li{font-family:'Share Tech Mono',monospace;font-size:.68rem;color:var(--g);display:flex;align-items:center;gap:.35rem}
.mc ul li::before{content:'›';color:var(--r)}

/* INSTALL */
.itabs{display:flex;border-bottom:1px solid var(--bd2)}
.itab{font-family:'Orbitron',sans-serif;font-size:.67rem;letter-spacing:2px;padding:.55rem 1.3rem;background:none;border:none;border-bottom:2px solid transparent;color:var(--g);cursor:pointer;transition:all .3s;text-transform:uppercase}
.itab.on{color:var(--r);border-bottom-color:var(--r)}
.itp{display:none;padding:1.4rem 0}.itp.on{display:block}
.cblk{background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;overflow:hidden;margin-bottom:1.1rem}
.chdr{background:rgba(255,0,51,.05);border-bottom:1px solid var(--bd2);padding:.45rem .9rem;display:flex;align-items:center;justify-content:space-between}
.clng{font-family:'Orbitron',sans-serif;font-size:.6rem;letter-spacing:2px;color:var(--r)}
.cdots{display:flex;gap:.35rem}
.cdot{width:9px;height:9px;border-radius:50%}
.cdot:nth-child(1){background:#ff5f57}.cdot:nth-child(2){background:#febc2e}.cdot:nth-child(3){background:#28c840}
pre{padding:1.1rem 1.4rem;font-family:'Share Tech Mono',monospace;font-size:.79rem;line-height:1.9;color:#ccc;overflow-x:auto}
.cm{color:rgba(255,0,51,.45)}.kw{color:#a78bfa}.sv{color:#86efac}.sk{color:#fbbf24}
.pq-grid{display:grid;grid-template-columns:1fr 1fr;gap:.75rem;margin-top:.9rem}
.pqi{display:flex;align-items:center;gap:.75rem;background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:.75rem .95rem}
.pqi i{color:var(--r);width:14px;text-align:center;flex-shrink:0}
.pqi span{font-size:.9rem;color:#bbb}
.bstps{display:flex;flex-direction:column;gap:.55rem;margin-top:.9rem}
.bst{display:flex;align-items:center;gap:.9rem;background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:.72rem 1.1rem;transition:all .3s}
.bst:hover{border-color:var(--bd);transform:translateX(4px)}
.bsn{font-family:'Orbitron',sans-serif;font-size:.6rem;font-weight:700;width:22px;height:22px;border-radius:50%;background:var(--r);color:#fff;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.bst span{font-size:.93rem;color:#bbb}

/* TEST */
.ttbl{width:100%;border-collapse:separate;border-spacing:0;background:var(--bg2);border:1px solid var(--bd);border-radius:12px;overflow:hidden}
.ttbl thead tr{background:rgba(255,0,51,.06)}
.ttbl thead th{font-family:'Orbitron',sans-serif;font-size:.65rem;letter-spacing:2px;color:var(--r);padding:.78rem 1.1rem;text-align:left;border-bottom:1px solid var(--bd)}
.ttbl tbody tr{border-bottom:1px solid var(--bd2);transition:background .2s}
.ttbl tbody tr:last-child{border-bottom:none}
.ttbl tbody tr:hover{background:rgba(255,0,51,.03)}
.ttbl td{padding:.78rem 1.1rem;font-size:.9rem}
.tid{font-family:'Orbitron',sans-serif;font-size:.65rem;letter-spacing:1px;color:var(--r)}
.tpass{display:inline-flex;align-items:center;gap:.35rem;color:var(--green);font-family:'Share Tech Mono',monospace;font-size:.72rem}
.trt{font-family:'Share Tech Mono',monospace;font-size:.75rem;color:var(--cyan)}
.perf-row{display:flex;gap:.9rem;margin-top:1.4rem;flex-wrap:wrap}
.pc{flex:1;min-width:170px;background:var(--bg2);border:1px solid var(--bd);border-radius:10px;padding:1.1rem;text-align:center;clip-path:polygon(0 0,calc(100% - 10px) 0,100% 10px,100% 100%,10px 100%,0 calc(100% - 10px))}
.pv{font-family:'Orbitron',sans-serif;font-size:1.7rem;font-weight:700;color:var(--r);display:block;filter:drop-shadow(0 0 8px var(--glow))}
.pl{font-size:.75rem;color:var(--g);letter-spacing:1px;text-transform:uppercase;margin-top:.25rem}

/* FUTURE */
.fg{display:grid;grid-template-columns:1fr 1fr;gap:1.1rem}
.fc2{background:var(--bg2);border:1px solid var(--bd2);border-radius:10px;padding:1.4rem;transition:all .3s}
.fc2:hover{border-color:var(--bd);box-shadow:0 0 18px var(--glow2);transform:translateY(-4px)}
.fct{font-family:'Orbitron',sans-serif;font-size:.75rem;letter-spacing:2px;color:var(--r);margin-bottom:.85rem;display:flex;align-items:center;gap:.55rem}
.fc2 ul{list-style:none;display:flex;flex-direction:column;gap:.32rem}
.fc2 ul li{font-size:.9rem;color:var(--g);display:flex;align-items:flex-start;gap:.45rem}
.fc2 ul li::before{content:'◦';color:var(--r);flex-shrink:0}

/* TEAM */
.team-row{display:flex;gap:1.3rem;flex-wrap:wrap;justify-content:center}
.tc{flex:1;min-width:250px;max-width:320px;background:var(--bg2);border:1px solid var(--bd);border-radius:14px;padding:1.8rem;text-align:center;position:relative;overflow:hidden;clip-path:polygon(0 0,calc(100% - 18px) 0,100% 18px,100% 100%,18px 100%,0 calc(100% - 18px));transition:all .3s}
.tc::before{content:'';position:absolute;top:0;left:0;width:100%;height:2px;background:linear-gradient(90deg,transparent,var(--r),transparent);animation:gpulse 2.5s ease-in-out infinite}
@keyframes gpulse{0%,100%{opacity:.3}50%{opacity:1}}
.tc:hover{box-shadow:0 0 30px var(--glow2);transform:translateY(-6px)}
.tav{width:86px;height:86px;border-radius:50%;border:2.5px solid var(--r);margin:0 auto 1.1rem;overflow:hidden;box-shadow:0 0 16px var(--glow2)}
.tav img{width:100%;height:100%;object-fit:cover}
.tav-ph{width:86px;height:86px;border-radius:50%;border:2.5px solid var(--r);margin:0 auto 1.1rem;background:rgba(255,0,51,.1);display:flex;align-items:center;justify-content:center;font-size:2rem;color:var(--r);box-shadow:0 0 16px var(--glow2)}
.tn2{font-family:'Orbitron',sans-serif;font-size:.88rem;font-weight:700;letter-spacing:2px;margin-bottom:.3rem}
.tr3{font-size:.85rem;color:var(--g);margin-bottom:.9rem}
.tgh{display:inline-flex;align-items:center;gap:.4rem;font-family:'Share Tech Mono',monospace;font-size:.7rem;color:var(--r);text-decoration:none;border:1px solid var(--bd);padding:.28rem .75rem;border-radius:4px;transition:all .3s}
.tgh:hover{background:rgba(255,0,51,.1)}
.guide-card{background:var(--bg2);border:1px solid var(--bd2);border-radius:10px;padding:1.4rem;text-align:center;margin-top:1.4rem}
.gn{font-family:'Orbitron',sans-serif;font-size:.85rem;letter-spacing:2px;margin-bottom:.3rem}
.gr{font-size:.85rem;color:var(--g);margin-bottom:.35rem}
.gd{font-size:.8rem;color:var(--g2)}

/* LICENSE */
.lic-box{background:var(--bg2);border:1px solid var(--bd);border-radius:12px;padding:2rem;text-align:center}
.lit{font-family:'Orbitron',sans-serif;font-size:1rem;letter-spacing:3px;color:var(--r);margin-bottom:.9rem}
.lic-code{background:var(--bg3);border:1px solid var(--bd2);border-radius:8px;padding:.9rem 1.1rem;font-family:'Share Tech Mono',monospace;font-size:.75rem;color:#bbb;text-align:left;margin:.9rem 0;line-height:1.85}

/* SUPPORT */
.sup-links{display:flex;gap:.9rem;flex-wrap:wrap;justify-content:center;margin-bottom:1.8rem}
.sl2{display:inline-flex;align-items:center;gap:.45rem;font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:1.5px;text-decoration:none;padding:.5rem 1.2rem;border-radius:6px;transition:all .3s;clip-path:polygon(6px 0,100% 0,100% calc(100% - 6px),calc(100% - 6px) 100%,0 100%,0 6px)}
.sl2:hover{transform:translateY(-3px)}
.sl-red{background:rgba(255,0,51,.1);border:1px solid var(--bd);color:var(--r)}.sl-red:hover{box-shadow:0 0 14px var(--glow2)}
.sl-blue{background:rgba(96,165,250,.07);border:1px solid rgba(96,165,250,.22);color:#60a5fa}.sl-blue:hover{box-shadow:0 0 14px rgba(96,165,250,.2)}
.sl-green{background:rgba(34,197,94,.07);border:1px solid rgba(34,197,94,.22);color:#22c55e}.sl-green:hover{box-shadow:0 0 14px rgba(34,197,94,.2)}
.star-box{background:var(--bg2);border:1px solid var(--bd);border-radius:12px;padding:1.8rem;text-align:center}
.star-title{font-family:'Orbitron',sans-serif;font-size:.88rem;letter-spacing:2px;margin-bottom:.5rem}
.star-sub{font-size:.9rem;color:var(--g)}

/* DIVIDER */
.sdiv{width:100%;height:1px;background:linear-gradient(90deg,transparent,var(--bd),transparent);margin:3rem 0;position:relative}
.sdiv::before{content:'◆';position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);background:var(--bg);color:var(--r);padding:0 .7rem;font-size:.55rem}

/* FOOTER */
footer{border-top:1px solid var(--bd2);padding:2.2rem 0;text-align:center;position:relative}
footer::before{content:'';position:absolute;top:0;left:50%;transform:translateX(-50%);width:180px;height:1px;background:linear-gradient(90deg,transparent,var(--r),transparent);box-shadow:0 0 8px var(--glow)}
.fb{font-family:'Orbitron',sans-serif;font-size:1.3rem;font-weight:700;letter-spacing:4px;background:linear-gradient(135deg,#fff,var(--r));-webkit-background-clip:text;-webkit-text-fill-color:transparent;margin-bottom:.45rem}
.ft{font-size:.85rem;color:var(--g2);font-style:italic;margin-bottom:.6rem}
.fc3{font-family:'Share Tech Mono',monospace;font-size:.7rem;color:var(--g2);letter-spacing:1px}
.fc3 span{color:var(--r)}

/* REVEAL */
.rv{opacity:0;transform:translateY(22px);transition:opacity .65s ease,transform .65s ease}
.rv.vis{opacity:1;transform:translateY(0)}
.rv1{transition-delay:.1s}.rv2{transition-delay:.2s}.rv3{transition-delay:.3s}

@media(max-width:768px){
  .obj-grid,.fg,.mod-grid,.pq-grid{grid-template-columns:1fr}
  .ar{flex-wrap:wrap}.arch{min-width:0}
  .nav-links{display:none}
  main{padding:88px 1.2rem 55px}
}
</style>
</head>
<body>

<div class="crn tl"></div><div class="crn tr"></div>
<div class="crn bl"></div><div class="crn br"></div>

<nav>
  <div class="nav-inner">
    <a href="#" class="nav-brand"><i class="fas fa-shield-alt"></i>AUTONIX<span class="nav-tag">README</span></a>
    <ul class="nav-links">
      <li><a href="#overview">Overview</a></li>
      <li><a href="#features">Features</a></li>
      <li><a href="#tech">Stack</a></li>
      <li><a href="#install">Install</a></li>
      <li><a href="#team">Team</a></li>
    </ul>
    <a href="https://yatin-anchan.github.io/AUTONIX-Website/" target="_blank" class="nav-cta"><i class="fas fa-globe" style="margin-right:.35rem"></i>WEBSITE</a>
  </div>
</nav>

<main>

<!-- HERO -->
<div class="hero rv">
  <div class="hero-eye">// PROJECT DOCUMENTATION v1.0</div>
  <h1 class="hero-title">AUTONIX</h1>
  <p class="hero-sub">RIDER SAFETY ASSISTANCE &amp; MONITORING SYSTEM</p>
  <p class="hero-tag"><span>Safety for all.</span> Accessible to all.</p>
  <div class="hero-div"></div>
  <div class="badge-row">
    <span class="badge b-green"><i class="fas fa-circle-check" style="font-size:.65rem"></i>BUILD PASSING</span>
    <span class="badge b-purple"><i class="fab fa-android" style="font-size:.65rem"></i>KOTLIN 1.9+</span>
    <span class="badge b-gold"><i class="fas fa-fire" style="font-size:.65rem"></i>FIREBASE ACTIVE</span>
    <span class="badge b-droid"><i class="fab fa-android" style="font-size:.65rem"></i>ANDROID 10+</span>
    <span class="badge b-cyan"><i class="fas fa-scale-balanced" style="font-size:.65rem"></i>MIT LICENSE</span>
  </div>
  <div class="link-row">
    <a href="https://yatin-anchan.github.io/AUTONIX-Website/" target="_blank" class="slink"><i class="fas fa-globe"></i>WEBSITE</a>
    <a href="https://www.aijfr.com/research-paper.php?id=1559" target="_blank" class="slink"><i class="fas fa-magnifying-glass"></i>RESEARCH PAPER</a>
    <a href="https://drive.google.com/file/d/169wh8a7fB0qaTMDbBEBixVDqTYjoomHM/view" target="_blank" class="slink"><i class="fas fa-book-open"></i>DOCS</a>
    <a href="https://github.com/yatin-anchan/Autonix/issues" target="_blank" class="slink"><i class="fas fa-bug"></i>REPORT BUG</a>
    <a href="https://github.com/yatin-anchan/AUTONIX-Website/releases/download/APP/AUTONIX_v1.0.apk" target="_blank" class="slink primary"><i class="fas fa-download"></i>DOWNLOAD APK</a>
  </div>
</div>

<div class="sdiv"></div>

<!-- OVERVIEW -->
<section id="overview" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-brain"></i></div><h2 class="stit">SYSTEM <span class="hl">OVERVIEW</span></h2></div>
  <div class="ocard">
    <p><strong>Autonix</strong> is an intelligent, smartphone-based <strong>driver safety and monitoring system</strong> engineered to reduce road accidents through real-time detection of <strong>drowsiness, crashes, and unsafe driving patterns</strong>.</p>
    <p>Unlike expensive hardware-dependent systems exclusive to luxury vehicles, Autonix leverages a <strong>smartphone's camera, GPS, and motion sensors</strong> to democratize advanced safety technology — making roads safer, smarter, and universally accessible.</p>
    <div class="mbox">
      <div class="mbox-label">CORE MISSION FLOW</div>
      <div class="mflow">
        <span>DETECT</span> <span class="arr"> → </span>
        <span>ALERT</span> <span class="arr"> → </span>
        <span>PROTECT</span> <span class="arr"> → </span>
        <span>RESPOND</span> <span class="arr"> → </span>
        <span>ANALYZE</span> <span class="arr"> → </span>
        <span>IMPROVE</span>
      </div>
    </div>
  </div>
</section>

<div class="sdiv"></div>

<!-- OBJECTIVES -->
<section id="objectives" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-crosshairs"></i></div><h2 class="stit">SYSTEM <span class="hl">OBJECTIVES</span></h2></div>
  <div class="obj-grid">
    <div class="obc rv rv1"><div class="obt"><i class="fas fa-eye" style="font-size:.85rem"></i>DETECTION</div>
      <ul><li>Real-time drowsiness monitoring via facial landmarks</li><li>Eye Aspect Ratio (EAR) calculation</li><li>Yawn and head tilt detection</li><li>Multi-parameter fatigue analysis</li></ul></div>
    <div class="obc rv rv2"><div class="obt"><i class="fas fa-satellite-dish" style="font-size:.85rem"></i>RESPONSE</div>
      <ul><li>Instant crash detection via sensor fusion</li><li>Automated emergency contact alerts</li><li>GPS coordinate transmission</li><li>SOS signal broadcasting</li></ul></div>
    <div class="obc rv rv1"><div class="obt"><i class="fas fa-route" style="font-size:.85rem"></i>NAVIGATION</div>
      <ul><li>Integrated trip planning system</li><li>Turn-by-turn guidance</li><li>Route optimization</li><li>Real-time traffic integration</li></ul></div>
    <div class="obc rv rv2"><div class="obt"><i class="fas fa-chart-line" style="font-size:.85rem"></i>ANALYTICS</div>
      <ul><li>Driving behavior tracking</li><li>Performance scoring system</li><li>Safety trend analysis</li><li>Fleet management dashboard</li></ul></div>
  </div>
</section>

<div class="sdiv"></div>

<!-- FEATURES -->
<section id="features" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-microchip"></i></div><h2 class="stit">KEY <span class="hl">FEATURES</span></h2></div>
  <div style="overflow-x:auto">
  <table class="ftbl">
    <thead><tr><th><i class="fas fa-icons" style="margin-right:.35rem"></i>FEATURE</th><th><i class="fas fa-circle-info" style="margin-right:.35rem"></i>DESCRIPTION</th><th><i class="fas fa-gears" style="margin-right:.35rem"></i>TECHNOLOGY</th></tr></thead>
    <tbody>
      <tr><td>Drowsiness Detection</td><td>Multi-parameter fatigue monitoring using facial landmark analysis</td><td>MediaPipe · ML Kit · EAR</td></tr>
      <tr><td>Crash Detection</td><td>Impact detection via accelerometer &amp; gyroscope sensor fusion</td><td>Real-time Sensor Analysis</td></tr>
      <tr><td>Emergency System</td><td>Automated SOS with GPS coordinates &amp; multi-channel alerts</td><td>Firebase Cloud Messaging</td></tr>
      <tr><td>Smart Navigation <span class="wip">WIP</span></td><td>Integrated route planning with trip management</td><td>OSMdroid</td></tr>
      <tr><td>Fleet Management <span class="wip">WIP</span></td><td>Multi-driver oversight with assignment &amp; tracking</td><td>Cloud-based Dashboard</td></tr>
      <tr><td>Analytics Engine</td><td>Performance metrics, safety trends &amp; visual reports</td><td>Firebase Analytics</td></tr>
      <tr><td>Privacy First</td><td>On-device detection with encrypted cloud storage</td><td>End-to-end Encryption</td></tr>
    </tbody>
  </table>
  </div>
</section>

<div class="sdiv"></div>

<!-- TECH STACK -->
<section id="tech" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-layer-group"></i></div><h2 class="stit">TECHNOLOGY <span class="hl">STACK</span></h2></div>
  <div class="sg rv rv1"><div class="sgt"><i class="fas fa-mobile-screen-button"></i>PLATFORM &amp; LANGUAGES</div>
    <div class="sp-row">
      <span class="sp spg"><i class="fab fa-android"></i>Android Studio Flamingo+</span>
      <span class="sp spp"><i class="fab fa-android"></i>Kotlin 1.9+</span>
      <span class="sp spo"><i class="fas fa-code"></i>XML UI</span>
    </div></div>
  <div class="sg rv rv2"><div class="sgt"><i class="fas fa-cloud"></i>BACKEND &amp; SERVICES</div>
    <div class="sp-row">
      <span class="sp spau"><i class="fas fa-fire"></i>Firebase Cloud</span>
      <span class="sp spb"><i class="fas fa-database"></i>Firestore</span>
      <span class="sp spg"><i class="fas fa-lock"></i>Firebase Auth</span>
    </div></div>
  <div class="sg rv rv3"><div class="sgt"><i class="fas fa-puzzle-piece"></i>CORE LIBRARIES</div>
    <div class="sp-row">
      <span class="sp spb"><i class="fas fa-camera"></i>CameraX</span>
      <span class="sp spr"><i class="fab fa-google"></i>ML Kit Vision</span>
      <span class="sp spt"><i class="fab fa-google"></i>MediaPipe Face</span>
      <span class="sp spm"><i class="fas fa-map"></i>OSMdroid</span>
    </div></div>
  <div class="sg rv rv1"><div class="sgt"><i class="fas fa-code-branch"></i>DEVELOPMENT TOOLS</div>
    <div class="sp-row">
      <span class="sp spfr"><i class="fab fa-git-alt"></i>Git</span>
      <span class="sp spdk"><i class="fab fa-github"></i>GitHub</span>
      <span class="sp spbr"><i class="fas fa-hammer"></i>Gradle</span>
    </div></div>
</section>

<div class="sdiv"></div>

<!-- ARCHITECTURE -->
<section id="architecture" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-cubes"></i></div><h2 class="stit">SYSTEM <span class="hl">ARCHITECTURE</span></h2></div>
  <div class="arch-wrap">
    <div class="arch">
      <div class="ar"><div class="an main"><i class="fas fa-mobile-alt" style="margin-right:.35rem"></i>MOBILE APPLICATION</div></div>
      <div class="aarw"><i class="fas fa-arrows-split-up-and-left"></i></div>
      <div class="ar">
        <div class="an"><i class="fas fa-camera" style="margin-right:.35rem;color:var(--r)"></i>CAMERA MODULE</div>
        <span style="color:var(--g2);font-size:.7rem">—</span>
        <div class="an"><i class="fas fa-compass" style="margin-right:.35rem;color:var(--r)"></i>SENSOR MODULE</div>
        <span style="color:var(--g2);font-size:.7rem">—</span>
        <div class="an"><i class="fas fa-location-dot" style="margin-right:.35rem;color:var(--r)"></i>LOCATION MODULE</div>
      </div>
      <div class="aarw"><i class="fas fa-arrow-down"></i></div>
      <div class="ar">
        <div class="an"><i class="fas fa-brain" style="margin-right:.35rem;color:var(--r)"></i>ML DETECTION ENGINE</div>
        <span style="color:var(--g2);font-size:.7rem">+</span>
        <div class="an"><i class="fas fa-gauge-high" style="margin-right:.35rem;color:var(--r)"></i>CRASH DETECTION</div>
      </div>
      <div class="aarw"><i class="fas fa-arrow-down"></i></div>
      <div class="ar"><div class="an alert"><i class="fas fa-bell" style="margin-right:.35rem"></i>ALERT SYSTEM</div></div>
      <div class="aarw"><i class="fas fa-arrow-down"></i></div>
      <div class="ar"><div class="an cloud"><i class="fas fa-database" style="margin-right:.35rem"></i>FIREBASE CLOUD</div></div>
      <div class="aarw"><i class="fas fa-arrow-down"></i></div>
      <div class="ar"><div class="an"><i class="fas fa-users" style="margin-right:.35rem;color:var(--r)"></i>EMERGENCY CONTACTS</div></div>
    </div>
  </div>
  <div class="mod-grid">
    <div class="mc rv rv1"><div class="mct"><i class="fas fa-door-open"></i>ENTRY LAYER</div><ul><li>Splash Activity</li><li>Welcome Activity</li><li>Authentication Flow</li></ul></div>
    <div class="mc rv rv2"><div class="mct"><i class="fas fa-shield-halved"></i>SAFETY LAYER</div><ul><li>Drowsiness Detector</li><li>Crash Alert Service</li><li>Emergency Response</li></ul></div>
    <div class="mc rv rv3"><div class="mct"><i class="fas fa-map"></i>NAVIGATION LAYER</div><ul><li>Trip Planner</li><li>Route Optimizer</li><li>Map Integration</li></ul></div>
    <div class="mc rv rv1"><div class="mct"><i class="fas fa-user-tie"></i>MANAGEMENT LAYER</div><ul><li>Fleet Control</li><li>Driver Assignment</li><li>Admin Dashboard</li></ul></div>
    <div class="mc rv rv2"><div class="mct"><i class="fas fa-chart-pie"></i>ANALYTICS LAYER</div><ul><li>Trip History</li><li>Performance Metrics</li><li>Safety Reports</li></ul></div>
    <div class="mc rv rv3"><div class="mct"><i class="fas fa-database"></i>DATA LAYER</div><ul><li>Firebase Integration</li><li>Local Storage</li><li>Cloud Sync</li></ul></div>
  </div>
</section>

<div class="sdiv"></div>

<!-- INSTALLATION -->
<section id="install" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-download"></i></div><h2 class="stit"><span class="hl">INSTALLATION</span></h2></div>
  <div style="background:var(--bg2);border:1px solid var(--bd);border-radius:12px;overflow:hidden">
    <div class="itabs">
      <button class="itab on" onclick="st('users',this)">For End Users</button>
      <button class="itab" onclick="st('devs',this)">For Developers</button>
    </div>
    <div id="itu" class="itp on" style="padding:1.4rem">
      <p style="color:#bbb;margin-bottom:1.1rem;font-size:.97rem">The easiest way to get started — no setup required.</p>
      <div style="display:flex;gap:.9rem;flex-wrap:wrap">
        <a href="https://yatin-anchan.github.io/AUTONIX-Website/" target="_blank" class="slink"><i class="fas fa-globe"></i>OFFICIAL WEBSITE</a>
        <a href="https://github.com/yatin-anchan/AUTONIX-Website/releases/download/APP/AUTONIX_v1.0.apk" target="_blank" class="slink primary"><i class="fas fa-download"></i>DOWNLOAD APK v1.0</a>
      </div>
    </div>
    <div id="itd" class="itp" style="padding:1.4rem">
      <div class="cblk"><div class="chdr"><div class="cdots"><div class="cdot"></div><div class="cdot"></div><div class="cdot"></div></div><span class="clng">BASH</span></div>
        <pre><span class="cm"># Clone the repository</span>
<span class="sv">git clone</span> <span class="sk">https://github.com/yatin-anchan/Autonix.git</span>
<span class="cm"># Navigate to project directory</span>
<span class="sv">cd</span> Autonix
<span class="cm"># Open in Android Studio</span>
<span class="cm"># File → Open → Select Project Directory</span></pre>
      </div>
      <div style="font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:2px;color:var(--r);margin-bottom:.75rem"><i class="fas fa-list-check" style="margin-right:.4rem"></i>PREREQUISITES</div>
      <div class="pq-grid">
        <div class="pqi"><i class="fas fa-terminal"></i><span>Android Studio Flamingo or later</span></div>
        <div class="pqi"><i class="fas fa-mobile-alt"></i><span>Android device / emulator (API 29+)</span></div>
        <div class="pqi"><i class="fas fa-fire"></i><span>Firebase account configured</span></div>
        <div class="pqi"><i class="fas fa-map"></i><span>OSMDroid for navigation features</span></div>
      </div>
      <div style="font-family:'Orbitron',sans-serif;font-size:.68rem;letter-spacing:2px;color:var(--r);margin:1.1rem 0 .75rem"><i class="fas fa-play" style="margin-right:.4rem"></i>BUILD &amp; RUN</div>
      <div class="bstps">
        <div class="bst"><div class="bsn">1</div><span>Sync Gradle dependencies</span></div>
        <div class="bst"><div class="bsn">2</div><span>Configure Firebase credentials in <code style="font-family:'Share Tech Mono',monospace;color:var(--r);font-size:.85em">google-services.json</code></span></div>
        <div class="bst"><div class="bsn">3</div><span>Enable permissions: Camera, Location, SMS</span></div>
        <div class="bst"><div class="bsn">4</div><span>Build → Make Project → Run 'app'</span></div>
      </div>
    </div>
  </div>
</section>

<div class="sdiv"></div>

<!-- TESTING -->
<section id="testing" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-flask-vial"></i></div><h2 class="stit">TESTING <span class="hl">RESULTS</span></h2></div>
  <div style="overflow-x:auto">
  <table class="ttbl">
    <thead><tr><th>TEST ID</th><th>TEST CASE</th><th>STATUS</th><th>RESPONSE TIME</th></tr></thead>
    <tbody>
      <tr><td class="tid">TC01</td><td>User Registration Flow</td><td><span class="tpass"><i class="fas fa-circle-check"></i>PASS</span></td><td class="trt">&lt; 2s</td></tr>
      <tr><td class="tid">TC02</td><td>Authentication System</td><td><span class="tpass"><i class="fas fa-circle-check"></i>PASS</span></td><td class="trt">&lt; 1s</td></tr>
      <tr><td class="tid">TC05</td><td>Drowsiness Detection Accuracy</td><td><span class="tpass"><i class="fas fa-circle-check"></i>PASS</span></td><td class="trt">Real-time</td></tr>
      <tr><td class="tid">TC07</td><td>Crash Detection Sensitivity</td><td><span class="tpass"><i class="fas fa-circle-check"></i>PASS</span></td><td class="trt">&lt; 500ms</td></tr>
      <tr><td class="tid">TC09</td><td>Emergency Alert Transmission</td><td><span class="tpass"><i class="fas fa-circle-check"></i>PASS</span></td><td class="trt">&lt; 3s</td></tr>
    </tbody>
  </table>
  </div>
  <div class="perf-row">
    <div class="pc rv rv1"><span class="pv">94%</span><div class="pl">Detection Accuracy</div></div>
    <div class="pc rv rv2"><span class="pv">&lt;500ms</span><div class="pl">Alert Response</div></div>
    <div class="pc rv rv3"><span class="pv">99.7%</span><div class="pl">System Uptime</div></div>
  </div>
</section>

<div class="sdiv"></div>

<!-- FUTURE -->
<section id="future" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-rocket"></i></div><h2 class="stit">FUTURE <span class="hl">ENHANCEMENTS</span></h2></div>
  <div class="fg">
    <div class="fc2 rv rv1"><div class="fct"><i class="fas fa-microphone"></i>VOICE INTEGRATION</div><ul><li>Hands-free alert management</li><li>Voice-activated navigation</li><li>Natural language commands</li></ul></div>
    <div class="fc2 rv rv2"><div class="fct"><i class="fas fa-robot"></i>AI ENHANCEMENTS</div><ul><li>Predictive fatigue analysis</li><li>Behavioral pattern learning</li><li>Risk assessment algorithms</li></ul></div>
    <div class="fc2 rv rv1"><div class="fct"><i class="fas fa-wifi"></i>OFFLINE CAPABILITIES</div><ul><li>Local alert processing</li><li>Offline map caching</li><li>Queue-based sync system</li></ul></div>
    <div class="fc2 rv rv2"><div class="fct"><i class="fas fa-hospital"></i>EMERGENCY SERVICES</div><ul><li>Direct 911 / emergency dispatch</li><li>Hospital integration</li><li>Real-time EMS coordination</li></ul></div>
    <div class="fc2 rv rv1"><div class="fct"><i class="fas fa-gamepad"></i>GAMIFICATION</div><ul><li>Safe driving rewards</li><li>Achievement system</li><li>Leaderboard integration</li></ul></div>
    <div class="fc2 rv rv2"><div class="fct"><i class="fas fa-globe"></i>PLATFORM EXPANSION</div><ul><li>iOS application</li><li>Web dashboard</li><li>Smartwatch integration</li></ul></div>
  </div>
</section>

<div class="sdiv"></div>

<!-- TEAM -->
<section id="team" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-users"></i></div><h2 class="stit">MEET THE <span class="hl">TEAM</span></h2></div>
  <div class="team-row">
    <div class="tc rv rv1">
      <div class="tav"><img src="https://avatars.githubusercontent.com/u/147016503?v=4" alt="Maizah" onerror="this.parentNode.outerHTML='<div class=tav-ph><i class=fas fa-user></i></div>'"></div>
      <div class="tn2">MAIZAH SHAIKH</div>
      <div class="tr3">Developer &amp; Researcher</div>
      <a href="https://github.com/maizahshaikh1004" target="_blank" class="tgh"><i class="fab fa-github"></i>GitHub</a>
    </div>
    <div class="tc rv rv2">
      <div class="tav"><img src="https://github.com/yatin-anchan.png" alt="Yatin" onerror="this.parentNode.outerHTML='<div class=tav-ph><i class=fas fa-user></i></div>'"></div>
      <div class="tn2">YATIN ANCHAN</div>
      <div class="tr3">Developer &amp; System Architect</div>
      <a href="https://github.com/yatin-anchan" target="_blank" class="tgh"><i class="fab fa-github"></i>GitHub</a>
    </div>
  </div>
  <div class="guide-card rv">
    <div style="font-size:1.4rem;color:var(--r);margin-bottom:.7rem"><i class="fas fa-chalkboard-teacher"></i></div>
    <div class="gn">MR. HASAN PHUDINAWALA</div>
    <div class="gr">Project Guide &amp; Mentor</div>
    <div class="gd">Department of Computer Science<br>Royal College of Arts, Science &amp; Commerce<br>Mira Road (E), Maharashtra, India</div>
  </div>
</section>

<div class="sdiv"></div>

<!-- LICENSE -->
<section id="license" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-scale-balanced"></i></div><h2 class="stit">LICENSE</h2></div>
  <div class="lic-box">
    <div class="lit">MIT LICENSE</div>
    <span class="badge b-cyan" style="margin-bottom:.9rem;display:inline-flex"><i class="fas fa-shield-check" style="font-size:.65rem"></i>Open Source — Free to Use</span>
    <div class="lic-code">Permission is hereby granted, free of charge, to any person obtaining a copy<br>of this software for educational and research purposes.</div>
    <a href="https://github.com/yatin-anchan/Autonix" target="_blank" class="slink" style="display:inline-flex;margin-top:.4rem"><i class="fas fa-file-contract"></i>VIEW ON GITHUB</a>
  </div>
</section>

<div class="sdiv"></div>

<!-- SUPPORT -->
<section id="support" class="rv">
  <div class="sh"><div class="si"><i class="fas fa-handshake"></i></div><h2 class="stit">SUPPORT &amp; <span class="hl">CONTACT</span></h2></div>
  <div class="sup-links">
    <a href="https://github.com/yatin-anchan/Autonix/issues" target="_blank" class="sl2 sl-red"><i class="fab fa-github"></i>REPORT A BUG</a>
    <a href="https://github.com/yatin-anchan/Autonix/discussions" target="_blank" class="sl2 sl-blue"><i class="fas fa-comments"></i>DISCUSSIONS</a>
    <a href="mailto:support@autonix.app" class="sl2 sl-green"><i class="fas fa-envelope"></i>EMAIL</a>
  </div>
  <div class="star-box">
    <div style="font-size:1.8rem;color:var(--gold);margin-bottom:.7rem;animation:ipulse 2s ease-in-out infinite"><i class="fas fa-star"></i></div>
    <div class="star-title">SHOW YOUR SUPPORT</div>
    <p class="star-sub">If this project helps improve road safety, consider giving it a ⭐<br>Your support drives innovation in accessible safety technology.</p>
    <a href="https://github.com/yatin-anchan/Autonix" target="_blank" class="slink" style="display:inline-flex;margin-top:1.1rem"><i class="fab fa-github"></i>STAR ON GITHUB</a>
  </div>
</section>

</main>

<footer>
  <div class="fb">AUTONIX</div>
  <p class="ft">Empowering drivers. Protecting lives. Connecting communities.</p>
  <p class="fc3">© 2025 <span>Autonix Project</span> &nbsp;|&nbsp; Built with ❤️ and ☕ in India &nbsp;|&nbsp; <span>MIT License</span></p>
</footer>

<script>
// Scroll reveal
const obs=new IntersectionObserver(es=>{es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('vis')})},{threshold:.08,rootMargin:'0px 0px -30px 0px'});
document.querySelectorAll('.rv').forEach(el=>obs.observe(el));

// Tab switcher
function st(id,btn){
  document.querySelectorAll('.itp').forEach(t=>t.classList.remove('on'));
  document.querySelectorAll('.itab').forEach(b=>b.classList.remove('on'));
  document.getElementById('it'+id[0]).classList.add('on');
  btn.classList.add('on');
}

// Active nav link on scroll
const secs=document.querySelectorAll('section[id]');
const nls=document.querySelectorAll('.nav-links a');
window.addEventListener('scroll',()=>{
  let cur='';
  secs.forEach(s=>{if(window.scrollY>=s.offsetTop-130)cur=s.id});
  nls.forEach(a=>{a.style.color=a.getAttribute('href').slice(1)===cur?'var(--r)':'';});
});
</script>
</body>
</html>
