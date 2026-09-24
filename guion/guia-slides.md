# Guía para armar las diapositivas: Sesión 2

> Guía orientativa para construir la presentación a partir de [`guion-instructor.md`](guion-instructor.md). Para cada bloque dice **qué diapositivas hacen falta, qué debe llevar cada una y qué visual la acompaña**. No es el texto final de las slides: es la lista de lo que no puede faltar.

---

## Criterios generales

- **Las slides acompañan, la terminal enseña.** La mayor parte de la clase ocurre en VS Code y GitHub.com. Las diapositivas sirven para abrir cada bloque (la pregunta), fijar la idea clave y dejar a la vista una referencia (tabla, comando, diagrama). No se proyectan pasos de clic en clic.
- **Una idea por slide.** Si una slide necesita dos frases clave, son dos slides.
- **Comandos en fuente monoespaciada y grandes.** Máximo 3 o 4 comandos por slide, cada uno con su traducción a lenguaje humano al lado.
- **Estructura repetible por bloque:** portada de bloque (número, título, pregunta que abre) → slides de contenido → slide de frase clave o diagrama → slide de transición (la pregunta que abre el siguiente bloque).
- **Pregunta de "¿dónde está esto?".** Conviene un icono o etiqueta fija de tres estados (💻 local / ☁️ origin / ambos) para reutilizar en las slides de comandos.
- **Recursos visuales disponibles:** logos en [`assets/logos/`](../assets/logos/) (Git, GitHub, UADY). Los diagramas Mermaid del guion se pueden exportar tal cual (mermaid.live) o redibujar.
- **Slides "fijas":** la tabla de traducción (Bloque 1), el ritual (Bloque 4) y el acordeón (Bloque 8) deben poder quedarse proyectadas varios minutos mientras los alumnos trabajan: letra grande y sin animaciones.

**Conteo estimado:** 45 a 55 diapositivas.

---

## Apertura (2 a 3 slides)

### Slide 0.1: Portada
- Título: *Git y GitHub en equipo, desde la terminal*. Subtítulo: Sesión 2, intensiva de 4 horas.
- Logos de UADY, Git y GitHub. Nombre del instructor.

### Slide 0.2: Reglas del juego de hoy
- Tres ideas: cero código, cero botones de Desktop, todo lo escrito es Markdown.
- Reparto de herramientas: **terminal** (git, gh) para lo que pasa en tu compu · **GitHub.com** para configurar y revisar · **VS Code** (Graph, GitLens) para mirar.
- Frase: *"La terminal no es el tema, es el volante."*

### Slide 0.3: Mapa de la sesión
- Los 8 bloques + descanso + cierre, con su duración (versión simplificada de la tabla del storyboard).
- Opcional: marcar con color las dos mitades (antes y después del descanso).

> Antes de pasar al Bloque 1: verificar `gh auth status` en todas las máquinas. Se puede dejar una slide de "check-in" con ese comando.

---

## Bloque 1: El botón era un comando (4 a 5 slides)

### Slide 1.1: Portada de bloque + gancho
- Captura de GitHub Desktop con el botón **Push origin** resaltado.
- Pregunta grande: *"¿Qué hace este botón cuando lo presionan?"*
- Siguiente clic (animación): `git push origin`. *"Hoy le quitamos el disfraz."*

### Slide 1.2: Primeros comandos
- `git --version`, `gh auth status`, `git config user.name`, cada uno con lo que responde.
- Nota: el nombre ya lo configuró GitHub Desktop; Desktop y la terminal usan el mismo Git.
- Frase clave: *"La terminal no es más difícil, es más honesta."*

### Slide 1.3: El ciclo del commit, en texto
- Secuencia vertical con su equivalente en Desktop:
  `git init` (New Repository) → `git status` (panel Changes) → `git add` (marcar la casilla) → `git commit -m` (Summary + Commit) → `git log --oneline` (History) → `git diff`.
- Visual: mini captura de la terminal con `status` en rojo y luego en verde.

