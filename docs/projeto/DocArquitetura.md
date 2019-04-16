# Chatbot Gaia
### Arquitetura
#### Versão 1.6


## Histórico de Revisão

| Data     | Versão |                         Descrição                                    |  Autor             |
|----------|--------|----------------------------------------------------------------------|--------------------|
|29/03/2019|   1.0  |Formatação do documento.                                              |Sofia Patrocínio    |
|29/03/2019|   1.1  |Criação dos tópicos 2.1, 2.2 e 2.3                                    |Sofia Patrocínio    |
|29/03/2019|   1.2  |Criação dos tópicos 3.1 e 3.2                                         |Micaella Gouveia    |
|29/03/2019|   1.3  |Criação do tópico 1                                                   |Samuel Pereira      |
|29/03/2019|   1.4  |Criação dos tópicos 2.4.1, 2.4.2,  2.4.3 e 2.4.4.                     |Luis Henrique Taira |
|05/04/2019|   1.5  |Adição dos tópicos 4.2.1,4.2.2,4.2.3, revisão e formatação do documento          |Micaella Gouveia    |
|12/04/2019| 1.6 | Adição do tópico 2.3 |Amanda Muniz |

## Sumário
 [1. Introdução](#_1-introdução) <br>
&emsp; [1.1 Finalidade](#_11-objetivo) <br>
&emsp; [1.2 Escopo](#_12-escopo) <br>
&emsp; [1.3 Definições, Acrônimos e Abreviações](#_13-definições-acrônimos-e-abreviações) <br>
&emsp; [1.4 Referências](#_14-referências) <br>
&emsp; [1.5 Visão Geral](#_15-visão-geral) <br>
[2. Representação Arquitetural](#_2-representação-arquitetural) <br>
&emsp; [2.1 Diagrama de Relações](#_21-diagrama-de-relações) <br>
&emsp; [2.2 Representação dos Microsserviços](#_22-representação-dos-microsserviços) <br>
&emsp; &emsp; [2.2.1 Cronjob Notifica](#_221-cronjob-notifica) <br>
&emsp; &emsp; [2.2.2 Busca Clima](#_222-busca-clima) <br>
&emsp; &emsp; [2.2.3 Escolhe Esporte](#_223-escolher-esporte) <br>
&emsp; &emsp; [2.2.4 Busca Local](#_224-busca-local) <br>
&emsp; &emsp; [2.2.5 API Gateway](#_225-api-gateway) <br>
&emsp; [2.3 Padrões](#_23-padrões) <br>
&emsp; &emsp; [2.3.1 Padrão API Gateway](#_231-padrão-api-gateway) <br>
&emsp; &emsp; [2.3.2 Padrão API Composition](#_232-padrão-api-composition) <br>
&emsp; [2.4 Tecnologias](#_24-tecnologias) <br>
&emsp; &emsp; [2.4.1 API de bot do Telegram](#_241-api-de-bot-do-telegram) <br>
&emsp; &emsp; [2.4.2 API de mensagens do Facebook Messenger](#_242-api-de-mensagens-do-facebook-messenger) <br>
&emsp; &emsp; [2.4.3 API OpenWeatherMap](#_243-api-de-openweathermap) <br>
&emsp; &emsp; [2.4.4 Google Maps Geocoding API](#_244-google-maps-geocoding-api) <br>
&emsp; &emsp; [2.4.5 Python](#_245-python) <br>
&emsp; &emsp; [2.4.6 JavaScript](#_246-javascript) <br>
[3. Metas e Restrições da Arquiteura](#_3-metas-e-restrições-da-arquitetura) <br>
&emsp; [3.1 Metas](#_31-metas) <br>
&emsp; [3.2 Restrições](#_31-restrições) <br>
[4. Visão Lógica](#_4-visão-lógica) <br>
&emsp; [4.1. Visão Geral](#_41-visão-geral) <br>
&emsp; [4.2. Pacotes de Design Significativos do Ponto de Vista da Arquitetura](#_42-pacotes-de-design-significativos-do-ponto-de-vista-da-arquitetura) <br>
&emsp; &emsp; [4.2.1 Diagrama de Pacotes](#_421-diagrama-de-pacotes) <br>
&emsp; &emsp; [4.2.2 Diagrama de Classes](#_422-diagrama-de-classes) <br>
&emsp; &emsp; [4.2.3 Diagramas de Fluxo](#_423-diagramas-de-fluxo) <br>

## 1. Introdução
### 1.1 Finalidade
<p align="justify">&emsp;&emsp;Este documento tem como finalidade fornecer uma visão geral da arquitetura do Gaia, utilizando-se de diversas visões arquiteturais - tais como a visão lógica e de caso de uso  - a fim de facilitar o entendimento dos processos e funcionamento de todo o sistema. Tem também como objetivo transmitir as decisões arquiteturais significativas tomadas em relação ao mesmo.</p>

### 1.2 Escopo
<p align="justify">&emsp;&emsp;Através desse documento, é possível obter um melhor entendimento da arquitetura do Gaia, permitindo ao leitor compreender o funcionamento de seu sistema, como também a abordagem utilizada para o seu desenvolvimento.</p>

### 1.3 Definições, Acrônimos e Abreviações
| Termo | Definição |
|--|--|
| API | Application Program Interface (Interface de Programação de Aplicações) |
| HTTP | HyperText Transfer Protocol (Protocolo de Transferência de Hipertexto) |
| Chatbot | Software de inteligência artificial o qual simula uma conversação humana de forma interativa |

### 1.4 Referências
>The Rasa Core dialogue engine; Disponível em: <https://rasa.com/docs/core/>; Acesso em 29 de março de 2019.
>Rasa NLU> Language Understanding for chatbots and AI assistants; Disponível em:<https://rasa.com/docs/nlu/>; Acesso em 29 de março de 2019.
>SANTO, Marco; A importância de um API Gateway na arquitetura de microsserviços; Disponível em: <http://dtidigital.com.br/blog/a-importancia-de-um-api-gateway-na-arquitetura-de-microsservicos/>; Acesso em 29 de março de 2019.
>JUNIOR, Luiz Fernando Duarte; API Gateway em arquitetura de microsserviços com Node.js; Disponível em: <https://imasters.com.br/apis-microsservicos/api-gateway-em-arquitetura-de-microservices-com-node-js>: Acesso em 29 de março de 2019.
>LEWIS, James; FOWLER, Martin; Microsserviços em poucas palavras; Disponível em: <https://www.thoughtworks.com/pt/insights/blog/microservices-nutshell>; Acesso em 29 de março de 2019.
>MARIOTTI, Flávio. Como documentar a Arquitetura de Software. Disponível em: <http://www.linhadecodigo.com.br/artigo/3343/como-documentar-a-arquitetura-de-software.aspx>. Acesso em: 29 de março de 2019.
>SILVA, Ana Carolina; DINIZ, Arthur; OLIVEIRA, Bruna; SILVA, Guilherme; LACERDA, Guilherme; OLIVEIRA, Ícaro; GOMES, Weyler; BESSA, Cecília; FILHO, Elmar; CLÍMACO, Gabriel; FERREIRA, Maria Calorina; SOUZA, Júlio. Trezentos: Documento de Arquitetura. Disponível em: <https://github.com/fga-eps-mds/2017.1-Trezentos/wiki/Documento-de-Arquitetura>. Acesso em: 29 de março de 2019.
>KAMAL, Byron; CERQUEIRA, Eduardo; ALVES, Gabriel; ARAGÃO, Igor; GUIMARÃES, Igor; JARDIM, João Pedro; DOS SANTOS, Marcelo; ASSUNÇÃO, Mateus; ALMEIDA, William. IncluCare: Architecture Document. Disponível em: <https://github.com/fga-eps-mds/2018.1-IncluCare_API/blob/master/docs/ARCHITECTURE_DOCUMENT.md>. Acesso em: 29 de março de 2019.
>The API Gateway Pattern; Disponível em: <https://freecontent.manning.com/the-api-gateway-pattern/>; Acesso em 12 de abril de 2019.
>RICHARDSON, Chris; Pattern: API Composition; Disponível em: <https://microservices.io/patterns/data/api-composition.html>; Acesso em 12 de abril de 2019.

### 1.5 Visão Geral
<p align="justify">&emsp;&emsp;Este documento apresenta, de forma detalhada, a arquitetura, os requisitos e as decisões tomadas a respeito do Gaia.</p>
<p align="justify">&emsp;&emsp;O documento está estruturado da seguinte maneira:</p>
<ul>
	<li>Histórico da Revisão: Responsável por deixar explícito cada alteração feita no documento e as informações a respeito do mesmo;</li>
	<li>Introdução: Fornece uma visão geral do documento inteiro;</li>
	<li>Representação arquitetural: Descreve qual é a arquitetura de software do sistema atual e como ela é representada;</li>
	<li>Metas e restrições da arquitetura: Descreve os requisitos e objetivos do software que têm algum impacto sobre a arquitetura;</li>
	<li>Visão Lógica: Descreve as partes significativas do ponto de vista da arquitetura do modelo de design;</li>
	<li>Visão de Processos: descreve a decomposição do sistema em processos leves e
processos pesados;</li>
<li>Visão de Implantação: descreve uma ou mais configurações da rede física na qual o software é implantado e executado;</li>
<li>Visão de Implementação: descreve a estrutura geral do modelo de implementação, a divisão do software em camadas e os subsistemas no modelo de implementação e todos os componentes significativos do ponto de vista da arquitetura;</li>
<li>Visão de Dados: descreve a perspectiva de armazenamento de dados persistentes do sistema;</li>
<li>Tamanho e Desempenho: descreve as principais características de dimensionamento do software que têm um impacto na arquitetura, bem como as restrições do desempenho desejado;</li>
<li>Qualidade: descreve como a arquitetura do software contribui para todos os recursos (exceto a funcionalidade) do sistema.</li>
</ul>

## 2. Representação Arquitetural
### 2.1 Diagrama de Relações

![alt text](https://i.imgur.com/cceUiwD.png)

<p align="justify">&emsp;&emsp;O estilo arquitetural de microsserviços é uma abordagem que visa implementar uma aplicação como uma suíte de pequenos serviços. Onde cada um executa um processo próprio e se comunica, geralmente, com requests HTTP. Tendo em vista a principal característica desse estilo arquitetural, a independência entre os serviços, o chatbot Gaia terá microsserviços como parte de sua arquitetura. </p>
<p align="justify">&emsp;&emsp;Além disso, cada serviço interno da Gaia terá seu próprio repositório. Destacando assim, mais uma característica desse estilo arquitetural, onde cada um deles terá seu próprio ambiente, tecnologias, integração contínua e deploy.</p>
<p align="justify">&emsp;&emsp;Os serviços que serão implementados na Gaia foram pensados para serem modulares, muitas vezes existindo apenas para executar uma função específica. Sendo assim, os serviços internos que fazem parte da Gaia são:</p>
<ul>
<li>API Gateway;</li>
<li>Cronjob Notifica;</li>
<li>Busca Clima;</li>
<li>Escolhe Esporte;</li>
<li>Busca Local.</li></ul>
<p align="justify">&emsp;&emsp;Para a execução completa do projeto será necessário consumir dados de fontes externas, sendo elas:</p>
<ul>
<li>API Telegram;</li>
<li>API Facebook;</li>
<li>API OpenWeatherMaps;</li>
<li>API GoogleMaps.</li></ul>
<p align="justify">&emsp;&emsp;Além do comportamento interno da Gaia, outro fator importante a ser considerado é a criação do chatbot em si. Para isso, vários fatores precisam ser considerados, como o uso de linguagem natural. Por isso, será utilizado a tecnologia Rasa, que se divide em Rasa Core e Rasa NLU. Rasa Core é de extrema importância para criar um bot baseado em Machine Learning. Já o Rasa NLU é responsável pelo processamento da linguagem natural. Essa combinação vai garantir que a Gaia tenha uma comunicação acessível com o usuário.</p>

### 2.2 Representação dos Microsserviços

#### 2.2.1 Cronjob Notifica
<p align="justify">&emsp;&emsp;O termo Cronjob ou Cron Job refere-se a tarefas que são executadas de forma automática dado um intervalo de tempo. Por isso, um microsserviço essencial para a Gaia é um cronjob de notificação. Ele será responsável por registrar as preferências de um usuário, sendo elas, uma cidade e um tempo determinado para a notificação; além de mandar o alerta para o chat com as condições climáticas da localização desejada no período esperado pelo usuário.</p>

#### 2.2.2 Busca Clima
<p align="justify">&emsp;&emsp;O microsserviço “Busca Clima” é responsável por fazer requisições para a API externa do OpenWeatherMaps. A necessidade dessa funcionalidade ocorre por haver uma limitação de requisições diárias na versão livre dessa API. Dessa forma, todos os pedidos de dados feitos ao OpenWeatherMaps estarão centralizadas em um só local. Além disso, esse microsserviço também será responsável por informar o usuário sobre as condições climáticas de qualquer local do mundo.</p>

#### 2.2.3 Escolhe Esporte
<p align="justify">&emsp;&emsp;Este microsserviço tem como responsabilidade indicar um esporte ou uma lista de esportes ao usuário, baseado nas condições climáticas da cidade. Ou seja, o usuário perguntará quais são os melhores esportes para serem praticados naquele determinado clima, e o microsserviço terá que comparar as variáveis presentes nas condições climáticas, com a condição climática ideal dos esportes e retornar esse informação ao usuário.</p>

#### 2.2.4 Busca Local
<p align="justify">&emsp;&emsp;O microsserviço “Busca Local” é responsável por receber o nome de uma cidade e responder com a sua latitude e longitude exata. Isso é necessário, uma vez que, a API OpenWeatherMaps não retorna informações com o nome exato do local como parâmetro - para cidades que não são capitais, mas se tiver a latitude e longitude sim. Por isso, um microsserviço responsável por fazer requisições a API do Google Maps é de extrema importância para manter um diálogo fácil com o usuário e retornar as informações certas sobre a condição climática.</p>

#### 2.2.5 API Gateway
<p align="justify">&emsp;&emsp;Dentro de uma arquitetura de microsserviços ter um API Gateway é importante para gerenciar o acesso às API’s de um determinado sistema. Ou seja, ele é um padrão de software que funciona de forma similar a uma fachada sendo o único ponto de acesso, - que controla as entradas e saídas de dados, o tráfego de tarefas e monitora, - para as API’s internas. Sua existência reduz problemas causados pela interação entre cliente e microsserviços, além de conservar o ambiente dos serviços. </p>

### 2.3 Padrões

#### 2.3.1 Padrão API Gateway
<p align="justify">&emsp;&emsp;Uma API Gateway é um serviço responsável por uma única entrada para os serviços internos. Ela organiza e recebe as requisições externas e as distribui para os microsserviços internos. Além disso, ela precisa se preocupar com as prioridades de requisição e com autenticação.</p>
<p align="justify">&emsp;&emsp;O Padrão API Gateway é bastante similar ao padrão Facade (Fachada), já que também encapsula a arquitetura interna e provê uma API para os usuários. Suas principais responsabilidades são encaminhar as requisições, compor a API, gerenciar os requests utilizando o padrão API Composition, - ao chamar os diferentes microsserviços e agregar os resultados em uma resposta para o usuário. Cada uma dessas responsabilidades possui características próprias e para o entendimento do padrão API Gateway é preciso entender cada uma delas.</p>
<p align="justify">&emsp;&emsp;O encaminhamento das requisições é uma das funções principais de uma API Gateway. Ela funciona implementando operações que encaminhem as requisições para o microsserviço correto.</p>
<p align="justify">&emsp;&emsp;A composição da API garante que a API Gateway seja mais do que um conjunto de funções para encaminhar requisições. Essa composição é feita, geralmente, utilizando o padrão API Composition.</p>
<p align="justify">&emsp;&emsp;Além dessas duas principais responsabilidades a API Gateway lida com funções como autenticação, autorização, respostas de cache, cors e requisições de log.</p>

#### 2.3.2 Padrão API Composition
<p align="justify">&emsp;&emsp;Ao encaminhar as requisições para os microsserviços internos a API Gateway irá desmembrar a requisição em pedidos menores e irá mandá-los para cada um dos microsserviços correspondentes. A papel do padrão API Composition é  pegar os resultados individuais de cada microsserviço anteriormente solicitado e compor uma resposta única que será mandado para o usuário.</p>


## 2.4 Tecnologias

#### 2.4.1 API do Bot de Telegram
<p align="justify">&emsp;&emsp;A API de bot do Telegram permite que bots interajam diretamente com usuários por meio de mensagens e comandos.</p>
<p align="justify">&emsp;&emsp;O telegram exige uma conexão HTTPS para interagir com a API e pede que todos os desenvolvedores suportem os comandos ‘/start’, ‘/help’, e ‘/settings’ em seus bots para facilitar a interação de usuários com a multitude de bots existentes. </p>

#### 2.4.2 API de Mensagens do Facebook Messenger
<p align="justify">&emsp;&emsp;O Messenger permite que bots mandem e recebam mensagens por meio de sua API.</p>
<p align="justify">&emsp;&emsp;Diferentemente de outras APIs para bots, a do Messenger possui a política chamada de ‘24+1’, que impõe um limite de 24 horas para que bots mandem mensagens para usuários após o usuário contatar o bot, sendo permitido que o bot mande uma mensagem depois de o limite de 24 horas ter expirado.</p>
<p align="justify">&emsp;&emsp;A API do Messenger disponibiliza também um modo, que está em beta, de mensagens por inscrição, que permite que bots mandem mensagens periódicas para usuários, sem que exista um limite de 24 horas. </p>

#### 2.4.3 API do OpenWeather
<p align="justify">&emsp;&emsp;A API do openweathermap.org é capaz de fornecer um grande número de informações relacionadas a previsão do tempo e principalmente de condições climáticas atuais com base em localização.</p>
<p align="justify">&emsp;&emsp;Podem ser fornecidos nomes de capitais ou coordenadas de localização para se obter dados da API.</p>


#### 2.4.4 Google Maps Geocoding API
<p align="justify">&emsp;&emsp;A Geocoding API do Google Maps fornece coordenadas geográficas quando a ela é fornecido o nome de um lugar como: lago Paranoá, Águas Claras, DF, Brasil.</p>
<p align="justify">&emsp;&emsp;As coordenadas fornecidas pela API serão fornecidas a API do OpenWeatherMap.</p>
<p align="justify">&emsp;&emsp;A Geocoding API também pode fornecer informações sobre o lugar fornecido como endereço legível por humanos, CEP e tipo de localização.</p>

#### 2.4.5 Python
<p align="justify">&emsp;&emsp;Python é uma moderna linguagem interpretada de alto nível é será utilizada no front end da aplicação em conjunto com os frameworks Rasa NLU e Rasa Core.</p>

#### 2.4.6 JavaScript
<p align="justify">&emsp;&emsp;JavaScript é uma linguagem interpretada de alto nível é será utilizada no back end da aplicação em conjunto com o framework Node.js</p>


## 3. Metas e Restrições de Arquitetura
### 3.1 Metas
<p align="justify">&emsp;&emsp;Possuímos as seguintes metas:</p>
Funcionar nos serviços de mensagens instantâneas Telegram e Messenger.
Consumir as API’s do Telegram, Facebook, OpenWeatherMaps, GoogleMaps.

### 3.2 Restrições
<p align="justify">&emsp;&emsp;Possuímos as seguintes restrições:</p>
Rasa: Framework para o desenvolvimento do chatbot
Python : Linguagem base das aplicações do front-end
Node.js : Plataforma de aplicação utilizada para o back-end
JavaScript : linguagem base do Node.js
MongoDB : Software utilizado para o banco de dados


## 4. Visão Lógica
### 4.1 Visão Geral
<p align=”justify”>&emsp;&emsp; A aplicação do ChatBot Gaia é construída sobre o framework Rasa em linguagem Python no front-end e sobre a plataforma Node.js em linguagem JavaScript no back-end. O objetivo do RasaNLU é aplicar algoritmos de linguagem natural para extrair a intenção do usuário (intents) e a partir do Rasa Core é possível gerir o diálogo entre o usuário e o bot. A principal funcionalidade é o policy, que recebe a intent do usuário, atualiza o tracker() e prevê a melhor ação do bot (utter, action, listening). A plataforma Node.js é um ambiente de tempo de execução que executa o código em JavaScript para escrever ferramentas de linha de comando e para scripts do lado do servidor, capaz de executar uma entrada/saída assíncrona, que permite que outro processamento continue antes que a transmissão tenha encerrado.</p>

### 4.2 Pacotes de Design Significativos do Ponto de Vista da Arquitetura

#### 4.2.1 Diagrama de pacotes
![alt text](https://i.imgur.com/HuuLyBC.png)

#### 4.2.2 Diagrama de classe
![alt text](https://i.imgur.com/GpuBj8p.png)

#### 4.2.3 Diagramas de fluxo
<p align="justify">&emsp;&emsp;Fluxo do Rasa:</p>

![alt text](https://i.imgur.com/ik3vWjQ.jpg)

<p align="justify">&emsp;&emsp;Fluxo do Node.js:</p>

![alt text](https://i.imgur.com/TtAzsd6.png)
