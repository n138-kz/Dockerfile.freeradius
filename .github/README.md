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
|`text`|password of test user|

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

## Github RestAPI

```http
GET https://api.github.com/repos/n138-kz/Dockerfile.freeradius
```
[n138-kz/Dockerfile.freeradius](https://api.github.com/repos/n138-kz/Dockerfile.freeradius) (Public repos only)

## License

[Copyright (c) 2025 Yuu Komiya (n138), Under MIT License](LICENSE)  
