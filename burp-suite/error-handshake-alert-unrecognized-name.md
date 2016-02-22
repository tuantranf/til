# Burp Suite error “burpsuite handshake alert: unrecognized_name”

When using Burp Suite, HTTPS websites will throw the error, “burpsuite handshake alert: unrecognized_name”.

This problem from an update in Java 7, where Server Name Indication (SNI) support was enabled by default. According to Wikipedia:

"Server Name Indication (SNI) is an extension to the TLS protocol[1] that indicates what hostname the client is attempting to connect to at the start of the handshaking process. This allows a server to present multiple certificates on the same IP address and port number and hence allows multiple secure (HTTPS) websites (or any other Service over TLS) to be served off the same IP address without requiring all those sites to use the same certificate. It is the conceptual equivalent to HTTP/1.1 virtual hosting for HTTPS.
Certain misconfigured websites will send an “Unrecognized Name” warning in the SSL handshake, causing Java to mishandle the connection."

To get around this using Burp Suite, use the following command, with Burp Suite version 1.5.21 as an example:

```bash
$ java -Djsse.enableSNIExtension=false -jar burpsuite_pro_v1.5.21.jar
```

