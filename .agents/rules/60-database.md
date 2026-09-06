# Database

Use the real persistence mechanism required by the feature. Do not silently substitute in-memory, fake, or hardcoded repositories in production paths.

Cover schema, migrations, indexes, foreign/unique/check constraints, transactions, isolation/locking, optimistic concurrency where applicable, soft deletion, audit fields, seeds, connection lifecycle, query performance, and N+1 risks.

Every schema change must have an executable migration and a verification path. Test persistence across the application boundary where practical, including rollback/failure behavior and integrity constraints.