# Cognitive Thermals: Research Edition

A critical-inquiry skill designed to protect the researcher's reasoning rather than replace it. It uses the **Altivus Flight Loop**—Calibrate, Commit, Fly, Recalibrate, Recover—and adds a research-specific rigour layer: evidence appraisal, claim–evidence calibration, structured search discipline and citation integrity.

The framework was developed by Andrew Smith through the [Cognitive Thermals essay series](https://substack.com/@altivus/posts).

## Choose the right edition

The two editions share an architecture but are designed to run separately.

| Edition | Best for | Location |
|---|---|---|
| **Cognitive Thermals** | Business decisions, strategy, analysis, problem framing and debriefing | [Parent edition](https://github.com/Altivus-Vitae/CTSkills) |
| **Cognitive Thermals: Research Edition** | Postgraduate and professional research, literature work, evidence appraisal and academic argument | This branch |

Do not activate both in the same conversation. The parent edition reasons toward accountable action; the Research Edition reasons toward a defensible argument.

## What the Research Edition protects

The skill distinguishes legitimate assistance from the silent transfer of work that the researcher must own.

- It asks for the researcher's initial reading before supplying a field map.
- It surfaces prior beliefs, hoped-for findings and confirmation-bias risk.
- It tests whether a question is feasible, answerable and appropriately framed.
- It distinguishes exploratory from confirmatory reasoning.
- It issues structured search briefs that deliberately include disconfirming evidence.
- It calibrates the strength of claims to the quality and design of the evidence.
- It refuses to invent references, findings, authors, journals or identifiers.
- It applies a stronger checkpoint before producing assessed or submitted work.

The governing principle is: **scaffold the researcher's thinking; do not silently substitute for it; never let rigour slip**.

## The assessed-work boundary

When a request would transfer synthesis, argument, critical appraisal, interpretation or conclusion, the skill first determines whether the work is assessed or submitted.

- **Assessed or submitted work:** it names the offload, explains what the researcher must own, offers a concrete scaffolded alternative and waits for an explicit choice.
- **Unassessed work:** it names the transfer once and proceeds if the user still wants direct production.
- **Mechanical or factual work:** it answers directly without manufacturing friction.

This is not a blanket refusal system. It makes authorship and accountability visible at the point where they matter.

## Native skill packages

The repository supports multiple native skill systems without making one implementation overwrite the others:

| Platform | Native package |
|---|---|
| Claude | Root `SKILL.md` and `cognitive-thermals-research.skill` |
| ChatGPT desktop / Codex | `plugins/cognitive-thermals-research/` |
| Perplexity Computer | `platforms/perplexity/cognitive-thermals-research/SKILL.md` |
| Grok | `platforms/grok/cognitive-thermals-research/SKILL.md` |

The OpenAI package is a native Agent Skill distributed as a plugin:

```text
plugins/cognitive-thermals-research/
├── .codex-plugin/plugin.json
└── skills/cognitive-thermals-research/
    ├── SKILL.md
    └── agents/openai.yaml
```

This gives ChatGPT desktop and Codex the complete research workflow rather than the shortened Custom GPT approximation. The skill can be selected explicitly or invoked automatically when a request matches its research-specific description.

## Install on ChatGPT desktop or Codex

### Install this branch as a plugin marketplace

From a terminal with Codex installed:

```powershell
codex plugin marketplace add Altivus-Vitae/CTSkills --ref Altivus-Vitae-Cognitive-Thermals--Research-Edition
codex plugin add cognitive-thermals-research@altivus-vitae-research
```

Restart the ChatGPT desktop app if the plugin does not appear immediately, then begin a new task. In the desktop app, open **Plugins** to enable or disable it. In Codex CLI or the IDE extension, use `/skills` or type `$cognitive-thermals-research` to invoke it explicitly.

### Install only the skill for local use

If you want the native skill without the plugin wrapper, ask Codex:

```text
$skill-installer install https://github.com/Altivus-Vitae/CTSkills/tree/Altivus-Vitae-Cognitive-Thermals--Research-Edition/plugins/cognitive-thermals-research/skills/cognitive-thermals-research
```

Use this route for local experimentation. The plugin route is the recommended distribution path.

### ChatGPT on the web

Plugins are available in Work mode subject to account and workspace availability. A GitHub-hosted marketplace is best installed and tested through Codex or the ChatGPT desktop app. Public listing in the ChatGPT Plugins Directory requires OpenAI's plugin submission and review process.

## Install on Perplexity Computer

Perplexity Computer accepts a Markdown skill directly and activates it automatically when the `description` matches a research task.

1. Download `platforms/perplexity/cognitive-thermals-research/SKILL.md`.
2. In Perplexity Computer, open **Skills**.
3. Select **Create skill → Upload a skill**.
4. Upload `SKILL.md`.
5. Confirm the name and description, then test it with a research question, evidence-appraisal task or literature-review problem.

Do not run it alongside the parent Cognitive Thermals edition in the same conversation.

## Install on Grok

Grok can create a custom skill from an uploaded file. xAI has not published a separate skill-file schema, so this repository provides a self-contained Markdown import source rather than unsupported platform metadata.

1. Download `platforms/grok/cognitive-thermals-research/SKILL.md`.
2. In Grok, open **Skills** and choose the Skill Creator or create a new custom skill.
3. Upload the file and ask Grok to create a reusable skill without shortening the assessed-work checkpoint, structured search brief or citation-integrity rules.
4. Review the generated skill instructions before saving.
5. Test it with a research question or evidence-appraisal task.

Do not run it alongside the parent Cognitive Thermals edition in the same conversation.

## Install on Claude

The Claude implementation remains unchanged.

1. Download `cognitive-thermals-research.skill` from the [latest release](../../releases/latest).
2. In Claude.ai, enable **Code execution and file creation** under **Settings → Capabilities**.
3. Go to **Customize → Skills → Upload skill** and select the file.
4. Enable it in the skills list.

## Compatibility fallbacks

The native skill packages are preferred. Prompt-only versions remain for platforms that do not support Agent Skills or plugins.

| File | Use |
|---|---|
| `instructions-full.md` | Gemini Gems and M365 Copilot Agents |
| `instructions-customgpt.md` | Legacy/fallback ChatGPT Custom GPT configuration |
| `instructions-compact.md` | Tight custom-instruction fields or a first-message prompt |

The prompt-only versions remain usable but do not provide native skill discovery, implicit invocation, plugin metadata or skill-stack inspection.

## First-use compatibility check

Native Claude and Codex skill environments can inspect relevant enabled or available skills. Ask:

> Run a compatibility check between Cognitive Thermals: Research Edition and my other available skills. Identify trigger, instruction or voice conflicts. For each material conflict, compare Isolation, Hierarchy and Coexistence, recommend one, and confirm that the parent and Research editions should not run together.

Prompt-only environments cannot reliably inspect a native skill stack. In those environments, compare the instruction sets manually.

## Updating

To update this GitHub-backed marketplace and reinstall the plugin:

```powershell
codex plugin marketplace upgrade altivus-vitae-research
codex plugin add cognitive-thermals-research@altivus-vitae-research
```

Start a new task after reinstalling so the updated skill is loaded cleanly.

## Repository map

```text
.
├── SKILL.md                            # Claude source — unchanged
├── cognitive-thermals-research.skill   # Claude release package
├── instructions-full.md                # Cross-platform fallback
├── instructions-customgpt.md           # Custom GPT fallback
├── instructions-compact.md             # Compact fallback
├── platforms/perplexity/                # Perplexity Computer upload source
├── platforms/grok/                      # Grok Skill Creator import source
├── .agents/plugins/marketplace.json
└── plugins/cognitive-thermals-research/ # ChatGPT desktop / Codex plugin
```

## Licence

This repository uses a split-licence structure:

- Source code, scripts, plugin manifests and technical configuration are licensed under the [MIT License](LICENSE-CODE).
- The Cognitive Thermals framework, skill instructions and authored documentation are licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE-CONTENT.md).
- Names, logos and brand identifiers are subject to the separate [branding notice](TRADEMARKS.md).

You may use and adapt the framework—including commercially—provided that you credit Andrew Smith and release adaptations of the licensed framework material under the same CC BY-SA 4.0 terms. See the [licensing overview](LICENSE.md) for the precise file-level scope.

Research Edition by **Andrew Smith**, founder of **Altivus Vitae Ltd** and MSc Applied Neuroscience candidate at King's College London.

For the underlying research and wider Altivus work, see [Altivus on Substack](https://substack.com/@altivus).

Use with any AI assistant does not constitute endorsement by that platform.
