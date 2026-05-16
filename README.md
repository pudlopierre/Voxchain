bash

extract-text /mnt/user-data/uploads/Readme.docx 2>/dev/null | head -300
Sortie

cat > public/index.html << 'ENDOFFILE'

<!DOCTYPE html>

<html lang="fr">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>VoxChain · La voix de la France</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Epilogue:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>

:root{

  --B:#002395;--Bm:#1a3fcc;--Bl:#dce7ff;--Bxl:#f0f4ff;

  --R:#ED2939;--Rl:#fdeaec;

  --W:#F9F8F4;--K:#0d0d12;--P:#5c5c6e;--G:#e6e6f0;

  --O:#c9a84c;--Ol:#fdf6e3;

  --V:#1a7a4a;--Vl:#e6f4ee;

  --bd:rgba(13,13,18,.1);--sh:0 2px 20px rgba(0,0,0,.06);

  --r:12px;

  --play:'Playfair Display',Georgia,serif;

  --epi:'Epilogue',system-ui,sans-serif;

  --mono:'JetBrains Mono',monospace;

}

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}

html{scroll-behavior:smooth;}

body{font-family:var(--epi);background:var(--W);color:var(--K);min-height:100vh;overflow-x:hidden;}

.tcb{height:4px;background:linear-gradient(90deg,var(--B) 33.33%,#fff 33.33% 66.66%,var(--R) 66.66%);position:fixed;top:0;left:0;right:0;z-index:500;}

.hdr{position:fixed;top:4px;left:0;right:0;z-index:400;background:rgba(13,13,18,.97);backdrop-filter:blur(14px);padding:0 32px;height:60px;display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid rgba(255,255,255,.07);}

.logo{display:flex;align-items:center;gap:12px;text-decoration:none;cursor:pointer;}

.logo-flag{width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,var(--B) 33%,#fff 33% 66%,var(--R) 66%);border:2px solid rgba(255,255,255,.18);flex-shrink:0;}

.logo-text{color:#fff;font-family:var(--play);font-size:17px;font-weight:700;}

.logo-sub{color:rgba(255,255,255,.35);font-size:9px;display:block;margin-top:-2px;letter-spacing:.08em;text-transform:uppercase;}

.nav{display:flex;gap:2px;align-items:center;}

.np{padding:5px 12px;border-radius:100px;border:1px solid rgba(255,255,255,.12);background:transparent;color:rgba(255,255,255,.55);font-family:var(--epi);font-size:12px;font-weight:500;cursor:pointer;transition:all .18s;white-space:nowrap;}

.np:hover{background:rgba(255,255,255,.09);color:#fff;}

.np.on{background:var(--B);color:#fff;border-color:var(--B);}

.np.ag{border-color:rgba(201,168,76,.35);color:rgba(201,168,76,.8);}

.np.ag.on,.np.ag:hover{background:var(--O);color:#fff;border-color:var(--O);}

.np.tr{border-color:rgba(26,122,74,.35);color:rgba(26,122,74,.8);}

.np.tr.on,.np.tr:hover{background:var(--V);color:#fff;border-color:var(--V);}

.app{padding-top:64px;}

.sc{display:none;animation:rise .3s cubic-bezier(.22,1,.36,1);}

.sc.vis{display:block;}

@keyframes rise{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}

.wrap{max-width:1040px;margin:0 auto;padding:40px 24px 80px;}

.wrap-sm{max-width:700px;margin:0 auto;padding:40px 24px 80px;}

.hero{background:var(--K);min-height:calc(100vh - 64px);display:flex;flex-direction:column;align-items:center;justify-content:center;position:relative;overflow:hidden;padding:60px 24px 40px;}

.hero-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(255,255,255,.022) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.022) 1px,transparent 1px);background-size:52px 52px;}

.hero-glow{position:absolute;width:800px;height:800px;background:radial-gradient(circle,rgba(0,35,149,.18) 0%,transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);pointer-events:none;}

.hero-body{position:relative;text-align:center;max-width:820px;z-index:1;}

.hero-badge{display:inline-flex;align-items:center;gap:8px;padding:6px 16px;border-radius:100px;border:1px solid rgba(201,168,76,.35);background:rgba(201,168,76,.07);color:var(--O);font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;margin-bottom:26px;}

.hero-badge-dot{width:6px;height:6px;border-radius:50%;background:var(--O);animation:pulse 2s infinite;}

@keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}

h1.hero-title{font-family:var(--play);font-size:clamp(38px,7vw,80px);color:#fff;line-height:1.04;font-weight:700;margin-bottom:20px;letter-spacing:-1.5px;}

h1.hero-title em{color:var(--O);font-style:italic;}

.hero-desc{color:rgba(255,255,255,.46);font-size:17px;font-weight:300;line-height:1.78;margin-bottom:36px;max-width:580px;margin-left:auto;margin-right:auto;}

.hero-countdown{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);border-radius:20px;padding:20px 32px;display:inline-flex;align-items:center;gap:24px;margin-bottom:36px;}

.cd-unit{text-align:center;}

.cd-num{font-family:var(--play);font-size:36px;color:#fff;line-height:1;font-weight:700;}

.cd-lbl{font-size:10px;color:rgba(255,255,255,.35);text-transform:uppercase;letter-spacing:.08em;margin-top:3px;}

.cd-sep{font-family:var(--play);font-size:28px;color:rgba(255,255,255,.2);margin-bottom:16px;}

.cd-info{font-size:12px;color:rgba(255,255,255,.38);margin-top:10px;}

.hero-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:52px;}

.hbtn{display:inline-flex;align-items:center;gap:8px;padding:13px 28px;border-radius:100px;font-family:var(--epi);font-size:14px;font-weight:600;border:none;cursor:pointer;transition:all .22s;}

.hbtn-b{background:var(--B);color:#fff;}

.hbtn-b:hover{background:var(--Bm);transform:translateY(-2px);box-shadow:0 8px 26px rgba(0,35,149,.38);}

.hbtn-o{background:transparent;color:rgba(255,255,255,.7);border:1px solid rgba(255,255,255,.2);}

.hbtn-o:hover{background:rgba(255,255,255,.08);color:#fff;}

.hero-stats{display:flex;gap:40px;justify-content:center;flex-wrap:wrap;padding-top:36px;border-top:1px solid rgba(255,255,255,.07);}

.hs-n{font-family:var(--play);font-size:26px;color:#fff;line-height:1;}

.hs-l{font-size:10px;color:rgba(255,255,255,.32);text-transform:uppercase;letter-spacing:.08em;margin-top:3px;}

.step-bar{display:flex;margin-bottom:32px;}

.sn{flex:1;display:flex;flex-direction:column;align-items:center;position:relative;}

.sn:not(:last-child)::after{content:'';position:absolute;top:15px;left:58%;width:84%;height:2px;background:var(--G);z-index:0;transition:background .4s;}

.sn.done:not(:last-child)::after{background:var(--V);}

.sc2{width:30px;height:30px;border-radius:50%;border:2px solid var(--G);display:flex;align-items:center;justify-content:center;font-size:13px;background:#fff;position:relative;z-index:1;transition:all .3s;}

.sn.act .sc2{border-color:var(--B);background:var(--Bl);}

.sn.done .sc2{border-color:var(--V);background:var(--V);color:#fff;font-size:11px;}

.slbl{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.06em;color:var(--P);margin-top:5px;}

.sn.act .slbl{color:var(--B);}

.sn.done .slbl{color:var(--V);}

.pnl{display:none;}

.pnl.on{display:block;animation:rise .28s ease;}

.card{background:#fff;border:1px solid var(--bd);border-radius:var(--r);padding:24px 28px;box-shadow:var(--sh);}

.card-b{border-left:4px solid var(--B);}

.card-v{border-left:4px solid var(--V);}

.card-r{border-left:4px solid var(--R);}

.card-o{border-left:4px solid var(--O);}

.ptag{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.1em;color:var(--P);margin-bottom:6px;display:block;}

.ptitle{font-family:var(--play);font-size:24px;margin-bottom:6px;}

.pdesc{font-size:13px;color:var(--P);line-height:1.7;margin-bottom:20px;}

.fld{margin-bottom:16px;}

.fld label{display:block;font-size:11px;font-weight:600;letter-spacing:.06em;text-transform:uppercase;color:var(--P);margin-bottom:6px;}

.fld input,.fld select{width:100%;padding:11px 13px;border:1.5px solid var(--G);border-radius:9px;font-family:var(--epi);font-size:14px;background:var(--W);color:var(--K);outline:none;transition:border-color .2s,box-shadow .2s;}

.fld input:focus,.fld select:focus{border-color:var(--B);box-shadow:0 0 0 3px rgba(0,35,149,.08);background:#fff;}

.cni-in{font-family:var(--mono)!important;font-size:16px!important;letter-spacing:.08em!important;}

.demo-tag{display:inline-flex;align-items:center;gap:5px;padding:4px 10px;border-radius:100px;background:var(--Ol);color:var(--O);border:1px dashed var(--O);font-size:11px;font-weight:600;margin-bottom:10px;}

.orow{display:flex;gap:7px;justify-content:center;margin:16px 0 4px;}

.od{width:48px;height:56px;border:2px solid var(--G);border-radius:10px;font-family:var(--mono);font-size:22px;font-weight:500;text-align:center;background:var(--W);color:var(--K);outline:none;transition:all .2s;}

.od:focus{border-color:var(--B);box-shadow:0 0 0 3px rgba(0,35,149,.08);background:#fff;}

.od.ok{border-color:var(--B);}

.otimer{text-align:center;font-size:12px;color:var(--P);margin-bottom:4px;}

.otimer.red{color:var(--R);font-weight:600;}

.lbtn{background:none;border:none;color:var(--B);font-size:12px;cursor:pointer;text-decoration:underline;font-family:var(--epi);}

.btn{display:inline-flex;align-items:center;justify-content:center;gap:7px;padding:11px 24px;border-radius:100px;font-family:var(--epi);font-size:13px;font-weight:600;cursor:pointer;transition:all .18s;border:1.5px solid transparent;}

.btn-b{background:var(--B);color:#fff;}

.btn-b:hover{background:var(--Bm);transform:translateY(-1px);box-shadow:0 5px 16px rgba(0,35,149,.26);}

.btn-v{background:var(--V);color:#fff;}

.btn-v:hover{background:#135c38;transform:translateY(-1px);}

.btn-o{background:var(--O);color:#fff;}

.btn-g{background:transparent;border-color:var(--G);color:var(--K);}

.btn-g:hover{background:var(--G);}

.btn-r{background:var(--Rl);color:var(--R);border-color:#f0c4bf;}

.btn-full{width:100%;}

.btn-sm{padding:7px 15px;font-size:12px;}

.btn:disabled{opacity:.38;cursor:not-allowed;transform:none!important;}

.vbtns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin:20px 0 8px;}

.VOUI{background:var(--V);color:#fff;font-size:17px;padding:16px 44px;border-radius:14px;border:none;cursor:pointer;font-family:var(--epi);font-weight:600;transition:all .2s;}

.VOUI:hover{background:#135c38;transform:translateY(-2px);box-shadow:0 8px 24px rgba(26,122,74,.3);}

.VNON{background:var(--R);color:#fff;font-size:17px;padding:16px 44px;border-radius:14px;border:none;cursor:pointer;font-family:var(--epi);font-weight:600;transition:all .2s;}

.VNON:hover{background:#c4202f;transform:translateY(-2px);box-shadow:0 8px 24px rgba(237,41,57,.3);}

.VABS{background:#fff;color:var(--P);border:2px solid var(--G);font-size:17px;padding:14px 32px;border-radius:14px;cursor:pointer;font-family:var(--epi);font-weight:600;transition:all .2s;}

.VABS:hover{background:var(--G);transform:translateY(-1px);}

.ref-card{background:var(--K);border-radius:20px;padding:28px 32px;color:#fff;margin-bottom:18px;position:relative;overflow:hidden;}

.ref-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--B) 33%,#fff 33% 66%,var(--R) 66%);}

.ref-live{font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.1em;color:rgba(255,255,255,.4);margin-bottom:8px;display:flex;align-items:center;gap:7px;}

.ldot{width:6px;height:6px;border-radius:50%;background:var(--R);display:inline-block;animation:pulse 1.5s infinite;}

.ref-q{font-family:var(--play);font-size:22px;line-height:1.35;font-weight:600;margin-bottom:8px;}

.ref-d{font-size:13px;color:rgba(255,255,255,.44);line-height:1.7;}

.ref-meta{margin-top:12px;display:flex;gap:16px;flex-wrap:wrap;font-size:11px;color:rgba(255,255,255,.32);}

.ref-meta strong{color:rgba(255,255,255,.62);}

.res-hero{background:var(--K);border-radius:20px;padding:32px 36px;color:#fff;margin-bottom:22px;position:relative;overflow:hidden;}

.res-hero::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--B) 33%,#fff 33% 66%,var(--R) 66%);}

.s3{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin:18px 0;}

.sc3{background:rgba(255,255,255,.07);border-radius:10px;padding:16px;text-align:center;border:1px solid rgba(255,255,255,.07);}

.snum{font-family:var(--play);font-size:32px;line-height:1;}

.spct{font-family:var(--mono);font-size:12px;opacity:.5;margin-top:3px;}

.snam{font-size:10px;text-transform:uppercase;letter-spacing:.08em;opacity:.38;margin-top:4px;}

.barmega{display:flex;height:12px;border-radius:6px;overflow:hidden;margin:4px 0 18px;}

.bm-v{background:var(--V);transition:width .8s cubic-bezier(.4,0,.2,1);}

.bm-a{background:#6b7280;}

.bm-r{background:var(--R);}

.tblwrap{overflow-x:auto;border-radius:var(--r);border:1px solid var(--bd);}

table{width:100%;border-collapse:collapse;font-size:13px;}

th{padding:10px 13px;font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.07em;color:var(--P);background:var(--G);text-align:left;}

th:not(:first-child){text-align:right;}

td{padding:11px 13px;border-top:1px solid #f0f0f6;vertical-align:middle;}

td:not(:first-child){text-align:right;}

tr:hover td{background:#f6f6fc;}

.chat-wrap{display:grid;grid-template-columns:1fr 300px;gap:20px;align-items:start;}

.chat-main{background:#fff;border:1px solid var(--bd);border-radius:20px;overflow:hidden;display:flex;flex-direction:column;height:600px;}

.chat-header{padding:16px 20px;border-bottom:1px solid var(--bd);background:var(--K);color:#fff;}
