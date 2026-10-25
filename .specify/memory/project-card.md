# egovframe-enterprise-business-template: project context

## Role, scope, and public entry points

`README.md` describes an internal-business reference template assembled from selected common
components: main page, business users, notices/boards, authorization, programs, menus, and codes.
`src/main/java/egovframework/com/` contains shared controllers/services, file management,
filters, and security-related integration. `DATABASE/` contains database setup assets.
Preserve MVC routes, forms, sessions, authorization boundaries, file behavior, service interfaces,
and schema/mapping semantics. README explicitly labels personnel rank, promotion, and attendance
screens as unimplemented sample pages; do not treat them as completed business workflows.

## Build and verification evidence

- `pom.xml` packages `egovframe-template-enterprise` as a WAR, inherits
  `org.egovframe.web:egovframe-web-config-parent:5.0.1`, and sets Java 17.
  It also specifies Servlet API 6.0.0, while README lists Servlet 5.0 / Jakarta EE 9.
  Check actual POM and deployment target compatibility rather than silently resolving the mismatch.
- `.github/workflows/maven.yml` targets `main` pushes/PRs, uses JDK 17, and runs
  `mvn -B package --file pom.xml`. No workflow targeting `work` was observed.
  The inherited build/test configuration and actual discovered tests determine coverage.
- README describes IDE server setup, schema and seed creation from `DATABASE/` for five listed
  database families, template configuration, and Run on Server. Runtime checks require a configured
  servlet container, datasource, and suitable local data; packaging does not establish business-flow
  correctness or deployed authorization behavior.
- Maven Central and eGovFrame dependency repository access is required. The repository contains
  HSQL-related resources as well, but their presence alone establishes no verified runtime setup.
  Use synthetic records and never put real account/configuration values in domain cards.

## Contribution and submission baseline

Actual parent: `eGovFramework/egovframe-enterprise-business-template`. No root AGENTS or
contribution guide was found in the file inventory; no undocumented upstream review policy is
assumed. Fetch the actual default ref and record the exact SHA. Preserve existing submission
branches/PRs. A missing `upstream-submit` starts directly at that upstream SHA, and later
application work uses a separate submission worktree. Adoption artifacts/commits stay on `work`;
this adoption does not implement sample screens, change dependencies, or create a PR.

## Exploration limits

No `.codegraph/` index was present. Evidence comes from targeted README, POM, CI, and source
path inspection. No application execution, service provisioning, or broad tests were performed.


## Maintenance process

Follow [constitution.md](constitution.md) for the domain-card, assessment, planning, verification,
and submission gates. Commands are installed under `.omp/commands/`; read them as agent
instructions. No application build or test was run for tool adoption. Scaffold checks establish
tool installation only, not application correctness.
