<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Vluzurius Lights Shop</title>
  <style>
    /* Reset and Base Styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f0f2f5;
      color: #333;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }
    header {
      background: #343a40;
      color: #fff;
      padding: 20px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    main {
      display: flex;
      flex: 1;
      margin: 20px;
      gap: 20px;
    }
    .container {
      flex: 3;
      background: #fff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    .sidebar {
      flex: 1;
      background: #fff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      height: fit-content;
    }
    h1, h2 {
      margin-bottom: 20px;
    }
    /* Product Form Styles */
    form {
      margin-bottom: 30px;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }
    form input[type="text"] {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 16px;
    }
    form button {
      width: 100%;
      padding: 12px;
      background: #007bff;
      color: #fff;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    form button:hover {
      background: #0056b3;
    }
    /* Products Grid */
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 20px;
    }
    .product {
      border: 1px solid #ddd;
      padding: 15px;
      border-radius: 8px;
      text-align: center;
      background: #fafafa;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .product:hover {
      transform: translateY(-5px);
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }
    .product img {
      max-width: 100%;
      height: 150px;
      object-fit: contain;
      margin-bottom: 10px;
    }
    .product h3 {
      margin-bottom: 10px;
      font-size: 18px;
      color: #333;
    }
    .product button {
      padding: 8px 16px;
      background: #28a745;
      color: #fff;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .product button:hover {
      background: #218838;
    }
    /* Cart Styles */
    .cart-item {
      border-bottom: 1px solid #eee;
      padding: 10px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .cart-item:last-child {
      border-bottom: none;
    }
    .cart-item-details {
      display: flex;
      align-items: center;
    }
    .cart-item img {
      max-width: 50px;
      height: 50px;
      object-fit: cover;
      margin-right: 10px;
      border-radius: 4px;
    }
    .cart-item button {
      background: #dc3545;
      border: none;
      color: #fff;
      padding: 6px 10px;
      border-radius: 4px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .cart-item button:hover {
      background: #c82333;
    }
    .cart-total {
      margin-top: 20px;
      font-size: 18px;
      text-align: center;
    }
    /* Responsive Design */
    @media (max-width: 768px) {
      main {
        flex-direction: column;
      }
      .container {
        margin-right: 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Vluzurius Lights Shop</h1>
  </header>
  <main>
    <div class="container">
      <!-- Product Input Form -->
      <form id="productForm">
        <h2>Add New Product</h2>
        <input type="text" id="productName" placeholder="Product Name" required />
        <input type="text" id="productImage" placeholder="Product Image URL" required />
        <button type="submit">Add Product</button>
      </form>
      
      <!-- Products Display Section -->
      <div class="products" id="productsContainer">
        <!-- Products will be added here -->
      </div>
    </div>
    
    <!-- Shopping Cart Sidebar -->
    <aside class="sidebar">
      <h2>Shopping Cart</h2>
      <div id="cartContainer">
        <!-- Cart items will be listed here -->
      </div>
      <div class="cart-total" id="cartTotal">Total Items: 0</div>
    </aside>
  </main>
  
  <script>
    // Arrays to store products and cart items
    let products = [];
    let cart = [];
    
    const productForm = document.getElementById('productForm');
    const productsContainer = document.getElementById('productsContainer');
    const cartContainer = document.getElementById('cartContainer');
    const cartTotal = document.getElementById('cartTotal');
    
    // Function to render products
    function renderProducts() {
      productsContainer.innerHTML = '';
      products.forEach((product, index) => {
        const productDiv = document.createElement('div');
        productDiv.className = 'product';
        productDiv.innerHTML = `
          <img src="${product.image}" alt="${product.name}" />
          <h3>${product.name}</h3>
          <button onclick="addToCart(${index})">Add to Cart</button>
        `;
        productsContainer.appendChild(productDiv);
      });
    }
    
    // Function to render cart items
    function renderCart() {
      cartContainer.innerHTML = '';
      cart.forEach((item, index) => {
        const cartItemDiv = document.createElement('div');
        cartItemDiv.className = 'cart-item';
        cartItemDiv.innerHTML = `
          <div class="cart-item-details">
            <img src="${item.image}" alt="${item.name}" />
            <span>${item.name}</span>
          </div>
          <button onclick="removeFromCart(${index})">Remove</button>
        `;
        cartContainer.appendChild(cartItemDiv);
      });
      cartTotal.textContent = `Total Items: ${cart.length}`;
    }
    
    // Form submission to add a new product
    productForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const name = document.getElementById('productName').value.trim();
      const image = document.getElementById('productImage').value.trim();
      if(name && image) {
        products.push({ name, image });
        renderProducts();
        productForm.reset();
      }
    });
    
    // Function to add product to the cart
    function addToCart(index) {
      cart.push(products[index]);
      renderCart();
    }
    
    // Function to remove product from the cart
    function removeFromCart(index) {
      cart.splice(index, 1);
      renderCart();
    }
  </script>
</body>
</html>

