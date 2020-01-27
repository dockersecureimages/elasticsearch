# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.5.2-alpine-3.11.3
2020/01/27 11:02:01 [INFO] ▶ Start clair-scanner
2020/01/27 11:02:04 [INFO] ▶ Server listening on port 9279
2020/01/27 11:02:04 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/01/27 11:02:04 [INFO] ▶ Analyzing 20d63ede7c53b397e00b21d522dd739a08ff0580207cc59db6e97ffaf4ff3683
2020/01/27 11:02:04 [INFO] ▶ Analyzing 8903ae91211b9378d72b71e9e5f2c2312be94d742678a583bf3d1d9a1654b9d2
2020/01/27 11:02:04 [INFO] ▶ Analyzing 71d64bb9dbb712554890c8b7f9b3166e4c3891dc3f1a080eeb220c21f274964f
2020/01/27 11:02:05 [INFO] ▶ Analyzing a46a5ddea47cb776ae5200f4fca46477bbd1f527ba413abf3df6283418290e06
2020/01/27 11:02:05 [INFO] ▶ Image [secureimages/elasticsearch:7.5.2-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress secureimages/elasticsearch:7.5.2-alpine-3.11.3
2020-01-27T09:02:12.393Z        INFO    Need to update DB
2020-01-27T09:02:12.393Z        INFO    Downloading DB...
2020-01-27T09:02:15.919Z        INFO    Reopening DB...
2020-01-27T09:02:19.875Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.5.2-alpine-3.11.3 (alpine 3.11.3)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.5.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.5.2
2020/01/27 11:02:26 [INFO] ▶ Start clair-scanner
2020/01/27 11:02:37 [INFO] ▶ Server listening on port 9279
2020/01/27 11:02:37 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/01/27 11:02:37 [INFO] ▶ Analyzing 39330db3630085112b189ac682056b72bf9afa42b9683c7c3f61b2d6ee907ad0
2020/01/27 11:02:37 [INFO] ▶ Analyzing 243591fd692551d7f2400f2be2147ae82c3d01700ceaae0fe11f1cd9909e7eb6
2020/01/27 11:02:37 [INFO] ▶ Analyzing 4a1fc2425a9fa478b9e1bf95fa73e9d3e8a72d27b5175664e5ebb273ebf8286c
2020/01/27 11:02:37 [INFO] ▶ Analyzing 67c18972772c4a420627f816cc111061e87419ee3385c3bf47f4223c94d69ef8
2020/01/27 11:02:37 [INFO] ▶ Analyzing 338c28a24559afe826ab1879288da727e889e737dc42791cb9b5d1636013ecf4
2020/01/27 11:02:37 [INFO] ▶ Analyzing 6e54d395971473a7528d6203198b652c8e7fed8584c0f8aba4c4067bf29f9b27
2020/01/27 11:02:37 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.5.2] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.5.2
2020-01-27T09:02:39.971Z        INFO    Need to update DB
2020-01-27T09:02:39.971Z        INFO    Downloading DB...
2020-01-27T09:02:43.855Z        INFO    Reopening DB...
2020-01-27T09:02:58.908Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.5.2 (centos 7.7.1908)
=====================================================================
Total: 627 (UNKNOWN: 0, LOW: 61, MEDIUM: 457, HIGH: 103, CRITICAL: 6)
```
