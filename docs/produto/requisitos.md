# Técnicas de Elicitação Utilizadas

## 1. Brainstorming

<p align="justify">&emsp;&emsp;O Brainstorming é uma técnica de reunião bem difundida na Engenharia de Requisitos. Ela consiste em um grupo de pessoas de diferentes áreas levantando opiniões e trocando ideias sobre determinado assunto. O Brainstorming foi utilizado pela equipe de EPS para pensar em quais seriam as principais funcionalidades de cada microsserviço. Assim, os cinco microsserviços que existem na arquitetura do bot e o chat possuem um objetivo geral. A partir desse funcionalidade principal foram elicitados outros requisitos.</p>

## 2. Introspecção

<p align="justify">&emsp;&emsp;A introspecção é uma técnica muito utilizada na etapa de elicitação. Ela consiste em entender as funcionalidades importantes de um sistema. Apesar de muito usada nem sempre a introspecção traz uma visão próxima da realidade, para evitar isso a Product Owner esteve presente na elicitação levando em conta a sua visão do produto.</p>

# Resultados

## 1. Clima

- O sistema deve ser capaz de fazer requisições para a api do OpenWeatherMaps;
- O sistema deve ser capaz de indicar o clima atual de um local;
- O sistema deve ser capaz de indicar o clima dos próximos cinco dias de um local;
- O sistema deve ser capaz de receber requisições do Gateway;

## 2. Local

- O sistema deve ser capaz de fazer requisições para a api OpenCage Geocoder;
- O sistema deve ser capaz de indicar a latitude e longitude de uma cidade a partir do seu nome;
- O sistema deve ser capaz de filtrar o resultado da requisição da API externa, para obter a localização correta;
- O sistema deve ser capaz de guardar a latitude e longitude de uma cidade;
- O sistema deve ser capaz de localizar no banco de dados a localização de uma cidade;

## 3. Notificação

- O sistema deve ser capaz de criar novo usuário;
- O sistema deve ser capaz de guardar as preferências de notificação do usuário;
- O sistema deve ser capaz de receber uma lista de cidades associada a um usuário;
- O sistema deve ser capaz de notificar o usuário de acordo com a preferência dele;
- O sistema deve ser capaz de cancelar notificações;
- O sistema deve ser capaz de excluir uma cidade;
- O sistema deve ser capaz de excluir um usuário;
- O sistema deve ser capaz de excluir a lista de cidade de um usuário;

## 4. Esporte

- O sistema deve ser capaz de guardar as condições climáticas ideais para cada esporte;
- O sistema deve ser capaz de comparar o clima atual com as condições climáticas ideais do esporte;
- O sistema deve ser capaz de exibir uma lista com os esportes ideias para o clima.

## 5. API GATEWAY

- O sistema deve ser capaz de fazer a integração entre os microsserviços;
- O sistema deve ser capaz de integrar o chatbot com os microsserviços;
- O sistema deve ser capaz de priorizar requisições;

## 6. Requisitos não funcionais

- O sistema deve ter integração com o Telegram;
- O sistema deve ter integração com o Facebook;
- O sistema deve conversar com o usuário em linguagem natural;
- O sistema deve respeitar a personalidade do bot;
- O sistema deve aprender novos comportamentos de acordo com a resposta do usuário;
