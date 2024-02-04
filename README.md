## API de memes

Para inicar a aplicação, navegue ao diretório raiz e execute o comando Maven a seguir:
```sh
mvn spring-boot:run
```

Para interagir com a aplicação através do comando Curl para POST e GET, você pode tentar os comandos abaixo:

> [!IMPORTANT]
> Existem vínculos entre as tabelas do banco de dados, por isso é preferível adicionar `memes` quando já existem `categorias` e `usuários`.
```
  curl -X POST \
  http://localhost:8081/memelandia/usuarios \
  -H 'Content-Type: application/json' \
  -d '{
    "nome": "João",
    "email": "joao@gmail.com",
    "dataCadastro": "1998-02-12"
   }'
```
```  
 curl -X POST \
  http://localhost:8081/memelandia/categorias \
  -H 'Content-Type: application/json' \
  -d '{
    "nome": "Catoon",
    "descricao": "Cartoon meme",
    "dataCadastro": "2013-01-01",
      "usuario": {
    	"id": "1"
      }
  }'
```
```
 curl -X POST \
  http://localhost:8081/memelandia/memes \
  -H 'Content-Type: application/json' \
  -d '{
  "nome": "This is fine",
  "descricao": "Dog sitting at a table, surrounded by flames",
  "dataCadastro": "2013-01-01",
  "categoriaMeme": {
    "id": 1,
    "usuario": {
      "id": 1
    }
  },
  "usuario": {
    "id": 1
    }
  }'
```
```  
  curl -X GET \
  http://localhost:8081/memelandia/memes \
  -H 'Content-Type: application/json'
```
``` 
  curl -X GET \
  http://localhost:8081/memelandia/categorias \
  -H 'Content-Type: application/json'
```
```
  curl -X GET \
  http://localhost:8081/memelandia/usuarios
  -H 'Content-Type: application/json'
```
  
 
 