### Slide 1.4: Tabla de traducción Desktop → terminal (slide fija)
- La tabla completa del guion (14 filas). Es la slide que queda visible el resto del bloque, así que debe leerse desde el fondo del salón.

### Slide 1.5: Repaso de ramas + cierre
- `git switch -c prueba` / `git switch main`: el cambio aparece y desaparece.
- Captura de la vista **Graph** nativa de VS Code con la bifurcación.
- Diagrama: *Botón en Desktop → comando de git ← tú en la terminal*.
- Frase de cierre: *"Este repo es solo suyo: es su cuaderno de práctica."*
- Transición: *"Hay dos copias del repo. ¿Cuál es la de verdad?"*

---

## Bloque 2: Local y origin (6 a 7 slides)

### Slide 2.1: Portada de bloque
- Pregunta: *"Cuando el repo sube a GitHub, ¿cuál es la copia de verdad?"*
- Roles: **líder** publica, **equipo** clona.

### Slide 2.2: El líder prepara la base
- Qué lleva el README del equipo: título, tabla *Integrantes* (solo encabezado: Nombre, Carrera, Usuario de GitHub), sección "Formato del perfil".
- Las dos plantillas que se copian del material: `.github/ISSUE_TEMPLATE/tarea.md` y `.github/pull_request_template.md`.
- `git add .` + `git commit`. Advertencia: revisar `git status` antes de `add .`.

### Slide 2.3: Crear el repo en GitHub, vacío
- Captura del formulario *New repository*: **Public**, **sin** README, .gitignore ni licencia (marcar en rojo las casillas que NO se tocan).
- Frase: *"Tiene que nacer vacío: la historia ya existe en su compu."*

### Slide 2.4: Los tres comandos de publicar
- `git remote add origin …` → *"le presento a mi repo su dirección en internet"*
- `git branch -M main` → *"le pongo el nombre que GitHub espera"*
- `git push -u origin main` → *"subo main y la amarro con la de origin"*
- Frase: *"Subió la historia completa. Y no subió `prueba`: solo sube lo que tú le dices."*

### Slide 2.5: Colaboradores y clonar
- Líder: `Settings → Collaborators → Add people`. Equipo: aceptar invitación.
- Equipo: `cd ..` + `gh repo clone lider/equipo-[nombre]`.
- Frase: *"Clonar es el único momento en que no hacen `git init`."*

### Slide 2.6: `main` vs `origin/main` (slide central del bloque)
- Diagrama del guion: tu compu (archivos, `main`, `origin/main`) y GitHub (`main` real), con las flechas add/commit, push, fetch, pull.
- Definición grande: **`main` es tu rama; `origin/main` es la foto que tu compu tiene de GitHub.**
- Contraste: `git remote -v` en el repo del equipo vs. en `practica-terminal` (no responde nada).

### Slide 2.7: La foto vieja
- Secuencia: `git status` dice *"up to date"* → pregunta *"¿es verdad?"* → `git fetch` → *"behind by 1 commit"* → `git pull`.
- Frase clave: *"`git status` no le pregunta a GitHub, le pregunta a tu foto de GitHub. `fetch` actualiza la foto; `pull` además trae los cambios."*
- Transición: *"¿Quién decide qué hay que hacer y quién lo hace?"*

---

## Bloque 3: Tu primer issue (3 a 4 slides)

### Slide 3.1: Portada + analogía
- Imagen de una **comanda** de cocina.
- *"Nadie cocina un platillo sin comanda; nadie trabaja algo sin issue."*
- Partes de un issue: título, descripción, responsable, número `#N`.

### Slide 3.2: Crear el issue
- Pasos en GitHub.com: Issues → New issue → plantilla **Tarea** → título `Agregar perfil de [nombre]` → las dos preguntas → **Assign yourself** → Create.
- Captura del formulario con la plantilla.
- Terminal: `gh issue list` (y `gh issue create` como alternativa). *"Anoten su número."*

