# Mercado Livre Vendedor

### Mercado Livre Vendedor para Claude, ChatGPT e agentes de IA

Mercado Livre (o maior marketplace da América Latina) via API oficial, perfil e reputação do vendedor, anúncios, pedidos, perguntas, envios (Mercado Envios), categorias e visitas, por OAuth 2.0. Somente leitura. Você cria o aplicativo no DevCenter do Mercado Livre e autoriza com OAuth.

- 📊 **14 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Mercado Livre Vendedor` e **URL** `https://api.mcp.ai/p_mercadolivre`.

### Cursor

[➕ Instalar Mercado Livre Vendedor no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=mercadolivre&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tZXJjYWRvbGl2cmUifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Mercado Livre Vendedor no VS Code](vscode:mcp/install?name=mercadolivre&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_mercadolivre%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_mercadolivre
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Liste meus pedidos pagos dos últimos 7 dias
Quais perguntas dos meus anúncios estão sem resposta?
Mostre as visitas do anúncio MLB... nos últimos 30 dias
```

---

## 14 ferramentas disponíveis

| Tool | Descrição |
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

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Mercado Livre, o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_mercadolivre`.


---

## Suporte

- 📧 [mercadolivre@mcp.ai](mailto:mercadolivre@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/mercadolivre-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_mercadolivre` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
