---
title: Concept
has_children: false
nav_order: 2
---

# Concept

The product developed in this project is a mobile application designed for Android devices, featuring a Graphical User Interface (GUI). The app allows users to interact with a calendar interface where they can view, add, edit, and manage their activities.

**Key characteristics** of the product:
- *Platform*: Android mobile application, built using the Android SDK.
- *User interface*: The app includes a GUI that presents a calendar view and a form-based interface for adding events.
- *Functionality*: The app provides core calendar functions such as creating, updating, and deleting events. Users can input event titles, dates, times, and optional descriptions.

The primary goal is to offer users an easy way to organize and keep track of personal or professional events within a structured, intuitive mobile application.

## Use case collection

**1. Add an event to the calendar**
- Actor: User
- Goal: Add an event to the calendar.
- Preconditions: User has the app installed and is logged in.
- Basic flow: 
    - The user opens the app and navigates to the calendar view.
    - The user taps on the "Add a new event" button.
    - A form appears where the user inputs the event details (date and time, description, duration).
    - The user saves the event.
    - The system stores the event in the database and updates the calendar view to show the new event.
- Postconditions: The event is saved and visible in the calendar.
- Alternative flows:
    - If the user decides not to add the event in the end, they can close the form and go back to the calendar view.

**2. View events on a specific date**
- Actor: User
- Goal: View all events scheduled for a specific day.
- Preconditions: The user has previously added events to the calendar.
- Basic flow:
    - The user opens the app and clicks on a day.
    - The system displays all events scheduled for that date, including their details.
- Postconditions: The user can view the events for the selected date.
- Alternative flows:
    - If no events are scheduled for the selected date, the system displays a "No events for the day" message.

**3. Edit an existing event**
- Actor: User
- Goal: Modify the details of an existing event.
- Preconditions: The user has added events to the calendar.
- Basic flow:
    - The user clicks on a day that has scheduled events.
    - A list of all the events for that date is shown to the user.
    - The user clicks the editing button of the event they want to modify.
    - The user modifies the event information (e.g., changes the time or description).
    - The user saves the changes.
    - The system updates the event in the database and reflects the changes in the calendar.
- Postconditions: The event is updated in the system.
- Alternative flows:
    - If the user cancels the editing process, the system keeps the original event details.

**4. Delete an event**
- Actor: User
- Goal: Remove an event from the calendar.
- Preconditions: The user has added events to the calendar.
- Basic flow:
    - The user clicks on a day that has scheduled events.
    - A list of all the events for that date is shown to the user.
    - The user clicks the deleting button of the event they want to remove.
    - The system removes the event from the database and updates the calendar view.
- Postconditions: The event is deleted and no longer visible in the calendar.
- Alternative flows:
    - If the user cancels the deletion, the event remains unchanged.

**5. Sync calendar with other devices**
- Actor: User
- Goal: Sync the calendar across multiple devices (e.g., phone, tablet).
- Preconditions: The user has a registered account and is logged in on multiple devices.
- Basic flow:
    - The user adds an event to the calendar on one device.
    - The system saves the event to the database.
    - The user opens the app on another device.
    - The system syncs the calendar and displays the event on both devices.
- Postconditions: The event is visible on all synced devices.
- Alternative flows:
    - If the devices are not connected to the internet, the calendar will not be synced.

**6. Scroll through the calendar**
- Actor: User
- Goal: Search for events based on date.
- Preconditions: The user is logged in.
- Basic flow:
    - The user scrolls through the calendar.
- Postconditions: The user can view on which dates events are planned.
- Alternative flows:
    - If there are no events created, the user will see the empty calendar.

**7. Create an account**
- Actor: New user
- Goal: Create a new account to start using the app and manage personal activities.
- Preconditions: The user has downloaded and installed the app.
- Basic flow:
    - The user opens the app and selects "Click to register".
    - The system presents a registration form requesting personal details (full name, email, password).
    - The user fills out the required details and submits the form.
    - The system validates the inputs (e.g., checks if the email is already registered, ensures passwords match and meet criteria).
    - Upon successful validation, the system creates a new account for the user and stores the information in the database.
    - The system logs the user into the app and redirects them to the main calendar view, where they can start adding events.
- Postconditions: The account is created, and the user is logged in with access to the app’s features.
- Alternative flows:
    - If the email is already registered, the system prompts an error.
    - If there are validation errors (e.g., weak password or missing information), the system highlights the issues.
    - If the user decides to sign in with Google, the system redirects the user to the third-party service for authentication, then returns to the app upon successful authentication.
