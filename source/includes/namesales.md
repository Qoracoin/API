# NameSales

## GET namesales

```shell
GET namesales
```

Returns an array of all the namesales owned by your accounts.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## GET namesales/address/{address}

```shell
GET namesales/address/{address}
```

Returns an array of all the namesales owned by a specific address in your wallet.

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## GET namesales/{name}

```shell
GET namesales/{name}
```

Return details about the given name that is for sale.

### Errors

| Error | Description |
| --- | --- |
| 410 | Name is not for sale. |

## GET namesales/network

```shell
GET namesales/network
```

> Response

```json
[
  "qora",
  "test"
]
```

Returns an array of all the names that are for sale.

For performance this array only contains the keys of the names that are for sale and not the details.


## POST namesales/{name}

```shell
POST namesales/{name}
```

Used to sell the given name.

Returns the transaction in JSON when successful.

> Format

```json
{
  "amount": "100",
  "fee": "1.00001"
}
```
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

## DELETE namesales/{name}/{fee}

```shell
DELETE namesales/{name}/{fee}
```

Used to cancel the sale of the given name.

Returns the transaction in JSON when successful.

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

## POST namesales/buy/{name}

```shell
POST namesales/buy/{name}
```

Used to purchase the given name.

Returns the transaction in JSON when successful.

> Format

```json
{
  "buyer": "QVeHoptRAeLj5DqGq2TKHVL4w51KFGS5R5",
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
| 111 | Invalid buyer. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 401 | Name does not exist. |
| 410 | Name is not for sale. |
| 411 | Buyer is already the owner. |
