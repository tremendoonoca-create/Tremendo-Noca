<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TREMENDO ÑOCA | Inicio</title>
  <style>
    /* VARIABLES Y ESTILOS GLOBALES */
    :root {
      --bg-dark: #0a192f;        /* Azul marino oscuro */
      --primary-blue: #1e3a8a;   /* Azul marino principal */
      --accent-blue: #2563eb;    /* Azul brillante para hover/detalles */
      --white: #ffffff;
      --light-gray: #f1f5f9;
      --text-dark: #0f172a;
      --border-black: #000000;
      --shadow-black: 0 4px 12px rgba(0, 0, 0, 0.4);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: var(--light-gray);
      color: var(--text-dark);
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    /* ENCABEZADO / HEADER */
    header {
      background-color: var(--bg-dark);
      color: var(--white);
      padding: 1rem 1.5rem;
      border-bottom: 3px solid var(--border-black);
      box-shadow: var(--shadow-black);
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    .header-container {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

    /* BRAND / LOGO */
    .brand-logo {
      font-size: 1.8rem;
      font-weight: 900;
      color: var(--white);
      text-decoration: none;
      letter-spacing: 1.5px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
      width: fit-content;
      transition: transform 0.2s;
    }

    .brand-logo:hover {
      transform: scale(1.02);
      color: #93c5fd;
    }

    /* BOTÓN DE MENÚ DESPLEGABLE (3 LÍNEAS / HAMBURGUESA) */
    .menu-toggle {
      background: transparent;
      border: 2px solid var(--white);
      color: var(--white);
      font-size: 1.4rem;
      padding: 0.3rem 0.8rem;
      border-radius: 6px;
      cursor: pointer;
      width: fit-content;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      transition: background-color 0.2s;
    }

    .menu-toggle:hover {
      background-color: var(--primary-blue);
    }

    /* NAVEGACIÓN DESPLEGABLE */
    nav.nav-menu {
      display: none; /* Oculto por defecto */
      background-color: var(--primary-blue);
      border: 2px solid var(--border-black);
      border-radius: 8px;
      margin-top: 0.5rem;
      overflow: hidden;
      box-shadow: var(--shadow-black);
    }

    nav.nav-menu.active {
      display: block; /* Se muestra al hacer clic */
    }

    nav.nav-menu ul {
      list-style: none;
    }

    nav.nav-menu ul li a {
      display: block;
      padding: 0.8rem 1.2rem;
      color: var(--white);
      text-decoration: none;
      font-weight: 600;
      border-bottom: 1px solid rgba(0, 0, 0, 0.2);
      transition: background 0.2s, padding-left 0.2s;
    }

    nav.nav-menu ul li:last-child a {
      border-bottom: none;
    }

    nav.nav-menu ul li a:hover {
      background-color: var(--accent-blue);
      padding-left: 1.6rem;
    }

    /* CONTENIDOS PRINCIPALES */
    main {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 1rem;
      flex: 1;
    }

    .section-title {
      font-size: 1.6rem;
      font-weight: 800;
      color: var(--bg-dark);
      border-left: 6px solid var(--primary-blue);
      padding-left: 0.8rem;
      margin-bottom: 1.5rem;
      text-transform: uppercase;
    }

    /* GRILLA DE NOTICIAS */
    .news-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.8rem;
    }

    /* TARJETA DE NOTICIA (CUADRO) */
    .news-card {
      background-color: var(--white);
      border: 2px solid var(--border-black);
      border-radius: 10px;
      overflow: hidden;
      box-shadow: var(--shadow-black);
      display: flex;
      flex-direction: column;
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .news-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.5);
    }

    .news-tag {
      position: absolute;
      top: 10px;
      left: 10px;
      background-color: var(--primary-blue);
      color: var(--white);
      font-size: 0.75rem;
      font-weight: 700;
      padding: 0.3rem 0.6rem;
      border-radius: 4px;
      border: 1px solid var(--border-black);
      text-transform: uppercase;
    }

    .news-img-wrapper {
      position: relative;
      width: 100%;
      height: 180px;
      background-color: #cbd5e1;
    }

    .news-img-wrapper img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .news-content {
      padding: 1.2rem;
      display: flex;
      flex-direction: column;
      flex: 1;
    }

    .news-title {
      font-size: 1.15rem;
      font-weight: 700;
      color: var(--text-dark);
      margin-bottom: 0.8rem;
      line-height: 1.3;
    }

    .news-snippet {
      font-size: 0.9rem;
      color: #475569;
      margin-bottom: 1.2rem;
      flex: 1;
    }

    .news-btn {
      display: inline-block;
      text-align: center;
      background-color: var(--bg-dark);
      color: var(--white);
      text-decoration: none;
      padding: 0.6rem 1rem;
      font-weight: 700;
      border-radius: 6px;
      border: 1px solid var(--border-black);
      transition: background-color 0.2s;
    }

    .news-btn:hover {
      background-color: var(--accent-blue);
    }

    /* SECCIÓN LOGOS DE FUENTES */
    .sources-section {
      margin-top: 3.5rem;
      background-color: var(--white);
      border: 2px solid var(--border-black);
      border-radius: 10px;
      padding: 1.5rem;
      box-shadow: var(--shadow-black);
      text-align: center;
    }

    .sources-section h3 {
      font-size: 1.1rem;
      color: var(--bg-dark);
      margin-bottom: 1.2rem;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .sources-logos {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 2rem;
      flex-wrap: wrap;
    }

    .source-logo {
      max-height: 45px;
      max-width: 120px;
      filter: grayscale(30%);
      transition: filter 0.2s, transform 0.2s;
    }

    .source-logo:hover {
      filter: grayscale(0%);
      transform: scale(1.08);
    }

    /* PIE DE PÁGINA / FOOTER CON AVISO LEGAL */
    footer {
      background-color: var(--bg-dark);
      color: var(--white);
      border-top: 3px solid var(--border-black);
      padding: 2rem 1rem;
      margin-top: 3rem;
      font-size: 0.85rem;
      text-align: center;
    }

    .footer-container {
      max-width: 1000px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      line-height: 1.5;
    }

    .footer-disclaimer {
      color: #94a3b8;
      border-top: 1px solid rgba(255, 255, 255, 0.2);
      padding-top: 1rem;
      font-size: 0.8rem;
    }
  </style>
</head>
<body>

  <!-- ENCABEZADO -->
  <header>
    <div class="header-container">
      <!-- Nombre / Logo que lleva al inicio -->
      <a href="index.html" class="brand-logo">TREMENDO ÑOCA</a>

      <!-- Botón de Menú Desplegable -->
      <button class="menu-toggle" id="menuBtn" aria-label="Abrir Menú">
        ☰ <span>Menú</span>
      </button>

      <!-- Opciones del Menú -->
      <nav class="nav-menu" id="navMenu">
        <ul>
          <li><a href="informacion.html">Información</a></li>
          <li><a href="videos.html">Videos</a></li>
          <li><a href="links-streams.html">Links de Streams</a></li>
          <li><a href="juegos.html">Juegos</a></li>
          <li><a href="noticias.html">Noticias</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- CONTENIDO PRINCIPAL -->
  <main>
    <h2 class="section-title">Noticias del Momento</h2>

    <!-- GRILLA DE NOTICIAS -->
    <div class="news-grid">

      <!-- NOTICIA 1 (Ejemplo Propia) -->
      <article class="news-card">
        <div class="news-img-wrapper">
          <span class="news-tag">Nota Propia</span>
          <!-- Reemplazar src por la ruta de tu foto -->
          <img src="https://via.placeholder.com/400x250/1e3a8a/ffffff?text=Nota+Propia" alt="Imagen noticia propia">
        </div>
        <div class="news-content">
          <h3 class="news-title">Análisis táctico: Las claves del triunfo en el clásico</h3>
          <p class="news-snippet">Repasamos los puntos más altos del equipo y la estrategia que definió el partido.</p>
          <a href="#" class="news-btn">Acceder a la nota</a>
        </div>
      </article>

      <!-- NOTICIA 2 (Ejemplo Fuente Externa TyC) -->
      <article class="news-card">
        <div class="news-img-wrapper">
          <span class="news-tag" style="background-color: #0f172a;">TyC Sports</span>
          <!-- Reemplazar src por la ruta de tu foto -->
          <img src="https://via.placeholder.com/400x250/0f172a/ffffff?text=TyC+Sports" alt="Imagen noticia externa">
        </div>
        <div class="news-content">
          <h3 class="news-title">Último momento: Novedades sobre el mercado de pases</h3>
          <p class="news-snippet">Toda la información confirmada sobre los refuerzos para el próximo torneo.</p>
          <a href="https://www.tycsports.com" target="_blank" rel="noopener noreferrer" class="news-btn">Leer en TyC Sports</a>
        </div>
      </article>

      <!-- NOTICIA 3 (Ejemplo Fuente Externa ESPN) -->
      <article class="news-card">
        <div class="news-img-wrapper">
          <span class="news-tag" style="background-color: #b91c1c;">ESPN</span>
          <!-- Reemplazar src por la ruta de tu foto -->
          <img src="https://via.placeholder.com/400x250/b91c1c/ffffff?text=ESPN" alt="Imagen noticia ESPN">
        </div>
        <div class="news-content">
          <h3 class="news-title">Conferencia de prensa: Las declaraciones del DT</h3>
          <p class="news-snippet">Las frases más destacadas del entrenador antes de la fecha definitoria.</p>
          <a href="https://www.espn.com.ar" target="_blank" rel="noopener noreferrer" class="news-btn">Leer en ESPN</a>
        </div>
      </article>

    </div>

    <!-- SECCIÓN LOGOS DE FUENTES EXTERNAS -->
    <section class="sources-section">
      <h3>Fuentes de información destacadas</h3>
      <div class="sources-logos">
        <!-- Reemplazar src por las imágenes de los logos reales -->
        <img src="https://via.placeholder.com/120x40/0a192f/ffffff?text=TyC+Sports" alt="TyC Sports Logo" class="source-logo">
        <img src="https://via.placeholder.com/120x40/cc0000/ffffff?text=ESPN" alt="ESPN Logo" class="source-logo">
        <img src="https://via.placeholder.com/120x40/000000/ffffff?text=Diario+Ole" alt="Olé Logo" class="source-logo">
      </div>
    </section>
  </main>

  <!-- PIE DE PÁGINA Y AVISO LEGAL -->
  <footer>
    <div class="footer-container">
      <p>© 2026 <strong>TREMENDO ÑOCA</strong> - Todos los derechos reservados.</p>
      
      <!-- Descargo de responsabilidad -->
      <p class="footer-disclaimer">
        <strong>Aviso Legal y Descargo de Responsabilidad:</strong> TREMENDO ÑOCA es un portal independiente de difusión. No somos propietarios del contenido, imágenes o marcas registradas pertenecientes a medios de comunicación de terceros (como TyC Sports, ESPN, entre otros). Toda la información citada se recopila y distribuye con fines puramente informativos y de divulgación, reconociendo y otorgando el debido crédito y atribución a sus fuentes originales.
      </p>
    </div>
  </footer>

  <!-- SCRIPT INTERACTIVO DEL MENÚ -->
  <script>
    const menuBtn = document.getElementById('menuBtn');
    const navMenu = document.getElementById('navMenu');

    // Alternar apertura/cierre del menú al hacer clic en las 3 líneas
    menuBtn.addEventListener('click', () => {
      navMenu.classList.toggle('active');
    });
  </script>
</body>
</html>
