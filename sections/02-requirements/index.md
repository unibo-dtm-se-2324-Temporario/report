---
title: Requirements
has_children: false
nav_order: 3
---

# Requirements

## User stories

1. As a student, I want to add my classes to the calendar, so that I can manage my schedule.

2. As a busy businesswoman, I want to create an account, so that I can sync my calendar across multiple devices.

3. As a parent, I want to edit any events, so that I can adapt to my family's plans.

4. As a wedding planner, I want to delete an event, so that I can remove cancelled activities according to my clients' preferences.

5. As a traveller, I want to quickly view the events from my calendar, so that I do not miss any planned activity.

6. As a manager, I want to view my calendar in a monthly format, so that I can easily plan meetings for the month.

7. As a user, I want to log in using my Google account, so that I do not need to keep track of unnecessary passwords.

8. As a 9-to-5 worker, I want to view the detailed schedule for the day, so I won't lose any time.

## Functional requirements

- The user must be able to sign in with a Google account.
    * The user can open the app, see and click the sign-in button.
    * The user can select an existing Google account and be authenticated by the app.
    * Upon successful authentication, the user is redirected to the main page of the app.

- The user must be able to see and scroll through the calendar.
    * The user can see the calendar on the app's main page.
    * The user can scroll forward and backwards through months by swiping or tapping the arrows.
    * The calendar is responsive, with no significant delay (less than 1 second).

- The user must be able to add events to the calendar.
    * The user can open the "Add a new event" form by clicking on the corresponding button.
    * The form includes fields for selecting the event date, time, duration, and adding a description.
    * If some of the values are not manually selected, the app uses default values.
    * The user can click "Create" and the event is shown in the calendar view.
    * The event is visible in the correct date slot.

- The user must be able to edit an existing event.
    * The user can see and tap the button for editing a specific event, once on the list-view page for a day.
    * Upon clicking the button, a form for editing the event opens, where all the fields (date, time, description and duration) are pre-filled with the event's current details.
    * The user can modify any field and click "Save event".
    * The updated event is desplayed on the calendar.

- The user must be able to delete existing events.
    * The user can see and tap the button for deleting a specific event, once in the list-view page for a day.
    * Upon clicking, the system shows a pop-up with the message "Event deleted!".
    * The event is no longer visible in the details page for the day nor in the calendar.

- The user must be able to view all the events for a certain day.
    * The user can tap on any date in the calendar to view a detailed list of the events for the day.
    * For every event, the date, time, desciption and duration are visible.
    * If there are no events for the day, a "No events for the day" message is displayed.

- The user must be able to immediately see any modifications made in the calendar view.
    * For every addition, modification or deletion the changes are immediately (less than 1 second) visible in the calendar view and in the details pages.

- The user must be able to see their modifications (events added, deleted, or edited) after closing and reopening the app, or signing out and signing back in.  
    * When the user adds, edits or deletes an event, the changes are immediately saved.
    * The changes are visible after the app is closed and reopened.
    * If the user signs out and signs back in, the calendar must reflect the latest state of the calendar.
    * The user's events must sink with their account, so the same modifications appear across different devices if they sign in with the same account.

- The user must be able to sign out of their account.
    * The user can see and click the "Sign out" button from the app's main page.
    * Upon clicking, the user is redirected to the login screen.

## Non-functional requirements

- The app must be responsive and load any page in under 3 seconds.
    * Any page should load within 3 seconds on devices with standard internet speed.
    * The user can scroll through the calendar and open forms (for adding, deleting or editing events) without noticeable lag (less than 200ms delay).

- Synchronization of data between the app and the backend should occur in the background within 3 seconds of any event modification.
    * When a user adds, edits, or deletes an event, the app initiates a synchronization process automatically in the background.
    * The synchronization process must be completed within 3 seconds under normal network connections.

- The app must use OAuth 2.0 for authenticating users via Google Sign-In to ensure secure access to user data.
    * When choosing to sign in with Google, the user should be redirected to the Google authentication page.

- The app must be easy to use and navigate.
    * The user must be able to access the adding, editing or deleting buttons with no more than 3 clicks.
    * The app must include clear labels for all buttons.
    * The app must show feedback messages after every successful activity (creation, modification or deletion of an event).

- The app must be compatible with a range of devices.
    * The app must function correctly on devices running Android 9.0 and above.

- The codebase must be easily understandable.
    * The code should follow established coding standards and be structured into meaningful modules.

## Implementation

- The app must be built using Kotlin and Android SDK.
    * The development environment uses Kotlin and Android SDK as primary technologies.

- The app must be developed using Android Studio as the IDE.
    * All source code is written and tested in Android Studio.

- The app must integrate with a Firebase backend for user authentication and data storage.
    * The app uses Firebase for user registration, login, and syncing calendar events across devices.

- The app must include tests.
    * Tests are run automatically in the CI/CD pipeline, with no critical failures.

- All third-party libraries and dependencies must be managed using Gradle.
    * The `build.gradle` file clearly lists all dependencies with specified versions.
    * The app builds successfully without any unresolved dependencies.

- The source must be stored in a Git repository on GitHub.
    * The Git repository shows a clear commit history following a consistent committing convention (Conventional Commits). 