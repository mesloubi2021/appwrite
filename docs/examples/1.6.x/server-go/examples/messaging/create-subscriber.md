package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/messaging"
)

func main() {
    client := client.NewClient()

    client.SetEndpoint("https://cloud.appwrite.io/v1") // Your API Endpoint
    client.SetProject("") // Your project ID
    client.SetJWT("") // Your secret JSON Web Token

    service := messaging.NewMessaging(client)
    response, error := service.CreateSubscriber(
        "<TOPIC_ID>",
        "<SUBSCRIBER_ID>",
        "<TARGET_ID>",
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}