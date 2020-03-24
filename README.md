# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.6.1-alpine-3.11.5
2020/03/24 18:48:12 [INFO] ▶ Start clair-scanner
2020/03/24 18:48:15 [INFO] ▶ Server listening on port 9279
2020/03/24 18:48:15 [INFO] ▶ Analyzing dac63304c60354902922613d675ec533c6e10879f72d49b7602575ae5d5f9257
2020/03/24 18:48:15 [INFO] ▶ Analyzing 0f641f9721803719e1b8ad07a216d0a9a7515506641aa6ad48170ff8ccc173a9
2020/03/24 18:48:16 [INFO] ▶ Analyzing 5b39855e5bb9fdc08cac166904e23a03cf59b7c29b99697855b369f02bcdcafe
2020/03/24 18:48:16 [INFO] ▶ Analyzing b448fc266023bc79551b68ea659e7635c6e1cdd3c074eeaf66bb3ed4ac55ebd5
2020/03/24 18:48:16 [INFO] ▶ Analyzing 253f5fa3be1074922ecb00ace89eabf044ac569d3c552328c4cffcb78a0d8ec0
2020/03/24 18:48:16 [INFO] ▶ Image [secureimages/elasticsearch:7.6.1-alpine-3.11.5] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress secureimages/elasticsearch:7.6.1-alpine-3.11.5
2020-03-24T16:48:22.860Z        INFO    Need to update DB
2020-03-24T16:48:22.860Z        INFO    Downloading DB...
2020-03-24T16:48:26.932Z        INFO    Reopening DB...
2020-03-24T16:48:33.709Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.6.1-alpine-3.11.5 (alpine 3.11.5)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.6.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.6.1
2020/03/24 18:48:38 [INFO] ▶ Start clair-scanner
2020/03/24 18:48:50 [INFO] ▶ Server listening on port 9279
2020/03/24 18:48:50 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/03/24 18:48:50 [INFO] ▶ Analyzing 41d8e51dd58c59460f51f712804f9e3fc34fdf7c45624e3584e7d7004b07545e
2020/03/24 18:48:52 [INFO] ▶ Analyzing 38d270adc222c647174f5216a2edf0a1ac4c5d72f56877f849073154a9d69514
2020/03/24 18:48:52 [INFO] ▶ Analyzing 93a3ecd58ef0a78f121cd2eb5d0e9109a87692b1a7304ef67d9307f90e6bdaff
2020/03/24 18:48:52 [INFO] ▶ Analyzing 89098f785bbb0b02b83f8babb4c3577d69362b8108079034941847f10e1bfc55
2020/03/24 18:48:52 [INFO] ▶ Analyzing c0f33c2ff6d63db2eeeec645b34045b1b6acf3e9ef3666a1717fa072125e975a
2020/03/24 18:48:52 [INFO] ▶ Analyzing 4377444a88f3f68eaec31b9db6adf2f9463118de1edcedaf1423cd2698d2d19d
2020/03/24 18:48:52 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.6.1
2020-03-24T16:48:54.549Z        INFO    Need to update DB
2020-03-24T16:48:54.549Z        INFO    Downloading DB...
2020-03-24T16:49:00.594Z        INFO    Reopening DB...
2020-03-24T16:49:14.915Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.6.1 (centos 7.7.1908)
=====================================================================
Total: 637 (UNKNOWN: 0, LOW: 67, MEDIUM: 460, HIGH: 106, CRITICAL: 4)
```
