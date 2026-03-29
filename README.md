# studious-octo-enigma
perfumes originales
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Essence Reviews | Login</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #ff9a76;
            --secondary-color: #ff6b8b;
            --accent-color: #4ecdc4;
            --dark-color: #2c3e50;
            --light-color: #f9f7f7;
            --gradient-bg: linear-gradient(135deg, #ff9a76 0%, #ff6b8b 100%);
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f7f7;
            color: #333;
            line-height: 1.6;
        }

        /* Estilos específicos para el Login */
        #login-page {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--gradient-bg);
        }

        .login-card {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        .login-card h2 {
            margin-bottom: 25px;
            color: var(--dark-color);
        }

        .login-card .logo i {
            color: var(--secondary-color);
            font-size: 3rem;
            margin-bottom: 10px;
        }

        /* Ocultar contenido principal inicialmente */
        #main-content {
            display: none;
        }

        /* Reutilización de tus estilos existentes */
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        header { background: var(--gradient-bg); color: white; padding: 15px 0; box-shadow: var(--shadow); position: sticky; top: 0; z-index: 100; }
        .logo { font-size: 1.8rem; font-weight: 700; display: flex; align-items: center; gap: 10px; justify-content: center; }
        .nav-container { display: flex; justify-content: space-between; align-items: center; }
        nav ul { display: flex; list-style: none; }
        nav ul li { margin-left: 30px; }
        nav ul li a { color: white; text-decoration: none; font-weight: 600; padding: 5px 10px; border-radius: 4px; transition: var(--transition); }
        nav ul li a:hover { background-color: rgba(255, 255, 255, 0.2); }
        
        .section { display: none; padding: 60px 0; animation: fadeIn 0.5s ease; }
        .section.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .hero { background: var(--gradient-bg); color: white; padding: 100px 0; text-align: center; border-radius: 0 0 20px 20px; margin-bottom: 40px; }
        .season-tag { display: inline-block; background-color: var(--accent-color); color: white; padding: 8px 20px; border-radius: 30px; margin-bottom: 30px; }
        
        .categories { display: flex; justify-content: center; flex-wrap: wrap; gap: 20px; margin-bottom: 40px; }
        .category-btn { background: white; border: none; padding: 12px 25px; border-radius: 30px; font-weight: 600; cursor: pointer; box-shadow: var(--shadow); transition: var(--transition); }
        .category-btn.active { background: var(--secondary-color); color: white; }

        .reviews-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 30px; }
        .review-card { background: white; border-radius: 15px; overflow: hidden; box-shadow: var(--shadow); transition: var(--transition); }
        .review-card:hover { transform: translateY(-10px); }
        .perfume-image { width: 100%; height: 200px; object-fit: cover; }
        .review-content { padding: 20px; }
        .price { font-weight: 700; color: var(--primary-color); font-size: 1.2rem; }
        .add-to-cart, .submit-btn, .checkout-btn { background: var(--gradient-bg); color: white; border: none; padding: 10px 20px; border-radius: 30px; cursor: pointer; font-weight: 600; }
        
        /* Estilos Formulario */
        .form-group { margin-bottom: 15px; text-align: left; }
        .form-group label { display: block; margin-bottom: 5px; font-weight: 600; }
        .form-group input { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 8px; }
        
        .cart-count { background: var(--accent-color); color: white; border-radius: 50%; padding: 2px 6px; font-size: 0.7rem; position: relative; top: -10px; }
    </style>
