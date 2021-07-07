# Dogecoin-Assignment
## Steps and roadblocks:
I was unable to setup the dogecoin cli due to Macbook M1 issues, I was able to install homebrew successfully but when I tried to install the dependencies using homebrew I got the following error:
Cannot install under Rosetta 2 in ARM default prefix (/opt/homebrew)!
To rerun under ARM use:
    arch -arm64 brew install ...
To install under x86_64, install Homebrew into /usr/local.

And when I looked at this issue I found a solution that I need to install Rosetta first before running the homebrew commands but when I tried to install Rosetta, I got the following error: Installing Rosetta 2 on this system is not supported. So I discussed this with Arslan rao and told him that I have asked Maaz to send me a laptop, in the meanwhile I will pair up with Minahil to setup the cli locally.

Now, I have installed the dogecoin release to test the commands. Hassan helped me in setting up the testnet environment on the release. We can set the environment by using the following commands, first we have to go to following path: cd /Applications/Dogecoin-Qt.app/Contents/MacOS
And then we can enable testnet by running the following command:
./Dogecoin-Qt --testnet

It will run dogecoin client in testnet environment, you can then run the commands by going to help -> debug window -> console

## Commands and Outputs:

### Get Synced Data
Testnet data is completely synced now, I can see the recent transactions and my upto date balance.

### Get Address
> Command: getaccountaddress "mudassar"

> Output: nUqLeCHjwFeJ4V4chHhoSzo2apuVTx3Ltj

### Get Account Balance
> Command: getbalance "ng952W2wBvqvyagMHsy8NKmtPkqmJFYBnt"

> Output: 0.00000000

### Create Account in Wallet
> Command: getnewaddress "mudassar"

> Output: nqeCH4CtveUzBdRWjLrc24W3NN1Hjs8Wom

### Raw Transactions
Use the following command to create a raw transaction:

> Command: createrawtransaction '[{"txid":"30f6e7af32d976d7fc6d11ca762d03c1c4ef3844851df9239e5774350b5df929","vout":1}]' '{"ng952W2wBvqvyagMHsy8NKmtPkqmJFYBnt":12.5}'

> Output: 010000000129f95d0b3574579e23f91d854438efc4c1032d76ca116dfcd776d932afe7f6300100000000ffffffff01807c814a000000001976a914830be3b98b1d091e905e80678224eb59a9b2a5e188ac00000000

Now sign this raw transaction by using the following command:

> Command: signrawtransaction "010000000129f95d0b3574579e23f91d854438efc4c1032d76ca116dfcd776d932afe7f6300100000000ffffffff01807c814a000000001976a914830be3b98b1d091e905e80678224eb59a9b2a5e188ac00000000"

> Output: {
 "hex": "010000000129f95d0b3574579e23f91d854438efc4c1032d76ca116dfcd776d932afe7f630010000006b4830450221008eb88523ccb1dfe9acee615c017d28601d4980c0850de94a06f9b1fe8d6a173d02204ff78baaa0aa0ad9d60df77e90781dbc3f201459bed32558930d6dd32990698a0121032898a0b743c3bc117b517bd6b2d37607c20abf3852ef143c31940d0d96520913ffffffff01807c814a000000001976a914830be3b98b1d091e905e80678224eb59a9b2a5e188ac00000000",
 "complete": true
}

Now send the transaction by using this command:

> Command: sendrawtransaction "010000000129f95d0b3574579e23f91d854438efc4c1032d76ca116dfcd776d932afe7f630010000006b4830450221008eb88523ccb1dfe9acee615c017d28601d4980c0850de94a06f9b1fe8d6a173d02204ff78baaa0aa0ad9d60df77e90781dbc3f201459bed32558930d6dd32990698a0121032898a0b743c3bc117b517bd6b2d37607c20abf3852ef143c31940d0d96520913ffffffff01807c814a000000001976a914830be3b98b1d091e905e80678224eb59a9b2a5e188ac00000000"

> Output: e2895daba1a209fbd63f6f86e56f13b015f166c5723a140c212b80face738b9e


### Get Public Key / Private Key / Address
I have already listed the command to get the address.

Now to get the public key from address:

> Command: validateaddress "ng952W2wBvqvyagMHsy8NKmtPkqmJFYBnt"

> Output: {
 "isvalid": true,
 "address": "ng952W2wBvqvyagMHsy8NKmtPkqmJFYBnt",
 "scriptPubKey": "76a914830be3b98b1d091e905e80678224eb59a9b2a5e188ac",
 "ismine": true,
 "iswatchonly": false,
 "isscript": false,
 "pubkey": "032898a0b743c3bc117b517bd6b2d37607c20abf3852ef143c31940d0d96520913",
 "iscompressed": true,
 "account": "",
 "timestamp": 1625576382,
 "hdkeypath": "m/0'/0'/1'",
 "hdmasterkeyid": "6a11dd36aed91800d35fd635f1e1179903d70f16"
}

This will contain the public key.

To get the private key, the following command is used:

> Command: dumpprivkey "ng952W2wBvqvyagMHsy8NKmtPkqmJFYBnt"

> Output: cijphevhyJSBNhLUo9iff9LWxxjjooip8oJEWwknv7ZCvvobRZca

### Get Faucet
For testnet I have used this website: https://shibe.technology/ to get the dogecoins

For mainnet we can use this website: https://www.dogefaucet.com/en 
