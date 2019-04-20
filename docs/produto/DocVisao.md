# Chatbot Gaia
### Visão
#### Versão 2.1

## Histórico de Revisão

| Data | Versão | Descrição | Autor |
| ---- | ------ | --------- | ----- |
|23/03/2019| 1.0 | Criação e formatação do documento. | Samuel Pereira | 
23/03/2019 | 1.1 | Adição dos tópicos 1.1, 1.2 e 1.4  | Sofia Patrocínio |
|23/03/2019| 1.2 | Adição do Tópico 2. |Samuel Pereira |
|23/03/2019| 1.3 | Adição do Tópico 4. | Luis Henrique Taira |
|23/03/2019| 1.4 | Adição do Tópico 5 e 6. |Micaella Gouveia |
|24/03/2019| 1.5 | Adição do Tópico 7. | Luis Henrique Taira |
|24/03/2019| 1.6 | Adição do Tópico 3. | Eduardo Lima |
|24/03/2019| 1.7 | Refeito o Tópico 4.1 com mais detalhes. |Luis Henrique Taira |
|24/03/2019| 1.8 | Revisão dos tópicos 3.1, 3.2, 3.3, 3.4.1 e 3.5. Adição do tópico 3.4.3| Eduardo Lima |
|25/03/2019| 1.9 | Revisão do documento e adição dos tópicos 1.3 e 1.5. |Sofia Patrocínio |
|25/03/2019| 2.0 | Revisão do documento, paginação e modificação do índice. |Samuel Pereira |
|25/03/2019| 2.1 | Revisão dos tópicos 1.2, 6.1 e 6.4. | Eduardo Lima |
| 18/04/2019 | 2.2 | Revisão do documento | Indiara Duarte | 

