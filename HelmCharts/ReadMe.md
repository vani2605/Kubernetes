## Helm Chart Best Practices
  
- ### Follow standarad helm chart structure

![image](https://github.com/user-attachments/assets/10122fc9-cc41-44a7-bd15-0c5283455992)

  
- ### Writing templates 
  - Use helm builtin functions(tpl, include, toyaml)
  - use helper.tpl to define reusable template logic
  - use lookup function, to query existing resource dynamically.
- ### Security 
  - use RBAC(Role,rolebinding, clusterrole and clusterrolebinding) when needed.
  - Store sensitive values in secrets, dont harcord in values.yaml
  - Use PodSecurityContext and SecurityContext in deployments
    
    `securityContext:
      runAsUser: 1000
      fsGroup: 2000`





  
