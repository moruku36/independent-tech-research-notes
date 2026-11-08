[日本語](2026-hightouch-identity-resolution-llm-judges.ja.md) | **English**

# A Jev that can ask Opus for help gives Opus accuracy at 4x lower cost

- This corporate experiment audits over-merges after identity resolution using a small model with escalation to Opus.
- On the easier synthetic dataset, Jev plus Opus achieved 98.8% accuracy at $0.88 per 1,000 identities, versus 99.0% and $3.86 for Opus alone.
- The cost advantage narrowed on harder data; real-customer performance, transferable thresholds, and statistical equivalence remain unestablished.

## Practical interpretation (7 lines)

- Treat this as an auditor for over-merges after matching.
- Route intermediate-confidence cases from a cheap model to a more expensive model.
- Evaluate confidence quality as well as standalone accuracy.
- Restrict the roughly fourfold cost claim to the easier experimental condition.
- Check false positives and false negatives at realistic over-merge prevalence.
- Separate threshold calibration from final evaluation and measure escalation, cost, and latency.
- The verification plan below is proposed; no model calls or reproduction were performed.

## Metadata and verification

- Authors: Albert Jin, Neil Desai, Delaney Mackenzie.
- Published: November 4, 2026. Corporate technical article, not a peer-reviewed paper.
- Checked: November 8, 2026 JST.
- Scope: primary article text, experimental tables, and limitations reviewed; reported results recorded without independent validation.
- Target: over-merging. Under-merging is identified as future work.

## Question and method

Can an inexpensive judge detect cases where records belonging to different people have been merged into one identity? The authors use pseudopeople to create a fictional US town, adding typos, shared addresses, relatives, twins, and other noise. These are synthetic records, not an evaluation of real customers.

The initial dataset contains 1,000 identities, split evenly between noisy single-person records and over-merged records. Models receive a common prompt with context and examples of noise; predictions and confidence are compared. A harder condition uses the same town with more difficult name overlaps, twins, and date errors.

In the Jev-to-Opus cascade, confidence between 30% and 90% triggers escalation. On the easier data this sends 22% of cases to Opus. This is an experimental configuration, not a universally optimal band.

## Reported evidence

| Condition | Configuration | Accuracy | Time per identity | Cost per 1,000 |
|---|---|---:|---:|---:|
| Easier | Opus 5.5 | 99.0% | 2.2 s | $3.86 |
| Easier | Jev + Opus | 98.8% | 0.63 s | $0.88 |
| Harder | Opus 5.5 | 95.1% | 2.6 s | $5.39 |
| Harder | Jev + Opus | 95.3% | 1.56 s | $2.94 |

The cost ratios are approximately 4.4 on easier data and 1.8 on harder data. Nearby accuracy estimates do not establish statistical equivalence. Prices and latency are historical observations under the article's setup, not current quotations or deployment guarantees.

At the default 50% threshold, standalone Jev achieves 95.6% accuracy with 31 false positives and 13 false negatives; GPT 6 Luna achieves 97.3% with 17 and 10; Opus achieves 99.0% with 3 and 7. Tuning Jev's threshold yields 95.7%, with 22 false positives and 21 false negatives. Thresholds change the error trade-off even when total accuracy barely moves.

The authors observe that Jev's mistakes concentrate closer to uncertainty, whereas Luna sometimes makes highly confident mistakes. Luna plus Opus achieves 98.5% at $0.33 on easier data but 91.6% at $1.15 on harder data. Standalone rankings need not predict cascade rankings. The proposed explanation about decision models not reasoning is speculation, not an established mechanism.

## Limitations

A balanced synthetic class distribution does not represent a deployment where over-merges are rare. Operational precision and missed-error rates depend on actual prevalence. The article does not sufficiently establish independent threshold-selection and evaluation splits, repeated runs, confidence intervals, or comprehensive calibration metrics.

Harder inputs increase dependence on the expensive model. This vendor experiment does not establish generalization to customer data, detection of under-merges, or end-to-end identity-resolution quality.

## Related notes

- [RIVET: multiturn LLM routing](../llm-infrastructure/2026-rivet-multiturn-llm-routing.md): routes using task and conversation information; its evaluation unit and method differ from this confidence-based cascade.

## Free or low-cost verification proposal — not performed

Create local synthetic records and labels with varying over-merge prevalence, twins, address changes, and shared contacts. First use saved predictions and confidence scores to verify threshold selection on calibration data and scoring on a separate evaluation split. Live model comparisons would incur separate costs and were not run.

Report false positives and negatives, precision and recall, escalation fraction, cost per 1,000, and latency across prevalence settings.

- Use status: proposed only; no implementation, model evaluation, or reproduction.
- Open questions: calibration transfer to real data, threshold maintenance under distribution shifts, and selection using operational error costs.

## Primary source

- [Hightouch article](https://hightouch.com/blog/llm-judges-identity-resolution)
