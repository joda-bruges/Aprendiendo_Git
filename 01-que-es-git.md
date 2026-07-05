# LECCIÓN 01 — ¿Qué es Git? + Tu primer repositorio

## 1. ¿Qué es Git?

Git es una **máquina del tiempo para tu código**. Cada vez que terminas algo
importante, le sacas una "foto" (un *commit*). Si mañana rompes todo, puedes
volver a cualquier foto anterior. Nunca más un `proyecto_final_FINAL_v2_bueno`.

Tres superpoderes que te da:
- **Historial**: ves qué cambiaste, cuándo y por qué.
- **Volver atrás**: regresas a una versión que funcionaba.
- **Ramas**: pruebas ideas sin tocar lo que ya funciona.

## 2. Git ≠ GitHub  (¡tú tienes los dos!)

Mucha gente los confunde. Son cosas distintas que trabajan juntas:

| Git | GitHub |
|-----|--------|
| Programa en **tu computador** | Página web **en internet** |
| Guarda las "fotos" localmente | Guarda una copia en la nube |
| Funciona sin internet | Para compartir / respaldar |

Analogía: **Git** es la cámara que toma las fotos. **GitHub** es el Instagram
donde las subes para que no se pierdan y otros las vean. Hoy solo usamos la
**cámara (Git)**; conectar con GitHub lo haremos en una lección más adelante.

## 3. Los 3 estados de un archivo (el mapa mental MÁS importante)

Cuando trabajas con Git, tus archivos viajan por **tres zonas**:

```
   [ 1. Working Directory ]  →  [ 2. Staging Area ]  →  [ 3. Repository ]
       (donde editas)            (lo que vas a            (las fotos
                                  meter en la foto)         guardadas)

         git add  ────────────────►
                                      git commit  ──────────────►
```

1. **Working Directory** — tu carpeta normal, donde escribes y editas.
2. **Staging Area** — la "sala de espera". Eliges QUÉ cambios entran en la
   próxima foto (no siempre quieres fotografiar todo a la vez).
3. **Repository** — el álbum de fotos ya guardadas (los commits).

Mueves cosas con dos comandos: `git add` (zona 1 → 2) y `git commit` (zona 2 → 3).
Esto lo practicaremos a fondo en la Lección 02.

---

## TU TURNO

Abre la terminal de VSCode (menú **Terminal → New Terminal**) y ejecuta los
comandos en orden. Después de cada uno, mira la respuesta.

### Paso 1 — Preséntate ante Git (identidad)
Git firma cada foto con tu nombre. Configúralo UNA sola vez (vale para todos
tus repos). Escribe exactamente, cambiando los datos si quieres:

```bash
git config --global user.name "Jose Bruges"
git config --global user.email "jpsundheim@gmail.com"
```

Comprueba que quedó bien:

```bash
git config --global user.name
git config --global user.email
```

→ Debe devolverte tu nombre y tu correo.

### Paso 2 — Que la rama principal se llame "main"
```bash
git config --global init.defaultBranch main
```

### Paso 3 — Crea tu primer repositorio
Asegúrate de estar dentro de la carpeta de práctica. En la terminal:

```bash
cd "C:/Users/joda_/OneDrive/Desktop/DEV/git-practica"
git init
```

→ Git responde algo como *"Initialized empty Git repository..."*.
¡Acabas de crear un repo! Se creó una carpeta oculta `.git` (NO la toques: ahí
vive toda la magia).

### Paso 4 — Pregúntale a Git cómo va todo
```bash
git status
```

`git status` es el comando que MÁS vas a usar en tu vida. Te dice en qué rama
estás y qué archivos están sin guardar.

---

## ✅ Cuando termines
Pégame aquí lo que te devolvió el último `git status` (cópialo de la terminal),
o simplemente escribe **"listo"**. Con eso reviso que todo quedó bien y pasamos
a la Lección 02: **tu primer commit (tu primera foto)**. 📸
1