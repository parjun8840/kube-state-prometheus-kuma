**kube-state-metrics-prometheus**

[![|](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/r/parjun8840/django-app02)
![|](https://img.shields.io/badge/kubernetes-326ce5.svg?&style=for-the-badge&logo=kubernetes&logoColor=white)
![|](https://img.shields.io/badge/Prometheus-000000?style=for-the-badge&logo=prometheus&labelColor=000000)
![|](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
<img src="https://kuma.io/images/social/og-image-1200-630.jpg" width="150">


This Helm Chart enables you to instantly push the Kuma Service Mesh metrics from an AWS EKS cluster to AWS AMP.
1. This chart may use  docker images from [parjun8840 Docker Hub](https://hub.docker.com/u/parjun8840) in future

2. It uses image from [kube-state-metrics RED HAT](https://quay.io/repository/coreos/kube-state-metrics)

3. It uses image from [promnetheus Docker Hub](https://hub.docker.com/r/prom/prometheus)

4. The installed application will collect metrics exclusivley in **Prometheus** format from a **Kuma Service Mesh** running on **EKS** and pushes to the **AMP**


- **Packaging**
```
$ helm package kube-state-prometheus-kuma
Successfully packaged chart and saved it to: /Users/arjunpandey/Documents/arjun-git/eks-proposed-kuma/kube-state-metrics-prometheus-0.6.0.tgz
```

- **Installing**
```
$ helm upgrade --install  kube-state-metrics-prometheus --namespace mesh-observability --set prometheus-server.iamRole="PLEASE-COPY-ARN-IAM-ROLE" --set prometheus-server.remoteWrite.url="URL-AMP-AWS-ACCOUNT"  kube-state-metrics-prometheus-0.6.0.tgz
```

**NOTE:**
This chart has been developed & maintained by:
[name:"parjun8840" ]

## License

Apache License 2.0
