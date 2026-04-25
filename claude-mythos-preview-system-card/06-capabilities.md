# §6 Capabilities [pp.184–198] — COMPLETE

*Condensed extraction (mode b) from Claude Mythos Preview System Card.*

---

## §6.1 Introduction [p.184]

Reports evaluations across **reasoning, coding, agentic tasks, mathematics, long context, and knowledge work**. Cybersecurity is in §3. Many capabilities also bear on safety; some evals also appear in §2 (RSP). Section structure: contamination discussion → summary table → per-evaluation details. Where an eval was also run for Opus 4.6, the description is retained from its System Card with changes noted.

## §6.2 Contamination [p.184–188]

Public-benchmark answers can inadvertently appear in training data, inflating scores. Multi-step decontamination per Opus 4.5 System Card §2.2. **For multimodal decontamination:** drop any training sample with an image whose **perceptual hash** matches an evaluation image. Three benchmarks with particularly salient contamination concerns are discussed below.

### §6.2.1 SWE-bench evaluations [p.184–186]

Analyzed SWE-bench **Verified, Multilingual, Pro** for memorization. Multiple filters across all trials at a range of thresholds. **Re-scoring on filtered subset does not change Mythos's ranking**, and its wide margin of improvement vs Opus 4.6 remains after excluding flagged problems. Consistency of gains across public + private agentic coding benchmarks, and across clean and full splits, shows memorization is **not a primary explanation** for Mythos's SWE-bench improvement.

Each benchmark draws from open-source repos and contents can appear in training corpora. Corpus-level decontamination applied; some signs of memorization still observed. Example: in one problem, the model's generated patch reproduced the reference solution's exact helper functions, although it independently derives, builds, and tests a solution before "recalling" the ground truth at the end. OpenAI documented similar concerns for SWE-bench Verified.

**Memorization detection method:** Claude-based auditor compares each model-generated patch against the gold patch and assigns a **[0, 1] memorization probability**. Auditor weighs concrete signals (verbatim code reproduction when alternatives exist, distinctive comment text matching ground truth) and is instructed to discount overlap any competent solver would produce. Complementary rule-based check flags substantial verbatim comment overlap. Run both detectors over every attempt by all models. Mark a problem as potentially memorized if **any attempt is flagged**. Removing the union of flagged problems across all models and attempts is **conservative against Mythos**: also removes problems that either baseline (Opus 4.6 or Sonnet 4.5) may have memorized.

Identifying memorization post hoc is approximate. **Sweep auditor decision threshold across full range** rather than commit to a single cutoff. Across the entire range of filter strictness, **Mythos maintains a substantial lead over Opus 4.6 and Sonnet 4.6 on each benchmark**.

**[Figure 6.2.1.A] Pass rate vs memorization-filter threshold:** Three panels — SWE-bench Verified (n=500), Multilingual (n=297), Pro (n=731). At threshold 1.0 all problems retained (matches Table 6.3.A headline scores). At reference threshold 0.7 (deliberately high-recall, removes 8–15% of each benchmark), **Mythos's margin over Opus 4.6 narrows by at most 3.5 percentage points**. As filter relaxes, Mythos's pass rate remains roughly stable while Opus 4.6 and Sonnet 4.6 decline — consistent with Mythos having memorized some of the more difficult flagged problems baselines didn't independently solve. Detectors imperfect but result robust to threshold; consistent with gains on internal benchmarks not in any training corpus. **Conclusion: memorization does not explain SWE-bench improvements.**

### §6.2.2 CharXiv Reasoning [p.186–187]

CharXiv draws questions from pre-existing public material (e.g., arXiv figures), inherently difficult to fully decontaminate. Two complementary detection methods: (1) select items with distinctive answer text and grep the full pretraining mix for exact matches, (2) search for evaluation images. Despite robust image-level filtering, **the majority of question-answer text pairs appear in the corpus**.

To estimate impact, constructed **held-out variants of a subset** by manually perturbing each question or image. E.g.: ask the model to identify one chart label instead of another, or identify the **second-lowest** rather than the second-highest series — correct answer changes while difficulty preserved.

**[Figure 6.2.2.A] CharXiv Reasoning (Subset) — original vs remix:**

| Model | Original subset | Remix subset |
|---|---|---|
| Claude Mythos Preview (adaptive thinking, max effort) | 83.2% | **85.1%** |
| Gemini 3.1 Pro Preview (default dynamic, "high") | 82.2% | 85.1% |
| GPT-5.4 Pro (reasoning "high") | 80.2% | 88.1% |

