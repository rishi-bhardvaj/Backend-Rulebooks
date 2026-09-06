# Mock and Bypass Detection

Before completion, search for `TODO`, `FIXME`, `mock`, `stub`, `fake`, `placeholder`, `hardcoded`, `temporary`, `skip auth`, `disable auth`, development bypasses, and hardcoded tokens/data.

Classify each hit. Intentional unit-test doubles are acceptable when isolated from production paths. Production repositories, services, authentication, authorization, or API responses must not be fake unless the requirement explicitly defines a simulation.

Trace suspicious code to determine whether the real application can execute it; do not delete legitimate tests merely because they contain mocks.