# /criar_readme_multilang — Criar README multi-idiomas

Você deve criar READMEs multi-idiomas a partir do README atual do projeto (ou criar um novo se não existir), gerando versões em Inglês, Português e Espanhol.

## Regras de execução (obrigatórias)

- **Leia o README existente**: se existir `README.md`, `README.pt-br.md` ou `README.es.md`, leia o conteúdo atual para manter consistência.
- **Mantenha a estrutura**: todos os arquivos devem ter a mesma estrutura e seções.
- **Traduza completamente**: traduza todo o conteúdo, mantendo formatação markdown, blocos de código, links e estrutura.
- **Adicione alternador de idioma**: no topo de cada arquivo, adicione links para as outras versões.

## Arquivos a criar/atualizar

1. **README.md** (Inglês - Conteúdo Principal)
   - Link no topo: `[Português](README.pt-br.md) | [Español](README.es.md)`
   - Conteúdo em inglês

2. **README.pt-br.md** (Português)
   - Link no topo: `[English](README.md) | [Español](README.es.md)`
   - Conteúdo em português brasileiro

3. **README.es.md** (Espanhol)
   - Link no topo: `[English](README.md) | [Português](README.pt-br.md)`
   - Conteúdo em espanhol

## Estrutura dos links de alternância

Cada arquivo deve começar com uma linha contendo os links para as outras versões, seguida de uma linha em branco:

```markdown
[Idioma1](arquivo1.md) | [Idioma2](arquivo2.md)

# Título do Projeto
```

## O que traduzir

- **Títulos e subtítulos**: todos os níveis de cabeçalho
- **Parágrafos**: todo o texto descritivo
- **Listas**: itens de listas ordenadas e não ordenadas
- **Notas e avisos**: textos de alerta, notas importantes, etc.
- **Comentários em código**: se houver comentários em blocos de código que sejam relevantes

## O que NÃO traduzir

- **Nomes de arquivos e caminhos**: mantenha como estão
- **Comandos de terminal**: mantenha os comandos exatamente como estão
- **Nomes de variáveis, classes, funções**: mantenha nomes técnicos
- **Blocos de código**: mantenha código como está (exceto comentários se aplicável)
- **URLs e links externos**: mantenha URLs como estão
- **Nomes de tecnologias**: mantenha nomes de frameworks, bibliotecas, etc.

## Processo de criação

1. **Leia o README atual** (se existir):
   - Se existir `README.md`, use como base
   - Se existir apenas `README.pt-br.md` ou `README.es.md`, use como base e traduza para os outros idiomas
   - Se não existir nenhum, crie um README básico baseado na estrutura do projeto

2. **Identifique a estrutura**:
   - Liste todas as seções e subseções
   - Identifique blocos de código, listas, tabelas, etc.

3. **Crie/atualize os três arquivos**:
   - Mantenha a mesma estrutura em todos
   - Traduza o conteúdo apropriadamente
   - Adicione os links de alternância no topo de cada arquivo

4. **Verifique consistência**:
   - Todos os arquivos devem ter o mesmo número de seções
   - Links internos devem funcionar em todos os idiomas
   - Formatação markdown deve ser idêntica

## Saída final esperada

- Três arquivos README criados/atualizados:
  - `README.md` (Inglês) com links para Português e Espanhol
  - `README.pt-br.md` (Português) com links para Inglês e Espanhol
  - `README.es.md` (Espanhol) com links para Inglês e Português
- Todos com a mesma estrutura e conteúdo traduzido apropriadamente
- Links de alternância de idioma funcionais no topo de cada arquivo
