<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Caregiver Retention OS — Signal & Intervention Framework</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --navy:#0d1c32;--navy2:#162a46;--nb:rgba(255,255,255,.08);
  --teal:#0e7490;--teal2:#06b6d4;--teal3:#ecfeff;
  --bg:#eef2f7;--sur:#fff;--sur2:#f8fafc;
  --t1:#0f172a;--t2:#334155;--t3:#64748b;--t4:#94a3b8;
  --br:#e2e8f0;--br2:#cbd5e1;
  --sc:#14532d;--sbg:#f0fdf4;--sa:#16a34a;--sb:#bbf7d0;
  --wc:#78350f;--wbg:#fffbeb;--wa:#d97706;--wb:#fde68a;
  --cc:#7c2d12;--cbg:#fff7ed;--ca:#ea580c;--cb:#fed7aa;
  --rc:#500724;--rbg:#fdf2f8;--ra:#be185d;--rb:#fbcfe8;
  --ic:#3b0764;--ibg:#f5f3ff;--ia:#7c3aed;
  --sw:258px;--r:10px;--rs:6px;--rl:16px;
  --s1:0 1px 3px rgba(15,28,50,.07);
  --s2:0 4px 12px rgba(15,28,50,.09),0 2px 4px rgba(15,28,50,.05);
  --s3:0 12px 32px rgba(15,28,50,.12),0 4px 12px rgba(15,28,50,.06);
}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',system-ui,sans-serif;
  background:var(--bg);color:var(--t1);line-height:1.5;font-size:14px;
  display:flex;min-height:100vh;-webkit-font-smoothing:antialiased}
#sb{width:var(--sw);background:var(--navy);min-height:100vh;position:fixed;
  top:0;left:0;bottom:0;display:flex;flex-direction:column;z-index:100;overflow-y:auto}
.sb-brand{padding:20px 20px 14px;border-bottom:1px solid var(--nb)}
.sb-logo{color:#fff;font-size:15px;font-weight:700;letter-spacing:-.3px;line-height:1.2}
.sb-sub{color:rgba(255,255,255,.38);font-size:10.5px;text-transform:uppercase;letter-spacing:.8px;margin-top:3px}
.sb-org{margin:10px 14px;background:rgba(255,255,255,.06);border-radius:8px;
  padding:9px 12px;cursor:pointer;border:1px solid var(--nb);transition:background .15s}
.sb-org:hover{background:rgba(255,255,255,.1)}
.sb-org-name{color:rgba(255,255,255,.88);font-size:13px;font-weight:600;
  white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.sb-org-hint{color:rgba(255,255,255,.28);font-size:11px;margin-top:1px}
.sb-sep{height:1px;background:var(--nb);margin:4px 0}
.sb-lbl{color:rgba(255,255,255,.28);font-size:10px;letter-spacing:1px;
  text-transform:uppercase;padding:10px 20px 4px;font-weight:600}
.nav-item{display:flex;align-items:center;gap:9px;padding:9px 20px;cursor:pointer;
  color:rgba(255,255,255,.55);font-size:13.5px;font-weight:500;
  border-left:3px solid transparent;transition:all .15s}
.nav-item:hover{background:rgba(255,255,255,.06);color:rgba(255,255,255,.9)}
.nav-item.active{background:rgba(6,182,212,.12);color:var(--teal2);border-left-color:var(--teal2)}
.nav-ico{width:18px;text-align:center;font-size:14px;flex-shrink:0}
.sb-foot{margin-top:auto;padding:14px 20px;border-top:1px solid var(--nb)}
.sb-foot-txt{color:rgba(255,255,255,.22);font-size:11px;line-height:1.6}
#main{margin-left:var(--sw);flex:1;min-height:100vh;display:flex;flex-direction:column}
.vh{background:var(--sur);border-bottom:1px solid var(--br);
  padding:16px 30px;display:flex;align-items:center;justify-content:space-between;
  gap:16px;position:sticky;top:0;z-index:50;flex-wrap:wrap}
.vh-left h2{font-size:18px;font-weight:700;color:var(--t1);letter-spacing:-.3px}
.vh-left p{font-size:12.5px;color:var(--t4);margin-top:1px}
.vh-right{display:flex;gap:8px;align-items:center;flex-wrap:wrap}
#vc{padding:26px 30px;flex:1}
.card{background:var(--sur);border:1px solid var(--br);border-radius:var(--r);box-shadow:var(--s1);padding:18px 20px}
.card-title{font-size:11px;font-weight:700;letter-spacing:.5px;text-transform:uppercase;color:var(--t4);margin-bottom:12px}
.btn{display:inline-flex;align-items:center;gap:5px;padding:8px 15px;border-radius:var(--rs);
  font-size:13px;font-weight:600;cursor:pointer;border:1px solid transparent;transition:all .15s;font-family:inherit}
.btn-primary{background:var(--teal);color:#fff;border-color:var(--teal)}
.btn-primary:hover{background:#0c6478}
.btn-secondary{background:var(--sur);border-color:var(--br2);color:var(--t2)}
.btn-secondary:hover{background:var(--sur2)}
.btn-ghost{background:transparent;color:var(--teal);border-color:transparent}
.btn-ghost:hover{background:var(--teal3)}
.btn-danger{background:transparent;border-color:var(--rb);color:var(--ra)}
.btn-danger:hover{background:var(--rbg)}
.btn-sm{padding:5px 10px;font-size:12px}
.btn-ico{width:34px;height:34px;padding:0;justify-content:center;border-radius:var(--rs);
  background:var(--sur2);border:1px solid var(--br);color:var(--t3);font-size:15px}
.btn-ico:hover{background:var(--br)}
.btn-row{display:flex;gap:8px;flex-wrap:wrap}
.badge{display:inline-flex;align-items:center;gap:4px;padding:3px 9px;border-radius:999px;
  font-size:11.5px;font-weight:700;letter-spacing:.1px;white-space:nowrap}
.badge-stable{background:var(--sbg);color:var(--sc);border:1px solid var(--sb)}
.badge-watch{background:var(--wbg);color:var(--wc);border:1px solid var(--wb)}
.badge-caution{background:var(--cbg);color:var(--cc);border:1px solid var(--cb)}
.badge-critical{background:var(--rbg);color:var(--rc);border:1px solid var(--rb)}
.bdot{width:6px;height:6px;border-radius:50%;background:currentColor;display:inline-block}
.field{margin-bottom:13px}
.field label{display:block;font-size:11px;font-weight:700;text-transform:uppercase;
  letter-spacing:.5px;color:var(--t3);margin-bottom:5px}
.field input,.field select,.field textarea{width:100%;padding:8px 11px;border:1px solid var(--br2);
  border-radius:var(--rs);font-family:inherit;font-size:13px;background:var(--sur);color:var(--t1)}
.field input:focus,.field select:focus,.field textarea:focus{
  outline:none;border-color:var(--teal);box-shadow:0 0 0 3px rgba(14,116,144,.14)}
.field textarea{resize:vertical;min-height:66px}
.field-hint{font-size:11.5px;color:var(--t4);margin-top:4px}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:22px}
.stat-card{background:var(--sur);border:1px solid var(--br);border-radius:var(--r);
  padding:14px 18px;box-shadow:var(--s1)}
.stat-label{font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4)}
.stat-val{font-size:30px;font-weight:800;line-height:1;margin:6px 0 2px}
.stat-sub{font-size:11.5px;color:var(--t4)}
.gauge-wrap{margin:10px 0 18px}
.gauge-track{position:relative;height:13px;border-radius:7px;
  background:linear-gradient(to right,var(--sa),var(--wa),var(--ca),var(--ra));box-shadow:inset 0 1px 2px rgba(0,0,0,.12)}
.gauge-pin{position:absolute;top:50%;transform:translate(-50%,-50%);width:22px;height:22px;
  border-radius:50%;border:3px solid #fff;box-shadow:0 2px 8px rgba(0,0,0,.22);transition:left .4s}
.gauge-zones{display:flex;justify-content:space-between;margin-top:6px}
.gauge-zones span{font-size:10.5px;font-weight:700}
.gauge-score-line{text-align:center;font-size:13px;font-weight:700;margin-top:4px}
.ekg-wrap{background:var(--sur2);border:1px solid var(--br);border-radius:var(--r);padding:10px 14px;margin:14px 0}
.ekg-label{font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4);margin-bottom:6px}
.sig-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(195px,1fr));gap:9px;margin:14px 0}
.sig-card{background:var(--sur);border:2px solid var(--br);border-radius:var(--r);
  padding:11px 13px;cursor:pointer;transition:all .15s}
.sig-card:hover{border-color:var(--teal);background:var(--teal3)}
.sig-card.selected{border-color:var(--teal2);background:rgba(6,182,212,.08)}
.sig-card-ico{font-size:20px;margin-bottom:5px}
.sig-card-name{font-size:13px;font-weight:600;color:var(--t1)}
.sig-card-desc{font-size:11.5px;color:var(--t3);margin-top:2px;line-height:1.4}
.int-row{display:flex;gap:8px;margin:8px 0}
.int-btn{flex:1;padding:9px;border:2px solid var(--br);border-radius:var(--rs);
  text-align:center;cursor:pointer;font-size:12px;font-weight:600;transition:all .15s;background:var(--sur)}
.int-btn:hover{border-color:var(--teal);background:var(--teal3)}
.int-btn.sel-1{border-color:var(--wa);background:var(--wbg);color:var(--wc)}
.int-btn.sel-2{border-color:var(--ca);background:var(--cbg);color:var(--cc)}
.int-btn.sel-3{border-color:var(--ra);background:var(--rbg);color:var(--rc)}
.team-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(272px,1fr));gap:15px}
.cg-card{background:var(--sur);border:1px solid var(--br);border-radius:var(--r);
  box-shadow:var(--s1);padding:15px;cursor:pointer;transition:box-shadow .15s}
.cg-card:hover{box-shadow:var(--s2)}
.cg-card-top{display:flex;align-items:center;gap:11px;margin-bottom:11px}
.avatar{border-radius:50%;display:flex;align-items:center;justify-content:center;
  font-weight:700;color:#fff;flex-shrink:0}
.cg-name{font-size:14.5px;font-weight:700;color:var(--t1)}
.cg-role{font-size:12px;color:var(--t3)}
.cg-meta{display:flex;align-items:center;justify-content:space-between;
  margin-top:10px;padding-top:10px;border-top:1px solid var(--br)}
.cg-meta-item{font-size:11.5px;color:var(--t3)}
.cg-meta-item strong{display:block;font-size:13px;color:var(--t1)}
.alert-list{display:flex;flex-direction:column;gap:2px}
.alert-item{display:flex;align-items:center;gap:11px;padding:10px 13px;background:var(--sur);
  border:1px solid var(--br);border-radius:var(--rs);transition:background .15s}
.alert-item:hover{background:var(--sur2)}
.alert-info{flex:1;min-width:0}
.alert-name{font-size:13px;font-weight:700}
.alert-sub{font-size:11.5px;color:var(--t3);margin-top:1px}
.alert-actions{display:flex;gap:5px;flex-shrink:0}
.sig-item{display:flex;align-items:flex-start;gap:11px;padding:9px 0;border-bottom:1px solid var(--br)}
.sig-item:last-child{border-bottom:none}
.sig-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0;margin-top:4px}
.sig-item-body{flex:1}
.sig-item-name{font-size:13px;font-weight:600}
.sig-item-sub{font-size:11.5px;color:var(--t3);margin-top:1px}
.sig-item-ctx{font-size:12px;color:var(--t4);margin-top:3px;font-style:italic}
.sig-item-date{font-size:11px;color:var(--t4);white-space:nowrap}
.int-item{display:flex;align-items:flex-start;gap:11px;padding:11px 0;border-bottom:1px solid var(--br)}
.int-item:last-child{border-bottom:none}
.int-icon{font-size:19px;flex-shrink:0;margin-top:1px}
.int-body{flex:1}
.int-name{font-size:13px;font-weight:600}
.int-sub{font-size:12px;color:var(--t3);margin-top:1px}
.int-outcome{font-size:12px;color:var(--t4);margin-top:3px;font-style:italic}
.star-row{display:flex;gap:1px;margin-top:3px}
.convo-script{background:var(--sur2);border:1px solid var(--br);border-radius:var(--r);padding:13px;margin:9px 0}
.convo-approach{font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t3);margin-bottom:5px}
.convo-text{font-size:13.5px;line-height:1.65;color:var(--t1);font-style:italic}
.convo-copy{font-size:12px;color:var(--teal);cursor:pointer;margin-top:6px;display:inline-block}
.convo-copy:hover{text-decoration:underline}
.guide-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(272px,1fr));gap:13px;margin:14px 0}
.guide-card{background:var(--sur);border:1px solid var(--br);border-radius:var(--r);padding:14px}
.guide-card-ico{font-size:22px;margin-bottom:5px}
.guide-card-name{font-size:14px;font-weight:700;margin-bottom:3px}
.guide-card-desc{font-size:12.5px;color:var(--t2);line-height:1.5}
.guide-card-why{font-size:12px;color:var(--t3);margin-top:7px;padding-top:7px;border-top:1px solid var(--br);font-style:italic;line-height:1.5}
.guide-weight{font-size:11px;font-weight:700;color:var(--teal);text-transform:uppercase;letter-spacing:.3px;margin-bottom:3px}
.inv-banner{background:var(--ibg);border:1px solid rgba(124,58,237,.3);border-radius:var(--r);padding:13px 16px;margin-bottom:16px}
.inv-banner-title{font-size:13px;font-weight:700;color:var(--ic);margin-bottom:3px}
.inv-banner-sub{font-size:12.5px;color:var(--ic);opacity:.8;line-height:1.5}
.inv-list{display:flex;flex-direction:column;gap:5px;margin-top:9px}
.inv-item{display:flex;align-items:center;gap:9px;padding:8px 11px;
  background:rgba(124,58,237,.06);border-radius:var(--rs);cursor:pointer;transition:background .15s}
