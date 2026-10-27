# Copilot Notebooks — Participant Guide
### One workspace, all your files, no re-attaching
**Bajaj Finance Limited | M365 Copilot Training — Payments (Sales), Field**
**Files used:** `PaymentsSales_Copilot_Demo.xlsx`, `PaymentsSales_Copilot_Dataset.xlsx`, `Merchant_Offer_and_FAQ_Sheet.pdf`, and the guides in this repo

---

## Why Notebooks?

In a normal Copilot Chat, every new conversation starts from zero. You attach the file again, explain your role again and restate the format you want. You are also limited to **3 attachments per prompt**.

A **Copilot Notebook** is a saved workspace for one piece of work. You add your files to it once, as **references**, and write your standing instructions once. Every chat you start inside the notebook then uses those references, across days. That includes on your phone, because notebooks open in the M365 Copilot app too.

| | Regular Copilot Chat | Copilot Notebook |
|---|---|---|
| Files | Attached per prompt (max **3** in BFL) | Added once as **references** |
| Context | Lost when you open a new chat | Kept in the notebook across chats and days |
| Instructions (role, tone, format) | Re-typed every time | Set once in **Copilot instructions** |
| Grounding | Your prompt + attachments (+ wider M365 / web, depending on settings) | **Only** your references, so answers stay on your files |

> 💡 **Rule of thumb:** one notebook per piece of work, for example "My beat — October" or "Team review — Q3". Don't create a new notebook for every question.

---

## ⭐ Going Beyond the 3-Attachment Limit

- The 3-file limit applies to **attachments in a chat prompt**.
- Notebook **references** are added through *Add references*, not the chat box, and Copilot uses **all** of them together.
- According to Microsoft's documentation:
  - **Copilot Chat** users can add up to **50 references**.
  - **Microsoft 365 Copilot** users can add more than 300 references, and the first **300** are used.
- A **OneDrive folder** can be one reference. Anything you add to the folder later becomes available automatically.

> ⚠️ **Check in your own tenant:** if notebook references also seem capped, tell your trainer or IT. Exercise 2 is a quick test.

---

## Before You Begin

- [ ] You can open the **M365 Copilot** app (laptop or phone) with your BFL work account and see **Notebooks**.
- [ ] You have copied this repo's files to a OneDrive folder such as `OneDrive › Copilot-Training-PaymentsSales`.
- [ ] You have made `.txt` copies of three Markdown guides. Notebooks do **not** accept `.md`:

| Original in repo | Rename to |
|---|---|
| `MetaPrompting_Guide.md` | `MetaPrompting_Guide.txt` |
| `Participant_Guide.md` | `Participant_Guide.txt` |
| `Excel_To_PowerPoint.md` | `Excel_To_PowerPoint.txt` |

Your folder should now hold **6 files**:

```
Copilot-Training-PaymentsSales/
├── PaymentsSales_Copilot_Demo.xlsx          (25 merchants, as of 30 Sep 2026)
├── PaymentsSales_Copilot_Dataset.xlsx       (Read Me, Merchant Lead Pipeline, Activation & Usage,
│                                                 Field Visit Log, FOS Performance, Merchant Queries)
├── Merchant_Offer_and_FAQ_Sheet.pdf             (offer sheet & FAQ — training sample)
├── MetaPrompting_Guide.txt
├── Participant_Guide.txt
└── Excel_To_PowerPoint.txt
```

---

# Exercise 1 — Create Your Notebook
**Time:** ~5 minutes

1. In the M365 Copilot app, select **Notebooks** → **New notebook**, and name it `Payments Sales — West Cluster, Oct 2026`.
2. Select **Add references** and add either all 6 files or the whole **folder** (recommended).
3. Open **Copilot instructions** and paste:

```
I work in Payments field sales at Bajaj Finance Limited, signing up and activating merchants for
UPI QR, QR + Soundbox, Android POS and Payment Links. West cluster: Pune West, Pune East,
Mumbai Andheri, Mumbai Dadar, Nashik. Currency is ₹. Data is as of 30 September 2026.
Prices, SLAs and rules come only from Merchant_Offer_and_FAQ_Sheet.pdf (a training sample).

When you answer:
- Use only the references in this notebook. Name the file and sheet (or clause number) for every
  number or rule.
- If something is not in the references, say "not in the data" — do not guess.
- Never invent a price, waiver or offer.
- Keep answers short enough to read on a phone: a 2-line summary, then a short list or table.
- Tone: practical and direct.
```

### ✅ Check
The notebook shows **6 references** (or 1 folder), and the instructions are saved.

---

# Exercise 2 — Validate the Notebook Can See Everything
**Time:** ~5 minutes

```
List every reference in this notebook with: file name, what it contains
(sheets / sections, row counts, dates), and one fact that proves you read it.
Tell me if any file could not be read.
```

### ✅ Check
- [ ] All **6 files** are listed.
- [ ] The dataset's **five** data sheets are named, plus the **Read Me** sheet.
- [ ] The demo file shows 25 merchants (MER-4101 to MER-4125).
- [ ] The PDF is identified as the Merchant Offer Sheet & Field FAQ (ref PAY-SALES-FAQ-03), training sample.

---

# Exercise 3 — Ask Across Files (the payoff)
**Time:** ~15 minutes

### 3a — Why aren't these merchants transacting?

