# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~401MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.7.1-alpine-3.12.0
2020/06/11 13:42:02 [INFO] ▶ Start clair-scanner
2020/06/11 13:42:05 [INFO] ▶ Server listening on port 9279
2020/06/11 13:42:05 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/06/11 13:42:05 [INFO] ▶ Analyzing cc8f26b81e798fe9a8439f30beadacf4576505cb13fbe2f77be13daf33bd4c29
2020/06/11 13:42:06 [INFO] ▶ Analyzing 45c1f802a21bf5ee9a93ae3189bbd2876d6090905ab7f28dee66c2291b22ded3
2020/06/11 13:42:06 [INFO] ▶ Analyzing 5ca1257456fa2da210840e3e6f1d1bd7b20db31cd86d0dd05b50426fcb3b6a7c
2020/06/11 13:42:06 [INFO] ▶ Analyzing 035d8d5bc6c0c30017f3a131df2610d62c2de29c4f1e688a35eb0fbc847e64fb
2020/06/11 13:42:06 [INFO] ▶ Image [secureimages/elasticsearch:7.7.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress secureimages/elasticsearch:7.7.1-alpine-3.12.0
2020-06-11T10:42:10.194Z        INFO    Need to update DB
2020-06-11T10:42:10.194Z        INFO    Downloading DB...
2020-06-11T10:42:19.769Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.7.1-alpine-3.12.0 (alpine 3.12.0)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~804MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.7.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.7.1
2020/06/11 13:42:24 [INFO] ▶ Start clair-scanner
2020/06/11 13:42:52 [INFO] ▶ Server listening on port 9279
2020/06/11 13:42:52 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/06/11 13:42:52 [INFO] ▶ Analyzing a98618dd07d42a15e9fd4869ee5a64481d747829c3240427e925004d0f31ad0a
2020/06/11 13:42:52 [INFO] ▶ Analyzing 4b78fdfb180b2adabefd1214c43551debb4f5530f0271261614610ab7536d43e
2020/06/11 13:42:53 [INFO] ▶ Analyzing 7f8b3dd8aba91919e24c1269312ef93cadf23ae5a72ff6f9f7c3cb8458a6a8d7
2020/06/11 13:42:53 [INFO] ▶ Analyzing 193921223d966c2fc11e37b39ce5a3a1130f3a34f8b620195ca6a8a196e18e17
2020/06/11 13:42:53 [INFO] ▶ Analyzing eae34869fdf4033334c8a6a0190119b61b720ae7efe6692dbc21228664955f1d
2020/06/11 13:42:53 [INFO] ▶ Analyzing 15b3cc717a9b283b09400101a308d253766e62a128f776f4f2f7392e4f2b9728
2020/06/11 13:42:53 [INFO] ▶ Analyzing db58c5e2d500f8a2c3644f07850956b89dde1f4a6a39ba90f0ba8659967f53ce
2020/06/11 13:42:53 [INFO] ▶ Analyzing 39f67a80381552a336cbba206526704ff38a86438cb98d4db04ea09703356684
2020/06/11 13:42:53 [WARN] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.7.1] contains 1 total vulnerabilities
2020/06/11 13:42:53 [ERRO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.7.1] contains 1 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.7.1
2020-06-11T10:42:56.052Z        INFO    Need to update DB
2020-06-11T10:42:56.052Z        INFO    Downloading DB...
2020-06-11T10:43:23.509Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.7.1 (centos 7.8.2003)
=====================================================================
Total: 617 (UNKNOWN: 0, LOW: 366, MEDIUM: 244, HIGH: 7, CRITICAL: 0)
```
