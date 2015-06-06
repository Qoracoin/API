# Seed

To generate a random base58 encoded seed. These seeds can be used to create a wallet or to import an account.

## Get Seed

```shell
curl "http://127.0.0.1:9085/seed"
```

```http
GET seed HTTP/1.1
Host: 127.0.0.1:9085
```

Returns a base58 encoded random seed of 32 bytes

### REQUEST

`GET seed`

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/seed" target="blank">http://127.0.0.1:9085/seed</a>
</aside>

## Get Seed By Length

```shell
curl "http://127.0.0.1:9085/seed/{length}"
```

```http
GET seed/{length} HTTP/1.1
Host: 127.0.0.1:9085
```

Use the optional parameter length to request a seed of {length} bytes.

### REQUEST

`GET seed/{length}`  
