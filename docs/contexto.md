# Introdução

O Projeto VaiChuve tem como objetivo a criação de uma solução web e mobile que permita ao usuário acessar informações de previsões do tempo e histórico meteorológico, além de receber notificações com a previsão meteorológica diária em seu dispositivo móvel.

## Problema

Atualmente, existem várias informações meteorológicas disponíveis em diversos sistemas e aplicações. No entanto, é necessário realizar uma pesquisa mais direcionada para encontrar aplicações úteis e inclusivas para pessoas com deficiência visual. 

## Objetivos

O objetivo do projeto é integrar uma ferramenta no cotidiano do usuário, permitindo que ele consulte informações meteorológicas de forma rápida e receba notificações em tempo real sobre situações meteorológicas fora do comum. De maneira específica, pretendemos focar nossas pesquisas na criação de um sistema acessível para portadores de deficiência visual e que permita a notificação
de situações meterológicas incomuns via plataformas mobile.

## Justificativa

Atravez de pesquisas nos acervos mais comuns de aplicativos notamos uma dificuldade de encontrar soluções metereológicas que foquem no usuário com deficiencia visual e tomamos essa dor como motivação para a criação desse tipo de aplicação.

## Público-Alvo

O público alvo da aplicação são pessoas deficiente visuais que tem costume de usar de computadores e smartphones adaptados para suas nescessidades.

# Especificações do Projeto

A seguir temos alguns exemplo de usuário e suas dores que servirão de base na ilustração de do publico alvo do projeto.

## Personas

Pedro Paulo tem 26 anos, é arquiteto recém-formado e autônomo. Pensa em se desenvolver profissionalmente através de um mestrado fora do país, pois adora viajar, é solteiro e sempre quis fazer um intercâmbio. Está buscando uma agência que o ajude a encontrar universidades na Europa que aceitem alunos estrangeiros.

Enumere e detalhe as personas da sua solução. Para tanto, baseie-se tanto nos documentos disponibilizados na disciplina e/ou nos seguintes links:

> **Links Úteis**:
> - [Rock Content](https://rockcontent.com/blog/personas/)
> - [Hotmart](https://blog.hotmart.com/pt-br/como-criar-persona-negocio/)
> - [O que é persona?](https://resultadosdigitais.com.br/blog/persona-o-que-e/)
> - [Persona x Público-alvo](https://flammo.com.br/blog/persona-e-publico-alvo-qual-a-diferenca/)
> - [Mapa de Empatia](https://resultadosdigitais.com.br/blog/mapa-da-empatia/)
> - [Mapa de Stalkeholders](https://www.racecomunicacao.com.br/blog/como-fazer-o-mapeamento-de-stakeholders/)
>
Lembre-se que você deve ser enumerar e descrever precisamente e personalizada todos os clientes ideais que sua solução almeja.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
|Usuário do sistema  | Registrar minhas tarefas           | Não esquecer de fazê-las               |
|Administrador       | Alterar permissões                 | Permitir que possam administrar contas |

Apresente aqui as histórias de usuário que são relevantes para o projeto de sua solução. As Histórias de Usuário consistem em uma ferramenta poderosa para a compreensão e elicitação dos requisitos funcionais e não funcionais da sua aplicação. Se possível, agrupe as histórias de usuário por contexto, para facilitar consultas recorrentes à essa parte do documento.

> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. 

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|---------------------------------------------------------------------------------------------------------------|------|
|RF-001| Permitir que o usuário consulte previsões metereológicas                                                      | ALTA |
|RF-002| Permitir que o usuário consulte histórico de previsões metereológicas                                         | ALTA | 
|RF-003| Permitir que o usuário mande um feedback sobre a previsão de tempo que ele recebeu                            | MÉDIA |
|RF-004| Exibir na interface uma noticia do dia para o usuário                                                         | BAIXA |
|RF-005| Permitir que o usuário participe em uma enquete de palpites sobre a situação metereológica dos próximos dias  | BAIXA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|------------------------------------------------------------------------------------------------|------|
|RNF-001| O sistema deve contar com métodos de acessibilidade para deficiente visuais                    | ALTA | 
|RNF-002| O sistema deve enviar notificações para usuário para situações de chuva no local do usuário    | ALTA |
|RNF-002| O sistema deve rodar em plataformas web, android e ios                                         | ALTA | 


## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                                                               |
|--|-----------------------------------------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre                                   |
|02| O desenvolvimento não irá atuar com programação mobile nativa                           |
|03| O projeto não irá incorporar práticas de inclusão de outras deficiências além da visual |

# Catálogo de Serviços

O projeto ira oferecer:

1 - Consulta de previsão metereológica.
2 - Consulta de histórico de condições metereológicas.
3 - Acessibilidade para deficiêntes visuais.

# Gerenciamento de Projeto

De acordo com o PMBoK v6 as dez áreas que constituem os pilares para gerenciar projetos, e que caracterizam a multidisciplinaridade envolvida, são: Integração, Escopo, Cronograma (Tempo), Custos, Qualidade, Recursos, Comunicações, Riscos, Aquisições, Partes Interessadas. Para desenvolver projetos um profissional deve se preocupar em gerenciar todas essas dez áreas. Elas se complementam e se relacionam, de tal forma que não se deve apenas examinar uma área de forma estanque. É preciso considerar, por exemplo, que as áreas de Escopo, Cronograma e Custos estão muito relacionadas. Assim, se eu amplio o escopo de um projeto eu posso afetar seu cronograma e seus custos.

## Gerenciamento de Tempo

Com diagramas bem organizados que permitem gerenciar o tempo nos projetos, o gerente de projetos agenda e coordena tarefas dentro de um projeto para estimar o tempo necessário de conclusão.

![Diagrama de rede simplificado notação francesa (método francês)](img/02-diagrama-rede-simplificado.png)

O gráfico de Gantt ou diagrama de Gantt também é uma ferramenta visual utilizada para controlar e gerenciar o cronograma de atividades de um projeto. Com ele, é possível listar tudo que precisa ser feito para colocar o projeto em prática, dividir em atividades e estimar o tempo necessário para executá-las.

![Gráfico de Gantt](img/02-grafico-gantt.png)

## Gerenciamento de Equipe

O gerenciamento adequado de tarefas contribuirá para que o projeto alcance altos níveis de produtividade. Por isso, é fundamental que ocorra a gestão de tarefas e de pessoas, de modo que os times envolvidos no projeto possam ser facilmente gerenciados. 

![Simple Project Timeline](img/02-project-timeline.png)

# Arquitetura da Solução

Definição de como o software é estruturado em termos dos componentes que fazem parte da solução e do ambiente de hospedagem da aplicação.

![Arquitetura da Solução](img/02-mob-arch.png)

## Tecnologias Utilizadas

Descreva aqui qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas.

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.

## Hospedagem

Explique como a hospedagem e o lançamento da plataforma foi feita.

> **Links Úteis**:
>
> - [Website com GitHub Pages](https://pages.github.com/)
> - [Programação colaborativa com Repl.it](https://repl.it/)
> - [Getting Started with Heroku](https://devcenter.heroku.com/start)
> - [Publicando Seu Site No Heroku](http://pythonclub.com.br/publicando-seu-hello-world-no-heroku.html)
