# Operating Contract

**CRITICAL:** `CODE EXISTS != FEATURE WORKS`. `COMPILES != WORKING`. `UI WORKING != BACKEND WORKING`. `ENDPOINT EXISTS != API WORKING`.

For every claimed behavior, identify the executable boundary and produce evidence. Prefer real runtime verification over static inspection. Work incrementally; preserve existing architecture unless change is required. Keep a decision/assumption record when requirements are ambiguous.

Never fabricate evidence. If commands cannot be run because of missing infrastructure, credentials, unavailable services, or tooling, state exactly what was not verified.

Completion requires the applicable gates: implementation → build → runtime → integration → tests → security → production readiness.