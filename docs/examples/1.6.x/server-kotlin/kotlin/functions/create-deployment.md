import io.appwrite.Client
import io.appwrite.coroutines.CoroutineCallback
import io.appwrite.models.InputFile
import io.appwrite.services.Functions

val client = Client()
    .setEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    .setProject("&lt;YOUR_PROJECT_ID&gt;") // Your project ID
    .setKey("&lt;YOUR_API_KEY&gt;") // Your secret API key

val functions = Functions(client)

val response = functions.createDeployment(
    functionId = "<FUNCTION_ID>",
    code = InputFile.fromPath("file.png"),
    activate = false,
    entrypoint = "<ENTRYPOINT>", // optional
    commands = "<COMMANDS>" // optional
)