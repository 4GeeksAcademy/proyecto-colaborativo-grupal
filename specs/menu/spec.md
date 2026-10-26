# Especificación: menú común

## Objetivo y fuentes

Definir el menú de navegación y de cuenta compartido por Home, catálogo, producto, carrito y checkout.

- Requisitos: [Context.md](../../Context.md), apartados Home y comportamiento compartido.
- Diseño: [DESIGN.md](../../DESIGN.md).
- Base obligatoria: [docs/reference/base.html](../../docs/reference/base.html).
- Forma de trabajo y límites: [AGENTS.md](../../AGENTS.md).

El contexto no define una página independiente llamada "Menú". Esta especificación se refiere a los menús de la navbar y su adaptación a móvil.

## Alcance

- Partir de la navbar de la plantilla base, sin crear otra estructura visual paralela.
- Mantener el logo o identidad, búsqueda, menú de cuenta y acceso al carrito de la base.
- Reutilizar el mismo menú en las cinco vistas.
- Conservar el footer y el `main` vacío de la plantilla de referencia; no añadir contenido de página como parte de esta tarea.
- Mantener Tailwind CSS v4 por CDN, tipografías y recursos existentes, sin introducir frameworks ni herramientas de build.
- Esta entrega solo documenta requisitos; no modifica HTML, estilos ni JavaScript.

## Elementos y comportamiento

### Identidad y navegación
- Mostrar la identidad de marca en la navbar; el rótulo "Marca" sigue siendo provisional.
- Conservar las entradas Inicio y Catálogo presentes en la base; conectar sus destinos cuando se acuerden las rutas.
- Mantener el menú compacto de móvil con las entradas existentes, incluidas calzado, camisas, pantalones y accesorios.
- No presentar enlaces sin destino como navegación funcional ni inventar rutas.

### Búsqueda
- Mantener el campo de búsqueda de la navbar y su etiqueta accesible.
- El contexto propone buscar por nombre desde el catálogo, pero ese comportamiento sigue pendiente de aprobación.
- No activar búsquedas, navegación ni envío de consultas como parte de esta especificación.
- Conservar el control deshabilitado mientras no se defina e implemente su alcance.

### Cuenta y carrito
- Mantener un menú de cuenta desplegable, operable con ratón, tacto y teclado.
- Conservar las opciones provisionales de la base, "Mi cuenta" y "Mis pedidos", deshabilitadas hasta confirmar su alcance.
- No incorporar inicio de sesión, registro, datos personales ni autenticación real.
- Mantener el acceso al carrito de la base deshabilitado hasta que exista un destino acordado.
- No añadir un contador ni persistencia del carrito sin confirmar esa funcionalidad.

## Estados e interacción

- Distinguir los estados cerrado y abierto de los desplegables mediante controles nativos accesibles, como en la base.
- Permitir abrir y cerrar el menú con su control y mediante teclado.
- Escape debe cerrar el desplegable activo y devolver el foco a su control.
- Las opciones pendientes no deben ejecutar acciones ni conducir a páginas inexistentes.
- Al abrirse el menú móvil, el contenido debe permanecer legible, sin desplazamiento horizontal ni solapamientos incoherentes.
- No usar semántica de menú de aplicación para enlaces de navegación ordinarios.

## Diseño y responsive

- Respetar fondo `#FAFAF8`, texto `#202020`, texto secundario `#595959` y acento `#A3293D`.
- Mantener Manrope en navegación y controles, y Bodoni Moda para la identidad provisional.
- Conservar ancho máximo de 1280 px, márgenes laterales de 24 px en escritorio y 16 px en móvil.
- Usar espaciado en múltiplos de 8 px, radios de 4 px y controles de texto de 16 px, sin espaciado adicional entre letras.
- Mostrar navegación completa cuando quepa y menú compacto cuando el espacio lo requiera, siguiendo la distribución de la base.
- La búsqueda debe continuar accesible en móvil y reorganizarse sin ocultar ni recortar otros controles.
- Mantener dimensiones estables de iconos y botones; no añadir decoración ajena a la guía visual.

## Accesibilidad

- Identificar la navegación principal y conservar el enlace de salto al `main`.
- Los controles con iconos deben tener un nombre accesible y ayuda para iconos poco familiares.
- Mantener foco visible, orden de tabulación lógico y objetivos táctiles de al menos 44 por 44 px.
- Comunicar el estado expandido mediante la semántica nativa de los desplegables.
- Mantener etiquetas de formulario; no usar el placeholder como único nombre del campo de búsqueda.
- Comunicar estados pendientes sin depender solo del color ni simular controles operativos.

## Criterios de aceptación y verificación futura

- El menú utiliza la navbar de la plantilla base y respeta la guía de diseño.
- Logo, búsqueda, cuenta y carrito siguen presentes; el footer y el contenido principal no sufren cambios ajenos al alcance.
- La navegación es consistente al reutilizarse en las cinco vistas.
- Los desplegables pueden abrirse y cerrarse con ratón, tacto y teclado; Escape cierra y devuelve el foco.
- No hay enlaces activos sin destino ni servicios pendientes presentados como implementados.
- Revisar móvil, tablet y escritorio: visibilidad, foco, contraste, tamaños táctiles y ausencia de recortes o solapamientos.
- No declarar estas comprobaciones como realizadas hasta ejecutarlas sobre la implementación.
- Para esta entrega documental, comprobar únicamente estructura y referencias, sin iniciar el servidor ni crear pruebas nuevas.

## Decisiones pendientes

- Marca y logo definitivos, idioma definitivo y rutas de navegación.
- Alcance y opciones definitivas del menú de cuenta.
- Comportamiento de búsqueda y conexión real con catálogo y carrito.
- Persistencia y contador del carrito, si finalmente se aprueban.