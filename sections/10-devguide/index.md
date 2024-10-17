---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer guide

To contribute to or extend Temporario, follow these steps to set up your development environment, build, and deploy the app.

## Setting up the development environment

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

## Configuring the Firebase APIs

**Firebase Realtime Database** is the database solution for storing and syncing data in real-time. 
**Firebase Authentication** is used to manage user authentication. 
Below are the steps to configure Firebase:

1. Go to the [Firebase Console](https://console.firebase.google.com/) and click "Create a project". Follow the steps to create a new Firebase project associated with the app.
2. Once the project is created, go to "Project settings" and click "Add app" in the "Your apps" section. Register the Android project by providing the *package name* found in the `AndroidManifest.xml` file. 
3. Download the generated `google-services.json` file and place it in the `app/` directory of the Android project, then make sure that the dependencies are included in the app's `build.gradle` file. For the development of the current release of Temporario the following versions were used:
    - Firebase Realtime Database: `com.google.firebase:firebase-database-ktx:21.0.0`;
    - Firebase Authentication: `com.google.firebase:firebase-auth:23.0.0`.
4. To enable Firebase Authentication, go to the Console and navigate to Authentication. Click on "Sign-in method" and enable authentication via Email/Password and Google Sign-In.
5. To enable the Realtime Database click on "Create database" and set its rules.
6. Build and run the app in Android Studio to make sure that it connects to Firebase properly. 

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