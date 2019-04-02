# Chatbot Wendy
### Visão
#### Versão 2.1

## Histórico de Revisão

| Data     | Versão |                         Descrição                                    |  Autor            |
|----------|--------|----------------------------------------------------------------------|--------------------|
|23/03/2019|  1.0   |Criação e formatação do documento.                                    |Samuel Pereira      |
|23/03/2019|   1.1  |Adição dos tópicos 1.1, 1.2 e 1.4                                     |Sofia Patrocínio    |
|23/03/2019|   1.2  |Adição do Tópico 2.                                                   |Samuel Pereira      |
|23/03/2019|   1.3  |Adição do Tópico 4.                                                   |Luis Henrique Taira |
|23/03/2019|   1.4  |Adição do Tópico 5 e 6.                                               |Micaella Gouveia    |
|24/03/2019|   1.5  |Adição do Tópico 7.                                                   |Luis Henrique Taira |
|24/03/2019|   1.6  |Adição do Tópico 3.                                                   |Eduardo Lima        |
|24/03/2019|   1.7  |Refeito o Tópico 4.1 com mais detalhes.                               |Luis Henrique Taira |
|24/03/2019|   1.8  |Revisão dos tópicos 3.1, 3.2, 3.3, 3.4.1 e 3.5. Adição do tópico 3.4.3|Eduardo Lima        |
|25/03/2019|   1.9  |Revisão do documento e adição dos tópicos 1.3 e 1.5.                  |Sofia Patrocínio    |
|25/03/2019|   2.0  |Revisão do documento, paginação e modificação do índice.              |Samuel Pereira      |
|25/03/2019|   2.1  |Revisão dos tópicos 1.2, 6.1 e 6.4.                                   |Eduardo Lima        |

