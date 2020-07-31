# Making a Microsft Chatbot

[tutorial]https://docs.microsoft.com/en-in/microsoftteams/platform/bots/how-to/create-a-bot-for-teams

[framework]https://docs.microsoft.com/en-us/azure/bot-service/javascript/bot-builder-javascript-quickstart?view=azure-bot-service-4.0

[AzureBotService]https://docs.microsoft.com/en-us/azure/bot-service/abs-quickstart?view=azure-bot-service-4.0

## Making a Chatbot in Administrator Command Prompt Windows

1. Make a Directory for your bots
2. **yo botbuilder**
3. Fill out form
4. go into directory of bot, **npm start**
5. Open Microsft Bot Emulator

## Connectecting the NGROK and Microsoft Teams

The messaging endpoint should be https://localhost:3978/api/messages.

## Deploying Your Chatbot

```
yo botbuilder
az login
az account set --subscription "Azure Subscription 1"
```

```
az ad app create --display-name "displayName" --password "AtLeastSixteenCharacters_0" --available-to-other-tenants
```
