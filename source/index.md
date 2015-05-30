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

# Seed

To generate a random base58 encoded seed. These seeds can be used to create a wallet or to import an account.

```shell
curl -s http://127.0.0.1:9085/seed/{length}
```
Returns a base58 encoded random seed of 32 bytes. Use the optional parameter length to request a seed of {length}bytes.

### HTTP Request

`GET http://127.0.0.1:9085/seed/{length}`

#Peers

```shell
curl -s http://127.0.0.1:9085/peers
```

Returns an array of all the IP’s of the peers to which the application is currently connected.

### HTTP Request

`GET http://127.0.0.1:9085/peers`

#Transactions

## View Transactions

```shell
curl -s http://127.0.0.1:9085/transactions
```

Returns an array of your accounts each with their 50 last transactions.

### HTTP Request

`GET http://127.0.0.1:9085/transactions`

## View Transactions (Limit)

```shell
curl -s http://127.0.0.1:9085/transactions/limit/{limit}
```

Returns an array of your accounts each with their {limit} last transactions.

### HTTP Request

`GET http://127.0.0.1:9085/transactions/limit/{limit}`

## View Transactions for Address

```shell
curl -s http://127.0.0.1:9085/transactions/address/{address}
```

Returns an array of the last 50 transactions of a specific address in your wallet.

### HTTP Request

`GET http://127.0.0.1:9085/transactions/transactions/address/{address}



