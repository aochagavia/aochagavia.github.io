+++
title = "chat-rs: a Tokio adventure"
draft = true
date = "2017-07-20T15:14:51+01:00"

+++

Since Tokio's 0.1 release, I have been wanting to implement a simple program
that goes a bit further than the examples given in the documentation. For a
long time I was stuck, unable to make sense of the
Tokio approach. Fortunately, after the last [Rust Utrecht Workshop][workshop]
I finally realized how it all fits together. Thanks to this insight I was able
to finish the project a couple of days later.

Let's get into the details!

# The project: chat-rs

[chat-rs][chat-rs] is a chat application. Clients connect to a server, identify
themselves with a nickname and communicate with each other in a single room.
That's basically it.

The crate implements a server and a client.

# Approach

Given my lack of experience with Tokio, I decided to write a first implementation
using the blocking `TcpStream` from the standard library. After that, I set out
to rewriting the code using Tokio. First the client, due to its simplicity, and
then the server. I kept the original implementation of the server in order to
compare it to the Tokio version (see the end of this post for
a comparison)

# Protocol

Communication between the server and the clients happens through messages. A
message consists of:

* A byte, specifying the length of the rest of the message
* A UTF-8 string

The first message sent by the client to the server is their nickname. Any
other messages are treated as a request to broadcast the text to the rest
of the clients. All messages sent by the server to the client are broadcasts.

For simplicity, there is no validation for the nickname. This means that you can
specify an empty nickname or a duplicated one and the server will not complain.

# The client

Let's begin with the client...

First of all, we need some way of bridging the blocking world of the terminal
to the async world of Tokio. Currently, the only way seems to be spinning up
a thread for `stdin` and another one for `stdout`, as can be seen in the [stdio][stdio]
module.



[workshop]: https://www.meetup.com/Rust-Utrecht/events/240660834/
[chat-rs]: https://github.com/aochagavia/chat-rs
[stdio]: FIXME
