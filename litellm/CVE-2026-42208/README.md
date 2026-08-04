# SQL Injection affecting LiteLLM proxy authentication (CVE-2026-42208)

LiteLLM proxy versions v1.82.0 and earlier fail to properly parameterize token verification queries. A remote unauthenticated attacker can supply crafted API keys containing malicious SQL syntax (such as tautology-based payloads) to bypass authentication checks and interact with protected proxy routes.

## Vulnerable Version

### Setup

Start the vulnerable LiteLLM proxy instance (v1.82.0-stable) and its PostgreSQL database on port 4000:

```sh
docker compose up -d litellm-vuln db
```

## Safe Version

### Setup

Start the patched LiteLLM proxy instance (v1.83.10-stable) and its PostgreSQL database on port 4001:

```sh
docker compose up -d litellm-patched db
```
