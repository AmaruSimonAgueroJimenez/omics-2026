# Clase 3 — Ejercicio práctico: Fork, Clone & Pull Request

## Objetivo

Al terminar este ejercicio habrás hecho tu primer **fork**, **clone**, **commit**, **push** y **pull request** en GitHub. Esta será la mecánica que usarás para entregar todas las tareas del curso.

## Requisitos previos

- Cuenta de GitHub creada ([github.com/signup](https://github.com/signup))
- Git instalado en tu computador (ver sección de instalación abajo)
- Acceso al repositorio del curso: `https://github.com/juancalderongiadrosic/omics-2026`

## Instalación de Git

### macOS

```bash
# Opción 1: viene preinstalado, verifica con:
git --version
# Opción 2: instalar via Homebrew
brew install git
```

### Windows

Descarga [Git for Windows](https://gitforwindows.org/). Durante la instalación, acepta las opciones por defecto. Esto instala Git Bash, que usarás como terminal.

### Linux

```bash
sudo apt install git    # Ubuntu/Debian
sudo dnf install git    # Fedora
```

### Alternativa sin terminal: GitHub Desktop

Descarga [GitHub Desktop](https://desktop.github.com/) — interfaz gráfica que hace lo mismo sin usar la terminal.

---

## Ejercicio paso a paso

### Paso 1: Configura tu identidad en Git (solo la primera vez)

**En terminal:**

```bash
git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu.email@ejemplo.com"
```

**En GitHub Desktop:** Ve a File → Options → Git y completa tu nombre y email.

---

### Paso 2: Haz Fork del repositorio del curso

1. Abre en tu navegador: `https://github.com/juancalderongiadrosic/omics-2026`
2. Haz clic en el botón **Fork** (esquina superior derecha).
3. Selecciona tu cuenta personal como destino.
4. Espera unos segundos — GitHub creará una copia en `https://github.com/TU-USUARIO/omics-2026`.

> **¿Qué acaba de pasar?** Ahora tienes tu propia copia del repositorio en tu cuenta de GitHub. Puedes modificarla libremente sin afectar el original.

---

### Paso 3: Clona tu fork a tu computador

**En terminal:**

```bash
# Navega a donde quieras guardar el proyecto
cd ~/Documents

# Clona TU fork (no el original)
git clone https://github.com/TU-USUARIO/omics-2026.git

# Entra a la carpeta
cd omics-2026
```

**En GitHub Desktop:** File → Clone Repository → selecciona `omics-2026` de la lista.

> **¿Qué acaba de pasar?** Descargaste todos los archivos del repositorio a tu computador. Git está rastreando los cambios desde este momento.

---

### Paso 4: Crea tu carpeta personal

**En terminal:**

```bash
# Crea tu carpeta en estudiantes/
mkdir -p estudiantes/nombre-apellido
```

**Sin terminal:** Simplemente crea la carpeta con el explorador de archivos.

---

### Paso 5: Crea tu archivo `about.md`

Crea un archivo llamado `about.md` dentro de tu carpeta. Usa cualquier editor de texto (VS Code, Notepad, TextEdit, nano).

Copia y completa esta plantilla:

```markdown
# [Tu nombre completo]

## Información básica

- **Programa:** [ej: Doctorado DCIM, año de ingreso]
- **Formación previa:** [ej: Medicina, Bioquímica, etc.]
- **Línea de investigación:** [tu tema de tesis o interés principal]
- **GitHub:** [@tu-usuario](https://github.com/tu-usuario)

## ¿Por qué este curso?

[1-2 oraciones sobre qué esperas aprender o aplicar]

## Un dato personal

[algo que quieras compartir con el grupo]
```

Guarda el archivo.

---

### Paso 6: Haz `add` y `commit`

**En terminal:**

```bash
# Verifica qué cambios detecta Git
git status

# Agrega tu carpeta al staging area
git add estudiantes/nombre-apellido/

# Crea un commit con un mensaje descriptivo
git commit -m "Agrega perfil de [Tu Nombre]"
```

**En GitHub Desktop:** Los archivos nuevos aparecen en el panel izquierdo. Escribe un mensaje de commit abajo y haz clic en "Commit to main".

> **¿Qué acaba de pasar?** Guardaste una "instantánea" de tu trabajo con un mensaje que describe qué hiciste. Este registro queda en el historial para siempre.

---

### Paso 7: Haz `push` a tu fork en GitHub

**En terminal:**

```bash
git push
```

**En GitHub Desktop:** Haz clic en "Push origin" (botón superior).

> **¿Qué acaba de pasar?** Subiste tu commit local a tu fork en GitHub. Si vas a `https://github.com/TU-USUARIO/omics-2026`, verás tu carpeta ahí.

---

### Paso 8: Crea un Pull Request

1. Ve a tu fork en GitHub: `https://github.com/TU-USUARIO/omics-2026`
2. Verás un banner que dice *"This branch is 1 commit ahead of juancalderongiadrosic:main"*. Haz clic en **Contribute → Open pull request**.
3. Completa:
   - **Título:** `Agrega perfil de [Tu Nombre]`
   - **Descripción:** "Mi primer PR en el curso de Ómicas DCIM 2026."
4. Haz clic en **Create pull request**.

> **¿Qué acaba de pasar?** Le enviaste una solicitud al repositorio original para que incorpore tus cambios. El docente revisará tu PR y hará *merge* si todo está bien.

---

### Paso 9: Verifica

- [ ] Tu fork existe en `github.com/TU-USUARIO/omics-2026`
- [ ] Tu carpeta `estudiantes/nombre-apellido/about.md` está visible en tu fork
- [ ] Tu Pull Request aparece en la pestaña "Pull Requests" del repositorio original

¡Felicitaciones! Acabas de completar el flujo completo de Git/GitHub que usarás durante todo el curso.

---

## Bonus: Conectar con el repositorio original (upstream)

Para mantener tu fork actualizado cuando el docente suba materiales nuevos:

```bash
# Agregar el repo original como "upstream"
git remote add upstream https://github.com/juancalderongiadrosic/omics-2026.git

# Traer los cambios nuevos
git fetch upstream
git merge upstream/main

# Subir la actualización a tu fork
git push
```

---

## Diagrama del flujo completo

```
REPOSITORIO ORIGINAL (juancalderongiadrosic/omics-2026)
         │
         │  fork
         ▼
TU FORK EN GITHUB (tu-usuario/omics-2026)
         │
         │  clone
         ▼
TU COPIA LOCAL (en tu computador)
         │
         │  edit → add → commit
         │
         │  push
         ▼
TU FORK EN GITHUB (actualizado)
         │
         │  pull request
         ▼
REPOSITORIO ORIGINAL (cambios integrados)
```

## ¿Problemas?

Revisa el cheat sheet en [`recursos/git-cheatsheet.md`](../../recursos/git-cheatsheet.md) o pregunta en clase.
