##private Ethereum network

Components for a private Ethereum network

 - Custom Genesis File
 - Custom Data Directory
 - Custom NetworkID
 - (Recommended) Disable Node Discovery

###Genesis File
```josn
{
  "nonce": "0xdeadbeefdeadbeef",
  "timestamp": "0x0",
  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "extraData": "0x0",
  "gasLimit": "0x8000000",
  "difficulty": "0x400",
  "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "coinbase": "0x3333333333333333333333333333333333333333",
  "alloc": {
  }
}
```

============================================================================
1) geth --datadir="/tmp/eth/60/01" -verbosity 6 --ipcdisable --port 30301 --rpcport 8101 console 2>> /tmp/eth/60/01.log
> admin.nodeInfo.enode

2) geth --datadir="/tmp/eth/60/02" --verbosity 6 --ipcdisable --port 30302 --rpcport 8102 console 2>> /tmp/eth/60/02.log 

> admin.addPeer(enodeUrlOfFirstInstance)

============================================================================

1)
geth --identity "MyNodeName" --genesis CustomGenesis.json --rpc --rpcport "8000" --rpccorsdomain "*" --datadir "C:\chains\VPSChain" --port "30303" --nodiscover --ipcapi "admin,db,eth,debug,miner,net,shh,txpool,personal,web3" --rpcapi "db,eth,net,web3" --autodag --networkid 1900 --nat "any" console

2)

=============================================================================
1)
geth --genesis genesis.json --datadir="/tmp/eth/70/01" --networkid 123 --nodiscover --maxpeers 0 console



> Written with [StackEdit](https://stackedit.io/).
