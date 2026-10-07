# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

ninaony

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/59#issuecomment-6024361354

Here's my plan:

Diagnosis:

Failing test issue: Commas included in claim words. Thus, ‘python,’ and ‘python’ resulted in a mismatch even though they contain the same word
Direct call failures: \_is_supported() only registers a match between the same two words, so words that mean or imply similar things (‘know’ and ‘expert’), don’t get counted as supported
Change:

Failing test issue: Strip punctuation from claim and context words (not '#', '+', '-')
Short claim failures: Cosine similarity on claims that don’t currently pass \_is_supported() overlap threshold (match < 2 words)
Short claims contains <= 4 words
Use already established embedding provider (ingestion/embeddings/provider.py) to embed claim and context
Perform cosine similarity
Threshold is True for similarity > 0.5; if provider errors out, default to word-overlap result
Add fake provider in unit tests
Scope:
In:

\_is_supported()’ , additional helper function (\_semantic_score()) in rag/evaluator/faithulness_checker.py
Writing additional tests in tests/unit/test_faithfulness_checker.py
Out:

Edge mismatch cases in claims of longer tests
Any other issues related to the faithfulness checker indicated by the other failed tests in tests/unit/test_faithfulness_checker
Integration tests to properly test helper function (provider correctness, threshold accuracy, etc.)
Test plan:

Add additional unit tests for short claim failures
a. High similarity -> True
b. Low similarity -> False
c. Skips semantic fallback for claims length > 4
d. Skips fallback when overlap already >= 2
e. 0.5 similarity -> False
f. 0.51 similarity -> True
Re-run the test (same command in repro-check)
Previously: Evaluated to 0.0
Expected: 1.0
Run test_faithfulness_checker.py: tests/unit/test_faithfulness_checker.py -q
Previously: 18 passed, 4 xfailed
Expected: 25 passed, 3xfailed
Re-run the direct calls (same command in repro-check)
Expected: First call unchanged, second call now outputs True (with OpenAI provider selected and API key)
Re-run test suite to ensure changes didn’t impact anything else:
Entire suite:
Previously: 375 passed, 53 xfailed, 1 warning in 23.87s
Expected: 382 passed, 52 xfailed, 1 warning in 23.87s
Risks and unknowns:

The existing mock provider returns random vectors, so it can't show semantic similarity
Integration test being out of scope means real provider correctness isn’t verified except manually via running the issue's direct calls
0.5 is an unvalidated threshold
The context is one concatenated string, so longer the lengths may dilute cosine score
Additional costs associated with making embedding calls
There are plenty of punctuation cases that may be useful to include and not strip, but I only targeted the most frequent cases (example use cases: well-known, C#, C++)

---

## Your branch

**Branch**

fix/59-faithfulness-checker-punctuation-induced-mismatch

fix/59-faithfulness-checker-claims-unsupported-on-different-words-similar-meaning

**Evidence**

BEFORE ->
Command 1: `pytest tests/unit/test_faithfulness_checker.py::TestFaithfulnessChecker::test_multiple_context_chunks --runxfail`

Output 1:

```
=================================== FAILURES ===================================
**\*\***\_**\*\*** TestFaithfulnessChecker.test_multiple_context_chunks **\*\***\_**\*\***

self = <tests.unit.test_faithfulness_checker.TestFaithfulnessChecker object at 0x109bf4050>
checker = <rag.evaluator.faithfulness_checker.FaithfulnessChecker object at 0x1098c6f90>

    @pytest.mark.xfail(
        strict=True,
        reason="issue #59: faithfulness checker can never mark short claims as supported",
    )
    def test_multiple_context_chunks(self, checker):
        """Test multiple context chunks contribute to score."""
        feedback = "The developer has Python, JavaScript, and Docker experience."
        context_chunks = [
            {"text": "Python expertise shown in backend projects."},
            {"text": "JavaScript skills demonstrated in frontend development."},
            {"text": "Docker and containerization knowledge evident in CI/CD pipelines."},
        ]

        score = checker.check(feedback, context_chunks)

        assert isinstance(score, float)
        assert 0.0 <= score <= 1.0
        # All three claims supported

>       assert score > 0.5
>
> E assert 0.0 > 0.5

tests/unit/test_faithfulness_checker.py:106: AssertionError
----------------------------- Captured stdout call -----------------------------
2026-09-29 13:53:18 [info ] faithfulness_checked claims_count=1 score=0.0 supported_count=0
=========================== short test summary info ============================
FAILED tests/unit/test_faithfulness_checker.py::TestFaithfulnessChecker::test_multiple_context_chunks
============================== 1 failed in 0.20s ===============================
```

Command 2: `python3 -c "from rag.evaluator.faithfulness_checker import FaithfulnessCh
ecker; prınt(FaithtulnessChecker.\_is_supported('Knows Python', 'The candidate knows Python'))"`

Output 2: True

Command 3: `python3 -c "from rag.evaluator faithfulness_checker import FaithfulnessCh
ecker; print(FaithfulnessChecker.\_is_supported('Knows Python', 'python expert'))"`

Output 3: False

AFTER ->
Output 1:

```
tests/unit/test_faithfulness_checker.py . [100%]

=============================================== 1 passed in 0.17s ================================================
```

Output 2: True

Output 3: False

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

1. agreement: 19/20 scored items (bar: 18/20: PASS)
2. agreement: 20/20 scored items (bar: 18/20: PASS)

**Package analysis**
`pkg-20` first failed, but now doesn't because I included the AI disclosures. When I didn't, it lacked the ability to check whether or not a plan comment was adhering to the repo's expectations. Now the gold label and my rubric both reject it because the repo requires disclosures, adn there's no AI disclosure present even though all packages are treated as AI assited.

**Check rationale**

| Check                  | Evidence                                | Pass condition                                                                                                                                                                                                                                            | Weight   |
| ---------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| Adheres to disclosures | issue contribution policy, comment body | if the repo or comments state a policy that specifically demands an explicit statement acknowledging AI use (naming the tool/extent), and the contributor doesn't include one, fail. If no explicit-acknowledgement requirement exists, the check passes. | required |

**Trade-offs**

"Between run 1 and run 2, only `pkg-20` changed from fail to pass after only this was added. The other 19 items scored identically, so the disclosure check didn't alter any other package's result. I also know know because I first tested this on a partial run where I ran it on the 7 other packages (`pkg-03`, `pkg-05`, `pkg-07`, `pkg-09`, `pkg-12`, `pkg-17`, and `pkg-20`) that mentioned an AI policy or generated work as the (rest stated "No AI policy") and they all passed.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
