# Excel with M365 Copilot (Basic) — No Agent Required
### Formulas & Pivot Tables for Payments (Sales), Field, using M365 Copilot chat + Meta-Prompting
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `PaymentsSales_Copilot_Demo.xlsx`
**Companion guides:** `MetaPrompting_Guide.md` · `Excel_Agent_Guide_Premium.md` (Agent version)

---

## Who This Guide Is For

`Excel_Agent_Guide_Premium.md` uses **Edit with Copilot** in Excel, in which Copilot writes formulas into your cells and builds pivot tables for you. It needs a **paid Microsoft 365 Copilot licence**.

This guide produces **the same results** with **M365 Copilot (Basic)**:

- **Copilot does the thinking.** It writes the formula, explains the logic and gives you the pivot layout.
- **You do the clicking.** You paste the formula and build the pivot in Excel yourself, which takes about 30 seconds per exercise.

| Your licence | What works for you |
|---|---|
| **M365 Copilot (Premium)** | Either guide. The Agent guide is faster. |
| **M365 Copilot (Basic)** | **This guide.** Run the prompts in M365 Copilot chat. Copilot will not edit the workbook for you. |

---

## How Every Exercise Works

```
Step 1 → Paste the Excel Meta Prompt with that exercise's TASK filled in
Step 2 → Read the Working Prompt Copilot generates
Step 3 → Attach PaymentsSales_Copilot_Demo.xlsx and run the Working Prompt
Step 4 → Apply Copilot's answer in Excel yourself (paste formula / build pivot)
Step 5 → Verify against the expected numbers in this guide
```

> 💡 **Why Step 5 matters:** without an agent, nobody checks the result but you. The expected numbers below let you spot a wrong formula in seconds.

---

## Before You Begin

1. Open `PaymentsSales_Copilot_Demo.xlsx` in **Excel** (desktop or web) and go to the **Merchant Onboarding** sheet.
2. Open **M365 Copilot** chat in a second window, either the M365 Copilot app or `m365copilot.com`.
3. Keep both windows side by side.

### What's in the file

- Row 1 is a title and **row 2 holds the headers**. **Data runs in rows 3–27** (25 merchant onboardings, as of **30 Sep 2026**). Row 28 is a note.
- **Column M is a blank spacer.** Columns **N–Q already have headers** (`➕ Days to Install`, `➕ Install SLA Status`, `➕ Activation Status`, `➕ Usage Band`) and empty cells below them. You will fill those cells.
- **Lead Date (G), Installed On (H) and First Txn On (J) hold real Excel dates.** H is blank until the device is installed and J is blank until the first transaction. Unlike some other workbooks in this programme, there is no text-date trap here.
- The data is as of **30 Sep 2026**, and no formula in this guide needs today's date, so everyone in the room gets the same answer.

| Column | Field | Column | Field |
|---|---|---|---|
| A | Merchant ID | H | Installed On *(blank if not yet)* |
| B | Merchant Name | I | Install SLA (days from lead) |
| C | Category | J | First Txn On *(blank if none yet)* |
| D | Area | K | Sep TPV (₹) |
| E | Product | L | Sep Txn Count |
| F | FOS | M | *(blank spacer)* |
| G | Lead Date | N–Q | **You fill these** |

---

## ⚡ The Excel Meta Prompt — Your Starting Point

This follows the RTCFT pattern from `MetaPrompting_Guide.md`, adapted for Excel. The file layout is already filled in, so for each exercise you only replace **[TASK]**.

