# DataForSEO resources

Reference material for working on OpenSEO's DataForSEO client in `src/server/lib/dataforseo/`. For account and API key setup, see [`DATAFORSEO_API_KEY.md`](./DATAFORSEO_API_KEY.md).

## Official docs

- [API v3 docs](https://docs.dataforseo.com/v3/): the reference for every endpoint, parameter and response.
- [Machine-readable doc index](https://docs.dataforseo.com/v3.md): markdown, handy to give to an agent.
- [v3 migration guide](https://docs.dataforseo.com/v3/migration_guide_v3/).
- The docs site also has a Kickstart guide, an API Playground for testing calls, and a free trial.

## Official GitHub

- [dataforseo/TypeScriptClient](https://github.com/dataforseo/TypeScriptClient) (npm `dataforseo-client`): generated from their OpenAPI YAML. Use it as a reference for exact request and response types. Do not add it as a dependency: `vite-plugin-lean-worker-bundle.ts` denylists it because it raises worker startup memory.
- [dataforseo/mcp-server-typescript](https://github.com/dataforseo/mcp-server-typescript): the official MCP server. Compare its tool coverage and schemas against OpenSEO's MCP tools to find endpoints we don't expose yet.
- Python, PHP and C# clients and Postman collections are linked from the docs.

## Verifying our client

1. Check hand-written request and response shapes against the TypeScriptClient types.
2. Check Appendix error codes and rate limits against `envelope.ts` and the retry logic.
3. Check endpoint coverage against the official MCP server.
