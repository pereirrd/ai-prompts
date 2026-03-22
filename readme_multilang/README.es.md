[English](README.md) | [Português](README.pt-br.md)

# Prompts de README multilingüe

Esta carpeta contiene **prompts para usar con un asistente de IA** y así crear o actualizar versiones del `README` del proyecto en **inglés**, **portugués brasileño** y **español**, con la misma estructura y un selector de idioma en la parte superior de cada archivo.

## Qué obtienes

Cada prompt describe el flujo completo: leer READMEs existentes si los hay, mantener la paridad de secciones entre idiomas, traducir el texto narrativo sin alterar código, rutas y comandos, y añadir enlaces en la parte superior entre `README.md`, `README.pt-br.md` y `README.es.md`.

## Archivos de prompt

| Idioma | Archivo |
|--------|---------|
| Inglés | [`prompt/create-readme-multilang.en.md`](prompt/create-readme-multilang.en.md) |
| Portugués brasileño | [`prompt/create-readme-multilang.pt-br.md`](prompt/create-readme-multilang.pt-br.md) |
| Español | [`prompt/create-readme-multilang.es.md`](prompt/create-readme-multilang.es.md) |

Elige el **mismo idioma en el que hablas en el chat** al pegar el prompt, para que las instrucciones y la conversación coincidan.

## Cómo usarlo

Los archivos de prompt son Markdown sencillo, con **instrucciones autocontenidas**. Ese formato coincide con lo que Cursor espera para **comandos con barra (`/`)**, así que puedes pegarlos a mano o instalarlos una vez y reutilizarlos con `/`.

### Uso manual (cualquier herramienta de IA)

1. Abre el archivo de prompt en el idioma que prefieras (ver tabla arriba).
2. Copia **todo** el contenido (desde el título hasta la última sección).
3. En tu herramienta de IA, pega el prompt y aporta **contexto**:
   - Indica la **raíz del repositorio** (o adjunta los archivos relevantes).
   - Indica si ya existen `README.md`, `README.pt-br.md` o `README.es.md`, o ninguno.
4. Ejecuta el asistente y revisa los tres README que cree o actualice.
5. Comprueba que el número de secciones coincida, que los enlaces internos funcionen y que los bloques de código no hayan cambiado.

### Uso como comando en Cursor

1. Abre el **proyecto** donde quieras el comando (el repositorio cuyo README vas a editar).
2. En la **raíz** de ese proyecto, crea la carpeta `.cursor/commands/` si no existe.
3. Copia (o crea un enlace simbólico a) un archivo de prompt dentro de `.cursor/commands/`, con un nombre corto en **kebab-case** y extensión `.md`—por ejemplo `create-readme-multilang.md`.  
   El **nombre del archivo sin `.md`** se convierte en el comando con barra: `create-readme-multilang.md` → escribe `/create-readme-multilang` en el chat.
4. **Opcional — comandos globales:** coloca el mismo `.md` en `~/.cursor/commands/` para que el comando esté disponible en todos los workspaces.
5. En el **Chat** o **Agent** de Cursor, escribe `/`, elige el comando para insertar el prompt completo y luego añade contexto (raíz del repo, READMEs existentes, etc.) y ejecuta.

Cursor carga comandos desde `.cursor/commands/` (proyecto) y desde `~/.cursor/commands/` (usuario) cuando escribes `/`.

## Qué debe generar el asistente

- **`README.md`** — Inglés (entrada estándar en GitHub); línea superior con enlaces al portugués y al español.
- **`README.pt-br.md`** — Portugués brasileño; línea superior con enlaces al inglés y al español.
- **`README.es.md`** — Español; línea superior con enlaces al inglés y al portugués.

Los tres comparten los mismos encabezados y disposición; solo se traduce el texto dirigido al lector.
