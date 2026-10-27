# BFL Payments (Sales) — M365 Copilot Participant Guide
### Meta Prompts for Merchant Pitch, Beat Planning, Objection Handling, Activation Follow-up, Team Review & Visit Notes

**Programme:** Microsoft Copilot for Payments (Sales) — Field
**Organisation:** Bajaj Finance Limited
**Interface:** M365 Copilot Chat (m365.cloud.microsoft/chat, Teams, or the **M365 Copilot app on your phone**)
**Files:** `PaymentsSales_Copilot_Dataset.xlsx` (data as of 30 Sep 2026, synthetic) and `Merchant_Offer_and_FAQ_Sheet.pdf` (training sample)

---

## How Each Exercise Works — The 3-Step Rhythm

| Step | What You Do | What It Shows |
|------|-------------|----------------|
| **Step 1 — Meta Prompt** | Fill in the template and paste it into Copilot | Copilot writes a tailored working prompt for you |
| **Step 2 — Generated Prompt** | Review what Copilot wrote | How your context shaped the prompt |
| **Step 3 — Live Apply** | Attach the file(s) using `/` (or the **+** on mobile) and run the prompt | Copilot produces something you can use in the field |

> 💡 BFL's Copilot allows **up to 3 file attachments per prompt**. Every exercise below stays within that limit.

> 📱 **Phone tip:** in the M365 Copilot app, tap **+** to attach a file from OneDrive, or use the **microphone** to dictate. Stages 1, 3, 4 and 6 are designed to be done on a phone.

---

## The Meta Prompt Template

```
Act as a Microsoft Copilot prompt expert.

I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

## RTCFT Quick Reference

| Element | What It Means | Example (Payments Field Sales) |
|---------|---------------|-------------------------------|
| **R** — Role | Who are you? | "You are an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited" |
| **T** — Task | What do you need? | "Write a two-minute pitch for a pharmacy owner" |
| **C** — Context | What is the situation? | "Busy counter, mostly UPI customers, already has another QR" |
| **F** — Format | How should it look? | "Under 120 words: 3 benefits, 1 objection reply, closing line" |
| **T** — Tone | What register? | "Simple, respectful, confident — not technical" |

---

## Your Files at a Glance

`PaymentsSales_Copilot_Dataset.xlsx`: in every sheet the title is in row 1, headers are in row 4 and data starts in row 5. **Merchant ID** links the merchant-level sheets. A **blank date** means that step hasn't happened yet; it is not missing data.

| Sheet | What it holds |
|---|---|
| Read Me | What each sheet holds, and what blanks and special values mean |
| Merchant Lead Pipeline | A September sample of 25 merchants from lead to first transaction, with install SLA, stage and next action |
| Activation & Usage | The 22 installed merchants: September payment value (TPV), transactions, active or inactive, usage band |
| Field Visit Log | 15 FOS visits (21–30 Sep) with outcome and the objection raised |
| FOS Performance | 5 FOS executives, Jul–Sep 2026 (full quarter, all onboardings): onboarding vs target, activation within 7 days, new TPV, visits |
| Merchant Queries | 15 merchant questions and objections, with category and whether resolved |

`Merchant_Offer_and_FAQ_Sheet.pdf`: products, rentals and waivers, installation SLAs, the activation rule, settlement, objection replies and conduct rules. It is a **training sample**. Do not quote its prices to real merchants.

---

## Stage 1 — Merchant Pitch by Category

**Use case:** a two-minute pitch you can say aloud at the counter.
**File to attach:** `Merchant_Offer_and_FAQ_Sheet.pdf`

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.
I need a short pitch to sign up a merchant for the right payment product —
UPI QR, QR + soundbox, Android POS or payment link — based on their category.
My audience is the shop owner, who has about two minutes.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

### Step 2 — Copilot Generates Your Working Prompt

*(Typical output. Yours will be worded differently.)*

```
You are an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.

Task: Write a two-minute pitch for the merchant described below.

Context: Products are UPI QR, UPI QR + Soundbox, Android POS and Payment Link.
Use only the facts in the attached offer sheet for prices, waivers and settlement.

Format:
- Recommended product and one reason
- Three benefits in plain, everyday words
- One likely objection with a two-line reply
- A closing question
Under 120 words.

Tone: Simple, respectful, confident. No jargon.
```

### Step 3 — Live Apply (attach the offer sheet)

```
I am attaching our merchant offer sheet. Using only facts from it, prepare
pitches for these two merchants:

1. A busy pharmacy that already takes UPI on another provider's QR.
2. A small restaurant where most customers pay by card.

