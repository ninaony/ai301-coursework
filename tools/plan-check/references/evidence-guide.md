# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

<!-- Where the plan states its cause, and where the repro evidence pins down the behavior that cause must explain. What it means for a diagnosis to follow from the evidence rather than contradict or ignore it. -->

**Where it lives:**

In the eval bundle - "Candidate plan" block against "Repro evidence" block

On Github.com - the plan comment in the Issue thread against repro check comment in the Issue thread and any attachments and files attached to repro check

**What good looks like:** The plan comment mentions what causes the bug and the stated cause is consistent with what's mentioned in repro evidence, meaning it would produce every step in the repro and doesn't depend on behavior the repro doesn't show. Any departure from the repro behavior is explained.

## Scope

<!-- Where the plan bounds itself: the in-scope statement, the
not-in-scope line, the files or areas named. What one bounded change
looks like next to a drive-by rewrite. -->

**Where it lives:**

In the eval bundle - "Candidate plan" block

On Github.com - the plan comment in the Issue thread

**What good looks like:** The change describes the smallest fix to accurately address the issue cause. The section mentions files it will change with reasoning aligning to the cause statement. The section also mentions it won’t change as well.

## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->

**Where it lives:**

In the eval bundle - "Candidate plan" block

On Github.com - the plan comment in the Issue thread

**What good looks like:** the plan names the location (e.g file, function) and the concrete action, so a stranger could open the code and start without asking the author. Ordering is only needed when the change has dependent steps.

## Test plan

<!-- Where the plan says how success will be observed, and how that
maps onto the repro evidence's steps and artifacts. What a decisive
test plan names that a vague one does not. -->

**Where it lives:**

In the eval bundle - "Candidate plan" block, "Repro evidence" block

On Github.com - the repro check and plan comment in the Issue thread

**What good looks like:**
The test actually addresses the stated root cause and can name the repro step where the result must change; fail if it only verifies a symptom or a mechanism that's not in the diagnosis

## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->

**Where it lives:**

In the eval bundle - "Candidate plan" block against "Repro evidence block"

On Github.com - the plan comment in the Issue thread against repro check comment

**What good looks like:**
Claims about what was observed (e.g. "reproduced") point to steps or artifacts in the repro evidence. Claims that go beyond the repro, like which code is at fault, are worded as hypotheses or have a stated way to confirm them, not asserted as fact.

## Comms

<!-- Where the words meet the thread and the repo: the plan comment
read against the issue's maintainer signals (thread highlights, or
the live thread) and against the repo-facts block's stated templates,
contributing asks, and contribution policy (including AI-use
disclosure requirements). What thread-aware looks like next to
boilerplate. -->

**Where it lives:**

In the eval bundle - "Candidate plan comment" against Thread highlights, "Repo facts"

On Github.com - the plan comment against the issue, comments against the repo's stated templates and contribution policy (including AI-use disclosure requirements)

**What good looks like:**
The plan comment responds to what the thread and repo ask for (e.g. acknowledges the contribution policy, follows the template, discloses AI use if required) and doesn't contradict a maintainer signal. With no thread comments, the check rests on the repo-facts block.
