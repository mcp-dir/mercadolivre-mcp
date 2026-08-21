---
name: mercadolivre-mcp
description: Skill da REST API do Mercado Livre Vendedor na MCP.AI: 14 endpoints em /api/mercadolivre. Mercado Livre (o maior marketplace da América Latina) via API oficial, perfil e reputação do vendedor, anúncios, pedidos, perguntas, envios (Mercado Envios), categorias e visitas, por OAuth 2.0. Somente leitura. Você cria o aplicativo no DevCenter do Mercado Livre e autoriza com OAuth. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Mercado Livre Vendedor — REST API skill

Você tem acesso à **Mercado Livre Vendedor** REST API na MCP.AI.

> Mercado Livre (o maior marketplace da América Latina) via API oficial, perfil e reputação do vendedor, anúncios, pedidos, perguntas, envios (Mercado Envios), categorias e visitas, por OAuth 2.0. Somente leitura. Você cria o aplicativo no DevCenter do Mercado Livre e autoriza com OAuth.

## Base URL

```
https://api.mcp.ai/api/mercadolivre
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/mercadolivre/get/category \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"id":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/mercadolivre/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (14)

#### `mercadolivre_get_category`

Detalha uma categoria por id (GET /categories/{id}): caminho, atributos, settings. _(POST /api/mercadolivre/get/category)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id da categoria (ex.: MLB1234) |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_get_items`

Detalha um ou mais anúncios por id (GET /items?ids=). _(POST /api/mercadolivre/get/items)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `ids` | string[] | Sim | Ids dos anúncios (ex.: MLB123...) |
| `attributes` | string | Não | Campos a retornar, separados por vírgula |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_get_order`

Detalha um pedido por id (GET /orders/{id}): itens, comprador, pagamento, envio. _(POST /api/mercadolivre/get/order)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id do pedido |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_get_question`

Detalha uma pergunta por id (GET /questions/{id}). _(POST /api/mercadolivre/get/question)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id da pergunta |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_get_shipment`

Detalha um envio por id (GET /shipments/{id}): status, rastreio, endereço, custo. _(POST /api/mercadolivre/get/shipment)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id do envio (shipment) |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_get_user`

Detalha um usuário público por id (GET /users/{id}). _(POST /api/mercadolivre/get/user)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id do usuário Mercado Livre |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_item_visits`

Visitas de um anúncio numa janela de tempo (GET /items/{id}/visits/time_window). _(POST /api/mercadolivre/item/visits)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | Id do anúncio |
| `last` | integer | Não | Quantidade de unidades (default 30) |
| `unit` | string | Não | Unidade: day, week ou month (default day) |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercadolivre_list_accounts`

Lista as contas Mercado Livre conectadas a este install — id, label, seller_id. _(POST /api/mercadolivre/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_list_categories`

Lista as categorias raiz de um site (GET /sites/{site}/categories). _(POST /api/mercadolivre/list/categories)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `site` | string | Não | Site ML (default MLB = Brasil) |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_list_items`

Lista os ids dos anúncios do vendedor conectado (GET /users/{seller}/items/search). _(POST /api/mercadolivre/list/items)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offset` | integer | Não | Offset de paginação (default 0) |
| `limit` | integer | Não | Itens por página (máx 50, default 50) |
| `status` | string | Não | Filtro por status: active, paused, closed |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_list_orders`

Lista pedidos do vendedor conectado (GET /orders/search?seller=). _(POST /api/mercadolivre/list/orders)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offset` | integer | Não | Offset de paginação (default 0) |
| `limit` | integer | Não | Itens por página (máx 50, default 50) |
| `status` | string | Não | Filtro order.status (paid, confirmed, cancelled...) |
| `sort` | string | Não | Ordenação: date_asc ou date_desc |
| `q` | string | Não | Busca textual |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_list_questions`

Lista perguntas recebidas pelo vendedor (GET /questions/search?seller_id=). _(POST /api/mercadolivre/list/questions)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offset` | integer | Não | Offset de paginação (default 0) |
| `limit` | integer | Não | Itens por página (máx 50, default 50) |
| `status` | string | Não | Filtro: UNANSWERED, ANSWERED, BANNED... |
| `item` | string | Não | Id do anúncio (filtra perguntas de um item) |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_me`

Dados da conta do vendedor conectado (GET /users/me): perfil, reputação, site, tipo de conta, status de vendedor. _(POST /api/mercadolivre/me)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

#### `mercadolivre_search_items`

Busca anúncios do vendedor já com detalhes (GET /sites/{site}/search?seller_id=). _(POST /api/mercadolivre/search/items)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offset` | integer | Não | Offset de paginação (default 0) |
| `limit` | integer | Não | Itens por página (máx 50, default 50) |
| `site` | string | Não | Site ML (default MLB = Brasil) |
| `q` | string | Não | Texto de busca |
| `category` | string | Não | Id da categoria |
| `account` | string | Não | Quando há múltiplas contas Mercado Livre conectadas: id, label ou seller_id. Veja mercadolivre_list_accounts. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_mercadolivre` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
