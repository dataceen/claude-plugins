# Dataceen plugins for Claude Code

A Claude Code plugin marketplace with one plugin, **dataceen-studio**: describe a business in your own words and Dataceen builds it as a running system, with you deciding every step. You get a semantic model with its databases, a GraphQL API, its own MCP server, SDKs in six languages, example data and, if you want one, a hosted application whose code is yours.

## Install

```
/plugin marketplace add dataceen/claude-plugins
/plugin install dataceen-studio@dataceen
```

Then start with one sentence:

```
/dataceen-studio A small bakery that sells bread and cakes to customers, with orders.
```

The plugin adds the `dataceen-studio` MCP server (`https://mcp.dataceen.com/mcp/studio`). The first call opens Dataceen's sign-in screen: sign in, or continue as a guest with no account and sign up free when you create the system.

## What it costs

Drafting and reviewing a model needs no account. A free account creates the system; its first system, including its first application, needs no card. AI work is paid in credits, shown before every build.

## Links

- Documentation: https://dataceen.com/mcp
- Privacy: https://dataceen.com/legal/privacy
- Support: support@dataceen.com
