<div align="center">

# Git en equipo: trabajo colaborativo desde la terminal

Segundo bloque del curso de Git. Aquí encontrarás lo que necesitas preparar, el material de la clase, la tarea y una guía rápida para repasar el flujo por tu cuenta.

<br>

<img src="assets/logos/git.webp" width="80" alt="Git" />
&nbsp;&nbsp;&nbsp;&nbsp;
<img src="assets/logos/github.png" width="80" alt="GitHub" />

<br><br>

<img src="assets/logos/uady.webp" width="80" alt="UADY" />
<br>
<em>Facultad de Matemáticas de la UADY · Vinculación FMAT</em>

</div>

---

## <font color="#179287">De qué trata este bloque</font>

En el primer bloque aprendiste Git con botones. En este dejamos los botones y trabajamos **en equipo, sobre un repositorio compartido, desde la terminal**. No vas a programar nada: todo lo que escribas será texto en Markdown.

Al terminar vas a poder:

- Crear un repositorio desde la terminal y publicarlo en GitHub.
- Entender la diferencia entre tu copia **local** y la copia en **origin**, y mantenerlas sincronizadas.
- Organizar el trabajo del equipo con **issues**, **ramas** y **Pull Requests**.
- Proteger la rama principal para que nadie se salte las reglas, ni siquiera el dueño.
- Mantener un historial limpio y fácil de seguir con **rebase** y **squash**.
- Resolver conflictos sin pánico.
- Decidir qué reglas necesita tu equipo, y cuáles no.

---

## <font color="#179287">Antes de la clase</font>

Del primer bloque ya tienes cuenta de GitHub, Git instalado y GitHub Desktop con tu cuenta vinculada. **No necesitas configurar Git a mano**: GitHub Desktop ya dejó registrados tu nombre y tu correo.

- [ ] Instalar **GitHub CLI** desde [cli.github.com](https://cli.github.com/). Comprueba en la terminal que `gh --version` responde.
- [ ] Iniciar sesión con `gh auth login` → GitHub.com → HTTPS → *Login with a web browser*. Comprueba con `gh auth status`.
- [ ] Tener **VS Code** con la extensión **GitLens** instalada. No inicies sesión ni conectes nada en GitLens; si te lo ofrece, cierra la ventana.
- [ ] Saber quién es el **líder** de tu equipo (3 o 4 personas).

---

## <font color="#179287">Material de la clase</font>

La carpeta [`material/`](material/) tiene tres archivos que tu equipo copiará durante la clase: una plantilla para issues, una plantilla para Pull Requests y un "robot revisor" que se ejecuta en cada PR. No tienes que escribirlos: en su [README](material/README.md) se explica para qué sirve cada uno y cómo copiarlo.

---

## <font color="#179287">Tarea: "Nuestras reglas del juego"</font>

En equipo, elegirán una idea de proyecto, investigarán qué estrategia de trabajo colaborativo le conviene y la documentarán en su repositorio. Además, grabarán un video de 5 a 10 minutos explicándola.

**Es obligatoria, se entrega antes del siguiente bloque y el video es necesario para acreditar los puntos de formación integral.**

👉 [Instrucciones completas de la tarea](tarea/README.md)

---

## <font color="#179287">Acordeón: el ritual de trabajo en equipo</font>

| Momento | Qué hago | Dónde / comando |
|---|---|---|
| **Antes** | Ver qué me toca | GitHub.com → Issues, o `gh issue list --assignee @me` |
| | Pararme en la base | `git switch main` |
| | Ponerme al día | `git pull` |
| | Abrir mi rama | `git switch -c feature/[número]-[descripción]` |
| **Durante** | Ver qué cambió | `git status` / `git diff` |
| | Guardar un avance pequeño | `git add [archivo]` + `git commit -m "tipo: mensaje"` |
| | Corregir mi último commit (antes de subirlo) | `git add [archivo]` + `git commit --amend --no-edit` |
| | Ver dónde estoy | `git log --oneline --graph` / Graph de VS Code |
| | Si main avanzó, ponerme al día | `git pull --rebase origin main` |
| **Después** | Subir mi rama | `git push -u origin [rama]` (la primera vez) / `git push` |
| | Subir después de un rebase o amend | `git push --force-with-lease` |
| | Pedir revisión | `gh pr create --web` (con plantilla) o `gh pr create --base main --title "tipo: qué hice" --body "Closes #[número]"` |
| | Ver el robot | Checks del PR en GitHub.com, o `gh pr checks` |
| | Revisar a otros | GitHub.com → Files changed → Review changes |
| | Integrar | GitHub.com → **Squash and merge** |
| | Limpiar después del squash | `git switch main` + `git pull` + `git branch -D [rama]` (cuando el PR diga *Merged*) |
| **Pánico** | Salir de un rebase a medias | `git rebase --abort` |
| | Deshacer algo que ya está en main | `git revert [hash]` en una rama nueva + PR |
| | Dejar mi main igual a origin | `git reset --hard origin/main` (borra lo que no esté en origin) |

**Reglas de oro:**

- Nunca se trabaja directo en `main`.
- Solo se reescribe historia **propia** (`amend`, `rebase`, `--force-with-lease`), y de preferencia antes de compartirla. La historia de `main` nunca se reescribe.
- Nunca `--force` a secas; siempre `--force-with-lease`.
- Una rama, un PR. Después de integrar, la rama se borra.

> Estas son las reglas que usamos en clase, no las únicas posibles. Cada equipo puede y debe elegir las suyas: de eso trata la tarea.

---

## <font color="#179287">Recursos para seguir practicando</font>

- Ayuda de GitHub CLI desde la terminal: `gh help` y `gh [comando] --help`
- [Pro Git en español](https://git-scm.com/book/es/v2): libro oficial y gratuito (capítulos 3, *Ramificaciones en Git*, y 5, *Git en entornos distribuidos*)
- [Documentación de GitHub](https://docs.github.com/es): flujos de trabajo, rulesets y métodos de merge
- [Oh My Git!](https://ohmygit.org/): juego visual para practicar, incluido el rebase

---

## <font color="#179287">Para instructores</font>

El guion completo de la sesión (escenas, tiempos, frases clave y notas) está en [`guion/guion-instructor.md`](guion/guion-instructor.md).
