# How bots work

- Every interatction between the user and the bot generates an activity.
- The Bot Framework Service, which is a component of the Azure Bot Service, sends information between the user's bot-connected app and the bot.

* Conversation updates may be sent when party joins the conversation.
* Message activity carries conversation information between the parties.

## POST Get

### GET

- GET is used to request data from a specified resource. GET is one of the most common HTTP methods
  - can be cached
  - remain in browser history
  - can be bookmarked
  - shouldn't be used when dealing with sensitive data
  - length restrictions
  - only used to request data, not modify

### POST

- POST is used to send data to a server to create/update a resource.
  - not cached
  - do not remain in browser history
  - cannot be bookmarked
  - no restrictions on data length

### HTTP Details

Activities arrive at the bot with an HTTP POST request. Te bot responds to the inbound POST request with a 200 HTTP status code. Activities send from the bot to the channel are sent on a separate HTTP POST to the Bot Framework Service. This, in turn is acknowledged with a 200 HTTP status code.

### Defining a turn

A _turn_ consists of the user's incoming activity to the bot and any activity the bot sends back to the user as an immediate response.

The _turn context_ object provides information about the activity such as the sender and receiver, the channel, and other data needed to process the acitivity.

### The Activity Processing Stack

The adapter, an integrated component of the SDK, is the core of the SDK runtime.

4 Layers:

1. Channel Endpoint
2. Bot Framework Service
3. Adapter TurnContext
4. Your bot

The _adapter_, an integrated component of the SDK, is the core of the SDK runtime. JSON gets deserialized to create the activity object.

The turn context provides the mechanism for the bot to send outbound activities, most often in response to an inbound activity. To achieve this, the turn context provides _send, update, and delete activity_ response methods. Each response runs in an asynchronous process. - Make sure you **await** activity calls so the primary thread will wait on the generated activity before finsihing its processing and disposing of the turn context.

### Javascript Activity Handler

- Uses an event emitter and listener pattern.
- For example, use the onMessage method to register an event listener for message activities.

- Your bot login for handling and responding to messages will go in the onMessage listeners. Likewise, your logic for handling members being added to the conversation will go in your **onMembersAdded** listerners.

- Make sure to save state before the turn ends, You can do so by overriding the activity handler **run** method and saving state after the parent's **run** method competes.

- As with all activity handlers, make sure you call **next()** to ensure the rest of the process wraps up.

### Middleware

- middleware is software that provides common services and capabilities to applications outside of what's offered by the operating system.

- like any other messaging middleware, comprising a linear set of components that are executed in order, giving each a chance to operate on the activity.

- the final stage of the middleware pipeline is a callback to the turn handler on the bot class the application has registered with the adapter's process activity method.

- The turn handler on **onTurn** in JavaScript. 

### Bot structure

The Yeoman generator creates a type of restify web application. If you look at the restify quickstart in their docs, you'll see an app similar to the generated index.js file. 

- **package.json** specifies dependencies and their associated versions for your bot. 

- **.env** The file specifies configuration information for your bot such as the port number, app ID, and password.

### Bot logic

The main bot logic is defined in the bot code, derives from ActivityHandler. 
