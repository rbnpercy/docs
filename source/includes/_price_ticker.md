# Price Ticker API

The “Ticker” API returns all relevant data (name, symbol, code, decimals, price 24h high, price 24h low, price, price 24h, volume 24h, total supply) for the specific pair.

“Volume” and “total supply” values are indicated in the smallest unit of the token (example: Wei for ETH) which means you will need to format it correctly based on the token’s decimal digit settings.

[See the Price Ticker API in use in this tutorial.](#)

## Get Price Ticker

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
```

> If incorrect Token Currency Codes are entered, you will receive the following error:

```json
{"errorCode":"invalidCurrencyId"}
```

> If your query params are incorrect, you will receive the following error:

```json
{"errorCode":"invalidArgs"}
```



This endpoint retrieves the Bancor Price Ticker details for the specified token pair.  [Available token pairs are listed here.](#get-available-pairs)

### HTTP Request

`GET https://api.bancor.network/0.1/currencies/"paired_token"/ticker?fromCurrencyCode="leading_token"`

### Sample URL format:

#### BNT / ETH pair:
`https://api.bancor.network/0.1/currencies/BNT/ticker?fromCurrencyCode=ETH`

#### Any other network token / BNT pair:
`https://api.bancor.network/0.1/currencies/GNO/ticker?fromCurrencyCode=BNT`



### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
paired_token | "BNT" | The 3 letter indication of the token you would like to receive data for.
leading_token | "ETH" | The 3 letter indication of the leading token you are pairing with. We support here 2 optional values, ETH or BNT.

<aside class="success">
Token indication must be in upper case and match the token code from the Pairs API.
</aside>
