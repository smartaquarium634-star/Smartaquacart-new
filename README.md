<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SMART AQUA CART | Premium Fishes & Accessories</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* === CSS VARIABLES & THEME === */
        :root {
            --primary: #0F9D58;
            --aqua: #00C9FF;
            --ocean: #007CF0;
            --gold: #FFD54F;
            --ivory: #FFFDF5;
            --coral: #FF8A65;
            --purple: #7B61FF;
            --text-dark: #1a1a1a;
            --text-light: #f5f5f5;
            --glass-bg: rgba(255, 255, 255, 0.1);
            --glass-border: rgba(255, 255, 255, 0.2);
            --glass-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.15);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(-45deg, #013A20, #001F3F, #005C53, #1A1A1A);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Animated Bubbles Background */
        .bubbles {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1; pointer-events: none; overflow: hidden;
        }
        .bubble {
            position: absolute;
            bottom: -20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: rise infinite ease-in;
        }
        @keyframes rise {
            0% { transform: translateY(0) scale(1); opacity: 0; }
            50% { opacity: 0.5; }
            100% { transform: translateY(-100vh) scale(1.5); opacity: 0; }
        }

        /* === HEADER === */
        header {
            position: fixed;
            top: 0; left: 0; width: 100%;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--glass-border);
            z-index: 1000;
            transition: all 0.3s ease;
        }
        .header-content {
            max-width: 1200px; margin: 0 auto;
            padding: 15px 20px;
            display: flex; justify-content: space-between; align-items: center;
        }
        .logo-area { display: flex; flex-direction: column; }
        .logo-title {
            font-size: 1.5rem; font-weight: 700;
            background: linear-gradient(45deg, var(--aqua), var(--primary));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        .logo-tagline { font-size: 0.7rem; color: var(--gold); letter-spacing: 1px; }
        
        .header-controls { display: flex; align-items: center; gap: 15px; }
        .search-bar {
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            padding: 8px 15px; border-radius: 20px;
            color: white; outline: none; width: 200px;
            transition: width 0.3s;
        }
        .search-bar:focus { width: 250px; background: rgba(255,255,255,0.2); }
        .search-bar::placeholder { color: #ccc; }
        
        .cart-icon {
            position: relative; cursor: pointer;
            font-size: 1.5rem; padding: 10px;
            color: white; transition: transform 0.2s;
        }
        .cart-icon:hover { transform: scale(1.1); color: var(--aqua); }
        .cart-badge {
            position: absolute; top: 0; right: 0;
            background: var(--coral); color: white;
            font-size: 0.75rem; font-weight: bold;
            height: 20px; width: 20px; border-radius: 50%;
            display: flex; justify-content: center; align-items: center;
            animation: popIn 0.3s;
        }

        /* === HERO SECTION === */
        .hero {
            padding: 120px 20px 60px;
            text-align: center;
            max-width: 1200px; margin: 0 auto;
        }
        .hero-glass {
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            border-radius: 24px; padding: 40px 20px;
            box-shadow: var(--glass-shadow);
            animation: slideUp 0.8s ease;
        }
        .hero h1 {
            font-size: 2.5rem; margin-bottom: 15px;
            background: linear-gradient(45deg, var(--ivory), var(--aqua));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        .hero p { color: #ddd; margin-bottom: 25px; font-size: 1.1rem; }
        .btn-gradient {
            background: linear-gradient(45deg, var(--primary), var(--aqua));
            border: none; padding: 12px 25px; border-radius: 25px;
            color: white; font-weight: 600; font-size: 1rem;
            cursor: pointer; box-shadow: 0 4px 15px rgba(0, 201, 255, 0.4);
            transition: all 0.3s; text-decoration: none; display: inline-block;
        }
        .btn-gradient:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 201, 255, 0.6);
        }

        /* === MAIN CONTENT === */
        .main-container { max-width: 1200px; margin: 0 auto; padding: 20px; }
        
        .categories {
            display: flex; gap: 10px; overflow-x: auto;
            padding-bottom: 15px; margin-bottom: 20px;
            scrollbar-width: none;
        }
        .categories::-webkit-scrollbar { display: none; }
        .cat-pill {
            background: var(--glass-bg); border: 1px solid var(--glass-border);
            padding: 8px 20px; border-radius: 20px;
            color: white; cursor: pointer; white-space: nowrap;
            transition: all 0.3s; font-weight: 500;
        }
        .cat-pill:hover, .cat-pill.active {
            background: linear-gradient(45deg, var(--ocean), var(--purple));
            border-color: transparent; transform: scale(1.05);
        }

        /* === PRODUCT GRID === */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px; padding-bottom: 50px;
        }
        .product-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: 24px; padding: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex; flex-direction: column;
            animation: fadeIn 0.5s ease backwards;
        }
        .product-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.1);
            box-shadow: 0 15px 35px rgba(0,201,255,0.2);
        }
        .product-img-wrapper {
            width: 100%; height: 200px;
            border-radius: 16px; overflow: hidden;
            margin-bottom: 15px; position: relative;
            background: #fff; /* White background for product images to pop */
        }
        .product-img {
            width: 100%; height: 100%;
            object-fit: contain; padding: 10px;
            transition: transform 0.5s;
        }
        .product-card:hover .product-img { transform: scale(1.1); }
        .cat-badge {
            position: absolute; top: 10px; left: 10px;
            background: rgba(0,0,0,0.6); backdrop-filter: blur(4px);
            font-size: 0.7rem; padding: 4px 8px; border-radius: 10px; color: white;
        }
        .product-info { flex-grow: 1; display: flex; flex-direction: column; }
        .product-title { font-size: 1.1rem; font-weight: 600; margin-bottom: 8px; line-height: 1.3; }
        .product-price { font-size: 1.3rem; font-weight: 700; color: var(--gold); margin-bottom: 15px; }
        .add-to-cart-btn {
            margin-top: auto;
            background: rgba(255,255,255,0.1); border: 1px solid var(--glass-border);
            color: white; padding: 10px; border-radius: 12px; cursor: pointer;
            transition: all 0.3s; font-weight: 600;
        }
        .product-card:hover .add-to-cart-btn {
            background: linear-gradient(45deg, var(--primary), var(--aqua));
            border-color: transparent;
        }

        /* === CART DRAWER === */
        .cart-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.6); backdrop-filter: blur(5px);
            z-index: 1001; opacity: 0; visibility: hidden; transition: 0.3s;
        }
        .cart-drawer {
            position: fixed; top: 0; right: -400px; width: 100%; max-width: 400px;
            height: 100%; background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(20px); border-left: 1px solid var(--glass-border);
            z-index: 1002; transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex; flex-direction: column; box-shadow: -10px 0 30px rgba(0,0,0,0.5);
        }
        .cart-overlay.active { opacity: 1; visibility: visible; }
        .cart-drawer.active { right: 0; }
        
        .cart-header {
            padding: 20px; border-bottom: 1px solid var(--glass-border);
            display: flex; justify-content: space-between; align-items: center;
        }
        .close-cart { background: none; border: none; color: white; font-size: 1.5rem; cursor: pointer; }
        
        .cart-items { flex-grow: 1; overflow-y: auto; padding: 20px; }
        .cart-item {
            display: flex; align-items: center; gap: 15px; margin-bottom: 20px;
            background: rgba(255,255,255,0.05); padding: 10px; border-radius: 12px;
            animation: slideLeft 0.3s ease;
        }
        .cart-item-img { width: 60px; height: 60px; border-radius: 8px; object-fit: contain; background: white; padding: 5px; }
        .cart-item-info { flex-grow: 1; }
        .cart-item-title { font-size: 0.9rem; font-weight: 500; margin-bottom: 5px; }
        .cart-item-price { color: var(--gold); font-weight: 600; }
        .cart-item-controls { display: flex; align-items: center; gap: 10px; margin-top: 5px; }
        .qty-btn {
            background: rgba(255,255,255,0.2); border: none; color: white;
            width: 24px; height: 24px; border-radius: 50%; cursor: pointer;
        }
        .remove-btn { color: #ff4d4d; cursor: pointer; font-size: 1.2rem; }
        
        .cart-footer { padding: 20px; border-top: 1px solid var(--glass-border); background: rgba(0,0,0,0.2); }
        .cart-total { display: flex; justify-content: space-between; font-size: 1.2rem; font-weight: 700; margin-bottom: 15px; }
        .checkout-btn { width: 100%; text-align: center; font-size: 1.1rem; }

        /* === CHECKOUT MODAL === */
        .checkout-modal {
            position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%) scale(0.9);
            width: 90%; max-width: 500px;
            background: rgba(15, 23, 42, 0.95); backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border); border-radius: 24px;
            padding: 30px; z-index: 1003; opacity: 0; visibility: hidden;
            transition: 0.3s; box-shadow: 0 20px 50px rgba(0,0,0,0.5);
        }
        .checkout-modal.active { opacity: 1; visibility: visible; transform: translate(-50%, -50%) scale(1); }
        .checkout-modal h2 { margin-bottom: 20px; text-align: center; }
        .form-group { margin-bottom: 15px; }
        .form-group label { display: block; margin-bottom: 5px; font-size: 0.9rem; color: #ccc; }
        .form-group input, .form-group textarea {
            width: 100%; padding: 12px; background: rgba(255,255,255,0.05);
            border: 1px solid var(--glass-border); border-radius: 12px; color: white;
            outline: none; transition: 0.3s;
        }
        .form-group input:focus, .form-group textarea:focus { border-color: var(--aqua); background: rgba(255,255,255,0.1); }
        
        /* Floating Buttons */
        .floating-btn {
            position: fixed; bottom: 20px; right: 20px;
            background: #25D366; color: white;
            width: 60px; height: 60px; border-radius: 50%;
            display: flex; justify-content: center; align-items: center;
            font-size: 2rem; box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
            cursor: pointer; z-index: 999; text-decoration: none;
            transition: transform 0.3s;
        }
        .floating-btn:hover { transform: scale(1.1) rotate(10deg); }

        /* Animations */
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes slideUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes slideLeft { from { opacity: 0; transform: translateX(30px); } to { opacity: 1; transform: translateX(0); } }
        @keyframes popIn { 0% { transform: scale(0); } 80% { transform: scale(1.2); } 100% { transform: scale(1); } }
        
        .empty-cart { text-align: center; color: #aaa; margin-top: 40px; }

        /* Mobile Adjustments */
        @media (max-width: 600px) {
            .hero h1 { font-size: 1.8rem; }
            .search-bar { width: 140px; }
            .search-bar:focus { width: 180px; }
            .product-grid { grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 15px; }
            .product-img-wrapper { height: 150px; }
            .product-title { font-size: 0.9rem; }
            .product-price { font-size: 1.1rem; }
        }
    </style>
</head>
<body>

    <div class="bubbles" id="bubbleContainer"></div>

    <header>
        <div class="header-content">
            <div class="logo-area">
                <div class="logo-title" id="shopNameDisplay">AQUA CART</div>
                <div class="logo-tagline" id="shopTaglineDisplay">PREMIUM QUALITY</div>
            </div>
            <div class="header-controls">
                <input type="text" id="searchInput" class="search-bar" placeholder="Search products...">
                <div class="cart-icon" onclick="toggleCart()">
                    <i class="fa-solid fa-cart-shopping"></i>
                    <div class="cart-badge" id="cartCount">0</div>
                </div>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="hero-glass">
            <h1 id="heroTitle">Welcome to SMART AQUA CART</h1>
            <p id="heroSubtitle">Explore our premium collection of live fishes and high-quality accessories.</p>
            <a href="#shop" class="btn-gradient">Shop Now</a>
        </div>
    </section>

    <main class="main-container" id="shop">
        <div class="categories" id="categoryContainer">
            </div>

        <div class="product-grid" id="productGrid">
            </div>
    </main>

    <div class="cart-overlay" id="cartOverlay" onclick="toggleCart()"></div>
    <div class="cart-drawer" id="cartDrawer">
        <div class="cart-header">
            <h2>Your Cart</h2>
            <button class="close-cart" onclick="toggleCart()">&times;</button>
        </div>
        <div class="cart-items" id="cartItemsContainer">
            </div>
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotalDisplay">₹0</span>
            </div>
            <button class="btn-gradient checkout-btn" onclick="openCheckout()">Proceed to Checkout</button>
        </div>
    </div>

    <div class="checkout-modal" id="checkoutModal">
        <h2>Place Your Order</h2>
        <form id="checkoutForm">
            <div class="form-group">
                <label>Full Name *</label>
                <input type="text" id="custName" required placeholder="John Doe">
            </div>
            <div class="form-group">
                <label>Phone Number *</label>
                <input type="tel" id="custPhone" required placeholder="10-digit mobile number">
            </div>
            <div class="form-group">
                <label>Delivery Address *</label>
                <textarea id="custAddress" required rows="3" placeholder="Full address with pincode"></textarea>
            </div>
            <div class="form-group">
                <label>Special Instructions (Optional)</label>
                <input type="text" id="custNotes" placeholder="e.g. Call before delivery">
            </div>
            <input type="hidden" name="Order_Details" id="cartSummaryHidden">
            
            <div style="display: flex; gap: 10px; margin-top: 20px;">
                <button type="button" class="btn-gradient" style="background: rgba(255,255,255,0.1); width: 50%;" onclick="closeCheckout()">Cancel</button>
                <button type="submit" class="btn-gradient" style="width: 50%;">Confirm Order</button>
            </div>
        </form>
    </div>

    <a href="#" id="waButton" class="floating-btn" target="_blank" title="Chat with us on WhatsApp">
        <i class="fa-brands fa-whatsapp"></i>
    </a>

    <script>
        /* ==========================================
           OWNER CONFIGURATION - EDIT DETAILS HERE
        ========================================== */
        const shopConfig = {
            // Business Details
            name: "SMART AQUA CART",
            tagline: "PREMIUM QUALITY FISHES AND THEIR ACCESSORIES",
            location: "KARAD, DIST- SATARA, MAHARASHTRA",
            phone: "917350039389", // Add country code (91 for India) without '+'
            email: "smartaquariumkarad634@gmail.com",
            
            // System Integration
            // Add your Formspree ID here to receive order emails (e.g., "xkgqjyab"). 
            // If left empty, it will simulate a successful order.
            formspreeId: "", 
            
            // Currency Symbol
            currency: "₹",

            // Product Categories
            categories: ["All", "Filters", "Fish Food", "Turtle food"],

            // Products Data
            products: [
                { id: 1, name: "Bluepet Aquarium Powerfilter 6000F", price: 320, category: "Filters", image: "https://i.ibb.co/4ZxR9JpS/1782745859148.webp" },
                { id: 2, name: "Bluepet Aquarium Powerfilter 1000F", price: 350, category: "Filters", image: "https://i.ibb.co/Z6D6DWRM/product-jpeg.jpg" },
                { id: 3, name: "Premium sponge filter XF-380", price: 250, category: "Filters", image: "https://i.ibb.co/Jjdm4N7b/g-Iz-Ozi-HU.webp" },
                { id: 4, name: "Premium Sponge Filter XF-280", price: 200, category: "Filters", image: "https://i.ibb.co/dJHDzpLN/71p4-Sso-Vvj-L.jpg" },
                { id: 5, name: "Aquarium Airpump For fishes", price: 200, category: "Filters", image: "https://i.ibb.co/rRgyjSwj/portable-aquarium-air-pump.jpg" },
                { id: 6, name: "6 in 1 Biological Sponge", price: 280, category: "Filters", image: "https://i.ibb.co/tPM0vQdL/1683465900149-SKU-0046-0.webp" },
                { id: 7, name: "Best Quality Siphon Pipe", price: 180, category: "Filters", image: "https://i.ibb.co/DHPpFDLN/51j0-X8-B5-KQL.jpg" },
                { id: 8, name: "Premium Colour Enhancing Royal arowana Food (100gm)", price: 250, category: "Fish Food", image: "https://i.ibb.co/HTmSKwCB/71c-OFRBmi-PL.jpg" },
                { id: 9, name: "Taiyo Turtle Food 250gm", price: 250, category: "Turtle food", image: "https://i.ibb.co/# Smartaquacart-new
