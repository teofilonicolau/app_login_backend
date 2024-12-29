# app_login_backend

## Descrição da Aplicação

O `app_login_backend` é uma API de autenticação construída com Spring Boot. Ele fornece endpoints para registrar novos usuários, autenticar usuários existentes e acessar informações de usuário autenticado. A aplicação utiliza tokens JWT para gerenciar a autenticação e a segurança.

### Funcionalidades

- **Registro de Usuário**: Permite que novos usuários se registrem fornecendo um nome, email e senha.
- **Autenticação de Usuário**: Permite que usuários existentes façam login fornecendo email e senha, retornando um token JWT para acesso autenticado.
- **Acesso a Informações do Usuário**: Permite que usuários autenticados acessem informações protegidas.

## Endpoints

### Testar o endpoint `/auth/register`

#### Configuração
- **Método:** POST
- **URL:** `http://localhost:8080/auth/register`
- **Headers:**
  - `Content-Type: application/json`
- **Corpo:**
 ```json 
{
  "name": "Teofilo Nicolau",
  "email": "teofilo@example.com",
  "password": "senha123"
}
```

#### Resposta Esperada
- **Status:** 200 OK
- **Corpo:**
 ```json  
{
  "name": "Teofilo Nicolau",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJsb2dpbi1hdXRoLWFwaSIsInN1YiI6InRlb2ZpbG9AZXhhbXBsZS5jb20iLCJleHAiOjE3MzU0ODA1MjR9.P5njEX2Bri9nF5p8a3xYYQTBEhyJd1y8G7CNSXDdKXo"
}
```
![Registro](https://github.com/user-attachments/assets/a39ab81e-d95e-428a-b8da-e013e75c82b7)


#### Caso o email já exista
- **Status:** 400 Bad Request

---

### Testar o endpoint `/auth/login`

#### Configuração
- **Método:** POST
- **URL:** `http://localhost:8080/auth/login`
- **Headers:**
  - `Content-Type: application/json`
- **Corpo:**
 ```json  
{
  "email": "teofilo@example.com",
  "password": "senha123"
}
```
![Login](https://github.com/user-attachments/assets/03e3095c-19bd-4bff-82eb-a06cb5b4b212)

---

### Testar o endpoint `/user`

#### Configuração
- **Método:** GET
- **URL:** `http://localhost:8080/user`
- **Headers:**
  - `Authorization: Bearer JWT_TOKEN_GERADO`

#### Resposta Esperada
- **Status:** 200 OK
  
![Usuário](https://github.com/user-attachments/assets/639bdff0-30d9-4ae6-ac99-df12ad5aae35)  

---

## Como Executar a Aplicação

### Pré-requisitos

- JDK 17
- Maven

### Passos para Execução

1. Clone o repositório:
   git clone https://github.com/teofilonicolau/app_login_backend.git
   cd app_login_backend

2. Construa o projeto:
   mvn clean install

3. Execute a aplicação:
   mvn spring-boot:run

A aplicação estará disponível em `http://localhost:8080`.

---

## Configurações de Segurança

A aplicação utiliza tokens JWT para autenticação e segurança. As configurações de segurança estão definidas na classe `SecurityConfig` e o serviço de geração e validação de tokens está na classe `TokenService`.

### Configuração JWT

Certifique-se de definir a chave secreta do token JWT no arquivo `application.properties`:
api.security.token.secret=my-secret-key-from-video

### Filtro de Segurança

A classe `SecurityFilter` é utilizada para interceptar as requisições e validar o token JWT.

---

## Dependências

- Spring Boot Starter Data JPA
- Spring Boot Starter Security
- Spring Boot Starter Web
- Spring Boot DevTools
- H2 Database
- Lombok
- Spring Boot Starter Test
- Spring Security Test
- Java JWT (com.auth0:java-jwt)

---

## Testes

A classe de testes está configurada para garantir que o contexto da aplicação carrega corretamente. Testes adicionais podem ser adicionados para cobrir outros aspectos da aplicação.

---

### Contribuições

Se você deseja contribuir com este projeto, sinta-se à vontade para abrir um Pull Request com suas alterações. Certifique-se de que suas mudanças estejam bem documentadas e testadas.

---

### Licença

Este projeto está licenciado sob a Licença XYZ. Consulte o arquivo LICENSE para obter mais detalhes.

---

### Contato

Para mais informações, entre em contato com Teofilo Nicolau.
