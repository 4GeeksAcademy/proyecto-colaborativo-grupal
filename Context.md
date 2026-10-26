# Contexto del proyecto

## Objetivo

Crear, en un equipo de dos personas, un prototipo visual y funcional de una tienda online para una reconocida marca de ropa con sede en Francia. Antes del desarrollo completo, el cliente necesita validar cinco vistas principales, un diseño moderno y consistente, SEO y adaptación a móvil, tablet y escritorio.

La marca y su identidad visual están pendientes de confirmar. Su sede en Francia no implica que el idioma de la tienda deba ser francés.

## Base técnica y alcance

- Usar HTML semántico, Tailwind CSS y JavaScript para las interacciones.
- La plantilla permite incorporar Tailwind CSS v4 mediante su CDN oficial.
- Usar el servidor incluido en `server.py` para visualizar el proyecto, siguiendo `README.es.md`.
- Mantener el contenido principal de las páginas en HTML para que sea indexable.
- Trabajar con productos de demostración e imágenes con permiso de uso.
- No incluir autenticación real, backend comercial ni procesamiento real de pagos en esta fase.
- No solicitar ni almacenar datos bancarios reales.

## Requisitos por vista

### 1. Home

- Navbar con logo, barra de búsqueda y menú de cuenta de usuario.
- Hero con una campaña de la marca o productos especiales.
- Sección de nuevos lanzamientos con tarjetas de producto en un listado horizontal.
- Sección de más vendidos con tarjetas de producto en un listado horizontal.
- Footer con categorías: calzado, camisas, pantalones y accesorios.
- En el footer, incluir términos y condiciones, política de privacidad, información sobre la marca y contacto.

### 2. Catálogo

- Reutilizar navbar y footer.
- Colocar filtros por categoría y talla antes del listado de productos.
- Mostrar inicialmente 20 productos como referencia.
- Distribuirlos en una rejilla de cuatro columnas y cinco filas en escritorio.
- Reducir las columnas en tablet y móvil sin desbordar el ancho de la página.
- Permitir combinar y restablecer filtros; mostrar un estado sin resultados cuando corresponda.
- Enlazar cada producto con su vista de detalle.

### 3. Vista de producto

- Reutilizar navbar y footer.
- Usar dos columnas en escritorio: imagen a la izquierda e información a la derecha.
- La imagen debe ocupar aproximadamente la mitad del ancho disponible.
- Mostrar nombre, código o referencia, talla, precio y selector de cantidad.
- Incluir el botón "Agregar al carrito" y confirmar visualmente la acción.
- Validar la selección de talla y una cantidad entera mayor que cero.
- Incluir debajo una descripción detallada con materiales y usos recomendados.
- Apilar imagen e información en móvil.

### 4. Carrito

- Reutilizar navbar y footer; presentar una página completa, no un panel lateral.
- Incluir tres productos de ejemplo para demostrar el comportamiento visual.
- Mostrar miniatura, precio unitario, cantidad y total por producto.
- Permitir modificar cantidades y eliminar productos.
- Mostrar subtotal, impuestos y total, actualizados al modificar el carrito.
- Incluir un botón "Comprar" que lleve al checkout.
- Mostrar un estado vacío con enlace al catálogo y evitar continuar sin productos.

### 5. Checkout

- Reutilizar navbar y footer.
- Organizar el formulario en tres pasos con un indicador del paso actual.
- Paso 1 confirmado por el enunciado: datos personales.
- Paso 2 propuesto, pendiente de confirmar: dirección y método de envío.
- Paso 3 propuesto, pendiente de confirmar: revisión del pedido y pago simulado.
- Permitir avanzar y retroceder sin perder los datos durante el flujo.
- Validar los campos obligatorios antes de avanzar y mostrar errores comprensibles.
- Finalizar con una confirmación simulada; no efectuar cargos reales.

El enunciado recibido está incompleto a partir de "Datos personales". Los campos y requisitos definitivos del checkout deben confirmarse antes de implementarlo.

## Comportamiento compartido

- Mantener navbar y footer consistentes en las cinco vistas, con un menú adaptado a móvil.
- Usar los mismos identificadores, nombres, tallas, imágenes y precios en todo el recorrido.
- Identificar cada línea del carrito por producto y talla; sumar cantidades al repetir la misma combinación.
- Propuesta: persistir el carrito con `localStorage` e introducir los tres ejemplos únicamente cuando no exista un carrito guardado, sin repoblar uno que el usuario haya vaciado.
- Definir moneda, impuestos y gastos de envío antes de implementar los cálculos; no asumir valores definitivos.
- Determinar si los precios incluyen impuestos para evitar cobrarlos dos veces.
- Propuesta: la búsqueda de la navbar conduce al catálogo y filtra por nombre.
- El alcance del menú de cuenta queda pendiente; no simular una autenticación real.

## Diseño, SEO y accesibilidad

- Definir una identidad compartida: colores, tipografía, espaciados y estados de controles.
- Priorizar imágenes claras de las prendas y contenido legible en todos los tamaños.
- Usar estructura semántica con `header`, `nav`, `main`, secciones y `footer`.
- Incluir un título y una descripción únicos por página, un H1 descriptivo y encabezados ordenados.
- Declarar el idioma del documento y usar enlaces con destinos y textos descriptivos.
- Añadir texto alternativo a imágenes informativas y dimensiones para reducir saltos de contenido.
- Asociar etiquetas a los campos, permitir navegación por teclado y mostrar el foco.
- Mantener contraste suficiente y evitar que la información dependa solo del color.
- Optimizar las imágenes y cargar de forma diferida las que estén fuera de la vista inicial.

## Colaboración propuesta

- Persona A: Home, catálogo y navbar.
- Persona B: producto, carrito, checkout y footer.
- Acordar primero estilos, datos de producto y formato del carrito compartidos.
- Evitar editar simultáneamente los mismos archivos sin coordinación.
- Usar ramas por funcionalidad, commits descriptivos y pull requests con revisión de la otra persona.
- Revisar conjuntamente la integración y redistribuir tareas si el esfuerzo queda desequilibrado.

## Criterios de aceptación

- Las cinco vistas son navegables y comparten navbar y footer.
- La Home incluye hero, nuevos lanzamientos y más vendidos.
- El catálogo muestra 20 productos inicialmente y permite filtrar por categoría y talla.
- El detalle permite seleccionar talla, cantidad y agregar el producto al carrito.
- El carrito presenta tres ejemplos inicialmente y recalcula importes al modificarlo.
- El checkout permite completar tres pasos y confirmar una compra simulada.
- El recorrido funciona con teclado y en móvil, tablet y escritorio, sin solapamientos ni desbordamientos de página.
- No hay imágenes rotas, enlaces internos sin destino ni errores de JavaScript durante el recorrido principal.
- Verificar manualmente: Home → catálogo → producto → carrito → checkout → confirmación.
- Revisar también filtros sin resultados, carrito vacío y formularios incompletos.

## Decisiones pendientes

- Confirmar la marca, el idioma, los textos y los recursos gráficos autorizados.
- Obtener el enunciado completo de los pasos y campos del checkout.
- Acordar moneda, impuestos, precios con o sin impuestos y gastos de envío.
- Confirmar el alcance de búsqueda, cuenta y destinos de los enlaces legales.
- Elegir cómo mantener navbar y footer compartidos sin inconsistencias entre páginas.
- Confirmar las propuestas de interacción y persistencia antes de desarrollarlas.