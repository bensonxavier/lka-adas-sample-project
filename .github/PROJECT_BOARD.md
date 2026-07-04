# GitHub Project Board Scheme (Jira Stand-In)

This repo uses a GitHub Project (Projects v2, board view) as a lightweight substitute for Jira, so the pipeline's Jira-ready output has somewhere real to land during Phase 1–2 testing.

## Board setup (manual, one-time)

1. Go to the repo → **Projects** tab → **New project** → **Board** template
2. Name it: `LKA Pipeline Test Board`
3. Create columns (replace the defaults):

| Column | Maps to Jira concept |
|---|---|
| `Backlog` | Untriaged stakeholder requirements |
| `Feature` | Decomposed features (output of Feature Decomposition stage) |
| `Story` | Generated user stories (output of User Story Generation stage) |
| `In Review` | Stories under human review before acceptance |
| `Done` | Accepted / pipeline-validated stories |

## Labels (substitute for Jira issue types / fields)

| Label | Meaning |
|---|---|
| `type:requirement` | Raw stakeholder requirement (SR-LKA-xxx) |
| `type:feature` | Decomposed feature |
| `type:story` | User story |
| `asil:C` | Safety-relevant, ASIL C (per ODD assumptions) |
| `needs-clarification` | Flagged by SR Analyst S1.7 clarification step |
| `source:SR-LKA-00X` | Traceability back to originating SR |

## Issue template mapping

- `.github/ISSUE_TEMPLATE/user_story.md` — mirrors the Jira-ready story format the pipeline is expected to output (title, description, acceptance criteria, traceability)
- `.github/ISSUE_TEMPLATE/clarification_request.md` — mirrors an S1.7 clarification package

## Phase 1 workflow (manual)
1. Run the pipeline against `requirements/SR-LKA-001-010.md`
2. For each generated feature/story in `workflow-outputs/`, manually create a matching GitHub Issue using the templates below, apply labels, place in the appropriate column
3. This manual mirroring step becomes automated in Phase 2 (see `docs/roadmap.md`)
