<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Noorix - Illuminate Your World</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .hot-deals-marquee { background: #fff3cd; padding: 10px; }
        .product-card { transition: transform .2s; }
        .product-card:hover { transform: scale(1.03); }
        #cart-sidebar { position: fixed; right: -350px; top: 0; width: 350px; height: 100%; }
        .music-player { position: fixed; bottom: 0; left: 0; z-index: 1000; }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand" href="#">Noorix</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link" href="#cart" onclick="toggleCart()"><i class="fas fa-shopping-cart"></i></a></li>
                    <li class="nav-item"><a class="nav-link" href="#register" data-bs-toggle="modal" data-bs-target="#registerModal">Register</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hot Deals Marquee -->
    <div class="hot-deals-marquee">
        <marquee>🔥 Hot Deals: Smart LED Bulb 20% Off | Rechargeable Lamps 15% Off | Weekend Special Offer! 🔥</marquee>
    </div>

    <!-- Product Grid -->
    <div class="container mt-5">
        <div class="row">
            <div class="col-md-4 mb-4">
                <div class="card product-card">
                    <img src="product1.jpg" class="card-img-top" alt="Smart LED Bulb">
                    <div class="card-body">
                        <h5 class="card-title">Smart LED Bulb</h5>
                        <p class="card-text">$29.99</p>
                        <select class="form-select mb-2 config-select">
                            <option>5W</option>
                            <option>7W</option>
                            <option>9W</option>
                        </select>
                        <button class="btn btn-primary" onclick="addToCart('Smart LED Bulb', 29.99)">Add to Cart</button>
                        <div class="reviews mt-3">
                            <div class="rating">★★★★☆</div>
                            <button class="btn btn-sm btn-link" data-bs-toggle="modal" data-bs-target="#reviewModal">Add Review</button>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Add more product cards -->
        </div>
    </div>

    <!-- Shopping Cart Sidebar -->
    <div id="cart-sidebar" class="bg-white shadow p-4">
        <h4>Shopping Cart</h4>
        <div id="cart-items"></div>
        <div class="total-cost mt-3">
            <h5>Total: $<span id="cart-total">0.00</span></h5>
        </div>
        <div class="promo-code mt-3">
            <input type="text" class="form-control" placeholder="Enter promo code">
            <button class="btn btn-success mt-2" onclick="applyPromo()">Apply</button>
        </div>
    </div>

    <!-- Registration Modal -->
    <div class="modal fade" id="registerModal">
        <!-- Registration form with name, phone, address fields -->
    </div>

    <!-- Music Player (Admin Only) -->
    <audio id="background-music" autoplay loop>
        <source src="background-music.mp3" type="audio/mpeg">
    </audio>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Shopping Cart Logic
        let cart = [];
        
        function addToCart(name, price) {
            cart.push({name, price});
            updateCartDisplay();
        }

        function updateCartDisplay() {
            // Update cart items and total
        }

        // Product Search
        function searchProducts() {
            // Implement search logic
        }

        // Preference Algorithm
        class PreferenceAlgorithm {
            // Implement user preference tracking
        }

        // Promo Code Handling
        function applyPromo() {
            // Add promo code validation
        }
    </script>
</body>
</html>
