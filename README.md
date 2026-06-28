# FlowProof for n8n

> The **`n8n-nodes-flowproof`** community node — install it from **Settings → Community Nodes**.

[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-8A2BE2)](https://github.com/sponsors/AkuchiS)
[![License](https://img.shields.io/github/license/AkuchiS/n8n-nodes-flowproof?color=8A2BE2)](LICENSE)
[![Last commit](https://img.shields.io/github/last-commit/AkuchiS/n8n-nodes-flowproof?color=8A2BE2)](https://github.com/AkuchiS/n8n-nodes-flowproof/commits)
[![Stars](https://img.shields.io/github/stars/AkuchiS/n8n-nodes-flowproof?color=8A2BE2)](https://github.com/AkuchiS/n8n-nodes-flowproof/stargazers)

**Validate a workflow export imports cleanly — right inside n8n.** Before you ship it to a client, publish it, or trust one you downloaded, FlowProof catches the exact things that break shared templates on import:

- 🔑 **leaked credentials** embedded in the JSON (must never ship)
- 🧩 **missing / community nodes** not installed on the target instance
- ⬆️ **version drift** (a node exported from a newer n8n than the importer runs)
- 🪢 **broken connections** and structural corruption
- ⚠️ **deprecated nodes & parameters**

**Runs entirely inside your n8n. No API, no network, no credentials — your workflows never leave the instance.**

## Install

Self-hosted n8n: **Settings → Community Nodes → Install** → `n8n-nodes-flowproof`.

## Operations

- **Check** — full diagnostic report (`importable`, `fidelity_score`, blockers, manual steps, required community packages, per-issue detail).
- **Verify** — a pass/fail verdict + the blockers, designed to gate a deploy (toggle *Fail Node on NOT-Importable* to stop a run).

## Why trust the verdict

FlowProof's verdicts are arbitrated against a **live n8n import** — in testing against 20 real workflows from 3 sources, the check matched the live importer with **0 mismatches**. This node re-implements that same logic in TypeScript and a CI parity test asserts it agrees with the reference engine on every fixture.

## This node vs FlowProof Pro

This community node is the **free FlowProof check, inside n8n**. The full family:

| | What you get | Where |
|---|---|---|
| **FlowProof for n8n** *(this node)* | **Check** + **Verify** that a workflow imports cleanly, inside n8n. Free. | Settings → Community Nodes |
| **FlowProof CLI** | The same check from your terminal or CI. Free, MIT, Python. | [github.com/AkuchiS/flowproof](https://github.com/AkuchiS/flowproof) |
| **FlowProof Pro** | Goes further: **repairs** the workflow into an import-ready file, a content-hashed *"FlowProof Checked"* **certificate**, and a client-ready **handover**. | [fp.akuchis.com](https://fp.akuchis.com) |

---

<sub>An [AkuchiS](https://github.com/AkuchiS) tool · MIT · more at [github.akuchis.com](https://github.akuchis.com). Private-by-design — runs on your machine; we host nothing and see no data.</sub>
