# Copilot in Excel — Participant Exercise Guide
### Formulas & Pivot Tables for Payments Field Sales
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `PaymentsSales_Copilot_Demo.xlsx`

> **Premium licence required.** This guide uses Copilot inside Excel (Agent / Edit with Copilot), which needs a paid Microsoft 365 Copilot licence. On M365 Copilot (Basic), use `Excel_Chat_Guide.md` instead. It produces the same results.
**Mode:** Copilot in Excel (Microsoft 365 Copilot licence, on a laptop). *M365 Copilot (Basic)? Use `Excel_Chat_Guide.md` instead.*

---

## Before You Begin

- Open `PaymentsSales_Copilot_Demo.xlsx` from **OneDrive**. Copilot in Excel needs the file saved in OneDrive or SharePoint with AutoSave on.
- Click the **Copilot** button (top-right of the Home ribbon) and keep the pane open.
- The sheet `Merchant Onboarding` has **25 merchants**. Headers are in **row 2**, data runs from **row 3 to row 27**, and the data is as of **30 Sep 2026**.
- Columns **N–Q are intentionally blank**. You will fill them using Copilot. Column M is a blank spacer.

| Column | Field | Column | Field |
|---|---|---|---|
| A | Merchant ID | G | Lead Date |
| B | Merchant Name | H | Installed On (blank if not yet) |
| C | Category | I | Install SLA (days from lead) |
| D | Area | J | First Txn On (blank if none yet) |
| E | Product | K | Sep TPV (₹) |
| F | FOS | L | Sep Txn Count |

---

## Exercise 1 — Days to Install (Column N)

Click **N3**, then type into the Copilot pane:

```
In column N, calculate the number of days from the Lead Date (column G) to
the Installed On date (column H). If column H is blank, leave the cell blank.
Apply it to all 25 rows.
```

**What Copilot will produce:**
```excel
=IF(H3="","",H3-G3)
```

✅ **Check:** Shree Ganesh Kirana (row 3) shows **3**. Urban Salon shows **15**. Three merchants are blank because they have no install yet.

---

## Exercise 2 — Install SLA Status (Column O)

Click **O3**, then type:

```
In column O, show "Not Installed" if column H is blank. Otherwise show
"Breach" if Days to Install (column N) is greater than the Install SLA
(column I), or "Within SLA" if not. Apply it to all 25 rows.
```

**What Copilot will produce:**
```excel
=IF(H3="","Not Installed",IF(N3>I3,"Breach","Within SLA"))
```

✅ **Check:** **10 Breach**, 12 Within SLA, 3 Not Installed. **6 of the 8 Android POS installs** breached their 5-day SLA.

---

## Exercise 3 — Activation Status (Column P)

Click **P3**, then type:

```
In column P, show "Not Installed" if Installed On (column H) is blank;
"Inactive" if it is installed but First Txn On (column J) is blank;
otherwise "Active". Apply it to all 25 rows.
```

**What Copilot will produce:**
```excel
=IF(H3="","Not Installed",IF(J3="","Inactive","Active"))
```

✅ **Check:** **17 Active, 5 Inactive, 3 Not Installed.** The inactive merchants are Hotel Annapurna, Gupta Hardware, Urban Salon, Balaji Stationers and Tanishq Opticals.

---

## Exercise 4 — Usage Band (Column Q)

Click **Q3**, then type:

```
In column Q, for Active merchants only (column P), band the Sep TPV in
column K: "High" if 2,00,000 or more, "Medium" if 50,000 or more, otherwise
"Low". Leave it blank for merchants that are not Active.
```

**What Copilot will produce:**
```excel
=IF(P3<>"Active","",IF(K3>=200000,"High",IF(K3>=50000,"Medium","Low")))
```

✅ **Check:** 5 High, 9 Medium, 3 Low. Mahalaxmi Jewellers is the top merchant at **₹12,45,000**.

> **Why the guard matters:** without `IF(P3<>"Active","",…)`, every merchant with no transactions would be banded "Low". That would mix *low usage* with *no usage at all*, two very different follow-ups in the field.

---

## Exercise 5 — Ask Copilot to Explain a Formula

Click **O3**, then type:

```
Explain this formula in simple terms. In what order does it check things,
and why does the blank check come first?
```

**What Copilot will explain:**
> *"It first checks whether there is an install date. If not, it returns Not Installed and stops, because there is nothing to compare. If there is one, it compares the days taken with the SLA: more than the SLA is a Breach, otherwise Within SLA."*

---

## Exercise 6 — Pivot Table: Activation by Area

Click anywhere in the data, then type:

```
Create a pivot table on a new sheet showing the count of merchants for each
Area, broken down by Activation Status (column P).
```

**What Copilot will produce:**
- **Rows:** Area
- **Columns:** Activation Status
- **Values:** Count of Merchant ID

✅ **Check:**
- **Nashik:** 2 of its 5 merchants are Inactive (Gupta Hardware, Tanishq Opticals).
- **Mumbai Andheri:** 2 are Not Installed and 1 is Inactive, so only 2 of 5 are Active.

> **Try this:** *"Add Sep TPV as a second value, summed."* Android POS merchants bring in most of the value: **₹30,57,200** of the ₹42,26,400 total.

> **If Copilot can't use column P:** the blank spacer column M can block range detection. Type `Spacer` into **M2** and ask again.

---

## Copilot Prompts — Quick Reference

| Task | Prompt to use in the Copilot pane |
|------|-------------------------------|
| Days to Install | "In column N, days from Lead Date (G) to Installed On (H); blank if H is blank." |
| Install SLA Status | "In column O: Not Installed if H is blank; Breach if N > I; else Within SLA." |
| Activation Status | "In column P: Not Installed if H blank; Inactive if J blank; else Active." |
| Usage Band | "In column Q, for Active only: High ≥ 2,00,000, Medium ≥ 50,000, else Low, on K." |
| Explain a formula | "Explain this formula in simple terms." |
| Pivot — activation | "Pivot: count of Merchant ID by Area and Activation Status." |
| Revisit list | "Filter to Activation Status = Inactive and sort by Installed On, oldest first." |

---

*Bajaj Finance Limited | AI Academy — Payments (Sales), Field | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*
