# Deploying a Conversational Chatbot in Teams with Azure CLI

## Creating a chatbot

### Prerequisites:

1. Microsoft Teams account and App
2. NodeJS
3. ngrok

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
az ad app create --display-name "akshay17thbot" --password "AtLeastSixteenCharacters_0" --available-to-other-tenants
```

Display Name is the name of your bot. Here the name is **akshay17thbot**Password name is ideally something different from
**AtLeastSixteenCharacters_0** Save the password for future steps

The output from the above commmand will look something like this:

```JSON

{
"acceptMappedClaims": null,
"addIns": [],
"allowGuestsSignIn": null,
"allowPassthroughUsers": null,
// CRITICAL
**"appId": "56007e56-07aa-4e08-aa94-b14c4aab14ea",**
//CRITICAL nothing else after this matters
```

Save this **app ID** for future reference.

For this next step, we create the bot application service. For the name of resource group, I use **akshay17thrg**.

For the **appID**, we use the appID that we _generated_ earlier.

For the **app secret**, we use the password that we _provided_ ealier.

- **Bot ID**: a name for the bot channels registration resource to create, you can use the _app id_ if you want, but it must be globally unique

The reason that this does not work is because there is a current bug regarding this [issue](https://github.com/Azure/azure-rest-api-specs/issues/8093).

To work around this, we create an app service plan on the GUI in azure portal.

Naviate to Azure Portal Home

1) Create a Resource
2) Type in "App Service Plan" in **Search the Marketplace**
3) Create
4) 



This is the output we get after running the above command.

```
az deployment group create --resource-group "akshay17thbot" --template-file "C:\Users\agul\myJsBots\akshay-17-thbot\deploymentTemplates\template-with-preexisting-rg.json" --parameters appId="56007e56-07aa-4e08-aa94-b14c4aab14ea" appSecret="AtLeastSixteenCharacters_0" botId="akshay17thbot" newWebAppName="akshay17thbot" newAppServicePlanName="akshay17thbot" appServicePlanLocation="West US" --name "akshay17thbot"
```

```
C:\Users\agul\myJsBots>az deployment group create --resource-group "akshay17thbot" --template-file "C:\Users\agul\myJsBots\akshay-17-thbot\deploymentTemplates\template-with-preexisting-rg.json" --parameters appId="56007e56-07aa-4e08-aa94-b14c4aab14ea" appSecret="AtLeastSixteenCharacters_0" botId="akshay17thbot" newWebAppName="akshay17thbot" newAppServicePlanName="akshay17thbot" appServicePlanLocation="Central US" --name "akshay17thbot"
```

```JSON
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Resources/deployments/akshay17thbot",
"location": null,
"name": "akshay17thbot",
"properties": {
"correlationId": "a97a81d1-dbb6-45e6-b077-e8d26ad596d1",
"debugSetting": null,
"dependencies": [
{
"dependsOn": [
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Web/serverfarms/akshay17thbot",
"resourceGroup": "akshay17thbot",
"resourceName": "akshay17thbot",
"resourceType": "Microsoft.Web/serverfarms"
}
],
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Web/sites/akshay17thbot",
 "resourceGroup": "akshay17thbot",
"resourceName": "akshay17thbot",
"resourceType": "Microsoft.Web/sites"
},
{
"dependsOn": [
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Web/sites/akshay17thbot",
"resourceGroup": "akshay17thbot",
"resourceName": "akshay17thbot",
"resourceType": "Microsoft.Web/sites"
}
],
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.BotService/botServices/akshay17thbot",
"resourceGroup": "akshay17thbot",
"resourceName": "akshay17thbot",
"resourceType": "Microsoft.BotService/botServices"
}
],
"duration": "PT26.1548099S",
"mode": "Incremental",
"onErrorDeployment": null,
"outputResources": [
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.BotService/botServices/akshay17thbot",
"resourceGroup": "akshay17thbot"
},
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Web/serverfarms/akshay17thbot",
"resourceGroup": "akshay17thbot"
},
{
"id": "/subscriptions/f148aa66-6ae9-4cdb-9de6-cbbd2422d29c/resourceGroups/akshay17thbot/providers/Microsoft.Web/sites/akshay17thbot",
 "resourceGroup": "akshay17thbot"
}
],
"outputs": null,
"parameters": {
"appId": {
"type": "String",
"value": "56007e56-07aa-4e08-aa94-b14c4aab14ea"
},
"appSecret": {
"type": "String",
"value": "AtLeastSixteenCharacters_0"
},
"appServicePlanLocation": {
"type": "String",
"value": "Central US"
},
"botId": {
"type": "String",
"value": "akshay17thbot"
},
"botSku": {
"type": "String",
"value": "F0"
},
"existingAppServicePlan": {
"type": "String",
"value": ""
},
"newAppServicePlanName": {
"type": "String",
"value": "akshay17thbot"
},
"newAppServicePlanSku": {
"type": "Object",
"value": {
"capacity": 1,
"family": "S",
"name": "S1",
"size": "S1",
"tier": "Standard"
}
},
"newWebAppName": {
"type": "String",
"value": "akshay17thbot"
}
},
"parametersLink": null,
"providers": [
{
"id": null,
"namespace": "Microsoft.Web",
"registrationPolicy": null,
"registrationState": null,
"resourceTypes": [
{
"aliases": null,
"apiVersions": null,
"capabilities": null,
"locations": [
"centralus"
],
"properties": null,
"resourceType": "serverfarms"
},
{
"aliases": null,
"apiVersions": null,
"capabilities": null,
"locations": [
"centralus"
],
"properties": null,
"resourceType": "sites"
}
]
},
{
"id": null,
"namespace": "Microsoft.BotService",
"registrationPolicy": null,
"registrationState": null,
"resourceTypes": [
{
"aliases": null,
"apiVersions": null,
"capabilities": null,
"locations": [
"global"
],
"properties": null,
"resourceType": "botServices"
}
]
}
],
"provisioningState": "Succeeded",
"template": null,
"templateHash": "554788647258636492",
"templateLink": null,
"timestamp": "2020-07-31T22:36:48.503933+00:00"
},
"resourceGroup": "akshay17thbot",
"type": "Microsoft.Resources/deployments"
}

```

CD into the project name and run the following commmand

```
az bot prepare-deploy --code-dir "." --lang Javascript
```

If it returns true, we have good news.

Add the appID and password that you set into the .env file.
The zipping must be done manually go into the folder and select all files and compress it into a zip.

az webapp deployment source config-zip --resource-group "akshay17thbot" --name "akshay17thbot" --src "C:\Users\agul\myJsBots\akshay-17-thbot\index.zip"

The output is arbitrary, run it again if you get errors.

start ngrok, and do npm start,change the bot endpoint,
Try running the webapp deployment again if it fails the first time.
Test in webChat.
Turn on the Microsoft channels switch.
Then go on the app studio, manifest editor > create an app, use a new appId for the app than the bot, fill in everything with an \* (arbittrary names), then go to set up a bot, enter the app Id that we have been using this entire team, set the scope to personal and team. Then you can download the manifest package. Make sure that you check the manifest package, as there are non deterministic bugs with it.
