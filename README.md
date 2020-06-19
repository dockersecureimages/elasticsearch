# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~406MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.8.0-alpine-3.12.0
2020/06/19 21:29:44 [INFO] ▶ Start clair-scanner
2020/06/19 21:29:48 [INFO] ▶ Server listening on port 9279
2020/06/19 21:29:48 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/06/19 21:29:48 [INFO] ▶ Analyzing f08d803e6073940d0c81e5c10637643d015860ff33cf794cad04367237e44f7e
2020/06/19 21:29:48 [INFO] ▶ Analyzing ce8aa3e5347bd5e5604477e66a4921746309d0b28f35e212340ee6692caee635
2020/06/19 21:29:48 [INFO] ▶ Analyzing 41e37e8ce76be0bc9bb4ae664ef9394b29a46bc8a73c7d54e5b77a2a4aae9360
2020/06/19 21:29:48 [INFO] ▶ Analyzing 52ac3fd49b1617ad499e73b6f8654fe933efc15b3cc30986c13314836e220583
2020/06/19 21:29:48 [INFO] ▶ Image [secureimages/elasticsearch:7.8.0-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress secureimages/elasticsearch:7.8.0-alpine-3.12.0
2020-06-19T18:29:53.114Z        INFO    Need to update DB
2020-06-19T18:29:53.114Z        INFO    Downloading DB...
2020-06-19T18:30:02.020Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.8.0-alpine-3.12.0 (alpine 3.12.0)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~810MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.8.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.8.0
2020/06/19 21:30:07 [INFO] ▶ Start clair-scanner
2020/06/19 21:30:18 [INFO] ▶ Server listening on port 9279
2020/06/19 21:30:18 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/06/19 21:30:18 [INFO] ▶ Analyzing bd526e81324a67c258143040fd420f5b2745dd17c40732e51e271d17b665e082
2020/06/19 21:30:18 [INFO] ▶ Analyzing c360dddd9b8455430e796e4e36a070e56c348a6799889c1ce0a808eefae8c0bf
2020/06/19 21:30:19 [INFO] ▶ Analyzing 3d03d51a432a4eaa7d9096e4a1648a27ed2baa07a1525c6bfa365ad35c774a73
2020/06/19 21:30:19 [INFO] ▶ Analyzing 6c6ee729a4d7af54d279fab992d8dddda7bbc2f7f861efab55e5c8dcf0ed7bce
2020/06/19 21:30:20 [INFO] ▶ Analyzing 32cc3216ae1861810421f64af615183187b1bc9c11ddff17d66ce1adb33e7c41
2020/06/19 21:30:20 [INFO] ▶ Analyzing 846e6b6093298ea6da3663996dac9d1cdae138d0a4825b2fd17cfe6cd031a24e
2020/06/19 21:30:20 [INFO] ▶ Analyzing f8c7e549aa46467293de7d9161c2927a29dbca965cf5bc3f70aa3a45e5f44654
2020/06/19 21:30:20 [INFO] ▶ Analyzing 4b9b0fa810b440ebc8b3f6defb73d30137e9409fbb34e294ddeed44466f906b8
2020/06/19 21:30:20 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.8.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.9.1 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.8.0
2020-06-19T18:30:22.251Z        INFO    Need to update DB
2020-06-19T18:30:22.251Z        INFO    Downloading DB...
2020-06-19T18:30:39.428Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.8.0 (centos 7.8.2003)
=====================================================================
Total: 621 (UNKNOWN: 0, LOW: 364, MEDIUM: 252, HIGH: 5, CRITICAL: 0)
```
