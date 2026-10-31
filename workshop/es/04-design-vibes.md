<!-- l10n-sync: source-file="04-design-vibes.md" -->
# Parte 4: Tematización Orientada al Diseño

---

En esta parte, usarás **Plan Mode** para diseñar una transformación de tema completa, y luego **Agent Mode** para implementarla. Esto es desarrollo orientado al diseño — comienza con la visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia a modo **Plan** en GitHub Copilot.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar plan mode.
<!-- track:cli:end -->

Escribe este prompt:

> I want to transform this page into a full retro arcade experience. Plan a comprehensive visual overhaul that includes: CRT scanline effects on the background, neon glow on the title that pulses like a neon sign, animated VS badge with gradient color shifts, shine/shimmer overlay on the user result cards, float-in animations for input fields, color-shifting loading text between green and purple, and hover glow effects on contribution squares. Keep the dark background (#0a0a1a) with green (#5fed83) and purple (#8a2be2) accent colors. Use a dark theme with the Press Start 2P retro gaming font from Google Fonts.

Copilot generará un plan detallado de implementación cubriendo todos los efectos visuales. **No lo aceptes de inmediato** — revisa el plan e itera:

- Sugiere ajustes en la velocidad de las animaciones (por ejemplo, "Make the neon pulse slower, around 3 seconds")
- Pregunta sobre efectos específicos (por ejemplo, "How will the shimmer overlay work on the cards?")
- Solicita cambios en el enfoque si algo no te convence

Una vez que estés satisfecho con el plan, deja que Copilot proceda con la implementación.

## Tarea 2: Implementa el Tema

Pide a Copilot que implemente el plan:

> Implement the retro arcade theme plan we just designed.

Copilot agregará múltiples animaciones CSS, pseudo-elementos y transiciones en tu hoja de estilos. Esto puede incluir:

- `@keyframes` para scanlines, pulso neón, shimmer y efectos de aparición flotante
- Pseudo-elementos (`::before`, `::after`) para efectos de superposición
- CSS custom properties para los colores del tema
- Transiciones y estados hover para elementos interactivos

Una vez aplicados los cambios, **revisa la vista previa en tu navegador** para ver la transformación completa al estilo retro arcade.

<!-- track:cli:start -->
Después de aplicar los cambios, usa `/diff` para revisar los cambios de estilo antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Ajusta las Vibras

> **⚠️ ¿No ves los cambios?** Si el nuevo tema o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), vuelve a iniciarlo con `npm run dev` y recarga por completo el navegador (`Ctrl+Shift+R`).

Mantén la vista previa del navegador abierta e itera sobre el diseño. Prueba prompts como:

> The scanline effect is too strong, reduce opacity to 0.03

> Add a subtle electrical flicker to the title text

> The VS badge should pulse more dramatically

Esto es **desarrollo orientado al diseño** — estás iterando sobre la salida visual en tiempo real. Cada prompt refina la experiencia hasta que se sienta correcta. No te conformes con "suficientemente bueno" — perfecciona las vibras hasta que la página parezca pertenecer a un gabinete arcade.

## Tarea 4: Actualiza las instrucciones

Las instrucciones de tu workspace deben reflejar las decisiones de diseño importantes. Pídele a Copilot:

<!-- track:vscode:start -->
> Add a design guide section to copilot-instructions.md describing our retro arcade theme: colors, fonts, animation style
<!-- track:vscode:end -->

<!-- track:cli:start -->
> Update our repository instructions with a short design guide for the retro arcade theme: colors, fonts, animation style, and the rule that new UI should keep the neon aesthetic.
<!-- track:cli:end -->

Esto mantiene las interacciones futuras de Copilot alineadas con la identidad visual que has establecido. Cualquier funcionalidad o componente nuevo seguirá la estética retro arcade.

Haz commit de las instrucciones y los cambios de diseño cuando la página tenga el aspecto que quieres.

## ✅ Parte 4 Completa

**Lo que aprendiste:**

- Usar flujos de planificación para definir un **sistema de diseño antes de implementarlo**
- **Iterar sobre la salida visual** — usar prompts rápidos de seguimiento para ajustar animaciones, colores y efectos
- **Mantener las instrucciones actualizadas con decisiones de diseño** — documentar tu tema para que Copilot se mantenga consistente
- **Flujo de trabajo de desarrollo orientado al diseño** — comenzar con la visión, implementar con IA, refinar hasta que se sienta correcto
