[English](README.md) | [Español](README.es.md)

# Como usar comandos do Git para encontrar um bug

Guia prático para investigar e localizar bugs usando os comandos do Git para examinar o histórico e o estado do repositório.

**Prompt:** [Entrevista para encontrar bug com Git](prompt/prompt-interview-bug.pt-br.md)

---

## 1. `git status` — Estado atual

Verifica o estado do working tree e quais arquivos foram modificados.

```bash
git status
```

**Quando usar:** Primeiro passo para entender o que mudou desde o último commit. Útil para ver se o bug está em alterações não commitadas.

---

## 2. `git diff` — Ver alterações

Mostra diferenças entre commits, entre commit e working tree, ou entre arquivos.

```bash
# Diferenças entre working tree e índice (staged)
git diff

# Diferenças entre índice e último commit
git diff --staged

# Diferenças entre dois commits
git diff <commit-antigo> <commit-novo>

# Diferenças em um arquivo específico
git diff -- caminho/do/arquivo
```

**Quando usar:** Para analisar exatamente o que mudou em cada alteração e identificar trechos suspeitos.

---

## 3. `git log` — Histórico de commits

Exibe o histórico de commits com informações relevantes.

```bash
# Log resumido com uma linha por commit
git log --oneline

# Log com estatísticas de arquivos alterados
git log --stat

# Log mostrando o diff de cada commit
git log -p

# Log de um arquivo específico
git log -- caminho/do/arquivo

# Log com gráfico de branches
git log --oneline --graph --all
```

**Quando usar:** Para descobrir quando o bug pode ter sido introduzido e em quais commits houve mudanças relevantes.

---

## 4. `git show` — Detalhes de um objeto

Mostra informações detalhadas de um commit ou outro objeto Git.

```bash
# Detalhes do último commit (mensagem + diff)
git show

# Detalhes de um commit específico
git show <hash-do-commit>

# Apenas os arquivos alterados em um commit
git show --name-only <hash-do-commit>
```

**Quando usar:** Para inspecionar em detalhe um commit suspeito após identificá-lo no log.

---

## 5. `git grep` — Buscar padrões

Procura por texto ou padrões no código versionado.

```bash
# Buscar uma string em todos os arquivos
git grep "texto ou padrão"

# Buscar com contexto (linhas antes e depois)
git grep -n -C 2 "padrão"

# Buscar em um commit específico
git grep "padrão" <hash-do-commit>

# Buscar em uma branch específica
git grep "padrão" nome-da-branch
```

**Quando usar:** Para localizar onde uma variável, função ou mensagem de erro aparece no código.

---

## 6. `git bisect` — Busca binária para encontrar o commit do bug

Usa busca binária para encontrar o commit que introduziu o bug.

```bash
# Iniciar o bisect
git bisect start

# Marcar o commit atual como ruim (com bug)
git bisect bad

# Marcar um commit antigo como bom (sem bug)
git bisect good <hash-do-commit-bom>

# A cada iteração, testar e marcar:
git bisect good   # se o bug NÃO está presente
git bisect bad    # se o bug ESTÁ presente

# Finalizar quando encontrar o commit
git bisect reset
```

**Quando usar:** Quando você sabe que o bug existe agora e que em um commit antigo não existia. O bisect reduz o número de commits a testar.

### Bisect automático (com script de teste)

```bash
git bisect start HEAD <commit-bom>
git bisect run ./script-de-teste.sh
```

---

## Fluxo sugerido para encontrar um bug

1. **`git status`** — Ver o estado atual.
2. **`git log --oneline`** — Listar commits recentes.
3. **`git diff`** — Se houver alterações locais, ver o que mudou.
4. **`git show <commit>`** — Inspecionar commits suspeitos.
5. **`git grep "termo"`** — Localizar onde o termo aparece no código.
6. **`git bisect`** — Se o momento exato do bug for incerto, usar busca binária.

---

## Referências

- `git help revisions` — Sobre revisões e especificadores de commit
- `git help bisect` — Documentação completa do bisect
- `git help diff` — Opções avançadas do diff