```
List every merchant that is installed but has no transaction yet.
For each one, pull together from all references:
- area, product, FOS, days since install (as of 30 Sep 2026)
- every field visit since install and its outcome (Field Visit Log)
- any open query or objection (Merchant Queries)
- what the offer sheet says to do next, with clause numbers
Then sort them by urgency and say which ones go to the Team Lead and why.
```

**What a good answer contains:**

| Merchant | Days since install | What's blocking | Next step (clause) |
|---|---|---|---|
| **Hotel Annapurna**, Pune East, POS | 17 | "Settlement too slow" (MQ-302). Two revisits with no change (FV-803, FV-814) | **Team Lead** after the second revisit (3.3). Reply on T+1 and the daily summary (4.1, 4.3) |
| **Balaji Stationers**, Pune West, QR | 17 | "Customers pay cash" (MQ-307). Two revisits (FV-801, FV-815) | **Team Lead** (3.3). Adoption pitch (5.1) |
| **Gupta Hardware**, Nashik, Soundbox | 10 | "Rental too high" (MQ-303). One visit | Revisit within 3 days (3.3). Explain the waiver (1.2, 5.2) |
| **Urban Salon**, Andheri, POS | 6 | **"Terminal not activated"** (MQ-312). No visit since install | Device issue, so raise a ticket. Not an objection |
| **Tanishq Opticals**, Nashik, POS | 1 | Asked to accept on mobile (MQ-315) | Within 7 days. The offer sheet **doesn't cover** mobile acceptance, so check with the Team Lead |

The point to notice: **every inactive merchant has an open query.** Fixing the query is usually what activates the merchant.

### 3b — Why is Nashik's activation falling?

```
Rohit Deore (Nashik) has the lowest activation in the team. Using all
references, explain what might be behind it:
- FOS Performance: his activation trend for Jul–Sep vs the 80% target
- Demo file: install SLA for his merchants (lead date to install vs the SLA
  in the offer sheet) and how many are inactive
- Field Visit Log and Merchant Queries for his merchants
Present the evidence, then suggest two actions. Be clear about what is a fact
and what is a likely explanation.
```

**What a good answer contains:**
- **Trend:** activation fell from 75.0% to 73.9% to **63.6%**, below 80% in all three months.
- **Installs are slow:** in the demo sample, **4 of his 5** installs breached SLA. Gupta Hardware took 13 days against 3; Tanishq Opticals 9 against 5. Late installs eat into the 7-day activation window.
- **Inactive merchants:** 2 (Gupta Hardware, Tanishq Opticals), one of them with a pricing objection.
- **Good news:** Mahalaxmi Jewellers is the team's highest-value merchant at ₹12,45,000.
- **Caution:** the demo file is a 25-merchant sample, not his full month. A good answer says the install delay is a *likely* cause and suggests checking his full install data.

### ✅ Check
- [ ] Every figure is quoted with its **file and sheet**, and every rule with its **clause**.
- [ ] 3a uses three sheets and the PDF; 3b uses two files.
- [ ] Facts and likely explanations are kept apart.
- [ ] You did **not** attach a single file.

---

# Exercise 4 — Re-run the Use Cases Without Re-attaching
**Time:** ~10 minutes

| Stage | Prompt inside the notebook |
|---|---|
| 1 — Pitch | `Pitch for a busy pharmacy that already uses another QR. Under 120 words. Facts from the offer sheet only.` |
| 2 — Beat plan | `Visit plan for 1 Oct for Imran Qureshi (Mumbai Andheri): inactive first, then installs, then KYC pending.` |
| 3 — Objections | `Reply to every unresolved query in Merchant Queries, with the offer-sheet clause for each.` |
| 5 — Team review | `FOS review Jul–Sep: activation vs 80%, who needs support, two actions for October.` |

### ✅ Check
The tone and format match your instructions **without** you retyping them.

---

# Exercise 5 — The 9-Step Flow, Inside One Notebook
**Time:** ~10 minutes

1. **Chat A** in the notebook: run Steps 1–4 of `Excel_To_PowerPoint.md` on the **FOS Performance** sheet. Copy the Working Prompt.
2. **Chat B** in the same notebook: paste the Working Prompt. No re-attaching.
3. Save the output as a **page**.
4. If you see **create options** (Word / PowerPoint), build the Area Manager deck from the notebook.

---

## Efficiency Rules — Quick Reference

| Do | Avoid |
|---|---|
| One notebook per piece of work (your beat, a team review) | One notebook for everything |
| Put role, area, units and tone in **Copilot instructions** | Re-typing the RTCFT block every time |
| Add a **folder** reference for files that keep coming | Re-uploading each new version |
| Ask for **file + sheet or clause** for every fact | Accepting a number or price you can't trace |
| Save good answers as **pages** | Leaving them buried in chat history |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| `.md` file can't be added | Rename it to `.txt`. |
| Copilot quotes a price that isn't in the offer sheet | Tell it: *"Use only the offer sheet; quote the clause."* |
| Notebooks not visible on your phone | Update the M365 Copilot app; if still missing, your licence may not include it yet. |
| A figure looks wrong | Open the source sheet and check, then ask Copilot to show the rows it used. |

---

## Further Reading

- [How Microsoft Copilot Notebooks works](https://support.microsoft.com/en-us/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works)
- [Add references to your Copilot Notebook](https://support.microsoft.com/en-us/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook)

---

*Bajaj Finance Limited | M365 Copilot Training — Payments (Sales), Field*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*
