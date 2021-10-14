# Throttling configuration

## CDMA throttling
The main config is enabling the throttling client in your application

```properties
throttling.client.enabled=true
```

The throttling client needs to know where to find the throttling service and tell the service what threshold to use. This is configured using the following settings:

```properties
throttling.configuration.name=CDMA
throttling.configuration.max.concurrency=1000
throttling.service.url=http://localhost:9090
throttling.service.timeout=PT30S
```


Multiple clients can use the same configuration by using the same `throttling.configuration.name`. Throttling will be globally handled across those clients. Make sure all clients that use the same name also use the same `throttling.configuration.max.concurrency`. The last client to register a configuration will determine the max concurrency (overwriting previous registrations).

The throttling service itself should be deployed only once, it is not suited for load balanced deployment.