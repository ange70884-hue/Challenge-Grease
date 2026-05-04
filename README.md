<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Challenge Grease Shop</title>
<style>
body {
font-family: Arial, sans-serif;
margin: 0;
padding: 20px;
background: #f8f8f8;
}
h1 {
text-align: center;
color: #333;
margin-bottom: 10px;
}
.products {
text-align: center;
}
.product {
background: white;
padding: 15px;
margin: 15px;
border-radius: 12px;
text-align: center;
width: 260px;
display: inline-block;
box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
button {
background: #007bff;
color: white;
border: none;
padding: 12px 20px;
margin: 10px 5px;
cursor: pointer;
border-radius: 6px;
font-size: 16px;
}
.description {
font-size: 14px;
color: #555;
line-height: 1.5;
margin: 12px 0;
text-align: left;
}
#cart, #checkout {
margin-top: 40px;
padding: 25px;
background: white;
border-radius: 12px;
max-width: 600px;
margin-left: auto;
margin-right: auto;
}
.footer {
text-align: center;
margin-top: 50px;
padding: 30px;
background: white;
border-radius: 12px;
}
.social a { margin: 0 12px; }
</style>
</head>
<body>

<!-- Logo Section -->
<div style="text-align: center; margin-bottom: 15px;">
<img src="logo.png" alt="Challenge Grease Logo" width="160">
</div>

<h1>Challenge Grease Shop</h1>

<div class="products">
<div class="product">
<img src="challenge-grease.jpg" width="180" alt="Challenge Grease 3oz">
<h3>Challenge Grease 3oz</h3>
<p><strong>$8.00</strong></p>
<p class="description">
Challenge Grease is made from 100% natural ingredients sourced from Ivory Coast in West Africa. This powerful formula effectively treats all types of hair loss and thinning. Most users start seeing visible results within just 3 weeks of regular use.
</p>
<button onclick="addToCart('Challenge Grease 3oz', 8.00)">Add to Cart</button>
</div>

<div class="product">
<img src="challenge-grease-2.jpg" width="180" alt="2x Challenge Grease">
<h3>2x Challenge Grease 3oz</h3>
<p><strong>$15.00</strong></p>
<p class="description">
Challenge Grease is made from 100% natural ingredients sourced from Ivory Coast in West Africa. This powerful formula effectively treats all types of hair loss and thinning. Most users start seeing visible results within just 3 weeks of regular use.
</p>
<button onclick="addToCart('2x Challenge Grease 3oz', 15.00)">Add to Cart</button>
</div>
</div>

<div id="cart">
<h2>Your Cart</h2>
<ul id="cart-items"></ul>
<p><strong>Total: $<span id="total">0</span></strong></p>
<button onclick="showCheckout()">Proceed to Checkout</button>
</div>

<div id="checkout">
<h2>Checkout</h2>
<p><strong>Total: $<span id="checkout-total">0</span></strong></p>

<h3>Shipping Information</h3>
<input type="text" id="name" placeholder="Full Name" style="display:block; margin:8px 0; padding:10px; width:100%;"><br>
<input type="text" id="address" placeholder="Shipping Address" style="display:block; margin:8px 0; padding:10px; width:100%;"><br>

<h3>Billing Information</h3>
<input type="text" id="card" placeholder="Card Number" style="display:block; margin:8px 0; padding:10px; width:100%;"><br>

<div style="display:flex; gap:10px;">
<input type="text" id="expiry" placeholder="MM/YY" style="flex:1; padding:10px;">
<input type="text" id="cvv" placeholder="CVV" style="flex:1; padding:10px;">
</div><br>

<input type="text" id="zip" placeholder="Zip Code" style="display:block; margin:8px 0; padding:10px; width:100%;"><br>
 <div style="margin: 15px 0; text-align: center;">
            <img src="visa-logo.png" width="60" style="margin: 0 10px;">
            <img src="mastercard-logo.png" width="60" style="margin: 0 10px;">
        </div>
<button onclick="completeOrder()">Place Order</button>
</div>

<div id="track-order" style="display:none; margin-top:30px; padding:25px; background:white; border-radius:12px; max-width:600px; margin-left:auto; margin-right:auto;">
<h2>Track Your Order</h2>
<p>Order Number: <strong>#GC-748291</strong></p>
<p>Status: <strong>Shipped - Expected delivery in 3-5 days</strong></p>
<button onclick="alert('Tracking link opened in new tab')">Track Package</button>
</div>

<div class="footer">
<h2>Contact Us</h2>
<div class="social">
<a href="https://instagram.com/yourusername" target="_blank">
<img src="instagram-logo.png" width="45" alt="Instagram">
</a>
<a href="https://tiktok.com/@yourusername" target="_blank">
<img src="tiktok-logo.png" width="45" alt="TikTok">
</a>
<a href="https://facebook.com/yourpage" target="_blank">
<img src="facebook-logo.png" width="45" alt="Facebook">
</a>
<a href="mailto:your.email@gmail.com">
<img src="gmail-logo.png" width="45" alt="Email">
</a>
</div>
<p style="margin-top:15px;">Follow us for updates & promotions</p>
</div>

<script>
let cart = [];
function addToCart(name, price) {
cart.push({name, price});
updateCart();
}
function updateCart() {
let items = document.getElementById("cart-items");
items.innerHTML = "";
let total = 0;
cart.forEach(item => {
items.innerHTML += `<li>${item.name} — $${item.price}</li>`;
total += item.price;
});
document.getElementById("total").textContent = total.toFixed(2);
document.getElementById("checkout-total").textContent = total.toFixed(2);
}
function showCheckout() {
document.getElementById("checkout").style.display = "block";
}
function completeOrder() {
alert("✅ Order placed successfully! Thank you for shopping at Challenge Grease.");
document.getElementById("checkout").style.display = "none";
document.getElementById("track-order").style.display = "block";
cart = [];
updateCart();
}
</script>
</body>
</html>

