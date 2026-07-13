# LECCIÓN 07 — Unir ramas (`merge`): traer lo bueno a `main` 🔀

En la Lección 06 aprendiste a crear un "guardado aparte" (la rama `experimento`)
y viste la magia: los cambios de una rama **no tocan** la otra. Pero… ¿de qué
sirve un experimento que salió BIEN si se queda encerrado en su rama? 🤔

Hoy cierras el círculo: aprendes a **traer lo bueno de una rama a `main`**. Eso se
llama **`merge`** (fusionar / unir). Es el momento en que dices *"esto ya funciona,
ahora sí que forme parte de la versión oficial"*. ✅

## La idea en una frase

> **`merge` = agarrar los commits de una rama y meterlos en otra.**

En un trabajo real es literalmente el paso final de cada tarea: terminas tu botón
en su rama, lo pruebas, y lo **fusionas a `main`** para que llegue a la web de verdad.

## El detalle que TODOS confunden (léelo con calma 🧠)

El `merge` **NO se hace parado en la rama que quieres traer.**
Se hace parado en la rama que quieres que **RECIBA** los cambios.

Piénsalo así, como un imán:
- Quieres que `main` reciba lo de `experimento`.
- Entonces te paras en **`main`** (esa es la que "atrae").
- Y le dices: *"main, jala lo de experimento hacia ti"*.

La regla de oro para memorizarlo:

> **Primero te cambias a la rama DESTINO, y desde ahí haces `git merge <la-otra>`.**

## El comando de hoy

- **`git merge <rama>`** → trae los commits de `<rama>` hacia la rama en la que
  estás parado ahora mismo (donde apunta `HEAD`).

---

## TU TURNO

Asegúrate de estar dentro de `git-practica` (el prompt debe decirlo).

### Paso 1 — Párate en la rama DESTINO (`main`)
```bash
git switch main
```
→ Recuerda: `notas.md` aquí NO tiene la línea del experimento. `main` está "limpia".
Justo eso vamos a cambiar. 📍

### Paso 2 — Haz el merge (la fusión 🔀)
```bash
git merge experimento
```
→ Git responde algo como `Fast-forward` y una lista de archivos cambiados. Eso
significa: *"listo, jalé los commits de experimento hacia main"*. 🎉

### Paso 3 — Compruébalo con tus propios ojos
Abre `notas.md` en VSCode y míralo...

👉 **¡La línea del experimento AHORA SÍ aparece en `main`!** 🤯 Lo que antes solo
vivía en la otra rama, ya es parte oficial de tu rama principal. Eso es un merge.

### Paso 4 — Míralo también en la historia
```bash
git log --oneline
```
→ Verás que el commit que hiciste en `experimento` ahora también está en la
historia de `main`. Se unieron las dos líneas. 🔗

### Paso 5 — Limpieza: borra la rama que ya cumplió su misión 🧹
Cuando un experimento ya se fusionó, la rama sobra (su trabajo ya vive en `main`).
Se borra así:
```bash
git branch -d experimento
```
→ Git responde `Deleted branch experimento`. Tranquilo: **no pierdes nada**, porque
esos commits ya están a salvo dentro de `main`. Borras la etiqueta, no el trabajo. ✨

(El `-d` es minúscula y solo borra ramas ya fusionadas. Es un seguro anti-errores:
si intentas borrar una rama con trabajo SIN fusionar, Git te frena. 🛡️)

---

## ✅ Cuando termines
Pégame lo que te salió en el `git merge` (Paso 2) o en el `git log --oneline`
(Paso 4), o escribe **"listo"**. Reviso que la fusión quedó bien y cerramos con
broche de oro el bloque de ramas.

## 💡 Para tu cabeza (el ciclo completo del frontend 🧑‍💻)
Este es EL flujo que vas a repetir mil veces en tu carrera:

1. `git switch -c mi-tarea` → creas una rama para la tarea.
2. Trabajas y haces commits ahí, tranquilo, sin tocar `main`.
3. `git switch main` → vuelves a la principal.
4. `git merge mi-tarea` → traes lo bueno a `main`.
5. `git branch -d mi-tarea` → limpias.

Crear rama → trabajar → fusionar → limpiar. Ese loop es el 90% del Git del día a
día. Ya lo tienes completo. 💪
S