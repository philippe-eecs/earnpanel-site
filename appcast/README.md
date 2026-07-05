# Sparkle appcast

This directory will host the Sparkle update feed for the EarnPanel macOS app:

- `appcast.xml` — the Sparkle appcast feed the app polls for updates
- Release archives (`EarnPanel-<version>.zip` or `.dmg`) referenced by the feed

Entries in `appcast.xml` must be signed with the Sparkle **EdDSA (ed25519)** key
(`sparkle:edSignature` on each enclosure), generated with Sparkle's
`generate_keys` tool and signed with `sign_update`.

## Key handling — important

- **Back up the EdDSA private key** (e.g., in a password manager or offline
  secure storage). If it is lost, existing installs can never verify another
  update and every user must manually reinstall.
- **Never commit the private key to this repository** (or any repository).
  Only the public key belongs in the app's `Info.plist` (`SUPublicEDKey`).