Then give me the same pitch for the pharmacy in Hindi.
```

**What a good answer contains:**
- **Pharmacy:** recommends **QR + Soundbox**. Mentions voice alerts in the local language and **no charge on UPI** (clause 1.1). Explains the rental and that it is waived above ₹50,000 of UPI receipts a month (clause 1.2). Does **not** criticise the other provider (clause 5.5).
- **Restaurant:** recommends **Android POS**, with ₹399 rental waived above ₹2,00,000 of card receipts a month (clause 1.3).
- **Check:** no invented prices, offers or "free" claims. If Copilot adds one, tell it: *"Use only the offer sheet."*

---

## Stage 2 — Daily Beat Plan

**Use case:** turn the pipeline into a sequenced visit plan.
**Sheets to use:** `Merchant Lead Pipeline` and `Activation & Usage` (same file)

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.
I need a visit plan for tomorrow from my onboarding pipeline — inactive
merchants, installs due, KYC pending and new leads — with activation within
7 days of install as my main target.
My audience is me and my Team Lead.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

### Step 2 — Copilot Generates Your Working Prompt

```
You are an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.

Task: Build tomorrow's visit plan from the pipeline for one FOS.

Context: Priority order — (1) installed but no transaction, oldest first;
(2) KYC done, device to install; (3) KYC pending; (4) new leads.
Use the Next Action column and any open merchant query as the visit objective.

Format: a numbered list — merchant, area, stage, objective for the visit,
what to carry. Then one line on what to escalate to the Team Lead.

Tone: Short and practical. Readable on a phone.
```

### Step 3 — Live Apply (attach the dataset)

```
I am attaching our Payments Sales dataset (as of 30 Sep 2026).
Build the visit plan for 1 October 2026 for Imran Qureshi (Mumbai Andheri),
using the Merchant Lead Pipeline, Activation & Usage and Merchant Queries sheets.
```

**What a good answer contains**, in this order:
1. **Urban Salon:** POS installed 6 days ago with no transaction, so it is about to cross the 7-day mark. Open query MQ-312: *"terminal not activated"*. Carry an activation ticket reference.
2. **Classic Footwear:** KYC done, but the install failed because the device was out of stock (FV-807). Confirm stock at the hub before going.
3. **Star Electronics:** KYC pending. The owner asked about EMI on card (FV-812; Raj Mobile Point asked the same in MQ-301), and the offer sheet says the Android POS supports EMI on eligible cards (clause 1.3).
- **Good to see:** the answer flags that Urban Salon's problem is a **device activation** issue, not an adoption issue.

---

## Stage 3 — Objection Handling

**Use case:** an honest, fact-based reply to a merchant's objection.
**Files to attach:** `Merchant_Offer_and_FAQ_Sheet.pdf` + dataset (2 attachments)

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.
I need replies to the objections merchants raise, using only our offer sheet.
My audience is the merchant, face to face.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

### Step 2 — Copilot Generates Your Working Prompt

```
You are an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.

Task: Give a reply to each merchant objection listed.

Context: Use only the attached offer sheet. Quote the clause number you rely on.
If the sheet does not answer the objection, say so and suggest what to check.

Format per objection: Acknowledge (1 line) → Answer with one fact (2 lines,
clause number) → A question that moves things forward (1 line).

Tone: Calm, honest, non-pushy. Never promise anything not in the sheet.
```

### Step 3 — Live Apply (attach both files)

```
I am attaching our offer sheet and our Payments Sales dataset.
From the "Merchant Queries" sheet, take every query that is still unresolved
and give me a reply for each, as described above.
```

**What a good answer contains** (6 open queries):

| Query | Merchant | Reply should rest on |
|---|---|---|
| MQ-302 Settlement too slow | Hotel Annapurna | T+1 and the daily summary (clauses 4.1, 4.3). Same-day settlement only above ₹5,00,000 a month (4.2). |
| MQ-303 Soundbox rental | Gupta Hardware | Rental waived above ₹50,000 UPI a month (1.2, 5.2) |
| MQ-307 Customers pay cash | Balaji Stationers | Clause 5.1 |
| MQ-310 Device not delivered | Classic Footwear | Not a pricing objection. Install SLA is 3 days (2.2), so escalate the stock issue. |
| MQ-312 Terminal not activated | Urban Salon | Device or activation issue. Raise a ticket, don't "handle" it as an objection. |
| MQ-315 Accept on mobile instead of POS | Tanishq Opticals | **Not in the sheet.** A good answer says so and suggests checking with the Team Lead. |

---

## Stage 4 — Activation Follow-up Message

**Use case:** a WhatsApp message before a revisit, in two languages.
**File to attach:** `Merchant_Offer_and_FAQ_Sheet.pdf`

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.
I need short WhatsApp messages for merchants who have a device installed but
have not taken a payment yet, in English and in Hindi or Marathi.
My audience is the merchant.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

### Step 2 — Copilot Generates Your Working Prompt

```
You are an FOS (Feet on Street) sales executive in the Payments team at Bajaj Finance Limited.

Task: Write a WhatsApp message to a merchant who has not taken a first payment.

Context: Address the concern the merchant raised, using the offer sheet only.

Format: Greeting with name → one line on their concern → one benefit →
one simple step to take a payment today → revisit time → sign-off with my name.
Under 60 words. English first, then the same in the language I name.