.inv-item:hover{background:rgba(124,58,237,.11)}
.empty{text-align:center;padding:52px 24px;color:var(--t3)}
.empty-ico{font-size:36px;margin-bottom:10px}
.empty h3{font-size:16px;font-weight:700;color:var(--t2);margin-bottom:6px}
.empty p{font-size:13.5px;max-width:320px;margin:0 auto 16px;line-height:1.6}
.modal-overlay{position:fixed;inset:0;background:rgba(10,20,40,.6);
  display:flex;align-items:center;justify-content:center;z-index:200;padding:20px}
.modal-overlay.hidden{display:none}
.modal-box{background:var(--sur);border-radius:var(--rl);box-shadow:var(--s3);
  width:100%;max-width:560px;max-height:90vh;overflow-y:auto;position:relative}
.modal-inner{padding:24px}
.modal-inner h3{font-size:17px;font-weight:700;margin-bottom:16px;padding-right:30px}
.modal-close{position:absolute;top:14px;right:16px;background:none;border:none;
  font-size:22px;cursor:pointer;color:var(--t4);line-height:1;padding:2px}
.modal-close:hover{color:var(--t1)}
#toast{position:fixed;bottom:22px;right:22px;background:var(--t1);color:#fff;
  padding:11px 16px;border-radius:var(--rs);font-size:13.5px;font-weight:500;
  box-shadow:var(--s3);z-index:300;max-width:360px;display:flex;align-items:center;gap:9px}
#toast.hidden{display:none}
#toast.success{background:#14532d}
#toast.error{background:var(--rc)}
.filter-bar{display:flex;align-items:center;gap:9px;margin-bottom:18px;flex-wrap:wrap}
.filter-bar input{padding:7px 12px;border:1px solid var(--br2);border-radius:var(--rs);
  font-family:inherit;font-size:13px;background:var(--sur);color:var(--t1);min-width:210px}
.filter-bar input:focus{outline:none;border-color:var(--teal);box-shadow:0 0 0 3px rgba(14,116,144,.12)}
.filter-bar select{padding:7px 11px;border:1px solid var(--br2);border-radius:var(--rs);
  font-family:inherit;font-size:13px;background:var(--sur);color:var(--t1)}
.profile-top{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:18px}
.sec-hd{display:flex;align-items:center;justify-content:space-between;margin-bottom:13px}
.sec-hd h3{font-size:15px;font-weight:700}
.sec-hd h4{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t3)}
.tab-bar{display:flex;gap:2px;background:var(--sur2);border:1px solid var(--br);
  border-radius:var(--rs);padding:3px;margin-bottom:14px;width:fit-content}
.tab-pill{padding:5px 13px;border-radius:4px;font-size:13px;font-weight:600;
  cursor:pointer;color:var(--t3);transition:all .15s}
.tab-pill.active{background:var(--sur);color:var(--t1);box-shadow:var(--s1)}
.rec-list{display:flex;flex-direction:column;gap:6px;margin-top:7px}
.rec-item{display:flex;align-items:flex-start;gap:8px;padding:8px 10px;
  background:var(--sur2);border-radius:var(--rs);border:1px solid var(--br)}
.rec-name{font-size:12.5px;font-weight:700;color:var(--t1)}
.rec-desc{font-size:11.5px;color:var(--t3);margin-top:1px;line-height:1.4}
.rec-time{font-size:11px;font-weight:700;color:var(--teal);white-space:nowrap;margin-left:auto;padding-left:6px;flex-shrink:0}
.privacy-box{background:var(--ibg);border:1px solid rgba(124,58,237,.25);border-radius:var(--r);padding:15px 18px;margin:18px 0}
.privacy-box h4{color:var(--ic);font-size:14px;font-weight:700;margin-bottom:6px}
.privacy-box p{font-size:13px;color:var(--ic);opacity:.9;line-height:1.65}
.tbl-wrap{background:var(--sur);border:1px solid var(--br);border-radius:var(--r);box-shadow:var(--s1);overflow:auto}
table{width:100%;border-collapse:collapse;min-width:560px}
thead th{text-align:left;font-size:11px;font-weight:700;text-transform:uppercase;
  letter-spacing:.4px;color:var(--t3);padding:10px 14px;background:var(--sur2);border-bottom:1px solid var(--br)}
tbody td{padding:10px 14px;border-bottom:1px solid var(--br);font-size:13px;vertical-align:middle}
tbody tr:last-child td{border-bottom:none}
tbody tr:hover td{background:var(--sur2)}
.rp-header{border-bottom:2px solid var(--t1);padding-bottom:13px;margin-bottom:16px}
.rp-title{font-size:22px;font-weight:700;letter-spacing:-.5px;font-family:Georgia,serif}
.rp-sub{font-size:13px;color:var(--t3);margin-top:3px}
.rp-sum{display:grid;grid-template-columns:repeat(4,1fr);gap:11px;margin:14px 0}
.rp-sum-card{border:1px solid var(--br);border-radius:var(--rs);padding:10px;text-align:center}
.rp-sum-val{font-size:24px;font-weight:800}
.rp-sum-lbl{font-size:11px;color:var(--t3);margin-top:2px}
@keyframes fadeIn{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}
.fade-in{animation:fadeIn .18s ease}
@media(max-width:768px){
  :root{--sw:0px}
  #sb{display:none}
  #main{margin-left:0}
  .stats-grid{grid-template-columns:repeat(2,1fr)}
  .profile-top{grid-template-columns:1fr}
  .frow{grid-template-columns:1fr}
  #vc{padding:14px 16px}
  .vh{padding:12px 16px}
}
@media print{
  *{-webkit-print-color-adjust:exact!important;print-color-adjust:exact!important}
  #sb,#toast,.modal-overlay,.vh-right{display:none!important}
  #main{margin-left:0!important}
}
</style>
</head>
<body>
<aside id="sb">
  <div class="sb-brand">
    <div class="sb-logo">Caregiver Retention OS</div>
    <div class="sb-sub">Signal &amp; Intervention Framework</div>
  </div>
  <div class="sb-org" data-action="open-org">
    <div class="sb-org-name" id="org-display">My Organization</div>
    <div class="sb-org-hint">Tap to configure</div>
  </div>
  <div class="sb-sep"></div>
  <div class="sb-lbl">Workspace</div>
  <div class="nav-item active" data-action="nav" data-view="dashboard"><span class="nav-ico">◈</span>Dashboard</div>
  <div class="nav-item" data-action="nav" data-view="team"><span class="nav-ico">◉</span>Your Team</div>
  <div class="nav-item" data-action="nav" data-view="log"><span class="nav-ico">⚡</span>Log a Signal</div>
  <div class="nav-item" data-action="nav" data-view="interventions"><span class="nav-ico">✦</span>Interventions</div>
  <div class="sb-sep"></div>
  <div class="sb-lbl">Outputs</div>
  <div class="nav-item" data-action="nav" data-view="reports"><span class="nav-ico">◻</span>Reports &amp; Export</div>
  <div class="nav-item" data-action="nav" data-view="guide"><span class="nav-ico">☰</span>Framework Guide</div>
  <div class="sb-foot">
    <div class="sb-foot-txt">All data lives on your device.<br>Nothing is sent anywhere.</div>
  </div>
</aside>
<div id="main">
  <header class="vh">
    <div class="vh-left"><h2 id="vh-title">Dashboard</h2><p id="vh-sub">Team wellbeing overview</p></div>
    <div class="vh-right" id="vh-actions"></div>
  </header>
  <div id="vc" class="fade-in"></div>
</div>
<div class="modal-overlay hidden" id="modal-overlay">
  <div class="modal-box">
    <button class="modal-close" data-action="close-modal">&#x2715;</button>
    <div class="modal-inner" id="modal-inner"></div>
  </div>
</div>
<div id="toast" class="hidden">
  <span id="toast-msg"></span>
  <span data-action="close-toast" style="cursor:pointer;opacity:.6;margin-left:4px;font-size:16px">&#x2715;</span>
</div>
<script>
'use strict';
// ═══════════════════════════════════════════════════════════════
// CAREGIVER RETENTION OS v2.0
// Behavioral Signal & Intervention Framework
// Worker-First | Privacy by Default | Offline-Ready
// All data stored locally in your browser. Nothing leaves this device.
// ═══════════════════════════════════════════════════════════════

// ─── SIGNAL DEFINITIONS ──────────────────────────────────────
const SIGNALS={
  'explicit-stress':{label:'Explicit Stress Mention',ico:'😔',w:10,cat:'direct',
    desc:'Directly expressing feeling overwhelmed, exhausted, or at a breaking point.',
    why:'Explicit disclosure is rare in caregiving culture. When it surfaces, it demands an immediate, unhurried response — not a form or a checklist.'},
  'tone-shift':{label:'Communication Tone Shift',ico:'💬',w:9,cat:'communication',
    desc:'Messages becoming noticeably shorter, flatter, or more terse than their usual style.',
    why:'Language tone often shifts weeks before explicit distress appears. It reflects emotional withdrawal already in motion.'},
  'after-hours':{label:'After-Hours Contact',ico:'🌙',w:8,cat:'behavioral',
    desc:'Messages or calls arriving very late at night or before 5am — outside any normal work window.',
    why:'Sleep disruption and boundary erosion are among the earliest physiological markers of burnout. The 3am message is rarely about the question it asks.'},
  'sick-days':{label:'Increased Sick Days',ico:'🤒',w:8,cat:'attendance',
    desc:'More frequent sick leave, or more mentions of feeling unwell.',
    why:'Chronic stress reduces immune function. Rising sick days reflect accumulated physical strain, not episodic illness.'},
  'physical-fatigue':{label:'Physical Fatigue Signs',ico:'😴',w:8,cat:'health',
    desc:'Visible exhaustion, sleep complaints, or physical health concerns mentioned in passing.',
    why:'Physical fatigue is body-level burnout. Sleep and energy are the last things to recover — and the first to signal a problem.'},
  'shift-swaps':{label:'Increased Shift Swaps',ico:'🔄',w:7,cat:'scheduling',
    desc:'Meaningfully more swap, drop, or delay requests than their usual pattern.',
    why:'Erratic schedule changes often reflect attempts to manage overload or emotional avoidance — not logistical inconvenience.'},
  'availability-drop':{label:'Availability Decline',ico:'📅',w:7,cat:'scheduling',
    desc:'Turning down hours or shifts they would normally accept without hesitation.',
    why:'Shrinking availability is often protective. It signals they no longer have capacity to give more — before they say so.'},
  'performance-dip':{label:'Performance Inconsistency',ico:'📊',w:7,cat:'performance',
    desc:'Noticeably variable quality of care or task completion compared to their own baseline.',
    why:'Inconsistency — not uniformly poor performance — is the burnout signature. Energy runs out unevenly before it runs out completely.'},
  'client-friction':{label:'Client Friction Increase',ico:'⚠️',w:7,cat:'performance',
    desc:'More friction, noted difficulty, or complaints in client-facing interactions.',
    why:'Emotional labor becomes unsustainable when someone is already running on empty. Client friction is the exhaust pipe.'},
  'doc-decline':{label:'Documentation Decline',ico:'📋',w:6,cat:'performance',
    desc:'Visit notes or records becoming shorter, delayed, or less thorough than before.',
    why:'Documentation is often the first task that slips under cognitive load. It is a proxy for bandwidth, not carelessness.'},
  'withdrawal':{label:'Social Withdrawal',ico:'🚶',w:6,cat:'behavioral',
    desc:'Pulling back from team interactions, missing team moments, becoming quieter than usual.',
    why:'Withdrawal often precedes resignation by weeks. It signals emotional disconnection from the role — long before formal disengagement.'},
  'slow-response':{label:'Slower Response Times',ico:'⏱️',w:5,cat:'communication',
    desc:'Taking significantly longer to reply compared to their established pattern.',
    why:'Lower urgency about work communication reflects declining engagement — an early signal worth noting, not acting on alone.'}
};

