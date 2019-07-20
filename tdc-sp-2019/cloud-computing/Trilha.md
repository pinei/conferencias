# Trilha "Cloud Computing" em 16/07/2019

- [x] Lista de palestras
- [ ] Contato do palestrante
- [ ] Seguir no Twitter
- [x] Tópicos
- [ ] Slides do site
- [ ] Material divulgado pelo palestrante
- [ ] Material adicional

## Muito alto pra carpi, muito baixo pra roçar! Entenda como a sua estratégia de migração pra nuvem é importante!  

* Por Natalia Girolamo e Alexandre Mazurque da AWS

- https://www.linkedin.com/in/nataliagirolamo


### Tópicos

- Desafio de uma migração para nuvem
    - Mapeamento, requisitos, dependências
- Estágios de adoção de nuvem (AWS)
    - Projeto → Fundação (Landing Zone) → Migração → Otimização / Reinvenção
- AWS
    - Vasto ecossistema de serviços
    - Segurança | Compliance | Governança
- Estratégias de Migração ([diagrama][1])
    - Rehost
    - Refactor
    - Replatform
    - Repurchase
- Objetivos
    - Automatizado
    - Self-service
    - Seguro, compliant (contas seguras dentro das normas)
    - Escalável, flexível
- Lembretes
    - Crescimento estruturado
    - Automatizar o máximo
    - Ser ágil e estar seguro é possível

[1]: https://twitter.com/DanOCallahan/status/1133824483201097728

## Attack vs. Defense: real time security protection  

* Por Thomás Capiotti da On-Security

### Tópicos

- Ataque e Defesa na borda
    - Camada de aplicação é que sofre os ataques
- Impactos x Métodos
- Repelindo ataques
    - XSS
- CDN [sobre][2]
    - Menor latência
- Uptime robots
- Geopicker
    - Ferramenta para medição de latência
- WAF (Web Application Firewall) [sobre][3]

[2]: https://www.gocache.com.br/cdn/
[3]: https://www.gocache.com.br/waf/

## Monitorar, Orquestrar, GO! Melhores práticas de Cloud Híbrida e como a Orquestração e Monitoração alavancam seu parque.  

* Por Alberto Cardoso da Oracle

### Tópicos

- Conceito de Orquestração Multicloud
- Desenho Aplicacional
- Desenho Infra Rede
- Camadas de Monitoramento
- Checklist de Boas Práticas

## Cloud Native Computing Foundation - A Mantenedora do Kubernetes  

* Por Paulo Alberto Simões da Oracle

### Tópicos

- Conceito de Cloud Computing (NIST)
- Cloud Native Computing Foundation (2015)
    - Dimensões
        - Projetos / ferramentas
        - Conhecimento
        - Comunidade
- Kubernetes
- Outros Projetos
    - NATS (mensageria)
    - ETCD (chave-valor)
- Cloud Native Trail Map
- Cursos / Certificações
- Comunidade / Colaboração

## As vantagens de ter um Plano de Continuidade de Negócio!

* Por Ruy Oliveira (adentro.com.br)

- Fatores para indisponibilidade
- Fatores que podem causar perdas de dados
- Alta disponibilidade

## Clientes Migrando para Cloud e o Mito da Caverna de Platão  

* Por Ricardo Cardoso de Almeida (CESAR - Centro de Inovação)

- Clientes migrando para a Cloud
- On-Premises / IAAS / PAAS / SAAS
- SAAS / FAAS / ... / PAAS / DAAS
- Monolítico → SOA → Microserviços
- dzone.com > What are microservices actually

## É hora de pensar em soluções portáveis na cloud!

* Por Isaac Felisberto de Souza

- Amazon AWS → primeiro provider IAAS
- Evolução para PAAS e *AAS
- Concorrentes
- Melhores serviços, melhores preços
- Consegue trocar de cloud? Qual esforço?
- Problemas de portabilidade desde sistemas operacionais
- Agora quem demanda são as empresas e não os usuários finais
- CI > Monitoramento e Logs

## A jornada do SiDi no desenvolvimento de uma plataforma de serviços e sua migração para a Cloud

* Por Rafael Simionato / Alan Corrales

- Problemas de Desempenho
- Analise de Hardware (nmon)
    - Pico de uso do disco
- Migrando de Docker Compose para ECS com Fargate
- Aumento de Produtividade
- Melhor dimensionamento do uso de recursos

##  Observando as nuvens  

* Por Eduardo Neves

- Conceito de observabilidade
    - Atributo do sistema assim como usabilidade, desempenho, etc.
- Necessidade de informações suficientes para resolver problemas
    - Indicadores de downtime, erro, respostas lentas, recursos, logs
- Principais desafios: informações corretas, tem que dosar
- Aspectos
    - Capacidade de detectar comportamentos indesejáveis
    - Informações precisas com debug rápido e eficiente em produção
- Usar o trio elastic
- Ferramentas
    - APM Tool, uptime tool, metric tool, logs tool

## Tudo o que você precisa saber sobre Azure Web Apps  

* Por André Dias da GFT (@andrediasbr)

- 100 vagas na espanha e alemanha
- Azure Apps
    - Criando WebApp a partir de um código
    - Container a partir de um Docker image → nginx
    - Deployment slots
        - Atualização com commit no github
        - Swap HML <> PRD
        - Autenticação com AD
        - Logstream

## Cloud Native Banking: como o Nubank usa imutabilidade na nuvem para atender milhões de clientes  

* Por Alexandre Cisneiros / Diogo Vecchiati Beato

- Problemas de escalabilidade
    - Message system
    - Database
        - Problema com throughput de escrita
- Shards
    - Segregados por tipos de clientes
    - Cópia de toda a infra
    - Pouco relacionamento entre os shards
- Microservices
    - 90% clojure
    - Arquitetura Ports and Adapters - alternativa ao MVC
- Infraestrutura imutável
- Infraestrutura como código
- Squads responsáveis pelos serviços
- Migrando pro Kubernetes
    - Por shard
- ...
    - Automação
    - Velocidade
    - Escalabilidade
    - Resiliência

## Programando a Internet do Futuro por meio das Redes Definidas por Software  

* Por João Maia

- Roteadores programáveis vs configuráveis
- Começou com o Google

## O backend da cloud e containers, você conhece?  

* Por Carol Valencia (em espanhol)

- Conceitos

## KEDA ? Kubernetes-based Event-driven Autoscale  

* Por Thiago Custódio (Microsoft MVP)

- Modelo poll
- Modelo push
    - Favorece event drive architectures
- Azure Functions
    - Scale Controller → monitora a fonte de eventos