```
Act as a Microsoft Copilot prompt expert specialising in Excel for merchant onboarding for a field sales team.

Role:    I am a Field Sales Analyst at Bajaj Finance Limited. I use M365 Copilot chat,
         which cannot edit my workbook — I will apply the result in Excel myself.
Task:    I need to: [TASK]
Context: Sheet "Merchant Onboarding" in PaymentsSales_Copilot_Demo.xlsx. Data as of 30 Sep 2026.
         Headers are in row 2; data is in rows 3 to 27 (25 merchants).
         Columns: A Merchant ID, B Merchant Name, C Category, D Area, E Product, F FOS,
         G Lead Date, H Installed On (blank if not installed), I Install SLA (days from lead),
         J First Txn On (blank if none yet), K Sep TPV, L Sep Txn Count. Column M is a blank spacer.
Format:  The prompt must ask Copilot for:
         1. The exact result (formula for row 3, or pivot/table layout) ready to copy
         2. Step-by-step instructions to apply it manually in Excel
         3. How to handle blanks (no install date, no first transaction)
         4. A quick way to verify the result is correct
Tone:    Clear and step-by-step, for a field sales user who is not an Excel expert.

Write me a detailed, ready-to-use Copilot prompt I can use in M365 Copilot chat with this file attached.
```

> ✏️ **Short on time?** Once you've done this for Exercise 1, reuse the Working Prompt Copilot gave you and swap in the new task for the later exercises.

---

---

# Exercise 1 — Formula Column: Days to Install (N)
**Time:** ~6 minutes

### Step 1 — [TASK] to paste into the Meta Prompt
```
write a formula for column N ("Days to Install") that returns the number of days from the Lead Date (G)
to the Installed On date (H), and leaves the cell blank if H is blank, for rows 3 to 27
```

### Step 2 — Check the Working Prompt
- [ ] Does it mention row 3 and filling down to row 27?
- [ ] Does it say what to do when H is blank?
- [ ] Does it ask for manual steps and a verification check?

### Step 3 — Attach the file and run
Attach `PaymentsSales_Copilot_Demo.xlsx` → paste the Working Prompt → send.

### Step 4 — Apply in Excel
1. Click **N3** and paste the formula Copilot gave you.
2. Fill it down to **N27**: select **N3:N27** and press **Ctrl + D**, or double-click the fill handle at the bottom-right corner of N3.

### Step 5 — Verify
Type this in any empty cell, such as **U3**:
```excel
=COUNT(N3:N27)
```
**Expected: 22** numbers, so **3 rows are blank**: the merchants with no install yet. Shree Ganesh Kirana (row 3) shows **3**, and Urban Salon shows **15**.

<details><summary>Reference formula (open only if stuck)</summary>

```excel
=IF(H3="","",H3-G3)
```
If the result shows as a date instead of a number, set the column format to **Number**.
</details>

---

# Exercise 2 — Formula Column: Install SLA Status (O)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column O ("Install SLA Status") that returns "Not Installed" if H is blank,
otherwise "Breach" if Days to Install (N) is greater than the Install SLA (I), or "Within SLA" if not,
for rows 3 to 27
```

### Steps 2–4
Same as Exercise 1, but paste in **O3** and fill down to **O27**.

### Step 5 — Verify
```excel
=COUNTIF(O3:O27,"Breach")
```
**Expected: 10 Breach · 12 Within SLA · 3 Not Installed.** Of the 8 Android POS merchants that were installed, **6** breached their 5-day SLA.

<details><summary>Reference formula</summary>

```excel
=IF(H3="","Not Installed",IF(N3>I3,"Breach","Within SLA"))
```
</details>

> **Discussion Point:** Six of the eight installed Android POS devices missed their SLA. Is the cause device stock, site readiness or scheduling?

---

# Exercise 3 — Formula Column: Activation Status (P)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column P ("Activation Status") that returns "Not Installed" if Installed On (H) is blank,
"Inactive" if it is installed but First Txn On (J) is blank, otherwise "Active", for rows 3 to 27
```

### Steps 2–4
Paste in **P3** and fill down to **P27**.

### Step 5 — Verify
```excel
=COUNTIF(P3:P27,"Active")
```
**Expected: 17 Active · 5 Inactive · 3 Not Installed.**
- The five Inactive merchants are Hotel Annapurna, Gupta Hardware, Urban Salon, Balaji Stationers and Tanishq Opticals.
- The three Not Installed are Classic Footwear, New India Bakery and Star Electronics.

<details><summary>Reference formula</summary>

