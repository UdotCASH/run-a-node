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

## run setup.sh

copy genesis files to devnet directory

```cp genesis.json genesis.ssz devnet/```

cd devnet




## run node

cd 

```./uchain.sh run geth 1```

```./uchain.sh run beacon 1```

```./uchain.sh run validator 1```