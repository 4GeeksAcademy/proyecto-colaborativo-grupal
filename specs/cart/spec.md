# Especificación: carrito

## Objetivo y fuentes

Definir la vista completa del carrito y su comportamiento dentro del recorrido de compra.

- Requisitos generales: [Context.md](../../Context.md), apartados Carrito y comportamiento compartido.
- Diseño: [DESIGN.md](../../DESIGN.md).
- Límites del proyecto: [AGENTS.md](../../AGENTS.md).
- Referencias relacionadas: [menú común](../menu/spec.md) y [checkout](../checkout/spec.md).

Esta es una especificación; no representa una interfaz implementada.

## Alcance

- Crear una página completa de carrito, no un panel lateral ni un modal.
- Reutilizar la navegación y el pie de página comunes.
- Enmarcar el listado y el resumen del pedido entre la navbar y el footer en una misma vista completa.
- Mostrar tres productos de demostración para que el estado inicial permita revisar la composición visual.
- Permitir revisar, modificar y eliminar líneas del carrito.
- No añadir autenticación, backend comercial ni procesamiento de pagos.
- Mantener idioma, marca, moneda, impuestos, precios y envío sin confirmar hasta que haya una decisión del equipo.

## Contenido de la página

### Lista de productos

Mostrar cada línea del carrito con:

- Miniatura del producto, con texto alternativo descriptivo y dimensiones reservadas.
- Nombre del producto y, cuando corresponda, variante o talla.
- Precio unitario.
- Cantidad seleccionada.
- Total de la línea, calculado como precio unitario por cantidad.
- Control para cambiar la cantidad y acción para eliminar el producto.

Identificar cada línea por producto y talla. Al añadir otra vez la misma combinación, sumar su cantidad en lugar de crear una línea duplicada. La selección de talla debe seguir visible para distinguir variantes.

Los tres productos de demostración deben reutilizar identificadores, variantes, nombres, imágenes y precios coherentes con el resto del prototipo. No fijar importes finales hasta confirmar moneda y reglas fiscales.

### Resumen del pedido

Mostrar un cuadro de totalización con subtotal, impuestos y total, además de un botón **Comprar** que conduce al checkout.

- Actualizar cantidades, total de línea, subtotal, impuestos y total tras modificar o eliminar productos.
- Calcular el subtotal a partir de las líneas del carrito.
- Aplicar impuestos y mostrar el total solo según las reglas aprobadas por el equipo.
- No asumir si los precios ya incluyen impuestos, el tipo impositivo, la moneda ni los gastos de envío.
- No inventar una estimación de envío ni sumar un cargo no definido.

### Carrito vacío

- Mostrar un estado vacío cuando no haya líneas.
- Incluir un enlace descriptivo para volver al catálogo.
- No permitir continuar al checkout sin productos.
- No volver a insertar automáticamente los productos de demostración después de que el usuario vacíe el carrito.

## Interacción y estados

- Cambiar la cantidad actualiza el total de su línea y el resumen.
- La cantidad debe ser un entero mayor que cero; cualquier control debe impedir cantidades inválidas y comunicar el error con texto.
- Eliminar una línea actualiza el resumen; eliminar la última lleva al estado vacío.
- El botón **Comprar** solo está disponible con un carrito no vacío y lleva al flujo de checkout.
- La persistencia del carrito sigue pendiente de aprobación. Si se acuerda, los productos de ejemplo solo se insertarán cuando corresponda a un carrito nuevo; nunca se debe repoblar uno que el usuario haya vaciado.
- No presentar datos de demostración como una compra real.

## Diseño, responsive y accesibilidad

- Seguir [DESIGN.md](../../DESIGN.md): fondo claro, tipografía Manrope para contenido y controles, Bodoni Moda para títulos, espaciado basado en múltiplos de 8 px y radios discretos.
- Presentar lista y resumen en una composición de página completa. En pantallas estrechas, apilar el resumen debajo de los productos.
- No usar un panel lateral como sustituto de la vista del carrito.
- Evitar desbordamiento horizontal; permitir que nombres y controles largos se adapten al ancho.
- Usar controles con etiquetas accesibles, nombres claros para eliminar productos y foco visible.
- Mantener objetivos táctiles de al menos 44 por 44 px.
- No depender solo del color para indicar errores, cambios o estados vacíos.
- Usar estructura semántica, un H1 descriptivo y metadatos propios de la página.

## Criterios de aceptación

- La vista es una página completa y reutiliza navegación y pie de página comunes.
- Se muestran tres productos de demostración con miniatura, precio unitario, cantidad y total por línea.
- Se puede modificar la cantidad y eliminar una línea; los importes relacionados se actualizan.
- Se muestran subtotal, impuestos, total y botón **Comprar** cuando hay productos.
- El estado vacío incluye enlace al catálogo e impide continuar al checkout.
- Las líneas se identifican por producto y talla; una combinación repetida suma cantidades.
- No se asumen moneda, tipo impositivo, inclusión de impuestos ni envío.
- La vista se puede usar con teclado y en móvil, tablet y escritorio sin recortes ni solapamientos.
- No se incorporan backend comercial, autenticación ni pagos reales.

## Decisiones pendientes

- Moneda y formato local de precios.
- Tipo impositivo, si los precios incluyen impuestos y método de cálculo.
- Si se mostrarán gastos de envío en el carrito o solo en checkout.
- Precios y conjunto definitivo de productos de demostración.
- Persistencia del carrito y criterio para inicializar los tres ejemplos.
- Rutas definitivas del catálogo y checkout.