## Sumário
 [1. Introdução](#_1-introdução) <br>
&emsp; [1.1 Objetivo](#_11-objetivo) <br>
&emsp; [1.2 Escopo](#_12-escopo) <br>
&emsp; [1.3 Definições, Acrônimos e Abreviações](#_13-definições-acrônimos-e-abreviações) <br>
&emsp; [1.4 Referências](#_14-referências) <br>
&emsp; [1.5 Visão Geral](#_15-visão-geral) <br>
[2. Planejamento](#_2-planejamento) <br>
&emsp; [2.1. Oportunidade de Negócios](#_21-oportunidade-de-negócios) <br>
&emsp; [2.2. Declaração do Problema](#_22-declaração-do-problema) <br>
&emsp; [2.3. Declaração da Posição do Produto](#_23-declaração-da-posição-do-produto) <br>
[3. Descrições da Parte Interessada e do Usuário](#_3-descrições-da-parte-interessada-e-do-usuário) <br>
&emsp; [3.1 Resumo da parte interessada](#_31-resumo-da-parte-interessada) <br>
&emsp; [3.2 Resumo do usuário](#_32-resumo-do-usuário) <br>
&emsp; [3.3 Ambiente do Usuário](#_33-ambiente-do-usuário) <br>
&emsp; [3.4 Perfis das partes interessadas](#_34-perfis-das-partes-interessadas) <br>
&emsp; &emsp; [3.4.1 Equipe de Desenvolvimento](#_341-equipe-de-desenvolvimento) <br>
&emsp; &emsp; [3.4.2 Equipe de Engenharia de Produto](#_342-equipe-de-engenharia-de-produto) <br>
&emsp; &emsp; [3.4.3 Professoras](#_343-professoras) <br>
&emsp; [3.5 Perfis de Usuários](#_35-perfis-de-usuário) <br>
&emsp; [3.6 Necessidades Principais do Investidor ou Usuário](#_36-necessidades-principais-do-investidor-ou-usuário) <br>
[4. Visão geral do Produto](#_4-visão-geral-do-produto) <br>
&emsp; [4.1. Perspectiva do Produto](#_41-perspectiva-do-produto) <br>
&emsp; [4.2. Resumo de Recursos](#_42-resumo-de-recursos) <br>
&emsp; [4.3. Licenciamento](#_43-licenciamento) <br>
[5. Recursos do Produto](#_5-recursos-do-produto) <br>
&emsp; [5.1. Plataforma de comunicação em linguagem natural.](#_51-plataforma-de-comunicação-em-linguagem-natural) <br>
&emsp; [5.2. Permitir o usuário escolher/cadastrar um local e data para obter informações sobre o tempo.](#_52-permitir-o-usuário-escolhercadastrar-um-local-e-data-para-obter-informações-sobre-o-tempo) <br>
&emsp; [5.3. Enviar notificações com informações do tempo para o usuário nos dias cadastrados.](#_53-enviar-notificações-com-informações-do-tempo-para-o-usuário-nos-dias-cadastrados) <br>
&emsp; [5.4. Fornecer informações sobre  o tempo e localização.](#_54-fornecer-informações-sobre-o-tempo-e-localização-tais-como) <br>
&emsp; [5.5. Sugerir ao usuário esportes viáveis para se praticar no local desejado levando em consideração sua situação climática.](#_55-sugerir-ao-usuário-esportes-viáveis-para-se-praticar-no-local-desejado-levando-em-consideração-sua-situação-climática) <br>
[6. Restrições do Produto](#_6-restrições-do-produto) <br>
&emsp; [6.1  Restrições de implementação](#_61-restrições-de-implementação) <br>
&emsp; [6.2  Restrições externas](#_62-restrições-externas) <br>
&emsp; [6.3 Restrições de Design](#_63-restrições-de-design) <br>
&emsp; [6.4  Restrições de Uso](#_64-restrições-de-uso) <br>
&emsp; [6.5  Restrições de Confiabilidade](#_65-restrições-de-confiabilidade) <br>
[7. Faixas de Qualidade](#_7-faixas-de-qualidade) <br>


## 1. Introdução
### 1.1 Objetivo
Esse documento visa especificar de maneira geral as características do desenvolvimento do ChatBot Gaia, deixando claro seu objetivo, razão de sua necessidade, características, utilidade e requisitos do sistema.

### 1.2 Escopo
O Chatbot Gaia possuirá três funcionalidades principais. Essas funcionalidades juntas, formam o escopo do software, que será entregue completo ao final da segunda release.

O bot terá como primeira funcionalidade consultar meteorologia, onde o usuário poderá informar qualquer localidade do mundo e assim obter informações à respeito das condições meteorológicas deste. Entende-se como condições meteorológicas dados sobre pressão atmosférica, umidade, rajadas de vento, temperatura, nebulosidade, dentre outras.

A segunda funcionalidade do Chatbot será a sugestão de modalidades ao ar livre de acordo com a meteorologia do dia. Portanto, com base na previsão do tempo de uma localidade específica, o Chatbot responderá com uma ou várias modalidades que forem mais favoráveis a serem praticas naquele período e clima.

A terceira funcionalidade contempla o gerenciamento de notificações do Chatbot. Deste modo, o usuário poderá cadastrar localidades e os dias que deseja ser notificado. Por exemplo, ele pode receber notificações diárias sobre a previsão do tempo na cidade de Brasília/DF. 

Por fim, tem-se o acompanhamento de furacão. Essa funcionalidade foi inserida no planejamento de produto, mas não de projeto. O intuito é que o usuário seja alertado quando houver ocorrência de furacões em quaisquer localidades do mundo.

### 1.3 Definições, Acrônimos e Abreviações
| Abreviação | Definição |
|--|--|
| MIT | Licença de software livre criada pelo Massachusetts Institute of Technology |
| API | Interface de Programação de Aplicações |

### 1.4 Referências

 - IBM Knowledge Center - Documento de Visão: A estrutura de tópicos do documento de visão. Disponível em: [https://www.ibm.com/support/knowledgecenter/pt-br/SSWMEQ_4.0.6/com.ibm.rational.rrm.help.doc/topics/r_vision_doc.html](https://www.ibm.com/support/knowledgecenter/pt-br/SSWMEQ_4.0.6/com.ibm.rational.rrm.help.doc/topics/r_vision_doc.html). Acesso em: 23 mar. 2019;
 - RODRIGUES, Adrielly; BELEZA, Caio César; AGUIAR, Guilherme; ROSA, João Vitor; COELHO, Victor Hugo. Projeto Gerencia mais: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.1_Gerencia_mais/blob/master/docs/documentos/Mds/Documento_de_Visao.md#3.3.2](https://github.com/fga-eps-mds/2018.1_Gerencia_mais/blob/master/docs/documentos/Mds/Documento_de_Visao.md#3.3.2). Acesso em: 23 mar. 2019;
 - KAMAL, Byron; CERQUEIRA, Eduardo; ALVES, Gabriel; ARAGÃO, Igor; GUIMARÃES, Igor; JARDIM, João Pedro; DOS SANTOS, Marcelo; ASSUNÇÃO, Mateus; ALMEIDA, William. Projeto IncluCare: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.1-IncluCare_API/blob/master/docs/VISION_DOCUMENT.md](https://github.com/fga-eps-mds/2018.1-IncluCare_API/blob/master/docs/VISION_DOCUMENT.md). Acesso em: 23 mar. 2019;
 - FREITAS, Esio; DUTRA, Lucas; FÉO, Pedro; KADER, Saleh; FALANEH, Youssef. Projeto Kalkuli: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.2-Kalkuli/blob/master/docs/DocumentoDeVisao.md](https://github.com/fga-eps-mds/2018.2-Kalkuli/blob/master/docs/DocumentoDeVisao.md). Acesso em: 23 mar. 2019;
 - Open Source Initiative: The MIT License. Disponivel em: [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT). Acesso em: 24 mar. 2019;
 - ADIDA, Ben. Understanding Open-Source Licensing. Disponível em: [https://openacs.org/about/licensing/open-source-licensing](https://openacs.org/about/licensing/open-source-licensing). Acesso em: 24 mar. 2019.
 
### 1.5 Visão Geral
Este documento descreve de forma detalhada o embasamento, o planejamento e a construção do ChatBot Gaia. Para isso, serão apresentados tópicos referentes a descrição do problema a ser solucionado, posicionamento do produto em relação ao mercado, as partes interessadas e usuários, perspectiva geral do produto: recursos e restrições, e requisitos para a aplicação do produto.

## 2. Planejamento
### 2.1 Oportunidade de Negócios
No contexto atual, a obtenção de informações acerca do clima são comumente feitas através de jornais ou páginas da web, sendo que a primeira opção não pode ser consultada a qualquer momento e não oferece uma informação em tempo real, mas sim uma previsão, enquanto a última opção, embora de melhor acesso, falte com a automatização do processo para tornar as consultas mais eficazes e bem planejadas.
Dessa forma, o Chatbot Gaia busca solucionar o problema de uma forma tecnológica e inteligente, disponibilizando aos usuários dados em tempo real a respeito do clima e recomendações de atividades esportivas referente aos dados recebidos, tal como a possibilidade de consultas automáticas agendadas pelo próprio usuário através de notificações.

### 2.2 Declaração do Problema
| O problema da | afeta | cujo impacto é | uma boa solução seria | 
| ------------- | ----- | -------------- | --------------------- | 
| Dificuldade em encontrar condições meteorológicas correlacionadas com modalidades ao ar livre | praticantes de exercicíos físicos | pouca praticidade para encontrar esta informação | automatizar o acesso às informações meteorológicas e disponibilizar modalidades mais farováveis |


### 2.3 Declaração da Posição do Produto
| Para | Que | A Gaia | Que | Diferente de | Nosso produto | 
| ---- | --- | ------ | --- | ------------ | ------------- |
| Praticantes de modalidades ao ar livre | Desejam saber qual(is) são os melhores dias e modalidades para praticar | É um Chabot | Informa previsão do tempo e modalidades propícias | Apps que exibem apenas previsão do tempo | Disponibiliza informações meteorológicas e as correlaciona com modalidades ao ar livre mais propícia em determinado local | 


## 3. Descrições da Parte Interessada e do Usuário
### 3.1 Resumo da parte interessada
| Nome | Descrição | Responsabilidade |
| ---- | --------- | ---------------- |
| Equipe de desenvolvimento | Graduandos em Engenharia de Software, cursando a disciplina Métodos de desenvolvimento de Software, pela Universidade de Brasília. | Desenvolver o software no período estipulado, bem como testá-lo e implementá-lo |
| Equipe de engenharia de produto | Graduandos em Engenharia de Software, cursando a disciplina Engenharia de Produto de Software, pela Universidade de Brasília. | Gestão da equipe de desenvolvimento. Garantir a aplicação do ágil e viabilidade do projeto |
| Carla Rocha e Bruna Moreira | Professoras da Universidade de Brasília, do curso de Engenharia de Software. | Orientar, acompanhar e avaliar o projeto |

### 3.2 Resumo do Usuário
| Nome | Descrição | Responsabilidades |
|----- | --------- | ----------------- |
| Praticantes de modalidades ao ar livre | Pessoas interessadas em receber informações sobre meteorologia  e atividades esportivas ao ar livre | Utilizar o ChatBot nas plataformas disponíveis. |


### 3.3 Ambiente do Usuário
O Chatbot Gaia poderá ser acessado através do Facebook e Telegram, sendo necessário um browser ou aplicativo do Facebook ou aplicativo do Telegram, conexão com a internet e uma conta na plataforma Facebook ou Telegram.

### 3.4 Perfis das partes interessadas
#### 3.4.1 Equipe de Desenvolvimento
| Representantes | Descrição | Tipo | Responsabilidade | Critério de sucesso | Envolvimento |
| -------------- | --------- | ---- | ---------------- | ------------------- | ------------ |
| Eduardo Vieira Lima, Luís Henrique Pereira Taira, Sofia Costa Patrocínio, Samuel de Souza Buters Pereira e Micaella Lorraine Gouveia de Lima | Desenvolvedores | Alunos da Universidade de Brasília, cursando Métodos de Desenvolvimento de Software | Desenvolver e testar o software, assim como elaborar documentação | Desenvolver o produto no período estipulado, como todos seus requisitos atendidos | Alto |


#### 3.4.2 Equipe de Engenharia de Produto
| Representantes | Descrição | Tipo | Responsabilidade | Critério de sucesso | Envolvimento |
| -------------- | --------- | ---- | ---------------- | ------------------- | ------------ |
| Calebe Rios, Amanda Muniz, Indiara Duarte e Luciana Ribeiro | Gerentes de Projeto | Alunos da Universidade de Brasília, cursando Engenharia de Produto de Software | Gerir e dar suporte à equipe de desenvolvimento, garantindo o melhor processo para o desenvolvimento do produto | Garantir qualidade de entrega, baseado em custo, tempo e escopo | Alto |


#### 3.4.3 Professoras
| Representantes | Descrição | Tipo | Responsabilidade | Critério de sucesso | Envolvimento |
| -------------- | --------- | ---- | ---------------- | ------------------- | ------------ |
| Bruna Moreira e Carla Rocha | Professoras das disciplinas Métodos de Desenvolvimento de Software e Engenharia de Produto de Software respectivamente, pela Universidade de Brasília | Professor | Orientar, acompanhar e avaliar o processo de desenvolvimento, bem como as equipes de Desenvolvimento e Engenharia de produto | Avaliar o produto em sua completude | Médio |


### 3.5 Perfis de Usuário
| Representantes | Descrição | Tipo | Responsabilidade | Critério de sucesso | Envolvimento |
| -------------- | --------- | ---- | ---------------- | ------------------- | ------------ |
| Praticantes de modalidades ao ar livre | Pessoa interessada em se organizar com o auxílio de informações sobre condições meteorológicas ou praticar atividades ao ar livre | Usuário |  Utilizar o Chatbot nas plataformas disponíveis | Obtenção das informações desejadas através do Chabot | Alto |


### 3.6 Necessidades Principais do Investidor ou Usuário
| Necessidade | Prioridade | Interesse | Solução Atual | Solução Proposta |
| ----------- | ---------- | --------- | ------------- | ---------------- |
| Receber informações sobre condições meteorológicas de qualquer localidade | Alta | Facilitar o acesso à informação com maior praticidade | Buscar em noticiários e/ou aplicações  | Obter a informação desejada através de um ChatBot no Facebook e Telegram |
| Receber sugestões de atividades físicas conforme as condições meteorológicas | Alta | Facilitar o acesso à informação com maior praticidade | Pesquisar manualmente sobre a atividade física desejada em várias fontes | Obter a informação desejada através de um ChatBot no Facebook e Telegram |

## 4. Visão Geral do Produto
### 4.1 Perspectiva do Produto
O software será um chatbot com o qual o usuário pode conversar em linguagem natural, podendo pedir informações sobre o tempo em tempo real.
O chatbot será capaz de fornecer informações nos dias desejados pelo usuário assim como sugerir os melhores esportes para se praticar com base no tempo.

### 4.2. Resumo de Recursos
| Benefício para o cliente | Recursos de suporte |
|------------------------- | ------------------- |
| Comunicar-se com o ChatBot em linguagem natural | A troca de informações entre o usuário e o ChatBot ocorre no formato de uma conversa natural |
| Fácil acesso a previsão do tempo | O ChatBot manda mensagens para o usuário informando-o das condições do tempo |
| Escolher o local que deseja-se receber informações | São enviadas informações meteorológicas sobre um lugar previamente especificado |
| Personalizar a periodicidade de recebimento de notificações | O ChatBot pode mandar notificações para o usuário em dias escolhidos por ele |
| Visualizar modalidades ao ar livre mais propícias de acordo com a previsão do tempo | Enviar modalidades favoráveis à meteorologia de um determinado local e data |

### 4.3 Licenciamento
O ChatBot será distribuído sob a licença MIT para softwares livres, que dá liberdade para todos que o adquirirem de modificar, distribuir, sublicenciar, vender e contribuir para o software.

## 5. Recursos do Produto
### 5.1 Plataforma de comunicação em linguagem natural.
### 5.2 Permitir o usuário escolher/cadastrar um local e data para obter informações sobre o tempo.
### 5.3 Enviar notificações com informações do tempo para o usuário nos dias cadastrados.
### 5.4 Fornecer informações sobre o tempo e localização, tais como:
-   Velocidade e direção dos ventos;
-   Temperatura;
-   Nebulosidade;
-   Pressão;
-   Umidade;
-   Nascer e pôr do sol;
-   Coordenadas geográficas.

### 5.5 Sugerir ao usuário esportes viáveis para se praticar no local desejado levando em consideração sua situação climática.

## 6. Restrições do Produto
### 6.1 Restrições de implementação
O sistema será implementado utilizando as tecnologias NodeJs(Javascript) e MongoDB para o banco de dados e framework Rasa, que utiliza a linguagem Python.

### 6.2 Restrições externas
A inexperiência e o período de tempo curto podem se tornar grandes riscos para o desenvolvimento do produto.

### 6.3 Restrições de Design
O sistema deve ser feito em uma interface de fácil usabilidade, tornando-o intuitivo para o usuário.

### 6.4  Restrições de Uso
Para  utilizar o ChatBot Gaia, o usuário deve ter uma conexão com a internet, possuir uma conta no Facebook com acesso ao Messenger ou conta no Telegram.

### 6.5  Restrições de Confiabilidade
O sistema terá uma cobertura de testes, de no mínimo 90% do sistema.

## 7. Faixas de Qualidade
Toda da interação com o software deve ocorrer na forma de uma conversa natural. Deve ser fácil entender como se usar todos os recursos do ChatBot apenas interagindo com ele.
O software oferecerá consistentência e confiabilidade, considerando que problemas na API OpenWeather e API OpenCageData ou na plataforma de uso escolhida (Facebook Messenger e Telegram) podem afetar o funcionamento desse serviço.