// ─── INTERVENTION DEFINITIONS ─────────────────────────────────
const INTERVS={
  'supervisor-checkin':{label:'Supervisor Check-In',ico:'💬',timeline:'24–48 hrs',minRisk:'watch',
    desc:'Private, unstructured conversation. No performance agenda. Ask and listen.'},
  'schedule-adjust':{label:'Schedule Adjustment',ico:'📅',timeline:'1–3 days',minRisk:'watch',
    desc:'Temporarily reduce hours or shift intensity. Ask what would help — don\'t assume.'},
  'peer-support':{label:'Peer Support Match',ico:'🤝',timeline:'3–7 days',minRisk:'watch',
    desc:'Connect with a trusted senior caregiver or peer buddy who understands this work.'},
  'flex-shifts':{label:'Flexible Shift Options',ico:'🔄',timeline:'1 week',minRisk:'watch',
    desc:'Offer alternative shift patterns that better fit their current capacity.'},
  'recognition':{label:'Recognition & Appreciation',ico:'⭐',timeline:'Immediate',minRisk:'stable',
    desc:'Specific, genuine acknowledgment of their work. Not generic. Not a form.'},
  'team-invite':{label:'Team Social Invitation',ico:'🌟',timeline:'1–2 weeks',minRisk:'watch',
    desc:'Warm, low-pressure invitation to a team moment. No expectation of performance.'},
  'respite-time':{label:'Respite Time',ico:'🌿',timeline:'1 week',minRisk:'caution',
    desc:'A paid or subsidized break of 1–5 days. Frame it as earned, not as a flag.'},
  'mh-referral':{label:'Mental Health Referral',ico:'💙',timeline:'2–5 days',minRisk:'caution',
    desc:'Warm handoff to EAP or counseling — a real conversation first, not a form.'},
  'client-reassign':{label:'Client Reassignment',ico:'👥',timeline:'1 week',minRisk:'caution',
    desc:'Reassign to better-matched or lower-intensity clients, temporarily.'},
  'support-line':{label:'Confidential Support Line',ico:'📞',timeline:'Immediate',minRisk:'caution',
    desc:'Share support line details. No disclosure or acknowledgment required.'},
  'training-oppty':{label:'Development Opportunity',ico:'📚',timeline:'2 weeks',minRisk:'stable',
    desc:'Offer a skill pathway or advancement opportunity — something to move toward.'},
  'financial-support':{label:'Financial Support Referral',ico:'💰',timeline:'24–48 hrs',minRisk:'critical',
    desc:'Connect discreetly with emergency assistance, wage advance, or hardship programs.'}
};

// ─── CONVERSATION SCRIPTS ─────────────────────────────────────
const CONVO={
  'explicit-stress':[
    {approach:'Open with presence, not a plan',
     script:'"[Name], I heard what you said and I haven\'t stopped thinking about it. I\'m not coming to you with a checklist right now — I just want to understand what you\'re carrying. When can we talk, just the two of us, no agenda?"'},
    {approach:'Name it directly',
     script:'"You mentioned feeling overwhelmed last week, and I don\'t want to move past that as if it was just a hard day. No evaluation, no performance conversation. I want to figure out together what we can actually change. What would help most right now?"'}
  ],
  'tone-shift':[
    {approach:'Name the change without pressure',
     script:'"[Name], I\'ve noticed your messages have felt a bit different lately — shorter, a little quieter. That happens to all of us when something\'s weighing on us. I\'m not raising it as a problem. I\'m raising it because I\'d like to know how you\'re actually doing."'},
    {approach:'Check in before assuming',
     script:'"I\'ve been meaning to catch you for a few minutes. You seem like you might be running close to empty, and I\'d rather ask now than wait until you hit a wall. What\'s been the hardest part lately?"'}
  ],
  'after-hours':[
    {approach:'Acknowledge the hours directly',
     script:'"[Name], I saw your message from this morning — it came in at 3am. I hope you got some rest after that. I just wanted to ask: how are you sleeping? How are you doing outside of work hours?"'},
    {approach:'Reframe what\'s being asked of them',
     script:'"I noticed you\'ve been reaching out at some unusual hours lately. I want to make sure we\'re not asking more of you than you have to give. Can we look at your schedule together this week? I\'d like to find some breathing room for you."'}
  ],
  'sick-days':[
    {approach:'Lead with care, not attendance',
     script:'"You\'ve needed a few more sick days lately, and I just wanted to check in — no judgment. Taking care of yourself isn\'t a problem here. But I want to make sure you\'re actually okay. What\'s been going on?"'},
    {approach:'Ask what\'s underneath',
     script:'"Before we talk about anything else — how are you doing? I noticed you haven\'t been feeling well lately, and I\'d like to understand what\'s actually going on before I assume I know."'}
  ],
  'shift-swaps':[
    {approach:'Normalize while still asking',
     script:'"Hey [Name], I noticed you\'ve been juggling your schedule a lot lately — and that\'s completely fine. I just want to make sure we\'re building a schedule that actually works for your life, not just one that fills the gaps. Can we sit down for ten minutes?"'},
    {approach:'Create permission to be honest',
     script:'"I saw you\'ve had to move some shifts around lately. I just want to check in and see if there\'s something going on we could work around together."'}
  ],
  'availability-drop':[
    {approach:'Ask without assuming',
     script:'"[Name], I noticed you\'ve been passing on some shifts you\'d usually take. No issue at all — I just wanted to check in and see if there\'s anything happening we could adjust to help."'},
    {approach:'Invite the real conversation',
     script:'"I wanted a quick conversation — not about the schedule, but about you. You seem like you might be pulling back a little, and I want you to know you can tell me if something\'s going on."'}
  ],
  'physical-fatigue':[
    {approach:'Say what you\'re seeing',
     script:'"I\'m going to be honest — you look exhausted, and I\'d rather say that than pretend I didn\'t notice. I\'m not prying. But I don\'t want to keep asking you to run on empty. What do you need right now?"'},
    {approach:'Ask permission to slow down',
     script:'"[Name], I\'ve noticed you seem really worn down lately. I want to make sure we\'re not asking you to keep going past what\'s sustainable. Can we talk about what would help — even just for the next few weeks?"'}
  ],
  'withdrawal':[
    {approach:'Notice without judgment',
     script:'"[Name], I\'ve noticed you\'ve been quieter with the team lately — and that\'s completely okay. I just wanted to say: we see you, and we\'re here. No expectation to show up differently. I just wanted you to know."'},
    {approach:'Low-pressure presence check',
     script:'"I noticed you weren\'t around for the last couple of team moments. I\'m not tracking attendance — I just noticed you weren\'t there, and I wanted to check in. Is everything okay?"'}
  ],
  'doc-decline':[
    {approach:'Lead with curiosity, not correction',
     script:'"I wanted to check in about your documentation lately — not because there\'s a performance issue, but because when notes start slipping, it usually means someone is stretched too thin. Are you doing okay? That matters more than the paperwork."'},
    {approach:'Name the signal, ask what\'s behind it',
     script:'"[Name], I noticed your visit notes have been a bit shorter recently. Before I say anything else, I just want to ask how you\'re doing. Something is clearly on your plate."'}
  ],
  'performance-dip':[
    {approach:'Care before correction',
     script:'"[Name], I\'ve seen some inconsistency in your work over the last few weeks, and my first instinct isn\'t to flag a problem — it\'s to ask if everything\'s alright. What\'s been going on?"'},
    {approach:'Name the pattern as care',
     script:'"When someone we trust starts to struggle, the question isn\'t what went wrong — it\'s what they need. I noticed you\'ve seemed off-balance lately. Can we talk?"'}
  ],
  'client-friction':[
    {approach:'Ask about them, not the client',
     script:'"I wanted to talk about the situation with [client] — not to put you on the spot, but because difficult dynamics often mean something else is going on. What has that felt like for you lately?"'},
    {approach:'Acknowledge the emotional cost',
     script:'"[Name], I heard there\'s been some friction with [client] lately. Before we talk about the client, I want to ask about you. How are you holding up with that assignment? That kind of work takes a lot."'}
  ],
  'slow-response':[
    {approach:'Don\'t make it about response time',
     script:'"[Name], I know response time isn\'t always the main thing — especially when you\'re mid-shift. I just wanted to check in and make sure you\'re not stretched too thin. How are things going?"'},
    {approach:'Name the observation gently',
     script:'"I noticed you\'ve been a bit harder to reach lately. I\'m not worried about the time itself — I\'m wondering if something\'s making things heavier. Is everything okay?"'}
  ]
};

// ─── APP STATE ────────────────────────────────────────────────
let D={org:{name:'',contact:''},caregivers:[],signals:[],interventions:[]};
let VIEW='dashboard',VP='',FILTER='',INT_TAB='active';
let confirmCb=null, logSigType='', logIntensity=0, logCid='';
const KEY='cros_v2';

