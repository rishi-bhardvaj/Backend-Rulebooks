# Integration Verification

When practical, start the actual application and exercise it through its real protocol boundary.

Minimum protected-API sequence: invalid credentials → expected 4xx; no credentials → expected 401/appropriate denial; malformed/invalid token → denial; expired token → denial; valid authorized token → expected 2xx; valid authenticated but unauthorized identity → expected 403 or policy-defined 404.

Trace representative flows end-to-end: client/action → network request → route → middleware → auth → service → database/external system → response → client state. Capture actual commands and observed results. If a dependency cannot run, mark the relevant gate NOT VERIFIED/BLOCKED.