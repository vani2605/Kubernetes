## Helm Cheat Sheet

- ### Create a Chart

  `helm create mychart`

 - ### Install and Uninstall chart

   `helm install <release-name> <chart-name>`
  
   `helm install myapp mychart/ `
  
   `helm uninstall <release-name>`
   
   `helm uninstall myapp`
  
   
   `helm list` -- to list installed charts

 - ### Upgrade chart

   `helm upgrade <release-name> <chart-name>`
   
   `helm upgrade myapp mychart/`

 - ### Rollback

   `helm rollback <release-name> <revision-number>`
   
   `helm rollback myapp 1`

   



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





  
