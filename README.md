# kubernetes com ArgoCD

Deploy de um container Nginx em AKS usando ArgoCD.

Este yaml possui as configurações de readinesProbe e livenessProbe.

- O readinessProbe quando configurado, garante que aplicação receba tráfego enquanto estiver saudável
- O livenessProbe quando configurado, checa se a aplicação está saudável
