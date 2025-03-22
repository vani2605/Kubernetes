# Helm Chart Best Practices
  
1. Follow standarad helm chart structure
mychart/
  ├── charts/         # Dependencies (if any)
  ├── templates/      # Kubernetes manifests with Helm templating
  ├── values.yaml     # Default configuration values
  ├── Chart.yaml      # Chart metadata
  ├── README.md       # Documentation
2. Writing templates 
  > Use helm builtin functions(tpl, include, toyaml)
  > use helper.tpl to define reusable template logic
  > use lookup function, to query existing resource dynamically.
3. Security 
  > use RBAC(Role,rolebinding, clusterrole and clusterrolebinding) when needed.
  > Store sensitive values in secrets, dont harcord in values.yaml
  > Use PodSecurityContext and SecurityContext in deployments
    securityContext:
      runAsUser: 1000
      fsGroup: 2000





  
