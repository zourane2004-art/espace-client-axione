<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Axione — Espace Client Tourmignies</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#0d1117;--bg2:#161b22;--bg3:#1c2330;--bg4:#21262d;
  --border:rgba(255,255,255,0.07);--border-l:rgba(255,255,255,0.13);
  --text:#e6edf3;--muted:#7d8590;--dim:#484f58;
  --green:#26c281;--green-bg:rgba(38,194,129,0.1);--green-br:rgba(38,194,129,0.3);
  --red:#f85149;--red-bg:rgba(248,81,73,0.1);--red-br:rgba(248,81,73,0.3);
  --orange:#f0883e;--orange-bg:rgba(240,136,62,0.1);--orange-br:rgba(240,136,62,0.3);
  --yellow:#e3b341;--yellow-bg:rgba(227,179,65,0.1);--yellow-br:rgba(227,179,65,0.3);
  --gray:#8b949e;--gray-bg:rgba(139,148,158,0.1);--gray-br:rgba(139,148,158,0.3);
  --blue:#388bfd;--blue-bg:rgba(56,139,253,0.1);--blue-br:rgba(56,139,253,0.3);
  --purple:#a371f7;--purple-bg:rgba(163,113,247,0.1);--purple-br:rgba(163,113,247,0.3);
  --teal:#2dd4bf;--teal-bg:rgba(45,212,191,0.1);--teal-br:rgba(45,212,191,0.3);
  --r:8px;--rl:12px;
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow:hidden;}

/* TOPBAR */
.topbar{height:52px;background:var(--bg2);border-bottom:1px solid var(--border);display:flex;align-items:center;padding:0 14px;gap:16px;position:sticky;top:0;z-index:100;}
.logo{display:flex;align-items:center;gap:8px;font-weight:700;font-size:13px;letter-spacing:-.02em;text-decoration:none;color:var(--text);}
.logo-ic{width:26px;height:26px;background:linear-gradient(135deg,#1f6feb,var(--purple));border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:12px;}
.logo-sub{font-size:9.5px;font-weight:400;color:var(--muted);}
.nav{display:flex;gap:1px;margin-left:4px;}
.nav a{padding:4px 10px;border-radius:6px;font-size:12px;color:var(--muted);text-decoration:none;cursor:pointer;transition:all .15s;}
.nav a:hover{background:var(--bg4);color:var(--text);}
.nav a.active{background:var(--bg4);color:var(--text);font-weight:500;}
.topbar-right{margin-left:auto;display:flex;align-items:center;gap:8px;}
.sync-pill{font-family:'DM Mono',monospace;font-size:9.5px;color:var(--dim);background:var(--bg4);padding:3px 8px;border-radius:20px;border:1px solid var(--border);}
.sync-dot{display:inline-block;width:5px;height:5px;border-radius:50%;background:var(--green);margin-right:4px;animation:blink 2s infinite;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}
.top-btn{display:flex;align-items:center;gap:5px;padding:4px 11px;border-radius:6px;font-size:11.5px;font-weight:500;cursor:pointer;transition:all .2s;border:1px solid;}
.top-btn:hover{transform:translateY(-1px);}
.tb-purple{background:var(--purple-bg);border-color:var(--purple-br);color:var(--purple);}
.tb-orange{background:var(--orange-bg);border-color:var(--orange-br);color:var(--orange);}
.avatar{width:27px;height:27px;background:linear-gradient(135deg,#1f6feb,var(--blue));border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:10.5px;font-weight:600;cursor:pointer;}

/* PAGES */
.page{display:none;height:calc(100vh - 52px);overflow-y:auto;}
.page.active{display:flex;}

/* ─── DASHBOARD PAGE ─── */
.dash-page{flex-direction:column;padding:24px;gap:20px;overflow-y:auto;}
.dash-title{font-size:20px;font-weight:700;letter-spacing:-.02em;}
.dash-sub{font-size:12px;color:var(--muted);margin-top:2px;}
.kpi-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;}
.kpi-card{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);padding:16px 18px;}
.kpi-label{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.06em;color:var(--muted);margin-bottom:8px;}
.kpi-val{font-size:28px;font-weight:700;font-family:'DM Mono',monospace;letter-spacing:-.03em;}
.kpi-sub{font-size:11px;color:var(--muted);margin-top:4px;}
.kpi-bar{height:4px;background:var(--bg4);border-radius:3px;margin-top:8px;overflow:hidden;}
.kpi-bar-fill{height:100%;border-radius:3px;}
.dash-grid2{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.dash-card{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);padding:16px 18px;}
.dash-card-title{font-size:12px;font-weight:600;margin-bottom:12px;display:flex;align-items:center;gap:6px;}
.activity-item{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px solid var(--border);font-size:12px;}
.activity-item:last-child{border-bottom:none;}
.act-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;}
.act-text{flex:1;color:var(--text);}
.act-time{font-size:10.5px;color:var(--dim);font-family:'DM Mono',monospace;}
.gauge-row{display:flex;align-items:center;gap:10px;margin-bottom:8px;}
.gauge-label{font-size:11.5px;flex:1;}
.gauge-bar{flex:2;height:6px;background:var(--bg4);border-radius:3px;overflow:hidden;}
.gauge-fill{height:100%;border-radius:3px;}
.gauge-val{font-size:11px;font-family:'DM Mono',monospace;color:var(--muted);min-width:36px;text-align:right;}

/* ─── OBSERVABILITE PAGE ─── */
.obs-page{flex-direction:row;}
.sidebar{background:var(--bg2);border-right:1px solid var(--border);padding:12px 9px;overflow-y:auto;display:flex;flex-direction:column;gap:16px;width:222px;flex-shrink:0;}
.sec-title{font-size:9px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--dim);padding:0 7px;margin-bottom:3px;}
.filter-chip{display:flex;align-items:center;gap:7px;padding:6px 8px;border-radius:var(--r);cursor:pointer;transition:all .15s;border:1px solid transparent;width:100%;}
.filter-chip:hover,.sub-chip:hover{background:var(--bg4);}
.filter-chip.active{background:var(--bg3);border-color:var(--border-l);}
.f-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;}
.f-label{font-size:11.5px;flex:1;color:var(--text);}
.f-cnt{font-family:'DM Mono',monospace;font-size:10px;color:var(--muted);background:var(--bg4);padding:1px 5px;border-radius:8px;min-width:18px;text-align:center;}
.hs-parent{display:flex;align-items:center;gap:7px;padding:6px 8px;border-radius:var(--r);cursor:pointer;transition:all .15s;border:1px solid transparent;width:100%;}
.hs-parent:hover{background:var(--bg4);}
.hs-parent.active{background:var(--red-bg);border-color:var(--red-br);}
.hs-parent.active .f-label{color:var(--red);font-weight:600;}
.hs-cnt{font-family:'DM Mono',monospace;font-size:10px;background:var(--bg4);padding:1px 5px;border-radius:8px;min-width:18px;text-align:center;color:var(--muted);}
.sub-chips{display:flex;flex-direction:column;gap:1px;margin-left:12px;padding-left:9px;border-left:1px solid var(--border);margin-top:2px;}
.sub-chip{display:flex;align-items:center;gap:7px;padding:4px 7px;border-radius:6px;cursor:pointer;transition:all .15s;border:1px solid transparent;width:100%;}
.sub-chip.active{background:var(--bg3);border-color:var(--border-l);}
.sub-chip .f-label{font-size:11px;}
.hs-cam-list{margin-left:12px;padding-left:9px;border-left:1px solid var(--border);margin-top:4px;display:flex;flex-direction:column;gap:2px;}
.hs-cam-item{display:flex;align-items:center;gap:6px;padding:5px 7px;border-radius:6px;cursor:pointer;transition:all .15s;border:1px solid transparent;width:100%;}
.hs-cam-item:hover{background:var(--bg4);}
.hs-cam-item.active{background:var(--bg3);border-color:var(--border-l);}
.hs-cam-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;}
.hs-cam-info{flex:1;min-width:0;}
.hs-cam-id{font-family:'DM Mono',monospace;font-size:9px;color:var(--dim);}
.hs-cam-name{font-size:10.5px;font-weight:500;color:var(--text);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.hs-cam-badge{font-size:9px;padding:1px 5px;border-radius:8px;border:1px solid;font-weight:500;white-space:nowrap;flex-shrink:0;}
.sla-block{background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);padding:10px 11px;}
.sla-val{font-size:22px;font-weight:700;font-family:'DM Mono',monospace;letter-spacing:-.03em;margin:3px 0;}
.sla-bar{height:4px;background:var(--bg4);border-radius:3px;overflow:hidden;margin:5px 0 3px;}
.sla-fill{height:100%;border-radius:3px;}
.sb-btn{width:100%;padding:7px 11px;border-radius:var(--r);border:1px solid;font-size:11.5px;font-weight:500;font-family:'DM Sans',sans-serif;cursor:pointer;display:flex;align-items:center;gap:7px;transition:all .2s;}
.sb-btn:hover{transform:translateY(-1px);}
.btn-purple{background:var(--purple-bg);border-color:var(--purple-br);color:var(--purple);}
.btn-orange{background:var(--orange-bg);border-color:var(--orange-br);color:var(--orange);}
.btn-blue{background:var(--blue-bg);border-color:var(--blue-br);color:var(--blue);}

