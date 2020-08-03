# Middleware

## Uses for middleware

- provides you with additional opportunites to interact with your users' conversation flow both before and after each turn of the conversation is processed.

## The bot middleware pipeline

- 1st middleware object's turn handler executes code before calling next.
  - 2nd middleware object's turn handler executes code before calling next
    - the bot's turn handler executes and returns
  - 2nd middleware object's turn handler executes any remaining code before returning
- 1st mw object's turn handler executes any remaining code before returning.

## Order of middleware

The first things in your middleware pipeline should likely be those that take care of the lowest-level tasks that are used every time.

- Logging
- Exception Handling
- Translation
  Last things should be bot-specific middleware

## Short circuiting

- You can use middleware to skip logic.

## Response event handlers

- called when the associated response happens on the current context object.

## Handling state in middleware
- save state is to call the save changes method at the end of the turn handler.