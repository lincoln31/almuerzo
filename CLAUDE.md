# CLAUDE.md

## Proyecto

Invitación romántica a un almuerzo, en español. Un solo archivo `index.html` (HTML, CSS y JS vanilla), sin build ni dependencias. Solo carga tipografías de Google Fonts (Fraunces, Figtree).

## Desarrollo

- Abrir `index.html` en el navegador o con cualquier servidor estático.
- Personalización: objeto `CONFIG` al inicio del `<script>` (nombre, mensaje, fecha, hora, lugar, menú, opciones de bebida y plato, `whatsapp`).
- Si `CONFIG.whatsapp` tiene un número (con indicativo, sin `+`), al confirmar se abre WhatsApp con la respuesta prellenada; si está vacío, solo se muestra el mensaje de gracias.

## Flujo

Portada → "Sí" (o "Bueno, sí voy" desde el modal del "No") → formulario de bebida/plato/alergias → mensaje de gracias. El botón "No" se escapa del cursor las primeras 4 veces y luego abre un modal.

Respeta `prefers-reduced-motion` (sin animaciones ni botón que huye).
