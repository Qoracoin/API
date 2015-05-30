---
title: API Reference

search: true
---
# Qora

## Stop Qora

```shell
curl -s http://127.0.0.1:9085/qora/stop
```

This command will peacefully stop the Qora daemon.  It does not return anything.

### HTTP Request

`GET http://127.0.0.1:9085/qora/stop`

## Get Qora's Status

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


## Check if Qora is up to date

```shell
curl -s http://127.0.0.1:9085/qora/isuptodate
```

Returns a boolean that shows if the application is synchronized with the network.


### HTTP Request

`GET http://127.0.0.1:9085/qora/isuptodate`

### Return Values

Status | Value
--------- | -----------
0 | Is not up to date
1 | Is up to date

