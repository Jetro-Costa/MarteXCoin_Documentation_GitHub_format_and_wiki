MarteX Core RPC client version v4.0.4.3-cbee601-dirty

Usage:
  martex-cli [options] <command> [params]  Send command to MarteX Core
  martex-cli [options] -named <command> [name=value] ... Send command to MarteX Core (with named arguments)
  martex-cli [options] help                List commands
  martex-cli [options] help <command>      Get help for a command

Options:

  -?
       This help message

  -conf=<file>
       Specify configuration file (default: MarteX.conf)

  -datadir=<dir>
       Specify data directory

Chain selection options:

  -testnet
       Use the test chain

  -devnet=<name>
       Use devnet chain with provided name

  -regtest
       Enter regression test mode, which uses a special chain in which blocks
       can be solved instantly. This is intended for regression testing
       tools and app development.

  -named
       Pass named instead of positional arguments (default: false)

  -rpcconnect=<ip>
       Send commands to node running on <ip> (default: 127.0.0.1)

  -rpcport=<port>
       Connect to JSON-RPC on <port> (default: 51314 or testnet: 41314)

  -rpcwait
       Wait for RPC server to start

  -rpcuser=<user>
       Username for JSON-RPC connections

  -rpcpassword=<pw>
       Password for JSON-RPC connections

  -rpcclienttimeout=<n>
       Timeout during HTTP requests (default: 900)

  -stdin
       Read extra arguments from standard input, one per line until EOF/Ctrl-D
       (recommended for sensitive information such as passphrases)