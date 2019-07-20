# Trilha "Arquitetura Java" em 17/07/2019

- [x] Lista de palestras
- [ ] Contato do palestrante
- [ ] Seguir no Twitter
- [x] Tópicos
- [ ] Slides do site
- [ ] Material divulgado pelo palestrante
- [ ] Material adicional

## Micronaut: Mudando a maneira como construímos microservices  

* Por Luram Archanjo da Sensedia (@github/larchanjo)

- Monolito → Microservices > Scalability
- Less resources with Java Language
- Spring faz muitas coisas, mas em runtime, usando massivamente "reflection"
- Microframeworks
    - Micronaut, Quarkus, Javalin, Ktor
- Ahead of Time Compilation
    - projeto Google Dagger 2 do Google
    - startup em menos de 1 segundo com 10 MB de memória
- Show me
    - micronaut-service → -Xmx 10m → 1 seg
    - spring-service → -Xmx 15m → 6 segundos
- Features
    - Non-blocking HTTP com RxJava + Netty
    - Permite usar as annotations do micronaut para AOT
    - Cloud Native features
- GraalVM
    - permite executável nativo de máquina
    - não uso de classloading dinâmico e reflection
    - micronaut-service → 600ms de startup com micronaut + GraalVM
    - Spring e Hibernate não são compatíveis com GraalVM

## Designing Bulletproof Code  

* Por Otávio Santana

- Tipos de dados para classes de domínio
    - Year (Java Time API)
    - MonetaryAmount (Java Money API)
- Builder
    - PLayerBuilder().withCity(..).withEndDate(..).. → não garante ordem dos atributos, podendo causar erros na validação
    - FluentAPI - declarar interfaces para expor apenas os métodos permitidos

## Supersonic, Subatomic Java with Quarkus

* Por Rafael Benevides (rafael.benevides@oracle.com) (@rafabene)

- Sugestão de sites
    - Oracle Developers > Cloud Native
    - microprofile.io
    - Blog rafabene.com > artigo sobre Java em containers
- Criando aplicação com plugin do Maven
    - mvn quarkus:maven:plugin create ([ ] confirmar)
        - Build gera 2 jars pequenos e uma pasta lib de 8 MB
    - Comando linux para teste de chamadas HTTP
        - while true curl ...
- Combinando AOT + GraalVM a aplicação inicia em 0.006ms
- native-image-docker-image > profile do Quarkus para gerar container ([ ] confirmar)
- Demonstração de live reloading
- Extensions
    - Swagger CI, Open API, jdbc-mariadb, resteasy-jsonb, Hibernate-panache

## Serverless com Java, dá certo?  

* Por Leandro Del Sole (@leandrodelsole) @github/leandrodelsole

- Backend as a service
- Function as a service
- Function
    - Você controle e automatiza → spec, code, build, deploy
    - O provedor controla → events, invoker, autoscale
    - Propriedades
        - Stateless, sem afinidade com infra computacional (cloud native)
    - *-as-a-service*
    - Estatística por linguagem → Java tem muito pouca utilização
    - Mostra de melhorias da function Java até chegar no GraalVM
    - Ferramenta Hey para comparar com Node
        - Java só perde no quesito cold start
- GraalVM
    - Release oficial em maio

## ArchUnit: Garantindo a integridade dos seus padrões arquiteturais em Java  

* Por Edlaine Zamora / Erika Silva da Totvs

- Desafios da arquitetura
- ArchUnit → Biblioteca livre para verificar arquitetura do código Java
    - Compatível com ferramentas de teste unitário
- Camadas do ArchUnit
    - Core
    - Lang
    - Library
- ArchRule → classe com FluentAPI para definir e aplicar as regras
- Dica de estudo
    - Building Evolutionary Architecture ([ ] pesquisar referência)

## Gerenciamento de transações em ambientes distribuídos sem queda de performance  

* Por Elder Moraes (@elderjava)

- Saga pattern
    - microservices.io/patterns/data/saga.html
    - Transação de compensação
        - Fazer algo que anule os efeitos
- Gerenciamento
    - Coreografado
    - Orquestrado
- Apache Camel
    - Baseado nos Enterprise Integration Patterns
- fnproject.io
- Dica de livro
    - Java EE 8 Cookbook

## Padrões essenciais de mensageria para integração de sistemas  

* Por Helder da Rocha (/helderdarocha)

- Porque integrar sistemas
- Desafios das soluções de integração
- Recorrer a padrão de design
- Mensageria
    - eaipatterns.com
        - Descrição dos 15 padrões mais importantes
        - Apache Camel e Spring Integration implementam os padrões

## Como fazemos autenticação OAuth de internet e mobile no Itaú.  

* Por Lilian Lima / Diego Junior da Silva Pereira

- OAuth overview | workflow
- Configuração
    - Benefícios - produtividade, solução distribuida
    - Desafios - comunicação, multiplicação do conhecimento

## Serviços Reativos na prática com Webflux, Kafka e DynamoDB.  

* Por Vinicius Soares / Cléber da Silveira (canal Coffe and IT) (@vicolino_) (@clsilveir)

- Event Driven Architecture
- Programação Reativa
    - Manifesto Reativo
- Spring Webflux
    - non-blocking
    - Suporte a streams reativos
- Kafka
- DynamoDB
- Cases
- Zipkin - ferramento para rastrear sistema (observability)

## Service Layer para migração de dados de sistemas legados para a tecnologia Cloud  

* Por Daiana Cambruzzi Ávila / Marcel de Souza Borges da Betha Sistemas (@daicambruzzi)

- Service layer
- jsonschema - ferramento para validação de JSON
- MongoDB
- Thorntail - servidor microprofile


