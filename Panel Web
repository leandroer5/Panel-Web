<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mi Panel</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.34.0/dist/tabler-icons.min.css">
<style>
@import url('https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{--bg:#0d0f14;--card:#1e2230;--card2:#252a3a;--accent:#5b8dee;--accent2:#7aa3f5;--border:rgba(255,255,255,0.08);--text:#e8eaf0;--text2:#9aa0b4;--text3:#5a6075;--danger:#e05c6a}
body{font-family:'Sora',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow-x:hidden}
#wp{position:fixed;inset:0;z-index:0;background-size:cover;background-position:center}
#ov{position:fixed;inset:0;z-index:1;background:rgba(0,0,0,0.55);pointer-events:none}
#app{position:relative;z-index:2;min-height:100vh;display:flex;flex-direction:column;align-items:center;padding:20px 20px 60px}
#topbar{width:100%;max-width:920px;display:flex;justify-content:space-between;align-items:center;margin-bottom:35px;padding:0 4px}
#clock{font-size:26px;font-weight:300;letter-spacing:2px}
#datep{font-size:12px;color:var(--text2);text-align:left;margin-top:2px}
#settbtn{background:rgba(255,255,255,0.08);border:1px solid var(--border);color:var(--text2);border-radius:10px;width:38px;height:38px;cursor:pointer;font-size:18px;display:flex;align-items:center;justify-content:center;transition:all .2s}
#settbtn:hover{background:rgba(255,255,255,0.15);color:var(--text)}
#hero{display:flex;flex-direction:column;align-items:center;gap:8px;margin-bottom:28px}
#hero-logo img{width:56px;height:56px;object-fit:contain;border-radius:12px}
#hero-logo .ti{font-size:48px;color:var(--text3)}
#hero-name{font-size:22px;font-weight:500}
#fnav{width:100%;max-width:900px;display:flex;align-items:center;gap:8px;margin-bottom:18px}
.arrbtn{background:rgba(255,255,255,0.07);border:1px solid var(--border);color:var(--text2);border-radius:10px;width:34px;height:34px;cursor:pointer;font-size:16px;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all .2s}
.arrbtn:hover{background:rgba(255,255,255,0.13);color:var(--text)}
.arrbtn:disabled{opacity:0.22;cursor:default}
#ftabs{flex:1;display:flex;gap:7px;overflow:hidden}
.ftab{display:flex;align-items:center;gap:6px;background:rgba(255,255,255,0.05);border:1px solid var(--border);border-radius:10px;padding:6px 13px;cursor:pointer;font-size:13px;color:var(--text2);white-space:nowrap;transition:all .2s;flex-shrink:0}
.ftab img{width:16px;height:16px;border-radius:3px}
.ftab.active{background:rgba(91,141,238,0.18);border-color:rgba(91,141,238,0.4);color:var(--accent2)}
.ftab:hover:not(.active){background:rgba(255,255,255,0.09);color:var(--text)}
#addfbtn{background:rgba(255,255,255,0.05);border:1px dashed rgba(255,255,255,0.18);color:var(--text3);border-radius:10px;width:34px;height:34px;cursor:pointer;font-size:18px;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all .2s}
#addfbtn:hover{background:rgba(91,141,238,0.1);color:var(--accent2);border-color:rgba(91,141,238,0.4)}
#grid{width:100%;max-width:900px;display:grid;grid-template-columns:repeat(auto-fill,minmax(130px,1fr));gap:13px}
.scard{background:var(--card);border:1px solid var(--border);border-radius:15px;padding:18px 12px;display:flex;flex-direction:column;align-items:center;gap:9px;cursor:pointer;transition:all .22s;position:relative}
.scard:hover{background:var(--card2);border-color:rgba(91,141,238,0.3);transform:translateY(-2px)}
.scard img{width:38px;height:38px;border-radius:9px;object-fit:contain;background:rgba(255,255,255,0.04);padding:3px}
.sfb{width:38px;height:38px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:18px;font-weight:600;color:#fff}
.sname{font-size:12px;color:var(--text2);text-align:center;max-width:110px;word-break:break-word}
.cacts{position:absolute;top:6px;right:6px;display:none;gap:3px}
.scard:hover .cacts{display:flex}
.cbtn{background:rgba(0,0,0,0.55);border:none;color:var(--text2);border-radius:7px;padding:4px 6px;cursor:pointer;font-size:13px;display:flex;align-items:center;transition:all .15s}
.cbtn:hover{color:var(--text)}
.cbtn.del:hover{color:var(--danger)}
.addcard{background:transparent;border:1px dashed rgba(255,255,255,0.13);border-radius:15px;padding:18px 12px;display:flex;flex-direction:column;align-items:center;gap:7px;cursor:pointer;transition:all .2s;color:var(--text3);font-size:13px}
.addcard:hover{background:rgba(91,141,238,0.07);border-color:rgba(91,141,238,0.35);color:var(--accent2)}
.addcard .ti{font-size:26px}
.mbg{position:fixed;inset:0;z-index:100;background:rgba(0,0,0,0.72);display:flex;align-items:center;justify-content:center;padding:20px}
.mod{background:#1a1e2a;border:1px solid rgba(255,255,255,0.1);border-radius:18px;padding:26px;width:100%;max-width:410px;display:flex;flex-direction:column;gap:15px}
.mod h3{font-size:17px;font-weight:500}
.mod label{font-size:13px;color:var(--text2);display:block;margin-bottom:5px}
.mod input{width:100%;background:rgba(255,255,255,0.06);border:1px solid rgba(255,255,255,0.12);border-radius:9px;padding:10px 13px;color:var(--text);font-family:'Sora',sans-serif;font-size:14px;outline:none}
.mod input:focus{border-color:rgba(91,141,238,0.5)}
.mrow{display:flex;gap:9px;justify-content:flex-end;margin-top:2px}
.bprim{background:var(--accent);border:none;color:#fff;border-radius:9px;padding:9px 20px;cursor:pointer;font-family:'Sora',sans-serif;font-size:14px;font-weight:500;transition:all .2s}
.bprim:hover{background:var(--accent2)}
.bcan{background:rgba(255,255,255,0.07);border:1px solid var(--border);color:var(--text2);border-radius:9px;padding:9px 17px;cursor:pointer;font-family:'Sora',sans-serif;font-size:14px;transition:all .2s}
.bcan:hover{background:rgba(255,255,255,0.12)}
.crow{display:flex;gap:7px;flex-wrap:wrap;margin-top:5px}
.copt{width:26px;height:26px;border-radius:7px;cursor:pointer;border:2px solid transparent;transition:all .2s}
.copt.sel{border-color:#fff;transform:scale(1.18)}
.wpopts{display:flex;gap:8px;flex-wrap:wrap}
.wpopt{border-radius:9px;width:76px;height:46px;cursor:pointer;border:2px solid transparent;display:flex;align-items:center;justify-content:center;font-size:11px;color:rgba(255,255,255,0.8);transition:all .2s}
.wpopt.sel,.wpopt:hover{border-color:var(--accent2)}
.slbl{font-size:11px;color:var(--text3);font-weight:500;letter-spacing:.5px;text-transform:uppercase}
</style>
</head>
<body>
<div id="wp"></div>
<div id="ov"></div>
<div id="app">
  <div id="topbar">
    <div>
      <div id="clock">00:00</div>
      <div id="datep"></div>
    </div>
    <button id="settbtn" onclick="openSettings()" title="Configuración"><i class="ti ti-settings"></i></button>
  </div>

  <div id="hero">
    <div id="hero-logo"></div>
    <div id="hero-name"></div>
  </div>

  <div id="fnav">
    <button class="arrbtn" id="prevbtn" onclick="moveFolder(-1)"><i class="ti ti-chevron-left"></i></button>
    <div id="ftabs"></div>
    <button class="arrbtn" id="nextbtn" onclick="moveFolder(1)"><i class="ti ti-chevron-right"></i></button>
    <button id="addfbtn" onclick="openAddFolder()"><i class="ti ti-plus"></i></button>
  </div>

  <div id="grid"></div>
</div>

<div class="mbg" id="sitemod" style="display:none">
  <div class="mod">
    <h3 id="sitetitle">Agregar sitio</h3>
    <div><label>Nombre</label><input id="sname" type="text" placeholder="Mi sitio"></div>
    <div><label>URL</label><input id="surl" type="text" placeholder="https://..."></div>
    <div><label>Color del ícono</label><div class="crow" id="cpick"></div></div>
    <div class="mrow">
      <button class="bcan" onclick="closeM('sitemod')">Cancelar</button>
      <button class="bprim" onclick="saveSite()">Guardar</button>
    </div>
  </div>
</div>

<div class="mbg" id="foldermod" style="display:none">
  <div class="mod">
    <h3>Nueva carpeta</h3>
    <div><label>Nombre</label><input id="fname" type="text" placeholder="Trabajo, Redes..."></div>
    <div>
      <label>URL del logo (opcional)</label>
      <input id="flogo" type="url" placeholder="https://ecosia.org/favicon.ico">
      <div style="font-size:11px;color:var(--text3);margin-top:4px">Tip: usá /favicon.ico de cualquier sitio</div>
    </div>
    <div class="mrow">
      <button class="bcan" onclick="closeM('foldermod')">Cancelar</button>
      <button class="bprim" onclick="saveFolder()">Crear</button>
    </div>
  </div>
</div>

<div class="mbg" id="settmod" style="display:none">
  <div class="mod" style="max-width:470px">
    <h3>Configuración</h3>
    <div>
      <div class="slbl" style="margin-bottom:8px">Fondo</div>
      <div class="wpopts" id="wpopts"></div>
      <div style="margin-top:10px"><label>O pega una URL de imagen</label><input id="wpurl" type="url" placeholder="https://..."></div>
    </div>
    <div>
      <div class="slbl" style="margin-bottom:8px">Carpeta activa</div>
      <div style="display:flex;gap:8px">
        <button class="bcan" style="flex:1" onclick="renameF()"><i class="ti ti-edit"></i> Renombrar</button>
        <button class="bcan" style="flex:1;color:var(--danger)" onclick="deleteF()"><i class="ti ti-trash"></i> Eliminar</button>
      </div>
    </div>
    
    <div style="margin-top:5px;border-top:1px solid rgba(255,255,255,0.08);padding-top:15px">
      <div class="slbl" style="margin-bottom:8px">Sincronización (JSONBin.io)</div>
      <div style="display:flex;gap:6px;margin-bottom:6px">
        <input id="binid_input" type="text" placeholder="ID del Bin de tu otra PC" style="flex:1;font-size:13px">
        <button class="bprim" style="padding:9px 12px;font-size:12px;flex-shrink:0" onclick="linkBin()">Vincular</button>
      </div>
      <button class="bcan" id="cloud_status_btn" style="width:100%;font-size:12px;text-align:center" onclick="createNewBin()">
        <i class="ti ti-cloud-upload"></i> Crear nuevo respaldo en la nube
      </button>
    </div>

    <div class="mrow" style="margin-top:10px">
      <button class="bcan" onclick="closeM('settmod')">Cancelar</button>
      <button class="bprim" onclick="saveSettings()">Guardar</button>
    </div>
  </div>
</div>

<script>
const BIN_API_KEY = '$2a$10$uIhSdvjRfdEJKB8Urx/ifuC65SokiZR4CpBU2YNufwsl1711MzHdm';
const COLS=['#5b8dee','#e05c6a','#4ecb8d','#f0a84a','#c97df0','#f06aab','#4ab8e0','#e0c74a'];
const WPS=[
  {lbl:'Ninguno',val:'none',s:'background:#0d0f14;border:1px solid rgba(255,255,255,0.15)'},
  {lbl:'Azul',val:'g1',s:'background:linear-gradient(135deg,#0d1b3e,#1a3a6e)'},
  {lbl:'Verde',val:'g2',s:'background:linear-gradient(135deg,#0d2e1a,#1a5c35)'},
  {lbl:'Morado',val:'g3',s:'background:linear-gradient(135deg,#1a0d2e,#3d1a6e)'},
  {lbl:'Rojo',val:'g4',s:'background:linear-gradient(135deg,#2e0d0d,#6e1a1a)'},
];
const WPCSS={g1:'linear-gradient(135deg,#0d1b3e,#1a3a6e)',g2:'linear-gradient(135deg,#0d2e1a,#1a5c35)',g3:'linear-gradient(135deg,#1a0d2e,#3d1a6e)',g4:'linear-gradient(135deg,#2e0d0d,#6e1a1a)'};

let st={wallpaper:'none',wpUrl:'',folders:[],fi:0};
let editIdx=null;
let cloudBinId = localStorage.getItem('mipanel_bin_id') || '';

function load(){
  try{const r=localStorage.getItem('mipanel');if(r)st={...st,...JSON.parse(r)};}catch(e){}
  if(!st.folders||!st.folders.length){
    st.folders=[
      {name:'Google',logo:'https://www.google.com/favicon.ico',sites:[
        {name:'Gmail',url:'https://mail.google.com',color:'#e05c6a'},
        {name:'Drive',url:'https://drive.google.com',color:'#f0a84a'},
        {name:'YouTube',url:'https://youtube.com',color:'#e05c6a'},
        {name:'Maps',url:'https://maps.google.com',color:'#4ecb8d'},
        {name:'Translate',url:'https://translate.google.com',color:'#5b8dee'},
      ]},
      {name:'Trabajo',logo:'',sites:[
        {name:'GitHub',url:'https://github.com',color:'#9aa0b4'},
        {name:'Notion',url:'https://notion.so',color:'#e8eaf0'},
      ]},
    ];
  }
  render();
  if(cloudBinId) fetchFromCloud();
}

function save(){
  try{
    localStorage.setItem('mipanel',JSON.stringify(st));
    if(cloudBinId) saveToCloud();
  }catch(e){}
}

async function createNewBin(){
  const btn = document.getElementById('cloud_status_btn');
  btn.disabled = true;
  btn.innerHTML = '<i class="ti ti-loader animate-spin"></i> Creando almacenamiento...';
  try{
    const res = await fetch('https://api.jsonbin.io/v3/b', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'X-Master-Key': BIN_API_KEY,
        'X-Bin-Private': 'true'
      },
      body: JSON.stringify(st)
    });
    const data = await res.json();
    if(data.metadata && data.metadata.id){
      cloudBinId = data.metadata.id;
      localStorage.setItem('mipanel_bin_id', cloudBinId);
      document.getElementById('binid_input').value = cloudBinId;
      alert('¡Respaldo en la nube creado exitosamente!\n\nID del Bin: ' + cloudBinId + '\n\nCopiá este ID y pegalo en la configuración de tu otra PC para mantenerlas sincronizadas.');
    }
  }catch(e){
    alert('Error de conexión al crear el almacenamiento en la nube.');
  }
  btn.disabled = false;
  btn.innerHTML = '<i class="ti ti-cloud-upload"></i> Crear nuevo respaldo en la nube';
}

async function fetchFromCloud(){
  try{
    const res = await fetch(`https://api.jsonbin.io/v3/b/${cloudBinId}/latest`, {
      headers: { 'X-Master-Key': BIN_API_KEY }
    });
    const data = await res.json();
    if(data.record){
      st = data.record;
      localStorage.setItem('mipanel', JSON.stringify(st));
      render();
    }
  }catch(e){ console.log('Error al traer datos de la nube'); }
}

async function saveToCloud(){
  try{
    await fetch(`https://api.jsonbin.io/v3/b/${cloudBinId}`, {
      method: 'PUT',
      headers: {
        'Content-Type': 'application/json',
        'X-Master-Key': BIN_API_KEY
      },
      body: JSON.stringify(st)
    });
  }catch(e){ console.log('Error al guardar datos en la nube'); }
}

function linkBin(){
  const inputVal = document.getElementById('binid_input').value.trim();
  if(!inputVal){ alert('Por favor, ingresá un ID válido.'); return; }
  if(confirm('¿Vincular este ID? Esto reemplazará la lista actual con los datos guardados en ese Bin.')){
    cloudBinId = inputVal;
    localStorage.setItem('mipanel_bin_id', cloudBinId);
    fetchFromCloud();
    alert('¡Sincronización vinculada con éxito!');
  }
}

function gf(){return st.folders[st.fi]||st.folders;}
function render(){applyWP();renderHero();renderTabs();renderGrid();updArr();}

function applyWP(){
  const el=document.getElementById('wp');
  if(st.wpUrl){el.style.backgroundImage=`url(${st.wpUrl})`;el.style.background='';}
  else if(WPCSS[st.wallpaper]){el.style.backgroundImage='none';el.style.background=WPCSS[st.wallpaper];}
  else{el.style.background='';el.style.backgroundImage='none';}
}

function renderHero(){
  const f=gf();if(!f)return;
  const wrap=document.getElementById('hero-logo');
  if(f.logo){wrap.innerHTML=`<img src="${f.logo}" style="width:56px;height:56px;border-radius:12px;object-fit:contain" onerror="this.outerHTML='<i class=\\'ti ti-folder\\' style=\\'font-size:48px;color:var(--text3)\\'></i>'">`;}
  else{wrap.innerHTML=`<i class="ti ti-folder" style="font-size:48px;color:var(--text3)"></i>`;}
  document.getElementById('hero-name').textContent=f.name;
}

function renderTabs(){
  const c=document.getElementById('ftabs');c.innerHTML='';
  st.folders.forEach((f,i)=>{
    const t=document.createElement('div');
    t.className='ftab'+(i===st.fi?' active':'');
    t.innerHTML=f.logo?`<img src="${f.logo}" onerror="this.style.display='none'"><span>${f.name}</span>`:`<i class="ti ti-folder"></i><span>${f.name}</span>`;
    t.onclick=()=>{st.fi=i;render();};
    c.appendChild(t);
  });
}

function updArr(){
  document.getElementById('prevbtn').disabled=st.fi===0;
  document.getElementById('nextbtn').disabled=st.fi>=st.folders.length-1;
}

function moveFolder(d){const n=st.fi+d;if(n>=0&&n<st.folders.length){st.fi=n;render();}}
function fav(url){try{return`https://www.google.com/s2/favicons?domain=${new URL(url).hostname}&sz=64`;}catch(e){return'';}}

function renderGrid(){
  const g=document.getElementById('grid');g.innerHTML='';
  const f=gf();if(!f)return;
  f.sites.forEach((s,i)=>{
    const c=document.createElement('div');c.className='scard';
    const fv=fav(s.url);
    c.innerHTML=`<div class="cacts"><button class="cbtn" onclick="editSite(event,${i})"><i class="ti ti-edit"></i></button><button class="cbtn del" onclick="delSite(event,${i})"><i class="ti ti-trash"></i></button></div>`
      +(fv?`<img src="${fv}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="sfb" style="display:none;background:${s.color||'#5b8dee'}">${s.name.toUpperCase()}</div>`
          :`<div class="sfb" style="display:flex;background:${s.color||'#5b8dee'}">${s.name.toUpperCase()}</div>`)
      +`<span class="sname">${s.name}</span>`;
    c.onclick=e=>{if(!e.target.closest('.cacts'))window.open(s.url,'_blank');};
    g.appendChild(c);
  });
  const a=document.createElement('div');a.className='addcard';
  a.innerHTML='<i class="ti ti-plus"></i><span>Agregar</span>';
  a.onclick=openAddSite;g.appendChild(a);
}

function openAddSite(){editIdx=null;document.getElementById('sitetitle').textContent='Agregar sitio';document.getElementById('sname').value='';document.getElementById('surl').value='';buildCP(COLS);document.getElementById('sitemod').style.display='flex';}
function editSite(e,i){e.stopPropagation();editIdx=i;const s=gf().sites[i];document.getElementById('sitetitle').textContent='Editar sitio';document.getElementById('sname').value=s.name;document.getElementById('surl').value=s.url;buildCP(s.color||COLS);document.getElementById('sitemod').style.display='flex';}
function buildCP(sel){const c=document.getElementById('cpick');c.innerHTML='';COLS.forEach(col=>{const d=document.createElement('div');d.className='copt'+(col===sel?' sel':'');d.style.background=col;d.onclick=()=>{c.querySelectorAll('.copt').forEach(x=>x.classList.remove('sel'));d.classList.add('sel');};c.appendChild(d);});}
function getCol(){const s=document.querySelector('#cpick .copt.sel');return s?s.style.background:COLS;}
function saveSite(){const name=document.getElementById('sname').value.trim();let url=document.getElementById('surl').value.trim();if(!name||!url)return;if(!/^https?:\/\//i.test(url))url='https://'+url;const color=getCol();const f=gf();if(editIdx!==null){f.sites[editIdx]={name,url,color};}else{f.sites.push({name,url,color});}save();render();closeM('sitemod');}
function delSite(e,i){e.stopPropagation();if(confirm('¿Eliminar este sitio?')){gf().sites.splice(i,1);save();render();}}
function openAddFolder(){document.getElementById('fname').value='';document.getElementById('flogo').value='';document.getElementById('foldermod').style.display='flex';}
function saveFolder(){const name=document.getElementById('fname').value.trim();if(!name)return;st.folders.push({name,logo:document.getElementById('flogo').value.trim(),sites:[]});st.fi=st.folders.length-1;save();render();closeM('foldermod');}

function openSettings(){
  document.getElementById('wpurl').value=st.wpUrl||'';
  document.getElementById('binid_input').value = cloudBinId;
  buildWP();
  document.getElementById('settmod').style.display='flex';
}

function buildWP(){const c=document.getElementById('wpopts');c.innerHTML='';WPS.forEach(w=>{const d=document.createElement('div');d.className='wpopt'+(st.wallpaper===w.val&&!st.wpUrl?' sel':'');d.style.cssText=w.s;d.innerHTML=`<span>${w.lbl}</span>`;d.onclick=()=>{c.querySelectorAll('.wpopt').forEach(x=>x.classList.remove('sel'));d.classList.add('sel');st.wallpaper=w.val;st.wpUrl='';document.getElementById('wpurl').value='';applyWP();};c.appendChild(d);});}
function saveSettings(){const u=document.getElementById('wpurl').value.trim();if(u){st.wpUrl=u;st.wallpaper='none';}save();render();closeM('settmod');}
function renameF(){const f=gf();const n=prompt('Nuevo nombre:',f.name);if(n&&n.trim()){f.name=n.trim();save();render();}}
function deleteF(){if(st.folders.length<=1){alert('Debe haber al menos una carpeta.');return;}if(confirm(`¿Eliminar "${gf().name}"?`)){st.folders.splice(st.fi,1);if(st.fi>=st.folders.length)st.fi=st.folders.length-1;save();render();closeM('settmod');}}
function closeM(id){document.getElementById(id).style.display='none';}

function tick(){const n=new Date();document.getElementById('clock').textContent=`${String(n.getHours()).padStart(2,'0')}:${String(n.getMinutes()).padStart(2,'0')}`;const ds=['Dom','Lun','Mar','Mié','Jue','Vie','Sáb'];const ms=['ene','feb','mar','abr','may','jun','jul','ago','sep','oct','nov','dic'];document.getElementById('datep').textContent=`${ds[n.getDay()]} ${n.getDate()} ${ms[n.getMonth()]}`;}
tick();setInterval(tick,30000);
load();
</script>
</body>
</html>
