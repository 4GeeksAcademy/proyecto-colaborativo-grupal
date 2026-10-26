# Plan: página provisional de revisión del menú

Crear `menu.html` en la raíz del proyecto para revisar visualmente el menú común, reutilizando `docs/reference/base.html`. Esta página será una vista provisional de comprobación, no una nueva vista comercial ni una integración del menú en las cinco páginas.

## Pasos

1. Usar `docs/reference/base.html` como fuente y conservar su estructura, recursos, estilos Tailwind, navegación, `main` vacío, footer e interacciones nativas.
2. Ajustar solo los metadatos necesarios para identificar `menu.html` como página provisional de revisión.
3. Mantener deshabilitados los enlaces y controles cuyo destino o comportamiento sigue pendiente, según `spec.md`. No inventar rutas ni implementar búsqueda, autenticación, contador o persistencia del carrito.
4. Validar estructura y errores del editor; después revisar la página en escritorio, tablet y móvil, y comprobar el teclado, Escape y retorno del foco.

## Criterios

- Mantener el diseño y la accesibilidad especificados en [spec.md](spec.md) y [DESIGN.md](../../DESIGN.md).
- No modificar la plantilla de referencia ni otras vistas como parte de este trabajo.
- No dar por verificada la presentación visual hasta probarla en el navegador.

## Decisiones pendientes

- Marca, logo e idioma definitivos.
- Rutas de navegación y destinos del footer.
- Alcance real de búsqueda y menú de cuenta.
- Si se aprueban un contador y persistencia del carrito.
- Cómo compartir la navbar entre las cinco vistas; no imponer una arquitectura desde esta página provisional.