<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crochet Haven - Handmade Crochet Creations</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #4a4a4a;
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Dancing Script', cursive;
            font-size: 2.2rem;
            color: #d63031;
            text-decoration: none;
            font-weight: 700;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            text-decoration: none;
            color: #4a4a4a;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-menu a:hover {
            color: #d63031;
        }

        .cart-btn {
            background: #d63031;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
        }

        .cart-btn:hover {
            background: #ca2a2e;
            transform: translateY(-2px);
        }

        /* Hero */
        .hero {
            background: linear-gradient(rgba(255,236,210,0.9), rgba(252,182,159,0.9)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><defs><pattern id="yarn" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="50" cy="50" r="3" fill="%23d63031" opacity="0.1"/><path d="M20 20 Q50 80 80 20" stroke="%23ffecd2" stroke-width="2" fill="none"/></pattern></defs><rect width="1200" height="800" fill="url(%23yarn)"/></svg>');
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            margin-top: 80px;
            position: relative;
        }

        .hero-content h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 4.5rem;
            color: #d63031;
            margin-bottom: 1.5rem;
            animation: fadeInUp 1s ease;
        }

        .hero-content p {
            font-size: 1.4rem;
            color: #6c5ce7;
            margin-bottom: 2.5rem;
            max-width: 600px;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .btn {
            display: inline-block;
            background: linear-gradient(45deg, #d63031, #e17055);
            color: white;
            padding: 15px 40px;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(214,48,49,0.3);
            animation: fadeInUp 1s ease 0.4s both;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(214,48,49,0.4);
        }

        /* Sections */
        .section {
            padding: 80px 0;
        }

        .section-title {
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            text-align: center;
            color: #d63031;
            margin-bottom: 3rem;
        }

        /* Products */
        .products {
            background: #fdfcfc;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0,0,0,0.08);
            transition: all 0.4s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
        }

        .product-img {
            height: 280px;
            background: linear-gradient(135deg, #ffecd2, #fcb69f);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: #d63031;
            position: relative;
        }

        .product-img::before {
            content: '';
            position: absolute;
            top: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            background: #d63031;
            border-radius: 50%;
            opacity: 0.1;
        }

        .product-info {
            padding: 2rem;
        }

        .product-title {
            font-size: 1.4rem;
            margin-bottom: 0.8rem;
            color: #2d3436;
        }

        .product-price {
            font-size: 1.8rem;
            color: #d63031;
            font-weight: 700;
            margin-bottom: 1.5rem;
        }

        .buy-btn {
            width: 100%;
            background: linear-gradient(45deg, #00b894, #00cec9);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .buy-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0,184,148,0.4);
        }

        /* About */
        .about {
            background: linear-gradient(135deg, #a29bfe 0%, #6c5ce7 100%);
            color: white;
            text-align: center;
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
        }

        /* Contact */
        .contact {
            background: #fdfcfc;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-top: 3rem;
        }

        .contact-info h3 {
            color: #d63031;
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
            gap: 1rem;
        }

        .contact-item i {
            font-size: 1.5rem;
            color: #00b894;
            width: 40px;
        }

        .contact-form {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: 2px solid #e1e8ed;
            border-radius: 12px;
            font-family: inherit;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #d63031;
            box-shadow: 0 0 0 3px rgba(214,48,49,0.1);
        }

        /* Footer */
        footer {
            background: #2d3436;
            color: white;
            text-align: center;
            padding: 3rem 0 1rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            color: #00b894;
            transform: translateY(-3px);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Mobile */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .hero-content h1 {
                font-size: 3rem;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .section {
                padding: 60px 0;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <a href="#" class="logo">🧶 Crochet Haven</a>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#shop">Shop</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <button class="cart-btn" onclick="showCart()">
                <i class="fas fa-shopping-cart"></i>
                <span id="cartCount">0</span>
            </button>
        </nav>
    </header>

    <!-- Hero -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Crochet Haven</h1>
            <p>Handcrafted with love, every stitch tells a story. Discover unique crochet creations made just for you.</p>
            <a href="#shop" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Shop -->
    <section id="shop" class="products section">
        <div class="container">
            <h2 class="section-title">Featured Collection</h2>
            <div class="products-grid">
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-hat-wizard"></i></div>
                    <div class="product-info">
                        <h3>Cozy Winter Beanie</h3>
                        <div class="product-price">$29</div>
                        <button class="buy-btn" onclick="addToCart('Cozy Winter Beanie', 29)">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-heart"></i></div>
                    <div class="product-info">
                        <h3>Amigurumi Bear</h3>
                        <div class="product-price">$22</div>
                        <button class="buy-btn" onclick="addToCart('Amigurumi Bear', 22)">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-hand-holding-heart"></i></div>
                    <div class="product-info">
                        <h3>Fingerless Gloves</h3>
                        <div class="product-price">$25</div>
                        <button class="buy-btn" onclick="addToCart('Fingerless Gloves', 25)">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-baby-carriage"></i></div>
                    <div class="product-info">
                        <h3>Baby Booties Set</h3>
                        <div class="product-price">$35</div>
                        <button class="buy-btn" onclick="addToCart('Baby Booties Set', 35)">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-mug-hot"></i></div>
                    <div class="product-info">
                        <h3>Coffee Cup Cozy</h3>
                        <div class="product-price">$12</div>
                        <button class="buy-btn" onclick="addToCart('Coffee Cup Cozy', 12)">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-gem"></i></div>
                    <div class="product-info">
                        <h3>Crochet Jewelry</h3>
                        <div class="product-price">$18</div>
                        <button class="buy-btn" onclick="addToCart('Crochet Jewelry', 18)">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About -->
    <section id="about" class="about section">
        <div class="container">
            <h2 class="section-title">About Our Craft</h2>
            <div class="about-content">
                <p style="font-size: 1.3rem; margin-bottom: 2rem;">
                    Every piece is handmade with premium yarns and endless love. From baby gifts to cozy home decor, 
                    we create timeless crochet treasures that bring warmth to every corner of your life.
                </p>
                <p style="font-size: 1.1rem;">
                    Custom orders welcome! Let's create something special together.
                </p>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="contact section">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Ready to start your custom order?</h3>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <span>hello@crochethaven.com</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <span>+1 (555) 123-CROCHET</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Craftsville, Yarn District 12345</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-clock"></i>
                        <span>Mon-Fri 9AM-6PM | Custom orders: 24hr response</span>
                    </div>
                </div>
                <form class="contact-form" onsubmit="submitForm(event)">
                    <div class="form-group">
                        <input type="text" placeholder="Your Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" placeholder="Your Email" required>
                    </div>
                    <div class="form-group">
                        <input type="text" placeholder="What would you like to order?">
                    </div>
                    <div class="form-group">
                        <textarea rows="4" placeholder="Tell us about your dream crochet project..."></textarea>
                    </div>
                    <button type="submit" class="btn" style="width: 100%;">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook-f"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-pinterest"></i></a>
                <a href="#"><i class="fab fa-etsy"></i></a>
            </div>
            <p>&copy; 2024 Crochet Haven. Handmade with ❤️ and lots of yarn. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            });
        });

        // Cart functionality
        let cart = [];
        function addToCart(name, price) {
            cart.push
