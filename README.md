<div align="center">

# Git en equipo: trabajo colaborativo desde la terminal

Sesión 2 del curso de Git · 4 horas. Desde aquí llegas a todo lo que necesitas: qué instalar antes de la clase, la guía que seguirás durante la sesión, el material, la tarea y los recursos para repasar por tu cuenta.

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

## <font color="#179287">De qué trata esta sesión</font>

En la Sesión 1 aprendiste Git con botones. En esta dejamos los botones y trabajamos **en equipo, sobre un repositorio compartido, desde la terminal**. No vas a programar nada: todo lo que escribas será texto en Markdown.

Al terminar vas a poder:

- Crear un repositorio desde la terminal y publicarlo en GitHub.
- Entender la diferencia entre tu copia **local** y la copia en **origin**, y mantenerlas sincronizadas.
- Organizar el trabajo del equipo con **issues**, **ramas** y **Pull Requests**.
- Proteger la rama principal para que nadie se salte las reglas, ni siquiera el dueño.
- Mantener un historial limpio y fácil de seguir con **rebase** y **squash**.
- Resolver conflictos sin pánico.
- Decidir qué reglas necesita tu equipo, y cuáles no.

---

## <font color="#179287">Qué hay en este repositorio</font>

| Qué | Para quién | Dónde |
|---|---|---|
| **Guía del alumno**: los 8 bloques de la sesión, paso a paso, con sus actividades y el acordeón | Alumnos | [`material/guia-alumno.md`](material/guia-alumno.md) |
| **Plantillas y robot**: plantillas de issue y de PR, y el robot revisor que copiará tu equipo | Alumnos | [`material/plantillas-y-robot/`](material/plantillas-y-robot/) |
| **Tarea**: "Nuestras reglas del juego" | Alumnos | [`material/tarea.md`](material/tarea.md) |
| **Guion**: el material guía del instructor, con tiempos, frases clave y notas | Instructores | [`guion/guion-instructor.md`](guion/guion-instructor.md) |
| **Guía de diapositivas**: qué debe llevar la presentación en cada bloque | Instructores | [`guion/guia-slides.md`](guion/guia-slides.md) |

**Vocabulario del curso:**

| Término | Qué es |
|---|---|
| **Sesión** | Una clase completa de 4 horas. Este repositorio cubre la Sesión 2 |
| **Bloque** | Cada parte de la sesión donde se explica y practica un concepto principal. La sesión tiene 8 |
| **Guion** | El material guía del instructor |
| **Guía del alumno** | Lo que tú sigues durante la sesión, bloque por bloque |

---

## <font color="#179287">Antes de la clase</font>

De la Sesión 1 ya tienes cuenta de GitHub, Git instalado y GitHub Desktop con tu cuenta vinculada. **No necesitas configurar Git a mano**: GitHub Desktop ya dejó registrados tu nombre y tu correo, y la terminal usa esa misma configuración.

| Herramienta | Enlace |
|---|---|
| GitHub CLI (`gh`) | [cli.github.com](https://cli.github.com/) |
| VS Code | [code.visualstudio.com](https://code.visualstudio.com/) |
| Extensión GitLens para VS Code | [GitLens en el Marketplace](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) |

- [ ] Instalar **GitHub CLI**. Comprueba en la terminal que `gh --version` responde.
- [ ] Iniciar sesión con `gh auth login` → GitHub.com → HTTPS → *Login with a web browser*. Comprueba con `gh auth status`.
- [ ] Tener **VS Code** con la extensión **GitLens** instalada. No inicies sesión ni conectes nada en GitLens; si te lo ofrece, cierra la ventana.
- [ ] Saber quién es el **líder** de tu equipo (3 o 4 personas).

> Si al empezar la clase `gh auth status` no responde bien, avísale a un asistente: te ayudará aparte sin detener al grupo.

---

## <font color="#179287">Durante la clase</font>

Sigue la [**guía del alumno**](material/guia-alumno.md). La sesión avanza en 8 bloques; cada uno explica qué vas a hacer, cómo hacer cada actividad y qué debes tener listo antes de pasar al siguiente.

| # | Bloque |
|---|---|
| 1 | El botón era un comando |
| 2 | Local y origin: el líder publica, el equipo clona |
| 3 | Tu primer issue |
| 4 | El ritual diario y tu primer Pull Request |
| ☕ | Descanso |
| 5 | Las reglas de la casa |
| 6 | Historia limpia: amend, pull --rebase y squash |
| 7 | Conflictos en equipo |
| 8 | Ciclo completo sin red |
| | Cierre: no hay una sola forma correcta |

Al final de la guía está el **acordeón del ritual de trabajo en equipo**: la tabla de comandos para repasar el flujo por tu cuenta.

---

## <font color="#179287">Después de la clase: la tarea</font>

En equipo, elegirán una idea de proyecto, investigarán qué estrategia de trabajo colaborativo le conviene y la documentarán en su repositorio. Además, grabarán un video de 5 a 10 minutos explicándola.

**Es obligatoria, se entrega antes de la siguiente sesión y el video es necesario para acreditar los puntos de formación integral.**

👉 [Instrucciones completas de la tarea](material/tarea.md)

---

## <font color="#179287">Recursos para seguir practicando</font>

- Ayuda de GitHub CLI desde la terminal: `gh help` y `gh [comando] --help`
- [Pro Git en español](https://git-scm.com/book/es/v2): libro oficial y gratuito (capítulos 3, *Ramificaciones en Git*, y 5, *Git en entornos distribuidos*)
- [Documentación de GitHub](https://docs.github.com/es): flujos de trabajo, rulesets y métodos de merge
- [Oh My Git!](https://ohmygit.org/): juego visual para practicar, incluido el rebase
