# Price Discovery API

The “Price Discover” API returns the expected amount of tokens you will receive when executing a transaction of a certain size using the Bancor Price Discovery formula.

## Get Prices

```shell
curl "https://api.bancor.network/0.1/currencies/5937d635231e97001f744267/value?toCurrencyId=594bb7e468a95e00203b048d&toAmount=1000000000000000000"
```

```javascript
const bancor = require('bancor');

let api = bancor.authorize('bancorkeyhere');
let price = api.price.get();
```

> The above command returns the following JSON:

```json
{ "data" : "6472519599021481" }
```

Note - execution amount may vary due to external changes. The calculation is dynamic and is relevant for the time of sampling. Since actual execution may be done with a delay, the result amount can change (up or down) given the data on the exact time of execution.

### HTTP Request

#### Requesting amount needed in the "To" token:
`https://api.bancor.network/0.1/currencies/{FromCurrencyID}/value?toCurrencyId={ToCurrencyID}&toAmount={Amount}`

#### Requesting amount needed in the "From" token:

`https://api.bancor.network/0.1/currencies/{FromCurrencyID}/value?toCurrencyId={ToCurrencyID}&fromAmount={Amount}`


### Query Parameters

Parameter | Description
--------- | -----------
FromCurrencyID |  This value is a unique currency ID that will indicate the token you would like to convert from. This is the token you currently have and would like to convert.
ToCurrencyID | This unique currency ID indicate the token you would like to convert to. This is the token you currently do not own and would like to receive at the end of the conversion process.
Amount | This integer value represents the smallest unit (wei) of the amount you would like to convert and receive indication for from the API.

<aside class="success">
Keep in mind: Bancor API is currently in alpha and is likely to break or be slow to respond.
</aside>
