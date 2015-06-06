# Polls

## Get Polls

```shell
curl "http://127.0.0.1:9085/polls"
```

```http
GET polls HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of all the polls created by your accounts.

### REQUEST

`GET polls`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Get Polls By Address

```shell
curl "http://127.0.0.1:9085/polls/address/{address}"
```

```http
GET polls/address/{address} HTTP/1.1
Host: 127.0.0.1:9085
```

Returns an array of all the polls owned by a specific address in your wallet.

### REQUEST

`GET polls/address/{address}`

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## Get Polls By Name

```shell
curl "http://127.0.0.1:9085/polls/{name}"
```

```http
GET polls/{name} HTTP/1.1
Host: 127.0.0.1:9085
```

### REQUEST

`GET polls/{name}`

Return details about the poll with the given name.

### Errors

| Error | Description |
| --- | --- |
| 501 | Poll does not exist. |

## List Polls

```shell
curl "http://127.0.0.1:9085/polls/network"
```

```http
GET polls/network HTTP/1.1
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
### REQUEST

`GET polls/network`

Returns an array of all the polls.

For performance this array only contains the names of the polls and not the details.

## Vote

```shell
curl "http://127.0.0.1:9085polls/vote/{name}"
  -X POST
  -d '{"voter":"QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6","option":"option one","fee":"1.00001"}'
```

```http
POST polls/vote/{name} HTTP/1.1
Host: 127.0.0.1:9085
{
  "voter": "QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6",
  "option": "option one",
  "fee": "1.00001"
}
```

Used to vote on a poll with the given name.

Returns the transaction in JSON when successful.

### REQUEST

`POST polls/vote/{name}`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 3 | Not yet released. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 114 | Invalid option length. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |
| 203 | Wallet is locked. |
| 404 | Name must be lowercase. |
| 501 | Poll does not exist. |
| 504 | Polloption does not exist. |
| 505 | Already voted for that option. |

## Create Poll

```shell
curl "http://127.0.0.1:9085/polls"
  -X POST
  -d '{"creator":"QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6","name":"testpoll","description":"this is a testpoll","options": ["option one","option two"],"fee":"1.00001"}'
```

```http
POST polls HTTP/1.1
Host: 127.0.0.1:9085
{
  "creator": "QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6",
  "name": "testpoll",
  "description": "this is a testpoll",
  "options": [
    "option one",
    "option two"
  ],
  "fee": "1.00001"
}
```

Used to create a new poll.

Returns the transaction in JSON when successful.

### REQUEST

`POST polls`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 2 | Not enough balance. |
| 3 | Not yet released. |
| 102 | Invalid address. |
| 105 | Invalid fee. |
| 108 | Invalid name length. |
| 109 | Invalid description length. |
| 113 | Invalid options length. |
| 114 | Invalid option length. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |
| 203 | Wallet is locked. |
| 404 | Name must be lowercase. |
| 502 | Poll already exists. |
| 503 | Duplicate option. |
