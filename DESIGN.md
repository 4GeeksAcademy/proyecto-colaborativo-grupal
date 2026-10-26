# Diseño del prototipo

## Alcance y dirección visual

Guía visual basada en [Context.md](Context.md) y [AGENTS.md](AGENTS.md). Documenta la propuesta de diseño; no representa una interfaz implementada ni una identidad de marca confirmada.

- Estética editorial de moda: fotografía protagonista, fondos claros y controles discretos.
- Priorizar las prendas, la legibilidad y un recorrido de compra sencillo.
- Evitar sombras decorativas, degradados y contenedores innecesarios.
- Mantener pendientes la marca, el idioma definitivo y los recursos gráficos autorizados.

## Colores

| Uso | Color | Aplicación |
| --- | --- | --- |
| Fondo principal | `#FAFAF8` | Páginas y espacios de descanso |
| Texto principal | `#202020` | Títulos, navegación y contenido |
| Texto secundario | `#595959` | Referencias y descripciones |
| Acento | `#A3293D` | Acciones principales y selección |
| Fondo secundario | `#EEF1ED` | Resumen del pedido y bandas informativas |
| Bordes | `#D6D6D2` | Separadores y límites decorativos |
| Blanco | `#FFFFFF` | Texto de botones principales |

- Botón principal: fondo de acento y texto blanco; hover con fondo `#842033`.
- Botón secundario: fondo transparente, texto y borde oscuros.
- Campos y controles deben tener límites distinguibles; usar un borde más oscuro cuando sea necesario para su contraste.
- Mostrar selección, errores y confirmaciones con texto o símbolos además del color.
- Verificar el contraste de las combinaciones finales, incluidos foco y estados interactivos.

## Tipografía

| Uso | Fuente propuesta | Tamaño |
| --- | --- | --- |
| Títulos principales | Bodoni Moda, serif | 48 px en escritorio; 32 px en móvil |
| Títulos de sección | Bodoni Moda, serif | 28 px |
| Navegación, contenido y controles | Manrope, sans-serif | 16 px |

- Usar fuentes alternativas de su misma familia si las propuestas no cargan.
- Mantener interlineado aproximado de 1.2 en títulos y 1.5 en contenido.
- Usar tamaños discretos según el espacio disponible, sin escalar la fuente con el ancho del viewport.
- Mantener el espaciado entre letras en cero y reservar las mayúsculas para etiquetas breves.
- Permitir saltos de línea sin recortes ni solapamientos.

## Layout y componentes comunes

- Ancho máximo del contenido: 1280 px; márgenes laterales de 24 px en escritorio y 16 px en móvil.
- Espaciado basado en múltiplos de 8 px y bordes redondeados de 4 px.
- Navbar y footer consistentes en las cinco vistas.
- Navbar con logo, búsqueda, menú de cuenta y acceso al carrito; menú compacto en móvil.
- Footer con calzado, camisas, pantalones, accesorios, información legal, sobre la marca y contacto.
- Fotografías de producto en proporción 3:4, con encuadre consistente y prendas claramente visibles.
- Tarjetas de producto sin marco decorativo: fotografía, nombre y precio.
- Usar iconos reconocibles para herramientas, con nombre accesible y ayuda al pasar el cursor cuando corresponda.
- Mantener dimensiones estables para imágenes, controles y botones; las etiquetas no deben desplazar el layout.
- No encerrar secciones completas en tarjetas ni anidar tarjetas decorativas.

## Layout por vista

### Home
- Hero fotográfico a todo el ancho con un título literal de categoría o la marca, cuando se confirme.
- Colocar texto y enlace al catálogo sobre una zona legible de la imagen, sin contenedor decorativo.
- Ajustar la altura para dejar visible el comienzo de la siguiente sección.
- Mostrar nuevos lanzamientos y más vendidos en dos listados horizontales accesibles.

### Catálogo
- Encabezado compacto, filtros de categoría y talla, contador de resultados y opción para restablecer filtros.
- Mostrar inicialmente 20 productos en cuatro columnas y cinco filas en escritorio.
- Incluir estados de filtros seleccionados y sin resultados.

### Producto
- Dos columnas equilibradas: imagen a la izquierda e información a la derecha.
- Mostrar nombre, referencia, precio, talla, cantidad y botón "Agregar al carrito".
- Usar un selector de talla y un control numérico de cantidad con etiquetas claras.
- Mostrar confirmación de añadido y errores junto a los controles correspondientes.
- Colocar materiales y usos recomendados debajo del bloque principal.

### Carrito
- Página completa: listado de productos a la izquierda y resumen del pedido a la derecha.
- Presentar tres productos iniciales de ejemplo con miniatura, precio unitario, cantidad y total por producto.
- Ofrecer modificación de cantidades y eliminación; mostrar subtotal, impuestos, total y botón "Comprar".
- Prever un estado vacío con enlace al catálogo.
- No fijar moneda, tipos impositivos ni gastos de envío hasta confirmarlos.

### Checkout
- Indicador de tres pasos, formulario principal y resumen lateral del pedido.
- Diseñar el primer paso para datos personales, con etiquetas permanentes y errores comprensibles.
- Mantener los campos concretos y los pasos 2 y 3 pendientes de confirmar según el enunciado completo.
- Prever navegación entre pasos y confirmación simulada, sin solicitar datos bancarios reales.

## Responsive y accesibilidad

- Escritorio: navegación completa, catálogo de cuatro columnas y compra en dos columnas.
- Tablet: catálogo de dos columnas; desplazar el resumen debajo si no cabe con claridad.
- Móvil: menú compacto, búsqueda accesible y contenido apilado; catálogo de dos columnas y una en pantallas estrechas.
- Adaptar los cambios de layout al contenido, sin permitir desbordamiento horizontal de la página.
- Usar objetivos táctiles de al menos 44 por 44 px y foco visible en todos los controles.
- Permitir navegación por teclado, asociar etiquetas a campos y no depender solo del color.
- Usar imágenes autorizadas con texto alternativo y dimensiones definidas; evitar recortes que oculten detalles esenciales.

## Validación prevista

- Revisar móvil, tablet y escritorio; comprobar que texto, imágenes y controles no se solapen.
- Verificar contraste, foco, teclado, estados de filtros, carrito vacío y errores de formulario.
- Comprobar consistencia de navbar, footer y componentes entre las cinco vistas.
- Validar el recorrido Home → catálogo → producto → carrito → checkout cuando esté implementado.
- Estas comprobaciones son criterios futuros, no verificaciones ya ejecutadas sobre una interfaz.