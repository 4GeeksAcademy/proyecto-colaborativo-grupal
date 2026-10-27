# Instrucciones del proyecto

## Proyecto
- Prototipo de tienda de ropa para una marca con sede en Francia, desarrollado por dos personas.
- Cinco vistas requeridas: Home, catálogo, producto, carrito y checkout; con SEO y diseño responsive.
- Consultar [Context.md](Context.md) para requisitos detallados y decisiones pendientes.

## Stack y estructura
- Existe una plantilla con documentación, `learn.json` y un servidor de archivos con Flask en `server.py`.
- Frontend: HTML semántico, Tailwind CSS v4 mediante CDN y JavaScript. Home existe en `index.html`; catálogo, producto, carrito y checkout quedan pendientes.
- No asumir carpetas, dependencias ni herramientas adicionales.

## Comandos
- Comando documentado en [README.es.md](README.es.md): `pip3 install flask && python3 server.py`.
- El servidor está configurado en `http://localhost:3000` y sirve `index.html` en `/`.
- La navbar reserva `/catalogo.html`, `/producto.html`, `/carrito.html` y `/checkout.html`; esas vistas todavía no tienen archivos y deben implementarse en una fase posterior.
- No hay comandos de build, lint o pruebas verificados.

## Convenciones
- Mantener cambios mínimos y respetar el estilo existente.
- Usar HTML semántico, controles accesibles y estilos consistentes entre vistas.
- Mantener navbar y footer comunes; no imponer una arquitectura sin acordarla.

## Reglas de dominio
- Catálogo inicial: 20 productos, en una rejilla de cuatro columnas y cinco filas en escritorio.
- Carrito de página completa con tres productos de ejemplo; mostrar cantidades, subtotal, impuestos y total.
- Checkout de tres pasos: solo está confirmado el primero, datos personales; confirmar los otros dos.
- No asumir marca, idioma, moneda, impuestos ni gastos de envío.
- Persistencia, comportamiento de búsqueda y reparto de tareas siguen siendo propuestas.

## Forma de trabajar
- Presentar un plan breve antes de tareas no triviales y trabajar una fase por vez.
- Leer solo lo necesario, preservar cambios ajenos y confirmar decisiones pendientes antes de implementarlas.
- Informar brevemente de los cambios y las verificaciones realizadas.

## Limites
- No incorporar backend comercial, autenticación ni pagos reales; no solicitar datos bancarios reales.
- No ampliar alcance ni cambiar de stack sin autorización.
- No crear pruebas nuevas salvo petición explícita.
- No hacer commits, crear ramas ni realizar operaciones destructivas sin solicitud.
- Ante un error persistente, detenerse tras dos intentos de corrección e informar.

## Verificacion
- Ejecutar solo comprobaciones pertinentes al cambio; no repetir suites completas.
- Para las vistas, revisar navegación, filtros, carrito, formularios, teclado y adaptación a móvil, tablet y escritorio.
- Para documentación, comprobar estructura, enlaces y correspondencia con lo verificado; no iniciar el servidor solo para ello.
- Distinguir siempre requisitos, propuestas y comportamiento implementado; no afirmar verificaciones no ejecutadas.