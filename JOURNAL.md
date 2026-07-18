## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/150

**Issue title:** Tech detector counts vendored and build-output files, skewing language detection

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
tech_detector.py fails to filter out biuld-output files such as node_modules/ and build/ directories. This causes the vendored or bundles files to be counted alongside actual source code. As a result, it is misclassified as primarily JavaScript instead of Python. There is failed tests.

**Branch name:** fix/150-tech-detector-skewing-language-detection

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [x] Issue added to cohort ledger