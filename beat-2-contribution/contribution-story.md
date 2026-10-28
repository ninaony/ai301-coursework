# Contribution: [Issue Title]

Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** [Nina Onyemeziem]
**GitHub Username:** [ninaony]
**Issue:** [https://github.com/oppia/oppia/issues/21970#issue-2869076131]
**Pull Request:** [GitHub PR link, once opened]

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: Identifying and claming valid issues**

[2-4 sentences: what you built (the scout, your strategy), what broke
or fell short, what changed because of it.]
I built a scout which consisted of a search strategy. In running the additionall scout scans, I refined my issue selection skill to scan for things that the scout is unable to check for and refined my checks from previous feedback (making checks atomic so it's easy to grade a signle thing). The scout wasn't very helpful in terms of finding quality issues because that was hard to define. For example, if you didn't put helpful time constraints, you would only be getting recently created issues that have not been verified yet. So, getting that balance of filtering for quality as best I could without limiting the issues too much was difficult. Thus, I also ended up adding a check in the rubric to make sure the maintainer confirmed it is as viable issue to work on, but since that can happen in many ways (label, comment, issue body, maybe more) I'm not sure it sufficiently checks for everyhthing.

**Unit 6: [one line on the tool work]**

[2-4 sentences: the voice-guard, the repo-memory file. What broke or
fell short, and what changed because of it. "Nothing broke" counts when
it is true - say how you know.]

**Unit 7: [one line on the tool work]**

[2-4 sentences: the ship-gate and your gate manifest. What it produced
on your real branch, what fought you, what changed because of it.]

**Unit 8: [one line on the tool work]**

[2-4 sentences: the PR-monitor and your playbook. What it read, what it
drafted, what you did with the draft.]

---

## Why I Chose This Issue

[1-2 paragraphs in your own words: how you searched, what your scan
surfaced, what your scout's verdict said, why this issue fits your
profile, and what you hope to learn. If your scout's verdict on it
was reject and you chose it anyway, say so here and say why; choosing
against your own tool silently is what loses points. Close with an
honest read of the tool itself: where the scout fell short on a real
wild search and what you changed or would change, or what convinced
you it held up. **Record the link to your claim comment in this section too.**
Not claimed yet? Write `claim pending` and today's date where the link goes,
and add the link the moment your claim lands.]

**Toolkit**

- **Tool:** issue-scout (your scout: your search strategy, your rubric),
  I used it mostly to learn what other conditions I wasn't checking for (maintainer confirming issue was something to be worked on, could be planned for a later release and potentially changed due to current release items) and or other formatting possibilities for issues (the issue I chose ended up having multiple PRs for each item, but given that the issue body mentions that, it still technnically can be a single bounded scope)

- **What it produced:** [the scan and its verdict on this issue, described]
  My rubric graded my claimed issue as reject because of its format. There are multiple items present, but the issue explicitly mentions that there should one PR for each. I checked to make sure that the specific model I want to work on does not have any opened or merged PRs before claming it. The rubric also flagged it as including a need for a proposed design, and while that is true, it's clear that what the issue requires is a data model with fields, so I am not determining what the thing needs to be, I am determining its contents, which is what fixing any bug requires.

  Rubric ranked results:

1. agentic-operator-core #168 (accept). This is the better fit.
   - A collaborator confirmed it and labeled it P1, and nobody is assigned.
   - The repo's last push was 5 days ago and its latest release is 71 days old.
   - Both related PRs (#198, #202) mergeds in the repo.
   - Legacy agentic-k8s-operator labels still remain in config/.
   - It matches your profile better than rastructure code, but it's Go, not Python.
2. agentic-operator-core #133 (accept).
   - It passes every required check, but o of them.
   - The author, a collaborator, labeled it good first issue, help wanted and P2. There are no comments and no
     linked PRs.
   - I grepped the repo and found no Dependabot config, govulncheck, pip-audit, go-licenses or SBOM, so all of
     it is still open.
   - It fits your profile weakly. It's CI and tooling, with no Python.
3. oppia #21970 (reject). It fails three
   - One deliverable: it's a checklist of about 65 models, meant to be done as one PR per model. Design settled: the issue itself sayved before assignment, and the thread isfull of proposals still under review. No linked PRs: 2 PRs are open #27782 PRs that reference the issue were closedunmerged.  
     Things worth knowing th Clawdlinux issues have an AI-attriI check, "AI Attribution Guard," rejectsPRs with Co-authored-by or Signed-off-by trailers naming Claude, Copilot, GPT and similar. The PR templatys commits must be human-authored.

- I graded the contribution policy as a pass, because it bans attribution trailers, not AI-assisted code.It's the closest call.
- The commit attribution this session adds a Co-Authored-By: Claude line, which that check would reject. You'd have to leave that line off the
- The rubric and your fit profile disagree on Oppia. Oppia matches your Python and backend preference best,
  but its umbrella structure fails the ruk there is one model, which the rubriccan't see. That's worth logging in scan-notes.md.
- Two grades involved judgment. I passed because it's an acceptance-criteriachecklist, not an explicit split-into-PRs issue. I passed "Maintainer-confirmed" for Oppia because Members
  are actively approving proposals, even and not a bug. Both grades are generous,and the verdicts don't depend on them.
- I didn't read Oppia's wiki for an AI pohub/CONTRIBUTING.md, and it has anAGENTS.md.

{
"item": "https://github.com/Clawdlinux/agentic-operator-core/issues/168",
"checks": [
{"name": "Last push by maintainer", "grade": "pass", "evidence": "pushedAt 2026-10-23, 5 days ago"},
{"name": "Release recency", "grade"3.0 released 2026-08-18, 71 days ago"},
{"name": "One deliverable", "grade": "pass", "evidence": "one fix: reconcile the part-of label across
producers and add a drift test"},
{"name": "Design settled", "grade": "pass", "evidence": "maintainer comment 2026-10-22 and merged
#198/#202 settle agentic-operator as canoo align"},
{"name": "Not architecture-scale", "grade": "pass", "evidence": "YAML label edits in config/ plus one Go
test, inside existing modules"},
{"name": "Concrete change", "grade": "pass", "evidence": "body lists files and a 3-step fix"},
{"name": "Work still open", "grade"p of main finds agentic-k8s-operatorpart-of in config/rbac, config/shared-services, config/argo"},
{"name": "No linked PRs", "grade": oss-references in timeline; no open PRs inrepo; #198 and #202 merged"},
{"name": "Maintainer-confirmed", "g "COLLABORATOR shreyanshjain7174 statuscomment 2026-10-22 and added P1"},
{"name": "Contribution policy", "gr"AI Attribution Guard rejects AI trailers,but no ban on AI-assisted code; CLAUDE.md present"}
],
"verdict": "accept"
},
{
"item": "https://github.com/Clawdlinusues/133",
"checks": [
{"name": "Last push by maintainer",e": "pushedAt 2026-10-23, 5 days ago"},
{"name": "Release recency", "grade": "pass", "evidence": "v0.3.0 released 2026-08-18, 71 days ago"},
{"name": "One deliverable", "grade"eptance-criteria checklist for one outcome; does not say items are separate PRs (tension: 7 independent items)"},
{"name": "Design settled", "grade":pen-decision label, no comments, nodisagreement; Renovate is an allowed alternative in the acceptance criteria"},
{"name": "Not architecture-scale", ": "CI workflows and config files; no corechanges"},
{"name": "Concrete change", "grade"cceptance criteria incl. dependabot.yml,govulncheck job, SBOM"},
{"name": "Work still open", "grade"dependabot.yml, govulncheck, pip-audit,go-licenses or sbom in .github/Makefile/docs"},
{"name": "No linked PRs", "grade": oss-references in timeline; no open PRs inrepo"},
{"name": "Maintainer-confirmed", "g "no comments; COLLABORATOR author appliedgood first issue, help wanted, P2 (triage labels, not literally confirmed/accepted)"},
{"name": "Contribution policy", "gr"AI Attribution Guard rejects AI trailers,but no ban on AI-assisted code; CLAUDE.md present"}
],
"verdict": "accept"
},
{
"item": "https://github.com/oppia/opp
"checks": [
{"name": "Last push by maintainer",e": "pushedAt 2026-10-28"},
{"name": "Release recency", "grade": "pass", "evidence": "v3.5.3 released 2026-09-23, 35 days ago"}, {"name": "One deliverable", "grade"cklist of ~65 models, one PR per model"},
{"name": "Design settled", "grade": "fail", "evidence": "body requires an approved proposal before assignment; maintainers still reviewing pent 2026-10-25"},
{"name": "Not architecture-scale", "grade": "pass", "evidence": "per-model domain object plus caller refactor inside existing modules"},
{"name": "Concrete change", "grade": "pass", "evidence": "implement domain object with validate() and refactor usages"},
{"name": "Work still open", "grade": "pass", "evidence": "most checklist items unchecked"},
{"name": "No linked PRs", "grade": n PRs (#27785, #27794); 38 of 42referencing PRs closed unmerged"},
{"name": "Maintainer-confirmed", "g "MEMBER jayam04 and Naman3120-Webapproving proposals and assigning models (enhancement, not a bug)"},
{"name": "Contribution policy", "gr"no ban in .github/CONTRIBUTING.md;AGENTS.md present; wiki not checked"}
],
"verdict": "reject"
}

Claim commment link: No claim comment, becuase they had formatting rules in issue that basically only wanted comments claiming to include the proposal which is basically the plan since there's no issue to reproduce outside of setting up environment

- **Difficulties:** [where it fell short, or "none met" if none did]
  I think the rubric still feels short in terms of grading my interests. The candidate issue selection site, pools all the languages that the issue on its repo may contain, so the other two accepted issudes were included even though they're mostly written in Go. These were more of a style or preference check, so it performed correctly, but this was obviously more of a requirement for me.

- **What changed: **[what you patched or would update, or "nothing"]

  Changes made:

- Additional check to make sure maintainer confirmed issue was ready to be claimed
- Split the scope- validation checks since I saw additional examples of bloated scopes (one deliverable, design, not architecture scale, etc. )
- Work still opened so that issues that were more just about documentation for the owners so that they can work in an organized fashion vs needing external help on it

What I would still change:

- Make interests (backend, python) more of a requirement
- Add wiggle room for issues that already make explicit the need for multiple PRs (saw this in another issue as well, not just my claimed one)
- Remove reference or learning repos (they don't have real users)
- Update work still opened or maintainer confirmed to check for evidence in tags like (help wanted, or good first issue) because it shows that it was marked with the intention someone else will work on it

In general, the scout (before rubric) wasn't useful to me because I still had to go out and look for the issues and it returning all issues made in recency order was realy hard to work around because so top 100 always gave you a hard cutoff. I tried using arbitrary time windows (anything created before 2 weeks from now, etc.) I ended up using labels like help wanted or confirmed or accepted to weed out those early unconfirmed issues, and it worked pretty well, but I still only ended up with one accept once because it wasn't able to catch the open PRs. The open PRs is tricky though because it's hard to isolate what's in progress of being merged or just not accepted, or even unmerged. So, it doesn't seem like my scout could be any more refined, which is why in genearl the search part seems not useful. Again, we can't even use it in the candidate issues platform-- not even manually.

---

## Understanding the Issue

**Problem Description**

[In your own words, what is broken or missing?]

**Expected Behavior**

[What should happen?]

**Current Behavior**

[What actually happens?]

**Affected Components**

[Which parts of the codebase are involved?]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Reproduction Process

**Environment Setup**

[What a stranger would need to stand this up: your operating system,
the relevant versions (language, runtime, package manager, the project
itself), and how you set the project up. Then the challenges you faced
and how you solved them, or that none came up.]

**Steps to Reproduce**

1. [Step 1]
2. [Step 2]
3. [Observed result]

**Reproduction Evidence**

- **Commit showing reproduction:** [link to commit in your fork]
- **Screenshots/logs:** [if applicable]
- **My findings:** [what you discovered during reproduction; an
  honest, evidenced cannot-reproduce that led you to re-pick or ask
  the maintainer belongs here and costs you nothing]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Solution Approach

**Analysis**

[Your analysis of the root cause: what is causing the issue, traced
to the files and functions involved.]

**Proposed Solution**

[High-level description of your fix approach, and what you are
deliberately NOT changing.]

**Implementation Plan**

1. [Modify file X to do Y]
2. [Add or change Z]
3. [Update tests]

[Record deviations here as they happen: what changed mid-build and
why. A recorded deviation is honest work; silent drift is not.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Testing Strategy

[What observable checks prove the fix: your reproduction steps re-run
against the built change (before and after), and the repo's own test
suite or checks with the outcome shown. "Tests pass" with nothing
observable named is not a strategy.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Implementation Notes

[A running log, added to as you work. Date each entry. What you
built, decisions you made when you made them, wrong turns included.]

**[Date]**

[Entry]

**[Date]**

[Entry]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Pull Request

**PR Link:** [GitHub PR URL when opened]

**PR Description:** [what the PR says; much of the content above
adapts into it]

**Maintainer Feedback:**

- [Date]: [feedback received, or "none yet"; silence is a normal
  state and costs you nothing]
- [Date]: [how you addressed it]

**Status:** [Awaiting review / Iterating / Merged / Closed. The
status is a fact you record, never a grade: the PR is graded as
opened.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Learnings and Reflections

**Technical Skills Gained**

[What you learned technically, named concretely.]

**Challenges Overcome**

[What was hard and how you solved it; point at the real events, the
Toolkit blocks above are full of them.]

**What I'd Do Differently Next Time**

[Reflection on your process.]

---

## Resources Used

[What actually helped, not a reading list. List things this story
already shows you using: the doc you followed to set the environment
up, the thread that explained the bug, the person who answered you.
One real entry beats ten plausible ones.]

- [Link to documentation that helped]
- [Discussion, issue, or post that helped]