```excel
=IF(H3="","Not Installed",IF(J3="","Inactive","Active"))
```
</details>

> **Discussion Point:** Inactive merchants are installed but not transacting. Which of the five should be revisited first, and what would you ask at the visit?

---

# Exercise 4 — Formula Column: Usage Band (Q)
**Time:** ~8 minutes

### Step 1 — [TASK]
```
write a formula for column Q ("Usage Band") for Active merchants only (column P): band the Sep TPV in
column K as "High" if 2,00,000 or more, "Medium" if 50,000 or more, otherwise "Low". Leave it blank
for merchants that are not Active. Rows 3 to 27.
```

### Steps 2–4
Paste in **Q3** and fill down to **Q27**.

### Step 5 — Verify
**Expected: 5 High · 9 Medium · 3 Low · 8 blank.** Mahalaxmi Jewellers is the top merchant at **₹12,45,000**.

<details><summary>Reference formula</summary>

```excel
=IF(P3<>"Active","",IF(K3>=200000,"High",IF(K3>=50000,"Medium","Low")))
```
</details>

> **Why the guard matters:** without `IF(P3<>"Active","",…)`, every merchant with no transactions would be banded "Low". That mixes *low usage* with *no usage at all*, which are two different follow-ups in the field.

---

# Exercise 5 — Ask Copilot to Explain a Formula
**Time:** ~3 minutes

No meta prompt or attachment is needed. Copy the formula from **O3** and paste it into M365 Copilot chat:
```
Explain this Excel formula in simple terms for a field sales user. In what order does it check things,
and why does the blank check come first?
[paste formula here]
```

**What to look for:**
- The explanation should say that with no install date there is nothing to compare, so the formula returns **Not Installed** and stops.
- Only when there is an install date does it compare the days taken with the SLA.

---

# Exercise 6 — Pivot Table: Activation by Area
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the count of merchants for each Area (rows) broken down by
Activation Status (columns: Active, Inactive, Not Installed). Give me the exact field placement and
click-by-click steps to build it in Excel, plus the expected result table so I can check my pivot.
```

### Steps 2–3
Run the Working Prompt with the file attached, as before.

### Step 4 — Build it in Excel
1. On **Merchant Onboarding**, select **A2:Q27** exactly. Don't include the title in row 1 or the note in row 28.
2. Go to **Insert → PivotTable → New Worksheet → OK**.
3. Place the fields:
   - **Area** → Rows
   - **Activation Status** → Columns
   - **Merchant ID** → Values (*Count of Merchant ID*)

### Step 5 — Verify

| Area | Active | Inactive | Not Installed | Total |
|---|---|---|---|---|
| Mumbai Andheri | 2 | 1 | 2 | 5 |
| Mumbai Dadar | 3 |  | 1 | 4 |
| Nashik | 3 | 2 |  | 5 |
| Pune East | 4 | 1 |  | 5 |
| Pune West | 5 | 1 |  | 6 |
| **Grand Total** | **17** | **5** | **3** | **25** |

*Excel sorts rows and columns alphabetically by default, so your order may differ.*

> **Discussion Point:** Mumbai Andheri has only 2 of 5 merchants Active, with 2 not yet installed. Nashik has 2 of 5 Inactive. Which area needs the Area Manager's attention first?

> **Try this:** add **Sep TPV (₹)** as a second value, summed. Android POS merchants bring in most of the value: **₹30,57,200** of the ₹42,26,400 total.

> **If Excel cannot see column P:** the blank spacer column M may be breaking range detection. Type `Spacer` in **M2** and rebuild the pivot.

---

# Exercise 7 — Pivot Table: FOS Performance by Install SLA Status
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the count of merchants for each FOS (rows) broken down by
Install SLA Status (columns: Breach, Within SLA, Not Installed). Give me the field placement,
click-by-click steps, and the expected row totals.
```

### Step 4 — Build it in Excel
1. Select **A2:Q27** → **Insert → PivotTable → New Worksheet**.
2. Place the fields:
   - **FOS** → Rows
   - **Install SLA Status** → Columns
   - **Merchant ID** → Values (*Count of Merchant ID*)

