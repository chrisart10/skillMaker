---
name: musicstuff-architect
description: "Estándar oficial para el desarrollo del proyecto MusicStuff. Úsalo SIEMPRE que realices cambios en el código (frontend o backend), refactorizaciones o creación de nuevos componentes en MusicStuff. Asegura el cumplimiento de reglas de CSS puro, i18n, seguridad en logs y limpieza de directorios."
---

# MusicStuff Architect Skill

Este skill garantiza que el desarrollo en MusicStuff siga los estándares SOTA 2026 y las reglas específicas definidas por el usuario.

## 🏛️ Directrices de Arquitectura y Entorno
- **Runtime**: Node.js v24.x (LTS/Krypton). Usa `fnm` para gestión.
- **Base de Datos**: MongoDB vía MCP.
- **Componentización**:
  - UI reutilizable en `components/ui/` o `components/common/`.
  - Componentes pequeños, desacoplados y con una sola responsabilidad.
  - No acoplar UI a lógicas de página (`pages/` o `app/**/page`).

## 🎨 Estándares de CSS y Estilos (Estricto)
- **PROHIBIDO**: Estilos inline (`style="..."` en HTML o `style={{...}}` en JSX).
- **Híbrido (Excepción)**: Solo permitido si el objeto se define **fuera** del componente y usa únicamente **tokens** (`styles/theme.js`) o **variables CSS**.
- **Preferencia**: CSS puro (`.css`) o CSS Modules (`.module.css`) co-localizados al componente.
- **Theming**: Variables CSS en `:root`. Cambios de tema vía `[data-theme="dark"]` en el elemento raíz.
- **Animaciones**: Definir SIEMPRE en el archivo CSS del componente.

## 🌍 Internacionalización (i18n)
- **REGLA DE ORO**: NUNCA pases la función `t` como prop a componentes hijos.
- **Flujo**: Traduce las llaves en el componente padre/origen y pasa el string final localizado como prop.
- **Motivo**: Permitir que los scripts de auditoría (`check-i18n-usage.js`) rastreen los literales correctamente.

## 🛡️ Seguridad y Configuración
- **Variables de Entorno**: Leer mediante `getRequiredEnv("KEY")` o `getRequiredEnvInt("KEY")`. Prohibido el uso de defaults silenciosos (`|| "default"`).
- **Logging**:
  - Máximo 1 línea por log.
  - Sin datos sensibles (Passwords, JWT, Cookies, MONGODB_URI).
  - Backend: Usar solo caracteres ASCII (evitar emojis y especiales).

## 🧹 Mantenimiento y Limpieza
- **Refactorización**: Al borrar o mover archivos, elimina siempre las carpetas que queden vacías.
- **Herramientas**: Usa funciones de `scripts/dev-commands.ps1` (ej: `Find-EmptyDirs`).
- **README**: NO sobrescribas ni borres la sección "TODO Notas pendientes". Solo anexa o actualiza en cascada.

## 🚀 Cómo aplicar este skill
1. Lee las instrucciones de `AGENT.md` en la raíz del proyecto para contexto adicional.
2. Antes de entregar cualquier cambio, verifica el cumplimiento de los estilos (no inline) y la arquitectura de componentes.
3. Si el cambio es un refactor, ejecuta la limpieza de directorios vacíos.
