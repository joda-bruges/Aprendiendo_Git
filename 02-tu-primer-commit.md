# LECCIÓN 02 — Tu primer commit (tu primera foto) 📸

En la Lección 01 creaste el repo y viste que `01-que-es-git.md` estaba
**Untracked** (sin vigilar). Hoy lo movemos por las 3 zonas hasta convertirlo
en tu **primer commit**: la primera foto de tu álbum.

## Recordatorio del mapa (los 3 estados)

```
   [ 1. Working Directory ]  →  [ 2. Staging Area ]  →  [ 3. Repository ]
       (donde editas)            (la sala de espera)      (las fotos)

         git add  ────────────────►
                                      git commit  ──────────────►
```

Hoy usamos los dos comandos de las flechas:
- **`git add`** → mueve un archivo de la zona 1 a la zona 2 (lo preparas para la foto).
- **`git commit`** → toma la foto de todo lo que hay en la zona 2 y lo guarda en la zona 3.

## ¿Por qué DOS pasos y no uno?

Buena pregunta. Porque no siempre quieres fotografiar TODO a la vez. La zona 2
(staging) te deja **elegir** qué cambios entran en cada foto. Ejemplo real:
arreglaste un botón Y empezaste otra cosa a medias → con `git add` metes solo el
botón a la foto y dejas lo demás para después. Control fino. 🎯

## El mensaje del commit (importantísimo)

Cada foto lleva una **etiqueta** que explica QUÉ hiciste: el *mensaje del commit*.
Se escribe con `-m "..."`. Un buen mensaje se lee así:

- ✅ `"Agrega lección 01 sobre qué es Git"`  → claro, dice qué pasó.
- ❌ `"cambios"` / `"asdf"` / `"cosas"`  → tu yo del futuro te lo agradecerá NO hacer esto.

Regla junior: escribe el mensaje como si completara la frase *"Este commit va a..."*.

---

## TU TURNO

Asegúrate de seguir dentro de la carpeta `git-practica`. Corre en orden:

### Paso 1 — Mete el archivo a la sala de espera (zona 1 → 2)
```bash
git add 01-que-es-git.md
```
No devuelve nada visible. Eso es normal en Git: **silencio = todo bien**.

### Paso 2 — Confirma que se movió
```bash
git status
```
→ Ahora el archivo debe salir en **verde** bajo *"Changes to be committed"*.
Antes estaba en rojo (untracked). ¡Cambió de zona! 🟢

### Paso 3 — Toma la foto (zona 2 → 3)
```bash
git commit -m "Agrega leccion 01 sobre que es Git"
```
→ Git responde con algo como `[main (root-commit) a1b2c3d] Agrega leccion...`
y cuántos archivos cambiaron. **Ese código raro (`a1b2c3d`) es el ID único de tu
foto.** Acabas de hacer tu primer commit de la vida. 🥳

### Paso 4 — Mira el estado ahora
```bash
git status
```
→ Debe decir *"nothing to commit, working tree clean"*. Traducción: **no hay nada
pendiente, todo está guardado**. Esa frase es la que quieres ver siempre. ✨

### Paso 5 — Abre tu álbum de fotos
```bash
git log
```
→ Verás tu commit: su ID, tu nombre (`Author`), la fecha y tu mensaje.
Para salir de esa pantalla, pulsa la tecla **`q`** (de *quit*).

---

## ✅ Cuando termines
Pégame lo que te devolvió el `git commit` (el Paso 3) o el `git log` (Paso 5),
o escribe **"listo"**. Reviso que tu primera foto quedó bien guardada y pasamos a
la Lección 03: **hacer cambios y ver las diferencias con `git diff`**. 🔍
 