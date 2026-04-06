<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fan / Membership Card Purchase</title>
<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #1e1e2f, #3a3a6a);
  color: white;
}
header {
  text-align: center;
  padding: 20px;
  font-size: 24px;
  font-weight: bold;
}
header div {margin-top:5px;}
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 20px;
}
.card {
  background: #2a2a40;
  border-radius: 20px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  transition: 0.3s;
}
.card:hover {transform: translateY(-5px);}
.profile-img {width: 90px; height: 90px; border-radius: 50%; border: 3px solid #fff; object-fit: cover;}
h2 {margin: 10px 0 5px;}
p {font-size: 14px; color: #ccc;}
.btn {margin-top: 10px; padding: 8px 18px; border: none; border-radius: 20px; background: #ff4d6d; color: white; cursor: pointer;}
.btn:hover {background: #ff1e4d;}
#cart {background:#2a2a40; padding:15px; border-radius:15px; margin:20px; text-align:center;}
#cart h3{margin-bottom:10px;}
</style>
</head>
<body>

<header>
  <div>🎫 Fan / Membership Card Purchase</div>
  <div style="font-size:16px;">Fan Club: X Japan</div>
  <div style="font-size:14px; color:#ccc;">Artist: Yoshiki</div>
</header>

<div style="text-align:center; margin:10px;">
  Select Country: 
  <select id="country">
    <option value="JP">Japan 🇯🇵</option>
    <option value="BR">Brazil 🇧🇷</option>
  </select>
</div>

<div class="container">

  <!-- Meet & Greet -->
  <div class="card" data-name="Meet & Greet" data-jp="100000" data-br="400">
    <img src="https://via.placeholder.com/100" class="profile-img">
    <h2>Meet & Greet</h2>
    <p>Get a chance to meet Yoshiki in person ❤️</p>
    <button class="btn" onclick="addToCart(this)">Add to Box</button>
  </div>

  <!-- Fan Card -->
  <div class="card" data-name="Fan Card" data-jp="150000" data-br="550">
    <img src="https://via.placeholder.com/100" class="profile-img">
    <h2>Fan Card</h2>
    <p>Official fan identity card 🎫</p>
    <button class="btn" onclick="addToCart(this)">Add to Box</button>
  </div>

  <!-- Membership Card -->
  <div class="card" data-name="Membership Card" data-jp="250000" data-br="750">
    <img src="https://via.placeholder.com/100" class="profile-img">
    <h2>Membership Card</h2>
    <p>Exclusive fan club access 🔥</p>
    <button class="btn" onclick="addToCart(this)">Add to Box</button>
  </div>

  <!-- Gold Card -->
  <div class="card" data-name="Gold Card" data-jp="400000" data-br="1800">
    <img src="https://via.placeholder.com/100" class="profile-img">
    <h2>Gold Card</h2>
    <p>VIP benefits + premium access 👑</p>
    <button class="btn" onclick="addToCart(this)">Add to Box</button>
  </div>

</div>

<div id="cart">
  <h3>Your Box</h3>
  <ul id="cart-items"></ul>
  <button class="btn" onclick="sendOrder()">Send Order via LINE</button>
</div>

<script>
let cart = [];

function addToCart(button){
  const card = button.parentElement;
  const name = card.getAttribute('data-name');
  const country = document.getElementById('country').value;
  const price = country === 'JP' ? card.getAttribute('data-jp') : card.getAttribute('data-br');
  const currency = country === 'JP' ? '¥' : 'R$';

  cart.push({name, price, currency, country});
  updateCart();
}

function updateCart(){
  const cartItems = document.getElementById('cart-items');
  cartItems.innerHTML = '';
  cart.forEach(item => {
    const li = document.createElement('li');
    li.textContent = `${item.name} - ${item.currency}${item.price} (${item.country})`;
    cartItems.appendChild(li);
  });
}

function sendOrder(){
  if(cart.length === 0){ alert("Your box is empty!"); return; }

  let message = "Hello! I want to purchase:\n";
  cart.forEach(item => {
    message += `- ${item.name} (${item.country}) ${item.currency}${item.price}\n`;
  });

  const lineLink = "https://line.me/ti/p/RRNekcxCXC";
  const url = `${lineLink}?text=${encodeURIComponent(message)}`;
  window.open(url, '_blank');
}
</script>

</body>
</html>
