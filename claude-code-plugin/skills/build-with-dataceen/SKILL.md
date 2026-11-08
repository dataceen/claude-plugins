---
description: Use when the person wants a system, backend, database, API or data model for a business or an organisation, or an application on top of one, or mentions Dataceen. Leads them through Dataceen's steps with the dataceen connector, one decision at a time.
---

# Build with Dataceen

Dataceen turns a description of a business into a running system: a semantic model, its databases, a GraphQL
API, MCP servers, SDKs, example data and, if wanted, a hosted application. You work through the `dataceen`
connector. If its tools are not available, tell the person to connect it once (on claude.ai, in the desktop app
or in Cowork: the plugin's Connectors tab, then Connect; in Claude Code: `/mcp`, then dataceen) and stop
there.

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
   with progress.
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

## An input pack

A person may bring an input pack from Dataceen's legacy assessment: a `README.md` across the models and one
`<Model>.md` per model with everything in it. Build the models in the order the README's section 4 gives, and ask
nothing the pack has settled: say what the pack says and go on. Per model:

1. `import_pack` with the model file whole (its text as `content`, or a `url`), as the session's first act, the file read
   and sent as it is, never retyped from memory. When the file is too big for a tool argument, or the session has already
   worked through the material, call `import_pack` with neither: it answers an upload address that takes the file from
   one curl line (in its reply) or a browser, and a pack's next model file goes to the same address. It creates the model from the file's
   Description, adds one source per fenced block of the Sources section with the header line's kind, and the Entities
   and Search sections as one `text` source; its reply lists what landed, what was refused, the images to `add_source`
   from the files beside the model file, and whether the file says the person confirmed the description (if not, show
   it to them before the build). Without `import_pack` the same by hand: `create_model` with the Description, then one
   `add_source` per block with its kind, never the whole file as one text source.
2. `build_model`, then the draft against the Entities table, entity by entity: present under the pack's name, the
   identity, the fixed lists, the links the notes name, what the table says is left out; `update_model` stages every
   difference, `build_model` applies them.
3. `create_system` with `locate` for the entities the Search table marks as located from an address.
4. `generate_example_data` from the Example data section (its Size line as `size`), or none if it says so.
5. One `update_scope` per row of the Scopes table, a restriction where it says only one party's rows, in the table's
   order: the first application's scope first (README section 4 names it) and `publish` at once; the feed's write scope
   waits for the feed-in program and never carries the first application.
6. `build_application` with the first application of README section 4 as the brief, on its scope. The hand-offs of section 3 are
   task applications, after the models they join.

## Why the model matters

The model is the asset: every application, integration and agent added later works on the same data through its
own scope, instead of each keeping its own copy. Say this once, when it helps the person decide, not as a pitch.
