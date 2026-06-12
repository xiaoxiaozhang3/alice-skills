# Engineering Lifecycle

Use the lightest workflow that still protects correctness.

## Default Flow

```text
clarify -> spec -> plan -> execute -> verify -> review -> release -> document
```

## Task Size Routing

| Situation | Route |
|---|---|
| Typo, formatting, tiny config | Direct edit + minimal verification |
| Clear one-file bug | Inspect -> fix -> verify -> record progress |
| Multi-file change | Requirements -> design -> plan -> tasks |
| Complex or risky behavior | Full change flow with review and verification gates |
| Interrupted work | `resume-change` before doing anything else |

## Schema-First API Rule

If a change touches frontend-backend data exchange, the plan must define schema and API contract before logic:

1. Data schema or domain model
2. Request, response, error, pagination, nullable, and enum shapes
3. Shared or aligned frontend/backend types
4. Backend handler/service logic
5. Frontend client and UI integration
6. Contract fixture or test proving alignment

Do not let frontend logic depend on undocumented mock-only fields.
