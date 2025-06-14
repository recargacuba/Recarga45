<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketWhats - Compra y vende con WhatsApp</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-firestore.js"></script>
    <style>
        :root {
            --primary: #25D366;
            --secondary: #128C7E;
            --dark: #075E54;
            --light: #DCF8C6;
            --gray: #f5f5f5;
            --dark-gray: #333;
            --white: #ffffff;
            --shadow: 0 4px 12px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--gray);
            color: var(--dark-gray);
            line-height: 1.6;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--secondary), var(--dark));
            color: var(--white);
            padding: 1rem 2rem;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo i {
            margin-right: 10px;
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 1.5rem;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            padding: 0.5rem;
            border-radius: 4px;
        }

        .nav-links a:hover {
            background-color: rgba(255, 255, 255, 0.1);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1607082348824-0a96f2a4b9da?ixlib=rb-4.0.3') no-repeat center/cover;
            height: 500px;
            display: flex;
            align-items: center;
            text-align: center;
            color: var(--white);
            padding: 0 1rem;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: var(--white);
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }

        .btn:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--white);
            margin-left: 1rem;
        }

        /* Features Section */
        .features {
            padding: 5rem 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark);
            margin-bottom: 1rem;
        }

        .section-title p {
            color: #666;
            max-width: 600px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: var(--white);
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        /* Products Section */
        .products {
            background-color: var(--light);
            padding: 5rem 1rem;
        }

        .products-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.12);
        }

        .product-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-category {
            color: var(--secondary);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .product-title {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 1rem;
        }

        .product-seller {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .seller-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            margin-right: 10px;
            object-fit: cover;
        }

        .whatsapp-btn {
            display: block;
            width: 100%;
            background-color: var(--primary);
            color: var(--white);
            text-align: center;
            padding: 10px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .whatsapp-btn:hover {
            background-color: var(--secondary);
        }

        /* Registration Section */
        .registration {
            padding: 5rem 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .tabs {
            display: flex;
            margin-bottom: 2rem;
            border-bottom: 2px solid #ddd;
        }

        .tab-btn {
            padding: 1rem 2rem;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 500;
            color: #777;
            position: relative;
        }

        .tab-btn.active {
            color: var(--dark);
        }

        .tab-btn.active::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--primary);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .form-container {
            max-width: 500px;
            margin: 0 auto;
            background: var(--white);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(37, 211, 102, 0.2);
        }

        .forgot-password {
            display: block;
            text-align: right;
            margin-bottom: 1.5rem;
            color: var(--secondary);
            text-decoration: none;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: var(--white);
            padding: 3rem 1rem 1rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-col h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
        }

        .footer-col h3::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--primary);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            margin-top: 1.5rem;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 50%;
            margin-right: 10px;
            color: var(--white);
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                width: 100%;
                background: var(--dark);
                flex-direction: column;
                padding: 1rem 0;
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            }

            .nav-links.active {
                display: flex;
            }

            .nav-links li {
                margin: 0;
                text-align: center;
            }

            .nav-links a {
                display: block;
                padding: 1rem;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .tab-btn {
                padding: 0.8rem 1.2rem;
                font-size: 1rem;
            }
        }

        @media (max-width: 480px) {
            .hero {
                height: 400px;
            }

            .hero h1 {
                font-size: 1.8rem;
            }

            .btn-outline {
                margin-left: 0;
                margin-top: 1rem;
            }

            .tabs {
                flex-direction: column;
            }

            .tab-btn {
                width: 100%;
                text-align: left;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="navbar">
            <div class="logo">
                <i class="fab fa-whatsapp"></i>
                <span>MarketWhats</span>
            </div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#productos">Productos</a></li>
                <li><a href="#vender">Vender</a></li>
                <li><a href="#como-funciona">Cómo funciona</a></li>
                <li><a href="#contacto">Contacto</a></li>
                <li><a href="#" id="login-btn">Iniciar Sesión</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobile-menu">
                <i class="fas fa-bars"></i>
            </button>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="hero-content">
            <h1>Compra y vende directamente con WhatsApp</h1>
            <p>Conecta con compradores y vendedores en tu zona. Publica productos, contacta directamente y realiza transacciones de forma segura.</p>
            <a href="#vender" class="btn">Publicar un producto</a>
            <a href="#productos" class="btn btn-outline">Explorar productos</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="como-funciona">
        <div class="section-title">
            <h2>¿Cómo funciona?</h2>
            <p>Simple, rápido y seguro. Todo lo que necesitas para comprar y vender</p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-user-plus"></i>
                </div>
                <h3>Regístrate fácilmente</h3>
                <p>Crea una cuenta en segundos con tu correo o número de teléfono. Verificamos tu identidad para mayor seguridad.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-camera"></i>
                </div>
                <h3>Publica tu producto</h3>
                <p>Sube fotos, añade descripción y precio. Tu anuncio estará visible en minutos para miles de usuarios.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fab fa-whatsapp"></i>
                </div>
                <h3>Conecta por WhatsApp</h3>
                <p>Los compradores pueden contactarte directamente por WhatsApp para preguntas y negociaciones.</p>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="productos">
        <div class="products-container">
            <div class="section-title">
                <h2>Productos Destacados</h2>
                <p>Descubre lo que otros usuarios están vendiendo cerca de ti</p>
            </div>
            <div class="products-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1546868871-7041f2a55e12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="iPhone 12" class="product-img">
                    <div class="product-info">
                        <div class="product-category">Tecnología</div>
                        <h3 class="product-title">iPhone 12 Pro Max 256GB</h3>
                        <div class="product-price">$850</div>
                        <div class="product-seller">
                            <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Vendedor" class="seller-avatar">
                            <span>Juan Pérez</span>
                        </div>
                        <a href="https://wa.me/15551234567?text=Hola%20Juan,%20estoy%20interesado%20en%20el%20iPhone%2012%20Pro%20Max" class="whatsapp-btn" target="_blank">
                            <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
                        </a>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1566150902887-9679ecc155ba?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Bicicleta" class="product-img">
                    <div class="product-info">
                        <div class="product-category">Deportes</div>
                        <h3 class="product-title">Bicicleta Montañera Profesional</h3>
                        <div class="product-price">$320</div>
                        <div class="product-seller">
                            <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Vendedora" class="seller-avatar">
                            <span>María Rodríguez</span>
                        </div>
                        <a href="https://wa.me/15551234568?text=Hola%20María,%20estoy%20interesado%20en%20la%20bicicleta" class="whatsapp-btn" target="_blank">
                            <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
                        </a>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Reloj" class="product-img">
                    <div class="product-info">
                        <div class="product-category">Accesorios</div>
                        <h3 class="product-title">Reloj Inteligente Samsung Galaxy</h3>
                        <div class="product-price">$180</div>
                        <div class="product-seller">
                            <img src="https://randomuser.me/api/portraits/men/67.jpg" alt="Vendedor" class="seller-avatar">
                            <span>Carlos Gómez</span>
                        </div>
                        <a href="https://wa.me/15551234569?text=Hola%20Carlos,%20estoy%20interesado%20en%20el%20reloj%20Samsung" class="whatsapp-btn" target="_blank">
                            <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
                        </a>
                    </div>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1491553895911-0055eca6402d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80" alt="Zapatos" class="product-img">
                    <div class="product-info">
                        <div class="product-category">Moda</div>
                        <h3 class="product-title">Zapatos Deportivos Nike Air Max</h3>
                        <div class="product-price">$95</div>
                        <div class="product-seller">
                            <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Vendedora" class="seller-avatar">
                            <span>Laura Martínez</span>
                        </div>
                        <a href="https://wa.me/15551234570?text=Hola%20Laura,%20estoy%20interesado%20en%20los%20zapatos%20Nike" class="whatsapp-btn" target="_blank">
                            <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Registration Section -->
    <section class="registration" id="vender">
        <div class="section-title">
            <h2>Únete a MarketWhats</h2>
            <p>Regístrate para empezar a comprar y vender hoy mismo</p>
        </div>
        
        <div class="tabs">
            <button class="tab-btn active" data-tab="login">Iniciar Sesión</button>
            <button class="tab-btn" data-tab="register">Registrarse</button>
        </div>
        
        <div class="tab-content active" id="login-content">
            <div class="form-container">
                <form id="login-form">
                    <div class="form-group">
                        <label for="login-email">Correo Electrónico</label>
                        <input type="email" id="login-email" class="form-control" placeholder="tu@email.com" required>
                    </div>
                    <div class="form-group">
                        <label for="login-password">Contraseña</label>
                        <input type="password" id="login-password" class="form-control" placeholder="••••••••" required>
                    </div>
                    <a href="#" class="forgot-password">¿Olvidaste tu contraseña?</a>
                    <button type="submit" class="btn">Iniciar Sesión</button>
                </form>
            </div>
        </div>
        
        <div class="tab-content" id="register-content">
            <div class="form-container">
                <form id="register-form">
                    <div class="form-group">
                        <label for="register-name">Nombre Completo</label>
                        <input type="text" id="register-name" class="form-control" placeholder="Tu nombre" required>
                    </div>
                    <div class="form-group">
                        <label for="register-email">Correo Electrónico</label>
                        <input type="email" id="register-email" class="form-control" placeholder="tu@email.com" required>
                    </div>
                    <div class="form-group">
                        <label for="register-phone">Teléfono (WhatsApp)</label>
                        <input type="tel" id="register-phone" class="form-control" placeholder="+1234567890" required>
                    </div>
                    <div class="form-group">
                        <label for="register-password">Contraseña</label>
                        <input type="password" id="register-password" class="form-control" placeholder="••••••••" required>
                    </div>
                    <div class="form-group">
                        <label for="register-confirm">Confirmar Contraseña</label>
                        <input type="password" id="register-confirm" class="form-control" placeholder="••••••••" required>
                    </div>
                    <button type="submit" class="btn">Crear Cuenta</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contacto">
        <div class="footer-content">
            <div class="footer-col">
                <h3>MarketWhats</h3>
                <p>La plataforma líder para comprar y vender productos usando WhatsApp. Conectando compradores y vendedores de forma segura y eficiente.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                </div>
            </div>
            <div class="footer-col">
                <h3>Enlaces Rápidos</h3>
                <ul class="footer-links">
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#productos">Productos</a></li>
                    <li><a href="#vender">Vender</a></li>
                    <li><a href="#como-funciona">Cómo funciona</a></li>
                    <li><a href="#">Términos y Condiciones</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>Categorías</h3>
                <ul class="footer-links">
                    <li><a href="#">Tecnología</a></li>
                    <li><a href="#">Hogar</a></li>
                    <li><a href="#">Moda</a></li>
                    <li><a href="#">Deportes</a></li>
                    <li><a href="#">Vehiculos</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>Contacto</h3>
                <ul class="footer-links">
                    <li><i class="fas fa-map-marker-alt"></i> Ciudad de México, MX</li>
                    <li><i class="fas fa-phone"></i> +52 55 1234 5678</li>
                    <li><i class="fas fa-envelope"></i> info@marketwhats.com</li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 MarketWhats. Todos los derechos reservados.</p>
        </div>
    </footer>

    <script>
        // Firebase Configuration (Replace with your own config)
        const firebaseConfig = {
            apiKey: "AIzaSyD3wwF3-E02dRP7Z8MH1k11UeR_pVqL66k",
            authDomain: "tienda-e1a2e.firebaseapp.com",
            databaseURL: "https://tienda-e1a2e-default-rtdb.firebaseio.com",
            projectId: "tienda-e1a2e",
            storageBucket: "tienda-e1a2e.firebasestorage.app",
            messagingSenderId: "706488670782",
            appId: "1:706488670782:web:226c0feaa3cf3213b50f6f"
        };

        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();
        const db = firebase.firestore();

        // Mobile Menu Toggle
        document.getElementById('mobile-menu').addEventListener('click', function() {
            document.querySelector('.nav-links').classList.toggle('active');
        });

        // Tab Switching
        const tabBtns = document.querySelectorAll('.tab-btn');
        tabBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                // Remove active class from all buttons and content
                tabBtns.forEach(b => b.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(content => {
                    content.classList.remove('active');
                });
                
                // Add active class to clicked button
                btn.classList.add('active');
                
                // Show corresponding content
                const tabId = btn.getAttribute('data-tab');
                document.getElementById(`${tabId}-content`).classList.add('active');
            });
        });

        // Login Form Submission
        document.getElementById('login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            auth.signInWithEmailAndPassword(email, password)
                .then((userCredential) => {
                    // Signed in
                    alert('¡Inicio de sesión exitoso!');
                    // Redirect to profile page
                    window.location.href = 'profile.html';
                })
                .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    alert(`Error: ${errorMessage}`);
                });
        });

        // Registration Form Submission
        document.getElementById('register-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const phone = document.getElementById('register-phone').value;
            const password = document.getElementById('register-password').value;
            const confirmPassword = document.getElementById('register-confirm').value;
            
            if (password !== confirmPassword) {
                alert('Las contraseñas no coinciden');
                return;
            }
            
            auth.createUserWithEmailAndPassword(email, password)
                .then((userCredential) => {
                    // Signed up 
                    const user = userCredential.user;
                    
                    // Save additional user data to Firestore
                    return db.collection('users').doc(user.uid).set({
                        name: name,
                        email: email,
                        phone: phone,
                        createdAt: firebase.firestore.FieldValue.serverTimestamp()
                    });
                })
                .then(() => {
                    alert('¡Cuenta creada con éxito!');
                    // Redirect to profile page
                    window.location.href = 'profile.html';
                })
                .catch((error) => {
                    const errorCode = error.code;
                    const errorMessage = error.message;
                    alert(`Error: ${errorMessage}`);
                });
        });

        // Password Reset
        document.querySelector('.forgot-password').addEventListener('click', function(e) {
            e.preventDefault();
            const email = prompt('Por favor ingresa tu correo electrónico para restablecer tu contraseña:');
            
            if (email) {
                auth.sendPasswordResetEmail(email)
                    .then(() => {
                        alert('Se ha enviado un correo electrónico para restablecer tu contraseña. Por favor revisa tu bandeja de entrada.');
                    })
                    .catch((error) => {
                        alert(`Error: ${error.message}`);
                    });
            }
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
