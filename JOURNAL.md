## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/150

**Issue title:** Tech detector counts vendored and build-output files, skewing language detection

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
tech_detector.py fails to filter out biuld-output files such as node_modules/ and build/ directories. This causes the vendored or bundles files to be counted alongside actual source code. As a result, it is misclassified as primarily JavaScript instead of Python. There is failed tests.

**Branch name:** fix/150-tech-detector-skewing-language-detection

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [x] Issue added to cohort ledger

## Week 8 — Reproduction & solution planning

**Reproduction commit link:** https://github.com/fuentesjm/pathreview/commit/65e11fd9b7987b1465447a556e5d8f89093c206c



**Reproduction summary:**
I ran pytest tests/unit/test_tech_detector.py and found test_node_modules_excluded and test_build_directory_excluded already failing: a repo with a root-level node_modules/ or build/ directory reports primary_language: "JavaScript" instead of "Python". The root cause is _should_skip_file, whose skip patterns require a leading slash (/node_modules/), so top-level vendored/build directories are never excluded and their files skew language detection.

**PLAN.md link:** https://github.com/fuentesjm/pathreview/blob/fix/150-tech-detector-skewing-language-detection/PLAN.md


**Walkthrough video (recommended):** [link to your Loom video, ≤2 min — recommended, not graded]

**Blockers or open questions:**
[Anything you're still uncertain about going into Week 9, or leave blank]