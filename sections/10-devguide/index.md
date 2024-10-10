---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer guide

## Setting up the development environment

To contribute to or extend Temporario, follow these steps to set up your development environment:

Prerequisites:
- Java JDK (version 17 or higher)
- Android Studio (recommended IDE)
- Gradle (used for building the project)
- Git (for version control)

Clone the project from the GitHub repository:

`git clone https://github.com/your-repo/android-calendar-app.git
cd android-calendar-app`

Open the project in Android Studio.

Dependencies:
- The app uses Gradle for dependency management. All necessary libraries and plugins are defined in the `build.gradle` files (both project-level and app-level).
- To sync the dependencies, open the project in Android Studio and click Sync Now when prompted or run `./gradlew build`.

## Building and running the app

After setting up the environment, follow these steps to build and run the app:

- To build the app: `./gradlew assembleDebug`;
- To run the app on an emulator or connected device, use: `./gradlew installDebug`.

Alternatively, use Android Studio’s build and run buttons for easier workflow.

## Testing

The project includes instrumentation tests to ensure app quality.

Running Instrumentation Tests (on an emulator or device): `./gradlew connectedAndroidTest`.

Developers are encouraged to write new tests and maintain test coverage when making changes.

## Contributing to the project

To contribute to the development of the app:

- Fork the repository and create a new branch for your changes: `git checkout -b feature/new-feature`
- Make your changes and commit them with a meaningful commit message:
`git commit -m "Add new feature"`
- Push the branch and submit a pull request to the main repository: `git push origin feature/new-feature`

Be sure to adhere to the project's coding guidelines and maintain a high level of code quality.