# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~406MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.9.1-alpine-3.12.0
2020/09/04 16:27:17 [INFO] ▶ Start clair-scanner
2020/09/04 16:27:21 [INFO] ▶ Server listening on port 9279
2020/09/04 16:27:21 [INFO] ▶ Analyzing 31609b718dd2bed92b93b1ab00c0ff67419a3121d0144bef0dc6ca49718820a7
2020/09/04 16:27:21 [INFO] ▶ Analyzing f9792c1b8a96eba955f94c7962deb50200d00df64999245828bc2fac715545e5
2020/09/04 16:27:21 [INFO] ▶ Analyzing e0132bd2d5f3df8dba1658cde87b5279ccb08bc2a17d84c5970082694a103d52
2020/09/04 16:27:21 [INFO] ▶ Analyzing 097c68747813c36689126465e9f7798abe575aaed1829b712cc3fd0bc9295f1c
2020/09/04 16:27:21 [INFO] ▶ Analyzing 235b0381ceb03a860cb48df37679ac6ae308b1f2e1444adfa3e4b3290bd64659
2020/09/04 16:27:21 [INFO] ▶ Image [secureimages/elasticsearch:7.9.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress secureimages/elasticsearch:7.9.1-alpine-3.12.0
2020-09-04T16:27:26.547Z        INFO    Need to update DB
2020-09-04T16:27:26.547Z        INFO    Downloading DB...
2020-09-04T16:27:35.543Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.9.1-alpine-3.12.0 (alpine 3.12.0)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~762MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.9.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.9.1
2020/09/04 16:27:40 [INFO] ▶ Start clair-scanner
2020/09/04 16:27:52 [INFO] ▶ Server listening on port 9279
2020/09/04 16:27:52 [INFO] ▶ Analyzing 33b5e87a65b65985a0445827bd27436b3467bb578d1b1cc2aa0b6000685fb4bf
2020/09/04 16:27:52 [INFO] ▶ Analyzing 5c23f234d53f866288a68554128d2089e92ed29335edd1a10fec469de95e8803
2020/09/04 16:27:52 [INFO] ▶ Analyzing a7d386635f8f3ffecc6ddbdfe9cc2e74b1669a441bda25e565cc52bf4956dd42
2020/09/04 16:27:52 [INFO] ▶ Analyzing c442b6a88e80cb2b0a4109d37fc6082dd6bc1eb88062c8132548cacefe44b550
2020/09/04 16:27:52 [INFO] ▶ Analyzing d497ec459df14f15b8368ff4f01cb397af103a664b870f92086660083528d475
2020/09/04 16:27:53 [INFO] ▶ Analyzing 71fa9eba8ff5789f17af9ad8b8f6d46e7a7de07f85c1d2c283c6b77951718c0a
2020/09/04 16:27:53 [INFO] ▶ Analyzing 3055382edd06f15fa9dec481bcf352c984cb9003a4f7fe79dc00f95ae7df528f
2020/09/04 16:27:53 [INFO] ▶ Analyzing e09f015cd8b6a47ae2959a3e00c8ce90686f1180eb15ef1727e81b08b2d04408
2020/09/04 16:27:53 [INFO] ▶ Analyzing 625b336910b3e637c4c127daf84ee485ce8063f7a6424b0025e78bbd49238b07
2020/09/04 16:27:53 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.9.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.9.1
2020-09-04T16:27:54.468Z        INFO    Need to update DB
2020-09-04T16:27:54.468Z        INFO    Downloading DB...
2020-09-04T16:28:09.978Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.9.1 (centos 7.8.2003)
=====================================================================
Total: 642 (UNKNOWN: 0, LOW: 369, MEDIUM: 268, HIGH: 5, CRITICAL: 0)
```
