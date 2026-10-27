# Tareas: plantilla HTML común

Basadas en [spec.md](spec.md) y [plan.md](plan.md). Las casillas marcadas reflejan trabajo realizado anteriormente; las restantes requieren verificación o una decisión posterior. Esta petición no implementa cambios en la plantilla.

## Acuerdos

- [x] Confirmar español provisional y rótulo "Marca".
- [x] Confirmar carga de fuentes mediante Google Fonts.
- [x] Acordar las rutas de Inicio, Catálogo, Vista de producto, Carrito y Checkout.
- [x] Mantener como texto no interactivo los destinos pendientes del footer.

## Plantilla existente

- [x] Crear el archivo HTML en la ubicación acordada.
- [x] Añadir codificación, viewport y metadatos de referencia.
- [x] Incluir Tailwind CSS v4 mediante el CDN indicado.
- [x] Declarar la paleta y las tipografías propuestas.
- [x] Añadir navbar con las cinco vistas en escritorio y móvil.
- [x] Enlazar logo a Inicio y acceso al carrito a su página.
- [x] Marcar la vista actual en cada página y dejar neutral la plantilla de referencia.
- [x] Cambiar anchors sin `href` por texto no interactivo y quitar etiqueta ARIA del `div` genérico.
- [x] Añadir desplegables nativos de cuenta y navegación móvil.
- [x] Añadir footer con categorías, información legal y contacto.
- [x] Mantener un único `main` vacío, sin H1.
- [x] Añadir enlace de salto al contenido.
- [x] Mantener búsqueda/cuenta inactivas y destinos legales sin rutas como texto.
- [x] Crear páginas provisionales en las cuatro rutas que no existían.
- [x] Mantener `noindex,nofollow` en las vistas provisionales hasta completar su contenido.

## Comprobaciones realizadas

- [x] Comprobar estructura HTML, `main` vacío y referencia al CDN v4.
- [x] Comprobar ausencia de enlaces con destino vacío.
- [x] Comprobar sintaxis del JavaScript.
- [x] Consultar errores del editor en la plantilla.
- [x] Comprobar que las páginas provisionales no tienen errores de HTML/JavaScript en el editor.
- [x] Comprobar que las cinco rutas responden desde el servidor.
- [x] Comprobar estáticamente que todos los enlaces comunes llegan a la vista correspondiente.

## Verificación pendiente en navegador

- [ ] Comprobar que Tailwind CSS carga y aplica los estilos.
- [ ] Comprobar carga de las fuentes y los iconos.
- [ ] Revisar navbar y footer en móvil.
- [ ] Revisar navbar y footer en tablet.
- [ ] Revisar navbar y footer en escritorio.
- [ ] Comprobar ausencia de recortes, solapamientos y desbordamiento horizontal.
- [ ] Probar apertura y cierre de ambos menús con teclado.
- [ ] Comprobar cierre con Escape y retorno del foco.
- [ ] Comprobar enlace de salto y foco sobre el `main`.
- [ ] Revisar contraste, foco visible y objetivos táctiles.
- [ ] Comprobar que el footer no tapa contenido.

## Antes de reutilizar en páginas definitivas

- [ ] Confirmar marca, logo, idioma definitivo y datos de contacto.
- [ ] Acordar y conectar las rutas y los destinos legales.
- [ ] Definir el comportamiento definitivo de búsqueda y cuenta.
- [ ] Adaptar título, descripción y política de indexación de cada página.
- [ ] Registrar resultados reales de las verificaciones pendientes.

## Funcionalidad de vistas pendiente

- [ ] Implementar catálogo con 20 productos, filtros por categoría/talla y estado sin resultados.
- [ ] Implementar selección y validación de talla/cantidad y acción de agregar al carrito.
- [ ] Implementar carrito con productos de ejemplo, cantidades, eliminación e importes tras confirmar moneda/impuestos.
- [ ] Confirmar pasos restantes del checkout; validar campos y simular confirmación sin procesar pagos.
- [ ] Retirar `noindex,nofollow` solo cuando el contenido de cada vista esté completo y listo para indexación.