# fp-bom

Bill of Materials and parent POMs for all Team Foreldrepenger Java
applications and libraries.

## Context

- [fp-context](https://github.com/navikt/fp-context) — team domain,
  architecture, conventions. Source of truth.
- Consumer view of this repo: see
  [`architecture/team-libraries.md`](https://github.com/navikt/fp-context/blob/main/architecture/team-libraries.md).
- Copilot Space: navikt / **TeamForeldrepenger**.

## Structure

| Module | Role |
|--------|------|
| `fp-bom` | The Bill of Materials (dependency versions only) |
| `fp-parent-app` | Parent POM for deployable applications (build, plugin config, packaging) |
| `fp-parent-lib` | Parent POM for libraries (build, plugin config, release) |

## Conventions

- All version pins live here. Downstream repos must not override versions.
- Dependabot drives upgrades in this repo first; consumers pick them up on
  next bump.
- Jakarta EE 10 baseline (Jetty, Jersey, Weld, Hibernate, Jackson, IBM MQ).
- Java 25.

## When changing

- Major version bumps: check breaking-change notes for downstream impact
  (especially Jetty, Jersey, Weld, Hibernate, Jackson).
- New dependencies: add only if used by ≥2 consumers; otherwise keep local.
- Build/plugin changes in parent POMs affect all downstream — coordinate.
