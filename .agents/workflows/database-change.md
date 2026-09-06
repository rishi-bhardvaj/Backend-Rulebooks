# Workflow: Database Change

1. Inspect current schema, migrations, constraints, indexes, application models, and deployment migration process.
2. Design the smallest safe schema change with integrity/concurrency implications.
3. Create an executable migration and update application persistence.
4. Run the migration against a real test database.
5. Verify reads/writes, constraints, rollback/failure behavior, and representative API flows.
6. Check query plans/performance when the change affects hot paths.
7. Run regression tests and report actual migration/runtime evidence.