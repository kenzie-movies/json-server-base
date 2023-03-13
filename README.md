 [<img src="/logo.svg" height=100 width=1200>](https://idroid.vercel.app/)
    
 Este é o repositório do projeto final - M3 da aplicação **Kenzie movies** - O objetivo dessa API é fornecer os dados necessários para o acesso a aplicação, bem como  interagir com suas funcionalidades. 

  ##  :hammer: Endpoints
  
  A API contém um total de X endpoints, sendo possível cadastrar novos usuários, realizar login e favoritar filmes, além de poder solicitar o cadastro de um novo filme, sendo aprovado ou rejeitado pelos administradores. 
  
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
   
   # Rotas que necessitam de autorização
   
   Rotas que necessitam de autorização devem ser informados no cabeçalho da requisição o campo "Authorization", dessa forma:
   **`Authorization: Bearer {token}`**
   
   ## Buscar Perfil do usuário logado (token e ID) 
   `GET/600/users/2 - ROTA DA REQUISIÇÃO`
   
   Nessa requisição é necessário o **TOKEN** e o **ID** do usuário setados no localStorage.
   
   Caso a requisição seja bem sucedida, a resposta será assim: 

  `GET/600/users/2 - FORMATO DA RESPOSTA - STATUS 200`
   
 ```markdown
{
	"email": "fulano@mail.com",
	"password": "$2a$10$JCAYhDCsqEiHQC.lFfhpLOWl/LmQvd7pMw19Lb6RKMxNKMrXsLQYm",
	"name": "fulano",
	"passwordConfirmation": "123456",
	"avatarLink": "https://avatars.githubusercontent.com/u/99143799?v=4",
	"id": 2
}
   ```

   ## Buscar todos os filmes (token) 
   `GET/movies/ - ROTA DA REQUISIÇÃO`
   
   Nessa requisição é necessário somente o **TOKEN.**
   
   Caso a requisição seja bem sucedida, a resposta será assim: 

  `GET/movies/ - FORMATO DA RESPOSTA - STATUS 200`
  
   ```markdown
[
	{
		"name": "Vingadores: Guerra Infinita",
		"synopsis": "Em Vingadores: Guerra Infinita, Thanos (Josh Brolin) enfim chega à Terra, disposto a reunir as Joias do Infinito. Para enfrentá-lo, os Vingadores precisam unir forças com os Guardiões da Galáxia, ao mesmo tempo em que lidam com desavenças entre alguns de seus integrantes.",
		"cover": "https://br.web.img3.acsta.net/c_310_420/pictures/18/03/16/15/08/2019826.jpg",
		"release": "26/04/2018",
		"duration": "2h36min",
		"genre": "Ação, Fantasia, Aventura",
		"classification": "12 anos",
		"verified": true,
		"userId": 1,
		"id": 1
	},
	{
		"name": "Vingadores: Ultimato",
		"synopsis": "Em Vingadores: Ultimato, após Thanos eliminar metade das criaturas vivas em Vingadores: Guerra Infinita, os heróis precisam lidar com a dor da perda de amigos e seus entes queridos. Com Tony Stark (Robert Downey Jr.) vagando perdido no espaço sem água nem comida, o Capitão América/Steve Rogers (Chris Evans) e a Viúva Negra/Natasha Romanov (Scarlett Johansson) precisam liderar a resistência contra o titã louco.",
		"cover": "https://br.web.img2.acsta.net/c_310_420/pictures/19/04/26/17/30/2428965.jpg",
		"release": "25/04/2019",
		"duration": "3h01min",
		"genre": "Ação, Fantasia, Aventura",
		"classification": "12 anos",
		"verified": true,
		"userId": 1,
		"id": 2
	}
]
   ```
  
   
   
   
   
