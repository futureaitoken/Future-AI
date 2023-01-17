---
cover: ../../.gitbook/assets/GITBOOK.png
coverY: 0
---

# 🔹 Data Source Provider

#### A brief description of how to develop a data source for an AI service on Future-AI:

_As Future-AI currently supports only shell script, a provider cannot use popular programming languages such as Java to develop their services._

_When developing the data source script, the job is fairly simple with no input arguments, as the providers only need to call their API using a cURL request. However, the output of a data source must be a string, not an object. A simple data source is given as follows:_

```
#!/bin/bash
curl -s -X GET "https://min-api.cryptocompare.com/data/price?fsym=ETH&tsyms=USD" -H "accept: application/json" | jq -r ".USD"
```

_The "jq" command is used to parse the JSON response of the request to collect only a string._
