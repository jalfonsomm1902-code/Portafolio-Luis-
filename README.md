# Portafolio-Luis-<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luis Fernández | Asistente Virtual Inmobiliario</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    
    <style>
        /* --- Variables CSS --- */
        :root {
            --primary-color: #1a2a3a; /* Azul oscuro profesional */
            --secondary-color: #c5a47e; /* Tono dorado/beige inmobiliario */
            --text-dark: #333333;
            --text-light: #ffffff;
            --whatsapp-green: #25D366;
            --bg-light: #f4f7f6;
        }

        /* --- Reseteo y Estilos Base --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background-color: var(--bg-light);
        }

        h1, h2, h3 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 700;
        }

        a { text-decoration: none; }

        /* --- Componentes --- */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            text-transform: uppercase;
            font-size: 0.9rem;
        }

        .btn-whatsapp {
            background-color: var(--whatsapp-green);
            color: white;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
        }

        .btn-whatsapp:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(37, 211, 102, 0.6);
        }

        /* --- HERO SECTION (El fondo de casas) --- */
        .hero {
            /* IMPORTANTE: Reemplaza esta URL con una imagen de casas de alta calidad */
            background-image: linear-gradient(rgba(26, 42, 58, 0.85), rgba(26, 42, 58, 0.7)), url('https://images.unsplash.com/photo-1560518883-ce09059eeffa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1973&q=80');
            background-size: cover;
            background-position: center;
            height: 85vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: var(--text-light);
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            letter-spacing: 1px;
        }

        .hero-content h2 {
            font-size: 1.5rem;
            font-weight: 400;
            color: var(--secondary-color);
            margin-bottom: 30px;
        }

        .hero-tagline {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 40px auto;
            opacity: 0.9;
        }

        /* --- SECCIÓN DE SERVICIOS --- */
        .services-section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 50px;
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 80px;
            height: 4px;
            background-color: var(--secondary-color);
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .service-card {
            background: white;
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            text-align: center;
            transition: transform 0.3s ease;
            border-bottom: 4px solid transparent;
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-bottom: 4px solid var(--secondary-color);
        }

        .service-icon {
            font-size: 3rem;
            color: var(--secondary-color);
            margin-bottom: 25px;
        }

        .service-card h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        .service-card ul {
            text-align: left;
            list-style: none;
            padding-left: 15px;
        }

        .service-card ul li {
            margin-bottom: 10px;
            position: relative;
        }

        .service-card ul li::before {
            content: '✓';
            color: var(--whatsapp-green);
            position: absolute;
            left: -20px;
            font-weight: bold;
        }

        /* --- FOOTER Y CONTACTO --- */
        .footer {
            background-color: var(--primary-color);
            color: var(--text-light);
            padding: 50px 0 80px 0; /* Padding extra abajo para el botón móvil */
            text-align: center;
        }

        .footer-contact-info h3 {
            color: var(--secondary-color);
            margin-bottom: 20px;
        }

        .phone-number {
            font-size: 1.8rem;
            font-family: 'Montserrat', sans-serif;
            font-weight: 700;
            margin: 20px 0;
            display: block;
            color: white;
        }

        /* --- BOTÓN WHATSAPP FLOTANTE (Móvil) --- */
        .sticky-whatsapp {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 400px;
            text-align: center;
            z-index: 100;
            display: none; /* Oculto por defecto en PC */
            animation: slideUp 0.5s ease-out;
        }

        .sticky-whatsapp a {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 15px 20px;
            font-size: 1.1rem;
        }

        @keyframes slideUp {
            from { bottom: -70px; opacity: 0; }
            to { bottom: 20px; opacity: 1; }
        }

        /* --- RESPONSIVE DESIGN --- */
        @media (max-width: 768px) {
            .hero-content h1 { font-size: 2.5rem; }
            .hero-content h2 { font-size: 1.2rem; }
            .section-title { font-size: 2rem; }
            
            /* Mostrar el botón flotante en móviles */
            .sticky-whatsapp { display: block; }
        }
    </style>
</head>
<body>

    <header class="hero">
        <div class="container hero-content">
            <h1>LUIS FERNÁNDEZ</h1>
            <h2>El Asistente Virtual Estratégico para Realtors Exitosos</h2>
            <p class="hero-tagline">Libera tu tiempo para cerrar más tratos. Yo me encargo de la administración, el marketing y la coordinación de tus propiedades.</p>
            <a href="https://wa.me/584245385650?text=Hola%20Luis,%20vi%20tu%20portafolio%20y%20estoy%20interesado%20en%20tus%20servicios%20para%20realtors." class="btn btn-whatsapp" target="_blank">
                <i class="fab fa-whatsapp"></i> Agendar Consulta Gratuita
            </a>
        </div>
    </header>

    <section class="services-section" id="servicios">
        <div class="container">
            <h2 class="section-title">Potencia tu Negocio Inmobiliario</h2>
            
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon"><i class="fas fa-tasks"></i></div>
                    <h3>Gestión Administrativa y CRM</h3>
                    <ul>
                        <li>Manejo y limpieza de tu base de datos (CRM).</li>
                        <li>Gestión proactiva de correo electrónico y agenda.</li>
                        <li>Programación de showings y citas con clientes.</li>
                        <li>Data entry y preparación de reportes.</li>
                    </ul>
                </div>

                <div class="service-card">
                    <div class="service-icon"><i class="fas fa-bullhorn"></i></div>
                    <h3>Marketing Digital para Propiedades</h3>
                    <ul>
                        <li>Creación de flyers digitales y fichas de propiedad.</li>
                        <li>Gestión de redes sociales (Instagram/Facebook Ads).</li>
                        <li>Edición básica de fotos y videos para listings.</li>
                        <li>Campañas de email marketing a prospectos.</li>
                    </ul>
                </div>

                <div class="service-card">
                    <div class="service-icon"><i class="fas fa-file-signature"></i></div>
                    <h3>Soporte a Transacciones (TC Support)</h3>
                    <ul>
                        <li>Seguimiento de documentos y plazos críticos.</li>
                        <li>Comunicación con notarías, agentes y clientes.</li>
                        <li>Recopilación de feedback después de las visitas.</li>
                        <li>Preparación de paquetes de bienvenida/cierre.</li>
                    </ul>
                </div>
                 <div class="service-card">
                    <div class="service-icon"><i class="fas fa-headset"></i></div>
                    <h3>Atención y Seguimiento a Leads</h3>
                    <ul>
                        <li>Respuesta rápida a consultas entrantes.</li>
                        <li>Pre-calificación básica de prospectos.</li>
                        <li>Seguimiento de leads fríos para reactivarlos.</li>
                        <li>Recordatorios de aniversarios de compra a clientes pasados.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <footer class="footer">
        <div class="container footer-contact-info">
            <h3>¿Listo para escalar tu negocio? Hablemos.</h3>
            <p>Contáctame directamente y diseñemos un plan de trabajo a tu medida.</p>
            
            <a href="tel:+584245385650" class="phone-number">
                <i class="fas fa-phone-alt"></i> 0424-538-5650
            </a>
            
            <div style="margin-top: 30px; font-size: 0.9rem; opacity: 0.7;">
                © 2024 Luis Fernández. Todos los derechos reservados.
            </div>
        </div>
    </footer>

    <div class="sticky-whatsapp">
        <a href="https://wa.me/584245385650?text=Hola%20Luis,%20necesito%20información%20sobre%20tus%20servicios%20de%20VA." class="btn btn-whatsapp" target="_blank">
            <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
        </a>
    </div>

</body>
</html>
