# LECCIÓN 06 — Ramas (`branch`): trabajar sin miedo 🌿

Hasta hoy toda tu historia fue **una sola línea recta** de commits, una tras otra,
en la rama `main`. Hoy aprendes el concepto que hace de Git una herramienta
PROFESIONAL: las **ramas**. Es, sin exagerar, el superpoder que más vas a usar
como frontend. 💪

## ¿Qué es una rama? (la analogía del videojuego 🎮)

Imagina que `main` es tu partida "buena", la que ya funciona y no quieres arruinar.
Una **rama** es como hacer un **"guardado aparte"** para experimentar: pruebas cosas
locas, y si sale mal, borras ese guardado y tu partida buena queda **intacta**. Si
sale bien, unes lo bueno a tu partida principal (eso será la Lección 07).

En términos reales de trabajo:
- `main` = la versión estable de tu web (la que funciona ✅).
- una rama nueva, ej. `nueva-funcion` = donde desarrollas algo sin tocar lo estable.

Así, si rompes algo mientras experimentas, **`main` sigue perfecta**. Cero miedo. 🛡️

## El concepto clave: `HEAD` (tú estás aquí 📍)

`HEAD` es un puntero que dice **"en qué rama estás parado ahora mismo"**. Ya lo
viste en tu `git log`: salía `HEAD -> main`. Cuando cambies de rama, `HEAD` se
mueve, y **todo lo que hagas (commits) cae en la rama donde apunta HEAD**.

## Los comandos de hoy

- **`git branch`** → lista tus ramas. La actual sale con un `*` al lado.
- **`git switch -c <nombre>`** → **c**rea una rama nueva Y te cambia a ella de una.
- **`git switch <nombre>`** → te cambias a una rama que ya existe.

(Ojo: quizá veas por internet `git checkout` para esto. Es lo viejo. `switch` es
lo moderno y más claro. Úsalo tú.)

---

## TU TURNO

Asegúrate de estar dentro de `git-practica` (el prompt debe decir `git-practica`).

### Paso 1 — Mira en qué rama estás
```bash
git branch
```
→ Debe salir `* main`. Ese `*` significa "aquí estás parado". Por ahora solo hay una. 📍

### Paso 2 — Crea una rama nueva y cámbiate a ella
```bash
git switch -c experimento
```
→ Git responde `Switched to a new branch 'experimento'`. Fíjate en tu prompt de
colores: ahora debería decir `experimento` en vez de `main`. 🌿

### Paso 3 — Confírmalo
```bash
git branch
```
→ Ahora salen DOS ramas, y el `*` está en `experimento`. Acabas de crear tu primer
"guardado aparte". Todo lo que hagas ahora NO toca `main`. ✨

### Paso 4 — Haz un cambio SOLO en esta rama
Abre `notas.md` en VSCode y agrégale una línea, por ejemplo:
```
- Esta linea la escribi en la rama experimento
```
Guarda (Ctrl+S) y haz tu ciclo de siempre:
```bash
git add notas.md
git commit -m "Agrega linea de prueba en rama experimento"
```

### Paso 5 — LA MAGIA 🎩✨ (esto es lo importante de hoy)
Vuelve a la rama principal:
```bash
git switch main
```
Ahora abre `notas.md` en el editor otra vez y **mírala con atención**...

👉 **¡La línea que escribiste DESAPARECIÓ!** No se borró ni se perdió — es que esa
línea vive en la rama `experimento`, y ahora estás parado en `main`. Cada rama es
su propio mundo. `main` sigue limpia, tal como la dejaste. 🤯

### Paso 6 — Comprueba que la línea sigue viva en la otra rama
```bash
git switch experimento
```
Abre `notas.md` de nuevo → **la línea reaparece**. No estaba perdida, solo estaba
en su rama. Ese ir y venir sin perder nada es TODO el punto de las ramas. 🔄

---

## ✅ Cuando termines
Pégame lo que te salió en el `git branch` (Paso 3) o cuéntame qué pasó con la línea
al cambiar de rama (Paso 5), o escribe **"listo"**. Reviso que entendiste la magia
de las ramas y pasamos a la Lección 07: **`merge`** — unir tu rama de experimento a
`main` cuando lo que hiciste sí sirvió. 🔀

## 💡 Para tu cabeza (por qué esto importa tanto)
En un trabajo real NADIE toca `main` directamente. Cada tarea nueva (un botón, un
bug, una sección) se hace en su propia rama, y solo cuando está lista y probada se
une a `main`. Dominar ramas es dominar cómo se trabaja en equipo de verdad. 🧑‍💻
