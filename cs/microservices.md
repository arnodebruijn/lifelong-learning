Microservices
=============


Checklist
---------
You need to be this tall to use [micro] services: (Martin Fowler)

- Basic Monitoring, instrumentation, health checks
- Distributed logging, tracing
- Ready to isolate not just code, but whole build+test+package+promote for every service
- Can define upstream/downstream/compile-time/runtime dependencies clearly for each service
- Know how to build, expose and maintain good APIs and contracts
- Ready to honor b/w and f/w compatibility, even if you're the same person consuming this service on the other side
- Good unit testing skills and readiness to do more (as you add more microservices it gets harder to bring everything up, hence more unit/contract/api test driven and lesser e2e driven)
- Aware of [micro] service vs modules vs libraries, distributed monolith, coordinated releases, database-driven integration, etc
- Know infrastructure automation (you'll need more of it)
- Have working CI/CD infrastructure
- Have or ready to invest in development tooling, shared libraries, internal artifact registries, etc
- Have engineering methodologies and process-tools to split down features and develop/track/release them across multiple services (xp, pivotal, scrum, etc)
