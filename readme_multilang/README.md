[Português](README.pt-br.md) | [Español](README.es.md)

# Multilingual README prompts

This folder holds **prompts you can give to an AI assistant** so it creates or updates **English**, **Brazilian Portuguese**, and **Spanish** versions of a project `README`, with matching structure and a language switcher at the top of each file.

## What you get

Each prompt describes the full workflow: read existing READMEs if present, keep section parity across languages, translate narrative text while leaving code, paths, and commands unchanged, and add top-of-file links between `README.md`, `README.pt-br.md`, and `README.es.md`.

## Prompt files

| Language | File |
|----------|------|
| English | [`prompt/create-readme-multilang.en.md`](prompt/create-readme-multilang.en.md) |
| Brazilian Portuguese | [`prompt/create-readme-multilang.pt-br.md`](prompt/create-readme-multilang.pt-br.md) |
| Spanish | [`prompt/create-readme-multilang.es.md`](prompt/create-readme-multilang.es.md) |

Pick the **same language you use in the chat** when you paste the prompt, so instructions and your conversation stay aligned.

## How to use

The prompt files are plain Markdown, written as **self-contained instructions**. That shape matches what Cursor expects for **custom slash commands**, so you can paste them manually or install them once and reuse them with `/`.

### Manual use (any AI tool)

1. Open the prompt file for your preferred language (see table above).
2. Copy **all** of its contents (from the title through the last section).
3. In your AI tool, paste the prompt and add **context**:
   - Point the model at your **repository root** (or attach the relevant files).
   - Say whether you already have `README.md`, `README.pt-br.md`, or `README.es.md`, or none.
4. Run the assistant and review the three README files it creates or updates.
5. Check that section counts match, internal links work, and code blocks are unchanged.

### Use as a Cursor command

1. Open the **project** where you want this command (the repo whose README you will edit).
2. At that project’s **root**, create a `.cursor/commands/` folder if it does not exist.
3. Copy (or symlink) one prompt file into `.cursor/commands/`, using a short **kebab-case** name and the `.md` extension—for example `create-readme-multilang.md`.  
   The **stem of the filename** (without `.md`) becomes the slash command: `create-readme-multilang.md` → type `/create-readme-multilang` in chat.
4. **Optional — global commands:** put the same `.md` under `~/.cursor/commands/` so the command is available in every workspace.
5. In **Cursor Chat** or **Agent**, type `/`, pick your command to insert the full prompt, then add context (open repo root, mention existing README files if any) and run.

Cursor loads commands from both `.cursor/commands/` (project) and `~/.cursor/commands/` (user) when you type `/`.

## What the assistant will produce

- **`README.md`** — English (default GitHub entry); top line links to Portuguese and Spanish.
- **`README.pt-br.md`** — Brazilian Portuguese; top line links to English and Spanish.
- **`README.es.md`** — Spanish; top line links to English and Portuguese.

All three share the same headings and layout; only human-facing prose is translated.
