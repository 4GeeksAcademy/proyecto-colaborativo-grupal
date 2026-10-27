# Plan: página Home

## Objetivo y alcance

Crear `index.html` en la raíz del proyecto para que `server.py` sirva la página Home en `/`. La página incluirá navbar, hero promocional, listados horizontales de nuevos lanzamientos y más vendidos, y footer. Seguirá [spec.md](spec.md), los requisitos de [Context.md](../../Context.md), la dirección visual propuesta en [DESIGN.md](../../DESIGN.md) y los patrones de [docs/reference/base.html](../../docs/reference/base.html).

Este plan incluye la navegación común acordada. Solo Home está implementada; las otras cuatro páginas se crearán después.

## Acuerdos provisionales

- Usar español y el nombre «Marca» como identidad provisional.
- Usar placeholders estáticos: `index.html` conserva el contenido indexable y no depende de Jinja ni de datos cargados por JavaScript.
- Marcar con comentarios `REEMPLAZAR:` los datos modificables; usar valores visibles provisionales sin inventar precios definitivos, moneda, campaña ni información comercial.
- Mantener rutas estables bajo `assets/home/` para logo, hero y productos; crear placeholders válidos que puedan sustituirse conservando nombres y proporciones.
- Incluir controles accesibles anterior/siguiente para el desplazamiento horizontal de cada listado.
- Mantener la búsqueda y el menú de cuenta inactivos; no implementar búsqueda funcional, autenticación ni backend.
- Repetir de forma consistente el markup de navbar y footer de la plantilla. No introducir una arquitectura de componentes compartidos en esta fase.
- Usar las rutas comunes `/`, `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`.
- Conservar las cinco rutas en navbar. Mantener el CTA y las tarjetas no interactivos hasta que existan las páginas de catálogo y producto; dejar el footer sin destinos no confirmados.

## Pasos

1. Crear el documento `index.html` con estructura semántica, `lang="es"`, metadatos propios de Home y Tailwind CSS v4 por CDN. Mantener el contenido principal en HTML indexable y no trasladar `noindex,nofollow` del ejemplo de menú.
2. Crear los placeholders PNG de `assets/home/` y el logo SVG; documentar sus nombres, dimensiones y proporciones en [spec.md](spec.md). Marcar el contenido reemplazable con comentarios `REEMPLAZAR:`.
3. Incorporar el enlace para saltar al contenido y la navbar responsive con las cinco rutas previstas; mantener búsqueda y cuenta inactivas.
4. Crear el hero con H1 descriptivo, imagen con dimensiones y texto alternativo, y CTA pendiente e inactivo hasta que exista `/catalogo.html`. Mantener el contenido legible y dejar visible el inicio de la sección siguiente.
5. Crear los listados de demostración con tarjetas informativas no interactivas hasta que exista `/producto.html`.
6. Añadir desplazamiento horizontal y controles accesibles anterior/siguiente a cada listado. Los controles deben respetar los extremos del desplazamiento y no producir overflow horizontal en la página.
7. Incorporar el footer de referencia con categorías, información legal, sobre la marca y contacto; dejar inactivos los destinos pendientes.
8. Verificar la página en el servidor y revisar diseño responsive, teclado, enlaces, recursos y errores de JavaScript. Registrar las verificaciones realmente ejecutadas.

## Convenciones visuales y accesibilidad

- Usar Bodoni Moda para títulos y Manrope para contenido, con alternativas; aplicar la paleta propuesta sin presentarla como identidad definitiva.
- Mantener ancho máximo de 1280 px, márgenes laterales de 16 px en móvil y 24 px en escritorio, foco visible y controles táctiles accesibles.
- El hero debe tener contraste suficiente; las imágenes informativas tendrán texto alternativo y dimensiones para reducir saltos de contenido.
- Usar encabezados en orden, nombres accesibles para controles de icono y navegación completa mediante teclado.
- Evitar tarjetas decorativas para secciones, recortes de texto, solapamientos y desbordamiento horizontal.

## Criterios de aceptación

- `http://localhost:3000/` muestra Home; las otras cuatro rutas quedan pendientes de creación.
- Navbar y footer contienen los elementos acordados y se adaptan a móvil, tablet y escritorio.
- El hero presenta un H1 único, contenido legible y un CTA inactivo hasta que exista su destino.
- Las secciones muestran tarjetas informativas; sus controles desplazan horizontalmente el listado con teclado y puntero.
- Título, descripción e idioma corresponden a Home; el documento no queda marcado como `noindex,nofollow`.
- No hay imágenes rotas, enlaces vacíos engañosos, errores de JavaScript, recortes, solapamientos ni overflow horizontal.

## Fuera de alcance y pendientes

- Marca y logo definitivos, precios reales, moneda, campañas y recursos gráficos comerciales.
- Búsqueda funcional, cuenta, catálogo, carrito, backend, pagos y persistencia.
- Destinos definitivos para categorías, información legal y contacto.
- Definir cómo compartir navbar y footer con las otras vistas.
- No crear pruebas nuevas salvo petición explícita; no añadir frameworks, dependencias ni herramientas de build.
