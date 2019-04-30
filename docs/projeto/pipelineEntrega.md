# Pipeline de entrega

<p>A pipeline de entrega tem como objetivo apresentar o fluxo de uma funcionalidade, desde o seu desenvolvimento até chegar ao usuário final.</p>

![Pipeline Entrega](../assets/imgs/devOps/pipelineEntrega.jpg)

---

## Ferramentas

### Docker

<p>Docker é uma ferramenta para isolar um ambiente de desenvolvimento através de containers. Estamos utilizando essa ferramenta para alguns propósitos: isolar o ambiente de desenvolvimento, padronizar o ambiente de todos os desenvolvedores, facilitar na integração contínua e no deploy.</p>

### Docker Compose

<p>O Docker Compose é uma ferramenta que utiliza o docker. O docker compose é o que chamamos de orquestrador de containers. Essa ferramenta é utilizada somente em ambiente de desenvolvimento, com ela é possível subir vários containers de um vez e criar regras de comunicação entre eles. Estamos utilizando o docker compose principalmente para subir serviços que possuem banco de dados.</p>

### Mocha e Chai

<p>São nossas ferramentas para testes unitários em javascript, já que todos os nossos microsserviços se encontram nessa linguagem. Os testes são de fundamental importância para garantir que ao incluir ou alterar um alguma funcionalidade, não acabe prejudicando outra.</p>

### Eslint

<p>Já para a ferramenta de testes estático estamos utilizando o Eslint, com o padrão do <b>airbnb-base</b>. O eslint está sendo utilizado para garantir que o código esteja padronizado com o da comunidade javascript.</p>

### Gitlab CI

<p>Nossa ferramenta para integração contínua, Gitlab CI. Como estamos utilizando o github como forge principal, configuramos o gitlab ci para fazer o mirror e assim poder executar o gitlab ci. O nosso gitlab ci está rodando basicamente 4 stages, sendo eles: build, test, quality e deploy. Os 3 primeiros rodam a cada commit, e eles garantem a qualidade e a confiabilidade do código. Já o deploy ele roda somente na dev e na master, ele build o serviço e da um push para o docker hub.</p>

### Docker hub

<p>Essa ferramenta é utilizada para disponibilizar as imagens dos containers, ele funciona como um git para imagens. Atualmente nossas imagens estão todas públicas através desse link: https://hub.docker.com/u/caleberios</p>

### Kubernets

<p>O Kubernets é outro orquestrador de containers, mas diferente do docker compose que é muito utilizado para o ambiente de desenvolvimento, o kubernetes é utilizado para homologação e produção. Através dele que estamos disponibilizando nossos serviços para todos os usuários finais.</p>
