from appwrite.client import Client

client = Client()
client.set_endpoint('https://cloud.appwrite.io/v1') # Your API Endpoint
client.set_project('&lt;YOUR_PROJECT_ID&gt;') # Your project ID
client.set_session('') # The user session to authenticate with

storage = Storage(client)

result = storage.get_file_view(
    bucket_id = '<BUCKET_ID>',
    file_id = '<FILE_ID>'
)