// ─── DATA LAYER ───────────────────────────────────────────────
function loadData(){try{const s=localStorage.getItem(KEY);if(s)D=JSON.parse(s);}catch(e){}}
function saveData(){try{localStorage.setItem(KEY,JSON.stringify(D));}catch(e){}}
function uid(){return Date.now().toString(36)+Math.random().toString(36).slice(2,6);}
function fmtDate(ts){if(!ts)return'—';return new Date(ts).toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'});}
function relTime(ts){
  if(!ts)return'';
  const d=Math.floor((Date.now()-new Date(ts).getTime())/86400000);
  if(d<1)return'today';if(d===1)return'yesterday';if(d<30)return d+'d ago';
  return fmtDate(ts);
}
function esc(s){const d=document.createElement('div');d.textContent=s||'';return d.innerHTML;}
function avCol(name){
  const c=['#0e7490','#0369a1','#6d28d9','#be185d','#166534','#92400e','#1e40af','#0f766e'];
  let h=0;for(const ch of(name||'?'))h=(h*31+ch.charCodeAt(0))&0xffff;return c[h%c.length];
}
function initials(name){const p=(name||'?').trim().split(/\s+/);return(p[0][0]+(p[1]?p[1][0]:'')).toUpperCase();}
function avatarEl(name,size=36){
  return`<div class="avatar" style="background:${avCol(name)};width:${size}px;height:${size}px;font-size:${Math.round(size*.36)}px">${initials(name)}</div>`;
}

// ─── RISK ENGINE ──────────────────────────────────────────────
const SW={
  'explicit-stress':10,'tone-shift':9,'after-hours':8,'sick-days':8,'physical-fatigue':8,
  'shift-swaps':7,'availability-drop':7,'performance-dip':7,'client-friction':7,
  'doc-decline':6,'withdrawal':6,'slow-response':5
};
function calcRisk(cid){
  const now=Date.now();
  const sigs=D.signals.filter(s=>s.cid===cid);
  if(!sigs.length)return 0;
  let raw=0;
  sigs.forEach(s=>{
    const age=(now-new Date(s.ts).getTime())/86400000;
    if(age>90)return;
    const td=age<=7?2.0:age<=30?1.0:0.4;
    const im=s.intensity===3?2.0:s.intensity===2?1.5:1.0;
    raw+=(SW[s.type]||5)*im*td;
  });
  const r7=sigs.filter(s=>(now-new Date(s.ts).getTime())<604800000);
  const cats=new Set(r7.map(s=>SIGNALS[s.type]?.cat).filter(Boolean));
  if(cats.size>=3)raw+=20;
  return Math.min(100,Math.round(raw/2.6));
}
function getRisk(sc){return sc<=25?'stable':sc<=50?'watch':sc<=75?'caution':'critical';}
function rMeta(risk){
  return{stable:{label:'Stable',col:'var(--sa)',bg:'var(--sbg)',tc:'var(--sc)'},
    watch:{label:'Watch',col:'var(--wa)',bg:'var(--wbg)',tc:'var(--wc)'},
    caution:{label:'Caution',col:'var(--ca)',bg:'var(--cbg)',tc:'var(--cc)'},
    critical:{label:'Critical',col:'var(--ra)',bg:'var(--rbg)',tc:'var(--rc)'}}[risk]||{label:'Stable',col:'var(--sa)',bg:'var(--sbg)',tc:'var(--sc)'};
}
function badge(risk){return`<span class="badge badge-${risk}"><span class="bdot"></span>${rMeta(risk).label}</span>`;}
function suggestIntervs(cid){
  const sc=calcRisk(cid),risk=getRisk(sc);
  const ord={stable:0,watch:1,caution:2,critical:3},lvl=ord[risk]||0;
  const sigMap={
    'explicit-stress':['supervisor-checkin','mh-referral'],
    'tone-shift':['supervisor-checkin','peer-support'],
    'after-hours':['schedule-adjust','supervisor-checkin'],
    'sick-days':['respite-time','schedule-adjust'],
    'physical-fatigue':['respite-time','supervisor-checkin'],
    'shift-swaps':['flex-shifts','schedule-adjust'],
    'availability-drop':['schedule-adjust','supervisor-checkin'],
    'performance-dip':['supervisor-checkin','client-reassign'],
    'client-friction':['client-reassign','peer-support'],
    'doc-decline':['schedule-adjust','supervisor-checkin'],
    'withdrawal':['supervisor-checkin','peer-support','team-invite'],
    'slow-response':['supervisor-checkin','schedule-adjust']
  };
  const now=Date.now();
  const recent=D.signals.filter(s=>s.cid===cid&&(now-new Date(s.ts).getTime())<2592000000)
    .sort((a,b)=>(SW[b.type]||5)*b.intensity-(SW[a.type]||5)*a.intensity);
  const seen=new Set(),res=[];
  recent.forEach(s=>(sigMap[s.type]||[]).forEach(k=>{
    if(!seen.has(k)&&INTERVS[k]&&ord[INTERVS[k].minRisk]<=lvl){seen.add(k);res.push({key:k,...INTERVS[k]});}
  }));
  Object.entries(INTERVS).forEach(([k,v])=>{
    if(!seen.has(k)&&ord[v.minRisk]<=lvl){seen.add(k);res.push({key:k,...v});}
  });
  return res.slice(0,4);
}
function isInvisible(cid){
  if(calcRisk(cid)>25)return false;
  const careTypes=['recognition','supervisor-checkin','peer-support','team-invite'];
  const cares=D.interventions.filter(i=>i.cid===cid&&careTypes.includes(i.type)&&i.status==='completed');
  const now=Date.now();
  if(!cares.length){
    const cg=D.caregivers.find(c=>c.id===cid);
    return cg?(now-new Date(cg.createdAt).getTime())/86400000>=45:false;
  }
  const latest=Math.max(...cares.map(i=>new Date(i.completedAt||i.createdAt).getTime()));
  return(now-latest)/86400000>=45;
}
function daysSinceCare(cid){
  const ct=['recognition','supervisor-checkin','peer-support','team-invite'];
  const cares=D.interventions.filter(i=>i.cid===cid&&ct.includes(i.type)&&i.status==='completed');
  if(!cares.length)return null;
  const latest=Math.max(...cares.map(i=>new Date(i.completedAt||i.createdAt).getTime()));
  return Math.floor((Date.now()-latest)/86400000);
}

// ─── COMPONENT RENDERERS ──────────────────────────────────────
function renderGauge(score,risk){
  const m=rMeta(risk),pct=Math.max(2,Math.min(98,score));
  return`<div class="gauge-wrap">
    <div class="gauge-track"><div class="gauge-pin" style="left:${pct}%;background:${m.col}"></div></div>
    <div class="gauge-zones">
      <span style="color:var(--sa)">Stable</span><span style="color:var(--wa)">Watch</span>
      <span style="color:var(--ca)">Caution</span><span style="color:var(--ra)">Critical</span>
    </div>
    <div class="gauge-score-line" style="color:${m.col}"><strong>${m.label}</strong> &mdash; ${score}/100</div>
  </div>`;
}
function renderEKG(cid){
  const W=680,H=76,DAYS=60,baseline=H*0.68,dpx=W/DAYS,now=Date.now();
  const sigs=D.signals.filter(s=>s.cid===cid&&(now-new Date(s.ts).getTime())/86400000<=DAYS);
  let svg=`<svg viewBox="0 0 ${W} ${H}" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:${H}px;display:block">`;
  for(let w=1;w<9;w++){const x=Math.round((DAYS-w*7)*dpx);if(x>0&&x<W)svg+=`<line x1="${x}" y1="3" x2="${x}" y2="${H-3}" stroke="#dde5ef" stroke-width="1" stroke-dasharray="3,3"/>`;}
  const z7=Math.round((DAYS-7)*dpx);
  svg+=`<rect x="${z7}" y="0" width="${W-z7}" height="${H}" fill="rgba(6,182,212,0.05)" rx="3"/>`;
  svg+=`<line x1="8" y1="${baseline}" x2="${W-8}" y2="${baseline}" stroke="#dde5ef" stroke-width="1.5"/>`;
  sigs.forEach(s=>{
    const age=(now-new Date(s.ts).getTime())/86400000;
    const x=Math.round((DAYS-age)*dpx);
    if(x<12||x>W-12)return;
    const sh=[0,17,33,52][s.intensity]||17;
    const col=s.intensity===3?'#be185d':s.intensity===2?'#ea580c':'#d97706';
    const pts=`${x-10},${baseline} ${x-4},${baseline} ${x-1},${baseline-sh} ${x+3},${baseline+Math.round(sh*.27)} ${x+10},${baseline}`;
    svg+=`<polyline points="${pts}" fill="none" stroke="${col}" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round" opacity="0.88"/>`;
    svg+=`<circle cx="${x-1}" cy="${baseline-sh}" r="3" fill="${col}" opacity="0.8"/>`;
  });
  svg+=`<text x="6" y="${H-3}" font-size="9" fill="#94a3b8" font-family="-apple-system,sans-serif">60 days ago</text>`;
  svg+=`<text x="${W-6}" y="${H-3}" font-size="9" fill="#94a3b8" font-family="-apple-system,sans-serif" text-anchor="end">today</text>`;
  svg+=`<text x="${z7+5}" y="13" font-size="9" fill="#06b6d4" font-family="-apple-system,sans-serif">↑ last 7 days</text>`;
  if(!sigs.length)svg+=`<text x="${W/2}" y="${baseline-10}" font-size="11" fill="#b0bec8" font-family="-apple-system,sans-serif" text-anchor="middle">No signals recorded in the last 60 days</text>`;
  svg+=`</svg>`;
  return svg;
}
function setHeader(title,sub,actions=''){
  document.getElementById('vh-title').textContent=title;
  document.getElementById('vh-sub').textContent=sub;
  document.getElementById('vh-actions').innerHTML=actions;
  document.querySelectorAll('.nav-item').forEach(el=>el.classList.toggle('active',el.dataset.view===VIEW));
}

// ─── NAVIGATE ─────────────────────────────────────────────────
function navigate(view,param=''){
  VIEW=view;VP=param;
  const vc=document.getElementById('vc');
  vc.className='fade-in';
  ({dashboard:renderDashboard,team:renderTeam,profile:()=>renderProfile(param),
    log:()=>renderLogSignal(param),interventions:renderInterventions,
    reports:renderReports,guide:renderGuide}[view]||renderDashboard)();
}

// ─── DASHBOARD ────────────────────────────────────────────────
function renderDashboard(){
  const total=D.caregivers.length;
  const scored=D.caregivers.map(c=>({c,sc:calcRisk(c.id),risk:getRisk(calcRisk(c.id))}));
  const crit=scored.filter(s=>s.risk==='critical').length;
  const caut=scored.filter(s=>s.risk==='caution').length;
  const watch=scored.filter(s=>s.risk==='watch').length;
  const atRisk=scored.filter(s=>s.sc>50).sort((a,b)=>b.sc-a.sc);
  const invisibles=D.caregivers.filter(c=>isInvisible(c.id));
  const recentSigs=[...D.signals].sort((a,b)=>new Date(b.ts)-new Date(a.ts)).slice(0,10);
  setHeader('Dashboard','Team wellbeing at a glance',
    `<button class="btn btn-primary" data-action="nav" data-view="log">⚡ Log Signal</button>
     <button class="btn btn-secondary" data-action="open-add-cg">+ Add Caregiver</button>`);
  if(!total){
    document.getElementById('vc').innerHTML=`<div class="empty">
      <div class="empty-ico">🌱</div><h3>Welcome to Caregiver Retention OS</h3>
      <p>Add your team members to begin tracking wellbeing signals, or load the sample team to explore the framework.</p>
      <div class="btn-row" style="justify-content:center">
        <button class="btn btn-primary" data-action="open-add-cg">+ Add First Caregiver</button>
        <button class="btn btn-secondary" data-action="load-sample">Load Sample Team</button>
      </div></div>`;return;
  }
  const invHtml=invisibles.length?`<div class="inv-banner">
    <div class="inv-banner-title">⭐ Invisible Contributors — ${invisibles.length} caregiver${invisibles.length>1?'s':''}</div>
    <div class="inv-banner-sub">These team members are stable and reliable. No signals. No problems. And perhaps no recognition for 45+ days. That silence is itself a signal.</div>
    <div class="inv-list">${invisibles.map(c=>{const d=daysSinceCare(c.id);return`<div class="inv-item" data-action="nav" data-view="profile" data-id="${c.id}">
      ${avatarEl(c.name,30)}<div><div style="font-size:13px;font-weight:700">${esc(c.name)}</div>
      <div style="font-size:11.5px;color:var(--ia)">${d===null?'No care touchpoint logged yet':`Last appreciated ${d} days ago`}</div></div>
      <button class="btn btn-sm btn-ghost" style="margin-left:auto" data-action="open-add-interv" data-cid="${c.id}">Reach Out →</button>
    </div>`;}).join('')}</div></div>`:'';
  const alertHtml=atRisk.length?`<div class="alert-list">${atRisk.map(({c,sc,risk})=>{
    const top=D.signals.filter(s=>s.cid===c.id).sort((a,b)=>new Date(b.ts)-new Date(a.ts))[0];
    return`<div class="alert-item">${avatarEl(c.name,34)}
      <div class="alert-info"><div class="alert-name">${esc(c.name)}</div>
      <div class="alert-sub">${badge(risk)} &nbsp; ${sc}/100${top?` &mdash; ${esc(SIGNALS[top.type]?.label||top.type)} <span style="color:var(--t4)">${relTime(top.ts)}</span>`:''}</div></div>
      <div class="alert-actions">
        <button class="btn btn-sm btn-ghost" data-action="show-convo" data-id="${c.id}" title="Conversation starter">💬</button>
        <button class="btn btn-sm btn-secondary" data-action="open-add-interv" data-cid="${c.id}">Intervene</button>
        <button class="btn btn-sm btn-ghost" data-action="nav" data-view="profile" data-id="${c.id}">View →</button>
      </div></div>`;}).join('')}</div>`
    :`<div style="color:var(--t4);font-size:13.5px;padding:18px;text-align:center;background:var(--sur2);border-radius:var(--r)">✅ No caregivers above the caution threshold right now.</div>`;
  const recentHtml=recentSigs.length?recentSigs.map(s=>{
    const cg=D.caregivers.find(c=>c.id===s.cid);
    const sig=SIGNALS[s.type]||{};
    const col=s.intensity===3?'var(--ra)':s.intensity===2?'var(--ca)':'var(--wa)';
    return`<div class="sig-item"><div class="sig-dot" style="background:${col};margin-top:4px;flex-shrink:0"></div>
      <div class="sig-item-body"><div class="sig-item-name">${sig.ico||''} ${esc(sig.label||s.type)}</div>
      <div class="sig-item-sub">${cg?`<a href="#" style="color:var(--teal);text-decoration:none" data-action="nav" data-view="profile" data-id="${cg.id}">${esc(cg.name)}</a> &mdash; `:''}${'●'.repeat(s.intensity)}${'○'.repeat(3-s.intensity)}</div>
      ${s.ctx?`<div class="sig-item-ctx">${esc(s.ctx)}</div>`:''}</div>
      <div class="sig-item-date">${relTime(s.ts)}</div></div>`;}).join('')
    :`<div style="color:var(--t4);font-size:13px;text-align:center;padding:16px">No signals logged yet.</div>`;
  document.getElementById('vc').innerHTML=`
    <div class="stats-grid">
      <div class="stat-card"><div class="stat-label">Team Size</div><div class="stat-val">${total}</div><div class="stat-sub">Caregivers tracked</div></div>
      <div class="stat-card"><div class="stat-label">Needs Attention</div><div class="stat-val" style="color:var(--ra)">${crit+caut}</div><div class="stat-sub">Caution or Critical</div></div>
      <div class="stat-card"><div class="stat-label">Under Watch</div><div class="stat-val" style="color:var(--wa)">${watch}</div><div class="stat-sub">Monitoring phase</div></div>
      <div class="stat-card"><div class="stat-label">Invisible Contributors</div><div class="stat-val" style="color:var(--ia)">${invisibles.length}</div><div class="stat-sub">Overdue for appreciation</div></div>
    </div>
    ${invHtml}
    <div style="display:grid;grid-template-columns:3fr 2fr;gap:20px">
      <div>
        <div class="sec-hd"><h3>Needs Attention Now</h3>${atRisk.length?`<span style="font-size:12px;color:var(--t4)">${atRisk.length} caregiver${atRisk.length>1?'s':''}</span>`:''}</div>
        ${alertHtml}
      </div>
      <div>
        <div class="sec-hd"><h3>Recent Signals</h3><button class="btn btn-sm btn-ghost" data-action="nav" data-view="log">+ Log</button></div>
        <div class="card" style="padding:6px 14px">${recentHtml}</div>
      </div>
    </div>`;
}

// ─── TEAM ─────────────────────────────────────────────────────
function renderTeam(){
  setHeader('Your Team',`${D.caregivers.length} caregivers`,
    `<input type="text" id="tsearch" placeholder="Search…" style="padding:7px 12px;border:1px solid var(--br2);border-radius:var(--rs);font-size:13px;width:190px" oninput="FILTER=this.value;renderTeamGrid()">
     <button class="btn btn-primary" data-action="open-add-cg">+ Add Caregiver</button>`);
  document.getElementById('vc').innerHTML=`<div id="tg"></div>`;
  renderTeamGrid();
}
function renderTeamGrid(){
  const q=FILTER.toLowerCase();
  const list=D.caregivers.filter(c=>!q||c.name.toLowerCase().includes(q)||(c.role||'').toLowerCase().includes(q))
    .map(c=>({c,sc:calcRisk(c.id),risk:getRisk(calcRisk(c.id))}))
    .sort((a,b)=>b.sc-a.sc);
  const el=document.getElementById('tg');if(!el)return;
  if(!D.caregivers.length){el.innerHTML=`<div class="empty"><div class="empty-ico">👥</div><h3>No caregivers yet</h3><p>Add team members to begin tracking their wellbeing signals.</p><button class="btn btn-primary" data-action="open-add-cg">+ Add First Caregiver</button></div>`;return;}
  if(!list.length){el.innerHTML=`<div class="empty"><h3>No results</h3><p>No caregivers match "${esc(FILTER)}".</p></div>`;return;}
  el.innerHTML=`<div class="team-grid">${list.map(({c,sc,risk})=>{
    const dsc=daysSinceCare(c.id),inv=isInvisible(c.id),m=rMeta(risk);
    return`<div class="cg-card" data-action="nav" data-view="profile" data-id="${c.id}">
      <div class="cg-card-top">${avatarEl(c.name,42)}
        <div style="flex:1;min-width:0"><div class="cg-name">${esc(c.name)}</div><div class="cg-role">${esc(c.role||'Caregiver')}</div></div>
        ${badge(risk)}
      </div>
      <div class="ekg-wrap" style="padding:7px 10px;margin:0 0 8px">${renderEKG(c.id)}</div>
      <div class="cg-meta">
        <div class="cg-meta-item"><strong style="color:${m.col}">${sc}/100</strong>Risk score</div>
        <div class="cg-meta-item"><strong>${dsc===null?'—':dsc+'d'}</strong>Since care</div>
        ${inv?`<span style="font-size:11px;background:var(--ibg);color:var(--ic);padding:2px 8px;border-radius:999px;font-weight:700">⭐ Invisible</span>`:''}
      </div>
    </div>`;}).join('')}</div>`;
}

// ─── CAREGIVER PROFILE ────────────────────────────────────────
function renderProfile(id){
  const cg=D.caregivers.find(c=>c.id===id);if(!cg){navigate('team');return;}
  const sc=calcRisk(id),risk=getRisk(sc),m=rMeta(risk);
  const sigs=D.signals.filter(s=>s.cid===id).sort((a,b)=>new Date(b.ts)-new Date(a.ts));
  const intv=D.interventions.filter(i=>i.cid===id).sort((a,b)=>new Date(b.createdAt)-new Date(a.createdAt));
  const recs=suggestIntervs(id);
  const topTypes=[...new Set(sigs.slice(0,6).map(s=>s.type))];
  const hasConvo=topTypes.some(t=>CONVO[t]);
  const dsc=daysSinceCare(id),inv=isInvisible(id);
  setHeader(cg.name,cg.role||'Caregiver',
    `<button class="btn btn-ghost" data-action="nav" data-view="team">← Team</button>
     ${hasConvo?`<button class="btn btn-secondary" data-action="show-convo" data-id="${id}">💬 Conversation Starter</button>`:''}
     <button class="btn btn-primary" data-action="nav" data-view="log" data-id="${id}">⚡ Log Signal</button>
     <button class="btn btn-secondary" data-action="open-add-interv" data-cid="${id}">+ Intervention</button>
     <button class="btn btn-ico btn-danger" data-action="del-cg" data-id="${id}" title="Remove">🗑</button>`);
  document.getElementById('vc').innerHTML=`
    ${inv?`<div class="inv-banner" style="margin-bottom:16px">
      <div class="inv-banner-title">⭐ Invisible Contributor Alert</div>
      <div class="inv-banner-sub">${esc(cg.name)} is stable with no recent signals — ${dsc===null?'but has never had a care touchpoint logged':`but the last care touchpoint was ${dsc} days ago`}. Reliable people go unnoticed. That\'s a retention risk.</div>
    </div>`:''}
    <div class="profile-top">
      <div>
        <div class="card" style="margin-bottom:15px">
          <div class="card-title">Wellbeing Risk Score</div>
          ${renderGauge(sc,risk)}
        </div>
        <div class="card">
          <div class="card-title">Recommended Actions</div>
          ${recs.length?`<div class="rec-list">${recs.map(r=>`<div class="rec-item">
            <span style="font-size:18px">${r.ico}</span>
            <div><div class="rec-name">${esc(r.label)}</div><div class="rec-desc">${esc(r.desc)}</div></div>
            <div class="rec-time">${r.timeline}</div>
          </div>`).join('')}</div>`:`<p style="color:var(--t4);font-size:13px">Log signals to see tailored recommendations.</p>`}
          <div style="margin-top:11px"><button class="btn btn-sm btn-primary" data-action="open-add-interv" data-cid="${id}">+ Log Intervention</button></div>
        </div>
      </div>
      <div>
        <div class="card">
          <div class="card-title">Caregiver Details</div>
          <div style="display:flex;align-items:center;gap:12px;margin-bottom:13px">${avatarEl(cg.name,46)}
            <div><div style="font-size:16px;font-weight:700">${esc(cg.name)}</div><div style="font-size:13px;color:var(--t3)">${esc(cg.role||'—')}</div></div>
          </div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;font-size:13px">
            <div><div style="font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4)">Start Date</div><div style="font-weight:600">${cg.startDate?fmtDate(cg.startDate):'—'}</div></div>
            <div><div style="font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4)">Last Care Touch</div><div style="font-weight:600">${dsc===null?'Never logged':dsc+'d ago'}</div></div>
            <div><div style="font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4)">Signals (30d)</div><div style="font-weight:600">${D.signals.filter(s=>s.cid===id&&(Date.now()-new Date(s.ts).getTime())<2592000000).length}</div></div>
            <div><div style="font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--t4)">Active Interventions</div><div style="font-weight:600">${D.interventions.filter(i=>i.cid===id&&i.status==='active').length}</div></div>
          </div>
          ${cg.notes?`<div style="margin-top:11px;font-size:12.5px;color:var(--t3);background:var(--sur2);border-radius:var(--rs);padding:9px;line-height:1.5">${esc(cg.notes)}</div>`:''}
          <div style="margin-top:11px"><button class="btn btn-sm btn-secondary" data-action="open-edit-cg" data-id="${id}">Edit Details</button></div>
        </div>
      </div>
    </div>
    <div class="card" style="margin-bottom:18px">
      <div class="card-title">Signal Timeline — Last 60 Days</div>
      <div class="ekg-wrap">${renderEKG(id)}</div>
      <div style="display:flex;gap:14px;font-size:11.5px;color:var(--t3);margin-top:7px;flex-wrap:wrap">
        <span><span style="color:var(--wa);font-weight:700">●</span> Mild</span>
        <span><span style="color:var(--ca);font-weight:700">●</span> Moderate</span>
        <span><span style="color:var(--ra);font-weight:700">●</span> Severe</span>
        <span style="margin-left:auto;color:var(--teal)">Blue tint = last 7 days</span>
      </div>
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:18px">
      <div>
        <div class="sec-hd"><h4>Signal History</h4><button class="btn btn-sm btn-ghost" data-action="nav" data-view="log" data-id="${id}">+ Log</button></div>
        ${sigs.length?sigs.slice(0,15).map(s=>{
          const sig=SIGNALS[s.type]||{};
          const col=s.intensity===3?'var(--ra)':s.intensity===2?'var(--ca)':'var(--wa)';
          return`<div class="sig-item"><div class="sig-dot" style="background:${col};margin-top:4px;flex-shrink:0"></div>
            <div class="sig-item-body"><div class="sig-item-name">${sig.ico||''} ${esc(sig.label||s.type)}</div>
            <div class="sig-item-sub">${'●'.repeat(s.intensity)}${'○'.repeat(3-s.intensity)} &mdash; ${relTime(s.ts)}</div>
            ${s.ctx?`<div class="sig-item-ctx">${esc(s.ctx)}</div>`:''}</div>
            <button class="btn btn-sm btn-ico" data-action="del-sig" data-id="${s.id}" title="Remove" style="font-size:13px">&#x2715;</button>
          </div>`;}).join('')
          :`<div style="color:var(--t4);font-size:13px;padding:14px 0">No signals yet. <a href="#" data-action="nav" data-view="log" data-id="${id}" style="color:var(--teal)">Log one →</a></div>`}
      </div>
      <div>
        <div class="sec-hd"><h4>Interventions</h4><button class="btn btn-sm btn-ghost" data-action="open-add-interv" data-cid="${id}">+ Add</button></div>
        ${intv.length?intv.map(i=>{
          const iv=INTERVS[i.type]||{};
          const stars=i.effectiveness?'★'.repeat(i.effectiveness)+'☆'.repeat(5-i.effectiveness):'';
          return`<div class="int-item"><span class="int-icon">${iv.ico||'📌'}</span>
            <div class="int-body"><div class="int-name">${esc(iv.label||i.type)}</div>
            <div class="int-sub">${i.status==='completed'?'✅ Done':'🔵 Active'} &mdash; ${fmtDate(i.createdAt)}</div>
            ${i.outcome?`<div class="int-outcome">"${esc(i.outcome)}"</div>`:''}
            ${stars?`<div class="star-row">${[...stars].map(s=>`<span style="color:${s==='★'?'#d97706':'#cbd5e1'}">${s}</span>`).join('')}</div>`:''}</div>
            ${i.status==='active'?`<button class="btn btn-sm btn-ghost" data-action="complete-interv" data-id="${i.id}">Complete</button>`:''}
          </div>`;}).join('')
          :`<div style="color:var(--t4);font-size:13px;padding:14px 0">No interventions logged yet.</div>`}
      </div>
    </div>`;
}

// ─── LOG SIGNAL ───────────────────────────────────────────────
function renderLogSignal(pre=''){
  logCid=pre||'';logSigType='';logIntensity=0;
  const cg=logCid?D.caregivers.find(c=>c.id===logCid):null;
  setHeader('Log a Signal',cg?`for ${cg.name}`:'Select caregiver and signal');
  const opts=D.caregivers.map(c=>`<option value="${c.id}"${c.id===logCid?' selected':''}>${esc(c.name)}</option>`).join('');
  if(!D.caregivers.length){document.getElementById('vc').innerHTML=`<div class="empty"><div class="empty-ico">👥</div><h3>Add caregivers first</h3><p>You need at least one caregiver to log signals.</p><button class="btn btn-primary" data-action="open-add-cg">+ Add Caregiver</button></div>`;return;}
  document.getElementById('vc').innerHTML=`<div style="max-width:720px">
    <div class="card" style="margin-bottom:14px">
      <div class="field"><label>Caregiver</label>
        <select id="log-cid" onchange="logCid=this.value"><option value="">— Select —</option>${opts}</select>
      </div>
    </div>
    <div class="card" style="margin-bottom:14px">
      <div class="card-title">Signal Type</div>
      <div class="sig-grid">${Object.entries(SIGNALS).map(([k,v])=>`
        <div class="sig-card" data-action="sel-sig" data-type="${k}">
          <div class="sig-card-ico">${v.ico}</div>
          <div class="sig-card-name">${esc(v.label)}</div>
          <div class="sig-card-desc">${esc(v.desc)}</div>
        </div>`).join('')}
      </div>
    </div>
    <div class="card" style="margin-bottom:14px">
      <div class="card-title">Intensity Level</div>
      <div class="int-row">
        <div class="int-btn" data-action="sel-int" data-level="1"><div style="font-size:18px">🟡</div><div>Mild</div><div style="font-size:11px;opacity:.7;margin-top:2px">Noticed, not alarming</div></div>
        <div class="int-btn" data-action="sel-int" data-level="2"><div style="font-size:18px">🟠</div><div>Moderate</div><div style="font-size:11px;opacity:.7;margin-top:2px">Clear pattern forming</div></div>
        <div class="int-btn" data-action="sel-int" data-level="3"><div style="font-size:18px">🔴</div><div>Severe</div><div style="font-size:11px;opacity:.7;margin-top:2px">Immediate attention</div></div>
      </div>
    </div>
    <div class="card" style="margin-bottom:14px">
      <div class="field"><label>Context Note (optional)</label>
        <textarea id="log-ctx" placeholder="What did you observe? Keep it factual and specific. Stored locally for your reference only."></textarea>
        <div class="field-hint">This note is private to this device and is for supervisory reference only.</div>
      </div>
    </div>
    <div id="log-info"></div>
    <div class="btn-row">
      <button class="btn btn-primary" data-action="save-signal">Save Signal</button>
      <button class="btn btn-secondary" data-action="nav" data-view="dashboard">Cancel</button>
    </div>
  </div>`;
}
function updateLogInfo(){
  const box=document.getElementById('log-info');if(!box||!logSigType)return;
  const sig=SIGNALS[logSigType];if(!sig)return;
  box.innerHTML=`<div class="card" style="margin-bottom:14px;border-left:3px solid var(--teal)">
    <div style="font-size:13px;font-weight:700;margin-bottom:4px">${sig.ico} Why this signal matters</div>
    <div style="font-size:13px;color:var(--t2);line-height:1.65">${esc(sig.why)}</div>
    <div style="margin-top:7px;font-size:12px;color:var(--t4)">Weight: ${sig.w}/10 &nbsp;·&nbsp; Category: ${sig.cat}</div>
  </div>`;
}

// ─── INTERVENTIONS ────────────────────────────────────────────
function renderInterventions(){
  const all=[...D.interventions].sort((a,b)=>new Date(b.createdAt)-new Date(a.createdAt));
  const active=all.filter(i=>i.status==='active');
  const done=all.filter(i=>i.status==='completed');
  const shown=INT_TAB==='active'?active:INT_TAB==='completed'?done:all;
  const rated=done.filter(i=>i.effectiveness);
  const avg=rated.length?(rated.reduce((s,i)=>s+i.effectiveness,0)/rated.length).toFixed(1):null;
  setHeader('Interventions',`${active.length} active, ${done.length} completed`,
    `<button class="btn btn-primary" data-action="open-add-interv" data-cid="">+ Add Intervention</button>`);
  document.getElementById('vc').innerHTML=`
    <div style="display:flex;gap:12px;margin-bottom:18px;flex-wrap:wrap">
      <div class="stat-card" style="flex:1;min-width:120px"><div class="stat-label">Active</div><div class="stat-val" style="color:var(--teal)">${active.length}</div></div>
      <div class="stat-card" style="flex:1;min-width:120px"><div class="stat-label">Completed</div><div class="stat-val" style="color:var(--sa)">${done.length}</div></div>
      <div class="stat-card" style="flex:1;min-width:120px"><div class="stat-label">Avg Effectiveness</div><div class="stat-val" style="color:var(--wa)">${avg?avg+'/5':'—'}</div></div>
    </div>
    <div class="tab-bar">
      <div class="tab-pill${INT_TAB==='active'?' active':''}" data-action="set-itab" data-tab="active">Active (${active.length})</div>
      <div class="tab-pill${INT_TAB==='completed'?' active':''}" data-action="set-itab" data-tab="completed">Completed (${done.length})</div>
      <div class="tab-pill${INT_TAB==='all'?' active':''}" data-action="set-itab" data-tab="all">All (${all.length})</div>
    </div>
    ${!shown.length?`<div class="empty"><div class="empty-ico">✦</div><h3>No interventions here</h3><p>${INT_TAB==='active'?'No active interventions. Add one from a caregiver profile or the button above.':'No completed interventions yet.'}</p></div>`:`
    <div class="tbl-wrap"><table>
      <thead><tr><th>Caregiver</th><th>Intervention</th><th>Date</th><th>Status</th><th>Effectiveness</th><th></th></tr></thead>
      <tbody>${shown.map(i=>{
        const cg=D.caregivers.find(c=>c.id===i.cid);
        const iv=INTERVS[i.type]||{};
        const stars=i.effectiveness?'★'.repeat(i.effectiveness)+'☆'.repeat(5-i.effectiveness):'—';
        return`<tr>
          <td><div style="font-weight:700">${cg?esc(cg.name):'Unknown'}</div></td>
          <td>${iv.ico||''} ${esc(iv.label||i.type)}</td>
          <td style="color:var(--t3)">${fmtDate(i.createdAt)}</td>
          <td>${i.status==='completed'?`<span style="color:var(--sa);font-weight:700">✅ Done</span>`:`<span style="color:var(--teal);font-weight:700">🔵 Active</span>`}</td>
          <td style="color:var(--wa)">${stars}</td>
          <td><div style="display:flex;gap:5px">
            ${i.status==='active'?`<button class="btn btn-sm btn-ghost" data-action="complete-interv" data-id="${i.id}">Complete</button>`:''}
            <button class="btn btn-sm btn-ico" data-action="del-interv" data-id="${i.id}" style="font-size:12px">&#x2715;</button>
          </div></td>
        </tr>`;}).join('')}
      </tbody>
    </table></div>`}`;
}

// ─── REPORTS ──────────────────────────────────────────────────
function renderReports(){
  const now=new Date().toLocaleDateString('en-US',{month:'long',day:'numeric',year:'numeric'});
  const scored=D.caregivers.map(c=>({c,sc:calcRisk(c.id),r:getRisk(calcRisk(c.id))}));
  const crit=scored.filter(s=>s.r==='critical').length,caut=scored.filter(s=>s.r==='caution').length;
  const watch=scored.filter(s=>s.r==='watch').length,stab=scored.filter(s=>s.r==='stable').length;
  setHeader('Reports & Export','Generate a PDF report or export a JSON data backup',
    `<button class="btn btn-primary" data-action="print-report">🖨️ Print / Save as PDF</button>
     <button class="btn btn-secondary" data-action="export-json">⬇ Export JSON Backup</button>`);
  document.getElementById('vc').innerHTML=`
    <div class="card" style="margin-bottom:18px">
      <div class="card-title">What the PDF Report Includes</div>
      <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));gap:6px">
        ${['📊 Executive summary with risk distribution','👥 Full team overview table','📈 Signal history per caregiver','✦ Intervention logs with outcomes','💡 Recommended next actions per person','📋 Signal & intervention reference'].map(i=>`<div style="font-size:13px;padding:5px 0">${i}</div>`).join('')}
      </div>
    </div>
    <div style="background:var(--sur);border:1px solid var(--br);border-radius:var(--r);padding:22px;box-shadow:var(--s1)">
      <div class="rp-header">
        <div style="font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--t4);margin-bottom:5px">CAREGIVER WELLBEING ASSESSMENT</div>
        <div class="rp-title">${esc(D.org.name||'Your Organization')}</div>
        <div class="rp-sub">Generated: ${now} &nbsp;|&nbsp; CONFIDENTIAL</div>
      </div>
      <div class="rp-sum">
        <div class="rp-sum-card"><div class="rp-sum-val">${D.caregivers.length}</div><div class="rp-sum-lbl">Total Team</div></div>
        <div class="rp-sum-card"><div class="rp-sum-val" style="color:var(--sa)">${stab}</div><div class="rp-sum-lbl">Stable</div></div>
        <div class="rp-sum-card"><div class="rp-sum-val" style="color:var(--wa)">${watch}</div><div class="rp-sum-lbl">Watch</div></div>
        <div class="rp-sum-card"><div class="rp-sum-val" style="color:var(--ra)">${crit+caut}</div><div class="rp-sum-lbl">Needs Attention</div></div>
      </div>
      ${D.caregivers.length?`
      <div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--t4);margin:14px 0 8px">Team Preview (sorted by risk)</div>
      <table><thead><tr><th>Name</th><th>Role</th><th>Risk Level</th><th>Score</th></tr></thead>
      <tbody>${scored.sort((a,b)=>b.s-a.s).map(({c,s,r})=>`<tr>
        <td><strong>${esc(c.name)}</strong></td><td>${esc(c.role||'—')}</td>
        <td><span style="font-weight:700;color:${rMeta(r).col}">${rMeta(r).label}</span></td>
        <td>${s}/100</td></tr>`).join('')}
      </tbody></table>
      <div style="font-size:11px;color:var(--t4);margin-top:11px;text-align:center">Full PDF includes individual signal histories, intervention records, and recommended next actions per caregiver.</div>`
      :`<div style="font-size:13px;color:var(--t4);text-align:center;padding:20px">Add caregivers to generate a full report.</div>`}
    </div>`;
}

