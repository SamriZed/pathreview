## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/147

**Issue title:** Resume section detection fails on text with leading whitespace
 

**Tier:** [✔] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The issue is in ingestion/resume_parser.py, where the section-detection logic does not handle lines that start with a space. Because of that, the parser can miss section headers and end up returning empty or incomplete output. A successful fix would make the parser ignore leading whitespace before checking for sections, so resumes with slightly messy formatting still parse correctly.

**"Is this right for me?" checklist**
I can explain the issue in my own words. 

I have a good understanding of the codebase and the problem.

I chose Tier 1, because this is my first open source contribution.

**Branch name:** fix/147-resume-parser-detection-error

**Setup confirmation:** [✔] App runs locally at localhost:5173

**Cohort ledger:** [✔] Issue added to cohort ledger