# twitter_ethereum_sample
twitter initial ethereum sample


## Run Geth(Ethereum) Server
```
geth --datadir=~/ethereum_workspace/ --networkid 123 --rpcport 8545 --rpcaddr 127.0.0.1 --port 30303 --rpc --rpcapi="db,eth,net,web3,personal,web3"  --maxpeers 3 --nat=any --nodiscover --rpccorsdomain "*"  console
```

```
miner.start()
```

## Compile and Migrate Contract

> npm install
> bower install

> truffle compile

**Unlock Your Account from your geth console**
```
web3.personal.unlockAccount("0X0000your_address_having_ether_in_account0000", "youraccountpassword", 50000);
```

**Migrate your Contract from your contract directory**

```
truffle migrate
```


**Run Contract Function**

**Call Setter Method**
```
MyFirstContract.deployed().then(function(contractInstance){contractInstance.setName('Pravesh').then(function(v){console.log(v)})});
```

***OutPut***

```
{ tx: '0x08bf70471a6225c1c024bf446c89ecad3386238bada2fedcac48e7dd0558f90c',
  receipt:
   { blockHash: '0xfdcf6c4774b33d562a939f53759dc324306149fa63c63171d24c96a7db08d251',
     blockNumber: 229,
     contractAddress: null,
     cumulativeGasUsed: 43061,
     from: '0xa1b6485f2ea4baef22b6f24333e0c7aec4ab2246',
     gasUsed: 43061,
     logs: [],
     logsBloom: '0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000',
     root: '0x29ac97f583df0d465649c53ec5a7dcfe3d97519c036987327470762e41fe4fd4',
     to: '0x93c767c597f041376e914677b7ba6ba9208de6f8',
     transactionHash: '0x08bf70471a6225c1c024bf446c89ecad3386238bada2fedcac48e7dd0558f90c',
     transactionIndex: 0 },
  logs: [] }
```
**Call Getter Method**
```
MyFirstContract.deployed().then(function(contractInstance){contractInstance.getName().then(function(v){console.log(`Im :` +v)})})
```

***OutPut***
```
undefined
truffle(development)> Im :Pravesh
```
