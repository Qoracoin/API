# Payment

## POST payment

```shell
POST payment
```

Send a new payment using the given data.

Returns the transaction in JSON when successful.

> Format

```json
{
  "amount": "10.05",
  "fee": "1.000001",
  "sender": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM",
  "recipient": "QhMaXFowsVqdAhvU2xkcLzuVaH5VDyEWsS"
}
```
### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 104 | Invalid amount. |
| 105 | Invalid fee. |
| 106 | Invalid sender. |
| 107 | Invalid recipient. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |

## POST namepayment

```shell
POST namepayment
```

Send a new namepayment using the given data.

Returns the transaction in JSON when successful.

> Format

```json
{
  "amount": "10.05",
  "fee": "1.000001",
  "sender": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM",
  "recipient": "qora"
}
```
### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 104 | Invalid amount. |
| 105 | Invalid fee. |
| 106 | Invalid sender. |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |
| 701 | Name not registered. |
| 702 | Name for sale. |
| 703 | Name with space. |
