[English](README.md) | [Português](README.pt-br.md)

# Cómo usar comandos de Git para encontrar un bug

Guía práctica para investigar y localizar bugs usando los comandos de Git para examinar el historial y el estado del repositorio.

**Prompt:** [Entrevista para encontrar bug con Git](prompt/prompt-interview-bug.es.md)

---

## 1. `git status` — Estado actual

Comprueba el estado del árbol de trabajo y qué archivos han sido modificados.

```bash
git status
```

**Cuándo usar:** Primer paso para entender qué ha cambiado desde el último commit. Útil para ver si el bug está en cambios no confirmados.

---

## 2. `git diff` — Ver cambios

Muestra diferencias entre commits, entre commit y árbol de trabajo, o entre archivos.

```bash
# Diferencias entre árbol de trabajo e índice (staged)
git diff

# Diferencias entre índice y último commit
git diff --staged

# Diferencias entre dos commits
git diff <commit-antiguo> <commit-nuevo>

# Diferencias en un archivo específico
git diff -- ruta/del/archivo
```

**Cuándo usar:** Para analizar exactamente qué cambió en cada modificación e identificar fragmentos sospechosos.

---

## 3. `git log` — Historial de commits

Muestra el historial de commits con información relevante.

```bash
# Log resumido con una línea por commit
git log --oneline

# Log con estadísticas de archivos modificados
git log --stat

# Log mostrando el diff de cada commit
git log -p

# Log de un archivo específico
git log -- ruta/del/archivo

# Log con gráfico de ramas
git log --oneline --graph --all
```

**Cuándo usar:** Para descubrir cuándo pudo haberse introducido el bug y en qué commits hubo cambios relevantes.

---

## 4. `git show` — Detalles de un objeto

Muestra información detallada de un commit u otro objeto Git.

```bash
# Detalles del último commit (mensaje + diff)
git show

# Detalles de un commit específico
git show <hash-del-commit>

# Solo los archivos modificados en un commit
git show --name-only <hash-del-commit>
```

**Cuándo usar:** Para inspeccionar en detalle un commit sospechoso después de identificarlo en el log.

---

## 5. `git grep` — Buscar patrones

Busca texto o patrones en el código versionado.

```bash
# Buscar una cadena en todos los archivos
git grep "texto o patrón"

# Buscar con contexto (líneas antes y después)
git grep -n -C 2 "patrón"

# Buscar en un commit específico
git grep "patrón" <hash-del-commit>

# Buscar en una rama específica
git grep "patrón" nombre-de-la-rama
```

**Cuándo usar:** Para localizar dónde aparece una variable, función o mensaje de error en el código.

---

## 6. `git bisect` — Búsqueda binaria para encontrar el commit del bug

Usa búsqueda binaria para encontrar el commit que introdujo el bug.

```bash
# Iniciar bisect
git bisect start

# Marcar el commit actual como malo (con bug)
git bisect bad

# Marcar un commit antiguo como bueno (sin bug)
git bisect good <hash-del-commit-bueno>

# En cada iteración, probar y marcar:
git bisect good   # si el bug NO está presente
git bisect bad    # si el bug ESTÁ presente

# Finalizar cuando se encuentre el commit
git bisect reset
```

**Cuándo usar:** Cuando sabes que el bug existe ahora y que en un commit antiguo no existía. Bisect reduce el número de commits a probar.

### Bisect automático (con script de prueba)

```bash
git bisect start HEAD <commit-bueno>
git bisect run ./script-de-prueba.sh
```

---

## Flujo sugerido para encontrar un bug

1. **`git status`** — Ver el estado actual.
2. **`git log --oneline`** — Listar commits recientes.
3. **`git diff`** — Si hay cambios locales, ver qué cambió.
4. **`git show <commit>`** — Inspeccionar commits sospechosos.
5. **`git grep "término"`** — Localizar dónde aparece el término en el código.
6. **`git bisect`** — Si el momento exacto del bug es incierto, usar búsqueda binaria.

---

## Referencias

- `git help revisions` — Sobre revisiones y especificadores de commit
- `git help bisect` — Documentación completa de bisect
- `git help diff` — Opciones avanzadas de diff