/* MAP */
.map-area{position:relative;background:#0a0f16;overflow:hidden;flex:1;}
.stats-bar{position:absolute;top:10px;left:10px;right:10px;display:flex;gap:5px;z-index:20;flex-wrap:wrap;}
.stat-pill{display:flex;align-items:center;gap:5px;padding:5px 10px;background:rgba(22,27,34,0.93);border:1px solid var(--border-l);border-radius:20px;font-size:10.5px;font-weight:500;backdrop-filter:blur(8px);cursor:pointer;transition:all .2s;white-space:nowrap;}
.stat-pill:hover{transform:translateY(-1px);}
.sp-dot{width:6px;height:6px;border-radius:50%;}
.sp-cnt{font-family:'DM Mono',monospace;font-size:11px;}
.hs-pill{border-color:var(--red-br);background:rgba(248,81,73,0.07);}
.map-svg-wrap{width:100%;height:100%;}
#mapSvg{width:100%;height:100%;}
.map-tooltip{position:absolute;pointer-events:none;background:var(--bg2);border:1px solid var(--border-l);border-radius:7px;padding:8px 12px;font-size:11px;z-index:50;display:none;min-width:170px;box-shadow:0 8px 24px rgba(0,0,0,.4);}
.map-controls{position:absolute;bottom:14px;left:14px;display:flex;flex-direction:column;gap:3px;z-index:20;}
.map-btn{width:30px;height:30px;background:var(--bg2);border:1px solid var(--border-l);border-radius:6px;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:13px;color:var(--text);}
.map-legend{position:absolute;bottom:14px;right:14px;background:rgba(22,27,34,0.93);border:1px solid var(--border-l);border-radius:var(--r);padding:9px 12px;backdrop-filter:blur(8px);}
.leg-title{font-size:8.5px;font-weight:600;letter-spacing:.06em;text-transform:uppercase;color:var(--dim);margin-bottom:6px;}
.leg-sec{font-size:8px;font-weight:600;color:var(--dim);margin:6px 0 3px;padding-top:5px;border-top:1px solid var(--border);}
.leg-item{display:flex;align-items:center;gap:6px;margin-bottom:3px;}
.leg-dot{width:7px;height:7px;border-radius:50%;}

/* DETAIL PANEL */
.detail-panel{background:var(--bg2);border-left:1px solid var(--border);display:flex;flex-direction:column;overflow:hidden;width:350px;flex-shrink:0;}
.empty-panel{display:flex;flex-direction:column;align-items:center;justify-content:center;height:100%;gap:9px;color:var(--dim);padding:24px;text-align:center;}
.ep-icon{font-size:32px;opacity:.3;}
.ep-title{font-size:12.5px;font-weight:500;color:var(--muted);}
.ep-desc{font-size:11px;line-height:1.6;}
.ep-support{margin-top:14px;display:flex;flex-direction:column;gap:6px;width:100%;}
.panel-header{padding:12px 14px;border-bottom:1px solid var(--border);}
.ph-id{font-family:'DM Mono',monospace;font-size:9.5px;color:var(--dim);margin-bottom:2px;}
.ph-name{font-size:14px;font-weight:700;letter-spacing:-.02em;margin-bottom:2px;}
.ph-addr{font-size:11px;color:var(--muted);margin-bottom:6px;}
.badges-row{display:flex;align-items:center;flex-wrap:wrap;gap:4px;}
.state-badge{display:inline-flex;align-items:center;gap:4px;padding:2px 8px;border-radius:20px;font-size:10px;font-weight:600;border:1px solid;}
.panel-body{flex:1;overflow-y:auto;padding:12px 14px;display:flex;flex-direction:column;gap:13px;}
.panel-sec{font-size:8.5px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--dim);margin-bottom:6px;}
.info-grid{display:grid;grid-template-columns:1fr 1fr;gap:5px;}
.info-cell{background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);padding:8px 10px;}
.cell-lbl{font-size:9px;color:var(--dim);margin-bottom:2px;text-transform:uppercase;letter-spacing:.04em;}
.cell-val{font-size:12px;font-weight:500;}
.cell-val.mono{font-family:'DM Mono',monospace;font-size:11px;}
.topo-chain{background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);padding:12px 14px;overflow-x:auto;}
.topo-row{display:flex;align-items:center;gap:0;min-width:max-content;}
.topo-node{display:flex;flex-direction:column;align-items:center;gap:4px;}
.topo-icon{width:36px;height:36px;border-radius:var(--r);display:flex;align-items:center;justify-content:center;font-size:15px;border:2px solid;position:relative;}
.topo-icon .topo-status{position:absolute;top:-4px;right:-4px;width:10px;height:10px;border-radius:50%;border:2px solid var(--bg3);}
.topo-label{font-size:9px;font-weight:600;color:var(--text);text-align:center;max-width:65px;}
.topo-sub{font-size:8px;color:var(--muted);text-align:center;max-width:65px;}
.topo-arrow{display:flex;flex-direction:column;align-items:center;padding:0 5px;padding-bottom:14px;}
.topo-line{width:20px;height:2px;margin-top:17px;}
.topo-line-label{font-size:7.5px;color:var(--dim);white-space:nowrap;margin-top:2px;}
.diag-block{background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);overflow:hidden;}
.diag-row{display:flex;align-items:center;justify-content:space-between;padding:6px 11px;border-bottom:1px solid var(--border);font-size:11px;}
.diag-row:last-child{border-bottom:none;}
.dk{color:var(--muted);}
.dv{font-family:'DM Mono',monospace;font-size:10.5px;}
.dv.ok{color:var(--green);}
.dv.ko{color:var(--red);}
.dv.warn{color:var(--yellow);}
.resp-banner{border-radius:var(--r);padding:10px 12px;border:1px solid;display:flex;gap:8px;}
.resp-icon{font-size:15px;flex-shrink:0;margin-top:1px;}
.resp-title{font-size:11px;font-weight:600;margin-bottom:2px;}
.resp-desc{font-size:10.5px;color:var(--muted);line-height:1.5;}
.timeline{display:flex;flex-direction:column;}
.tl-item{display:flex;gap:8px;padding-bottom:11px;position:relative;}
.tl-item::before{content:'';position:absolute;left:12px;top:20px;bottom:0;width:1px;background:var(--border);}
.tl-item:last-child::before{display:none;}
.tl-dot{width:25px;height:25px;border-radius:50%;border:2px solid;display:flex;align-items:center;justify-content:center;font-size:10px;flex-shrink:0;z-index:1;}
.tl-c{flex:1;padding-top:2px;}
.tl-ev{font-size:11.5px;font-weight:500;margin-bottom:1px;}
.tl-dt{font-size:10px;color:var(--muted);}
.tl-src{display:inline-flex;align-items:center;gap:3px;font-size:9px;background:var(--bg4);border:1px solid var(--border);border-radius:8px;padding:1px 5px;margin-top:2px;}
.cta-area{display:flex;flex-direction:column;gap:5px;}
.cta-btn{width:100%;padding:8px 12px;border-radius:var(--r);border:1px solid;font-size:12px;font-weight:500;font-family:'DM Sans',sans-serif;cursor:pointer;display:flex;align-items:center;gap:6px;transition:all .2s;}
.cta-btn:hover{transform:translateY(-1px);}
.cta-primary{background:linear-gradient(135deg,#1f6feb,var(--blue));border-color:var(--blue);color:#fff;}
.cta-primary:hover{box-shadow:0 4px 14px rgba(56,139,253,.35);}
.cta-warn{background:var(--yellow-bg);border-color:var(--yellow-br);color:var(--yellow);}
.cta-ghost{background:var(--bg3);border-color:var(--border-l);color:var(--muted);}
.cta-ghost:hover{color:var(--text);background:var(--bg4);}
.cta-support{background:var(--purple-bg);border-color:var(--purple-br);color:var(--purple);}
.cta-ticket{background:var(--orange-bg);border-color:var(--orange-br);color:var(--orange);}

/* ─── INCIDENTS PAGE ─── */
.full-page{flex-direction:column;padding:24px;gap:16px;overflow-y:auto;}
.page-header{display:flex;align-items:center;justify-content:space-between;}
.page-title{font-size:18px;font-weight:700;letter-spacing:-.02em;}
.page-sub{font-size:11.5px;color:var(--muted);margin-top:2px;}
.page-action-btn{padding:7px 14px;border-radius:var(--r);border:1px solid;font-size:12px;font-weight:500;cursor:pointer;display:flex;align-items:center;gap:6px;transition:all .2s;font-family:'DM Sans',sans-serif;}
.inc-table{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);overflow:hidden;}
.inc-thead{display:grid;grid-template-columns:90px 1fr 120px 110px 100px 90px;padding:10px 16px;background:var(--bg3);border-bottom:1px solid var(--border);font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.06em;color:var(--dim);}
.inc-row{display:grid;grid-template-columns:90px 1fr 120px 110px 100px 90px;padding:11px 16px;border-bottom:1px solid var(--border);font-size:12px;align-items:center;cursor:pointer;transition:background .15s;}
.inc-row:last-child{border-bottom:none;}
.inc-row:hover{background:var(--bg3);}
.inc-id{font-family:'DM Mono',monospace;font-size:10.5px;color:var(--blue);}
.inc-badge{display:inline-flex;align-items:center;gap:4px;padding:2px 8px;border-radius:10px;font-size:10px;font-weight:600;border:1px solid;}
.inc-pri{display:inline-flex;align-items:center;gap:4px;padding:2px 8px;border-radius:10px;font-size:10px;font-weight:500;}

/* ─── MAINTENANCE PAGE ─── */
.maint-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.maint-card{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);padding:16px 18px;}
.maint-card-title{font-size:12px;font-weight:600;margin-bottom:12px;display:flex;align-items:center;gap:6px;}
.maint-item{display:flex;align-items:center;gap:10px;padding:9px 0;border-bottom:1px solid var(--border);font-size:12px;}
.maint-item:last-child{border-bottom:none;}
.maint-icon{width:32px;height:32px;border-radius:var(--r);display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;}
.maint-info{flex:1;}
.maint-name{font-size:12px;font-weight:500;}
.maint-date{font-size:10.5px;color:var(--muted);}
.maint-status{font-size:10px;font-weight:600;padding:2px 8px;border-radius:8px;border:1px solid;}

/* ─── CONTRATS PAGE ─── */
.contrat-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;}
.contrat-card{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);padding:18px;}
.contrat-header{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:14px;}
.contrat-type{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.06em;color:var(--muted);}
.contrat-name{font-size:14px;font-weight:700;margin-top:3px;}
.contrat-badge{font-size:10px;font-weight:600;padding:3px 9px;border-radius:10px;border:1px solid;}
.contrat-detail{display:flex;flex-direction:column;gap:8px;}
.contrat-row{display:flex;justify-content:space-between;font-size:12px;padding-bottom:8px;border-bottom:1px solid var(--border);}
.contrat-row:last-child{border-bottom:none;padding-bottom:0;}
.contrat-key{color:var(--muted);}
.contrat-val{font-weight:500;font-family:'DM Mono',monospace;font-size:11px;}
.progress-block{margin-top:12px;}
.prog-label{display:flex;justify-content:space-between;font-size:10.5px;margin-bottom:5px;}
.prog-bar{height:5px;background:var(--bg4);border-radius:3px;overflow:hidden;}
.prog-fill{height:100%;border-radius:3px;}

