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


## Week 8 — Reproduction & solution planning

**Reproduction commit link:** [link to commit documenting the reproduced issue]

**Reproduction steps:**
1. Open the resume parser in Python and use these two text samples:

```python
good = "Experience:\nSenior Dev\n\nEducation:\nBS CS"
bad = "  Experience:\nSenior Dev\n\n  Education:\nBS CS"
```

2. Run `_detect_sections()` on both samples.
3. Confirm that the normal input returns detected sections like `['Experience', 'Education']`, while the input with leading spaces returns `[]`.

**Reproduction summary:**
I reproduced the issue by running the resume parser on text where section headers had leading spaces, such as `  Experience:` and `  Education:`. In that case, `_detect_sections()` missed those headers, while the same text without the leading spaces was detected correctly.

**PLAN.md link:** [link to PLAN.md in your fork]

**Walkthrough video (recommended):** [link to your Loom video, ≤2 min — recommended, not graded]

**Blockers or open questions:**
[Anything you're still uncertain about going into Week 9, or leave blank]