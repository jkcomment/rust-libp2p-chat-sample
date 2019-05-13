# rust-libp2p-chat-sample

A basic chat application demonstrating libp2p and the mDNS and floodsub protocols.

Using two terminal windows, start two instances. If you local network allows mDNS,
they will automatically connect. Type a message in either terminal and hit return: the
message is sent and printed in the other terminal. Close with Ctrl-c.

You can of course open more terminal windows and add more participants.
Dialing any of the other peers will propagate the new participant to all
chat members and everyone will receive all messages.

# If they don't automatically connect

If the nodes don't automatically connect, take note of the listening address of the first
instance and start the second with this address as the first argument. In the first terminal
window, run:

```sh
cargo run chat
```

It will print the PeerId and the listening address, e.g. `Listening on
"/ip4/0.0.0.0/tcp/24915"`

In the second terminal window, start a new instance of the example with:

```sh
cargo run chat /ip4/127.0.0.1/tcp/24915
```

The two nodes then connect.
