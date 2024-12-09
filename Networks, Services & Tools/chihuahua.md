# Chihuahua

| Image                                                                                  |
| -------------------------------------------------------------------------------------- |
| <img src="/img/chains/chihuahua.jpg" alt="Chihuahua Image" width="100" height="100" /> |

## Links

| Platform | Link                                                                           |
| -------- | ------------------------------------------------------------------------------ |
| Website  | [https://www.chihuahua.wtf/](https://www.chihuahua.wtf/)                       |
| Discord  | [https://discord.com/invite/AR38BTh4X8](https://discord.com/invite/AR38BTh4X8) |
| Twitter  | [https://twitter.com/ChihuahuaChain](https://twitter.com/ChihuahuaChain)       |

## Network Metricss

| Metric       | Value       |
| ------------ | ----------- |
| Network      | Persistence |
| CoinGecko ID | persistence |

## Delegation Statistics

| Metric            | Value         |
| ----------------- | ------------- |
| Img Staked        | (Enter Value) |
| Unique Delegators | (Enter Value) |

## Chain Explorer

| Explorer | Link                                                                   |
| -------- | ---------------------------------------------------------------------- |
| Mintscan | [https://www.mintscan.io/chihuahua](https://www.mintscan.io/chihuahua) |
| Ping.pub | [https://ping.pub/chihuahua](https://ping.pub/chihuahua)               |

## Public Endpoints

| Type           | Endpoint                                                                                  |
| -------------- | ----------------------------------------------------------------------------------------- |
| API            | [https://api.chihuahua.validatus.com](https://api.chihuahua.validatus.com/)               |
| RPC            | [https://rpc.chihuahua.validatus.com](https://rpc.chihuahua.validatus.com/)               |
| gRPC (SSL/TLS) | `grpc.chihuahua.validatus.com:443`                                                        |
| gRPC Web       | [https://grpc-web.chihuahua.validatus.com](https://grpc-web.chihuahua.validatus.com/)     |
| Prometheus     | [https://prometheus.chihuahua.validatus.com](https://prometheus.chihuahua.validatus.com/) |

## Peering Information

| Type      | Address                                                                    |
| --------- | -------------------------------------------------------------------------- |
| Seed Node | 7549de9e4fada385ec0bd2807f83f7d97c6a15ec@seed.chihuahua.validatus.com:2000 |

## Address Book Configuration

| Command      | Code                                                                                                                 |
| ------------ | -------------------------------------------------------------------------------------------------------------------- |
| Address Book | `curl -Ls https://quicksync.validatus.com/addrbook/chihuahua/addrbook.json > $HOME/.chihuahuad/config/addrbook.json` |

## Latest Snapshot (Updated every 2 hours)

| Description        | Command                                                                                |
| ------------------ | -------------------------------------------------------------------------------------- | ----------- | ------------------------------ | --------- |
| Chain              | `chihuahua`                                                                            |
| Snapshot Retrieval | `NodeSnapshot=$(curl -v --silent https://quicksync.validatus.com/snapshots/ --stderr - | tr '>' '\n' | grep -o "${chain}-.\*.tar.lz4" | tail -1)` |
| Snapshot URL       | `URL="https://quicksync.validatus.com/snapshots/$NodeSnapshot"`                        |
| Download Snapshot  | `wget $URL`                                                                            |
