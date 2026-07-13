# LECCIÓN 05 — Subir tu código a GitHub ☁️

Hasta hoy todas tus fotos (commits) viven SOLO en tu computador. Si se daña el
disco... adiós. Hoy conectas tu repo con **GitHub** (la nube) y subes tu trabajo.
Esto es lo que te permite: (1) tener respaldo, (2) trabajar desde otra máquina, y
(3) **mostrar tu código a reclutadores**. Para un junior frontend, tu GitHub ES
tu carta de presentación. 💼

## El mapa mental nuevo

Ahora hay DOS repos: el tuyo (**local**, en tu compu) y uno en **GitHub** (remoto).

```
   [ TU COMPU (local) ]  ── git push ──►  [ GITHUB (remoto/nube) ]
      tus commits                             copia en la nube
                          ◄── git pull ──
```

- **`push`** = *empujar* tus commits hacia la nube (subir ⬆️).
- **`pull`** = *jalar* cambios desde la nube hacia tu compu (bajar ⬇️).
- **`origin`** = el apodo estándar que Git le pone a "tu repo en GitHub". Lo verás
  mucho: `origin` = "la nube".

---

## TU TURNO

Este día tiene una parte en el **navegador** (crear el repo vacío en GitHub) y otra
en la **terminal** (conectarlo y subir). Ve con calma. 🐢

### PARTE A — Crear el repo vacío en GitHub (navegador)

**Paso 1** — Entra a https://github.com e inicia sesión con tu cuenta.

**Paso 2** — Arriba a la derecha, clic en el **`+`** → **"New repository"**.

**Paso 3** — Llénalo así:
- **Repository name:** `git-practica`
- **Description** (opcional): `Mi practica de Git aprendiendo`
- Déjalo en **Public** (así podrás mostrarlo).
- ⚠️ **MUY IMPORTANTE:** NO marques *"Add a README"*, NO agregues *.gitignore*
  ni *license*. Queremos el repo **100% vacío**, porque el tuyo local ya tiene
  historia. (Si lo llenas, chocan y se complica.)

**Paso 4** — Clic en **"Create repository"**. GitHub te mostrará una página con
comandos. Fíjate en la línea que empieza con `git remote add origin ...` —
contiene la **URL de tu repo**. La vamos a usar. Déjala a mano.

### PARTE B — Conectar y subir (terminal, dentro de `git-practica`)

**Paso 5** — Dile a tu repo local dónde vive la nube. Copia la URL de tu repo
(termina en `.git`) y córrela así (reemplaza TU-USUARIO por tu usuario real):
```bash
git remote add origin https://github.com/TU-USUARIO/git-practica.git
```
No devuelve nada (silencio = bien 🤫).

**Paso 6** — Comprueba que quedó conectado:
```bash
git remote -v
```
→ Debe listar `origin` con tu URL, dos veces (fetch y push). ✅

**Paso 7** — El gran momento. Sube tus commits a la nube:
```bash
git push -u origin main
```
- `-u origin main` = *"sube mi rama `main` a `origin` y recuérdalo para la próxima"*.
- 🔐 **La primera vez te pedirá iniciar sesión en GitHub** (se abrirá una ventana
  del navegador o un cuadro pidiendo autorizar). Acepta / inicia sesión. Es normal
  y solo pasa una vez; después Git recuerda tus credenciales.

**Paso 8** — Cuando termine, verás algo como `Writing objects: 100%` y una línea
`main -> main`. ¡Tu código ya está en la nube! ☁️🎉

**Paso 9** — Comprueba en el navegador: recarga la página de tu repo en GitHub.
Deberías ver tus archivos (`01-que-es-git.md`, `notas.md`, etc.) y, si haces clic
en *"commits"*, ¡tus 4 fotos con sus mensajes! 📸

---

## ✅ Cuando termines
Pégame lo que te salió en el `git push` (Paso 7/8), o mándame el **link de tu repo
en GitHub** (algo como `github.com/tu-usuario/git-practica`) o escribe **"listo"**.
Reviso que tu primer push quedó perfecto y pasamos a la Lección 06: **ramas
(`branch`)** — trabajar sin miedo a romper lo que ya funciona. 🌿

## 🆘 Si algo falla
No te frustres, los errores de push/login son SÚPER comunes al principio. Pégame
el mensaje de error tal cual (captura o texto) y lo resolvemos juntos paso a paso.
La autenticación de GitHub es lo único "espinoso" de esta lección; el resto es fácil.
