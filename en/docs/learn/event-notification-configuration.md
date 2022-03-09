#Event Notification Configurations

To enable the Event Notification feature in WSO2 Open Banking UK Toolkit:

1. Open the `<IS_HOME>/repository/conf/deployment.toml` file.
2. Add the following tags and configure them:

    ??? tip "Click here to see the definitions of the configuration tags..."
         | Configuration | Description |
         | ------------- | ----------- |
         | `token_issuer` | The issuer of the notification JWT. For example, bank. |
         | `number_of_sets_to_return` | The maximum number of events to be returned. This is the default value for `maxEvents`, if the request payload has not defined a value. |
         | `event_creation_handler` | Configure the Event Creation Handler. If you have not implemented a custom handler, configure the default handler by following the sample below. This handler adheres to the IETF Security Event Token (SET) specification. |
         | `event_polling_handler` | Configure the Event Polling Handler. If you have not implemented a custom handler, configure the default handler by following the sample below. This handler adheres to the IETF Security Event Token (SET) specification. |
         | `event_notification_generator` | Configure the Event Notification Generator. If you have not implemented a custom generator, configure the default handler by following the sample below. This generator adheres to the IETF Security Event Token (SET) specification. |
         | `set_sub_claim_included`, `set_txn_claim_included`, `set_toe_claim_included`| Configure the customized optional claims in event notification using these tags. They represent the subject, transaction, and time of event claims respectively. |

      ``` toml
       token_issuer = "www.openbank.com"
       number_of_sets_to_return = 5
       event_creation_handler = "com.wso2.openbanking.accelerator.event.notifications.service.handler.DefaultEventCreationServiceHandler"
       event_polling_handler = "com.wso2.openbanking.accelerator.event.notifications.service.handler.DefaultEventPollingServiceHandler"
       event_notification_generator = "com.wso2.openbanking.accelerator.event.notifications.service.service.DefaultEventNotificationGenerator"
       set_sub_claim_included = true
       set_txn_claim_included = true
       set_toe_claim_included = true
      ```
