# Convert API

In order to build a quickConvert transaction and submit it to the blockchain, you can use our "Convert" API. This will allow you to easily create the correct transaction using basic information required to successfully execute it.

## Build a transaction using the Convert API

```shell
curl "https://api.bancor.network/0.1/currencies/BNT/ticker?fromCurrencyCode=ETH"
```

```javascript
const bancor = require('bancor');

let api = bancor.authorize('bancorkeyhere');
let ticker = api.ticker.get();
```

> The above command returns the following JSON:

```json
[
  { "data" :
    { "name" : "Bancor",
      "symbol" : "BNT",
      "code" : "BNT",
      "decimals" : 18,
      "totalSupply" : "78314723629253897771940086",
      "price" : 0.006480832822998037,
      "price24h" : 0.006468881995466672,
      "volume24h" : "3522008124434191547611" }
  }
]
```

This endpoint retrieves the Bancor Price Ticker.

### HTTP Request

`GET https://api.bancor.network/0.1/currencies/"paired_token"/ticker?fromCurrencyCode="leading_token"`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
paired_token | "BNT" | The 3 letter indication of the token you would like to receive data for.
leading_token | "ETH" | The 3 letter indication of the leading token you are pairing with. We support here 2 optional values, ETH or BNT.

<aside class="success">
Keep in mind: Bancor API is currently in alpha and is likely to break or be slow to respond.
</aside>