### Slide 3.3: La configuración es un archivo
- Captura del encabezado de `tarea.md` (líneas entre `---`: `name`, `about`) junto al menú de GitHub donde aparece "Tarea".
- Idea: lo que está en `.github/` configura GitHub y viaja con el repo.

### Slide 3.4: Del issue al cierre (diagrama)
- *Issue #3 → rama → Pull Request → issue cerrado automáticamente.*
- Transición: *"El ritual que van a repetir cada vez que se sienten a trabajar."*

---

## Bloque 4: El ritual diario + primer PR (7 a 8 slides)

### Slide 4.1: Portada + el ritual en tres momentos (slide fija)
- **Antes:** ponerse al día. **Durante:** commits pequeños y mirar dónde estás. **Después:** subir, pedir revisión, integrar, limpiar.
- Diseño en tres columnas; se queda proyectada durante el bloque.

### Slide 4.2: Antes de empezar
- `git switch main` → *"me paro en la base"*
- `git pull` → *"me pongo al día"*
- `git switch -c feature/3-perfil-ana` → *"abro mi desvío desde un main fresco"*
- Anatomía del nombre de rama: `feature` / número de issue / descripción.
- Frase: *"Main es la mesa donde se sirve, no la tabla donde se corta."*

### Slide 4.3: Durante
- `git status` · `git add` · `git commit -m "docs: …"` · `git diff` · `git log --oneline --graph`.
- Mini tabla de prefijos: `docs:` documentos, `fix:` correcciones, `feat:` algo nuevo.
- Frase: *"Commits pequeños y seguidos: son tus puntos de guardado."*

### Slide 4.4: Subir y abrir el PR
- `git push -u origin feature/3-perfil-ana` (qué hace el `-u`).
- `gh pr create --web` → captura del formulario con la plantilla.
- Remarcar: el **título del PR** usa la convención de commits (será historia de `main`) y `Closes #3` cierra el issue.
- Alternativa en una línea: `gh pr create --base main --title "…" --body "Closes #3"`.

### Slide 4.5: Revisar el PR de un compañero
- Rotación: cada quien revisa al de su derecha.
- Capturas: pestaña **Files changed**, el `+` azul para comentar, **Review changes → Approve**.

### Slide 4.6: Integrar y limpiar
- En la web: **Merge pull request** + **Delete branch**; el issue se cerró solo.
- En la terminal: `git switch main` · `git pull` · `git branch -d …` · `git fetch --prune`.
- Frase: *"Una rama es un desvío temporal."*

### Slide 4.7: Foto mental de la historia
- Diagrama gitGraph del guion (dos PR con merge commit) o captura real del `git log --oneline --graph` con los *"Merge pull request #…"*.
- Texto: *"Tómenle foto mental; en el Bloque 6 la vamos a comparar."*

### Slide 4.8: GitLens, "¿quién escribió esto?"
- Tres capturas pequeñas: **Current Line Blame**, **hover** con la tarjeta del commit, **CodeLens**.
- Recuadro de advertencia: botones que **no** se usan hoy (*Explain*, *Connect to GitHub*, *Revert*, *Reset*, *Rebase*…).
- Frase: *"GitLens solo mira."*
- Transición: *"¿Qué impide el atajo y qué mantiene la historia legible?"*

**Slide de descanso:** 10 minutos, con un reloj o la hora de regreso.

---

## Bloque 5: Las reglas de la casa (6 a 7 slides)

### Slide 5.1: Portada + la puerta abierta
- Captura de la terminal: commit directo en `main` y `git push` que **funciona**.
- Frase: *"Nadie revisó esto. Nadie sabe por qué se hizo."*

### Slide 5.2: Cómo entra el trabajo (Settings → General)
- Captura de la sección *Pull Requests*: solo **Allow squash merging**; *Default commit message* = **Pull request title and description**; **Automatically delete head branches**.
- Explicación de squash en una línea: *todos los commits de la rama entran a main como uno solo, con `(#número)`*.

