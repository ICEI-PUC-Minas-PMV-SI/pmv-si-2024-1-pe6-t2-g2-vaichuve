# APIs e Web Services

O projeto de backend da aplicação VaiChuve consiste em uma solução serveless hosteado no provedor de serviços SupaBase e utilizando serviços de
cloud functions e banco de dados on demand. 

## Objetivos da API

A API tem como objetivo ser leve e escalável para aguentar diversas cargas de workload dos usuários web e mobile e além disso entregar uma solução simples
de desenvolvimento e manutenção para que um pequeno pacote de dados seja entregue ao usuário de maneira rápida e confiável.

## Arquitetura

- Supabase: Supabase é uma plataforma que fornece um conjunto de ferramentas para desenvolvimento de aplicativos web e móveis, incluindo banco de dados PostgreSQL, autenticação, armazenamento de arquivos e funções serverless.

- Banco de Dados PostgreSQL: O banco de dados PostgreSQL é o componente central onde os dados do aplicativo são armazenados. Ele é gerenciado pelo Supabase e contém informações como usuários, configurações do aplicativo e dados relacionados ao clima.

- Funções Serverless: As funções serverless são pequenos trechos de código que podem ser executados em resposta a eventos específicos, como solicitações de API. No caso do Supabase, essas funções são executadas em resposta a chamadas de API e têm acesso direto ao banco de dados. Vamos utilizar como um cronograma de consulta as informações do clima.

- Integração com o Aplicativo e Aplicação Web: O aplicativo e a aplicação web fazem solicitações para as APIs fornecidas pelo backend. Isso inclui solicitações para autenticação de usuários, recuperação e modificação de dados do banco de dados e obtenção de informações sobre o clima. As funções serverless respondem a essas solicitações executando consultas no banco de dados ou interagindo com APIs externas, conforme necessário, e retornam os resultados para os clientes.

## Modelagem da Aplicação

Abaixo temos um overview geral da modelagem de dados que iremos utilizar na aplicação.
\\
![Modelagem de Dados](img/ModelagemDeDados.jpg)

## Fluxo de Dados

O principal fluxo de dados consiste principalmente em chamados que o usuário mobile ou web faz de maneira pública ao backend para receber as informações de clima da sua localidade em um espaço de tempo. Esse chamado deve prover os dados de localidade e opcionalmente data para pesquisas de histórico de clima.

## Requisitos Funcionais

|ID    | Descrição do Requisito                                                                                        | Prioridade |
|------|---------------------------------------------------------------------------------------------------------------|------------|
|RF-001| Permitir que o usuário consulte previsões metereológicas                                                      | ALTA       |
|RF-002| Permitir que o usuário consulte histórico de previsões metereológicas                                         | ALTA       | 
|RF-003| Exibir na interface notícias relacionadas ao clima                                                            | BAIXA      |

## Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|------------------------------------------------------------------------------------------------|------|
|RNF-001| O sistema deve contar com métodos de acessibilidade para deficiente visuais                    | ALTA | 
|RNF-002| O sistema deve enviar notificações para usuário para situações de chuva no local do usuário    | ALTA |
|RNF-002| O sistema deve rodar em plataformas web, android                                               | ALTA | 

## Tecnologias Utilizadas

- PostgreSQL
- Serverless Functions
- React Native
- React

## API Endpoints

### Endpoint 1
- Método: GET
- URL: /cidade
- Parâmetros:
  - id: Identificador único da Cidade (bigint)
  - nome: Nome da Cidade (character varying)
  - uf: Identificador único do Estado (bigint)
  - ibge: Identificador único do IBGE (integer)
  - lat_lon: Lat e Long espacial (point)
  - latitude: Latitude (double precision)
  - longitude: Longitude (double precision)
  - cod_tom: Código TOM (SEFAZ) (smallint)
- Resposta:
  - Sucesso (200 OK)
    ```
    [
    	{
    		"id": 1,
    		"nome": "Nome da Cidade",
    		"uf": 1,
    		"ibge": 123456,
    		"lat_lon": "(12.3456789,-12.3456789)",
    		"latitude": 12.3456789,
    		"longitude": -12.3456789,
    		"cod_tom": 123
    	}
    ]
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 2
- Método: GET
- URL: /clima
- Parâmetros:
  - id: No description (bigint)
  - dados_api: No description (json)
  - cidade: No description (bigint)
  - created_at: No description (timestamp with time zone)
- Resposta:
  - Sucesso (200 OK)
    ```
    [
    	{
    		"id": 1,
    		"dados_api": {},
    		"cidade": 1,
    		"created_at": "2024-03-21T00:56:39.991817+00:00"
    	}
    ]
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 3
- Método: GET
- URL: /dispositivos
- Parâmetros:
  - id: No description (bigint)
  - uuid: No description (uuid)
  - cidade: No description (bigint)
  - latitude: No description (double precision)
  - longitude: No description (double precision)
  - created_at: No description (timestamp with time zone)
