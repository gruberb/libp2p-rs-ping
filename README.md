# libp2p-rs-ping

Using libp2p and tokio to create a ping server.

## Setup

```bash
$ git clone git@github.com:gruberb/libp2p-rs-ping.git
$ cd libp2p-rs-ping
```

## Usage

You need to terminal windows. In the first, just start the node via

```bash
$ cargo run
```

and wait for the output, like:

```bash
Local peer id: PeerId("12D3KooWEZzGuboyyyjy97ZDGNaTco5umEvNnbt4ov5nU6jfaahc")
Listen on "/ip4/127.0.0.1/tcp/62391"
Listen on "/ip4/192.168.178.27/tcp/62391"
```

In the second terminal window, pass the first nodes IP address and port as an argument:

```bash
$ cargo run -- /ip4/127.0.0.1/tcp/62391
```

## Example output

##### First node

```bash
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.13s
     Running `target/debug/libp2p-ping-rs`
Local peer id: PeerId("12D3KooWA9v5GjfSMuZe1F9Yk1C5ZcCPW8zrcEfU75SBc2TRxuuB")
Listen on "/ip4/127.0.0.1/tcp/62396"
Listen on "/ip4/192.168.178.27/tcp/62396"
Ping(Event { peer: PeerId("12D3KooWNN3YQP21JJekop5Wb9ibzwzGNP1hszU2cHk2vesE4cBa"), result: Ok(Pong) })
Ping(Event { peer: PeerId("12D3KooWNN3YQP21JJekop5Wb9ibzwzGNP1hszU2cHk2vesE4cBa"), result: Ok(Ping { rtt: 202.792µs }) })
````

##### Second node
```bash
$ cargo run -- /ip4/127.0.0.1/tcp/62396
    Finished dev [unoptimized + debuginfo] target(s) in 0.13s
     Running `target/debug/libp2p-ping-rs /ip4/127.0.0.1/tcp/62396`
Local peer id: PeerId("12D3KooWNN3YQP21JJekop5Wb9ibzwzGNP1hszU2cHk2vesE4cBa")
Dialed /ip4/127.0.0.1/tcp/62396
Listen on "/ip4/127.0.0.1/tcp/62397"
Listen on "/ip4/192.168.178.27/tcp/62397"
Ping(Event { peer: PeerId("12D3KooWA9v5GjfSMuZe1F9Yk1C5ZcCPW8zrcEfU75SBc2TRxuuB"), result: Ok(Pong) })
Ping(Event { peer: PeerId("12D3KooWA9v5GjfSMuZe1F9Yk1C5ZcCPW8zrcEfU75SBc2TRxuuB"), result: Ok(Ping { rtt: 246.084µs }) })
```