/* MODAL */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.65);z-index:200;display:none;align-items:center;justify-content:center;backdrop-filter:blur(4px);}
.modal-overlay.open{display:flex;}
.modal{background:var(--bg2);border:1px solid var(--border-l);border-radius:var(--rl);width:500px;max-width:96vw;max-height:90vh;overflow:hidden;display:flex;flex-direction:column;animation:slideUp .2s ease;}
@keyframes slideUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
.modal-header{padding:15px 18px 12px;border-bottom:1px solid var(--border);display:flex;align-items:flex-start;justify-content:space-between;}
.modal-title{font-size:14.5px;font-weight:700;letter-spacing:-.02em;margin-bottom:2px;}
.modal-sub{font-size:11px;color:var(--muted);}
.modal-close{width:26px;height:26px;border-radius:6px;background:var(--bg4);border:1px solid var(--border);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:12px;color:var(--muted);flex-shrink:0;}
.modal-close:hover{color:var(--text);}
.modal-body{padding:15px 18px;flex:1;overflow-y:auto;display:flex;flex-direction:column;gap:12px;}
.form-row{display:flex;flex-direction:column;gap:5px;}
.form-row label{font-size:10px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;}
.form-input,.form-select,.form-textarea{background:var(--bg3);border:1px solid var(--border-l);border-radius:var(--r);padding:8px 11px;font-family:'DM Sans',sans-serif;font-size:12.5px;color:var(--text);outline:none;transition:border-color .15s;width:100%;}
.form-input:focus,.form-select:focus,.form-textarea:focus{border-color:var(--blue);}
.form-textarea{resize:vertical;min-height:72px;line-height:1.5;}
.hint{font-size:9.5px;color:var(--dim);}
.modal-footer{padding:11px 18px;border-top:1px solid var(--border);display:flex;gap:7px;justify-content:flex-end;}
.modal-btn{padding:7px 14px;border-radius:var(--r);border:1px solid;font-size:12px;font-weight:500;font-family:'DM Sans',sans-serif;cursor:pointer;transition:all .2s;}
.modal-cancel{background:var(--bg3);border-color:var(--border-l);color:var(--muted);}
.modal-submit{background:linear-gradient(135deg,#1f6feb,var(--blue));border-color:var(--blue);color:#fff;}
.modal-submit:hover{box-shadow:0 4px 12px rgba(56,139,253,.35);}
.success-state{text-align:center;padding:18px 0;}
.ticket-ref{font-family:'DM Mono',monospace;font-size:14px;background:var(--bg3);border:1px solid var(--green-br);color:var(--green);padding:5px 13px;border-radius:6px;display:inline-block;margin-top:8px;}

::-webkit-scrollbar{width:3px;}
::-webkit-scrollbar-thumb{background:var(--bg4);border-radius:3px;}
.hidden{display:none!important;}
</style>
</head>
<body>

<div class="topbar">
  <a class="logo" href="https://zourane2004-art.github.io/axione-tourmignies1" target="_blank">
    <div class="logo-ic">📡</div>
    <div>
      <div>Axione</div>
      <div class="logo-sub">Espace client vidéoprotection</div>
    </div>
  </a>
  <nav class="nav">
    <a onclick="showPage('dashboard')">Tableau de bord</a>
    <a onclick="showPage('observabilite')" class="active">Observabilité</a>
    <a onclick="showPage('incidents')">Incidents</a>
    <a onclick="showPage('maintenance')">Maintenance</a>
    <a onclick="showPage('contrats')">Contrats</a>
  </nav>
  <div class="topbar-right">
    <div class="sync-pill"><span class="sync-dot"></span>Sync <span id="syncTime">2 min</span></div>
    <div class="top-btn tb-purple" onclick="openModal('support')">🎧 Support</div>
    <div class="top-btn tb-orange" onclick="openModal('ticket',null)">🎫 Ticket</div>
    <div class="avatar">TC</div>
  </div>
</div>

<!-- ═══════════════════════════════════════════
     PAGE 1 — TABLEAU DE BORD
═══════════════════════════════════════════ -->
<div class="page dash-page" id="page-dashboard">
  <div>
    <div class="dash-title">Tableau de bord</div>
    <div class="dash-sub">Commune de Tourmignies (59551) · Vidéoprotection · Mis à jour il y a 2 min</div>
  </div>
  <div class="kpi-grid">
    <div class="kpi-card">
      <div class="kpi-label">Total caméras</div>
      <div class="kpi-val" style="color:var(--text)">15</div>
      <div class="kpi-sub">Parc vidéoprotection</div>
      <div class="kpi-bar"><div class="kpi-bar-fill" style="width:100%;background:var(--blue)"></div></div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Opérationnelles</div>
      <div class="kpi-val" style="color:var(--green)">8</div>
      <div class="kpi-sub">53.3% du parc actif</div>
      <div class="kpi-bar"><div class="kpi-bar-fill" style="width:53%;background:var(--green)"></div></div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Hors service</div>
      <div class="kpi-val" style="color:var(--red)">7</div>
      <div class="kpi-sub">SLA : 53.3% / objectif 95%</div>
      <div class="kpi-bar"><div class="kpi-bar-fill" style="width:53%;background:var(--red)"></div></div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Tickets ouverts</div>
      <div class="kpi-val" style="color:var(--orange)">6</div>
      <div class="kpi-sub">Dont 1 en attente client</div>
      <div class="kpi-bar"><div class="kpi-bar-fill" style="width:40%;background:var(--orange)"></div></div>
    </div>
  </div>
  <div class="dash-grid2">
    <div class="dash-card">
      <div class="dash-card-title">📊 Répartition des états</div>
      <div class="gauge-row"><span class="gauge-label">✅ Opérationnelle</span><div class="gauge-bar"><div class="gauge-fill" style="width:53%;background:var(--green)"></div></div><span class="gauge-val" style="color:var(--green)">8</span></div>
      <div class="gauge-row"><span class="gauge-label">🔴 HS · sans action</span><div class="gauge-bar"><div class="gauge-fill" style="width:13%;background:var(--red)"></div></div><span class="gauge-val" style="color:var(--red)">2</span></div>
      <div class="gauge-row"><span class="gauge-label">🎫 Ticket créé</span><div class="gauge-bar"><div class="gauge-fill" style="width:7%;background:var(--teal)"></div></div><span class="gauge-val" style="color:var(--teal)">1</span></div>
      <div class="gauge-row"><span class="gauge-label">🔧 Remplacement</span><div class="gauge-bar"><div class="gauge-fill" style="width:7%;background:var(--orange)"></div></div><span class="gauge-val" style="color:var(--orange)">1</span></div>
      <div class="gauge-row"><span class="gauge-label">📋 Devis attente</span><div class="gauge-bar"><div class="gauge-fill" style="width:7%;background:var(--yellow)"></div></div><span class="gauge-val" style="color:var(--yellow)">1</span></div>
      <div class="gauge-row"><span class="gauge-label">⚡ Panne élec.</span><div class="gauge-bar"><div class="gauge-fill" style="width:7%;background:var(--gray)"></div></div><span class="gauge-val" style="color:var(--gray)">1</span></div>
      <div class="gauge-row"><span class="gauge-label">↺ Reboot</span><div class="gauge-bar"><div class="gauge-fill" style="width:7%;background:var(--blue)"></div></div><span class="gauge-val" style="color:var(--blue)">1</span></div>
    </div>
    <div class="dash-card">
      <div class="dash-card-title">🕐 Activité récente</div>
      <div class="activity-item"><div class="act-dot" style="background:var(--red)"></div><div class="act-text">CAM-TRG-14 · Perte de signal (Sortie Sud-Est)</div><div class="act-time">10h05</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--blue)"></div><div class="act-text">CAM-TRG-12 · Reboot distant initié (Zone Est)</div><div class="act-time">11h52</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--teal)"></div><div class="act-text">CAM-TRG-10 · Ticket #TRG-2847 créé</div><div class="act-time">02h50</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--gray)"></div><div class="act-text">CAM-TRG-13 · Panne électrique identifiée</div><div class="act-time">07h10</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--red)"></div><div class="act-text">CAM-TRG-06 · Hors service (Salle des fêtes)</div><div class="act-time">08h22</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--yellow)"></div><div class="act-text">CAM-TRG-04 · Devis #DV-TRG-26 transmis</div><div class="act-time">Hier</div></div>
    </div>
  </div>
  <div class="dash-grid2">
    <div class="dash-card">
      <div class="dash-card-title">📦 État des coffrets</div>
      <div class="activity-item"><div class="act-dot" style="background:var(--green)"></div><div class="act-text"><strong>COF-A</strong> · Coffret Mairie · 5 caméras</div><div class="act-time" style="color:var(--green)">OK</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--red)"></div><div class="act-text"><strong>COF-B</strong> · Salle des fêtes · 2 caméras HS</div><div class="act-time" style="color:var(--red)">⚠</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--orange)"></div><div class="act-text"><strong>COF-C</strong> · Zone Nord · 1 en remplacement</div><div class="act-time" style="color:var(--orange)">⚠</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--blue)"></div><div class="act-text"><strong>COF-D</strong> · Zone Est · 1 reboot en cours</div><div class="act-time" style="color:var(--blue)">↺</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--green)"></div><div class="act-text"><strong>COF-E</strong> · Hameau Nord · OK</div><div class="act-time" style="color:var(--green)">OK</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--red)"></div><div class="act-text"><strong>COF-F</strong> · Sortie Sud-Est · HS</div><div class="act-time" style="color:var(--red)">⚠</div></div>
    </div>
    <div class="dash-card">
      <div class="dash-card-title">🎯 Actions prioritaires</div>
      <div class="activity-item"><div class="act-dot" style="background:var(--yellow)"></div><div class="act-text" style="color:var(--yellow)"><strong>URGENT</strong> · Valider devis #DV-TRG-26 (CAM-TRG-04)</div><div class="act-time">3j</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--red)"></div><div class="act-text"><strong>SLA</strong> · 2 caméras HS +24h sans résolution</div><div class="act-time">!</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--gray)"></div><div class="act-text"><strong>ÉLEC</strong> · Vérifier coffret COF-B (alimentation)</div><div class="act-time">18h</div></div>
      <div class="activity-item"><div class="act-dot" style="background:var(--blue)"></div><div class="act-text"><strong>REBOOT</strong> · Vérifier résultat CAM-TRG-12</div><div class="act-time">30min</div></div>
      <div style="margin-top:10px;display:flex;gap:7px;">
        <button class="cta-btn cta-support" style="flex:1;" onclick="openModal('support')">🎧 Contacter le support</button>
        <button class="cta-btn cta-ticket" style="flex:1;" onclick="openModal('ticket',null)">🎫 Créer un ticket</button>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════
     PAGE 2 — OBSERVABILITÉ
