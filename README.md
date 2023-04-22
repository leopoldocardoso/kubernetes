# kubernetes com ArgoCD

Deploy do Nginx em AKS usando ArgoCD.

Este yaml possui as seguintes configurações:

- readinessProbe quando configurado, garante que aplicação receba tráfego enquanto estiver saudável.
- livenessProbe quando configurado, checa se a aplicação está saudável.
- ConfigMaps pode é utilizado para passar variáveis em uma aplicação. Sua utilização é bastante útil, já que uma vez que o tipo configmaps com as variáveis necessárias, posso utilizar
este configMap para várias aplicações sem precisar está colocando na mesma o valor literal dela. Neste exemplo temos um objeto configmap com meus dados e nos pods criados a partir do deploy site nginx é possível ver estes dados com através do comando kubectl exec -it **nome-do-pod** -- env

![ArgoCD.png](/home/leopoldo/Pictures)