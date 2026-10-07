My plan.

Diagnosis:

1. Failing test issue: Commas included in claim words. Thus, ‘python,’ and ‘python’ resulted in a mismatch even though they contain the same word
2. Direct call failures: `_is_supported()` only registers a match between the same two words, so words that mean or imply similar things (‘know’ and ‘expert’), don’t get counted as supported

Change:

1. Failing test issue: Strip punctuation from claim and context words (not #,+,-)
2. Short claim failures: Cosine similarity on claims that don’t currently pass `_is_supported()` overlap threshold (match < 2 words)
   1. Short claims contains <= 4 words
   2. Use already established embedding provider (`ingestion/embeddings/provider.py`) to embed claim and context
   3. Perform cosine similarity
   4. Threshold is True for similarity > 0.5; if provider errors out, default to word-overlap result
   5. Add fake provider in unit tests

Scope:
In:

- \_is_supported()’ , additional helper function (`_semantic_score()`) in `rag/evaluator/faithulness_checker.py`
- Writing additional tests in `tests/unit/test_faithfulness_checker.py`
  Out:
- Edge mismatch cases in longer claims
- Any other issues related to the faithfulness checker indicated by the other failed tests in `tests/unit/test_faithfulness_checker`
- Integration tests to properly test helper function (provider correctness, threshold accuracy, etc.)

Test plan:

1. Add additional unit tests for short claim failures
   1. High similarity -> True
   2. Low similarity -> False
   3. Skips semantic fallback for claims length > 4
   4. Skips fallback when overlap already >= 2
   5. 0.5 similarity -> False
   6. 0.51 similarity -> True
2. Re-run the test (same command in repro-check)
   - Previously: Evaluated to 0.0
   - Expected: 1.0
3. Run `test_faithfulness_checker.py`: tests/unit/test_faithfulness_checker.py -q
   - Previously: 18 passed, 4 xfailed
   - Expected: 25 passed, 3xfailed
4. Re-run the direct calls (same command in repro-check)
   - Expected: First call unchanged, second call calls now output True with OpenAI provider selected and Open AI key
5. Re-run test suite to ensure changes didn’t impact anything else:
   - Entire suite:
     - Previously: 375 passed, 53 xfailed, 1 warning in 23.87s
     - Expected: 382 passed, 52 xfailed, 1 warning in 23.87s

Risks and unknowns:

- The existing mock provider returns random vectors, so it can't show semantic similarity
  - Integration test being out of scope means real provider correctness isn’t verified except manually via running the issue's direct calls
  - 0.5 is an unvalidated threshold
  - The context is one concatenated string, so a long context may dilute the cosine score.
- Additional costs associated with making embedding calls
- There are plenty of punctuation cases that may be useful to include and not strip, but I only targeted the most frequent cases (examples: well-known, C#, C++)

## Deviations

General

- Split the work across two branches because the two changes, although both in \_is_supported(), are independent.
- Test related (on both branches): Added a type annotation (context_chunks: list[dict] = []) to two existing tests in `test_empty_context_chunks_returns_zero` and `test_both_empty_returns_zero` in `test_faithfulness_checker.py` because pre-commit mypy hook rejected the untyped empty lists and blocked the commit (type-label change, so no effect on behavior)

Semantic similarity fix:

- Didn’t use pre-existing mock provider. Created fake providers so I could control the output
- Test related: Added provider-error test -> expected counts become 26 passed, 3 xfailed and 383 for the suite (after both branches merge)

Punctuation fix:

- Plan exempted #, + and -; implementation exempts only # and +. `strip()` only touches word edges, so something like “well-known” is still unaffected. However, in general cases like that (e.g. CI/CD) aren’t handled and should be thought through further.
- Test related: Removed xfail marker from test so pytest doesn’t report it as a failure
