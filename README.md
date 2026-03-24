### 1\. POST /autores

*   Descrição: Cria um novo autor.
    
*   Corpo da requisição:
    
        [
        {
          "nome": "Autor A",
          "nacionalidade": "Brasileiro",
          "data_nascimento": "1965-07-31"
        },
        {
          "nome": "Autor B"
          "nacionalidade": "desconhecido",
          "data_nascimento": "desconhecido"
          }]
        
        
    
*   _Resposta de sucesso_ (201):
    
        {
          "message": "Autor criado com sucesso."
        }
        
        
    
*   Erros:
    
    *   400: O nome é obrigatório.

### 2\. POST /livros

*   Descrição: Cria um novo livro.
    
*   Corpo da requisição:
    
        [{
          "titulo": "Livro A",
          "genero": "Fantasia",
          "ano": 2020,
          "id_autor": 1
        },
            {
          "titulo": "livro B"
          "genero": "Terror",
          "ano": "2024",
          "id_autor":  null,
        }]
        
        
    
*   _Resposta de sucesso_ (201):
    
        {
          "message": "Livro criado com sucesso."
        }
        
        
    
*   Erros:
    
    *   400: O título é obrigatório.

### 3\. POST /autores/{id}/livros/{id\_livro}

*   Descrição: Associa um livro a um autor.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois os IDs são fornecidos na URL.
    
*   Resposta de sucesso (201):
    
        {
          "message": "Associação criada com sucesso"
        }
        
    
*   _Erros_:
    
    *   _404_: Autor ou livro não encontrado.
    *   _409_: Associação já existe.
    *   _400_: ID inválido.
    *   _404_: Rota não encontrada.

### 4.GET /autores:

*   Descrição: Retorna uma lista de todos os autores.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois o ID é fornecido na URL.
    
*   _Resposta de sucesso_ (200):
    
        [
          {
              "id": 1,
              "nome": "Autor A",
              "nacionalidade": "Brasileiro",
              "data_nascimento": "1965-07-31"
          },
          {
              "id": 2,
              "nome": "Autor B",
              "nacionalidade": "desconhecido",
              "data_nascimento": "desconhecido"
          }
        ]
        
        
    
*   Erros:
    
    *   404: Não existem autores.

### 5.GET /livros:

*   Descrição: Retorna uma lista de todos os livros.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois o ID é fornecido na URL.
    
*   Resposta de sucesso (200):
    
        [
          {
              "id":  1,
              "titulo": "livro A"
              "genero": "Fantasia",
              "ano": "2020",
              "id_autor":  1,
          },
          {
              "id":  1,
              "titulo": "livro B"
              "genero": "Terror",
              "ano": "2024",
              "id_autor":  null,
          }
        ]
        
        
    
*   Erros:
    
    *   404: Não existem livros.

### 6.GET /autores/{id}:

*   Descrição: Retorna as informações de um autor específico baseado no ID específico.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois o ID é fornecido na URL.
    
*   _Resposta de sucesso_ (200):
    
        {
        "id": 1,
        "nome": "Autor A",
        "nacionalidade": "Brasileiro",
        "data_nascimento": "1960-05-14"
        } 
        
    
*   Erros:
    
    *   404: Autor não encontrado.
    *   400: ID inválido

### 7\. GET /livros/{id}:

*   Descrição: Retorna as informações de um livro específico baseado no ID fornecido.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois o ID é fornecido na URL.
    
*   Resposta de sucesso (200):
    
         {
           "id": 1,
           "titulo": "Livro X",
           "genero": "Ficção",
           "ano": "2021",
           "id_autor": 1
           }
        
    
*   _Erros_:
    
    *   _404_: Livro não encontrado.
    *   _400_: ID inválido

### 8\. _GET /autores/{id}/livros_

*   _Descrição_: Retorna todos os livros associados a um autor.
    
*   _Corpo da requisição_: Não é necessário corpo da requisição, pois o ID do autor é fornecido na URL.
    
*   _Resposta de sucesso_ (200):
    
        [
          {
            "titulo": "Livro A",
            "genero": "Fantasia",
            "ano": 2020,
            "id_autor": 1
          },
          {
            "titulo": "Livro B",
            "genero": "Ficção",
            "ano": 2018,
            "id_autor": 1
          }
        ]
        
    
*   Erros:
    
    *   404: Autor não encontrado ou não possui livros associados.
    *   400: ID inválido.
    *   404: Rota não encontrada.

### 9\. PUT /autores/{id}

*   Descrição: Atualiza as informações de um autor existente com base no ID fornecido.
    
*   Corpo da requisição:
    
        {
         "nome": "Autor A atualizado ",
         "nacionalidade": "Brasileiro",
         "data de nascimento": "1965-07-31"
        }
        
    
*   _Resposta de sucesso_ (200):
    
        {
         "message":  "Autor atualizado"
        }
         
        
    
*   Erros:
    
    *   404: Autor não encontrado.
    *   400: ID inválido.

### 10\. PUT /livros/{id}

*   Descrição: Atualiza as informações de um livro existente com base no ID fornecido.
    
*   Corpo da requisição:
    
        {
        "titulo": "Livro A Atualizado",
        "genero": "Fantasia",
        "ano": 2020,
        "id_autor": 1
        }
        
    
*   _Resposta de sucesso_ (200):
    
        {
         "message":  "Livro atualizado"
        }
        
        
    
*   Erros:
    
    *   404: Livro não encontrado.
    *   400: ID inválido.

### 11.DELETE /autores/{id}:

*   Descrição: Remove um autor específico de acordo com o ID fornecido. Caso o autor tenha livros, as referências também serão removidas.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois o ID do autor é fornecido na URL.
    
*   Resposta de sucesso (200):
    
        {
        "message": "Autor removido"
        }
        
    
*   _Erros_:
    
    *   _404_: Autor não encontrado.
    *   _400_: ID inválido.

### 12\. DELETE /livros/{id}:

*   Descrição: Remove um livro específico de acordo com o ID fornecido. As referências a esse livro também serão removidas das associações com autores.
    
*   _Corpo da requisição_: Não é necessário corpo da requisição, pois o ID do autor é fornecido na URL.
    
*   _Resposta de sucesso_ (200):
    
        {
        "message": "Livro removido"
        }
        
    
*   Erros:
    
    *   404: Livro não encontrado.
    *   400: ID inválido.

### 13\. DELETE /autores/{id}/livros/{id\_livro}

*   Descrição: Remove a associação entre um autor e um livro.
    
*   Corpo da requisição: Não é necessário corpo da requisição, pois os IDs são fornecidos na URL.
    
*   Resposta de sucesso (200):
    
        {
          "message": "Associação removida com sucesso"
        }
        
    
*   Erros:
    
    *   404: Associação não encontrada.
    *   400: ID inválido.
    *   404: Rota não encontrada.
