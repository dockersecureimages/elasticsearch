# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.6.2-alpine-3.11.5
2020/04/01 15:41:55 [INFO] ▶ Start clair-scanner
2020/04/01 15:41:59 [INFO] ▶ Server listening on port 9279
2020/04/01 15:41:59 [INFO] ▶ Analyzing dac63304c60354902922613d675ec533c6e10879f72d49b7602575ae5d5f9257
2020/04/01 15:41:59 [INFO] ▶ Analyzing c93a3cb92e55d815ccc0a4ecfaa4cf21c5bfae319100e2235716c0944b88f349
2020/04/01 15:42:00 [INFO] ▶ Analyzing 8fc32bd3077cf51ab788108bcd7d845b0a7ae0669d4e0294ef37b2d5234eb05e
2020/04/01 15:42:00 [INFO] ▶ Analyzing 15020704a2cfbe1e87757803f7c0ef2ec4128dec0cd5c295144061ecf14aa959
2020/04/01 15:42:00 [INFO] ▶ Analyzing db8a5449d596d4fe61084eb75d19f700e69738882a0bbbb4263c6ab8364e0288
2020/04/01 15:42:00 [INFO] ▶ Image [secureimages/elasticsearch:7.6.2-alpine-3.11.5] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress secureimages/elasticsearch:7.6.2-alpine-3.11.5
2020-04-01T12:42:03.351Z        INFO    Need to update DB
2020-04-01T12:42:03.351Z        INFO    Downloading DB...
2020-04-01T12:42:15.818Z        INFO    Reopening DB...
2020-04-01T12:42:22.786Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.6.2-alpine-3.11.5 (alpine 3.11.5)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.6.2
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.6.2
2020/04/01 15:42:28 [INFO] ▶ Start clair-scanner
2020/04/01 15:42:39 [INFO] ▶ Server listening on port 9279
2020/04/01 15:42:39 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/04/01 15:42:40 [INFO] ▶ Analyzing 2d412aaa38b90f36e9c86a872c8a8bc3e8941b45d687b6eff96de3829d4833b2
2020/04/01 15:42:41 [INFO] ▶ Analyzing d32afbb0401e61d49436fee49e54c603bdaf2526983cedcc259b1228f2897239
2020/04/01 15:42:41 [INFO] ▶ Analyzing cabdf5da1004aa21265a854ed1f80062bffbcdf0f58fb0019796efd1a7319f41
2020/04/01 15:42:41 [INFO] ▶ Analyzing 2005b5128965adaaf5068aca13e4adc68977a4b768f7205cd52467530adb414a
2020/04/01 15:42:41 [INFO] ▶ Analyzing 88f46d617e0fec3c9df3f3e2cc177b22dbf00dd705d00da0ad9a9e1d563740d5
2020/04/01 15:42:41 [INFO] ▶ Analyzing a58957ae3fe330007dac3639135fe28e330debabf4409d70abd9b74e03c38d63
2020/04/01 15:42:41 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.2] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.5.3 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.6.2
2020-04-01T12:44:12.939Z        INFO    Need to update DB
2020-04-01T12:44:12.939Z        INFO    Downloading DB...
2020-04-01T12:44:41.359Z        INFO    Reopening DB...
2020-04-01T12:44:56.166Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.6.2 (centos 7.7.1908)
=====================================================================
Total: 635 (UNKNOWN: 0, LOW: 66, MEDIUM: 459, HIGH: 106, CRITICAL: 4)
```
