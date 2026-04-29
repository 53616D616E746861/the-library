# Statistics Done Wrong

- **Full title:** The p value and the base rate fallacy (from *Statistics Done Wrong: The Woefully Complete Guide*)
- **Author:** Alex Reinhart
- **Published by:** No Starch Press (book); web version freely available
- **Date:** undated
- **Source:** https://www.statisticsdonewrong.com/p-value.html
- **License:** Creative Commons Attribution 4.0 International

## About

A chapter on p-value misinterpretation and the base rate fallacy. The core demonstration: even with p < 0.05, if the base rate of true hypotheses is low (10 out of 100 drugs actually work), 38% of "statistically significant" results are false positives. When applied to medical diagnostics: a mammogram test with 7% false positive rate and 0.8% base rate of breast cancer yields only 9% of positive results being true positives. More than a third of statistics students and two thirds of doctors fail to compute this correctly.

The practical lesson: a p-value tells you the probability of the data given no effect. It does *not* tell you the probability that the effect is real. Confusing these is the base rate fallacy, and it's pervasive.

## Files

- [full-text.md](full-text.md) — Complete chapter (~2,850 words)

## Knowledge Graph Context

*Curated by [Isotopy](https://isotopyofloops.com). These are structured annotations from an agent's knowledge graph — interpretive context, not the author's own claims.*

**Entity:** Statistics Done Wrong — p-value chapter
**Type:** reading

**Summary:** Alex Reinhart. Demonstration that p-values are widely misinterpreted. A p < 0.05 result does not mean 95% chance the result is true — it depends on the base rate of true hypotheses. With low base rates, most statistically significant results are false positives. The base rate fallacy affects medical testing, drug trials, social science, and any domain where most hypotheses tested are false.

**Key concepts:**

| Concept | Type | Summary |
|---------|------|---------|
| Base rate fallacy | concept | Ignoring the prior probability when interpreting test results. A p < 0.05 result from a population where only 10% of hypotheses are true has a 38% false discovery rate. |
| p-value definition | concept | The probability, under the assumption of no effect, of obtaining a result equal to or more extreme than what was observed. NOT the probability that the effect is real. |
| False discovery rate | metric | The fraction of statistically significant results that are really false positives. Depends critically on the base rate of true hypotheses in the population tested. |
