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

### Armazenamento

#### Volume

Volumes são basicamente diretórios contendo dados, acessíveis aos contêineres em um pod. Volumes possuem ciclo de vida dependentes de Pods e independentes de containers.

#### PersistentVolume

Um PersistentVolume (PV) é uma parte do armazenamento dentro do cluster que tenha sido provisionada por um administrador, ou dinamicamente utilizando `StorageClasses`.

#### PersistentVolumeClaim

Uma PersistentVolumeClaim (PVC) é uma requisição para armazenamento por um usuário. É similar a um Pod. Pods utilizam recursos do nó e PVCs utilizam recursos do PV.

Para mais informações, utilizar como referência o link da [documentação](https://kubernetes.io/pt-br/docs/concepts/storage/volumes/).

#### StorageClasses

Um StorageClass fornece uma maneira para os administradores descreverem as classes de armazenamento que oferecem.

#### StatefulSet

O StatefulSet é utilizado para gerenciar aplicativos que precisam manter estado, ou seja, que necessitam de identidades persistentes e garantias de ordem e unicidade para seus Pods, ao contrário de um Deployment que trata seus Pods como efêmeros.

#### Probes

Os `Probes` são mecanismos utilizados para verificar o estado de um contêiner em execução. Esses `probes`(sondas) ajudam o Kubernetes a garantir que os contêineres estejam saudáveis e prontos para lidar com o tráfego, aumentando a confiabilidade e a disponibilidade das aplicações.

**Liveness Probes** - Ajuda a detectar situações em que aplicativos em execução por longos períodos eventualmente quebram e não conseguem se recuperar, exceto sendo reiniciados.

**Readiness Probe** - Verifica se o contêiner está pronto para receber tráfego. Se o contêiner não estiver pronto, o Kubernetes interrompe o envio de tráfego para ele, permitindo que ele se recupere antes de ser colocado em serviço.

**Startup Probe** - Consegue verificar se o contêiner está pronto para receber tráfego durante o processo de inicialização. É semelhante ao `Readness Probe`, mas é usado apenas durante o início do contêiner.

#### HorizontalPodAutoscaler

O `HorizontalPodAutoscaler` do Kubernetes automatiza o ajuste da quantidade de pods em um Deployment ou StatefulSet para atender à demanda. Ele faz isso automaticamente, aumentando ou diminuindo a quantidade de pods conforme necessário.

É necessário ter um servidor de métricas para capturar a utilização de CPU [Metric Server](https://github.com/kubernetes-sigs/metrics-server).

#### VerticalPodAutoscaler

O `VerticalPodAutoscaler` remove a necessidade de definir limites e pedidos por recursos do sistema, como cpu e memória. Quando definido, ele define os consumos de maneira automática baseada na utilização em cada um dos nós, além disso, quanto tem disponível ainda de recurso.
