# Polls

## GET polls

```shell
GET polls
```

Returns an array of all the polls created by your accounts.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## GET polls/address/{address}

```shell
GET polls/address/{address}
```

Returns an array of all the polls owned by a specific address in your wallet.

### Errors

| Error | Description |
| --- | --- |
| 102 | Invalid address. |
| 201 | Wallet does not exist. |
| 202 | Address does not exist in wallet. |

## GET polls/{name}

```shell
GET polls/{name}
```

Return details about the poll with the given name.

### Errors

| Error | Description |
| --- | --- |
| 501 | Poll does not exist. |

## GET polls/network

```shell
GET polls/network
```

Returns an array of all the polls.

For performance this array only contains the names of the polls and not the details.

> Response

```json
[
  "qora",
  "test"
]
```
## POST polls

```shell
POST polls
```

Used to create a new poll.

Returns the transaction in JSON when successful.

> Format

```json
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

## POST polls/vote/{name}

```shell
POST polls/vote/{name}
```

Used to vote on a poll with the given name.

Returns the transaction in JSON when successful.

> Format

```json
{
  "voter": "QNbA69dbnmwqJHLQeS9v63hSLZXXGkmtC6",
  "option": "option one",
  "fee": "1.00001"
}
```
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
