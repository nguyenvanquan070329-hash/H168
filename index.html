<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>H168</title>

<style>
body{
  margin:0;
  font-family:Arial;
  background:black;
  color:gold;
  text-align:center;
  overflow-x:hidden;
}

body::before{
  content:"";
  position:fixed;
  width:100%;
  height:100%;
  background:radial-gradient(circle at center, rgba(255,140,0,0.3), black 70%);
  animation: fireMove 5s infinite alternate;
  z-index:-1;
}

@keyframes fireMove{
  from{transform:scale(1);}
  to{transform:scale(1.1);}
}

.logo{
  width:320px;
  max-width:90%;
  margin-top:20px;
  animation: glow 2s infinite alternate;
}

@keyframes glow{
  from{filter:drop-shadow(0 0 10px gold);}
  to{filter:drop-shadow(0 0 35px orange);}
}

.subtitle{
  font-size:20px;
  margin-bottom:30px;
  text-shadow:0 0 10px gold;
}

.card{
  background:rgba(0,0,0,0.6);
  backdrop-filter:blur(10px);
  border:1px solid gold;
  margin:15px auto;
  padding:15px;
  width:300px;
  border-radius:15px;
  box-shadow:0 0 15px rgba(255,215,0,0.4);
}

input{
  padding:10px;
  margin:6px;
  border-radius:5px;
  border:none;
  width:200px;
}

button{
  padding:8px 15px;
  margin:5px;
  background:linear-gradient(to right,gold,orange);
  border:none;
  border-radius:5px;
  cursor:pointer;
  font-weight:bold;
}

button:hover{
  transform:scale(1.05);
}

.admin-btn{
  background:red;
  color:white;
}

.coin{
  position:fixed;
  top:-50px;
  width:25px;
  animation:fall linear infinite;
}

@keyframes fall{
  to{transform:translateY(110vh);}
}
</style>
</head>

<body>

<img src="logo.png" class="logo">
<div class="subtitle">Luôn Đồng Hành Cùng Bạn</div>

<!-- LOGIN -->
<div id="loginPage">
  <div class="card">
    <input id="username" placeholder="Tài khoản"><br>
    <input id="password" type="password" placeholder="Mật khẩu"><br>
    <button onclick="login()">Đăng nhập</button>
    <p id="message"></p>
  </div>
</div>

<!-- USER GAME -->
<div id="dashboard" style="display:none;">
  <h2>🎲 DỰ ĐOÁN LỚN BÉ 🎲</h2>

  <div class="card">
    <p>Số dư: <span id="score">0</span></p>
    <p>Thời gian: <span id="time">45</span>s</p>

    <div style="font-size:60px;margin:15px;">
      <span id="dice1">🎲</span>
      <span id="dice2">🎲</span>
      <span id="dice3">🎲</span>
    </div>

    <button onclick="selectChoice('big')">Chọn LỚN (11-18)</button>
    <button onclick="selectChoice('small')">Chọn BÉ (3-10)</button>

    <p id="result"></p>
  </div>

  <button onclick="logout()">Đăng xuất</button>
</div>

<!-- ADMIN -->
<div id="adminPage" style="display:none;">
  <h2>👑 ADMIN PANEL</h2>
  <div id="userList"></div>
  <button onclick="logout()">Đăng xuất</button>
</div>

<script>

/* ================= USER SYSTEM ================= */

let users = JSON.parse(localStorage.getItem("users"));

if(!users){
  users = [
    {username:"admin", password:"123456", approved:true, role:"admin"},
    {username:"user1", password:"111111", approved:true, role:"user", balance:1000}
  ];
  saveUsers();
}

function saveUsers(){
  localStorage.setItem("users", JSON.stringify(users));
}

let currentUser = null;

function login(){
  let u=username.value;
  let p=password.value;

  let user=users.find(x=>x.username===u && x.password===p);

  if(!user){
    message.innerHTML="Sai tài khoản!";
    return;
  }

  currentUser = user;
  loginPage.style.display="none";

  if(user.role==="admin"){
    adminPage.style.display="block";
    renderUsers();
  }else{
    dashboard.style.display="block";
    if(!currentUser.balance) currentUser.balance=0;
    score.innerText=currentUser.balance;
    updateSessionDisplay();
  }
}

/* ================= ADMIN ================= */

let forcedResult="random";
let sessionCode=generateSessionCode();

function generateSessionCode(){
  return Math.floor(100000 + Math.random()*900000);
}

function renderUsers(){
  let html="";

  html+=`
  <div class="card">
    <p><b>Mã phiên:</b> ${sessionCode}</p>
    <button onclick="setResult('random')">Random</button>
    <button onclick="setResult('big')">Ép LỚN</button>
    <button onclick="setResult('small')">Ép BÉ</button>
  </div>

  <div class="card">
    <p><b>Thêm tài khoản</b></p>
    <input id="newUser" placeholder="Username">
    <input id="newPass" placeholder="Password">
    <button onclick="addUser()">Tạo</button>
  </div>
  `;

  users.forEach((u,i)=>{
    if(u.role==="admin") return;
    if(!u.balance) u.balance=0;

    html+=`
    <div class="card">
      <p><b>${u.username}</b></p>
      <p>Số dư: ${u.balance}</p>
      <input type="number" id="money${i}" placeholder="Nhập tiền">
      <button onclick="giveMoney(${i})">Cấp tiền</button>
      <button class="admin-btn" onclick="deleteUser(${i})">Xóa</button>
    </div>
    `;
  });

  userList.innerHTML=html;
}

