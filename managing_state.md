# Managing State

- State within a bot follows the same paradigm as web applications.

As it pertains to bots, there are a few layers using state that we need to cover.

Layers of Your Bot

1. Adapter Turn Context,
   - transmits onTurn to your Bot
2. Your Bot
   - create to DialogSet, DialogContext
   - Continue/Begin, to DS,DC
   - transmits SaveAll Changes to BotState
3. DialogSet,Dialog Context
4. BotState Accessor
5. BotStateSet
6. BotState
7. Storage

## Storage Layer

- Memory Storage implements in memory storage for testing purposes.
- Azure Blob Storage

## State management

- state management automates the reading and writing of your bot's state to the underlying storage layer.

- State properties are lumped into scoped "buckets",
  - User State
  - Conversation State
  - Private Conversation State

## Connecting to Multiple Databases

State property accessors are used to *actually* read or write one of your state properties, and provide *get,set, and delete* methods for accessing your state properties from within a turn.

