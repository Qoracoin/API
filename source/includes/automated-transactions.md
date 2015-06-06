# Automated Transactions

## Get AT

```shell
curl "http://127.0.0.1:9085/at"
```

```http
GET at HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of deployed AT scripts.

### REQUEST

`GET at`

For performance this array only contains the addresses of the deployed AT scripts and not the details.

## Get AT By ID

```shell
curl "http://127.0.0.1:9085/at/id/{id}"
```

```http
GET at/id/{id} HTTP/1.1
Host" 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "tags": "acct,atomic cross chain tx,respond,responder",
  "accountBalance": "0.00000000",
  "description": "Responders BURST address: BURST-2Z98-XJU6-A2UA-FDKZP",
  "minActivation": "20.00000000",
  "name": "BURSTQORA @ 0.10",
  "state": {
    "stopped": "false",
    "machineData": "8e6a81f23b849c75d33f6398244d84881066c9cc09f9c3e1fe8c72710f64b62300000000b88301003a334bb82f7d8b71010c8c94148688024e5f2027fb0b930ca00000000000000001000000f48201000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
    "prevBalance": "0.00000000",
    "machineCode": "3501030900000006040000000900000029302009000000040000000f1ab4000000330403090000003525010a000000260a000000320903350703090000003526010a0000001b0a000000cd322801331601000000003317010100000033180102000000331901030000003505020a0000001b0a000000a1320b033205041e050000001833000509000000320a033203041ab400000033160105000000331701060000003318010700000033190108000000320304320b033203041ab70000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
    "finished": "false",
    "currentBalance": "0.00000000",
    "dead": "false",
    "frozen": "true",
    "running": "false"
  },
  "creationBlock": 99056,
  "type": "acct",
  "creator": "QVDVVphUiaQsEKVTXsNwsWbQvV6zTzeP2t",
  "version": 1
}
```

Returns the details of the given AT id.

###REQUEST

`GET at/id/{id}`

## Get AT By Creator

```shell
curl "http://127.0.0.1:9085/at/creator/{creator}"
```

```http
GET at/creator/{creator} HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```
```json
[
  "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
  "ALqEsn9ZysQqxmBvmvYCNTksrdNJLhjmrj"
]
```

Returns the IDs of the ATs created by the given creator.

### REQUEST

`GET at/creator/{creator}`

## Get AT By Type

```shell
curl "http://127.0.0.1:9085/at/type/{type}"
```

```http
GET at/type/{type} HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```
```json
[
  "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
  "AJMrqNG7LiwTquYtpXCuZbgzaD9hANSntn",
  "AJiK5MN1r1vtgCnjaDD7FWDfrQo3Gmsx1f",
  "ALHZt7FYS2RcFjJjmXGkqAF9dcVQuFTGdb",
  "ALqEsn9ZysQqxmBvmvYCNTksrdNJLhjmrj",
  "ASUn6hgiMYad1GPwiHodGgQvv6EkAadGiD"
]
```

Returns an array of the AT IDs for the given type.

### REQUEST

`GET at/type/{type}`

## Get Limited AT

```shell
curl "http://127.0.0.1:9085/at/limit/{limit}"
```

```http
GET at/limit/{limit} HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```
```json
[
  "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
  "ALqEsn9ZysQqxmBvmvYCNTksrdNJLhjmrj",
  "AVMvpJxRpdHxxEHcmnibDt6nYC3cBe8oH5",
  "AJiK5MN1r1vtgCnjaDD7FWDfrQo3Gmsx1f",
  "ALHZt7FYS2RcFjJjmXGkqAF9dcVQuFTGdb",
  "AJMrqNG7LiwTquYtpXCuZbgzaD9hANSntn",
  "ASUn6hgiMYad1GPwiHodGgQvv6EkAadGiD"
]
```

Returns an array of the AT IDs limited

### REQUEST

`GET at/limit/{limit}`

## Get AT Transactions

```shell
curl "http://127.0.0.1:9085/at/transactions/id/{id}"
```

```http
GET at/transactions/id/{id} HTTP/1.1
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
    "message": "",
    "amount": "1.20000000",
    "sender": "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
    "blockHeight": 99057,
    "seq": 0,
    "recipient": "11111111111111111111111111"
  },
  {
    "message": "f596db64ca23c2c312658ee15a5d74eea858696e9279ecc1592982acdf6cfc68",
    "amount": "0.00000000",
    "sender": "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
    "blockHeight": 99061,
    "seq": 0,
    "recipient": "QVDVVphUiaQsEKVTXsNwsWbQvV6zTzeP2t"
  },
  {
    "message": "",
    "amount": "50000.20000000",
    "sender": "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
    "blockHeight": 99061,
    "seq": 1,
    "recipient": "QRHDHASWAXarqTvB2X4SNtJCWbxGf68M2o"
  },
  {
    "message": "",
    "amount": "18.60000000",
    "sender": "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
    "blockHeight": 99061,
    "seq": 2,
    "recipient": "11111111111111111111111111"
  }
]
```

Returns the transactions of the given AT ID.

### REQUEST

`GET at/transactions/id/{id}`

## Get AT Transactions By Recipient

```shell
curl "http://127.0.0.1:9085/at/transactions/recipients/{address}"
```

```http
GET at/transactions/recipients/{address} HTTP/1.1
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
    "message": "",
    "amount": "50000.20000000",
    "sender": "AGvtqUUWEpBM8CeDFcPP7a9s42nE4RKwK7",
    "blockHeight": 99061,
    "seq": 1,
    "recipient": "QRHDHASWAXarqTvB2X4SNtJCWbxGf68M2o"
  },
  {
    "message": "",
    "amount": "50000.20000000",
    "sender": "ALqEsn9ZysQqxmBvmvYCNTksrdNJLhjmrj",
    "blockHeight": 99090,
    "seq": 1,
    "recipient": "QRHDHASWAXarqTvB2X4SNtJCWbxGf68M2o"
  }
]

```

Returns the AT transactions for the given recipient's address.  

### REQUEST

`GET at/transactions/recipients/{address}`

## Create AT

```shell
curl "http://127.0.0.1:9085/at"
  -X POST
  -d '{"creator":"","name":"","description":"","type":"","tags":"","fee":"","quantity":"","code":"","data":"","dpages":"","cspages":"","uspages":"","minActivationAmount":""}'
```

```http
POST at HTTP/1.1
Host: 127.0.0.1:9085
{
  "creator":"",
  "name":"",
  "description":"",
  "type":"",
  "tags":"",
  "fee":"",
  "quantity":"",
  "code":"",
  "data":"",
  "dpages":"",
  "cspages":"",
  "uspages":"",
  "minActivationAmount":""

}
```

Deploys an AT with the given details.Returns the transaction when successful.

`POST at`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 3 | Not yet released. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 104 | Invalid amount. |
| 108 | Invalid name length. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |
| 203 | Wallet is locked. |
| 801 | Invalid desc length. |
| 809 | Invalid creation bytes. |
