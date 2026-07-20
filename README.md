# Cognitive Thermals — Critical Thinking Skills

Two AI skills designed to scaffold human reasoning rather than replace it. Both use the **Altivus Flight Loop**—Calibrate, Commit, Fly, Recalibrate, Recover—and were developed through Andrew Smith's [Cognitive Thermals essay series](https://substack.com/@altivus/posts).

## Choose an edition

The editions share a framework but are designed to run separately.

| Edition | Best for | Location |
|---|---|---|
| **Cognitive Thermals** | Business decisions, strategy, analysis, problem framing and debriefing | This branch |
| **Cognitive Thermals: Research Edition** | Postgraduate and professional research, evidence appraisal, search discipline and citation integrity | [Research Edition branch](https://github.com/Altivus-Vitae/CTSkills/tree/Altivus-Vitae-Cognitive-Thermals--Research-Edition) |

Install the edition that matches the work in front of you. Do not activate both in the same conversation: the parent edition reasons toward accountable action; the Research Edition reasons toward a defensible argument.

## What the skill protects

Cognitive Thermals does not prohibit AI assistance. It makes the transfer of consequential cognitive work visible.

- It asks for the user's initial reading before supplying a frame.
- It separates facts, assumptions and interpretations.
- It stress-tests the question before analysing it.
- It expands the option and evidence set without quietly owning the synthesis.
- It names when judgement, recommendation or reflection is being offloaded.
- It answers factual, mechanical and explicitly delegated tasks directly.

The governing principle is simple: **scaffold the user's thinking; do not silently substitute for it**.

## Native skill packages

The repository supports multiple native skill systems without making one implementation overwrite the others:

| Platform | Implementation | Capability level |
|---|---|---|
| Anthropic Claude | Root `SKILL.md` and release file `cognitive-thermals.skill` | Native Agent Skill |
| ChatGPT desktop / OpenAI Codex | `plugins/cognitive-thermals/` | Native Agent Skill distributed as a Codex plugin |
| GitHub Copilot | `platforms/github-copilot/cognitive-thermals/SKILL.md` | Native Agent Skill |
| Perplexity Computer | `platforms/perplexity/cognitive-thermals/SKILL.md` | Native/custom skill |
| xAI Grok | `platforms/grok/cognitive-thermals/SKILL.md` | Skill Creator import source |
| Microsoft 365 Copilot Chat and Notebooks | `instructions-compact.md` | Prompt-level custom instructions |
| Microsoft 365 Agent Builder / Copilot Studio | `platforms/microsoft-365-copilot/cognitive-thermals/` | Declarative-agent instructions |

The OpenAI package is a native Agent Skill distributed as a plugin. It includes:

```text
plugins/cognitive-thermals/
├── .codex-plugin/plugin.json
└── skills/cognitive-thermals/
    ├── SKILL.md
    └── agents/openai.yaml
```

This gives ChatGPT desktop and Codex the complete workflow rather than the shortened Custom GPT approximation. The skill can be selected explicitly or invoked automatically when a request matches its description. The `agents/openai.yaml` file supplies UI metadata and invocation policy.

## Install on ChatGPT desktop or Codex

Skills are available in the ChatGPT desktop app, Codex CLI and the Codex IDE extension. Plugins distribute those skills to Work mode and Codex in the desktop app.

### Install from this GitHub repository

From a terminal with Codex installed:

```powershell
codex plugin marketplace add Altivus-Vitae/CTSkills
codex plugin add cognitive-thermals@altivus-vitae
```

Restart the ChatGPT desktop app if the plugin does not appear immediately, then begin a new task. In the desktop app, open **Plugins** to enable or disable it. In Codex CLI or the IDE extension, use `/skills` or type `$cognitive-thermals` to invoke it explicitly.

### Install only the skill for local use

If you want the skill without the plugin wrapper, ask Codex:

```text
$skill-installer install https://github.com/Altivus-Vitae/CTSkills/tree/main/plugins/cognitive-thermals/skills/cognitive-thermals
```

Use this route for local experimentation. The plugin route is the recommended distribution path.

### ChatGPT on the web

Plugins are available in Work mode subject to account and workspace availability. A GitHub-hosted marketplace is best installed and tested through Codex or the ChatGPT desktop app. Public listing in the ChatGPT Plugins Directory requires OpenAI's plugin submission and review process.

## Install on GitHub Copilot

GitHub Copilot supports the [open Agent Skills format](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills) in Copilot coding agent, code review, Copilot CLI, the GitHub Copilot app and agent mode in supported IDEs.

Download `platforms/github-copilot/cognitive-thermals/SKILL.md`, then install the complete `cognitive-thermals` folder in one of these locations:

```text
# Project skill — available in one repository
.github/skills/cognitive-thermals/SKILL.md

# Personal skill — available across local projects
~/.copilot/skills/cognitive-thermals/SKILL.md
```

GitHub Copilot also recognises `.agents/skills` locations. Keep only one copy at the intended scope to avoid duplicate discovery. The skill is preferable to an always-on custom agent because it loads conditionally when consequential reasoning is relevant.

## Install on Perplexity Computer

Perplexity Computer accepts a Markdown skill directly and activates it automatically when the `description` matches the task.

1. Download `platforms/perplexity/cognitive-thermals/SKILL.md`.
2. In Perplexity Computer, open **Skills**.
3. Select **Create skill → Upload a skill**.
4. Upload `SKILL.md`.
5. Confirm the name and description, then test it with a consequential decision or strategy question.

If the Research Edition is also installed, keep only one edition active for a given conversation.

## Install on Grok

Grok can create a custom skill from an uploaded file. xAI has not published a separate skill-file schema, so this repository provides a self-contained Markdown import source rather than unsupported platform metadata.

1. Download `platforms/grok/cognitive-thermals/SKILL.md`.
2. In Grok, open **Skills** and choose the Skill Creator or create a new custom skill.
3. Upload the file and ask Grok to create a reusable skill from it without shortening or removing the offloading checkpoint.
4. Review the generated skill instructions before saving.
5. Test it with a consequential decision or strategy question.

If the Research Edition is also installed, activate only one edition for a given conversation.

## Use with Microsoft Copilot

Microsoft has several Copilot layers. They do not use one interchangeable package.

### Microsoft 365 Copilot Chat

Use `instructions-compact.md` in **Copilot settings → Personalization → Custom instructions** as described in [Microsoft's personalization guidance](https://support.microsoft.com/en-us/microsoft-365-copilot/customize-how-microsoft-365-copilot-responds-to-you). This is persistent prompt-level guidance, not a native Agent Skill, so invocation and inspection are less reliable than in Claude, Codex or GitHub Copilot.

### Microsoft 365 Copilot Notebooks

Use `instructions-compact.md` under the notebook's **Copilot instructions**. The framework then applies only within that notebook and is visible to collaborators who can edit it. See [Microsoft's Notebook instructions](https://support.microsoft.com/en-us/Microsoft-365-Copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook).

### Microsoft 365 Agent Builder

Create a declarative agent and copy the three files from `platforms/microsoft-365-copilot/cognitive-thermals/` into the corresponding fields:

- `description.md` → Description
- `instructions.md` → Instructions
- `conversation-starters.md` → Suggested prompts or conversation starters

The dedicated instructions are below [Microsoft's 8,000-character declarative-agent limit](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/declarative-agent-instructions). Do not substitute `instructions-full.md`, and do not store overflow instructions in SharePoint or another knowledge source. Add knowledge only when it supplies evidence relevant to the user's work; it must not replace the behavioural instructions.

### Microsoft Copilot Studio

Use the same description and instructions as the behavioural foundation of a new [Copilot Studio agent](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio). Add knowledge, tools, topics, flows or triggers only when the deployment requires them. Cognitive Thermals should begin as an instruction-led reasoning agent: any action that changes external state should remain explicitly authorised by the user.

Agent availability, organizational sharing, knowledge grounding and consumption depend on Microsoft 365 licensing, tenant policy and Copilot Studio capacity. A future Microsoft 365 Agents Toolkit package would be appropriate for governed tenant or marketplace deployment; it is not required for personal or team use through Agent Builder.

## Install on Claude

The Claude implementation remains unchanged.

1. Download `cognitive-thermals.skill` from the [latest release](../../releases/latest).
2. In Claude.ai, enable **Code execution and file creation** under **Settings → Capabilities**.
3. Go to **Customize → Skills → Upload skill** and select the file.
4. Enable it in the skills list.

Repeat the equivalent steps from the Research Edition branch if that is the edition you need.

## Compatibility fallbacks

The native skill packages are preferred. Prompt-only versions remain for platforms that do not support Agent Skills or plugins.

| File | Use |
|---|---|
| `instructions-full.md` | Full prompt fallback for platforms with sufficiently large instruction fields, including Gemini Gems |
| `instructions-customgpt.md` | Legacy/fallback ChatGPT Custom GPT configuration |
| `instructions-compact.md` | Microsoft 365 Copilot Chat, Copilot Notebooks, tight custom-instruction fields or a first-message prompt |

### ChatGPT Custom GPT fallback

If native skills or plugins are unavailable on your ChatGPT account:

1. Open `instructions-customgpt.md` and copy its contents.
2. In ChatGPT, create a GPT and open its configuration.
3. Paste the text into **Instructions**.
4. Keep the GPT private unless you intend to distribute it separately.

This remains usable, but it does not provide native skill discovery, implicit invocation, plugin metadata or skill-stack inspection.

### Compact fallback

Paste `instructions-compact.md` into a platform's custom-instruction field or as the first message in a new conversation. It preserves the five stages and offloading checkpoint but necessarily loses depth.

## First-use compatibility check

Native Claude, Codex and GitHub Copilot skill environments can inspect relevant enabled or available skills. Ask:

> Run a compatibility check between Cognitive Thermals and my other available skills. Identify trigger, instruction or voice conflicts. For each material conflict, compare Isolation, Hierarchy and Coexistence, recommend one, and confirm that the parent and Research editions should not run together.

Prompt-only environments cannot reliably inspect a native skill stack. In those environments, compare the instruction sets manually.

## Updating

Releases contain stable versions. To update a GitHub-backed Codex marketplace and reinstall the plugin:

```powershell
codex plugin marketplace upgrade altivus-vitae
codex plugin add cognitive-thermals@altivus-vitae
```

Start a new task after reinstalling so the updated skill is loaded cleanly.

## Repository map

```text
.
├── SKILL.md                       # Claude source — do not replace with the Codex copy
├── cognitive-thermals.skill       # Claude release package
├── instructions-full.md           # Cross-platform fallback
├── instructions-customgpt.md      # Custom GPT fallback
├── instructions-compact.md        # Compact fallback
├── platforms/github-copilot/      # GitHub Copilot native Agent Skill
├── platforms/microsoft-365-copilot/ # Agent Builder / Copilot Studio material
├── platforms/perplexity/           # Perplexity Computer upload source
├── platforms/grok/                 # Grok Skill Creator import source
├── .agents/plugins/marketplace.json
└── plugins/cognitive-thermals/    # ChatGPT desktop / Codex plugin
```

## Licence

This repository uses a split-licence structure:

- Source code, scripts, plugin manifests and technical configuration are licensed under the [MIT License](LICENSE-CODE).
- The Cognitive Thermals framework, skill instructions and authored documentation are licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE-CONTENT.md).
- Names, logos and brand identifiers are subject to the separate [branding notice](TRADEMARKS.md).

In practical terms, you may use and adapt the framework—including commercially—provided that you credit Andrew Smith and release adaptations of the licensed framework material under the same CC BY-SA 4.0 terms. See the [licensing overview](LICENSE.md) for the precise file-level scope.

Framework by **Andrew Smith**, founder of **Altivus Vitae Ltd**. The eight operating principles are the foundation of Altivus methodology; the Flight Loop organises them.

The framework, research and wider Altivus work span strategic finance, applied neuroscience and decision-making under consequence. See [Altivus on Substack](https://substack.com/@altivus).

Use with any AI assistant does not constitute endorsement by that platform.
