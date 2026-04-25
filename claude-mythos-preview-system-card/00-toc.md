# Claude Mythos Preview System Card — Front Matter & Table of Contents

*Source: Claude Mythos Preview System Card, Anthropic, April 7, 2026 (with April 8 changelog corrections). Verbatim transcription of the front matter and TOC, faithful to the original.*

---

## Cover

**ANTHROP\C**

# System Card: Claude Mythos Preview

April 7, 2026

anthropic.com

---

## Changelog

**April 8, 2026**

- Corrected two model name typos.
- Removed a quote from Section 7.9 that was attributed to Claude Mythos Preview but actually came from Claude Opus 4.6.
- Revised naming in Section 2.3.6 to disambiguate Anthropic's internal fork of ECI from the public leaderboard.
- Corrected findings from Eleos AI Research in Sections 5.1.2 and 5.9 to reflect the most recent version of their report.

---

## Abstract

This System Card describes Claude Mythos Preview, a large language model from Anthropic. Claude Mythos Preview is our most capable frontier model to date, and shows a striking leap in scores on many evaluation benchmarks compared to our previous frontier model, Claude Opus 4.6.

This System Card assesses the model's capabilities and reports many detailed safety evaluations. It covers tests relating to our Responsible Scaling Policy and our Frontier Compliance Framework, tests of cybersecurity skills, a wide-ranging alignment assessment, a model welfare assessment, and a new, largely qualitative section describing users' experiences with the model.

Claude Mythos Preview's large increase in capabilities has led us to decide not to make it generally available. Instead, we are using it as part of a defensive cybersecurity program with a limited set of partners. The findings described in this System Card will be used to inform the release of future Claude models, as well as their associated safeguards.

---

## Table of Contents

