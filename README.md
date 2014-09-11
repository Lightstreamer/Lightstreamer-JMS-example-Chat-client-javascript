# Lightstreamer JMS Gateway - Basic Chat Demo - HTML Client

<!-- START DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

This project includes a front-end example based on the Chat Demo for Lightstreamer JMS gateway.

## Details

The JMS Chat Demo implements an extremely simple chat application, where all the users connected to the page can exchange messages.<br>

Launch multiple instances of the demo, possibly on different machines, to appreciate the message broadcast capability.<br>
This page uses the <b>JMS JS Client API for Lightstreamer</b> on top of [JavaScript Client API for Lightstreamer](http://www.lightstreamer.com/docs/client_javascript_uni_api/index.html) to handle the communications with Lightstreamer Server.<br>

Check out the sources for further explanations.

![screenshot](screen-large.png)

<!-- END DESCRIPTION lightstreamer-jms-example-chat-client-javascript -->

## Install

Before you can run the demo of this project some dependencies need to be solved:

* Note that, as prerequisite, the [Lightstreamer JMS Gateway - Basic Chat Demo - Java (JMS) Service](https://github.com/Weswit/Lightstreamer-JMS-example-Chat-service-java) has to be deployed on your local Lightstreamer Server instance (running a properly configured JMS Gateway). Please check out that project and follow the installation instructions provided with it.
* Launch Lightstreamer Server.
* Get the `lightstreamer-jms.js` file from the [Lightstreamer JMS Gateway](http://download.lightstreamer.com/#jms) and put it in the root folder of this project.
* Lightstreamer JS client is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.
* RequireJS is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.
* jQuery is currently hot-linked in the html page: you may want to replace it with a local version and/or to upgrade its version.

Now, you need to configure the `index.html` of this example by specifying the name of the data adapter you are going to use. By default the demo will look for the <b>HornetQ</b> data adapter, please refer to the related [Service project](https://github.com/Weswit/Lightstreamer-JMS-example-Chat-service-java) for more details on the choice of a JMS broker to be used.
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

To access the demo from a web browser copy it somewhere under your root webserver directory. You can also add it to the standard Lightstreamer demo pages under `LightstreamerHome/pages/demos` directory and access it as: <i>http://_your_lightstreamer_http_address_/demos/ChatDemo_JMS/</i>.

## See Also

### Lightstreamer Services Needed by This Demo Client

<!-- START RELATED_ENTRIES -->
* [Lightstreamer JMS Gateway - Basic Chat Demo - Java (JMS) Service](https://github.com/Weswit/Lightstreamer-JMS-example-Chat-service-java)

<!-- END RELATED_ENTRIES -->

### Related Projects

* [Lightstreamer JMS Gateway - Basic Stock-List Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-StockList-client-javascript)
* [Lightstreamer JMS Gateway - Basic Portfolio Demo - HTML Client](https://github.com/Weswit/Lightstreamer-JMS-example-Portfolio-client-javascript)
* [Lightstreamer - Basic Chat Demo - HTML Client](https://github.com/Weswit/Lightstreamer-example-chat-client-javascript)

## Lightstreamer Compatibility Notes

* Compatible with Lightstreamer JavaScript Client library version 6.1 or newer.
* Compatible with Lightstreamer JMS Gateway Adapter since version 1.0 or newer.
