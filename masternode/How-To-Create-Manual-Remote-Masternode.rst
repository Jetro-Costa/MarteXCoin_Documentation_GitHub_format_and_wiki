Deploy an MXT Master Node
=========================

NOTE:
^^^^^

-  "MNx" is an alias for your MN, you can name them what you want. we
   are using x to denote MN1, MN2, MN3.... as masternode aliases
-  Configuration files locations by default are:
-  Linux: ``~/.MXT/``
-  Windows: ``%appdata%\MXT\``
    |Image of Windows\_Roamin\_folder|
-  OSX: ``~/Library/Application Support/MXT/``
-  Take note of the outputs of all commands you run in steps 1-3 as you
   will need them later

Step 1: Prepare for your REMOTE MasterNode
------------------------------------------

On your master wallet, You will need to generate/prepare a Masternode
Key/s by following these steps:

For every Masternode you want to create:

#. In your wallet Debug Console
#. | Generate an address to hold your MN collateral using :
   ``getaccountaddress MN1``
   |  |Image of getaccountaddress\_in|
   |  |Image of getaccountaddress\_out|
   |  >\ **sample output:** iEZzKiAcit8MCULTexkeZZZZZ7aevL6xv

#. | Generate a Masternode KEY for the above MN: ``masternode genkey``
   |  |Image of masternode\_genkey\_in|
   |  |Image of masternode\_genkey\_out|
   |  >\ **sample output:** 2rBZzZzZzZC3zZzZzZzZUgrqWsYJPFDmmaGrsWzZ

#. Using your QT wallet interface
#. | Send - In a single Transaction - 5K MXT to the address generated in
   step 1.i - requires *15 confirmations*
   |  |Image of send\_payment|

#. In your wallet Debug Console
#. | Run the following command and save its output:
   ``masternode outputs``
   |  |Image of masternode\_output\_in|
   |  |Image of masternode\_output\_out|
   |  >\ **sample output:** {
   "d1197905eaffd2fbfcd35f681adba92b25e32c62de6d0f7a5487926c01a70897":"0"
   }

#. On your desktop, edit the file named ``masternode.conf`` located in
   your INSN wallet folder; add a **SINGLE SPACED SINGLE LINE** for each
   of your Masternodes based on the following template :

       *MN\_ALIAS REMOTE\_MN\_IP:51315 MASTERNODE\_PRIVKEY
       TRANSACTION\_HASH INDEX*

**Example:** the second line is not to be included in the config file
and is to assist in pointing out the source of the information

    .. raw:: html

       <pre><code>MN1 123.123.123.123:51315 2rBZzZzZzZC3zZzZzZzZUgrqWsYJPFDmmaGrsWzZ d1197905eaffd2fbfcd35f681adba92b25e32c62de6d0f7a5487926c01a70897 0<br>
       1.i 123.123.123.123:51315 ^^^^^^ 1.ii ^^^^^^^^^^^^^^^^^^^^^^^^^^^^ ^^^^^^^^^  3.i  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ ^</code></pre>

`Sample masternode.conf <./mxt-mn/blob/master/masternode.conf>`__

Step 2: Deploy to VPS
---------------------

**Requirements:**
-----------------

5000 MXT

1GB of RAM/Swap only to the masternode.

Dedicated IP

Port 51315 Available.

We recommend generating a ssh key for you to connect to the masternode.

| We recommend follows those steps to protect you VPS:
| 
https://github.com/MarteXcoin-documentation/MarteXCoin_Documentation_GitHub_format_and_wiki/blob/master/masternode/How-to-protect-your-Masternode-VPS-against-DDoS-attack---Linux.md

Download your Wallet (QT or Daemon)

    Wallet synchronized

**BEFORE YOU BEGIN**
--------------------

Acess your masternode. Create one folder to the masternode instance that
you will create.

Example: ``~mkdir .MXT``

    Donwload the wallet core:

Example:
``~wget https://martexcoin.org/releases/martexcore-3.0.6-x86_64-linux-gnu.tar.gz``

Extract wallet to you local folder

``tar -vzxf nameoffile.tar.gz``

Create a sh file to run one masternode instance. For example:

``~nano masternode.sh`` (to use the folder .MXT)

inside masternode.sh put:

``#!/bin/bash  cd /root/Downloads/martexcore/bin  ./martexd --datadir="/root/.MXT" $1 $2 $3 $4``

Create a sh file to run the cliente program of masternode instance. For
example:

``~nano masternode_cliente.sh``

inside masternode\_cliente.sh put:

``#!/bin/bash  cd /root/Downloads/martexcore/bin  ./martex-cli --datadir="/root/.MXT" $1 $2 $3 $4``

1) Make sure you know where is your MarteX data folder:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

https://github.com/martexcoin/martexcoin/blob/master/mxt-docs/Home.md#martex-data-folder

In this folder you will find all .conf files required in this guide.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the folder of the step above, edit the file or open it, with the name: MarteX.conf
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In the MarteX.conf file, change this lines:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

    #rpcconnect=127.0.0.1

In the MarteX.conf file, change or put this lines:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

    masternode=1
    masternodeaddr=ExternalIPDedicated:51315
    masternodeprivkey=ReturnOfMasternodeGenkey
    externalip=ExternalIPDedicated
    logtimestamps=1
    txindex=1
    mnconflock=1
    stake=0
    staking=0
    listen=1
    server=1
    daemon=1
    maxconnections=500
    rpcuser=(put your user here)
    rpcpassword=put_a_long_password_here
    port=51315
    rpcport=51314
    rpcallowip=127.0.0.1
    addnode=add.other.noder.here.with:port
    addnode=ip_node:port_node
    addnode=seed2.martexcoin.org:51315
    addnode=seed3.martexcoin.org:51315
    addnode=seed4.martexcoin.org:51315

Do not use { }
^^^^^^^^^^^^^^

Now start your VPS wallet, wait synchronize and start the masternode remotely:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In you local wallet, in the tab masternodes; remote start your
masternode.

Check masternode status:
~~~~~~~~~~~~~~~~~~~~~~~~

``sh masternode_cliente.sh masternode status``

--------------

**FAQ**
-------

**For more informations acess: https://t.me/martexcoin**

**Will I receives every block?**

| A. No, there's a line to be followed here, so you will have to wait
your turn.
| Tip: Keep eyes on the block winners with this commands:

**masternode winners**

``sh masternode_cliente.sh masternode winners``

**masternode list rank**

``sh masternode_cliente.sh masternode list``

**How much Masternode receives as reward?**

1.125 MXT

To report issues or for support :  `MarteXcoin Telegram @martexcoin <https://t.me/martexcoin>`__
-----------------------------------------------------------------------------------------------

.. |Image of Windows\_Roamin\_folder| image:: ./mxt-mn/images/Roaming_Folder.png
.. |Image of getaccountaddress\_in| image:: ./mxt-mn/images/Generate_MN_PubKey_I.png
.. |Image of getaccountaddress\_out| image:: ./mxt-mn/images/Generate_MN_PubKey_O.png
.. |Image of masternode\_genkey\_in| image:: ./mxt-mn/images/Generate_MN_Key_I.png
.. |Image of masternode\_genkey\_out| image:: ./mxt-mn/images/Generate_MN_Key_O.png
.. |Image of send\_payment| image:: ./mxt-mn/images/MN_Collateral.png
.. |Image of masternode\_output\_in| image:: ./mxt-mn/images/Masternode_Outputs_I.png
.. |Image of masternode\_output\_out| image:: ./mxt-mn/images/Masternode_Outputs_O.png
