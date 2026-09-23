
# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54

**Verdict output**

All three pass. Note: scope.md's fit profile is still blank ("(Write a few sentences here.)"), so I ranked by rubric evidence only — stated effort and blast radius — rather than by fit.

Shared evidence (repo-facts, same for all three):
- Maintainer activity — Aburke225 (COLLABORATOR) commented 2026-09-16, 6 days ago → pass
- Repository activity — last default-branch commit 2026-09-16 → pass

Ranked accepted:

1. #54 — Resume section detection / leading whitespace. One localized regex bug in _detect_sections(), repro snippet + three named failing tests, zero comments, no assignee. Tightest blast radius of the three.
2. #72 — verify_password should fail closed on UnknownHashError. Stated effort 1–2h, one function plus an xfail removal. Two classmates (mikeng07, DilanCaro) have posted claims and repros; under the Path Review house rule that does not block, and their repros are useful reading.
3. #69 — JSON array fallback in output_parser.py. Stated effort 2–4h, the largest of the three; one classmate claim (jacho15), which again does not block.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Collaborator Aburke225 commented on issues #52/#43 on 2026-09-16, within 30 days."},
      {"name": "Repository activity", "grade": "pass", "evidence": "Latest default-branch commit 2026-09-16 ('chore: track five more manifest entries'), within 90 days."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "One bug: '_detect_sections() ... anchors every section-header pattern at the start of a line', with a runnable repro and three named failing tests."},
      {"name": "Existing ownership", "grade": "pass", "evidence": "assignees: [] and zero comments on the issue."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Collaborator Aburke225 commented on 2026-09-16, within 30 days."},
      {"name": "Repository activity", "grade": "pass", "evidence": "Latest default-branch commit 2026-09-16, within 90 days."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "One behavior in core/security.py: 'Verification against a malformed hash should fail closed (return False), not raise'; estimated effort 1-2 hours."},
      {"name": "Existing ownership", "grade": "pass", "evidence": "assignees: []; claims by mikeng07 and DilanCaro are classmate claims, which the Path Review house rule says do not block."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Collaborator Aburke225 commented on 2026-09-16, within 30 days."},
      {"name": "Repository activity", "grade": "pass", "evidence": "Latest default-branch commit 2026-09-16, within 90 days."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "One defect: '.items() on the parsed value ... raises AttributeError' for top-level JSON arrays; estimated effort 2-4 hours, two files."},
      {"name": "Existing ownership", "grade": "pass", "evidence": "assignees: []; jacho15's claim is a classmate claim, which the house rule says does not block."}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

**Run history**

I completed one scored evaluation run using my initial filled rubric. The result was:

`agreement: 16/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in policy)`

The first two attempts did not produce scored results. The first failed because the rubric was empty, and the second encountered a Windows text-encoding error. After correcting these problems, the evaluation completed and generated eval-run.txt.

I did not complete any further scored evaluation runs.

**Issue analysis**

I chose issue-01 for my analysis.

The evaluation output recorded:

`issue-01  accept  reject   NO     failed: Manageable scope`

My rubric rejected issue-01, while the gold label was accept.

The Manageable scope check requires an issue to describe one identifiable problem or improvement, provide enough information to identify the affected behavior, and avoid major architectural redesign.

My rubric's evaluation of issue-01 did not find sufficient evidence to pass this check, resulting in a reject verdict.

This disagreement suggests that my scope check may be too restrictive in some cases. An issue can be suitable for a first contribution even when its description does not meet every part of my current scope requirement.

**Check rationale**

The check I am analyzing is Manageable scope. Its current wording in my rubric is:

"Pass if the issue describes one identifiable problem or improvement, provides enough information to identify the affected behavior, and does not require a major architectural redesign."

Evidence: Issue body, reproduction steps, and comment thread.

Weight: required.

I included this check because I want the skill to identify issues that a newcomer can reasonably complete. Requiring a specific problem and enough information about the expected behavior helps avoid issues that are too broad or difficult to understand.

I made this check required because an issue that involves major architectural changes may be too difficult for someone making their first contribution.

**Trade-offs**

The main trade-off is that this check can reject issues that are suitable for newcomers but do not satisfy every part of its pass condition.

For example, the evaluation rejected issue-01 and issue-19 because of Manageable scope, even though their gold labels were accept.

The check helps filter out complicated issues, but it may also exclude acceptable issues that require some additional investigation or have less detailed descriptions.

I kept the check because limiting the scope is important for a first contribution, but the evaluation results show that its conditions could be made more flexible.

---

## Selection rationale

**Selection rationale**

1. Fit to my interests and available time:

I chose issue #54 because it involves fixing a specific bug in a Python resume parser. I have experience with Python, and I want to improve my debugging and testing skills. The issue has a clear problem, a reproduction example, and three related tests. I prefer an issue with a small scope that I can work on without spending too much time learning an unfamiliar codebase.

2. What the verdict identified correctly and what I weighed separately:

My skill correctly identified that the repository is active, the maintainer is responsive, the issue has a manageable scope, and nobody is assigned to it.

The skill also identified the relevant function and the existing reproduction example. These details make the issue a reasonable first contribution.

Beyond the rubric, I considered my familiarity with Python and whether I would be comfortable understanding and fixing the problem. I also considered the time I have available and the fact that the issue already identifies related tests.

3. Anticipated difficulty in claiming the issue:

The issue had no assignee or existing comments when I evaluated it, so I do not expect an ownership conflict to be a major problem.

My main challenge will likely be setting up the project locally, understanding how the resume parser works, reproducing the bug, and making sure my changes pass the relevant tests.

I will follow the course instructions for claiming the issue in Unit 2.
