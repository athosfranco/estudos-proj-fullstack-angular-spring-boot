## 1. Inicializando o Projeto Front-End

Após criar o projeto Angular, devemos criar três pastas dentro da pasta src/app: ***components***, ***classes*** e ***services***.

### 1.1. Pasta "classes"
Essa pasta vai armazenar todas as classes que vamos utilizar no projeto. Exemplo: classe "Produto".

![image](https://user-images.githubusercontent.com/73993813/176905072-1cbb334b-0cc2-4e9e-9c12-162606d9fb56.png)

### 1.2. Pasta "services"
Vão ser armazenados todos os services que vamos usar na aplicação. 

## 2. Angular Services

### 2.1. O que são Services

Services são classes auxiliares que criam algum tipo de funcionalidade, buscam dados, etc.

### 2.2. Porque usar Services

Os componentes não devem buscar ou salvar dados diretamente. O Angular se preocupa bastante com a divisão correta de obrigações seguindo a arquitetura MVC, por isso,
os componentes devem se concentrar em apresentar dados (VIEW) e delegar acessos e busca dos dados a um service.


### 2.3. Criando um Service para buscar dados

![image](https://user-images.githubusercontent.com/73993813/177173393-e4507dd5-8ee3-4f45-89a0-cfd84d5e6e02.png)

Dentro da pasta "Services" devemos criar um serviço que vai ser utilizado para buscar dados na API REST desenvolvida em Spring Boot. 

Primeiro, antes de criar esse Service, vamos precisar de um módulo nativo do Angular chamado ***HttpClientModule***, que é utilizado para dar suporte a requisições HTTP. 
Vamos importar e declarar esse módulo dentro de ***src/app.module.ts***

![image](https://user-images.githubusercontent.com/73993813/177174907-800e49b6-204a-4481-bf15-360c63ed630f.png)


