# Names

## GET names

```shell
GET names
```

Returns an array of all the names owned by your accounts.

## GET names/address/{address}

```shell
GET names/address/{address}
```

Returns an array of all the names owned by a specific address in your wallet.

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## GET names/{name}

```shell
GET names/{name}
```

Returns details about the given name

> Response

```json
{
  "owner": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "name": "qora",
  "value": "http://qora.org"
}
```
### Errors

| Error | Description |
| --- | --- |
| 401 | Name does not exist. |


## POST names

```shell
POST names
```

Register a new name.

Returns the transaction in JSON when successful.

> Format

```json
{
  "name": "qora",
  "value": "http://qora.org",
  "registrant": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "fee": "1.00001"
}
```
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


## POST names/{name}

```shell
POST names/{name}
```

Updates an existing name.

Returns the transaction in JSON when successful.

> Format

```json
{
  "newvalue": "http://qora.net",
  "newowner": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
  "fee": "1.00001"
}
```
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
