# Agent entry: ama-mobstack

1. This repository is **public**. Assume everything you write here is read by anyone.
2. Never add private agent canon, founder workflows, mentor data, client material, secrets or credentials.
3. Do not redefine the MobStack standard; reference `MajorDream444/Mobstack`.
4. Mark anything unbuilt as proposed. Do not claim features, payments or integrations work unless a test here shows it.
5. Changes go through pull requests with a description of what was tested.

**Walk Test:** a fresh agent should be able to say what this repo is for, what must never be committed here, and that it has no runnable code yet.

## Build with Hanzo (HIPs)

HAMAL is part of the Hanzo ecosystem. Before building anything, check the Hanzo Improvement Proposals at https://hips.hanzo.ai and build on the standard that already covers it. Prefer **Final** HIPs; a **Draft** may change. Some HIP numbers appear twice in the listing, so cite a HIP by number **and** title.

Read first: HIP-0119 Service Conventions, HIP-0130 Open-Core Split, HIP-0134 One Process, One Socket, One Identity, HIP-0139 Capability.

| Need | Build on |
| --- | --- |
| Knowledge and memory | HIP-1260 Knowledge (Final); HIP-0522 Context Graph; HIP-0526 Semantic Memory |
| Decisions and verdicts | HIP-1332 Kai (Draft); HIP-0129 Eval (Final) for scoring |
| Tools agents call | HIP-1213 Tool Plane; HIP-0010 / HIP-0300 MCP; HIP-0120 Zap. Expose tools over both MCP and Zap |
| Agents | HIP-1210 Agents; HIP-0009 Agent SDK |
| Skills | HIP-1322 Skills catalogue |
| Identity and permissions | HIP-0111 IAM; HIP-1041 Authz; HIP-1340 Principal |
| Marketplace and payment | HIP-1137 Marketplace; HIP-1335 Listings (Draft); HIP-1163 x402; HIP-1000 Author royalty |
| Tenancy | HIP-0118 Tenant isolation; HIP-0521 Org hierarchy |
| Learning | Hanzo University (white-labelled); HIP-1349 Sensei; HIP-1402 XP |

Do not rebuild what a Final HIP already covers. If nothing covers it, say so in the pull request.

## ICM: how this workspace is organized

This repository follows the Interpretable Context Methodology (ICM): the folder structure *is* the agent architecture.

ICM was created by Jake Van Clief and David McDermott ("Interpretable Context Methodology: Folder Structure as Agentic Architecture", arXiv:2603.16021, 2026), and is open source under the MIT license: https://github.com/RinDig/Interpretable-Context-Methodology-ICM. HAMAL applies ICM to its agents; credit the authors when describing it.

- **Entry:** this `AGENTS.md` is the root. `CLAUDE.md` only points here.
- **Three primitives:** *sequence* (numbered folders, e.g. `01_inputs/`, run in order, each step's output is the next step's input), *shelf* (unnumbered folders of same-shaped files, e.g. `templates/`), and *catalog* (short index files such as `INDEX.md` that point into folders so agents load only what they need).
- **Every file is one of:** Catalog, Contract (schemas, rules), Factory (prompts, scripts that transform inputs), Product (finished outputs), or Dead (prune or archive it).
- **Stepwise checks:** every sequence step ends with a check (a script, a small model, or a human) before the next step runs.
- **Walk Test:** a fresh agent with no prior memory must be able to read this file, navigate the folders, do its task, and report status from local files alone. Any change must keep the Walk Test passing.
- **Vendor-neutral:** plain Markdown and schemas, readable by any model.
