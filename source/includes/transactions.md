# Transactions

## Get Transactions

```shell
curl "http://127.0.0.1:9085/transactions"
```

```http
GET transactions HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
[
  {
    "transactions": [

    ],
    "account": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM"
  },
  {
    "transactions": [

    ],
    "account": "QQNFGuE8iZZ3sHjCnvvdbhfQHXokU8SgCX"
  }
]
```

Returns an array of your accounts each with their 50 last transactions.

### REQUEST

`GET transactions`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Get Limited Transactions

```shell
curl "http://127.0.0.1:9085/transactions/limit/{limit}"
```

```http
GET transactions/limit/{limit} HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
[
  {
    "transactions": [

    ],
    "account": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM"
  },
  {
    "transactions": [

    ],
    "account": "QQNFGuE8iZZ3sHjCnvvdbhfQHXokU8SgCX"
  }
]
```

Returns an array of your accounts each with their {limit} last transactions.

### REQUEST

`GET transactions/limit/{limit}`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

<!-- ##  GET transactions/{address}

```shell
GET transactions/{address}
```

Returns an array of the last 50 transactions of a specific address in your wallet.

Will be removed in future versions, use GET transactions/address/{address} instead.

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | address does not exist in wallet | -->

## Get Transactions By Address

```shell
curl "http://127.0.0.1:9085/transactions/address/{address}"
```

```http
GET transactions/address/{address} HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of the last 50 transactions of a specific address in your wallet.

### REQUEST

`GET transactions/address/{address}`

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | address does not exist in wallet |

## Get Limited Transactions By Address

```shell
curl "http://127.0.0.1:9085/transactions/address/{address}/limit/{limit}"
```

```http
GET transactions/address/{address}/limit/{limit} HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of the last {limit} transactions of a specific address in your wallet.

### REQUEST

`GET transactions/address/{address}/limit/{limit}`

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | address does not exist in wallet |

## Get Transactions By Signature

```shell
curl "http://127.0.0.1:9085/transactions/signature/{signature}"
```

```http
GET transactions/signature/{signature} HTTP/1.1
Host: 127.0.0.1:9085
```

Returns the transaction that matches the given signature.

### REQUEST

`GET transactions/signature/{signature}`

<!-- Will be moved to GET transactions/{signature} once GET transactions/{address} is removed. -->

### Errors

| Error | Description |
| --- | --- |
| 101 | Invalid signature. |
| 311 | Transaction does not exist. |

## Get Network Transactions

```shell
curl "http://127.0.0.1:9085/transactions/network"
```

```http
GET transactions/network HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of all the unconfirmed transactions known to the client.

### REQUEST

`GET transactions/network`

## Scan Transactions

```shell
curl "http://127.0.0.1:9085/transactions/scan"
  -d '{"blocklimit": 1000,"transactionlimit": 100,"type": 2}'
  -X POST
```
```http
POST transactions/scan HTTP/1.1
Host: 127.0.0.1:9085
{
  "blocklimit": 1000,
  "transactionlimit": 100,
  "type": 2
}
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "amount": 303,
  "lastscanned": "HQzVY265bpf2pSuLK8P5PRWQN47Ui5PiqyFsgyz2WpRiu6xUaLyyj99yrkUt2xSMbexRoF5fqJijJwG9DGJjPVYDwrhgSa33vg2KxvehAXRdhXvegzjnW55Fn1NXy51Ei3D8A9CyW7N4ohzFdHwmGjNryM26RPnqaTmmrZA32HeX7uc",
  "transactions": [
    {
      "fee": "1.00000000",
      "timestamp": 1400254833419,
      "sender": "Qec5ueWc4rcBrty47GZfFSqvLymxvcycFm",
      "amount": "1.00000000",
      "confirmations": 1959,
      "type": 2,
      "reference": "38sGerf4a24fRCTeknzQJgGBJe6hKribjKZGpQmrqajJwDM216FoUm9VCve7tst4Dypn1qgHKVgb6qN4vK9QFv3p",
      "signature": "2kioUSPPZdGvqWYZuT61J5M9nQ3udSzS2AZGU3MhdtNdbS2naWfuD6cpR2T9ZpKjRs2GFsyEYHDntQbBmTdsCyZL",
      "recipient": "QWNNYAh4dD7gktCfN9hb454qEaitjEnfy5"
    },
    {
      "fee": "1.00000000",
      "timestamp": 1400258674297,
      "sender": "QVjcFWE6TnGePGJEtbNc1thwD2sgHBLvUV",
      "amount": "42940527.25000000",
      "confirmations": 1949,
      "type": 2,
      "reference": "kRMLekdCQY7Prq2nyL8XLuL77oAJKP8WNarq1GaU6CTLQZ8VHgZJQFAeqJrNeKpt52QgsYrawcscRncY1XEsePB",
      "signature": "4YEbzGrvKntTJbfX3v4AZSY1JUaUqw7LFRm1s4ZDZKJqxfMWtKUw2Ho1jXXE16FSqwU4GqP8dxHaCV8huA6xDSg5",
      "recipient": "Qd9jQKZSXoYgFypTQySJUSbXcZvjgdiemn"
    }
  ]
}
```

Returns all the transactions that match the filters. All filters are optional but please limit that amount of transactions or blocks to scan to avoid running into issues.

### REQUEST

`POST transactions/scan`


| Filter | Description |
| --- | --- |
| start | The signature of the starting block. |
| blocklimit | The maximum amount of blocks to scan. |
| transactionlimit | The maximum amount of transactions to return. |
| type | Only return transactions with the given type. |
| service | Only return Arbitrary Transactions with the given service. |
| address | Only return transactions where the given address is involved. |

Return the last block it scanned, the amount of blocks it scanned and the scanned transactions.

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 102 | Invalid address. |
| 101 | Invalid signature. |
| 301 | Block does not exist. |
