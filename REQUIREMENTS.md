# Requirements

## Functional Requirements

1. **Check Management**
   - Each check contains a title, a detailed description, one main deadline, and zero or more additional deadlines with short descriptions.
   - A newly created check starts in the yellow status.
   - Each check automatically transitions status based on deadlines:
     - **Red** when any deadline is due or passed and the check is not marked complete.
     - **Yellow** when not all deadlines are passed and no deadline is currently due.
     - **Green** when the user marks the check complete and no remaining deadlines exist; otherwise it reverts to yellow.

2. **Web Application**
   - Display a list of all checks with their current statuses (green, red, yellow).
   - Provide a form to create a new check with main and additional deadlines.
   - Allow marking a check as complete.

3. **Android Application**
   - Show persistent notifications for red checks without action buttons.
   - Issue an urgent notification (vibration and full-screen alert if possible) when a check turns red.
   - Provide a home-screen widget displaying all checks as tiles.

4. **Telegram Bot**
   - Command to list all checks.
   - Command to delete a specific check with confirmation.
   - Command to mark a check as complete (same status rules as web app).
   - Command to add an additional deadline to a check.
   - Command to create a new check.
   - Send a notification when a check becomes red.

5. **Backend Service**
   - Expose an API used by all frontend clients for check data and operations.
   - Handle authentication so each user sees only their own checks.
   - Process all commands from the web app, Android app, and Telegram bot.
   - Integrate with Google Calendar to import and display events for the upcoming week as checks.

## Non-functional Requirements

1. **Data Consistency**: All clients must see up-to-date check statuses and details.
2. **Security**: Authentication must protect user data and ensure isolation between users.
3. **Reliability**: Notifications for red checks must be delivered promptly and persist until addressed.
4. **Scalability**: Backend should support multiple users and multiple concurrent clients per user.
5. **Usability**: Interfaces should clearly differentiate check statuses using color coding and provide intuitive interactions for managing checks.
6. **Extensibility**: The system should allow adding future integrations or clients without major architectural changes.

