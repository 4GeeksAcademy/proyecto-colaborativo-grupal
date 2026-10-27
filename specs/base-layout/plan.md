# Plan: plantilla HTML común

## Objetivo y alcance

Preparar una plantilla de referencia y navegación común para las cinco vistas de la tienda, siguiendo [spec.md](spec.md), [DESIGN.md](../../DESIGN.md) y [AGENTS.md](../../AGENTS.md).

La referencia se encuentra en `docs/reference/base.html`. Solo Home está implementada en `index.html`; las otras cuatro rutas permanecen en la navbar como destinos planificados, pero sus páginas se crearán después.

## Acuerdos provisionales

- Idioma español y rótulo neutro "Marca", confirmados para la plantilla, no como identidad definitiva.
- Bodoni Moda y Manrope mediante Google Fonts, con fuentes alternativas.
- Rutas acordadas para la navbar: `/`, `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`; solo `/` tiene actualmente un archivo HTML.
- Destinos legales y servicios comerciales pendientes, sin inventar contactos ni datos.

## Pasos

1. Confirmar los valores provisionales y mantener identificadas las decisiones definitivas pendientes.
2. Crear el documento HTML con codificación, viewport, metadatos adaptables, Tailwind CSS v4 por CDN y enlace de salto al contenido.
3. Aplicar paleta, tipografías, ancho máximo de 1280 px, márgenes responsive y espaciado definidos en la guía visual.
4. Construir navbar con las cinco vistas en escritorio y móvil; enlazar logo e icono del carrito; mantener búsqueda y cuenta sin función comercial.
5. Conservar el footer definido: categorías, legal/sobre la marca y contacto; dejar no interactivos los destinos no confirmados.
6. Conservar un único `main` vacío en la referencia; cada vista hija agrega contenido, metadatos propios y estado `aria-current`.
7. Verificar estructura, rutas, recursos externos, teclado, contraste y adaptación a móvil, tablet y escritorio. Registrar qué sigue pendiente.

## Estado al guardar este plan

- La plantilla se actualizó con los cinco enlaces previstos, navegación móvil equivalente, logo y acceso al carrito, footer sin enlaces vacíos y sin vista activa por defecto.
- Solo Home está implementada. Catálogo, producto, carrito y checkout fueron pospuestos y sus archivos se eliminaron; sus enlaces de navbar se conservan como rutas futuras.
- Búsqueda, autenticación, gestión comercial del carrito y pagos no están implementados.
- El editor no reporta errores de HTML/JavaScript en las páginas; mantiene avisos CSS de `@theme`/`@apply` que deben comprobarse en navegador con Tailwind v4.
- La comprobación visual en móvil/tablet/escritorio y las pruebas de teclado todavía están pendientes.

## Límites y cierre

- No implementar autenticación, búsqueda comercial, persistencia ni pagos reales.
- Crear las cuatro páginas faltantes antes de considerar funcional la navegación a esos destinos.
- Completar el contenido de cada vista antes de publicarla o decidir su política de indexación.
- Ejecutar comprobaciones enfocadas, sin crear archivos de pruebas ni herramientas de build.
- Completar la revisión pendiente antes de dar la plantilla por validada; usar [tasks.md](tasks.md) para el seguimiento.