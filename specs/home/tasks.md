# Tareas: página Home

Basadas en [spec.md](spec.md), [plan.md](plan.md), [Context.md](../../Context.md) y [DESIGN.md](../../DESIGN.md). Esta lista registra el trabajo futuro; todavía no se ha implementado la Home.

## Preparación

- [x] Revisar los requisitos de Home y la plantilla visual existente.
- [x] Confirmar español y «Marca» como identidad provisional.
- [x] Confirmar el uso de datos demostrativos, controles de desplazamiento y markup consistente repetido.
- [x] Confirmar placeholders estáticos en HTML, sin Jinja ni datos cargados por JavaScript.
- [x] Confirmar las rutas previstas de navbar: `/`, `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`.
- [x] Crear placeholders PNG locales válidos y logo SVG bajo `assets/home/`, con nombres, dimensiones y proporciones documentados en [spec.md](spec.md).
- [x] Preparar contenido demostrativo para el hero y cinco productos por lista, sin fijar una moneda definitiva.

## Estructura y navbar

- [x] Crear `index.html` con estructura semántica y metadatos propios de Home.
- [x] Añadir `lang="es"`, título y descripción únicos; no marcar la Home como `noindex,nofollow`.
- [x] Cargar Tailwind CSS v4 y recursos siguiendo `docs/reference/base.html`.
- [x] Añadir comentarios `REEMPLAZAR:` a los textos y valores provisionales, sin mostrar tokens técnicos en la interfaz.
- [x] Añadir enlace de salto al contenido y un único `main` con H1 descriptivo.
- [x] Incorporar navbar con logo, las cinco rutas comunes, búsqueda y cuenta inactivas.
- [x] Implementar el layout responsive de navegación móvil siguiendo la plantilla.

## Hero

- [x] Añadir imagen de campaña reemplazable en `assets/home/hero-campaign.png`, con dimensiones estables y texto alternativo adecuado.
- [x] Incorporar texto de campaña demostrativo y CTA inactivo hasta que exista `/catalogo.html`.
- [ ] Comprobar legibilidad del texto sobre la imagen y visibilidad del comienzo de la siguiente sección.

## Listados de productos

- [x] Crear «Nuevos lanzamientos» con cinco tarjetas de demostración y rutas de imagen reemplazables.
- [x] Crear «Más vendidos» con cinco tarjetas de demostración y rutas de imagen reemplazables.
- [x] Mantener las tarjetas sin enlace hasta que exista `/producto.html`.
- [x] Mantener tarjetas sin marco decorativo, con imagen 3:4, nombre y precio provisional.
- [x] Añadir desplazamiento horizontal nativo a ambos listados.
- [x] Añadir controles anterior/siguiente con nombres accesibles y foco visible en cada listado.
- [ ] Comprobar límites de desplazamiento y que los listados no causen overflow horizontal en la página.

## Footer

- [x] Incorporar grupos de categorías: calzado, camisas, pantalones y accesorios.
- [x] Incorporar términos y condiciones, política de privacidad y sobre la marca.
- [x] Añadir sección de contacto sin inventar datos personales o de empresa.
- [x] Mantener sin destino los enlaces que todavía no existan y definir el footer responsive.

## Verificación

- [x] Comprobar que `/` sirve la Home.
- [ ] Comprobar las cuatro rutas restantes después de crear sus páginas.
- [ ] Revisar móvil, tablet y escritorio: hero, secciones, navbar y footer.
- [ ] Navegar con teclado por el enlace de salto, la navbar y los controles de los listados.
- [ ] Comprobar foco visible, nombres accesibles y operación de los controles con teclado y puntero.
- [x] Comprobar respuestas HTTP de las imágenes y validar estáticamente textos alternativos, enlaces, metadatos, H1 e IDs.
- [ ] Revisar la consola del navegador y confirmar ausencia de errores JavaScript.
- [ ] Confirmar que no haya texto recortado, solapamientos ni desbordamiento horizontal.
- [x] Registrar las comprobaciones efectivamente realizadas y dejar pendientes las revisiones visuales y de teclado.
