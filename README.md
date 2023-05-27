# Projeto Java 11 com Spring Boot Web

Este é um projeto Java 11 que utiliza o framework Spring Boot Web para criar duas APIs independentes: uma API de produtos e uma API de avaliações. A API de produtos implementa um Circuit Breaker utilizando o Resilience4j para as chamadas com a API de avaliações. Ambas as APIs utilizam bancos de dados locais e um cache em memória apenas para fins de exemplo.

## Pré-requisitos

Certifique-se de ter os seguintes itens instalados em seu ambiente de desenvolvimento:

- Java 11 (ou superior)
- Maven

## Estrutura do projeto

O projeto é dividido em dois módulos:

1. **api-produtos**: Contém a API de produtos, que lida com as operações relacionadas aos produtos.
2. **api-avaliacoes**: Contém a API de avaliações, responsável por gerenciar as avaliações dos produtos.

## Configuração do ambiente

1. Clone este repositório para o seu ambiente de desenvolvimento local.
2. Importe os projetos `api-produtos` e `api-avaliacoes` em sua IDE favorita.

## Configuração dos bancos de dados

Cada API possui seu próprio banco de dados local. Certifique-se de configurar os bancos de dados antes de executar as APIs.

### Banco de dados da API de produtos

O banco de dados da API de produtos está configurado para utilizar um banco de dados local embutido (H2) por padrão. Você pode modificar as configurações do banco de dados no arquivo `api-produtos/src/main/resources/application.properties`, se necessário.

### Banco de dados da API de avaliações

O banco de dados da API de avaliações também utiliza um banco de dados local embutido (H2) por padrão. As configurações do banco de dados podem ser encontradas no arquivo `api-avaliacoes/src/main/resources/application.properties`.

## Configuração do cache

As APIs utilizam um cache em memória para exemplos. O cache está configurado por padrão e não requer nenhuma configuração adicional.

## Executando as APIs

Siga as etapas abaixo para executar as APIs:

1. Navegue até o diretório raiz do projeto clonado.
2. Execute o seguinte comando para iniciar a API de produtos:
   ```
   cd api-produtos
   mvn spring-boot:run
   ```
3. Em outro terminal, execute o seguinte comando para iniciar a API de avaliações:
   ```
   cd api-avaliacoes
   mvn spring-boot:run
   ```
4. As APIs agora estão em execução e podem ser acessadas através dos seguintes endpoints:
    - API de produtos: http://localhost:8080/api/produtos
                       http://localhost:8080/api/produtos/1
    - API de avaliações: http://localhost:8081/api/avaliacoes

## Utilizando o Circuit Breaker

O Circuit Breaker foi implementado na API de produtos utilizando a biblioteca Resilience4j. Ele é responsável por lidar com falhas temporárias na chamada da API de avaliações.

A configuração do Circuit Breaker pode ser encontrada no arquivo `api-produtos/src/main/resources/application.properties`.

## Contribuindo

Se você deseja contribuir com este projeto, siga as etapas abaixo:

1. Faça um fork deste repositório e clone-o em seu ambiente local.
2. Crie uma nova branch para suas alterações:
   ```
   git

checkout -b minha-nova-feature
   ```
3. Faça as alterações necessárias e adicione os arquivos modificados:
   ```
git add .
   ```
4. Faça o commit das suas alterações:
   ```
git commit -m "Minha nova feature"
   ```
5. Faça o push das alterações para o seu repositório remoto:
   ```
git push origin minha-nova-feature
   ```
6. Abra um pull request neste repositório para que possamos revisar e mesclar suas alterações.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para obter mais informações.