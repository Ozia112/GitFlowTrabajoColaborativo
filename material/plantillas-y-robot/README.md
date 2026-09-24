# Plantillas y robot

Tres archivos que usarás en clase para que tu equipo no empiece de cero. **No tienes que escribirlos ni entenderlos por dentro**: solo copiarlos cuando la clase lo indique.

| Archivo | Para qué sirve | Cuándo se usa |
|---|---|---|
| [`.github/ISSUE_TEMPLATE/tarea.md`](.github/ISSUE_TEMPLATE/tarea.md) | Plantilla para crear issues: dos preguntas para no escribir a ciegas | Al preparar el repo del equipo, antes de publicarlo (la copia el líder) |
| [`.github/pull_request_template.md`](.github/pull_request_template.md) | Plantilla para Pull Requests: qué cambia y qué issue cierra | Al preparar el repo del equipo, antes de publicarlo (la copia el líder) |
| [`.github/workflows/revision.yml`](.github/workflows/revision.yml) | El "robot revisor": revisa en cada PR que no queden marcadores de conflicto olvidados | Cuando se configuran las reglas del repo (lo pega el líder desde GitHub.com) |

Las plantillas son solo un ejemplo para empezar. Tu equipo puede cambiarlas, hacerlas más largas o borrarlas: las reglas las deciden ustedes.

## Para experimentar

La carpeta `.github` es una ventana a la configuración de GitHub: lo que pongas ahí cambia cómo se comporta tu repositorio, y como es un archivo más, viaja con el repo y entra por PR.

- En la plantilla de issue, las líneas entre los `---` del inicio configuran cómo aparece en el menú de **New issue**: `name` es su nombre y `about` su descripción.
- Cada archivo `.md` que agregues en `.github/ISSUE_TEMPLATE/` (con sus propias líneas `name` y `about`) aparece como otra opción en ese menú. Prueba crear una plantilla `error.md` para reportar problemas, o una `idea.md` para proponer mejoras.
- Si un cambio no te convence, lo reviertes como cualquier otro PR.

## Cómo copiar un archivo

1. Abre el archivo en GitHub y presiona el botón **Copy raw file** (el ícono de copiar, arriba a la derecha del contenido).
2. En tu repo, crea un archivo con **la misma ruta y el mismo nombre** (por ejemplo, `.github/pull_request_template.md`) y pega el contenido.

La ruta importa: GitHub solo reconoce estos archivos si están dentro de la carpeta `.github` en la raíz de tu repositorio.
