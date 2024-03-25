## [Kubernetes (k8s)](https://kubernetes.io/docs/home/)

### Services

No Kubernetes, um Service (SVC) é um recurso para expor internamente um aplicativo sendo executado à rede com um ou mais pods no cluster.

**ClusterIP** - Redireciona requisição para pods selecionados através de etiquetas (`labels`) definidas no `metadata` e utilizando o campo `selector` no service, mantendo um IP fixo para serviços.

**NodePort** - Expõe um pod para fora do cluster e também funciona como _ClusterIP_ internamente do cluster.

**LoadBalancer** - Tipo de Service que integra diretamente com o CloudProvider para criar um balanceador de carga.

**ConfigMap** - Um ConfigMap é um objeto da API usado para armazenar dados não-confidenciais em pares chave-valor.

### ReplicaSets

Em Kubernetes, um ReplicaSet (RS) é utilizado para gerenciar um conjunto de réplicas de Pods em execução a qualquer momento. Por isso, é geralmente utilizado para garantir a disponibilidade de um certo número de Pods idênticos.

### Deployments

Um Deployment fornece atualizações declarativas para pods e ReplicaSets.

Você descreve um estado desejado em uma implantação e o controlador de implantação altera o estado real para o estado desejado em uma taxa controlada. Você pode definir implantações para criar novos ReplicaSets ou para remover implantações existentes e adotar todos os seus recursos com novas implantações.
