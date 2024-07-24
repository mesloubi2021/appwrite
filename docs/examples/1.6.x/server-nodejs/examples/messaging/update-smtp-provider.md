const sdk = require('node-appwrite');

const client = new sdk.Client()
    .setEndpoint('https://cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('&lt;YOUR_PROJECT_ID&gt;') // Your project ID
    .setKey('&lt;YOUR_API_KEY&gt;'); // Your secret API key

const messaging = new sdk.Messaging(client);

const result = await messaging.updateSmtpProvider(
    '<PROVIDER_ID>', // providerId
    '<NAME>', // name (optional)
    '<HOST>', // host (optional)
    1, // port (optional)
    '<USERNAME>', // username (optional)
    '<PASSWORD>', // password (optional)
    sdk.SmtpEncryption.None, // encryption (optional)
    false, // autoTLS (optional)
    '<MAILER>', // mailer (optional)
    '<FROM_NAME>', // fromName (optional)
    'email@example.com', // fromEmail (optional)
    '<REPLY_TO_NAME>', // replyToName (optional)
    '<REPLY_TO_EMAIL>', // replyToEmail (optional)
    false // enabled (optional)
);