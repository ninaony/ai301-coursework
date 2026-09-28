# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->


## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Last push by maintainer | "last push to any branch" under Repo facts | Within 90 days| required |
| Release recency | the date of the "latest release" under Repo facts | Within the last 150 days | preferred |
| One bounded issue | Information under Issue header and comment thread |  Fails only if one of these is true: (a) the issue is explicitly a checklist/tracking issue where items are meant to be split into separate issues or PRs, (b) the comment thread shows a live, unresolved design disagreement that no maintainer has settled, (c) a maintainer states outright that the fix requires core-internals/architecture changes, or (d) it is a pure usage/support question rather than a concrete change. Multiple examples, root causes, suggested approaches, or files touched do not by themselves fail this check as long as they all serve one described fix or outcome. | required |
| No linked PRs | linked PRs:" with state per PR, plus any PRs mentioned in the Comments section | No PRs that are open in list , and no pattern of two or more abandoned attempts (closed unmerged PRs)| required |
| Contribution policy | the "contribution policy" line under Repo facts | Does not say or strongly imply that they do not accept AI-generated code | required|
s

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

1. Accept if every required check passes. 
2. Preferred checks never change change the verdict, they
rank accepted issues
3. Unclear counts as fail
