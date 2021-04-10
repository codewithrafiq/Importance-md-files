# Django ReactJs GraphQl

### [Graphene-Django](https://docs.graphene-python.org/projects/django/en/latest/)

### [Django GraphQl JWT](https://django-graphql-jwt.domake.io/en/latest/quickstart.html)

### [React Apollo Client](https://www.apollographql.com/docs/react/get-started/)

## Fetching Data

#### index.js

```javascript
import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import {
  ApolloClient,
  ApolloProvider,
  InMemoryCache,
  gql,
} from "@apollo/client";

const uri = "http://127.0.0.1:8000/graphql/";
const cache = new InMemoryCache();

const client = new ApolloClient({ uri, cache });

ReactDOM.render(
  <ApolloProvider client={client}>
    <App />
  </ApolloProvider>,
  document.getElementById("root")
);
```

#### app.js No - 1

```javascript
import { gql, useQuery } from "@apollo/client";
const { loading, error, data } = useQuery(QUERY_GRAPHQL);
console.log(data);
```

#### app.js No - 2

```javascript
> > > export index.js client
import { client } from "..";
  client
    .query({
      query: gql`
        {
          todos {
            id
            title
            content
          }
        }
      `,
    })
    .then((result) => console.log("data", result)).catch(e=>{
      console.log(e);
    })

```
