# CLAUDE.md

## Proyecto

Invitación romántica a un almuerzo, en español. Un solo archivo `index.html` (HTML, CSS y JS vanilla), sin build ni dependencias. Solo carga tipografías de Google Fonts (Bodoni Moda, Jost). Concepto: "una mesa para dos a la luz de las velas" (vino, dorado, marfil, rosa).

## Desarrollo

- Abrir `index.html` en el navegador o con cualquier servidor estático.
- Personalización: objeto `CONFIG` al inicio del `<script>` (nombre, mensaje, fecha, `fechaISO`, hora, lugar, menú, bebidas, platos, fotos, `whatsapp`).
- Fotos en `images/` (ver `INSTRUCCIONES_FOTOS.md`); si falta una, se muestra un marco vacío.
- Si `CONFIG.whatsapp` tiene número (con indicativo, sin `+`), al confirmar se abre WhatsApp con la respuesta prellenada.

## Arquitectura

Flujo: intro (`#intro`, vela) → clic → `abrir()` enciende la vela, arranca la música y arma la mesa SVG (`#mesa.armada`, elementos `.pop` con retraso `--d`) → secciones con aparición por scroll (`.reveal` + IntersectionObserver) → mensaje, galería de polaroids, detalles, RSVP.

- **Música:** sintetizada con WebAudio (arpegio sobre Am7–Fmaj7–Cmaj7–G6, eco y filtro). Solo puede iniciar tras un gesto del usuario, por eso arranca al tocar la vela. Botón `#musica` para silenciar.
- **"No":** huye del cursor 4 veces y luego abre un modal.
- **Accesibilidad:** `prefers-reduced-motion` omite animaciones y el botón que huye; todo pasa por `esperar()`.
