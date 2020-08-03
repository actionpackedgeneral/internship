# intro to adaptive dialogs

- new event-based addition to the Dialogs library that enables you to easily layer conversation management techniques.

## Adaptive Dialogs

- Dynamically update conversation flow based on context and events
- Modeling interruptions, cancellation, and execution planning semantics are a lot easier
- input recognition and rule-based event handling
- combine conversation model and output generation into one ohesive, self-contained unit
- support extensibility points for recognition

## Anatomy of an adaptive dialog

### Triggers

All adaptive dialgos contain a list of one or more event handlers called _triggers_.
Triggers are what enable you to catch and respond to events.

### Actions

- define the conversation flow when a specific event is captured via a Trigger

### Inputs

- Perform exisistential checks, to avoid repetitive info requests
- save the input to the specified property if it matches the type of entity expected.
- Accept constraints - min,max

### Recognizers

- enable your bot to extract meaningful pieces of information from user's input.

### Generator

- tie a specific language genertion system to an adaptive dialog.

### Memory scopes and managing state

- Provide a way to access and manage memory.

### Declarative assists
- enable you to define your dialog as a class by creating a new Adaptive Dialog object and defining your triggers and actions in the same cllasses file

## TYing it all together

### The adaptive dialog runtime behavior
