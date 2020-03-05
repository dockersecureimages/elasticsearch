# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.6.1-alpine-3.11.3
2020/03/05 15:13:40 [INFO] ▶ Start clair-scanner
2020/03/05 15:13:44 [INFO] ▶ Server listening on port 9279
2020/03/05 15:13:44 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/03/05 15:13:45 [INFO] ▶ Analyzing 63f2aa1533d9c3a21f0d1a635909ef2fd6ac7091bb85703b7e75ef101a181ad6
2020/03/05 15:13:45 [INFO] ▶ Analyzing 637ac8f66b54f9906f646d9aff8d235d5abeaab48f35e66407901b2a9f823a6c
2020/03/05 15:13:45 [INFO] ▶ Analyzing cecb736c02eefce520841832b1d2b77e2b5c2b1da07f74c39ed023d15cce5b54
2020/03/05 15:13:45 [INFO] ▶ Analyzing e8238e2ce72a5e6a07e806d74456c8a3b71220865fd44de31021f93b5e2e0194
2020/03/05 15:13:46 [INFO] ▶ Image [secureimages/elasticsearch:7.6.1-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.4 --no-progress secureimages/elasticsearch:7.6.1-alpine-3.11.3
2020-03-05T13:14:01.279Z        INFO    Need to update DB
2020-03-05T13:14:01.279Z        INFO    Downloading DB...
2020-03-05T13:14:05.010Z        INFO    Reopening DB...
2020-03-05T13:14:09.478Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.6.1-alpine-3.11.3 (alpine 3.11.3)
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
2020/03/05 15:14:21 [INFO] ▶ Start clair-scanner
2020/03/05 15:14:38 [INFO] ▶ Server listening on port 9279
2020/03/05 15:14:38 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/03/05 15:14:39 [INFO] ▶ Analyzing 41d8e51dd58c59460f51f712804f9e3fc34fdf7c45624e3584e7d7004b07545e
2020/03/05 15:14:39 [INFO] ▶ Analyzing 38d270adc222c647174f5216a2edf0a1ac4c5d72f56877f849073154a9d69514
2020/03/05 15:14:39 [INFO] ▶ Analyzing 93a3ecd58ef0a78f121cd2eb5d0e9109a87692b1a7304ef67d9307f90e6bdaff
2020/03/05 15:14:40 [INFO] ▶ Analyzing 89098f785bbb0b02b83f8babb4c3577d69362b8108079034941847f10e1bfc55
2020/03/05 15:14:40 [INFO] ▶ Analyzing c0f33c2ff6d63db2eeeec645b34045b1b6acf3e9ef3666a1717fa072125e975a
2020/03/05 15:14:40 [INFO] ▶ Analyzing 4377444a88f3f68eaec31b9db6adf2f9463118de1edcedaf1423cd2698d2d19d
2020/03/05 15:14:40 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.4 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.6.1
2020-03-05T13:14:43.947Z        INFO    Need to update DB
2020-03-05T13:14:43.947Z        INFO    Downloading DB...
2020-03-05T13:14:48.785Z        INFO    Reopening DB...
2020-03-05T13:15:19.594Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.6.1 (centos 7.7.1908)
=====================================================================
Total: 629 (UNKNOWN: 0, LOW: 63, MEDIUM: 460, HIGH: 102, CRITICAL: 4)
```
