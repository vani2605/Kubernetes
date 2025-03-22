# Kubernetes
All about Kubernetes

# Kubernetes Best Practices
1. Use Namespaces to isolate workloads
2. Limit Cluster size
3. Resource management: Set resource limits and requests for CPU and Memory for deployments.
4. Use Autoscaler to scale worker nodes dynamically. Use HPA to scale CPU and memory.
5. Security: Use RBAC and least previlege policy
6. Use Network policies: Istio(pod to pod and external communication)
7. Avoid running containers as root. Enable securityContext.runAsNonRoot: true
8. Use secrets and configmaps instead of hardcoding values
9. Logging and Monitoring: Use Centralized logging solution like elastisearch, fluentd, otel. Monitor with prometheus and Grafana.
10. Use liveness and rediness to detect failure at early stage, at pod creation.
11. Use GitOps tools like argocd, flux for declarative deployments.
12. Leverage rolling updates eg. argo-rollouts
13. Use Helm or kustomize to manage manifests
14. Use Ingress controller(Nginx), better traffic management
15. Enable mutual TLS (mTLS) between services for security (Istio).
16. Use PV and PVC for storage management
17. Ensure etcd snapshots for cluster recovery.
18. Test disaster recovery plans periodically
   
