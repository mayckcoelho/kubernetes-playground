## Docker

### Como o docker consegue manter o isolamento entre os containers e o host?

Com a utilização de namespaces, os containers conseguem garantir isolamento em diversas camadas.

### O que são as imagens?

Imagens são como “receitas” para gerar containers. As camadas são a menor unidade que compõem uma imagem. Quando uma imagem esta sendo executada, é incluída uma camada de leitura e escrita.

### Para que serve o Dockerfile?

Usamos Dockerfiles para criar nossas imagens quando queremos utilizar containers. Temos como base as seguintes instruções:

- `FROM` é usada para definirmos uma imagem como base para a nossa.
- `WORKDIR` serve para alterar o diretório de trabalho.
- `ARG` é utilizada para especificar valores de variáveis em tempo de build.
- `ENV` é usada para variáveis de ambiente.
- `EXPOSE` descreve quais portas sua aplicação vai escutar.
- `COPY` serve para copiar arquivos e diretórios.
- `RUN` executa comandos em tempo de build.
- `ENTRYPOINT` especifica o comando de execução padrão da imagem.

Para mais comandos, utilizar como referência o link da [documentação](https://docs.docker.com/reference/dockerfile/).

### Quais os tipos de persistência?

Existem 3 tipos de persistências:

- Com `volumes`, é possível escrever os dados em uma camada persistente independe de como as pastas do sistema estão estruturadas.
- Com `bind mounts`, é possível escrever os dados em uma camada persistente baseado na estrutura de pastas do host.
- Com `tmpfs`, podemos armazenam dados em memória volátil.

### Quais os tipos de driver de rede?

Por padrão, todos os containers criados utilizam a rede `bridge`, que já permite que os container se comuniquem. Existem 3 drivers de rede:

- O driver `bridge` é o utilizado por padrão no docker.
- Com o driver `host`, removemos o isolamento entre o container e o sistema.
- Com o driver `none`, removemos a interface de rede.

### Para que serve o Docker Compose?

Docker Compose é uma ferramenta de coordenação de containers. Com ele, podemos resolver o problema de executar múltiplos containers de uma só vez e de maneira coordenada, evitando executar cada comando de execução individualmente.

Para mais informações, utilizar como referência o link da [documentação](https://docs.docker.com/compose/).
