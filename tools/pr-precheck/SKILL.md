---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

<!--
THIS IS THE PART YOU WRITE, and it is the last one: the frame itself.
Weeks 1 through 3 handed you a working SKILL.md and you filled the
files behind it; this week the frame ships as headings, and you write
what it says. The frontmatter above and the section headings below are
fixed (CONTRACT.md's layout rule); the instructions under each heading
are yours. Write instructions to the tool, in the imperative, the way
weeks 1-3's frames spoke to you: what to read, in what order, what to
refuse, what to emit. Your executor in the rotation is the test: a
frame gap they hit (cannot tell what the tool reads, or how a verdict
gets assembled) is a missing sentence here.

One section is not yours: the JSON schema in "Verdict and output" is
reproduced from CONTRACT.md verbatim and may not be altered. Your
words decide everything around it.
-->

## The question

<!-- State, in your words, the one question this tool answers and what
a PR package is: what artifacts it contains and what they are read
against. CONTRACT.md fixes the question; your frame has to say it so
the tool cannot wander into grading something else. -->

A pr-precheck tool answers exactly one question about exactly one PR
package: **is this ready to submit?** A PR package is a candidate pull
request (title, description, commits, diff, test evidence), read
against the plan it claims to implement and the issue that plan
belongs to. The tool never answers a different question, never grades
more than one package per run, and never answers from gut feel: it
executes the components in this directory.

## Inputs and modes

<!-- Define both modes. Live mode: name every input (your plan.md with
its deviation notes, your branch's diff, your draft PR title and
description, your test evidence, your issue), where each comes from,
and what a house-chain student reads instead. The branch's diff is
everything the branch changes relative to the repo's default branch:
`git diff main...HEAD` (three dots), run from the working copy, is
the command that produces it; name the source that concretely. Eval
mode: state that the bundle is the whole world, nothing is fetched,
and every check runs with the full verdict rule. -->

The tool runs in exactly two modes:

- **Live mode**: the student's own submission, checked before it goes
  out. Inputs: their `plan.md` (deviation/change notes included), the diff on
  their branch, their draft PR title and description, and their test
  evidence, read against their issue. A house-chain student reads the
  house plan and the house repro pack instead; the same checks grade
  the same things there. Live mode gathers issue-side evidence from
  the real repo (the thread, the PR template, the stated policy).
- **Eval mode**: a package bundle is the whole world. Every fact comes
  from the bundle text; nothing is fetched, nothing else is read. Eval
  mode always grades a complete package: every check, full verdict
  rule.

## The scope seam (live mode only)

<!-- Tell the tool when to read scope.md, what to do with the rules it
finds there, what to refuse, and what to do when the scope's repo line
is an unfilled placeholder. State that eval mode ignores scope.md
entirely. CONTRACT.md names the required behavior; your frame has to
instruct it. -->

In live mode, the tool reads `scope.md` before anything else. The
scope names where the student's PR must live and the house rules of
that environment; the tool refuses to grade work outside the scoped
repo, and if the scope's repo line still carries an unfilled
placeholder it stops without grading and tells the student to fill
the `Repo:` line in `scope.md` with their section's Path Review repo.
It never guesses a scope. In eval mode, `scope.md` is ignored
entirely. This seam is why the same tool graduates: staff swap one
file and the field of view changes.

## The voice seam (live mode only)

<!-- Tell the tool when to read voice-guide.md, which outgoing text it
gates (the PR title and description), how to report a broken rule, and
why it never changes the verdict on its own. State that eval mode
ignores it entirely. -->

In live mode, the tool also reads `voice-guide.md` (the student's own
rules for how they write upstream and
holds the outgoing PR text, the title and the description, against
those rules, reporting any rule the draft breaks in the summary. The
voice guide never changes the verdict on its own unless the rubric has
a check that reads it. In eval mode, `voice-guide.md` is ignored
entirely: voice is personal and carries no gold labels; universal
communication-quality checks live in the rubric.

## Component reads

<!-- Tell the tool how the pieces connect: rubric.md defines the
checks and the verdict rule, references/evidence-guide.md maps where
each evidence family lives, procedure.md is executed as written. Say
what the tool does when the procedure is silent on a step (report the
gap, never improvise around it) and what it does when rubric.md or
procedure.md has no content (the refusal rule, stated as an
instruction). -->

The rubric is the brain. Read rubric.md. It defines:

A table of checks. Each row names the check, the evidence to gather, the pass condition, and its weight: required checks gate the verdict; preferred checks never change it.
A verdict rule: how check results combine into a final verdict.
references/evidence-guide.md is the rubric's map: where each kind of evidence lives in a plan package (and, live, on GitHub), and what good looks like there.

The procedure is the hands.
Execute procedure.md.

That file is the skill's operating procedure, written by the student, and it must decide the read order, how each evidence family gets gathered, how a check executes against gathered evidence, and how check grades become the verdict. Follow it as written, the same way an executor follows a rubric: exactly, without improvising around gaps. Where the procedure is silent, note the gap in your summary rather than silently inventing a step; a procedure gap is feedback the student needs.

If rubric.md has no checks filled in, or procedure.md has no steps filled in, stop and say so: this skill cannot grade without a rubric AND a procedure, and that is by design. The rubric, the evidence guide, and the procedure are the parts the student writes; the voice guide carries over from week 2.

## Verdict and output

<!-- State the binary verdict space (accept means submit, reject means
hold) and instruct the tool to end its reply with the fenced JSON
block below, valid and last, with nothing after it. The schema is
CONTRACT.md's, verbatim; do not edit it. -->

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {
      "name": "<check name>",
      "grade": "pass|fail|unclear",
      "evidence": "<one line: the fact or quote that decided it>"
    }
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

<!-- Write the standing rules the tool grades under: evidence first,
grade the thing not the polish, the rubric decides, the procedure
decides how, and how unclear grades are treated when the rubric's
verdict rule is silent. CONTRACT.md states each as a guarantee; your
frame has to make them instructions. -->

These are not style advice; they are interface guarantees the master
tool honors and the bar assumes:

- **Evidence first.** No check is graded without naming the fact or
  quote that decided it. "Looks fine" is not evidence.
- **Grade the thing, not the polish.** A terse complete PR can be
  ready and a beautiful confident one can be hiding drift. Every check
  reads the artifact itself against the plan, the issue, and the
  stated standards, never the formatting.
- **The rubric decides, not the run.** If a check passes by its stated
  condition but feels wrong, it still passes; the fix belongs in the
  rubric, not in the run.
- **The procedure decides how, not the run.** The tool follows
  `procedure.md` as written and reports its gaps instead of silently
  inventing steps.
- **Unclear defaults to fail.** Treat `unclear` as the rubric's
  verdict rule directs; where the rule is silent, an unverifiable
  claim is a failing one. A PR you cannot verify from the package is a
  PR that is not ready to submit.
