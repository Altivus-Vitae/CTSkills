[README.md](https://github.com/user-attachments/files/28762182/README.md)
# Cognitive Thermals — Critical Thinking Skills

Two AI skills that scaffold human reasoning rather than replacing it. Built on the **Altivus Flight Loop** — a five-stage discipline for working through consequential intellectual work — and developed in the Cognitive Thermals essay series((https://substack.com/@altivus/posts)) by Andrew Smith.

---

## What's in this repository

Two skills, one framework. Choose the edition that fits your work; **they are designed to be mutually exclusive**.

### Cognitive Thermals — the parent edition

For **business and strategic work**. Decisions, strategy, analysis, problem framing, debriefing — any consequential, open-ended thinking task. Five stages, eight operating principles, and an offloading checkpoint that names when a request would transfer your own cognitive work to the assistant. Folder: https://github.com/Altivus-Vitae/CTSkills

### Cognitive Thermals: Research Edition

For **postgraduate and professional research**. Same five-stage Flight Loop, tuned for research with a rigour layer the parent does not carry: evidence appraisal, claim–evidence calibration, search discipline, citation integrity, and a structured search brief. Built for MSc and PhD students, early-career and established researchers, with usability preserved for R&D scientists, analysts, and anyone reasoning rigorously from a literature. Folder: [`cognitive-thermals-research/`](./cognitive-thermals-research/)

**Which one?** Pick by your predominant work. Strategic and decision-making → parent. Research, evidence work, academic argument → Research Edition. If both apply at different times, install one, run it in isolation, and load the other only when the task changes.

---

## Best on Claude

These were built as Claude Skills. Claude is the assistant best-tuned to follow scaffolding instructions of this kind — the discipline of pushing back rather than answering, refusing to summarise rather than obliging, surfacing contradictions rather than smoothing them over. The Claude versions deliver the cleanest experience.

For users on other platforms, faithful approximations are provided in each skill's folder. They keep the framework intact, lose some of the rigour and a few capabilities that don't translate (notably the compatibility check, which only Claude can run natively). If the framework matters to you, Claude is where it lives best — the other versions are bridges.

### Install on Claude

Pick the skill you want, then:

1. Download the relevant `.skill` file from the [Releases page](../../releases/latest):
   - `cognitive-thermals.skill` (parent)
   - `cognitive-thermals-research.skill` (Research Edition)
2. In Claude.ai: **Settings → Capabilities** and confirm *Code execution and file creation* is enabled.
3. Go to **Customize → Skills → Upload skill** and select the `.skill` file.
4. Toggle on in your skills list.

After installing, paste the [compatibility check prompt](#first-use-compatibility-check) as your first message in a new chat.

---

## Other platforms

The framework content is portable. What changes is how each platform lets you set persistent instructions and how much instruction text it accepts.

Three versions of the instructions are provided per skill:

| Version | Size | Best for |
|---|---|---|
| `instructions-full.md` | ~17–22K chars | Gemini Gems, Perplexity Spaces, M365 Copilot Agents |
| `instructions-customgpt.md` | ~8K chars | ChatGPT Custom GPTs |
| `instructions-compact.md` | ~1.5K chars | ChatGPT Custom Instructions, Grok, Copilot consumer, any tight space |

### ChatGPT — Custom GPT *(recommended for ChatGPT users)*

A Custom GPT gives you a saved assistant you can launch whenever you want the framework.

1. Open `instructions-customgpt.md` from the skill's folder and copy its contents.
2. In ChatGPT: **Explore GPTs → Create** (top right).
3. Switch to the **Configure** tab.
4. Name: *Cognitive Thermals* or *Cognitive Thermals: Research Edition*. Description: a one-line summary of the framework's purpose.
5. Paste the instructions into the *Instructions* field.
6. Save (keep it private unless you want to share publicly).
7. Launch from your GPT list whenever you want to think through something.

### ChatGPT — Custom Instructions *(fallback)*

If you don't have ChatGPT Plus or prefer not to set up a Custom GPT:

1. Open `instructions-compact.md` from the skill's folder.
2. In ChatGPT: **Settings → Personalization → Custom Instructions**.
3. Paste into the *How would you like ChatGPT to respond?* field.
4. Save.

This sets it as your default behaviour across all chats. The compact version keeps the bones — the five stages, the offloading checkpoint, the key behavioural rules — but loses depth and most of the rigour layer (in the Research Edition). Use it as a starting point; upgrade to the Custom GPT path when you can.

### Google Gemini — Gem

1. Open `instructions-full.md` from the skill's folder.
2. In Gemini: **Gem manager → New Gem**.
3. Name it *Cognitive Thermals* (or Research Edition). Paste the instructions into the *Custom instructions* field.
4. Save. Launch from your Gems list when you want the framework active.

### Perplexity — Space

1. Open `instructions-full.md` from the skill's folder.
2. In Perplexity: **Library → Spaces → Create**.
3. Name it appropriately. Paste the instructions into the *AI Prompt* field.
4. Save. Switch into the Space whenever you want the framework active.

### Microsoft 365 Copilot — Custom Agent

For users with M365 Copilot (the enterprise/paid version):

1. Open `instructions-full.md` from the skill's folder.
2. In M365 Copilot: **Agents → New Agent → Configure**.
3. Name appropriately. Paste the instructions into the agent's instructions field.
4. Save and pin to your agent list.

Consumer Copilot (the free version on Windows and web) has no equivalent feature. For that, use the compact version pasted at the start of each chat.

### Grok

Grok's customisation options are limited compared with the others. The realistic path:

1. Open `instructions-compact.md` from the skill's folder.
2. Paste it as the opening message of a new chat or Workspace session.
3. Begin your actual task in the next message.

### Any other AI assistant

If your platform lets you set a system prompt, custom instructions, or first-message context, pick the version that fits its character limit and follow the same pattern.

---

## First-use compatibility check

Useful only on Claude (where the assistant can actually inspect your other installed skills). On other platforms, skip this — there is no equivalent stack to check.

Paste the appropriate prompt as your first message after installing on Claude.

### For the parent edition (`cognitive-thermals`):

> I've just installed the cognitive-thermals skill — a five-stage scaffold (Calibrate, Commit, Fly, Recalibrate, Recover) that triggers on substantive thinking tasks: decisions, strategy, analysis, problem framing, debriefing, and any prompt like "help me think through X". Its core principle is to scaffold the user's thinking rather than offload it.
>
> Before I use it for real, please run a compatibility check against my other installed skills:
>
> 1. List all skills I currently have enabled.
> 2. For each, identify whether its triggers, instructions, or voice overlap with cognitive-thermals.
> 3. Flag any direct conflicts — skills that would push you in a contradictory direction.
> 4. For each conflict, suggest one of three resolution paths and recommend one: **Isolation** (toggle the conflicting skill off), **Hierarchy** (add a line to my Custom Instructions stating which skill takes precedence), or **Coexistence** (confirm the skills serve different domains).
> 5. Important: if I also have the Cognitive Thermals: Research Edition installed, note that these two editions are designed to be mutually exclusive — recommend isolation between them rather than running both together.
> 6. Recommend a default mode for me given the stack, and one sentence on when I might want to revisit it.

### For the Research Edition (`cognitive-thermals-research`):

> I've just installed the cognitive-thermals-research skill — the Research Edition of the Cognitive Thermals framework, a five-stage critical-inquiry scaffold (Calibrate, Commit, Fly, Recalibrate, Recover) for postgraduate and professional research. Its core principle is to scaffold the researcher's own thinking and enforce academic rigour (evidence appraisal, claim–evidence calibration, citation integrity), not do the research for them.
>
> Before I use it for real, please run a compatibility check against my other installed skills:
>
> 1. List all skills I currently have enabled.
> 2. For each, identify whether its triggers, instructions, or voice overlap with cognitive-thermals-research.
> 3. Flag any direct conflicts — skills that would push you in a contradictory direction.
> 4. For each conflict, suggest one of three resolution paths and recommend one: **Isolation**, **Hierarchy**, or **Coexistence**.
> 5. Important: if I also have the parent Cognitive Thermals skill installed, note that these two editions are designed to be mutually exclusive — recommend isolation between them rather than running both together.
> 6. Recommend a default mode for me given the stack, and one sentence on when I might want to revisit it.

If you're new to Claude Skills and have nothing else installed, the check will return clean and you can begin using the skill immediately.

---

## Mutual exclusivity — why and how

The two editions share architecture but pull in different directions when active simultaneously. The parent assumes the user is reasoning toward a decision they will execute; the Research Edition assumes the user is reasoning toward an argument that will be examined. Both lead to scaffolding behaviour, but the scaffolding language, the prompts, the offloading checkpoint, and the rigour layer differ — and running them together produces interference rather than additive value.

**The recommendation:**

- Most users should install only one. Pick by your predominant work.
- If you do both kinds of work, install both, keep the predominant one toggled on as default, and switch deliberately when the task changes.
- Never run them together in the same conversation. Isolate.

---

## Updates

New versions are published as [Releases](../../releases). Watch this repository (the *Watch* button, top right) to be notified.

When a new version arrives, re-download the version that matches your platform and re-install. The framework itself evolves slowly; updates will typically be refinements rather than overhauls.

---

## Credit and licence

Framework by **Andrew Smith**, founder of **Altivus Vitae Ltd**. The eight operating principles are the foundation of Altivus methodology. The Flight Loop is the framework that organises it. Free to use, modify, and share.

The underlying research, the full essay series, and the broader Altivus work — including how the framework applies to strategic finance, applied neuroscience, and decision-making under consequence — is at [substack.com/@altivus](https://substack.com/@altivus).

Use of these frameworks with any particular AI assistant does not constitute endorsement by that platform.
