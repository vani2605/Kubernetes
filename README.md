## Kubernetes EKS Upgrade
### Pre-requesites and Best practices
- one version at a time
- backup all the manifests deployed in cluster.
- kubectl version update, current eks version can support 3 prior version of kubectl.
- compatalibility check for add-ons
- Refer changelog for changes in latest version
- Perform one step at a time
- Make sure Subnet has enogh IP's.
- Make sure SG
- Review the version skew between the Kubernetes kube-apiserver and the kubelet on your nodes
  
### Updating EKS Cluster includes below steps

- Check current EKS Version and latest available version.
- Upgrade EKS ControlPlane : EKS Controlplane should be upgraded before upgrading Worker Nodes
  - Update EKS version from 1.28 to 1.29 in terraform
- Ugrade Managed Node Groups
  - Update ami version with updated(1.29) version
- If you are using self manager Worker Nodes. Update Autoscaling group(Launch template) with new ami.
- Upgrade eks add-ons.
   - vpc cni,
   - kube-proxy
   - CoreDNS
   - Amazon EBS CSI Driver
   - Amazon EFS CSI Driver
- Upgrade managed add-ons(Nginx, metrics-server, prometheus, Istio, cluster-autoscaler,flutbit etc)


## Kubernetes Best Practices
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
   
