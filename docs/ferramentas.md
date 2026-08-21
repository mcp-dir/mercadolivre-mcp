# Ferramentas

Mercado Livre Vendedor expõe 14 ferramentas (todas somente leitura).

### 1. `mercadolivre_list_accounts`
**Input**: `account` (opcional)

Lista as contas Mercado Livre conectadas a este install — id, label, seller_id.

### 2. `mercadolivre_me`
**Input**: `account` (opcional)

Dados da conta do vendedor conectado (GET /users/me): perfil, reputação, site, tipo de conta, status de vendedor.

### 3. `mercadolivre_get_user`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um usuário público por id (GET /users/{id}).

### 4. `mercadolivre_list_items`
**Input**: `offset` (opcional), `limit` (opcional), `status` (opcional), `account` (opcional)

Lista os ids dos anúncios do vendedor conectado (GET /users/{seller}/items/search).

### 5. `mercadolivre_get_items`
**Input**: `ids`, `attributes` (opcional), `account` (opcional)

Detalha um ou mais anúncios por id (GET /items?ids=).

### 6. `mercadolivre_search_items`
**Input**: `offset` (opcional), `limit` (opcional), `site` (opcional), `q` (opcional), `category` (opcional), `account` (opcional)

Busca anúncios do vendedor já com detalhes (GET /sites/{site}/search?seller_id=).

### 7. `mercadolivre_list_orders`
**Input**: `offset` (opcional), `limit` (opcional), `status` (opcional), `sort` (opcional), `q` (opcional), `account` (opcional)

Lista pedidos do vendedor conectado (GET /orders/search?seller=).

### 8. `mercadolivre_get_order`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um pedido por id (GET /orders/{id}): itens, comprador, pagamento, envio.

### 9. `mercadolivre_list_questions`
**Input**: `offset` (opcional), `limit` (opcional), `status` (opcional), `item` (opcional), `account` (opcional)

Lista perguntas recebidas pelo vendedor (GET /questions/search?seller_id=).

### 10. `mercadolivre_get_question`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha uma pergunta por id (GET /questions/{id}).

### 11. `mercadolivre_get_shipment`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um envio por id (GET /shipments/{id}): status, rastreio, endereço, custo.

### 12. `mercadolivre_list_categories`
**Input**: `site` (opcional), `account` (opcional)

Lista as categorias raiz de um site (GET /sites/{site}/categories).

### 13. `mercadolivre_get_category`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha uma categoria por id (GET /categories/{id}): caminho, atributos, settings.

### 14. `mercadolivre_item_visits`
**Input**: `id`, `last` (opcional), `unit` (opcional), `account` (opcional), `ids` (opcional)

Visitas de um anúncio numa janela de tempo (GET /items/{id}/visits/time_window).

## Prompts de exemplo

```
Liste meus pedidos pagos dos últimos 7 dias
Quais perguntas dos meus anúncios estão sem resposta?
Mostre as visitas do anúncio MLB... nos últimos 30 dias
```
