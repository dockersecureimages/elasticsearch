# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.6.0-alpine-3.11.3
2020/02/11 20:12:48 [INFO] ▶ Start clair-scanner
2020/02/11 20:12:52 [INFO] ▶ Server listening on port 9279
2020/02/11 20:12:52 [INFO] ▶ Analyzing c60e0e5e0b8cce2c353f5af4186afb2cde56680bc78ff165fd2368a003530178
2020/02/11 20:12:52 [INFO] ▶ Analyzing 836a5da40ab217117ca645e5acf531578cc05cdb653b37aaed23716d5710d856
2020/02/11 20:12:52 [INFO] ▶ Analyzing 19f413bed89cf4ad596e43e3936bdd092bcaa788d6a1ce58f485ad2116fde96e
2020/02/11 20:12:52 [INFO] ▶ Analyzing 5a2926d851e84cae7b817424c9c5e202e3320c289e265b5571a037e76ae0fcef
2020/02/11 20:12:52 [INFO] ▶ Analyzing cdbeccac425bc26d1b974c8545518487e388895f3fcd2da94c1d4f9d64ba265b
2020/02/11 20:12:52 [INFO] ▶ Image [secureimages/elasticsearch:7.6.0-alpine-3.11.3] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress secureimages/elasticsearch:7.6.0-alpine-3.11.3
2020-02-11T18:13:02.961Z        INFO    Need to update DB
2020-02-11T18:13:02.961Z        INFO    Downloading DB...
2020-02-11T18:13:07.113Z        INFO    Reopening DB...
2020-02-11T18:13:13.322Z        INFO    Detecting Alpine vulnerabilities...

secureimages/elasticsearch:7.6.0-alpine-3.11.3 (alpine 3.11.3)
==============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.6.0
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.6.0
2020/02/11 20:13:20 [INFO] ▶ Start clair-scanner
2020/02/11 20:13:34 [INFO] ▶ Server listening on port 9279
2020/02/11 20:13:34 [INFO] ▶ Analyzing efabb8e7a64ff0670af40775b5aa02a8e19f73baa9f9e24aef8ce37a563f632d
2020/02/11 20:13:35 [INFO] ▶ Analyzing 9f4e7283864f578ae81c8242c368f89b786018f517f3a50f753e4384337af570
2020/02/11 20:13:36 [INFO] ▶ Analyzing d1a67f01db89818c702cf68c6268e120b12c38634c7add8d7dd9649b4cc6b5ad
2020/02/11 20:13:36 [INFO] ▶ Analyzing f7d4e2961e67a9afea6793c631aea8f63b8f7ff96da19e710602f0471f55f084
2020/02/11 20:13:36 [INFO] ▶ Analyzing 668336e0933bd794a59656ccf670b388161cbaf5845fe0ab956b851687d2975a
2020/02/11 20:13:36 [INFO] ▶ Analyzing 05dddd3769e524df102eac1af5866bac6fb0ae6cba9589ada9d813d2e8b642d7
2020/02/11 20:13:36 [INFO] ▶ Analyzing 738799b3d226d366ec7a4590d476548dfa8ab90ef5a763a06d44fdb03c24d1b7
2020/02/11 20:13:36 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.6.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.4.3 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.6.0
2020-02-11T18:13:38.921Z        INFO    Need to update DB
2020-02-11T18:13:38.921Z        INFO    Downloading DB...
2020-02-11T18:13:43.455Z        INFO    Reopening DB...
2020-02-11T18:13:57.242Z        INFO    Detecting RHEL/CentOS vulnerabilities...

docker.elastic.co/elasticsearch/elasticsearch:7.6.0 (centos 7.7.1908)
=====================================================================
Total: 621 (UNKNOWN: 0, LOW: 61, MEDIUM: 453, HIGH: 103, CRITICAL: 4)
```
