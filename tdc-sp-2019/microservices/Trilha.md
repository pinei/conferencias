# Trilha "Microservices" em 19/07/2019

- [ ] Lista de palestras
- [ ] Contato do palestrante
- [ ] Seguir no Twitter
- [ ] Tópicos
- [ ] Slides do site
- [ ] Material divulgado pelo palestrante
- [ ] Material adicional

## Microservices RESTLess e Event-Driven Architecture  

* Por Edson Yanaga da Red Hat @yanaga

- Livro "Migrating to Microservice Databases"
- Domínios
    - Sistemas Corporativos
        - Correlação alta dos dados
        - Baixa complexidade de infra
    - Sistemas públicos
        - Correlação baixa
        - Alta complexidade de infra estrutura
- Code is easy, state is hard
    - Dados tem massa.... atraem mais dados, ficando mais difícil distribuir
- Acoplamento temporal
    - Comunicação síncrona entre os microserviços
- Latency / availability / performance
- Eventual consistency
- Japão ainda está tentando migrar para Java EE 7
    - Cultura do "não pode errar"
- "Yaml hell"
- Annotations trouxe metadado para perto do código
- POJO (anemic) domain model é um anti pattern
- Event sourcing → substitui snapshot por transactions
    - Complexidade na garantia de ordem nas transações em brokers
    - Habilita pensar mais no comportamento do sistema e menos na estrutura de dados
- CQS (Command Query Separation)
    - Separar interfaces
        - Métodos de leitura
        - Métodos de escrita
    - (Bertrano Meyer) Asking a question should not change the answer
- CQRS (Command Query Responsability Separation)
    - "separate data stores"
    - Como transferir dados do modelo de escrita para o modelo de leitura
    - Distribution, availability, integration, analytics
    - 10 anos atrás se pensava em performance
- Mensageria
    - Substitui o método poll (ETL) por push
- Events are facts that happen in the system
- Níveis de abstração dos eventos
    - Low level - pedido-criado, pedido-excluido, pedido-alterado
    - Domain level - endereco-cliente-alterado
- Toda estrutura de dados tem schema (na estrutura ou na leitura)
- Kafka não é broker mas um log distribuido
    - Tem replay de mensagens
- Quarkus
    - Garante o Java para os próximos 20 anos

bit.ly/eda-tutorial (repositorio girhub)


## O que aprendi montando uma arquitetura de microsserviços  

* Por Giovanni Bassi da Lambda 3

- Primeira regra de distribuição de sistemas → não distribua
    - Mais caro, mais lento, problemas em produçào
    - Exige excelência técnica em Devs e Ops
- Motivações para adoção
    - Sistema global
    - Alta disponibilidade
    - Custo operacional eficiente
    - Escalabilidade
        - Tamanho do serviço
        - Quantidade de serviços
        - Distribuição computacional
- 8 falácias da computação distribuida por L Peter Deutsch
- Tamanho do serviço
    - O menor possível desde que faça sentido
    - Aggregate, Bounded Context
- Linguagens
    - Uma para o dia a dia
    - Uma para o alto desempenho (Go, Rust)
- Serviços não compartilham banco de dados (não há cenário)
    - São independentes
- Princípios
- Functions
- Paas de aplicação
- Kubernetes
- Service Mesh
    - Políticas de tráfego
    - Telemetria
    - Segurança (autenticação com mTLS)
- Independência de Microserviços
    - Dificil testar o sistema como um todo
    - Documentação Swagger
        - Comparar versões da documentação para identificar quebra de compatibilidade
- API Management
    - Independe da arquitetura de microserviços
    - Entrega segurança, escalabilidade, throthling
        - Coisas que o Kubernetes entrega de graça
- Tratando o legado
    - Cache interno de eventos
    - Camada anticorrupção
- Comunicação entre serviços
    - REST, JSON
    - RPC, Protobuf
    - Timeout, Retry, Circuit Breaker (Service Mesh de graça)
    - Correlation ID
