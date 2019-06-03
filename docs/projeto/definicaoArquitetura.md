# Definição Arquitetural da Gaia

## 1. Estilo arquitetural definido

<p align="justify">&emsp;&emsp;Para o chatbot Gaia será utilizado o estilo arquitetural de microsserviços. Essa arquitetura é focada no desenvolvimento de uma única aplicação com pequenos serviços internos. Cada serviço é independente, podendo ter sua própria tecnologia, ambiente de desenvolvimento, integração contínua e deploy. O objetivo por trás dessa independência é ter serviços modulares e de fácil manutenção.</p>

<p align="justify">&emsp;&emsp;Esses microsserviços são gerenciados por uma API Gateway, que é uma parte do sistema responsável por controlar o acesso aos microsserviços internos. Ela funciona de forma similar a uma fachada (padrão de software), sendo o único ponto de acesso a esses serviços. A API Gateway pode reduzir os problemas causados pelas interações cliente-serviço e melhora a conservação do ambiente dos microsserviços. Além disso, ela também controla as requisições e saídas de dados, que nesse estilo arquitetural são feitas através de requests HTTP.</p>

<p align="justify">&emsp;&emsp;Sendo assim, a Gaia terá dois microsserviços e um
Gateway para formar a API da aplicação e um sistema para a construção do bot em si. Ao todo os sistemas são Gaia, Gaia-Esporte, Gaia-Ciclone e Gaia-Gateway. </p>

<p align="justify">&emsp;&emsp;A Gaia será o serviço do bot, que será construído utilizando as tecnologias Rasa Core e Rasa NLU. Ela será responsável por lidar com o contato com o usuário, ao manter um diálogo com o mesmo. Além disso, terá que respeitar a manter a personalidade do bot e precisará mandar as requisições do usuário para os serviços internos.</p>

<p align="justify">&emsp;&emsp;O Gaia-Gateway é o serviço onde os padrões API Gateway e API Composition serão implementados. Ele será responsável por lidar com as requisições externas para os microsserviços. Ele quebrará o pedido do usuário em pequenas requisições, se necessário, e as mandará para o microsserviço responsável. E pagará as respostas individuais dos serviços e montará a resposta completa que deverá ser enviada para o usuário. Por ser o grande responsável pelas requisições, terá que lidar com autenticação, autorização, CORS, cache e logs. Não só isso, mas será o principal foco na parte de integração REST.</p>

<p align="justify">&emsp;&emsp;O microsserviço Gaia-Esporte é um cronjob que possui duas funcionalidades principais: indicar o melhor esporte a ser praticado de acordo com as condições climáticas do dia e mandar notificações para o usuário. Para a realização dessas duas funcionalidades, é preciso que o microsserviço realize outras tarefas, sendo elas: indicar o clima atual de determinada localidade, indicar a previsão do tempo de até cinco dias e indicar a latititude e longitude ao receber o nome de uma cidade. </p>

<p align="justify">&emsp;&emsp;Para que esse microsserviço consiga indicar informações sobre o clima, é preciso consumir dados da API externa OpenWeatherMap. Como essa API dificulta o acesso com apenas o nome de uma localidade, é preciso saber a latitude e longitude do mesmo. Por isso, Gaia-Esporte irá consumir dados da API externa OpenCage Geocoder e salvará as coordenadas recebidas em cada requisição, para que ao longo do tempo a dependência para com essa tecnologia externa se torne menor. Com as informações conseguidas com essas duas api, o microsserviço será capaz de lidar com as notificações do usuário.</p>

<p align="justify">&emsp;&emsp;O microsserviço Gaia-Ciclone será um cronjob de notificação. Ele, assim como o Gaia-Notifica, terá um user e mandará notificações para ele. A diferença entre os dois é que esse microsserviço terá que mandará uma notificação sempre que um Ciclone estiver ocorrendo em alguma parte do mundo. Para isso, ele consumirá dados da API Externa Aeris Weather, sempre fazendo uma nova requisição a cada duas horas. Além disso, consumirá também a API OpenCage Geocoder para informar o nome exato do local que está sendo atingido pelo ciclone. </p>

## 2. Tecnologias escolhidas

