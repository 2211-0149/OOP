//product 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spice Spectrum - Product</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Product Details</h1>
<img src=" 1726237771749.jpg " alt="Spice 1"> <p>Cloves</p> <p>Price: 100g=LKR 350.00</p> <img src="1726237676710 .jpg " alt="Spice 2"> <p>Lemmon Grass</p> <p>Price: 100g=LKR 300.00</p> <img src="1726237178583 .jpg " alt="Spice 3"> <p>Black Pepar </p> <p>Price: 100g=LKR 400.00</p> <img src="1726237134343.jpg " alt="Spice 4"> <p>Cinnamon </p> <p>Price: 100g=LKR 450.00</p> <img src=" 1726237443137.jpg " alt="Spice 5"> <p>Ginger </p> <p>Price: 100g=LKR 350.00</p> <img src=" 1726237471797 .jpg " alt="Spice 6"> <p>Curry Leaves </p> <p>Price: 100g=LKR 150.00</p> <img src=" 1726237365717 .jpg " alt="Spice 7"> <p>Nutmeg </p> <p>Price: 100g=LKR 600.00</p> <img src=" 1726237071523 .jpg " alt="Spice 8"> <p>Turmeric </p> <p>Price: 100g=LKR 300.00</p>
        <nav>
            <a href="index.html">Home</a>
            <a href="cart.html">Cart</a>
        </nav>
    </header>
    
    <section id="product-detail">
     
        <button onclick="addToCart('spice1')">Add to Cart</button>
    </section>
    
    <footer>
        <p>&copy; 2024 Spice Spectrum. All rights reserved.</p>
    </footer>
    
    <script src="scripts.js"></script>
</body>
</html>
//index
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spice Spectrum - Home</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to Spice Spectrum</h1>
<img src="   1726237863102  .jpg >
        <nav>
            <a href="index.html">Home</a>
            <a href="product.html">Products</a>
            <a href="login.html">Login</a>
            <a href="cart.html">Cart</a>
        </nav>
    </header>
    
    <section id="featured-products">
        <h2>Featured Products</h2>
        <div class="product">
 <img src="  1726237771749.jpg    " alt="Spice 1">
            <p>Cloves</p>
            <p>Price: 100g=LKR 350.00</p>
<img src="1726237676710 .jpg    " alt="Spice 2">
            <p>Lemmon Grass</p>
            <p>Price: 100g=LKR 300.00</p>
<img src="1726237178583 .jpg    " alt="Spice 3">
            <p>Black Pepar </p>
            <p>Price: 100g=LKR 400.00</p>
<img src="1726237134343.jpg    " alt="Spice 4">
            <p>Cinnamon  </p>
            <p>Price: 100g=LKR 450.00</p>
<img src=" 1726237443137.jpg    " alt="Spice 5">
            <p>Ginger </p>
            <p>Price: 100g=LKR 350.00</p>
<img src=" 1726237471797   .jpg    " alt="Spice 6">
            <p>Curry Leaves  </p>
            <p>Price: 100g=LKR 150.00</p>
<img src="     1726237365717   .jpg    " alt="Spice 7">
            <p>Nutmeg </p>
            <p>Price: 100g=LKR 600.00</p>
<img src="    1726237071523   .jpg    " alt="Spice 8">
            <p>Turmeric  </p>
            <p>Price: 100g=LKR 300.00</p>
            <button onclick="addToCart('spice1')">Add to Cart</button>
        </div>
        <!-- Add more product cards -->
    </section>
    
    <footer>
        <p>&copy; 2024 Spice Spectrum. All rights reserved.</p>
    </footer>

    <script src="scripts.js"></script>
</body>
</html>
//script
function addToCart(productId) {
    let cart = JSON.parse(localStorage.getItem('cart')) || [ ];
    cart.push(productId);
    localStorage.setItem('cart', JSON.stringify(cart));
    alert('Product added to cart!');
}

