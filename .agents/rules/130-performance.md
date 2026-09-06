# Performance

Measure before optimizing unless a known bottleneck or obvious resource hazard exists. Review database queries, N+1 behavior, unbounded pagination, payload sizes, connection pools, CPU/memory-heavy work, and external call latency.

Set explicit limits for list endpoints and expensive inputs. Use caching only with a defined invalidation/consistency policy. Do not trade correctness or security for benchmark improvements.

Where concurrency matters, test contention, duplicate writes, race conditions, and timeout behavior rather than relying on single-user happy paths.