# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57


**Verdict output**

Scope check: all three are in codepath/pathreview-ai301-fa26-s3 — in scope. Applying the Path Review house rule (claim comments don't block).

Accepted:
1. #57 — Tech detector counts vendored/build files (only accepted candidate). Fit: closest match to your backend focus — it's a Python heuristic/parsing bug in agent/tools/tech_detector.py (not really ML, more backend tooling logic), narrow and unclaimed by anyone with actual code.

2. #13 (integration test for the RAG pipeline) passes "One bounded issue" by the letter of your four clauses — no checklist, no comment thread (0 comments) to show disagreement, no maintainer statement, not a support question. But read the body again: "ReviewGenerator builds its own OpenAI client, so the test needs a way to pass in a fixed response." Nobody has said how — monkeypatch, a constructor param for client injection, an env var pointing at a mock server — and picking one is a real design decision that could mean touching ReviewGenerator's internals, not just adding a test file. That's structurally the same shape as issue-20: an unresolved design question sitting in silence, no thread to show it, so none of your four clauses catch it. It still passes per the rubric as written — I'm noting the tension, not overriding the verdict.

3. #59 (faithfulness checker word-overlap bug) is clean by comparison: single function, single failing test, the fix is narrowing an over-eager heuristic rather than deciding an open design question. This is also the stronger fit for you content-wise — it's a real RAG-evaluation/NLP problem (why "Knows Python" vs "python expert" scores differently), squarely in the ML-adjacent territory you said you want, versus #13 which is closer to test infrastructure/mocking design than ML principles. One heads-up: PR #80 ("tolerate None text in faithfulness checker context chunks") is open on the same file, but it's a different bug (None-handling, not word-overlap scoring) and doesn't reference #59 — so it's not a linked-PR conflict, just a same-file neighbor worth knowing about.

Rejected:
- #53 — PII scrubber parenthesized phone numbers: sunk by No linked PRs — open PR #77 ("Fixes #53") already exists, unmerged. The house rule forgives claim comments (and #53 has plenty — 8 different students), but not an actual open PR; someone's already written the fix.
- #69 — Output parser crashes on JSON array: same failure — open PR #79 ("Fixes #69") already exists, unmerged.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "narrow bug: excludes node_modules/build paths in TechDetector; 2 named failing tests; no checklist, no thread disagreement, no maintainer core-change statement, not a support question"},
      {"name": "No linked PRs", "grade": "pass", "evidence": "no PR in the repo's open-PR list or PR search references #57; only one claim comment (ApoorvThite), no code submitted"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/53",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "clear repro steps, named file/line, multiple independent reproductions converging on the same root cause (phone_us separator regex); no checklist, no maintainer core-change statement, not a support question"},
      {"name": "No linked PRs", "grade": "fail", "evidence": "open PR #77 'fix: redact parenthesized US phone numbers in PII scrubber', body says 'Fixes #53', state open/unmerged"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "single crash path (.items() on a list), named file/test, estimated effort 2-4h stated in issue body; no checklist, no maintainer core-change statement, not a support question"},
      {"name": "No linked PRs", "grade": "fail", "evidence": "open PR #79 'fix: handle top-level JSON arrays in output parser', body says 'Fixes #69', state open/unmerged"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/59",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "single function (_is_supported), single failing test named, root cause is an over-strict word-overlap heuristic; no checklist, no thread disagreement, no maintainer core-change statement, not a support question"},
      {"name": "No linked PRs", "grade": "pass", "evidence": "PR search for #59 returns 0 results; open PR #80 touches the same file but a different bug (None-text handling), does not reference #59"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/13",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "single deliverable (one integration test file) with named relevant files and estimated effort; no checklist structure, no comment thread (0 comments) so no visible disagreement, no explicit maintainer core-change statement, not a support question — note: the issue itself states the mock-injection approach is undecided ('needs a way to pass in a fixed response'), which none of the four clauses are worded to catch since there's no thread to show it"},
      {"name": "No linked PRs", "grade": "pass", "evidence": "PR search for #13 returns 0 results; not present in the open-PR list"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "accept"
  }
]

```

**The verdict must record `accept` for this issue.** 

Faithfulness checker scores claims unsupported when the context uses different words #59

```json
{
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/59",
    "checks": [
      {"name": "Last push by maintainer", "grade": "pass", "evidence": "repo pushed_at 2026-09-16, within 90 days"},
      {"name": "Release recency", "grade": "unclear", "evidence": "no releases published in this repo"},
      {"name": "One bounded issue", "grade": "pass", "evidence": "single function (_is_supported), single failing test named, root cause is an over-strict word-overlap heuristic; no checklist, no thread disagreement, no maintainer core-change statement, not a support question"},
      {"name": "No linked PRs", "grade": "pass", "evidence": "PR search for #59 returns 0 results; open PR #80 touches the same file but a different bug (None-text handling), does not reference #59"},
      {"name": "Contribution policy", "grade": "pass", "evidence": "no CONTRIBUTING.md in repo (404) — silence, no restriction"}
    ],
    "verdict": "accept"
  }
```




## Eval iterations


**Run history**

1. agreement: 12/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in clear-accept)
run written to eval-run.txt
2. agreement: 14/20 scored items  (bar: 18/20: below the bar)
run written to eval-run.txt
3. agreement: 18/20 scored items  (bar: 18/20: PASS)
run written to eval-run.txt
4. agreement: 19/20 scored items  (bar: 18/20: PASS)
run written to eval-run.txt
5. agreement: 18/20 scored items  (bar: 18/20: PASS)
run written to eval-run.txt
6. agreement: 19/20 scored items  (bar: 18/20: PASS)
run written to eval-run.txt

**Issue analysis**

`issue-20` 

Rubric decision: accept

Golden Label: reject 

Reason: graded accept



**Check rationale**

Name: One bounded issue

Evidence: Information under Issue header and comment thread

Pass condition: Fails only if one of these is true: (a) the issue is explicitly a checklist/tracking issue where items are meant to be split into separate issues or PRs, (b) the comment thread shows a live, unresolved design disagreement that no maintainer has settled, (c) a maintainer states outright that the fix requires core-internals/architecture changes, or (d) it is a pure usage/support question rather than a concrete change. Multiple examples, root causes, suggested approaches, or files touched do not by themselves fail this check as long as they all serve one described fix or outcome. 

**Weight:** required 



**Trade-offs**

This check was written to try to satisfy all the possible ways an issue description could beyond a single bounded scope. At first, my wording was more about the polish vs acknowledging that many files or elements could be mentioned despite all describing a singular issue, which is why I failed a lot at the beginning. But the Claude heldped me realize that it was much easier to describe what a failed look like
because what's wrong into a smaller set of recognizable patterns. 

The cost is that any pattern I fail to name defaults to a pass, not a fail. Thus, my gaps become false accepts rather than false rejects, which for a first-issue picker is the more expensive mistake to make. That means my pass condition list does require me to actually be more exhaustive. 

For example, issue-20 fails currently because my rubric defines an undefined spec in the context of a disagreement, however in issue-20, it's more of a neutral thing. I think the wording "disagreement" means that my grader is looking for explicit conflict. I would be able to easily edit that in, but since I don't know all the common cases, I could run into some issues. 

So the tradeoff is that my wording requires me to list out each possibility that could cause a fail, which requires me to be more exhaustive of what I list. 


---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**



1. The issue's fit to your interests and to the time available.

I was looking to do something related to ML, and so I really wanted a rag tagged issue, which issue has. It's also tagged as tier 1, which I think will be a good introduction issue for me since I've only ever cotributed to OSS in the context of the previous AI Codepath course. 

2. What the verdict identified correctly, and what you weighed that the rubric could not.

My rubric helped verify that the content was actually scoped and the tier-1 issue tag was actually accurate. The bug looks scoped, and the fact that a test case has already been written for it makes it easier for me to reproduce. My previous fix in AI201 had a similar shape , so I figured this would be good as my intro contribution.

3. The anticipated difficulty in claiming it.

I don't anticipate this to be very difficult at least to reproduce since there is an established test that's failing. I understand vaguely there's maybe some a measurement of similarity issue, but I'm not sure if it's LLM related or some regex rules. I also don't fully get the intended use case of this yet, but I have confidence I will figure it out as there's an example provided, so once I see the code, I'll become more familiar.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
