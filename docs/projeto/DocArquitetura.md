# Chatbot Gaia
### Arquitetura
#### Versão 1.7


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
|17/04/2019| 1.7 | Revisão geral, adição de novas versões dos diagramas, correção de informações |Amanda Muniz |
|25/05/2019| 1.8 | Adição do microsserviço Gaia-Ciclone |Amanda Muniz |
|29/05/2019| 1.9 | Remoção versão da arquitetura da release 1| Amanda Muniz |
|29/05/2019| 2.0 | Mudança da arquitetura | Amanda Muniz |
|29/05/2019| 2.1 | Refatoração do diagrama de relações | Amanda Muniz |
|20/06/2019| 2.2 | Refatoração dos diagramas de pacotes e classe | Amanda Muniz |

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
&emsp; &emsp; [2.2.1 Gaia-Esporte](#_221-gaia-esporte) <br>
&emsp; &emsp; [2.2.2 Gaia-Ciclone](#_222-gaia-ciclone) <br>
&emsp; &emsp; [2.2.3 API Gateway](#_223-api-gateway) <br>
&emsp; [2.3 Padrões](#_23-padrões) <br>
&emsp; &emsp; [2.3.1 Padrão API Gateway](#_231-padrão-api-gateway) <br>
&emsp; &emsp; [2.3.2 Padrão API Composition](#_232-padrão-api-composition) <br>
&emsp; [2.4 Tecnologias](#_24-tecnologias) <br>
&emsp; &emsp; [2.4.1 API de bot do Telegram](#_241-api-de-bot-do-telegram) <br>
&emsp; &emsp; [2.4.2 API de mensagens do Facebook Messenger](#_242-api-de-mensagens-do-facebook-messenger) <br>
&emsp; &emsp; [2.4.3 OpenWeatherMap API](#_243-openweathermap-api) <br>
&emsp; &emsp; [2.4.4 OpenCage Geocoder API](#_244-opencage-geocoder-api) <br>
&emsp; &emsp; [2.4.5 Rasa](#_245-rasa) <br>
&emsp; &emsp; [2.4.6 NodeJS](#_246-nodejs) <br>
&emsp; &emsp; [2.4.7 MongoDB](#_247-mongodb) <br>
[3. Metas e Restrições da Arquiteura](#_3-metas-e-restrições-da-arquitetura) <br>
&emsp; [3.1 Restrições Tecnológicas](#_31-restrições-tecnológicas) <br>
&emsp; [3.2 Requisitos Não Funcionais](#_31-requisitos-não-funcionais) <br>
[4. Visão Lógica](#_4-visão-lógica) <br>
&emsp; [4.1. Visão Geral](#_41-visão-geral) <br>
&emsp; [4.2. Pacotes de Design Significativos do Ponto de Vista da Arquitetura](#_42-pacotes-de-design-significativos-do-ponto-de-vista-da-arquitetura) <br>
&emsp; &emsp; [4.2.1 Diagrama de Pacotes](#_421-diagrama-de-pacotes) <br>
&emsp; &emsp; [4.2.2 Diagrama de Classes](#_422-diagrama-de-classes) <br>
&emsp; &emsp; &emsp; [4.2.2.1 Diagrama de Classe do Gaia-Esporte](#_4221-diagrama-de-classe-do-gaia-esporte) <br>
&emsp; &emsp; &emsp; [4.2.2.2 Diagrama de Classe do Gaia-Ciclone](#_4222-diagrama-de-classe-do-gaia-ciclone) <br>

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

![](../assets/imgs/architecture/arquiteturaV06.png)
Imagem 01 - Representação da arquitetura através de um diagrama de relações

<p align="justify">&emsp;&emsp;O estilo arquitetural de microsserviços é uma abordagem que visa implementar uma aplicação como uma suíte de pequenos serviços. Onde cada um executa um processo próprio e se comunica, geralmente, com requests HTTP. Tendo em vista a principal característica desse estilo arquitetural, a independência entre os serviços, o chatbot Gaia terá microsserviços como parte de sua arquitetura. </p>
<p align="justify">&emsp;&emsp;Além disso, cada serviço interno da Gaia terá seu próprio repositório. Destacando assim, mais uma característica desse estilo arquitetural, onde cada um deles terá seu próprio ambiente, tecnologias, integração contínua e deploy.</p>
<p align="justify">&emsp;&emsp;Os serviços que serão implementados na Gaia foram pensados para serem modulares, muitas vezes existindo apenas para executar uma função específica. Sendo assim, os serviços internos que fazem parte da Gaia são:</p>
<ul>
<li>API Gateway;</li>
<li>Gaia-Esporte;</li>
<li>Gaia-Ciclone.</li></ul>
<p align="justify">&emsp;&emsp;Para a execução completa do projeto será necessário o consumo de dados de fontes externas, sendo elas:</p>
<ul>
<li>API Telegram;</li>
<li>API Facebook;</li>
<li>API OpenWeatherMaps;</li>
<li>API OpenCage Geocoder;</li>
<li>API Aeris Weather;</li></ul>
<p align="justify">&emsp;&emsp;Além do comportamento interno da Gaia, outro fator importante a ser considerado é a criação do chatbot em si. Para isso, vários fatores precisam ser considerados, como o uso de linguagem natural. Por isso, será utilizado a tecnologia Rasa, que se divide em Rasa Core e Rasa NLU. Rasa Core é de extrema importância para criar um bot baseado em Machine Learning. Já o Rasa NLU é responsável pelo processamento da linguagem natural. Essa combinação vai garantir que a Gaia tenha uma comunicação acessível com o usuário.</p>

### 2.2 Representação dos Microsserviços

#### 2.2.1 Gaia-Esporte
<p align="justify">&emsp;&emsp;O microsserviço Gaia-Esporte é responsável por lidar com o core do projeto, - indicação de esportes. Para isso ele possui diversas funcionalidades. A principal delas é o cronjob de notificação, que irá manter notificações. Isso será feito registrando as preferências do usuário, sendo elas, uma cidade, um esporte, um tempo determinado para a notificação. Além disso, deverá mandar o alerta para o chat com as condições climáticas da localização desejada no período esperado pelo usuário.</p>

<p align="justify">&emsp;&emsp;Para mandar as notificações será preciso saber as condições climáticas. Isso traz a necessidade das funcionalidades referentes ao clima: indicar o clima atual e indicar a previsão do tempo de até cinco dias. Para essas funcionalidades serem possíveis, o microsserviço irá consumir a API Externa OpenWeatherMaps e irá tratar os dados que são recebidos.  </p>

<p align="justify">&emsp;&emsp;Porém, a API OpenWeatherMaps não retorna informações com o nome exato do local como parâmetro - para cidades que não são capitais, mas se tiver a latitude e longitude sim. Portanto, o microsserviço irá fazer requisições para a API externa OpenCage Geocoder, para receber a latitude e longitude exata de um local. Isso é de extrema importância para manter um diálogo fácil com o usuário.</p>

<p align="justify">&emsp;&emsp;A última funcionalidade presente neste microsserviço é a indicação de um esporte ou uma lista de esportes ao usuário, baseado nas condições climáticas da cidade. Ou seja, o usuário perguntará quais são os melhores esportes para serem praticados naquele determinado clima, e o microsserviço terá que comparar as variáveis presentes nas condições climáticas, com a condição climática ideal dos esportes e retornar esse informação ao usuário.</p>

#### 2.2.2 Gaia-Ciclone

<p align="justify">&emsp;&emsp;O microsserviço Gaia-Ciclone é responsável por manter notificações sobre furacões, tufões e ciclones. Ele deve fazer requisições para a API externa Aeris Weather a cada duas horas, no endpoint /tropicalcyclones que retorna a lista de ciclones que estão acontecendo. Sempre que essa lista retornar um objeto, o microsserviço terá que mandar notificações para os usuários que a agendaram anteriormente. Além disso, em sua resposta deve conter o nome da localidade que está sofrendo com as tempestades de vento. Por isso, deverá fazer requisições para a API OpenCage Geocoder.</p>

#### 2.2.3 API Gateway
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
<p align="justify">&emsp;&emsp;A API de bot do Telegram permite que bots interajam diretamente com usuários por meio de mensagens e comandos. Ela será usada para um dos deploys, de forma a garantir que a Gaia consiga atingir uma faixa de usuários que não utilizam o Facebook. Para isso a Gaia precisará atender alguns critérios, já que o Telegram exige uma conexão HTTPS para interagir com a API e pede que todos os desenvolvedores suportem os comandos ‘/start’, ‘/help’, e ‘/settings’ em seus bots para facilitar a interação de usuários. </p>

#### 2.4.2 API de Mensagens do Facebook Messenger
<p align="justify">&emsp;&emsp;O Messenger permite que bots mandem e recebam mensagens por meio de sua API. Porém diferente de outras, o Messenger possui uma política chamada de ‘24+1’. Essa política impõe um limite de 24 horas, após o contato do usuário, para que os bots consigam mandar mensagens resposta, sendo permitido o envio de uma úncia mensagem depois desse limite ter expirado. A API do Messenger disponibiliza também um modo, atualmente em beta, de mensagens por inscrição que permite que bots mandem mensagens periódicas para usuários sem que exista um limite.</p>

#### 2.4.3 OpenWeatherMap API
<p align="justify">&emsp;&emsp;A API do OpenWeatherMap é capaz de fornecer um grande número de informações relacionadas a previsão do tempo e principalmente de condições climáticas atuais com base em localização, tanto pelo nome de capitais quanto pelas coordenadas geográficas. Além disso, a OpenWeatherMaps possui diferentes categorias para requests. A Gaia irá utilizar duas dessas categorias, a Current Weather para o microsserviço clima e a 5 days/3 hours forecast para o cronjob de notificação.</p>


#### 2.4.4 OpenCage Geocoder API
<p align="justify">&emsp;&emsp; A API OpenCage Geocoder converte coordenadas em nome de lugares e vice-versa. Ela será utilizada pela Gaia no microsserviço Gaia-Local. Isso é necessário porque a API externa OpenWeatherMap só consegue fornecer o clima por nome para cidades grandes. Portanto, a OpenCage Geocoder será acessada sempre que o usuário falar o nome de um local, para que o microsserviço Gaia-Clima consiga forncer o clima a partir da latitude e longitude de um lugar.</p>

#### 2.4.5 Rasa

![](../assets/imgs/architecture/diagramaFluxoRASA.jpeg)
Imagem 02 - Fluxo básico da tecnologia Rasa

<p align="justify">&emsp;&emsp;Rasa é um conjunto de ferramentas para Python para a criação de bots. Ele tem duas principais frentes, o Rasa Core e o Rasa NLU. O Rasa Core baseia a o desenvolvimento em Machine Learning, onde você consegue treinar e atualizar as models “conversando” e provendo feedback para o bot. Já o Rasa NLU é responsável pelo processamento da linguagem natural.</p>

#### 2.4.6 NodeJS

![](../assets/imgs/architecture/diagramaFluxoNodejs.png)

Imagem 03 - Fluxo básico da tecnologia NodeJS

<p align="justify">&emsp;&emsp;Node.js é uma plataforma de aplicação para Javascript, que tem como principal objetivo facilitar a construção de softwares escaláveis. Ele geralmente é usado ao lado do servidor e é orientado para o estilo de programação voltada a evento. Isso faz com que ele seja leve, eficiente e uma boa alternativa para arquitetura de microsserviços.</p>

#### 2.4.7 MongoDB

<p align="justify">&emsp;&emsp;MongoDB é um framework de banco de dados noSQL. Ele é orientado a documento, livre de esquemas, não relacional, e open-source. MongoDB trabalha com arquivos JSON que contém toda a informação do banco de dados.</p>

## 3. Metas e Restrições de Arquitetura

### 3.1 Restrições Tecnológicas

<p align="justify">&emsp;&emsp;Para o desenvolvimenta da Gaia serão utilizados as seguintes tecnologias:</p>

- Rasa: Conjuntos de ferramentas de Machine Learning para a criação de chatbots.
- Python: Linguagem base utilizada no Rasa.
- Node.js: Plataforma de aplicação utilizada nos microsserviços.
- JavaScript: Linguagem base utilizada no Node.js.
- MongoDB: Software utilizado para o banco de dados,

### 3.2 Requisitos Não Funcionais

- O sistema deve ter integração com o Telegram;
- O sistema deve ter integração com o Facebook;
- O sistema deve conversar com o usuário em linguagem natural;
- O sistema deve respeitar a personalidade do bot;
- O sistema deve aprender novos comportamentos de acordo com a resposta do usuário;

## 4. Visão Lógica

### 4.1 Visão Geral

<p align=”justify”>&emsp;&emsp; A aplicação do ChatBot Gaia é construída com a tecnologia Rasa em linguagem Python no bot e sobre a plataforma Node.js em linguagem JavaScript nos microsserviços. O objetivo do RasaNLU é aplicar algoritmos de linguagem natural para extrair a intenção do usuário (intents) e a partir do Rasa Core é possível gerir o diálogo entre o usuário e o bot. A principal funcionalidade é o policy, que recebe a intent do usuário, atualiza o tracker() e prevê a melhor ação do bot (utter, action, listening). A plataforma Node.js é um ambiente de tempo de execução que executa o código em JavaScript para escrever ferramentas de linha de comando e para scripts do lado do servidor, capaz de executar uma entrada/saída assíncrona, que permite que outro processamento continue antes que a transmissão tenha encerrado.</p>

### 4.2 Pacotes de Design Significativos do Ponto de Vista da Arquitetura

#### 4.2.1 Diagrama de pacotes

![](../assets/imgs/architecture/diagramaRasa.png)

Imagem 04 - Diagrama de Pacotes da Gaia

![](../assets/imgs/architecture/diagramaPacotesGateway.png)

Imagem 05 - Diagrama de Pacotes do Gaia-Gateway

![](../assets/imgs/architecture/diagramaPacotesEsporte.png)

Imagem 06 - Diagrama de Pacotes do Gaia-Esporte

![](../assets/imgs/architecture/diagramaPacotesCiclone.png)

Imagem 07 - Diagrama de Pacotes do Gaia-Ciclone

#### 4.2.2 Diagrama de classe

##### 4.2.2.1 Diagrama de Classe do Gaia-Esporte

![](../assets/imgs/architecture/diagramaClasseEsporte.png)

Imagem 08 - Diagrama de Classe do Microsserviço Gaia-Esporte

##### 4.2.2.2 Diagrama de Classe do Gaia-Ciclone

![](../assets/imgs/architecture/diagramaClasseCiclone.png)

Imagem 09 - Diagrama de Classe do Microsserviço Gaia-Ciclone

