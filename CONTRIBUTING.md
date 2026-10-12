# Contributing

## Setup

1. Install JDK 17+ and the Android SDK (platform 35).
2. Clone the repo and run `./gradlew assembleDebug`.

## Before opening a PR

CI runs the following; run them locally first:

```sh
./gradlew assembleDebug testDebugUnitTest lintDebug
```

## Guidelines

- Follow the official Kotlin code style (`kotlin.code.style=official`).
- Keep the module boundaries in [README.md](README.md#project-layout): `core:*` modules
  must not depend on `feature:*` modules or `app`.
- Add dependencies through `gradle/libs.versions.toml`.
- Never log secrets, passwords, or decrypted database contents.
- Changes to the database format must stay compatible with the desktop
  [OTPClient](https://github.com/paolostivanin/OTPClient); add tests with known vectors.

By contributing you agree that your contributions are licensed under the GPL v3 (see [LICENSE](LICENSE)).
