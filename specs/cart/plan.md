# Plan: implementar el carrito

Implementar una página de carrito completa que permita revisar productos y cantidades, con importes consistentes con las reglas que acuerde el equipo.

## Fases

1. **Cerrar datos compartidos**: acordar productos de demostración, variantes, moneda, presentación de precios, impuestos, envío y persistencia. Mantener sin cálculo definitivo los conceptos que sigan pendientes.
2. **Construir la página**: reutilizar navbar y footer; mostrar inicialmente tres productos en una página completa. Cada línea debe incluir miniatura, precio unitario, cantidad y total por línea. Presentar junto al listado un resumen con subtotal, impuestos y total, además del botón **Comprar**; apilar el resumen debajo en móvil.
3. **Implementar interacciones**: cambiar cantidades, eliminar líneas, recalcular importes y mostrar el estado vacío. Evitar continuar al checkout con el carrito vacío.
4. **Conectar el recorrido**: enlazar **Comprar** al checkout y compartir el mismo modelo de productos y variantes con catálogo, producto y checkout.
5. **Verificar**: revisar teclado, estados, cálculos acordados y adaptación a móvil, tablet y escritorio.

## Criterios para avanzar

- Antes de implementar cálculos finales, deben acordarse moneda, impuestos, inclusión de impuestos y envío.
- Las líneas se identifican por producto y talla; combinar cantidades repetidas.
- Los datos de demostración no deben volver a aparecer después de vaciar el carrito.
- No añadir persistencia hasta aprobar su comportamiento.
- No presentar precios o impuestos inventados como definitivos.

## Validación prevista

- Comprobar navbar y footer comunes, los tres artículos iniciales y que cada línea muestre miniatura, precio unitario, cantidad y total.
- Comprobar el resumen con subtotal, impuestos, total y botón **Comprar**; validar importes finales solo después de acordar las reglas comerciales.
- Comprobar cantidades válidas, eliminación y actualización de subtotales.
- Revisar estado vacío, enlace al catálogo y bloqueo de checkout sin productos.
- Comprobar el flujo con teclado, lectores de pantalla en los controles principales y tamaños móvil, tablet y escritorio.
- Verificar que navbar y footer coincidan con las demás vistas.

Estas comprobaciones son futuras; no se han ejecutado sobre una interfaz.