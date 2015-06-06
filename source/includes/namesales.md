# NameSales

## Get Namesales

```shell
curl 'http://127.0.0.1:9085/namesales'
```

```http
GET namesales HTTP/1.1
Host: 127.0.0.1:9085
```
Returns an array of all the namesales owned by your accounts.

### REQUEST

`GET namesales`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Get Namesales By Address

```shell
curl "http://127.0.0.1:9085/namesales/address/{address}"
```

```http
GET namesales/address/{address} HTTP/1.1
Host: 127.0.0.1:9085
```
Returns an array of all the namesales owned by a specific address in your wallet.

### REQUEST

`GET namesales/address/{address}`

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## Get Sale Name Details

```shell
curl "http://127.0.0.1:9085/namesales/{name}"
```

```http
GET namesales/{name} HTTP/1.1
Host: 127.0.0.1:9085
```

Return details about the given name that is for sale.

### REQUEST

`GET namesales/{name}`

### Errors

| Error | Description |
| --- | --- |
| 410 | Name is not for sale. |

## List Names

```shell
curl "http://127.0.0.1:9085/namesales/network"
```

```http
GET namesales/network HTTP/1.1
Host: 127.0.0.1:9085
```
> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
[
  "qora",
  "test"
]
```

Returns an array of all the names that are for sale.

For performance this array only contains the keys of the names that are for sale and not the details.

### REQUEST

`GET namesales/network`

## Buy A Name

```shell
curl "http://127.0.0.1:9085/namesales/buy/{name}"
  -X POST
  -d '{"buyer":"QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5","fee":"1.00001"}'
```

```http
POST namesales/buy/{name} HTTP/1.1
Host: 127.0.0.1:9085
{
  "buyer": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "fee": "1.00001"
}
```

Used to purchase the given name.

Returns the transaction in JSON when successful.

### REQUEST

`POST namesales/buy/{name}`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 111 | Invalid buyer. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 401 | Name does not exist. |
| 410 | Name is not for sale. |
| 411 | Buyer is already the owner. |

## Sell A Name

```shell
curl "http://127.0.0.1:9085/namesales/{name}"
  -X POST
  -d '{"amount":"100","fee":"1.00001"}'
```

```http
POST namesales/{name} HTTP/1.1
Host: 127.0.0.1:9085
{
  "amount": "100",
  "fee": "1.00001"
}
```
Used to sell the given name.

Returns the transaction in JSON when successful.

<!-- ### REQUEST -->
### REQUEST

`POST namesales/{name}`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 102 | Invalid address. |
| 104 | Invalid amount. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 109 | Invalid name owner. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 401 | Name does not exist. |
| 403 | Name already for sale. |

## Cancel Sale Name

```shell
curl "http://127.0.0.1:9085/namesales/{name}/{fee}"
  -X DELETE
```

```http
DELETE namesales/{name}/{fee} HTTP/1.1
Host: 127.0.0.1:9085
```
Used to cancel the sale of the given name.

Returns the transaction in JSON when successful.

### REQUEST

`DELETE namesales/{name}/{fee}`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 110 | Invalid name owner. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 401 | Name does not exist. |
| 410 | Name is not for sale. |
