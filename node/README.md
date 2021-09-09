# libp2p in the node

This example is modified from its [browser version](https://github.com/libp2p/js-libp2p/tree/master/examples/libp2p-in-the-browser).

## Setup

In order to run the example:

- Install the dependencies from same directory as this README:

```
yarn
```

## Running the examples

Start by running the nodejs start command:

```
npm start
```

The output should look something like this:

```log
$ npm start

> libp2p-in-node@1.0.0 start
> node index.js

Starting libp2p...
Found peer QmNnooDu7bfjPFoTZYxMNLWUQJyrVwtbZg5gBMjTezGAJN
...
libp2p started!
libp2p id is QmaPp31oS8WPiQpUVxTQWGBtHh7164JgKWHfDgH65rmW7X
Found peer 12D3KooWJxqxVskEzMxgF2AJLq5GBBWrttrd9roQPhnhNQde3D8p
Connected to QmNnooDu7bfjPFoTZYxMNLWUQJyrVwtbZg5gBMjTezGAJN
...
```

You should see a log of your node's Peer ID, the discovered peers from the Bootstrap module, and connections to those peers as they are created.

Your node will be notified of any peer that connects to the same signaling server you are connected to. Once libp2p discovers this new peer, it will attempt to establish a direct WebRTC connection.

## Going to production?

This example uses public `libp2p-webrtc-star` servers. These servers should be used for experimenting and demos, they **MUST** not be used in production as there is no guarantee on availability.

You can see how to deploy your own signaling server in [libp2p/js-libp2p-webrtc-star/DEPLOYMENT.md](https://github.com/libp2p/js-libp2p-webrtc-star/blob/master/DEPLOYMENT.md).

Once you have your own server running, you should add its listen address in your libp2p node configuration.
