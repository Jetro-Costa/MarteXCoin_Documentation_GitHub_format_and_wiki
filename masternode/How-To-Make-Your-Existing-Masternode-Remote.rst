Steps to do
-----------

The method
~~~~~~~~~~

Just dump you masternode wallet: using ``dumpwallet "filename"``

Download to you computer.

Use the follow command to download your wallet from your VPS:

``scp user_name@your_vps_ip:/your_file_path local_file_path``

Then import to your local wallet using the Debug Console in the Tab
Console.

Then use the follow commands: ``importwallet file_path`` or
``importwallet "file_path"``

On local wallet
---------------

After that, close your local wallet.

Go to your wallet folder.

Edit your masternode.conf located at the following link `data
folder <https://github.com/MarteXcoin-documentation/Documentation/blob/master/commands/cmd-rpc.rst#arguments-and-commands>`__
and put as showed in the example (**SINGLE SPACED SINGLE LINE** ):

    *MN\_ALIAS REMOTE\_MN\_IP:51315 MASTERNODE\_PRIVKEY
    TRANSACTION\_HASH INDEX*

After that, reopen your wallet and active Masternode Tab in Setting>
Options> Wallet
