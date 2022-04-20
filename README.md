helm-gcloud-deployer
======

helm-gcloud-deployer helps to deploy apps to gcloud's kubernetes cluster, using helm.

# Docker hub id:

emeno/helm-gcloud-deployer

# Installation

```
docker pull emeno/helm-gcloud-deployer
```

# Quick Start

.gitlab-ci.yaml stage for example

```shell
deploy:
  image: "emeno/helm-gcloud-deployer"
  script:
    - gcloud auth activate-service-account --key-file=<key-file-path>
    - gcloud container clusters get-credentials <cluster-name> --zone <project-zone> --project <project-id>
    - helm repo add <repo-name> <repo-link>
    - helm install <app-name> <chart-name>
````