### 2.1 Rasa
<p align="justify">&emsp;&emsp;Rasa é um conjunto de ferramentas para Python para a criação de bots. Ele tem duas principais frentes, o Rasa Core e o Rasa NLU. O Rasa Core baseia o desenvolvimento em Machine Learning, onde você consegue treinar e atualizar as models “conversando” e provendo feedback para o bot. Já o Rasa NLU é responsável pelo processamento da linguagem natural. O Rasa foi escolhido por ser open-source e porque a equipe precisa ter o maior controle possível sobre a Gaia, sem que ela perca seu nível de customização. </p>


### 2.2 Node.js
<p align="justify">&emsp;&emsp;Node.js é uma plataforma de aplicação para Javascript, que tem como principal objetivo facilitar a construção de softwares escaláveis. Ele geralmente é usado ao lado do servidor e é orientado para o estilo de programação voltada a  evento. Isso faz com que ele seja leve, eficiente e uma boa alternativa para arquitetura de microsserviços.</p>

### 2.3 MongoDB
<p align="justify">&emsp;&emsp;MongoDB é um framework de banco de dados noSQL. Ele é orientado a documento, livre de esquemas, não relacional, e open-source. MongoDB trabalha com arquivos JSON que contém toda a informação do banco de dados. Ele foi escolhido por ser facilmente escalável horizontalmente, mas ainda sim se manter simples.  </p>

## 3. Arquitetura de integração de microsserviços
<p align="justify">&emsp;&emsp;O estilo arquitetural da integração de microsserviços que será utilizado na Gaia é o estilo orquestrado. Ele é caracterizado por centralizar o ponto de comando, nesse caso a API Gateway, que deve ser responsável por fazer as requisições aos microsserviços e compor uma resposta final ao usuário com os retornos individuais de cada microsserviço.</p>

<p align="justify">&emsp;&emsp;Dentro do estilo orquestrado será utilizada a integração REST. Ela é capaz de garantir a passagem de informações entre cliente e servidor de forma mais atómica possível. Ela é usada para requisições HTTP, sendo capaz de as receber e enviar sem perder dados. Essa escolha foi feita porque esse tipo de integração é capaz de suportar o uso de cache e consegue possibilitar maior autonomia e flexibilidade entre os microsserviços.</p>


## Referências

>The Rasa Core dialogue engine; Disponível em: <https://rasa.com/docs/core/>; Acesso em 29 de março de 2019.

>Rasa NLU> Language Understanding for chatbots and AI assistants; Disponível em:<https://rasa.com/docs/nlu/>; Acesso em 29 de março de 2019.


>SANTO, Marco; A importância de um API Gateway na arquitetura de microsserviços; Disponível em: <http://dtidigital.com.br/blog/a-importancia-de-um-api-gateway-na-arquitetura-de-microsservicos/>; Acesso em 29 de março de 2019.

>JUNIOR, Luiz Fernando Duarte; API Gateway em arquitetura de microsserviços com Node.js; Disponível em: <https://imasters.com.br/apis-microsservicos/api-gateway-em-arquitetura-de-microservices-com-node-js>: Acesso em 29 de março de 2019.
>LEWIS, James; FOWLER, Martin; Microsserviços em poucas palavras; Disponível em: <https://www.thoughtworks.com/pt/insights/blog/microservices-nutshell>; Acesso em 29 de março de 2019.

>NDISCII, Diyin; Rasa Core open source machine learning framework builds better bots; Disponível em: <https://www.whatsnewonthenet.com/blog/the-rasa-core-open-source-machine-learning-framework-builds-better-bots-10112017/>; Acesso em 29 de março de 2019.

>O que é Node.JS; Disponível em: <http://nodebr.com/o-que-e-node-js/>; Acesso em 29 de março de 2019.

>HIGOR; Introdução ao MongoDB; Disponível em: <https://www.devmedia.com.br/introducao-ao-mongodb/30792>; Acesso em 29 de março de 2019.

>ROZLOG, Mike; REST e SOAP: Usar um dos dois ou ambos?; Disponível em: <https://www.infoq.com/br/articles/rest-soap-when-to-use-each>; Acesso em 29 de abril de 2019.

>SCHMITZ, Daniel; A evolução do MVC para REST; Disponível em: <https://imasters.com.br/devsecops/a-evolucao-do-mvc-para-rest>; Acesso em 29 de abril de 2019.

>SCHMITZ, Daniel; Exemplo de Integração REST entre servidor e cliente; Disponível em: <https://imasters.com.br/desenvolvimento/exemplo-de-integracao-rest-entre-servidor-e-cliente>; Acesso em 29 de abril de 2019.
