from appwrite.client import Client

client = Client()
client.set_endpoint('https://cloud.appwrite.io/v1') # Your API Endpoint
client.set_project('&lt;YOUR_PROJECT_ID&gt;') # Your project ID
client.set_session('') # The user session to authenticate with

functions = Functions(client)

result = functions.get_execution(
    function_id = '<FUNCTION_ID>',
    execution_id = '<EXECUTION_ID>'
)