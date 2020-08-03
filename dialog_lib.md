# Dialogs Library

- _Dialogs_ are structures taht act like functions in your bot's programs.
  - _Waterfalls_ and _prompt_ dialogs combine multiple steps, allowing your bot to follow a predefined sequence and pass information from 1 step to another.
  - _Component dialogs_ allow you to encapsulate and reuse sets of dialogs.
  - Adaptive, action, and input dialogs are an event-driven desgin for building sophisticated conversations.

## Adaptive Dialogs

    - Event driven model for conversations

## Dialogs and their pieces

- _dialog set_ - collection of dialogs
- _dialog context_ contains information pertaining to a dialog set, and is used within the framework to interact with those dialogs.
- when a dialog ends, it can return a _dialog result_ with some resulting information from the dialog.
- A _dialog manager_ automates tasks.

## Dialog State

Dialog based bots can hold a dialog set collection as a member vairable in its bot implementation.

## Prompts

- provide an easy way to ask the user for info and evaluate response. Prompts are a 2-step dialog, asking for input, and input validation / re-prompt
- _prompt options_ are given when the prompt is called, which is where you can specifit the text to prompt with.
- Aditionally, you can choose to add some custom validation for your prompt when you create it.

## Branch a conversation

- _begin dialog_ method creates a child and pushes that dialog onto the top of the stack.
- _end dialog_ method pops the top dialog off the stack.
