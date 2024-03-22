## Kubernetes (k8s)

### Services

No Kubernetes, um Service (SVC) é um recurso para expor internamente um aplicativo sendo executado à rede com um ou mais pods no cluster.

**ClusterIP** - Redireciona requisição para pods selecionados através de etiquetas (`labels`) definidas no `metadata` e utilizando o campo `selector` no service, mantendo um IP fixo para serviços.

**NodePort** - Expõe um pod para fora do cluster e também funciona como _ClusterIP_ internamente do cluster.

**LoadBalancer** - Tipo de Service que integra diretamente com o CloudProvider para criar um balanceador de carga.

**ConfigMap** - Um ConfigMap é um objeto da API usado para armazenar dados não-confidenciais em pares chave-valor.