// ─── FRAMEWORK GUIDE ─────────────────────────────────────────
function renderGuide(){
  setHeader('Framework Guide','Reference material for the Behavioral Signal & Intervention Framework');
  document.getElementById('vc').innerHTML=`<div style="max-width:900px">
    <div class="card" style="margin-bottom:18px">
      <div style="font-size:15px;font-weight:700;margin-bottom:9px">How This Framework Works</div>
      <div style="font-size:13.5px;color:var(--t2);line-height:1.72">
        This tool helps supervisors detect early signs of caregiver burnout — before they become a resignation. It logs behavioral signals, calculates a risk score weighted by recency and severity, and surfaces specific conversation approaches and interventions matched to the signals present.<br><br>
        The design is <strong>worker-first</strong>: all data stays on your device, every feature is built around proactive support rather than monitoring, and transparency with caregivers about how this framework is used is built into the methodology — not optional.
      </div>
    </div>
    <div class="privacy-box">
      <h4>🔒 Privacy Promise</h4>
      <p>No data ever leaves this device. Nothing is sent to any server, ever. Every signal, note, and intervention record is stored only in your browser's local storage. Caregivers should be informed that this framework is in use, and that its purpose is to support them — not to monitor or evaluate them. That transparency is not a nice-to-have. It is the mechanism that makes everything else work.</p>
    </div>
    <div style="font-size:15px;font-weight:700;margin:22px 0 13px">The 12 Behavioral Signals</div>
    <div class="guide-grid">${Object.entries(SIGNALS).map(([k,v])=>`
      <div class="guide-card">
        <div class="guide-card-ico">${v.ico}</div>
        <div class="guide-weight">Weight ${v.w}/10 · ${v.cat}</div>
        <div class="guide-card-name">${esc(v.label)}</div>
        <div class="guide-card-desc">${esc(v.desc)}</div>
        <div class="guide-card-why">${esc(v.why)}</div>
      </div>`).join('')}
    </div>
    <div style="font-size:15px;font-weight:700;margin:22px 0 13px">The 12 Interventions</div>
    <div class="tbl-wrap" style="margin-bottom:22px">
      <table><thead><tr><th>Intervention</th><th>Description</th><th>Timeline</th><th>Min. Risk</th></tr></thead>
      <tbody>${Object.entries(INTERVS).map(([k,v])=>`<tr>
        <td><strong>${v.ico} ${esc(v.label)}</strong></td>
        <td style="color:var(--t2)">${esc(v.desc)}</td>
        <td><span style="color:var(--teal);font-weight:700">${v.timeline}</span></td>
        <td>${badge(v.minRisk)}</td></tr>`).join('')}
      </tbody></table>
    </div>
    <div class="card" style="margin-bottom:18px">
      <div style="font-size:15px;font-weight:700;margin-bottom:11px">Risk Score Methodology</div>
      <div style="font-size:13px;color:var(--t2);line-height:1.7">
        Each signal is scored: <strong>weight (1–10) × intensity multiplier (1.0 mild / 1.5 moderate / 2.0 severe) × time decay (2.0 within 7 days / 1.0 within 30 days / 0.4 older than 30 days)</strong>. Scores normalize to 0–100.<br><br>
        A <strong>clustering bonus of +20 points</strong> is added when 3 or more signals from different categories appear within any 7-day window — because a cluster of diverse signals is more significant than one signal repeated. Thresholds: <strong>0–25 Stable · 26–50 Watch · 51–75 Caution · 76–100 Critical</strong>.
      </div>
    </div>
    <div class="card" style="margin-bottom:18px">
      <div style="font-size:15px;font-weight:700;margin-bottom:11px">⭐ The Invisible Contributor Problem</div>
      <div style="font-size:13px;color:var(--t2);line-height:1.7">
        The most reliable caregivers — the ones who show up consistently, handle difficult clients, and never complain — are statistically the most likely to burn out quietly. Because they generate no signals, no one checks on them. This framework flags any stable caregiver who hasn't had a care touchpoint (recognition, check-in, peer support, or team event) logged in 45+ days as an <strong>Invisible Contributor</strong>. Appreciation is not a reward. It is a retention mechanism.
      </div>
    </div>
    <div class="card">
      <div style="font-size:15px;font-weight:700;margin-bottom:11px">Five Conversation Principles</div>
      <div style="display:flex;flex-direction:column;gap:12px">
        ${[
          ['Ask before assuming','Every signal is a question, not a verdict. It tells you to check in — not what is wrong.'],
          ['Care before correction','If performance is involved, lead with concern for the person first. You will get further.'],
          ['Separate check-ins from evaluations','State explicitly that this is not a performance conversation. Caregivers should not have to guess.'],
          ['Name what you noticed','Naming the signal gently gives the caregiver permission to be honest. Do not pretend you did not see it.'],
          ['Give something to move toward','Interventions work better when they offer something, not just remove something. A lighter schedule lands better with an explanation of what that space is for.']
        ].map(([t,d])=>`<div>
          <div style="font-size:13px;font-weight:700;color:var(--teal);margin-bottom:2px">${t}</div>
          <div style="font-size:13px;color:var(--t2);line-height:1.6">${d}</div>
        </div>`).join('')}
      </div>
    </div>
  </div>`;
}

