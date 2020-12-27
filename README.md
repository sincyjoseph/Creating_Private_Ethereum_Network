# Creating_Private_Ethereum_Network

Prerequiesites
install geth
install ganache - >    npm install -g ganache-cli
		       ganache-cli

1. create a directory ethereum-private
2. Go to directory ethereum-private
3. Create a genesis.json file in the directory ethereum-private

	{
	"config": {
	"chainId": 10,
	"homesteadBlock": 0,
	"eip150Block": 0,
	"eip150Hash": "0x0000000000000000000000000000000000000000000000000000000000000000",
	"eip155Block": 0,
	"eip158Block": 0,
	"byzantiumBlock": 0,
	"constantinopleBlock": 0,
	"petersburgBlock": 0,
	"istanbulBlock":0,
	"ethash": {}
	},
	"nonce": "0x0",
	"timestamp": "0x5e4a53b2",
	"extraData": "0x0000000000000000000000000000000000000000000000000000000000000000",
	"gasLimit": "0x47b760",
	"difficulty": "0x80000",
	"mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
	"coinbase": "0x0000000000000000000000000000000000000000",
	"alloc": {
	"0000000000000000000000000000000000000000": {
	  "balance": "0x2000000000000000000000000000000000000000000000000000000000000000"
	}
	},
	"number": "0x0",
	"gasUsed": "0x0",
	"parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000"
	}
  
4. geth --datadir C:\Users\Admin\Desktop\ethereum-private init genesis.json

output:

INFO [12-27|17:02:59.642] Maximum peer count                       ETH=25 LES=0 total=25

INFO [12-27|17:02:59.661] Allocated cache and file handles         database=C:\\Users\\Admin\\Desktop\\ethereum-private\\geth\\chaindata cache=16 handles=16

INFO [12-27|17:02:59.870] Persisted trie from memory database      nodes=1 size=172.00B time=0s gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B

INFO [12-27|17:02:59.915] Successfully wrote genesis state         database=chaindata                                                    hash=a19881…c24b7f

INFO [12-27|17:02:59.940] Allocated cache and file handles         database=C:\\Users\\Admin\\Desktop\\ethereum-private\\geth\\lightchaindata cache=16 handles=16

INFO [12-27|17:03:00.111] Persisted trie from memory database      nodes=1 size=172.00B time=0s gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B

INFO [12-27|17:03:00.163] Successfully wrote genesis state         database=lightchaindata                                                    hash=a19881…c24b7f


5. geth --networkid 8982 --datadir C:\Users\Admin\Desktop\ethereum-private --rpc --rpcaddr "0.0.0.0" --rpcport "8547" --rpcapi "web3,net,eth,admin,personal" rpccorsdomain "*" --allow-insecure-unlock console 2>>eth1.log

6.geth console

  geth attach
  
7.personal.newAccount("password")		//creating account address

"0xdb2c75d59a0bfb5ce20fd9252726e7f889bf9a73"

8.personal.listAccounts

9.miner.start()

10.Open another terminal 

	tail -f eth1.log
  
11.eth.getBalance(eth.accounts[0])

12.admin.nodeInfo

13.Open remix code

14.Open deploy and run

15.click web3.js

16.Type http://127.0.0.1:8547

17.It will connect with private ethereum accounts
  
  
