<!-- l10n-sync: source-file="README.md" -->
🌐 [English](README.md) | Español | [Português (Brasil)](README.pt_BR.md) | [한국어](README.ko.md)

# 🎮 Mona Mayhem

**Taller de VS Code y GitHub Copilot CLI** — Construye una arena de batalla de contribuciones de GitHub

Plantilla de taller para crear con Astro un sitio web con estética de arcade retro que compara los gráficos de contribuciones de GitHub de dos usuarios. Este es el **punto de partida**: crearás la aplicación paso a paso con GitHub Copilot.

![Captura de pantalla de Mona Mayhem](https://github.com/user-attachments/assets/5eca79e2-cb9f-4e93-aa0d-23666ebde3b7)
*Esto es lo que habrás creado al terminar el taller.*

## 📚 Taller

El taller ofrece dos recorridos; sigue el que mejor se adapte a tu forma de trabajar:

- **Recorrido de VS Code** — Chat, Plan Mode, Agent Mode, agentes en segundo plano y ciclos de revisión integrados en el editor
- **Recorrido de CLI** — `copilot`, contexto con `@file`, `/plan`, ediciones autónomas, `/fleet`, `/delegate` y `/review`

| Parte | Título | Enfoque de Copilot |
|------|-------|--------------------|
| [00](workshop/es/00-overview.md) | Descripción general | Selección del recorrido y objetivos de aprendizaje |
| [01](workshop/es/01-setup.md) | Configuración e ingeniería de contexto | Instrucciones, permisos y configuración del entorno |
| [02](workshop/es/02-plan-and-scaffold.md) | Planificación y estructura inicial | Planificación de la API y la arquitectura de la página |
| [03](workshop/es/03-agent-mode.md) | Construcción del juego | Implementación agéntica e iteración |
| [04](workshop/es/04-design-vibes.md) | Tematización desde el diseño | Planificación e implementación del diseño visual |
| [05](workshop/es/05-polish.md) | Pulido y trabajo paralelo | Paralelismo, revisiones y controles de calidad |
| [06](workshop/es/06-bonus.md) | Bonus y extensiones | Ideas de funcionalidades abiertas y experimentos adicionales con Copilot |

## 🚀 Inicio rápido

1. **Crea primero tu propio repositorio**:
   - haz clic en **Use this template** para crear un repositorio, o
   - crea un fork de este repositorio.
2. Elige el recorrido del taller:
   - **VS Code:** clona tu repositorio y ábrelo en VS Code.
   - **GitHub Copilot CLI:** clona tu repositorio localmente, instala `copilot` y trabaja desde la terminal.
3. Sigue la [guía del taller](workshop/es/00-overview.md).

## Requisitos previos

### Comunes

- GitHub Copilot (Pro, Business o Enterprise)
- Git
- Node.js

### Recorrido de VS Code

- VS Code v1.107+
- Sesión iniciada en la extensión GitHub Copilot

### Recorrido de CLI

- GitHub Copilot CLI (`copilot`)
- Node.js 22+ si piensas instalar el CLI con `npm install -g @github/copilot`
- También puedes instalarlo con Homebrew o WinGet

## Tecnologías

- **Framework**: [Astro](https://astro.build/) v6
- **Runtime**: Node.js con el adaptador [@astrojs/node](https://docs.astro.build/en/guides/integrations-guide/node/)
- **Fuente**: Press Start 2P (fuente de videojuegos retro)
- **API**: API del gráfico de contribuciones de GitHub

## Notas de implementación

### Configuración actual de GitHub Pages

El workflow de `.github/workflows/deploy.yml` implementa actualmente el contenido estático del taller y la documentación de `docs/` y `workshop/` en GitHub Pages. No compila ni implementa la aplicación Astro de `src/`.

### Si quieres implementar la aplicación Astro en GitHub Pages

GitHub Pages es un servicio de alojamiento estático, por lo que la aplicación Astro debe generar archivos estáticos.

1. Cambia `output` de `server` a `static` en `astro.config.mjs`.
2. Elimina el adaptador de Node (`@astrojs/node`) de `astro.config.mjs` y `package.json`.
3. Actualiza el workflow de GitHub Actions para ejecutar `npm ci` y `npm run build`, y luego subir `dist/` como artefacto de Pages.
4. Si implementas en una página de proyecto (`https://<user>.github.io/<repo>/`), configura `site` y `base` en `astro.config.mjs`.

Si quieres mantener las rutas de API en producción, usa una plataforma de servidor en lugar de GitHub Pages (por ejemplo, Vercel, Netlify o un servidor Node).

## Licencia

MIT
