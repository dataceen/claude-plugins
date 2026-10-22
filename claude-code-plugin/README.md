# Dataceen

Describe a business in your own words and Dataceen builds it as a running system, with you deciding every step.
Claude drafts a semantic model from your description: the entities, how they relate and what each holds. You
review it as a picture and change it in conversation. When it is right, Dataceen creates the system from it: a
database per model, a GraphQL API, search, an event stream, documentation, SDKs in six languages and an MCP server
of its own. A scope decides what each consumer sees; each published scope is its own MCP server and API. Fill it
with example data that adds up, and if you want, have Dataceen build and host an application on it: a dashboard,
a full site or a task program. The code is yours in a private GitHub repository.

Data first, not AI first. The model is the asset: everything else is generated from it and follows it when it
changes, so a dashboard, a customer site, a partner's integration and an AI agent each get their own scope on one
model instead of their own database.

## Install

On claude.ai or in Cowork, add it from the directory. In Claude Code:

```
/plugin install dataceen --marketplace dataceen/claude-plugins
```

Then connect it, once: on claude.ai, in the desktop app and in Cowork, open the plugin's **Connectors** tab and
select **Connect**; in Claude Code, run `/mcp`, choose `dataceen` and authenticate. Either way Dataceen's
screen opens: sign in, or continue as a guest with no account. Installing alone signs you in to nothing.

## What the plugin contains

- **The `dataceen` connector**: Dataceen's remote MCP server at `https://mcp.dataceen.com/mcp/studio`
  (streamable HTTP). On claude.ai and in Cowork, connect it from the plugin's Connectors tab.
- **The `build-with-dataceen` skill**: how to lead the person through the steps (one question at a time, the
  person's own words as the description, nothing built before they say so). Claude uses it when the conversation
  is about building a system, a backend or a data model for a business.
- **The `/dataceen` command**: the same flow started from one sentence, for example
  `/dataceen A small bakery that sells bread and cakes to customers, with orders.`

The plugin runs nothing on your computer: no scripts, no hooks, no local server, no packages installed.

## What it connects to and sends

- Everything goes to one server, `mcp.dataceen.com`, run by Dataceen AB (Sweden), over HTTPS. Nothing else is
  contacted by the plugin.
- What is sent is what you give the tools: your description of the business, any text, documents, images or
  schemas you add as sources, and your answers (names, scopes, the example data's setting, an application's
  brief). Dataceen stores the model, the system's data and the call log under your account, or under a guest
  identity until you sign up.
- Dataceen uses Anthropic's Claude to draft models, example data and applications from that material.
- Applications Dataceen builds are hosted under `apps.dataceen.com`; their code goes to a private repository in
  Dataceen's GitHub organisation, which you can be invited to or take over.
- The first connection opens Dataceen's sign-in screen: sign in, or continue as a guest with no account. No
  credential is stored in the plugin.

Privacy policy: https://dataceen.com/legal/privacy

## What it costs

Drafting and reviewing a model needs no account. A free account creates the system; its first system, including
its first application, needs no card. AI work is paid in credits, shown before every build.

## Links

- Documentation: https://dataceen.com/mcp
- Support: support@dataceen.com
- Licence: Apache-2.0 (this plugin's files)
