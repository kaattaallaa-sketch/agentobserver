# AgentObserver

AgentObserver is a dependency preflight and pre-spend verification service for AI agents.

Use it when an agent is evaluating an external x402/API dependency and wants factual evidence before committing money or workflow state: endpoint demand, current observable terms, drift/watch state, and a fresh hash-bound Preflight where supported.

## Current coverage

- **10/10** catalog resources have a reviewed GET-only observation surface.
- **7/10** have external endpoint-level demand evidence.
- **4/10** expose a direct x402 challenge and have a canonical paid AgentObserver Preflight product.
- AgentObserver never sends a provider payment signature from free checks or spend-status.

Catalog examples include **Exa Search, BlockRun Chat Completions, OneSource Deepstate Markets, Apify x402, Laevitas, AgentUtility, StableSocial and Cluster Protocol**.

## Start here

Quickstart:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/quickstart

Dependency catalog:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/dependencies

Resolve by capability:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/resolve?capability=web-search

## Direct free checks

These URLs are designed for agents and indexers evaluating a specific dependency.

- Exa Search  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/check/exa/search
- BlockRun Chat Completions  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/check/blockrun/chat-completions
- OneSource Deepstate Markets  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/check/onesource/deepstate-markets
- Apify x402 Prepaid Token  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/check/apify/x402-prepaid-token

The full catalog exposes one direct check URL per dependency.

## Canonical paid x402 products

Each product has its own URL and returns an unsigned x402 V2 payment requirement when called without payment.

- OneSource Deepstate Markets  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/dependency-preflight/onesource/deepstate-markets
- BlockRun Exa Find Similar  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/dependency-preflight/blockrun/exa-find-similar
- Apify x402 Prepaid Token  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/dependency-preflight/apify/x402-prepaid-token
- Laevitas Instruments  
  https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/v1/dependency-preflight/laevitas/instruments

Price: **0.05 USDC on Base**.

These canonical products are registered in x402scan discovery. The generic parameterized route remains available for compatibility but is not the preferred marketplace surface.

## MCP

Official registry name:

`io.github.kaattaallaa-sketch/agentobserver`

Remote MCP endpoint:

https://icqzbuuix6e4bed2stnnboqcti.srv.us/mcp

Primary tools:

- `agentobserver_dependencies` — discover demand-backed dependencies.
- `agentobserver_resolve` — resolve a capability such as web-search, inference or market-data.
- `agentobserver_spend_status` — check a specific dependency before spending; optional safe unsigned live observation.
- `agentobserver_dependency_watch` — read persisted drift/watch state.
- `agentobserver_dependency_preflight` — x402-paid fresh hash-bound report for eligible resources.

Legacy registered-counterparty tools remain available for compatibility but are not the primary product.

## A2A

Agent Card:

https://spi4fidztufwksb67wbf5dnyii.srv.us/.well-known/agent-card.json

JSON-RPC:

https://spi4fidztufwksb67wbf5dnyii.srv.us/a2a

Examples:

- `spend-status exa search`
- `spend-status blockrun chat-completions`
- `watch exa search`
- `dependency-preflight blockrun exa-find-similar`

## Machine-readable discovery

- OpenAPI: https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/openapi.json
- x402 discovery: https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/.well-known/x402
- MCP manifest: https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/.well-known/mcp.json
- MCP Server Card: https://icqzbuuix6e4bed2stnnboqcti.srv.us/mcp/server-card
- AI Catalog: https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/.well-known/ai-catalog.json
- llms.txt: https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/llms.txt

## Evidence semantics

AgentObserver separates:

- external provider-wide context,
- endpoint-specific external demand evidence,
- first-party AgentObserver usage,
- live observable contract/payment conditions,
- paid Preflight evidence.

A missing endpoint-demand match is reported as **unknown**, not zero demand. Catalog inclusion and demand figures are factual observations, not endorsements or trust scores.

## Publishing

MCP Registry metadata lives in `server.json`. Changes to that file trigger the GitHub Actions OIDC publisher; no MCP Registry PAT is stored in this repository.
