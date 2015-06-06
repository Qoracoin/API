# Errors

When an error happens the API will return a HTTP message 400(bad request) combined with an error.

> Response  

```http
HTTP/1.1 400 Bad Request
```

```json
{
  "error"101: ,
  "message": "invalid signature"
}
```

| Error | Description |
| --- | --- |
| 0 | Unknown error. |
| 1 | Json error. |
| 2 | Not enough balance. |
| 3 | Not yet released. |
| 101 | Invalid signature. |
| 102 | Invalid address. |
| 103 | Invalid seed. |
| 104 | Invalid amount. |
| 105 | Invalid fee. |
| 106 | Invalid sender. |
| 107 | Invalid recipient. |
| 108 | Invalid name length. |
| 109 | Invalid value length. |
| 110 | Invalid name owner. |
| 111 | Invalid buyer. |
| 112 | Invalid public key. |
| 113 | Invalid options length. |
| 114 | Invalid option length. |
| 115 | Invalid data. |
| 116 | Invalid data length. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |
| 203 | Wallet is locked |
| 204 | Wallet already exists. |
| 301 | Block does not exist. |
| 311 | Transaction does not exist. |
| 401 | Name does not exist. |
| 402 | Name already exists. |
| 403 | Name already for sale. |
| 404 | Name must be lower case. |
| 410 | Name is not for sale. |
| 411 | Buyer is already the owner. |
| 501 | Poll does not exist. |
| 502 | Poll already exists. |
| 503 | Duplicate option. |
| 504 | Polloption does not exist. |
| 505 | Already voted for that option. |