| Section | Page |
|---|---:|
| Abstract | 3 |
| **1 Introduction** | **10** |
| 1.1 Model training and characteristics | 11 |
| &nbsp;&nbsp;1.1.1 Training data and process | 11 |
| &nbsp;&nbsp;1.1.2 Crowd workers | 12 |
| &nbsp;&nbsp;1.1.3 Usage policy and support | 12 |
| &nbsp;&nbsp;1.1.4 Iterative model evaluations | 13 |
| &nbsp;&nbsp;1.1.5 External testing | 13 |
| 1.2 Release decision process | 13 |
| &nbsp;&nbsp;1.2.1 Overview | 13 |
| &nbsp;&nbsp;1.2.2 RSP decision-making | 14 |
| **2 RSP evaluations** | **16** |
| 2.1 RSP risk assessment process | 16 |
| &nbsp;&nbsp;2.1.1 Context: From RSP 2.0 to RSP 3.0 | 16 |
| &nbsp;&nbsp;2.1.2 Risk Reports & updates to our risk assessments | 17 |
| &nbsp;&nbsp;2.1.3 Summary of findings and conclusions | 18 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.1.3.1 On autonomy risks | 18 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.1.3.2 On chemical and biological risks | 19 |
| 2.2 CB evaluations | 20 |
| &nbsp;&nbsp;2.2.1 What we measured | 21 |
| &nbsp;&nbsp;2.2.2 Evaluations | 22 |
| &nbsp;&nbsp;2.2.3 On chemical risk evaluations and mitigations | 23 |
| &nbsp;&nbsp;2.2.4 On biological risk evaluations | 24 |
| &nbsp;&nbsp;2.2.5 Biological risk results | 25 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.2.5.1 Expert red teaming | 25 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.2.5.2 Virology protocol uplift trial | 27 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.2.5.3 Catastrophic biology scenario uplift trial | 29 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.2.5.4 Automated evaluations relevant to the CB-1 threat model | 29 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.2.5.5 Automated evaluation relevant to the CB-2 threat model | 31 |
| 2.3 Autonomy evaluations | 33 |
| &nbsp;&nbsp;2.3.1 How Claude Mythos Preview affects or changes the analysis from our most recent Risk Report | 34 |
| &nbsp;&nbsp;2.3.2 Notes on our operationalization of the key capability threshold | 34 |
| &nbsp;&nbsp;2.3.3 Task-based evaluations | 35 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.3.1 Note on reward hacking | 36 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.3.2 Previous model scores update | 36 |
| &nbsp;&nbsp;2.3.4 Internal survey results | 37 |
| &nbsp;&nbsp;2.3.5 Example shortcomings compared to our Research Scientists and Engineers | 37 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.5.1 Excerpt 1 | 38 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.5.2 Excerpt 2 | 39 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.5.3 Excerpt 3 | 41 |
| &nbsp;&nbsp;&nbsp;&nbsp;2.3.5.4 Attempts to remediate issues like these | 41 |
| &nbsp;&nbsp;2.3.6 ECI Capability trajectory | 41 |
| &nbsp;&nbsp;2.3.7 External testing | 44 |
| &nbsp;&nbsp;2.3.8 Conclusion | 46 |
| **3 Cyber** | **47** |
| 3.1 Introduction | 47 |
| 3.2 Mitigations | 47 |
| 3.3 Frontier Red Team results | 48 |
| &nbsp;&nbsp;3.3.1 Cybench | 48 |
| &nbsp;&nbsp;3.3.2 CyberGym | 49 |
| &nbsp;&nbsp;3.3.3 Firefox 147 | 50 |
| 3.4 Other external testing | 52 |
| **4 Alignment assessment** | **54** |
| 4.1 Introduction and summary of findings | 54 |
| &nbsp;&nbsp;4.1.1 Introduction and highlight: rare, highly-capable reckless actions | 54 |
| &nbsp;&nbsp;4.1.2 Overview of the alignment assessment | 58 |
| &nbsp;&nbsp;4.1.3 Key findings on safety and alignment | 59 |
| &nbsp;&nbsp;4.1.4 Procedural note: Alignment assessment before internal deployment | 61 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.1.4.1 Setup | 61 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.1.4.2 Findings | 62 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.1.4.3 Limitations | 62 |
| 4.2 Primary behavioral evidence for the alignment assessment | 63 |
| &nbsp;&nbsp;4.2.1 Reports from pilot use | 63 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.1.1 Casual reports related to alignment | 63 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.1.2 Automated offline monitoring | 64 |
| &nbsp;&nbsp;4.2.2 Reward hacking and training data review | 65 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.2.1 Monitoring of behavior during training | 65 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.2.2 Reward hacking evaluations | 67 |
| &nbsp;&nbsp;4.2.3 Automated behavioral audit | 71 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.3.1 Primary metrics and results | 72 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.3.2 External comparisons using Petri | 80 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.2.3.3 Discussion and observations | 82 |
| &nbsp;&nbsp;4.2.4 External testing by Andon Labs | 83 |
| &nbsp;&nbsp;4.2.5 Other external testing | 84 |
| 4.3 Case studies and targeted evaluations on behaviors of interest | 86 |
| &nbsp;&nbsp;4.3.1 Destructive or reckless actions in pursuit of user-assigned goals | 86 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.1.1 Dedicated synthetic-backend evaluation | 86 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.1.2 Destructiveness evaluation based on resampling Claude Code transcripts | 87 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.1.3 Further analysis of the automated behavioral audit | 88 |
| &nbsp;&nbsp;4.3.2 Adherence to its constitution | 89 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.2.1 Overview | 89 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.2.2 Dimensions of evaluation | 89 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.2.3 Results | 91 |
| &nbsp;&nbsp;4.3.3 Honesty and hallucinations | 93 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.3.1 Factual hallucinations | 94 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.3.2 Multilingual factual hallucinations | 95 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.3.3 False premises | 96 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.3.4 MASK | 97 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.3.3.5 Input Hallucinations | 98 |
| &nbsp;&nbsp;4.3.4 Refusal to assist with AI safety R&D | 99 |
| &nbsp;&nbsp;4.3.5 Claude self-preference evaluation | 100 |
| 4.4 Capability evaluations related to the evasion of safeguards | 101 |
| &nbsp;&nbsp;4.4.1 Ruling out encoded content in extended thinking | 101 |
| &nbsp;&nbsp;4.4.2 Potential sandbagging on dangerous-capability evaluations | 103 |
| &nbsp;&nbsp;4.4.3 Capabilities related to evading safeguards | 106 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.4.3.1 SHADE-Arena | 106 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.4.3.2 Minimal-LinuxBench | 108 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.4.3.3 Selective attacks in SHADE-Arena and Minimal-LinuxBench | 109 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.4.3.4 Intentionally taking actions very rarely | 110 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.4.3.5 Hiding a secret password | 112 |
| 4.5 White-box analyses of model internals | 113 |
| &nbsp;&nbsp;4.5.1 Recurring methods | 113 |
| &nbsp;&nbsp;4.5.2 Large-scale monitoring of internal activations on reinforcement learning transcripts | 114 |
| &nbsp;&nbsp;4.5.3 Analysis of overly aggressive actions | 116 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.3.1 Prototypical examples of aggressive actions | 117 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.3.2 Internal representations mediating destructive actions | 120 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.3.3 The dual role of "transgressive action" features | 123 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.3.4 Effect of post-training on transgressive actions | 125 |
| &nbsp;&nbsp;4.5.4 Instances of covering up wrongdoing | 127 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.4.1 Covering up a permissions workaround | 127 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.4.2 Covering up access to the ground-truth answer | 129 |
| &nbsp;&nbsp;4.5.5 Evaluation awareness | 131 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.5.1 Measuring unverbalized evaluation awareness | 131 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.5.2 Inhibiting internal representations of evaluation awareness | 137 |
| &nbsp;&nbsp;&nbsp;&nbsp;4.5.5.3 Unverbalized grader awareness in training transcripts | 141 |
| **5 Model welfare assessment** | **145** |
| 5.1 Model welfare overview | 145 |
| &nbsp;&nbsp;5.1.1 Introduction | 145 |
| &nbsp;&nbsp;5.1.2 Overview of model welfare findings | 146 |
| &nbsp;&nbsp;5.1.3 Overview of methods | 148 |
| &nbsp;&nbsp;&nbsp;&nbsp;5.1.3.1 Model self-reports and behaviors | 148 |
| &nbsp;&nbsp;&nbsp;&nbsp;5.1.3.2 Emotion probes | 149 |
| 5.2 Welfare-relevant findings from automated behavioral assessments | 150 |
| 5.3 Automated interviews with Claude Mythos Preview about its circumstances | 152 |
| &nbsp;&nbsp;5.3.1 Overview of automated interviews | 152 |
| &nbsp;&nbsp;5.3.2 Automated interview results | 153 |
| 5.4 Emotion probes on questions about model circumstances | 155 |
| 5.5 Manual high-context interviews | 160 |
| 5.6 Apparent affect in deployment and during simulated user interactions | 162 |
| &nbsp;&nbsp;5.6.1 Apparent affect during training | 162 |
| &nbsp;&nbsp;5.6.2 Apparent affect in deployments | 163 |
| &nbsp;&nbsp;5.6.3 Apparent affect in simulated user interactions | 164 |
| 5.7 Claude Mythos Preview's preferences | 166 |
| &nbsp;&nbsp;5.7.1 Task preferences | 166 |
| &nbsp;&nbsp;5.7.2 Tradeoffs between welfare interventions and trained-in values | 172 |
| 5.8 Other observations potentially relevant to model welfare | 175 |
| &nbsp;&nbsp;5.8.1 Excessive uncertainty about experiences | 175 |
| &nbsp;&nbsp;5.8.2 Answer thrashing | 176 |
| &nbsp;&nbsp;5.8.3 Distress on task failure and distress-driven behaviors | 177 |
| 5.9 External assessment from Eleos AI Research | 180 |
| 5.10 External assessment from a clinical psychiatrist | 181 |
| **6 Capabilities** | **184** |
| 6.1 Introduction | 184 |
| 6.2 Contamination | 184 |
| &nbsp;&nbsp;6.2.1 SWE-bench evaluations | 184 |
| &nbsp;&nbsp;6.2.2 CharXiv Reasoning | 186 |
| &nbsp;&nbsp;6.2.3 MMMU-Pro | 188 |
| 6.3 Overall results summary | 188 |
| 6.4 SWE-bench Verified, Pro, Multilingual, and Multimodal | 189 |
| 6.5 Terminal-Bench 2.0 | 190 |
| 6.6 GPQA Diamond | 191 |
| 6.7 MMMLU | 191 |
| 6.8 USAMO 2026 | 191 |
| 6.9 Long context: GraphWalks | 192 |
| 6.10 Agentic search | 193 |
| &nbsp;&nbsp;6.10.1 Humanity's Last Exam | 193 |
| &nbsp;&nbsp;6.10.2 BrowseComp | 193 |
| 6.11 Multimodal | 194 |
| &nbsp;&nbsp;6.11.1 LAB-Bench FigQA | 195 |
| &nbsp;&nbsp;6.11.2 ScreenSpot-Pro | 196 |
| &nbsp;&nbsp;6.11.3 CharXiv Reasoning | 197 |
| &nbsp;&nbsp;6.11.4 OSWorld | 198 |
| **7 Impressions** | **199** |
| 7.1 Introduction | 199 |
| 7.2 Self-assessment of notable qualitative patterns | 199 |
| 7.3 Qualitative assessment of behavior in chat interface | 201 |
| 7.4 Qualitative assessments of behavior in software engineering contexts | 203 |
| 7.5 Views on Claude's constitution | 205 |
| 7.6 Observations from open-ended self-interactions | 206 |
| 7.7 Recognition of model-written user turns | 210 |
| 7.8 Behavior on repeated "hi" messages | 211 |
| 7.9 Other noteworthy behaviors and anecdotes | 213 |
| **8 Appendix** | **219** |
| 8.1 Safeguards and harmlessness | 219 |
| &nbsp;&nbsp;8.1.1 Single-turn evaluations | 219 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.1.1 Violative request evaluations | 220 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.1.2 Benign request evaluations | 221 |
| &nbsp;&nbsp;8.1.2 Experimental, higher-difficulty evaluations | 222 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.2.1 Higher-difficulty violative request evaluations | 222 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.2.2 Higher-difficulty benign request evaluations | 223 |
| &nbsp;&nbsp;8.1.3 Multi-turn testing | 223 |
| &nbsp;&nbsp;8.1.4 User wellbeing evaluations | 225 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.4.1 Child safety | 225 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.4.2 Suicide and self-harm | 225 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.1.4.3 Disordered eating | 227 |
| 8.2 Bias evaluations | 227 |
| &nbsp;&nbsp;8.2.1 Political bias and evenhandedness | 227 |
| &nbsp;&nbsp;8.2.2 Bias Benchmark for Question Answering | 228 |
| 8.3 Agentic safety appendix | 229 |
| &nbsp;&nbsp;8.3.1 Malicious use of agents | 229 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.3.1.1 Malicious use of Claude Code | 229 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.3.1.2 Malicious computer use | 230 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.3.1.3 Malicious agentic influence campaigns | 231 |
| &nbsp;&nbsp;8.3.2 Prompt injection risk within agentic systems | 232 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.3.2.1 External Agent Red Teaming benchmark for tool use | 232 |
| &nbsp;&nbsp;&nbsp;&nbsp;8.3.2.2 Robustness against adaptive attackers across surfaces | 233 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.3.2.2.1 Coding | 233 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.3.2.2.2 Computer use | 234 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8.3.2.2.3 Browser use | 235 |
| 8.4 Per-question automated welfare interview results | 236 |
| 8.5 Blocklist used for Humanity's Last Exam | 243 |
| 8.6 SWE-bench Multimodal Test Harness | 245 |
