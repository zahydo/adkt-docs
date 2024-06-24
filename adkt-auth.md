---
title: Authorization
description: How to get access to ADKT.
layout: libdoc/page

#LibDoc specific below
category: API
order: 20
---
* 
{:toc}

## Request the API KEY

Once the Backend ([README](./adkt-install.md)) is installed, you will have an API KEY to make requests from any HTTP client, all you have to do is add the following header to the request with the corresponding value.

## HTTP Header

The following header must be added to the HTTP request with the value received for the API KEY.

`x-api-key: "ds3-xxxxxxxxxxxxxxxcccccccccc"`

## Example

### cURL

```curl
curl --location --request POST 'https://x2qmbh2qm5gs7gczfbxebbbeie.appsync-api.us-east-1.amazonaws.com/graphql' \
--header 'x-api-key: ds3-xxxxxxxxxxxxxxxcccccccccc' \
--header 'Content-Type: application/json' \
--data-raw '{"query":"query getMetadata ($id: ID!) {\n    getMetadata (id: $id) {\n        id\n        reporterName\n        sourceRef\n        createdAt\n        updatedAt\n        metadataDesignDecisionId\n    }\n}","variables":{"id":"5a8df4f3-8b9e-43ad-9229-63b0b893fac8"}}'
```
### Axios

```javascript
var axios = require('axios');
var data = JSON.stringify({
  query: `query getMetadata ($id: ID!) {
    getMetadata (id: $id) {
        id
        reporterName
        sourceRef
        createdAt
        updatedAt
        metadataDesignDecisionId
    }
}`,
  variables: {"id":"5a8df4f3-8b9e-43ad-9229-63b0b893fac8"}
});

var config = {
  method: 'post',
  url: 'https://x2qmbh2qm5gs7gczfbxebbbeie.appsync-api.us-east-1.amazonaws.com/graphql',
  headers: { 
    'x-api-key': 'ds3-xxxxxxxxxxxxxxcccccccccccc', 
    'Content-Type': 'application/json'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```