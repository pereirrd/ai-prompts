[Español](README.es.md) | [Português](README.pt-br.md)

# How to use Git commands to find a bug

Practical guide to investigate and locate bugs using Git commands to examine repository history and state.

**Prompt:** [Interview to find bug with Git](prompt/prompt-interview-bug.md)

---

## 1. `git status` — Current state

Checks the state of the working tree and which files have been modified.

```bash
git status
```

**When to use:** First step to understand what has changed since the last commit. Useful to see if the bug is in uncommitted changes.

---

## 2. `git diff` — View changes

Shows differences between commits, between commit and working tree, or between files.

```bash
# Differences between working tree and index (staged)
git diff

# Differences between index and last commit
git diff --staged

# Differences between two commits
git diff <old-commit> <new-commit>

# Differences in a specific file
git diff -- path/to/file
```

**When to use:** To analyze exactly what changed in each modification and identify suspicious sections.

---

## 3. `git log` — Commit history

Displays commit history with relevant information.

```bash
# Summary log with one line per commit
git log --oneline

# Log with statistics of changed files
git log --stat

# Log showing the diff of each commit
git log -p

# Log of a specific file
git log -- path/to/file

# Log with branch graph
git log --oneline --graph --all
```

**When to use:** To discover when the bug may have been introduced and in which commits relevant changes occurred.

---

## 4. `git show` — Object details

Shows detailed information about a commit or other Git object.

```bash
# Details of the last commit (message + diff)
git show

# Details of a specific commit
git show <commit-hash>

# Only the files changed in a commit
git show --name-only <commit-hash>
```

**When to use:** To inspect in detail a suspicious commit after identifying it in the log.

---

## 5. `git grep` — Search patterns

Searches for text or patterns in versioned code.

```bash
# Search for a string in all files
git grep "text or pattern"

# Search with context (lines before and after)
git grep -n -C 2 "pattern"

# Search in a specific commit
git grep "pattern" <commit-hash>

# Search in a specific branch
git grep "pattern" branch-name
```

**When to use:** To locate where a variable, function, or error message appears in the code.

---

## 6. `git bisect` — Binary search to find the bug commit

Uses binary search to find the commit that introduced the bug.

```bash
# Start bisect
git bisect start

# Mark current commit as bad (with bug)
git bisect bad

# Mark an old commit as good (without bug)
git bisect good <good-commit-hash>

# At each iteration, test and mark:
git bisect good   # if the bug is NOT present
git bisect bad    # if the bug IS present

# Finish when the commit is found
git bisect reset
```

**When to use:** When you know the bug exists now and that it didn't exist in an old commit. Bisect reduces the number of commits to test.

### Automatic bisect (with test script)

```bash
git bisect start HEAD <good-commit>
git bisect run ./test-script.sh
```

---

## Suggested flow to find a bug

1. **`git status`** — See current state.
2. **`git log --oneline`** — List recent commits.
3. **`git diff`** — If there are local changes, see what changed.
4. **`git show <commit>`** — Inspect suspicious commits.
5. **`git grep "term"`** — Locate where the term appears in the code.
6. **`git bisect`** — If the exact moment of the bug is uncertain, use binary search.

---

## References

- `git help revisions` — About revisions and commit specifiers
- `git help bisect` — Complete bisect documentation
- `git help diff` — Advanced diff options
