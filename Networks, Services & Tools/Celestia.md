# The first modular blockchain network

![celestia-icon](../hidden-assets/svg/celestia-icon.svg)

**Celestia** is the first modular blockchain network designed to provide scalable and secure infrastructure for decentralized applications. By decoupling consensus and data availability, Celestia allows developers to deploy customized blockchains without the limitations of monolithic chains. With features like state-sync, node snapshots, and gRPC endpoints, Celestia ensures seamless node management and optimal network performance. Explore the full suite of community tools and services to participate in governance, enhance security, and streamline blockchain operations.



| [![www](../hidden-assets/icons/website-icon-15px.svg)](https://celestia.org) | [![docs](../hidden-assets/icons/docs-icon-15px.svg)](https://celestia.org/learn/) | [![x-icon-15px](../hidden-assets/icons/x-icon-15px.svg)](https://twitter.com/CelestiaOrg) | [![github-icon-15px](../hidden-assets/icons/github-icon-15px.svg)](https://github.com/celestiaorg/celestia-node) | [![discord-icon-15px-15px](../hidden-assets/icons/discord-icon-15px.svg)]() | [![telegram-icon-15px.svg](../hidden-assets/icons/telegram-icon-15px.svg)](https://t.me/CelestiaCommunity) | [![medium-icon-15px.svg](../hidden-assets/icons/medium-icon-15px.svg)](https://blog.celestia.org/) |
| ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |



## Network

### Onchain Metrics

<NetworkMetrics
  network="celestia"
  repoUrl="celestiaorg/celestia-node"
  coingeckoID="celestia"
/>

### Public Endpoints

<APITables columns={columns} rows={rows} />
### Seed Nodes

### Live Peers

### IBC Relaying

### Network Scan

## Downloads

### Peering Information

- **Seed Node:**
  - 23b88ebcfb2177dbd2d8b2920c363a25e038e69a@seed.celestia.valiatus.com:2000

### Nodes Snapshot (Updated every 3 hours )

These are pruned snapshots:

```bash
chain="celestia"
NodeSnapshot=$(curl -v --silent https://quicksync.validatus.com/snapshots/ --stderr - | tr '>' '\n' | grep -o "${chain}-.*.tar.lz4" | tail -1)
echo "Snapshot Height: $NodeSnapshot"
URL="https://quicksync.validatus.com/snapshots/$NodeSnapshot"
echo "URL $URL"
wget $URL
```

### Address book Configuration

```bash
curl -Ls https://quicksync.validatus.com/addrbook/celestia/addrbook.json > $HOME/.celestia-app/config/addrbook.json
```

### Archive Snapshots

### Addbook File

### Genesis File

### Run a Node

<NodesAccordian sections={Data} />
