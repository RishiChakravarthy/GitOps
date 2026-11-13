# GitOps CI/CD Pipeline on Kubernetes with Argo CD

Every commit is linted, built into a Docker image, pushed to Docker Hub,
and deployed to Kubernetes automatically by Argo CD.

## Flow
Code -> GitHub Actions -> Docker Hub -> config-repo -> Argo CD -> Kubernetes

## Tools
Docker, Kubernetes (kind), GitHub Actions, Argo CD, Prometheus, Grafana

## Monitoring
![Grafana dashboard](docs/grafana-dashboard.png)

## Rollback
I pushed a broken image tag. Argo CD marked the app as Degraded. I ran
`git revert` and pushed, and Argo CD restored the working version.

![Degraded](docs/argocd-degraded.png)
![Recovered](docs/argocd-recovered.png)