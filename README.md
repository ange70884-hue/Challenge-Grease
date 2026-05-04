
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
            margin-bottom: 30px;
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
            width: 240px; 
            display: inline-block;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        button { 
            background: #007bff; 
            color: white; 
            border: none; 
            padding: 12px 20px; 
            margin: 8px 5px; 
            cursor: pointer; 
            border-radius: 6px; 
            font-size: 16px;
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
    </style>
</head>
<body>
    <h1>Challenge Grease Shop</h1>

    <div class="products">
        <div class="product">
            <img src="challenge-grease.jpg" width="180" alt="Challenge Grease 3oz">
            <h3>Challenge Grease 3oz</h3>
            <p><strong>$8.00</strong></p>
            <button onclick="addToCart('Challenge Grease 3oz', 29.99)">Add to Cart</button>
        </div>

        <div class="product">
            <img src="challenge-grease-2.jpg" width="180" alt="2x Challenge Grease">
            <h3>2x Challenge Grease 3oz</h3>
            <p><strong>$15.00</strong></p>
            <button onclick="addToCart('2x Challenge Grease 3oz', 49.99)">Add to Cart</button>
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
        <button onclick="completeOrder()">Place Order</button>
    </div>

    <div id="track-order" style="display:none; margin-top:30px; padding:25px; background:white; border-radius:12px; max-width:600px; margin-left:auto; margin-right:auto;">
        <h2>Track Your Order</h2>
        <p>Order Number: <strong>#GC-748291</strong></p>
        <p>Status: <strong>Shipped - Expected delivery in 3-5 days</strong></p>
        <button onclick="alert('Tracking link opened in new tab')">Track Package</button>
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
