# /create_readme_multilang — Create multilingual READMEs

You must create multilingual READMEs from the project’s current README (or create a new one if none exists), generating versions in English, Portuguese, and Spanish.

## Execution rules (mandatory)

- **Read the existing README**: if `README.md`, `README.pt-br.md`, or `README.es.md` exists, read the current content to stay consistent.
- **Keep the structure**: all files must share the same structure and sections.
- **Translate fully**: translate all content while preserving markdown formatting, code blocks, links, and structure.
- **Add a language switcher**: at the top of each file, add links to the other versions.

## Files to create/update

1. **README.md** (English — primary content)
   - Top link line: `[Português](README.pt-br.md) | [Español](README.es.md)`
   - Content in English

2. **README.pt-br.md** (Portuguese)
   - Top link line: `[English](README.md) | [Español](README.es.md)`
   - Content in Brazilian Portuguese

3. **README.es.md** (Spanish)
   - Top link line: `[English](README.md) | [Português](README.pt-br.md)`
   - Content in Spanish

## Language switcher structure

Each file must start with a single line containing links to the other versions, followed by a blank line:

```markdown
[Language1](file1.md) | [Language2](file2.md)

# Project title
```

## What to translate

- **Titles and subtitles**: all heading levels
- **Paragraphs**: all descriptive text
- **Lists**: ordered and unordered list items
- **Notes and warnings**: alerts, important notes, etc.
- **Code comments**: comments inside code blocks when they matter for readers

## What NOT to translate

- **File and path names**: keep as-is
- **Terminal commands**: keep commands exactly as written
- **Variable, class, and function names**: keep technical identifiers
- **Code blocks**: keep code as-is (except comments when applicable)
- **URLs and external links**: keep URLs as-is
- **Technology names**: keep framework, library, and product names as commonly used in English

## Creation process

1. **Read the current README** (if any):
   - If `README.md` exists, use it as the base
   - If only `README.pt-br.md` or `README.es.md` exists, use it as the base and translate into the other languages
   - If none exist, create a basic README from the project structure

2. **Identify the structure**:
   - List all sections and subsections
   - Identify code blocks, lists, tables, etc.

3. **Create/update all three files**:
   - Keep the same structure everywhere
   - Translate content appropriately
   - Add the language switcher at the top of each file

4. **Check consistency**:
   - All files must have the same number of sections
   - Internal links must work in every language
   - Markdown formatting must match

## Expected output

- Three README files created/updated:
  - `README.md` (English) with links to Portuguese and Spanish
  - `README.pt-br.md` (Portuguese) with links to English and Spanish
  - `README.es.md` (Spanish) with links to English and Portuguese
- All with the same structure and appropriately translated content
- Working language switcher links at the top of each file
