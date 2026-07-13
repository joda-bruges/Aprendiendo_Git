# LECCIÓN 03 — Modificar archivos y ver los cambios con `git diff` 🔍

Hasta ahora guardaste un archivo NUEVO. Pero el 99% del trabajo real es
**modificar** archivos que ya existen. Hoy aprendes a ver, con precisión de
cirujano, QUÉ cambiaste antes de tomar la siguiente foto.

## El concepto clave: "tracked" (vigilado)

Tu `01-que-es-git.md` ya está en un commit → ahora Git lo **vigila** (*tracked*).
Eso cambia el juego: si lo editas, Git ya no dice *"untracked"*, sino
**"modified"** (modificado). Y te puede mostrar EXACTAMENTE qué línea tocaste.

## El comando estrella de hoy: `git diff`

`git diff` responde a la pregunta: *"¿qué he cambiado desde la última foto y
todavía NO está en la sala de espera?"* Te muestra las diferencias línea por línea:

- Líneas que **quitaste** → empiezan con `-` (y salen en rojo).
- Líneas que **agregaste** → empiezan con `+` (y salen en verde).

Es tu red de seguridad: **míralo SIEMPRE antes de hacer `git add`**, para no
guardar sin querer algo que no querías. Es un hábito de profesional. 🧠

---

## TU TURNO

### Paso 1 — Crea un archivo nuevo para jugar
Vamos a crear un pequeño archivo de notas. En la terminal:
```bash
echo "# Mis notas de Git" > notas.md
```
Esto crea `notas.md` con esa línea dentro.

### Paso 2 — Guárdalo en un commit (repasa el ciclo tú solo)
```bash
git add notas.md
git commit -m "Agrega archivo de notas"
```
→ Ya tienes tu segunda foto. (Este ciclo ya lo dominas 💪).

### Paso 3 — Ahora MODIFICA el archivo
Abre `notas.md` en VSCode (aparece en el explorador de la izquierda) y agrégale
una línea nueva debajo, por ejemplo:
```
- Git es una maquina del tiempo para mi codigo
```
**Guarda el archivo** (Ctrl+S). ¡Importante guardar!

### Paso 4 — Pregúntale a Git qué cambió
```bash
git status
```
→ Ahora `notas.md` sale en rojo pero como **"modified"** (no "untracked"),
porque Git ya lo vigila.

### Paso 5 — El momento estrella: mira el diff
```bash
git diff
```
→ Vas a ver tu línea nueva con un **`+`** verde delante. Eso es Git diciéndote
*"esto es exactamente lo que agregaste"*. 🟢
(Si la vista llena la pantalla, sales con la tecla `q`.)

### Paso 6 — Guarda el cambio en una foto
```bash
git add notas.md
git commit -m "Agrega nota sobre que es Git"
```

### Paso 7 — Mira tu historia creciendo
```bash
git log --oneline
```
→ `--oneline` muestra cada commit en UNA sola línea (ID corto + mensaje). Mucho
más cómodo para ver el historial de un vistazo. Deberías ver ya 3 commits. 📈
(Sales con `q` si llena la pantalla.)

---

## ✅ Cuando termines
Pégame lo que te salió en el `git diff` (Paso 5) o en el `git log --oneline`
(Paso 7), o escribe **"listo"**. Con eso cerramos y pasamos a la Lección 04:
**deshacer cambios** (el botón de "me equivoqué, regrésame"). ⏪
