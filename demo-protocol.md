# Demo of using NATS with Telnet

> The NATS wire protocol is a simple, text-based publish/subscribe style protocol. Clients connect to and communicate with gnatsd (the NATS server) through a regular TCP/IP socket using a small set of protocol operations that are terminated by newline.

More information about this demo and about Telnet
* http://nats.io/documentation/internals/nats-protocol-demo/
* http://nats.io/documentation/internals/nats-protocol/


Open 3 different terminals:
```
gnatsd                  # run the NATS server in terminal 1
telnet localhost 4222   # connect to the server in terminal 2
telnet localhost 4222   # connect to the server in terminal 3
```

subscribe in terminal 2:
```
sub foo.* 90
```

publish in terminal 3:
```
pub foo.bar 5
hello
```

Publish another message in terminal 3. now with a reply subject:
```
pub foo.bar optional.reply.subject 5
hello
```

If a client doesn't send ping to the server, the server disconnects the client.
to avoid it run ping:
```
ping
```
