# kubernetes com ArgoCD

Deploy do Nginx em AKS usando ArgoCD.

Este yaml possui as seguintes configurações:

- readinessProbe: Quando configurado, garante que aplicação receba tráfego enquanto estiver saudável.

- livenessProbe: Quando configurado, checa se a aplicação está saudável.

- ConfigMaps: Utilizado para passar variáveis em uma aplicação. Sua utilização é bastante útil, já que uma vez que o tipo configmaps com as variáveis necessárias, posso utilizar
este configMap para várias aplicações sem precisar está colocando na mesma o valor literal dela. Neste exemplo temos um objeto configmap com meus dados e nos pods criados a partir do deploy site nginx é possível ver estes dados com através do comando kubectl exec -it **nome-do-pod** -- env.

- Secrets: Objeto que contém uma pequena quantidade informação sensível, como senhas, tokens ou chaves.

- Metrics: Objeto que limita uso de cpu e memória da sua aplicação no kubernetes.