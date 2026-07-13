# 🧾 Chuleta de Git — comandos del día a día

Tu machete personal, José. Aquí están los comandos que vas a usar **de verdad**,
en el orden en que aparecen en un día normal de trabajo. Todos los dominas ya. 💪

> 💡 Regla mental: **mira siempre `git status` antes y después** de cualquier cosa.
> Es tu brújula: te dice dónde estás parado y qué va a pasar.

---

## ⚙️ 1. Configuración (solo una vez por computador)

```bash
git config --global user.name "Jose Bruges"
git config --global user.email "jodabruges@gmail.com"
```
Le dice a Git quién eres, para que firme tus commits con tu nombre.

---

## 🔄 2. El ciclo diario (el 90% de tu trabajo)

| Comando | Qué hace |
|---|---|
| `git status` | 🧭 Tu brújula: qué cambió, qué está listo para guardar. |
| `git add .` | 📦 Prepara **todo** lo cambiado para la foto (staging). |
| `git add archivo.ts` | 📦 Prepara **solo ese archivo**. |
| `git commit -m "mensaje claro"` | 📸 Toma la foto (guarda los cambios preparados). |

**El flujo típico:**
```bash
git status                          # ¿qué cambió?
git add .                           # preparo los cambios
git commit -m "Agrega función X"    # los guardo con un mensaje que diga QUÉ cambió
```

> ✍️ El mensaje describe **qué hace ese cambio**, no "cambios" o "update".
> Bien: `"Agrega validación al formulario"`. Mal: `"cambios"`.

---

## 🔍 3. Ver la historia y los cambios

| Comando | Qué hace |
|---|---|
| `git log` | 📜 Lista todos los commits (foto por foto). |
| `git log --oneline` | 📜 Lo mismo, pero una línea por commit (más limpio). |
| `git diff` | 🔬 Muestra **qué cambiaste** y aún no has preparado. |
| `git diff --staged` | 🔬 Muestra lo que ya está preparado (staged). |

> 🖱️ Cuando `git log` o `git diff` abren pantalla completa (el *pager*),
> presiona la tecla **`q`** para salir. (Es una tecla, no un comando: sin Enter.)

---

## ↩️ 4. Deshacer (sin miedo — nada se pierde)

| Comando | Qué hace |
|---|---|
| `git restore archivo.ts` | 🧽 Descarta cambios NO guardados de ese archivo (vuelve a la última foto). |
| `git restore --staged archivo.ts` | 🔙 Saca un archivo del staging (sigue modificado, pero ya no "preparado"). |
| `git restore --staged .` | 🔙 Saca **todo** del staging de un golpe. |

> ⚠️ `git restore archivo` **sí borra** los cambios no guardados de ese archivo.
> `git restore --staged` es seguro: solo "desprepara", no borra tu trabajo.

---

## 🌿 5. Ramas (branches)

| Comando | Qué hace |
|---|---|
| `git branch` | 📋 Lista tus ramas (la actual tiene un `*`). |
| `git switch -c nueva-rama` | 🌱 **Crea** y se cambia a una rama nueva. |
| `git switch main` | 🔀 Se cambia a una rama que ya existe. |
| `git merge otra-rama` | 🤝 Trae los cambios de `otra-rama` a la que estás parado. |
| `git branch -d rama-vieja` | 🗑️ Borra una rama que ya fusionaste. |

**Flujo típico de rama:**
```bash
git switch -c mejora-login    # creo la rama y trabajo ahí
# ...hago cambios, add, commit...
git switch main               # vuelvo a main
git merge mejora-login        # traigo mi trabajo a main
git branch -d mejora-login    # limpio la rama
```

---

## ☁️ 6. GitHub (subir y bajar)

| Comando | Qué hace |
|---|---|
| `git clone <url>` | ⬇️ Descarga un repo de GitHub por primera vez. |
| `git remote add origin <url>` | 🔗 Conecta tu repo local con uno de GitHub. |
| `git push -u origin main` | 🚀 Sube por **primera vez** una rama (la empareja con GitHub). |
| `git push` | 🚀 Sube tus commits nuevos (cuando la rama ya está emparejada). |
| `git pull` | ⬇️ Baja los cambios que haya en GitHub. |

> 💡 El `-u` (set-upstream) solo se necesita la **primera vez** que subes una rama.
> Después basta con `git push` a secas.

---

## 🤝 7. Flujo profesional con Pull Request (trabajo en equipo)

Así se trabaja en un equipo real (y como practicaste en la L09):

```bash
git switch main
git pull                          # 1. arranco con lo último
git switch -c mi-cambio           # 2. creo mi rama
# ...trabajo, add, commit...
git push -u origin mi-cambio      # 3. subo mi rama a GitHub
# 4. En GitHub: abro el Pull Request y lo fusiono
git switch main
git pull                          # 5. bajo el cambio ya fusionado
```

---

## 🙈 8. Ignorar archivos (.gitignore)

Crea un archivo llamado `.gitignore` y adentro pon lo que Git debe **ignorar**:

```
node_modules/     # dependencias (se reinstalan con npm install)
.env              # secretos, contraseñas, API keys
.DS_Store         # basura del sistema
```

Comprobar que algo está ignorado:
```bash
git check-ignore -v node_modules/
```

---

## 🆘 Comandos salvavidas

| Situación | Comando |
|---|---|
| "¿Dónde estoy? ¿Qué pasó?" | `git status` |
| "¿En qué rama estoy?" | `git branch` |
| "Quiero ver los últimos commits" | `git log --oneline` |
| "Me arrepentí de lo que preparé" | `git restore --staged .` |
| "¿Con qué GitHub está conectado?" | `git remote -v` |

---

*Hecho para José en su camino a frontend junior. Actualízala cuando aprendas algo nuevo. 🚀*
