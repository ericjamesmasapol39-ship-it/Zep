<!-- l10n-sync: source-file="02-plan-and-scaffold.md" -->
# Parte 2: Planificar y Estructurar

---

Antes de escribir código, usemos **Plan Mode** para pensar en la arquitectura. Planificar primero te ayuda a diseñar mejores sistemas y le da a Copilot el contexto que necesita para generar código de mayor calidad.

## Tarea 1: Planifica la Arquitectura de la API

<!-- track:vscode:start -->
1. Cambia a modo **Plan** en Copilot Chat (haz clic en el selector de modo en la parte inferior del panel de chat).
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Entra en **plan mode** en Copilot CLI pulsando **Shift+Tab** hasta que cambie el modo o ejecutando `/plan`.
<!-- track:cli:end -->

2. Escribe este prompt:

   ```
   I need to build a server-side API proxy that fetches GitHub contribution data
   for any username. The endpoint is https://github.com/{username}.contribs which
   returns JSON. We need to bypass CORS restrictions. Plan the implementation
   including the route structure, error handling, and caching strategy.
   ```

3. **Revisa el plan** — aquí es donde Plan Mode brilla. No aceptes la primera respuesta sin más:
   - Pide aclaraciones sobre cualquier cosa que no esté clara
   - Sugiere cambios si algo no te convence
   - Itera hasta que estés satisfecho con el enfoque

<!-- track:vscode:start -->
4. Cuando estés satisfecho con el plan, pide a Copilot que lo implemente: cambia a modo **Agent** y dile que proceda.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Cuando estés satisfecho con el plan, pide a Copilot CLI que lo implemente.
5. Revisa las ediciones resultantes con `/diff` antes de aprobarlas.
<!-- track:cli:end -->

6. **Resultado:** Ahora deberías tener una ruta de API creada en:
   ```
   src/pages/api/contributions/[username].ts
   ```

## Tarea 2: Prueba la API

> **⚠️ ¿No ves los cambios?** Si el servidor de desarrollo no detecta la nueva ruta, detenlo (`Ctrl+C`) y vuelve a iniciarlo con `npm run dev`.

1. Asegúrate de que tu servidor de desarrollo esté en ejecución y prueba el endpoint:

   ```bash
   curl http://localhost:4321/api/contributions/octocat
   ```

2. Deberías ver datos de contribuciones en formato JSON.

3. Prueba también el caso de error: intenta con un nombre de usuario no válido y confirma que devuelve una respuesta adecuada.

## Tarea 3: Planifica la Página de Batalla

<!-- track:vscode:start -->
1. Mantente en modo **Plan** y escribe este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Mantente en plan mode (o ejecuta `/plan`) y escribe este prompt:
<!-- track:cli:end -->

   ```
   Now I need the main page. Plan a battle page for "Mona Mayhem - GitHub
   Contribution Battle Arena" with: two username inputs (Player 1 and Player 2),
   a battle button, and a results area. Keep the UI simple — don't over-engineer
   the layout or styling at this stage. Plan the HTML structure, basic styling,
   and how the battle interaction will work.
   ```

2. **Revisa e itera** sobre el plan — haz preguntas, sugiere cambios, refina el enfoque

<!-- track:vscode:start -->
3. Cuando estés satisfecho, cambia a modo **Agent** y deja que Copilot construya la página
<!-- track:vscode:end -->

<!-- track:cli:start -->
3. Cuando estés satisfecho, pide a Copilot CLI que implemente el plan aprobado.
4. Vuelve a usar `/diff` para inspeccionar el esqueleto HTML y CSS antes de aprobarlo.
<!-- track:cli:end -->

## Tarea 4: Verifica la Estructura

> **⚠️ ¿No ves los cambios?** Si la página no se ve bien o no se ha actualizado, detén el servidor de desarrollo (`Ctrl+C`), vuelve a iniciarlo con `npm run dev` y actualiza el navegador.

1. Abre http://localhost:4321 en tu navegador.

2. Deberías ver:
   - El título del juego
   - Dos campos de entrada para nombres de usuario (Player 1 y Player 2)
   - Un botón de batalla

3. El botón aún no funcionará; ¡es lo esperado! Todavía no hemos conectado la lógica de interacción. Eso viene después.

---

## ✅ ¡Parte 2 Completa!

Has aprendido a:

- **Usar Plan Mode** para diseñar la arquitectura antes de escribir código
- **Iterar sobre los planes** — hacer preguntas y refinar antes de implementar
- **Alternar entre Plan Mode y Agent Mode** para pasar del diseño a la implementación
