# /crear_readme_multilang — Crear README multilingüe

Debes crear READMEs multilingües a partir del README actual del proyecto (o crear uno nuevo si no existe), generando versiones en inglés, portugués y español.

## Reglas de ejecución (obligatorias)

- **Lee el README existente**: si existen `README.md`, `README.pt-br.md` o `README.es.md`, lee el contenido actual para mantener coherencia.
- **Mantén la estructura**: todos los archivos deben tener la misma estructura y secciones.
- **Traduce por completo**: traduce todo el contenido conservando el formato markdown, bloques de código, enlaces y estructura.
- **Añade selector de idioma**: en la parte superior de cada archivo, añade enlaces a las otras versiones.

## Archivos a crear/actualizar

1. **README.md** (Inglés — contenido principal)
   - Enlace superior: `[Português](README.pt-br.md) | [Español](README.es.md)`
   - Contenido en inglés

2. **README.pt-br.md** (Portugués)
   - Enlace superior: `[English](README.md) | [Español](README.es.md)`
   - Contenido en portugués brasileño

3. **README.es.md** (Español)
   - Enlace superior: `[English](README.md) | [Português](README.pt-br.md)`
   - Contenido en español

## Estructura de los enlaces de cambio de idioma

Cada archivo debe empezar con una línea que contenga los enlaces a las otras versiones, seguida de una línea en blanco:

```markdown
[Idioma1](archivo1.md) | [Idioma2](archivo2.md)

# Título del proyecto
```

## Qué traducir

- **Títulos y subtítulos**: todos los niveles de encabezado
- **Párrafos**: todo el texto descriptivo
- **Listas**: ítems de listas ordenadas y no ordenadas
- **Notas y avisos**: alertas, notas importantes, etc.
- **Comentarios en código**: si hay comentarios en bloques de código relevantes para el lector

## Qué NO traducir

- **Nombres de archivos y rutas**: mantenerlos tal cual
- **Comandos de terminal**: mantener los comandos exactamente como están
- **Nombres de variables, clases y funciones**: mantener identificadores técnicos
- **Bloques de código**: mantener el código como está (salvo comentarios cuando aplique)
- **URLs y enlaces externos**: mantener las URLs tal cual
- **Nombres de tecnologías**: mantener nombres de frameworks, bibliotecas, etc., tal como se usan habitualmente

## Proceso de creación

1. **Lee el README actual** (si existe):
   - Si existe `README.md`, úsalo como base
   - Si solo existe `README.pt-br.md` o `README.es.md`, úsalo como base y traduce a los demás idiomas
   - Si no existe ninguno, crea un README básico según la estructura del proyecto

2. **Identifica la estructura**:
   - Enumera todas las secciones y subsecciones
   - Identifica bloques de código, listas, tablas, etc.

3. **Crea/actualiza los tres archivos**:
   - Mantén la misma estructura en todos
   - Traduce el contenido de forma adecuada
   - Añade los enlaces de cambio de idioma al inicio de cada archivo

4. **Verifica la coherencia**:
   - Todos los archivos deben tener el mismo número de secciones
   - Los enlaces internos deben funcionar en todos los idiomas
   - El formato markdown debe ser idéntico

## Resultado esperado

- Tres archivos README creados/actualizados:
  - `README.md` (Inglés) con enlaces a portugués y español
  - `README.pt-br.md` (Portugués) con enlaces a inglés y español
  - `README.es.md` (Español) con enlaces a inglés y portugués
- Todos con la misma estructura y contenido traducido de forma adecuada
- Enlaces de cambio de idioma operativos en la parte superior de cada archivo