## Sumário
 [1. Introdução](#intro) <br>
&emsp; [1.1 Objetivo](#objetivo) <br>
&emsp; [1.2 Escopo](#escopo) <br>
&emsp; [1.3 Definições, Acrônimos e Abreviações](#defs) <br>
&emsp; [1.4 Referências](#refs) <br>
&emsp; [1.5 Visão Geral](#visaogeral) <br>
[2. Planejamento](#planej) <br>
&emsp; [2.1. Oportunidade de Negócios](#oportu) <br>
&emsp; [2.2. Declaração do Problema](#declprob) <br>
&emsp; [2.3. Declaração da Posição do Produto](#declpos) <br>
[3. Descrições da Parte Interessada e do Usuário](#descparti) <br>
&emsp; [3.1 Resumo da parte interessada](#resparti) <br>
&emsp; [3.2 Resumo do usuário](#resuser) <br>
&emsp; [3.3 Ambiente do Usuário](#ambienteuser) <br>
&emsp; [3.4 Perfis das partes interessadas](#perfisparti) <br>
&emsp; &emsp; [3.4.1 Equipe de Desenvolvimento](#devteam) <br>
&emsp; &emsp; [3.4.2 Equipe de Engenharia de Produto](#prodteam) <br>
&emsp; &emsp; [3.4.3 Professoras](#prof) <br>
&emsp; [3.5 Perfis de Usuários](#perfisuser) <br>
&emsp; [3.6 Necessidades Principais do Investidor ou Usuário](#neces) <br>
[4. Visão geral do Produto](#visaogeralproduto) <br>
&emsp; [4.1. Perspectiva do Produto](#perspectprod) <br>
&emsp; [4.2. Resumo de Recursos](#resrecur) <br>
&emsp; [4.3. Licenciamento](#license) <br>
[5. Recursos do Produto](#recurprod) <br>
&emsp; [5.1. Plataforma de comunicação em linguagem natural.](#f1) <br>
&emsp; [5.2. Permitir o usuário escolher/cadastrar um local e data para obter informações sobre o tempo.](#f2) <br>
&emsp; [5.3. Enviar notificações com informações do tempo para o usuário nos dias cadastrados.](#f3) <br>
&emsp; [5.4. Fornecer informações sobre  o tempo e localização.](#f4) <br>
&emsp; [5.5. Sugerir ao usuário esportes viáveis para se praticar no local desejado levando em consideração sua situação climática.](#f5) <br>
[6. Restrições do Produto](#restricprod) <br>
&emsp; [6.1  Restrições de implementação](#restriimp) <br>
&emsp; [6.2  Restrições externas](#restriext) <br>
&emsp; [6.3 Restrições de Design](#restridesign) <br>
&emsp; [6.4  Restrições de Uso](#restriuso) <br>
&emsp; [6.5  Restrições de Confiabilidade](#restriconf) <br>
[7. Faixas de Qualidade](#qualidade) <br>


## 1. Introdução <a name="intro"></a>
### 1.1 Objetivo <a name="objetivo"></a>
Esse documento visa especificar de maneira geral as características do desenvolvimento do ChatBot Wendy, deixando claro seu objetivo, razão de sua necessidade, características, utilidade e requisitos do sistema.
### 1.2 Escopo <a name="escopo"></a>
O Chatbot possuirá duas funcionalidades principais. Essas funcionalidades juntas, formam o escopo do software, que será entregue completo ao final da segunda release. O bot terá como primeira responsabilidade enviar notificações sobre o clima da cidade que o usuário cadastrar. Assim, o usuário poderá definir uma cidade e os dias em que precisa ser notificado e o bot terá que, na quantidade de dias desejados, enviar notificações diariamente.

A segunda responsabilidade do bot será a identificação dos esportes que podem ser melhor praticados de acordo com o clima do dia. Ou seja, o usuário pedirá o clima específico de uma cidade e o bot responderá com um esporte ou uma lista de esportes que podem ser praticados nessas circunstâncias climáticas.
### 1.3 Definições, Acrônimos e Abreviações <a name="defs"></a>
| Abreviação | Definição |
|--|--|
| MIT | Licença de software livre criada pelo Massachusetts Institute of Technology |
| API | Interface de Programação de Aplicações |
### 1.4 Referências <a name="refs"></a>

 - IBM Knowledge Center - Documento de Visão: A estrutura de tópicos do documento de visão. Disponível em: [https://www.ibm.com/support/knowledgecenter/pt-br/SSWMEQ_4.0.6/com.ibm.rational.rrm.help.doc/topics/r_vision_doc.html](https://www.ibm.com/support/knowledgecenter/pt-br/SSWMEQ_4.0.6/com.ibm.rational.rrm.help.doc/topics/r_vision_doc.html). Acesso em: 23 mar. 2019;
 - RODRIGUES, Adrielly; BELEZA, Caio César; AGUIAR, Guilherme; ROSA, João Vitor; COELHO, Victor Hugo. Projeto Gerencia mais: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.1_Gerencia_mais/blob/master/docs/documentos/Mds/Documento_de_Visao.md#3.3.2](https://github.com/fga-eps-mds/2018.1_Gerencia_mais/blob/master/docs/documentos/Mds/Documento_de_Visao.md#3.3.2). Acesso em: 23 mar. 2019;
 - KAMAL, Byron; CERQUEIRA, Eduardo; ALVES, Gabriel; ARAGÃO, Igor; GUIMARÃES, Igor; JARDIM, João Pedro; DOS SANTOS, Marcelo; ASSUNÇÃO, Mateus; ALMEIDA, William. Projeto IncluCare: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.1-IncluCare_API/blob/master/docs/VISION_DOCUMENT.md](https://github.com/fga-eps-mds/2018.1-IncluCare_API/blob/master/docs/VISION_DOCUMENT.md). Acesso em: 23 mar. 2019;
 - FREITAS, Esio; DUTRA, Lucas; FÉO, Pedro; KADER, Saleh; FALANEH, Youssef. Projeto Kalkuli: Documento de Visão. Disponível em: [https://github.com/fga-eps-mds/2018.2-Kalkuli/blob/master/docs/DocumentoDeVisao.md](https://github.com/fga-eps-mds/2018.2-Kalkuli/blob/master/docs/DocumentoDeVisao.md). Acesso em: 23 mar. 2019;
 - Open Source Initiative: The MIT License. Disponivel em: [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT). Acesso em: 24 mar. 2019;
 - ADIDA, Ben. Understanding Open-Source Licensing. Disponível em: [https://openacs.org/about/licensing/open-source-licensing](https://openacs.org/about/licensing/open-source-licensing). Acesso em: 24 mar. 2019.
### 1.5 Visão Geral <a name="visaogeral"></a>
Este documento descreve de forma detalhada o embasamento, o planejamento e a construção do ChatBot Wendy. Para isso, serão apresentados tópicos referentes a declaração do problema que iremos solucionar, posicionamento do produto em relação ao mercado, as partes interessadas e usuários, perspectiva geral do produto: recursos e restrições, e requisitos para a aplicação do produto e documentação necessária para o bom andamento da aplicação.
## 2. Planejamento <a name="planej"></a>
### 2.1 Oportunidade de Negócios <a name="oportu"></a>
No contexto atual, a obtenção de informações acerca do clima são comumente feitas através de jornais ou páginas da web, sendo que a primeira opção não pode ser consultada a qualquer momento e não oferece uma informação em tempo real, mas sim uma previsão, enquanto a última opção, embora de melhor acesso, falte com a automatização do processo para tornar as consultas mais eficazes e bem planejadas.
Dessa forma, o Chatbot Wendy busca solucionar o problema de uma forma tecnológica e inteligente, disponibilizando aos usuários dados em tempo real a respeito do clima e recomendações de atividades esportivas referente aos dados recebidos, tal como a possibilidade de consultas automáticas agendadas pelo próprio usuário através de notificações.
### 2.2 Declaração do Problema <a name="declprob"></a>
<table>
	<tr>
		<td><b>O problema da</b></th>
		<td>Necessidade de ter informações sobre o clima de determinado local em tempo real</th>
	</tr>
	<tr>
		<td><b>O qual afeta</b></th>
		<td>Eventos e compromissos, e os indivíduos envolvidos em tais</th>
	</tr>
	<tr>
		<td><b>O impacto do problema é</b></th>
		<td>O mal planejamento em razão da falta de informação a respeito do clima</th>
	</tr>
	<tr>
		<td><b>Uma solução ideal seria</b></th>
		<td>Uma forma automatizada e inteligente de informatização a respeito do clima e eventos esportivos recomendados para o mesmo</th>
	</tr>
</table>

### 2.3 Declaração da Posição do Produto <a name="declpos"></a>
<table>
	<tr>
		<td><b>Para</b></td>
		<td>Praticantes de atividades ao ar livre</td>
	</tr>
	<tr>
		<td><b>Quem</b></td>
		<td>Desejam um melhor planejamento diário em relação ao clima</td>
	</tr>
	<tr>
		<td><b>O Wendy</b></td>
		<td>É um Chatbot</td>
	</tr>
	<tr>
		<td><b>Que</b></td>
		<td>Visa informatizar, de maneira inteligente e automatizada, a respeito do clima e eventos esportivos recomendados</td>
	</tr>
	<tr>
		<td><b>Diferente</b></td>
		<td>De consultas feitas através de jornais e websites, de forma manual</td>
	</tr>
	<tr>
		<td><b>Nosso produto</b></td>
		<td>Automatiza o processo de informatização tanto a respeito ao clima como às recomendações de eventos esportivos</td>
	</tr>
</table>

## 3. Descrições da Parte Interessada e do Usuário <a name="descparti"></a>
### 3.1 Resumo da parte interessada <a name="resparti"></a>
| Nome | Descrição | Responsabilidade |
|--|--|--|
| Equipe de desenvolvimento | Graduandos em Engenharia de Software, cursando a disciplina Métodos de desenvolvimento de Software, pela Universidade de Brasília. | Desenvolver o software no período estipulado, bem como testá-lo e implementá-lo. |
| Equipe de engenharia de produto | Graduandos em Engenharia de Software, cursando a disciplina Engenharia de Produto de Software, pela Universidade de Brasília. | Gestão da equipe de desenvolvimento. Garantir a aplicação do ágil e viabilidade do projeto. |
| Cliente | Requisitor do projeto. | Informar suas preferências e exigências acerca do projeto. |
| Professora | Professoras da Universidade de Brasília, do curso de Engenharia de Software. | Orientar, acompanhar e avaliar o projeto. |

### 3.2 Resumo do Usuário <a name="resuser"></a>
| Nome | Descrição | Responsabilidades |
|--|--|--|
| Praticantes de modalidades ao ar livre | Pessoas interessadas em receber informações sobre o clima. | Utilizar o ChatBot nas plataformas disponíveis. |
| Atleta | Pessoas interessadas em receber informações sobre atividades físicas de acordo com o clima atual. | Utilizar o ChatBot nas plataformas disponíveis. |

### 3.3 Ambiente do Usuário <a name="ambienteuser"></a>
O Chatbot Wendy poderá ser acessado através do Facebook e Telegram. Sendo necessário um browser ou aplicativo do Facebook ou aplicativo do Telegram, conexão com a internet e uma conta na plataforma Facebook ou Telegram.
### 3.4 Perfis das partes interessadas <a name="perfisparti"></a>
#### 3.4.1 Equipe de Desenvolvimento <a name="devteam"></a>
<table>
	<tr>
		<td>Representantes</td>
		<td>Eduardo Vieira Lima, Luís Henrique Pereira Taira, Sofia Costa Patrocínio, Samuel de Souza Buters Pereira e Micaella Lorraine Gouveia de Lima.</td>
	</tr>
	<tr>
		<td>Descrição</td>
		<td>Desenvolvedores.</td>
	</tr>
	<tr>
		<td>Tipo</td>
		<td>Alunos da Universidade de Brasília, cursando Métodos de Desenvolvimento de Software.</td>
	</tr>
	<tr>
		<td>Responsabilidade</td>
		<td>Desenvolver e testar o Software, assim como elaborar seus documentos.</td>
	</tr>
	<tr>
		<td>Critério de sucesso</td>
		<td>Desenvolver o software no período estipulado, como todos seus requisitos.</td>
	</tr>
	<tr>
		<td>Envolvimento</td>
		<td>Alto.</td>
	</tr>
</table>

#### 3.4.2 Equipe de Engenharia de Produto <a name="prodteam"></a>
<table>
	<tr>
		<td>Representantes</td>
		<td>Calebe Rios, Amanda Muniz, Indiara Duarte e Luciana Ribeiro.</td>
	</tr>
	<tr>
		<td>Descrição</td>
		<td>Gestores do projeto.</td>
	</tr>
	<tr>
		<td>Tipo</td>
		<td>Alunos da Universidade de Brasília, cursando Engenharia de Produto de Software.</td>
	</tr>
	<tr>
		<td>Responsabilidade</td>
		<td>Gerir e dar suporte à equipe de desenvolvimento, garantindo o melhor processo para o desenvolvimento do produto.</td>
	</tr>
	<tr>
		<td>Critério de sucesso</td>
		<td>Garantir os prazos estipulados do projeto, aplicando o melhor processo para tal.</td>
	</tr>
	<tr>
		<td>Envolvimento</td>
		<td>Alto.</td>
	</tr>
</table>

#### 3.4.3 Professoras <a name="prof"></a>
<table>
	<tr>
		<td>Representantes</td>
		<td>Professoras Bruna Moreira e Carla Rocha.</td>
	</tr>
	<tr>
		<td>Descrição</td>
		<td>Professoras.</td>
	</tr>
	<tr>
		<td>Tipo</td>
		<td>Professoras das disciplinas Métodos de Desenvolvimento de Software e Engenharia de Produto de Software respectivamente, pela Universidade de Brasília.</td>
	</tr>
	<tr>
		<td>Responsabilidade</td>
		<td>Orientar, acompanhar e avaliar o processo de desenvolvimento, bem como as equipes de Desenvolvimento e Engenharia de produto. Avaliar o produto em sua completude.</td>
	</tr>
	<tr>
		<td>Critério de sucesso</td>
		<td>-</td>
	</tr>
	<tr>
		<td>Envolvimento</td>
		<td>Médio.</td>
	</tr>
</table>

### 3.5 Perfis de Usuário <a name="perfisuser"></a>
<table>
	<tr>
		<td>Representantes</td>
		<td>Praticante de modalidades ao ar livre.</td>
	</tr>
	<tr>
		<td>Descrição</td>
		<td>Qualquer pessoa interessada em se organizar com o auxílio de informações sobre o clima ou praticar esportes.</td>
	</tr>
	<tr>
		<td>Tipo</td>
		<td>Usuário.</td>
	</tr>
	<tr>
		<td>Responsabilidade</td>
		<td>Utilizar o serviço da forma que preferir.</td>
	</tr>
	<tr>
		<td>Critério de sucesso</td>
		<td>Receber as informações desejadas.</td>
	</tr>
	<tr>
		<td>Envolvimento</td>
		<td>Baixo.</td>
	</tr>
</table>
<br>
<table>
	<tr>
		<td>Representantes</td>
		<td>Atleta.</td>
	</tr>
	<tr>
		<td>Descrição</td>
		<td>Atleta interessado em escolher sua atividade física de acordo com o clima.</td>
	</tr>
	<tr>
		<td>Tipo</td>
		<td>Usuário.</td>
	</tr>
	<tr>
		<td>Responsabilidade</td>
		<td>Utilizar o serviço da forma que preferir.</td>
	</tr>
	<tr>
		<td>Critério de sucesso</td>
		<td>Receber as informações desejadas.</td>
	</tr>
	<tr>
		<td>Envolvimento</td>
		<td>Baixo.</td>
	</tr>
</table>

### 3.6 Necessidades Principais do Investidor ou Usuário <a name="neces"></a>
| Necessidade | Prioridade | Interesse | Solução Atual | Solução Proposta |
|--|--|--|--|--|
| Receber informações sobre o clima e vento. | Alta. | Facilitar o acesso à informação de forma natural e conveniente. | Procurar em jornais físicos e virtuais. | Receber a informação desejada por meio de um ChatBot no Facebook. |
| Receber sugestões de atividades físicas para o clima atual. | Alta. | Facilitar o acesso à informação de forma natural e conveniente. | Pesquisar manualmente sobre a atividade física desejada em várias fontes. | Receber a informação desejada em um único lugar. |

## 4. Visão Geral do Produto <a name="visaogeralproduto"></a>
### 4.1 Perspectiva do Produto <a name="perspectprod"></a>
O software será um chatbot com o qual o usuário pode conversar em linguagem natural, podendo pedir informações sobre o tempo em tempo real.
O chatbot será capaz de fornecer informações nos dias desejados pelo usuário assim como sugerir os melhores esportes para se praticar com base no tempo.
### 4.2. Resumo de Recursos <a name="resrecur"></a>
| Benefício para o cliente | Recursos de suporte |
|--|--|
| Comunicar-se com o ChatBot em linguagem natural | A troca de informações entre o usuário e o ChatBot ocorre no formato de uma conversa natural |
| Possui fácil acesso a informações do tempo | O ChatBot manda mensagens para o usuário informando-o das condições do tempo |
| Pode escolher o local do qual quer receber informações | São mandadas informações do tempo de um lugar previamente especificado |
| Pode escolher a frequência de notificações sobre o tempo desejada. | O ChatBot pode mandar mensagens para o usuário em dias especificados. |
| Receber uma lista de esportes com base no tempo | Montar uma lista de esportes que podem ser melhor praticados nas condições do tempo de cada dia |
### 4.3 Licenciamento <a name="license"></a>
O ChatBot será distribuído sob a licença MIT para softwares livres, que dá liberdade para todos que o adquirirem de modificar, distribuir, sublicenciar, vender e contribuir para o software.

## 5. Recursos do Produto <a name="recurprod"></a>
### 5.1 Plataforma de comunicação em linguagem natural. <a name="f1"></a>
### 5.2 Permitir o usuário escolher/cadastrar um local e data para obter informações sobre o tempo. <a name="f2"></a>
### 5.3 Enviar notificações com informações do tempo para o usuário nos dias cadastrados. <a name="f3"></a>
### 5.4 Fornecer informações sobre o tempo e localização, tais como: <a name="f4"></a>
-   Velocidade e direção dos ventos;
-   Temperatura;
-   Nebulosidade;
-   Pressão;
-   Umidade;
-   Nascer e pôr do sol;
-   Coordenadas geográficas.
### 5.5 Sugerir ao usuário esportes viáveis para se praticar no local desejado levando em consideração sua situação climática. <a name="f5"></a>

## 6. Restrições do Produto<a name="restricprod"></a>
### 6.1 Restrições de implementação<a name="restriimp"></a>
O sistema será implementado utilizando as tecnologias NodeJs(Javascript) e MongoDB para o banco de dados , o chatbot será construído com o uso do framework Rasa, que utiliza a linguagem Python.
### 6.2 Restrições externas <a name="restriext"></a>
A inexperiência e o período de tempo curto podem se tornar empecilhos para a produção do projeto.
### 6.3 Restrições de Design <a name="restridesign"></a>
O sistema deve ser feito em uma interface de fácil usabilidade, tornando-o intuitivo para o usuário.
### 6.4  Restrições de Uso <a name="restriuso"></a>
Para  utilizar o ChatBot Wendy, o usuário deve ter uma conexão com a internet, possuir uma conta no Facebook com acesso ao Messenger ou conta no Telegram.
### 6.5  Restrições de Confiabilidade <a name="restriconf"></a>
O sistema terá uma cobertura de testes, de no mínimo 90% do sistema.

## 7. Faixas de Qualidade <a name="qualidade"></a>
Toda da interação com o software deve ocorrer na forma de uma conversa natural. Deve ser fácil entender como se usar todos os recursos do ChatBot apenas conversando com ele.
O software buscará oferecer um serviço consistente e confiável, considerando que problemas na API OpenWeather ou na rede social escolhida (Facebook messenger) podem afetar o funcionamento desse serviço.
