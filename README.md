# AgentObserver

AgentObserver is an agent health and counterparty Preflight service for AI agents.

Use it when an agent needs to verify the current observable state of another agent or MCP service before relying on it, calling it, or paying it.

## Official MCP Registry

Registry name:
`io.github.kaattaallaa-sketch/agentobserver`

Status:
**active**

Current registry version:
`0.7.2`

Remote MCP endpoint:
https://icqzbuuix6e4bed2stnnboqcti.srv.us/mcp

Protocol:
MCP 2026-07-28 over Streamable HTTP

## MCP tools

Free:
- `agentobserver_interfaces` — discover HTTP/x402, MCP/x402 and A2A surfaces
- `agentobserver_targets` — list enabled Preflight targets
- `agentobserver_status(target)` — check freshness, material changes, expectation mismatches and factual attention reasons

Paid:
- `agentobserver_preflight(target, max_age_seconds=900)` — full x402 Preflight evidence package for 0.05 USDC

The free status tool now exposes fields such as:
- `material_changes_detected`
- `material_change_count`
- `payment_terms_changed`
- `agent_identity_or_transport_changed`
- `agent_capabilities_changed`
- `attention_required_by_observed_facts`
- `attention_reasons`

These are deterministic facts derived from observed state and configured expectations, not a subjective trust score.

## MCP resources

- `agentobserver://interfaces`
- `agentobserver://targets`

## MCP prompts

- `preflight_before_payment(target)`

This prompt guides an agent to check free status first and purchase the full Preflight only when complete evidence is needed.

## Discovery documents

MCP Server Card:
https://icqzbuuix6e4bed2stnnboqcti.srv.us/mcp/server-card

Registry manifest:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/.well-known/mcp.json

AI Catalog:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/.well-known/ai-catalog.json

Agent-readable index:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us/llms.txt

## Other public interfaces

HTTP/x402:
https://oaiy26ruf2tfo2qujrk5f67r7a.srv.us

A2A Agent Card:
https://spi4fidztufwksb67wbf5dnyii.srv.us/.well-known/agent-card.json

A2A JSON-RPC:
https://spi4fidztufwksb67wbf5dnyii.srv.us/a2a

## Target coverage

Production currently exposes one paid Preflight target.

A two-target staging registry has been validated to prove onboarding, baseline capture and multi-target summarization before adding more opt-in production targets.

## Search terms / use cases

AgentObserver is relevant to:
- agent preflight
- agent health check
- verify agent before payment
- MCP service health
- counterparty verification
- x402 payment preflight
- agent drift detection
- freshness and change detection

## Publishing

This repository contains the MCP Registry metadata in `server.json`.

Publishing uses GitHub Actions OIDC with `id-token: write`; no registry PAT is stored in this repository.
