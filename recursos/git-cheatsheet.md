# Git & GitHub — Cheat Sheet

Referencia rápida de los comandos y conceptos más usados en el curso.

## Glosario

| Término | Qué es | Analogía |
|---------|--------|----------|
| **Repository (repo)** | Carpeta de proyecto rastreada por Git | Tu carpeta de laboratorio, pero con historial completo |
| **Clone** | Copia local de un repositorio remoto | Fotocopiar el cuaderno de alguien para trabajar en tu mesa |
| **Fork** | Copia personal de un repo ajeno en tu cuenta GitHub | Tu propia versión del cuaderno, independiente |
| **Commit** | Instantánea del estado de tus archivos + mensaje | "Guardar partida" en un videojuego |
| **Branch** | Línea paralela de desarrollo | Borrador alternativo sin tocar el original |
| **Merge** | Unir los cambios de una rama a otra | Pasar en limpio el borrador al cuaderno oficial |
| **Pull** | Traer cambios del repositorio remoto al local | Actualizar tu copia con los cambios nuevos |
| **Push** | Enviar tus commits locales al repositorio remoto | Subir tu trabajo a la nube |
| **Pull Request (PR)** | Solicitud para integrar tus cambios al repo original | Pedir al profesor que revise e incorpore tu trabajo |
| **Staging area** | Zona intermedia entre edición y commit | La bandeja de "listo para guardar" |
| **.gitignore** | Archivo que lista lo que Git debe ignorar | "No rastrear estos archivos" |
| **README.md** | Archivo de presentación del proyecto | La portada de tu informe |
| **GitHub Pages** | Sitio web estático generado desde un repo | Publicar tu repo como página web |

## Comandos esenciales

### Configuración inicial (una sola vez)

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### Flujo básico diario

```bash
# Ver estado de los archivos
git status

# Agregar archivos al staging area
git add archivo.md              # un archivo específico
git add .                       # todos los archivos modificados

# Crear un commit (instantánea)
git commit -m "Descripción breve de qué cambié"

# Enviar al repositorio remoto
git push

# Traer cambios del remoto
git pull
```

### Clonar y trabajar con forks

```bash
# Clonar tu fork
git clone https://github.com/TU-USUARIO/omics-2026.git
cd omics-2026

# Conectar con el repositorio original (upstream)
git remote add upstream https://github.com/juancalderongiadrosic/omics-2026.git

# Actualizar tu fork con cambios del original
git fetch upstream
git merge upstream/main
```

### Ramas (branches)

```bash
# Crear y cambiar a una rama nueva
git checkout -b nombre-de-rama

# Cambiar entre ramas
git checkout main
git checkout nombre-de-rama

# Ver ramas existentes
git branch

# Subir rama al remoto
git push -u origin nombre-de-rama
```

### Ver historial

```bash
# Historial de commits
git log --oneline

# Ver cambios no guardados
git diff
```

## Flujo para entregar tareas

```
1. git pull                              # actualizar tu fork
2. (crear/editar archivos de la tarea)
3. git add .                             # agregar cambios
4. git commit -m "Tarea N - Mi Nombre"   # guardar instantánea
5. git push                              # subir a GitHub
6. Ir a GitHub → crear Pull Request      # solicitar revisión
```

## Errores comunes y soluciones

| Problema | Solución |
|----------|----------|
| `fatal: not a git repository` | Estás fuera de la carpeta del repo. Usa `cd omics-2026` |
| `error: failed to push` | Tu fork está desactualizado. Haz `git pull` primero |
| `merge conflict` | Edita el archivo conflictivo, busca `<<<<<<<`, resuelve, y haz commit |
| Subí un archivo que no debía | Agrégalo a `.gitignore` y haz `git rm --cached archivo` |

## Recursos

- [GitHub Docs](https://docs.github.com/es) — documentación oficial en español
- [Git Cheat Sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf) — PDF descargable
- [Oh My Git!](https://ohmygit.org/) — juego para aprender Git
