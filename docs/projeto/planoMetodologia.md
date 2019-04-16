# Plano de Metodologia

<p> Nesse documento serão explicados e explicitados os papéis de cada membro do time e como serão usados. O time utilizará uma metodologia orientada à práticas ágeis, que também serão explicadas ao logo do documento.</p>

## Papéis do time

<p> Ao longo do projeto a equipe terá 5 papéis muito bem definidos, que posteriormente à Release 2 será rotacionado.</p>

* A **Arquiteta** do projeto é a pessoa responsável por construir a arquitetura do projeto, além disso, ela deve garantir que o projeto siga a arquitetura desenhada, além de definir a tecnologia a ser utilizada. 
* O **DevOps** do projeto é o responsável por unir o desenvolvimento à parte operacional, realizando configuração de Docker, integração contínua, é responsável por toda a ambientação do projeto e é quem tem uma visão geral do projeto todo.
* A **Project Owner** da equipe tem uma visão mais aprofundada do produto, ela representa os interesses do cliente dentro do time. Garante que o desenvolvimento caminhe junto aos interesses do cliente. É a pessoa responsável por criar o conceito de produto do projeto e garantir que o projeto siga o que foi definido como produto.
* A **Tech Lead** é tão importante para o projeto quanto a Product Owner é importante para o produto. É ela quem garante que o projeto esteja caminhando de forma constante e entregando. A Tech Lead é a pessoa responsável por planejar as sprints e garantir que o planejamento esteja sendo seguindo, além disso é a pessoa que faz a análise do que passou e mitiga os erros e riscos. Além de unir a equipe e fazer todos caminharem para o mesmo objetivo. 
* O time de **Devs** é composto por uma equipe responsável por desenvolver e testar o que foi planejado.

<br />

| Amanda | Calebe | Indiara | Luciana | Eduardo | Luís | Micaella | Samuel | Sofia |
| --------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| Arquiteta | DevOps | Project Owner | Tech Lead | Dev | Dev | Dev | Dev | Dev |


## Práticas Ágeis 

<p> Para o planejamento, análise e desenvolvimento foram selecionadas práticas ágeis que devem ser seguidas ao longo do projeto.  </p>

### Requisitos

* **Visão do Produto**: Um momento específico no início do projeto onde a equipe se reune para fazer uma análise mais detalhada do produto, pensando nas principais entregas, nas funcionalidades de alto nível e alinhando toda a equipe sobre o projeto. 
*  **Product Backlog**: Um conjunto de funcionalidades pensadas e desejadas para o produto. 
*  **Histórias de Usuário**: Uma forma de definir e organizar os requisitos do sistema, centrando a visão no usuário. 
*  **Planning Poker**: Ao longo do projeto o planning poker é usado para pontuar as issues de forma conjunta.
*  **Canvas de Negócio**: Utilizado no projeto para obter um maior entendimento a respeito do produto.

### Desenvolvimento 

*  **Pair-Programming**: O pareamento consiste em uma forma de trocar conhecimento, alinhar o grupo, tirar dúvidas e desenvolver algo em conjunto. É o momento em que os pares se juntam para que um desenvolva e o outro axilie por um curto período até que o papel rotacione.
*  **Refatoring**: O processo de refatoração de código com o intuito de melhorar a sua estrutura sem que haja alteração no que o sistema faz. 
*  **Build Automatizado**: Utilizado para que construir a aplicação de forma automatizada, a partir de apenas um comando. 
*  **Integração Contínua**: A integração constínua é feita utlizando Travis e Codeclimate com o intuito de receber um feedback instantâneo a respeito do que foi commitado, rodando os testes e a análise do código de forma automática. 
*  **Code Reviews**: A revisão de código é feita em duas partes no projeto. A primeira é feita pela Arquiteta e o DevOps, onde eles analisam se a arquitetura está sendo seguida e também a saúde do código. A segunda parte é feita na reunião da Sprint onde o time avalia e repassa os conhecimento adquiridos, as dificuldades enfrentadas e então o que deve ser melhorado vem à tona. 
*  **Controle de Versão**: O controle de versão é feito principalmente com relação à documentação. De forma objetiva, os documentos são evoluídos constantemente e para manter o rastro disso, é feito o controle de versão. 
*  **Entregas Frequentes**: As entregas ao longo do projeto são feitas de forma frequente. Para que a equipe alcance o nível ótimo de produtividade, é preciso que as entregas sejam constantes, para isso são planejadas as entregas ao longo da sprint. 

### Testes

* **Testes Unitários**: A equipe de desenvolvimento é responsável por realizar os testes unitários de todo o código desenvolvido.
* **Testes de Aceitação**: Os testes de aceitação visam alinhas as expectativas quanto ao que foi definido no inicio do projeto e o que está sendo entregue. 

### Processo

* **Iterações**: Ao longo do projeto está sendo utilizadas técnicas como timeboxing, onde definimos um tempo limite de cada etapa de uma reunião, visando controlar o tempo. As sprints são fixas e tem duração de 1 semana, e todos os sábados há uma reunião presencial semanal. 
* **Sprint Planning**: Uma reunião no início de cada sprint para definir o que será feito de agora em diante, realizando pontuação e outras técnicas. 
* **Definição de Pronto**: No projeto, a definição de pronto é funcionando, agrega valor, testado e aprovado pelos membros responsáveis pelo code review. 
* **Daily Stand-up Meeting**: A Daily é feita presencialmente e também via issue no GitHub, onde é possível manter o traking do que está sendo feito. É obrigatória para todo o time. 
* **Velocity**: É o método utlizado para medir o que o time planeja e o que entrega, de forma que ao passar das Sprints é possível ver se o time sabe se planejar ou se planeja além do limite. 
* **Sprint Review**: É realizada na reunião da Sprint e tem como objetivo verificar e analisar o que foi feito ao longo da sprint.
* **Retrospectiva**: A retrospectiva também é realizada na reunião da Sprint e seu objetivo é fazer uma análise de como foi a sprint, o que está bom ou ruim e o que pode melhorar.
* **Backlog de Melhoria**: Onde estarão todas as atividades, features e artefatos que deverão ser evoluídos e/ou modificados.

