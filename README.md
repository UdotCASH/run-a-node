# uchain-node-tutorial
Instructions to run a uchain node. 

## dev environment setup

install go 

```sudo apt update && wget https://golang.org/dl/go1.21.0.linux-amd64.tar.gz && sudo tar -C /usr/local -xzf go1.21.0.linux-amd64.tar.gz && echo "export PATH=\$PATH:/usr/local/go/bin" >> ~/.bashrc && source ~/.bashrc ```

```
go version
```

## run setup.sh

```./setup.sh```

## run node

cd devnet

```./uchain.sh run geth 1```

```./uchain.sh run beacon 1```

```./uchain.sh run validator 1```