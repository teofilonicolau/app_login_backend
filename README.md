1. Testar o endpoint /auth/register: 
- Configuração
 - Método: POST
- URL: http://localhost:8080/auth/register
- Headers:
- Content-Type: application/json.
- Corpo:
   ```
     {
     "name": "Teofilo Nicolau",
     "email": "teofilo@example.com",
     "password": "senha123"
    }

   ```

  - Se o email já existir no banco de dados, a API deverá retornar:
  - Status: 400 Bad Request




![image](https://github.com/user-attachments/assets/a39ab81e-d95e-428a-b8da-e013e75c82b7)


2. Testar o endpoint /auth/login:
- Configuração
- Método: POST.
- URL: http://localhost:8080/auth/login.
- Headers:
 -Content-Type: application/json.
 - - Corpo:
   ```
    {
     "email": "teofilo@example.com",
     "password": "senha123"
   }

   ```


![image](https://github.com/user-attachments/assets/03e3095c-19bd-4bff-82eb-a06cb5b4b212).

3. Testar o endpoint /user:
 - Configuração
- Método: GET
- URL: http://localhost:8080/user
- Headers:
- Authorization: Bearer JWT_TOKEN_GERADO
- Resposta Esperada
- Status: 200 OK
- Corpo:  
   


