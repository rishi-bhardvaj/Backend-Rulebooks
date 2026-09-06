# Testing

Choose the lowest test level that proves the claim, but use integration/API/E2E tests when the claim concerns wiring or real infrastructure.

For important features cover: happy path + validation failure + authentication failure + authorization failure + not found + conflict + relevant edge cases. Add regression tests for discovered bugs. Add concurrency/failure tests where race conditions or partial failures are plausible.

Do not claim real integration from tests that mock the integration boundary. Test doubles are permitted only when intentional, isolated, and clearly identified as unit-test infrastructure.