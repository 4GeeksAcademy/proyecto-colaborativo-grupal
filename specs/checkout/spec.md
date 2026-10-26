# Especificación: checkout

## Objetivo y fuentes

Definir el flujo de checkout de tres pasos para continuar desde un carrito no vacío y finalizar una compra de demostración.

El flujo tiene este orden: 1) Datos personales, 2) Dirección de entrega y 3) Pago con tarjeta simulado. La navbar y el footer comunes se mantienen en la página durante los tres pasos y la confirmación.

- Requisitos generales: [Context.md](../../Context.md), apartados Checkout y comportamiento compartido.
- Diseño: [DESIGN.md](../../DESIGN.md).
- Límites del proyecto: [AGENTS.md](../../AGENTS.md).
- Referencia de importes: [carrito](../cart/spec.md).

El usuario confirmó este orden de pasos: datos personales, dirección de entrega y pago con tarjeta. El proyecto no permite cargos reales ni solicitar o almacenar datos bancarios reales; por tanto, el paso de pago es una simulación sin captura de datos de tarjeta.

## Alcance

- Reutilizar navbar y footer comunes, manteniéndolos presentes durante todos los pasos y la confirmación.
- Presentar un indicador de progreso y un formulario principal para tres pasos.
- Mantener un resumen del pedido relacionado con el carrito.
- Permitir avanzar y retroceder sin perder los datos personales y de entrega durante el flujo.
- Validar los campos obligatorios antes de avanzar y explicar los errores junto a los controles.
- Finalizar con una confirmación simulada, sin procesar pagos.
- No añadir backend comercial, autenticación ni almacenamiento permanente de datos personales o financieros.

## Flujo

### Paso 1: Datos personales

- Mostrar un formulario etiquetado para los datos personales que se acuerden.
- Marcar y validar los campos obligatorios según el conjunto de campos que apruebe el equipo.
- No inventar campos definitivos; nombre, correo y teléfono son opciones por confirmar.
- Permitir avanzar a la dirección solo cuando los campos obligatorios acordados sean válidos.

### Paso 2: Dirección de entrega

- Mostrar un formulario etiquetado para la dirección de entrega.
- Confirmar con el equipo los campos obligatorios y el formato antes de implementarlos; no asumir países, formatos postales ni cobertura de entrega.
- Permitir volver al paso personal sin perder los valores introducidos.
- Permitir avanzar al paso de pago solo cuando los campos obligatorios acordados sean válidos.

### Paso 3: Pago con tarjeta (simulación)

- Identificar claramente el paso como pago de demostración; no procesar un cargo.
- No mostrar campos que soliciten número de tarjeta, fecha de vencimiento, CVV, PIN u otros datos bancarios reales.
- No guardar ni transmitir datos financieros.
- Mostrar una acción de confirmación de demostración que finalice el flujo y presente un estado de pedido confirmado como simulado.
- Permitir volver a los pasos previos sin perder los datos introducidos en ese flujo.

### Indicador y navegación

- Indicar cuál de los tres pasos está activo y cuáles se completaron, sin depender solo del color.
- Ofrecer acciones claras para avanzar y retroceder; no mostrar el paso de pago como procesador real.
- Conservar en el flujo los valores personales y de dirección cuando se cambia de paso.
- Impedir completar el checkout si el carrito está vacío; proporcionar una ruta de vuelta al carrito.

## Resumen del pedido

- Mostrar los productos, variantes, cantidades y los importes acordados con el carrito.
- Presentar subtotal, impuestos y total de forma consistente con el carrito.
- No fijar moneda, impuestos, inclusión de impuestos ni gastos de envío antes de confirmarlos.
- En escritorio, colocar el resumen junto al formulario; en móvil, debajo del contenido del paso actual.

## Campos y privacidad

- Los campos exactos de datos personales y dirección están pendientes de aprobación.
- Recoger solo los datos necesarios para la demostración y no persistirlos más allá de lo acordado.
- Nunca solicitar datos reales de tarjeta o credenciales bancarias.
- No afirmar que se creó una orden comercial o que se realizó un pago real.

## Diseño, responsive y accesibilidad

- Seguir [DESIGN.md](../../DESIGN.md): tipografías, paleta, espaciado, foco visible y controles legibles.
- Mantener navegación y pie de página coherentes con las otras vistas.
- Usar estructura semántica, un H1 descriptivo y un orden de encabezados lógico.
- Etiquetar todos los campos y asociar mensajes de error con su control.
- Permitir completar el flujo con teclado y objetivos táctiles de al menos 44 por 44 px.
- En móvil, apilar formulario y resumen sin desbordamiento ni solapamientos.
- Mostrar errores y estado de confirmación con texto, no solo con color.

## Criterios de aceptación

- El checkout presenta los tres pasos confirmados en el orden acordado.
- No se puede avanzar desde un paso si falta un campo obligatorio acordado o si sus datos no son válidos.
- Los valores personales y de dirección se conservan al avanzar y retroceder dentro del flujo.
- El paso 3 es una simulación, no incluye campos de tarjeta y no realiza cargos.
- La confirmación indica que la compra es de demostración.
- Un carrito vacío no puede iniciar ni completar el checkout.
- El resumen y sus importes coinciden con el carrito y no usan reglas fiscales inventadas.
- El flujo es responsive y navegable con teclado; los errores son comprensibles y accesibles.

## Decisiones pendientes

- Campos obligatorios de datos personales y dirección de entrega.
- Países, cobertura y validación de formatos de dirección.
- Moneda, impuestos, precios con o sin impuestos y gastos de envío.
- Texto y comportamiento exactos de la confirmación simulada.
- Persistencia temporal de los datos personales y de dirección durante el flujo.
- Rutas definitivas de carrito, checkout y confirmación.