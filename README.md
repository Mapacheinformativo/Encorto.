<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>EnCorto – Lo que pasa, EnCorto.</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;900&family=Source+Serif+4:ital,wght@0,300;0,400;1,300&display=swap" rel="stylesheet">
  <style>
    :root {
      --azul:    #1a2472;
      --rojo:    #d93025;
      --blanco:  #ffffff;
      --gris-bg: #f2f4f8;
      --gris-borde: #d0d4e0;
      --gris-texto: #444;
      --fuente-titulo: 'Montserrat', sans-serif;
      --fuente-cuerpo: 'Source Serif 4', Georgia, serif;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: var(--fuente-cuerpo); background: var(--gris-bg); color: #111; font-size: 16px; line-height: 1.7; }
    a { color: inherit; text-decoration: none; }
    a:hover { text-decoration: underline; }
    img { width: 100%; height: 200px; object-fit: cover; display: block; border-radius: 4px; margin-bottom: 0.75rem; }
    .contenedor { max-width: 1100px; margin: 0 auto; padding: 0 1.5rem; }

    /* HEADER */
    header { background: var(--azul); color: var(--blanco); padding: 0; }
    .header-top { display: flex; justify-content: space-between; align-items: center; padding: 0.5rem 1.5rem; font-size: 11px; opacity: 0.75; border-bottom: 1px solid rgba(255,255,255,0.15); }
    .header-brand { text-align: center; padding: 1.25rem 1.5rem 0; }
    .nombre-periodico { font-family: var(--fuente-titulo); font-size: 3.8rem; font-weight: 900; letter-spacing: -2px; line-height: 1; color: var(--rojo); }
    .nombre-periodico span { color: var(--blanco); }
    .eslogan { font-size: 12px; letter-spacing: 2px; color: rgba(255,255,255,0.6); margin-top: 4px; font-style: italic; }
    nav { display: flex; gap: 0; justify-content: center; border-top: 3px solid var(--rojo); margin-top: 1rem; background: var(--azul); }
    nav a { color: rgba(255,255,255,0.85); font-family: var(--fuente-titulo); font-size: 12px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; padding: 0.65rem 1.4rem; transition: background 0.2s, color 0.2s; }
    nav a:hover { background: var(--rojo); color: var(--blanco); text-decoration: none; }
    nav a.activo { background: var(--rojo); color: var(--blanco); }

    /* BREAKING NEWS BAR */
    .breaking { background: var(--rojo); color: var(--blanco); display: flex; align-items: center; gap: 0; font-size: 13px; overflow: hidden; }
    .breaking-label { background: #a01a10; padding: 0.45rem 1rem; font-family: var(--fuente-titulo); font-weight: 900; font-size: 11px; letter-spacing: 1px; text-transform: uppercase; white-space: nowrap; }
    .breaking-text { padding: 0.45rem 1rem; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

    /* CUERPO */
    .cuerpo { display: grid; grid-template-columns: 2fr 1fr; gap: 2rem; padding: 2rem 0; }

    /* ETIQUETA SECCIÓN */
    .etiqueta { font-family: var(--fuente-titulo); font-size: 10px; font-weight: 900; text-transform: uppercase; letter-spacing: 2.5px; color: var(--blanco); background: var(--azul); padding: 4px 10px; display: inline-block; margin-bottom: 1rem; border-radius: 2px; }
    .etiqueta.roja { background: var(--rojo); }

    /* NOTICIA PRINCIPAL */
    .titular-grande { font-family: var(--fuente-titulo); font-size: 2.3rem; font-weight: 900; line-height: 1.15; margin-bottom: 0.6rem; color: var(--azul); }
    .subtitular { font-size: 1.05rem; color: var(--gris-texto); font-style: italic; margin-bottom: 0.75rem; line-height: 1.5; }
    .firma { font-size: 11px; text-transform: uppercase; letter-spacing: 1px; color: var(--gris-texto); border-bottom: 2px solid var(--rojo); padding-bottom: 0.5rem; margin-bottom: 1rem; }
    .texto-noticia p { margin-bottom: 1rem; font-size: 15px; line-height: 1.85; }
    .texto-noticia blockquote { border-left: 4px solid var(--rojo); padding-left: 1rem; margin: 1.5rem 0; font-style: italic; font-size: 1.1rem; color: var(--azul); }

    /* DIVISOR */
    hr { border: none; border-top: 1px solid var(--gris-borde); margin: 1.5rem 0; }
    .hr-rojo { border: none; border-top: 3px solid var(--rojo); margin: 1.5rem 0; }

    /* CUADRÍCULA */
    .cuadricula { display: grid; grid-template-columns: 1fr 1fr; gap: 1.25rem; margin-top: 1rem; }
    .tarjeta { background: var(--blanco); border-radius: 4px; padding: 0.85rem; border: 1px solid var(--gris-borde); }
    .tarjeta h3 { font-family: var(--fuente-titulo); font-size: 0.95rem; font-weight: 700; line-height: 1.3; margin-bottom: 4px; color: var(--azul); }
    .tarjeta p { font-size: 13px; color: var(--gris-texto); line-height: 1.5; }
    .tarjeta img { height: 110px; margin-bottom: 0.6rem; }

    /* LATERAL */
    .lateral { }
    .lateral .tarjeta { margin-bottom: 1rem; }
    .lateral .tarjeta h3 { font-size: 0.9rem; }
    .lateral .tarjeta img { height: 90px; }

    /* SECCIONES ESPECIALES LATERAL */
    .agenda { background: var(--azul); color: var(--blanco); border-radius: 4px; padding: 1rem; margin-bottom: 1rem; }
    .agenda h4 { font-family: var(--fuente-titulo); font-size: 11px; font-weight: 900; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 0.75rem; color: rgba(255,255,255,0.6); }
    .agenda-item { display: flex; gap: 10px; margin-bottom: 0.6rem; font-size: 13px; align-items: flex-start; }
    .agenda-dia { font-family: var(--fuente-titulo); font-weight: 900; font-size: 11px; color: var(--rojo); text-transform: uppercase; min-width: 30px; padding-top: 2px; }

    /* REDES SOCIALES */
    .redes { background: var(--rojo); border-radius: 4px; padding: 1rem; margin-bottom: 1rem; }
    .redes h4 { font-family: var(--fuente-titulo); font-size: 11px; font-weight: 900; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 0.75rem; color: rgba(255,255,255,0.75); }
    .redes-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; }
    .red-btn { background: rgba(255,255,255,0.15); color: var(--blanco); border-radius: 3px; padding: 6px 8px; font-size: 12px; font-family: var(--fuente-titulo); font-weight: 700; text-align: center; cursor: pointer; transition: background 0.2s; }
    .red-btn:hover { background: rgba(255,255,255,0.3); }

    /* FOOTER */
    footer { background: var(--azul); color: rgba(255,255,255,0.7); padding: 1.5rem; text-align: center; font-size: 12px; margin-top: 1rem; }
    footer strong { color: var(--blanco); font-family: var(--fuente-titulo); }
    footer a { color: rgba(255,255,255,0.6); }
    footer a:hover { color: var(--blanco); }

    /* PLACEHOLDER FOTO */
    .foto-placeholder { background: #dde2ef; border: 1px dashed var(--gris-borde); width: 100%; height: 200px; display: flex; flex-direction: column; align-items: center; justify-content: center; color: #7a8ab0; font-size: 13px; margin-bottom: 1rem; border-radius: 4px; gap: 6px; }
    .foto-placeholder svg { opacity: 0.4; }
    .foto-sm { height: 110px; }
    .foto-xs { height: 90px; }

    /* RESPONSIVE */
    @media (max-width: 720px) {
      .nombre-periodico { font-size: 2.5rem; }
      .cuerpo { grid-template-columns: 1fr; }
      .cuadricula { grid-template-columns: 1fr; }
      nav { flex-wrap: wrap; }
      nav a { font-size: 11px; padding: 0.5rem 0.8rem; }
      .header-top { flex-direction: column; gap: 2px; text-align: center; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <div class="header-top">
      <span id="fecha">Lunes, 25 de mayo de 2026</span>
      <span>Periodismo digital local · Edición web</span>
      <span>Chimbote, Áncash</span>
    </div>
    <div class="header-brand">
      <!-- INSTRUCCIÓN: Puedes cambiar el eslogan si quieres -->
      <div class="nombre-periodico">En<span>Corto</span></div>
      <div class="eslogan">"Lo que pasa, EnCorto."</div>
    </div>
    <nav>
      <a href="#" class="activo">Portada</a>
      <a href="#">Política</a>
      <a href="#">Comunidad</a>
      <a href="#">Seguridad</a>
      <a href="#">Economía</a>
      <a href="#">Denuncias</a>
      <a href="#">Opinión</a>
    </nav>
  </header>

  <!-- BARRA BREAKING NEWS -->
  <div class="breaking">
    <span class="breaking-label">&#9654; Ahora</span>
    <!-- INSTRUCCIÓN: Cambia este texto por tu titular urgente del día -->
    <span class="breaking-text">Aquí va un titular urgente o noticia de último momento · Puedes editar este texto</span>
  </div>

  <div class="contenedor">
    <div class="cuerpo">

      <!-- COLUMNA PRINCIPAL -->
      <main>
        <span class="etiqueta roja">Noticia principal</span>

        <!-- INSTRUCCIÓN: Cambia este titular -->
        <h1 class="titular-grande">Aquí va el título de tu noticia más importante del día en la comunidad</h1>

        <!-- INSTRUCCIÓN: Cambia el subtítulo -->
        <p class="subtitular">Un subtítulo que amplía el titular con más contexto. Debe complementar, no repetir, lo que dice el título.</p>

        <!-- INSTRUCCIÓN: Cambia autor y fecha -->
        <div class="firma">Por Andrea Tinco Céspedes · 25 de mayo de 2026</div>

        <!-- INSTRUCCIÓN: Para agregar una foto, reemplaza este bloque por: <img src="fotos/mi-foto.jpg" alt="Descripción"> -->
        <div class="foto-placeholder">
          <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
          Aquí va tu foto principal
        </div>

        <!-- INSTRUCCIÓN: Escribe aquí el cuerpo de tu noticia -->
        <div class="texto-noticia">
          <p>Este es el primer párrafo de tu noticia. Aquí responde: ¿qué pasó?, ¿quién lo hizo?, ¿cuándo?, ¿dónde? y ¿por qué? Es el párrafo más importante: muchos lectores solo leen el inicio.</p>
          <p>En este segundo párrafo amplías los detalles, agregas contexto y puedes incluir declaraciones de fuentes. Continúa con información relevante para los vecinos de la comunidad.</p>
          <blockquote>"Aquí coloca una cita textual importante de alguna fuente o persona involucrada en la noticia." – Nombre de la fuente</blockquote>
          <p>Sigue desarrollando la historia con más detalles, antecedentes y citas de las personas involucradas. Cierra con información sobre los próximos pasos o las consecuencias del hecho.</p>
        </div>

        <div class="hr-rojo"></div>

        <span class="etiqueta">Más noticias</span>
        <div class="cuadricula">

          <div class="tarjeta">
            <div class="foto-placeholder foto-sm">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
            </div>
            <h3>Título de la segunda noticia importante del día</h3>
            <p>Breve descripción para que el lector decida si quiere leerla completa.</p>
          </div>

          <div class="tarjeta">
            <div class="foto-placeholder foto-sm">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
            </div>
            <h3>Título de la tercera noticia del día en la región</h3>
            <p>Breve descripción para que el lector decida si quiere leerla completa.</p>
          </div>

          <div class="tarjeta">
            <div class="foto-placeholder foto-sm">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
            </div>
            <h3>Cuarta noticia relevante de la comunidad local</h3>
            <p>Breve descripción para que el lector decida si quiere leerla completa.</p>
          </div>

          <div class="tarjeta">
            <div class="foto-placeholder foto-sm">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
            </div>
            <h3>Quinta noticia de interés para los vecinos</h3>
            <p>Breve descripción para que el lector decida si quiere leerla completa.</p>
          </div>

        </div>
      </main>

      <!-- BARRA LATERAL -->
      <aside class="lateral">

        <span class="etiqueta">Últimas noticias</span>

        <div class="tarjeta">
          <div class="foto-placeholder foto-xs">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#7a8ab0" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="m21 15-5-5L5 21"/></svg>
          </div>
          <h3>Noticia breve número uno de la región</h3>
          <p>Resumen corto de lo que ocurrió. Dos o tres líneas máximo.</p>
        </div>

        <div class="tarjeta">
          <h3>Noticia breve número dos sin imagen</h3>
          <p>Resumen corto de lo que ocurrió. Dos o tres líneas máximo.</p>
        </div>

        <div class="tarjeta">
          <h3>Noticia breve número tres de la comunidad</h3>
          <p>Resumen corto de lo que ocurrió. Dos o tres líneas máximo.</p>
        </div>

        <div class="tarjeta">
          <h3>Noticia breve número cuatro local</h3>
          <p>Resumen corto de lo que ocurrió. Dos o tres líneas máximo.</p>
        </div>

        <!-- AGENDA EDITORIAL -->
        <div class="agenda">
          <h4>📅 Agenda editorial</h4>
          <div class="agenda-item"><span class="agenda-dia">Lun</span><span>Noticias vecinales</span></div>
          <div class="agenda-item"><span class="agenda-dia">Mar</span><span>Política local</span></div>
          <div class="agenda-item"><span class="agenda-dia">Mié</span><span>Seguridad ciudadana</span></div>
          <div class="agenda-item"><span class="agenda-dia">Jue</span><span>Entrevistas y denuncias</span></div>
          <div class="agenda-item"><span class="agenda-dia">Vie</span><span>Reportaje audiovisual</span></div>
          <div class="agenda-item"><span class="agenda-dia">Sáb</span><span>Resumen semanal</span></div>
          <div class="agenda-item"><span class="agenda-dia">Dom</span><span>Debate o transmisión en vivo</span></div>
        </div>

        <!-- REDES SOCIALES -->
        <div class="redes">
          <h4>📲 Síguenos</h4>
          <div class="redes-grid">
            <!-- INSTRUCCIÓN: Cambia los href="#" por tus links reales -->
            <a href="#" class="red-btn">Facebook</a>
            <a href="#" class="red-btn">Instagram</a>
            <a href="#" class="red-btn">TikTok</a>
            <a href="#" class="red-btn">YouTube</a>
            <a href="#" class="red-btn" style="grid-column: span 2;">WhatsApp</a>
          </div>
        </div>

      </aside>

    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <strong>EnCorto</strong> · "Lo que pasa, EnCorto." · Periodismo digital local<br>
    <!-- INSTRUCCIÓN: Cambia el correo por el real -->
    Contacto: <a href="mailto:redaccion@encorto.pe">redaccion@encorto.pe</a><br><br>
    <small>Equipo: Andrea Tinco · Minerva Vidal · Mickella Umeres · Jared Olortiga</small>
  </footer>

  <script>
    const dias = ['Domingo','Lunes','Martes','Miércoles','Jueves','Viernes','Sábado'];
    const meses = ['enero','febrero','marzo','abril','mayo','junio','julio','agosto','septiembre','octubre','noviembre','diciembre'];
    const hoy = new Date();
    document.getElementById('fecha').textContent =
      dias[hoy.getDay()] + ', ' + hoy.getDate() + ' de ' + meses[hoy.getMonth()] + ' de ' + hoy.getFullYear();
  </script>

</body>
</html>