═══════════════════════════════════════════ -->
<div class="page obs-page active" id="page-observabilite">
  <aside class="sidebar">
    <div>
      <div class="sec-title">État des caméras</div>
      <div style="display:flex;flex-direction:column;gap:2px;">
        <div class="filter-chip active" data-filter="all" onclick="setFilter('all',this)"><div class="f-dot" style="background:var(--muted)"></div><span class="f-label">Toutes les caméras</span><span class="f-cnt" id="cnt-all">0</span></div>
        <div class="filter-chip" data-filter="operational" onclick="setFilter('operational',this)"><div class="f-dot" style="background:var(--green)"></div><span class="f-label">Opérationnelle</span><span class="f-cnt" id="cnt-op">0</span></div>
        <div class="hs-parent" data-filter="hors-service" onclick="setFilter('hors-service',this)"><div class="f-dot" style="background:var(--red)"></div><span class="f-label">Hors service</span><span class="hs-cnt" id="cnt-hs-total">0</span></div>
        <div class="sub-chips">
          <div class="sub-chip" data-filter="hs" onclick="setFilter('hs',this)"><div class="f-dot" style="background:var(--red)"></div><span class="f-label">↳ HS · sans action</span><span class="f-cnt" id="cnt-hs">0</span></div>
          <div class="sub-chip" data-filter="ticket" onclick="setFilter('ticket',this)"><div class="f-dot" style="background:var(--teal)"></div><span class="f-label">↳ Ticket créé</span><span class="f-cnt" id="cnt-ticket">0</span></div>
          <div class="sub-chip" data-filter="replacing" onclick="setFilter('replacing',this)"><div class="f-dot" style="background:var(--orange)"></div><span class="f-label">↳ En remplacement</span><span class="f-cnt" id="cnt-rep">0</span></div>
          <div class="sub-chip" data-filter="devis" onclick="setFilter('devis',this)"><div class="f-dot" style="background:var(--yellow)"></div><span class="f-label">↳ Devis en attente</span><span class="f-cnt" id="cnt-dev">0</span></div>
          <div class="sub-chip" data-filter="elec" onclick="setFilter('elec',this)"><div class="f-dot" style="background:var(--gray)"></div><span class="f-label">↳ Panne électrique</span><span class="f-cnt" id="cnt-elec">0</span></div>
          <div class="sub-chip" data-filter="reboot" onclick="setFilter('reboot',this)"><div class="f-dot" style="background:var(--blue)"></div><span class="f-label">↳ Reboot en cours</span><span class="f-cnt" id="cnt-reb">0</span></div>
        </div>
        <div style="margin-top:6px;">
          <div style="font-size:8.5px;font-weight:600;letter-spacing:.06em;text-transform:uppercase;color:var(--dim);padding:0 7px;margin-bottom:3px;">Caméras concernées</div>
          <div class="hs-cam-list" id="hsCamList"></div>
        </div>
      </div>
    </div>
    <div>
      <div class="sec-title">Santé du parc</div>
      <div class="sla-block">
        <div style="font-size:10px;color:var(--muted);">Taux de disponibilité</div>
        <div class="sla-val" id="slaVal">—</div>
        <div class="sla-bar"><div class="sla-fill" id="slaFill" style="width:0%"></div></div>
        <div style="font-size:9px;color:var(--dim);">Objectif SLA : 95% · Mairie Tourmignies</div>
      </div>
    </div>
    <div>
      <div class="sec-title">Alertes</div>
      <div id="alertsBlock" style="display:flex;flex-direction:column;gap:4px;"></div>
    </div>
    <div>
      <div class="sec-title">Assistance</div>
      <div style="display:flex;flex-direction:column;gap:4px;">
        <button class="sb-btn btn-purple" onclick="openModal('support')">🎧 Contacter le support</button>
        <button class="sb-btn btn-orange" onclick="openModal('ticket',null)">🎫 Créer un ticket</button>
        <button class="sb-btn btn-blue" onclick="openModal('suivi')">📋 Suivi des tickets</button>
      </div>
    </div>
  </aside>

  <div class="map-area">
    <div class="stats-bar" id="statsBar"></div>
    <div class="map-svg-wrap">
      <svg id="mapSvg" viewBox="0 0 900 620" xmlns="http://www.w3.org/2000/svg">
        <rect width="900" height="620" fill="#0a0f16"/>
        <defs><pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse"><path d="M 40 0 L 0 0 0 40" fill="none" stroke="rgba(56,139,253,0.04)" stroke-width="1"/></pattern></defs>
        <rect width="900" height="620" fill="url(#grid)"/>
        <polygon points="20,20 280,20 280,130 20,130" fill="rgba(38,194,129,0.04)" stroke="rgba(38,194,129,0.07)" stroke-width="1"/>
        <polygon points="620,20 880,20 880,200 620,200" fill="rgba(38,194,129,0.04)" stroke="rgba(38,194,129,0.07)" stroke-width="1"/>
        <polygon points="20,460 350,460 350,600 20,600" fill="rgba(38,194,129,0.04)" stroke="rgba(38,194,129,0.07)" stroke-width="1"/>
        <polygon points="600,420 880,420 880,600 600,600" fill="rgba(38,194,129,0.04)" stroke="rgba(38,194,129,0.07)" stroke-width="1"/>
        <rect x="0" y="270" width="900" height="22" fill="rgba(255,255,255,0.055)" rx="2"/>
        <text x="440" y="285" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.22)" font-family="DM Sans">Rue du Général de Gaulle</text>
        <rect x="390" y="0" width="16" height="620" fill="rgba(255,255,255,0.045)" rx="2"/>
        <text x="384" y="90" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.2)" font-family="DM Sans" transform="rotate(-90,384,90)">Rue de la Mairie</text>
        <line x1="80" y1="0" x2="320" y2="260" stroke="rgba(255,255,255,0.04)" stroke-width="14"/>
        <text x="130" y="105" font-size="8" fill="rgba(255,255,255,0.16)" font-family="DM Sans" transform="rotate(52,130,105)">Rue d'Attiches</text>
        <line x1="820" y1="0" x2="560" y2="270" stroke="rgba(255,255,255,0.04)" stroke-width="12"/>
        <text x="740" y="90" font-size="8" fill="rgba(255,255,255,0.16)" font-family="DM Sans" transform="rotate(-32,740,90)">Rue de Mérignies</text>
        <rect x="0" y="420" width="900" height="14" fill="rgba(255,255,255,0.03)" rx="2"/>
        <text x="180" y="431" font-size="8" fill="rgba(255,255,255,0.14)" font-family="DM Sans">Chemin de la Croix</text>
        <rect x="560" y="180" width="13" height="440" fill="rgba(255,255,255,0.035)" rx="2"/>
        <text x="554" y="340" text-anchor="middle" font-size="8" fill="rgba(255,255,255,0.14)" font-family="DM Sans" transform="rotate(-90,554,340)">Rue du Moulin</text>
        <rect x="200" y="130" width="11" height="270" fill="rgba(255,255,255,0.03)" rx="2"/>
        <text x="194" y="250" text-anchor="middle" font-size="8" fill="rgba(255,255,255,0.12)" font-family="DM Sans" transform="rotate(-90,194,250)">Allée des Tilleuls</text>
        <rect x="415" y="220" width="55" height="42" fill="rgba(56,139,253,0.12)" stroke="rgba(56,139,253,0.4)" stroke-width="1.5" rx="3"/>
        <text x="442" y="237" text-anchor="middle" font-size="8" fill="rgba(56,139,253,0.85)" font-family="DM Sans">🏛</text>
        <text x="442" y="249" text-anchor="middle" font-size="7.5" fill="rgba(56,139,253,0.7)" font-family="DM Sans">Mairie</text>
        <rect x="290" y="190" width="52" height="36" fill="rgba(163,113,247,0.1)" stroke="rgba(163,113,247,0.35)" stroke-width="1.5" rx="3"/>
        <text x="316" y="205" text-anchor="middle" font-size="8" fill="rgba(163,113,247,0.8)" font-family="DM Sans">🏫</text>
        <text x="316" y="217" text-anchor="middle" font-size="7.5" fill="rgba(163,113,247,0.65)" font-family="DM Sans">École</text>
        <rect x="490" y="180" width="48" height="40" fill="rgba(227,179,65,0.08)" stroke="rgba(227,179,65,0.28)" stroke-width="1.5" rx="3"/>
        <text x="514" y="196" text-anchor="middle" font-size="8" fill="rgba(227,179,65,0.8)" font-family="DM Sans">⛪</text>
        <text x="514" y="208" text-anchor="middle" font-size="7.5" fill="rgba(227,179,65,0.6)" font-family="DM Sans">Église</text>
        <rect x="600" y="308" width="62" height="38" fill="rgba(38,194,129,0.07)" stroke="rgba(38,194,129,0.22)" stroke-width="1.5" rx="3"/>
        <text x="631" y="323" text-anchor="middle" font-size="8" fill="rgba(38,194,129,0.7)" font-family="DM Sans">🏟</text>
        <text x="631" y="335" text-anchor="middle" font-size="7.5" fill="rgba(38,194,129,0.55)" font-family="DM Sans">Salle des fêtes</text>
        <rect x="100" y="468" width="80" height="50" fill="rgba(38,194,129,0.06)" stroke="rgba(38,194,129,0.18)" stroke-width="1" rx="3"/>
        <text x="140" y="489" text-anchor="middle" font-size="8" fill="rgba(38,194,129,0.6)" font-family="DM Sans">⚽</text>
        <text x="140" y="501" text-anchor="middle" font-size="7.5" fill="rgba(38,194,129,0.45)" font-family="DM Sans">Terrain sport</text>
        <rect x="700" y="76" width="56" height="38" fill="rgba(240,136,62,0.07)" stroke="rgba(240,136,62,0.18)" stroke-width="1" rx="3"/>
        <text x="728" y="93" text-anchor="middle" font-size="8" fill="rgba(240,136,62,0.6)" font-family="DM Sans">🌾</text>
        <text x="728" y="105" text-anchor="middle" font-size="7.5" fill="rgba(240,136,62,0.45)" font-family="DM Sans">Hameau Nord</text>
        <text x="140" y="56" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.05)" font-family="DM Sans" font-weight="600" letter-spacing="2">ZONE NORD-OUEST</text>
        <text x="720" y="232" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.05)" font-family="DM Sans" font-weight="600" letter-spacing="2">ZONE EST</text>
        <text x="185" y="535" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.05)" font-family="DM Sans" font-weight="600" letter-spacing="2">ZONE SUD</text>
        <text x="700" y="525" text-anchor="middle" font-size="9" fill="rgba(255,255,255,0.05)" font-family="DM Sans" font-weight="600" letter-spacing="2">ZONE SUD-EST</text>
        <g id="pinsLayer"></g>
      </svg>
    </div>
    <div class="map-tooltip" id="tooltip"></div>
    <div class="map-controls">
      <div class="map-btn">＋</div><div class="map-btn">－</div><div class="map-btn">⊕</div>
    </div>
    <div class="map-legend">
      <div class="leg-title">Légende</div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--green)"></div><span style="font-size:9.5px;">Opérationnelle</span></div>
      <div class="leg-sec">Hors service →</div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--red)"></div><span style="font-size:9.5px;">HS · sans action</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--teal)"></div><span style="font-size:9.5px;">Ticket créé</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--orange)"></div><span style="font-size:9.5px;">En remplacement</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--yellow)"></div><span style="font-size:9.5px;">Devis en attente</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--gray)"></div><span style="font-size:9.5px;">Panne électrique</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:var(--blue)"></div><span style="font-size:9.5px;">Reboot en cours</span></div>
    </div>
  </div>

  <aside class="detail-panel">
    <div class="empty-panel" id="emptyState">
      <div class="ep-icon">📷</div>
      <div class="ep-title">Sélectionnez une caméra</div>
      <div class="ep-desc">Cliquez sur un point de la carte ou sur une caméra dans la liste pour consulter son état, sa topologie réseau et les actions disponibles.</div>
      <div class="ep-support">
        <button class="cta-btn cta-support" onclick="openModal('support')">🎧 Contacter le support</button>
        <button class="cta-btn cta-ticket" onclick="openModal('ticket',null)">🎫 Créer un ticket</button>
      </div>
    </div>
    <div id="cameraDetail" class="hidden" style="display:flex;flex-direction:column;height:100%;"></div>
  </aside>
</div>

<!-- ═══════════════════════════════════════════
     PAGE 3 — INCIDENTS
═══════════════════════════════════════════ -->
<div class="page full-page" id="page-incidents">
  <div class="page-header">
    <div><div class="page-title">Incidents</div><div class="page-sub">6 tickets actifs · Commune de Tourmignies (59551)</div></div>
    <button class="page-action-btn cta-ticket" onclick="openModal('ticket',null)">🎫 Créer un ticket</button>
  </div>
  <div class="inc-table">
    <div class="inc-thead"><div>Référence</div><div>Description</div><div>Caméra</div><div>Coffret/Switch</div><div>Statut</div><div>Priorité</div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2849</div><div>Hors service · Salle des fêtes</div><div style="font-size:11px;">CAM-TRG-06</div><div style="font-size:10px;color:var(--muted);">COF-B · SW-03</div><div><span class="inc-badge" style="color:var(--orange);border-color:var(--orange-br);background:var(--orange-bg);">En cours</span></div><div><span class="inc-pri" style="color:var(--red);background:var(--red-bg);">🔴 Haute</span></div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2851</div><div>Hors service · Sortie Sud-Est</div><div style="font-size:11px;">CAM-TRG-14</div><div style="font-size:10px;color:var(--muted);">COF-F · SW-07</div><div><span class="inc-badge" style="color:var(--orange);border-color:var(--orange-br);background:var(--orange-bg);">En cours</span></div><div><span class="inc-pri" style="color:var(--red);background:var(--red-bg);">🔴 Haute</span></div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2847</div><div>Ticket créé · Carrefour Attiches</div><div style="font-size:11px;">CAM-TRG-10</div><div style="font-size:10px;color:var(--muted);">COF-A · SW-02</div><div><span class="inc-badge" style="color:var(--teal);border-color:var(--teal-br);background:var(--teal-bg);">Ticket créé</span></div><div><span class="inc-pri" style="color:var(--orange);background:var(--orange-bg);">🟠 Normale</span></div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2845</div><div>Reboot en cours · Zone Est</div><div style="font-size:11px;">CAM-TRG-12</div><div style="font-size:10px;color:var(--muted);">COF-D · SW-05</div><div><span class="inc-badge" style="color:var(--blue);border-color:var(--blue-br);background:var(--blue-bg);">Reboot</span></div><div><span class="inc-pri" style="color:var(--orange);background:var(--orange-bg);">🟠 Normale</span></div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2840</div><div>Devis en attente · Passage école</div><div style="font-size:11px;">CAM-TRG-04</div><div style="font-size:10px;color:var(--muted);">COF-A · SW-02</div><div><span class="inc-badge" style="color:var(--yellow);border-color:var(--yellow-br);background:var(--yellow-bg);">Attente client</span></div><div><span class="inc-pri" style="color:var(--yellow);background:var(--yellow-bg);">⚠ Action req.</span></div></div>
    <div class="inc-row"><div class="inc-id">#TRG-2838</div><div>Remplacement planifié · Terrain sport</div><div style="font-size:11px;">CAM-TRG-08</div><div style="font-size:10px;color:var(--muted);">COF-C · SW-04</div><div><span class="inc-badge" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">Planifié</span></div><div><span class="inc-pri" style="color:var(--green);background:var(--green-bg);">✅ Normal</span></div></div>
  </div>
  <div style="display:flex;gap:10px;margin-top:4px;">
    <button class="cta-btn cta-support" style="width:auto;padding:8px 16px;" onclick="openModal('support')">🎧 Contacter le support Axione</button>
    <button class="cta-btn cta-ghost" style="width:auto;padding:8px 16px;" onclick="openModal('suivi')">📋 Suivi détaillé des tickets</button>
  </div>
</div>

<!-- ═══════════════════════════════════════════
     PAGE 4 — MAINTENANCE
