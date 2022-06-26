# Spring Boot #1 - Inicializando o Projeto

A maioria das anotações nesse repositório vão documentar o processo de desenvolvimento backend para o projeto fullstack com Angular e Spring Boot.

## 1. Utilizando Spring Initializr

Link: https://start.spring.io/

![image](https://user-images.githubusercontent.com/73993813/174905450-a303286f-4e50-44fc-87fa-ee03fb40d56e.png)

## 2. Construindo o banco de dados com PostgreSQL

Foram criadas duas tabelas: produto e categoria_produto

Tabela 'produto'
![image](https://user-images.githubusercontent.com/73993813/174916456-8a0724de-6ed4-4714-9bf5-2ea801d151e9.png)

Tabela 'categoria_produto'
![image](https://user-images.githubusercontent.com/73993813/174916485-84b452f5-12a6-4111-b8c0-aa7b1df172a3.png)

## 3. Importar projeto no IntelliJ e editar o arquivo 'application.properties'

usei esse template para configurar o application.properties:
```
# ===============================
# = DATA SOURCE
# ===============================
# Set here configurations for the database connection
spring.datasource.url=jdbc:postgresql://localhost:5433/springbootdb
spring.datasource.username=postgres
spring.datasource.password=athos
spring.datasource.driver-class-name=org.postgresql.Driver
# Keep the connection alive if idle for a long time (needed in production)
spring.datasource.testWhileIdle=true
spring.datasource.validationQuery=SELECT 1
# ===============================
# = JPA / HIBERNATE
# ===============================
# Show or not log for each sql query
spring.jpa.show-sql=true
# Hibernate ddl auto (create, create-drop, update): with "create-drop" the database
# schema will be automatically created afresh for every start of application
spring.jpa.hibernate.ddl-auto=update

spring.data.rest.base-path=/api

# Naming strategy
spring.jpa.hibernate.naming.implicit-strategy=org.hibernate.boot.model.naming.ImplicitNamingStrategyLegacyHbmImpl
spring.jpa.hibernate.naming.physical-strategy=org.springframework.boot.orm.jpa.hibernate.SpringPhysicalNamingStrategy

# Allows Hibernate to generate SQL optimized for a particular DBMS
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

## 4. Desenvolver as entidades JPA

### 4.1. Criar package 'entities' e criar as entidades JPA 

Entidades são classes com os mesmos atributos encontrados no banco de dados.

![image](https://user-images.githubusercontent.com/73993813/175815882-87a56cc8-342d-4c7b-b28a-7c8d099e9d73.png)

### 4.2. Implementar as anotações necessárias para a entidade
![image](https://user-images.githubusercontent.com/73993813/175816169-d8a0f626-e425-49de-8e38-83bf93f061bf.png)

***OBS: IMPORTANTE:*** Adicionar as anotações @CreationTimestamp e @UpdateTimestamp nos atributos de DataCadastro e DataAtualizacao. O Hibernate vai automaticamente criar a data na criação e atualização de cada entrada no banco de dados.

### 4.3. Criar a entidade 'CategoriaProduto'

![image](https://user-images.githubusercontent.com/73993813/175817714-eebb95d2-265c-4304-8621-f99857002041.png)

Essa entidade possui um relacionamento avançado "OneToMany", onde teremos uma categoria para vários produtos. 

É necessário estabelecer a mesma relação inversa em "Produto", desta vez, com "ManyToOne".

![image](https://user-images.githubusercontent.com/73993813/175817792-481624a0-2583-4530-b73e-1d668d4fb3e3.png)

## 5. Desenvolver a REST API


