# Stripped punctuation from claim and context tokens to fix faithfulness checker matching failures

## Summary

<!-- One paragraph describing what this PR does and why -->

Fixes the faithfulness checker issue associated with the `test_multiple_context_chunks` test such that punctuation incorrectly included to the same word ('python,' or 'python-' vs 'python') no longer occurs. Thus, preventing and incorrect failures on the matching logic used to ensure claims are properly supported by retrieved context in `_is_supported()` (`rag/evaluator/faithfulness_checker.py`).

The test now passes.

## Issue

Part of #59

## Changes

<!-- Bullet list of the specific changes made -->

Commit af54d1f:

- added additional stripping of punctuation in `rag/evaluator/faithfulness_checker.py`
- added type in `tests/unit/test_faithfulness_checker.py`

## Testing

<!-- How did you verify your changes? -->

- [ ] **CI is green on this PR (all five jobs)** — required for review
- [x] Unit tests pass (`make test-unit`)
- [x] Integration tests pass (`make test-integration`)
- [x] Linter passes (`make lint`)
- [x] Type checker passes (`make typecheck`)
- [x] New/updated tests cover the changes
- [x] If this fixes a seeded bug: removed its `@pytest.mark.xfail` marker (and any
      matching suppression in `pyproject.toml`)

**Test results output**:
[Test before](test_before.md)
[Test after](test_after.md)
[Test evidence](test_evidence.md)

## Screenshots / Demo

<!-- If applicable, add screenshots or a link to a demo video -->

N/A; evidence proving fix is provided in the test files above

## Notes for Reviewers

<!-- Anything the reviewer should pay particular attention to -->

- This PR only addresses the one failed test mentioned in the issue; the other xfail marked tests associated with this issue (#59) are still present as their changes were out of scope
- The original issue documents two seemingly related tests (the failed test mentioned above and 2 example failures (direct calls to `_is_supported()`)). I created a seperate branch (fix/59-faithfulness-checker-claims-unsupported-on-different-words-similar-meaning) for those changes as they were independent fixes.
- Changes made for `tests/unit/test_faithfulness_checker.py` were for two unrelated tests that were failing the linter. This did not have an effect on the behavior of anything else as shown via all other unit test tests still passing.
- I used AI to build the change, but the core idea was mine. An explicit plan was made to assist the build, and I reviewed the changes after.
