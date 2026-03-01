# Guide de Comandos y Prompts: skillMaker 🛠️

Este archivo sirve como referencia para que sepas qué pedirme y cómo interactuar con el **Arquitecto de skillMaker** de manera eficiente.

## 🔄 Mantenimiento de Documentación
Usa estos comandos para mantener tu fuente de verdad actualizada con Anthropic.

- **Prompt**: "Gemini, actualiza la documentación de Anthropic."
- **Lo que hace**: Ejecuta `git submodule update --remote` para traer los últimos estándares SOTA 2026.

## 🔍 Análisis de Proyectos (Multirepo)
Usa este comando para que audite tus otros proyectos y te proponga skills a medida.

- **Prompt**: "Gemini, analiza mi proyecto [nombre-del-repo] en la carpeta Git y dime qué skills necesito."
- **Lo que hace**: Entro en la carpeta del proyecto, analizo su estructura/código y te propongo una lista de skills universales que fabricaremos aquí en `skillMaker`.

## 📚 Agregar Fuentes de Referencia
Si encuentras otros repositorios o documentación útil (por ejemplo, de OpenAI o herramientas específicas), usa estos comandos.

- **Prompt**: "Gemini, agrega una nueva fuente de referencia desde [URL-del-Repo-GitHub] en la carpeta ./docs-[nombre]."
- **Lo que hace**: Configuro un nuevo Git Submodule para que esa fuente también sea fácil de actualizar en el futuro.

## 🎨 Creación de Skills Universales
Usa estos prompts para iniciar la fabricación de nuevos skills. **Nota**: Cada skill generado incluirá automáticamente su `VALIDATION_REPORT.md`.

- **Prompt**: "Quiero crear un nuevo skill universal llamado [nombre-del-skill] que sirva para [propósito]."
- **Prompt**: "Genera un `SKILL.md` para [tarea] siguiendo el estándar de la carpeta docs-anthropic."
- **Prompt**: "Revisa este skill y asegúrate de que sea compatible con Gemini, Claude y GPT."

## 🚀 Gestión de GitHub
Para asegurar que tu trabajo esté siempre a salvo en la nube.

- **Prompt**: "Sube los últimos cambios a GitHub."
- **Prompt**: "Revisa el estado de mi repositorio y confírmame si todo está sincronizado."

---
> [!TIP]
> Puedes ser tan específico como quieras. Como tu Arquitecto, entiendo el contexto técnico de SOTA 2026 y aplicaré las mejores prácticas automáticamente.