- Resposta:
  - Sucesso (200 OK)
    ```
    [
    	{
    		"id": 1,
    		"uuid": "some_uuid",
    		"cidade": 1,
    		"latitude": 12.3456789,
    		"longitude": -12.3456789,
    		"created_at": "2024-03-21T00:56:39.991817+00:00"
    	}
    ]
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 4
- Método: GET
- URL: /estado
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - uf: No description (character varying)
  - ibge: No description (integer)
  - pais: No description (bigint)
  - ddd: No description (json)
- Resposta:
  - Sucesso (200 OK)
    ```
    [
    	{
    		"id": 1,
    		"nome": "Nome do Estado",
    		"uf": "UF",
    		"ibge": 123456,
    		"pais": 1,
    		"ddd": {}
    	}
    ]
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 5
- Método: GET
- URL: /pais
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - nome_pt: No description (character varying)
  - sigla: ISO 3166-1 Alpha2 (character varying)
  - bacen: No description (integer)
- Resposta:
  - Sucesso (200 OK)
    ```
    [
    	{
    		"id": 1,
    		"nome": "Nome do País",
    		"nome_pt": "Nome do País em Português",
    		"sigla": "BR",
    		"bacen": 1234
    	}
    ]
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```
### Endpoint 6
- Método: POST
- URL: /cidade
- Parâmetros:
  - id: Identificador único da Cidade (bigint)
  - nome: Nome da Cidade (character varying)
  - uf: Identificador único do Estado (bigint)
  - ibge: Identificador único do IBGE (integer)
  - lat_lon: Lat e Long espacial (point)
  - latitude: Latitude (double precision)
  - longitude: Longitude (double precision)
  - cod_tom: Código TOM (SEFAZ) (smallint)
