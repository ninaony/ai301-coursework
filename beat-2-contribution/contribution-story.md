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

**Unit 6: Checking claim comment and reproducing issue**

Nothing broke as my claim was pretty much one sentence and the design doc that was required by the issue description took up much of the space. Since it was a design doc, I had to be specific about files and where I was getting my information, and there was no AI contribution policy. My tool acknowledge went further and gave accurate warnings on the accuracy of my design, and they were actually helpful suggestions.

It actually did break a bit when introducing repro steps because my rubric was originally calibrated for issues that were bugs and not enhancements.

**Unit 7: [one line on the tool work]**

[2-4 sentences: the ship-gate and your gate manifest. What it produced
on your real branch, what fought you, what changed because of it.]

**Unit 8: [one line on the tool work]**

[2-4 sentences: the PR-monitor and your playbook. What it read, what it
drafted, what you did with the draft.]

---

## Why I Chose This Issue

**Toolkit**

- **Tool:** issue-scout (your scout: your search strategy, your rubric),
  I used it mostly to learn what other conditions I wasn't checking for (maintainer confirming issue was something to be worked on, could be planned for a later release and potentially changed due to current release items) and or other formatting possibilities for issues (the issue I chose ended up having multiple PRs for each item, but given that the issue body mentions that, it still technnically can be a single bounded scope)

- **What it produced:**
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

Claim commment link: https://github.com/oppia/oppia/issues/21970#issuecomment-6968321411

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

As it stands, there's a bunch of data models that are being accessed across service functions, and the maintainers want domain objects that can be validated to be created and refactor the code to reflect those changes.

**Expected Behavior**

Instead, service functions outside the gets/save functions should only interact with the domain objects instead of directly with the model.

**Current Behavior**

The StartEventExplorationLogEntryModel has no domain object. StartExplorationEventHandler.\_handle_event (event_services.py:228-241) passes raw arguments straight to StartExplorationEventLogEntryModel.create (event_services.py:240). create builds and saves the model with no validation (gae_models.py:466-511).

In production code, this is the only place the model is used. Tests also use it directly:

reader_test.py:2912, 2925, 2929, 2950 read the model back with get_all().
event_services_test.py:128, 135 do the same.
gae_models_test.py:250, 259 call create and get on the model directly.

**Affected Components**

- `core/domain/stats_domain.py` (adding domain object and helper functions) and its tests `core/domain/stats_domain_test.py`.

- `StartExplorationEventHandler.\_handle_event` (event_services.py:228-241) and its tests `event_services_test.py:132`
- reader_test.py:2904 (test_starting_a_state)

**Toolkit**

- Tool: Na - I didn't build a skill for this, I just chatted with Claude to trace the code manually and verify my understaneding.
- What it produced: Na
- Difficulties: Na
- What changed: Na

---

## Reproduction Process

**Environment Setup**

