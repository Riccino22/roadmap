# 14 — MCP (Model Context Protocol)

Protocolo abierto creado por **Anthropic** que estandariza cómo se exponen tools, recursos y prompts a los LLMs.

## Problema que resuelve

Hoy, si querés que Claude, ChatGPT y Cursor accedan a tu base de Jira, tenés que escribir **tres integraciones distintas**. Con MCP, escribís **un servidor MCP de Jira una vez** y cualquier cliente compatible lo usa.

## Componentes

- **MCP server:** expone tools / resources / prompts. Lo escribís vos o usás uno ya hecho.
- **MCP client:** la app que consume el server (Claude Desktop, Cursor, Claude Code, etc.).
- **Transports:** stdio (local), HTTP+SSE (remoto).

## Servidores oficiales / populares

- Gmail, Google Drive, Google Calendar
- Slack, GitHub, GitLab
- Filesystem, SQLite, Postgres
- Brave Search, Puppeteer

## Por qué importa

- Reusabilidad: una integración, muchos clientes.
- Ecosistema creciendo muy rápido.
- Base para harness engineering serio.

## Ideas para experimentar

- Conectar el server MCP de filesystem a Claude Desktop y pedirle que lea archivos.
- Escribir un MCP server propio que exponga una API privada.
- Ver cómo los tools de un MCP server aparecen en el contexto del modelo.

## Recursos

- [modelcontextprotocol.io](https://modelcontextprotocol.io)
- [SDKs oficiales](https://github.com/modelcontextprotocol) (TypeScript, Python)
