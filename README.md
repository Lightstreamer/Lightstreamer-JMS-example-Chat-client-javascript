# Lightstreamer JMS Extender - Basic Chat Demo - HTML Client

<!-- START DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

This project includes a simple JMS-based chat.

## Details

The JMS Chat Demo implements an extremely simple chat application, where all the users connected to the page can exchange messages.

Launch multiple instances of the demo, possibly on different machines, to appreciate the message broadcast capability.

This page uses the <b>Lightstreamer JMS Extender JavaScript Client API</b> to handle communications with JMS Extender.

Check out the sources for further explanations.

![screenshot](screen-large.png)

<!-- END DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

## Install

Before you can run the demo of this project, some dependencies need to be solved:

* Configure the JMS broker as described in the next section.
* Configure and launch a Lightstreamer JMS Extender instance. Please refer to Lightstreamer web site [download page](http://download.lightstreamer.com/) to find the JMS Extender download package.
* jQuery is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.
* As the latest version of the Lightstreamer JMS Extender JavaScript library is always available through [unpkg](https://unpkg.com/lightstreamer-jms-web-client), it is hot-linked in the html page.

## JMS Broker

This demo needs a JMS infrastructure to run.
You can choose a JMS broker to be used for this example.
You should have already configured the JMS connector for your preferred broker by following the JMS Extender documentation. Also have a look at `<JMS_EXTENDER_HOME>/GETTING_STARTED.TXT` for how to add the third-party client library jars.

Now it is necessary to create the topic to be used by this demo.
We will show 3 examples using **Apache ActiveMQ**, **Apache ActiveMQ Artemis**, and **TIBCO EMS**. If you already know how to create a topic, go create a "chatTopic" topic and skip this part.

#### Apache ActiveMQ

There's no need to create topics or queues, because [ActiveMQ](http://activemq.apache.org/components/classic/) supports dynamic configuration of destinations.


#### Apache ActiveMQ Artemis

There's no need to create topics or queues, because [ActiveMQ Artemis](http://activemq.apache.org/components/artemis/) supports dynamic configuration of destinations.


#### TIBCO EMS

Open the `topics.conf` file located under [EMSHome](http://www.tibco.com/products/automation/messaging/enterprise-messaging/enterprise-message-service/default.jsp)`/bin/` and append to it *chatTopic*.


## Configure

Now, you need to configure the `index.html` of this example by specifying the name of the JMS connector you are going to use.
To set the JMS connector name (and possibly the JMS Extender address), modify the following line (as you can see `ActiveMQ` is pre-configured):

```js
  jms.TopicConnectionFactory.createTopicConnection("http://localhost:8080/", "ActiveMQ", null, null, {
```

## Launch

To access the demo from a web browser, copy it somewhere under your webserver root directory. You can also add it to the JMS Extender internal web server pages under `<JMS_EXTENDER_HOME>/pages` directory by copying it there with a folder name such as `ChatDemo_JMS`. Subsequently you may access it as: [http://_your_jms_extender_http_address_/ChatDemo_JMS/](http://_your_jms_extender_http_address_/ChatDemo_JMS/).
Depending on the browser in use, and on the security settings, you might also be able to launch the index.html file directly from the file system.

## See Also

### Related Projects

* [Lightstreamer JMS Extender - Basic Stock-List Demo - HTML Client](https://github.com/Lightstreamer/Lightstreamer-JMS-example-StockList-client-javascript)
* [Lightstreamer JMS Extender - Basic Portfolio Demo - HTML Client](https://github.com/Lightstreamer/Lightstreamer-JMS-example-Portfolio-client-javascript)
* [Lightstreamer - Basic Chat Demo - HTML Client](https://github.com/Lightstreamer/Lightstreamer-example-chat-client-javascript)

## Lightstreamer Compatibility Notes

* Compatible with Lightstreamer JMS Extender JavaScript Client library version 2.0.0 or newer.
* Compatible with Lightstreamer JMS Extender since version 2.0.0 or newer.
