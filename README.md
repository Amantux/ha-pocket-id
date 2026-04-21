# Home Assistant Add-on: Pocket ID

[![GitHub Release](https://img.shields.io/github/release/Amantux/ha-pocket-id.svg)](https://github.com/Amantux/ha-pocket-id/releases)
[![License](https://img.shields.io/github/license/Amantux/ha-pocket-id.svg)](LICENSE)

A Home Assistant add-on that runs [Pocket ID](https://github.com/pocket-id/pocket-id) — a lightweight OIDC provider for passkey/SSO authentication.

With Pocket ID, you can set up **single sign-on** across your self-hosted services (Mealie, etc.) using **Face ID, Touch ID, or a security key** — no passwords required.

## Installation

1. Add this repository to your Home Assistant add-on store:
   - **Settings → Add-ons → Add-on Store → ⋮ → Repositories**
   - Add: `https://github.com/Amantux/ha-pocket-id`

2. Install **Pocket ID** from the add-on store.

3. Configure:
   - `app_url`: the URL where Pocket ID will be accessible from your browser (e.g. `http://homeassistant.local:1411`)
   - `encryption_key`: optional — auto-generated and persisted on first run if left blank

4. Start the add-on. Open the web UI at port `1411` to create your admin account and register your first passkey.

## Connecting Mealie

In your Mealie add-on options, add these env vars:

```
OIDC_AUTH_ENABLED=true
OIDC_SIGNUP_ENABLED=false
OIDC_CONFIGURATION_URL=http://homeassistant.local:1411/.well-known/openid-configuration
OIDC_CLIENT_ID=<client-id from Pocket ID>
OIDC_CLIENT_SECRET=<client-secret from Pocket ID>
OIDC_PROVIDER_NAME=Home
OIDC_AUTO_REDIRECT=true
OIDC_REMEMBER_ME=true
OIDC_USER_CLAIM=preferred_username
```

> **Note on passkeys**: WebAuthn/passkeys require HTTPS except on localhost. For local LAN access over HTTP, use Pocket ID's one-time login code flow instead. Passkeys work fully if your HA instance is behind HTTPS (Nabu Casa, Let's Encrypt, etc.).

## Versions

See [CHANGELOG.md](CHANGELOG.md).

## Credits

- [Pocket ID](https://github.com/pocket-id/pocket-id) by the Pocket ID contributors
- Add-on wrapper by [Amantux](https://github.com/Amantux)
