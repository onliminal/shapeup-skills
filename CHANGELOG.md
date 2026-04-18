# Changelog

Release notes for the installable Shape Up plugin.

This changelog is intentionally release-facing rather than commit-facing. It summarizes what changed for users of the skill.

## [1.2.1] - 2026-04-18

### Added

- Added a new `skills/shapeup/examples/` section with four completed sample runs:
  - `new-product`
  - `internal-tool`
  - `customer-request`
  - `ai-workflow`
- Added abridged transcripts plus finished artifacts for each example so users can see tone, pacing, handoffs, and output quality in practice.

### Changed

- Updated repo docs to make the distinction explicit between normative protocol docs in `references/` and illustrative sample runs in `examples/`.

## [1.2.0] - 2026-04-17

### Added

- Added persistent `Open Questions` and `Next Best Question` sections to the artifact formats across the planning pipeline.

### Changed

- Updated resume behavior so returning sessions surface unresolved questions and, by default, continue with the recorded next-best question.
- Extended pitch assembly guidance and the pitch template to preserve resumability information through kickoff.

## [1.1.0] - 2026-04-17

### Added

- Added a new optional `Evidence` phase between Explore and Frame for lightweight interviews, smoke tests, concierge tests, fake doors, and other cheap validation work.
- Added a new `evidence.md` artifact format for capturing experiments, signals, and the resulting recommendation.

### Changed

- Updated routing so promising but still-uncertain wedges move into Evidence before they earn appetite.
- Tightened Explore and Frame handoffs so the skill can distinguish between branching, testing, and converging.

## [1.0.2] - 2026-04-17

### Added

- Added explicit Explore-to-Frame handoff criteria in both `explore.md` and `frame.md`.

### Changed

- Clarified when to stay in Explore versus when a problem is specific enough to begin Framing.

## [1.0.1] - 2026-04-17

### Added

- Added contributor-facing versioning rules for deciding when and how to bump the plugin version.

### Changed

- Bumped the plugin manifest version after shipped behavior changes to establish a clearer release process.

## [1.0.0] - 2026-03-31

### Added

- Introduced the installable plugin structure with `.claude-plugin/plugin.json` and marketplace metadata.
- Packaged the Shape Up skill for plugin-style installation while preserving the core planning workflow.

### Changed

- Reorganized the repository into the current `skills/shapeup/` layout used by the installable plugin.
