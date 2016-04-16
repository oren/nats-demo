# Demo of Monitoring NATS

Run the NATS server with the monitoring argument:
```
gnatsd -m 8222
```

Run various monitoring commands:
```
curl localhost:8222/varz
curl localhost:8222/connz
curl localhost:8222/routez
curl localhost:8222/subscriptionsz
```
