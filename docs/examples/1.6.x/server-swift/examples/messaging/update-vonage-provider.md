import Appwrite

let client = Client()
    .setEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    .setProject("&lt;YOUR_PROJECT_ID&gt;") // Your project ID
    .setKey("&lt;YOUR_API_KEY&gt;") // Your secret API key

let messaging = Messaging(client)

let provider = try await messaging.updateVonageProvider(
    providerId: "<PROVIDER_ID>",
    name: "<NAME>", // optional
    enabled: false, // optional
    apiKey: "<API_KEY>", // optional
    apiSecret: "<API_SECRET>", // optional
    from: "<FROM>" // optional
)
