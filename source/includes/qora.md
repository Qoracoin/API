# Qora

Provides general information about the state of the application and the ability to close the application.

## Stop

```shell
curl "http://127.0.0.1:9085/qora/stop"
```

```http
GET qora/stop HTTP/1.1
Host: 127.0.0.1:9085
```

Will stop the application. This command might not be able to return a http OK message.

### REQUEST

`GET qora/stop`

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/qora/stop" target="blank">http://127.0.0.1:9085/qora/stop</a>
</aside>

## Status

```shell
curl "http://127.0.0.1:9085/qora/status"
```

```http
GET /qora/status HTTP/1.1
Host: 127.0.0.1:9085
```

Returns the status of the application

### REQUEST

`GET qora/status`

| Status | Value |
| --- | --- |
| 0 | No connections |
| 1 | Synchronizing |
| 2 | Oke |

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/qora/status" target="blank">http://127.0.0.1:9085/qora/status</a>
</aside>

## Forging Status

```shell
curl "http://127.0.0.1:9085/qora/status/forging"
```

```http
GET qora/status/forging HTTP/1.1
Host: 127.0.0.1:9085
```

Returns the forging status

### REQUEST

`GET qora/status/forging`

| Status | Value |
| --- | --- |
| 0 | Forging Disabled |
| 1 | Forging Enabled |
| 2 | Forging |

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/qora/status/forging" target="blank">http://127.0.0.1:9085/qora/status/forging</a>
</aside>

## Is Up To Date  

```shell
curl "http://127.0.0.1:9085/qora/isuptodate"
```

```http
GET qora/isuptodate HTTP/1.1
Host: 127.0.0.1:9085
```

Returns a boolean that shows if the application is synchronized with the network.

### REQUEST

`GET qora/isuptodate`

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/qora/isuptodate" target="blank">http://127.0.0.1:9085/qora/isuptodate</a>
</aside>

## Version

```shell
curl "http://127.0.0.1:9085/version"
```

```http
GET version HTTP/1.1
Host: 127.0.0.1:9085
```

Returns the current version and the build date of the installed application.

### REQUEST

`GET version`

<aside class="notice">
You can execute this command by clicking here: <a href="http://127.0.0.1:9085/version" target="blank">http://127.0.0.1:9085/version</a>
</aside>
