# Plan: plantilla HTML común

## Objetivo y alcance

Preparar una plantilla de referencia para las cinco vistas de la tienda, siguiendo [spec.md](spec.md), [DESIGN.md](../../DESIGN.md) y [AGENTS.md](../../AGENTS.md).

El único archivo de implementación previsto es `docs/reference/base.html`: Tailwind CSS v4 por CDN, navbar, footer y un único `main` vacío. No crear todavía las páginas de la tienda ni servicios comerciales.

## Acuerdos provisionales

- Idioma español y rótulo neutro "Marca", confirmados para la plantilla, no como identidad definitiva.
- Bodoni Moda y Manrope mediante Google Fonts, con fuentes alternativas.
- Destinos y servicios pendientes deshabilitados, sin inventar rutas, contactos ni datos comerciales.

## Pasos

1. Confirmar los valores provisionales y mantener identificadas las decisiones definitivas pendientes.
2. Crear el documento HTML con codificación, viewport, metadatos adaptables, Tailwind CSS v4 por CDN y enlace de salto al contenido.
3. Aplicar paleta, tipografías, ancho máximo de 1280 px, márgenes responsive y espaciado definidos en la guía visual.
4. Construir navbar y footer: búsqueda, menús de cuenta y móvil, acceso al carrito, categorías, información legal y contacto. Mantener deshabilitados los servicios sin implementar.
5. Conservar un único `main` vacío y un footer en el flujo normal, sin superponerlo al contenido.
6. Verificar estructura, recursos externos, teclado, contraste y adaptación a móvil, tablet y escritorio. Registrar qué sigue pendiente.

## Estado al guardar este plan

- La plantilla ya fue creada en una petición anterior; esta petición solo añade documentación.
- Se comprobó el `main` único y vacío, la referencia al CDN v4, la presencia de navbar y footer y la ausencia de enlaces con destino vacío.
- Se comprobó la sintaxis JavaScript y no se detectaron errores del editor.
- No se verificaron visualmente los tamaños de pantalla, la carga de recursos ni las interacciones de teclado en un navegador.

## Límites y cierre

- No modificar la plantilla durante esta fase documental.
- No implementar autenticación, búsqueda comercial, persistencia, pagos ni las cinco vistas.
- Ejecutar comprobaciones enfocadas, sin crear archivos de pruebas ni herramientas de build.
- Completar la revisión pendiente antes de dar la plantilla por validada; usar [tasks.md](tasks.md) para el seguimiento.