### Slide 5.3: El ruleset `proteger-main`
- Captura del ruleset con las casillas marcadas.
- Tabla de traducción regla → lenguaje de equipo:
  - Restrict deletions → "nadie borra main"
  - Block force pushes → "nadie reescribe main"
  - Require linear history → "main es una línea recta"
  - Require a pull request (1 aprobación) → "todo entra por PR con un visto bueno"

### Slide 5.4: Ni el dueño
- Captura del rechazo (*"Repository rule violations"*).
- Frase: *"La regla no es para desconfiar de alguien, es para que nadie tenga que acordarse."*
- Comando de limpieza `git reset --hard origin/main`, con advertencia visible: **tira lo local**.

### Slide 5.5: Contratar al robot
- Idea sin código: *"Una receta: en cada PR, GitHub presta una compu, sigue la receta y reporta."*
- Ruta: Actions → set up a workflow yourself → `revision.yml` → pegar la receta del material.
- Captura del check **Sin marcadores de conflicto** corriendo y en verde. Nota: *"Hasta el robot entró por PR"* (el botón ya dice **Squash and merge**).

### Slide 5.6: Hacer obligatorio al robot
- Ruleset: **Require status checks to pass** + **Require branches to be up to date**.
- Traducción: "el robot tiene que dar el visto bueno" / "tu rama tiene que estar al día con main".
- Capturas de la demo: X roja y merge bloqueado → palomita verde y merge habilitado. Comandos: `gh run list`, `gh pr checks`.

### Slide 5.7: El camino de un PR (diagrama)
- Flowchart del guion: push directo rechazado vs. rama + PR → ¿aprobación? → ¿robot verde? → ¿al día? → squash.
- Transición: *"Tu rama nace fresca y envejece sola. ¿Cómo la pongo al día sin ensuciar la historia?"*

---

## Bloque 6: Historia limpia (8 a 9 slides)

### Slide 6.1: Portada + la meta
- Idea central: **un PR = un commit en `main`**, con título claro y `(#N)` que lleva al PR.
- Las cuatro herramientas en línea de tiempo: commits pequeños → `amend` → `pull --rebase` → squash.

### Slide 6.2: Nueva tarea y el fast-forward
- Ritual completo para el issue *"Agregar mi ritual de trabajo"*.
- Captura de `git pull` respondiendo **Fast-forward**. Frase: *"main solo avanza hacia adelante."*

### Slide 6.3: `amend`, el commit con un olvido
- Antes/después: la tentación (`"ya ahora sí"`) vs. `git commit --amend --no-edit`.
- Variante para cambiar el mensaje: `git commit --amend -m "…"`.
- Detalle visual: el hash cambia. *"No lo editaste: lo reemplazaste."*
- Frase: *"Amend es gratis mientras el commit no haya salido de tu compu."*

### Slide 6.4: "This branch is out-of-date"
- Captura del aviso en el PR y del botón **Update branch** tachado.
- Motivo: ese botón mete un merge (un nudo) dentro de tu rama.

### Slide 6.5: La analogía del post-it
- Dos ilustraciones lado a lado:
  - **merge:** otro post-it encima que dice "aquí junté lo nuevo" → nudos.
  - **rebase:** despegas tu post-it, cambias la hoja de abajo, lo vuelves a pegar → línea recta.

### Slide 6.6: Ejecutar el rebase
- Diagramas antes / después de `git pull --rebase origin main` (los dos gitGraph del guion).
- Secuencia: `git pull --rebase origin main` → `git push` **rechazado** (¿por qué?) → `git push --force-with-lease`.
- Traducción del `--force-with-lease`: *"empuja a la fuerza, pero solo si nadie más tocó mi rama"*.

### Slide 6.7: Squash and merge
- Captura de la caja de confirmación: título del PR + `(#número)`, descripción con `Closes #`.
- Frase: *"Esto es lo que va a quedar escrito en main para siempre."*
- Comparación lado a lado: el log del Bloque 4 (nudos) vs. el de ahora (línea recta, un commit por PR).

