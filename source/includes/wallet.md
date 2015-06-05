# Wallet

## GET wallet

```shell
GET wallet
```

Returns general information about the wallet.

> Format

```json
{
  "exists": true,
  "isunlocked": false
}
```
## GET wallet/seed

```shell
GET wallet/seed
```

Return the 32-byte long base58-encoded wallet seed.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |
| 203 | Wallet is locked. |

## GET wallet/synchronize

```shell
GET wallet/synchronize
```

Rescans the blockchain for data.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## GET wallet/lock

```shell
GET wallet/lock
```

Locks the wallet.

Returns true/false depending on the fact if the wallet was already locked and if the password was correct.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |

## POST wallet

```shell
POST wallet
```

Creates a wallet using the given 32-byte long base58-encoded seed, password,recover flag and amount.

> Format

```json
{
  "seed": "FQgbSAm6swGbtqA3NE8PttijPhT4N3Ufh4bHFAkyVnQz",
  "password": "cookies",
  "recover": false,
  "amount": 10
}
```
### Errors

| Error | Description |
| --- | --- |
| 1 | Json error. |
| 103 | Invalid seed. |
| 104 | Invalid amount. |
| 204 | Wallet already exists. |

## POST wallet/unlock

```shell
POST wallet/unlock password
```

Unlocks the wallet using the given password.

Returns true/false depending on the fact if the password is correct.

### Errors

| Error | Description |
| --- | --- |
| 201 | Wallet does not exist. |
