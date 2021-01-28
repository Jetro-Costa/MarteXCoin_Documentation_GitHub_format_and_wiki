.. meta::
   :description: MarteX Core wallet startup arguments and RPC command reference
   :keywords: martex, core, wallet, arguments, commands, RPC

.. _martexcore-rpc:

======================
Arguments and commands
======================

All command-line options (except for ``-datadir`` and ``-conf``) may be
specified in a configuration file, and all configuration file options
may also be specified on the command line. Command-line options override
values set in the configuration file. The configuration file is a list
of ``setting=value`` pairs, one per line, with optional comments
starting with the ``#`` character.

The configuration file is not automatically created; you can create it
using your favorite plain-text editor. By default, martex-qt (or martexd)
will look for a file named ``MarteX.conf`` in the martex data directory, but
both the data directory and the configuration file path may be changed
using the -datadir and -conf command-line arguments.

+----------+--------------------------------+-----------------------------------------------------------------------------------------------+
| Platform | Path to data folder            | Typical path to configuration file                                                            |
+==========+================================+===============================================================================================+
| Linux    | ~/                             | /home/username/.MXT/Martex.conf                                                               |
+----------+--------------------------------+-----------------------------------------------------------------------------------------------+
| macOS    | ~/Library/Application Support/ | /Users/username/Library/Application Support/MXT/MarteX.conf                                   |
+----------+--------------------------------+-----------------------------------------------------------------------------------------------+
| Windows  | %APPDATA%                      | (Vista-10) C:\\Users\\username\\AppData\\Roaming\\MXT\\MarteX.conf                            |
|          |                                |                                                                                               |
|          |                                | (2000-XP) C:\\Documents and Settings\\username\\Application Data\\MXT\\MarteX.conf            |
+----------+--------------------------------+-----------------------------------------------------------------------------------------------+

Note: if running MarteX in testnet mode, the sub-folder ``testnet3`` will
be appended to the data directory automatically.

Command line arguments
======================

These commands are accurate as of MarteX Core version v4.0.4.3-cbee601-dirty.

- `martexd <martexdcommandslist.rst>`_

- `martex-qt <martex-qtcommandslist.rst>`_

- `martex-cli <martex-clicommandslist.rst>`_

- `martex-tx <martex-txcommandslist.rst>`_
