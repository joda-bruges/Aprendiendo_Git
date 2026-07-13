# LECCIÓN 04 — Deshacer cambios: el botón de "regrésame" ⏪

Hasta ahora solo has AVANZADO: crear, modificar, guardar fotos. Pero el poder
real de Git es que también puedes **RETROCEDER**. Hoy aprendes a deshacer sin
miedo — porque si Git es una máquina del tiempo, esta es la palanca de "volver". 🕰️

## Los dos "arrepentimientos" más comunes

Recuerda tus 3 zonas: **Working Directory → Staging → Repository**. Casi siempre
te vas a arrepentir en una de estas dos situaciones:

1. **"Edité un archivo y quiero borrar ese cambio"** (aún NO le hiciste `add`).
   → El cambio está solo en la **zona 1** (Working Directory).
2. **"Le hice `add` sin querer y quiero sacarlo de la sala de espera"**.
   → El cambio ya está en la **zona 2** (Staging).

Para cada caso hay UN comando. Los dos usan la misma palabra clave: `git restore`.

## Comando 1 — Descartar cambios NO guardados (zona 1)

```bash
git restore <archivo>
```
Traducción: *"regrésame este archivo a como estaba en la última foto (commit)"*.
⚠️ **Ojo:** esto BORRA tus cambios no guardados para siempre. Por eso el hábito de
mirar `git diff` ANTES existe: primero ves qué vas a perder, luego decides.

## Comando 2 — Sacar de la sala de espera (zona 2 → 1)

```bash
git restore --staged <archivo>
```
Traducción: *"quita este archivo del staging, pero NO borres mis cambios"*.
El archivo vuelve a la zona 1 (sigues teniendo tus cambios, solo que ya no está
"preparado para la foto"). Es el **deshacer del `git add`**. 🔙

Diferencia clave: `--staged` es la palabra mágica que decide en qué zona actúas.

---

## TU TURNO

Sigue dentro de `git-practica`. Vamos a provocar un "error" a propósito y deshacerlo.

### Caso A — Deshacer un cambio no guardado

**Paso 1** — Abre `notas.md` y agrégale una línea cualquiera, por ejemplo:
```
- Esta linea la escribi por error
```
Guarda con **Ctrl+S**.

**Paso 2** — Comprueba que Git la ve:
```bash
git status
```
→ `notas.md` sale como **modified** (rojo).

**Paso 3** — Míralo antes de borrar (buen hábito 🧠):
```bash
git diff
```
→ Verás tu línea con `+` verde.

**Paso 4** — Arrepiéntete y bórrala:
```bash
git restore notas.md
```
No devuelve nada (silencio = todo bien 🤫).

**Paso 5** — Confirma la magia:
```bash
git status
```
→ Debe decir **"nothing to commit, working tree clean"**. La línea del error
desapareció. Abre `notas.md` en el editor: ya no está. ⏪✨

### Caso B — Deshacer un `git add`

**Paso 6** — Agrega otra línea a `notas.md` y guarda (Ctrl+S):
```
- Esta si la quiero guardar bien
```

**Paso 7** — Métela a la sala de espera... a propósito:
```bash
git add notas.md
```

**Paso 8** — Mira el estado:
```bash
git status
```
→ Ahora sale en **verde** bajo *"Changes to be committed"*. Está en staging.

**Paso 9** — "Uy, todavía no quería prepararla". Sácala del staging:
```bash
git restore --staged notas.md
```

**Paso 10** — Confirma:
```bash
git status
```
→ Vuelve a salir en **rojo** como *modified*. 👉 Importante: tu línea **sigue ahí**
(no la perdiste), solo salió de la sala de espera. Eso es lo que hace `--staged`.

**Paso 11** — Ahora sí, guárdala bien con un buen mensaje:
```bash
git add notas.md
git commit -m "Agrega nota que si quiero conservar"
```

---

## ✅ Cuando termines
Pégame lo que te salió en algún `git status` de los pasos (por ejemplo el Paso 5
o el Paso 10), o escribe **"listo"**. Reviso que dominaste el deshacer y pasamos a
la Lección 05: **conectar tu repo con GitHub y subir tu trabajo a la nube** ☁️🚀
