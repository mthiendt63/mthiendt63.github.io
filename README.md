# mthiendt63.github.io
not
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport"
content="width=device-width, initial-scale=1, viewport-fit=cover">

<title>Smart Home</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

html,body{
  background:#0f172a;
  font-family:'Poppins',sans-serif;
  color:#fff;
}

.app{
  padding:20px 16px 100px;
}

.header{
  margin-bottom:20px;
}

.header h1{
  font-size:30px;
}

.header p{
  color:#94a3b8;
  margin-top:5px;
}

/* TAB */
.tabs{
  display:flex;
  background:#1e293b;
  border-radius:18px;
  padding:5px;
  margin-bottom:20px;
}

.tab-btn{
  flex:1;
  border:none;
  background:none;
  color:#94a3b8;
  padding:14px;
  border-radius:14px;
  font-size:16px;
  cursor:pointer;
}

.tab-btn.active{
  background:#22c55e;
  color:#fff;
  font-weight:600;
}

.tab-content{
  display:none;
}

.tab-content.active{
  display:block;
}

.container{
  display:flex;
  flex-direction:column;
  gap:14px;
}

.card{
  background:#1e293b;
  border-radius:24px;
  padding:18px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.info{
  display:flex;
  align-items:center;
  gap:14px;
}

.icon{
  width:58px;
  height:58px;
  border-radius:50%;
  background:#475569;
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:26px;
  transition:.3s;
}

.icon.on{
  background:#ffd60a;
  box-shadow:0 0 22px #ffd60a;
}

.text h3{
  font-size:17px;
}

.status{
  color:#94a3b8;
  font-size:14px;
}

.switch{
  position:relative;
  width:58px;
  height:32px;
}

.switch input{
  display:none;
}

.slider{
  position:absolute;
  inset:0;
  background:#334155;
  border-radius:999px;
  cursor:pointer;
  transition:.3s;
}

.slider::before{
  content:'';
  position:absolute;
  width:24px;
  height:24px;
  left:4px;
  top:4px;
  background:#fff;
  border-radius:50%;
  transition:.3s;
}
.fan-box{
  background:#1e293b;
  border-radius:24px;
  padding:20px;
}

.fan-header{
  display:flex;
  align-items:center;
  gap:14px;
  margin-bottom:18px;
}

.fan-controls{
  display:flex;
  flex-direction:column;
  gap:18px;
}

.control-group{
  background:#0f172a;
  border-radius:18px;
  padding:14px;
}

.control-title{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:12px;
}

.control-title h4{
  font-size:15px;
  font-weight:500;
}

.value{
  color:#22c55e;
  font-weight:600;
}

.range{
  width:100%;
  appearance:none;
  height:8px;
  border-radius:999px;
  background:#334155;
  outline:none;
}

.range::-webkit-slider-thumb{
  appearance:none;
  width:22px;
  height:22px;
  border-radius:50%;
  background:#22c55e;
  cursor:pointer;
}

input:checked + .slider{
  background:#22c55e;
}

input:checked + .slider::before{
  transform:translateX(26px);
}
</style>
</head>

<body>

<div class="app">

<div class="header">
<h1>🏠 Smart Home</h1>
<p>Điều khiển thiết bị</p>
</div>

<!-- TAB -->
<div class="tabs">
  <button
    class="tab-btn active"
    onclick="showTab('lights',this)">
    💡 Đèn
  </button>

  <button
    class="tab-btn"
    onclick="showTab('fans',this)">
    🌀 Quạt
  </button>
</div>

<!-- TAB ĐÈN -->
<div
id="lights"
class="tab-content active">

<div class="container">

<div class="card">
<div class="info">
<div class="icon"
id="light1">💡</div>

<div class="text">
<h3>Phòng khách</h3>
<div class="status"
id="status-light1">
Đang tắt
</div>
</div>
</div>

<label class="switch">
<input
type="checkbox"
onclick="toggleDevice('lights',1,this)">
<span class="slider"></span>
</label>
</div>

<div class="card">
<div class="info">
<div class="icon"
id="light2">💡</div>

<div class="text">
<h3>Phòng ngủ</h3>
<div class="status"
id="status-light2">
Đang tắt
</div>
</div>
</div>

<label class="switch">
<input
type="checkbox"
onclick="toggleDevice('lights',2,this)">
<span class="slider"></span>
</label>
</div>

<div class="card">
<div class="info">
<div class="icon"
id="light3">💡</div>

<div class="text">
<h3>Nhà bếp</h3>
<div class="status"
id="status-light3">
Đang tắt
</div>
</div>
</div>

<label class="switch">
<input
type="checkbox"
onclick="toggleDevice('lights',3,this)">
<span class="slider"></span>
</label>
</div>

<div class="card">
<div class="info">
<div class="icon"
id="light4">💡</div>

<div class="text">
<h3>Ban công</h3>
<div class="status"
id="status-light4">
Đang tắt
</div>
</div>
</div>

<label class="switch">
<input
type="checkbox"
onclick="toggleDevice('lights',4,this)">
<span class="slider"></span>
</label>
</div>

</div>
</div>

<!-- TAB QUẠT -->
<!-- TAB QUẠT -->
<div
id="fans"
class="tab-content">

<div class="container">

<!-- QUẠT 1 -->
<div class="fan-box">

<div class="fan-header">
<div class="icon on">
🌀
</div>

<div class="text">
<h3>Quạt 1</h3>
<div class="status">
Điều khiển quạt
</div>
</div>
</div>

<div class="fan-controls">

<!-- TỐC ĐỘ -->
<div class="control-group">

<div class="control-title">
<h4>Tốc độ</h4>

<span
class="value"
id="speedValue1">
1
</span>
</div>

<input
type="range"
min="1"
max="12"
value="1"
class="range"
oninput="
updateSpeed(1,this.value)"
>

</div>

<!-- ĐẢO -->
<div class="control-group">

<div class="control-title">
<h4>Đảo gió</h4>

<label class="switch">
<input
type="checkbox"
onchange="
toggleSwing(1,this.checked)">
<span class="slider"></span>
</label>

</div>

</div>

<!-- TIMER -->
<div class="control-group">

<div class="control-title">
<h4>Timer</h4>

<span
class="value"
id="timerValue1">
0 giờ
</span>

</div>

<input
type="range"
min="0"
max="12"
value="0"
class="range"
oninput="
updateTimer(1,this.value)"
>

</div>

</div>
</div>

<!-- QUẠT 2 -->
<div class="fan-box">

<div class="fan-header">
<div class="icon on">
🌀
</div>

<div class="text">
<h3>Quạt 2</h3>
<div class="status">
Điều khiển quạt
</div>
</div>
</div>

<div class="fan-controls">

<!-- TỐC ĐỘ -->
<div class="control-group">

<div class="control-title">
<h4>Tốc độ</h4>

<span
class="value"
id="speedValue2">
1
</span>

</div>

<input
type="range"
min="1"
max="12"
value="1"
class="range"
oninput="
updateSpeed(2,this.value)"
>

</div>

<!-- ĐẢO -->
<div class="control-group">

<div class="control-title">
<h4>Đảo gió</h4>

<label class="switch">
<input
type="checkbox"
onchange="
toggleSwing(2,this.checked)">
<span class="slider"></span>
</label>

</div>

</div>

<!-- TIMER -->
<div class="control-group">

<div class="control-title">
<h4>Timer</h4>

<span
class="value"
id="timerValue2">
0 giờ
</span>

</div>

<input
type="range"
min="0"
max="12"
value="0"
class="range"
oninput="
updateTimer(2,this.value)"
>

</div>

</div>
</div>

</div>
</div>

<script type="module">

import {
initializeApp
}
from
"https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";

import {
getDatabase,
ref,
set,
onValue
}
from
"https://www.gstatic.com/firebasejs/10.12.2/firebase-database.js";

const firebaseConfig={
apiKey:"AIzaSyCgeR15MWy_9j2X1NiE677NLgBNr6AFCkQ",
authDomain:
"control-device-nhim-house.firebaseapp.com",
databaseURL:
"https://control-device-nhim-house-default-rtdb.asia-southeast1.firebasedatabase.app",
projectId:
"control-device-nhim-house"
};

const app=
initializeApp(firebaseConfig);

const db=
getDatabase(app);

// TAB
window.showTab=
function(id,btn){

document
.querySelectorAll(
'.tab-content'
)
.forEach(
x=>x.classList.remove('active')
);

document
.getElementById(id)
.classList.add('active');

document
.querySelectorAll(
'.tab-btn'
)
.forEach(
x=>x.classList.remove('active')
);

btn.classList.add('active');
};

// TOGGLE
window.toggleDevice=
function(type,id,checkbox){

const value=
checkbox.checked;

const key=
type==='lights'
? 'light'
: 'fan';

set(
ref(
db,
`${type}/${key}${id}`
),
value
);
};

// UPDATE UI
function updateUI(
type,
id,
isOn
){

const key=
type==='lights'
? 'light'
: 'fan';

document
.getElementById(
`${key}${id}`
)
.classList.toggle(
'on',
isOn
);

document
.getElementById(
`status-${key}${id}`
)
.textContent=
isOn
? 'Đang bật'
: 'Đang tắt';
}

// REALTIME
['lights','fans']
.forEach(type=>{

const total=
type==='lights'
? 4
: 2;

for(
let i=1;
i<=total;
i++
){

const key=
type==='lights'
? 'light'
: 'fan';

onValue(

ref(
db,
`feedback/${key}${i}`
),

snapshot=>{

const value=
!!snapshot.val();

updateUI(
type,
i,
value
);

document
.querySelectorAll(
'#'+type+
' input[type="checkbox"]'
)[i-1]
.checked=
value;
}
);
}
});
// ===== FAN UI =====

window.updateSpeed =
function(id,value){

document
.getElementById(
`speedValue${id}`
)
.textContent =
value;
set(ref(db,`fans/fan${id}/speed`), Number(value));
};

window.toggleSwing =
function(id,state){

set(
ref(
db,
`fans/fan${id}/swing`
),
state
);
};

window.updateTimer =
function(id,value){

document
.getElementById(
`timerValue${id}`
)
.textContent =
value + " giờ";

set(
ref(
db,
`fans/fan${id}/timer`
),
Number(value)
);
};
for(let i=1;i<=2;i++)
{
  onValue(
    ref(db,`fans/fan${i}`),
    snapshot=>{

      const data =
        snapshot.val();

      if(!data)
        return;

      // speed
      document
      .querySelectorAll(
        '#fans .range'
      )[(i-1)*2]
      .value =
      data.speed || 1;

      document
      .getElementById(
        `speedValue${i}`
      )
      .textContent =
      data.speed || 1;

      // timer
      document
      .querySelectorAll(
        '#fans .range'
      )[(i-1)*2+1]
      .value =
      data.timer || 0;

      document
      .getElementById(
        `timerValue${i}`
      )
      .textContent =
      (data.timer || 0)
      + " giờ";

      // swing
      document
      .querySelectorAll(
        '#fans input[type="checkbox"]'
      )[i-1]
      .checked =
      !!data.swing;
    }
  );
}
</script>

</body>
</html>