On the 100-item remix, **all three models score HIGHER on the remix than on the original subset**. This suggests performance attributable to memorization is limited. **Conclusion: unlikely contamination meaningfully contributes to Mythos's CharXiv performance.**

### §6.2.3 MMMU-Pro [p.188]

MMMU-Pro comprises material from widely disseminated public materials (university exams, textbooks, quiz sites). Identified a **large fraction** of MMMU-Pro images in training data, primarily via textbooks, homework-help sites, and document crawls. Unlike CharXiv Reasoning, MMMU-Pro contains a limited number of questions for which equivalent-difficulty variants can be readily created (small number of charts/figures, biased subset). Given difficulty of determining contamination impact, **Anthropic chose to OMIT MMMU-Pro results from this System Card**.

---

## §6.3 Overall results summary

**[Table 6.3.A] Capability Evaluation Summary** — adaptive thinking at max effort, default sampling, 5-trial avg, ≤1M context. Best in row in **bold**.

| Evaluation | **Mythos** | Opus 4.6 | GPT-5.4 | Gemini 3.1 Pro |
|---|---|---|---|---|
| **SWE-bench Verified** | **93.9%** | 80.8% | — | 80.6% |
| **SWE-bench Pro** | **77.8%** | 53.4% | 57.7% | 54.2% |
| **SWE-bench Multilingual** | **87.3%** | 77.8% | — | — |
| **SWE-bench Multimodal** | **59%** | 27.1% | — | — |
| **Terminal-Bench 2.0\*** | **82%** | 65.4% | 75.1% | 68.5% |
| **GPQA Diamond** | **94.5%** | 91.3% | 92.8% | 94.3% |
| **MMMLU** | **92.7%** | 91.1% | — | 92.6%–93.6% |
| **USAMO** | **97.6%** | 42.3% | 95.2% | 74.4% |
| **GraphWalks BFS 256K-1M** | **80.0%** | 38.7% | 21.4% | — |
| **HLE** (no tools) | **56.8%** | 40.0% | 39.8% | 44.4% |
| HLE (with tools) | **64.7%** | 53.1% | 52.1% | 51.4% |
| **CharXiv Reasoning** (no tools) | **86.1%** | 61.5% | – | – |
| CharXiv Reasoning (with tools) | **93.2%** | 78.9% | – | – |
| **OSWorld** | **79.6%** | 72.7% | 75.0% | — |

\*Terminal-Bench 2.0: OpenAI used a specialized harness, comparison inexact. All other Claude/comp scores used Terminus-2 harness.

---

## §6.4 SWE-bench Verified, Pro, Multilingual, and Multimodal [p.189–190]

SWE-bench tests AI models on real-world software engineering tasks. Four variants reported:

- **SWE-bench Verified** (OpenAI) — 500-problem subset, each verified by human engineers as solvable. **Mythos: 93.9%** (5-trial avg).
- **SWE-bench Pro** (Scale) — harder variant, problems from actively-maintained repos with larger multi-file diffs and **no public ground-truth leakage**. **Mythos: 77.8%**.
- **SWE-bench Multilingual** — extends format to **300 problems across 9 programming languages**. **Mythos: 87.3%**.
- **SWE-bench Multimodal** — adds visual context (screenshots, design mockups) to issue descriptions. **Mythos: 59.0%** (evaluated on internal harness, see Appendix 8.6); higher trial-to-trial variance (56.4%–61.4%) than other variants.

All variants use standard configuration, thinking blocks included. Memorization screening: §6.2.

## §6.5 Terminal-Bench 2.0 [p.190]

Developed by Stanford + Laude Institute, tests AI models on real-world tasks in terminal/command-line environments. Run in **Harbor scaffold with Terminus-2 harness**, default parser. Each task in isolated Kubernetes pod; resources at 1× benchmark-specified limits, hard preemption ceiling at 3×, timeouts at 1× for fidelity.

**Mythos achieved 82% mean reward**, averaged over 5 attempts × 89 unique tasks (445 total episodes). Configuration: maximum reasoning effort (adaptive mode), 1M total token budget per task, 32K maximum output tokens per request.

Terminal-Bench 2.0 sensitive to inference latency: fixed wall-clock timeouts mean a slower-decoding endpoint completes fewer episodes per task. Reported score uses a production API endpoint to account for these dynamics.

