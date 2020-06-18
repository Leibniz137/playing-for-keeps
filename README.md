# playing-for-keeps
This repo will get you started staking keep on ropsten.

### prerequisites:
You will need docker-compose and git installed on your node! This repo assumes you are using OS X or Linux.

```
# need to clone the dappnode submodule
git clone --recursive git@github.com:Leibniz137/playing-for-keeps.git
```

### step 1: sync ropsten node
```
# NOTE: this will take several hours to sync
docker-compose -f ropsten/DAppNodePackage-ropsten/docker-compose.yml up -d
```

### step 2: generate keypair
Generate an ethereum account/wallet using either MEW (my ether wallet) or `geth account create`

See [this medium post](https://medium.com/@novysf/run-a-keep-network-testnet-node-37096946af35) on
how to generate a wallet using MEW.


Save your generated json keyfile to `./keep_wallet.json`

save your passphrase to a file like this:
```
echo 'KEEP_ETHEREUM_PASSWORD=<password-goes-here>' > keep-account-password.env
```

### step 3: fill in config.toml
Get your account's address from `keep_wallet.json` file and prepend `0x` to the string.
Update the address field with this command:
```
sed -i.bak 's/Address = ""/Address = "0x..."/' ./keep-client/config/config.toml

# if the toml file looks good you can remove the backup
rm ./keep-client/config/config.toml.bak
```

### step 4: Load your wallet into metamask and complete the staking process.
Follow the steps in [this medium post](https://medium.com/@novysf/run-a-keep-network-testnet-node-37096946af35) to get eth/keep funds from their respective faucets and delegate to your own address.
