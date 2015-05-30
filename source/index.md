---
title: API Reference

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.


# Qora

## Stop Qora

```shell
curl -s http://127.0.0.1:9085/qora/stop
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://127.0.0.1:9085/qora/stop`

## Get Status

```shell
curl -s http://127.0.0.1:9085/qora/status
```

### HTTP Request

`GET http://127.0.0.1:9085/qora/status`

### Return Values

Status | Value
--------- | -----------
0 | No connections
1 | Synchronizing
2 | oke

