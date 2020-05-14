# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~405MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.7.0-alpine-3.11.6
2020/05/14 11:48:28 [INFO] ▶ Start clair-scanner
2020/05/14 11:48:31 [INFO] ▶ Server listening on port 9279
2020/05/14 11:48:31 [INFO] ▶ Analyzing a5304328ea0f44bd1ac8bb5416ad6b7cc3b747ac232c6af66d7d9f12e9854344
2020/05/14 11:48:32 [INFO] ▶ Analyzing aedc0d41cceccff564abdb4e6b4cdc7271b24f9b22cd5374ba576dcaf0506c78
2020/05/14 11:48:32 [INFO] ▶ Analyzing 0529e4ce221c6427eb124ac5db353da1e038e79b664d3f8a72af07fd9d3ebef3
2020/05/14 11:48:32 [INFO] ▶ Analyzing c2332cee3a756ff8c2d8abba1950b01185c1abc11713853bec6082787d7e7df2
2020/05/14 11:48:32 [INFO] ▶ Analyzing cfb48acdfab9bba91b40d8feb933a30a6a30cdc93565564dd7609f9520cb7b10
2020/05/14 11:48:32 [INFO] ▶ Image [secureimages/elasticsearch:7.7.0-alpine-3.11.6] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.7.0 --no-progress secureimages/elasticsearch:7.7.0-alpine-3.11.6
2020-05-14T08:48:47.279Z        INFO    Need to update DB
2020-05-14T08:48:47.279Z        INFO    Downloading DB...
2020-05-14T08:48:55.603Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.7.0-alpine-3.11.6 (alpine 3.11.6)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~757MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.7.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.7.0
2020/05/14 11:49:29 [INFO] ▶ Start clair-scanner
2020/05/14 11:49:41 [INFO] ▶ Server listening on port 9279
2020/05/14 11:49:41 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/05/14 11:49:42 [INFO] ▶ Analyzing a98618dd07d42a15e9fd4869ee5a64481d747829c3240427e925004d0f31ad0a
2020/05/14 11:49:42 [INFO] ▶ Analyzing fcca8669f31d89c7b99d2f132d34749a2052d206aefd874a4b4eec4f18e41599
2020/05/14 11:49:43 [INFO] ▶ Analyzing 89b52368113a91aa1c85e8b0dc8f3e847ca3621caa7ded9d3099419d76214080
2020/05/14 11:49:43 [INFO] ▶ Analyzing d3aaa43cac29f531345536488f8121d245b03c5cb0a401ba85bee029d79d3807
2020/05/14 11:49:43 [INFO] ▶ Analyzing b3a1cdf14d720a2dd53174af1423e490dd1d14a3f856370f4b163298c725c1e4
2020/05/14 11:49:43 [INFO] ▶ Analyzing 931f48944c3a48d611b9f3d0506800f3f3c68b5ae46127cdc997ce65204d4b77
2020/05/14 11:49:43 [INFO] ▶ Analyzing 08a3a964fbe2de0667534aa0853ed00da0f0248d61972d735e35e87cccd0b24c
2020/05/14 11:49:43 [INFO] ▶ Analyzing 5141f9c910dff72110dd64fd1aa7d8f6d6fa03d6023c8c090e0a11ddc82392c7
2020/05/14 11:49:43 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.7.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.7.0 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.7.0
2020-05-14T08:49:45.589Z        INFO    Need to update DB
2020-05-14T08:49:45.589Z        INFO    Downloading DB...
2020-05-14T08:50:03.290Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.7.0 (centos 7.8.2003)
=====================================================================
Total: 607 (UNKNOWN: 0, LOW: 365, MEDIUM: 237, HIGH: 5, CRITICAL: 0)
```
