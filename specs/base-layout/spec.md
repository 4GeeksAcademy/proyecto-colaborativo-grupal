# Especificación: plantilla HTML común

## Objetivo

Definir una plantilla de referencia para Home, catálogo, producto, carrito y checkout, con estructura semántica, navbar y footer consistentes y un área principal vacía.

Fuentes: [Context.md](../../Context.md), [DESIGN.md](../../DESIGN.md) y [AGENTS.md](../../AGENTS.md).

## Alcance y entregable futuro

- La plantilla se guardará en `docs/reference/base.html`.
- Esta tarea solo documenta requisitos; no crea la plantilla ni implementa código.
- Incluir estructura del documento, metadatos básicos, Tailwind CSS v4 por CDN, navbar, un único `main` vacío y footer.
- No incluir hero, productos, filtros, carrito, formularios ni contenido específico de las vistas.
- La plantilla es una referencia estática; `/` sirve Home. La navbar reserva `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`, pero sus archivos se crearán en una fase posterior.
- No introducir frameworks, dependencias de build ni una arquitectura de componentes.

## Documento y dependencias

- Usar HTML5, codificación UTF-8 y configuración de viewport para dispositivos móviles.
- Declarar el idioma según la decisión del proyecto; no deducirlo de la sede de la marca.
- Reservar título y descripción para que cada página tenga valores únicos y descriptivos antes de publicarse.
- Cargar Tailwind CSS v4 mediante el CDN oficial documentado en la plantilla del repositorio: https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.
- No sustituirlo por Tailwind v3 ni exigir instalación con npm.
- Aplicar Bodoni Moda a títulos y Manrope a contenido y controles, con alternativas serif y sans-serif respectivamente.
- Acordar el método de carga de fuentes sin convertirlo en un requisito de build.

## Estructura semántica

- Orden del contenido: enlace de salto al contenido, `header` con `nav`, `main` y `footer`.
- El `main` tendrá un identificador que permita el salto desde teclado y estará completamente vacío: sin texto, secciones, H1 ni contenido de ejemplo.
- Cada futura página añadirá su contenido y un H1 descriptivo dentro del `main`.
- Mantener navbar y footer en el flujo normal, sin tapar contenido ni fijarlos sobre la pantalla.
- Permitir que el footer llegue al final del viewport cuando el contenido sea escaso.

## Navbar

- Incluir las cinco vistas comunes: Inicio (`/`), Catálogo (`/catalogo.html`), Vista de producto (`/producto.html`), Carrito (`/carrito.html`) y Formulario de pago (checkout; `/checkout.html`).
- El logo enlaza a Inicio; el acceso por icono al carrito enlaza a `/carrito.html`.
- Marcar la vista actual con `aria-current="page"` en cada página implementada. La plantilla de referencia no debe declarar una vista activa por defecto.
- Incluir búsqueda y menú de cuenta; mantener su comportamiento inactivo hasta acordarlo.
- La vista de producto de demostración se puede abrir desde Catálogo y desde las tarjetas de Home.
- Proporcionar un campo de búsqueda con etiqueta accesible, no solo un placeholder.
- Mostrar las cinco vistas en navegación de escritorio desde un ancho suficiente; en anchos menores, ofrecer un menú compacto con esas mismas rutas y sin desbordamiento.
- Mantener esos cuatro href como destinos futuros aunque sus archivos todavía no existan; no considerar esas rutas funcionales hasta crear las vistas.
- Prever un menú compacto para móvil con control accesible, estado expandido identificable y navegación mediante teclado.
- Los botones de icono tendrán nombre accesible y ayuda para iconos poco familiares.
- No implementar autenticación, resultados de búsqueda, contador de carrito ni persistencia como parte de esta plantilla.
- El comportamiento definitivo de búsqueda y cuenta queda pendiente; no presentar controles de demostración como servicios operativos.

## Footer

- Organizar enlaces por categorías, información legal y contacto.
- Categorías: calzado, camisas, pantalones y accesorios.
- Información legal: términos y condiciones, política de privacidad e información sobre la marca.
- No inventar direcciones, correos, datos de empresa ni textos legales.
- Apilar los grupos en móvil y distribuirlos en columnas cuando el espacio lo permita.
- Mantener como texto no interactivo los destinos legales, categorías y contacto que todavía no tengan páginas aprobadas; no usar anchors sin `href`.

## Diseño responsive y accesibilidad

- Fondo principal `#FAFAF8`, texto principal `#202020` y texto secundario `#595959`.
- Acento `#A3293D`, fondo secundario `#EEF1ED` y separadores `#D6D6D2`; comprobar contraste en controles y foco.
- Contenido común con ancho máximo de 1280 px y márgenes laterales de 24 px en escritorio y 16 px en móvil.
- Usar espaciado en múltiplos de 8 px, radios de 4 px y texto de controles de 16 px.
- Mantener espaciado entre letras en cero y evitar sombras decorativas y secciones encerradas en tarjetas.
- No añadir fotografías de campaña ni contenido visual de producto a esta base; el logo queda sujeto a recursos autorizados.
- Adaptar navbar y footer a móvil, tablet y escritorio sin recortes, solapamientos ni desbordamiento horizontal.
- Mantener objetivos táctiles de al menos 44 por 44 px, foco visible y orden de tabulación lógico.
- No depender exclusivamente del color para comunicar estados; respetar etiquetas y semántica de enlaces y botones.

## Criterios de aceptación y verificación futura

- La implementación futura existe en la ubicación acordada y carga Tailwind CSS v4 desde el CDN indicado.
- El documento incluye viewport, codificación, idioma y metadatos adaptables por página.
- Existe exactamente un `main`, vacío y accesible mediante el enlace de salto.
- Navbar y footer contienen los elementos acordados; la navegación conserva href para las cinco rutas previstas y el footer sus grupos definidos.
- Las cuatro rutas futuras no se consideran funcionales hasta que se creen sus archivos HTML.
- No hay anchors sin `href`; los elementos sin destino aprobado son no interactivos.
- Cada vista implementada marca la actual con `aria-current="page"`; la plantilla de referencia no marca ninguna como actual.
- Revisar manualmente móvil, tablet y escritorio, teclado, foco, menú compacto y ausencia de solapamientos.
- Comprobar carga de recursos, contraste y destinos de enlaces cuando estén definidos.
- No afirmar funcionalidad comercial, autenticación, búsqueda ni persistencia que no se hayan implementado.
- En esta fase solo verificar la estructura del documento y sus referencias; no iniciar el servidor ni crear pruebas nuevas.

## Decisiones pendientes

- Marca, logo autorizado, idioma definitivo y datos de contacto.
- Destinos de categorías, enlaces legales y contacto.
- Alcance de búsqueda y cuenta, y método de carga de las fuentes.
- Esta especificación no aprueba las propuestas pendientes de checkout, impuestos, moneda ni persistencia.