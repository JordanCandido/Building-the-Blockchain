# Blockchain Instructions

1. Install MCrypto and gETH

2. Create accounts for two nodes for the network with a separate datadir for each using geth.
./geth --datadir node1 account new
./geth --datadir node2 account new

3. Run puppeth in git bash

4. Select Clique (Proof of Authority)

5. Paste both account addresses in one at a time.

6. Choose no for pre-funding.

7. Complete prompts and choose "Manage existing genesis" option.

8. Export genesis configurations.

9. Using geth, initialize each node with the new networkname.json.
./geth --datadir node1 init networkname.json
./geth --datadir node2 init networkname.json

10. Run the nodes in separate terminal windows with the commands:
./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

11. Open the MyCrypto app, then click Change Network at the bottom left. 

12. After connecting to the custom network in MyCrypto, it can be tested by sending money between accounts. On the next screen, click Select Wallet File, then navigate to the keystore directory inside your Node1 directory, select the file located there, provide your password when prompted and then click Unlock. 

13. In the To Address box, type the account address from Node2, then fill in an arbitrary amount of ETH.

14. Click the Check TX Status when the green message pops up, confirm the logout.

Congratulations, you successfully created your own private blockchain!

