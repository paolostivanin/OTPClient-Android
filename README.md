# OTPClient for Android

[![CI](https://github.com/paolostivanin/OTPClient-Android/actions/workflows/ci.yml/badge.svg)](https://github.com/paolostivanin/OTPClient-Android/actions/workflows/ci.yml)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)

An Android port of [OTPClient](https://github.com/paolostivanin/OTPClient), a
highly secure and easy to use TOTP/HOTP/Steam client. It reads and writes the same
encrypted database format as the desktop application.

> **Status:** early development. Not yet released.

## Features

- TOTP, HOTP and Steam codes (SHA-1 / SHA-256 / SHA-512)
- Desktop-compatible encrypted database (AES-256-GCM; Argon2id key derivation,
  with PBKDF2 for legacy v1 databases)
- Biometric unlock
- Add tokens by scanning a QR code (CameraX + ML Kit) or manually
- Import / export: Aegis, Authenticator Pro, FreeOTP+, 2FAS, and Google
  Authenticator migration QR codes
- Multiple databases
- Sync through Google Drive or WebDAV
- Screenshots / recents thumbnails blocked (`FLAG_SECURE`); app lock on background

## Requirements

- JDK 17 or newer
- Android SDK with platform 35 (`ANDROID_HOME` set, or `sdk.dir` in `local.properties`)
- A device or emulator running Android 12 (API 31) or newer

## Building

```sh
./gradlew assembleDebug          # debug APK -> app/build/outputs/apk/debug/
./gradlew testDebugUnitTest      # unit tests
./gradlew lintDebug              # Android lint
./gradlew installDebug           # install on a connected device
```

## Project layout

Multi-module Gradle build (Kotlin, Jetpack Compose, Hilt):

| Module | Purpose |
| --- | --- |
| `app` | Application entry point, navigation, theme, app lock |
| `core:core-model` | Shared data classes and crypto constants |
| `core:core-crypto` | AES-GCM cipher, Argon2id / PBKDF2 key derivation |
| `core:core-otp` | TOTP / HOTP / Steam generation, Base32 |
| `core:core-database` | Encrypted database file format and repository |
| `core:core-importexport` | Import/export providers (Aegis, Authenticator Pro, FreeOTP+, 2FAS, Google migration) |
| `core:core-sync` | Google Drive and WebDAV sync providers |
| `feature:feature-*` | Compose screens: unlock, token list, add token, settings, import/export, database manager |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Security issues: see [SECURITY.md](SECURITY.md).

## License

OTPClient for Android is free software, licensed under the
[GNU General Public License v3.0](LICENSE).
