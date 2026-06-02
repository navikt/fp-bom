# fp-bom

Bill of Materials and parent POMs for all Team Foreldrepenger Java applications and libraries.

## Shared context

- Source of truth for shared domain, architecture, and conventions: `navikt/fp-context`
- Copilot Space: `navikt/TeamForeldrepenger`

## Structure

| Module          | Role                                                                     |
|-----------------|--------------------------------------------------------------------------|
| root            | Test deps and common build steps                                         |
| `fp-bom`        | The Bill of Materials (dependency versions only)                         |
| `fp-parent-app` | Parent POM for deployable applications (build, plugin config, packaging) |
| `fp-parent-lib` | Parent POM for libraries (build, plugin config, release)                 |

## Conventions

- All version pins live here. Downstream repos must not override versions
- Downstream repos use `fp-parent-app` or `fp-parent-lib` as parent POM, which imports `fp-bom` for dependency versions.
- Dependabot drives upgrades in this repo first; consumers pick them up on next bump.
- Jakarta EE 11 baseline: Jetty, Jersey (server only), Weld CDI, Hibernate
- Other: Jackson 2 (moving to Jackson 3), Kafka 4, flyway, Hikari, Database drivers
- Logging and Observability: SLF4J + logback and bridges, Prometheus + Micrometer, OpenTelemetry
- Test: JUnit 6, AssertJ, Mockito, Testcontainers
- Build: dependencies and common build-steps used downstream (e.g. release plugin)
- Java 25+.

Not in `fp-bom`:
- No libraries from the fp ecosystem like `fp-felles`. Downstream repos import these directly.
- No Spring Boot or dependents like token-support

## When changing

- Major version bumps: check breaking-change notes for downstream impact
  (especially Jetty, Jersey, Weld, Hibernate, Jackson)
- May verify signigicant version bumps by first building a local version of `fp-bom`, then use snapshot versions in to build `fp-felles` and then `fp-sak`, and then the `navikt/fp-autotest` suite `verdikjede` locally.
- New dependencies: add only if used by ≥2 consumers; otherwise keep local.
- Build/plugin changes in parent POMs affect all downstream — coordinate.
