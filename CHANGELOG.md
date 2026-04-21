# Changelog

## [2.6.1] - 2026-04-21

### Added
- `api_key` option: exposes `STATIC_API_KEY` for headless/automated API access
- BSD 2-Clause License (matching upstream Pocket ID), no copyright line
- "Add to Home Assistant" one-click install button in README
- `OIDC_SIGNUP_ENABLED=true` documented so new users can self-register via OIDC

### Changed
- README updated with clearer Mealie integration instructions

## [2.6.0] - 2026-04-21

### Added
- Initial release wrapping Pocket ID v2.6.0
- Supports amd64, aarch64, armv7 architectures
- Auto-generates and persists encryption key if not configured
- Multi-arch Docker images published to GHCR via GitHub Actions
