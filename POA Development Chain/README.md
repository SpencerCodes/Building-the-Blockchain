All dependencies are preloaded into /POA Development Chain directory

Network Configuration:

    Blocktime: 15 sec

    Chain ID: 111

    Account passwords: 123

    ports: 
        Node 1: 30303
        Node 2: 30304

    Node public keys:
        Node 1 Public Key: 
            0x315fEBf3c032e4B82C74F231e31a892c3E20c49e

        Node 2 Public Key: 
            0x7a3206702127f6d8AFdB70336e2270BCF89759eb

    Enodes:
        Node 1:
            enode://38c91b277d965d3941f1142c460b5a7b461acf515af4f5019e8d449dda586a42d1da01086eb7aead6e25f6c7893dcb4281b927e6eb562ef7954cc3b8cfe51c42@127.0.0.1:30303
        Node 2:
            enode://5cf022face9706bb224fd85b090edb9362289261f3f1b9a7bd2966c816550c1751ad4b541483dd289070ab096cc7b01ac18b01d0e0298ce40ef8ba6c39994c18@127.0.0.1:30304
    Local Address:
        http://127.0.0.1:8545

Geth flags:

    --mine == Enable mining
    --ipcdisable == Disable the IPC-RPC server
    --port value == Network listening port (default: 30303)
    --unlock value == Comma separated list of accounts to unlock
    --rpc == Enable the HTTP-RPC server (deprecated, use --http)
    --datadir value == Data directory for the databases and keystore
    --bootnodes value == Comma separated enode URLs for P2P discovery bootstrap
    --allow-insecure-unlock == Allow insecure account unlocking when account-related RPCs are exposed by http


Instructions to run blockchain:
    In two seperate terminals (Command lines) navegate to repo

    First initilaize both nodes:
        In terminal one, run:
            ./geth init fintech_homework.json --datadir node1

        In terminal two, run:
            ./geth init fintech_homework.json --datadir node2
    
    Second, unlock and run nodes:
        In terminal one run:
            ./geth --datadir node1 --unlock "0x315fEBf3c032e4B82C74F231e31a892c3E20c49e" --mine --rpc --allow-insecure-unlock

        In terminal two run:
            ./geth --datadir node2 --unlock "0x7a3206702127f6d8AFdB70336e2270BCF89759eb" --mine --port 30304 --bootnodes "enode://38c91b277d965d3941f1142c460b5a7b461acf515af4f5019e8d449dda586a42d1da01086eb7aead6e25f6c7893dcb4281b927e6eb562ef7954cc3b8cfe51c42@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

Instructions to send transaction:

    -Open My-Crypto
    -On left hand side, at very bottom, click "Change Network"
    -On left hand side, Scroll to very bottom and chick "Add custom node"
    -Fill out fields as per picture:

![my_crypto_node_setup.png](https://github.com/Is-A-Wizard/blockchain-homework/blob/main/POA%20Development%20Chain/Screen-Shots/my_crypto_node_setup.png)

    -Click "Save & Use Custom Node

    -On left had side of My-Crypto window, click "View & Send"
    -Click "Keystore File"
    -Click "Select Wallet File"
    -Follow path /blockchain_homework/PoA Development Chain/node1/Keystore and select the keystore file
    -Imput password (123)
    -For "To Address" paste public address of second node.
    -Fill amount
    -Hit send
    -Hit view transaction
    -Congratulations! You just set up your very own blockchain!!!