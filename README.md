# Lightstreamer JMS Gateway - Basic Chat Demo - HTML Client #

This project includes a front-end example based on the Chat Demo for Lightstreamer JMS gateway.

The JMS Chat Demo implements an extremely simple chat application, where all the users connected to the page can exchange messages.<br>

Launch multiple instances of the demo, possibly on different machines, to appreciate the message broadcast capability.<br>

This page uses the <b>JMS JS Client API for Lightstreamer</b> on top of <b>JavaScript Client API for Lightstreamer</b> to handle the communications with Lightstreamer Server.<br>
Check out the sources for further explanations.

# Deploy #

Before you can run the demo of this project some dependencies need to be solved:

-  Get the lightstreamer.js file from the [latest Lightstreamer distribution](http://www.lightstreamer.com/download) and put it in the root folder of this project.
-  Get the require.js file form [requirejs.org](http://requirejs.org/docs/download.html) and put it in the root folder of this project.
-  Get the lightstreamer-jms.js file from the [Lightstreamer JMS Gateway preview](http://www.lightstreamer.com/download) (please click the "From the Labs" section) and put it in the root folder of this project.

Now, you need to configure the index.html of this example by specifying the name of the data adapter you are going to use. By default the demo will look for the <b>HornetQ</b> data adapter, please refer to the related [Service project](https://github.com/Weswit/Lightstreamer-JMS-example-Chat-service-java) for more details on the choice of a JMS broker to be used.
To set the data adapter name and the connection name look where the connection is created:

```js
  ConnectionFactory.createConnection(function(conn) {
    ...
    ...
    ...
  }, "http://localhost:8080/", "JMS", "HornetQ", // Change data adapter here
    ...
    ...
    ...
  });
```

To access the demo from a web browser copy it somewhere under your root webserver directory. You can also add it to the standard Lightstreamer demo pages under "LightstreamerHome/pages/demos" directory and access it as: <i>http://_your_lightstreamer_http_address_/demos/ChatDemo_JMS/</i>.

## Running the Demo ##

The JMS Gateway Chat Demo requires the following components to be
configured and running in order to function properly:

* a JMS broker;
* the Chat Demo Service;
* a Lightstreamer instance running a properly configured JMS Gateway;
* this Client.

Please refer to Lightstreamer web site [download page](http://www.lightstreamer.com/download) to find Lightstreamer and JMS Gateway download packages. See below for the Service part of this Demo and other Demos for the JMS Gateway.

# See Also #

## Lightstreamer back-end Service needed by this demo client ##

* [Lightstreamer JMS Gateway - Basic Chat Demo - Java SE (JMS) Service](https://github.com/Weswit/Lightstreamer-JMS-example-Chat-service-java)

## Similar demo clients that may interest you ##

* [Lightstreamer JMS Gateway - Basic Stock-List Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-StockList-client-javascript)
* [Lightstreamer JMS Gateway - Basic Portfolio Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-Portfolio-client-javascript)
* [Lightstreamer - Basic Chat Demo - HTML Client](https://github.com/Weswit/Lightstreamer-example-chat-client-javascript)

# Lightstreamer Compatibility Notes #

- Compatible with Lightstreamer JavaScript Client library version 6.0 or newer.
- Compatible with Lightstreamer JMS Gateway Adapter since version 1.0 or newer.
