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

To request an API KEY you just have to send the data in the following [form](https://forms.gle/ttzV3CFhkDC7m3DV9) and wait for the response with the API KEY value of the demo environment. In case you have answered `Yes` to the question **¿Desea solicitar una API KEY privada para su compañía?**, we will contact the email sent with the next steps to follow.

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