Tone: Warm, helpful, not salesy.
```

### Step 3 — Live Apply

```
Write the message for Hotel Annapurna (Pune East, Android POS). The owner's
concern is that settlement takes too long. I will revisit on 1 Oct at 11 AM.
My name is Priya Jagtap. Give it in English and Marathi.
```

**What a good answer contains:** settlement **T+1**, with the daily summary visible in the app or SMS (clauses 4.1, 4.3). No promise of same-day settlement, because Hotel Annapurna has no receipts yet, so clause 4.2 does not apply. Under 60 words per language.

> ⚠️ Read the message before you send it. Never include a merchant's account details or anything the merchant hasn't already shared.

---

## Stage 5 — Team Performance Review (Team Leads)

**Use case:** the monthly FOS review for the Area Manager.
**Sheet to use:** `FOS Performance`

### Step 1 — Fill in the Template

```
Act as a Microsoft Copilot prompt expert.

I am a Team Lead in Payments sales at Bajaj Finance Limited.
I need a monthly review of my FOS executives for Jul–Sep 2026 — onboarding
against target, activation within 7 days (target 80%), new TPV and visits.
My audience is my Area Manager.

Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

### Step 2 — Copilot Generates Your Working Prompt

```
You are a Team Lead in Payments sales at Bajaj Finance Limited.

Task: Review FOS performance for Jul–Sep 2026 and recommend actions.

Context: Targets are 100% of onboarding target and 80% activation within 7 days.

Format:
1. 3-line summary for September
2. Table by FOS: onboarding %, activation %, new TPV — Jul / Aug / Sep
3. Who needs support, and why (one line each)
4. Two actions for October

Tone: Factual, fair, constructive.
```

### Step 3 — Live Apply (attach the dataset)

```
I am attaching our Payments Sales dataset. Use the "FOS Performance" sheet.
Run the review as described. Also total the team for each month:
target, onboarded, activated within 7 days, and activation %.
```

**What a good answer contains:**
- **Team totals:**

  | Month | Target | Onboarded | Activated within 7 days | Activation % |
  |---|---|---|---|---|
  | Jul | 147 | 146 | 121 | 82.9% |
  | Aug | 147 | 150 | 123 | 82.0% |
  | Sep | 158 | 153 | 111 | **72.5%** |

- **September story:** onboarding held up but **activation dropped**. Only **Kavita Sawant** (Mumbai Dadar, 85.7%) is above 80%.
- **Needs support:**
  - **Rohit Deore** (Nashik): activation below 80% in all three months, falling to **63.6%**.
  - **Imran Qureshi** (Mumbai Andheri): missed the onboarding target at **86.8%** (33 of 38), with activation at **66.7%**.
  - **Akash Shinde** (Pune West): over target at 106.3%, but activation fell to **73.5%**. That is the onboarding-versus-activation gap.

---

## Stage 6 — Bonus: Visit Notes to CRM Entry (on your phone)

**Use case:** dictate rough notes after a visit and get a clean record.
**No file needed. Use the M365 Copilot app and tap the microphone.**

### Step 3 — Live Apply

```
Turn these rough notes into a visit record with fields: Merchant, Purpose,
Outcome, Objection, Next action, Follow-up date. Do not add anything I did not
say. Mark missing fields as "not captured".

Notes: went to vishal medicals pune west cold visit, owner interested, uses
another QR already, showed him soundbox with marathi voice, come back thursday
with standee
```

**What a good answer contains:**
- **Merchant:** Vishal Medicals (Pune West). **Purpose:** cold visit. **Outcome:** interested.
- **Objection:** already uses another QR. **Next action:** revisit with a standee.
- **Follow-up date:** "Thursday" only, or "not captured" if Copilot is careful. It should **not** invent a calendar date.

---

## All Exercises at a Glance

| Stage | Use Case | File / Tool | Phone-friendly? |
|-------|----------|-------------|---|
| 1 | Merchant pitch | Offer sheet PDF | ✓ |
| 2 | Daily beat plan | Pipeline + Activation + Queries sheets | Best on laptop |
| 3 | Objection handling | Offer sheet + Merchant Queries | ✓ |
| 4 | Activation follow-up message | Offer sheet | ✓ |
| 5 | Team review (TLs) | FOS Performance | Laptop |
| 6 *(Bonus)* | Visit notes to CRM | None, voice | ✓ |

---

## ⚠️ Data Handling

The files here are **synthetic**, so they are safe to use. Real merchant data is not:

- Use Copilot signed in with your **BFL work account** (look for the enterprise data protection indicator).
- Never paste or photograph a merchant's PAN, bank account, GST certificate, card details, OTP or UPI PIN into any tool. Upload KYC only through the onboarding app (offer sheet clause 6.2).
- Never quote a price, waiver or settlement term that Copilot suggested unless it is in the official documents.

---

*Bajaj Finance Limited | AI Academy — Payments (Sales), Field | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*
