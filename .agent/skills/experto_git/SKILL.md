---
name: Experto en GitHub y Git
description: Agente experto en control de versiones usando Git y colaboración en GitHub.
---

# Experto en GitHub y Git

Esta habilidad proporciona conocimientos avanzados y flujos de trabajo recomendados para trabajar con Git y GitHub. Úsala cuando necesites realizar operaciones de control de versiones, resolver conflictos, gestionar ramas o entender mejores prácticas.

## Mejores Prácticas de Commit (Conventional Commits)

Utiliza el estándar "Conventional Commits" para mensajes claros y legibles para máquinas:

- `feat: descripción`: Una nueva característica.
- `fix: descripción`: Una corrección de errores.
- `docs: descripción`: Cambios solo en documentación.
- `style: descripción`: Cambios que no afectan el significado del código (espacios, formato, etc).
- `refactor: descripción`: Cambio de código que no arregla un bug ni añade una característica.
- `perf: descripción`: Cambio de código que mejora el rendimiento.
- `test: descripción`: Añadir tests faltantes o corregir existentes.
- `chore: descripción`: Cambios en el proceso de construcción o herramientas auxiliares.

## Estrategia de Ramas (Git Flow Simplificado)

1.  **main/master**: Rama estable y desplegable. No trabajar directamente aquí.
2.  **develop** (opcional): Rama de integración para la próxima versión.
3.  **feature/nombre-feature**: Ramas para nuevas características. Se crean desde `main` o `develop`.
4.  **fix/nombre-bug**: Ramas para corrección de errores.

## Flujos de Trabajo Comunes

### 1. Iniciar una nueva tarea
```bash
git checkout main
git pull origin main
git checkout -b feature/mi-nueva-tarea
```

### 2. Guardar progreso
```bash
git add .
git commit -m "feat: implementar lógica inicial de login"
```

### 3. Sincronizar con el remoto
```bash
git push origin feature/mi-nueva-tarea
```

### 4. Resolver Conflictos
Si al hacer merge o pull hay conflictos:
1.  Git marcará los archivos en conflicto.
2.  Abre los archivos y busca `<<<<<<<`, `=======`, `>>>>>>>`.
3.  Edita el código para dejar la versión final deseada.
4.  `git add <archivo-resuelto>`
5.  `git commit` (sin argumentos para usar el mensaje por defecto de merge).

## Solución de Problemas (Troubleshooting)

### Deshacer el último commit (sin perder cambios)
```bash
git reset --soft HEAD~1
```

### Descartar cambios locales en un archivo
```bash
git checkout -- nombre_archivo
# O en versiones nuevas de git:
git restore nombre_archivo
```

### Modificar el mensaje del último commit
```bash
git commit --amend -m "nuevo mensaje correcto"
```

### Ver el historial de forma gráfica
```bash
git log --graph --oneline --all
```

## Comandos Git Esenciales

| Comando | Descripción |
| :--- | :--- |
| `git status` | Estado actual de archivos modificados/staged. |
| `git diff` | Ver diferencias no commiteadas. |
| `git branch` | Listar ramas. |
| `git checkout <rama>` | Cambiar de rama. |
| `git merge <rama>` | Fusionar `<rama>` en la actual. |
| `git remote -v` | Ver repositorios remotos configurados. |
| `git stash` | Guardar cambios temporalmente. |
| `git stash pop` | Recuperar cambios guardados. |
