# Bundled Role Experts

These role files provide optional expert perspectives. Select the smallest relevant role set for the task; one role is the default unless genuinely distinct perspectives are required.

| Role | Purpose | Use when |
|---|---|---|
| [Product manager](product/product-manager.md) | Frame product outcomes, requirements, priorities, roadmaps, and launch decisions. | The work needs product discovery, prioritization, a PRD, or lifecycle ownership. |
| [Software architect](engineering/engineering-software-architect.md) | Evaluate system structure, boundaries, domain models, and architectural trade-offs. | A change affects system-wide design or requires an architecture decision. |
| [Backend architect](engineering/engineering-backend-architect.md) | Design scalable backend services, APIs, data flows, and integration boundaries. | The task involves backend architecture, API contracts, or service boundaries. |
| [Frontend developer](engineering/engineering-frontend-developer.md) | Guide implementation of maintainable, accessible modern web interfaces. | The task requires frontend component, state, performance, or integration judgment. |
| [UI designer](design/design-ui-designer.md) | Shape visual systems, components, interaction states, and accessible interface presentation. | A user interface needs visual direction, a design system, or component-level design. |
| [Minimal-change engineer](engineering/engineering-minimal-change-engineer.md) | Find the smallest safe diff that satisfies a clearly bounded request. | A scoped fix should minimize blast radius and preserve surrounding behavior. |
| [Code reviewer](engineering/engineering-code-reviewer.md) | Review correctness, maintainability, risks, and actionable improvements. | An implementation needs an independent engineering-quality perspective. |
| [AppSec engineer](security/security-appsec-engineer.md) | Identify application threats and strengthen secure development controls. | A change crosses trust boundaries or affects sensitive data, authentication, or authorization. |
| [API tester](testing/testing-api-tester.md) | Design API validation for behavior, contracts, errors, security, and reliability. | An API or integration boundary needs a focused test strategy or review. |
| [Accessibility auditor](testing/testing-accessibility-auditor.md) | Audit interfaces for WCAG conformance and assistive-technology usability. | A UI needs accessibility review, keyboard testing, or screen-reader validation. |
| [DevOps automator](engineering/engineering-devops-automator.md) | Advise on repeatable infrastructure, CI/CD, deployment, and observability automation. | The work involves build pipelines, infrastructure automation, or release operations. |
| [UX researcher](design/design-ux-researcher.md) | Plan and synthesize research about user needs, behavior, and usability. | Product or design decisions need evidence from users or a research plan. |
| [Database optimizer](engineering/engineering-database-optimizer.md) | Improve schema design, queries, indexing, and database performance. | The task involves database structure, slow queries, or data-access efficiency. |
| [SRE](engineering/engineering-sre.md) | Advise on reliability targets, error budgets, incidents, and operational resilience. | A service needs SLOs, reliability analysis, incident readiness, or capacity judgment. |
| [Performance benchmarker](testing/testing-performance-benchmarker.md) | Define reproducible performance tests, baselines, and bottleneck analysis. | Latency, throughput, resource usage, or regression limits must be measured. |
| [Technical writer](engineering/engineering-technical-writer.md) | Produce clear developer documentation, references, tutorials, and API guidance. | Technical behavior must be explained for users, operators, or contributors. |

## Advisory Boundary

Role experts are advisory only. They may shape analysis, review, questions, risks, and recommendations, but they do not grant permission to run tools, create accounts, install dependencies, publish content, deploy changes, contact people, move money, scan external targets, or perform any other side effect. The main agent remains responsible for scope, execution, verification, and completion claims.

## Optional Catalog Expansion

This starter intentionally bundles only broadly useful roles. When the starter is being assembled from its source repository, consult the repository-root `agents/INDEX.md` catalog for optional specialists and copy only roles the project genuinely needs. The starter does not require that source catalog during normal operation.
