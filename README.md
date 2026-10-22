# Dataceen plugins for Claude Code

A Claude Code plugin marketplace with one plugin, **dataceen**: describe a business in your own words and Dataceen builds it as a running system, with you deciding every step. You get a semantic model with its databases, a GraphQL API, its own MCP server, SDKs in six languages, example data and, if you want one, a hosted application whose code is yours.

Data first, not AI first. The model is the asset: everything else is generated from it and follows it
when it changes. So many applications and integrations can share the same data: a dashboard, a customer
site, a partner's integration and an AI agent each get their own scope on one model instead of their own
database. AI can now build an app with its own database in ten minutes, and ten such apps mean ten copies
of the customer list drifting apart: the data-quality problem of the near future. Built on one model,
they agree, and the next application costs only the application.

## Install

```
/plugin marketplace add dataceen/claude-plugins
/plugin install dataceen@dataceen
```

Then start with one sentence:

```
/dataceen A small bakery that sells bread and cakes to customers, with orders.
```

The plugin adds the `dataceen` MCP server (`https://mcp.dataceen.com/mcp/studio`), the `build-with-dataceen` skill and the `/dataceen` command; `claude-code-plugin/README.md` says what it connects to and sends. The first call opens Dataceen's sign-in screen: sign in, or continue as a guest with no account and sign up free when you create the system.

## What it costs

Drafting and reviewing a model needs no account. A free account creates the system; its first system, including its first application, needs no card. AI work is paid in credits, shown before every build.

## Links

- Documentation: https://dataceen.com/mcp
- Privacy: https://dataceen.com/legal/privacy
- Support: support@dataceen.com
