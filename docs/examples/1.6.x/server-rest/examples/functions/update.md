PUT /v1/functions/{functionId} HTTP/1.1
Host: cloud.appwrite.io
Content-Type: application/json
X-Appwrite-Response-Format: 1.5.0
X-Appwrite-Project: &lt;YOUR_PROJECT_ID&gt;
X-Appwrite-Key: &lt;YOUR_API_KEY&gt;

{
  "name": "<NAME>",
  "runtime": "node-14.5",
  "execute": ["any"],
  "events": [],
  "schedule": ,
  "timeout": 1,
  "enabled": false,
  "logging": false,
  "entrypoint": "<ENTRYPOINT>",
  "commands": "<COMMANDS>",
  "scopes": [],
  "installationId": "<INSTALLATION_ID>",
  "providerRepositoryId": "<PROVIDER_REPOSITORY_ID>",
  "providerBranch": "<PROVIDER_BRANCH>",
  "providerSilentMode": false,
  "providerRootDirectory": "<PROVIDER_ROOT_DIRECTORY>"
}
