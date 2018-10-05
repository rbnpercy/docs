# Convert API

In order to build a quickConvert transaction and submit it to the Blockchain, you can use our Convert API. This will allow you to easily create the correct transaction using basic information required to successfully execute it.


## Build a transaction using the Convert API

```shell
curl -d '{"blockchainType":"ethereum", "fromCurrencyId":"5937d635231e97001f744267", "toCurrencyId":"59d745ff90509add31e9db14", "amount":"100000000000000000", "minimumReturn":"1", "ownerAddress":"0xb626a5facc4de1c813f5293ec3be31979f1d1c78"}' -H "Content-Type: application/json" -X POST "https://api.bancor.network/0.1/currencies/convert"
```

```javascript
const bancor = require('bancor');
```

> The above command returns the following JSON:

```json
"data": [
  {
    "from": "0x03733d509f60a33f1b86856560256351f23e5531",
    "to": "0xb626a5facc4de1c813f5293ec3be31979f1d1c78",
    "data":  "0xf0843ba90000000000000000000000000000000000000000000000000000000000000060000000000000000000000000000000000000000000000000016345785d8a000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000007000000000000000000000000c0829421c1d260bd3cb3e0f06cfe2d52db2ce3150000000000000000000000001f573d6fb3f13d689ff844b4ce37794d79a7ff1c0000000000000000000000001f573d6fb3f13d689ff844b4ce37794d79a7ff1c000000000000000000000000d7eb9db184da9f099b84e2f86b1da1fe6b305b3d000000000000000000000000d7eb9db184da9f099b84e2f86b1da1fe6b305b3d000000000000000000000000d7eb9db184da9f099b84e2f86b1da1fe6b305b3d0000000000000000000000006810e776880c02933d47db1b9fc05908e5386b96",
    "value": "0x16345785d8a0000",
    "gasPrice": "0x77359400",
    "nonce": "0x1c6",
    "gasLimit": "0x9dc62"
  }
]
```

> If there are not enough funds in the specified wallet, you will receive the following error:

```json
{"errorCode" : "insufficientFunds"}
```

You will need to collect the relevant information needed and send it to our Convert API. In return, you will receive the transaction format and data string that is required from the relevant Blockchain.

### HTTP Request

`POST  https://api.bancor.network/0.1/currencies/convert`

### Query Parameters

Parameter | Description
--------- | -----------
blockchainType | Indication of the Blockchain transaction type. *Currently Ethereum only.*
fromCurrencyId | The currency ID of the token you wish to convert tokens from.
toCurrencyId | The currency ID of the token you wish to convert tokens to.
amount | The amount of tokens you wish to convert. *This value needs to be in the smallest possible unit (Wei) and integer only.*
minimumReturn | The minimum amount of tokens you are willing to accept in return for the transaction. *We recommend setting this value to 2% under the expected return amount.*
ownerAddress | The address of the wallet executing the transaction.


### Hashed Values

Bancor uses a prioritization mechanism to enable transactions to be executed in the correct and valid order. Changing any of these values will cause the transaction to fail:

1. **Block number** - we initiate a transaction life of X blocks. Meaning, from the moment you create the transaction you have X amount of blocks to execute it. Executing it after the transaction lifetime will cause the transaction to fail.
2. **Gas price** - the gas price received is part of the transaction's hard coded values. Changing the gas price will cause the transaction to fail.
3. **User address** - transaction is limited to a specific user.
4. **Nonce** - transaction is limited to a specific nonce.


### Send the transaction to the Blockchain:

At this stage, you have the correct transaction created by our server and you will need to transmit it into the relevant Blockchain.

Ethereum format can be found here: [https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_sendrawtransaction](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_sendrawtransaction)

[Our technical tutorial on this process can be found here.](#)

<br/>

<aside class="success">
Keep in mind: Bancor API is currently in alpha and is likely to break or be slow to respond.
</aside>
