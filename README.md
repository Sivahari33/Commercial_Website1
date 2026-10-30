# EX 02 Commercial Website
## Date: 30.10.2026
## AKASH G - 212224100004
## AIM
To create a commercial website using CSS Flexbox.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for Homepage, Products / Services, About Us, Contact Details and User Account.

### STEP 5
Include social media links at the footer with copyright information.

### STEP 6
Define global styles for fonts, colors, and layout.

### STEP 7
Style the header, navigation bar, and sections.

### STEP 8
Use Flexbox for layout design.

### STEP 9
Add hover effects and transitions for interactivity.

### STEP 10
Add Images and Media.

### STEP 11
Use optimized images for a professional look.

### STEP 12
Open the HTML file in a browser to check layout and functionality.

### STEP 13
Fix styling issues and refine content placement.

### STEP 14
Deploy the website.

### STEP 15
Upload to GitHub Pages for free hosting.

## PROGRAM
~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AKASAM | Skincare Essentials</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <div class="logo">AKASH G</div>
        <nav>
            <a href="#home">Home</a>
            <a href="#products">Products</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
            <button class="cart-btn" onclick="openCart()">
                Cart (<span id="cart-count">0</span>)
            </button>
        </nav>
    </header>

    <!-- The generated banner already contains its own text and button. -->
    <section class="hero" id="home" aria-label="AKASAM skincare banner"></section>

    <section class="products" id="products">
        <div class="heading">
            <h2>The AKASAM Essentials</h2>
            <p>Simple. Effective. Everyday Skincare.</p>
        </div>

        <div class="product-container">
            <article class="card">
                <img src="akasam_sunscreen.jpg" alt="AKASAM Sunscreen">
                <div class="card-content">
                    <h3>AKASAM Sunscreen</h3>
                    <p>SPF 50+ | Daily Sun Protection</p>
                    <div class="price">₹499</div>
                    <div class="card-buttons">
                        <button class="add-btn" onclick="addToCart('AKASAM Sunscreen', 499)">Add to Cart</button>
                        <button class="buy-btn" onclick="buyNow('AKASAM Sunscreen', 499)">Buy Now</button>
                    </div>
                </div>
            </article>

            <article class="card">
                <img src="akasam_moisturiser.jpg" alt="AKASAM Moisturiser">
                <div class="card-content">
                    <h3>AKASAM Moisturiser</h3>
                    <p>Deep Hydration for Soft Skin</p>
                    <div class="price">₹399</div>
                    <div class="card-buttons">
                        <button class="add-btn" onclick="addToCart('AKASAM Moisturiser', 399)">Add to Cart</button>
                        <button class="buy-btn" onclick="buyNow('AKASAM Moisturiser', 399)">Buy Now</button>
                    </div>
                </div>
            </article>

            <article class="card">
                <img src="akasam_lip_balm.jpg" alt="AKASAM Lip Balm">
                <div class="card-content">
                    <h3>AKASAM Lip Balm</h3>
                    <p>Daily Moisture for Soft Lips</p>
                    <div class="price">₹199</div>
                    <div class="card-buttons">
                        <button class="add-btn" onclick="addToCart('AKASAM Lip Balm', 199)">Add to Cart</button>
                        <button class="buy-btn" onclick="buyNow('AKASAM Lip Balm', 199)">Buy Now</button>
                    </div>
                </div>
            </article>
        </div>
    </section>

    <section class="about" id="about">
        <h2>About AKASAM</h2>
        <p>
            AKASAM believes skincare should be simple, accessible and effective.
            Our collection focuses on everyday essentials designed to make
            your skincare routine effortless.
        </p>
    </section>

    <section class="contact" id="contact">
        <h2>Get In Touch</h2>
        <p>Have questions or feedback? We'd love to hear from you.</p>
        <a class="primary-btn" href="mailto:akashgans07@gmail.com">Contact Us</a>
    </section>

    <footer>
        <h3>AKASH G</h3>
        <p>© 2026 AKASAM. All Rights Reserved.</p>
        <p>Founded by AKASH G</p>
    </footer>

    <aside class="cart-panel" id="cart-panel" aria-label="Shopping cart">
        <div class="cart-heading">
            <h2>Your Cart</h2>
            <button class="close-btn" onclick="closeCart()" aria-label="Close cart">✕</button>
        </div>
        <div id="cart-items">Your cart is empty.</div>
        <div class="cart-total" id="cart-total">Total: ₹0</div>
        <button class="checkout-btn" onclick="checkout()">Proceed to Checkout</button>
    </aside>

    <script>
        let cart = [];

        function addToCart(name, price) {
            const item = cart.find(product => product.name === name);

            if (item) {
                item.quantity++;
            } else {
                cart.push({ name, price, quantity: 1 });
            }

            updateCart();
            alert(name + " added to cart!");
        }

        function updateCart() {
            const count = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById("cart-count").textContent = count;

            const container = document.getElementById("cart-items");
            container.innerHTML = "";

            if (cart.length === 0) {
                container.textContent = "Your cart is empty.";
            }

            cart.forEach((item, index) => {
                const row = document.createElement("div");
                row.className = "cart-item";

                const details = document.createElement("div");
                details.textContent = `${item.name} — ₹${item.price} × ${item.quantity}`;

                const controls = document.createElement("div");

                const minus = document.createElement("button");
                minus.textContent = "−";
                minus.setAttribute("aria-label", "Decrease quantity");
                minus.onclick = () => changeQuantity(index, -1);

                const plus = document.createElement("button");
                plus.textContent = "+";
                plus.setAttribute("aria-label", "Increase quantity");
                plus.onclick = () => changeQuantity(index, 1);

                const remove = document.createElement("button");
                remove.textContent = "Remove";
                remove.onclick = () => removeItem(index);

                controls.append(minus, plus, remove);
                row.append(details, controls);
                container.appendChild(row);
            });

            const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
            document.getElementById("cart-total").textContent = "Total: ₹" + total;
        }

        function changeQuantity(index, amount) {
            cart[index].quantity += amount;
            if (cart[index].quantity <= 0) {
                cart.splice(index, 1);
            }
            updateCart();
        }

        function removeItem(index) {
            cart.splice(index, 1);
            updateCart();
        }

        function openCart() {
            document.getElementById("cart-panel").style.display = "block";
        }

        function closeCart() {
            document.getElementById("cart-panel").style.display = "none";
        }

        function buyNow(name, price) {
            addToCart(name, price);
            openCart();
        }

        function checkout() {
            if (cart.length === 0) {
                alert("Your cart is empty!");
                return;
            }

            const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
            alert(
                "Thank you for choosing AKASAM!\n" +
                "Your demo order total is ₹" + total +
                ". No payment has been processed."
            );
        }
    </script>
