# [Dockerfile.freeradius](https://github.com/n138-kz/Dockerfile.freeradius)

## Activity

[![GitHub repo license](https://img.shields.io/github/license/n138-kz/Dockerfile.freeradius)](/LICENSE)
[![GitHub repo size](https://img.shields.io/github/repo-size/n138-kz/Dockerfile.freeradius)](/../../)
[![GitHub repo file count](https://img.shields.io/github/directory-file-count/n138-kz/Dockerfile.freeradius)](/../../)
[![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/n138-kz/Dockerfile.freeradius)](/../../)
[![GitHub last commit](https://img.shields.io/github/last-commit/n138-kz/Dockerfile.freeradius)](/../../commits)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/w/n138-kz/Dockerfile.freeradius)](/../../commits)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/t/n138-kz/Dockerfile.freeradius)](/../../commits)
[![GitHub issues](https://img.shields.io/github/issues/n138-kz/Dockerfile.freeradius)](/../../issues)
[![GitHub issues closed](https://img.shields.io/github/issues-closed/n138-kz/Dockerfile.freeradius)](/../../issues)
[![GitHub pull requests closed](https://img.shields.io/github/issues-pr-closed/n138-kz/Dockerfile.freeradius)](/../../pulls)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/n138-kz/Dockerfile.freeradius)](/../../pulls)
[![GitHub language count](https://img.shields.io/github/languages/count/n138-kz/Dockerfile.freeradius)](/../../)
[![GitHub top language](https://img.shields.io/github/languages/top/n138-kz/Dockerfile.freeradius)](/../../)

## Refs

- [![](https://www.google.com/s2/favicons?size=64&domain=https://hub.docker.com)freeradius/freeradius-server](https://hub.docker.com/r/freeradius/freeradius-server)
- [![](https://www.google.com/s2/favicons?size=64&domain=https://github.com)Dockerfile](https://github.com/n138-kz/Dockerfile/)
- [![](https://www.google.com/s2/favicons?size=64&domain=https://github.com)Dockerfile.freeradius](https://github.com/n138-kz/Dockerfile.freeradius/)

## freeradius/freeradius-server

### add user

Edit the [authorize](/build-core/raddb/mods-config/files/authorize)

```conf
bob	Cleartext-Password := "test"
```

|name|description|
|:-|:-|
|`bob`|test username|
|`test`|password of test user|

### add client segment

Edit the [clients.conf](/build-core/raddb/clients.conf)

```conf
client name {
    ipaddr = 172.17.0.0/16
    secret = testing123
}
```

### pre-shared-key

Edit the `secret` in [clients.conf](/build-core/raddb/clients.conf)

```conf
client name {
    ipaddr = 172.17.0.0/16
    secret = testing123
}
```

### Test run

```sh
docker compose build --no-cache
docker compose up -d
```

```sh
docker compose exec -it freeradius-core radtest bob test 127.0.0.1 0 testing123
```

|name|description|
|:-|:-|
|`bob`|test username|
|`test`|password of test user|
|`127.0.0.1`|address of server|
|`0`|port number of local(0=auto)|
|`testing123`|pre-shared-key|

```sh
Usage: radtest [OPTIONS] user passwd radius-server[:port] nas-port-number secret [ppphint] [nasname]
        -d RADIUS_DIR       Set radius directory
        -t <type>           Set authentication method
                            type can be pap, chap, mschap, or eap-md5
        -P protocol         Select udp (default) or tcp
        -x                  Enable debug output
        -4                  Use IPv4 for the NAS address (default)
        -6                  Use IPv6 for the NAS address
```

#### OK pattern

```log
root@8d0831a60970:/# radtest bob test 127.0.0.1 0 testing123
Sent Access-Request Id 150 from 0.0.0.0:36661 to 127.0.0.1:1812 length 73
        User-Name = "bob"
        User-Password = "test"
        NAS-IP-Address = 172.24.0.2
        NAS-Port = 0
        Message-Authenticator = 0x00
        Cleartext-Password = "test"
Received Access-Accept Id 150 from 127.0.0.1:1812 to 127.0.0.1:36661 length 38
        Message-Authenticator = 0x4a7750799c95aabc804128b2524dfe13
```

## Github RestAPI

```http
GET https://api.github.com/repos/n138-kz/Dockerfile.freeradius
```
[n138-kz/Dockerfile.freeradius](https://api.github.com/repos/n138-kz/Dockerfile.freeradius) (Public repos only)

## License

[Copyright (c) 2025 Yuu Komiya (n138), Under MIT License](LICENSE)  
