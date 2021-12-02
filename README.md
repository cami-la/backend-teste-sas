# Teste técnico – Desenvolvedor Backend


## Considerações sobre o desafio

* Desenvolva as funcionalidades propostas utilizando JAVA 8 ou superior e Spring Boot
* Fazer upload do código para o github e enviar o link do repositório para nicolasfontenele@aridesa.com.br com o título **Teste Técnico - Dev Backend - <%NOME_COMPLETO%>**
* Esperamos uma documentação que contenha: Instruções de execução do projeto e instruções de como executar os testes unitários. Esperamos poder executar o projeto sem a necessidade de uma IDE.

* Você terá 7 dias corridos para entregar a solução. Caso precise de mais tempo entre em contato. Somos flexíveis com o prazo 😉.
* Utilizar ferramentas de build Maven ou Gradle
* Você deverá utilizar um banco de dados em memória, como o H2.

## Descrição do desafio

O SAS Aplica periodicamente simulados em toda a base de escolas para medir o desempenho de seus alunos. Para isso, precisamos de um sistema que faça a gestão desses simulados.

### Regras de negócio:

* Um simulado poderá ter N provas
* Cada prova tem uma lista de 10 questões, sendo 3 fáceis, 4 médias e 3 difíceis
* Cada prova contém um gabarito diferente associado

#### Cálculo de nota:
As notas dos alunos será composta pela seguinte formula:
$$
NP = (Qf *Vf) + (Qm *Vm) +  (Qd *Vd) + 600
$$
Onde,
*NP*: Nota da prova
*Qf*: quantidade de acertos de questões fáceis
*Qm*: quantidade de acertos de questões médias
*Qd*: quantidade de acertos de questões difíceis
*Vf*: valor de uma questão fácil.
*Vm*: valor de uma questão média.
*Vd*: valor de uma questão difícil.

|     Nível      |      Valor     |
|----------------|----------------|
|Fácil           |`15 pontos`     |
|Média           |`12 pontos`     |
|Difícil         |`8 pontos`      |

**A nota final do aluno será a média das notas de todas as provas de um simulado.**

#### Empate:
Caso haja empate de notas, os alunos que tiverem a mesma nota deverão ter a mesma classificação, por exemplo:

|     Aluno      |      Nota      |     Ranking    |
|----------------|----------------|----------------|
|João            |`750`           |`1`             |
|Pedro           |**`690`**       |**`2`**         |
|Maria           |**`690`**       |**`2`**         |
|Antonio         |`500`           |`4`             |
|José            |`400`           |`5`             |

### API:
Gostaríamos que fossem implementados os seguintes endpoints:

* Listagem de simulados
* Listagem do gabarito de uma prova
* Responder questão
* Listagem do Ranking dos 5 alunos melhores colocados com suas respectivas notas em um simulado

**Você poderá criar uma migration para ter uma massa de respostas.**

## O que iremos avaliar

* Se as funcionalidades estão implementadas corretamente
* Padrão REST
* Testes unitários
* Design de código (SOLID, DRY, KISS)
* Arquitetura da solução
* Documentação

## Pontos extras

* Ambiente rodando em container
* Uso de migrations para criação do banco de dados
* Hospedagem em alguma nuvem pública
