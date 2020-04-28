 ## **Requirements:**

> 5000 MXT or multiples of 5000 MXT

> Some People claim that to have a good cost benefit without overloading the vps, you must run a maximum of 3 masternodes per VPS.

> 1GB of RAM/Swap per masternode instance.

> Dedicated IP

> Port 15315 Available or any another. You must use differents port per masternode instance.

> We recommend generating a ssh key for you to connect to the masternode.

> We recommend follows those steps to protect you VPS:
 https://github.com/martexcoin/martexcoin/blob/master/mxt-docs/How-to-protect-your-Masternode-VPS-against-DDoS-attack---Linux.md

> Download your Wallet (QT or Daemon)

> Wallet synchronized

## **BEFORE YOU BEGIN**

> Acess your masternode. Create one folder past per masternode instance that you will create.

> Example: ~mkdir .MXT .MXT1 .MXT3 etc.

> Donwload the wallet core:

> Example: ~wget https://martexcoin.org/releases/martexcore-3.0.6-x86_64-linux-gnu.tar.gz

> tar- -vzxf nameoffile.tar.gz

> Create a sh file to run one masternode instance. For example:

> ~nano masternode.sh (to use the folder .MXT)

> inside masternode.sh put:

`#!/bin/bash`
`cd /root/Downloads/martexcore/bin`
`./martexd --datadir="/root/.MXT" $1 $2 $3 $4`

> Create a sh file to run the cliente program of masternode instance. For example:

>~nano masternode_cliente.sh

> inside masternode_cliente.sh put:

`#!/bin/bash`
`cd /root/Downloads/martexcore/bin`
`./martex-cli --datadir="/root/.MXT" $1 $2 $3 $4`

### 1) Make sure you know where is your MarteX data folder:

https://github.com/martexcoin/martexcoin/blob/master/mxt-docs/Home.md#martex-data-folder

#### In this folder you will find all .conf files required in this guide.

### 2) To generate a new address, **type in bash** then run:

`masternode_cliente.sh getaccountaddress MN1`

After than run

`masternode_cliente.sh masternode genkey`

_The first command returns the address that will receive your earnings as a Masternode_

### 3) Now send exactly 5000 MXT to the address generated at the 2nd step

### 4) Wait 16 confirmations 

### 5) Inside Console, run a command to generate the masternode outputs:

`masternode_cliente.sh masternode outputs`


_Copy all data from step 2 and 5_

### 6) After you waited 16 confirmations previously, close the wallet.

### 7) In the folder of the 1st step, edit the file or open it, with the name: MarteX.conf

### 8) In the MarteX.conf file, change this lines:

```
#rpcconnect=127.0.0.1
```
### 8.1) In the MarteX.conf file, change or put this lines:

```
masternode=1
masternodeaddr=ExternalIPDedicated:51315
masternodeprivkey=ReturnOfMasternodeGenkey
externalip=ExternalIPDedicated
nlogtimestamps=1
txindex=1
mnconflock=1
stake=0
staking=0
```
### 8.2) In the masternode.conf file, delete everithing and put this line:
```
MN_ALIAS IPEXTERNODEDICADO:51315 MASTERNODE_PRIVKEY TRANSACTION_HASH INDEX

Description:
MN_ALIAS = Name given in the fisrt step
IPEXTERNODEDICADO = Your external dedicated ip
MASTERNODE_PRIVKEY = Return Of Masternode Genkey
TRANSACTION_HASH = First data returned of command in the step 5
INDEX = Second data returned of command in the step 5
```
#### Make sure that your **GENKEY** is the same generated in the 2rd step
 
#### And the **EXTERNAL IP** must be a dedicated one, otherwise it wont work.

#### Do not use { } 

### 10) Now start your wallet and check for the masternode status:
`masternode status`

***

## **FAQ**

**For more informations acess: https://t.me/martexcoin**

**Will I receives every block?**

A. No, there's a line to be followed here, so you will have to wait your turn.
Tip: Keep eyes on the block winners with this commands:
 
**masternode winners**

**masternode list rank** 

**How much Masternode receives as reward?**
