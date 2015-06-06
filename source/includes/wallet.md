# Wallet

## Get Wallet

```shell
curl "http://127.0.0.1:9085/wallet"
```

```http
GET wallet HTTP/1.1
Host: 127.0.0.1:9085
```

> Response

```json
{
  "exists": true,
  "isunlocked": false
}
```

Returns general information about the wallet.

### REQUEST

`GET wallet`


## Get Wallet Seed

```shell
curl "http://127.0.0.1:9085/wallet/seed"
```

```http
GET wallet/seed HTTP/1.1
Host: 127.0.0.1:9085
```

Return the 32-byte long base58-encoded wallet seed.

### REQUEST

`GET wallet/seed`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |

## Wallet Synchronize

```shell
curl "http://127.0.0.1:9085/wallet/synchronize"
```

```http
GET wallet/synchronize HTTP/1.1
Host: 127.0.0.1:9085
```

Rescans the blockchain for data.

### REQUEST

`GET wallet/synchronize`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Lock Wallet

```shell
curl "http://127.0.0.1:9085/wallet/lock"
```

```http
GET wallet/lock HTTP/1.1
Host: 127.0.0.1:9085
```

Locks the wallet.

Returns true/false depending on the fact if the wallet was already locked and if the password was correct.

### REQUEST

`GET wallet/lock`

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Unlock Wallet

```shell
curl "http://127.0.0.1:9085/wallet/unlock"
  -X POST
  -d password
```

```http
POST wallet/unlock HTTP/1.1
Host: 127.0.0.1:9085
password
```

Unlocks the wallet using the given password.

Returns true/false depending on the fact if the password is correct.

### REQUEST

<!-- `POST wallet/unlock` -->
`POST wallet/unlock`


### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## Create Wallet

```shell
curl "http://127.0.0.1:9085/wallet"
  -X POST
  -d '{"seed": "FQgbSAm6swGbtqA3NE8PttijPhT4N3Ufh4bHFAkyVnQz","password": "cookies","recover": false,"amount": 10}'
```

```http
POST wallet HTTP/1.1
Host: 127.0.0.1:9085
{
  "seed": "FQgbSAm6swGbtqA3NE8PttijPhT4N3Ufh4bHFAkyVnQz",
  "password": "cookies",
  "recover": false,
  "amount": 10
}
```

Creates a wallet using the given 32-byte long base58-encoded seed, password,recover flag and amount.

### REQUEST

`POST wallet`

### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 103 | Invalid seed. |
| 104 | Invalid amount. |
| 204 | Wallet already exists. |
