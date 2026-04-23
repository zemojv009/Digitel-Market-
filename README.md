<!DOCTYPE html>
<html>
<head>
  <title>Digital Investment Platform</title>
  <style>
    body {
      font-family: Arial;
      margin: 0;
      background: #0f2027;
      color: white;
    }

    .center {
      text-align: center;
      margin-top: 80px;
    }

    input, button, select {
      padding: 10px;
      margin: 10px;
      width: 220px;
      border-radius: 5px;
      border: none;
    }

    button {
      background: gold;
      cursor: pointer;
      font-weight: bold;
    }

    .hidden { display: none; }

    .dashboard {
      padding: 20px;
    }

    .card {
      background: rgba(255,255,255,0.1);
      padding: 15px;
      margin: 10px;
      border-radius: 10px;
    }
  </style>
</head>

<body>

<!-- LOGIN -->
<div id="login" class="center">
  <h1>💰 Login</h1>
  <button onclick="googleLogin()">Login with Google</button><br>
  <input type="text" id="phone" placeholder="Enter phone number"><br>
  <button onclick="register()">Register</button>
</div>

<!-- DASHBOARD -->
<div id="dashboard" class="hidden dashboard">
  <h2>Welcome 👋</h2>
  <h3>Balance: Rs <span id="balance">0</span></h3>

  <div class="card">
    <h3>📋 Daily Task</h3>
    <button onclick="earn()">Complete Task (+50 Rs)</button>
  </div>

  <div class="card">
    <h3>💸 Withdrawal</h3>
    <select id="method">
      <option>EasyPaisa</option>
      <option>JazzCash</option>
    </select><br>
    <input type="text" id="withdrawNumber" placeholder="Enter number"><br>
    <button onclick="withdraw()">Request Withdrawal</button>
  </div>

  <div class="card">
    <h3>📈 Investment</h3>
    <select id="investAmount">
      <option value="200">200 → 500</option>
      <option value="300">300 → 600</option>
      <option value="400">400 → 700</option>
      <option value="500">500 → 800</option>
      <option value="600">600 → 900</option>
      <option value="700">700 → 1000</option>
      <option value="800">800 → 1100</option>
      <option value="900">900 → 1200</option>
      <option value="1000">1000 → 1300</option>
    </select><br>
    <button onclick="invest()">Invest</button>
  </div>

</div>

<script>
let balance = 0;

function googleLogin() {
  alert("Google login demo only");
}

function register() {
  let phone = document.getElementById("phone").value;
  if(phone === "") {
    alert("Enter phone number");
    return;
  }
  document.getElementById("login").classList.add("hidden");
  document.getElementById("dashboard").classList.remove("hidden");
}

function earn() {
  balance += 50;
  updateBalance();
}

function withdraw() {
  let num = document.getElementById("withdrawNumber").value;
  
