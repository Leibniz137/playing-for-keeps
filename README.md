# playing-for-keeps
```
# docker exec -it <container-name> geth attach ipc:///root/.ethereum/testnet/geth.ipc --exec 'eth.blockNumber'

# check that ropsten chain works
docker exec -it geth geth attach http://ropsten.dnp.dappnode.eth:8545/ --exec 'eth.blockNumber'
docker exec -it geth geth attach ws://ropsten.dnp.dappnode.eth:8546/ --exec 'eth.blockNumber'
```
