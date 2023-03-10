 [<img src="/logo.svg" height=100 width=1200>](https://idroid.vercel.app/)

  ##  Endpoints
  
  A API contém um total de X endpoints, sendo possível cadastrar novos usuários, realizar login e favoritar filmes, além de ... 
  
 A url base da API é esta: [Link de acesso](https://kenzie-movies.onrender.com/)
  
  # Cadastro de usuário
  
  `POST /users - FORMATO DA REQUISIÇÃO`
  
  ```markdown
   {
      "email": "fulano@mail.com",
      "password": "123456",
      "name": "fulano",
      "passwordConfirmation": "123456",
      "avatarLink":"https://avatars.githubusercontent.com/u/99143799?v=4"
        
   }
   ```

Caso a requisição seja bem sucedida, a resposta será assim:

`POST/users - FORMATO DA RESPOSTA - STATUS 201`

  ```markdown
{
	"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1pZ2xlc0BtYWlsLmNvbSIsImlhdCI6MTY3Nzg3MjA1MCwiZXhwIjoxNjc3ODc1NjUwLCJzdWIiOiI0In0.PV665AVld2zHU5cNeiurzp0gRpQXm-4-x9s8Yg_OQmw",
	"user": {
		"email": "fulano@mail.com",
		"name": "fulano",
		"passwordConfirmation": "123456",
		"avatarLink": "https://avatars.githubusercontent.com/u/99143799?v=4",
		"id": 3
	}
}
```
## Possíveis erros 

Caso seja enviado algum campo errado, a resposta de erro será assim:

A senha precisa ter pelo menos 6 caracteres.

`POST/users - FORMATO DA RESPOSTA - STATUS 400`

  ```markdown
"Password is too short"
```
Email já cadastrado.

`POST/users - FORMATO DA RESPOSTA - STATUS 400`
  ```markdown
"Email already exists"
```
 # Login
 
`POST/login - FORMATO DA REQUISIÇÃO`
 
 ```markdown
   {
      "email": "fulano@mail.com",
      "password": "123456",
             
   }
   ```
   
 Caso a requisição seja bem sucedida, a resposta será assim:

`POST/login - FORMATO DA RESPOSTA - STATUS 201`


 ```markdown
  {
	"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImNsYXJpY2VAbWFpbC5jb20iLCJpYXQiOjE2Nzc4NzMzOTYsImV4cCI6MTY3Nzg3Njk5Niwic3ViIjoiMyJ9.umQpgvEEUkRRBrrViZUzd3_Z6Nj5oUy5FfudDjw6BGk",
	"user": {
		"email": "fulano@mail.com",
		"name": "fulano",
		"passwordConfirmation": "123456",
		"avatarLink": "https://avatars.githubusercontent.com/u/99143799?v=4",
		"id": 3
	}
}
   ```
