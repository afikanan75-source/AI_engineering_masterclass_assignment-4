# Class 4: Generation Control and Production Prompting

## What is in this folder

- `Class4.ipynb`: the lab notebook (already run, so you can see what to expect)
- `prompts/triage_v1.md`, `prompts/triage_v2.md`: prompts kept as files, versioned like code
- `requirements.txt`: what to install
- `AI-Engineering-MasterClass-Class-4.pdf`: the slides

## Setup (3 minutes)

Use the same virtual environment and `.env` as before. Type each line separately.

**Windows (PowerShell)**

    .venv\Scripts\python -m pip install -r Class4\requirements.txt

**macOS / Linux**

    .venv/bin/python -m pip install -r Class4/requirements.txt

Open `Class4.ipynb` in VS Code, select the `.venv` kernel, and run it from the `Class4` folder
so it can find the `prompts` folder. The whole notebook costs a fraction of a cent.

## Before Class 5

1. Write `prompts/triage_v3.md` that passes all fourteen test cases, then add one new case and
   fix it without breaking any other.
2. Add a `request_refund(order_id, reason)` tool that only accepts delivered orders.
3. Push the notebook with outputs, your three prompt files and `class4_results.json`.

## solution the home task 
# AI Engineering MasterClass - Class 4 Lab
### Generation Control, Production Prompting & Tool Calling

This repository contains the completed tasks and homework for **Class 4 Lab** (Support Bot for an online shop in Bangladesh).

---

## 📌 Completed Homework Tasks (Before Class 5)

### 1. Prompt Versioning & Evaluation (`triage_v3.md`)
- **Fixes in v3:**
  - Resolved the legacy 4-digit order regression (e.g. `৪৫৬৭` converted to `4567` without an English letter is properly accepted).
  - Enforced uppercase order letters (e.g. `m4040` -> `M4040`).
  - Added a new 15th tricky edge case (rude delivery rider behavior query correctly classified as `other`, rather than over-generalized to `payment`).
- **Evaluation Results:**
  - `prompt v1`: 11/14 correct
  - `prompt v2`: 14/14 correct
  - `prompt v3`: **15/15 correct** (All cases passed!)

---

### 2. Second Tool: `request_refund(order_id, reason)`
Implemented a second tool following the **"Your code is the Gatekeeper"** pattern:
- **Business Logic:** Strictly checks database status and only accepts refund requests if the order status is `delivered`.
- **Demonstration:**
  - **Accepted Call:** Order `B7781` (Status: `delivered`) -> Refund accepted.
  - **Refused Call:** Order `A1234` (Status: `in transit`) -> Refund refused gracefully with an informative message.

---

## 📁 Repository Structure
