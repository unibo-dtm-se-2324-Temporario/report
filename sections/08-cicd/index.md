---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

## What is automated?

In this project, the CI/CD pipeline is designed to ensure that every code change is automatically built, tested, and, if wanted, released. 

1. **Code checkout** - Every time code is pushed to the main branch, it is automatically checked out from the repository using GitHub Actions.

2. **Build automation** - The project is automatically built by running the Gradle build system. It compiles the Android app code and generates the necessary APKs. Specifically, it runs the `assembleDebug` and `assembleRelease` tasks.

3. **Automated testing** - Instrumentation tests are automatically executed on every push. These tests ensure that the app functions correctly by running them on an emulator. If any test fails, the pipeline stops, preventing broken code from being released.

4. **Artifact generation and release** - Upon successful completin of the test, the release APK is generated. If a new version tag is pushed, the pipeline automatically generates a release on GitHub, attaching the release APK as an artifact. This allows for the automated deployment of the application to GitHub without manual intervention.

5. **Test reporting** - Test reports are automatically collected and published, providing immmediate feedback on the quality and stability of the app.

## Why is this automated?

Automation is essential for several reasons:
- *Consistency*: Manual processes are prone to errors. The CI/CD pipeline ensures that the process is executed the same way every time, improving reliability.
- *Speed*: Changes are integrated and tested immediately.
- *Immediate feedback*: Instant feedback is received through build and test results. This allows for catching errors and fixing issues easrly in the development cycle.
- *Quality assurance*: automated tests ensure that the code is always tested before being released, improving the overall quality of the software.
- *Efficient release management*: Automation of the release process removes the need for manual intervention and ensures that releases are consistent and easy to manage.

## GitHub Actions implementation

**GitHub Actions** is used as the automation tool for the CI/CD workflow. The pipeline is defined in a YAML file located at `.github/workflows/main`.yaml. It triggers on every push to the `main` branch, on pull requests to the `main` branch, and whenever a version tag that starts with 'v' is created. The workflow consists of the following steps:

### Run tests

- **Checkout code**: This is handled by the `actions/checkout@v2` action, which pulls the latest code from the repository.
- **Set Up JDK**: The `actions/setup-java@v2` action is used to configure JDK 17 with the Temurin distribution, which is required for building the Android application.
- **Build the app**: The build process is automated using Gradle, specifically running the tasks `assembleDebug` and `assembleAndroidTest`.
- **Run instrumentation tests**: Instrumentation tests are executed using the `emulator-wtf/run-tests@v0.9.10` action, ensuring that the app functions correctly on an Android emulator.
- **Publish test report**: Test results are published with the `mikepenz/action-junit-report@v2` action, making it easy to track the outcomes of the tests.

### Release

This job runs is dependent on the completion of the `run-tests` job. It triggers only for tagged releases.
- **Checkout code**: The repository is checked out using `actions/checkout@v2`.
- **Set Up JDK**: The JDK 17 is set up with the `actions/setup-java@v2` action.
- **Build release APK**: The release version of the APK is built using Gradle by executing the `assembleRelease` task.
- **Sign APK**: The `ilharp/sign-android-release@v1` action is used to sign the APK with the specified signing credentials, ensuring that the APK is secure and ready for release.
- **Upload artifact**: The signed release APK is uploaded using the `actions/upload-artifact@v3` action, making it available for download.
- **Create GitHub release**: A new GitHub release is created when a new tag is pushed, using the `softprops/action-gh-release@v1`. The release is tagged with the name of the version specified in `github.ref`.
- **Upload APK to GitHub Release**: The signed APK is uploaded to the created GitHub release, ensuring it is easily accessible.