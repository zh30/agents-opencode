AGENTS.md for agents-opencode

- Build/lint/test:
  - No build step required (Markdown-only repo)
  - Lint docs: markdownlint '**/*.md'
  - Spell/style check (optional): cspell '**/*'
  - Tests: none present; if adding tests use: npm test or pytest per language subdir
  - Run single test (if added):
    - Jest: npx jest path/to/file.test.ts -t "test name"
    - Vitest: npx vitest run path/to/file.test.ts -t "test name"
    - Pytest: pytest path/to/test_file.py -k "name"

- Code style guidelines for this repo’s Markdown agents:
  - Imports: N/A (Markdown). When adding code samples, prefer ESM imports for JS/TS
  - Formatting: 80-100 char lines, fenced code blocks with language tags, lists over long paragraphs
  - Types: In TS samples use strict types, explicit return types for public APIs
  - Naming: kebab-case filenames for agents (e.g., backend-architect.md); functions camelCase; Types PascalCase
  - Structure: Each agent file begins with frontmatter name/description/model/tools then a concise system prompt
  - Error handling in examples: prefer Result/Either or explicit try/catch; never swallow errors; log minimal context, no secrets
  - Conventions: avoid comments in prompts; be concise and directive; avoid leaking credentials or private URLs
  - Links: use full HTTPS URLs; avoid placeholders unless necessary
  - Cursor/Copilot rules: none found (.cursor/rules, .cursorrules, .github/copilot-instructions.md absent)
  - PRs/Commits: meaningful messages explaining why; no secrets; follow CODE_OF_CONDUCT and CONTRIBUTING
  - New agents: follow README Subagent Format; lower-case hyphenated name; specify model when relevant
