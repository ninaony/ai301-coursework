# Unit 4 — Test and Submit

Path: `beat-1-sandbox/unit-4/pull-request.md`

---

## Your pull request

**Pull request**

https://github.com/codepath/pathreview-ai301-fa26-s3/pull/177

**Branch**

fix/59-faithfulness-checker-punctuation-induced-failure

## Eval iterations

**Run history**

1. agreement: 19/20 scored items (bar: 18/20: PASS)
2. agreement: 20/20 scored items (bar: 18/20: PASS)

**Package analysis**

`pkg-04`

My rubric correclty decides reject because while it mentions the original test passing and showing the original behavior, it doesn't actually show that visual evidence.

**Check rationale**
| Check | Evidence | Pass condition | Weight |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| poor test quality | test plan and PR description against test evidence in attachments, screenshots, test evidence section ag | if there is no clear evidence proving the fix is addressed the issue, then fail. Merely stating that the tests passes does not count. The direct output of the the test must show the expected behavior. | required |

This check specifically looks for evidence in some kind of visual output to ensure that that the claims made are actually proven. The second part is added becasue of packages like `pkg-04` where the PR it mentions tests passing, but there is no visual evidence shown for it.

**Trade-offs**

When I was fixing my rubric to adjust for the one package I got wrong, I first checked against the other tests that look for the "not-tested" category to ensure that my corrections weren't throwing the other tests off. Thus, nothing changed when that adjustment was made and it serves true for the rest of the packages in the harness as all of them are correctly graded.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/pr-precheck/`.
