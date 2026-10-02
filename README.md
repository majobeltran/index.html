<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>MBStore | Cosméticos y belleza</title>

    <meta name="description"
          content="MBStore - Plataforma web para la gestión y venta de productos cosméticos en El Espinal, Tolima.">

    <style>

        /* =========================
           CONFIGURACIÓN GENERAL
        ========================= */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #fff8fb;
            color: #3d3036;
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        button,
        input {
            font-family: inherit;
        }

        /* =========================
           ENCABEZADO
        ========================= */

        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(255, 255, 255, 0.96);
            border-bottom: 1px solid #f0dce5;
            box-shadow: 0 3px 15px rgba(80, 40, 60, 0.08);
        }

        .header-container {
            max-width: 1200px;
            margin: auto;
            padding: 15px 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
        }

        .logo {
            font-size: 28px;
            font-weight: 900;
            letter-spacing: 1px;
            color: #c94f83;
        }

        .logo span {
            color: #4f3842;
        }

        nav {
            display: flex;
            gap: 22px;
            align-items: center;
        }

        nav a {
            font-weight: 700;
            color: #4f3842;
            transition: 0.3s;
        }

        nav a:hover {
            color: #c94f83;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .language-btn,
        .cart-btn {
            border: none;
            padding: 9px 13px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            background: #f9e3ec;
            color: #9d3e68;
            transition: 0.3s;
        }

        .language-btn:hover,
        .cart-btn:hover {
            transform: translateY(-2px);
            background: #f2cbdc;
        }

        /* =========================
           HERO
        ========================= */

        .hero {
            min-height: 620px;
            display: flex;
            align-items: center;
            background:
                radial-gradient(circle at top right, #f9d8e7, transparent 35%),
                linear-gradient(135deg, #fff8fb, #fdebf3);
        }

        .hero-container {
            max-width: 1200px;
            width: 100%;
            margin: auto;
            padding: 70px 25px;
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            align-items: center;
            gap: 60px;
        }

        .hero-text h1 {
            font-size: clamp(45px, 7vw, 78px);
            line-height: 1;
            color: #bd4779;
            margin-bottom: 20px;
        }

        .hero-text h1 span {
            color: #49343d;
        }

        .hero-text h2 {
            font-size: 25px;
            margin-bottom: 15px;
        }

        .hero-text p {
            max-width: 650px;
            font-size: 18px;
            color: #66535c;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .primary-btn,
        .secondary-btn {
            border: none;
            padding: 14px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: 0.3s;
        }

        .primary-btn {
            background: #c94f83;
            color: white;
        }

        .primary-btn:hover {
            background: #a93d6a;
            transform: translateY(-3px);
        }

        .secondary-btn {
            background: white;
            color: #bd4779;
            border: 2px solid #e7a8c3;
        }

        .secondary-btn:hover {
            background: #fff0f6;
            transform: translateY(-3px);
        }

        .hero-card {
            min-height: 400px;
            border-radius: 35px;
            background: linear-gradient(145deg, #f6c8dc, #fff);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(120, 50, 85, 0.16);
        }

        .hero-products {
            display: flex;
            align-items: end;
            gap: 15px;
        }

        .cosmetic {
            width: 90px;
            border-radius: 20px 20px 12px 12px;
            background: white;
            box-shadow: 0 12px 20px rgba(70, 40, 50, 0.15);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 13px;
            font-weight: bold;
            color: #a3426d;
            text-align: center;
            padding: 10px;
        }

        .cosmetic.one {
            height: 180px;
        }

        .cosmetic.two {
            height: 230px;
        }

        .cosmetic.three {
            height: 145px;
        }

        /* =========================
           SECCIONES
        ========================= */

        section {
            padding: 80px 25px;
        }

        .section-container {
            max-width: 1200px;
            margin: auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 45px;
        }

        .section-title h2 {
            font-size: 40px;
            color: #bd4779;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #6d5a63;
        }

        /* =========================
           PRODUCTOS
        ========================= */

        .search-box {
            max-width: 500px;
            margin: 0 auto 35px;
        }

        .search-box input {
            width: 100%;
            padding: 15px 20px;
            border: 2px solid #efcadb;
            border-radius: 30px;
            outline: none;
            font-size: 16px;
            background: white;
        }

        .search-box input:focus {
            border-color: #c94f83;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 25px;
        }

        .product-card {
            background: white;
            border-radius: 22px;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(80, 40, 60, 0.08);
            transition: 0.3s;
            border: 1px solid #f4dce6;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(100, 50, 70, 0.14);
        }

        .product-image {
            height: 210px;
            background: linear-gradient(145deg, #fde9f2, #f7c9dd);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 70px;
        }

        .product-info {
            padding: 20px;
        }

        .product-info h3 {
            color: #4b3840;
            margin-bottom: 8px;
        }

        .product-info p {
            color: #77656d;
            font-size: 14px;
            min-height: 45px;
        }

        .price {
            color: #c14376;
            font-size: 21px;
            font-weight: bold;
            margin: 12px 0;
        }

        .add-cart {
            width: 100%;
            padding: 11px;
            border: none;
            border-radius: 15px;
            background: #c94f83;
            color: white;
            cursor: pointer;
            font-weight: bold;
        }

        .add-cart:hover {
            background: #a93d6a;
        }

        .no-products {
            text-align: center;
            grid-column: 1 / -1;
            padding: 30px;
        }

        /* =========================
           NOSOTROS
        ========================= */

        .about {
            background: #fff;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-box {
            padding: 35px;
            border-radius: 25px;
            background: #fff4f8;
            border: 1px solid #f0d5e1;
        }

        .about-box h3 {
            color: #bd4779;
            font-size: 27px;
            margin-bottom: 15px;
        }

        .about-box p {
            margin-bottom: 15px;
            color: #66535c;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .feature {
            background: white;
            padding: 20px;
            border-radius: 18px;
            box-shadow: 0 5px 18px rgba(70, 40, 50, 0.07);
        }

        .feature strong {
            color: #bd4779;
        }

        /* =========================
           PROYECTOS
        ========================= */

        .projects {
            background: #fff5f9;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .project-card {
            background: white;
            padding: 28px;
            border-radius: 22px;
            border: 1px solid #f0d8e3;
        }

        .project-card h3 {
            color: #bd4779;
            margin-bottom: 10px;
        }

        .project-card p {
            color: #6b5961;
            margin-bottom: 20px;
        }

        .project-link {
            display: inline-block;
            color: #b84072;
            font-weight: bold;
        }

        /* =========================
           CONTACTO
        ========================= */

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .contact-info {
            background: #fff1f6;
            border-radius: 25px;
            padding: 35px;
        }

        .contact-info h3 {
            color: #bd4779;
            font-size: 28px;
            margin-bottom: 20px;
        }

        .contact-item {
            padding: 12px 0;
            border-bottom: 1px solid #efd3df;
        }

        .contact-form {
            background: white;
            padding: 35px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(70, 40, 50, 0.08);
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            margin-bottom: 15px;
            padding: 13px;
            border-radius: 12px;
            border: 1px solid #e6cbd7;
            outline: none;
        }

        .contact-form textarea {
            min-height: 130px;
            resize: vertical;
        }

        /* =========================
           CARRITO
        ========================= */

        .cart-panel {
            position: fixed;
            top: 0;
            right: -400px;
            width: 360px;
            height: 100vh;
            background: white;
            z-index: 2000;
            box-shadow: -10px 0 30px rgba(0,0,0,0.15);
            transition: 0.4s;
            padding: 25px;
            overflow-y: auto;
        }

        .cart-panel.active {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .cart-header h2 {
            color: #bd4779;
        }

        .close-cart {
            border: none;
            background: #f8e4ec;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            cursor: pointer;
            font-size: 18px;
        }

        .cart-item {
            padding: 15px 0;
            border-bottom: 1px solid #efd9e2;
        }

        .cart-item strong {
            display: block;
            color: #4c3941;
        }

        .cart-item button {
            margin-top: 7px;
            border: none;
            background: #f8e4ec;
            color: #a33e68;
            padding: 6px 10px;
            border-radius: 8px;
            cursor: pointer;
        }

        .cart-total {
            margin-top: 25px;
            font-size: 22px;
            font-weight: bold;
            color: #bd4779;
        }

        /* =========================
           FOOTER
        ========================= */

        footer {
            background: #382b31;
            color: white;
            text-align: center;
            padding: 40px 20px;
        }

        footer h2 {
            color: #f2aac7;
            margin-bottom: 10px;
        }

        footer p {
            color: #e8dce1;
        }

        /* =========================
           RESPONSIVE
        ========================= */

        @media (max-width: 950px) {

            nav {
                display: none;
            }

            .hero-container {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-buttons {
                justify-content: center;
            }

            .products-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .about-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 600px) {

            .header-container {
                padding: 12px 15px;
            }

            .logo {
                font-size: 23px;
            }

            .language-btn,
            .cart-btn {
                padding: 7px 9px;
                font-size: 12px;
            }

            section {
                padding: 55px 17px;
            }

            .hero {
                min-height: auto;
            }

            .hero-container {
                padding: 60px 15px;
            }

            .hero-card {
                min-height: 300px;
            }

            .products-grid {
                grid-template-columns: 1fr;
            }

            .features {
                grid-template-columns: 1fr;
            }

            .cart-panel {
                width: 100%;
                right: -100%;
            }
        }

    </style>
</head>

<body>

<!-- =========================
     ENCABEZADO
========================= -->

<header>

    <div class="header-container">

        <a href="#inicio" class="logo">
            MB<span>Store</span>
        </a>

        <nav>

            <a href="#inicio" data-es="Inicio" data-en="Home">
                Inicio
            </a>

            <a href="#productos" data-es="Productos" data-en="Products">
                Productos
            </a>

            <a href="#nosotros" data-es="Nosotros" data-en="About us">
                Nosotros
            </a>

            <a href="#proyectos" data-es="Proyectos" data-en="Projects">
                Proyectos
            </a>

            <a href="#contacto" data-es="Contacto" data-en="Contact">
                Contacto
            </a>

        </nav>

        <div class="header-actions">

            <button class="language-btn" id="languageBtn">
                🇺🇸 EN
            </button>

            <button class="cart-btn" id="cartBtn">
                🛒 <span id="cartCount">0</span>
            </button>

        </div>

    </div>

</header>


<!-- =========================
     INICIO
========================= -->

<section class="hero" id="inicio">

    <div class="hero-container">

        <div class="hero-text">

            <h1>
                MB<span>Store</span>
            </h1>

            <h2
                data-es="Belleza, confianza y estilo"
                data-en="Beauty, confidence and style">
                Belleza, confianza y estilo
            </h2>

            <p
                data-es="Descubre productos cosméticos para cuidar, resaltar y expresar tu belleza."
                data-en="Discover cosmetic products to care for, enhance and express your beauty.">
                Descubre productos cosméticos para cuidar, resaltar y expresar tu belleza.
            </p>

            <div class="hero-buttons">

                <a href="#productos" class="primary-btn"
                   data-es="Ver productos"
                   data-en="View products">
                    Ver productos
                </a>

                <a href="#nosotros" class="secondary-btn"
                   data-es="Conócenos"
                   data-en="About MBStore">
                    Conócenos
                </a>

            </div>

        </div>


        <div class="hero-card">

            <div class="hero-products">

                <div class="cosmetic one">
                    💄<br>
                    Lipstick
                </div>

                <div class="cosmetic two">
                    🧴<br>
                    Body Care
                </div>

                <div class="cosmetic three">
                    ✨<br>
                    Beauty
                </div>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     PRODUCTOS
========================= -->

<section id="productos">

    <div class="section-container">

        <div class="section-title">

            <h2
                data-es="Nuestros productos"
                data-en="Our products">
                Nuestros productos
            </h2>

            <p
                data-es="Encuentra productos para tu rutina de belleza."
                data-en="Find products for your beauty routine.">
                Encuentra productos para tu rutina de belleza.
            </p>

        </div>


        <div class="search-box">

            <input
                type="text"
                id="searchInput"
                placeholder="Buscar producto..."
                data-placeholder-es="Buscar producto..."
                data-placeholder-en="Search product..."
            >

        </div>


        <div class="products-grid" id="productsGrid">

            <!-- PRODUCTO 1 -->

            <article class="product-card"
                     data-name-es="Gloss"
                     data-name-en="Lip Gloss">

                <div class="product-image">
                    💋
                </div>

                <div class="product-info">

                    <h3 data-es="Gloss" data-en="Lip Gloss">
                        Gloss
                    </h3>

                    <p
                        data-es="Brillo labial para un acabado luminoso."
                        data-en="Lip gloss for a beautiful and luminous finish.">
                        Brillo labial para un acabado luminoso.
                    </p>

                    <div class="price">
                        $25.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Gloss"
                        data-product-en="Lip Gloss"
                        data-price="25000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 2 -->

            <article class="product-card"
                     data-name-es="Mantequilla corporal"
                     data-name-en="Body Butter">

                <div class="product-image">
                    ✨
                </div>

                <div class="product-info">

                    <h3
                        data-es="Mantequilla corporal"
                        data-en="Body Butter">
                        Mantequilla corporal
                    </h3>

                    <p
                        data-es="Mantequilla corporal con destellos para una piel luminosa."
                        data-en="Body butter with shimmer for glowing skin.">
                        Mantequilla corporal con destellos para una piel luminosa.
                    </p>

                    <div class="price">
                        $30.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Mantequilla corporal"
                        data-product-en="Body Butter"
                        data-price="30000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 3 -->

            <article class="product-card"
                     data-name-es="Splash corporal"
                     data-name-en="Body Mist">

                <div class="product-image">
                    🌸
                </div>

                <div class="product-info">

                    <h3
                        data-es="Splash corporal"
                        data-en="Body Mist">
                        Splash corporal
                    </h3>

                    <p
                        data-es="Fragancia fresca y agradable para tu rutina diaria."
                        data-en="A fresh and pleasant fragrance for your daily routine.">
                        Fragancia fresca y agradable para tu rutina diaria.
                    </p>

                    <div class="price">
                        $35.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Splash corporal"
                        data-product-en="Body Mist"
                        data-price="35000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 4 -->

            <article class="product-card"
                     data-name-es="Beauty blender"
                     data-name-en="Beauty Blender">

                <div class="product-image">
                    🩷
                </div>

                <div class="product-info">

                    <h3
                        data-es="Beauty blender"
                        data-en="Beauty Blender">
                        Beauty blender
                    </h3>

                    <p
                        data-es="Esponja para aplicar y difuminar maquillaje."
                        data-en="Makeup sponge for applying and blending makeup.">
                        Esponja para aplicar y difuminar maquillaje.
                    </p>

                    <div class="price">
                        $15.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Beauty blender"
                        data-product-en="Beauty Blender"
                        data-price="15000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 5 -->

            <article class="product-card"
                     data-name-es="Tinta de labios"
                     data-name-en="Lip Tint">

                <div class="product-image">
                    💄
                </div>

                <div class="product-info">

                    <h3
                        data-es="Tinta de labios"
                        data-en="Lip Tint">
                        Tinta de labios
                    </h3>

                    <p
                        data-es="Color para labios con un acabado natural."
                        data-en="Lip color with a natural finish.">
                        Color para labios con un acabado natural.
                    </p>

                    <div class="price">
                        $22.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Tinta de labios"
                        data-product-en="Lip Tint"
                        data-price="22000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 6 -->

            <article class="product-card"
                     data-name-es="Laminador de cejas"
                     data-name-en="Brow Gel">

                <div class="product-image">
                    👁️
                </div>

                <div class="product-info">

                    <h3
                        data-es="Laminador de cejas"
                        data-en="Brow Gel">
                        Laminador de cejas
                    </h3>

                    <p
                        data-es="Producto para peinar y fijar las cejas."
                        data-en="Product for styling and setting eyebrows.">
                        Producto para peinar y fijar las cejas.
                    </p>

                    <div class="price">
                        $18.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Laminador de cejas"
                        data-product-en="Brow Gel"
                        data-price="18000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 7 -->

            <article class="product-card"
                     data-name-es="Contorno de ojos"
                     data-name-en="Eye Contour">

                <div class="product-image">
                    🧴
                </div>

                <div class="product-info">

                    <h3
                        data-es="Contorno de ojos"
                        data-en="Eye Contour">
                        Contorno de ojos
                    </h3>

                    <p
                        data-es="Producto para complementar el cuidado del contorno de ojos."
                        data-en="Product to complement your eye contour care routine.">
                        Producto para complementar el cuidado del contorno de ojos.
                    </p>

                    <div class="price">
                        $28.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Contorno de ojos"
                        data-product-en="Eye Contour"
                        data-price="28000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>


            <!-- PRODUCTO 8 -->

            <article class="product-card"
                     data-name-es="Diadema de skincare"
                     data-name-en="Skincare Headband">

                <div class="product-image">
                    🎀
                </div>

                <div class="product-info">

                    <h3
                        data-es="Diadema de skincare"
                        data-en="Skincare Headband">
                        Diadema de skincare
                    </h3>

                    <p
                        data-es="Accesorio práctico para realizar tu rutina facial."
                        data-en="Practical accessory for your skincare routine.">
                        Accesorio práctico para realizar tu rutina facial.
                    </p>

                    <div class="price">
                        $12.000 COP
                    </div>

                    <button
                        class="add-cart"
                        data-product="Diadema de skincare"
                        data-product-en="Skincare Headband"
                        data-price="12000"
                        data-es="Agregar al carrito"
                        data-en="Add to cart">
                        Agregar al carrito
                    </button>

                </div>

            </article>

        </div>

    </div>

</section>


<!-- =========================
     NOSOTROS
========================= -->

<section class="about" id="nosotros">

    <div class="section-container">

        <div class="section-title">

            <h2
                data-es="Sobre MBStore"
                data-en="About MBStore">
                Sobre MBStore
            </h2>

            <p
                data-es="Una propuesta de comercio electrónico enfocada en productos cosméticos."
                data-en="An e-commerce project focused on cosmetic products.">
                Una propuesta de comercio electrónico enfocada en productos cosméticos.
            </p>

        </div>


        <div class="about-grid">

            <div class="about-box">

                <h3
                    data-es="Nuestro proyecto"
                    data-en="Our project">
                    Nuestro proyecto
                </h3>

                <p
                    data-es="MBStore es una plataforma web para la gestión y venta de productos cosméticos en El Espinal, Tolima."
                    data-en="MBStore is a web platform for the management and sale of cosmetic products in El Espinal, Tolima.">
                    MBStore es una plataforma web para la gestión y venta de productos cosméticos en El Espinal, Tolima.
                </p>

                <p
                    data-es="El proyecto busca presentar los productos de una manera organizada, sencilla y atractiva para los clientes."
                    data-en="The project aims to present products in an organized, simple and attractive way for customers.">
                    El proyecto busca presentar los productos de una manera organizada, sencilla y atractiva para los clientes.
                </p>

            </div>


            <div class="features">

                <div class="feature">
                    🛍️
                    <br>
                    <strong
                        data-es="Catálogo"
                        data-en="Catalog">
                        Catálogo
                    </strong>

                    <p
                        data-es="Productos organizados."
                        data-en="Organized products.">
                        Productos organizados.
                    </p>
                </div>


                <div class="feature">
                    🌐
                    <br>
                    <strong
                        data-es="Multidioma"
                        data-en="Multilingual">
                        Multidioma
                    </strong>

                    <p
                        data-es="Español e inglés."
                        data-en="Spanish and English.">
                        Español e inglés.
                    </p>
                </div>


                <div class="feature">
                    📱
                    <br>
                    <strong
                        data-es="Responsive"
                        data-en="Responsive">
                        Responsive
                    </strong>

                    <p
                        data-es="Adaptado a celulares."
                        data-en="Adapted to mobile devices.">
                        Adaptado a celulares.
                    </p>
                </div>


                <div class="feature">
                    🔎
                    <br>
                    <strong
                        data-es="Búsqueda"
                        data-en="Search">
                        Búsqueda
                    </strong>

                    <p
                        data-es="Busca productos rápidamente."
                        data-en="Find products quickly.">
                        Busca productos rápidamente.
                    </p>
                </div>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     PROYECTOS
========================= -->

<section class="projects" id="proyectos">

    <div class="section-container">

        <div class="section-title">

            <h2
                data-es="Mis proyectos"
                data-en="My projects">
                Mis proyectos
            </h2>

            <p
                data-es="Proyectos relacionados con mi formación en Ingeniería de Sistemas."
                data-en="Projects related to my Systems Engineering studies.">
                Proyectos relacionados con mi formación en Ingeniería de Sistemas.
            </p>

        </div>


        <div class="projects-grid">

            <article class="project-card">

                <h3>🛍️ MBStore</h3>

                <p
                    data-es="Plataforma web para la gestión y venta de productos cosméticos."
                    data-en="Web platform for the management and sale of cosmetic products.">
                    Plataforma web para la gestión y venta de productos cosméticos.
                </p>

                <a href="#inicio" class="project-link">
                    MBStore →
                </a>

            </article>


            <article class="project-card">

                <h3>💻 HTML & CSS</h3>

                <p
                    data-es="Ejercicios y prácticas de desarrollo web."
                    data-en="Web development exercises and practices.">
                    Ejercicios y prácticas de desarrollo web.
                </p>

                <a href="#" class="project-link"
                   onclick="alert(currentLanguage === 'es' ? 'Enlace pendiente de agregar.' : 'Link pending to be added.'); return false;">
                    <span
                        data-es="Ver proyecto →"
                        data-en="View project →">
                        Ver proyecto →
                    </span>
                </a>

            </article>


            <article class="project-card">

                <h3>⚙️ JavaScript</h3>

                <p
                    data-es="Ejercicios y proyectos realizados con JavaScript."
                    data-en="Exercises and projects created with JavaScript.">
                    Ejercicios y proyectos realizados con JavaScript.
                </p>

                <a href="#" class="project-link"
                   onclick="alert(currentLanguage === 'es' ? 'Enlace pendiente de agregar.' : 'Link pending to be added.'); return false;">
                    <span
                        data-es="Ver proyecto →"
                        data-en="View project →">
                        Ver proyecto →
                    </span>
                </a>

            </article>

        </div>

    </div>

</section>


<!-- =========================
     CONTACTO
========================= -->

<section id="contacto">

    <div class="section-container">

        <div class="section-title">

            <h2
                data-es="Contacto"
                data-en="Contact">
                Contacto
            </h2>

            <p
                data-es="¿Tienes alguna pregunta? Escríbenos."
                data-en="Do you have any questions? Contact us.">
                ¿Tienes alguna pregunta? Escríbenos.
            </p>

        </div>


        <div class="contact-grid">

            <div class="contact-info">

                <h3>MBStore 💗</h3>

                <div class="contact-item">
                    📍
                    <strong
                        data-es="Ubicación:"
                        data-en="Location:">
                        Ubicación:
                    </strong>

                    El Espinal, Tolima, Colombia
                </div>

                <div class="contact-item">
                    📱
                    <strong
                        data-es="Teléfono:"
                        data-en="Phone:">
                        Teléfono:
                    </strong>

                    320 924 7284
                </div>

                <div class="contact-item">
                    💻
                    <strong
                        data-es="Proyecto:"
                        data-en="Project:">
                        Proyecto:
                    </strong>

                    MBStore
                </div>

            </div>


            <form class="contact-form" id="contactForm">

                <input
                    type="text"
                    id="name"
                    required
                    placeholder="Nombre"
                    data-placeholder-es="Nombre"
                    data-placeholder-en="Name"
                >

                <input
                    type="email"
                    id="email"
                    required
                    placeholder="Correo electrónico"
                    data-placeholder-es="Correo electrónico"
                    data-placeholder-en="Email"
                >

                <textarea
                    id="message"
                    required
                    placeholder="Escribe tu mensaje..."
                    data-placeholder-es="Escribe tu mensaje..."
                    data-placeholder-en="Write your message..."
                ></textarea>

                <button
                    type="submit"
                    class="primary-btn"
                    data-es="Enviar mensaje"
                    data-en="Send message">
                    Enviar mensaje
                </button>

            </form>

        </div>

    </div>

</section>


<!-- =========================
     CARRITO
========================= -->

<div class="cart-panel" id="cartPanel">

    <div class="cart-header">

        <h2
            data-es="Mi carrito"
            data-en="My cart">
            Mi carrito
        </h2>

        <button class="close-cart" id="closeCart">
            ✕
        </button>

    </div>

    <div id="cartItems"></div>

    <div class="cart-total" id="cartTotal">
        Total: $0 COP
    </div>

</div>


<!-- =========================
     FOOTER
========================= -->

<footer>

    <h2>MBStore 💗</h2>

    <p
        data-es="Plataforma web para la gestión y venta de productos cosméticos."
        data-en="Web platform for the management and sale of cosmetic products.">
        Plataforma web para la gestión y venta de productos cosméticos.
    </p>

    <p>
        © <span id="year"></span> MBStore
    </p>

</footer>


<!-- =========================
     JAVASCRIPT
========================= -->

<script>

    /* =========================
       IDIOMA
    ========================= */

    let currentLanguage = "es";

    const languageBtn = document.getElementById("languageBtn");

    function changeLanguage() {

        currentLanguage = currentLanguage === "es" ? "en" : "es";

        document.documentElement.lang = currentLanguage;

        document.querySelectorAll("[data-es][data-en]").forEach(element => {

            element.textContent =
                currentLanguage === "es"
                ? element.dataset.es
                : element.dataset.en;

        });

        document.querySelectorAll("[data-placeholder-es][data-placeholder-en]")
            .forEach(element => {

                element.placeholder =
                    currentLanguage === "es"
                    ? element.dataset.placeholderEs
                    : element.dataset.placeholderEn;

            });

        languageBtn.textContent =
            currentLanguage === "es"
            ? "🇺🇸 EN"
            : "🇨🇴 ES";

        renderCart();

    }

    languageBtn.addEventListener("click", changeLanguage);


    /* =========================
       BUSCADOR
    ========================= */

    const searchInput = document.getElementById("searchInput");

    searchInput.addEventListener("input", function() {

        const search = this.value.toLowerCase().trim();

        const products =
            document.querySelectorAll(".product-card");

        let visibleProducts = 0;

        products.forEach(product => {

            const name =
                currentLanguage === "es"
                ? product.dataset.nameEs
                : product.dataset.nameEn;

            if (name.toLowerCase().includes(search)) {

                product.style.display = "";

                visibleProducts++;

            } else {

                product.style.display = "none";

            }

        });

        let message =
            document.getElementById("noProducts");

        if (visibleProducts === 0) {

            if (!message) {

                message = document.createElement("div");

                message.id = "noProducts";

                message.className = "no-products";

                document
                    .getElementById("productsGrid")
                    .appendChild(message);

            }

            message.textContent =
                currentLanguage === "es"
                ? "No se encontraron productos."
                : "No products were found.";

        } else {

            if (message) {
                message.remove();
            }

        }

    });


    /* =========================
       CARRITO
    ========================= */

    let cart = [];

    const cartBtn =
        document.getElementById("cartBtn");

    const cartPanel =
        document.getElementById("cartPanel");

    const closeCart =
        document.getElementById("closeCart");

    const cartItems =
        document.getElementById("cartItems");

    const cartTotal =
        document.getElementById("cartTotal");

    const cartCount =
        document.getElementById("cartCount");


    document.querySelectorAll(".add-cart")
        .forEach(button => {

            button.addEventListener("click", function() {

                const product = {

                    nameEs: this.dataset.product,

                    nameEn: this.dataset.productEn,

                    price: Number(this.dataset.price)

                };

                cart.push(product);

                renderCart();

                cartPanel.classList.add("active");

            });

        });


    function renderCart() {

        cartItems.innerHTML = "";

        if (cart.length === 0) {

            cartItems.innerHTML =
                currentLanguage === "es"
                ? "<p>Tu carrito está vacío.</p>"
                : "<p>Your cart is empty.</p>";

            cartTotal.textContent =
                currentLanguage === "es"
                ? "Total: $0 COP"
                : "Total: $0 COP";

            cartCount.textContent = "0";

            return;

        }


        let total = 0;


        cart.forEach((item, index) => {

            total += item.price;

            const div =
                document.createElement("div");

            div.className = "cart-item";

            const name =
                currentLanguage === "es"
                ? item.nameEs
                : item.nameEn;

            div.innerHTML = `

                <strong>${name}</strong>

                <span>
                    $${item.price.toLocaleString("es-CO")} COP
                </span>

                <br>

                <button onclick="removeFromCart(${index})">

                    ${
                        currentLanguage === "es"
                        ? "Eliminar"
                        : "Remove"
                    }

                </button>

            `;

            cartItems.appendChild(div);

        });


        cartTotal.textContent =
            `${
                currentLanguage === "es"
                ? "Total"
                : "Total"
            }: $${total.toLocaleString("es-CO")} COP`;

        cartCount.textContent = cart.length;

    }


    function removeFromCart(index) {

        cart.splice(index, 1);

        renderCart();

    }


    cartBtn.addEventListener("click", function() {

        cartPanel.classList.add("active");

    });


    closeCart.addEventListener("click", function() {

        cartPanel.classList.remove("active");

    });


    /* =========================
       FORMULARIO
    ========================= */

    document
        .getElementById("contactForm")
        .addEventListener("submit", function(event) {

            event.preventDefault();

            if (currentLanguage === "es") {

                alert(
                    "¡Gracias por escribirnos! 💗 Tu mensaje ha sido preparado correctamente."
                );

            } else {

                alert(
                    "Thank you for contacting us! 💗 Your message has been prepared successfully."
                );

            }

            this.reset();

        });


    /* =========================
       AÑO AUTOMÁTICO
    ========================= */

    document.getElementById("year").textContent =
        new Date().getFullYear();


    /* =========================
       INICIAR CARRITO
    ========================= */

    renderCart();

</script>

</body>
</html>
