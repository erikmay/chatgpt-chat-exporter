# AGENTS.md

Browser tools that export ChatGPT and Google Gemini conversations to Markdown, PDF, or HTML. Plain JavaScript, no build step, no tests.

- Each exporter (`exporter-markdown.js`, `exporter-pdf.js`, `exporter-html.js`, `gemini-exporter-markdown.js`) and userscript (`chatgpt-*-exporter.user.js`) is self-contained: users paste it into the browser console or install it as a userscript. A fix to shared logic must be applied in every file that has it.
- The `README.md` links these files by raw GitHub URL, so do not rename or move them.
- `core/` (selector cascade, DOM analyzer, message detector with confidence scores) is not imported by the exporters. `archived/` holds old exporter versions; `temporal/` holds old planning notes.
- Test an exporter by pasting it into the console on a real ChatGPT or Gemini conversation.
- When the ChatGPT or Gemini UI changes, prefer selectors in this order: data attributes (`[data-testid*="..."]`), ARIA roles, semantic elements, classes (last resort).
