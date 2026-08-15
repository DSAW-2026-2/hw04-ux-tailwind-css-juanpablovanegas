# Bitácora de IA

Usamos IA (Claude) para reconstruir el `index.html` de HW03 con clases utilitarias de Tailwind CSS (vía CDN) y para implementar el toggle de modo oscuro con persistencia en `localStorage`.

**Paleta de Tailwind:** la IA sugirió mantener la paleta de grises de Tailwind (`slate`) para fondos y texto, con `pink-600`/`pink-500` como color de acento — para conservar el mismo magenta (`#ff2e88` aproximado) que ya usábamos en el wireframe de Figma del equipo y en el CSS de HW03, en vez de introducir un color nuevo. Lo que cambiamos: en HW03 el fondo oscuro era un morado muy oscuro (`#14121a`) hecho a mano; aquí usamos `slate-900`/`slate-800` de Tailwind porque son los tonos más cercanos disponibles como utilidades, sin tener que definir colores custom en la configuración de Tailwind.

**Qué aprendimos que no habríamos aprendido si la IA hiciera todo:** que el modo oscuro de Tailwind con la estrategia `class` no cambia solo con CSS — hay que agregar/quitar la clase `dark` en `<html>` con JavaScript, y por eso cada color que debe cambiar necesita su par `dark:` explícito en la misma clase (por ejemplo `bg-white dark:bg-slate-900`). No es automático como `prefers-color-scheme` puro; se necesita el script que lee `localStorage` y aplica la clase antes de que la página termine de cargar, para evitar el parpadeo del tema equivocado.
