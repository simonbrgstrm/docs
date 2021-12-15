
---
title: "network"
linkTitle: "network"
date: 2017-01-05
description: >
  Network related commands.
---

{{% pageinfo %}}
man **command**.
{{% /pageinfo %}}


Network.

### netcat

```shell
nc -l 8080 
```

### netstat < ss

```shell
netstat -tlpn
ss -tlpn
```

```shell
netstat -tn | cut -d " " -f 23 | cut -d ":" -f 1 | sort | uniq
```

### nmap

```shell
nmap -sP 192.168.0.0/24
```
```shell
nmap 192.168.100.10
```


### nslookup

```shell
nslookup google.com
```

```shell
nslookup 142.250.74.78
```

### ping

```shell
ping google.com
```

### traceroute

```shell
traceroute google.com
```
