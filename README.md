# twilio
sample WebDev code for twilio

For our application we created a web service so if we needed to make any changes to the integration with Twilio we could do this quickly and not require a windows application upgraded.

The web service is called with the local customer's Twilio account info and SMS request details.  This allows the customer to have multiple phone numbers and configurations.

The web service processes the request with Twilio and response to the window app.

The replies are handled by the same web service.  The web hook is configured on each Twilio account.  The web service gets the SMS reply and post it to a RabbitMQ server for the customer's unique topic/channel.  We have a local windows service listening and handles saving the reply and creating user notifications.
