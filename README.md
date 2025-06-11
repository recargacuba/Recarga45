<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recargas Premium | Máximo Rendimiento</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4cc9f0;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4ade80;
            --warning: #f59e0b;
            --card-bg: #ffffff;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f0f4ff, #e6f7ff);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin: 0 auto;
        }
        
        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
        }
        
        /* Panel Izquierdo - Información */
        .info-panel {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 40px;
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            overflow: hidden;
            animation: fadeIn 0.8s ease-out;
        }
        
        .info-panel::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--primary), var(--accent));
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 25px;
        }
        
        .logo i {
            font-size: 2.2rem;
            color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--dark);
        }
        
        .tagline {
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 30px;
            font-weight: 400;
        }
        
        .highlight {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
        }
        
        .features {
            margin: 25px 0;
        }
        
        .feature {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 18px;
            padding: 12px 15px;
            border-radius: 12px;
            transition: var(--transition);
        }
        
        .feature:hover {
            background: rgba(67, 97, 238, 0.05);
            transform: translateX(5px);
        }
        
        .feature i {
            font-size: 1.2rem;
            color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        
        .feature-content h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .feature-content p {
            font-size: 0.95rem;
            color: #666;
        }
        
        .contact-methods {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }
        
        .contact-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 20px;
            border-radius: 10px;
            background: var(--light);
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            border: 1px solid #e9ecef;
        }
        
        .contact-btn:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.3);
        }
        
        .contact-btn.whatsapp:hover {
            background: #25D366;
        }
        
        /* Panel Derecho - Oferta */
        .offer-panel {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 40px;
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            animation: slideIn 0.8s ease-out;
        }
        
        .offer-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .offer-header h2 {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 10px;
        }
        
        .offer-amount {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 20px 0;
        }
        
        .offer-card {
            background: linear-gradient(135deg, rgba(67, 97, 238, 0.05), rgba(76, 201, 240, 0.05));
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 25px;
            border: 1px solid rgba(67, 97, 238, 0.1);
        }
        
        .offer-card h3 {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .offer-card h3 i {
            font-size: 1.4rem;
        }
        
        .options-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        @media (max-width: 480px) {
            .options-grid {
                grid-template-columns: 1fr;
            }
        }
        
        .option {
            background: white;
            border-radius: 12px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: var(--transition);
            border: 1px solid #e9ecef;
        }
        
        .option:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05);
            border-color: var(--accent);
        }
        
        .option-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(67, 97, 238, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
        }
        
        .option-icon i {
            font-size: 1.8rem;
            color: var(--primary);
        }
        
        .option-amount {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 5px;
            color: var(--dark);
        }
        
        .option-label {
            font-size: 0.9rem;
            color: #666;
            text-align: center;
        }
        
        .cta-container {
            margin-top: auto;
            text-align: center;
        }
        
        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 16px 40px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 10px 25px rgba(67, 97, 238, 0.3);
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(67, 97, 238, 0.4);
        }
        
        .cta-button:active {
            transform: translateY(0);
        }
        
        .note {
            font-size: 0.85rem;
            color: #777;
            margin-top: 20px;
            text-align: center;
            line-height: 1.6;
        }
        
        /* Animaciones */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Panel de Información -->
        <div class="info-panel">
            <div class="logo">
                <i class="fas fa-bolt"></i>
                <h1>Recargas <span class="highlight">Premium</span></h1>
            </div>
            
            <p class="tagline">Olvídate de las estafas de ETECSA. Aquí tu dinero <span class="highlight">vale más</span>.</p>
            
            <div class="features">
                <div class="feature">
                    <i class="fas fa-rocket"></i>
                    <div class="feature-content">
                        <h3>Rápido y Seguro</h3>
                        <p>Transacciones instantáneas con máxima seguridad</p>
                    </div>
                </div>
                
                <div class="feature">
                    <i class="fas fa-chart-line"></i>
                    <div class="feature-content">
                        <h3>Máximo Rendimiento</h3>
                        <p>Obtén hasta un 30% más de saldo que en ETECSA</p>
                    </div>
                </div>
                
                <div class="feature">
                    <i class="fas fa-headset"></i>
                    <div class="feature-content">
                        <h3>Soporte 24/7</h3>
                        <p>Atención personalizada cuando la necesites</p>
                    </div>
                </div>
            </div>
            
            <h3>Contáctanos ahora:</h3>
            <div class="contact-methods">
                <a href="#" class="contact-btn">
                    <i class="fab fa-facebook-messenger"></i> Messenger
                </a>
                <a href="#" class="contact-btn whatsapp">
                    <i class="fab fa-whatsapp"></i> WhatsApp
                </a>
            </div>
        </div>
        
        <!-- Panel de Oferta -->
        <div class="offer-panel">
            <div class="offer-header">
                <h2>Oferta Especial</h2>
                <p>Recarga por Zelle y obtén el máximo beneficio</p>
            </div>
            
            <div class="offer-amount">$20 USD</div>
            
            <div class="offer-card">
                <h3><i class="fas fa-mobile-alt"></i> Recibirás 2520 CUP de saldo móvil</h3>
                <p>Con esos 2520 CUP puedes comprar en ETECSA:</p>
                
                <div class="options-grid">
                    <div class="option">
                        <div class="option-icon">
                            <i class="fas fa-wifi"></i>
                        </div>
                        <div class="option-amount">42 GB</div>
                        <div class="option-label">Datos móviles</div>
                    </div>
                    
                    <div class="option">
                        <div class="option-icon">
                            <i class="fas fa-phone-alt"></i>
                        </div>
                        <div class="option-amount">420 min</div>
                        <div class="option-label">Llamadas</div>
                    </div>
                    
                    <div class="option">
                        <div class="option-icon">
                            <i class="fas fa-sms"></i>
                        </div>
                        <div class="option-amount">490 SMS</div>
                        <div class="option-label">Mensajes</div>
                    </div>
                    
                    <div class="option">
                        <div class="option-icon">
                            <i class="fas fa-gift"></i>
                        </div>
                        <div class="option-amount">+ Bonos</div>
                        <div class="option-label">Adicionales</div>
                    </div>
                </div>
            </div>
            
            <p class="highlight" style="text-align: center; font-size: 1.2rem; margin: 20px 0;">¡Así de claro! Tu saldo, tu elección.</p>
            
            <div class="cta-container">
                <button class="cta-button pulse">
                    <i class="fas fa-bolt"></i> ¡QUIERO MI RECARGA AHORA!
                </button>
                <p class="note">* Servicio independiente no afiliado a ETECSA. <br>Verifica las condiciones actuales antes de realizar transacciones.</p>
            </div>
        </div>
    </div>

    <script>
        // Animación para los elementos al hacer scroll
        document.addEventListener('DOMContentLoaded', function() {
            const features = document.querySelectorAll('.feature');
            const options = document.querySelectorAll('.option');
            
            features.forEach((feature, index) => {
                setTimeout(() => {
                    feature.style.opacity = '1';
                    feature.style.transform = 'translateX(0)';
                }, 300 * index);
            });
            
            options.forEach((option, index) => {
                setTimeout(() => {
                    option.style.opacity = '1';
                    option.style.transform = 'translateY(0)';
                }, 300 * index);
            });
            
            // Efecto para el botón de CTA
            const ctaButton = document.querySelector('.cta-button');
            ctaButton.addEventListener('click', function() {
                this.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Procesando...';
                setTimeout(() => {
                    this.innerHTML = '<i class="fas fa-check"></i> ¡Recarga Solicitada!';
                    this.style.background = 'linear-gradient(to right, #4ade80, #22c55e)';
                }, 1500);
            });
        });
    </script>
</body>
</html>
