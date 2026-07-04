# Roadmap — LKA Sample Project

This roadmap tracks the maturity of this repo as a **test fixture** for the `requirements-to-userstories` pipeline. It is intentionally decoupled from the framework's own roadmap.

## Phase 1 — Manual pipeline run (current)
- [x] Repo scaffolding created
- [x] Sample stakeholder requirements authored (`requirements/SR-LKA-001-010.md`)
- [x] ODD and assumptions documented
- [ ] GitHub Project board created (Backlog / Feature / Story / Done)
- [ ] Pipeline run manually against `requirements/`, output reviewed in `workflow-outputs/`

## Phase 2 — Automation
- [ ] GitHub Action triggers pipeline run on new/changed files in `requirements/`
- [ ] Generated features/stories auto-committed to `workflow-outputs/`
- [ ] Auto-create GitHub Issues from generated user stories

## Phase 3 — Real tracker integration
- [ ] Replace GitHub Issues stand-in with Jira Cloud (free tier) as the real target system
- [ ] Validate Jira-ready story format (acceptance criteria, story points, labels) against real Jira import

## Phase 4 — Additional ADAS domains
- [ ] Add a second module (e.g., Automatic Emergency Braking or Adaptive Cruise Control) as an additional test domain
- [ ] Validate pipeline generalizes across domains without LKA-specific tuning

## Reference implementation (optional track)
- [ ] Minimal OpenCV-based lane detection script in `reference-impl/`, adapted from open-source lane-finding approaches, to give requirements a concrete (if toy) grounding
