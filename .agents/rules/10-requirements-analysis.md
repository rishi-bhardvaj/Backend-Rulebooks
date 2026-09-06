# Requirements Analysis

Before coding, map: actors; trusted/untrusted inputs; permissions; entities and relationships; endpoints/events/jobs; request/response contracts; validation; business rules; persistence; external systems; failure modes; security boundaries; tests; observability; deployment.

For ambiguous requirements, ask a question when the ambiguity can change security, data integrity, public API behavior, or irreversible operations. Otherwise record an explicit assumption in the plan. Do not silently invent critical behavior.

Convert each acceptance criterion into a verification method. Include at least one negative case for every security-sensitive or state-changing behavior.