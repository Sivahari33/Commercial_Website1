# EX 02 Commercial Website
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
~~~

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NovaCart - Online Shopping</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Navigation Bar -->
    <header>
        <nav class="navbar">
            <h2 class="logo">SIVAHARI
            
            </h2>

            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#footer">Contact</a></li>
            </ul>

            <a href="#products" class="cart">Shop Now</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Discover Your Style</h1>
            <p>Find the best products at amazing prices.</p>
            <a href="#products" class="btn">Explore Products</a>
        </div>
    </section>

    <!-- Categories -->
    <section class="categories" id="categories">
        <h2>Shop By Category</h2>

        <div class="category-container">
            <div class="category">👕 Fashion</div>
            <div class="category">📱 Electronics</div>
            <div class="category">⌚ Accessories</div>
            <div class="category">👟 Footwear</div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <h2>Featured Products</h2>

        <div class="product-container">

            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500"
                     alt="Wrist Watch">
                <h3>Classic Watch</h3>
                <p>Stylish wrist watch for everyday use.</p>
                <h4>₹1,499</h4>
                <button>Buy Now</button>
            </div>

            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500"
                     alt="Headphones">
                <h3>Wireless Headphones</h3>
                <p>Enjoy high-quality sound anywhere.</p>
                <h4>₹2,499</h4>
                <button>Buy Now</button>
            </div>

            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500"
                     alt="Sports Shoes">
                <h3>Sports Shoes</h3>
                <p>Comfortable shoes for daily activities.</p>
                <h4>₹1,999</h4>
                <button>Buy Now</button>
            </div>

            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f?w=500"
                     alt="Camera">
                <h3>Digital Camera</h3>
                <p>Capture your beautiful moments.</p>
                <h4>₹8,999</h4>
                <button>Buy Now</button>
            </div>

        </div>
    </section>

    <!-- Footer -->
    <footer id="footer">
        <h2>NovaCart</h2>
        <p>Your one-stop destination for online shopping.</p>

        <div class="student-details">
            <p>Name: Sivaharibalan Karthikeyan</p>
            <p>Register Number: 212224220103

            </p>
        </div>

        <p class="copyright">
            © 2026 NovaCart. All Rights Reserved.
        </p>
    </footer>

</body>
</html>


~~~
~~~css

/* General Styling */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

html {
    scroll-behavior: smooth;
}

body {
    background-color: #f5f6fa;
}

/* Navigation Bar */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 8%;
    background-color: #17172e;
    color: white;
    flex-wrap: wrap;
    gap: 15px;
}

.logo {
    color: #ffb703;
    font-size: 28px;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 30px;
}

.nav-links a {
    color: white;
    text-decoration: none;
    font-size: 16px;
}

.nav-links a:hover {
    color: #ffb703;
}

.cart {
    background-color: #ffb703;
    color: #17172e;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
}

/* Hero Section */
.hero {
    min-height: 350px;
    background: linear-gradient(
        rgba(23, 23, 46, 0.75),
        rgba(23, 23, 46, 0.75)
    ), url("https://images.unsplash.com/photo-1441986300917-64674bd600d8?w=1400");
    background-size: cover;
    background-position: center;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;
    padding: 40px 20px;
}

.hero-content h1 {
    font-size: 45px;
    margin-bottom: 15px;
}

.hero-content p {
    font-size: 18px;
    margin-bottom: 25px;
}

.btn {
    display: inline-block;
    background-color: #ffb703;
    color: #17172e;
    padding: 12px 25px;
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
}

/* Categories */
.categories {
    padding: 45px 8%;
    text-align: center;
}

.categories h2,
.products h2 {
    font-size: 28px;
    margin-bottom: 30px;
    color: #17172e;
}

.category-container {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.category {
    background-color: white;
    padding: 25px 35px;
    border-radius: 10px;
    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    font-weight: bold;
    flex: 1 1 180px;
}

/* Products */
.products {
    padding: 45px 8%;
    text-align: center;
}

.product-container {
    display: flex;
    justify-content: center;
    align-items: stretch;
    gap: 25px;
    flex-wrap: wrap;
}

.product-card {
    background-color: white;
    width: 240px;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 3px 12px rgba(0,0,0,0.1);

    display: flex;
    flex-direction: column;
    align-items: center;
}

.product-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: 8px;
}

.product-card h3 {
    margin: 15px 0 8px;
}

.product-card p {
    color: #666;
    font-size: 14px;
    margin-bottom: 12px;
}

.product-card h4 {
    color: #e76f00;
    font-size: 20px;
    margin-bottom: 15px;
}

.product-card button {
    background-color: #17172e;
    color: white;
    border: none;
    padding: 10px 25px;
    border-radius: 5px;
    cursor: pointer;
    margin-top: auto;
}

.product-card button:hover {
    background-color: #ffb703;
    color: #17172e;
}

/* Footer */
footer {
    background-color: #17172e;
    color: white;
    text-align: center;
    padding: 35px 15px;
}

footer h2 {
    color: #ffb703;
    margin-bottom: 10px;
}

.student-details {
    margin: 20px 0;
    line-height: 2;
}

.copyright {
    border-top: 1px solid #555;
    padding-top: 15px;
    font-size: 14px;
}

/* Responsive Design */
@media (max-width: 768px) {

    .navbar {
        flex-direction: column;
    }

    .nav-links {
        flex-wrap: wrap;
        justify-content: center;
        gap: 15px;
    }

    .hero-content h1 {
        font-size: 32px;
    }

    .product-card {
        width: 45%;
        min-width: 200px;
    }
}

@media (max-width: 480px) {

    .nav-links {
        flex-direction: column;
        text-align: center;
    }

    .product-card {
        width: 100%;
    }

    .hero-content h1 {
        font-size: 27px;
    }

    .category {
        flex-basis: 100%;
    }
}


~~~
## OUTPUT


<img width="1911" height="960" alt="image" src="https://github.com/user-attachments/assets/f984d0b0-250b-4177-932f-7627c9c40e0e" />


<img width="1907" height="1027" alt="image" src="https://github.com/user-attachments/assets/c9492068-ee1b-40e0-9467-d7cff4d41d3c" />



## RESULT
The program for creating commercial website using CSS Flexbox is executed successfully.
