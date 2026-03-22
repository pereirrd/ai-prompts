[English](README.md) | [Español](README.es.md)

# Prompts de README multilíngue

Esta pasta contém **prompts para usar com um assistente de IA** a fim de criar ou atualizar versões do `README` do projeto em **inglês**, **português brasileiro** e **espanhol**, com a mesma estrutura e um alternador de idioma no topo de cada arquivo.

## O que você obtém

Cada prompt descreve o fluxo completo: ler READMEs existentes se houver, manter paridade de seções entre idiomas, traduzir texto narrativo deixando código, caminhos e comandos intactos, e adicionar links no topo entre `README.md`, `README.pt-br.md` e `README.es.md`.

## Arquivos de prompt

| Idioma | Arquivo |
|--------|---------|
| Inglês | [`prompt/create-readme-multilang.en.md`](prompt/create-readme-multilang.en.md) |
| Português brasileiro | [`prompt/create-readme-multilang.pt-br.md`](prompt/create-readme-multilang.pt-br.md) |
| Espanhol | [`prompt/create-readme-multilang.es.md`](prompt/create-readme-multilang.es.md) |

Escolha o **mesmo idioma em que você conversa no chat** ao colar o prompt, para manter instruções e diálogo alinhados.

## Como usar

Os arquivos de prompt são Markdown simples, com **instruções autocontidas**. Esse formato é o que o Cursor espera para **comandos com barra (`/`)**, então você pode colar manualmente ou instalar uma vez e reutilizar com `/`.

### Uso manual (qualquer ferramenta de IA)

1. Abra o arquivo de prompt no idioma do seu interesse (veja a tabela acima).
2. Copie **tudo** o conteúdo (do título até a última seção).
3. Na sua ferramenta de IA, cole o prompt e forneça **contexto**:
   - Indique a **raiz do repositório** (ou anexe os arquivos relevantes).
   - Diga se já existem `README.md`, `README.pt-br.md` ou `README.es.md`, ou nenhum.
4. Execute o assistente e revise os três READMEs que ele criar ou atualizar.
5. Confira se o número de seções bate, os links internos funcionam e os blocos de código permanecem iguais.

### Como comando no Cursor

1. Abra o **projeto** em que você quer o comando (o repositório cujo README será editado).
2. Na **raiz** desse projeto, crie a pasta `.cursor/commands/` se ela ainda não existir.
3. Copie (ou crie um link simbólico para) um arquivo de prompt dentro de `.cursor/commands/`, com nome em **kebab-case** e extensão `.md`—por exemplo `create-readme-multilang.md`.  
   O **nome do arquivo sem `.md`** vira o comando com barra: `create-readme-multilang.md` → digite `/create-readme-multilang` no chat.
4. **Opcional — comandos globais:** coloque o mesmo `.md` em `~/.cursor/commands/` para o comando aparecer em todos os workspaces.
5. No **Chat** ou **Agent** do Cursor, digite `/`, escolha o comando para inserir o prompt inteiro, depois informe o contexto (raiz do repo, READMEs existentes, se houver) e execute.

O Cursor carrega comandos de `.cursor/commands/` (projeto) e de `~/.cursor/commands/` (usuário) quando você digita `/`.

## O que o assistente deve gerar

- **`README.md`** — Inglês (entrada padrão no GitHub); linha superior com links para português e espanhol.
- **`README.pt-br.md`** — Português brasileiro; linha superior com links para inglês e espanhol.
- **`README.es.md`** — Espanhol; linha superior com links para inglês e português.

Os três compartilham os mesmos títulos e layout; só o texto voltado ao leitor é traduzido.
