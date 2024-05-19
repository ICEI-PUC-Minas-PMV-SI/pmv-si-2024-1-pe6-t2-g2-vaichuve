# Front-end Web

O Projeto VaiChuve Web pretende disponibilizar uma versão desktop da aplicação ultilizando as ferramentas de acessibilidade dos navegadores mais ultilizados atualmente e leva em consideração as nescessidades de portadores de diversos tipos de deficiências visuais ao proporcionar acesso a informações de clima e local.

## Tecnologias Utilizadas

- Next.js: Framework React para renderização do lado do servidor e criação de aplicações web rápidas e eficientes.
- React: Biblioteca JavaScript para construção de interfaces de usuário.
- Chakra UI: Biblioteca de componentes React para a criação de interfaces de usuário acessíveis e estilizadas.
- TypeScript: Superset de JavaScript que adiciona tipagem estática ao código.
- Tailwind CSS: Framework CSS utilitário para criar layouts customizados rapidamente.
- ESLint: Ferramenta de linting para garantir a qualidade e consistência do código.

## Arquitetura

A arquitetura da aplicação "vai-chuve" segue um modelo baseado em componentes, onde cada parte da interface é construída como um componente reutilizável e independente. Abaixo está uma descrição geral dos componentes principais e suas interações:\

- Componentes de Interface: Utilizando Chakra UI para construir componentes estilizados e responsivos.
- Context API / React Hooks: Utilizados para gerenciar o estado da aplicação, como dados meteorológicos e preferências do usuário.
- Fetch/Axios: Utilizados para realizar chamadas a APIs externas para obter dados meteorológicos.
- Tailwind CSS: Utilizado para estilização utilitária, permitindo a rápida criação de layouts personalizados.

## Modelagem da Aplicação
[Descreva a modelagem da aplicação, incluindo a estrutura de dados, diagramas de classes ou entidades, e outras representações visuais relevantes.]

## Projeto da Interface Web

A imagem a abaixo mostra como foi inicialmente planejado a estrutura visual do projeto, suas logos e imagens bem como os blocos de informação que a aplicação vai disponibilizar.

![Design do Projeto](img/designProjeto.jpg)

### Layout Responsivo
[Discuta como a interface será adaptada para diferentes tamanhos de tela e dispositivos.]

### Interações do Usuário

O projeto não ira ultilizar de ferramentas visuais de animação, transição, modais e estruturas complexas de representação visual afim de maximizar a compatibilidade da informação com as interfaces de acessebilidades disponibilizadas insfraestruturas das plataformas onde a aplicação será disponibilizada. Dito isso a projeto pretende atender boas práticas de contraste de cores e fontes para a facilitação da interpretação da informação por portadores de deficiências que levam a visibilidade reduzida.

## Fluxo de Dados

[Diagrama ou descrição do fluxo de dados na aplicação.]

## Requisitos Funcionais

[Liste os principais requisitos funcionais da aplicação.]

## Requisitos Não Funcionais

[Liste os principais requisitos não funcionais da aplicação, como desempenho, segurança, escalabilidade, etc.]


## Considerações de Segurança

Para garantir a segurança da aplicação "vai-chuve", adotamos diversas técnicas de segurança essenciais. Primeiramente, utilizamos HTTPS para assegurar que todas as comunicações entre o cliente e o servidor sejam criptografadas, protegendo os dados contra interceptações maliciosas. Implementamos validação e sanitização rigorosas dos dados de entrada para prevenir ataques de injeção, como SQL Injection e Cross-Site Scripting (XSS). A autenticação e autorização robustas são configuradas para garantir que apenas usuários autenticados e autorizados possam acessar determinadas funcionalidades e dados sensíveis. Utilizamos bibliotecas e dependências seguras, mantendo-as sempre atualizadas para evitar vulnerabilidades conhecidas. Também empregamos ferramentas de análise estática e dinâmica do código para identificar e corrigir vulnerabilidades antes que elas sejam exploradas. Além disso, monitoramos continuamente a aplicação para detectar e responder rapidamente a qualquer atividade suspeita ou tentativa de ataque.

## Implantação

1. Certifique-se de que o ambiente de produção tenha suporte para Node.js.
2. Garanta pelo menos 512MB de RAM para lidar com operações simultâneas.
3. Assegure uma conexão estável à internet para acessar APIs externas de meteorologia.
4. Utilize a plataforma Vercel para hospedar a aplicação devido à sua robustez e facilidade de integração com Next.js.
5. Acesse o painel de controle da Vercel.
6. Conecte o repositório GitHub que contém o código da aplicação.
7. No painel da Vercel, configure o projeto para instalar automaticamente todas as dependências listadas no package.json.
8. No painel da Vercel, vá para a seção de variáveis de ambiente.
9. Adicione todas as variáveis necessárias, como chaves de API para serviços de meteorologia, garantindo que estejam configuradas corretamente para o ambiente de produção.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
