# Home Assistant Add-on: Pocket ID

[![GitHub Release](https://img.shields.io/github/release/Amantux/ha-pocket-id.svg)](https://github.com/Amantux/ha-pocket-id/releases)
[![License](https://img.shields.io/github/license/Amantux/ha-pocket-id.svg)](LICENSE)

A Home Assistant add-on that runs [Pocket ID](https://github.com/pocket-id/pocket-id) — a lightweight OIDC provider for passkey/SSO authentication.

With Pocket ID, you can set up **single sign-on** across your self-hosted services (Mealie, etc.) using **Face ID, Touch ID, or a security key** — no passwords required.

> **Note:** This is a Home Assistant **add-on**, not a HACS integration. Add-ons are installed through the built-in Supervisor add-on store — HACS is not required and cannot install this.

## Installation

1. In Home Assistant, go to **Settings → Add-ons → Add-on Store**

2. Click the **⋮ (three-dot menu)** in the top-right corner, then choose **Repositories**

3. Paste the following URL and click **Add**:
   ```
   https://github.com/Amantux/ha-pocket-id
   ```

4. Close the dialog. The **Pocket ID** add-on will appear in the store — click it, then click **Install**

5. Once installed, open the **Configuration** tab and set:
   - `app_url`: the URL where Pocket ID will be accessible from your browser (e.g. `http://homeassistant.local:1411`)
   - `encryption_key`: leave blank — auto-generated and persisted to `/data/encryption_key` on first run
   - `api_key`: leave blank — auto-generated and persisted to `/data/api_key` on first run; visible in the add-on log

6. Click **Save**, then go to the **Info** tab and click **Start**

7. Open `http://homeassistant.local:1411` to create your admin account and register your first passkey (or use a one-time login code if on HTTP)

## Connecting Mealie

In your Mealie add-on options, add these env vars:

```
OIDC_AUTH_ENABLED=true
OIDC_SIGNUP_ENABLED=true
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

## License

[BSD 2-Clause](LICENSE) — matching upstream [Pocket ID](https://github.com/pocket-id/pocket-id)

## Credits

- [Pocket ID](https://github.com/pocket-id/pocket-id) by the Pocket ID contributors
- Add-on wrapper by [Amantux](https://github.com/Amantux)

## Connecting Mealie

In your Mealie add-on options, add these env vars:

```
OIDC_AUTH_ENABLED=true
OIDC_SIGNUP_ENABLED=true
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

## License

[BSD 2-Clause](LICENSE) — matching upstream [Pocket ID](https://github.com/pocket-id/pocket-id)

## Credits

- [Pocket ID](https://github.com/pocket-id/pocket-id) by the Pocket ID contributors
- Add-on wrapper by [Amantux](https://github.com/Amantux)