1. Install Rosetta and open an Intel (x86_64) terminal (as is)
2. Install Intel Homebrew for the build libraries (slightly different: it is no longer supported, so I used MacPorts with build_arch x86_64 instead)
3. Install direnv (slightly different: I downloaded the amd64 binary from its GitHub releases instead of using Homebrew)
4. Create the direnvrc file with the wiki's use_python function (as is)
5. Install git, fork the repo, clone it and add the upstream remote (as is)
6. Install pyenv with curl pyenv.run | bash and add its lines to ~/.zshrc (as is)
7. Install the pyenv build dependencies (slightly different: I installed them with MacPorts rather than Homebrew)
8. Install Java (as is)
9. Build Python 3.12.13 with pyenv (slightly different: I had to add PYTHON_CONFIGURE_OPTS="--with-openssl=/opt/local/libexec/openssl3", because MacPorts puts OpenSSL where pyenv doesn't look)
10. Create .envrc with use python 3.12.13, run direnv allow, then python -m scripts.start (as is)

**Steps to Reproduce**

Environment: run everything from the repo root on branch `develop`.

1. Run `git checkout 89cbd7e566`

To demonstrate that no domain class exists for the Start event grep -rn "StartExplorationEventLogEntry" core/domain/

2. Run `grep -rn "StartExplorationEventLogEntry" core/domain/` and
   Run `grep -n "^class .\*StartExploration" core/domain/stats_domain.py`

Observed result:
core/domain/event_services_test.py:128: all_models = stats_models.StartExplorationEventLogEntryModel.get_all()
core/domain/event_services_test.py:135: all_models = stats_models.StartExplorationEventLogEntryModel.get_all()
core/domain/event_services.py:240: stats_models.StartExplorationEventLogEntryModel.create(

Observed result: nothing

To demonstrate there's no validation occurs before data being saved into model

3. Run `grep -n "validate" core/domain/event_services.py` and
   `sed -n 396,500p core/storage/statistics/gae_models.py | grep -n "validate"`

Observed result: nothing

Observed result: nothing

**Reproduction Evidence**

- **Commit showing reproduction:** 89cbd7e566 (repo commit showing the state of code where I ran the above code)
- **Screenshots/logs:** Shown above
- **My findings:**

1. The environment setup was difficult because as noted above, because Homebrew was deprecated for Intel, I had to do some of the workarounds. Granted, there was a lot of documentation provided, but I've never really had to do anything that required a Windows OS on my Mac, so there was a bit of a learning curve there.
2. Since a plan (they called it a design proposal) was required before approval, I noted some questions in my claim comment. For example, the changes required affected how current tests were setup. For example, the validation checks imply that the domain object should be validated and then saved into the data store, but the base model's save function passes in values directly for some of the properties. That means, the properties your validating aren't necessarily the ones getting saved, and so I asked about that, and the maintainer responded to keep the base model's save function as is, so I'm taking that to mean that it's okay. He also had some other notes on some checks I should change, but overall my plan was approved.

**Toolkit**

Tool: Repro-check

- What it produced:
  Verdict: accept. Your rubric changed, and that flipped the one failing check.
- "No vague references" now passes if a paraphrased step names its source. Your repro links the Oppia wiki page for the setup, so it passes.
- "Output error behavior matches issue gap" keeps the "missing feature" wording, and the greps still show the gap.

The skill's references/evidence-guide.md still doesn't exist, so I found the evidence myself. The scout did grade #21970 (in scan-output-week6.md, where it rejected the issue), so scope allows grading it.

| Check                         | Grade | Evidence                                                                                                      |
| ----------------------------- | ----- | ------------------------------------------------------------------------------------------------------------- |
| Traceable proof               | pass  | Step 1 is git checkout 89cbd7e566, and setup names Python 3.12.13.                                            |
| Output error behavior matches | pass  | The greps show no StartExploration domain class and no validate in event_services.py issue gap or the model.  |
| No vague references           | pass  | The setup is "paraphrased from" the linked Oppia wiki page. Every grep step names the file and its arguments. |
| Adheres to disclosures        | pass  | I found no AI-disclosure requirement in Oppia's CONTRIBUTING.md.                                              |
| Generic claim comment         | pass  | The claim names StartExplorationEventLogEntryModel and specific files, with no completion promises.           |
| No AI-isms (preferred)        | pass  | No em dashes or leftover prompt text.                                                                         |

Caveats the rubric doesn't catch

- Scope rule on duplicates: the claim draft would be a duplicate of your own comment, posted 2026-11-18, and you're already assigned. scope.md says "never duplicate", so don't repost it. The repro may still be useful as a comment on the thread or in your PR description.
- Claim contradicts the maintainer. The draft still says session_id is length 24, keeps id as a property and changes the create() signature. @iHamza14 told you the opposite on all three. It also has the base_mode typo and the state_domain.py filename.
- Voice guide: your rule "Reproducible steps that don't logically track … underspecified" still applies to setup steps 4, 6, 7 and 8. They pass the rubric, but they're still vague ("the wiki's use_python function", "add its lines to ~/.zshrc").
- Formatting: the trailing duplicate "Observed result: nothing" lines are unclear about which command each belongs to.

{
"item": "https://github.com/oppia/oppia/issues/21970",
"checks": [
{"name": "Traceable proof", "grade": "pass", "evidence": "Step 1 'git checkout 89cbd7e566'; setup names Python 3.12.13"},
{"name": "Output error behavior matches issue gap", "grade": "pass", "evidence": "Greps show no StartExploration domain class and no 'validate' in event_services.py or the model's create() range"},
{"name": "No vague references", "grade": "pass", "evidence": "Setup is 'paraphrased from the Oppia site' with the wiki link; grep steps give file names and arguments"},
{"name": "Adheres to disclosures", "grade": "pass", "evidence": "No AI-disclosure requirement found in Oppia's CONTRIBUTING.md"},
{"name": "Generic claim comment", "grade": "pass", "evidence": "Claim names StartExplorationEventLogEntryModel and specific files; no completion promises"},
{"name": "No AI-isms", "grade": "pass", "evidence": "No em dashes or prompt artifacts in either draft"}
],
"verdict": "accept"
}

- Difficulties:
- The rubric just seemed to have so much sensitivity on certain things which I guess is the point. Like the whole vague references when paraphrasing the setup documentation. The only reason why I wanted to paraphrase instead of just say plainly follow the steps was because there were various setup options and I ran into so many random errors, that I had to just keep cheryrypicking which set of options I wanted. I think making me include the link was reasonable, but I guess I was just annoyed at to how precise I have to be, which again, probably is good in the long run.
- What changed:
  I had to change my rubric to include in wording for enhancements. It was previously written to only check for bugs, so I made it so that it was generalized to whatever the issue describe vs just looking for an error.
  I also had to update "No vague references" because it was determinig my paraphrasing of the the exact setup steps from the repo as vauge.

---

## Solution Approach

**Analysis**

Na - this is enhancment so there is no bug to figure out the root cause for

**Proposed Solution**

**The claim comment I posted with my plan:**
Hi @iHamza14, I'd like to take on this issue for StartExplorationEventLogEntryModel.

**File name:** core/domain/stats_domain.py

**Properties and validation checks**

`id`: Type is string of length <= ID_LENGTH (core/storage/base_mode/gae_models.py:88)

`event_type`: Type is string that matches feconf.EVENT_TYPE_START_EXPLORATION

`exploration_id`: Type is string of 1 to 12 chars, each a letter, digit, hyphen or underscore (matches constants.ENTITY_ID_REGEX )

`exploration_version`: Type is not a boolean and int >= 1

`state_name`: Type is string; Length does not exceed constants.MAX_STATE_NAME_LENGTH; passes utils.require_valid_name()

`session_id`: Type is string of length 24 (utils.py:798-805)

`client_time_spent_in_secs`: Type is a float = 0.0

`params`: Type is a dict; For each param: key and value type is a string

`play_type`: Type is string that matches feconf.PLAY_TYPE_PLAYTEST or feconf.PLAY_TYPE_NORMAL

`event_schema_version`: Type is not a boolean and int of value x where 1 <= x <= feconf.CURRENT_EVENT_MODELS_SCHEMA_VERSION

**Refactor**

StartExplorationEventHandler.\_handle_event() in core/domain/event_services.py will construct and validate the domain object before persisting it via the service layer.

Open question: Does stats_models.StartExplorationEventLogEntryModel.get_all() count as violating the no model usage outside get/save requirement? If so, plan is to replace with get_start_exploration_event_from_model(). If not, is the model to domain function necessary since nothing else currently reads this model?
Helper conversion/persistence and get_start_exploration_event_from_model() methods will be housed in core/domain/event_services.py

create() in core/storage/statistics/gae_models.py:475 signature change to include domain properties

Open question: Should unused_version: int = 1 be removed as it is never accessed?

**Test coverage**

Add unit tests in core/domain/stats_domain_test.py covering valid properties and all invalid edge cases

Changes in the current test:

Controller tests core/controllers/reader_test.py:2904 - uses invalid dummy values if above validation is accepted for session_id, state_name, maybe params
Service tests in core/domain/event_services_test.py - same as above
Model tests in core/storage/statistics/gae_models_test.py:240 - signature change

Open questions
Should I include helper methods (eg to_dict())?
Request schema reader.py:1086-1092 shows that params value accept int or string values while \_handle_event() in event_services.py:234 is typed string. My validation rule uses the latter, is that okay?

**Implementation Plan**

The steps are modeled after maintainer feedback of my approach since its a requirement of this issue.

1. In core/domain/stats_domain.py, add StartExplorationEventLogEntryDict (a TypedDict) and StartExplorationEventLogEntry, with to_dict() and validate().
2. In core/domain/event_services.py:
   - Add get_start_exploration_event_from_model().

- Change StartExplorationEventHandler.\_handle_event (lines 228-241) to build and validate the domain object first, then call create() with its fields.

3. In core/domain/stats_domain_test.py, add tests for a valid object, to_dict(), and one failing case per check.
4. In core/domain/event_services_test.py, add tests for get_start_exploration_event_from_model() and for invalid input being rejected before anything is stored.
5. In core/controllers/reader_test.py, change the params value at lines 2920 and 2938 to a string, because the int fails the Dict[str, str] rule. The 'state_name' and 'session_id' values in that test, and event_services_test.py:132, should still pass.
6. Run the three affected test files and confirm 100% line and branch coverage on the new code.

**Toolkit**

- Tool:
- What it produced:
  Verdict: reject (hold). The plan's own text still contradicts the maintainer's reply to your claim. It also has no "won't change" statement, so two required checks fail.

I read plan.md as both the plan and the comment, since plan-comment.md doesn't exist. The reply I'm checking against is @iHamza14's on issue #21970, which assigned you the model.

┌────────────────────────────┬────────────────────┬────────────────────────────────────────────────────────────────────────────────────┐
│ Check │ Grade │ Deciding fact │
├────────────────────────────┼────────────────────┼────────────────────────────────────────────────────────────────────────────────────┤
│ diagnosis-matches-evidence │ unclear (counts as │ The plan says "Na - this is enhancement", so it states no cause. There is no repro │
│ │ fail) │ comment either. │
├────────────────────────────┼────────────────────┼────────────────────────────────────────────────────────────────────────────────────┤
│ within-issue-scope │ fail │ Files are named, but nothing says what won't change. The plan also proposes │
│ │ │ changes the maintainer ruled out. │
├────────────────────────────┼────────────────────┼────────────────────────────────────────────────────────────────────────────────────┤
│ test-target-cause │ pass │ Tests add one failing case per validate() check in stats_domain_test.py, which is │
│ │ │ what the issue asks for. │
├────────────────────────────┼────────────────────┼────────────────────────────────────────────────────────────────────────────────────┤
│ Adheres to disclosures │ pass │ I found no AI-disclosure rule in .github/CONTRIBUTING.md, the PR template or the │
│ │ │ thread. I did not check the wiki. │
└────────────────────────────┴────────────────────┴────────────────────────────────────────────────────────────────────────────────────┘

Contradictions with the maintainer's reply

- The maintainer said to validate session_id as a non-empty string and not enforce length 24. Your plan still says "string of length 24".
- The maintainer said to omit id from the domain object. Your id row is still there.
- The maintainer said not to change the create() signature and to leave unused_version alone. Your plan still has a "create() … signature change", an open question about removing unused_version, and a model-test change for the signature.
- Your Implementation Plan says it is "modeled after maintainer feedback", but the properties and refactor sections above it aren't.
- The scope file says maintainer direction outranks your plan. These items are what hold the package.

Fixes before you post

1. Remove id, the length-24 rule, and the create()/unused_version items. Drop the model-test signature change.
2. Settle the two open questions the maintainer answered: to_dict() is included, and Dict[str, str] is correct.
3. Add a "Not changing" line: create(), unused_version and gae_models.py.
4. Add one line saying this is an enhancement and what the missing domain object is. That should satisfy the diagnosis check.

Voice guide: The plan repeats itself, which breaks your "overly long prose / redundant content" rule. Properties, Refactor, Test coverage and Implementation Plan restate the same changes. Your other rules aren't broken.

Gaps in my procedure and rubric

- The rubric has no case for an enhancement with no repro.
- It has no check that the plan follows maintainer direction, even though scope.md requires it.
- The evidence guide describes an Executability check, but the rubric has no matching row.
- The read order never mentions reading the issue thread.

{
"item": "https://github.com/oppia/oppia/issues/21970",
"checks": [
{"name": "diagnosis-matches-evidence", "grade": "unclear", "evidence": "Plan states 'Na - this is enhancement so there is no bug to figure out the root cause for'; no repro evidence exists and the rubric has no enhancement case, so unclear counts as fail."},
{"name": "within-issue-scope", "grade": "fail", "evidence": "Files are named but no 'will not change' statement exists, and the plan still proposes a create() signature change that the maintainer said not to make."},
{"name": "test-target-cause", "grade": "pass", "evidence": "Step 3 adds stats_domain_test.py tests for a valid object, to_dict(), and one failing case per validate() check, which exercises the missing domain object and validation the issue asks for."},
{"name": "Adheres to disclosures", "grade": "pass", "evidence": "No AI-disclosure requirement found in .github/CONTRIBUTING.md, the PR template, or the issue thread; the wiki was not checked."}
],
"verdict": "reject"
}

- Difficulties:
  Since my plan comment had to be written with the claim, it technically contradicts the new implementation plana nd feedback from the maintainer. I however cannot change the comment anymore. Also, in terms of not including a "won't touch" file list, technically, with the maintainer feedback, it's clear that the base model file won't be touched.
- What changed:
  Nothing because I think this may be a unique case of having to design something beforehand. I maybe should have just re-edited the original comment, but I wasn't sure if that would be following the assignment.

---

## Testing Strategy

Gap checks, rerun after the fix.

These are the commands from my repro, and they should now show:
grep -n "^class .\*Event" core/domain/stats_domain.py shows StartExplorationEventLogEntry. Before, it showed nothing.
grep -n "validate" core/domain/event_services.py shows a validate() call. Before, it showed nothing.
git diff core/storage/statistics/gae_models.py is empty, so create() is unchanged.
Outside gae_models.py and the tests, the model is referenced only in the conversion and save code in event_services.py.

Existing tests: After changing params at reader_test.py:2920 and 2938, rerun the same command and save the output as test_after.txt. The three modules should still pass, compared with test_before.txt (218 passed).

New tests: The new tests in stats_domain_test.py (valid object, to_dict(), one failure per check) and event_services_test.py (get_start_exploration_event_from_model(), invalid input rejected before saving) pass with 100% coverage of the new code.

**Toolkit**

- Tool: na - Only Claude Code was used to refine the testing strategy.
- What it produced: na
- Difficulties: na
- What changed: na

---

## Implementation Notes

[A running log, added to as you work. Date each entry. What you
built, decisions you made when you made them, wrong turns included.]

**11/23**

- Used claude to implement the plan. Honestly, because so much upfront work happened, there wasn't many hiccups.

Here are some of the small bumps enocuntered:

- The repo's pre-commit hook couldn't find ruff, so had to be retried with my venv on PATH.
- Lint still reports errors. The only ones are CODEOWNERS complaints about your untracked files: test_before.txt, CLAUDE.local.md, requirements_dev 2.txt and dump 2.rdb. Since these are related to this course and my environment setup and thus not commiting them, I think it's okay

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Pull Request

**PR Link:** Na

**PR Description:**
Draft:
**PR title:** Fix part of #21970: Add StartExplorationEventLogEntry domain object

---

## Overview

This PR does the following: it adds a domain object with a `validate()` method for `StartExplorationEventLogEntryModel`, following the plan approved by @iHamza14 on the issue (https://github.com/oppia/oppia/issues/21970#issuecomment-7050732096). Before this change, start events were saved with no validation of their values, and the storage model was used directly by the event handler.

- Adds `StartExplorationEventLogEntry` and `StartExplorationEventLogEntryDict` to `core/domain/stats_domain.py`, with `to_dict()` and `validate()`. The object has no `id`, because the entity ID is generated when the model is saved. `validate()` checks that:
  - `event_type` is the start exploration event type.
  - `exploration_id` matches `constants.ENTITY_ID_REGEX`.
  - `exploration_version` is an int that is at least 1 (booleans are rejected, since `bool` is a subclass of `int`).
  - `state_name` is a string with a length between 1 and `constants.MAX_STATE_NAME_LENGTH`.
  - `session_id` is a non-empty string.
  - `client_time_spent_in_secs` is the float `0.0`.
  - `params` is a dict with string keys and string values.
  - `play_type` is `playtest` or `normal`. The `playtest` value is legacy but can still exist in stored events.
  - `event_schema_version` is an int between 1 and `feconf.CURRENT_EVENT_MODELS_SCHEMA_VERSION` (booleans are rejected).
- Adds `get_start_exploration_event_from_model()` to `core/domain/event_services.py`. `StartExplorationEventHandler._handle_event` now builds and validates the domain object before it creates the storage model, so invalid values are never stored. `StartExplorationEventLogEntryModel.create()` is unchanged.
- Adds tests for every validation branch, `to_dict()`, the conversion function, and invalid input being rejected before anything is stored.

### Deviations from the plan

- **`state_name` uses a looser rule than my proposal.** My proposal said `utils.require_valid_name()`. This PR checks for a non-empty string within `constants.MAX_STATE_NAME_LENGTH` instead, because the existing test value `'state_name'` contains `_`, which is in `INVALID_NAME_CHARS` (`assets/constants.ts`), so `require_valid_name()` would reject it. The same rule was approved on the `CompleteExplorationEventLogEntryModel` plan on this issue.
- **Changes from my proposal that the maintainer asked for:** the domain object has no `id`, `session_id` is only checked for being non-empty (not for length 24), `create()` and `unused_version` are left untouched, `to_dict()` and the TypedDict are included, and `params` is validated as `Dict[str, str]`.
- **Test changed:** in `core/controllers/reader_test.py`, `test_starting_a_state` posted `params` with an int value (`{'test_param1': 1}`), which `Dict[str, str]` rejects, so both the request and the assertion now use a string value.

### Things for reviewers to check

- **Requests that the controller accepts can now fail validation.** The request schema in `core/controllers/reader.py` (`HANDLER_ARGS_SCHEMAS`, `params` and `session_id` and `state_name`) still accepts int `params` values and any string for `session_id` and `state_name`. A request with an int param value, an empty `session_id` or `state_name`, or a `state_name` longer than 50 characters now raises a `ValidationError` in `_handle_event` instead of being stored. I haven't checked how the controller turns that into a response, and I did not change the schema because it was outside the plan. Should the schema be tightened to match?
- **`create()` is still called from `_handle_event`.** As in the plan, there is no separate save helper, so the storage model is referenced in `_handle_event` and in `get_start_exploration_event_from_model()`. I can add a save helper if you would prefer the model to be used only in get and save functions.
- **Stored values for three fields still come from `create()`.** `create()` sets `event_type`, `client_time_spent_in_secs` and `event_schema_version` itself, so for new events the values validated on the domain object are the same constants that `create()` stores. Validating those fields is only meaningful when the object is built from a stored model.
- **Existing tests still read the model with `get_all()`** (`event_services_test.py`, `reader_test.py`). I left them because the feedback did not ask to change them.

### Before and after

Gap checks, run from the repo root. Before is `develop`, after is this branch:

| Check                                                                            | Before                                      | After                                                                                                         |
| -------------------------------------------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `grep -n "^class .*Event" core/domain/stats_domain.py`                           | no output                                   | `208:class StartExplorationEventLogEntryDict(TypedDict):` and `2408:class StartExplorationEventLogEntry:`     |
| `grep -n "validate" core/domain/event_services.py`                               | no output                                   | `271:        start_event_log_entry.validate()` (plus one comment line)                                        |
| `git diff upstream/develop HEAD --stat -- core/storage/statistics/gae_models.py` | n/a                                         | no output, so `create()` is unchanged                                                                         |
| Non-test uses of `StartExplorationEventLogEntryModel` outside `core/storage/`    | `event_services.py:240` (the `create` call) | `event_services.py:272` (the `create` call) and `event_services.py:466` (the type of the conversion function) |

Tests, using the same command before and after (`test_before.txt` and `test_after.txt`):

| Module                                    | Before     | After      |
| ----------------------------------------- | ---------- | ---------- |
| `core.domain.event_services_test`         | 20 passed  | 22 passed  |
| `core.storage.statistics.gae_models_test` | 86 passed  | 86 passed  |
| `core.controllers.reader_test`            | 112 passed | 112 passed |
| Total                                     | 218 passed | 220 passed |

The new `StartExplorationEventLogEntry` tests are in `core.domain.stats_domain_test`, which has 189 tests, and all of them pass.

### Checks passing

- Backend tests: all pass (see the proof section below).
- Coverage: `core/domain/stats_domain.py` and `core/domain/event_services.py` are both at 100% line and branch coverage.
- Mypy (`scripts.run_mypy_checks` on the changed files), Black, and Ruff import sorting pass.
- The Oppia linter reports no errors in the changed files. Its only messages were CODEOWNERS warnings about untracked local files that are not part of this PR.

### What AI helped with

I used Claude on this PR. I traced how start events are created and saved, wrote the proposal on the issue, and decided how to apply the maintainer's feedback. Claude checked my proposal against the code, wrote the implementation and tests from my approved plan, and ran the formatter, type checks, linter and tests. It also helped me check which other tests call the handler (`user_services_test` and `stats_services_test`, which I ran and which pass).

## Essential checklist

- [x] I have referenced the issue(s) that this PR fixes or fixes part of on line 1 above. Once I open the PR, I will check that any issues this PR fully fixes are listed in the "Development" section of the sidebar.

- [x] I have checked the "Files Changed" tab and confirmed that the changes are what I want to make.

- [x] I have written tests for my code.

- [x] The PR title starts with "Fix #bugnum: " or "Fix part of #bugnum: ...", followed by a short, clear summary of the changes.

- [x] I have assigned the correct reviewers to this PR (or will leave a comment with the phrase "@{{reviewer_username}} PTAL" if I can't assign them directly).

## Proof that changes are correct

This PR has no user-facing changes. I ran the backend tests, using the same command before and after the change:

```
python -m scripts.run_backend_tests --skip_install --test_targets=core.domain.event_services_test,core.storage.statistics.gae_models_test,core.controllers.reader_test
```

Output after the change (from `test_after.txt`):

```
SUCCESS   core.domain.event_services_test: 22 tests (7.9 secs)
SUCCESS   core.storage.statistics.gae_models_test: 86 tests (11.3 secs)
SUCCESS   core.controllers.reader_test: 112 tests (113.7 secs)

Ran 220 tests in 3 test classs.
All tests passed.
```

For the new domain tests and the coverage of the two changed source files:

```
python -m scripts.run_backend_tests --skip_install --ignore_coverage --generate_coverage_report --test_targets=core.domain.stats_domain_test,core.domain.event_services_test
coverage report -m --include=core/domain/stats_domain.py,core/domain/event_services.py
```

```
SUCCESS   core.domain.stats_domain_test: 189 tests (29.8 secs)
SUCCESS   core.domain.event_services_test: 22 tests (11.4 secs)

Ran 211 tests in 2 test classs.
All tests passed.

Name                            Stmts   Miss Branch BrPart  Cover   Missing
core/domain/event_services.py     136      0     22      0   100%
core/domain/stats_domain.py       686      0    226      0   100%
TOTAL                             822      0    248      0   100%
```

<!-- Attach a screenshot of the test_after.txt summary here before opening the PR. -->

## PR Pointers

- Never force push! If you do, your PR will be closed.
- To reply to reviewers, follow these instructions: https://github.com/oppia/oppia/wiki/Rules-for-making-PRs#step-5-address-review-comments-until-all-reviewers-approve
- Some acceptance tests are flaky, and can fail for reasons unrelated to your PR. We are working on fixing this, but in the meantime, if you need to restart the tests, please check the ["If your build fails" wiki page](https://github.com/oppia/oppia/wiki/If-CI-checks-fail-on-your-PR).
- See the [Code Owner's wiki page](https://github.com/oppia/oppia/wiki/Oppia's-code-owners-and-checks-to-be-carried-out-by-developers) for what code owners will expect.

**Maintainer Feedback:**

- Na

**Status:** Not submitted yet

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Learnings and Reflections

**Technical Skills Gained**

I didn't realize how hard it was going to be to trace the code, and keep track fo everything. I eventually started writing everything down manually so that I could actually visualize what was going on. And then even looking up how to interpret the file structure and how the modules were organized to better understand the roles and relationships between the files helped. Fore xampling, reveiwing what I learned about handlers vs service and domain modules helped me understand the relationships between all the objects and functions better, and where something would most likely be callsed.

**Challenges Overcome**

The hardest part was really trying to understand how the code worked. I will say that even though it was really annoying how specific it got, the repro-check forcing me to prove exaclty how the issue could be reproduced was helpful because I had to really think about how to show that since there's no test in the issue description that you can point to that's wrong. It made think about well okay which file would have this particular function, and how does this actually prove that the gap the issue is describing.

**What I'd Do Differently Next Time**

I would probably go for an issue that was a bit more contained or at least I would give myself a lot more for something like an enhancement. I really wanted to challenge myself, and I'm glad I did, but I think I still need to get a bit more comfortable with reading larger codebases, so working on issues that are bit more defined wcould be helfpu..

---

## Resources Used

[What actually helped, not a reading list. List things this story
already shows you using: the doc you followed to set the environment
up, the thread that explained the bug, the person who answered you.
One real entry beats ten plausible ones.]

- Oppia had extensive documentation (setup, how to write a PR). Like even understand what the objects were from the user perspective was very helpful:
  - [Contributor page with link to site and setup instructions](https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia#good-first-issues-for-new-contributors)
  - [How to write a PR](https://github.com/oppia/oppia/wiki/Rules-for-making-PRs#step-4-create-a-pull-request)
- Claude was very helpful in answering all my questions. I would consistently give it ideas, and it would challenge my thoughts.
- Since there are a lot of models to refactor, there were a lot of contributions and comments that helped me. I looked at PRs that were merged and ones that didn't. Here are some of the contriubtions that helepd me the most:
  - [Example comment](https://github.com/oppia/oppia/issues/21970#issuecomment-7050732096)
  - [Example PR](https://github.com/oppia/oppia/pull/28226)
