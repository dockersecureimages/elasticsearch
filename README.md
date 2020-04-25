# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~393MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.6.2-alpine-3.11.6
2020/04/25 12:11:30 [INFO] ▶ Start clair-scanner
2020/04/25 12:11:33 [INFO] ▶ Server listening on port 9279
2020/04/25 12:11:33 [INFO] ▶ Analyzing a5304328ea0f44bd1ac8bb5416ad6b7cc3b747ac232c6af66d7d9f12e9854344
2020/04/25 12:11:33 [INFO] ▶ Analyzing f6d696d3336a78027ce05d4ef95d271f44b4de7ef0725647d17d6eac9cb182c2
2020/04/25 12:11:34 [INFO] ▶ Analyzing f7e7bdbbd465941d1083b1f6b46b950db304daf94971a926fe4178a2271f7ac4
2020/04/25 12:11:34 [INFO] ▶ Analyzing 88122684df3a241049d2d3365c16aaac0a72c6b906b56e9bfb25d85c28f9f0ee
2020/04/25 12:11:34 [INFO] ▶ Analyzing b308b79661f131f2aa5cf2e2e606db96b85cf4872f6068b5cdd3dabd1027871a
2020/04/25 12:11:34 [INFO] ▶ Image [secureimages/elasticsearch:7.6.2-alpine-3.11.6] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.6.0 --no-progress secureimages/elasticsearch:7.6.2-alpine-3.11.6
2020-04-25T09:11:38.872Z        INFO    Need to update DB
2020-04-25T09:11:38.872Z        INFO    Downloading DB...
2020-04-25T09:11:47.739Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.6.2-alpine-3.11.6 (alpine 3.11.6)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~791MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.6.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.6.2
2020/04/25 12:11:53 [INFO] ▶ Start clair-scanner
2020/04/25 12:12:05 [INFO] ▶ Server listening on port 9279
2020/04/25 12:12:05 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/04/25 12:12:06 [INFO] ▶ Analyzing 2d412aaa38b90f36e9c86a872c8a8bc3e8941b45d687b6eff96de3829d4833b2
2020/04/25 12:12:07 [INFO] ▶ Analyzing d32afbb0401e61d49436fee49e54c603bdaf2526983cedcc259b1228f2897239
2020/04/25 12:12:07 [INFO] ▶ Analyzing cabdf5da1004aa21265a854ed1f80062bffbcdf0f58fb0019796efd1a7319f41
2020/04/25 12:12:07 [INFO] ▶ Analyzing 2005b5128965adaaf5068aca13e4adc68977a4b768f7205cd52467530adb414a
2020/04/25 12:12:07 [INFO] ▶ Analyzing 88f46d617e0fec3c9df3f3e2cc177b22dbf00dd705d00da0ad9a9e1d563740d5
2020/04/25 12:12:07 [INFO] ▶ Analyzing a58957ae3fe330007dac3639135fe28e330debabf4409d70abd9b74e03c38d63
2020/04/25 12:12:07 [WARN] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.2] contains 12 total vulnerabilities
2020/04/25 12:12:07 [ERRO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.2] contains 12 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.6.0 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.6.2
2020-04-25T09:12:09.419Z        INFO    Need to update DB
2020-04-25T09:12:09.419Z        INFO    Downloading DB...
2020-04-25T09:12:29.149Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.6.2 (centos 7.7.1908)
=====================================================================
Total: 633 (UNKNOWN: 0, LOW: 64, MEDIUM: 459, HIGH: 106, CRITICAL: 4)
```