</body>
</html>

~~~
~~~css
/* GENERAL */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    scroll-behavior: smooth;
}

body {
    font-family: Arial, sans-serif;
    background: #faf9f6;
    color: #20352a;
}

/* HEADER */
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 7%;
    background: white;
    position: sticky;
    top: 0;
    z-index: 10;
}

.logo {
    font-size: 23px;
    font-weight: bold;
    letter-spacing: 2px;
}

nav {
    display: flex;
    align-items: center;
    gap: 28px;
}

nav a {
    text-decoration: none;
    color: #20352a;
}

nav a:hover {
    color: #a47c54;
}

button {
    cursor: pointer;
    border: none;
    border-radius: 4px;
}

.cart-btn,
.primary-btn,
.buy-btn {
    display: inline-block;
    background: #203a2c;
    color: white;
    padding: 13px 22px;
    text-decoration: none;
}

.cart-btn:hover,
.primary-btn:hover,
.buy-btn:hover {
    background: #45634e;
}

/* HERO: generated banner has its own text on the right */
.hero {
    width: 100%;
    min-height: 430px;
    background: url("akasam_hero_reversed.jpg") center center / cover no-repeat;
}

/* PRODUCTS */
.products {
    padding: 65px 7%;
}

.heading {
    text-align: center;
    margin-bottom: 35px;
}