</head>
<body>

    <div id="login-page">
        <div class="login-card">
            <div class="logo">
                <i class="fas fa-spray-can-sparkles"></i>
            </div>
            <h2>Bienvenido a Essence</h2>
            <form id="login-form">
                <div class="form-group">
                    <label for="username">Usuario</label>
                    <input type="text" id="username" placeholder="Ingresa tu usuario" required>
                </div>
                <div class="form-group">
                    <label for="password">Contraseña</label>
                    <input type="password" id="password" placeholder="••••••••" required>
                </div>
                <button type="submit" class="submit-btn" style="width: 100%; margin-top: 10px;">Ingresar</button>
            </form>
            <p id="login-error" style="color: red; margin-top: 15px; display: none;">Usuario o contraseña incorrectos</p>
        </div>
    </div>

    <div id="main-content">
        <header>
            <div class="container nav-container">
                <div class="logo">
                    <i class="fas fa-spray-can-sparkles"></i>
                    <span>Perfumes Árabes</span>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="nav-link active" data-section="inicio">Inicio</a></li>
                        <li><a href="#" class="nav-link" data-section="carrito">
                            <i class="fas fa-shopping-cart"></i> Carrito <span class="cart-count">0</span>
                        </a></li>
                        <li><a href="#" class="nav-link" data-section="contacto">Contacto</a></li>
                        <li><a href="#" id="logout-btn" style="color: #ffeb3b;"><i class="fas fa-sign-out-alt"></i> Salir</a></li>
                    </ul>
                </nav>
            </div>
        </header>

        <section id="inicio" class="section active">
            <div class="hero">
                <div class="container">
                    <div class="season-tag">Reseñas de Verano 2026</div>
                    <h1>Descubre las Fragancias de la Temporada</h1>
                    <p>Explora nuestras reseñas de perfumes exclusivos.</p>
                </div>
            </div>
            <div class="container">
                <div class="categories">
                    <button class="category-btn active" data-category="all">Todos</button>
                    <button class="category-btn" data-category="hombre">Hombre</button>
                    <button class="category-btn" data-category="mujer">Mujer</button>
                </div>
                <div class="reviews-grid" id="reviews-container"></div>
            </div>
        </section>

        <section id="carrito" class="section">
            <div class="container">
                <h2>Tu Carrito</h2>
                <div id="cart-items" style="background: white; padding: 20px; border-radius: 15px; margin-top: 20px;"></div>
                <button class="checkout-btn" style="margin-top: 20px;">Pagar ahora</button>
            </div>
        </section>

        <section id="contacto" class="section">
            <div class="container">
                <h2>Contacto</h2>
                <p>Encuéntranos en Reynosa, Tamaulipas.</p>
            </div>
        </section>
    </div>

    <script>
        // --- LÓGICA DE LOGIN ---
        const loginForm = document.getElementById('login-form');
        const loginPage = document.getElementById('login-page');
        const mainContent = document.getElementById('main-content');
        const loginError = document.getElementById('login-error');

        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const user = document.getElementById('username').value;
            const pass = document.getElementById('password').value;

            // Validación simple (puedes cambiar "admin" por lo que quieras)
            if(user === "admin" && pass === "1234") {
                loginPage.style.display = 'none';
                mainContent.style.display = 'block';
                loadPerfumeReviews('all');
            } else {
                loginError.style.display = 'block';
            }
        });

        document.getElementById('logout-btn').addEventListener('click', () => {
            location.reload(); // Recarga la página para cerrar sesión
        });

        // --- DATOS Y NAVEGACIÓN ---
        const perfumes = [
            { id: 1, name: "LIGHT BLUE SUMMER", brand: "D&G", category: ["mujer"], price: 1089, image: "https://www.perfumenz.co.nz/cdn/shop/files/dolce-light-blue-summer-vibes-125ml_grande.png?v=1706564019", description: "Fresco y cítrico." },
            { id: 2, name: "SAUVAGE EDP", brand: "DIOR", category: ["hombre"], price: 3650, image: "https://i5.walmartimages.com.mx/samsmx/images/product-images/img_large/981031830l.jpg?odnHeight=768&odnWidth=768&odnBg=FFFFFF", description: "Intenso y masculino." },
            { id: 3, name: "KHAMRAH", brand: "LATTAFA", category: ["hombre"], price: 1500, image: "https://odperfumes.com/wp-content/uploads/2025/02/Lattafa-Khamrah-EDP-Spray-3-4-Oz-For-Men_81080ddf-a440-40e6-bb7c-bdd9516b91ab.468a6e1a30e36e3f25bd9926392fb176.jpeg", description: "Dulce y especiado." }
        ];

        let cart = [];

        function loadPerfumeReviews(cat) {
            const container = document.getElementById('reviews-container');
            container.innerHTML = '';
            const filtered = cat === 'all' ? perfumes : perfumes.filter(p => p.category.includes(cat));
            
            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="review-card">
                        <img src="${p.image}" class="perfume-image">
                        <div class="review-content">
                            <h4>${p.brand}</h4>
                            <h3>${p.name}</h3>
                            <p>${p.description}</p>
                            <div style="display:flex; justify-content:space-between; align-items:center; margin-top:15px;">
                                <span class="price">$${p.price}</span>
                                <button class="add-to-cart" onclick="addToCart(${p.id})">Agregar</button>
                            </div>
                        </div>
                    </div>`;
            });
        }

        // Navegación de pestañas
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                if(this.id === 'logout-btn') return;
                e.preventDefault();
                const sectionId = this.getAttribute('data-section');
                document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
                document.getElementById(sectionId).classList.add('active');
                document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
                this.classList.add('active');
            });
        });

        function addToCart(id) {
            const p = perfumes.find(item => item.id === id);
            cart.push(p);
            document.querySelector('.cart-count').textContent = cart.length;
            alert(`${p.name} añadido al carrito`);
            updateCartUI();
        }

        function updateCartUI() {
            const cartList = document.getElementById('cart-items');
            if(cart.length === 0) {
                cartList.innerHTML = "Tu carrito está vacío.";
                return;
            }
            cartList.innerHTML = cart.map(item => `<div>• ${item.name} - $${item.price}</div>`).join('');
        }
    </script>
</body>
</html>