// ─── MODALS ───────────────────────────────────────────────────
function openModal(html){document.getElementById('modal-inner').innerHTML=html;document.getElementById('modal-overlay').classList.remove('hidden');}
function closeModal(){document.getElementById('modal-overlay').classList.add('hidden');document.getElementById('modal-inner').innerHTML='';confirmCb=null;}

function openCgModal(id=''){
  const cg=id?D.caregivers.find(c=>c.id===id):null;
  openModal(`<h3>${cg?'Edit':'Add'} Caregiver</h3>
    <div class="field"><label>Full Name *</label><input type="text" id="cg-name" value="${cg?esc(cg.name):''}" placeholder="e.g. Marisol Delgado"></div>
    <div class="frow">
      <div class="field"><label>Role</label><input type="text" id="cg-role" value="${cg?esc(cg.role||''):''}" placeholder="e.g. Home Health Aide"></div>
      <div class="field"><label>Start Date</label><input type="date" id="cg-start" value="${cg&&cg.startDate?cg.startDate.split('T')[0]:''}"></div>
    </div>
    <div class="field"><label>Notes (optional)</label><textarea id="cg-notes" placeholder="Context useful for supporting this person">${cg?esc(cg.notes||''):''}</textarea></div>
    <div class="btn-row">
      <button class="btn btn-primary" data-action="save-cg" data-id="${id}">Save</button>
      <button class="btn btn-secondary" data-action="close-modal">Cancel</button>
    </div>`);
}

function openIntervModal(cid=''){
  const opts=D.caregivers.map(c=>`<option value="${c.id}"${c.id===cid?' selected':''}>${esc(c.name)}</option>`).join('');
  const iOpts=Object.entries(INTERVS).map(([k,v])=>`<option value="${k}">${v.ico} ${esc(v.label)}</option>`).join('');
  openModal(`<h3>Log an Intervention</h3>
    <div class="field"><label>Caregiver *</label>
      <select id="int-cid"><option value="">— Select —</option>${opts}</select></div>
    <div class="field"><label>Intervention Type *</label>
      <select id="int-type"><option value="">— Select —</option>${iOpts}</select></div>
    <div class="field"><label>Notes (optional)</label>
      <textarea id="int-notes" placeholder="What was discussed or agreed?"></textarea></div>
    <div class="btn-row">
      <button class="btn btn-primary" data-action="save-interv">Save</button>
      <button class="btn btn-secondary" data-action="close-modal">Cancel</button>
    </div>`);
}