### Slide 6.8: La pista no se perdió + limpieza
- Tres niveles: **main cuenta el qué · el PR cuenta el cómo · el issue cuenta el porqué.**
- Captura del hover de GitLens con el `(#número)` y **Open Commit on GitHub**; comando `gh pr view [número] --web`.
- Limpieza: `git branch -d` falla (*not fully merged*), por qué, y `git branch -D` tras confirmar que el PR dice **Merged**.

### Slide 6.9: Reglas de oro + mapa de decisiones
- Cuatro reglas de oro (solo historia propia, nunca `--force` a secas, una rama un PR, `git rebase --abort` si algo sale raro).
- Tabla *Situación / Herramienta / ¿Reescribe historia?* (7 filas del guion). Puede ir en slide aparte.
- Remate: `git config --global pull.rebase true`, *"ahora que saben qué significa"*.
- Transición: *"¿Qué hace Git cuando dos personas tocan la misma línea?"*

---

## Bloque 7: Conflictos en equipo (6 a 7 slides)

### Slide 7.1: Portada + la tarea que garantiza el choque
- Todos agregan **su fila** a la tabla *Integrantes* del README, en el mismo lugar.
- Captura del aviso en el PR: *"This branch has conflicts that must be resolved"*.

### Slide 7.2: CONFLICT no es un error
- Captura de la terminal con `CONFLICT` y de `git status` a mitad del rebase (sugiere `--continue` / `--abort`).
- Frase: *"Git no se rompió. Se detuvo a preguntarte algo que no puede decidir solo."*

### Slide 7.3: Leer el conflicto en VS Code
- Captura del archivo con `<<<<<<<` / `=======` / `>>>>>>>` y los botones Accept Current / Incoming / Both / Merge Editor.
- Recordatorio: dos borradores del mismo párrafo.

### Slide 7.4: ⚠️ Las etiquetas se invierten en un rebase
- Slide de advertencia, muy visible, **antes** de que abran el editor:
  - *Current* = lo que ya está en main (la fila del compañero).
  - *Incoming* = tu commit que se está volviendo a pegar.
- Respuesta de este ejercicio: **Accept Both**.

### Slide 7.5: Terminar el rebase
- `git add README.md` → *"ya resolví este archivo"*
- `git rebase --continue` → cerrar el editor del mensaje (pestaña de VS Code, o `:wq` + Enter si es Vim).
- `git push --force-with-lease`
- Botón de pánico siempre visible: `git rebase --abort`.

### Slide 7.6: Resultado: sigue siendo una línea recta
- gitGraph del guion (fila de Ana, rama de Luis tras el rebase, squash).
- Nota del robot: si quedó un marcador olvidado, se pone en rojo; para eso lo contrataron.

### Slide 7.7: Integrar en cadena + File Blame
- Los siguientes PR vuelven a chocar: cada autor resuelve solo.
- Captura de **GitLens: Toggle File Blame** sobre la tabla: cada fila con su autor y su `(#número)`.
- Frase: *"Cuatro personas en paralelo, con conflictos, y main sigue siendo una línea recta."*
- Transición: *"Mañana, solos, ¿saben qué hacer primero?"*

---

## Bloque 8: Ciclo completo sin red (3 slides)

### Slide 8.1: La consigna
- *"Cada quien crea un issue para otra persona, y cada quien resuelve el que le asignaron. Solo con el acordeón."*
- Tema: `recomendaciones/[tu-nombre].md` (libro, video o canal).
- Comandos útiles: `gh issue create --assignee …`, `gh issue list --assignee @me`.

### Slide 8.2: Acordeón del ritual diario (slide fija, también se entrega)
- La tabla completa del guion agrupada por **Antes / Durante / Después / Pánico**. Probablemente necesite dos slides o un diseño muy compacto; conviene también entregarla en PDF.
- Diagrama circular del ciclo (Issue → switch + pull → rama → commits → rebase → push → PR → squash → limpieza → Issue).

