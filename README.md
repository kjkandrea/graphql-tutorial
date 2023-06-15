# GET

```js
endpoint = '/graphql';
queryCode = `
    query ($topicId: Int!) {
        title,
        topics {
            id,
            title,
            body
        },
        getTopic(id:$topicId) {
          id title body
        }
    }
`;
variables = {"topicId": 1};

options = {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({
    query: queryCode,
    variables
  })
};
fetch(endpoint, options).then(type => type.json()).then(console.log);
```
