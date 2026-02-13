---
name: Creador de Habilidades
description: Una guía y herramienta para crear nuevas habilidades en el entorno Antigravity en español.
---

# Creador de Habilidades

Esta habilidad te guía paso a paso para crear tus propias habilidades (skills) personalizadas. Las habilidades son paquetes de instrucciones y herramientas que extienden las capacidades del agente.

## Estructura de una Habilidad

Cada habilidad reside en su propia carpeta dentro de `.agent/skills/`. La estructura básica es la siguiente:

```text
.agent/skills/
└── <nombre_de_la_habilidad>/
    └── SKILL.md  (Obligatorio)
    ├── scripts/  (Opcional: scripts de ayuda)
    ├── examples/ (Opcional: ejemplos de uso)
    └── resources/ (Opcional: plantillas o recursos)
```

## Paso 1: Crear la Carpeta

Crea una carpeta con el nombre de tu habilidad (en minúsculas y guiones bajos preferiblemente) dentro de `.agent/skills/`.

Ejemplo: `.agent/skills/mi_nueva_habilidad/`

## Paso 2: Crear el archivo SKILL.md

Dentro de la carpeta creada, debes crear un archivo llamado `SKILL.md`. Este archivo contiene la definición de la habilidad y sus instrucciones.

El archivo **debe** comenzar con un bloque de metadatos YAML (frontmatter) seguido de las instrucciones en Markdown.

### Formato del SKILL.md

```markdown
---
name: Nombre Legible de la Habilidad
description: Una breve descripción de lo que hace la habilidad.
---

# Título de la Habilidad

Aquí van las instrucciones detalladas de cómo usar la habilidad.
Puedes usar formato Markdown estándar.

## Secciones Recomendadas

- **Propósito**: ¿Para qué sirve esta habilidad?
- **Instrucciones**: Pasos a seguir.
- **Ejemplos**: Cómo invocarla o usarla.

```

## Consejos

1.  **Claridad**: Escribe instrucciones claras y concisas. El agente seguirá estas instrucciones literalmente.
2.  **Contexto**: Si tu habilidad requiere herramientas específicas o contextos, menciónalo.
3.  **Modularidad**: Si la habilidad es muy compleja, considera dividirla o usar scripts de apoyo en la carpeta `scripts/`.

## Ejemplo Práctico

Si quieres crear una habilidad para "Despliegue en Producción", crearías:
`.agent/skills/deploy_prod/SKILL.md`

Con contenido:
```markdown
---
name: Despliegue en Producción
description: Procedimiento para desplegar la aplicación en el servidor de producción.
---

# Despliegue en Producción

Sigue estos pasos para desplegar:
1. Ejecuta los tests: `npm test`
2. Construye el proyecto: `npm run build`
3. ...
```
