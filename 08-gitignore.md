# LECCIÓN 08 — Decirle a Git qué IGNORAR (`.gitignore`) 🙈

Hasta ahora le hemos dicho a Git *"guarda esto, sube aquello"*. Pero hay una
habilidad igual de importante: enseñarle a Git a **NO mirar** ciertos archivos.

Hoy aprendes el archivo mágico **`.gitignore`**: una lista donde escribes los
nombres de los archivos que quieres que Git **ignore por completo**. 🙈

## ¿Por qué querría IGNORAR archivos? 🤔

Porque no todo lo que hay en una carpeta merece subirse a GitHub. Ejemplos reales
que verás mil veces en tu carrera:

- **`node_modules/`** → una carpeta ENORME con miles de archivos de librerías. Jamás
  se sube (pesa muchísimo y se puede regenerar). En React la vas a ver siempre.
- **Contraseñas y claves secretas** (archivos `.env`) → ¡nunca deben ir a GitHub! 🔒
- **Archivos de basura temporal** → logs, cachés, cosas que crea tu editor.

> La regla: **el código sí; la basura, los secretos y lo pesado, NO.**

## La idea en una frase

> **`.gitignore` = una lista de nombres que Git finge que no existen.**

Si un archivo está en esa lista, Git no lo muestra en `git status`, no lo puedes
`add`, y por lo tanto **nunca se sube**. Como si fuera invisible. 👻

## El detalle clave 🧠

`.gitignore` es **un archivo de texto normal**, uno por línea:
- Escribes `basura.log` → ignora ESE archivo.
- Escribes `*.log` → el `*` significa "cualquier cosa", así que ignora TODOS los
  archivos que terminen en `.log`. (`error.log`, `debug.log`, etc.)
- Escribes `node_modules/` → el `/` al final significa "toda esa CARPETA".

---

## TU TURNO

Asegúrate de estar dentro de `git-practica` (mira el prompt 👀).

### Paso 1 — Crea un archivo "basura" a propósito
Vamos a fabricar un archivo que NO queremos subir, para luego ignorarlo:
```bash
echo "esto es basura temporal" > basura.log
```
→ Esto crea un archivo `basura.log`. Ahora míralo con:
```bash
git status
```
👉 Git lo muestra como `Untracked` (en rojo). Git lo está "viendo". Justo eso vamos
a apagar. 📍

### Paso 2 — Crea el archivo `.gitignore`
Ahora creamos la lista de ignorados con una línea dentro:
```bash
echo "basura.log" > .gitignore
```
→ Acabas de crear el archivo `.gitignore` con el nombre `basura.log` adentro. Le
estás diciendo a Git: *"a este archivo, ni lo mires"*. 🙈

### Paso 3 — La magia: vuelve a mirar el status
```bash
git status
```
👉 **¡`basura.log` YA NO aparece!** 🤯 Git lo está ignorando. Fíjate que ahora
en la lista sale `.gitignore` (ese SÍ queremos guardarlo, porque es la lista de
reglas y sí debe subir).

### Paso 4 — Guarda las reglas con un commit
El `.gitignore` sí se sube (para que las reglas queden guardadas en el proyecto):
```bash
git add .gitignore
git commit -m "Agrega gitignore para ignorar archivos de basura"
```

---

## ✅ Cuando termines
Pégame lo que te salió en el `git status` del **Paso 3** (donde `basura.log` ya
no aparece). Reviso que quedó bien y cerramos la lección.

## 💡 Para tu cabeza (esto lo vas a usar SIEMPRE)
Cuando llegues a **React** (tu Fase 3), lo PRIMERÍSIMO que hace un proyecto es crear
un `.gitignore` que ignora `node_modules/`. Sin eso, subirías miles de archivos
inútiles a GitHub. Hoy aprendiste algo que usan en el 100% de los proyectos reales. 🔥

Dato de oro: **`.gitignore` solo funciona sobre archivos que Git AÚN no rastrea.**
Si un archivo ya lo commiteaste antes, agregarlo al `.gitignore` no lo borra de la
historia. Por eso el `.gitignore` se crea al PRINCIPIO del proyecto, no al final. ⏰
