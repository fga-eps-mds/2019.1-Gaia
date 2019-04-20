# Plano de Gerenciamento de Riscos do Projeto

## Escopo

O plano de risco tem como objetivo descrever quais são os riscos do projeto, como eles serão monitorados e controlados ao longo das sprints, visando entender seus impactos, procurando formas de mitigar esses possíveis riscos. 

<br />
<br />

# Riscos e suas consequências

### Riscos de Projeto

|ID | Risco | Consequência |
| - | - | - |
| 1 | Mudança Arquitetural | Gera retrabalho, como alteração nas histórias planjetadas, mudanças de infra e mudanças a nível de código | 
| 2 | Mudança de Escopo | Alteração no cronograma e redefinição de requisitos |
| 3 | Falha na Comunicação | Erros e até perdas de informação |
| 4 | Imaturidade na gerência | Diminui qualidade das entregas, aumenta o custo do projeto, afeta o planejamento e entre outros |
| 5 | Desistencia de membros | Sobrecarga dos membros remanescentes, distribuição de tarefas | 
| 6 | Descomprometimento da Equipe | Falhas na entrega, desgaste nos membros comprometidos |
| 7 | Erro de Priorização | Estimativa de produtividade e refatorações |   


### Risco Técnico

| ID | Risco | Consequência |
| - | - | - |
| 8 | Dificuldade com as Tecnologias Adotadas | Prazo e qualidade de entrega, priorização de requisitos, planejamento, entre outros | 
| 9 | Atraso nas Entregas | Planejamento e prazo |


### Risco Externo

| ID | Risco | Consequência |
| - | - | - |
| 10 | Greve na UnB | Viabilidade do projeto |


### Risco de Produto

| Risco | Consequência |
| - | - |
| 11 | A Solução não atender as expectativas do usuário final | Valor do projeto e desgaste da equipe |

<br />
<br />

# Análise Qualitativa e Quantitativa dos Dados

<p>A análise qualitativa e quantitativa dos riscos do projeto é feita a partir da probabilidade de ocorrência, do impacto gerado e a partir desses dois valores a análise do grau de risco. As tabelas a seguir mostram como esses valores são definidos.</p>

## Probabilidade 



| Probabilidade | % de certeza | Peso |
| - | - | - |
| Nula | 0% | 0 |
| Muito baixa | 0 a 20%| 1 |
| Baixa | 20 a 40% | 2 |
| Média | 40 a 60% | 3 |
| Alta | 60 a 80% | 4 |
| Muito alta | 80 a 100% | 5 |   


   
## Impacto

| Impacto | Impacto sobre o Custo Original (%) | Peso |
| - | - | - |
| Nulo | 0% | 0 |
| Muito baixo | 1 a 5%| 1 |
| Baixo | 5 a 10% | 2 |
| Médio | 10 a 15% | 3 |
| Alto | 15 a 20% | 4 |
| Muito alto | Acima de 20% | 5 | 

<br />

### O grau de risco é definido pela multiplicação da probabilidade pelo impacto. Conforme tabela abaixo:

