
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Supermercado Largacha | Durazno</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- CONFIGURACIÓN GENERAL --- */
        :root {
            --primary: #22c55e;
            --primary-dark: #16a34a;
            --dark: #1f2937;
            --gray: #6b7280;
            --light-bg: #f9fafb;
            --white: #ffffff;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --radius: 12px;
        }

        /* ESTO HACE QUE LOS BOTONES NAVEGUEN SUAVEMENTE */
        html {
            scroll-behavior: smooth;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        body {
            color: var(--dark);
            background-color: var(--white);
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; }
        ul { list-style: none; }

        /* --- BOTONES --- */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 10px 24px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.95rem;
            border: none; /* Reset borde por defecto */
        }

        .btn-primary {
            background-color: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            color: white; /* Asegurar texto blanco */
        }

        .btn-outline {
            background-color: transparent;
            border: 1px solid #d1d5db; /* Gris visible */
            color: var(--dark);
        }

        .btn-outline:hover {
            border-color: var(--dark);
            background-color: #f3f4f6;
        }

        /* --- HEADER / NAV --- */
        header {
            position: sticky;
            top: 0;
            background: rgba(255, 255, 255, 0.98);
            border-bottom: 1px solid #e5e7eb;
            z-index: 1000;
            padding: 1rem 5%;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.25rem;
            font-weight: 700;
            white-space: nowrap;
        }

        .logo i {
            color: var(--white);
            background-color: var(--primary);
            padding: 8px;
            border-radius: 8px;
            font-size: 1rem;
        }

        .logo span { color: var(--primary); }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            font-size: 0.95rem;
            color: var(--gray);
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-actions {
            display: flex;
            gap: 15px;
        }

        /* --- HERO SECTION (CORREGIDO) --- */
        .hero {
            position: relative;
            padding: 80px 5%;
            background-color: var(--dark);
            /* IMAGEN DE FONDO REAL DE UN SUPERMERCADO (Fuente estable) */
            background-image: linear-gradient(rgba(0,0,0,0.65), rgba(0,0,0,0.65)), url('https://images.unsplash.com/photo-1578916171728-46686eac8d58?q=80&w=1974&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            color: white;
            min-height: 600px;
            display: flex;
            align-items: center;
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        .badge {
            background-color: rgba(255,255,255,0.2);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            margin-bottom: 20px;
            color: #fbbf24;
            backdrop-filter: blur(5px);
        }

        .hero h1 {
            font-size: 3.5rem;
            line-height: 1.1;
            margin-bottom: 20px;
            max-width: 700px;
            font-weight: 800;
        }

        .hero h1 span { color: var(--primary); }

        .hero p {
            font-size: 1.2rem;
            color: #e5e7eb;
            max-width: 600px;
            margin-bottom: 30px;
        }

        .hero-features {
            display: flex;
            gap: 25px;
            margin-bottom: 35px;
            font-size: 0.95rem;
            color: #d1d5db;
            font-weight: 500;
        }

        .hero-features div { display: flex; align-items: center; gap: 8px; }
        .hero-features i { color: var(--primary); }

        /* --- SECCIONES GENERALES --- */
        .section-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 80px 20px;
            scroll-margin-top: 80px; /* Para que el menú no tape el título al hacer click */
        }

        .section-header {
            text-align: left;
            margin-bottom: 50px;
        }

        .tag {
            background-color: #dcfce7;
            color: var(--primary-dark);
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
            display: inline-block;
        }

        .section-header h2 {
            font-size: 2.5rem;
            color: var(--dark);
            margin-bottom: 15px;
        }

        .section-header p {
            color: var(--gray);
            max-width: 600px;
        }

        /* --- LAYOUTS ESPECÍFICOS --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .benefits-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .benefit-card {
            background: var(--white);
            padding: 25px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid #f3f4f6;
        }

        .benefit-icon {
            width: 50px; height: 50px; background-color: #dcfce7; color: var(--primary);
            border-radius: 12px; display: flex; align-items: center; justify-content: center;
            font-size: 1.5rem; margin-bottom: 15px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .product-card {
            background: var(--white);
            padding: 30px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid #f3f4f6;
            transition: transform 0.3s ease;
            text-align: left;
        }

        .product-card:hover { transform: translateY(-5px); border-color: var(--primary); }

        .p-icon { font-size: 2rem; color: var(--primary); margin-bottom: 15px; display: block; }
        .product-card h3 { margin-bottom: 10px; }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .review-card {
            background: var(--white);
            padding: 30px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid #f3f4f6;
        }

        .stars { color: #fbbf24; margin-bottom: 15px; }
        .quote-icon {
            background-color: var(--primary);
            color: white; width: 40px; height: 40px; border-radius: 50%;
            display: flex; align-items: center; justify-content: center; margin-bottom: 20px;
        }

        .review-text { font-style: italic; color: var(--gray); margin-bottom: 20px; }
        .reviewer { font-weight: 700; display: flex; align-items: center; gap: 10px; }
        .reviewer-avatar {
            width: 40px; height: 40px; background: #e5e7eb; border-radius: 50%;
            display: flex; align-items: center; justify-content: center; color: var(--gray);
        }

        /* --- CONTACTO --- */
        .contact-layout {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .info-card {
            display: flex;
            gap: 20px;
            padding: 20px;
            background: var(--white);
            border: 1px solid #e5e7eb;
            border-radius: var(--radius);
            margin-bottom: 20px;
            align-items: center;
        }

        .info-icon {
            width: 50px; height: 50px; background: #dcfce7; color: var(--primary);
            border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 1.2rem;
        }

        .cta-box {
            background-color: var(--primary);
            color: white;
            padding: 40px;
            border-radius: var(--radius);
            text-align: center;
            box-shadow: 0 10px 15px -3px rgba(34, 197, 94, 0.3);
        }

        .cta-box h3 { font-size: 1.8rem; margin-bottom: 10px; }
        .cta-box button { 
            background-color: #ffffff; 
            color: var(--primary); 
            border: none; 
            font-size: 1.1rem; 
            padding: 15px 30px; 
            margin-top: 20px; 
            font-weight: 700;
        }
        .cta-box button:hover { background-color: #f0fdf4; transform: scale(1.05); }

        /* --- MAPA CORREGIDO --- */
        .map-frame {
            width: 100%;
            height: 350px;
            border-radius: var(--radius);
            overflow: hidden;
            border: 1px solid #e5e7eb;
            background: #e5e7eb;
        }

        .map-frame iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* --- FOOTER --- */
        footer {
            background-color: #111827;
            color: #9ca3af;
            padding: 60px 5% 30px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
            border-bottom: 1px solid #374151;
            padding-bottom: 40px;
        }

        .footer-brand h4 { color: white; font-size: 1.5rem; margin-bottom: 15px; display: flex; align-items: center; gap: 10px; }
        .footer-links h5 { color: white; margin-bottom: 15px; font-weight: 600; }
        .footer-links ul li { margin-bottom: 10px; }
        .footer-links a:hover { color: var(--primary); }

        .copyright {
            text-align: center;
            padding-top: 30px;
            font-size: 0.9rem;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .nav-links, .nav-actions { display: none; } /* Ocultar en móvil para demo simple */
            .logo { flex-grow: 1; justify-content: center; }
            .hero h1 { font-size: 2.5rem; }
            .about-grid, .contact-layout, .footer-content { grid-template-columns: 1fr; }
            .hero-features { flex-direction: column; gap: 10px; }
            .hero { padding-top: 40px; text-align: center; }
            .hero-content { display: flex; flex-direction: column; align-items: center; }
            .hero p { margin-bottom: 20px; }
        }
    </style>
</head>
<body>

    <header>
        <nav>
            <div class="logo">
                <i class="fa-solid fa-basket-shopping"></i>
                Supermercado <span>Largacha</span>
            </div>
            <ul class="nav-links">
                <li><a href="#">Inicio</a></li>
                <li><a href="#nosotros">Nosotros</a></li>
                <li><a href="#productos">Productos</a></li>
                <li><a href="#testimonios">Testimonios</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
            <div class="nav-actions">
                <a href="https://www.google.com/maps/search/Supermercado+Largacha+Durazno" target="_blank" class="btn btn-outline">Cómo llegar</a>
                <a href="tel:092724550" class="btn btn-primary"><i class="fa-solid fa-phone"></i> Llamar ahora</a>
            </div>
        </nav>
    </header>

    <section class="hero">
        <div class="hero-content">
            <div class="badge"><i class="fa-solid fa-star"></i> 4.5 • 56 reseñas • Supermercado de confianza</div>
            <h1>Tu supermercado de <br><span>confianza</span> en <br>Durazno</h1>
            <p>Buen surtido, atención rápida y entrega a domicilio. Encuentra todo lo que necesitás para tu hogar con la calidad y cercanía de siempre.</p>
            
            <div class="hero-features">
                <div><i class="fa-solid fa-truck"></i> Entrega a domicilio</div>
                <div><i class="fa-regular fa-clock"></i> Atención rápida</div>
                <div><i class="fa-solid fa-bag-shopping"></i> Gran variedad</div>
            </div>

            <div style="display: flex; gap: 15px; flex-wrap: wrap; justify-content: center;">
                <a href="tel:092724550" class="btn btn-primary" style="padding: 15px 30px;">Llamar ahora</a>
               
            </div>
        </div>
    </section>

    <section id="nosotros" class="section-container">
        <div class="about-grid">
            <div class="about-text">
                <span class="tag">Sobre Nosotros</span>
                <h2>Tu supermercado de barrio en <span style="color:var(--primary)">Durazno</span></h2>
                <p style="margin-bottom: 20px;">
                    En <strong>Supermercado Largacha</strong> nos enorgullece ser parte de la comunidad de Durazno. Ofrecemos un local bien surtido con las mejores marcas de productos alimenticios, atención rápida y un servicio de autoservicio cómodo para vos.
                </p>
                <p>
                    Nuestro compromiso es brindarte calidad, buenos precios y la cercanía que solo un negocio de barrio puede ofrecer. Además, contamos con entrega a domicilio para tu comodidad.
                </p>
                
            </div>

            <div class="benefits-grid">
                <div class="benefit-card">
                    <div class="benefit-icon"><i class="fa-regular fa-heart"></i></div>
                    <h3>Atención personalizada</h3>
                    <p>Te atendemos como vecinos, con calidez y cercanía.</p>
                </div>
                <div class="benefit-card">
                    <div class="benefit-icon"><i class="fa-solid fa-users"></i></div>
                    <h3>Negocio familiar</h3>
                    <p>Tradición y compromiso sirviendo a la comunidad.</p>
                </div>
                <div class="benefit-card">
                    <div class="benefit-icon"><i class="fa-regular fa-clock"></i></div>
                    <h3>Servicio rápido</h3>
                    <p>Atención ágil para que no pierdas tiempo.</p>
                </div>
                <div class="benefit-card">
                    <div class="benefit-icon"><i class="fa-solid fa-award"></i></div>
                    <h3>Productos de calidad</h3>
                    <p>Las mejores marcas al mejor precio.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="productos" class="section-container bg-light" style="background: white;">
        <div class="section-header" style="text-align: center;">
            <span class="tag">Lo que ofrecemos</span>
            <h2>Todo lo que necesitás en un solo lugar</h2>
            <p style="margin: 0 auto;">Amplia variedad de productos de calidad para abastecer tu hogar.</p>
        </div>

        <div class="products-grid">
            <div class="product-card">
                <i class="fa-solid fa-apple-whole p-icon"></i>
                <h3>Alimentos frescos</h3>
                <p>Frutas, verduras y productos de calidad.</p>
            </div>
            <div class="product-card">
                <i class="fa-solid fa-basket-shopping p-icon"></i>
                <h3>Productos de almacén</h3>
                <p>Todo lo esencial para tu despensa.</p>
            </div>
            <div class="product-card">
                <i class="fa-solid fa-wine-glass p-icon"></i>
                <h3>Bebidas</h3>
                <p>Refrescos, aguas, jugos y más.</p>
            </div>
            <div class="product-card">
                <i class="fa-solid fa-sparkles p-icon"></i>
                <h3>Limpieza</h3>
                <p>Productos para mantener tu hogar impecable.</p>
            </div>
            <div class="product-card">
                <i class="fa-solid fa-heart-pulse p-icon"></i>
                <h3>Cuidado personal</h3>
                <p>Higiene y cuidado para toda la familia.</p>
            </div>
            <div class="product-card">
                <i class="fa-solid fa-box-open p-icon"></i>
                <h3>Variedad de marcas</h3>
                <p>Las mejores marcas del mercado.</p>
            </div>
        </div>
        
        <div style="text-align: center; margin-top: 40px;">
             <div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap;">
                <div style="background: #ecfdf5; padding: 20px; border-radius: 12px; display: flex; align-items: center; gap: 15px; border: 1px solid #d1fae5;">
                    <div style="background: var(--primary); color: white; padding: 10px; border-radius: 8px;"><i class="fa-solid fa-truck"></i></div>
                    <div style="text-align: left;">
                        <strong>Entrega a domicilio</strong><br>
                        <span style="font-size: 0.9rem; color: var(--gray);">Te llevamos tus compras a casa</span>
                    </div>
                </div>
                <div style="background: #ecfdf5; padding: 20px; border-radius: 12px; display: flex; align-items: center; gap: 15px; border: 1px solid #d1fae5;">
                    <div style="background: var(--primary); color: white; padding: 10px; border-radius: 8px;"><i class="fa-solid fa-tag"></i></div>
                    <div style="text-align: left;">
                        <strong>Promociones semanales</strong><br>
                        <span style="font-size: 0.9rem; color: var(--gray);">Ofertas especiales para que ahorres</span>
                    </div>
                </div>
             </div>
        </div>
    </section>

    <section id="testimonios" class="section-container">
        <div class="section-header" style="text-align: center;">
            <span class="tag">Testimonios</span>
            <h2>Lo que dicen nuestros clientes</h2>
            <div style="font-size: 1.2rem; margin-top: 10px; color: #fbbf24;">
                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star-half-stroke"></i>
                <span style="color: var(--dark); font-weight: 700;">4.5</span> <span style="color: var(--gray); font-size: 0.9rem;">(56 reseñas en Google)</span>
            </div>
        </div>

        <div class="testimonials-grid">
            <div class="review-card">
                <div class="quote-icon"><i class="fa-solid fa-quote-left"></i></div>
                <div class="stars">
                    <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                </div>
                <p class="review-text">"Excelente local, muy bien surtido. Buenas marcas de productos alimenticios. Con servicio de autoservicio."</p>
                <div class="reviewer">
                    <div class="reviewer-avatar">M</div>
                    <div>
                        <p>Mary Javi</p>
                        <span style="font-size: 0.8rem; color: var(--gray); font-weight: 400;">Hace 3 años</span>
                    </div>
                </div>
            </div>

            <div class="review-card">
                <div class="quote-icon"><i class="fa-solid fa-quote-left"></i></div>
                <div class="stars">
                    <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                </div>
                <p class="review-text">"Excelente lugar, rapidez y atención. Muy atentos con los clientes."</p>
                <div class="reviewer">
                    <div class="reviewer-avatar">E</div>
                    <div>
                        <p>Eddy Fizzio</p>
                        <span style="font-size: 0.8rem; color: var(--gray); font-weight: 400;">Hace 1 año</span>
                    </div>
                </div>
            </div>

             <div class="review-card">
                <div class="quote-icon"><i class="fa-solid fa-quote-left"></i></div>
                <div class="stars">
                    <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                </div>
                <p class="review-text">"Un supermercado de barrio con todo lo que necesito. Siempre encuentro lo que busco y la atención es muy buena."</p>
                <div class="reviewer">
                    <div class="reviewer-avatar">C</div>
                    <div>
                        <p>Cliente Satisfecho</p>
                        <span style="font-size: 0.8rem; color: var(--gray); font-weight: 400;">Cliente frecuente</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contacto" class="section-container">
        <div class="section-header">
            <span class="tag">Contacto</span>
            <h2>Visitanos o contactanos</h2>
            <p>Estamos ubicados en el corazón de Durazno. Visitanos en nuestro local o llamanos para hacer tu pedido con entrega a domicilio.</p>
        </div>

        <div class="contact-layout">
            <div class="contact-info">
                <div class="info-card">
                    <div class="info-icon"><i class="fa-solid fa-phone"></i></div>
                    <div>
                        <span style="font-size: 0.85rem; color: var(--gray);">Teléfono</span>
                        <h4 style="font-size: 1.2rem;">092 724 550</h4>
                        <a href="tel:092724550" style="color: var(--primary); font-size: 0.9rem; font-weight: 600;">Llamar ahora</a>
                    </div>
                </div>

                <div class="info-card">
                    <div class="info-icon"><i class="fa-solid fa-location-dot"></i></div>
                    <div>
                        <span style="font-size: 0.85rem; color: var(--gray);">Dirección</span>
                        <h4 style="font-size: 1.2rem;">Durazno, Uruguay</h4>
                        <span style="color: var(--gray); font-size: 0.9rem;">JF5V+5P3, 97000</span><br>
                        
                    </div>
                </div>

                <div class="info-card">
                    <div class="info-icon"><i class="fa-regular fa-clock"></i></div>
                    <div>
                        <span style="font-size: 0.85rem; color: var(--gray);">Horario</span>
                        <h4 style="font-size: 1.2rem;">Lunes a Sábado</h4>
                        <span style="color: var(--gray); font-size: 0.9rem;">08:00 - 20:00 (Aprox)</span>
                    </div>
                </div>
            </div>

            <div style="display: flex; flex-direction: column; gap: 20px;">
                <div class="map-frame">
                    <iframe 
                        src="https://maps.google.com/maps?q=Supermercado+Largacha+Durazno+Uruguay&t=&z=15&ie=UTF8&iwloc=&output=embed" 
                        allowfullscreen 
                        loading="lazy">
                    </iframe>
                </div>

                <div class="cta-box">
                    <h3>¿Necesitás hacer un pedido?</h3>
                    <p>Llamanos y te lo llevamos a domicilio</p>
                    <button onclick="window.location.href='tel:092724550'"><i class="fa-solid fa-phone"></i> 092 724 550</button>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-content">
            <div class="footer-brand">
                <div class="logo" style="margin-bottom: 20px;">
                    <i class="fa-solid fa-basket-shopping"></i>
                    <span style="color: white;">Supermercado <span style="color: var(--primary);">Largacha</span></span>
                </div>
                <p>Tu supermercado de confianza en Durazno. Calidad, atención y cercanía para toda la comunidad.</p>
                <div style="margin-top: 20px; display: flex; gap: 10px;">
                    <a href="tel:092724550" class="btn btn-outline" style="border-color: #374151; color: white;"><i class="fa-solid fa-phone"></i> Llamar</a>
                   
                </div>
            </div>

            <div class="footer-links">
                <h5>Enlaces</h5>
                <ul>
                    <li><a href="#">Inicio</a></li>
                    <li><a href="#nosotros">Nosotros</a></li>
                    <li><a href="#productos">Productos</a></li>
                    <li><a href="#testimonios">Testimonios</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </div>

            <div class="footer-links">
                <h5>Contacto</h5>
                <ul>
                    <li style="display: flex; gap: 10px; align-items: center;"><i class="fa-solid fa-phone" style="color: var(--primary);"></i> 092 724 550</li>
                    <li style="display: flex; gap: 10px; align-items: center;"><i class="fa-solid fa-location-dot" style="color: var(--primary);"></i> Durazno, Uruguay</li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            © 2025 Supermercado Largacha. Todos los derechos reservados. <br>
            <span style="color: #4b5563; font-size: 0.8rem;">Hecho con <i class="fa-solid fa-heart" style="color: #ef4444;"></i> en Durazno, Uruguay</span>
        </div>
    </footer>

</body>
</html>
