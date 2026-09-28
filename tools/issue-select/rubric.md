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

prev one bounded issue description:Information describes an issue that doesn't require dependencies in order to fix. Multiple examples, possible causes, suggestions for potential fixes, or files to be changed are fine so as long they are all contributing to a single issue being fixed. 
-->


## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer response latency | Reply times in maintainer first-response sample under Repo facts  | 2 out of 5 reply times are 7 days or less | required |
| Last push by maintainer | "last push to any branch" under Repo facts | Within 90 days| required |
| Release recency | the date of the "latest release" under Repo facts | Within the last 150 days | preferred |
| One bounded issue | Information under Issue header | Presence acceptance criteria that describes one atomic issue (no dependencies, multiple sub-items) | required |
| No asignees | "this issue: assignees:" under Repo facts |  | required |
| Contribution policy | the "contribution policy" line under Repo facts | Does not say or strongly imply that they do not accept AI-generated code | required|


## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

1. Accept if every required check passes. 
2. Preferred checks never change change the verdict, they
rank accepted issues
3. Unclear counts as fail
