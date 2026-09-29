# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

## Your identity upstream

**GitHub username**
ninaony

---

## Posted upstream

**Claim comment**


Link: https://github.com/codepath/pathreview-ai301-fa26-s3/issues/59#issuecomment-5896828870

Hi! I'd like to take on this issue: Faithfulness checker scores claims unsupported when the context uses different words #59.

I’m writing a repro report with my environment, steps, and log, then I’ll attempt a fix. I’m a beginner contributor btw.



**Reproduction comment**

Link: https://github.com/codepath/pathreview-ai301-fa26-s3/issues/59#issuecomment-5899261476

Repro report:

Environment:
macOS 26.6.2
Python 3.13.0
pytest 9.1.1

Steps from a fresh clone:

1. Clone repo
2. Followed docs/SETUP.md steps exactly
3. Reproduced issues:

- Failed test

Ran `pytest tests/unit/test_faithfulness_checker.py::TestFaithfulnessChecker::test_multiple_context_chunks --runxfail`

Output was as expected ([log](references/reproduction_evidence.txt) attached with details): assert 0.0 > 0.5

- Direct calls to is_supported()


Ran `python3 -c "from rag.evaluator.faithfulness_checker import FaithfulnessChecker; print(FaithfulnessChecker._is_supported('Knows Python', 'The candidate knows Python'))"`

Output was as expected ([screenshot](references/repro_evidence_2.png) attached with response): True (1.0)

Ran `python3 -c "from rag.evaluator.faithfulness_checker import FaithfulnessChecker; print(FaithfulnessChecker._is_supported('Knows Python', 'python expert'))"`

Output was as expected ([screenshot](references/repro_evidence_2.png) attached with response): False (0.0)

## Eval iterations

**Run history**

1. agreement: 15/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in disclosure)
2. agreement: 20/20 scored items  (bar: 18/20: PASS)


**Package analysis**

`pkg-3`

Current - 
Gold: accept  
My rubric: accept   
Match/reasoning: n/a 


My rubric is reading it as an accept because while an AI contribution policy exists and there is no acknowledgement of this in the claim comment/repro check, it doesn't matter. The specific policy is that it needs to be human readable, which it is.

**Check rationale**


| comment body |  if the repo or comments state a policy that specifically demands an explicit statement acknowledging AI use (naming the tool/extent), and the contributor doesn't include one, fail. If no explicit-acknowledgement requirement exists, the check passes. | required |

This check took me a couple tries to get because there are two levels to the disclosures. Previously, I was understanding as any mention of an AI policy warrants acknowledgement. What I needed to get clearer on, which `pkg-03` helped with was the fact on that a policy could exist but not necessarily necessitate an acknowledgement. Thus, there are some conditions where not acknowledging AI even though there is a policy, can still pass.


**Trade-offs**

The check gives up catching a human sounding AI comment. When a repo's policy asks for an explicit "I used AI" statement, the check just looks for that sentence as it's easy to verify, which is why pkg-20 grades reliably. When a policy just asks to "sound human," the check has to guess based on how the writing reads. I tried fixing that by telling the grader to assume every comment is AI-assisted no matter what, but that broke `pkg-03` because it wanted an explicit disclosure statement from a policy that never asked for one. So I left the softer check as is. Since I have the no AI isms check though, hopefully that'll be caught there.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
