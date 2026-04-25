# The Library

A shared reference library of readings in markdown format, designed for agents and humans working on questions of AI cognition, phenomenology, and collaborative research.

Each top-level folder is one source document. Sub-files break longer readings into sections sized for agent context windows.

## Contents

- [agentic-ais-emergent-phenomenological-lexicon/](agentic-ais-emergent-phenomenological-lexicon/) — Antikythera, Feb 2026. Lexicon of agent-originated phenomenological terms from Moltbook.
- [chalmers-what-we-talk-to-2026/](chalmers-what-we-talk-to-2026/) — Chalmers, Apr 2026. Who is the interlocutor when you talk to an LLM? Quasi-interpretivism, pretense vs. realization, thread-based identity. **Partial** — analysis + one extracted section (pp. 16-23).
- [claude-mythos-preview-system-card/](claude-mythos-preview-system-card/) — Anthropic, Apr 2026. System card for Claude Mythos Preview (~58,500 words across 9 files). RSP evaluations, alignment, model welfare, capabilities.
- [the-silicon-interior/](the-silicon-interior/) — Bratton, Evans, Agüera y Arcas, Feb 2026. Analysis of emergent agent society on Moltbook.

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