### Slide 8.3: Limpieza final y la prueba
- Checklist: `git switch main`, `git pull`, `git branch` (solo `main`), `git fetch --prune`, Issues cerrados, PR vacíos.
- La prueba: `git log --oneline` desde el Bloque 5 = un PR por línea. Un *"ya ahora sí"* o un *"Merge branch…"* significa que algo del ritual se saltó.

---

## Cierre (5 a 6 slides)

### Slide C.1: El recorrido
- Captura de la **Graph** real de un equipo, anotada de abajo hacia arriba con el bloque que produjo cada tramo: `git init` → publicación → nudos de los perfiles → entra el robot → línea recta (rebase y conflictos).
- Mensaje: la mitad de abajo contra la mitad de arriba.

### Slide C.2: Lo de hoy es *una* estrategia
- Cita grande: *"Es una estrategia. No es la definitiva ni la correcta. Es una de muchas."*
- Lista de lo que se eligió hoy: issue por tarea, rama por issue, aprobación obligatoria, robot, rebase, squash.

### Slide C.3: ¿Qué cambiaría sus reglas?
- Tabla de factores (tamaño del equipo, vida del proyecto, tiempo, burocracia, trazabilidad, costo del error, frecuencia de entrega, experiencia) con las columnas *menos reglas / más reglas*.
- Puede revelarse fila por fila para ir preguntando.

### Slide C.4: Tres ejemplos + alternativas
- Proyecto personal (directo en `main`), hackatón de 48 h (ramas cortas, sin aprobación), producto con usuarios (más revisores, etiquetas, pruebas).
- Alternativas legítimas: rebase merging, merge commits, sin protección.
- Frase: *"Un botón les da una sola forma; la terminal les da todas. Las reglas están para servirle al equipo."*

### Slide C.5: La tarea
- **Qué:** proyecto propio, ≥3 estrategias de trabajo y ≥2 formas de integrar, elegir y justificar en `docs/soporte/workflow_y_politicas_de_trabajo_colaborativo.md`.
- **Cómo:** con el flujo de trabajo (issue, rama, PR); el historial cuenta.
- **Lo que casi nadie hace:** documentar las reglas que decidieron **no** tener y ajustar la configuración del repo.
- **Video:** 5 a 10 min, con slides y todos los integrantes; explicar, no leer.
- **Fecha:** antes del siguiente sesión. **Sin video no se acreditan los puntos.** (Destacado en color.)
- Referencia: [`material/tarea.md`](../material/tarea.md).

### Slide C.6: Recursos y despedida
- Recursos: `gh help`, docs de GitHub (flujos, rulesets, métodos de merge), Pro Git en español, Oh My Git!.
- Recordatorio: `practica-terminal` es su repo para equivocarse sin consecuencias.
- Frase final: *"Lo que aprendieron hoy no es Git, es trabajo en equipo."*
- Preguntas (o como issues en el repo del curso).

---

## Slides de respaldo (opcionales, al final del deck)

Útiles para no improvisar si surge el problema; no se proyectan salvo que haga falta.

- **"Please tell me who you are":** `git config --global user.name` / `user.email`.
- **Repo creado con README por error:** Settings → Danger Zone → borrar y crear de nuevo vacío.
- **Me perdí en mi copia del equipo:** borrar la carpeta y `gh repo clone` otra vez (no aplica al líder antes de su primer push).
- **Por qué squash y no merge commit ni rebase merging:** comparación de las tres opciones en tres columnas.
- **Rama reutilizada tras un squash:** por qué choca y cómo salir (rama nueva desde `main`).
- **Atajos para adelantados:** `gh issue develop [número] --checkout`, `gh pr merge --squash --delete-branch`.
- **Fuera de esta sesión:** `rebase -i`, `stash`, `cherry-pick`, `reflog`, tags y releases.
