# Copilot Instructions for security-samples

This repository contains multiple Android Studio projects, each demonstrating a different Android security feature. These instructions are for AI coding agents to maximize productivity and maintain project conventions.

## Repository Structure
- Each top-level folder is a standalone Android Studio project:
  - `BiometricAuthentication/`: Fingerprint authentication using Android KeyStore.
  - `BiometricLoginKotlin/`: Canonical sample for integrating Android Biometrics (BiometricPrompt API).
  - `DirectBoot/`: Demonstrates device-protected storage and direct boot aware components.
  - `FileLocker/`: Secure file and preferences encryption using Jetpack Security.

## Key Patterns & Conventions
- **No shared code**: Each project is independent. Do not introduce cross-project dependencies.
- **AndroidX & Jetpack**: Use AndroidX libraries and Jetpack Security where applicable.
- **Minimum SDKs**: Respect the minimum SDK version in each module (see `build.gradle`).
- **Security APIs**: Follow the sample's approach for using Android KeyStore, BiometricPrompt, and EncryptedFile/EncryptedSharedPreferences.
- **Direct Boot**: For `DirectBoot`, use `Context.createDeviceProtectedStorageContext()` and set `android:directBootAware="true"` in the manifest for components that must run before unlock.

## Build & Run
- Use the included `gradlew` or `gradlew.bat` in each project root for builds: `./gradlew build`.
- Open individual projects in Android Studio for development and debugging.
- No monorepo build: build/test each sample independently.

## Testing & Debugging
- Each sample is self-contained; test and debug within its own Android Studio session.
- Refer to the `README.md` in each project for sample-specific instructions and screenshots.

## External Dependencies
- Jetpack Security, AndroidX Biometrics, and Android Support libraries are used. See each module's `build.gradle` for details.

## Examples
- See `FileLocker/app/src/main/java/` for EncryptedFile and EncryptedSharedPreferences usage.
- See `BiometricLoginKotlin/app/src/main/java/` for BiometricPrompt integration.
- See `DirectBoot/Application/src/main/AndroidManifest.xml` for direct boot manifest config.

## Do Not
- Do not refactor to share code across samples.
- Do not add new dependencies without updating the relevant `build.gradle` and documenting in the sample's `README.md`.

---
For more details, always check the sample's own `README.md` and source code for the canonical implementation.
