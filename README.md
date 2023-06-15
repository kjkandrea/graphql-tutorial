# READ

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

## CREATE

```js
endpoint = '/graphql';
queryCode = `
    mutation($title: String!, $body: String) {
        createTopic(title: $title, body: $body) {
          id
        }
    }
`;
variables = {"title": "qraphQL", "body": "graphQL is ..." };

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
