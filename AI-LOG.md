# Bitácora de IA

Utilizamos IA para elegir una paleta de colores para CineHub. Se propusieron tonos rosa (pink) para botones y elementos principales, y tonos gris (gray) para fondos y textos. Mantuvimos el rosa porque conserva la identidad visual de CineHub y adaptamos los grises para mejorar la legibilidad en modo claro y oscuro.

**Qué aprendimos que no habríamos aprendido si la IA hiciera todo:** que el modo oscuro de Tailwind con la estrategia `class` no cambia solo con CSS — hay que agregar/quitar la clase `dark` en `<html>` con JavaScript, y por eso cada color que debe cambiar necesita su par `dark:` explícito en la misma clase (por ejemplo `bg-white dark:bg-slate-900`). No es automático como `prefers-color-scheme` puro; se necesita el script que lee `localStorage` y aplica la clase antes de que la página termine de cargar, para evitar el parpadeo del tema equivocado.