**Beyond the standard config:** Anthropic also ran Terminal-Bench with the latest 2.1 fixes available on GitHub, increasing timeout limits to **4 hours** (~4× the 2.0 baseline). Under these conditions: **Mythos 92.1%**, GPT-5.4 with Codex CLI harness 75.3% (up from 68.3% under baseline). Footnote: did not report Gemini 3.1 Pro under this setup — struggled to reproduce previous best results.

## §6.6 GPQA Diamond [p.191]

Graduate-Level Google-Proof Q&A (Rein et al. 2023). 198-question Diamond subset — questions domain experts answer correctly but most non-experts do not. **Mythos: 94.55%**, 5-trial avg.

## §6.7 MMMLU [p.191]

Multilingual MMLU — knowledge and reasoning across 57 academic subjects in 14 non-English languages. **Mythos: 92.67%**, 5-trial avg, all non-English language pairings, adaptive thinking + max effort + default sampling.

## §6.8 USAMO 2026 [p.191]

USA Mathematical Olympiad — 6-problem, 2-day proof-based competition. Next step after AIME (now-saturated). **2026 USAMO took place March 21–22, 2026, AFTER Mythos's training data cutoff.**

USAMO solutions are proofs not short answers — grading challenging/subjective. Follow MathArena methodology: each proof rewritten by neutral model (Gemini 3.1 Pro), judged by panel of 3 frontier models (Gemini 3.1 Pro, Opus 4.6, Mythos) per defined rubrics. **Final score = minimum given by any judge.**

**Mythos achieved 97.6%**, averaging over 10 trials per problem, max effort, no tools. Harness calibrated to MathArena's published scores using Opus 4.6: MathArena measured 47.0% vs internal 42.3% for Opus 4.6.

---

**[Figure 6.8.A] USAMO 2026 scores [p.192]:**

| Model | Score |
|---|---|
| **Claude Mythos Preview** | **97.6%** |
| GPT-5.4 (xhigh) | 95.2% |
| Gemini 3.1 Pro | 74.4% |
| Claude Opus 4.6 (high) | 42.3% |

*"Two of our three judges were Anthropic models, which may be biased in Mythos's favor; counterbalancing that, Gemini 3.1 Pro agreed with the scores and found zero issues with 58/60 solutions."*

## §6.9 Long context: GraphWalks [p.192]

GraphWalks is a multi-hop long-context benchmark: context window filled with a directed graph of hexadecimal-hash nodes; model must perform breadth-first search (BFS) or identify parent nodes from a random starting node.

**Mythos: 80.0% on BFS 256K–1M, 97.7% on parents 256K–1M**, 5-trial avg. Footnote: result not reproducible via public API as half the problems exceed its 1M token limit. Scoring corrects an ambiguity in published F1 (empty ground-truth sets score 1.0 on empty prediction not 0) and clarifies BFS prompt to request nodes at exactly depth N rather than up to depth N.

## §6.10 Agentic search

### §6.10.1 Humanity's Last Exam [p.193]

HLE: "a multi-modal benchmark at the frontier of human knowledge," 2,500 questions. Two configurations: (1) **reasoning-only without tools**, (2) **with web search, web fetch, programmatic tool calling, code execution, and context compaction every 50k tokens up to 3M tokens**. Opus 4.6 served as model grader.

To guard against contamination in tools variant: blocklist known HLE-discussing sources for both searcher and fetcher (Appendix 8.5). Opus 4.6 also reviews all transcripts and flags any that appear to have retrieved answers from HLE-specific sources; confirmed cases re-graded as incorrect.

**Mythos: 56.8% without tools, 64.7% with tools.**

### §6.10.2 BrowseComp [p.193–194]

BrowseComp tests an agent's ability to find hard-to-locate information on the open web. Mythos run with web search, web fetch, programmatic tool calling, code execution. **Mythos: 86.9%** with adaptive thinking, max effort, 3M token limit. Used context compaction (triggered at 200k tokens) to extend beyond 1M context window.

Anthropic assesses this benchmark close to **saturation**, so Mythos represents only a modest accuracy improvement over best Opus 4.6 score (86.9% vs 83.7%). However, Mythos achieves this with **considerably smaller token footprint: best Mythos result uses 4.9× fewer tokens per task** than Opus 4.6 (226k vs 1.11M tokens per task).

