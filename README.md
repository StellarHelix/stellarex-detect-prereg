# Stage 1 Pre-Registration
---

## Pre-registered metrics

Reported at both sample and sequence/feature level: TPR, FPR, FNR, precision, recall, F1; ROC and precision-recall curves; limit-of-detection curves over coverage x depth x read length x platform; alerts per 1,000 samples; abstention rate; expected calibration error (ECE, 15-bin equal-mass, bootstrap CI).

## Pre-registered targets

**Sensitivity (sample level).** At 50M reads: >=95% TPR for anomalous elements at >=2x element coverage, >=80% at >=1x, at <=1 false alert per 100 samples. Below roughly 1x coverage the sample is reported Inconclusive rather than Benign, by design.

**Attribution (sequence level).** >=80% correct identification of the anomalous region in detected cases, with traceable supporting reads.

**Calibration and restraint.** ECE <=0.05 on held-out baseline data. Abstention is reported rather than capped; <=15% of samples receive no call from any always-available layer.

**Operating points.** Strict (0.5 false alerts per 100 samples), balanced (1 per 100, default), sensitive (5 per 100).

**What we do not claim.** No false-positive rate below 1e-4. Demonstrating one needs roughly 30,000 clean negative samples for a 95% upper bound by the rule of three. By the same arithmetic, a <=1-per-100 claim needs about 300 clean negatives to bound 1% at 95% if none fire, and about 1,000 to separate 1% from 2%. We state that budget rather than a point estimate.

## Pre-registered splits

Leave-one-environment-out; leave-one-clade-out (taxonomy-aware, preventing leakage); leave-one-perturbation-type-out; leave-one-platform-out; leave-one-protocol-out; leave-one-prevalence-out. Nested cross-validation and stress tests for depth, read length and contamination follow. Operating points are chosen on held-out data only.

## Falsification

If Stage 2 shows the method cannot hold a fixed alert budget across varied background without recall collapsing, it does not warrant transition, and we will report that rather than retune until it passes. The test is specified before data receipt.

---

## Sealed protocol

The full pre-registration - including the design assumption under test, the measurement protocol, the named public datasets, the stated expected outcome and the pre-specified response if that expectation is met - is fixed as of today and committed below by hash. The plaintext is withheld only until the measurement publishes, so that the content cannot be revised in the interval.

SHA-256 of `PREREGISTRATION-full.md`, sealed 20 October 2026:

`4da4a7f319943da0c0af3c2f436f79a1519fc4207c35b0870d138e285594ec2e`

Verify on release with `sha256sum PREREGISTRATION-full.md`.

## Scheduled release

By **4 November 2026** this repository will publish, under Apache 2.0: the sealed protocol in plaintext, the measurement result, the analysis code, and the exact public accession list.

| Item | Due | Status |
|---|---|---|
| Pre-registration of metrics, targets, splits | 20 Oct 2026 | Registered |
| Sealed protocol (hash committed above) | 20 Oct 2026 | Sealed |
| Measurement, analysis code, accession list, protocol plaintext | 4 Nov 2026 | Pending |

---

*Contains no Challenge data, no select-agent sequences, and no material provided by DHS.*
