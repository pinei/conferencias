# Trilha "Go" em 20/07/2019

- [x] Lista de palestras
- [ ] Contato do palestrante
- [ ] Seguir no Twitter
- [ ] Tópicos
- [ ] Slides do site
- [ ] Material divulgado pelo palestrante
- [ ] Material adicional

## Por que Go?

* Por Diego Bernardes Gaulke (perdeu o voo)

## Iniciando em Go

* Por Diego Santos (backend at Fliper - pesquisa de investimentos) @diegosantosws

- Um simples crawler usando Go
- função main é apenas o start do seu programa

## Error Tracking

* Por Diego Saouda - Software Engineer na Finanças 360 (www.financas360.com.br)

www.meetup.com > golangbr
github.com/dsaouda ([ ] pegar os slides)

- Go não tem try/catch
    - Uso da variável `err`
- panic
- defer
- recover
- errors (package)

## Case: Projeto SHIVA do Grupo Bandeirantes de Comunicação  

* Por Marcela Sisiliani msisiliani.github.io medium@msisiliani @ma_sisiliani

- Processamento de grande quantidade de dados
- Material no site do Rabbit → um passo a passo sobre todos os tipos de filas
- Problemas em produção com goroutine 
    - Necessário estudar o funcionamento e efeitos colaterais
- Biblioteca do Go é muito completa
- Processo em Node que demorava 30 minutos passou a durar 10 minutos em Go

## Criando CLI's com estilo  

* Por Guilherme Caruso @guicaruso_ Engenheiro de Software do QuintoAndar 

- Go Community BR no medium tem varios artigos pra quem esta começando
- quin.to/carreiras
- Ja tem bibliotecas para CLI
    - Fazer "na unha" é bpm para entender o que você está utilizando
- Pacotes Flag | FlagSet
    - Permite fazer o parser dos parâmetros de linha de comando, armazenando em variáveis
- Ponteiro
- Struct e Interface

## Reactive Programming on the Go  

* Por Igor Luiz Halfeld @IgorHalfed - consultoria Halfed - Microsoft MVP

- Slides na igorluiz.me
- Programação reativa
    - Controlar os fluxos da aplicação
- Javascript tem uma lib chamada "CEP Promise"
- Lib Lagoinha
- Lib RxGo

## Como manter seus projetos em Go sempre monitorados  

* Por Marco Paulo Ollivier da OLX @marcopollivier[twitter, github, linkedin] ollivier.com.br

- Palestra no TDC e Speackerdeck

- Comunidade GopheRio
- Traffic - load balancer, proxy reverso
- Artigo no medium
    - Percents e sua importância nos testes de performance
- Apdex (Application Performance Index)
    - Padrão aberto que define um método padronizado para reportar, avaliar, acompanhar o desempenho de aplicativos
    - 3 níveis
        - Satisfação
        - Tolerável (>T)
        - Frustração (>F=4*T)
- Modelo Push
    - Elastic Search, NewRelics
- Modelo Pull
    - Prometheus
- Elixir
    - Não suportava NewRelics
- Artigo no site Daniel Scott
    - Como 1 segundo custava 16 bilhao em vendas a Amazon
- Vegeta
    - Ferramenta escrita em Go para teste de esforço
    - Jagger / JPlot para construir o gráfico
- Pacote expvar e ferramenta expvarmon
- APM Elastic
    - Instalar o agente
    - Painel de indicadores
- Prometheus
    - artigo na medium - instrumenting ... in 5 minutes
    - Prometheus + Grafana
- NewRelic
    - Boa documentação
    - Painel específico para goroutines
- Greenwall (Healthcheck)

## Como migrar do GoDep para o Go Modules sem medo  

* Por Júlio Lustosa Eng Devops da Globo.com

- Curso de Go do Jeff na Udemy

- Godep migrou para o Go Modules na 1.12
- Tsuru seria o Heuroku opensource
- Comandos
    -  go mod init
    -  go mod verify
    -  go get github.com/pck/_package_
- Exemplo com rsc.io/quote
- Material para iniciantes
    - github.com/golang/go/wiki
    - blog.golang.org

## Testes idiomáticos com Golang  

* Por Hussani Oliveira corganizer no Golang SP - Engenheiro na Cabify @hussanii

- Porque testar?
    - Teste serve para documentar
    - Escrever melhor o código
- "Arrange-Act-Assert": a pattern for arranging and formatting code in UnitTest methods
- Race Conditions
    - O Go tem ferramentas pra testar race condition (flag -race)
        - WARNING: DATA RACE
- Fixtures
    - Dados em arquivo JSON para alimentar os testes
    - Dados binários
    - Strings randômicas

## Testes em GoLang - Asserts, Mocks, Benchmarks e Multithread  

* Por Bruno Damasceno do Mercado Livre @BrunoDM...

- [ ] Vai subir a palestra pro site

- Package testify
    - Asserts disponíveis
- Packages gomock, mockgen
    - go get gomock
    - go install mockgen
- Pacote gorm (como do Grails)
    - 
- Mercado Livre
    - API em Go - 40 milhoes de requests/minuto respondendo em 10ms

## Action Flow, agilidade e simplicidade com go routines  

* Por Guilherme Macedo Esteves @guilhermesteves

- Contratando Go & Vue Fulstack Developer

- Criou o Aclow
    - Alexandre Marco github/AlexMarco7
- Sobre o ActorModel
    - Modelo conceitual onde o Ator é uma unidade de computação

