# Elasticsearch

Elasticsearch, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~414MB)

Security scanning using Clair
```
clair-scanner secureimages/elasticsearch:7.11.1-alpine-3.13.2
2021/02/20 14:28:34 [INFO] ▶ Start clair-scanner
2021/02/20 14:28:38 [INFO] ▶ Server listening on port 9279
2021/02/20 14:28:38 [INFO] ▶ Analyzing b73bac2fe5a7b9d1abcbf0138798281e20b11e59b4605b104d38e914fa35b4d2
2021/02/20 14:28:38 [INFO] ▶ Analyzing 54b679721faf4d8cad7c14e5d729d1d09f09d30e73efb0548a47c9269ecff774
2021/02/20 14:28:38 [INFO] ▶ Analyzing 396e682b504541aaac576c322f300acba547b3a9ef596939a799e26a6aba315a
2021/02/20 14:28:38 [INFO] ▶ Analyzing fbf68ecaa0af07fc88c1f323ed3054345bc4cd961ba0e807d74b8bfb759e16b7
2021/02/20 14:28:38 [INFO] ▶ Analyzing a9b0d354e257d2461106a94d55f3c54ede471d35db28672aa6764935b135bd97
2021/02/20 14:28:39 [WARN] ▶ Image [secureimages/elasticsearch:7.11.1-alpine-3.13.2] contains 1 total vulnerabilities
2021/02/20 14:28:39 [ERRO] ▶ Image [secureimages/elasticsearch:7.11.1-alpine-3.13.2] contains 1 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress secureimages/elasticsearch:7.11.1-alpine-3.13.2
2021-02-20T14:28:41.245Z        INFO    Need to update DB
2021-02-20T14:28:41.245Z        INFO    Downloading DB...
2021-02-20T14:28:48.078Z        INFO    Detecting Alpine vulnerabilities...
2021-02-20T14:28:48.078Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

secureimages/elasticsearch:7.11.1-alpine-3.13.2 (alpine 3.13.2)
===============================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~819MB)

[https://www.docker.elastic.co/](https://www.docker.elastic.co/)
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.11.1
```

Security scanning using Clair
```
clair-scanner docker.elastic.co/elasticsearch/elasticsearch:7.11.1
2021/02/20 14:29:45 [INFO] ▶ Start clair-scanner
2021/02/20 14:29:58 [INFO] ▶ Server listening on port 9279
2021/02/20 14:29:58 [INFO] ▶ Analyzing b5ad3981919b474c18caec8885fc124b01bc7c3e7fa19738cbfae253a22d4a16
2021/02/20 14:29:58 [INFO] ▶ Analyzing e511af1a022c64fdd237fccc7077dc3523d456b78851dcebf55e1b08da722bcc
2021/02/20 14:30:00 [INFO] ▶ Analyzing 73fbdea1167cda0533aee9843b21ae23faf680fe6b3b031569540f1a3404d11f
2021/02/20 14:30:00 [INFO] ▶ Analyzing 158896353aa2bebd7fb90768aa99461c5d7822104ce6c1adcde74cc13b20639a
2021/02/20 14:30:01 [INFO] ▶ Analyzing e8d9d73176773e5ab3e2cbe908c97c3400f0e8af32cf4fb7ba6e444635043097
2021/02/20 14:30:01 [INFO] ▶ Analyzing 46344f4e21766a7371c6134b39b7be70c788ddc622dc93e0ba2f1c3600348287
2021/02/20 14:30:01 [INFO] ▶ Analyzing 7c52ac4c52dfb2746f2ca8f3d0185ceedf9366292e91c9fc98d0d06db80cc2a2
2021/02/20 14:30:01 [INFO] ▶ Image [docker.elastic.co/elasticsearch/elasticsearch:7.11.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress docker.elastic.co/elasticsearch/elasticsearch:7.11.1
2021-02-20T14:30:02.944Z        INFO    Need to update DB
2021-02-20T14:30:02.944Z        INFO    Downloading DB...
2021-02-20T14:30:19.407Z        INFO    Detecting RHEL/CentOS vulnerabilities...
2021-02-20T14:30:19.433Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

docker.elastic.co/elasticsearch/elasticsearch:7.11.1 (centos 8.3.2011)
======================================================================
Total: 168 (UNKNOWN: 0, LOW: 79, MEDIUM: 84, HIGH: 5, CRITICAL: 0)
```
