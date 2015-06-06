# Payment

## POST payment

```shell
curl "http://127.0.0.1/9085/payment"
  -X POST
  -d {"amount":"10.05","fee":"1.000001","sender":"Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM","recipient":"QhMaXFowsVqdAhvU2xkcLzuVaH5VDyEWsS"}
```

```http
POST payment HTTP/1.1
Host: 127.0.0.1:9085
{
  "amount": "10.05",
  "fee": "1.000001",
  "sender": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM",
  "recipient": "QhMaXFowsVqdAhvU2xkcLzuVaH5VDyEWsS"
}
```
Send a new payment using the given data.

Returns the transaction in JSON when successful.

### REQUEST

`POST payment`

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
curl http://127.0.0.1:9085/namepayment
  -X POST
  -d {"amount": "10.05","fee": "1.000001","sender": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM","recipient":"qora"}
```

```http
POST namepayment HTTP/1.1
Host: 127.0.0.1:9085
{
  "amount": "10.05",
  "fee": "1.000001",
  "sender": "Qdxn4qW8kiPUiBnBSy9mbqMGBrBHRhK2JM",
  "recipient": "qora"
}
```
Send a new namepayment using the given data.

Returns the transaction in JSON when successful.

### REQUEST

`POST namepayment`

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