function addUser(){
  let u=newUser.value;
  let p=newPass.value;
  if(!u||!p){ alert("Nhập đủ thông tin"); return; }
  if(users.find(x=>x.username===u)){ alert("Đã tồn tại"); return; }

  users.push({username:u,password:p,role:"user",balance:0});
  saveUsers();
  renderUsers();
}

function setResult(type){
  forcedResult=type;
  alert("Ép "+type+" cho phiên "+sessionCode);
}

function giveMoney(i){
  let money=parseInt(document.getElementById("money"+i).value);
  if(!money||money<=0){ alert("Nhập tiền hợp lệ"); return; }
  users[i].balance+=money;
  saveUsers();
  renderUsers();
}

function deleteUser(i){
  if(confirm("Xóa tài khoản?")){
    users.splice(i,1);
    saveUsers();
    renderUsers();
  }
}

function logout(){
  location.reload();
}

/* ================= GAME ================= */

let timeLeft=45;
let selectedChoice=null;
let betAmount=0;
let isWaiting=false;
let history=[];

function updateSessionDisplay(){
  if(!document.getElementById("sessionBox")){
    let div=document.createElement("div");
    div.id="sessionBox";
    div.style.marginTop="10px";
    document.querySelector("#dashboard .card").appendChild(div);
  }

  sessionBox.innerHTML=
  `<b>Mã phiên:</b> ${sessionCode}<br>
   <b>Cửa đã chọn:</b> ${selectedChoice?selectedChoice:"Chưa chọn"}<br>
   ${betAmount>0? "<b>Tiền đã đặt:</b> "+betAmount : ""}`;
}

function selectChoice(type){

  if(isWaiting){ alert("Đang chờ phiên mới"); return; }

  let bet=parseInt(prompt("Nhập tiền cược"));
  if(!bet||bet<=0){ alert("Không hợp lệ"); return; }
  if(bet>currentUser.balance){ alert("Không đủ tiền"); return; }

  if(!selectedChoice){
    selectedChoice=type;
  }

  if(selectedChoice!==type){
    alert("Không đặt ngược cửa");
    return;
  }

  betAmount+=bet;
  currentUser.balance-=bet;
  saveUsers();
  score.innerText=currentUser.balance;
  updateSessionDisplay();
}

function startTimer(){
  const timer=setInterval(()=>{
    timeLeft--;
    time.innerText=timeLeft;

    if(timeLeft<=0){
      clearInterval(timer);
      rollDice();
    }
  },1000);
}

function rollDice(){

  isWaiting=true;

  let d1,d2,d3,total;

  if(forcedResult==="big"){
    d1=6; d2=5; d3=4;
  }else if(forcedResult==="small"){
    d1=1; d2=2; d3=3;
  }else{
    d1=Math.floor(Math.random()*6)+1;
    d2=Math.floor(Math.random()*6)+1;
    d3=Math.floor(Math.random()*6)+1;
  }

  total=d1+d2+d3;

  dice1.innerText=d1;
  dice2.innerText=d2;
  dice3.innerText=d3;

  history.unshift(total);
  if(history.length>10) history.pop();

  if(!document.getElementById("historyBox")){
    let div=document.createElement("div");
    div.id="historyBox";
    div.style.marginTop="15px";
    document.querySelector("#dashboard .card").appendChild(div);
  }

  historyBox.innerHTML=
  "<b>10 phiên gần nhất:</b><br>"+history.join(" | ");

  if(selectedChoice){
    let resultType=total>=11?"big":"small";

    if(selectedChoice===resultType){
      let win=betAmount*2;
      currentUser.balance+=win;
      result.innerText="🎉 Tổng "+total+" - Thắng +"+win;
    }else{
      result.innerText="❌ Tổng "+total+" - Thua";
    }

    saveUsers();
    score.innerText=currentUser.balance;
  }

  setTimeout(resetGame,7000);
}

function resetGame(){
  timeLeft=45;
  selectedChoice=null;
  betAmount=0;
  isWaiting=false;
  forcedResult="random";
  sessionCode=generateSessionCode();

  result.innerText="";
  dice1.innerText="🎲";
  dice2.innerText="🎲";
  dice3.innerText="🎲";

  updateSessionDisplay();
  startTimer();

  if(currentUser.role==="admin"){
    renderUsers();
  }
}

startTimer();

/* ================= COIN EFFECT ================= */

function createCoin(){
  let coin=document.createElement("img");
  coin.src="https://cdn-icons-png.flaticon.com/512/138/138292.png";
  coin.className="coin";
  coin.style.left=Math.random()*100+"vw";
  coin.style.animationDuration=(3+Math.random()*3)+"s";
  document.body.appendChild(coin);
  setTimeout(()=>coin.remove(),6000);
}

setInterval(createCoin,800);

</script>

</body>
</html>
