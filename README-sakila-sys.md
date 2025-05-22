
# Sakila System API

A **Sakila System API** permite o gerenciamento de informações de filmes, atores e clientes baseado no banco de dados Sakila do MySQL.  
Ela fornece endpoints REST para consulta, criação, atualização e exclusão desses dados.

---

## 🔐 Autenticação

A API utiliza **Client ID Enforcement** para controle de acesso.  
Inclua os seguintes headers em todas as requisições:

```http
client_id: seu-client-id
client_secret: seu-client-secret
Content-Type: application/json
```

---

## 📦 Formato das Respostas

Todas as respostas são no formato `application/json`.

### Exemplo de erro:
```json
{
  "error": "Recurso não encontrado",
  "code": 404
}
```

---

## 📃 Paginação e Filtros

A API suporta filtros e paginação em determinados recursos (ex: `/films`, `/customers`), usando parâmetros como `limit`, `offset` e `name`.

### Exemplo:
```http
GET /films?limit=10&offset=0&title=academy
```

---

## 🔧 Como testar a API

Você pode utilizar **Postman**, **Insomnia** ou o **API Console da Anypoint Platform**.

### Exemplo de GET:
```http
GET https://api.evermind.com/sakila-sys/v1/films
```

### Exemplo de POST:
```http
POST /actors
Content-Type: application/json

{
  "first_name": "Tom",
  "last_name": "Hanks"
}
```

---

## ✅ Boas Práticas

- Sempre envie os **headers obrigatórios**.
- Use filtros para melhorar performance e usabilidade.
- Trate os principais códigos de resposta:
  - `200` – Sucesso
  - `201` – Criado
  - `400` – Erro de validação
  - `404` – Recurso não encontrado
  - `500` – Erro interno

---

## 📌 Recursos Disponíveis

- `/films` – Gerenciamento de filmes
- `/customers` – Gerenciamento de clientes
- `/actors` – Gerenciamento de atores

---

## 🧑‍💻 Suporte

Para dúvidas, melhorias ou bugs, entre em contato com a equipe responsável pela API.
