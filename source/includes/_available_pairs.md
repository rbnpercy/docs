# Available Pairs API

The Pairs API returns token pairs in the Bancor network.

Since Bancor allow converting any token to any token, the API will only focus on major pairs that are known and familiar outside the Bancor network.

The token pairs are structured in the following way:

 1. BNT <> ETH
 2. Any other token on the Bancor network <> BNT

## Get Available Pairs

```shell
curl "https://api.bancor.network/0.1/currencies/convertiblePairs"
```

```javascript
const bancor = require('bancor');

let api = bancor.authorize('bancorkeyhere');
let pairs = api.pairs.get();
```

> The above command returns the following JSON:

```json
{ "data" :
  {"BNT":"ETH","GNOBNT":"BNT","ENJBNT":"BNT","INDBNT":"BNT","BMCBNT":"BNT","KINBNT":"BNT","WISHBNT":"BNT","OMGBNT":"BNT","TAASBNT":"BNT","STORMBNT":"BNT","AIXBNT":"BNT","GNO":"BNT","BMC":"BNT","OMG":"BNT","AIX":"BNT","ENJ":"BNT","WISH":"BNT","IND":"BNT","KIN":"BNT","TAAS":"BNT","STORM":"BNT"}
}
```

This endpoint retrieves the available Token Pairs on the Bancor network.

### HTTP Request

`GET https://api.bancor.network/0.1/currencies/convertiblePairs`


<aside class="success">
Keep in mind: Bancor API is currently in alpha and is likely to break or be slow to respond.
</aside>
