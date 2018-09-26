# Token Data API

The “Tokens” API returns all the available data we have for the tokens on the Bancor network.

## Get Token Data

```shell
curl "https://api.bancor.network/0.1/currencies/tokens?limit=1&skip=0&fromCurrencyCode=ETH&includeTotal=false&orderBy=liquidityDepth&sortOrder=desc"
```

```javascript
const bancor = require('bancor');

let api = bancor.authorize('bancorkeyhere');
let token = api.token.get();
```

> The above command returns the following JSON:

```json
{"data":
  {"currencies":
    {"page":[
      {"_id":"594bb7e468a95e00203b048d",
        "supply":"75628405621850972886869922",
        "price":"0.006471562192984408",
        "priceHistory":[[0,6.4532],[1,66.13951],[2,61.73125],[3,60.53484],[4,62.33903],[5,79.39344],[6,74.6141],[7,92.75279],[8,54.50476],[9,50.1355],[10,55.72737],[11,64.21937],[12,81.39679],[13,66.37319],[14,43.64426],[15,50.08056],[16,43.89377],[17,59.1542],[18,64.78362],[19,63.8329],[20,75.91232],[21,71.9252],[22,78.5372],[23,66.82557],[24,50.02945],[25,45.39536],[26,44.64484],[27,57.69205],[28,39.88201],[29,0.04753],[30,13.27318],[31,8.74444],[32,34.69279],[33,48.3164],[34,49.93265],[35,55.29752],[36,57.52854],[37,56.89308],[38,30.49635],[39,34.29457],[40,47.69491],[41,51.07029],[42,46.38753],[43,46.28871],[44,43.83918],[45,45.40251],[46,40.38629],[47,7.28573],[48,12.8],[49,6.23962],[50,9.34949],[51,12.3525],[52,22.67207],[53,0.81869],[54,14.91857],[55,16.16185],[56,14.41028],[57,20.32021],[58,35.13495],[59,27.15939],[60,35.53055],[61,26.88415],[62,32.72443],[63,31.40899],[64,27.39092],[65,30.74249],[66,39.95735],[67,41.9523],[68,51.2714],[69,56.61535],[70,59.01226],[71,40.67463],[72,44.74318],[73,67.2107],[74,89.10614],[75,93.36203],[76,94.46383],[77,100],[78,92.91551],[79,93.70494],[80,75.47702],[81,71.66508],[82,66.97369],[83,59.82079]],
        "liquidityDepth":50673.796995883065,
        "volume24h":"3351759694646034693034",
        "change24h":0.22682224882133442,
        "code":"BNT",
        "name":"Bancor",
        "primaryCommunityId":"5967699a4a93370018b7b891",
        "primaryCommunityImageName":"f80f2a40-eaf5-11e7-9b5e-179c6e04aa7c.png",
        "subType":"smart"}]}
        }
      }
```

### HTTP Request

`GET https://api.bancor.network/0.1/currencies/{TokenType}?`

### Query Parameters

Parameter | Description | Values
--------- | ----------- | --------------
TokenType | Indicate the type of tokens you wish to receive in the response. | `token`, `relay`
fromCurrencyCode | Receive data back in specified currency. | `ETH`
orderBy | Define the order of items returned. | `liquidityDepth`, `change24`, `price`, `volume24`, `code`
sortOrder | Define the sort order of the list received. | `desc`, `asc`
limit | Determine the amount of records to receive. | `1 - 100`
skip | Determine the amount of records to skip. | `1 - 100`
includeTotal | Indicate if you with to receive the total amount of available tokens in the response. | `true`, `false`


<aside class="success">
Keep in mind: Bancor API is currently in alpha and is likely to break or be slow to respond.
</aside>
