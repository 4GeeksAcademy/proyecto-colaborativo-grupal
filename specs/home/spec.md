# Especificación: página Home

## Objetivo

Definir el contenido, comportamiento y criterios de aceptación de la Home de la tienda. La implementación futura será `index.html`, servido en `/` por `server.py`.

Fuentes: [Context.md](../../Context.md), [DESIGN.md](../../DESIGN.md) y [docs/reference/base.html](../../docs/reference/base.html).

## Alcance

La página incluirá:

- Navbar con identidad provisional, búsqueda, menú de cuenta y acceso al carrito.
- Hero promocional.
- Listados horizontales de «Nuevos lanzamientos» y «Más vendidos».
- Footer con categorías, información legal, información sobre la marca y contacto.

Esta especificación define la estructura y los reemplazos de contenido; no implementa servicios comerciales reales.

## Decisiones provisionales

- Usar español y «Marca» como identidad provisional.
- Mantener `index.html` como HTML estático con contenido principal presente en el documento, sin Jinja ni carga de datos desde JavaScript.
- Usar las rutas acordadas para las vistas compartidas: `/`, `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`.
- Usar textos, productos y precios demostrativos claramente provisionales. No asumir precios definitivos, moneda, campaña real ni información de contacto.
- Usar placeholders locales válidos mientras no haya recursos comerciales autorizados.
- Mantener la búsqueda y el menú de cuenta inactivos; no implementar búsqueda funcional, autenticación ni backend.
- Repetir de forma consistente el markup de navbar y footer de la plantilla. No introducir una arquitectura de componentes compartidos en esta fase.
- Enlazar CTA del hero al catálogo y tarjetas de producto a la vista de producto de demostración.
- No crear destinos ficticios para categorías, legal o contacto; mientras no existan páginas, presentarlos como texto no interactivo.

## Archivos reemplazables

Mantener rutas y nombres de archivo estables para que se pueda cambiar el contenido sin editar el HTML. Los placeholders deben existir y ser recursos válidos, no referencias rotas.

| Ruta | Uso | Reemplazo esperado |
|---|---|---|
| `assets/home/brand-logo.svg` | Identidad de navbar y footer | Logo autorizado de la marca |
| `assets/home/hero-campaign.png` | Imagen principal del hero | Fotografía autorizada de campaña o producto especial |
| `assets/home/new-arrivals/product-01.png` a `product-05.png` | Imágenes de nuevos lanzamientos | Fotografías autorizadas de los productos correspondientes |
| `assets/home/best-sellers/product-01.png` a `product-05.png` | Imágenes de más vendidos | Fotografías autorizadas de los productos correspondientes |

Los placeholders de producto serán PNG de 600 × 800 px (proporción 3:4). El placeholder del hero será PNG de 1600 × 720 px. Al cambiar una imagen se conservarán la ruta y la proporción esperada; si el formato o proporción cambia, se actualizará también esta especificación.

## Contenido reemplazable en `index.html`

Añadir comentarios `REEMPLAZAR:` junto a los valores provisionales para identificar lo que debe actualizarse:

- Nombre de marca y texto alternativo del logo.
- Título y descripción SEO de la Home.
- Texto, imagen, texto alternativo y CTA del hero.
- Nombres, imágenes, textos alternativos y precios de productos.
- Moneda y formato de precios, una vez confirmados.
- Datos de contacto y destinos de navegación, una vez confirmados.

Los comentarios son orientativos para quien edite el archivo y no deben aparecer en la interfaz. Mientras falten datos, usar textos visibles como «Campaña pendiente» o «Precio pendiente», sin tokens técnicos ni contenido comercial inventado.

## Navbar

- Mostrar logo provisional enlazado a `/`.
- Incluir búsqueda con etiqueta accesible; permanecerá deshabilitada hasta que se acuerde su comportamiento.
- Incluir las cinco rutas comunes y marcar Inicio con `aria-current="page"`.
- Incluir un menú de cuenta que identifique las opciones pendientes, sin simular inicio de sesión.
- Conservar el acceso al carrito de la plantilla, inactivo hasta que exista su vista.
- Adaptar la navegación a móvil sin recortes ni desbordamiento horizontal.
- Mantener objetivos táctiles de al menos 44 × 44 px y foco visible.

