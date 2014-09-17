# Lightstreamer JMS Gateway - Basic Chat Demo - HTML Client

<!-- START DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

This project includes a simple JMS-based chat.

## Details

The JMS Chat Demo implements an extremely simple chat application, where all the users connected to the page can exchange messages.

Launch multiple instances of the demo, possibly on different machines, to appreciate the message broadcast capability.

This page uses the <b>JMS JS Client API for Lightstreamer</b> on top of [JavaScript Client API for Lightstreamer](http://www.lightstreamer.com/docs/client_javascript_uni_api/index.html) to handle the communications with Lightstreamer Server.

Check out the sources for further explanations.

![screenshot](screen-large.png)

<!-- END DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

## Install

Before you can run the demo of this project some dependencies need to be solved:

* Configure the JMS broker as described in the next section.
* Configure and launch a Lightstreamer server instance running a properly configured JMS Gateway. Please refer to Lightstreamer web site [download page](http://download.lightstreamer.com/) to find *Lightstreamer server* and *JMS Gateway* download packages.
* Get the `lightstreamer-jms.js` file from the [Lightstreamer JMS Gateway](http://download.lightstreamer.com/#jms) and put it in the root folder of this project.
* Lightstreamer JS client is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.
* RequireJS is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.
* jQuery is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.

## JMS Broker

This demo needs a JMS infrastructure to run. You can choose a JMS broker to be used for this example. You should have already configured the gateway adapter for you preferred
broker by following the gateway adapter documentation. Now it is necessary to create the topic to be used by this demo. 
We will show 4 examples using **HornetQ (AKA JBoss Messaging)**, **TIBCO EMS**, **Apache ActiveMQ** and **JBossMQ**. If you already know how to create a topic, go create a "chatTopic" topic and skip this part

### HornetQ (AKA JBoss Messaging)

Open the `hornetq-jms.xml` located under [HornetQHome](http://www.jboss.org/hornetq)`/config/stand-alone/non-clustered` and add the following node:

```xml

   <topic name="chatTopic">
      <entry name="chatTopic"/>
   </topic>

```

## TIBCO EMS

Open the `topics.conf` located under [EMSHome](http://www.tibco.com/products/automation/enterprise-messaging/enterprise-message-service)`/bin/` and append to it the line "chatTopic".

### Apache ActiveMQ

There's no need to create the topic since [ActiveMQ](http://activemq.apache.org/) supports dynamic configuration of destinations.

### JBossMQ

Open the `jbossmq-destinations-service.xml` located under [JBossHome](http://www.jboss.org/products/amq)`/server/default/deploy/jms/` and add the mbean node as shown below:

```xml

  <mbean code="org.jboss.mq.server.jmx.Topic"
    name="jboss.mq.destination:service=Topic,name=chatTopic">
    <depends optional-attribute-name="DestinationManager">jboss.mq:service=DestinationManager</depends>
  </mbean>

```

## Configure

Now, you need to configure the `index.html` of this example by specifying the name of the data adapter you are going to use.
To set the data adapter name (and possibly the Lightstreamer server address) modify the following line (as you can see HornetQ is pre-configured):

```js
  TopicConnectionFactory.createTopicConnection("http://localhost:8080/", "JMS", "HornetQ", null, null, {
```

## Launch

To access the demo from a web browser copy it somewhere under your webserver root directory. You can also deploy it into the Lightstreamer internal webserver. 
Depending on the browser in use and on the security settings you might also be able to launch the index.html file directly from the file system.

## See Also

### Related Projects

* [Lightstreamer JMS Gateway - Basic Stock-List Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-StockList-client-javascript)
* [Lightstreamer JMS Gateway - Basic Portfolio Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-Portfolio-client-javascript)
* [Lightstreamer - Basic Chat Demo - HTML Client](https://github.com/Weswit/Lightstreamer-example-chat-client-javascript)

## Lightstreamer Compatibility Notes

* Compatible with Lightstreamer JavaScript Client library version 6.1 or newer.
* Compatible with Lightstreamer JMS Gateway Adapter since version 1.1 or newer.