- Consistência eventual
- Terraform - configuração como código


## A Saga da consistência de dados entre Microservices  

* Por Andreia Silva da Sensedia @andreiacamila github/andreiac-silva

- Shared database vs Database per Service
- Gerenciamento de múltiplas bases é complexo
- Adeus a ACID properties
- Two Phased Commit não é recomendado
    - Sincrono
    - Bloqueante
    - Todos os envolvidos devem ter suporte
- Consistência eventual
    - Trabalhar com estados intermediários
- Event sourcing
- Site Debelium
    - Artigo "Realiable microservices data exchange with the outbox pattern"
- Saga
    - Padrão de gerenciamento de falhas
    - Representa uma coleção de sub-transações locais
    - Comunicação sincrona ou assincrona
    - Cada sub-transação deve possuir uma transação de compensação
- Tipos de Saga
    - Orquestrada
        - Apache Camel
    - Coreografada (complicado para vários componentes)
- Exemplo com Camel no Github

## Como manter a disponibilidade dos seus serviços através do monitoramento de métricas  

* Por Elder Moraes

- Microprofile
    - JEE leve o suficiente para microserviços
    - Helidon.io é a implementação
        - Helidon SE
        - Helidon MP
- Exemplo do RockyBalboaService
- 3 tipos de métrica do Microprofile
    - Base
        - JVM
        - Threads
        - ThreadPools
        - ClassLoading
        - S.O.
    - Vendor
    - Application
- Formato padrão → Prometheus
- Métricas via annotation
    - @counted
    - @metered
    - @gauge
    - @timed
- Arquitetura do Helidon SE
- Helidon MP se compara a
    - Micronaut
    - Javalin
    - Spark
- Pode conectar com o Prometheus e gerar visualizações no Grafana

## Cloud Native Banking: como o Nubank usa imutabilidade na nuvem para atender milhões de clientes  

* Por Alexandre Cisneiros / Diogo Vecchiati Beato

- Problemas de escalabilidade com Kafka
- 11 shards
    - cada um tem todos os microserviços
    - auth, compra, boletos
- Clojure
    - JVM lisp
    - Funcional
    - Produtivo
- Datomic
    - Git para dados
    - Queries no passado
    - Storage desaclopado
- Kafka
    - Canal de comunicação
    - Mensagens persistentes
    - Resiliência
- Arquitetura hexagonal
    - Ports and adapters
- Shard infrastructure
    - Cluster de kubernetes
    - 1 banco de dados por serviço
    - Quando necessário, duplica uma stack e começa a mandar o tráfego para a nova
- Devops é cultura (não tem um time)
    - Tem um time de engenheiros de infraestrutura
- Infra as a Code
- Provisionamento com Cloud Formation

sou.nu/jobs-at-nubank

- Sobre APM
    - Biblioteca comum espalhada nos serviços
    - Usando Prometheus
- Usam o Go-CI não usam jenkins

## Conciliando uso de camadas com microservices  

* Por Isaac Felisberto de Souza (slides no linkedin)

* devparana - comunidade de devs

...
- Princípios
    - Solid
    - GoF
    - Grasp
        - High cohesion
        - Low coupling
- MVC - considere que a sua API é a view

## Desenvolvendo Chatbots com micro serviços  

* Por Matheus Kumano / Luis Hansen da Certsys

- Serviço do NLU / NLC
    - Natural Language Understanding
    - Natural Language Classifier

## Arquitetura Evolucionária e Domain Driven Design: Os fundamentos de microservices  

* Por --Felipe Rodrigues-- Grazi Bonizi

- Revisando o DDD
- Complexidade técnica acidental
- Linguagem ubíqua
- Building blocks - parte mais fácil do DDD
- Domínio
    - principal - equipe mais experiente
    - genérico - terceirizar ou comprar
    - auxiliar - equipe menos experiente
- Mapa de contexto
## Do Monolito aos Microfrontends: Preparando a arquitetura para crescer  

* Por Rodrigo Branas