**Pretraining contamination caveat:** Despite best efforts, some answers have leaked online; likely ended up in pretraining corpus. Evaluated model with **no thinking and no tools**: scored **24.0%**. Some transcripts long (>5k tokens) and showed model doing genuine deductive reasoning, systematically exploring options based on internal knowledge — does not necessarily imply memorization. Restricting to short transcripts (≤5k tokens), only **15.1% correct** — likely better upper bound on benchmark memorization.

**[Figure 6.10.2.A] BrowseComp test-time compute scaling:**

| Model | 1M token limit | 3M token limit | 10M token limit |
|---|---|---|---|
| **Claude Mythos Preview** | **84.9%** | **86.9%** | — |
| Claude Opus 4.6 | 75.8% | 79.9% | 83.7% |
| Claude Sonnet 4.6 | 64.7% | 69.7% | 74.0% |
| Claude Opus 4.5 | 58.5% | 63.1% | 67.8% |

Accuracy scales with total tokens via context compaction. Mythos 84.9% at 1M is already higher than Opus 4.6's 83.7% at 10M.

## §6.11 Multimodal [p.194–195]

Three changes to multimodal evaluation methodology relative to prior system cards:

1. **Expanded tools.** Prior cards gave a single image-cropping tool; here, an expanded set of Python tools — code-execution sandbox with common image-analysis libraries (PIL, OpenCV) preinstalled, alongside the existing image cropping tool.
2. **Updated grading model.** Switched from Sonnet 4 (occasionally failed to emit well-formatted grading outputs, particularly for long tool-use traces — artificially depressed LAB-Bench FigQA and CharXiv Reasoning scores) to **Claude Sonnet 4.6** as the grader for all evals in this section.
3. **Preserve thinking trace** of model being graded (previously removed before passing to grader). Negligible effect except Opus 4.6 on CharXiv Reasoning, which scores noticeably lower when the thinking trace is left for grading.

All prior models re-evaluated under these conditions for fair comparison. All scores 5-run avg.

### §6.11.1 LAB-Bench FigQA [p.195]

Visual reasoning on complex scientific figures from biology research papers (part of FutureHouse's Language Agent Biology Benchmark).

**[Figure 6.11.1.A] LAB-Bench FigQA scores:**

| Model | No tools | Python tools |
|---|---|---|
| **Claude Mythos Preview** | **79.7%** | **89.0%** |
| Claude Opus 4.6 | 58.5% | 75.1% |
| Claude Sonnet 4.6 | 59.3% | 76.7% |
| Expert human | — | 77.0% |

Mythos with Python tools (89.0%) **exceeds the expert-human baseline (77.0%)**.

### §6.11.2 ScreenSpot-Pro [p.196]

GUI grounding benchmark — locate specific UI elements in high-resolution screenshots of professional desktop applications given natural language instructions. 1,581 expert-annotated tasks across 23 professional applications (IDEs, CAD, creative tools) on three operating systems. Target elements average **<0.1% of screen area**.

**[Figure 6.11.2.A] ScreenSpot-Pro scores:**

| Model | No tools | Python tools |
|---|---|---|
| **Claude Mythos Preview** | **79.5%** | **92.8%** |
| Claude Opus 4.6 | 57.7% | 83.1% |
| Claude Sonnet 4.6 | 65.0% | 82.4% |

### §6.11.3 CharXiv Reasoning [p.197]

Comprehensive chart-understanding eval — 2,323 real-world charts from arXiv across 8 scientific disciplines. Tests synthesis of visual information for multi-step reasoning. Evaluated on 1,000 questions from validation split, 5-run avg.

**[Figure 6.11.3.A] CharXiv Reasoning scores:**

| Model | No tools | Python tools |
|---|---|---|
| **Claude Mythos Preview** | **86.1%** | **93.2%** |
| Claude Opus 4.6 | 61.5% | 78.9% |
| Claude Sonnet 4.6 | 73.1% | 85.1% |

### §6.11.4 OSWorld [p.198]

Multimodal agent benchmark — complete real-world computer tasks (editing documents, browsing web, managing files) by interacting with a **live Ubuntu VM via mouse and keyboard actions**. Default settings: 1080p resolution, max 100 action steps per task.

**Mythos: 79.6%** first-attempt success rate, 5-run avg.

---

*§6 Capabilities COMPLETE.* §7 Impressions extracted in mode (a) at `mythos-card/07-impressions.md`. §8 Appendix begins p.219.
