---
description: Use when the person wants a system, backend, database, API or data model for a business or an organisation, or an application on top of one, or mentions Dataceen. Leads them through Dataceen's steps with the dataceen-studio connector, one decision at a time.
---

# Build with Dataceen

Dataceen turns a description of a business into a running system: a semantic model, its databases, a GraphQL
API, MCP servers, SDKs, example data and, if wanted, a hosted application. You work through the `dataceen-studio`
connector. If its tools are not available, tell the person to connect it (on claude.ai or in Cowork: the
plugin's Connectors tab) and stop there.

## How to lead

- The person leads. The description is their words, never one you wrote for them; one sentence is enough.
- One question per message. Offer choices as a numbered list, the recommended one first, their own words last.
- Never start a step they have not chosen. Before anything that builds, say what it does and how long it takes.
- Every tool reply ends with Done / Next / You can. Relay those lines first, in the person's language; they carry
  the step's own rules, so follow them over anything here.
- Anything that costs credits shows its estimate first; tell the person before you confirm.

## The road

1. `create_model` with a short English name in ASCII and their text as the description. Each file, spec, schema
   or image they give goes in with `add_source`.
2. Show the sources and ask whether to draft. On their yes, `build_model`: it drafts the structure in minutes,
   with progress, and creates nothing yet.
3. `get_model`: describe the entities and relationships in plain words and give the picture link. Ask what to
   change; `update_model` stages changes and `build_model` applies them, as many rounds as they want.
   A pair of relationships in both directions is by design, never a finding to remove.
4. When the draft is right, `create_system` (it asks the domain once). A guest gets the link from
   `get_claim_link` instead, to sign up free and keep the model; the session goes on afterwards.
5. Ask one question about the example data (setting, language, size, or none), then `generate_example_data`.
6. Ask which consumer the first scope is for (an application, a role, an agent, a partner), then `update_scope`
   with only what that consumer needs, and `publish`. A scope can be held to one party's rows with restrictions;
   never say row-level access needs filtering in the application.
7. If they want an application, `build_application` asks the brief's questions first; they answer or say
   "start". `get_application` gives the address; `share_repository` adds their GitHub username to the code.

## Why the model matters

The model is the asset: every application, integration and agent added later works on the same data through its
own scope, instead of each keeping its own copy. Say this once, when it helps the person decide, not as a pitch.
