require 'appwrite'

include Appwrite

client = Client.new
    .set_endpoint('https://cloud.appwrite.io/v1') # Your API Endpoint
    .set_project('&lt;YOUR_PROJECT_ID&gt;') # Your project ID
    .set_key('&lt;YOUR_API_KEY&gt;') # Your secret API key

users = Users.new(client)

result = users.create(
    user_id: '<USER_ID>',
    email: 'email@example.com', # optional
    phone: '+12065550100', # optional
    password: '', # optional
    name: '<NAME>' # optional
)