# Demo of NATS

[NATS](http://nats.io) is a messaging system for distributed systems.

![NATS](http://nats.io/img/documentation/nats-pub-sub-eg.png)

Setup
```
go get github.com/nats-io/gnatsd
git clone https://github.com/nats-io/nats
cd nats && go get && cd examples
```

Run the NATS server
```
gnatsd

[25846] 2016/04/16 02:15:18.330567 [INF] Starting gnatsd version 0.8.0.beta
[25846] 2016/04/16 02:15:18.330632 [INF] Listening for client connections on 0.0.0.0:4222
[25846] 2016/04/16 02:15:18.330675 [INF] server is ready
```

Run a subscriber
```
go run nats-sub.go com.msg.one

Listening on [com.msg.one]
```

Run a publisher
```
go run nats-pub.go com.msg.one "NATS MESSAGE"

Published [com.msg.one] : 'NATS MESSAGE'
```

Notice that the subscriber recieves the message. You should see: `[#1] Received on [com.msg.one]: 'NATS MESSAGE'`
