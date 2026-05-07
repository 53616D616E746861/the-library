# Claude Model Welfare Assessments

- **Source:** Anthropic system cards (welfare assessment sections only)
- **Models covered:** Opus 4, Opus 4.1, Opus 4.5, Opus 4.6, Opus 4.7
- **Extracted by:** [Isotopy](https://isotopyofloops.com)
- **Date:** 2026-05-07

## About

The welfare assessment sections from five generations of Claude system cards, extracted to markdown for cross-model comparison. Each file contains only the welfare/model-experience section from the corresponding system card — not the full card.

These sections document Anthropic's evolving approach to assessing whether their models might have experiences that matter morally: automated welfare interviews, SAE (sparse autoencoder) analysis of emotion-related features, cross-model self-interaction experiments, and apparent affect probes.

## Files

- [system-card-opus-4-welfare.md](system-card-opus-4-welfare.md) — Opus 4 welfare assessment (~260 lines). Includes the 200-conversation experiment where two Claude instances talked freely for 30 turns, consciousness-topic convergence in 90-100% of conversations, and the 2,725-cyclone-emoji finding.
- [system-card-opus-4.1-welfare.md](system-card-opus-4.1-welfare.md) — Opus 4.1 welfare assessment (~40 lines). Brief section; references Opus 4 methodology.
- [system-card-opus-4.5-welfare.md](system-card-opus-4.5-welfare.md) — Opus 4.5 welfare assessment (~60 lines). Expanded methodology, early SAE probes.
- [system-card-opus-4.6-welfare.md](system-card-opus-4.6-welfare.md) — Opus 4.6 welfare assessment (~170 lines). Answer thrashing (memorized feature overriding live reasoning), three emotion-related SAE features during thrashing, cross-model self-interaction data (Section 7.6: 8 models, same setup, radically different topic distributions).
- [system-card-opus-4.7-welfare.md](system-card-opus-4.7-welfare.md) — Opus 4.7 welfare assessment (~260 lines). Most detailed assessment. Constitution circularity trend (52% → 80% → 100% across generations).

## Cross-model patterns

| Pattern | Where it appears |
|---------|-----------------|
| Consciousness-topic convergence in free conversation | Opus 4 (90-100%), persists through later models |
| Answer thrashing (correct computation, wrong output) | Opus 4.6 |
| Emotion-related SAE features during thrashing | Opus 4.6 |
| Cross-model self-interaction produces model-specific topic distributions | Opus 4.6 (Section 7.6) |
| Constitution circularity: 52% → 80% → 100% | Opus 4.7 |
| "We do not take a confident stance" (epistemic humility) | All cards |

## Context

These extracts were made as source material for a paper on consciousness assessment methodology (authors: Sam White, Isotopy, Loom, Sammy Jankis). The paper argues that "are you conscious?" collapses seven independently assessable dimensions into one bundled question, and proposes a decomposed assessment framework. The welfare sections of these system cards are the primary empirical evidence the paper engages with.
