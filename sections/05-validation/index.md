---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing

For the testing of Temporario, an **Instrumented Testing** approach was used to ensure that the app behaves as expected in a real Android environment. This involved creating a suite of **5 instrumental tests** that was executed on physical devices, focusing on different components' behavior.

- Type of tests conducted: All tests were functional tests aimed at verifying the UI and behavior of the app.
- Testing framework: The instrumental tests were developed using the Android testing framework, specifically utilizing tools like `Espresso` for UI testing to simulate user interactions.

**Disclaimer**: During the preparation of the testing suite, ChatGPT was used to generate some templates for instrumental tests. After using this tool, the work was reviewed, edited and further developed as needed. The author takes full responsibility for the content of the final artifact.

### Success rate 
The success rate of the tests conducted was 100%, with all tests passing successfully. This indicates that the app’s functionality aligns with the intended design and user experience, as specified in the requirements.

### Coverage
Due to the limited number of tests performed and the focus on UI, further testing is recommended to enhance coverage on both core functionalities and edge cases.
- Areas covered: buttons functionality, display behavior, fragment transitions. 

### Future testing plans
To improve coverage, additional tests should be developed to encompass a broader range of functionalities, including error handling and performance testing.

### Comments w.r.t. requirements' acceptance criteria
The instrumental tests were aligned with the acceptance criteria established during the requirements phase. 

## Acceptance test

Acceptance testing was conducted manually to ensure that the calendar app meets the defined requirements and provides the expected functionality for users. This phase involved verifying critical features and user workflows as outlined in the application’s specifications. Test scenarios were derived from user stories and requirements specified in this documentation.

### Test Cases
1. User registration
    - Description: Verify that users can successfully register a new account.
    - Outcome: Passed. The registration process was completed without errors, and users received a confirmation message.

2. User login:
    - Description: Verify that registered users can log in to their accounts.
    - Outcome: Passed. Users were able to log in successfully with valid credentials, and error messages were displayed for invalid logins.

3. Create event:
    - Description: Verify that users can create a new event with valid details.
    - Outcome: Passed. Events were created successfully, and users received confirmation of the creation.

4. Edit event:
    - Description: Verify that users can edit existing events.
    - Outcome: Passed. Users were able to update event details, and changes were saved correctly.

5. Delete event:
    - Description: Verify that users can delete an event.
    - Outcome: Passed. Users successfully deleted events, and they no longer appeared in the event list.

6. List events:
    - Description: Verify that users can view a list of their events.
    - Outcome: Passed. The app displayed a list of events, and users could see all their scheduled events.

### Comments w.r.t. requirements’ acceptance criteria
All acceptance tests confirmed that the app fulfils the key user requirements as defined in the project documentation.