═══════════════════════════════════════════ -->
<div class="page full-page" id="page-maintenance">
  <div class="page-header">
    <div><div class="page-title">Maintenance</div><div class="page-sub">Planning et historique des interventions · Tourmignies (59551)</div></div>
    <button class="page-action-btn btn-blue" style="background:var(--blue-bg);border-color:var(--blue-br);color:var(--blue);" onclick="openModal('ticket',null)">📅 Planifier une intervention</button>
  </div>
  <div class="maint-grid">
    <div class="maint-card">
      <div class="maint-card-title">🔧 Interventions à venir</div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--orange-bg);border:1px solid var(--orange-br);">🔧</div>
        <div class="maint-info"><div class="maint-name">Remplacement CAM-TRG-08</div><div class="maint-date">23 fév. 2026 · 09h00 · Julien M.</div></div>
        <span class="maint-status" style="color:var(--orange);border-color:var(--orange-br);background:var(--orange-bg);">Planifié</span>
      </div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--blue-bg);border:1px solid var(--blue-br);">🔌</div>
        <div class="maint-info"><div class="maint-name">Vérif. coffret COF-B</div><div class="maint-date">24 fév. 2026 · 14h00 · Marc D.</div></div>
        <span class="maint-status" style="color:var(--blue);border-color:var(--blue-br);background:var(--blue-bg);">Confirmé</span>
      </div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--yellow-bg);border:1px solid var(--yellow-br);">📋</div>
        <div class="maint-info"><div class="maint-name">Remplacement CAM-TRG-04 (si devis OK)</div><div class="maint-date">À planifier après accord client</div></div>
        <span class="maint-status" style="color:var(--yellow);border-color:var(--yellow-br);background:var(--yellow-bg);">En attente</span>
      </div>
    </div>
    <div class="maint-card">
      <div class="maint-card-title">✅ Interventions récentes</div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--green-bg);border:1px solid var(--green-br);">✓</div>
        <div class="maint-info"><div class="maint-name">Maintenance préventive CAM-TRG-01</div><div class="maint-date">14 jan. 2026 · Technicien Axione</div></div>
        <span class="maint-status" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">Terminé</span>
      </div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--green-bg);border:1px solid var(--green-br);">✓</div>
        <div class="maint-info"><div class="maint-name">Remplacement objectif CAM-TRG-03</div><div class="maint-date">8 fév. 2026 · Thomas R.</div></div>
        <span class="maint-status" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">Terminé</span>
      </div>
      <div class="maint-item">
        <div class="maint-icon" style="background:var(--green-bg);border:1px solid var(--green-br);">✓</div>
        <div class="maint-info"><div class="maint-name">Mise en service CAM-TRG-02</div><div class="maint-date">5 mar. 2025 · Équipe Axione</div></div>
        <span class="maint-status" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">Terminé</span>
      </div>
    </div>
    <div class="maint-card">
      <div class="maint-card-title">📊 Statistiques maintenance</div>
      <div class="gauge-row"><span class="gauge-label">Caméras vérifiées (12 mois)</span><div class="gauge-bar"><div class="gauge-fill" style="width:80%;background:var(--blue)"></div></div><span class="gauge-val">12/15</span></div>
      <div class="gauge-row"><span class="gauge-label">Interventions réussies</span><div class="gauge-bar"><div class="gauge-fill" style="width:92%;background:var(--green)"></div></div><span class="gauge-val">92%</span></div>
      <div class="gauge-row"><span class="gauge-label">Délai moyen résolution</span><div class="gauge-bar"><div class="gauge-fill" style="width:60%;background:var(--orange)"></div></div><span class="gauge-val">6h</span></div>
      <div class="gauge-row"><span class="gauge-label">Durée moy. intervention</span><div class="gauge-bar"><div class="gauge-fill" style="width:45%;background:var(--purple)"></div></div><span class="gauge-val">2h30</span></div>
    </div>
    <div class="maint-card">
      <div class="maint-card-title">🗓 Prochaine visite préventive</div>
      <div style="background:var(--blue-bg);border:1px solid var(--blue-br);border-radius:var(--r);padding:14px;text-align:center;margin-bottom:12px;">
        <div style="font-size:28px;font-weight:700;font-family:'DM Mono',monospace;color:var(--blue);">15 mars</div>
        <div style="font-size:12px;color:var(--muted);margin-top:4px;">2026 · Visite semestrielle planifiée</div>
        <div style="font-size:11px;color:var(--dim);margin-top:3px;">Technicien Axione · 15 caméras + 6 coffrets</div>
      </div>
      <button class="cta-btn cta-support" onclick="openModal('support')">🎧 Contacter le support</button>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════
     PAGE 5 — CONTRATS
═══════════════════════════════════════════ -->
<div class="page full-page" id="page-contrats">
  <div class="page-header">
    <div><div class="page-title">Contrats</div><div class="page-sub">Gestion des contrats de maintenance et de supervision · Tourmignies</div></div>
  </div>
  <div class="contrat-grid">
    <div class="contrat-card">
      <div class="contrat-header">
        <div><div class="contrat-type">Maintenance</div><div class="contrat-name">Contrat MCO Vidéo</div></div>
        <span class="contrat-badge" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">✓ Actif</span>
      </div>
      <div class="contrat-detail">
        <div class="contrat-row"><span class="contrat-key">N° contrat</span><span class="contrat-val">AX-59551-MCO</span></div>
        <div class="contrat-row"><span class="contrat-key">Début</span><span class="contrat-val">01/01/2024</span></div>
        <div class="contrat-row"><span class="contrat-key">Échéance</span><span class="contrat-val">31/12/2026</span></div>
        <div class="contrat-row"><span class="contrat-key">Caméras couvertes</span><span class="contrat-val">15 caméras</span></div>
        <div class="contrat-row"><span class="contrat-key">Coffrets couverts</span><span class="contrat-val">6 coffrets</span></div>
      </div>
      <div class="progress-block">
        <div class="prog-label"><span style="font-size:10.5px;color:var(--muted);">Avancement contrat</span><span style="font-size:10.5px;color:var(--green);">63%</span></div>
        <div class="prog-bar"><div class="prog-fill" style="width:63%;background:var(--green)"></div></div>
      </div>
    </div>
    <div class="contrat-card">
      <div class="contrat-header">
        <div><div class="contrat-type">Supervision</div><div class="contrat-name">Contrat Télésupervision</div></div>
        <span class="contrat-badge" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">✓ Actif</span>
      </div>
      <div class="contrat-detail">
        <div class="contrat-row"><span class="contrat-key">N° contrat</span><span class="contrat-val">AX-59551-SUP</span></div>
        <div class="contrat-row"><span class="contrat-key">Début</span><span class="contrat-val">01/01/2024</span></div>
        <div class="contrat-row"><span class="contrat-key">Échéance</span><span class="contrat-val">31/12/2026</span></div>
        <div class="contrat-row"><span class="contrat-key">SLA garanti</span><span class="contrat-val">95% / mois</span></div>
        <div class="contrat-row"><span class="contrat-key">Astreinte</span><span class="contrat-val">24h/24 · 7j/7</span></div>
      </div>
      <div class="progress-block">
        <div class="prog-label"><span style="font-size:10.5px;color:var(--muted);">SLA actuel</span><span style="font-size:10.5px;color:var(--orange);">53.3%</span></div>
        <div class="prog-bar"><div class="prog-fill" style="width:53%;background:var(--orange)"></div></div>
      </div>
    </div>
    <div class="contrat-card">
      <div class="contrat-header">
        <div><div class="contrat-type">Réseau</div><div class="contrat-name">Contrat Connectivité</div></div>
        <span class="contrat-badge" style="color:var(--green);border-color:var(--green-br);background:var(--green-bg);">✓ Actif</span>
      </div>
      <div class="contrat-detail">
        <div class="contrat-row"><span class="contrat-key">N° contrat</span><span class="contrat-val">AX-59551-NET</span></div>
        <div class="contrat-row"><span class="contrat-key">Type liaison</span><span class="contrat-val">Fibre + 4G</span></div>
        <div class="contrat-row"><span class="contrat-key">Bande passante</span><span class="contrat-val">100 Mbps</span></div>
        <div class="contrat-row"><span class="contrat-key">Coffrets fibre</span><span class="contrat-val">COF-A/B/C/D</span></div>
        <div class="contrat-row"><span class="contrat-key">Coffrets 4G</span><span class="contrat-val">COF-E</span></div>
      </div>
      <div class="progress-block">
        <div class="prog-label"><span style="font-size:10.5px;color:var(--muted);">Disponibilité réseau</span><span style="font-size:10.5px;color:var(--green);">98.2%</span></div>
        <div class="prog-bar"><div class="prog-fill" style="width:98%;background:var(--green)"></div></div>
      </div>
    </div>
  </div>
  <div style="display:flex;gap:10px;margin-top:4px;">
    <button class="cta-btn cta-support" style="width:auto;padding:8px 16px;" onclick="openModal('support')">🎧 Contacter le support Axione</button>
    <button class="cta-btn cta-ghost" style="width:auto;padding:8px 16px;">📄 Télécharger les contrats PDF</button>
  </div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modalOverlay" onclick="if(event.target===this)closeModal()">
  <div class="modal">
    <div class="modal-header" id="modalHeader"></div>
    <div class="modal-body" id="modalBody"></div>
    <div class="modal-footer" id="modalFooter"></div>
  </div>
</div>

<script>
const HS_STATES=["hs","ticket","replacing","devis","elec","reboot"];
const SC={
  operational:{label:"Opérationnelle",color:"#26c281",bg:"rgba(38,194,129,0.1)",br:"rgba(38,194,129,0.3)",icon:"✓",emoji:"✅",resp:"Aucune action requise."},
  hs:         {label:"HS · sans action",color:"#f85149",bg:"rgba(248,81,73,0.1)",br:"rgba(248,81,73,0.3)",icon:"✕",emoji:"🔴",resp:"Responsabilité Axione — diagnostic en cours sous 4h."},
  ticket:     {label:"Ticket créé",color:"#2dd4bf",bg:"rgba(45,212,191,0.1)",br:"rgba(45,212,191,0.3)",icon:"🎫",emoji:"🎫",resp:"Ticket d'incident créé, en attente de prise en charge."},
  replacing:  {label:"En remplacement",color:"#f0883e",bg:"rgba(240,136,62,0.1)",br:"rgba(240,136,62,0.3)",icon:"🔧",emoji:"🔧",resp:"Intervention planifiée — technicien Axione en déplacement."},
  devis:      {label:"Devis en attente",color:"#e3b341",bg:"rgba(227,179,65,0.1)",br:"rgba(227,179,65,0.3)",icon:"!",emoji:"📋",resp:"Action client requise : votre accord est nécessaire."},
  elec:       {label:"Panne électrique",color:"#8b949e",bg:"rgba(139,148,158,0.1)",br:"rgba(139,148,158,0.3)",icon:"⚡",emoji:"⚡",resp:"Responsabilité client — vérifiez l'alimentation électrique."},
  reboot:     {label:"Reboot en cours",color:"#388bfd",bg:"rgba(56,139,253,0.1)",br:"rgba(56,139,253,0.3)",icon:"↺",emoji:"🔄",resp:"Axione intervient à distance."},
};
const COFFRETS={
  "COF-A":{name:"Coffret Mairie",addr:"3 r. Gén. de Gaulle",link:"Fibre GPON",status:"ok"},
  "COF-B":{name:"Coffret Salle des fêtes",addr:"Rue du Moulin",link:"Fibre GPON",status:"ok"},
  "COF-C":{name:"Coffret Zone Nord",addr:"Allée des Tilleuls",link:"Ethernet",status:"ok"},
  "COF-D":{name:"Coffret Zone Est",addr:"Rue du Moulin Sud",link:"Fibre GPON",status:"ok"},
  "COF-E":{name:"Coffret Hameau Nord",addr:"Rue de Mérignies",link:"4G LTE",status:"ok"},
  "COF-F":{name:"Coffret Sud-Est",addr:"Route de Pont-à-Marcq",link:"Ethernet",status:"ok"},
};
const SWITCHES={
  "SW-01":{name:"Switch PoE 8P",coffret:"COF-A",brand:"Cisco SG350",status:"ok"},
  "SW-02":{name:"Switch PoE 8P",coffret:"COF-A",brand:"Cisco SG350",status:"ok"},
  "SW-03":{name:"Switch PoE 16P",coffret:"COF-B",brand:"HP Aruba 1930",status:"ok"},
  "SW-04":{name:"Switch PoE 8P",coffret:"COF-C",brand:"Cisco SG350",status:"ok"},
  "SW-05":{name:"Switch PoE 8P",coffret:"COF-D",brand:"Netgear GS308P",status:"ok"},
  "SW-06":{name:"Switch PoE 4P",coffret:"COF-E",brand:"TP-Link TL-SG",status:"ok"},
  "SW-07":{name:"Switch PoE 8P",coffret:"COF-F",brand:"Cisco SG350",status:"ok"},
};
const HC={operational:{c:"#26c281",i:"✓"},hs:{c:"#f85149",i:"✗"},ticket:{c:"#2dd4bf",i:"🎫"},replacing:{c:"#f0883e",i:"🔧"},devis:{c:"#e3b341",i:"!"},elec:{c:"#8b949e",i:"⚡"},reboot:{c:"#388bfd",i:"↺"},système:{c:"#388bfd",i:"⚙"}};

