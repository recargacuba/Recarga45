<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketWhats - Compra y vende con WhatsApp</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
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

        /* Seller Dashboard */
        .dashboard {
            display: none;
            padding: 5rem 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .dashboard-actions {
            display: flex;
            gap: 1rem;
        }

        /* Product Form */
        .product-form {
            background: var(--white);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: var(--shadow);
            max-width: 800px;
            margin: 0 auto;
        }

        .form-row {
            display: flex;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .form-col {
            flex: 1;
        }

        /* Alert messages */
        .alert {
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
            display: none;
        }
        
        .alert-success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .alert-error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }

        /* Loader */
        .loader {
            display: none;
            text-align: center;
            margin: 20px 0;
        }
        
        .loader-spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            border-left-color: var(--primary);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
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

            .form-row {
                flex-direction: column;
                gap: 0;
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
            <div class="products-grid" id="products-grid">
                <!-- Los productos se cargarán dinámicamente -->
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
        
        <!-- Alert Messages -->
        <div id="alert-message" class="alert" style="display: none;"></div>
        
        <!-- Loader -->
        <div id="loader" class="loader" style="display: none;">
            <div class="loader-spinner"></div>
            <p>Procesando...</p>
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

    <!-- Seller Dashboard -->
    <section class="dashboard" id="dashboard">
        <div class="dashboard-header">
            <div class="section-title">
                <h2>Mi Panel de Vendedor</h2>
                <p>Gestiona tus productos y ventas</p>
            </div>
            <div class="dashboard-actions">
                <button class="btn" id="new-product-btn">
                    <i class="fas fa-plus"></i> Nuevo Producto
                </button>
                <button class="btn btn-outline" id="logout-btn">
                    <i class="fas fa-sign-out-alt"></i> Cerrar Sesión
                </button>
            </div>
        </div>
        
        <!-- New Product Form -->
        <div class="product-form" id="product-form" style="display: none;">
            <h3>Publicar Nuevo Producto</h3>
            <form id="publish-form">
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="product-name">Nombre del Producto</label>
                            <input type="text" id="product-name" class="form-control" placeholder="Ej: iPhone 12 Pro Max" required>
                        </div>
                        <div class="form-group">
                            <label for="product-price">Precio ($)</label>
                            <input type="number" id="product-price" class="form-control" placeholder="Ej: 850" required>
                        </div>
                        <div class="form-group">
                            <label for="product-category">Categoría</label>
                            <select id="product-category" class="form-control" required>
                                <option value="">Seleccionar categoría</option>
                                <option value="Tecnología">Tecnología</option>
                                <option value="Moda">Moda</option>
                                <option value="Hogar">Hogar</option>
                                <option value="Deportes">Deportes</option>
                                <option value="Vehiculos">Vehículos</option>
                                <option value="Otros">Otros</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-col">
                        <div class="form-group">
                            <label for="product-description">Descripción</label>
                            <textarea id="product-description" class="form-control" rows="5" placeholder="Describe tu producto..." required></textarea>
                        </div>
                        <div class="form-group">
                            <label for="product-image">Imagen (URL)</label>
                            <input type="text" id="product-image" class="form-control" placeholder="https://..." required>
                        </div>
                    </div>
                </div>
                <button type="submit" class="btn">Publicar Producto</button>
            </form>
        </div>
        
        <div class="section-title">
            <h3>Mis Productos Publicados</h3>
        </div>
        <div class="products-grid" id="my-products-grid">
            <!-- Los productos del usuario se cargarán aquí -->
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

    <!-- Firebase SDK -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-app.js";
        import { 
            getAuth, 
            createUserWithEmailAndPassword, 
            signInWithEmailAndPassword,
            sendPasswordResetEmail,
            onAuthStateChanged,
            signOut
        } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-auth.js";
        import { 
            getFirestore, 
            doc, 
            setDoc, 
            serverTimestamp,
            collection,
            addDoc,
            query,
            where,
            getDocs
        } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore.js";

        // Configuración de Firebase (REEMPLAZA CON TUS DATOS)
        const firebaseConfig = {
            apiKey: "AIzaSyD3wwF3-E02dRP7Z8MH1k11UeR_pVqL66k",
            authDomain: "tienda-e1a2e.firebaseapp.com",
            databaseURL: "https://tienda-e1a2e-default-rtdb.firebaseio.com",
            projectId: "tienda-e1a2e",
            storageBucket: "tienda-e1a2e.firebasestorage.app",
            messagingSenderId: "706488670782",
            appId: "1:706488670782:web:226c0feaa3cf3213b50f6f"
        };

        // Inicializar Firebase
        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const db = getFirestore(app);

        // Referencias a elementos del DOM
        const dashboardSection = document.getElementById('dashboard');
        const registrationSection = document.getElementById('vender');
        const productsSection = document.getElementById('productos');
        const loginBtn = document.getElementById('login-btn');
        const logoutBtn = document.getElementById('logout-btn');
        const newProductBtn = document.getElementById('new-product-btn');
        const productForm = document.getElementById('product-form');
        const publishForm = document.getElementById('publish-form');
        const myProductsGrid = document.getElementById('my-products-grid');
        const productsGrid = document.getElementById('products-grid');

        // Funciones para mostrar/ocultar alertas y loader
        function showAlert(message, type) {
            const alertDiv = document.getElementById('alert-message');
            alertDiv.textContent = message;
            alertDiv.className = `alert alert-${type}`;
            alertDiv.style.display = 'block';
            
            // Ocultar después de 5 segundos
            setTimeout(() => {
                alertDiv.style.display = 'none';
            }, 5000);
        }
        
        function showLoader(show) {
            document.getElementById('loader').style.display = show ? 'block' : 'none';
        }

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
        document.getElementById('login-form').addEventListener('submit', async function(e) {
            e.preventDefault();
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            showLoader(true);
            
            try {
                await signInWithEmailAndPassword(auth, email, password);
                showAlert('¡Inicio de sesión exitoso!', 'success');
                showLoader(false);
            } catch (error) {
                showLoader(false);
                console.error("Error en inicio de sesión:", error);
                showAlert(`Error: ${error.message}`, 'error');
            }
        });

        // Registration Form Submission
        document.getElementById('register-form').addEventListener('submit', async function(e) {
            e.preventDefault();
            const name = document.getElementById('register-name').value;
            const email = document.getElementById('register-email').value;
            const phone = document.getElementById('register-phone').value;
            const password = document.getElementById('register-password').value;
            const confirmPassword = document.getElementById('register-confirm').value;
            
            if (password !== confirmPassword) {
                showAlert('Las contraseñas no coinciden', 'error');
                return;
            }
            
            if (password.length < 6) {
                showAlert('La contraseña debe tener al menos 6 caracteres', 'error');
                return;
            }
            
            showLoader(true);
            
            try {
                // Crear usuario en autenticación
                const userCredential = await createUserWithEmailAndPassword(auth, email, password);
                
                // Guardar datos adicionales en Firestore
                const user = userCredential.user;
                await setDoc(doc(db, "users", user.uid), {
                    name: name,
                    email: email,
                    phone: phone,
                    createdAt: serverTimestamp()
                });
                
                showLoader(false);
                showAlert('¡Cuenta creada con éxito! Bienvenido a MarketWhats', 'success');
                
                // Cambiar a pestaña de inicio de sesión después de registro
                setTimeout(() => {
                    document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
                    document.querySelectorAll('.tab-content').forEach(content => content.classList.remove('active'));
                    
                    document.querySelector('.tab-btn[data-tab="login"]').classList.add('active');
                    document.getElementById('login-content').classList.add('active');
                    
                    // Autocompletar email en login
                    document.getElementById('login-email').value = email;
                }, 2000);
                
            } catch (error) {
                showLoader(false);
                console.error("Error en registro:", error);
                
                // Mensajes de error personalizados
                if (error.code === 'auth/email-already-in-use') {
                    showAlert('Este correo electrónico ya está registrado', 'error');
                } else if (error.code === 'auth/weak-password') {
                    showAlert('La contraseña es demasiado débil', 'error');
                } else if (error.code === 'auth/invalid-email') {
                    showAlert('El correo electrónico no es válido', 'error');
                } else {
                    showAlert(`Error: ${error.message}`, 'error');
                }
            }
        });

        // Password Reset
        document.querySelector('.forgot-password').addEventListener('click', async function(e) {
            e.preventDefault();
            const email = prompt('Por favor ingresa tu correo electrónico para restablecer tu contraseña:');
            
            if (email) {
                try {
                    await sendPasswordResetEmail(auth, email);
                    showAlert('Se ha enviado un correo electrónico para restablecer tu contraseña. Por favor revisa tu bandeja de entrada.', 'success');
                } catch (error) {
                    showAlert(`Error: ${error.message}`, 'error');
                }
            }
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Verificar estado de autenticación
        onAuthStateChanged(auth, async (user) => {
            if (user) {
                console.log("Usuario autenticado:", user.uid);
                loginBtn.textContent = "Mi Cuenta";
                
                // Mostrar dashboard y ocultar sección de registro
                dashboardSection.style.display = 'block';
                registrationSection.style.display = 'none';
                
                // Cargar productos del usuario
                await loadUserProducts(user.uid);
                
                // Cargar todos los productos
                await loadAllProducts();
            } else {
                console.log("Usuario no autenticado");
                loginBtn.textContent = "Iniciar Sesión";
                
                // Ocultar dashboard y mostrar sección de registro
                dashboardSection.style.display = 'none';
                registrationSection.style.display = 'block';
                
                // Cargar todos los productos
                await loadAllProducts();
            }
        });

        // Toggle formulario de nuevo producto
        newProductBtn.addEventListener('click', () => {
            productForm.style.display = productForm.style.display === 'none' ? 'block' : 'none';
        });

        // Publicar nuevo producto
        publishForm.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const user = auth.currentUser;
            if (!user) {
                showAlert('Debes iniciar sesión para publicar productos', 'error');
                return;
            }
            
            const productName = document.getElementById('product-name').value;
            const productPrice = document.getElementById('product-price').value;
            const productCategory = document.getElementById('product-category').value;
            const productDescription = document.getElementById('product-description').value;
            const productImage = document.getElementById('product-image').value;
            
            showLoader(true);
            
            try {
                // Guardar producto en Firestore
                await addDoc(collection(db, "products"), {
                    name: productName,
                    price: parseFloat(productPrice),
                    category: productCategory,
                    description: productDescription,
                    image: productImage,
                    sellerId: user.uid,
                    createdAt: serverTimestamp()
                });
                
                showLoader(false);
                showAlert('¡Producto publicado con éxito!', 'success');
                
                // Limpiar formulario
                publishForm.reset();
                productForm.style.display = 'none';
                
                // Recargar productos del usuario
                await loadUserProducts(user.uid);
                
                // Recargar todos los productos
                await loadAllProducts();
                
            } catch (error) {
                showLoader(false);
                console.error("Error al publicar producto:", error);
                showAlert(`Error: ${error.message}`, 'error');
            }
        });

        // Cerrar sesión
        logoutBtn.addEventListener('click', async () => {
            try {
                await signOut(auth);
                showAlert('Sesión cerrada correctamente', 'success');
            } catch (error) {
                console.error("Error al cerrar sesión:", error);
                showAlert(`Error: ${error.message}`, 'error');
            }
        });

        // Cargar productos del usuario
        async function loadUserProducts(userId) {
            myProductsGrid.innerHTML = '';
            
            try {
                const q = query(collection(db, "products"), where("sellerId", "==", userId));
                const querySnapshot = await getDocs(q);
                
                if (querySnapshot.empty) {
                    myProductsGrid.innerHTML = '<p>No has publicado ningún producto aún.</p>';
                    return;
                }
                
                querySnapshot.forEach((doc) => {
                    const product = doc.data();
                    addProductToGrid(product, myProductsGrid, true);
                });
                
            } catch (error) {
                console.error("Error al cargar productos del usuario:", error);
                showAlert(`Error al cargar productos: ${error.message}`, 'error');
            }
        }

        // Cargar todos los productos
        async function loadAllProducts() {
            productsGrid.innerHTML = '';
            
            try {
                const querySnapshot = await getDocs(collection(db, "products"));
                
                if (querySnapshot.empty) {
                    productsGrid.innerHTML = '<p>No hay productos disponibles en este momento.</p>';
                    return;
                }
                
                querySnapshot.forEach((doc) => {
                    const product = doc.data();
                    addProductToGrid(product, productsGrid, false);
                });
                
            } catch (error) {
                console.error("Error al cargar productos:", error);
                showAlert(`Error al cargar productos: ${error.message}`, 'error');
            }
        }

        // Añadir producto a la cuadrícula
        function addProductToGrid(product, grid, isOwner) {
            const productCard = document.createElement('div');
            productCard.className = 'product-card';
            
            let actionsHTML = '';
            if (isOwner) {
                actionsHTML = `
                    <div style="margin-top: 10px; display: flex; gap: 10px;">
                        <button class="btn" style="background-color: #4CAF50; padding: 8px;">
                            <i class="fas fa-edit"></i> Editar
                        </button>
                        <button class="btn" style="background-color: #f44336; padding: 8px;">
                            <i class="fas fa-trash"></i> Eliminar
                        </button>
                    </div>
                `;
            }
            
            productCard.innerHTML = `
                <img src="${product.image}" alt="${product.name}" class="product-img">
                <div class="product-info">
                    <div class="product-category">${product.category}</div>
                    <h3 class="product-title">${product.name}</h3>
                    <div class="product-price">$${product.price.toFixed(2)}</div>
                    <p>${product.description}</p>
                    <div class="product-seller">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Vendedor" class="seller-avatar">
                        <span>${isOwner ? 'Tú' : 'Vendedor'}</span>
                    </div>
                    <a href="https://wa.me/15551234567?text=Hola%20estoy%20interesado%20en%20${encodeURIComponent(product.name)}" 
                       class="whatsapp-btn" target="_blank">
                        <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
                    </a>
                    ${actionsHTML}
                </div>
            `;
            
            grid.appendChild(productCard);
        }

        // Cargar algunos productos de ejemplo iniciales
        window.addEventListener('DOMContentLoaded', async () => {
            // Simular carga de productos mientras se inicializa Firebase
            const exampleProducts = [
                {
                    name: "iPhone 12 Pro Max 256GB",
                    price: 850,
                    category: "Tecnología",
                    description: "iPhone 12 Pro Max en excelente estado, con 256GB de almacenamiento. Incluye cargador y estuche.",
                    image: "https://images.unsplash.com/photo-1546868871-7041f2a55e12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80"
                },
                {
                    name: "Bicicleta Montañera Profesional",
                    price: 320,
                    category: "Deportes",
                    description: "Bicicleta profesional para montaña, apenas usada. Incluye accesorios de seguridad.",
                    image: "https://images.unsplash.com/photo-1566150902887-9679ecc155ba?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80"
                }
            ];
            
            exampleProducts.forEach(product => {
                addProductToGrid(product, productsGrid, false);
            });
        });
    </script>
</body>
</html>
