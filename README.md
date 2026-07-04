# LKA ADAS Sample Project

A minimal, open-source **Lane Keep Assist (LKA)** project used as a **test fixture** for the [`requirements-to-userstories`](https://github.com/bensonxavier/automotive-sw-development-agents/tree/main/requirements-to-userstories) agentic pipeline.

This repo is **not** a production ADAS system. It exists to give the requirements→feature→user-story agent workflow realistic, domain-grounded input (stakeholder requirements, an ODD definition, and a toy reference implementation) so the pipeline can be exercised end-to-end in a separate chat context from the framework's own development.

## Why this repo exists

The `requirements-to-userstories` framework needs a realistic subject to test against — one with genuine ambiguity, safety-relevant requirements, and enough structure to validate the SR Analyst → Feature Decomposition → User Story generation chain. Lane Keep Assist was chosen because it's a well-understood, safety-critical Level 2 ADAS function with public reference material (ISO 26262, ASPICE, AIAG-VDA) that maps cleanly onto automotive SW development practices.

## Structure

```
lka-adas-sample-project/
├── requirements/        # Stakeholder Requirements (SR-LKA-xxx) — pipeline input
├── reference-impl/       # Toy open-source lane detection reference (OpenCV-based)
├── docs/                 # ODD definition, assumptions, safety goals
├── workflow-outputs/     # Where the agentic pipeline writes generated features/stories
└── .github/               # Issue templates + Project board scheme (Jira stand-in)
```

## How to use this repo with the pipeline

1. Point the `requirements-to-userstories` SR Analyst agent at `requirements/SR-LKA-001-010.md`
2. Run the pipeline (S1.1 normalization → feature decomposition → user story generation)
3. Review generated output in `workflow-outputs/`
4. Mirror generated stories onto this repo's GitHub Project board (manually for now; GitHub Actions automation is a later phase — see `docs/roadmap.md`)

## Open-source tools used

| Tool | Role |
|---|---|
| GitHub Issues + Projects | Jira stand-in for user story tracking |
| Python + OpenCV | Toy lane-detection reference implementation |
| Markdown/YAML | Stakeholder requirement format (pipeline input contract) |
| GitHub Actions *(planned)* | Auto-trigger pipeline runs on new SR commits |

## Standards referenced

ISO 26262 (Functional Safety), ASPICE (SWE.1–SWE.6), AIAG-VDA FMEA — referenced for realism and traceability structure, not for full compliance. This is a test fixture, not a certified deliverable.

## Status

🚧 Sample/test project — actively used to validate the `requirements-to-userstories` agentic framework. Not intended for real-world ADAS deployment.

## License

MIT — see `LICENSE`.
