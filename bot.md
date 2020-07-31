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
az ad app create --display-name "akshay17thbot" --password "AtLeastSixteenCharacters_0" --available-to-other-tenants
```

Display Name is the name of your bot. Here the name is **akshay17thbot**Password name is ideally something different from
**AtLeastSixteenCharacters_0**

The output from the above commmand will look something like this:

```JSON

{
"acceptMappedClaims": null,
"addIns": [],
"allowGuestsSignIn": null,
"allowPassthroughUsers": null,
// CRITICAL
**"appId": "56007e56-07aa-4e08-aa94-b14c4aab14ea",**
//CRITICAL
"appLogoUrl": null,
"appPermissions": null,
"appRoles": [],
"applicationTemplateId": null,
"availableToOtherTenants": true,
"deletionTimestamp": null,
"displayName": "akshay17thbot",
"errorUrl": null,
"groupMembershipClaims": null,
"homepage": null,
"identifierUris": [],
"informationalUrls": {
"marketing": null,
"privacy": null,
"support": null,
"termsOfService": null
},
"isDeviceOnlyAuthSupported": null,
"keyCredentials": [],
"knownClientApplications": [],
"logo@odata.mediaContentType": "application/json;odata=minimalmetadata; charset=utf-8",
"logo@odata.mediaEditLink": "directoryObjects/47bcb776-807b-4b8c-b341-894365166179/Microsoft.DirectoryServices.Application/logo",
"logoUrl": null,
"logoutUrl": null,
"mainLogo@odata.mediaEditLink": "directoryObjects/47bcb776-807b-4b8c-b341-894365166179/Microsoft.DirectoryServices.Application/mainLogo",
 "oauth2AllowIdTokenImplicitFlow": true,
"oauth2AllowImplicitFlow": false,
"oauth2AllowUrlPathMatching": false,
"oauth2Permissions": [
{
"adminConsentDescription": "Allow the application to access akshay17thbot on behalf of the signed-in user.",
"adminConsentDisplayName": "Access akshay17thbot",
"id": "0e9cdaad-8056-4575-b715-ec229b3d9c38",
"isEnabled": true,
"type": "User",
"userConsentDescription": "Allow the application to access akshay17thbot on your behalf.",
"userConsentDisplayName": "Access akshay17thbot",
"value": "user_impersonation"
}
],
"oauth2RequirePostResponse": false,
"objectId": "47bcb776-807b-4b8c-b341-894365166179",
"objectType": "Application",
"odata.metadata": "https://graph.windows.net/f8c78e84-32f3-4629-a2d9-0bd6ec55b97a/$metadata#directoryObjects/@Element",
"odata.type": "Microsoft.DirectoryServices.Application",
"optionalClaims": null,
"orgRestrictions": [],
"parentalControlSettings": {
"countriesBlockedForMinors": [],
"legalAgeGroupRule": "Allow"
},
"passwordCredentials": [
{
"additionalProperties": null,
"customKeyIdentifier": null,
"endDate": "2021-07-30T09:07:17.640971+00:00",
"keyId": "1db253b5-d408-48c4-aace-cc3755d16092",
"startDate": "2020-07-31T09:07:17.640971+00:00",
"value": null
}
],
"preAuthorizedApplications": null,
"publicClient": null,
"publisherDomain": "agulabrao.onmicrosoft.com",
"recordConsentConditions": null,
"replyUrls": [],
"requiredResourceAccess": [],
"samlMetadataUrl": null,
"signInAudience": "AzureADMultipleOrgs",
"tokenEncryptionKeyId": null,
"wwwHomepage": null
}

```
