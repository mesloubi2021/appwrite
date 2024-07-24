import { Client, Users, MessagingProviderType } from "https://deno.land/x/appwrite/mod.ts";

const client = new Client()
    .setEndpoint('https://cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('&lt;YOUR_PROJECT_ID&gt;') // Your project ID
    .setKey('&lt;YOUR_API_KEY&gt;'); // Your secret API key

const users = new Users(client);

const response = await users.createTarget(
    '<USER_ID>', // userId
    '<TARGET_ID>', // targetId
    MessagingProviderType.Email, // providerType
    '<IDENTIFIER>', // identifier
    '<PROVIDER_ID>', // providerId (optional)
    '<NAME>' // name (optional)
);