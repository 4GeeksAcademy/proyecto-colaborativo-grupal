# Tareas: checkout

Basadas en [spec.md](spec.md) y [plan.md](plan.md). El flujo de demostración está implementado; las decisiones comerciales y verificaciones manuales de interfaz siguen pendientes.

## Requisitos documentados

- [x] Confirmar el orden de los pasos: datos personales, dirección de entrega y pago con tarjeta.
- [x] Confirmar que la navbar y el footer comunes se mantienen durante los tres pasos y la confirmación.
- [x] Definir indicador, navegación entre pasos, validación y conservación de datos durante el flujo.
- [x] Limitar el pago a una simulación sin datos bancarios ni cargos.
- [x] Definir resumen del pedido coherente con el carrito.
- [x] Registrar campos y reglas comerciales que aún no están confirmados.

## Decisiones pendientes

- [ ] Confirmar los campos obligatorios de datos personales.
- [ ] Confirmar campos, formatos, países y cobertura de la dirección.
- [ ] Confirmar moneda, impuestos, inclusión de impuestos y envío.
- [ ] Aprobar el texto de confirmación de compra simulada.
- [ ] Acordar cuánto tiempo se conservan los datos personales y de dirección durante el flujo.
- [ ] Confirmar las rutas de carrito, checkout y confirmación.

## Implementación

- [x] Crear la página `checkout.html` reutilizando navbar y footer comunes durante todo el flujo.
- [x] Mostrar indicador accesible de los tres pasos: datos personales, dirección de entrega y pago con tarjeta simulado.
- [x] Implementar formularios provisionales de datos personales con etiquetas y validación; los campos definitivos siguen pendientes de aprobación.
- [x] Implementar formulario provisional de dirección con etiquetas y validación; sus campos y formatos definitivos siguen pendientes.
- [x] Conservar los valores al avanzar y retroceder dentro de la página.
- [x] Implementar un paso de pago simulado sin campos ni captura de datos bancarios.
- [x] Impedir iniciar o completar el flujo con el carrito vacío.
- [x] Mostrar resumen de productos y subtotal, y confirmación claramente simulada; impuestos y total final siguen pendientes de reglas acordadas.

## Verificación

- [ ] Probar errores de campos obligatorios y corrección de valores.
- [ ] Probar avance y retroceso sin pérdida de datos.
- [ ] Comprobar el bloqueo de checkout con carrito vacío.
- [x] Revisar el código para confirmar que no solicita ni transmite datos bancarios ni realiza cargos.
- [ ] Revisar semántica, foco, teclado y mensajes accesibles.
- [ ] Revisar móvil, tablet y escritorio, incluida la ubicación del resumen.
- [ ] Completar un recorrido de demostración desde carrito hasta confirmación.