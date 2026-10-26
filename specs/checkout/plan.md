# Plan: implementar el checkout

Implementar un flujo de compra demostrativo de tres pasos, conectado al carrito y sin cargos reales ni captura de datos bancarios.

## Pasos confirmados

1. **Datos personales**.
2. **Dirección de entrega**.
3. **Pago con tarjeta** como simulación, sin campos bancarios ni cargos reales.

La navbar y el footer comunes permanecen en la página durante los tres pasos y la confirmación.

## Fases

1. **Acordar campos y reglas**: definir campos personales y de dirección, validaciones, moneda, impuestos y envío. Mantener explícitamente pendientes las reglas no aprobadas.
2. **Preparar estructura común**: reutilizar navbar/footer durante todo el flujo, mostrar indicador de los tres pasos en el orden confirmado y resumen del pedido enlazado con el carrito.
3. **Implementar datos personales y entrega**: crear formularios etiquetados, validar antes de avanzar y conservar valores al retroceder o avanzar dentro del flujo.
4. **Implementar pago simulado**: mostrar el paso de pago con tarjeta como demostración, sin entradas de número, vencimiento o CVV, sin guardar ni transmitir datos financieros y sin integrar un procesador.
5. **Completar el recorrido**: impedir checkout con carrito vacío y mostrar confirmación inequívoca de una compra simulada.
6. **Verificar**: recorrer avance, retroceso, errores y confirmación con teclado y en móvil, tablet y escritorio.

## Criterios para avanzar

- No implementar campos personales o de dirección como definitivos hasta que el equipo acuerde cuáles son obligatorios.
- No introducir supuestos sobre países, cobertura, moneda, impuestos ni envío.
- No crear inputs para datos de tarjeta ni conectar proveedores de pago.
- Mantener el pedido y los importes coherentes con la especificación del carrito.

## Validación prevista

- Probar cada paso con campos válidos e incompletos; comprobar mensajes de error y conservación de datos.
- Comprobar navegación atrás/adelante y bloqueo con carrito vacío.
- Confirmar que el pago se identifica como simulado y que no existe captura de información bancaria.
- Revisar lector/teclado, foco y presentación responsive, incluido el resumen del pedido.

Estas comprobaciones son futuras; no se han ejecutado sobre una interfaz.