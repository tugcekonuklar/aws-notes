# SQS

* SQS is actually the first ever AWS service that was publicly available
* SQS is a distributed message queuing system, and it allows us to decouple the components of an application so that
  they are independent. And if 1 of our application servers crashes, before they complete a task, you're not going to
  lose the task because it will reappear in the queue.
* it's basically a message queue service
* it enables web service applications to quickly and reliably queue messages, that one component in the application
  generates, for another component to consume
* if you get a massive surge of messages in the queue, this can trigger the auto scaling group to launch additional
  instances, to cope with the increased number of messages or jobs to complete.
* And if you have a reduced number of messages in the queue, auto scaling can also reduce the number of EC2 instances
  needed to process the messages
* if they are asking you for a pull-based service, then they're usually talking about SQS.
    * However, if they are asking you about a push-based system, then you'll need something like a Simple Notification
      Service or SNS
* the great thing about SQS is that if any of our application servers crashed, any messages, which are partially
  processed,
  will not be deleted and will end up back in the queue.
    * And this is because when a message is first picked up by our application server, it's going to be marked as
      invisible so that no other application server can start processing that message. And this is called the
      **visibility timeout**, and this is the amount of time that the application server gets to process the message,
      and as soon as that window has expired,
    * if the message has not been completely processed, then it will appear in the queue again and another application
      server will pick up that message and begin processing it.
* by using SQS, you're removing dependencies between individual components in your application.
* By using SQS, you can **decouple** your application components. So you can decouple the components of an application,
  allowing them to run independently and easing message management between components
* Any component of a distributed application can store messages in the queue and messages can contain up to 256
  kilobytes of text in any format.
    * For example, XML, JSON, or plain text format and any component can later retrieve the messages, programmatically
      using the Amazon SQS API
* SQS effectively act as a buffer between the components of your application.
* It guarantees that the messages will be processed at least once. The retention period of messages is up to 14 days.
* So messages can be kept in the queue from between one minute to 14 days. So the minimum is for one minute and the
  maximum is 14 days, but the default retention period is 4 days.