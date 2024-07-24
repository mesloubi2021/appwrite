import io.appwrite.Client
import io.appwrite.coroutines.CoroutineCallback
import io.appwrite.services.Users
import io.appwrite.enums.AuthenticatorType

val client = Client()
    .setEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    .setProject("&lt;YOUR_PROJECT_ID&gt;") // Your project ID
    .setKey("&lt;YOUR_API_KEY&gt;") // Your secret API key

val users = Users(client)

val response = users.deleteMfaAuthenticator(
    userId = "<USER_ID>",
    type =  AuthenticatorType.TOTP
)