# LECCIÓN 09 — El flujo REAL de un equipo (Pull Request) 🤝

Esta es la **última lección del bloque de Git**, y la más importante para tu primer
trabajo. Hasta ahora trabajaste **solo**. Hoy aprendes cómo se trabaja **en equipo**,
que es como se hace en TODAS las empresas. 💼

## El problema que resuelve el trabajo en equipo 🤔

Imagina que eres frontend junior en una empresa. Hay UN proyecto en GitHub y **cinco
personas** tocándolo a la vez. Si todos empujaran a `main` directo, sería un caos:
código a medias, cosas rotas, unos pisando a otros. 💥

La solución que usa TODO el mundo tiene 3 piezas nuevas:

- **`git clone`** → copiar el proyecto de GitHub a tu compu (la primera vez).
- **Pull Request (PR)** → *"propongo estos cambios, revísenlos antes de meterlos a `main`"*. 🔍
- **`git pull`** → bajar a tu compu los cambios que otros ya metieron. ⬇️

## La estrella de hoy: el Pull Request 🌟

Un **Pull Request** es como **pedir permiso educadamente** antes de meter tu trabajo
al proyecto oficial:

> *"Hice esta mejora en mi rama. ¿La revisan y, si está bien, la unen a `main`?"*

En lugar de fusionar tú mismo (como hicimos con `git merge` en local), en un equipo
**subes tu rama a GitHub y abres un PR**. Ahí un compañero lo revisa, comenta, y le
da al botón verde de **Merge**. Así nada roto llega a `main`. ✅

Es LITERALMENTE lo que harás todos los días en tu trabajo. Hoy lo haces por primera vez. 🎉

---

## TU TURNO — vas a hacer un Pull Request REAL en tu propio repo

Como no tienes compañeros todavía, harás las dos partes tú: propones el cambio
(rama + PR) y luego lo apruebas. Así vives el flujo completo. 🎬

Asegúrate de estar en `git-practica` (mira el prompt 👀).

### Paso 0 — Sube lo que tengas pendiente
Primero, deja tu `main` sincronizada con GitHub:
```bash
git switch main
git push
```
→ Esto sube el commit del `.gitignore` que quedó pendiente. Tu prompt debería
quedar `main ≡` (todo sincronizado).

### Paso 1 — Crea una rama para tu "tarea"
```bash
git switch -c mejora-notas
```
→ Estás en una rama nueva. Aquí trabajas tranquilo sin tocar `main`. 🌿

### Paso 2 — Haz un cambio y commitéalo
Agrega una línea a `notas.md`:
```bash
echo "Linea agregada desde un Pull Request" >> notas.md
git add notas.md
git commit -m "Agrega linea de prueba para el PR"
```
(Ojo: `>>` con DOS flechitas = "añade al final". Con una sola `>` borraría todo. ⚠️)

### Paso 3 — Sube TU RAMA a GitHub (no main)
```bash
git push -u origin mejora-notas
```
→ Fíjate: subes la rama `mejora-notas`, NO `main`. Git te dará un **link** en la
respuesta para abrir el PR. 🔗

### Paso 4 — Abre el Pull Request (en el navegador 🌐)
1. Ve a tu repo en GitHub: `github.com/joda-bruges/Aprendiendo_Git`
2. Verás un aviso amarillo: **"Compare & pull request"** → dale clic.
3. Pon un título, y abajo dale al botón verde **"Create pull request"**.
4. ¡Ya está creado tu PR! 🎉 (Aquí, en un trabajo, un compañero lo revisaría).

### Paso 5 — Apruébalo y fusiónalo (haces de "revisor")
1. Dentro del PR, dale al botón verde **"Merge pull request"** → **"Confirm merge"**.
2. GitHub te avisa que quedó fusionado. Tu cambio ya está en `main`... **pero en GitHub**. 🌐

### Paso 6 — Baja el cambio a tu compu con `git pull`
Tu `main` de GitHub ahora tiene algo que tu `main` local NO tiene. Sincroniza:
```bash
git switch main
git pull
```
→ `git pull` **baja** el merge que hiciste en GitHub. Ahora tu `main` local también
tiene la línea nueva. 🔄 Abre `notas.md` y compruébalo.

---

## ✅ Cuando termines
Pégame lo que salió en el **`git pull`** (Paso 6), o una captura de tu PR fusionado.
Reviso que cerraste el ciclo completo y... ¡habrás terminado TODO el bloque de Git! 🏁

## 💡 Para tu cabeza (el flujo profesional COMPLETO)
Este es el ciclo real de cualquier frontend, todos los días:

1. `git pull` → bajas lo último del equipo.
2. `git switch -c mi-tarea` → creas tu rama.
3. Trabajas + commits.
4. `git push -u origin mi-tarea` → subes tu rama.
5. Abres un **Pull Request** en GitHub.
6. Un compañero lo revisa y lo fusiona.
7. `git pull` → todos bajan el cambio.

pull → rama → trabajar → push → PR → review → merge → pull. Ese loop es el corazón
del trabajo en equipo. Y hoy lo hiciste TÚ SOLO, de punta a punta. 💪
