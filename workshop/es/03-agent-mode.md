<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Agent Mode — Construir el Juego

---

Agent Mode permite a Copilot planificar e implementar cambios de forma autónoma en múltiples archivos. En lugar de escribir código línea por línea, describes lo que quieres y Copilot determina qué archivos crear o modificar, luego implementa todo de principio a fin.

## Tarea 1: Conecta la batalla

<!-- track:vscode:start -->
1. Cambia a modo **Agent** en Copilot Chat (selecciona "Agent" en el menú desplegable de modo).

2. Escribe este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Devuelve Copilot CLI al flujo normal de programación (o continúa en autopilot si quieres que siga trabajando hasta que lo detengas).
2. Si te sirve, menciona el archivo de la página para dar más contexto: `@src/pages/index.astro`.
3. Escribe este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   > 9. Simple UI for now that is already scaffolded.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deja que Agent Mode trabaje en la implementación a través de `index.astro`. Observa cómo planifica su enfoque, identifica los archivos que necesita modificar y escribe el código.

4. Revisa los cambios propuestos en la vista de diferencias antes de aceptarlos.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deja que Copilot CLI implemente los cambios en `src/pages/index.astro`.
5. Inspecciona los cambios generados con `/diff` y apruébalos.
<!-- track:cli:end -->

## Tarea 2: Prueba la Batalla

1. Introduce `octocat` y `torvalds` como nombres de usuario y haz clic en **Battle**.
2. Deberías ver ambos gráficos de contribuciones renderizados lado a lado con cuadrículas de colores.
3. Prueba los casos de error:
   - Deja uno o ambos campos vacíos y haz clic en Battle — deberías ver un error de validación.
   - Introduce un nombre de usuario no válido; la aplicación debería mostrar un error de la API.
4. Prueba presionar **Enter** en cualquier campo de entrada — debería activar la batalla igual que al hacer clic en el botón.

## Tarea 3: Itera con Agent

Si algo no está del todo bien, dale retroalimentación a Agent directamente en el chat. Por ejemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
Agent Mode maneja de forma natural los cambios en varios archivos y las iteraciones. Cada prompt de seguimiento se basa en la conversación, así que puedes refinar la implementación de manera incremental sin empezar de cero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Las sesiones de Copilot CLI conservan el historial, así que cada prompt de seguimiento se apoya en el anterior. Usa `/session` o `/context` para inspeccionar el contexto que Copilot mantiene y `/review` después de una iteración grande para buscar errores o mejoras.
<!-- track:cli:end -->

## Consejos para esta parte

- **Sé específico sobre lo que quieres** — requisitos claros producen mejores resultados.
- **Divide las tareas grandes en prompts más pequeños** si Copilot se desvía.
- **Revisa los cambios antes de aceptar** — usa la vista de diferencias para entender qué se modificó.
- **Prueba la aplicación después de cada implementación** para detectar los problemas cuanto antes.

## ✅ Parte 3 Completa

Has aprendido a:

- Usar **Agent Mode** para implementaciones complejas en múltiples archivos
- **Iterar sobre los resultados** con retroalimentación dirigida
- Manejar el **ciclo de vida completo de una funcionalidad** — desde la implementación hasta las pruebas y el refinamiento — en una sola conversación
