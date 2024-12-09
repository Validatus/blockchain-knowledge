# The first modular blockchain network

![celestia-icon](../hidden-assets/svg/celestia-icon.svg)

**Celestia** is the first modular blockchain network designed to provide scalable and secure infrastructure for decentralized applications. By decoupling consensus and data availability, Celestia allows developers to deploy customized blockchains without the limitations of monolithic chains. With features like state-sync, node snapshots, and gRPC endpoints, Celestia ensures seamless node management and optimal network performance. Explore the full suite of community tools and services to participate in governance, enhance security, and streamline blockchain operations.



| [![www](../hidden-assets/icons/website-icon-15px.svg)](https://celestia.org) | [![docs](../hidden-assets/icons/docs-icon-15px.svg)](https://celestia.org/learn/) | [![x-icon-15px](../hidden-assets/icons/x-icon-15px.svg)](https://twitter.com/CelestiaOrg) | [![github-icon-15px](../hidden-assets/icons/github-icon-15px.svg)](https://github.com/celestiaorg/celestia-node) | [![discord-icon-15px-15px](../hidden-assets/icons/discord-icon-15px.svg)]() | [![telegram-icon-15px.svg](../hidden-assets/icons/telegram-icon-15px.svg)](https://t.me/CelestiaCommunity) | [![medium-icon-15px.svg](../hidden-assets/icons/medium-icon-15px.svg)](https://blog.celestia.org/) |
| ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |

## Network

### Metrics

| **Network Information** | Chain ID             |     |
| ----------------------- |:-------------------- | --- |
|                         | Latest Version Tag   |     |
|                         | WASM Support         |     |
| **Performance Metrics** | Block Time           |     |
|                         | Total Transactions   |     |
| **Economic Metrics**    | Inflation Rate       |     |
|                         | Staking APR          |     |
|                         | Bonded Tokens        |     |
|                         | Total Supply         |     |
| **Community Metrics**   | Community Pool       |     |
|                         | Community Pool Value |     |
|                         | Unique Delegators    |     |

### Public Endpoints

| **Service**          | **Endpoint**                                | **Archive Endpoint**                                     |
|-----------------------|---------------------------------------------|---------------------------------------------------------|
| API                  | https://api.celestia.validatus.com          | https://api.archive.celestia.validatus.com               |
| RPC                  | https://rpc.celestia.validatus.com          | https://rpc.archive.celestia.validatus.com               |
| gRPC with SSL/TLS    | grpc.celestia.validatus.com                 | grpc.archive.celestia.validatus.com                      |
| gRPC Web             | https://grpc-web.celestia.validatus.com     | https://grpc-web.archive.celestia.validatus.com          |
| Prometheus           | https://prometheus.celestia.validatus.com   | https://prometheus.archive.celestia.validatus.com        |



<APITables columns={columns} rows={rows} />
### Peering Information

### Live Peers
```
curl -sS https://rpc.celestia.validatus.com/net_info | jq -r '.result.peers[] | "\(.node_info.id)@\(.remote_ip):\(.node_info.listen_addr)"' | awk -F ':' '{print $1":"$(NF)","}'

```


## Services

### Seed Node
```
23b88ebcfb2177dbd2d8b2920c363a25e038e69a@seed.celestia.valiatus.com:2000
```

### Address Book
```
curl -Ls https://quicksync.validatus.com/addrbook/celestia/addrbook.json > $HOME/.celestia-app/config/addrbook.json

```

### Genesis File
```
wget -O genesis.json https://quicksync.validatus.com/genesis/celestia/genesis.json 
mv genesis.json ~/.celestia-app/config
```

### Snapshots
#### Steps to Restore a Node from a Snapshot

1. **Stop the Node**:
   Stop your node service to prevent conflicts during the restoration process.

   ```bash
   sudo systemctl stop <your-node-service>.service
   ```

2. **Fetch the latest snapshot**:
   ```bash    
    networkID="celestia"
    quicksyncServer="https://quicksync.validatus.com/snapshots/"
    nodeSnapshot=$(curl -v --silent $quicksyncServer --stderr - | tr '>' '\n' | grep -o "${networkID}-.*.tar.lz4" | tail -1)
    URL="${quicksyncServer}${nodeSnapshot}"
    
    echo $nodeSnapshot
    echo $URL
    wget $URL
   ```

3. **Clear Previous Data**:
    Create a timestamped backup directory to safely store critical files, including priv_validator_state.json to preserve the validator state.
   ```bash
    # Clear Previous Data:
    read -p "WARNING: This will reset all node data. Have you backed up all critical files? (y/n): " confirm
    if [ "$confirm" != "y" ]; then
      echo "Operation cancelled."
      exit 1
    fi
   <your-node-binary> tendermint unsafe-reset-all --keep-addr-book

   ```

5. **Extract the Snapshot to the Binary Home Directory**:
   Decompress and extract the snapshot into the correct data directory for your node.

   ```bash
   lz4 -d <snapshot-file> | tar -xvf - -C $HOME/<your-node-data-directory> --strip-components=2
   ```

**Notes:**
- Replace `<your-node-service>` with the name of your node's service (e.g., `celestia-appd`).
- Replace `<snapshot-URL>` with the full URL to the snapshot.
- Replace `<your-node-binary>` with your node binary name (e.g., `celestia-appd`).
- Replace `<your-node-data-directory>` with the data directory for your blockchain node (e.g., `.celestia-app`).


<NodesAccordian sections={Data} />
