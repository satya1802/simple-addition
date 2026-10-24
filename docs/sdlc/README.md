# Simple addition — SDLC Documentation

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start overview -->
Simple addition

**Documentation version:** v6
<!-- sdlc:auto:end overview -->

## Contents

<!-- sdlc:auto:start contents -->
| Document | State |
|---|---|
| [Requirements](requirements/README.md) | v1 approved |
| [Architecture](architecture/README.md) | 15 entries |
| [Development](development/README.md) | 11 entries |
| [Testing](testing/README.md) | 1 entry |
| [Deployment](deployment/README.md) | 1 entry |
| [Maintenance](maintenance/README.md) | 1 entry |
| [Data model](architecture/data-model.md) | generated |
| [API (OpenAPI)](architecture/api/openapi.yaml) | generated |
| [Decisions (ADRs)](architecture/adr/README.md) | 4 decisions |
| [Sprint plan](development/sprint-plan.md) | 4 sprints |
| [Developer guide](development/developer-guide.md) | generated |
| [API reference](development/api-reference.md) | 1 route |
| [Test report](testing/test-report.md) | not run yet |
| [Deployment guide](deployment/deployment-guide.md) | not deployed yet |
| [Runbook](deployment/runbook.md) | not deployed yet |
| [Release notes](deployment/release-notes.md) | 0 releases |
| [Traceability matrix](traceability-matrix.md) | 20 requirements |
| [Changelog](CHANGELOG.md) | 6 versions |
<!-- sdlc:auto:end contents -->

## Open gaps

<!-- sdlc:auto:start open-gaps -->
### Requirements

- Assumption that lines carry number only (no labels) is flagged in the input as the most likely-to-be-wrong assumption if real use is expenses or stock-taking - not yet confirmed.
- Editing feature set (delete/edit/clear/copy) is an explicit assumption for v1 scope, not a confirmed requirement - may be trimmed later.
- No formal accessibility audit or conformance certification is in scope for v1 - only basic expectations assumed; not verified by any input provided.
- Analytics tool/vendor for 'privacy-friendly aggregate page counts' is not specified in any input.

### Architecture

- Input does not state who approved this architecture or on what date.
- No explicit linkage given between this architecture and specific requirement IDs (US-001..US-020); traceability_matrix for this phase cannot be populated from architecture input alone.
- No requirement IDs explicitly cited for this component in the input.
- Not deployed at launch -- confirm with deployment phase whether/when this is ever activated.
- No requirement IDs explicitly cited for this critical path in the input.
- Input does not state how tape relates structurally to tape_line (e.g. one-to-many) beyond both being listed as entities.
- FastAPI node is explicitly reserved/not deployed -- confirm actual deployment status once a deployment phase exists.
- Saved-history feature using PostgreSQL is explicitly out of scope now -- no current requirement drives this decision.

### Development

- No explicit mapping provided of which backlog items belong to which sprint.
- No execution/completion status (not started, in progress, done) reported for any sprint or story.
- No code, commit, PR, or build artifacts referenced for this phase.
- Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 1.
- No status reported on whether Sprint 1 work has started, is in progress, or is complete.
- Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 2.
- No status reported on whether Sprint 2 work has started, is in progress, or is complete.
- Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 3.
- No status reported on whether Sprint 3 work has started, is in progress, or is complete.
- Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 4.
- No status reported on whether Sprint 4 work has started, is in progress, or is complete.
- No development/ticket status reported for any story in this epic (not started, in progress, done).
- No code or test evidence provided.
- No code or test evidence provided, including no confirmation of how penny-accurate decimal arithmetic (US-012) was implemented.
- No code or test evidence provided, including no confirmation of the persistence mechanism used for US-016.
- No code or test evidence provided, including no confirmation that US-019's no-data-leaves-device guarantee has been implemented or verified.

### Testing

- No test plans, cases, or execution results exist for any of the 20 user stories / 61 acceptance criteria.
- The dev plan names qa-agent test tasks per story, but no evidence these tasks have been executed or their results captured.

### Deployment

- No deployment record exists despite an approved architecture naming a specific hosting target (S3+CloudFront, EU region).
- No release/version tagging information available to link into the traceability matrix's deployment_ref field.

### Maintenance

- No monitoring, incident, or support data exists yet; expected given no deployment has occurred.
<!-- sdlc:auto:end open-gaps -->