function openCompleteModal(id){
  const iv=D.interventions.find(i=>i.id===id);if(!iv)return;
  const ivt=INTERVS[iv.type]||{};
  openModal(`<h3>Complete Intervention</h3>
    <div style="font-size:14px;font-weight:600;margin-bottom:15px">${ivt.ico||''} ${esc(ivt.label||iv.type)}</div>
    <div class="field"><label>Effectiveness (1 = didn't help · 5 = very effective)</label>
      <div class="int-row">
        ${[1,2,3,4,5].map(n=>`<div class="int-btn" data-action="sel-eff" data-val="${n}" style="font-size:19px">${'★'.repeat(n)}</div>`).join('')}
      </div>
      <input type="hidden" id="eff-val" value="0">
    </div>
    <div class="field"><label>Outcome Note (optional)</label>
      <textarea id="int-outcome" placeholder="How did the caregiver respond? What changed?"></textarea></div>
    <div class="btn-row">
      <button class="btn btn-primary" data-action="save-complete" data-id="${id}">Save Completion</button>
      <button class="btn btn-secondary" data-action="close-modal">Cancel</button>
    </div>`);
}

function openOrgModal(){
  openModal(`<h3>Organization Settings</h3>
    <div class="field"><label>Organization Name</label><input type="text" id="org-name" value="${esc(D.org.name||'')}" placeholder="Your organization name"></div>
    <div class="field"><label>Admin Contact Email</label><input type="text" id="org-email" value="${esc(D.org.contact||'')}" placeholder="admin@yourorg.com"></div>
    <div style="border-top:1px solid var(--br);margin:15px 0;padding-top:15px">
      <div style="font-size:12px;font-weight:700;color:var(--rc);margin-bottom:8px">Danger Zone</div>
      <button class="btn btn-sm btn-danger" data-action="confirm-clear">Clear All Data</button>
    </div>
    <div class="btn-row">
      <button class="btn btn-primary" data-action="save-org">Save</button>
      <button class="btn btn-secondary" data-action="close-modal">Cancel</button>
    </div>`);
}

function openConfirm(msg,cb){
  confirmCb=cb;
  openModal(`<h3>Are you sure?</h3>
    <p style="font-size:14px;color:var(--t2);margin-bottom:18px">${esc(msg)}</p>
    <div class="btn-row">
      <button class="btn btn-danger" data-action="do-confirm">Yes, delete</button>
      <button class="btn btn-secondary" data-action="close-modal">Cancel</button>
    </div>`);
}

function showConvoStarter(cid){
  const cg=D.caregivers.find(c=>c.id===cid);if(!cg)return;
  const sigs=D.signals.filter(s=>s.cid===cid)
    .sort((a,b)=>(SW[b.type]||5)*b.intensity-(SW[a.type]||5)*a.intensity);
  const topTypes=[...new Set(sigs.map(s=>s.type))].filter(t=>CONVO[t]).slice(0,2);
  if(!topTypes.length){
    openModal(`<h3>Conversation Starter</h3>
      <p style="color:var(--t4);font-size:13.5px;line-height:1.6">Log at least one signal for ${esc(cg.name)} to receive tailored conversation suggestions. The framework maps signal types to specific conversation approaches.</p>
      <div class="btn-row" style="margin-top:14px"><button class="btn btn-secondary" data-action="close-modal">Close</button></div>`);
    return;
  }
  const scripts=topTypes.flatMap(t=>(CONVO[t]||[]).map(s=>({...s,sigLabel:SIGNALS[t]?.label||t})));
  window._cs=scripts;
  openModal(`<h3>Conversation Starter — ${esc(cg.name)}</h3>
    <div style="font-size:13px;color:var(--t3);margin-bottom:14px;line-height:1.6">Based on the highest-weight recent signals. These are openers, not scripts to read verbatim. Adapt them to your own voice and relationship.</div>
    ${scripts.map((s,i)=>`<div class="convo-script">
      <div class="convo-approach">Approach ${i+1}: ${esc(s.approach)}</div>
      <div style="font-size:10.5px;color:var(--t4);margin-bottom:5px">Signal: ${esc(s.sigLabel)}</div>
      <div class="convo-text">${esc(s.script)}</div>
      <span class="convo-copy" data-action="copy-cs" data-idx="${i}">Copy to clipboard</span>
    </div>`).join('')}
    <div style="font-size:12px;color:var(--t4);margin-top:11px;padding:9px;background:var(--sur2);border-radius:var(--rs);line-height:1.55">Replace [Name] with their name. Replace [client] with the specific client if relevant. The goal is the opening — what happens after is the real conversation.</div>
    <div class="btn-row" style="margin-top:13px"><button class="btn btn-secondary" data-action="close-modal">Close</button></div>`);
}

// ─── EVENT DISPATCH ───────────────────────────────────────────
document.addEventListener('click',e=>{
  const el=e.target.closest('[data-action]');if(!el)return;
  const a=el.dataset.action;
  if(a==='nav'){navigate(el.dataset.view,el.dataset.id||'');}
  else if(a==='open-add-cg'){openCgModal();}
  else if(a==='open-edit-cg'){openCgModal(el.dataset.id);}
  else if(a==='save-cg'){saveCg(el.dataset.id);}
  else if(a==='del-cg'){openConfirm(`Remove ${D.caregivers.find(c=>c.id===el.dataset.id)?.name||'this caregiver'} and all their data?`,()=>delCg(el.dataset.id));}
  else if(a==='sel-sig'){logSigType=el.dataset.type;document.querySelectorAll('.sig-card').forEach(c=>c.classList.toggle('selected',c.dataset.type===logSigType));updateLogInfo();}
  else if(a==='sel-int'){logIntensity=parseInt(el.dataset.level);document.querySelectorAll('.int-btn[data-action="sel-int"]').forEach(b=>{b.className='int-btn'+(b.dataset.level==logIntensity?' sel-'+b.dataset.level:'');});}
  else if(a==='save-signal'){saveSignal();}
  else if(a==='del-sig'){openConfirm('Remove this signal entry?',()=>delSig(el.dataset.id));}
  else if(a==='open-add-interv'){openIntervModal(el.dataset.cid||'');}
  else if(a==='save-interv'){saveInterv();}
  else if(a==='complete-interv'){openCompleteModal(el.dataset.id);}
  else if(a==='sel-eff'){const v=parseInt(el.dataset.val);const inp=document.getElementById('eff-val');if(inp)inp.value=v;document.querySelectorAll('[data-action="sel-eff"]').forEach(b=>b.style.opacity=parseInt(b.dataset.val)<=v?'1':'0.3');}
  else if(a==='save-complete'){saveComplete(el.dataset.id);}
  else if(a==='del-interv'){openConfirm('Remove this intervention record?',()=>delInterv(el.dataset.id));}
  else if(a==='show-convo'){showConvoStarter(el.dataset.id);}
  else if(a==='copy-cs'){const s=window._cs?.[parseInt(el.dataset.idx)];if(s){navigator.clipboard?.writeText(s.script).then(()=>toast('Copied to clipboard'));el.textContent='✓ Copied!';setTimeout(()=>el.textContent='Copy to clipboard',2200);}}
  else if(a==='open-org'){openOrgModal();}
  else if(a==='save-org'){saveOrg();}
  else if(a==='confirm-clear'){openConfirm('Clear ALL data? Every caregiver, signal, and intervention record will be permanently deleted.',clearAll);}
  else if(a==='set-itab'){INT_TAB=el.dataset.tab;renderInterventions();}
  else if(a==='print-report'){printReport();}
  else if(a==='export-json'){exportJSON();}
  else if(a==='load-sample'){loadSample();}
  else if(a==='do-confirm'){if(confirmCb)confirmCb();closeModal();}
  else if(a==='close-modal'){closeModal();}
  else if(a==='close-toast'){document.getElementById('toast').classList.add('hidden');}
});

// ─── FORM SAVE HANDLERS ───────────────────────────────────────
function saveCg(eid=''){
  const name=(document.getElementById('cg-name')?.value||'').trim();
  if(!name){toast('Name is required.','error');return;}
  const role=document.getElementById('cg-role')?.value.trim()||'';
  const start=document.getElementById('cg-start')?.value||'';
  const notes=document.getElementById('cg-notes')?.value.trim()||'';
  if(eid){const cg=D.caregivers.find(c=>c.id===eid);if(cg)Object.assign(cg,{name,role,startDate:start,notes});}
  else D.caregivers.push({id:uid(),name,role,startDate:start,notes,createdAt:new Date().toISOString()});
  saveData();closeModal();toast(eid?'Caregiver updated.':'Caregiver added.');navigate(VIEW,VP);
}
function delCg(id){
  D.caregivers=D.caregivers.filter(c=>c.id!==id);
  D.signals=D.signals.filter(s=>s.cid!==id);
  D.interventions=D.interventions.filter(i=>i.cid!==id);
  saveData();toast('Caregiver removed.');navigate('team');
}
function saveSignal(){
  const cid=(document.getElementById('log-cid')?.value||logCid).trim();
  if(!cid){toast('Select a caregiver.','error');return;}
  if(!logSigType){toast('Select a signal type.','error');return;}
  if(!logIntensity){toast('Select an intensity level.','error');return;}
  const ctx=document.getElementById('log-ctx')?.value.trim()||'';
  D.signals.push({id:uid(),cid,type:logSigType,intensity:logIntensity,ctx,ts:new Date().toISOString()});
  saveData();const cg=D.caregivers.find(c=>c.id===cid);
  toast(`Signal logged for ${cg?.name||'caregiver'}.`);navigate('profile',cid);
}
function delSig(id){D.signals=D.signals.filter(s=>s.id!==id);saveData();toast('Signal removed.');navigate(VIEW,VP);}
function saveInterv(){
  const cid=document.getElementById('int-cid')?.value||'';
  const type=document.getElementById('int-type')?.value||'';
  if(!cid){toast('Select a caregiver.','error');return;}
  if(!type){toast('Select an intervention type.','error');return;}
  const notes=document.getElementById('int-notes')?.value.trim()||'';
  D.interventions.push({id:uid(),cid,type,notes,status:'active',createdAt:new Date().toISOString()});
  saveData();closeModal();toast('Intervention logged.');navigate(VIEW,VP);
}
function saveComplete(id){
  const iv=D.interventions.find(i=>i.id===id);if(!iv)return;
  const eff=parseInt(document.getElementById('eff-val')?.value||0);
  const outcome=document.getElementById('int-outcome')?.value.trim()||'';
  iv.status='completed';iv.completedAt=new Date().toISOString();
  if(eff>0)iv.effectiveness=eff;if(outcome)iv.outcome=outcome;
  saveData();closeModal();toast('Intervention marked complete.');navigate(VIEW,VP);
}
function delInterv(id){D.interventions=D.interventions.filter(i=>i.id!==id);saveData();toast('Intervention removed.');navigate(VIEW,VP);}
function saveOrg(){
  D.org.name=document.getElementById('org-name')?.value.trim()||'';
  D.org.contact=document.getElementById('org-email')?.value.trim()||'';
  saveData();closeModal();
  document.getElementById('org-display').textContent=D.org.name||'My Organization';
  toast('Settings saved.');
}
function clearAll(){D={org:{name:'',contact:''},caregivers:[],signals:[],interventions:[]};saveData();navigate('dashboard');toast('All data cleared.');}

