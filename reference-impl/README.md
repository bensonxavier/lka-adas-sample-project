# Reference Implementation (Placeholder)

This folder is reserved for a minimal, open-source lane-detection reference implementation (Python + OpenCV), to be added in a later phase (see `docs/roadmap.md`).

**Purpose:** give the stakeholder requirements in `requirements/` a concrete, inspectable grounding — so that when the requirements-to-userstories pipeline generates features/stories referencing "lane detection," there's a real (if toy) artifact to point to, not just prose.

**Planned approach:** adapt a well-known open-source lane-finding technique (e.g., color/gradient thresholding + perspective transform + polynomial lane fit, in the style of common open-source "advanced lane finding" projects) into a single-file script — not a production perception stack.

This is intentionally out of scope for the initial pipeline test. It can be added once Phase 1 (manual pipeline run) is validated.
