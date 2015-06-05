# Arbitrary Transactions

## POST arbitrarytransactions

```shell
POST arbitrarytransactions
```

> Format

```json
{
  "creator": "QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6",
  "data": "4GFHMAo9fmbUq7usopgntwUfAiLtpL98K6QCosAJsqQmY95tfd5KoUaKu34v6Qwp7RtYEhobCx7LVi7aYbbtpzfA",
  "service": 555,
  "fee": "1.00001"
}
```

Used to send an arbitrary transaction.

The data of the arbitrary transaction must be base58 encoded and must be between 1-4000 bytes.

Returns the transaction in JSON when successful.


### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 3 | Not yet released. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 115 | Invalid data. |
| 116 | Invalid data length. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |
| 203 | Wallet is locked. |
