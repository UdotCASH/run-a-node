# uchain-node-tutorial
Instructions to run a uchain node. 

## dev environment setup

install go 

```sudo apt update && wget https://golang.org/dl/go1.21.0.linux-amd64.tar.gz && sudo tar -C /usr/local -xzf go1.21.0.linux-amd64.tar.gz && echo "export PATH=\$PATH:/usr/local/go/bin" >> ~/.bashrc && source ~/.bashrc ```

```
go version
```
## make scripts executable 
```chmod +x uchain.sh```
```chmod +x setup.sh```


## run setup.sh

```./setup.sh```

## copy genesis files

copy genesis files to devnet directory

```cp genesis.json genesis.ssz devnet/```

cd devnet


## run node (temporary)

```./geth --datadir=gethdata2 init genesis.json```

```
./geth --http --http.api eth,net,web3 --ws --ws.api eth,net,web3 --authrpc.jwtsecret jwt.hex --datadir gethdata2 --nodiscover --syncmode full --discovery.port 30304 --port 30304 --http.port 8547 --ws.port 8548 --authrpc.port 8552
```

```export PEER=```

```./beacon-chain --datadir beacondata2 --min-sync-peers 1 --genesis-state genesis.ssz --bootstrap-node= --interop-eth1data-votes --chain-config-file config.yml --contract-deployment-block 0 --chain-id 32382 --accept-terms-of-use --jwt-secret jwt.hex --suggested-fee-recipient 0x123463a4B065722E99115D6c222f267d9cABb524 --minimum-peers-per-subnet 0 --enable-debug-rpc-endpoints --execution-endpoint gethdata2/geth.ipc --peer=$PEER --p2p-udp-port 12001 --p2p-tcp-port 13001 --grpc-gateway-port 3501 --rpc-port 4001```


## run node

cd 

```./uchain.sh run geth 1```

```./uchain.sh run beacon 1```

```./uchain.sh run validator 1```

## enter geth console

```geth attach http://localhost:8545```