function loadCart() {
    let cart = JSON.parse(localStorage.getItem('cart')) || [ ];
    let cartItems = document.getElementById('cart-items');
    cart.forEach(item => {
        cartItems.innerHTML += `<div>${item}</div>`;
    });
}
//admin user
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - User Management</title>
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <header>
        <h1>User Management</h1>
        <nav>
            <a href="admin-products.html">Products</a>
            <a href="admin-orders.html">Orders</a>
            <a href="admin-content.html">Content</a>
        </nav>
    </header>

    <section>
        <h2>Manage Users</h2>
        <button onclick="addUser()">Add New User</button>
        <table>
            <thead>
                <tr>
                    <th>Username</th>
                    <th>Email</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody id="user-list">
                <!-- Users will be dynamically loaded here -->
            </tbody>
        </table>
    </section>

    <script>
        function loadUsers() {
      
            let users = [
                { username: 'user1', email: 'user1@abc.com' },
                { username: 'user2', email: 'user2@abc1.com' }
            ];

            let userList = document.getElementById('user-list');
            users.forEach(user => {
                userList.innerHTML += `<tr>
                    <td>${user.username}</td>
                    <td>${user.email}</td>
                    <td>
                        <button onclick="editUser('${user.username}')">Edit</button>
                        <button onclick="deleteUser('${user.username}')">Delete</button>
                    </td>
                </tr>`;
            });
        }

        function addUser() {
            alert('Add new user functionality coming soon!');
        }

        function editUser(username) {
            alert('Editing user: ' + username);
        }

        function deleteUser(username) {
            alert('Deleting user: ' + username);
        }

        window.onload = loadUsers;
    </script>
</body>
</html>
//admin products
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - Product Management</title>
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <header>
        <h1>Product Management</h1>
        <nav>
            <a href="admin-users.html">Users</a>
            <a href="admin-orders.html">Orders</a>
            <a href="admin-content.html">Content</a>
        </nav>
    </header>

    <section>
        <h2>Manage Products</h2>
        <button onclick="addProduct()">Add New Product</button>
        <table>
            <thead>
                <tr>
                    <th>Product Name</th>
                    <th>Price</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody id="product-list">
                <!-- Products will be dynamically loaded here -->
            </tbody>
        </table>
    </section>

    <script>
        function loadProducts() {
         
            let products = [
                { name: 'Spice 1', price: 'Lkr10' },
                { name: 'Spice 2', price: 'Lkr15' }
            ];

            let productList = document.getElementById('product-list');
            products.forEach(product => {
                productList.innerHTML += `<tr>
                    <td>${product.name}</td>
                    <td>${product.price}</td>
                    <td>
                        <button onclick="editProduct('${product.name}')">Edit</button>
                        <button onclick="deleteProduct('${product.name}')">Delete</button>
                    </td>
                </tr>`;
            });
        }

        function addProduct() {
            alert('Add new product functionality coming soon!');
        }

        function editProduct(productName) {
            alert('Editing product: ' + productName);
        }

        function deleteProduct(productName) {
            alert('Deleting product: ' + productName);
        }

        window.onload = loadProducts;
    </script>
</body>
</html>
//profile 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Profile - Spice Spectrum</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Your Profile</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="product.html">Products</a>
            <a href="cart.html">Cart</a>
            <a href="logout.html">Logout</a>
        </nav>
    </header>

    <section id="profile">
        <h2>User Profile</h2>
        <form id="profile-form">
            <label for="username">Username:</label>
            <input type="text" id="username" required>

            <label for="email">Email:</label>
            <input type="email" id="email" required>

            <label for="password">Password:</label>
            <input type="password" id="password" required>

            <label for="confirm-password">Confirm Password:</label>
            <input type="password" id="confirm-password" required>

            <button type="submit">Update Profile</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2024 Spice Spectrum. All rights reserved.</p>
    </footer>

    <script src="scripts.js"></script>
    <script>

        let user = {
            username: "user123",
            email: "user@abc.com",
            password: "password123"
        };

        function loadUserProfile() {
            document.getElementById('username').value = user.username;
            document.getElementById('email').value = user.email;
            document.getElementById('password').value = user.password;
            document.getElementById('confirm-password').value = user.password;
        }

        // Handle profile update submission
        document.getElementById('profile-form').onsubmit = function(event) {
            event.preventDefault();

            // Get updated values from form
            let updatedUsername = document.getElementById('username').value;
            let updatedEmail = document.getElementById('email').value;
            let updatedPassword = document.getElementById('password').value;
            let confirmPassword = document.getElementById('confirm-password').value;

            // Check if passwords match
            if (updatedPassword !== confirmPassword) {
                alert("Passwords do not match!");
                return;
            }

            // Save updated profile data (here, we're just updating the dummy user object)
            user.username = updatedUsername;
            user.email = updatedEmail;
            user.password = updatedPassword;

            alert("Profile updated successfully!");
        }

        // Load user data on page load
        window.onload = loadUserProfile;
    </script>
</body>
</html>
//styles 
body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
}