.heading h2 {
    font-family: Georgia, serif;
    font-size: 34px;
    margin-bottom: 10px;
}

.heading p {
    color: #777;
}

.product-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 25px;
}

.card {
    width: 31%;
    min-width: 250px;
    background: white;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 18px #00000012;
    padding-bottom: 20px;
}

.card img {
    width: 100%;
    height: 230px;
    object-fit: cover;
    display: block;
}

.card-content {
    padding: 15px;
}

.card h3 {
    margin-bottom: 10px;
}

.card p {
    color: #777;
    font-size: 14px;
    line-height: 1.5;
}

.price {
    font-size: 21px;
    font-weight: bold;
    margin: 14px 0;
}

.card-buttons {
    display: flex;
    gap: 10px;
}

.card-buttons button {
    flex: 1;
    padding: 12px 5px;
}

.add-btn {
    background: white;
    color: #203a2c;
    border: 1px solid #203a2c;
}

.add-btn:hover {
    background: #e9eee7;
}

/* ABOUT */
.about {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-wrap: wrap;
    gap: 25px;
    background: #e8eddf;
    padding: 55px 8%;
}

.about h2 {
    font-family: Georgia, serif;
    font-size: 30px;
}

.about p {
    max-width: 600px;
    line-height: 1.8;
    color: #555;
}

/* CONTACT */
.contact {
    text-align: center;
    padding: 55px 20px;
}

.contact h2 {
    margin-bottom: 15px;
}

.contact p {
    color: #777;
    margin-bottom: 20px;
}

/* FOOTER */
footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 15px;
    padding: 25px 7%;
    background: #203a2c;
    color: white;
}

/* CART */
.cart-panel {
    display: none;
    position: fixed;
    right: 0;
    top: 0;
    width: 370px;
    max-width: 100%;
    height: 100vh;
    background: white;
    padding: 25px;
    z-index: 20;
    overflow-y: auto;
    box-shadow: -5px 0 20px #0002;
}

.cart-heading {
    display: flex;
    justify-content: space-between;
    margin-bottom: 25px;
}

.close-btn {
    background: none;
    font-size: 25px;
}

.cart-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    padding: 15px 0;
    border-bottom: 1px solid #ddd;
    font-size: 13px;
}

.cart-item button {
    padding: 6px;
    background: #e9eee7;
    margin: 2px;
}

.cart-total {
    font-size: 20px;
    font-weight: bold;
    margin-top: 25px;
}

.checkout-btn {
    width: 100%;
    padding: 14px;
    margin-top: 20px;
    background: #203a2c;
    color: white;
}

.checkout-btn:hover {
    background: #45634e;
}

/* RESPONSIVE DESIGN */
@media (max-width: 700px) {
    header {
        flex-direction: column;
        gap: 18px;
    }

    nav {
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
    }

    .hero {
        min-height: 300px;
        background-position: center;
    }

    .products {
        padding: 45px 15px;
    }

    .card {
        width: 100%;
    }

    .about {
        flex-direction: column;
        text-align: center;
    }

    footer {
        flex-direction: column;
        text-align: center;
    }
}

~~~
## OUTPUT

<img width="1440" height="900" alt="Screenshot 2026-10-30 at 10 48 04 AM" src="https://github.com/user-attachments/assets/3a39a98c-79c2-49c3-852c-aef89e85b6b8" />
<img width="1440" height="900" alt="Screenshot 2026-10-30 at 10 48 24 AM" src="https://github.com/user-attachments/assets/f22f7c69-9b2a-4cf9-a9f5-8a79591d90d0" />
<img width="1440" height="900" alt="Screenshot 2026-10-30 at 10 48 36 AM" src="https://github.com/user-attachments/assets/9b9480a6-9b2f-41cb-b00c-ecde44c8d2a0" />


## RESULT
The program for creating commercial website using CSS Flexbox is executed successfully.