### Step 5 — Verify

| FOS | Breach | Within SLA | Not Installed | Total |
|---|---|---|---|---|
| Akash Shinde | 2 | 4 |  | 6 |
| Imran Qureshi | 1 | 2 | 2 | 5 |
| Kavita Sawant | 1 | 2 | 1 | 4 |
| Priya Jagtap | 2 | 3 |  | 5 |
| Rohit Deore | 4 | 1 |  | 5 |
| **Grand Total** | **10** | **12** | **3** | **25** |

> **Discussion Point:** Rohit Deore (Nashik) breached on 4 of his 5 installs, and all five of his merchants have a device installed. Is that a person, a route or a device-supply issue?

> 💡 **No pivot tables allowed on your machine?** Ask Copilot for the same result as a `COUNTIFS` formula grid instead. For example, `=COUNTIFS(F3:F27,"Rohit Deore",O3:O27,"Breach")` returns **4**.

---

# Exercise 8 — Bonus: Ask Copilot for Insights
**Time:** ~5 minutes

This works directly in M365 Copilot chat with the file attached. No manual steps are needed.

```
Look at the Merchant Onboarding sheet in the attached file. Which FOS has the most Install SLA
breaches (installed days greater than Install SLA), and what do those merchants have in common
(product, area)? Summarise the key risk areas for the Payments (Sales) team in 3 bullet points,
quoting Merchant IDs as evidence.
```

**Expected:**
- **Rohit Deore has the most breaches, 4**, all in Nashik: MER-4110, MER-4114, MER-4118 and MER-4123.
- Akash Shinde and Priya Jagtap have 2 each.
- **Android POS is the weak product:** 6 of its 8 installs breached.

> 💡 **Lesson:** if Copilot names one FOS, check it with a `COUNTIFS`. A breach count is only fair next to the number of installs behind it.

---

## Reference: What Your Results Should Show

| Check | Expected |
|---|---|
| Total merchants | 25: 22 installed · 3 not installed |
| Days to Install | 3 blank · Shree Ganesh Kirana 3 · Urban Salon 15 |
| Install SLA Status | 10 Breach · 12 Within SLA · 3 Not Installed |
| Activation Status | 17 Active · 5 Inactive · 3 Not Installed |
| Usage Band | 5 High · 9 Medium · 3 Low · 8 blank |
| Top merchant by TPV | Mahalaxmi Jewellers, ₹12,45,000 |
| FOS with most breaches | Rohit Deore, 4 (of 5 installs) |

---

## Agent vs M365 Copilot (Basic) — What Changes

| | Edit with Copilot (Agent) | M365 Copilot chat + Meta Prompt (this guide) |
|---|---|---|
| Licence | M365 Copilot (Premium) | M365 Copilot (Basic) |
| Writes formula into cells | ✅ Automatic | ✍️ You paste and fill down |
| Builds pivot table | ✅ Automatic | ✍️ You build it using Copilot's layout |
| Explains formulas, gives insights | ✅ | ✅ Same |
| Handles errors | Agent retries | You paste the error back and ask for a fix |
| What you learn | Prompting | Prompting **plus** checking the formula logic yourself |

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Formula refers to row 1 or the wrong column | Remind Copilot: *"Headers are row 2, data starts row 3."* |
| Days to Install shows a date | Set the column format to **Number**. |
| `#NAME?` after pasting | Curly quotes crept in. Retype the `"` characters in Excel. |
| Pivot shows *Count* instead of *Sum* | Change it in **Value Field Settings**. |
| Pivot includes the title or note text | Rebuild it from **A2:Q27** only. |
| Pivot cannot see column P | Type `Spacer` in **M2** and rebuild. |
| Copilot says it can't open the file | Re-attach it from OneDrive, or paste the relevant rows as text. |

---

*Bajaj Finance Limited | AI Academy — Payments (Sales), Field | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India***