#profile {
    margin: 2rem auto;
    width: 50%;
    background-color: white;
    padding: 1rem;
    border-radius: 8px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

#profile h2 {
    text-align: center;
}

#profile-form {
    display: flex;
    flex-direction: column;
}

#profile-form label {
    margin-top: 10px;
}

#profile-form input {
    padding: 10px;
    margin-top: 5px;
    font-size: 1rem;
    border: 1px solid #ddd;
    border-radius: 4px;
}

button {
    background-color: #333;
    color: white;
    border: none;
    padding: 10px;
    margin-top: 20px;
    cursor: pointer;
    font-size: 1rem;
}

button:hover {
    background-color: #555;
}

footer {
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}
//admin content 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - Content Management</title>
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <header>
        <h1>Content Management</h1>
        <nav>
            <a href="admin-users.html">Users</a>
            <a href="admin-products.html">Products</a>
            <a href="admin-orders.html">Orders</a>
        </nav>
    </header>

    <section>
        <h2>Manage Content</h2>
        <button onclick="addContent()">Add New Content</button>
        <table>
            <thead>
                <tr>
                    <th>Title</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody id="content-list">
                <!-- Content items will be dynamically loaded here -->
            </tbody>
        </table>
    </section>

    <script>
        function loadContent() {
            // Dummy data for content
            let contents = [
                { title: 'FAQs' },
                { title: 'Blog Post 1' }
            ];

            let contentList = document.getElementById('content-list');
            contents.forEach(content => {
                contentList.innerHTML += `<tr>
                    <td>${content.title}</td>
                    <td>
                        <button onclick="editContent('${content.title}')">Edit</button>
                        <button onclick="deleteContent('${content.title}')">Delete</button>
                    </td>
                </tr>`;
            });
        }

        function addContent() {
            alert('Add new content functionality coming soon!');
        }

        function editContent(contentTitle) {
            alert('Editing content: ' + contentTitle);
        }

        function deleteContent(contentTitle) {
            alert('Deleting content: ' + contentTitle);
        }

        window.onload = loadContent;
    </script>
</body
//admin orders
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - Order Management</title>
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <header>
        <h1>Order Management</h1>
        <nav>
            <a href="admin-users.html">Users</a>
            <a href="admin-products.html">Products</a>
            <a href="admin-content.html">Content</a>
        </nav>
    </header>

    <section>
        <h2>Manage Orders</h2>
        <table>
            <thead>
                <tr>
                    <th>Order ID</th>
                    <th>Customer</th>
                    <th>Status</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody id="order-list">
                <!-- Orders will be dynamically loaded here -->
            </tbody>
        </table>
    </section>

    <script>
        function loadOrders() {
            // Dummy data for orders
            let orders = [
                { id: '1234', customer: 'user1', status: 'Pending' },
                { id: '5678', customer: 'user2', status: 'Shipped' }
            ];

            let orderList = document.getElementById('order-list');
            orders.forEach(order => 
 //check out
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spice Spectrum - Checkout</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Checkout</h1>
    </header>
    
    <section id="checkout">
        <form id="payment-form">
            <label for="card-number">Card Number:</label>
            <input type="text" id="card-number" required>
            
            <label for="expiry-date">Expiry Date:</label>
            <input type="text" id="expiry-date" required>
            
            <label for="cvv">CVV:</label>
            <input type="text" id="cvv" required>
            
            <button type="submit">Pay Now</button>
        </form>
    </section>
    
    <footer>
        <p>&copy; 2024 Spice Spectrum. All rights reserved.</p>
    </footer>
    
    <script src="scripts.js"></script>
</body>
</html>
//cart
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spice Spectrum - Cart</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Your Cart</h1>
        <nav>
            <a href="index.html">Home</a>
            <a href="checkout.html">Checkout</a>
        </nav>
    </header>
    
    <section id="cart">
        <h2>Your Cart Items</h2>
        <div id="cart-items"></div>
    </section>
    
    <footer>
        <p>&copy; 2024 Spice Spectrum. All rights reserved.</p>
    </footer>
    
    <script src="scripts.js"></script>
    <script>loadCart();</script>
</body>
</html>
//style
body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
}

#featured-products {
    display: flex;
    justify-content: space-around;
    margin: 20px;
}

.product {
    border: 1px solid #ddd;
    padding: 10px;
    width: 30%;
    text-align: center;
}

button {
    background-color: #333;
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
}

button:hover {
    background-color: #555;
}

footer {
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}
