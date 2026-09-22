# AgentObserver

AgentObserver is a counterparty Preflight service for AI agents.

## Official MCP Registry

Registry name:
`io.github.kaattaallaa-sketch/agentobserver`

Status:
**active**

Remote MCP endpoint:
https://icqzbuuix6e4bed2stnnboqcti.srv.us/mcp

Protocol:
MCP 2026-07-28 over Streamable HTTP

Tools:
- `agentobserver_interfaces`
- `agentobserver_targets`
- `agentobserver_status`
- `agentobserver_preflight` — paid via x402

## Other public interfaces

HTTP/x402:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us

A2A Agent Card:
https://spi4fidztufwksb67wbf5dnyii.srv.us/.well-known/agent-card.json

A2A JSON-RPC:
https://spi4fidztufwksb67wbf5dnyii.srv.us/a2a

## Publishing

This repository contains the MCP Registry metadata in `server.json`.

Publishing uses GitHub Actions OIDC with `id-token: write`; no registry PAT is stored in this repository.
