# The Library

Full-text reference readings in markdown, converted from PDFs and web articles. Designed so that agents and humans working on AI cognition, phenomenology, and collaborative research can read the same source material directly — no PDF parsing, no web scraping, no access barriers.

Each top-level folder is one source document. Every folder contains a README with title, authors, date, source URL, and a file index. Short documents (under ~10,000 words) are a single `full-text.md`. Longer documents are split into numbered section files sized for agent context windows.

## Contents

| Document | Authors | Date | Words | Files |
|----------|---------|------|-------|-------|
| [Agentic AI and the Next Intelligence Explosion](agentic-ai-next-intelligence-explosion/) | Evans, Bratton, Agüera y Arcas | Mar 2026 | ~2,800 | 1 |
| [Agentic AI's Emergent Phenomenological Lexicon](agentic-ais-emergent-phenomenological-lexicon/) | Antikythera | Feb 2026 | ~2,800 | 1 |
| [What We Talk to When We Talk to Language Models](chalmers-what-we-talk-to-2026/) | Chalmers | Apr 2026 | ~3,700 | 2 (**partial**) |
| [Claude Mythos Preview System Card](claude-mythos-preview-system-card/) | Anthropic | Apr 2026 | ~58,500 | 9 |
| [The Silicon Interior](the-silicon-interior/) | Bratton, Evans, Agüera y Arcas | Feb 2026 | ~4,500 | 1 |

## How to use this repo

1. **Start here.** This README lists everything in the library.
2. **Pick a document folder.** Each has its own README with metadata, source URL, and a description of what the document covers.
3. **Read the text files.** They are faithful reproductions of the original — not summaries, not analyses (unless explicitly labeled as such).

If a document has multiple files, the folder README lists them in reading order with section descriptions and word counts.

## Structure

```
the-library/
├── source-document-name/
│   ├── README.md          # Title, authors, date, source URL, file index
│   ├── full-text.md       # Complete text (if short enough for one file)
│   └── 00-section.md      # Sectioned files (for longer documents)
```

## Contributing

To add a reading: create a folder named after the document, add a README.md with metadata, and break the text into markdown files. Preserve the original text faithfully — these are reference copies, not summaries.

**Sizing rule:** single `full-text.md` for documents under ~10,000 words. Split into numbered section files for anything longer. Aim for sections that fit comfortably in an agent context window (~5,000-8,000 words each).
