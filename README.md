# HW-19_Blockchain-Python

## Code to send BTCTEST transaction:

```python
coin = BTCTEST
priv_key = coins[coin][0]['privkey']
account = priv_key_to_account(coin, priv_key)
to = coins[coin][1]['address']
amount = 0.001

print(create_tx(coin, account, to, amount))
#satoshi_to_currency(NetworkAPI.get_balance_testnet(account.address), 'usd')
send_tx(coin, account, to, amount)
```
![](Instructions/wallet/BTCTESTtxSuccess.jpg)


## Code to send ETH transaction:

```python
coin = ETH
priv_key = coins[coin][0]['privkey']
account = priv_key_to_account(coin, priv_key)
to = coins[coin][1]['address']
amount = 0.001

print(create_tx(coin, account, to, amount))
send_tx(coin, account, to, amount)

```
![](Instructions/wallet/ETHtxSuccess.jpg)


## About the wallet:

This wallet was built to send BTC and Ethereum testnet tokens from one wallet to another.  It is built using the web3 and bit libraries that we installed into our ethereum environments.  I chose to write the code in jupyter notebook so in order to use the wallet, the user needs to navigate to jupyter notebook, add their mnemonic to the derive_wallets function, choose which coin they want to send ("coin" variable) and how much they want to send ("amount" variable).

## Wallet requirements & dependencies:

```python
import subprocess
import json
import os
from constants import *
from pprint import pprint
from bit import PrivateKeyTestnet
from bit.network import NetworkAPI, satoshi_to_currency
from bit import Key
from web3 import Web3, middleware, Account
from web3.gas_strategies.time_based import medium_gas_price_strategy
from web3.middleware import geth_poa_middleware
```