const cameras=[
  {id:"CAM-TRG-01",name:"Mairie — Entrée principale",addr:"3 Rue du Général de Gaulle",state:"operational",x:398,y:238,sinceH:null,model:"Axis P3245-V",ip:"10.12.1.1",ping:"11ms",snmp:"OK",uptime:"99.7%",tech:null,coffret:"COF-A",sw:"SW-01",port:"Port 1",poe:"15.4W",history:[{ev:"Maintenance préventive",date:"14 jan. 2026",type:"operational",src:"technicien"}]},
  {id:"CAM-TRG-02",name:"Mairie — Parking arrière",addr:"Pl. de la Mairie, côté Est",state:"operational",x:470,y:245,sinceH:null,model:"Hikvision DS-2CD3T",ip:"10.12.1.2",ping:"9ms",snmp:"OK",uptime:"100%",tech:null,coffret:"COF-A",sw:"SW-01",port:"Port 2",poe:"12.7W",history:[{ev:"Mise en service",date:"5 mar. 2025",type:"operational",src:"technicien"}]},
  {id:"CAM-TRG-03",name:"Carrefour r. du Moulin",addr:"Intersection r. du Moulin / r. de Gaulle",state:"operational",x:395,y:275,sinceH:null,model:"Bosch FLEXIDOME 7000",ip:"10.12.1.3",ping:"14ms",snmp:"OK",uptime:"98.5%",tech:null,coffret:"COF-A",sw:"SW-02",port:"Port 1",poe:"13.1W",history:[]},
  {id:"CAM-TRG-04",name:"Passage piéton école",addr:"Devant École primaire, r. de la Mairie",state:"devis",x:315,y:225,sinceH:null,model:"Axis P3225 (à remplacer)",ip:"—",ping:"TIMEOUT",snmp:"FAIL",uptime:"—",tech:"Devis #DV-TRG-26 transmis le 19 fév.",coffret:"COF-A",sw:"SW-02",port:"Port 2",poe:"0W",history:[{ev:"Caméra HS confirmée",date:"17 fév. 2026",type:"hs",src:"technicien"},{ev:"Devis transmis au client",date:"19 fév. 2026",type:"devis",src:"système"}]},
  {id:"CAM-TRG-05",name:"Église Saint-Martin",addr:"Parvis église",state:"operational",x:510,y:205,sinceH:null,model:"Dahua IPC-HDW5",ip:"10.12.1.5",ping:"8ms",snmp:"OK",uptime:"99.1%",tech:null,coffret:"COF-A",sw:"SW-02",port:"Port 3",poe:"11.4W",history:[]},
  {id:"CAM-TRG-06",name:"Salle des fêtes",addr:"Rue du Moulin, angle",state:"hs",x:602,y:318,sinceH:28,model:"Hikvision DS-2CD2T",ip:"10.12.1.6",ping:"TIMEOUT",snmp:"FAIL",uptime:"—",tech:"Diagnostic Axione en cours",coffret:"COF-B",sw:"SW-03",port:"Port 1",poe:"0W",history:[{ev:"Perte de flux vidéo",date:"21 fév. 2026 · 08h22",type:"hs",src:"réseau"},{ev:"Ticket #2849 ouvert auto.",date:"21 fév. 2026 · 08h26",type:"hs",src:"système"}]},
  {id:"CAM-TRG-07",name:"Chemin de la Croix — Ouest",addr:"Sortie village",state:"operational",x:130,y:422,sinceH:null,model:"Axis Q3536-LVE",ip:"10.12.1.7",ping:"16ms",snmp:"OK",uptime:"97.8%",tech:null,coffret:"COF-C",sw:"SW-04",port:"Port 1",poe:"14.2W",history:[]},
  {id:"CAM-TRG-08",name:"Terrain de sport",addr:"Rue du Stade, entrée",state:"replacing",x:140,y:495,sinceH:null,model:"Bosch FLEXIDOME (remplacement)",ip:"—",ping:"—",snmp:"—",uptime:"—",tech:"Julien M. · ETA: 23 fév. 09h00",coffret:"COF-C",sw:"SW-04",port:"Port 2",poe:"0W",history:[{ev:"Devis #DV-TRG-22 accepté",date:"18 fév. 2026",type:"devis",src:"client"},{ev:"Intervention planifiée",date:"19 fév. 2026",type:"replacing",src:"technicien"}]},
  {id:"CAM-TRG-09",name:"Hameau Nord — Entrée",addr:"Rue de Mérignies, N° 45",state:"operational",x:728,y:98,sinceH:null,model:"Dahua IPC-HFW3",ip:"10.12.1.9",ping:"21ms",snmp:"OK",uptime:"96.4%",tech:null,coffret:"COF-E",sw:"SW-06",port:"Port 1",poe:"10.9W",history:[]},
  {id:"CAM-TRG-10",name:"Carrefour r. d'Attiches",addr:"Croisement r. Attiches / r. de Gaulle",state:"ticket",x:268,y:268,sinceH:14,model:"Axis P3267-LV",ip:"10.12.1.10",ping:"TIMEOUT",snmp:"FAIL",uptime:"—",tech:"Ticket #TRG-2847 — prise en charge sous 4h",coffret:"COF-A",sw:"SW-02",port:"Port 4",poe:"0W",history:[{ev:"Anomalie flux détectée",date:"22 fév. 2026 · 02h40",type:"hs",src:"réseau"},{ev:"Ticket #TRG-2847 créé",date:"22 fév. 2026 · 02h50",type:"ticket",src:"système"}]},
  {id:"CAM-TRG-11",name:"Allée des Tilleuls",addr:"Allée des Tilleuls, N° 8",state:"operational",x:202,y:320,sinceH:null,model:"Hikvision DS-2CD2145",ip:"10.12.1.11",ping:"12ms",snmp:"OK",uptime:"99.2%",tech:null,coffret:"COF-C",sw:"SW-04",port:"Port 3",poe:"12.2W",history:[]},
  {id:"CAM-TRG-12",name:"Zone Est — Carrefour",addr:"Rue du Moulin / Chemin de la Croix",state:"reboot",x:563,y:425,sinceH:0.5,model:"Dahua IPC-HDW5831H",ip:"10.12.1.12",ping:"TIMEOUT",snmp:"PARTIAL",uptime:"—",tech:"Reboot distant Axione · Lancé 22 fév. 11h52",coffret:"COF-D",sw:"SW-05",port:"Port 2",poe:"0W",history:[{ev:"Flux vidéo dégradé",date:"22 fév. 2026 · 11h44",type:"hs",src:"réseau"},{ev:"Reboot distant initié",date:"22 fév. 2026 · 11h52",type:"reboot",src:"système"}]},
  {id:"CAM-TRG-13",name:"Parking salle des fêtes",addr:"Rue du Moulin, parking Nord",state:"elec",x:648,y:298,sinceH:18,model:"Bosch 7000 IP",ip:"—",ping:"TIMEOUT",snmp:"FAIL",uptime:"—",tech:"Coupure alimentation coffret élec. C-04",coffret:"COF-B",sw:"SW-03",port:"Port 2",poe:"0W",history:[{ev:"Hors tension détecté",date:"21 fév. 2026 · 17h42",type:"elec",src:"réseau"},{ev:"Cause électrique identifiée",date:"22 fév. 2026 · 07h10",type:"elec",src:"technicien"}]},
  {id:"CAM-TRG-14",name:"Sortie Sud-Est",addr:"Route de Pont-à-Marcq",state:"hs",x:740,y:540,sinceH:6,model:"Axis Q3517-LV",ip:"10.12.1.14",ping:"TIMEOUT",snmp:"FAIL",uptime:"—",tech:"Diagnostic Axione en cours",coffret:"COF-F",sw:"SW-07",port:"Port 1",poe:"0W",history:[{ev:"Perte de signal",date:"22 fév. 2026 · 10h05",type:"hs",src:"réseau"},{ev:"Ticket #2851 ouvert auto.",date:"22 fév. 2026 · 10h08",type:"hs",src:"système"}]},
  {id:"CAM-TRG-15",name:"Allée des Tilleuls — Sud",addr:"Allée des Tilleuls / Chemin de la Croix",state:"operational",x:202,y:415,sinceH:null,model:"Axis P3225-LV",ip:"10.12.1.15",ping:"13ms",snmp:"OK",uptime:"99.8%",tech:null,coffret:"COF-C",sw:"SW-04",port:"Port 4",poe:"11.8W",history:[]},
];

let currentFilter="all", selectedCam=null;

// ─── PAGE NAVIGATION ───
function showPage(name){
  document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
  document.getElementById("page-"+name).classList.add("active");
  document.querySelectorAll(".nav a").forEach(a=>a.classList.remove("active"));
  const labels={dashboard:"Tableau de bord",observabilite:"Observabilité",incidents:"Incidents",maintenance:"Maintenance",contrats:"Contrats"};
  document.querySelectorAll(".nav a").forEach(a=>{if(a.textContent.trim()===labels[name])a.classList.add("active");});
}

// ─── COUNTS ───
function getCounts(){
  const c={all:0,operational:0,hs:0,ticket:0,replacing:0,devis:0,elec:0,reboot:0,"hors-service":0};
  cameras.forEach(cam=>{c.all++;if(cam.state==="operational")c.operational++;else{c["hors-service"]++;c[cam.state]=(c[cam.state]||0)+1;}});
  return c;
}

