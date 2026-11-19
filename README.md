# ANODHAS Business Hub for Codex

A local Codex plugin that connects an existing ANODHAS Business Hub installation on macOS over MCP (stdio). It exposes 24 tools across six business modules, including pricing, discounts, supplier comparison, cash forecasts, delivery planning, and order drafts.

This repository contains the marketplace manifest, plugin manifest, and launcher. Running the plugin requires the separately installed ANODHAS Business Hub preproduction runtime. The launcher uses the existing local SQLite database and Obsidian preproduction cards.

## Install

From the root of a local clone:

```sh
codex plugin marketplace add "$PWD"
codex plugin add business-hub@anodhas-local
```

Then open a new Codex chat. The MCP server is named `anodhas_business_core`. On an installation that already registers this server manually, back up the original configuration before replacing that registration with the plugin.

The launcher expects the hub runtime under `~/Library/Application Support/ANODHAS/BusinessHub-Preproduction`. The default cards directory is under `~/Documents/Obsidian/Codex-Operational-Vault/20_Operational/Производственный бизнес/Предпродакшен`. To use a different preproduction layout, adjust the launcher before installing from your local copy.

## Verified on macOS

A clean Codex session discovered the installed MCP server, read a saved calculation draft, and ran a fresh discount calculation. MCP discovery returned 24 tools. Goods receipt and payment reconciliation were separately exercised in preproduction using synthetic evidence documents. The payment workflow records evidence of a completed payment.

[Portfolio case study in Russian](PORTFOLIO.md)

The plugin source is available under the [MIT License](LICENSE).
