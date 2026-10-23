<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#090711">
<title>Painel de Likes • Free Fire</title>
<style>
:root{color-scheme:dark;--bg:#090711;--panel:#151020;--purple:#9b5cff;--text:#f8f4ff;--muted:#aaa0bd;--line:#39264f;--green:#61e6a3;--red:#ff6b86}
*{box-sizing:border-box}
body{margin:0;background:radial-gradient(ellipse at 50% -10%,#32164d 0,transparent 48%),var(--bg);color:var(--text);font:16px/1.45 system-ui,-apple-system,Segoe UI,Roboto,sans-serif;min-height:100vh}
button,input{font:inherit}
button{cursor:pointer}
.app{max-width:520px;margin:auto;min-height:100vh;padding:22px 17px 96px}
.top{display:flex;align-items:center;justify-content:space-between;gap:10px;margin-bottom:22px}
.brand{font-size:12px;letter-spacing:.2em;color:#cbb9ec;font-weight:800}
.brand strong{display:block;font-size:21px;letter-spacing:.07em;color:white}
.pill{font-size:11px;border:1px solid #594070;color:#d8c3ff;border-radius:999px;padding:6px 10px;background:#1a1029}
.hero{text-align:center;padding:22px 15px 24px;border:1px solid #58347a;border-radius:25px;background:linear-gradient(155deg,#21132f,#110d1c 68%);box-shadow:0 0 28px #8a35ff20;position:relative;overflow:hidden}
.heart{font-size:56px;line-height:1.2;filter:drop-shadow(0 0 14px #a34cff)}
.eyebrow{font-size:11px;font-weight:800;letter-spacing:.23em;color:#c4a1ff;margin:12px 0 5px}
.hero h1{font-size:clamp(26px,7vw,35px);line-height:1.05;margin:0;text-transform:uppercase;text-shadow:0 0 18px #a84dff77}
.hero p{margin:10px 0 0;color:#c4bad5;font-size:14px}
.card{margin-top:17px;border:1px solid var(--line);border-radius:20px;padding:19px;background:linear-gradient(145deg,#181223,#100d18)}
.label{display:block;font-size:13px;font-weight:700;margin-bottom:9px}
.input-wrap{display:flex;align-items:center;gap:10px;border:1px solid #4b3566;background:#0d0a14;border-radius:13px;padding:0 13px}
.input-wrap span{color:#ba8cff}
.input-wrap input{width:100%;min-width:0;background:transparent;color:white;border:0;outline:0;padding:15px 0;font-size:16px}
.input-wrap:focus-within{border-color:#b47aff;box-shadow:0 0 0 3px #a34cff20}
.hint{color:var(--muted);font-size:12px;margin:8px 1px 0}
.stats{display:flex;justify-content:space-between;align-items:center;margin:18px 0 14px;gap:10px}
.stats span{color:var(--muted);font-size:13px}
.count{border:1px solid #5e3b80;border-radius:10px;background:#27163b;color:#e6d3ff;padding:7px 11px;font-size:13px;font-weight:800}
.primary{width:100%;border:0;border-radius:14px;padding:15px 18px;font-weight:900;color:white;background:linear-gradient(100deg,#7136d6,#b348f2);box-shadow:0 7px 22px #8e3be83b}
.primary:disabled{opacity:.55;cursor:not-allowed}
.secondary{border:1px solid #594070;background:#21172e;color:#e8d9ff;border-radius:10px;padding:10px 12px;font-size:13px;font-weight:700}
.notice{margin-top:12px;padding:11px 12px;border-radius:12px;background:#21172e;color:#c6bad8;font-size:12px;border:1px solid #382749}
.section-title{font-size:17px;margin:0 0 13px}
.muted{color:var(--muted)}
.empty{padding:23px 10px;text-align:center;color:var(--muted);font-size:14px;border:1px dashed #443253;border-radius:13px}
.item{padding:13px 0;border-bottom:1px solid #2d223a;display:flex;justify-content:space-between;gap:10px;align-items:center}
.item:last-child{border-bottom:0}
.item strong{display:block;font-size:14px;overflow-wrap:anywhere}
.item small{color:var(--muted);font-size:12px}
.status{font-size:11px;border-radius:999px;padding:5px 8px;border:1px solid #6b4a24;background:#302215;color:#ffd58b;white-space:nowrap}
.setting{display:flex;align-items:center;justify-content:space-between;gap:14px;padding:14px 0;border-bottom:1px solid #30243d}
.setting strong{font-size:14px;display:block}
.setting small{display:block;color:var(--muted);font-size:12px;margin-top:3px}
.toggle{width:46px;height:27px;border:1px solid #59466b;border-radius:99px;background:#33283f;padding:3px;flex-shrink:0}
.toggle:after{content:"";display:block;width:19px;height:19px;border-radius:50%;background:#a99ab9;transition:transform .15s}
.toggle.on{background:#6736a3;border-color:#a96dff}
.toggle.on:after{transform:translateX(19px);background:#fff}
.bottom{position:fixed;bottom:0;left:0;right:0;padding:10px 12px max(10px,env(safe-area-inset-bottom));background:#0b0812ed;border-top:1px solid #30203f;backdrop-filter:blur(16px);z-index:5}
.nav{max-width:520px;margin:auto;display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
.navbtn{border:0;border-radius:12px;padding:9px 4px;background:transparent;color:#8f839f;font-size:11px;font-weight:700}
.navbtn .ico{display:block;font-size:19px;margin-bottom:2px}
.navbtn.active{background:#28183a;color:#e4c8ff}
.page{display:none}
.page.active{display:block}
.toast{position:fixed;top:14px;left:50%;transform:translateX(-50%);width:calc(100% - 30px);max-width:480px;padding:13px 15px;border-radius:13px;background:#2c1a3d;border:1px solid #8052a8;box-shadow:0 8px 30px #0008;z-index:10;font-size:13px;display:none}
.toast.show{display:block}
.toast strong{display:block;margin-bottom:3px}
.footer-note{text-align:center;color:#796d8b;font-size:11px;margin-top:20px}
.authrow{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.authrow button{flex:1;min-width:130px}
</style>
</head>
<body>
<div class="app">
<header class="top"><div class="brand"><strong>FREE FIRE</strong>FAN PANEL • EM DESENVOLVIMENTO</div><div class="pill" id="modePill">● NÃO CONECTADO</div></header>
<main>
<section class="page active" id="home">
<div class="hero"><div class="heart" aria-hidden="true">💜</div><div class="eyebrow">RECONHECIMENTO PARA SEU PERFIL</div><h1>Painel de Likes</h1><p>Visual gamer • integração em desenvolvimento.</p></div>
<div class="card">
<h2 class="section-title">Sua conta</h2><p id="userStatus" class="muted" style="font-size:13px">Entre com Google para habilitar o histórico privado.</p>
<div class="authrow"><button class="primary" id="loginBtn">Entrar com Google</button><button class="secondary" id="logoutBtn" hidden>Sair</button></div>
<div class="notice">O login só funciona quando este site é aberto por um endereço HTTPS autorizado no Firebase Hosting; não teste abrindo o arquivo localmente.</div>
</div>