function updateUI(){
  const c=getCounts();
  document.getElementById("cnt-all").textContent=c.all;
  document.getElementById("cnt-op").textContent=c.operational;
  document.getElementById("cnt-hs-total").textContent=c["hors-service"];
  document.getElementById("cnt-hs").textContent=c.hs||0;
  document.getElementById("cnt-ticket").textContent=c.ticket||0;
  document.getElementById("cnt-rep").textContent=c.replacing||0;
  document.getElementById("cnt-dev").textContent=c.devis||0;
  document.getElementById("cnt-elec").textContent=c.elec||0;
  document.getElementById("cnt-reb").textContent=c.reboot||0;
  const pct=Math.round(c.operational/c.all*1000)/10;
  const slaColor=pct>=95?"#26c281":pct>=80?"#f0883e":"#f85149";
  const slaEl=document.getElementById("slaVal");
  slaEl.textContent=pct+"%";slaEl.style.color=slaColor;
  const fill=document.getElementById("slaFill");
  fill.style.width=pct+"%";fill.style.background=`linear-gradient(90deg,${slaColor},${slaColor}70)`;
  const alerts=[];
  if(c.devis>0)alerts.push(`<div style="background:rgba(227,179,65,0.1);border:1px solid rgba(227,179,65,0.3);border-radius:var(--r);padding:7px 9px;font-size:10.5px;"><div style="color:#e3b341;font-weight:600;margin-bottom:1px;">⚠ ${c.devis} devis à valider</div><div style="color:var(--muted);">Accord requis pour intervention</div></div>`);
  if(c["hors-service"]>0)alerts.push(`<div style="background:rgba(248,81,73,0.1);border:1px solid rgba(248,81,73,0.3);border-radius:var(--r);padding:7px 9px;font-size:10.5px;"><div style="color:#f85149;font-weight:600;margin-bottom:1px;">🔴 ${c["hors-service"]} caméras HS</div><div style="color:var(--muted);">SLA ${pct}% / objectif 95%</div></div>`);
  document.getElementById("alertsBlock").innerHTML=alerts.join("");
  const hsCams=cameras.filter(cam=>HS_STATES.includes(cam.state));
  document.getElementById("hsCamList").innerHTML=hsCams.map(cam=>{
    const s=SC[cam.state];const isSel=selectedCam&&selectedCam.id===cam.id;
    return `<div class="hs-cam-item${isSel?" active":""}" onclick="selectCamera(cameras.find(c=>c.id==='${cam.id}'))">
      <div class="hs-cam-dot" style="background:${s.color}"></div>
      <div class="hs-cam-info"><div class="hs-cam-id">${cam.id.replace("CAM-TRG-","TRG-")}</div><div class="hs-cam-name">${cam.name}</div></div>
      <span class="hs-cam-badge" style="color:${s.color};border-color:${s.color}44;background:${s.color}18;">${s.icon}</span>
    </div>`;
  }).join("");
  const subBreakdown=["hs","ticket","replacing","devis","elec","reboot"].filter(st=>c[st]>0).map(st=>`<span style="color:${SC[st].color}">${SC[st].icon}${c[st]}</span>`).join(" ");
  document.getElementById("statsBar").innerHTML=`
    <div class="stat-pill"><span style="font-size:9.5px;color:var(--muted)">📍 Tourmignies 59551</span></div>
    <div class="stat-pill" onclick="setFilter('operational',null)"><span class="sp-dot" style="background:#26c281"></span><span class="sp-cnt" style="color:#26c281">${c.operational}</span><span style="font-size:9.5px;color:var(--muted)">opé.</span></div>
    <div class="stat-pill hs-pill" onclick="setFilter('hors-service',null)"><span class="sp-dot" style="background:#f85149"></span><span class="sp-cnt" style="color:#f85149">${c["hors-service"]}</span><span style="font-size:9.5px;color:var(--muted)">HS</span><span style="font-size:8.5px;color:var(--dim);margin-left:3px;">(${subBreakdown})</span></div>`;
}

// ─── RENDER PINS ───
function renderPins(){
  const layer=document.getElementById("pinsLayer");layer.innerHTML="";
  const ns="http://www.w3.org/2000/svg";
  cameras.forEach(cam=>{
    const isHS=HS_STATES.includes(cam.state);
    if(currentFilter==="operational"&&cam.state!=="operational")return;
    if(HS_STATES.includes(currentFilter)&&cam.state!==currentFilter)return;
    if(currentFilter==="hors-service"&&!isHS)return;
    const s=SC[cam.state];const col=s.color;const sel=selectedCam&&selectedCam.id===cam.id;
    const g=document.createElementNS(ns,"g");g.style.cursor="pointer";
    if(cam.state!=="operational"){
      const pulse=document.createElementNS(ns,"circle");
      pulse.setAttribute("cx",cam.x);pulse.setAttribute("cy",cam.y);pulse.setAttribute("r","11");pulse.setAttribute("fill","none");pulse.setAttribute("stroke",col);pulse.setAttribute("stroke-width","1.5");pulse.setAttribute("opacity","0.45");
      const a1=document.createElementNS(ns,"animate");a1.setAttribute("attributeName","r");a1.setAttribute("from","11");a1.setAttribute("to","21");a1.setAttribute("dur",cam.state==="hs"?"1.1s":"2s");a1.setAttribute("repeatCount","indefinite");
      const a2=document.createElementNS(ns,"animate");a2.setAttribute("attributeName","opacity");a2.setAttribute("from","0.45");a2.setAttribute("to","0");a2.setAttribute("dur",cam.state==="hs"?"1.1s":"2s");a2.setAttribute("repeatCount","indefinite");
      pulse.appendChild(a1);pulse.appendChild(a2);g.appendChild(pulse);
    }
    const outer=document.createElementNS(ns,"circle");outer.setAttribute("cx",cam.x);outer.setAttribute("cy",cam.y);outer.setAttribute("r",sel?"14":"11");outer.setAttribute("fill",col+"22");outer.setAttribute("stroke",col);outer.setAttribute("stroke-width",sel?"3":"2");g.appendChild(outer);
    const iconsMap={operational:"✓",hs:"✕",ticket:"T",replacing:"⚙",devis:"!",elec:"⚡",reboot:"↺"};
    const txt=document.createElementNS(ns,"text");txt.setAttribute("x",cam.x);txt.setAttribute("y",cam.y+4);txt.setAttribute("text-anchor","middle");txt.setAttribute("font-size","9");txt.setAttribute("fill",col);txt.setAttribute("font-family","DM Sans");txt.setAttribute("font-weight","700");txt.textContent=iconsMap[cam.state]||"?";g.appendChild(txt);
    const lbl=document.createElementNS(ns,"text");lbl.setAttribute("x",cam.x);lbl.setAttribute("y",cam.y+24);lbl.setAttribute("text-anchor","middle");lbl.setAttribute("font-size","7");lbl.setAttribute("fill","rgba(255,255,255,0.35)");lbl.setAttribute("font-family","DM Sans");lbl.textContent=cam.id.replace("CAM-TRG-","C-");g.appendChild(lbl);
    g.addEventListener("click",()=>selectCamera(cam));
    g.addEventListener("mouseenter",()=>showTip(cam,col));
    g.addEventListener("mouseleave",()=>{document.getElementById("tooltip").style.display="none";});
    layer.appendChild(g);
  });
}

function showTip(cam,col){
  const svg=document.getElementById("mapSvg");const r=svg.parentElement.getBoundingClientRect();const vb=svg.viewBox.baseVal;
  const px=cam.x*(r.width/vb.width),py=cam.y*(r.height/vb.height);
  const s=SC[cam.state];const cof=COFFRETS[cam.coffret];
  document.getElementById("tooltip").innerHTML=`<div style="font-family:'DM Mono',monospace;font-size:9.5px;color:var(--muted);">${cam.id}</div><div style="font-weight:600;margin:2px 0;">${cam.name}</div><div style="color:${col};font-size:10px;">${s.label}${cam.sinceH?` · ${cam.sinceH}h`:""}</div><div style="font-size:9.5px;color:var(--muted);margin-top:3px;border-top:1px solid var(--border);padding-top:3px;">📦 ${cof.name} · ${cam.sw}</div>`;
  document.getElementById("tooltip").style.left=(px-85)+"px";document.getElementById("tooltip").style.top=(py-88)+"px";document.getElementById("tooltip").style.display="block";
}

function setFilter(f,el){
  currentFilter=f;
  document.querySelectorAll(".filter-chip,.hs-parent,.sub-chip").forEach(c=>c.classList.remove("active"));
  if(el)el.classList.add("active");else{const ch=document.querySelector(`[data-filter="${f}"]`);if(ch)ch.classList.add("active");}
  renderPins();
}

function selectCamera(cam){
  selectedCam=cam;renderPins();updateUI();
  // Auto-switch to observabilite page
  showPage('observabilite');
  document.getElementById("emptyState").classList.add("hidden");
  const det=document.getElementById("cameraDetail");det.classList.remove("hidden");det.style.cssText="display:flex;flex-direction:column;height:100%;";
  const s=SC[cam.state];const col=s.color;const isHS=HS_STATES.includes(cam.state);
  const cof=COFFRETS[cam.coffret];const sw=SWITCHES[cam.sw];
  const camOk=cam.state==="operational";const swOk=sw.status==="ok";const cofOk=cof.status==="ok";
  const nodeH=(icon,label,sub,ok,isTarget=false)=>`<div class="topo-node"><div class="topo-icon" style="background:${(isTarget?col:(ok?"#26c281":"#f85149"))}18;border-color:${(isTarget?col:(ok?"#26c281":"#f85149"))}44;">${icon}<div class="topo-status" style="background:${isTarget?(camOk?"#26c281":col):(ok?"#26c281":"#f85149")};"></div></div><div class="topo-label">${label}</div><div class="topo-sub">${sub}</div></div>`;
  const arrow=(label,ok)=>`<div class="topo-arrow"><div class="topo-line" style="background:${ok?"#26c281":"#f85149"};opacity:.7;"></div><div class="topo-line-label" style="color:${ok?"#26c281":"#f85149"}">${label}</div></div>`;

  det.innerHTML=`
    <div class="panel-header">
      <div class="ph-id">${cam.id} · Tourmignies (59551)</div>
      <div class="ph-name">${cam.name}</div>
      <div class="ph-addr">📍 ${cam.addr}</div>
      <div class="badges-row">
        ${isHS?`<span class="state-badge" style="color:#f85149;border-color:#f8514944;background:#f8514918;">✗ Hors service</span>`:""}
        <span class="state-badge" style="color:${col};border-color:${col}44;background:${col}18;">${s.icon} ${s.label}${cam.sinceH?` · ${cam.sinceH}h`:""}</span>
      </div>
    </div>
    <div class="panel-body">
      <div>
        <div class="panel-sec">Identification réseau</div>
        <div class="info-grid">
          <div class="info-cell"><div class="cell-lbl">Modèle</div><div class="cell-val">${cam.model}</div></div>
          <div class="info-cell"><div class="cell-lbl">IP</div><div class="cell-val mono">${cam.ip}</div></div>
          <div class="info-cell"><div class="cell-lbl">Ping</div><div class="cell-val mono" style="color:${cam.ping==='TIMEOUT'?'#f85149':cam.ping==='—'?'var(--dim)':'#26c281'}">${cam.ping}</div></div>
          <div class="info-cell"><div class="cell-lbl">SNMP</div><div class="cell-val mono" style="color:${cam.snmp==='OK'?'#26c281':cam.snmp==='PARTIAL'?'#e3b341':'#f85149'}">${cam.snmp}</div></div>
        </div>
      </div>
      <div>
        <div class="panel-sec">Topologie de connexion</div>
        <div class="topo-chain">
          <div class="topo-row">
            ${nodeH("🌐","Réseau","Axione",true)}
            ${arrow(cof.link,cofOk)}
            ${nodeH("🗄️",cam.coffret,cof.name.replace("Coffret ",""),cofOk)}
            ${arrow("PoE/LAN",swOk)}
            ${nodeH("🔀",cam.sw,sw.name,swOk)}
            ${arrow(cam.port,camOk)}
            ${nodeH("📷",cam.id.replace("CAM-TRG-","TRG-"),cam.name.substring(0,12),camOk,true)}
          </div>
          <div style="margin-top:9px;display:grid;grid-template-columns:1fr 1fr;gap:5px;">
            <div class="info-cell"><div class="cell-lbl">Coffret</div><div class="cell-val mono" style="font-size:10px;">${cam.coffret} · ${cof.addr}</div></div>
            <div class="info-cell"><div class="cell-lbl">Switch / Port</div><div class="cell-val mono" style="font-size:10px;">${cam.sw} · ${cam.port}</div></div>
            <div class="info-cell"><div class="cell-lbl">Liaison</div><div class="cell-val">${cof.link}</div></div>
            <div class="info-cell"><div class="cell-lbl">PoE</div><div class="cell-val mono" style="color:${cam.poe==='0W'?'#f85149':'#26c281'}">${cam.poe}</div></div>
          </div>
        </div>
      </div>
      ${buildDiag(cam)}
      <div><div class="panel-sec">Responsabilité & statut</div><div class="resp-banner" style="background:${col}18;border-color:${col}44;"><span class="resp-icon">${s.emoji}</span><div><div class="resp-title" style="color:${col};">${s.label}</div><div class="resp-desc">${s.resp}${cam.tech?`<br><br><strong style="color:var(--text)">${cam.tech}</strong>`:""}</div></div></div></div>
      ${buildHistory(cam)}
      <div><div class="panel-sec">Actions</div><div class="cta-area">${buildCTA(cam)}</div></div>
      <div style="border-top:1px solid var(--border);padding-top:12px;">
        <div class="panel-sec">Assistance Axione</div>
        <div class="cta-area">
          <button class="cta-btn cta-support" onclick="openModal('support','${cam.id}')">🎧 Contacter le support</button>
          <button class="cta-btn cta-ticket" onclick="openModal('ticket','${cam.id}')">🎫 Créer un ticket</button>
        </div>
      </div>
    </div>`;
}

