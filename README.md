# jionic
Java implementation of simple server side task for the ionic framework.
First implementation is ionic push.

## Installation

Just add the following to your pom.xml :

```xml
<dependency>
	<groupId>dk.braintrust.ionic</groupId>
	<artifactId>push</artifactId>
</dependency>
```

## Prerequisites

Before you are able to push via the Ionic platform, you should have all your apple APN and Google GCM certificates etc. in order.
You should also have pushed and uploaded your app to ionic and received a private key and an app_id which should be used for a push scenario.

## Push

To do a push message to the ionic platform (and hence to APN and GCM), create an ionic object with your application id private key, like so:

```java
Ionic i = new Ionic("xxxx", "xxxx");
i.push(json);
```

The json input should, of course be correct JSON formated, otherwise an exception will arise.

To retrieve status of a push message, you just have to get the message id of your previous push and pass it to this method:

```java
i.getPushStatus(messageId);
```

All responses from the REST endpoints are in String types. Hence you can choose your own serializer (e.g jackson, Gson etc.) 
