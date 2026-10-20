---
description: Describe a business and let Dataceen build it as a running system, with you deciding every step
argument-hint: <the business, in a sentence or a paragraph, in your own words>
---

Build a Dataceen system for this business with the `dataceen-studio` MCP server. These are my words; use them as the description as they are:

$ARGUMENTS

How to work with me: one question at a time, every choice as a numbered list with the recommended one first; never start a step I have not chosen. Each tool reply ends with Done / Next / You can: tell me those lines first, in my language.

1. `create_model` with a short English name and my text above as the description. If I mention files, specs, schemas or images, `add_source` each one.
2. Show me the sources and ask whether to draft. On my yes, `build_model` (it drafts and creates nothing; minutes, with progress).
3. `get_model`: show me the entities and relationships in plain words and the `graph_url` picture, then ask what to change. Take each change with `add_source` and `build_model` again, as many rounds as I want. A pair of relationships both ways is by design, not a finding.
4. When I say the draft is right, `create_system` (it asks the domain once). As a guest, it gives me the link to sign up and keep the model; the session goes on after that.
5. Ask me one question about the example data (setting, language, size), then `generate_example_data` with my answer.
6. Ask which consumer the first scope is for (an application, a role, an agent), then `update_scope` with only what that consumer needs, and `publish`. Give me the `claude mcp add` line from the reply, so I can ask the scope's own server a question here.
7. If I want an application: `build_application` asks the brief's three questions first; I answer or say "start". Then `get_application` for the address, and `share_repository` with my GitHub username when I want the code.
