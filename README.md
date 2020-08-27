# Desafio de Front-end

Seu desafio para a vaga de desenvolvedor front-end na viralize é criar uma página baseada neste protótipo: [Link do protótipo](https://www.figma.com/proto/q2Sl8JCc3Y87nOvCeNgHJR/Viralize?node-id=840%3A10201&scaling=scale-down-width).

A página deve ser responsiva e ter um layout funcional em tamanhos de tela diferentes. Os dados apresentados na página devem ser consumidos da nossa API de testes que você pode ver logo abaixo.

## Endpoints da API de teste:

A url base da API é https://viralize.online

### `GET` {URL_BASE}/challenge/general

Endpoint para os dados da tela 'Visão Geral'

**Parâmetros:** Nenhum

**Retorno:**

`200`: Ok

Corpo da resposta:
```javascript
{
  "results": [
    {
      "date": String // YYYY-MM-DD,
      "theme": String,
      "created": Number,
      "corrected": Number
    }
  ]
}
```
### `GET` {URL_BASE}/challenge/corrections

Endpoint para os dados da tela 'Correções'

**Parâmetros:**
| Nome  | Tipo                | Obrigatório | Exemplo           |
|-------|---------------------|-------------|-------------------|
| start | String (YYYY-MM-DD) | Não         | ?start=2020-08-01 |
| end   | String (YYYY-MM-DD) | Não         | ?end=2020-08-23   |
| theme | String              | Não         | ?theme=Fitness    |

**Retorno:**

`200`: Ok

Corpo da resposta:
```javascript
{
  "results": [
    {
      "post": Number
      "post_title": String,
      "correction_title": String,
      "theme": String,
      "tag": String,
      "description": String,
      "created_at": String // YYYY-MM-DD
    }
  ]
}
```

`400`: A data está em formato errado ou a data inicial do período é maior que a data final
### `GET` {URL_BASE}/challenge/reports

Endpoint para os dados da tela 'Relatórios'

**Parâmetros:** Nenhum

**Retorno:**

`200`: Ok

Corpo da resposta:
```javascript
{
  "results": [
    {
      "user": String,
      "sector": String,
      "created": Number,
      "corrected": Number
    }
  ]
}
```
