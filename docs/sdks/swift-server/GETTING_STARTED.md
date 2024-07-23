## Getting Started

### Add your Swift Platform
To initialize your SDK and start interacting with Appwrite services, you need to add a new Swift platform to your project. To add a new platform, go to your Appwrite console, select your project (or create one if you haven't already), and click the 'Add Platform' button on the project Dashboard.

From the options, choose to add a new **Swift** platform and add your app credentials.

Add your app **Name** and **Bundle ID**. Your `Bundle ID` can be found in Xcode from Project Settings > General > **Bundle Identifier**. By registering a new platform, you are allowing your app to communicate with the Appwrite API.

> If you're using Swift Package manager and not Xcode, your Bundle ID is your library or executable's `name` in your `Package.swift`.

### Init your SDK

Initialize your SDK with your Appwrite server API endpoint and project ID, which can be found in your project settings page.

```swift
import Appwrite

let client = Client()
  .setEndpoint("https://[HOSTNAME_OR_IP]/v1") // Your API Endpoint
  .setProject("5df5acd0d48c2") // Your project ID
  .setKey('919c2d18fb5d4...a2ae413da83346ad2') // Your secret API key
  .setSelfSigned() // Remove in production
```

Before sending any API calls to your new Appwrite instance, make sure your iOS simulators, macOS machines, or other Swift compatible devices have network access to the Appwrite server hostname or IP address.

When trying to connect to Appwrite from a simulator or a mobile device, localhost is the hostname of the device or simulator and not your local Appwrite instance. You should replace localhost with your private IP. You can also use a service like [ngrok](https://ngrok.com/) to proxy the Appwrite API.

### Make Your First Request

Once your SDK object is set, access any of the Appwrite services and choose any request to send. Full documentation for any service method you would like to use can be found in your SDK documentation or in the [API References](https://appwrite.io/docs) section.

```swift
// Register User
let users = Users(client: client)
users.create("email@example.com", "password") { (result: Result<HTTPClient.Response, AppwriteError>) in
    switch result {
    case .failure(let error):
        print(error.message)
    case .success(var response):
        print(response.body!.readString(length: response.body!.readableBytes))
    }
}
```

### Full Example

```swift
import Appwrite

let client = Client()
  .setEndpoint("https://[HOSTNAME_OR_IP]/v1") // Your API Endpoint
  .setProject("5df5acd0d48c2") // Your project ID
  .setKey('919c2d18fb5d4...a2ae413da83346ad2') // Your secret API key
  .setSelfSigned() // Remove in production

let users = Users(client: client)

users.create("email@example.com", "password") { result in
    switch result {
    case .failure(let error):
        print(error.message)
    case .success(var response):
        print(response.body!.readString(length: response.body!.readableBytes))
    }
}
```

### Error Handling

The Appwrite Swift SDK responds with an `AppwriteError` object with a `message` property. You can catch any errors by switching on `result` and catching the `.failure()` case. Below is an example.

```swift
account.create("email@example.com", "password") { result in
    switch result {
    case .failure(let error):
        print(error.message)
    case .success(var response):
        print(response.body!.readString(length: response.body!.readableBytes))
    }
}
```

### Learn more
You can use the following resources to learn more and get help
- 🚀 [Getting Started Tutorial](https://appwrite.io/docs/getting-started-for-swift)
- 📜 [Appwrite Docs](https://appwrite.io/docs)
- 💬 [Discord Community](https://appwrite.io/discord)
- 🚂 [Appwrite Android Playground](https://github.com/appwrite/playground-for-swift)