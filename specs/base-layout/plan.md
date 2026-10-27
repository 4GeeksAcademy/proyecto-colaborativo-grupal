# Plan: plantilla HTML común

## Objetivo y alcance

Preparar una plantilla de referencia y navegación común para las cinco vistas de la tienda, siguiendo [spec.md](spec.md), [DESIGN.md](../../DESIGN.md) y [AGENTS.md](../../AGENTS.md).

La referencia se encuentra en `docs/reference/base.html`. Las rutas de navegación tienen páginas HTML provisionales en la raíz; sus funciones comerciales siguen pendientes.

## Acuerdos provisionales

- Idioma español y rótulo neutro "Marca", confirmados para la plantilla, no como identidad definitiva.
- Bodoni Moda y Manrope mediante Google Fonts, con fuentes alternativas.
- Rutas acordadas: `/`, `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`.
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

- La plantilla se actualizó con los cinco enlaces, navegación móvil equivalente, logo y acceso al carrito funcionales, footer sin enlaces vacíos y sin vista activa por defecto.
- Se crearon páginas provisionales para catálogo, producto, carrito y checkout; cada una tiene contenido y metadatos propios, navegación común y una marca de página actual.
- Las páginas provisionales tienen `noindex,nofollow` y declaran sus funcionalidades pendientes; no se implementaron búsqueda, autenticación, gestión comercial del carrito ni pagos.
- El editor no reporta errores de HTML/JavaScript en las páginas; mantiene avisos CSS de `@theme`/`@apply` que deben comprobarse en navegador con Tailwind v4.
- La comprobación visual en móvil/tablet/escritorio y las pruebas de teclado todavía están pendientes.

## Límites y cierre

- No implementar autenticación, búsqueda comercial, persistencia ni pagos reales.
- Completar el contenido y las funciones de catálogo, producto, carrito y checkout antes de retirar `noindex,nofollow`.
- Ejecutar comprobaciones enfocadas, sin crear archivos de pruebas ni herramientas de build.
- Completar la revisión pendiente antes de dar la plantilla por validada; usar [tasks.md](tasks.md) para el seguimiento.