![ear](https://i.imgur.com/UgqOw1k.png)


Sendo que:

1. Risco >= 15: **Elevado**
2. 5 < Risco < 15: **Médio**
3. Risco =< 5: **Baixo** 


## Análise dos Riscos

<table class="table table-hover">
    <thead>
        <tr>
            <th scope="col">#</th>
            <th scope="col">Descrição</th>
            <th scope="col">Probabilidade</th>
            <th scope="col">Impacto</th>
            <th scope="col">Risco</th>
        </tr>
    </thead>
    <tbody>
        <tr class="table-danger">
            <th scope="row">3</th>
            <td>Falha na Comunicação</td>
            <td>5</td>
            <td>5</td>
            <td>25</td>
        </tr>
        <tr class="table-danger">
            <th scope="row">1</th>
            <td>Mudança Arquitetural</td>
            <td>4</td>
            <td>5</td>
            <td>20</td>
        </tr>
        <tr class="table-danger">
            <th scope="row">6</th>
            <td>Descomprometimento da Equipe</td>
            <td>4</td>
            <td>5</td>
            <td>20</td>
        </tr>
        <tr class="table-danger">
            <th scope="row">8</th>
            <td>Dificuldade com as Tecnologias Adotadas</td>
            <td>4</td>
            <td>4</td>
            <td>16</td>
        </tr>
        <tr class="table-warning">
            <th scope="row">2</th>
            <td>Mudança de Escopo</td>
            <td>3</td>
            <td>4</td>
            <td>12</td>
        </tr>
        <tr class="table-warning">
            <th scope="row">4</th>
            <td>Imaturidade na Gerência</td>
            <td>3</td>
            <td>4</td>
            <td>12</td>
        </tr>
        <tr class="table-warning">
            <th scope="row">9</th>
            <td>Atraso nas Entregas</td>
            <td>3</td>
            <td>4</td>
            <td>12</td>
        </tr>
        <tr class="table-warning">
            <th scope="row">7</th>
            <td>Erro de Priorização</td>
            <td>3</td>
            <td>3</td>
            <td>9</td>
        </tr>
        <tr class="table-warning">
            <th scope="row">5</th>
            <td>Desistência de Membros</td>
            <td>2</td>
            <td>4</td>
            <td>8</td>
        </tr>
        <tr class="table-info">
            <th scope="row">10</th>
            <td>Greve na UnB</td>
            <td>1</td>
            <td>5</td>
            <td>5</td>
        </tr>
        <tr class="table-info">
            <th scope="row">11</th>
            <td>A solução não atender as expectativas do usuário final</td>
            <td>1</td>
            <td>2</td>
            <td>2</td>
        </tr>
    </tbody>
</table>

<br />
<br />

# Planejamento de respostas aos riscos

| ID | Descrição | Risco | Ação | Descrição da Ação | Responsável |
| - | - | - | - | - | - |
| 1 | Mudança Arquitetural | 20 | Mitigar |  Pensamento crítico a respeito da arquitetura e procurando professores e outros suportes para a sua construção   | Arquiteta |
| 2 | Mudança de Escopo | 12 | Previnir | Validando constantemente com os steakholders | Product Owner |
| 3 | Falha na Comunicação | 25 | Previnir | Realizando sempre todos os rituais e incentivando a comunicação por issue | Tech Lead |
| 4 | Imaturidade na Gerência | 12 | Mitigar | Mantendo o pensamento critico e estratégico a respeito das métricas coletadas e realizando todos os rituais | Time de EPS, mas principalmente a Tech Lead |
| 5 | Desistência de Membros | 8 | Aceitar | Realocação de tarefas | Tech Lead |
| 6 | Descomprometimento da Equipe | 20 | Previnir | Mostrar o propósito de suas ações, trazendo a sensação de responsabilidade, além de aproximar o time de MDS das tomadas de decisão | Time de EPS |
| 7 | Erro de Priorização | 9 | Previnir | Utilizando técnicas de priorização e estar constantemente reavaliando a priorização | Product Owner | 
| 8 | Dificuldade com as Tecnologias Adotadas | 16 | Mitigar | Promover treinamentos, conteúdo online e fornecer suporte para dúvidas e dificuldades de MDS | Time de EPS, mas principalmente Arquiteta e DevOps |
| 9 | Atraso nas Entregas | 12 | Previnir | Realizando os rituais e observando ao longo da sprint a necessidade de intervenção de EPS | Tech Lead |
| 10 | Greve na UnB | 5 | Aceitar | Reavaliar planejamento do projeto | Tech Lead |
| 11 | A solução não atender as expectativas do usuário final | 2 | Previnir | Deve ser evitado realizando uma pesquisa de mercado e avaliando o interesse do público alvo na aplicação | Product Owner |

<br />

### O monitoramento dos riscos será feito utilizando o Burndown de Riscos, que estará presente na documentação dos resultados da sprint. Assim como o relatório do que foi feito para que os riscos sejam mitigados. 