function buildDiag(cam){
  if(cam.state==="operational")return `<div><div class="panel-sec">Supervision réseau</div><div class="diag-block"><div class="diag-row"><span class="dk">Ping</span><span class="dv ok">${cam.ping}</span></div><div class="diag-row"><span class="dk">SNMP</span><span class="dv ok">OK</span></div><div class="diag-row"><span class="dk">Flux vidéo</span><span class="dv ok">Nominal</span></div><div class="diag-row"><span class="dk">Dispo. 30j</span><span class="dv ok">${cam.uptime}</span></div></div></div>`;
  if(["hs","ticket","reboot"].includes(cam.state))return `<div><div class="panel-sec">Diagnostic réseau</div><div class="diag-block"><div class="diag-row"><span class="dk">Ping</span><span class="dv ko">TIMEOUT</span></div><div class="diag-row"><span class="dk">SNMP</span><span class="dv ${cam.snmp==='PARTIAL'?'warn':'ko'}">${cam.snmp==='PARTIAL'?'Partiel':'FAIL'}</span></div><div class="diag-row"><span class="dk">Flux vidéo</span><span class="dv ko">Interrompu</span></div></div></div>`;
  if(cam.state==="elec")return `<div><div class="panel-sec">Diagnostic réseau</div><div class="diag-block"><div class="diag-row"><span class="dk">Ping</span><span class="dv ko">TIMEOUT</span></div><div class="diag-row"><span class="dk">Cause</span><span class="dv warn">Alimentation coupée</span></div><div class="diag-row"><span class="dk">Périmètre Axione</span><span class="dv" style="color:var(--gray)">Non concerné</span></div></div></div>`;
  return "";
}

function buildHistory(cam){
  if(!cam.history||!cam.history.length)return "";
  return `<div><div class="panel-sec">Historique</div><div class="timeline">${cam.history.map(h=>{const c=HC[h.type]||HC[h.src]||{c:"var(--muted)",i:"•"};return `<div class="tl-item"><div class="tl-dot" style="background:${c.c}20;border-color:${c.c};color:${c.c}">${c.i}</div><div class="tl-c"><div class="tl-ev">${h.ev}</div><div class="tl-dt">${h.date}</div><span class="tl-src">${h.src==="réseau"?"🌐":h.src==="technicien"?"🔧":"⚙"} ${h.src}</span></div></div>`;}).join("")}</div></div>`;
}

function buildCTA(cam){
  if(cam.state==="operational")return `<button class="cta-btn cta-ghost">📋 CR de maintenance</button><button class="cta-btn cta-ghost">📊 Statistiques</button>`;
  if(cam.state==="hs")return `<button class="cta-btn cta-primary">📞 Voir le ticket incident</button>`;
  if(cam.state==="ticket")return `<button class="cta-btn cta-primary">🎫 Suivre le ticket</button>`;
  if(cam.state==="replacing")return `<button class="cta-btn cta-primary">🔧 Suivre l'intervention</button><button class="cta-btn cta-ghost">📋 Devis PDF</button>`;
  if(cam.state==="devis")return `<button class="cta-btn cta-warn" onclick="acceptDevis(this,'${cam.id}')">✅ Accepter le devis</button><button class="cta-btn cta-ghost">📄 Télécharger le devis</button>`;
  if(cam.state==="elec")return `<button class="cta-btn cta-ghost">⚡ Guide panne électrique</button>`;
  if(cam.state==="reboot")return `<button class="cta-btn cta-primary">🔄 Suivre le reboot</button>`;
  return "";
}

function acceptDevis(btn,camId){
  btn.innerHTML="✅ Devis accepté";btn.style.background="var(--green-bg)";btn.style.borderColor="var(--green-br)";btn.style.color="var(--green)";btn.disabled=true;
  setTimeout(()=>{const cam=cameras.find(c=>c.id===camId);if(cam){cam.state="replacing";selectedCam=cam;}updateUI();renderPins();setTimeout(()=>selectCamera(cam),100);},1400);
}

function openModal(type,camId){
  document.getElementById("modalOverlay").classList.add("open");
  const mh=document.getElementById("modalHeader"),mb=document.getElementById("modalBody"),mf=document.getElementById("modalFooter");
  const cam=camId?cameras.find(c=>c.id===camId):null;
  if(type==="support"){
    mh.innerHTML=`<div><div class="modal-title">🎧 Contacter le support Axione</div><div class="modal-sub">Commune de Tourmignies (59551)</div></div><div class="modal-close" onclick="closeModal()">✕</div>`;
    mb.innerHTML=`<div style="background:var(--blue-bg);border:1px solid var(--blue-br);border-radius:var(--r);padding:11px 13px;"><div style="font-size:11px;font-weight:600;color:var(--blue);margin-bottom:3px;">📞 Hotline Axione 24h/24</div><div style="font-family:'DM Mono',monospace;font-size:18px;color:var(--text);font-weight:700;">0 800 XXX XXX</div><div style="font-size:10.5px;color:var(--muted);">Numéro gratuit · Astreinte disponible</div></div><div style="background:var(--purple-bg);border:1px solid var(--purple-br);border-radius:var(--r);padding:11px 13px;"><div style="font-size:11px;font-weight:600;color:var(--purple);margin-bottom:3px;">✉ Email</div><div style="font-size:12.5px;color:var(--text);font-weight:500;">support-client@axione.fr</div></div><div class="form-row"><label>Objet</label><input class="form-input" type="text" value="${cam?cam.name:""}" placeholder="Objet de votre demande"></div><div class="form-row"><label>Message</label><textarea class="form-textarea" placeholder="Décrivez votre problème..."></textarea></div>`;
    mf.innerHTML=`<button class="modal-btn modal-cancel" onclick="closeModal()">Annuler</button><button class="modal-btn modal-submit" onclick="submitSupport()">📨 Envoyer</button>`;
  }
  if(type==="ticket"){
    const ref="#TRG-"+Math.floor(Math.random()*9000+1000);
    mh.innerHTML=`<div><div class="modal-title">🎫 Créer un ticket d'incident</div><div class="modal-sub">Mairie de Tourmignies · Vidéoprotection</div></div><div class="modal-close" onclick="closeModal()">✕</div>`;
    mb.innerHTML=`<div class="form-row"><label>Caméra concernée</label><select class="form-select">${cameras.map(c=>`<option value="${c.id}"${cam&&cam.id===c.id?" selected":""}>${c.id} — ${c.name} [${c.coffret}·${c.sw}]</option>`).join("")}<option value="autre">Autre / Plusieurs</option></select></div><div class="form-row"><label>Type d'incident</label><select class="form-select"><option>Hors service / Perte de flux</option><option>Image dégradée</option><option>Problème réseau</option><option>Panne électrique (coffret)</option><option>Défaut switch</option><option>Vandalisme</option><option>Autre</option></select></div><div class="form-row"><label>Priorité</label><select class="form-select"><option>Haute — SLA en danger</option><option>Normale</option><option>Basse — Information</option></select></div><div class="form-row"><label>Description</label><textarea class="form-textarea" placeholder="Décrivez le dysfonctionnement..."></textarea></div><div class="form-row"><label>Contact sur site</label><input class="form-input" type="text" placeholder="Nom et téléphone du référent"><div class="hint">Utilisé par le technicien Axione si intervention physique.</div></div>`;
    mf.innerHTML=`<button class="modal-btn modal-cancel" onclick="closeModal()">Annuler</button><button class="modal-btn modal-submit" onclick="submitTicket('${ref}')">🎫 Créer le ticket</button>`;
  }
  if(type==="suivi"){
    const tickets=[{id:"#TRG-2849",cam:"CAM-TRG-06",label:"HS · Salle des fêtes",date:"21 fév.",status:"En cours",col:"#f0883e"},{id:"#TRG-2851",cam:"CAM-TRG-14",label:"HS · Sortie Sud-Est",date:"22 fév.",status:"En cours",col:"#f0883e"},{id:"#TRG-2847",cam:"CAM-TRG-10",label:"Ticket · Carrefour Attiches",date:"22 fév.",status:"Ticket créé",col:"#2dd4bf"},{id:"#TRG-2845",cam:"CAM-TRG-12",label:"Reboot · Zone Est",date:"22 fév.",status:"Reboot",col:"#388bfd"},{id:"#TRG-2840",cam:"CAM-TRG-04",label:"Devis · Passage école",date:"19 fév.",status:"Attente client",col:"#e3b341"},{id:"#TRG-2838",cam:"CAM-TRG-08",label:"Remplacement · Terrain sport",date:"19 fév.",status:"Planifié",col:"#26c281"}];
    mh.innerHTML=`<div><div class="modal-title">📋 Suivi des tickets</div><div class="modal-sub">Tourmignies · ${tickets.length} tickets actifs</div></div><div class="modal-close" onclick="closeModal()">✕</div>`;
    mb.innerHTML=tickets.map(t=>`<div style="background:var(--bg3);border:1px solid var(--border);border-radius:var(--r);padding:9px 12px;display:flex;align-items:center;gap:10px;"><div style="flex:1;"><div style="font-family:'DM Mono',monospace;font-size:10px;color:var(--blue);margin-bottom:2px;">${t.id} · ${t.cam}</div><div style="font-size:12px;font-weight:500;">${t.label}</div><div style="font-size:10px;color:var(--muted);">${t.date}</div></div><span style="font-size:10px;font-weight:600;color:${t.col};background:${t.col}22;border:1px solid ${t.col}44;padding:2px 7px;border-radius:8px;white-space:nowrap;">${t.status}</span></div>`).join("");
    mf.innerHTML=`<button class="modal-btn modal-cancel" onclick="closeModal()">Fermer</button>`;
  }
}

function closeModal(){document.getElementById("modalOverlay").classList.remove("open");}
function submitSupport(){document.getElementById("modalBody").innerHTML=`<div class="success-state"><div class="success-icon">✅</div><div style="font-size:14px;font-weight:600;color:#26c281;margin-bottom:6px;">Message envoyé !</div><div style="font-size:11.5px;color:var(--muted);line-height:1.6;">Réponse sous 4h en heures ouvrées.</div></div>`;document.getElementById("modalFooter").innerHTML=`<button class="modal-btn modal-submit" onclick="closeModal()">Fermer</button>`;}
function submitTicket(ref){document.getElementById("modalBody").innerHTML=`<div class="success-state"><div class="success-icon">🎫</div><div style="font-size:14px;font-weight:600;color:#26c281;margin-bottom:6px;">Ticket créé !</div><div style="font-size:11.5px;color:var(--muted);line-height:1.6;">Transmis au centre de supervision Axione.<br>Prise en charge sous 4h.</div><div class="ticket-ref">${ref}</div></div>`;document.getElementById("modalFooter").innerHTML=`<button class="modal-btn modal-submit" onclick="closeModal()">Fermer</button>`;}

// INIT
updateUI();renderPins();
let sec=120;
setInterval(()=>{sec++;const el=document.getElementById("syncTime");if(el)el.textContent=sec<60?`${sec}s`:`${Math.floor(sec/60)} min`;if(sec>300)sec=0;},1000);
</script>
</body>
</html>
