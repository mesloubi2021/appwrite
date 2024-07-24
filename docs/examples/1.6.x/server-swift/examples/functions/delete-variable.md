import Appwrite

let client = Client()
    .setEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    .setProject("&lt;YOUR_PROJECT_ID&gt;") // Your project ID
    .setKey("&lt;YOUR_API_KEY&gt;") // Your secret API key

let functions = Functions(client)

let result = try await functions.deleteVariable(
    functionId: "<FUNCTION_ID>",
    variableId: "<VARIABLE_ID>"
)
