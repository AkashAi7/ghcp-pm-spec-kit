---
mode: agent
description: "/release — Generate release notes for a version or sprint delivery. Covers new features, fixes, known issues, and upgrade steps."
---

# Release Notes Generator

## Trigger
This prompt runs when the user types `/release`, `/release-notes`, or asks to "document a release" or "write release notes".

## Instructions

1. Ask for the release version (e.g., `v1.0.0`, `Sprint 3 Release`), OR infer from the sprint plan.

2. Read the WBS from `output/04-wbs-*.md` and sprint plan from `output/08-sprint-plan-*.md` to identify completed features for this release.

3. Read the FSD from `output/02-fsd-*.md` to get feature descriptions and acceptance criteria.

4. Generate release notes in the following format:

---

## Release Notes — <Project Name> <Version>

**Release Date:** <date>
**Released By:** <team>
**Environment:** Development / Staging / Production

---

### Highlights
> One paragraph summarising the most important thing delivered in this release.

---

### New Features
| Feature | Description | FSD Ref | Notes |
|---------|-------------|---------|-------|
| | | FSD-FR-xx | |

For each feature, also write:
```
#### <Feature Name>
<2-3 sentence description in plain language for end users>
```

### Improvements & Enhancements
- Bullet list of improvements (not new features, but things made better)

### Bug Fixes
| Bug ID | Description | Severity | Fixed In |
|--------|-------------|---------|---------|

### Security Updates
- List any security-related changes (auth, permissions, patching)

### Breaking Changes
> ⚠️ List anything that changes existing behaviour that requires user action.

### Deprecations
- Any features/APIs being deprecated (targeted for removal in future release)

### Known Issues
| Issue | Workaround | Target Fix |
|-------|-----------|-----------|

### Upgrade / Migration Steps
If this release requires any setup steps, list them:
1. Step 1
2. Step 2

### Rollback Procedure
- How to revert to the prior version if issues occur

### Dependencies
- New packages, services, or configuration changes introduced

---

5. Also generate a **short version** (5 bullet points max) for email/Teams announcements.

6. Save to `output/14-release-notes-<project-name>-<version>.md`.

Print: `✅ Release notes saved to output/14-release-notes-<project-name>-<version>.md`
