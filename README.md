# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~405MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.8.1-alpine-3.12.0
2020/07/31 17:09:11 [INFO] ▶ Start clair-scanner
2020/07/31 17:09:15 [INFO] ▶ Server listening on port 9279
2020/07/31 17:09:15 [INFO] ▶ Analyzing 76de98d374759ed05698adec9aa042db7bc0f62c25fb612c0f9be1419a581421
2020/07/31 17:09:15 [INFO] ▶ Analyzing abfef95fe8054b9a3a07b0093b3768d2d88d0d189bb099bca1ac144852766f3c
2020/07/31 17:09:15 [INFO] ▶ Analyzing 95c919816e9d1f489e65d04addf609519a805ee3881194d6b5127c538fe10762
2020/07/31 17:09:15 [INFO] ▶ Analyzing b14c4fab434764130dc2a1e5b4aa261e82709cb1205244f60c51cf3e867f89fa
2020/07/31 17:09:15 [INFO] ▶ Analyzing 284f9ef98ed22f1e389a62755cfb978a4344376ff85b9ecd55dc36e2e81a59ff
2020/07/31 17:09:15 [INFO] ▶ Image [secureimages/elasticsearch:7.8.1-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.1 --no-progress secureimages/elasticsearch:7.8.1-alpine-3.12.0
2020-07-31T14:09:18.890Z        INFO    Need to update DB
2020-07-31T14:09:18.890Z        INFO    Downloading DB...
2020-07-31T14:09:28.080Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.8.1-alpine-3.12.0 (alpine 3.12.0)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~811MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.8.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.8.1
2020/07/31 17:09:32 [INFO] ▶ Start clair-scanner
2020/07/31 17:09:43 [INFO] ▶ Server listening on port 9279
2020/07/31 17:09:43 [INFO] ▶ Analyzing c53e4ebe5d0a558645655ec8b3e667ed7cae98e3252a08914c1ab5a08cef4da0
2020/07/31 17:09:43 [INFO] ▶ Analyzing 511b300a9cc7ee9b8ac8b751953d9f1d56047af10dd6c026c5a69e8f5ea6144c
2020/07/31 17:09:43 [INFO] ▶ Analyzing 0970aa65c72b58432ddefc463ecf31d6806a786da3d59e2cbd8d37b9aa86514e
2020/07/31 17:09:45 [INFO] ▶ Analyzing b6dd68a7ba84bf9283d5aed46abd7b60c214e336d2eb0655efa6cd09187bb77d
2020/07/31 17:09:45 [INFO] ▶ Analyzing f86acaf90db656b9683d3aff83826ff62a8c9e534e6788035618423a1f23b95f
2020/07/31 17:09:45 [INFO] ▶ Analyzing 91f0718aa0226aa1ed2ab5a6f99708a43741781219aa2d1f15a2ee7445c3de28
2020/07/31 17:09:45 [INFO] ▶ Analyzing 4033f4cb079b69fcede0ba717a9e21d4fb1a500541662f827ed13aa7123ac952
2020/07/31 17:09:45 [INFO] ▶ Analyzing 6918d3830b362ec852abb91d0406b2ff7fd5770c42a73318434a99529cc75f94
2020/07/31 17:09:45 [INFO] ▶ Analyzing e8afe431bfec59ef5fd4704cc158fd49983b92bca403e4ced59742ecf3027dba
2020/07/31 17:09:45 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.8.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.1 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.8.1
2020-07-31T14:09:47.657Z        INFO    Need to update DB
2020-07-31T14:09:47.657Z        INFO    Downloading DB...
2020-07-31T14:10:04.686Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.8.1 (centos 7.8.2003)
=====================================================================
Total: 624 (UNKNOWN: 0, LOW: 365, MEDIUM: 254, HIGH: 5, CRITICAL: 0)
```
