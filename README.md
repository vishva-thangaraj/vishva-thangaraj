# Vishva T

**Backend engineer at Zoho, building distributed systems in Java.**

I work on retail POS backends — the services behind registers, payments and loyalty — where being
correct under load matters more than being clever. Most of what I enjoy is the unglamorous half:
event-driven decoupling, cache behaviour, failure paths, and deployments you can roll back.

📍 Madurai, Tamil Nadu, India

---

## What I'm working on

**Loyalty Management · Zoho Retail POS**

Owned the module end to end while migrating it out of a monolith into a standalone, event-driven
microservice — requirements and low-level design through implementation, testing and deployment.

- REST services for Register, Cash Management, Session, Payment and Tender, on a platform processing
  **2.3M+ invoices a month**, peaking near **950 calls/min (~15.8 RPS)** at P50/P95/P99 of
  **1.90s / 4.45s / 7.27s**.
- A configuration cache that served **17.2M+ reads** against roughly **11K** daily database
  fallbacks — a **~99.94% hit rate**, and a lot of load the database never saw.
- Wired loyalty in as a **Kafka consumer** of the Zoho Finance event stream, so it reacts to store
  transactions without coupling to the service that produces them.

Alongside that: production support and incident response — log analysis, root-cause investigation
and fixes for critical backend defects — plus code and design reviews, and translating product
requirements into backend designs with architects.

Before this I was a Technical Trainee at Zoho, building REST APIs and backend components for core
retail workflows in a large Java/J2EE monolith.

---

## Featured project

### Feature Flag Platform · Java 17, Spring Boot 3.5
*Backend + SDK — [gitlab.com/featureflag](https://gitlab.com/featureflag)*

A multi-tenant feature-flag service: per-environment targeting rules — membership, numeric ranges,
semantic-version comparison — plus per-user overrides and percentage rollouts, so teams change
behaviour at runtime instead of redeploying.

A few decisions that shaped it:

- **Authorization is fail-closed.** A declarative JSON policy drives role enforcement on every
  endpoint, and an invalid policy stops the application at startup. It used to pass as a warning,
  which silently disabled role checks platform-wide.
- **SDK keys are scoped to one environment**, and the tenant and environment come from the key
  rather than from the request — so a production key shipped inside a customer's binary cannot read
  staging's unreleased flags.
- **Config is served over conditional GET**, so a polling SDK transfers nothing while flags are
  unchanged.
- **Deploys go from GitLab CI to AWS EC2 over SSM, not SSH** — port 22 stays closed and no deploy
  key lives in CI — with secrets pulled from Parameter Store and rollback by redeploying an earlier
  image tag.

---

## Tech

| | |
|---|---|
| **Languages** | Java 17, SQL, Bash |
| **Backend** | Spring Boot, Spring Security, JPA/Hibernate, REST, microservices |
| **Distributed systems** | Kafka, Avro, Schema Registry, Redis, event-driven architecture |
| **Cloud & DevOps** | AWS (EC2, RDS, Systems Manager, IAM), Docker, nginx, TLS, GitLab CI/CD, Git |
| **Testing** | JUnit 5, Mockito, Testcontainers |
| **Fundamentals** | OOP, design patterns, concurrency, data structures & algorithms, system design |

---

## Elsewhere

[LinkedIn](https://linkedin.com/in/vishvat1403) · [GitLab](https://gitlab.com/VISHVA1403) ·
[vishva28sep@gmail.com](mailto:vishva28sep@gmail.com)

*B.E. Electronics & Communication Engineering — Karpagam Institute of Technology, Coimbatore
(2021–2025)*
