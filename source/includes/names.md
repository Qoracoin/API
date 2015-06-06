# Names

## Get Names

```shell
curl 'http://127.0.0.1:9085/names'
```

```http
GET names HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of all the names owned by your accounts.

### REQUEST

`GET names`

## Get Names By Address

```shell
curl 'http://127.0.0.1:9085/names/address/{address}'
```

```http
GET names/address/{address} HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of all the names owned by a specific address in your wallet.

### REQUEST

`GET names/address/{address}`

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## Get Name Details

```shell
curl 'http://127.0.0.1:9085/names/{name}'
```

```http
GET names/{name} HTTP/1.1
Host: 127.0.0.1/9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "owner": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "name": "qora",
  "value": "http://qora.org"
}
```

Returns details about the given name

### REQUEST

`GET names/{name}`

### Errors

| Error | Description |
| --- | --- |
| 401 | Name does not exist. |


## Register Name

```shell
curl "http://127.0.0.1/9085/names"
  -X POST
  -d '{"name": "qora","value": "http://qora.org","registrant": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5","fee": "1.00001"}'
```

```http
POST names HTTP/1.1
Host: 127.0.0.1:9085
{
  "name": "qora",
  "value": "http://qora.org",
  "registrant": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "fee": "1.00001"
}
```
Register a new name.

Returns the transaction in JSON when successful.

### REQUEST

`POST names`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 109 | Invalid value length. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 402 | Name already exists. |
| 404 | Name must be lower case. |


## Update Name

```shell
curl "http://127.0.0.1:9085/names/{name}"
  -X POST
  -d '{"newvalue":"http://qora.net","newowner":"QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5","fee":"1.00001"}'
```

```http
POST names/{name} HTTP/1.1
Host: 127.0.0.1/9085
{
  "newvalue": "http://qora.net",
  "newowner": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "fee": "1.00001"
}
```

Updates an existing name.

Returns the transaction in JSON when successful.

### REQUEST

`POST names/{name}`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 109 | Invalid value length. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 401 | Name does not exist. |
| 403 | Name already for sale. |
