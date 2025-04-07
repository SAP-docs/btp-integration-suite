<!-- loio58e3729f3075488099c2bf1b594530ea -->

# Webhook Subscriptions

A webhook subscription is a configuration on the message client that facilitates message delivery from a queue to REST-based consumers.

A webhook is a method used by web applications to communicate with each other automatically and in real-time. When an event happens on a web application, like a button click, a webhook sends a message which prompts an action on a different web app. In this case, the application sending the message is known as the webhook provider and the responding app is known as the webhook receiver.

You use webhooks whenever you want an event on one application to automatically trigger an event in other application. As there is no polling, webhooks consume lesser resources. As soon as a message reaches the queue, a webhook triggers a near real time delivery of the message. On contrary, in an API paradigm, a receiver application must manually ask the provider application for information, which in turn, consumes more resources.

A **webhook subscription** in the Event Mesh capability of SAP Integration Suite creates a connection to your webhook and associates the same to a queue. When messages reach a queue, a webhook subscription lets you automatically send those messages to your webhook in near real time.

**Related Information**  


[Create a Webhook Subscription](50-Development/create-a-webhook-subscription-e120b8b.md "Understand how to create webhook subscriptions.")

