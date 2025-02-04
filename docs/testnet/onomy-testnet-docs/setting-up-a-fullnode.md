# How to Run an Onomy Testnet Full Node

As a Cosmos-based chain, the ONET full nodes are similar to any Cosmos full nodes. Unlike the validator flow, running a full node requires no external software. 

## What do I need?

A Linux server with any modern Linux distribution, 4cores, 8gb of RAM and at least 20gb of SSD storage.

[Pre installation](pre-installation.md) is required prior to setting up a node.


### Initiate chain

```
git clone -b dev https://github.com/onomyprotocol/onomy.git
cd onomy/deploy/testnet
```

### Run the first time bootstrapping playbook and script

This script will run the needed commands to generate keys and store these in files. Be mindful of the generated keys, as you’ll need them later.

Important Note: Here in the script file, we have set up implementation with the home directory `$HOME/onomy-testnet1/onomy`. So, if you have changed this path, then provide the home directory path accordingly in the `onomyd` command.


```
bash peer-validator/init.sh

Note: 1. Script will ask for enter validator name(Type any name for example validator1)
      2. Script will ask for enter node-id of any validator that is running in chain to add seed(Please enter 5e0f5b9d54d3e038623ddb77c0b91b559ff13495)
      3. Script will ask for enter ip of validator for which you have added node-id(Please enter testnet1.onomy.io)
```

Now, it's finally up and has started the sycing block

### Check the status of the Onomy Network Testnet

You should be good to go! You can check the status of the three Onomy chain by running:
```
curl http://localhost:26657/status
```
If catching_up is false, this means that your node is fully synced. Congratulations!

