# Django ReactJs GraphQl

###[Graphene-Django](https://docs.graphene-python.org/projects/django/en/latest/)
###[Django GraphQl JWT](https://django-graphql-jwt.domake.io/en/latest/quickstart.html)
###[React Apollo Client](https://www.apollographql.com/docs/react/get-started/)

## Fetching Data
#### index.js
```reactjs
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

export const client = new ApolloClient({ uri, cache });

ReactDOM.render(
  <ApolloProvider client={client}>
    <App />
  </ApolloProvider>,
  document.getElementById("root")
);

```
#### app.js

