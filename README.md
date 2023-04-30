# kubernetes com ArgoCD

Deploy do Nginx em AKS usando ArgoCD. As configurações do Yaml tem como base o curso CKA da Proevolua.

Este yaml possui as seguintes configurações:

- labels: Utilizado para especificar identificação de objetos que são relevantes para o usuário.

- readinessProbe: Quando configurado, garante que aplicação receba tráfego enquanto estiver saudável.

- livenessProbe: Quando configurado, checa se a aplicação está saudável.

- ConfigMaps: Utilizado para passar variáveis em uma aplicação. Sua utilização é bastante útil, já que uma vez que o tipo configmaps esteja com as variáveis necessárias, posso utilizar este configMap para várias aplicações sem precisar colocar em cada uma das aplicações as varivaeis.
Neste exemplo temos um objeto configmap com dados do responsável pela aplicação e nos pods criados a partir do deploy site nginx é possível ver estes dados com através do comando kubectl exec -it **nome-do-pod** -- env.

- Secrets: Objeto que contém uma pequena quantidade informação sensível, como senhas, tokens ou chaves.

- LimitRange: Objeto que limita uso de cpu e memória da sua aplicação no kubernetes.

- Persistent Volumes (PV): Montagem de diretórios para armazenamento persistente de informações. Este diretório é criado no cluster. A utilização de Persistent Volume é muito importante para que não perdermos as informações caso haja algum problema com o nosso pod.

- Persistent Volumes Claim (PVC): São pequenas partes dentro do PV. Após criação do PV e PVC podemos associá-los ao pod.
# Obs: Não é aconselhado em ambiente de produção, já que se perder o cluster, a informação também é perdida. Em produção é aconselhável usar um Storage no Azure ou S3 na AWS.