// ─── PRINT / PDF REPORT ───────────────────────────────────────
function printReport(){
  const nd=new Date().toLocaleDateString('en-US',{month:'long',day:'numeric',year:'numeric'});
  const sc=D.caregivers.map(c=>({c,s:calcRisk(c.id),r:getRisk(calcRisk(c.id))})).sort((a,b)=>b.s-a.s);
  const rCol={stable:'#166534',watch:'#92400e',caution:'#7c2d12',critical:'#500724'};
  const total=D.caregivers.length;
  let h=`<!DOCTYPE html><html><head><meta charset="UTF-8">
  <title>Caregiver Wellbeing Report — ${esc(D.org.name||'Organization')}</title>
  <style>
    *{box-sizing:border-box;margin:0;padding:0}
    body{font-family:Georgia,'Times New Roman',serif;font-size:11pt;color:#111;line-height:1.55}
    .page{padding:48px 56px;max-width:8in;margin:0 auto}
    h2{font-size:14pt;border-bottom:1.5px solid #111;padding-bottom:7pt;margin:22pt 0 11pt}
    h3{font-size:12pt;font-weight:700;margin:13pt 0 5pt}
    .cover{page-break-after:always;text-align:center;padding-top:90px}
    .cover-lbl{font-size:9pt;letter-spacing:3px;text-transform:uppercase;color:#888;margin-bottom:11pt}
    .cover-org{font-size:26pt;font-weight:700;margin-bottom:8pt;letter-spacing:-1px}
    .cover-date{font-size:12pt;color:#555;margin-bottom:50pt}
    .cover-conf{font-size:9pt;color:#aaa;margin-top:100pt;font-style:italic;line-height:1.6}
    .sum{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin:13pt 0}
    .sum-card{border:1px solid #ddd;padding:10px;text-align:center;border-radius:4px}
    .sum-val{font-size:24pt;font-weight:800;line-height:1}
    .sum-lbl{font-size:8pt;text-transform:uppercase;letter-spacing:1px;color:#888;margin-top:3pt}
    table{width:100%;border-collapse:collapse;margin:9pt 0}
    th{text-align:left;font-size:8pt;text-transform:uppercase;letter-spacing:.4px;
       padding:7pt 10pt;background:#f5f5f5;border-bottom:1px solid #ddd}
    td{padding:7pt 10pt;border-bottom:1px solid #eee;font-size:10pt;vertical-align:top}
    .cg-hd{background:#f8f8f8;padding:9pt 13pt;border-left:4px solid #333;margin:16pt 0 8pt}
    .row{padding:4pt 0;border-bottom:1px solid #f0f0f0}
    .row:last-child{border-bottom:none}
    .footer{margin-top:44pt;font-size:8pt;color:#aaa;text-align:center;border-top:1px solid #eee;padding-top:10pt}
    @media print{body{-webkit-print-color-adjust:exact;print-color-adjust:exact}
      .page{padding:32px 40px}}
  </style></head><body><div class="page">
  <div class="cover">
    <div class="cover-lbl">Caregiver Wellbeing Assessment</div>
    <div class="cover-org">${esc(D.org.name||'Organization Report')}</div>
    <div class="cover-date">${nd}</div>
    <div style="font-size:11pt;color:#555">Behavioral Signal &amp; Intervention Framework</div>
    <div class="cover-conf">CONFIDENTIAL<br>This document contains sensitive personnel information.<br>Handle, store, and distribute with appropriate care and discretion.</div>
  </div>
  <h2>Executive Summary</h2>
  <p style="color:#555;margin-bottom:12pt">Team wellbeing assessment as of ${nd}. Risk scores are calculated from logged behavioral signals, weighted by severity and recency.</p>
  <div class="sum">
    <div class="sum-card"><div class="sum-val">${total}</div><div class="sum-lbl">Total Team</div></div>
    <div class="sum-card"><div class="sum-val" style="color:#166534">${sc.filter(s=>s.r==='stable').length}</div><div class="sum-lbl">Stable</div></div>
    <div class="sum-card"><div class="sum-val" style="color:#92400e">${sc.filter(s=>s.r==='watch').length}</div><div class="sum-lbl">Watch</div></div>
    <div class="sum-card"><div class="sum-val" style="color:#500724">${sc.filter(s=>s.r==='critical'||s.r==='caution').length}</div><div class="sum-lbl">Needs Attention</div></div>
  </div>
  <h2>Team Overview</h2>
  <table><thead><tr><th>Name</th><th>Role</th><th>Risk Level</th><th>Score</th><th>Active Interventions</th><th>Signals (30d)</th></tr></thead>
  <tbody>${sc.map(({c,s,r})=>{
    const ai=D.interventions.filter(i=>i.cid===c.id&&i.status==='active').length;
    const s30=D.signals.filter(sg=>sg.cid===c.id&&(Date.now()-new Date(sg.ts).getTime())<2592000000).length;
    return`<tr><td><strong>${esc(c.name)}</strong></td><td>${esc(c.role||'—')}</td>
    <td style="font-weight:700;color:${rCol[r]}">${rMeta(r).label}</td>
    <td>${s}/100</td><td>${ai||'—'}</td><td>${s30||'—'}</td></tr>`;}).join('')}
  </tbody></table>
  <h2>Individual Profiles</h2>
  ${sc.map(({c,s,r})=>{
    const sigs=D.signals.filter(sg=>sg.cid===c.id).sort((a,b)=>new Date(b.ts)-new Date(a.ts));
    const intv=D.interventions.filter(i=>i.cid===c.id);
    const recs=suggestIntervs(c.id);
    return`<div style="page-break-inside:avoid;margin-top:18pt">
      <div class="cg-hd" style="border-left-color:${rCol[r]}">
        <strong>${esc(c.name)}</strong> — ${esc(c.role||'Caregiver')}<br>
        <span style="font-weight:700;color:${rCol[r]}">${rMeta(r).label} — ${s}/100</span>
        ${c.startDate?` &nbsp;|&nbsp; Started: ${fmtDate(c.startDate)}`:''}
      </div>
      <h3>Recent Signals</h3>
      ${sigs.length?sigs.slice(0,20).map(sg=>`<div class="row">
        <strong>${esc(SIGNALS[sg.type]?.label||sg.type)}</strong> — Intensity ${'●'.repeat(sg.intensity)}${'○'.repeat(3-sg.intensity)} — ${fmtDate(sg.ts)}
        ${sg.ctx?`<div style="color:#666;font-size:9pt;margin-top:2pt;font-style:italic">${esc(sg.ctx)}</div>`:''}</div>`).join('')
        :`<p style="color:#999;font-size:10pt">No signals recorded.</p>`}
      <h3>Interventions</h3>
      ${intv.length?intv.map(i=>`<div class="row">
        <strong>${esc(INTERVS[i.type]?.label||i.type)}</strong> — ${i.status} — ${fmtDate(i.createdAt)}
        ${i.effectiveness?` — Effectiveness: ${'★'.repeat(i.effectiveness)}${'☆'.repeat(5-i.effectiveness)}`:''}
        ${i.outcome?`<div style="color:#666;font-size:9pt;font-style:italic;margin-top:2pt">${esc(i.outcome)}</div>`:''}</div>`).join('')
        :`<p style="color:#999;font-size:10pt">No interventions logged.</p>`}
      ${recs.length?`<h3>Recommended Next Actions</h3>
        <ul style="padding-left:16pt;margin-top:5pt">${recs.map(rv=>`<li style="margin-bottom:3pt;font-size:10pt">
          <strong>${esc(rv.label)}</strong> (${rv.timeline}) — ${esc(rv.desc)}</li>`).join('')}</ul>`:''}
    </div>`;}).join('')}
  <div class="footer">
    Caregiver Retention OS — Behavioral Signal &amp; Intervention Framework<br>
    ${nd} &nbsp;|&nbsp; ${esc(D.org.name||'Organization')} &nbsp;|&nbsp; For internal supervisory use only. Not for distribution.
  </div>
  </div>
  <script>window.onload=function(){setTimeout(function(){window.print();},500);};<\/script>
  </body></html>`;
  const w=window.open('','_blank');
  if(w){w.document.write(h);w.document.close();}
  else toast('Enable pop-ups in your browser to open the print report.','error');
}

// ─── JSON EXPORT ──────────────────────────────────────────────
function exportJSON(){
  const payload=JSON.stringify({
    _meta:{exported:new Date().toISOString(),version:'cros-v2',framework:'Behavioral Signal & Intervention Framework'},
    ...D
  },null,2);
  const blob=new Blob([payload],{type:'application/json'});
  const a=document.createElement('a');
  a.href=URL.createObjectURL(blob);
  a.download=`cros-backup-${new Date().toISOString().split('T')[0]}.json`;
  document.body.appendChild(a);a.click();document.body.removeChild(a);
  URL.revokeObjectURL(a.href);
  toast('JSON backup downloaded successfully.');
}

// ─── TOAST ────────────────────────────────────────────────────
let _tt;
function toast(msg,type='success'){
  const el=document.getElementById('toast');
  document.getElementById('toast-msg').textContent=msg;
  el.className=type;el.classList.remove('hidden');
  clearTimeout(_tt);_tt=setTimeout(()=>el.classList.add('hidden'),3600);
}

// ─── SAMPLE DATA ──────────────────────────────────────────────
function loadSample(){
  if(D.caregivers.length&&!confirm('Add sample data alongside your existing team? Your current data will not be removed.'))return;
  const ts=d=>new Date(Date.now()-d*86400000).toISOString();
  const ids=[uid(),uid(),uid(),uid(),uid(),uid()];
  const cgS=[
    {id:ids[0],name:'Marisol Delgado',role:'Home Health Aide',startDate:'2019-03-14',notes:'6-year veteran. Exceptional client relationships. Currently showing high burnout risk.',createdAt:ts(2190)},
    {id:ids[1],name:'Grace Okafor',role:'Certified Nursing Assistant',startDate:'2022-11-01',notes:'Highly consistent. Specialises in long-stay dementia clients. Signals building.',createdAt:ts(500)},
    {id:ids[2],name:'Thomas Reyes',role:'Registered Nurse',startDate:'2021-06-22',notes:'Was in crisis last month. Recovering well after intervention. Monitor for relapse.',createdAt:ts(900)},
    {id:ids[3],name:'Priya Nair',role:'Personal Care Aide',startDate:'2023-09-10',notes:'Early-stage watch. Low-level signals in last two weeks.',createdAt:ts(300)},
    {id:ids[4],name:'Amara Osei',role:'Home Health Aide',startDate:'2022-02-28',notes:'Highly reliable. Rarely requests changes. No signals in 60 days. Invisible contributor risk.',createdAt:ts(430)},
    {id:ids[5],name:'Jordan Blake',role:'Home Health Aide',startDate:ts(18).split('T')[0],notes:'New hire, still onboarding. No signal history yet.',createdAt:ts(18)}
  ];
  const sgS=[
    // Marisol — escalating to critical
    {id:uid(),cid:ids[0],type:'after-hours',intensity:1,ctx:'Message at 2:47am asking about a client medication schedule.',ts:ts(21)},
    {id:uid(),cid:ids[0],type:'shift-swaps',intensity:1,ctx:'Swapped one weekend shift with a colleague.',ts:ts(18)},
    {id:uid(),cid:ids[0],type:'tone-shift',intensity:2,ctx:'Messages noticeably shorter this week. One-word replies to scheduling messages.',ts:ts(12)},
    {id:uid(),cid:ids[0],type:'after-hours',intensity:2,ctx:'Two 3am messages this week — one about a client, one asking about time-off policy.',ts:ts(9)},
    {id:uid(),cid:ids[0],type:'shift-swaps',intensity:3,ctx:'Dropped 3 shifts in 5 days. When asked, said "I need a break but I can\'t afford one."',ts:ts(5)},
    {id:uid(),cid:ids[0],type:'explicit-stress',intensity:3,ctx:'Told the shift coordinator she is "running on nothing" and "doesn\'t know how much longer she can do this."',ts:ts(2)},
    // Grace — caution level building
    {id:uid(),cid:ids[1],type:'doc-decline',intensity:2,ctx:'Visit notes shorter and delayed by 2-3 days compared to her usual same-day pattern.',ts:ts(20)},
    {id:uid(),cid:ids[1],type:'availability-drop',intensity:2,ctx:'Declined 2 extra shifts she would normally accept without question.',ts:ts(12)},
    {id:uid(),cid:ids[1],type:'withdrawal',intensity:2,ctx:'Skipped the weekly team huddle. Said she was tired. Third consecutive no-show.',ts:ts(6)},
    {id:uid(),cid:ids[1],type:'physical-fatigue',intensity:2,ctx:'Mentioned to a colleague that she hasn\'t slept properly in two weeks.',ts:ts(3)},
    // Thomas — past crisis, recovering (older signals, interventions complete)
    {id:uid(),cid:ids[2],type:'explicit-stress',intensity:3,ctx:'Broke down during handover. Said he couldn\'t keep up and felt invisible.',ts:ts(30)},
    {id:uid(),cid:ids[2],type:'sick-days',intensity:2,ctx:'Three sick days across two weeks.',ts:ts(25)},
    {id:uid(),cid:ids[2],type:'tone-shift',intensity:2,ctx:'',ts:ts(28)},
    // Priya — early watch
    {id:uid(),cid:ids[3],type:'shift-swaps',intensity:1,ctx:'',ts:ts(14)},
    {id:uid(),cid:ids[3],type:'slow-response',intensity:1,ctx:'Taking 4-6 hours to respond to scheduling messages, up from under 1 hour.',ts:ts(7)},
    {id:uid(),cid:ids[3],type:'after-hours',intensity:1,ctx:'Late-night question about next week\'s scheduling.',ts:ts(3)},
    // Amara — stable, invisible contributor (one old signal, no care touchpoints)
    {id:uid(),cid:ids[4],type:'shift-swaps',intensity:1,ctx:'One swap, 7 weeks ago.',ts:ts(52)}
  ];
  const ivS=[
    // Thomas — full intervention cycle, successful
    {id:uid(),cid:ids[2],type:'supervisor-checkin',notes:'Long 1:1. He talked through the pressure. Agreed to lighten schedule for 3 weeks.',status:'completed',effectiveness:4,outcome:'Noticeably more open after the conversation. Said he felt heard for the first time.',createdAt:ts(29),completedAt:ts(28)},
    {id:uid(),cid:ids[2],type:'schedule-adjust',notes:'Removed all back-to-back weekend doubles for 3 weeks. Assigned lighter client load.',status:'completed',effectiveness:5,outcome:'Visible improvement in energy within the first week. Documentation quality recovered fully.',createdAt:ts(27),completedAt:ts(7)},
    {id:uid(),cid:ids[2],type:'recognition',notes:'Acknowledged his work with the long-stay dementia client cohort at the team meeting.',status:'completed',effectiveness:3,outcome:'',createdAt:ts(10),completedAt:ts(10)},
    // Marisol — intervention just scheduled, not yet completed
    {id:uid(),cid:ids[0],type:'supervisor-checkin',notes:'Scheduled for tomorrow morning. Plan to use the after-hours conversation approach.',status:'active',createdAt:ts(1)},
    // Priya — early intervention
    {id:uid(),cid:ids[3],type:'flex-shifts',notes:'Offered alternative shift pattern — proposed Tues/Thurs mornings instead of current mixed schedule.',status:'active',createdAt:ts(5)}
  ];
  D.caregivers=[...D.caregivers,...cgS.filter(s=>!D.caregivers.find(c=>c.id===s.id))];
  D.signals=[...D.signals,...sgS];
  D.interventions=[...D.interventions,...ivS];
  if(!D.org.name)D.org.name='Care First Home Health';
  saveData();
  document.getElementById('org-display').textContent=D.org.name;
  toast('Sample team loaded — 6 caregivers with realistic signal patterns and intervention histories.');
  navigate('dashboard');
}

// ─── INIT ─────────────────────────────────────────────────────
function init(){
  loadData();
  if(D.org.name)document.getElementById('org-display').textContent=D.org.name;
  navigate('dashboard');
}
init();
</script>
</body>
</html>
