---
name: detran_rj_nada_consta-mcp
description: Skill da REST API do DETRAN RJ: Nada Consta na MCP.AI: 1 endpoint em /api/detran_rj_nada_consta. DETRAN RJ: Nada Consta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DETRAN RJ: Nada Consta — REST API skill

Você tem acesso à **DETRAN RJ: Nada Consta** REST API na MCP.AI.

> DETRAN RJ: Nada Consta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/detran_rj_nada_consta
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
curl -X POST https://api.mcp.ai/api/detran_rj_nada_consta/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"renavam":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/detran_rj_nada_consta/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `detran_rj_nada_consta_consultar`

DETRAN RJ: Nada Consta, consulta em fonte oficial. _(POST /api/detran_rj_nada_consta/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `renavam` | string | Sim | Parâmetro de consulta "renavam". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_detran_rj_nada_consta` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
