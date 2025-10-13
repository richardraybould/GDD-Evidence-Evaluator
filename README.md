# GDD-Evidence-Evaluator
Files and prompts to create an GPT to provide an assessment of GGD evidence. 

# 🧩 Setup Guide — DDaT Evidence Evaluator (HMCTS) GPT

This guide explains how to build the **GDD Evidence Evaluator (HMCTS)** custom GPT from scratch using the provided files.

---

## 1. 📦 Prepare Your Materials

Make sure you have the following three files ready:

| File | Purpose |
|------|----------|
| `DDaT Evidence Evaluator (HMCTS) — Interactive + Logged + CSV Export_prompt.txt` | The main prompt that defines behaviour and workflow. |
| `GDD_Skill_Levels_descriptions.xlsx` | Reference for DDaT skill level definitions. |
| `Senior developer - management_GDD_Description.rtf` | Reference for Software Developer capability descriptors (management focus). |

### ✅ Before You Start
- Confirm each file name is clear and final.
- Decide on your GPT’s **name** and **short description**, for example:
  - **Name:** `GDD Evidence Evaluator (HMCTS)`
  - **Description:** `Evaluates DDaT developer evidence, assigns level, and exports a CSV log.`

---

## 2. 🧠 Create the GPT in the Builder

1. Open the **GPT Builder** (via [chat.openai.com → Explore GPTs → Create a GPT](https://chat.openai.com/gpts)).
2. Choose **Create a GPT**.
3. Fill in:
   - **Name:** `GDD Evidence Evaluator (HMCTS)`
   - **Description:** `Expert assessor for DDaT (Software Developer) evidence. Runs an interactive workflow, produces a Markdown report, and exports a CSV log. Timezone: Europe/London.`

---

## 3. 🧩 Add the Core Instructions

1. In the **Instructions** (system prompt) section, paste the entire contents of  
   `DDaT Evidence Evaluator (HMCTS) — Interactive + Logged + CSV Export_prompt.txt`.
2. At the very top of that file, prepend these key setup lines (if not already included):

   ```text
   You are "GDD Evidence Evaluator (HMCTS)".
   Use Europe/London timezone for all timestamps.
   Always produce:
     • A Markdown evaluation report with timestamp and reviewer
     • A downloadable CSV export file and fenced CSV code block
     • A Per-Capability Rubric Table (10 areas if “All of them” selected)
   Never infer missing data — always collect interactively.

## 4. 📚 Upload Knowledge Files

1. In the GPT Builder, open the **Knowledge** (or **Upload files**) panel.
2. Upload the following files:
   - `GDD_Skill_Levels_descriptions.xlsx`
   - `Senior developer - management_GDD_Description.rtf`
3. In your **Instructions**, add a reminder for the model to use these files:
   > Use the uploaded knowledge files as authoritative references for capability definitions and level descriptors. When drawing on them, align evaluations to these sources.

---

## 5. ⚙️ Enable Tools and Capabilities

Open the **Configure** / **Capabilities** panel and set:

| Capability | Setting | Purpose |
|---|---|---|
| **Web Browsing** | **ON** | Verify evolving DDaT/HMCTS references and cite sources when needed. |
| **Code Interpreter (Python)** | **ON** | Generate timestamped CSV outputs and handle table/report formatting. |
| **File Uploads** | **ON** | Allow large evidence submissions to be evaluated. |

> No external Actions are required — everything runs with standard GPT tools.


