<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Venue Pro — Catering Hall Rental</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.19.0/dist/tabler-icons.min.css">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f5f5f3;
  --bg-tertiary: #eeede9;
  --text-primary: #1a1a1a;
  --text-secondary: #6b6b6b;
  --border-light: rgba(0,0,0,0.1);
  --border-med: rgba(0,0,0,0.18);
  --radius-md: 8px;
  --radius-lg: 12px;
  --green: #1D9E75;
  --green-dark: #0F6E56;
  --green-bg: #E1F5EE;
  --green-text: #085041;
  --amber-bg: #FAEEDA;
  --amber-text: #633806;
  --amber-border: #EF9F27;
  --purple-bg: #EEEDFE;
  --purple-text: #3C3489;
  --coral-bg: #FAECE7;
  --coral-text: #712B13;
  --blue-bg: #E6F1FB;
  --blue-text: #0C447C;
  --red-bg: #FCEBEB;
  --red-text: #791F1F;
  --teal-bg: #E1F5EE;
  --teal-text: #085041;
  --danger: #E24B4A;
}
@media (prefers-color-scheme: dark) {
  :root {
    --bg-primary: #1e1e1e;
    --bg-secondary: #2a2a2a;
    --bg-tertiary: #242424;
    --text-primary: #e8e8e8;
    --text-secondary: #9a9a9a;
    --border-light: rgba(255,255,255,0.1);
    --border-med: rgba(255,255,255,0.18);
    --green-bg: #04342C;
    --green-text: #9FE1CB;
    --amber-bg: #412402;
    --amber-text: #FAC775;
    --purple-bg: #26215C;
    --purple-text: #CECBF6;
    --coral-bg: #4A1B0C;
    --coral-text: #F5C4B3;
    --blue-bg: #042C53;
    --blue-text: #B5D4F4;
    --red-bg: #501313;
    --red-text: #F7C1C1;
    --teal-bg: #04342C;
    --teal-text: #9FE1CB;
  }
}
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  font-size: 14px;
  color: var(--text-primary);
  background: var(--bg-tertiary);
  height: 100vh;
  display: flex;
  align-items: stretch;
}
.app {
  display: flex;
  width: 100%;
  max-width: 1100px;
  margin: 16px auto;
  border: 0.5px solid var(--border-light);
  border-radius: var(--radius-lg);
  overflow: hidden;
  background: var(--bg-primary);
  box-shadow: 0 2px 12px rgba(0,0,0,0.08);
}
.sidebar {
  width: 210px;
  border-right: 0.5px solid var(--border-light);
  background: var(--bg-secondary);
  display: flex;
  flex-direction: column;
  flex-shrink: 0;
}
.sidebar-logo {
  padding: 16px;
  border-bottom: 0.5px solid var(--border-light);
}
.sidebar-logo h1 { font-size: 15px; font-weight: 600; }
.sidebar-logo p { font-size: 11px; color: var(--text-secondary); margin-top: 2px; }
nav { padding: 8px 0; }
.nav-item {
  display: flex;
  align-items: center;
  gap: 9px;
  padding: 9px 16px;
  cursor: pointer;
  color: var(--text-secondary);
  font-size: 13px;
  border-left: 2px solid transparent;
  transition: all .12s;
  user-select: none;
}
.nav-item:hover { background: var(--bg-primary); color: var(--text-primary); }
.nav-item.active { background: var(--bg-primary); color: var(--text-primary); border-left-color: var(--green); font-weight: 500; }
.nav-item i { font-size: 17px; }
.main { flex: 1; display: flex; flex-direction: column; overflow: hidden; position: relative; }
.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 20px;
  border-bottom: 0.5px solid var(--border-light);
  flex-shrink: 0;
}
.topbar h2 { font-size: 16px; font-weight: 500; }
.btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 7px 14px;
  border-radius: var(--radius-md);
  border: 0.5px solid var(--border-med);
  background: transparent;
  color: var(--text-primary);
  font-size: 13px;
  cursor: pointer;
  font-family: inherit;
  transition: background .12s;
}
.btn:hover { background: var(--bg-secondary); }
.btn.primary { background: var(--green); border-color: var(--green); color: #fff; }
.btn.primary:hover { background: var(--green-dark); }
.btn.sm { padding: 5px 10px; font-size: 12px; }
.btn.danger { color: var(--danger); }
.content { flex: 1; overflow-y: auto; padding: 18px 20px; }
.stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 18px;
}
.stat { background: var(--bg-secondary); border-radius: var(--radius-md); padding: 12px 14px; }
.stat-label { font-size: 11px; color: var(--text-secondary); margin-bottom: 4px; }
.stat-value { font-size: 22px; font-weight: 500; }
.stat-value.green { color: var(--green-dark); }
.stat-value.amber { color: #854F0B; }
.sec-title {
  font-size: 11px; font-weight: 500; color: var(--text-secondary);
  text-transform: uppercase; letter-spacing: .06em; margin-bottom: 8px;
}
.card {
  background: var(--bg-primary);
  border: 0.5px solid var(--border-light);
  border-radius: var(--radius-lg);
  margin-bottom: 12px;
  overflow: hidden;
}
.card-row {
  display: flex;
  align-items: center;
  padding: 11px 16px;
  gap: 11px;
  cursor: pointer;
  transition: background .1s;
  border-bottom: 0.5px solid var(--border-light);
}
.card-row:last-child { border-bottom: none; }
.card-row:hover { background: var(--bg-secondary); }
.avatar {
  width: 34px; height: 34px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 500; flex-shrink: 0;
}
.av-teal { background: var(--teal-bg); color: var(--teal-text); }
.av-purple { background: var(--purple-bg); color: var(--purple-text); }
.av-coral { background: var(--coral-bg); color: var(--coral-text); }
.av-blue { background: var(--blue-bg); color: var(--blue-text); }
.row-main { flex: 1; min-width: 0; }
.row-name { font-weight: 500; font-size: 13px; margin-bottom: 2px; }
.row-sub { font-size: 11px; color: var(--text-secondary); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.badge { display: inline-block; padding: 2px 8px; border-radius: 999px; font-size: 11px; font-weight: 500; }
.badge.confirmed { background: var(--green-bg); color: var(--green-text); }
.badge.pending { background: var(--amber-bg); color: var(--amber-text); }
.badge.cancelled { background: var(--red-bg); color: var(--red-text); }
.badge.inquiry { background: var(--blue-bg); color: var(--blue-text); }
.row-right { text-align: right; min-width: 95px; }
.row-date { font-size: 11px; color: var(--text-secondary); }
.row-price { font-size: 12px; font-weight: 500; color: var(--green-dark); }
.modal-bg {
  display: none;
  position: absolute; inset: 0;
  background: rgba(0,0,0,.35);
  z-index: 20;
  align-items: center;
  justify-content: center;
}
.modal-bg.open { display: flex; }
.modal {
  background: var(--bg-primary);
  border-radius: var(--radius-lg);
  border: 0.5px solid var(--border-light);
  width: 450px;
  max-height: 560px;
  overflow-y: auto;
}
.modal-hdr {
  display: flex; align-items: center; justify-content: space-between;
  padding: 15px 20px; border-bottom: 0.5px solid var(--border-light);
}
.modal-hdr h3 { font-size: 15px; font-weight: 500; }
.modal-body { padding: 18px 20px; }
.field { margin-bottom: 13px; }
.field label { display: block; font-size: 11px; color: var(--text-secondary); margin-bottom: 5px; font-weight: 500; text-transform: uppercase; letter-spacing: .04em; }
.field input, .field select, .field textarea {
  width: 100%; padding: 8px 10px;
  border: 0.5px solid var(--border-med);
  border-radius: var(--radius-md);
  font-size: 13px; font-family: inherit;
  background: var(--bg-primary);
  color: var(--text-primary);
}
.field textarea { resize: vertical; min-height: 65px; }
.field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.modal-ftr {
  padding: 12px 20px;
  border-top: 0.5px solid var(--border-light);
  display: flex; justify-content: flex-end; gap: 8px;
}
.detail-panel {
  display: none;
  position: absolute; right: 0; top: 0; bottom: 0;
  width: 300px;
  background: var(--bg-primary);
  border-left: 0.5px solid var(--border-light);
  z-index: 5;
  flex-direction: column;
  overflow-y: auto;
}
.detail-panel.open { display: flex; flex-direction: column; }
.detail-hdr {
  display: flex; align-items: center; justify-content: space-between;
  padding: 13px 16px; border-bottom: 0.5px solid var(--border-light);
}
.detail-sec { padding: 13px 16px; border-bottom: 0.5px solid var(--border-light); }
.detail-sec h4 {
  font-size: 11px; font-weight: 500; color: var(--text-secondary);
  text-transform: uppercase; letter-spacing: .05em; margin-bottom: 9px;
}
.drow { display: flex; justify-content: space-between; margin-bottom: 8px; font-size: 13px; }
.drow span:first-child { color: var(--text-secondary); }
.drow span:last-child { font-weight: 500; text-align: right; }
.icon-btn {
  background: none; border: none; cursor: pointer;
  color: var(--text-secondary); padding: 4px;
  display: flex; align-items: center; border-radius: 4px;
}
.icon-btn:hover { background: var(--bg-secondary); color: var(--text-primary); }
.space-selector {
  border: 0.5px solid var(--border-med);
  border-radius: var(--radius-md);
  overflow: hidden;
  margin-bottom: 12px;
}
.space-opt {
  padding: 11px 13px; cursor: pointer;
  border-bottom: 0.5px solid var(--border-light);
  transition: background .1s;
}
.space-opt:last-child { border-bottom: none; }
.space-opt:hover { background: var(--bg-secondary); }
.space-opt.selected { background: var(--green-bg); }
.space-opt-row { display: flex; align-items: center; justify-content: space-between; }
.space-opt-name { font-size: 13px; font-weight: 500; }
.space-opt-price { font-size: 12px; color: var(--green-dark); font-weight: 500; }
.space-opt-desc { font-size: 11px; color: var(--text-secondary); margin-top: 2px; }
.ds-sections { display: flex; gap: 6px; margin-top: 9px; }
.ds-sec-btn {
  flex: 1; padding: 7px;
  border: 0.5px solid var(--border-med);
  border-radius: var(--radius-md);
  background: transparent; font-size: 12px; cursor: pointer;
  font-family: inherit; color: var(--text-secondary);
  transition: all .1s; line-height: 1.4;
}
.ds-sec-btn.active { background: var(--green-bg); border-color: #5DCAA5; color: var(--green-text); font-weight: 500; }
.ds-sec-btn:hover:not(.active) { background: var(--bg-secondary); }
.conflict-warn {
  background: var(--amber-bg); border: 0.5px solid var(--amber-border);
  border-radius: var(--radius-md); padding: 9px 11px;
  font-size: 12px; color: var(--amber-text);
  margin-bottom: 10px; display: none;
}
.conflict-warn.show { display: block; }
.settings-section { margin-bottom: 22px; }
.settings-section h3 { font-size: 14px; font-weight: 500; margin-bottom: 10px; }
.price-row {
  display: flex; align-items: center; justify-content: space-between;
  padding: 9px 0; border-bottom: 0.5px solid var(--border-light);
}
.price-row:last-child { border-bottom: none; }
.price-row label { font-size: 13px; }
.price-row input {
  width: 110px; padding: 6px 9px;
  border: 0.5px solid var(--border-med);
  border-radius: var(--radius-md); font-size: 13px;
  font-family: inherit; text-align: right;
  background: var(--bg-primary); color: var(--text-primary);
}
.cal-grid { display: grid; grid-template-columns: repeat(7, 1fr); gap: 4px; }
.cal-hdr { font-size: 11px; color: var(--text-secondary); text-align: center; padding: 4px; }
.cal-day {
  aspect-ratio: 1; display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  border-radius: var(--radius-md); font-size: 12px; cursor: pointer;
  position: relative; transition: background .1s;
}
.cal-day:hover { background: var(--bg-secondary); }
.cal-day.booked-up { background: var(--purple-bg); }
.cal-day.booked-ds { background: var(--green-bg); }
.cal-day.booked-both { background: var(--blue-bg); }
.cal-day.today { border: 1.5px solid var(--green); }
.cal-day.other-month { opacity: .35; }
.cal-dots { display: flex; gap: 2px; position: absolute; bottom: 4px; }
.cal-dot { width: 4px; height: 4px; border-radius: 50%; }
.cal-dot.up { background: #7F77DD; }
.cal-dot.ds { background: var(--green); }
.month-nav { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
.month-nav h3 { font-size: 14px; font-weight: 500; }
.legend { display: flex; gap: 14px; margin-bottom: 12px; }
.legend-item { display: flex; align-items: center; gap: 5px; font-size: 11px; color: var(--text-secondary); }
.legend-dot { width: 10px; height: 10px; border-radius: 50%; }
</style>
</head>
<body>
<div class="app">
  <div class="sidebar">
    <div class="sidebar-logo">
      <h1>Venue Pro</h1>
      <p>Hall Rental Manager</p>
    </div>
    <nav>
      <div class="nav-item active" onclick="showView('dashboard')" id="nav-dashboard"><i class="ti ti-layout-dashboard"></i> Dashboard</div>
      <div class="nav-item" onclick="showView('reservations')" id="nav-reservations"><i class="ti ti-calendar-event"></i> Reservations</div>
      <div class="nav-item" onclick="showView('clients')" id="nav-clients"><i class="ti ti-users"></i> Clients</div>
      <div class="nav-item" onclick="showView('calendar')" id="nav-calendar"><i class="ti ti-calendar"></i> Calendar</div>
      <div class="nav-item" onclick="showView('settings')" id="nav-settings"><i class="ti ti-settings"></i> Settings</div>
    </nav>
  </div>
  <div class="main">
    <div class="topbar">
      <h2 id="view-title">Dashboard</h2>
      <div id="topbar-actions"></div>
    </div>
    <div class="content" id="main-content"></div>
    <div class="modal-bg" id="modal-bg"><div class="modal" id="modal-box"></div></div>
    <div class="detail-panel" id="detail-panel"></div>
  </div>
</div>

<script>
const PRICES = { upstairs: 1200, ds_small: 800, ds_medium: 1400, ds_full: 2000 };
const DS_TIERS = {
  1: { label: 'Small (1 section)', price: () => PRICES.ds_small },
  2: { label: 'Medium (2 sections)', price: () => PRICES.ds_medium },
  3: { label: 'Full (3 sections)', price: () => PRICES.ds_full },
};
const avColors = ['teal','purple','coral','blue'];
const statuses = ['inquiry','pending','confirmed','cancelled'];

const state = {
  view: 'dashboard',
  clients: [
    {id:1,name:'Margaret & David Chen',email:'mchen@email.com',phone:'(212) 555-0134',initials:'MC',color:'teal',notes:'Kosher catering required.'},
    {id:2,name:'Santos Family',email:'jsantos@email.com',phone:'(718) 555-0287',initials:'SF',color:'purple',notes:'Large extended family.'},
    {id:3,name:'Aisha & Marcus Webb',email:'awebb@email.com',phone:'(646) 555-0319',initials:'AW',color:'coral',notes:'Outdoor ceremony, indoor reception.'},
    {id:4,name:'Rivera Corporate',email:'events@rivera.co',phone:'(212) 555-0451',initials:'RC',color:'blue',notes:'Annual holiday party.'},
  ],
  reservations: [
    {id:1,clientId:1,event:'Wedding Reception',date:'2026-06-14',guests:180,space:'upstairs',dsSections:0,status:'confirmed',deposit:true,notes:'Champagne toast at 7pm.'},
    {id:2,clientId:2,event:'Quinceañera',date:'2026-07-04',guests:220,space:'downstairs',dsSections:3,status:'confirmed',deposit:true,notes:'DJ booth required.'},
    {id:3,clientId:3,event:'Wedding',date:'2026-08-22',guests:150,space:'downstairs',dsSections:2,status:'pending',deposit:false,notes:'Garden theme.'},
    {id:4,clientId:4,event:'Holiday Gala',date:'2026-12-05',guests:95,space:'upstairs',dsSections:0,status:'confirmed',deposit:true,notes:'Open bar.'},
    {id:5,clientId:1,event:'Baby Shower',date:'2026-06-14',guests:45,space:'upstairs',dsSections:0,status:'confirmed',deposit:true,notes:'Afternoon tea style.'},
  ],
};

function clientById(id){return state.clients.find(c=>c.id===id);}
function resById(id){return state.reservations.find(r=>r.id===id);}
function fmtDate(d){return new Date(d+'T00:00').toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'});}
function spaceLabel(r){return r.space==='upstairs'?'Upstairs':'Downstairs — '+DS_TIERS[r.dsSections].label;}
function spacePrice(r){return r.space==='upstairs'?PRICES.upstairs:DS_TIERS[r.dsSections].price();}
function fmtPrice(n){return '$'+n.toLocaleString();}
function hasDownstairsConflict(date,excludeId){return state.reservations.some(r=>r.id!==excludeId&&r.space==='downstairs'&&r.date===date);}

function showView(v){
  state.view=v;
  document.querySelectorAll('.nav-item').forEach(el=>el.classList.remove('active'));
  document.getElementById('nav-'+v).classList.add('active');
  const titles={dashboard:'Dashboard',reservations:'Reservations',clients:'Clients',calendar:'Calendar',settings:'Settings'};
  document.getElementById('view-title').textContent=titles[v];
  closeDetail();
  const actions=document.getElementById('topbar-actions');
  if(v==='reservations') actions.innerHTML='<button class="btn primary" onclick="openAddRes()"><i class="ti ti-plus"></i> New reservation</button>';
  else if(v==='clients') actions.innerHTML='<button class="btn primary" onclick="openAddClient()"><i class="ti ti-plus"></i> New client</button>';
  else actions.innerHTML='';
  const c=document.getElementById('main-content');
  if(v==='dashboard') renderDashboard(c);
  else if(v==='reservations') renderReservations(c);
  else if(v==='clients') renderClients(c);
  else if(v==='calendar') renderCalendar(c);
  else if(v==='settings') renderSettings(c);
}

function renderDashboard(el){
  const confirmed=state.reservations.filter(r=>r.status==='confirmed').length;
  const pending=state.reservations.filter(r=>r.status==='pending'||r.status==='inquiry').length;
  const today=new Date().toISOString().split('T')[0];
  const upcoming=state.reservations.filter(r=>r.date>=today).length;
  const revenue=state.reservations.filter(r=>r.status==='confirmed').reduce((a,r)=>a+spacePrice(r),0);
  el.innerHTML=`
    <div class="stats">
      <div class="stat"><div class="stat-label">Upcoming events</div><div class="stat-value">${upcoming}</div></div>
      <div class="stat"><div class="stat-label">Confirmed</div><div class="stat-value green">${confirmed}</div></div>
      <div class="stat"><div class="stat-label">Pending / inquiries</div><div class="stat-value amber">${pending}</div></div>
      <div class="stat"><div class="stat-label">Confirmed revenue</div><div class="stat-value" style="font-size:16px;">${fmtPrice(revenue)}</div></div>
    </div>
    <div class="sec-title">Upcoming reservations</div>
    <div class="card">${state.reservations.filter(r=>r.date>=today).sort((a,b)=>a.date.localeCompare(b.date)).slice(0,8).map(r=>resRowHtml(r)).join('')}</div>`;
}

function resRowHtml(r){
  const c=clientById(r.clientId);
  return `<div class="card-row" onclick="openDetail('res',${r.id})">
    <div class="avatar av-${c.color}">${c.initials}</div>
    <div class="row-main">
      <div class="row-name">${r.event}</div>
      <div class="row-sub">${c.name} · ${spaceLabel(r)} · ${r.guests} guests</div>
    </div>
    <span class="badge ${r.status}">${r.status}</span>
    <div class="row-right"><div class="row-date">${fmtDate(r.date)}</div><div class="row-price">${fmtPrice(spacePrice(r))}</div></div>
  </div>`;
}

function clientRowHtml(c){
  const ev=state.reservations.filter(r=>r.clientId===c.id);
  return `<div class="card-row" onclick="openDetail('client',${c.id})">
    <div class="avatar av-${c.color}">${c.initials}</div>
    <div class="row-main"><div class="row-name">${c.name}</div><div class="row-sub">${c.email} · ${ev.length} event${ev.length!==1?'s':''}</div></div>
    <i class="ti ti-chevron-right" style="color:var(--text-secondary);font-size:15px;"></i>
  </div>`;
}

function renderReservations(el){
  const sorted=[...state.reservations].sort((a,b)=>a.date.localeCompare(b.date));
  el.innerHTML=`<div class="card">${sorted.map(r=>resRowHtml(r)).join('')}</div>`;
}
function renderClients(el){
  el.innerHTML=`<div class="card">${state.clients.map(c=>clientRowHtml(c)).join('')}</div>`;
}

let calMonth=new Date().getMonth()+1, calYear=new Date().getFullYear();
function renderCalendar(el){
  const mn=new Date(calYear,calMonth-1,1).toLocaleString('en-US',{month:'long',year:'numeric'});
  const fd=new Date(calYear,calMonth-1,1).getDay();
  const dim=new Date(calYear,calMonth,0).getDate();
  const diPrev=new Date(calYear,calMonth-1,0).getDate();
  const upDays=new Set(state.reservations.filter(r=>{const[y,m]=r.date.split('-').map(Number);return y===calYear&&m===calMonth&&r.space==='upstairs';}).map(r=>+r.date.split('-')[2]));
  const dsDays=new Set(state.reservations.filter(r=>{const[y,m]=r.date.split('-').map(Number);return y===calYear&&m===calMonth&&r.space==='downstairs';}).map(r=>+r.date.split('-')[2]));
  const todayStr=new Date().toISOString().split('T')[0];
  const [ty,tm,td]=todayStr.split('-').map(Number);
  let cells='';
  for(let i=0;i<fd;i++) cells+=`<div class="cal-day other-month">${diPrev-fd+1+i}</div>`;
  for(let d=1;d<=dim;d++){
    const isToday=d===td&&calMonth===tm&&calYear===ty;
    const hasUp=upDays.has(d),hasDs=dsDays.has(d);
    let cls='cal-day';
    if(hasUp&&hasDs) cls+=' booked-both';
    else if(hasUp) cls+=' booked-up';
    else if(hasDs) cls+=' booked-ds';
    if(isToday) cls+=' today';
    const dots=(hasUp?'<span class="cal-dot up"></span>':'')+(hasDs?'<span class="cal-dot ds"></span>':'');
    cells+=`<div class="${cls}" onclick="calClick(${d})">${d}${dots?`<div class="cal-dots">${dots}</div>`:''}</div>`;
  }
  const rem=42-fd-dim;
  for(let i=1;i<=rem;i++) cells+=`<div class="cal-day other-month">${i}</div>`;
  el.innerHTML=`
    <div class="month-nav">
      <button class="btn sm" onclick="changeMonth(-1)"><i class="ti ti-chevron-left"></i></button>
      <h3>${mn}</h3>
      <button class="btn sm" onclick="changeMonth(1)"><i class="ti ti-chevron-right"></i></button>
    </div>
    <div class="legend">
      <div class="legend-item"><div class="legend-dot" style="background:#7F77DD;"></div>Upstairs</div>
      <div class="legend-item"><div class="legend-dot" style="background:#1D9E75;"></div>Downstairs</div>
      <div class="legend-item"><div class="legend-dot" style="background:#378ADD;"></div>Both spaces</div>
    </div>
    <div class="cal-grid">
      ${['Su','Mo','Tu','We','Th','Fr','Sa'].map(d=>`<div class="cal-hdr">${d}</div>`).join('')}
      ${cells}
    </div>`;
}
function changeMonth(d){calMonth+=d;if(calMonth>12){calMonth=1;calYear++;}if(calMonth<1){calMonth=12;calYear--;}showView('calendar');}
function calClick(d){
  const ds=`${calYear}-${String(calMonth).padStart(2,'0')}-${String(d).padStart(2,'0')}`;
  const res=state.reservations.filter(r=>r.date===ds);
  if(res.length) openDetail('res',res[0].id);
}

function renderSettings(el){
  el.innerHTML=`
    <div class="settings-section">
      <h3>Rental prices</h3>
      <div class="card" style="padding:4px 16px;">
        <div class="price-row"><label>Upstairs (full space)</label><input type="number" value="${PRICES.upstairs}" onchange="savePrice('upstairs',this.value)"></div>
        <div class="price-row"><label>Downstairs — small (1 section)</label><input type="number" value="${PRICES.ds_small}" onchange="savePrice('ds_small',this.value)"></div>
        <div class="price-row"><label>Downstairs — medium (2 sections)</label><input type="number" value="${PRICES.ds_medium}" onchange="savePrice('ds_medium',this.value)"></div>
        <div class="price-row"><label>Downstairs — full (3 sections)</label><input type="number" value="${PRICES.ds_full}" onchange="savePrice('ds_full',this.value)"></div>
      </div>
    </div>
    <div class="settings-section">
      <h3>Space rules</h3>
      <div class="card" style="padding:12px 16px;">
        <div style="font-size:13px;color:var(--text-secondary);line-height:1.7;">
          <div style="margin-bottom:6px;"><i class="ti ti-check" style="color:#1D9E75;margin-right:6px;"></i>Upstairs and downstairs can be booked simultaneously.</div>
          <div><i class="ti ti-alert-circle" style="color:#BA7517;margin-right:6px;"></i>Only one event allowed downstairs per day (regardless of sections used).</div>
        </div>
      </div>
    </div>`;
}
function savePrice(key,val){PRICES[key]=parseInt(val)||0;}

function openDetail(type,id){
  const panel=document.getElementById('detail-panel');
  panel.classList.add('open');
  if(type==='res'){
    const r=resById(parseInt(id));
    const c=clientById(r.clientId);
    panel.innerHTML=`
      <div class="detail-hdr"><strong style="font-size:14px;">${r.event}</strong><button class="icon-btn" onclick="closeDetail()"><i class="ti ti-x"></i></button></div>
      <div class="detail-sec">
        <h4>Reservation</h4>
        <div class="drow"><span>Date</span><span>${fmtDate(r.date)}</span></div>
        <div class="drow"><span>Space</span><span>${spaceLabel(r)}</span></div>
        <div class="drow"><span>Guests</span><span>${r.guests}</span></div>
        <div class="drow"><span>Price</span><span style="color:var(--green-dark);">${fmtPrice(spacePrice(r))}</span></div>
        <div class="drow"><span>Status</span><span><span class="badge ${r.status}">${r.status}</span></span></div>
        <div class="drow"><span>Deposit</span><span>${r.deposit?'✓ Received':'✗ Pending'}</span></div>
      </div>
      <div class="detail-sec">
        <h4>Client</h4>
        <div class="drow"><span>Name</span><span style="font-size:12px;">${c.name}</span></div>
        <div class="drow"><span>Email</span><span style="font-size:11px;">${c.email}</span></div>
        <div class="drow"><span>Phone</span><span>${c.phone}</span></div>
      </div>
      ${r.notes?`<div class="detail-sec"><h4>Notes</h4><p style="font-size:12px;line-height:1.5;color:var(--text-secondary);">${r.notes}</p></div>`:''}
      <div style="padding:12px 16px;display:flex;gap:8px;">
        <button class="btn" style="flex:1;" onclick="openEditRes(${r.id})"><i class="ti ti-edit"></i> Edit</button>
        <button class="btn danger" onclick="deleteRes(${r.id})"><i class="ti ti-trash"></i></button>
      </div>`;
  } else {
    const c=clientById(parseInt(id));
    const res=state.reservations.filter(r=>r.clientId===c.id);
    panel.innerHTML=`
      <div class="detail-hdr"><strong style="font-size:14px;">${c.name}</strong><button class="icon-btn" onclick="closeDetail()"><i class="ti ti-x"></i></button></div>
      <div class="detail-sec">
        <h4>Contact</h4>
        <div class="drow"><span>Email</span><span style="font-size:11px;">${c.email}</span></div>
        <div class="drow"><span>Phone</span><span>${c.phone}</span></div>
      </div>
      ${c.notes?`<div class="detail-sec"><h4>Notes</h4><p style="font-size:12px;line-height:1.5;color:var(--text-secondary);">${c.notes}</p></div>`:''}
      <div class="detail-sec">
        <h4>Events (${res.length})</h4>
        ${res.length===0?'<p style="font-size:12px;color:var(--text-secondary);">No events yet.</p>':res.map(r=>`
          <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:9px;cursor:pointer;" onclick="openDetail('res',${r.id})">
            <div><div style="font-size:13px;font-weight:500;">${r.event}</div><div style="font-size:11px;color:var(--text-secondary);">${fmtDate(r.date)} · ${fmtPrice(spacePrice(r))}</div></div>
            <span class="badge ${r.status}">${r.status}</span>
          </div>`).join('')}
      </div>
      <div style="padding:12px 16px;"><button class="btn" style="width:100%;" onclick="openEditClient(${c.id})"><i class="ti ti-edit"></i> Edit client</button></div>`;
  }
}
function closeDetail(){document.getElementById('detail-panel').classList.remove('open');}

function openModal(html){document.getElementById('modal-box').innerHTML=html;document.getElementById('modal-bg').classList.add('open');}
function closeModal(){document.getElementById('modal-bg').classList.remove('open');}
document.getElementById('modal-bg').addEventListener('click',e=>{if(e.target===e.currentTarget)closeModal();});

let formSpace='upstairs';
let formDsSections=1;

function spacePickerHtml(date,excludeId){
  const dsConflict=date?hasDownstairsConflict(date,excludeId||0):false;
  return `
    <div class="conflict-warn${dsConflict?' show':''}" id="ds-conflict">Another event is already booked downstairs on this date.</div>
    <div class="space-selector">
      <div class="space-opt${formSpace==='upstairs'?' selected':''}" onclick="selectSpace('upstairs','${date||''}','${excludeId||0}')">
        <div class="space-opt-row"><span class="space-opt-name">Upstairs</span><span class="space-opt-price">${fmtPrice(PRICES.upstairs)}</span></div>
        <div class="space-opt-desc">Full upstairs space · can book alongside downstairs</div>
      </div>
      <div class="space-opt${formSpace==='downstairs'?' selected':''}" onclick="selectSpace('downstairs','${date||''}','${excludeId||0}')">
        <div class="space-opt-row"><span class="space-opt-name">Downstairs</span><span class="space-opt-price" id="ds-price-label">${fmtPrice(DS_TIERS[formDsSections].price())}</span></div>
        <div class="space-opt-desc">Choose number of sections needed</div>
        <div class="ds-sections" id="ds-sec-btns">
          <button class="ds-sec-btn${formDsSections===1?' active':''}" onclick="selectDsSec(1,event)">1 section<br><small>Small</small></button>
          <button class="ds-sec-btn${formDsSections===2?' active':''}" onclick="selectDsSec(2,event)">2 sections<br><small>Medium</small></button>
          <button class="ds-sec-btn${formDsSections===3?' active':''}" onclick="selectDsSec(3,event)">3 sections<br><small>Full</small></button>
        </div>
      </div>
    </div>`;
}

function selectSpace(sp,date,excludeId){
  formSpace=sp;
  document.getElementById('space-picker').innerHTML=spacePickerHtml(date,parseInt(excludeId)||0);
}
function selectDsSec(n,e){
  e.stopPropagation();
  formSpace='downstairs';
  formDsSections=n;
  document.querySelectorAll('.ds-sec-btn').forEach((b,i)=>b.classList.toggle('active',i+1===n));
  const pl=document.getElementById('ds-price-label');
  if(pl) pl.textContent=fmtPrice(DS_TIERS[n].price());
  document.querySelectorAll('.space-opt').forEach((o,i)=>o.classList.toggle('selected',i===1));
}

function openAddRes(){
  formSpace='upstairs'; formDsSections=1;
  openModal(`
    <div class="modal-hdr"><h3>New reservation</h3><button class="icon-btn" onclick="closeModal()"><i class="ti ti-x"></i></button></div>
    <div class="modal-body">
      <div class="field"><label>Client</label><select id="f-client">${state.clients.map(c=>`<option value="${c.id}">${c.name}</option>`).join('')}</select></div>
      <div class="field"><label>Event type</label><input id="f-event" placeholder="e.g. Wedding Reception"></div>
      <div class="field-row">
        <div class="field"><label>Date</label><input type="date" id="f-date" onchange="refreshSpacePicker(0)"></div>
        <div class="field"><label>Guests</label><input type="number" id="f-guests" placeholder="0"></div>
      </div>
      <div class="field"><label>Space</label><div id="space-picker">${spacePickerHtml('',0)}</div></div>
      <div class="field-row">
        <div class="field"><label>Status</label><select id="f-status">${statuses.map(s=>`<option>${s}</option>`).join('')}</select></div>
        <div class="field"><label>Deposit</label><select id="f-deposit"><option value="0">Pending</option><option value="1">Received</option></select></div>
      </div>
      <div class="field"><label>Notes</label><textarea id="f-notes" placeholder="Special requests..."></textarea></div>
    </div>
    <div class="modal-ftr">
      <button class="btn" onclick="closeModal()">Cancel</button>
      <button class="btn primary" onclick="saveRes()">Save reservation</button>
    </div>`);
}

function openEditRes(id){
  const r=resById(id);
  formSpace=r.space; formDsSections=r.dsSections||1;
  openModal(`
    <div class="modal-hdr"><h3>Edit reservation</h3><button class="icon-btn" onclick="closeModal()"><i class="ti ti-x"></i></button></div>
    <div class="modal-body">
      <div class="field"><label>Client</label><select id="f-client">${state.clients.map(c=>`<option value="${c.id}"${c.id===r.clientId?' selected':''}>${c.name}</option>`).join('')}</select></div>
      <div class="field"><label>Event type</label><input id="f-event" value="${r.event}"></div>
      <div class="field-row">
        <div class="field"><label>Date</label><input type="date" id="f-date" value="${r.date}" onchange="refreshSpacePicker(${id})"></div>
        <div class="field"><label>Guests</label><input type="number" id="f-guests" value="${r.guests}"></div>
      </div>
      <div class="field"><label>Space</label><div id="space-picker">${spacePickerHtml(r.date,id)}</div></div>
      <div class="field-row">
        <div class="field"><label>Status</label><select id="f-status">${statuses.map(s=>`<option${s===r.status?' selected':''}>${s}</option>`).join('')}</select></div>
        <div class="field"><label>Deposit</label><select id="f-deposit"><option value="0"${!r.deposit?' selected':''}>Pending</option><option value="1"${r.deposit?' selected':''}>Received</option></select></div>
      </div>
      <div class="field"><label>Notes</label><textarea id="f-notes">${r.notes}</textarea></div>
    </div>
    <div class="modal-ftr">
      <button class="btn" onclick="closeModal()">Cancel</button>
      <button class="btn primary" onclick="saveRes(${id})">Update</button>
    </div>`);
}

function refreshSpacePicker(excludeId){
  const date=document.getElementById('f-date').value;
  document.getElementById('space-picker').innerHTML=spacePickerHtml(date,excludeId);
}

function saveRes(editId){
  const event=document.getElementById('f-event').value.trim();
  const date=document.getElementById('f-date').value;
  if(!event||!date) return;
  if(formSpace==='downstairs'&&hasDownstairsConflict(date,editId||0)){
    const w=document.getElementById('ds-conflict');
    if(w) w.classList.add('show');
    return;
  }
  const data={
    clientId:parseInt(document.getElementById('f-client').value),
    event,date,
    guests:parseInt(document.getElementById('f-guests').value)||0,
    space:formSpace,
    dsSections:formSpace==='downstairs'?formDsSections:0,
    status:document.getElementById('f-status').value,
    deposit:document.getElementById('f-deposit').value==='1',
    notes:document.getElementById('f-notes').value.trim(),
  };
  if(editId) Object.assign(resById(editId),data);
  else{data.id=Date.now();state.reservations.push(data);}
  closeModal();showView(state.view);
}

function deleteRes(id){state.reservations=state.reservations.filter(r=>r.id!==id);closeDetail();showView(state.view);}

function openAddClient(){
  openModal(`
    <div class="modal-hdr"><h3>New client</h3><button class="icon-btn" onclick="closeModal()"><i class="ti ti-x"></i></button></div>
    <div class="modal-body">
      <div class="field"><label>Full name / Organization</label><input id="f-name" placeholder="e.g. Smith Family"></div>
      <div class="field-row">
        <div class="field"><label>Email</label><input type="email" id="f-email"></div>
        <div class="field"><label>Phone</label><input id="f-phone"></div>
      </div>
      <div class="field"><label>Notes</label><textarea id="f-notes" placeholder="Preferences, requirements..."></textarea></div>
    </div>
    <div class="modal-ftr">
      <button class="btn" onclick="closeModal()">Cancel</button>
      <button class="btn primary" onclick="saveClient()">Save client</button>
    </div>`);
}

function openEditClient(id){
  const c=clientById(id);
  openModal(`
    <div class="modal-hdr"><h3>Edit client</h3><button class="icon-btn" onclick="closeModal()"><i class="ti ti-x"></i></button></div>
    <div class="modal-body">
      <div class="field"><label>Full name / Organization</label><input id="f-name" value="${c.name}"></div>
      <div class="field-row">
        <div class="field"><label>Email</label><input type="email" id="f-email" value="${c.email}"></div>
        <div class="field"><label>Phone</label><input id="f-phone" value="${c.phone}"></div>
      </div>
      <div class="field"><label>Notes</label><textarea id="f-notes">${c.notes}</textarea></div>
    </div>
    <div class="modal-ftr">
      <button class="btn" onclick="closeModal()">Cancel</button>
      <button class="btn primary" onclick="saveClient(${id})">Update</button>
    </div>`);
}

function saveClient(editId){
  const name=document.getElementById('f-name').value.trim();
  if(!name) return;
  if(editId){
    const c=clientById(editId);
    c.name=name;c.email=document.getElementById('f-email').value.trim();
    c.phone=document.getElementById('f-phone').value.trim();
    c.notes=document.getElementById('f-notes').value.trim();
  } else {
    const words=name.split(' ');
    const initials=(words[0][0]+(words[1]?.[0]||'')).toUpperCase();
    state.clients.push({id:Date.now(),name,email:document.getElementById('f-email').value.trim(),phone:document.getElementById('f-phone').value.trim(),initials,color:avColors[state.clients.length%avColors.length],notes:document.getElementById('f-notes').value.trim()});
  }
  closeModal();showView(state.view);
}

showView('dashboard');
</script>
</body>
</html>
