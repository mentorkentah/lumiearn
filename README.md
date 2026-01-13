<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LUMIEARN Dashboard</title>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
:root{
  --primary:#1e5bff;
  --secondary:#6a11cb;
  --bg:#f4f6fb;
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
  font-family:Segoe UI,Roboto,Arial,sans-serif;
}

body{
  background:var(--bg);
  overflow-x:hidden;
}

/* HEADER */
.header{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:70px;
  background:linear-gradient(135deg,var(--secondary),var(--primary));
  display:flex;
  align-items:center;
  justify-content:center;
  z-index:1000;
}

.logo{
  color:#fff;
  font-size:24px;
  font-weight:700;
}

.menu-toggle{
  position:absolute;
  right:15px;
  width:46px;
  height:46px;
  border-radius:12px;
  background:linear-gradient(135deg,var(--secondary),var(--primary));
  display:flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;
}

.menu-toggle span,
.menu-toggle span::before,
.menu-toggle span::after{
  width:22px;
  height:3px;
  background:#fff;
  display:block;
  position:relative;
  transition:.3s;
}

.menu-toggle span::before{content:"";position:absolute;top:-7px;}
.menu-toggle span::after{content:"";position:absolute;top:7px;}

.menu-toggle.active span{background:transparent;}
.menu-toggle.active span::before{transform:rotate(45deg);top:0;}
.menu-toggle.active span::after{transform:rotate(-45deg);top:0;}

/* SIDE MENU */
.menu{
  position:fixed;
  right:-60%;
  top:0;
  width:60%;
  height:100vh;
  background:linear-gradient(135deg,var(--secondary),var(--primary));
  padding:90px 15px 20px;
  transition:.35s;
  z-index:900;
  display:flex;
  flex-direction:column;
}

.menu.active{right:0;}

.menu-item{
  color:#fff;
  text-decoration:none;
  padding:14px;
  border-radius:10px;
  display:flex;
  align-items:center;
  margin-bottom:6px;
}

.menu-item i{margin-right:10px;}

.menu-item.active{
  background:#fff;
  color:#001f7a;
}

.menu-item.logout{
  margin-top:auto;
  background:#b80909;
}

/* CONTENT */
.content-wrapper{
  padding:90px 15px 30px;
}

/* WELCOME */
.welcome{
  background:linear-gradient(135deg,var(--secondary),var(--primary));
  color:#fff;
  padding:22px;
  border-radius:18px;
  margin-bottom:22px;
}

.welcome h2{font-size:22px;margin-bottom:6px;}
.welcome p{font-size:15px;margin-bottom:16px;}

.stats{
  display:flex;
  margin-bottom:18px;
}

.stat{
  flex:1;
  font-size:14px;
}

.stat span{
  display:block;
  font-size:20px;
  font-weight:700;
  margin-top:6px;
}

.stat.expense{
  border-right:2px solid #fff;
  padding-right:20px;
  margin-right:20px;
}

/* BUTTONS */
.action-buttons{
  display:flex;
  gap:14px;
}

.btn{
  flex:1;
  padding:14px;
  border-radius:12px;
  text-align:center;
  text-decoration:none;
  color:#fff;
  font-weight:600;
}

.btn.whatsapp{background:#25D366;}
.btn.download{background:#000;}

/* WALLET CARDS */
.stat-card{
  border-radius:20px;
  padding:22px;
  margin-bottom:16px;
  color:#fff;
  position:relative;
}

.stat-card h2{
  font-size:28px;
  margin:6px 0;
}

.stat-card .subtext{
  font-size:13px;
  opacity:.9;
}

.icon{
  position:absolute;
  right:16px;
  top:50%;
  transform:translateY(-50%);
  width:52px;
  height:52px;
  border-radius:50%;
  background:rgba(255,255,255,.25);
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:22px;
}

/* COLORS */
.green{background:#009933;}
.yellow{background:#ffcc00;color:#000;}
.red{background:#b80909;}
.dark-blue{background:#001f7a;}
.gray{background:#808080;}
</style>
</head>

<body>

<!-- HEADER -->
<div class="header">
  <div class="logo">LUMIEARN</div>
  <div class="menu-toggle" id="menuBtn"><span></span></div>
</div>

<!-- SIDE MENU -->
<div class="menu" id="menu">
  <a class="menu-item active"><i class="fa-solid fa-house"></i>Dashboard</a>
  <a class="menu-item"><i class="fa-solid fa-wallet"></i>Cashout</a>
  <a class="menu-item logout"><i class="fa-solid fa-right-from-bracket"></i>Logout</a>
</div>

<!-- CONTENT -->
<div class="content-wrapper">

  <!-- WELCOME -->
  <div class="welcome">
    <h2>Hello, Lumiearn 👋</h2>
    <p>Your journey to a thousand milestones starts now.</p>

    <div class="stats">
      <div class="stat expense">
        Expenses
        <span>KES 150</span>
      </div>
      <div class="stat">
        Profit
        <span>KES 23,501</span>
      </div>
    </div>

    <div class="action-buttons">
      <a href="#" class="btn whatsapp">Join WhatsApp</a>
      <a href="#" class="btn download">Download App</a>
    </div>
  </div>

  <!-- WALLETS -->
  <div class="stat-card green">
    <h4>Current Balance</h4>
    <h2>KES 6,895</h2>
    <p class="subtext">Withdrawable Balance</p>
    <div class="icon"><i class="fa-solid fa-building-columns"></i></div>
  </div>

  <div class="stat-card yellow">
    <h4>Welcome Bonus</h4>
    <h2>KES 100</h2>
    <p class="subtext">Locked • Use to activate earnings</p>
    <div class="icon"><i class="fa-solid fa-gift"></i></div>
  </div>

  <div class="stat-card red">
    <h4>Total Withdrawn</h4>
    <h2>KES 18,340</h2>
    <p class="subtext">All Time Cashouts</p>
    <div class="icon"><i class="fa-solid fa-sack-dollar"></i></div>
  </div>

  <div class="stat-card dark-blue">
    <h4>Pending Amount</h4>
    <h2>KES 0</h2>
    <p class="subtext">Awaiting Disbursement</p>
    <div class="icon"><i class="fa-solid fa-clock"></i></div>
  </div>

  <div class="stat-card gray">
    <h4>Deposit Wallet</h4>
    <h2>KES 1,500</h2>
    <p class="subtext">Added Funds</p>
    <div class="icon"><i class="fa-solid fa-credit-card"></i></div>
  </div>

</div>

<script>
const menuBtn = document.getElementById("menuBtn");
const menu = document.getElementById("menu");

menuBtn.onclick = () => {
  menu.classList.toggle("active");
  menuBtn.classList.toggle("active");
};
</script>

</body>
</html>
