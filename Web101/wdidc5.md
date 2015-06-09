Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Intro to the Internet

## LEARNING OBJECTIVES

* Define a "communication protocol" in reference to computer communications
* Name the four basic parts of the Internet protocol suite (the TCP/IP 'stack')
* Explain the purpose of having a protocol stack.
* Explain the client-server model
* Describe the basics of the HTTP protocol, and explain what an HTTP Request is
* Explain the difference between GET and POST and when you would use each (in
  the common mode).
* Describe, in simple terms, the premise of REST.
* Explain the parts of a url in detail (with reference to their use in the two
  "modes" of HTTP).

## Computer communication

What is communication?
* It's just sending messages between things.

Where have we passed messages to our computer?
* command line
* OOP - encapsulation as communication
* databases

Is our communication with out computer formal?
Are there rules about how and when we say things?

## Communication Protocols

### Write-Pair-Share - Protocols

2 minutes writing - what is a protocol and why do we have them?
2 minutes discussion
2 minutes sharing out

Communicating systems use well-defined formats for exchanging messages. Each
message has an exact meaning intended to provoke a particular response of the
receiver.

Thus, a protocol must define:
1. the syntax,
2. semantics, and
3. synchronization of communication;

**Implementation**
...the specified behavior is typically independent of how it is to be
implemented. A protocol can therefore be implemented as hardware, software, or
both.

**Standards**
Communications protocols have to be agreed upon by the parties **involved**.
To reach agreement a protocol may be developed into a technical **standard**.

### Example

Ask for examples of a protocol.

**Formal Introductions**:
  * Person Introduces less senior to more senior, including full name and
    usually something about them.
  * Handshake
  * Less senior person says "Hi, #{others name}, nice to meet you!"
  * More senior person responds in kind.
  * Each party comments on the weather.
  * General communication can begin.
  * When someone says 'boy, howdy, look at the time', then it's time to stop
    communicating

### Syntax

* Data Format - How do we encode and represent our messages?
* Addressing - How do we indicate sender and receiver
* Routing - How do we get our message from A -> B
* Reliability - How do we make sure our message got there, and do we retry if
  not?
* Synchronization - How we do make sure messages are interpreted in the correct
  order?

### Semantics

The meaning of the things being said (equivalent to defining words in the
english language, and them having meaning in introductions).

### Synchronization

System wouldn't work if we didn't have a sense of an order.

Example: Nerdiest joke I know...
  * The barman says: “We don’t serve faster-than-light particles here.” A
    tachyon enters a bar.

## Exercise - Designing the Internet

Hand out index cards, and give students 15-20 minutes to come up with a protocol
for transmitting messages.

Think about:
* Reliability: He cannot guarantee that every message will be delivered successfully.
* Order: He cannot guarantee delivered messages will arrive in the same order that they were sent.
* Integrity: He cannot guarantee that all messages will arrive in their entirety.
* Recipient: He cannot guarantee that messages will always be delivered to the correct recipient.


## TCP/IP Stack (the Internet protocol suite)

### Summary of Layers

Discuss

### Exercise - Look up in groups of three

* Link layer
  * IEEE 802.11
  * IEEE 802.3
* Internet layer
  * IP
  * DNS
* Transport layer
  * TCP/IP
  * UDP
* Application layer
  * HTTP (2)
  * FTP (2)
  * GOPHER (2)

What is the purpose of the protocol stack?
**encapsulation**

![Image](http://upload.wikimedia.org/wikipedia/commons/c/c4/IP_stack_connections.svg)

**USPS**
Different levels of abstraction:
person -> person
postman -> postman
office -> office

### Link Layer

- Provides communication between devices on the same local network.
- e.g. ethernet and wifi

### Internet Layer

#### IP (Internet Protocol)

- Every computer on the network has an addressable IP
- DNS
- `host localhost` (special IP for our computer - can connect to ourselves!)
- packets

### Transport Layer

#### TCP (Transmission Control Protocol)

- make a connection -> data transfer -> close connection
- Data transfer: delivery and acknowledgement before next packet. Retry if not
  delivered.
- guarantee about order/reliability
- TCP for HTTP - we care that your whole order or credit card was sent
- Use ports - Web traffic on 80

#### UDP (User Datagram Protocol)

- No connection made; just send packets at will!
- Faster because no overhead of connection negotiation
- less reliable
- Great for VOIP - it's ok if you drop some packets - important for real-time
  to stream fast

### Application Layer

Example Application Protocols
- HTTP
- FTP
- SMTP/IMAP/POP
- SSH
- DNS
- VOIP

- for process-to-process
- Use the "plumbing" established by the lower layers to start doing real work
- this is the layer we care most about!

* Ports
* Application protocol lists

### HTTP

- request - response (client/server)
- status codes (200, 404 (client error), 500 (server error))

Modes of HTTP:

* common
* Web services: (make things API-like)
  * REST
  * SOAP
  * WebSockets

HTTP in depth:

- methods (GET, HEAD, POST, PUT, DELETE, OPTIONS, PATCH, etc.)
  - GET: server retrieve resource
  - POST: server store data
  - PUT: server modify existing resource
  - DELETE: server delete resource
- Semantics of each verb (POST is idempotent)
  - header v body
  - headers are key/value pairs (make analogy to Ruby Hashes)
- introduce the idea of metadata (for the computer) vs. content (for the user)
- Putting it all together
  - `curl -v example.com -o /dev/null`
  - `nc -l 1234`
  - URL -> DNS -> TCP connection -> HTTP GET Request -> Response

```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 62

<h1>Bill?</h1><img src="http://www.fillmurray.com/300/300" />
```

### URL BREAKDOWN!

`scheme://domain:port/path?query_string#fragment_id`
