# GitOps CI/CD Pipeline on Kubernetes with Argo CD

Every commit is linted, built into a Docker image, pushed to Docker Hub,
and deployed to Kubernetes automatically by Argo CD.

## Flow
Code -> GitHub Actions -> Docker Hub -> config-repo -> Argo CD -> Kubernetes

## Tools
Docker, Kubernetes (kind), GitHub Actions, Argo CD, Prometheus, Grafana

## Monitoring
<img width="1912" height="856" alt="Screenshot 2026-11-13 151540" src="https://github.com/user-attachments/assets/b1c53deb-a88b-49e5-819c-95ba88830503" />


## Rollback
I pushed a broken image tag. Argo CD marked the app as Degraded. I ran
`git revert` and pushed, and Argo CD restored the working version.

![Degraded] 
<img width="1902" height="817" alt="Screenshot 2026-11-13 145344" src="https://github.com/user-attachments/assets/c8d0221b-8a0c-4929-84a1-8a1e83602471" />

![Recovered] 
<img width="1853" height="828" alt="Screenshot 2026-11-13 145437" src="https://github.com/user-attachments/assets/b0239dc2-a685-404d-9821-d55968157a21" />