- Corpo:
  ```
  {
    "nome": "Nome da Cidade",
    "uf": 1,
    "ibge": 123456,
    "lat_lon": "(12.3456789,-12.3456789)",
    "latitude": 12.3456789,
    "longitude": -12.3456789,
    "cod_tom": 123
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 7
- Método: POST
- URL: /clima
- Parâmetros:
  - id: No description (bigint)
  - dados_api: No description (json)
  - cidade: No description (bigint)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "dados_api": {},
    "cidade": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 8
- Método: POST
- URL: /dispositivos
- Parâmetros:
  - id: No description (bigint)
  - uuid: No description (uuid)
  - cidade: No description (bigint)
  - latitude: No description (double precision)
  - longitude: No description (double precision)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "uuid": "some_uuid",
    "cidade": 1,
    "latitude": 12.3456789,
    "longitude": -12.3456789
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 9
- Método: POST
- URL: /estado
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - uf: No description (character varying)
  - ibge: No description (integer)
  - pais: No description (bigint)
  - ddd: No description (json)
- Corpo:
  ```
  {
    "nome": "Nome do Estado",
    "uf": "UF",
    "ibge": 123456,
    "pais": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 10
- Método: POST
- URL: /pais
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - nome_pt: No description (character varying)
  - sigla: ISO 3166-1 Alpha2 (character varying)
  - bacen: No description (integer)
- Corpo:
  ```
  {
    "nome": "Nome do País",
    "nome_pt": "Nome do País em Português",
    "sigla": "BR",
    "bacen": 1234
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```
### Endpoint 11
- Método: PATCH
- URL: /cidade
- Parâmetros:
  - id: Identificador único da Cidade (bigint)
  - nome: Nome da Cidade (character varying)
  - uf: Identificador único do Estado (bigint)
  - ibge: Identificador único do IBGE (integer)
  - lat_lon: Lat e Long espacial (point)
  - latitude: Latitude (double precision)
  - longitude: Longitude (double precision)
  - cod_tom: Código TOM (SEFAZ) (smallint)
- Corpo:
  ```
  {
    "id": 1,
    "nome": "Novo Nome da Cidade",
    "uf": 2,
    "ibge": 654321,
    "lat_lon": "(11.1111111,-11.1111111)",
    "latitude": 11.1111111,
    "longitude": -11.1111111,
    "cod_tom": 456
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 12
- Método: PATCH
- URL: /clima
- Parâmetros:
  - id: No description (bigint)
  - dados_api: No description (json)
  - cidade: No description (bigint)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "id": 1,
    "dados_api": {"new_data": "new_value"}
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 13
- Método: PATCH
- URL: /dispositivos
- Parâmetros:
  - id: No description (bigint)
  - uuid: No description (uuid)
  - cidade: No description (bigint)
  - latitude: No description (double precision)
  - longitude: No description (double precision)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "id": 1,
    "uuid": "new_uuid",
    "cidade": 2,
    "latitude": 22.2222222,
    "longitude": -22.2222222
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 14
- Método: PATCH
- URL: /estado
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - uf: No description (character varying)
  - ibge: No description (integer)
  - pais: No description (bigint)
  - ddd: No description (json)
- Corpo:
  ```
  {
    "id": 1,
    "nome": "Novo Nome do Estado",
    "uf": "NN",
    "ibge": 987654,
    "pais": 2
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```

### Endpoint 15
- Método: PATCH
- URL: /pais
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - nome_pt: No description (character varying)
  - sigla: ISO 3166-1 Alpha2 (character varying)
  - bacen: No description (integer)
- Corpo:
  ```
  {
    "id": 1,
    "nome": "Novo Nome do País",
    "nome_pt": "Novo Nome do País em Português",
    "sigla": "NP",
    "bacen": 5678
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY
  - Content-Type: application/json
  - Prefer: return=minimal
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```
### Endpoint 16
- Método: DELETE
- URL: /cidade
- Parâmetros:
  - id: Identificador único da Cidade (bigint)
  - nome: Nome da Cidade (character varying)
  - uf: Identificador único do Estado (bigint)
  - ibge: Identificador único do IBGE (integer)
  - lat_lon: Lat e Long espacial (point)
  - latitude: Latitude (double precision)
  - longitude: Longitude (double precision)
  - cod_tom: Código TOM (SEFAZ) (smallint)
- Corpo:
  ```
  {
    "id": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY

### Endpoint 17
- Método: DELETE
- URL: /clima
- Parâmetros:
  - id: No description (bigint)
  - dados_api: No description (json)
  - cidade: No description (bigint)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "id": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY

### Endpoint 18
- Método: DELETE
- URL: /dispositivos
- Parâmetros:
  - id: No description (bigint)
  - uuid: No description (uuid)
  - cidade: No description (bigint)
  - latitude: No description (double precision)
  - longitude: No description (double precision)
  - created_at: No description (timestamp with time zone)
- Corpo:
  ```
  {
    "id": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY

### Endpoint 19
- Método: DELETE
- URL: /estado
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - uf: No description (character varying)
  - ibge: No description (integer)
  - pais: No description (bigint)
  - ddd: No description (json)
- Corpo:
  ```
  {
    "id": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY

### Endpoint 20
- Método: DELETE
- URL: /pais
- Parâmetros:
  - id: No description (bigint)
  - nome: No description (character varying)
  - nome_pt: No description (character varying)
  - sigla: ISO 3166-1 Alpha2 (character varying)
  - bacen: No description (integer)
- Corpo:
  ```
  {
    "id": 1
  }
  ```
- Cabeçalhos:
  - apikey: PRIVATE_KEY
  - Authorization: Bearer PRIVATE_KEY


## Considerações de Segurança

Estaremos utilizando a versão gratuita do Supabase, dessa forma não estaremos aderente ao SOC2. Os logs de acesso ao sistema serão retidos por apenas um dia, todos os endpoints estarão protegidos e será necessário a autenticação utilizando uma conta de serviço para acesso anônimo aos dados.

## Implantação

Para implantar nossa aplicação de previsão de clima com acessibilidade para pessoas com deficiência visual em um ambiente de produção, seguimos os seguintes passos. Primeiro, definimos os requisitos de hardware, como um servidor com capacidade de processamento e armazenamento adequada, também um smartphone com acesso a internet, e software, incluindo um sistema operacional compatível (Andriod ou IOS) e as dependências necessárias para executar o Supabase, React e React Native. Em seguida, escolhemos o Supabase como nossa plataforma de hospedagem, aproveitando sua facilidade de uso e escalabilidade para sistemas distribuídos. Depois, configuramos o ambiente de implantação no Supabase, instalando as dependências do projeto e configurando as variáveis de ambiente, como chaves de API e configurações específicas do ambiente de produção. Com tudo preparado, realizamos o deploy da aplicação no Supabase, seguindo suas instruções específicas para implantação de aplicativos React e React Native. Por fim, conduzimos testes extensivos para garantir que a aplicação esteja funcionando corretamente no ambiente de produção, assegurando uma experiência confiável e acessível para todos os usuários, incluindo pessoas com deficiência visual.

## Testes

Foram realizados testes utilizando a plataforma Insomnia para validar a funcionalidade e integridade dos endpoints da API. Utilizando uma abordagem manual, cada solicitação foi examinada para garantir que os dados fossem corretamente transmitidos e que as respostas estivessem de acordo com as especificações. Essa estratégia permitiu uma validação detalhada e eficaz, garantindo a qualidade e confiabilidade dos serviços oferecidos pelo Back-end da aplicação.

# Referências

Foi utilizada a documentação do Supabase para realizar as consultas para construção do código.
