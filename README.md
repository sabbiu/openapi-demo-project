# example

simple example using express-openapi-validator

## Install

```shell
npm i
```

## Run

From this directory, run:

```shell
npm start
```

or run

```shell
npm run dev
```

## Issue

When I add this in query and run, it gives error

Ref: [stackoverflow comment](https://stackoverflow.com/a/49587746/6892277)

```yaml
- name: params
  in: query
  required: false
  schema:
    type: object
    # If the parameter values are of specific type, e.g. string:
    # additionalProperties:
    #   type: string
    # If the parameter values can be of different types
    # (e.g. string, number, boolean, ...)
    additionalProperties: true

  # `style: form` and `explode: true` is the default serialization method
  # for query parameters, so these keywords can be omitted
  style: form
  explode: true
```

```shell

$ curl http://localhost:3000/v1/pets\?type\=dog\&limit\=10\&test\=query


# returns {"message":"Cannot convert undefined or null to object"}
```
