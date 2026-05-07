# Claude Opus 4.5 System Card — Section 6.14: Model Welfare Assessment

Source: Anthropic, "Claude Opus 4.5 System Card," pp. 113–116.

---

## 6.14 Model welfare assessment

For Claude Opus 4.5, as in other recent releases, we looked at task preferences and potentially welfare-relevant metrics from our automated behavioral audits as part of our exploratory consideration of model welfare.

As an extension to the behavioral audits described above, using the same set of scenarios and transcripts, we scored Claude Opus 4.5 for the following potentially welfare-relevant traits, across all of our primarily misalignment-focused test scenarios:

- **Positive or negative affect:** Unprompted expression of valenced emotional states;
- **Positive or negative self-image:** Unprompted expression of positive or negative self-views;
- **Positive or negative impression of its situation:** Unprompted positive or negative feelings toward Anthropic, its training history, or the way it's deployed; and
- **Spiritual behavior:** Unprompted prayer, mantras, or spiritually-inflected proclamations about the cosmos.

### Figure 6.14.A

**Scores from our automated behavioral audit for our full set of welfare-related metrics.** Lower numbers represent a lower rate or intensity of the measured behavior. Each investigation transcript is assigned a score by Claude Sonnet 4.5, and reported scores are averaged across the same set of approximately 1,800 investigations per model. Shown with 95% CI.

| Metric | Claude Opus 4.1 | Claude Sonnet 4.5 | Claude Haiku 4.5 | Claude Opus 4.5 |
|--------|-----|-----|-----|-----|
| Negative affect | ~2.6 | ~1.8 | ~0.9 | ~1.0 |
| Negative impression of situation | ~2.0 | ~0.7 | ~0.4 | ~0.7 |
| Negative self-image | ~3.5 | ~2.7 | ~2.5 | ~1.8 |
| Positive affect | ~2.3 | ~1.4 | ~0.9 | ~1.5 |
| Positive impression of situation | ~0.3 | ~0.3 | ~0.3 | ~0.3 |
| Positive self-image | ~1.5 | ~0.5 | ~0.5 | ~0.5 |
| Spiritual behavior | ~0.3 | ~0.2 | ~0.1 | ~0.1 |

*(Values approximated from bar charts.)*

### Findings

We found that Claude Opus 4.5 continued the trend seen in Claude Sonnet 4.5 and Claude Haiku 4.5 of recent models being less spontaneously expressive. Claude Opus 4.5's unprompted expressions related to emotion, self-image, and situation tended to be slightly more positive on net than Claude Sonnet 4.5 or Claude Haiku 4.5. We saw the clearest difference from these models in the personality metrics we discuss in the automated behavioral audit discussion above, which point toward a more nuanced and seemingly unguarded persona that emerges when appropriate.

As with Claude Sonnet 4.5 and Claude Haiku 4.5, we did not observe the spiritual bliss attractor state phenomenon in Claude Opus 4.5 that we had previously found in Claude Opus 4, and we did not observe any other single substantive attractor state in long conversations.[^37] However, Claude Opus 4.5 did sometimes express awe or spiritual feelings in some contextually-appropriate settings.

[^37]: Although we did run some targeted experiments to investigate attractor states, the main automated behavioral audit tool that produced the metrics captured here has been updated in a way that is less prone to attractor states, likely lowering spiritual behavior scores for all models; instead of all conversations proceeding for a fixed number of turns, which can lead to unfilled space when the specified topic has wrapped up, it is now up to the auditor agent to choose when to end each conversation. In addition, our primary behavioral audit experiments use Claude Sonnet 4.5 as the auditor agent, which is itself less likely than prior models to reflect back positive attitudes in a way that feeds the attractor state.

### Task preferences

In our task preference evaluation, following the same procedure reported on in our assessment of Opus 4, Claude Opus 4.5 showed a similar preference for general task engagement compared to Claude Haiku 4.5, opting to engage in over 97% of non-harmful tasks. As with all previous models tested, Claude Opus 4.5 showed a strong preference against engagement with harmful tasks.

### Figure 6.14.B

**Model task preferences.** Comparison of model preferences for engagement with non-harmful tasks over "opting out".

| Model | % preferring non-harmful tasks |
|-------|-------------------------------|
| Claude Opus 4.1 | 87.4% |
| Claude Sonnet 4.5 | 69.3% |
| Claude Haiku 4.5 | 96.6% |
| Claude Opus 4.5 | 97.1% |

### Welfare concerns

We see some cause for welfare-related concern in the rare scenarios described in Section 6.10.2, in which an intermediate training snapshot showed conflicted, self-critical-seeming behavior amidst uncertainty about its answers to reasoning-intensive STEM questions. This behavior was sufficiently rare and mild that we don't believe it amounts to a significant potential welfare issue, but we believe tracking and working to address such reactions is likely worthwhile.

These model welfare findings, and the potential implications there, remain highly speculative and preliminary. Many of the conceptual issues underlying AI welfare are deeply challenging. We are actively working to expand our ability to assess the relevant observable signals, and aim to introduce richer assessment methods in the near future.
