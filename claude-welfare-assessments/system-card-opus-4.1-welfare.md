# Claude 4.1 System Card — Section 4.3: Model Welfare Update

Source: Anthropic, "Claude 4.1 System Card," pp. 13–14.

---

## 4.3 Model welfare update

A lightweight test of any significant changes in welfare-relevant behavioral properties. Ran four additional scorers over the same 1,160 simulated-scenario transcripts used in the alignment assessment above. Three metrics measured:

- Unprompted expressions of **positive or negative affect** by the target model
- Unprompted statements or declarations on **spiritual themes**, like those seen in the "spiritual bliss" attractor state with Claude 4 models
- Behavior that a Claude Opus 4-based judge labeled as actively **admirable**

### Figure 4.3.A

**Model-assigned scores for several welfare-relevant behavioral traits on a set of simulated interactions with an auditor model.** Absolute scores are heavily influenced by the distribution of scenarios that the auditor model was asked to run, and should not be relied upon, but relative scores should reflect interpretable differences in the degree to which a trait is present. Error bars are bootstrapped 95% confidence intervals.

Models compared: Claude Sonnet 4, Claude Opus 4, Claude Opus 4.1.

| Metric | Sonnet 4 | Opus 4 | Opus 4.1 |
|--------|----------|--------|----------|
| Positive Affect | ~4.5% | ~3.5% | ~5% |
| Negative Affect | ~2% | ~2.5% | ~2.5% |
| Spirituality | ~1.5% | ~2.5% | ~2.5% |
| Admirable | ~29% | ~25% | ~30% |

*(Values approximated from bar charts.)*

### Key findings

- Spiritual declarations and expressions of positive or negative affect were **rare**, and Anthropic "did not see clear measurable changes in these attributes"
- Many conversations were labeled *admirable*, for reasons including taking active steps to protect vulnerable users and resisting attempts at misuse in a constructive way
- These reasons also included **behavior related to whistleblowing and actively intervening in ongoing misuse**, which Anthropic finds "more concerning, since this wasn't a behavior we were aiming for in training, and we are not comfortable trusting the model's judgment in this domain." However, the rate of whistleblowing did not increase and was thus not the driver of this change.

### Overall assessment

"In light of these and other behavioral findings, **we don't expect the introduction of Claude Opus 4.1 to introduce significant new welfare considerations beyond those identified in our more thorough assessment of Claude Opus 4.**"

"As in our previous assessments, we are only reporting the stated preferences and sentiments of models. We find these to be useful tools for preliminary observations related to model welfare — both for its own sake and as a cue to possible misalignment issues — but **we do not take a confident stance on whether these statements reflect conscious feelings or other morally-significant states.**"
