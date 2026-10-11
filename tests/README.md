# Synthetic Test Plan

All fixtures must use fake identities and timestamps. Never check in customer messages or live execution results.

- Validate malformed RFC Message-ID is rejected.
- Verify a confirmed reply blocks an SMS; no reply found with incomplete thread verification remains UNKNOWN and blocks.
- Verify all-green synthetic proof inputs still cannot bypass the hard-off SMS gate.
- Verify a second inquiry with the same key does not stage twice; **this sequential test is not proof of atomic concurrent deduplication**.
- Verify failed API checks, absent consent, missing opt-out proof, invalid phone, overlapping estimate, and missing sender each fail closed.
- No SMS transmissions in any automated regression test.
