# Mercado Livre Vendedor

### Mercado Livre Vendedor for Claude, ChatGPT and AI agents

Mercado Livre (Latin America's largest marketplace) via the official API, seller profile and reputation, listings, orders, questions, shipping (Mercado Envios), categories and visits, over OAuth 2.0. Read-only. You create the app in the Mercado Livre DevCenter and authorize via OAuth.

- 📊 **14 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Mercado Livre Vendedor`, URL `https://api.mcp.ai/p_mercadolivre`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=mercadolivre&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tZXJjYWRvbGl2cmUifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=mercadolivre&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_mercadolivre%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_mercadolivre
```

---

## 14 tools

| Tool | Description |
|---|---|
| `mercadolivre_list_accounts` | Lista as contas Mercado Livre conectadas a este install — id, label, seller_id. |
| `mercadolivre_me` | Dados da conta do vendedor conectado (GET /users/me): perfil, reputação, site, tipo de conta, status de vendedor. |
| `mercadolivre_get_user` | Detalha um usuário público por id (GET /users/{id}). |
| `mercadolivre_list_items` | Lista os ids dos anúncios do vendedor conectado (GET /users/{seller}/items/search). |
| `mercadolivre_get_items` | Detalha um ou mais anúncios por id (GET /items?ids=). |
| `mercadolivre_search_items` | Busca anúncios do vendedor já com detalhes (GET /sites/{site}/search?seller_id=). |
| `mercadolivre_list_orders` | Lista pedidos do vendedor conectado (GET /orders/search?seller=). |
| `mercadolivre_get_order` | Detalha um pedido por id (GET /orders/{id}): itens, comprador, pagamento, envio. |
| `mercadolivre_list_questions` | Lista perguntas recebidas pelo vendedor (GET /questions/search?seller_id=). |
| `mercadolivre_get_question` | Detalha uma pergunta por id (GET /questions/{id}). |
| `mercadolivre_get_shipment` | Detalha um envio por id (GET /shipments/{id}): status, rastreio, endereço, custo. |
| `mercadolivre_list_categories` | Lista as categorias raiz de um site (GET /sites/{site}/categories). |
| `mercadolivre_get_category` | Detalha uma categoria por id (GET /categories/{id}): caminho, atributos, settings. |
| `mercadolivre_item_visits` | Visitas de um anúncio numa janela de tempo (GET /items/{id}/visits/time_window). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_mercadolivre` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