## Hero

- Destacar productos especiales o una campaña mediante imagen autorizada o placeholder temporal.
- Incluir un único H1 descriptivo y texto demostrativo, sin afirmar campañas comerciales reales.
- Enlazar el CTA a `/catalogo.html`.
- Mantener el texto legible sobre la imagen, sin tarjeta decorativa superpuesta.
- Definir dimensiones estables para la imagen y texto alternativo cuando sea informativa.
- En móvil y escritorio debe quedar visible el comienzo de la sección siguiente en la primera pantalla.

## Listados de productos

Habrá dos secciones independientes: «Nuevos lanzamientos» y «Más vendidos».

Cada sección deberá:

- Mostrar cinco productos de demostración para que el desplazamiento sea comprobable.
- Usar tarjetas sin marco decorativo, con imagen 3:4, nombre y precio provisional.
- Enlazar cada tarjeta a `/producto.html`, que presenta un producto de demostración.
- Permitir desplazamiento táctil y mediante controles anterior/siguiente.
- Dar a cada control un nombre accesible asociado con su sección; identificar el listado controlado y deshabilitar el control correspondiente al llegar a cada extremo.
- Permitir operar los controles con teclado y mantener el foco visible.
- Evitar que el desplazamiento de la lista provoque desbordamiento horizontal de la página.

No habrá reproducción automática ni animación automática.

## Footer

Incluir los siguientes grupos:

- **Categorías:** calzado, camisas, pantalones y accesorios.
- **Legal:** términos y condiciones, política de privacidad y sobre la marca.
- **Contacto:** sin inventar correo, dirección ni datos de empresa.

Los elementos sin destino confirmado se mostrarán inactivos, no como enlaces vacíos. El footer deberá apilar sus grupos en pantallas estrechas.

## Diseño, responsive y accesibilidad

- Seguir la dirección visual propuesta en `DESIGN.md`: Bodoni Moda para títulos, Manrope para contenido, paleta clara con acento rojo y ancho máximo de 1280 px.
- Usar márgenes laterales de 16 px en móvil y 24 px en escritorio.
- Mantener foco visible, contraste suficiente y jerarquía correcta de encabezados.
- Declarar `lang="es"`, proporcionar título y descripción únicos, y mantener el contenido principal en HTML indexable.
- No aplicar `noindex,nofollow` a la Home pública.
- Cargar prioritariamente la imagen principal y diferir las imágenes de producto fuera de la vista inicial.
- No ocultar información al cambiar de tamaño ni depender solo del color para comunicar estados.

## Criterios de aceptación

1. `python3 server.py` sirve la Home en `http://localhost:3000/` y las otras cuatro rutas comunes.
2. La página contiene un único H1, navbar, hero, las dos secciones de producto y footer.
3. Navbar, CTA y tarjetas enlazan a las rutas acordadas; los listados se desplazan con teclado, puntero y gestos táctiles.
4. Navbar, hero, listados y footer se adaptan a móvil, tablet y escritorio sin recortes, solapamientos ni overflow horizontal.
5. Las imágenes cargan, tienen dimensiones definidas y texto alternativo apropiado.
6. Los placeholders referenciados existen en las rutas documentadas y pueden sustituirse conservando rutas y proporciones.
7. La página tiene idioma, título y descripción propios; no contiene enlaces vacíos ni errores de JavaScript en consola.
8. Los valores provisionales están identificados y no presentan marca, precios, moneda, campaña ni contacto como información real.

## Fuera de alcance

- Marca, logo, campaña, productos, precios, moneda e imágenes comerciales definitivos.
- Búsqueda funcional, autenticación, catálogo, carrito operativo, backend, pagos y persistencia.
- Destinos definitivos para categorías, enlaces legales y contacto.
- Definir una estrategia común de componentes para las cinco vistas.