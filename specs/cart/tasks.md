# Tareas: carrito

Basadas en [spec.md](spec.md) y [plan.md](plan.md). La página y el enlace de checkout de demostración están implementados; las reglas comerciales y verificaciones visuales pendientes siguen sin marcar.

## Requisitos documentados

- [x] Definir una vista completa, no un panel lateral.
- [x] Especificar tres productos de demostración.
- [x] Enumerar miniatura, precio unitario, cantidad y total por línea.
- [x] Definir modificación de cantidad y eliminación de productos.
- [x] Definir resumen con subtotal, impuestos, total y acción **Comprar**.
- [x] Definir estado vacío, enlace al catálogo y bloqueo para continuar sin productos.
- [x] Registrar decisiones pendientes de moneda, impuestos, envío y persistencia.

## Decisiones y datos

- [ ] Confirmar moneda y formato de precios.
- [ ] Confirmar tipos impositivos y si los precios incluyen impuestos.
- [ ] Confirmar tratamiento de gastos de envío.
- [ ] Aprobar productos, variantes y precios de demostración.
- [ ] Acordar si se persiste el carrito y cuándo se inicializan los ejemplos.

## Implementación

- [x] Crear la página completa del carrito con navbar y footer comunes.
- [x] Mostrar los tres productos de ejemplo; cada línea presenta miniatura, precio unitario, cantidad y total por producto.
- [x] Mostrar el resumen con subtotal, impuestos, total y botón **Comprar**; los importes finales de impuestos y total siguen pendientes de las reglas acordadas.
- [x] Mostrar y actualizar las líneas por producto y talla.
- [x] Implementar edición de cantidades y eliminación.
- [ ] Calcular importes según las reglas aprobadas.
- [x] Añadir estado vacío y prevenir avance al checkout sin productos.
- [ ] Enlazar el estado vacío con el catálogo cuando se acuerde una ruta existente.
- [x] Conectar **Comprar** con `checkout.html`, transfiriendo solo productos, tallas y cantidades en la URL para esta demostración.

Los valores de ejemplo actualizan el subtotal y los totales por línea, pero no se calculan impuestos ni total final hasta que se acuerden moneda y reglas fiscales. **Comprar** queda deshabilitado si el carrito está vacío; la transferencia no persiste el carrito.

## Verificación

- [ ] Revisar estructura semántica, etiquetas, foco y navegación por teclado.
- [ ] Probar cantidades inválidas, modificación, eliminación y carrito vacío.
- [ ] Revisar la presentación responsive en móvil, tablet y escritorio.
- [ ] Comprobar que no haya desbordamientos, recortes ni solapamientos.
- [ ] Validar cálculos con moneda e impuestos aprobados.