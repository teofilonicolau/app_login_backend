# app_login_backend

## Testar o endpoint `/auth/register`

### Configuração
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

### Resposta Esperada
- **Status:** 200 OK
- **Corpo:**
```json
{
  "name": "Teofilo Nicolau",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJsb2dpbi1hdXRoLWFwaSIsInN1YiI6InRlb2ZpbG9AZXhhbXBsZS5jb20iLCJleHAiOjE3MzU0ODA1MjR9.P5njEX2Bri9nF5p8a3xYYQTBEhyJd1y8G7CNSXDdKXo"
}
```

### Caso o email já exista
- **Status:** 400 Bad Request

![Registro](https://github.com/user-attachments/assets/a39ab81e-d95e-428a-b8da-e013e75c82b7)

---

## Testar o endpoint `/auth/login`

### Configuração
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

## Testar o endpoint `/user`

### Configuração
- **Método:** GET
- **URL:** `http://localhost:8080/user`
- **Headers:**
  - `Authorization: Bearer JWT_TOKEN_GERADO`

### Resposta Esperada
- **Status:** 200 OK
- **Corpo:**

![Usuário](https://github.com/user-attachments/assets/639bdff0-30d9-4ae6-ac99-df12ad5aae35)
