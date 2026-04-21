## 2.6.3

### Added
- Auto-generate a stable `STATIC_API_KEY` if `api_key` option is blank; persisted to `/data/api_key` so it survives restarts

## 2.6.2

### Fixed
- Debug logging now confirms when `STATIC_API_KEY` is active at startup
- Warning logged when no `api_key` is configured

## 2.6.1

### Added
- `api_key` option: exposes Pocket ID's `STATIC_API_KEY` for headless API access
- `encryption_key` option: persists a stable encryption key for the SQLite database
- Auto-generates and persists `encryption_key` to `/data/encryption_key` if left blank

## 2.6.0

### Added
- Initial release wrapping Pocket ID v2.6.0
- Supports amd64, aarch64, and armv7 architectures
- Passkey/WebAuthn-based authentication for Home Assistant users
- OIDC provider for SSO with Mealie and other self-hosted apps
- Automatic multi-arch Docker images via GitHub Actions CI
