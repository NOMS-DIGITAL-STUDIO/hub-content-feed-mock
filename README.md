# Hub Wiremock Content Feed

This is a small project using [Wiremock](http://wiremock.org/) to simulate the REST api and provide canned responses to test the Laravel front-end of the Hub.

The project is automatically deployed to Heroku and started using a Procfile with the following command:

```
web: java $JAVA_OPTS -Dserver.port=$PORT -jar wiremock-standalone-2.6.0.jar --port $PORT
```
