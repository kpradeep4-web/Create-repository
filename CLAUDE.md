# Project memory – Finance workspace (Ecoboo Maldives)

User: Kalluri Saidachari, Financial Controller, Ecoboo Maldives Pvt Ltd (V. Thinadhoo). Emp# 1012.
Read this first in every session. Update the "Work log" and "Open items" at the end of each session.

## Attendance tracker – `ATTENDANCE TRACKER 2026 - PAYROLL vs KEPLAR (SEP-26).xlsx`
The user uploads the latest copy each session. Always edit the uploaded copy and keep its conventions:
- Font Book Antiqua 9 (titles 14 / 12 bold purple `6D3063`), purple header row with white bold text, thin borders,
  yellow `FFF2CC` = input cells HR/Payroll fill. Rows 1–4 = company name / address / title / instruction; logo top right.
- Sign-off block on every sheet: Prepared by AP / Payroll · Checked by Kalluri Saidachari, Financial Controller · Approved by Co/Founder.
- Use formulas only (no hard-coded results). Staff rows 7–178 line up across STAFF MASTER, LEAVE BALANCES, OPENING BAL & R&R and MONTH CONTROL.

Key sheets: SETUP (payroll month B7, period 21st–20th, leave entitlements C16:C22, daily divisor B30 = 30, PH factor B29 = 0.5,
today B11), ATT DATA (one row per staff per month: PH, P, OFF, AL, NP, PDO, SL, EL, PL, Total, Basic USD, Basic MVR, Source),
LEAVE BALANCES, OPENING BAL & R&R, MONTH CONTROL, FC DASHBOARD (controls 1–19), COMPLIANCE REVIEW, ADJUSTMENTS & NOTES,
LEAVE APPLICATION CHECK, F&F SETTLEMENT, PASTE PAYROLL REG / PASTE KEPLAR ATT / PASTE KEPLAR LEAVE, HOW TO (MANASA & HR).

Business rules:
- Final attendance = HR/Payroll (Manasa) monthly Attendance Summary. Keplar is a reference only; HR must make Keplar agree.
- Attendance period 21st → 20th; salary paid for the full calendar month. Service charge (SVC) paid one month behind
  (Oct payroll pays Sep SVC).
- AL 30 days/yr accrues 2.5 days/month; SL 30; EL 10; PL 3; ML 60. NP deducted at basic ÷ 30 per day. PH premium = basic ÷ 30 × 0.5.
- HR policy email 28-Dec-25 (Sansala): 2025 AL / PDO not carried forward, except balances HR acknowledged in writing
  (1012: 30 days). Flagged in COMPLIANCE REVIEW as conflicting with the Employment Act (earned leave must be paid, not forfeited).
- 1012: joined 04-Oct-24; designation Financial Controller from 01-Oct-26; no leave of any kind taken since joining;
  R&R 7 days per 6-month period, only the R&R cash allowance (USD 600) was paid.

F&F SETTLEMENT tab (added 05-Oct-26):
- Part A (leavers, rows 8–27): HR enters Emp#, separation type, last working day, AL not yet in ATT DATA, off-day adjustment,
  PH days in lieu, other days, F&F paid date. Pays AL balance + R&R + pending weekly off/PDO + PH in lieu + other, × basic ÷ 30.
  Due date = last day + 7 (Employment Act). Negative AL = recover. Column AC = SVC note (previous month full + leaving month
  pro-rata, amounts from the SVC sheet). Column AD = monthly leave-pay base if not basic (e.g. basic + MWA); blank = basic.
  Hidden column AE = as-at date (last day, else SETUP period end) so a row fills in as soon as an Emp# is typed.
- Notes block: what is payable on exit under the Maldives Employment Act (AL, weekly off, PH, R&R, sick/EL not paid, SVC, timing).
- Part B (all staff): pending AL + R&R + day off and value (leave liability) per currency.
- Part A counts SINCE JOINING (FC instruction 05-Oct-26), using ATT DATA history from SETUP B13 = 01-Jan-25:
  AL earned = 2.5 × COMPLETED months from MAX(joining, 01-Jan-25) to last day (DATEDIF, same as the F&F model) – all AL taken
  since then + HR adjustment (K: + balance before Jan-25 / – AL not yet in ATT DATA). Weekly off earned = (total days – AL – SL
  – EL – PL – NP) ÷ 7 over the same window, less all OFF + PDO taken. Part B (liability) still uses 2026 YTD balances.
- FC DASHBOARD control 19 counts F&F REDs; COMPLIANCE REVIEW rows 17 and 23 link to this tab.

LEAVE STATEMENT tab (05-Oct-26): one employee (D6 Emp#, D7 last day). Month-by-month since joining (or from 01-Jan-26 when
HR opening balance exists): attendance, AL earned (completed months)/taken/running balance, off earned (1 in 7)/OFF+PDO taken/
running balance, PH worked with Yes/No "paid in payroll" per month → PH pending. Summary: opening balance 31-Dec-25 (OPENING BAL
D = AL, new U = day off, new V = PH), earned, taken, F&F adjustments, pending days and value; agreement check with F&F part A;
service-charge block (SVC and tips: previous month full + last-day month pro-rata, rows 20–23): column M = SVC amount typed manually (overrides per-head × days), N = already paid Yes/No, O = due in F&F. Draft v7.
Rule from FC: if an HR opening balance is entered, F&F = opening balance + 2026 earned – 2026 taken; else count since joining.

F&F STATEMENT tab (05-Oct-26): printable A4 statement in the same layout as the per-employee F&F model, driven by
LEAVE STATEMENT D6/D7. Earnings: final-period salary (last day – "salary paid up to" – no-pay after cut-off) on basic +
fixed allowances, PH not paid, AL, day off/PDO, R&R/other, notice in lieu, SVC, tips, arrears; deductions: MRPS 7% (Maldivian,
on basic), EWT and recoveries (typed); bank, clearance, signatories. Inputs in yellow panel I:L (not printed); helper N51 =
salary days. Tested: 4025 → MVR 9,000 (matches F&F file); 1013 → USD 868.57 before SVC/tips. Draft v8.

## Per-employee F&F model – `ECOBOO_FF_SETTLEMENT-<EMP#>-<NAME>-<MON-YY>.xlsx`
Tabs README, SETUP (Act parameters, MRPS 7%+7% Maldivians, MIRA EWT slabs, notice table, QB accounts, rate 15.42),
INPUT (yellow), CALC, F&F STATEMENT (A4), CHECKS (PASS/INFO/ALERT/PENDING/FAIL), QB JV, REGISTER.
Leave pay base there = basic + MWA (fixed allowances flagged "Leave / notice base"); salary paid for the full calendar
month in payroll, so F&F pays only days after the paid month. 4025 Hussain Samin: joined 28-Dec-25, resigned, LWD 30-Sep-26,
22.5 days AL = MVR 9,000; Sep SVC/tips pending; due 07-Oct-26. Tracker F&F tab agrees (MVR 9,000).

## Environment notes
- Recalculate with the xlsx skill's `scripts/recalc.py`. If LibreOffice hangs even on a tiny file, `libreoffice-calc` is missing:
  `apt-get install -y libreoffice-calc`. Do not `pkill -f soffice` from a shell whose own command line contains "soffice".
- openpyxl needs `pillow` installed or the logos are dropped on save. EMPLOYEE TRACK B6 Emp# drop-down must be re-added after
  saving (openpyxl drops x14 validations).

## Work log
- 04-Oct-26: Sep-26 tracker built – controls, compliance review, Keplar findings, ATT DATA Jan-25…Sep-26 (Sep-25 missing),
  1012 opening balance and R&R, proposed Oct-26 NP adjustments (net USD -505 / MVR +329).
- 05-Oct-26: F&F SETTLEMENT tab added (draft v3); LEAVE APPLICATION CHECK notice check fixed for blank dates.
  Leavers entered: 4025 (LWD 30-Sep-26, base MVR 12,000 → 22.5 days = MVR 9,000) and 1013 Manasa Kaveti
  (LWD 06-Oct-26, due 13-Oct-26: AL 50 earned – 31 taken = 19.0 + day off 7.57 = 26.57 days = USD 708.57 on basic 800). Draft v5.
  5 PH-worked months for 1013 need Yes/No; Sep-25 and Oct-26 attendance missing; Jan–Apr 2025 show no off days.
  4025 joining date 28-Dec-25 added to STAFF MASTER. Reviewed the 4025 F&F model file.

## Open items
- User to review the F&F draft (off-day rule, PH in lieu, SVC note wording).
- Decide the leave-pay / no-pay daily base for staff with MWA: basic only (tracker) or basic + MWA (F&F model, Sep payroll NP).
- 1013 F&F: needs separation type, Oct attendance 21-Sep to 06-Oct, salary components, nationality, bank, clearance.
- 4025: pay MVR 9,000 by 07-Oct-26; designation/department differ (tracker Tour Guide / RECREATION vs F&F
  Public Relation and Entertainment Associate / Sales and Marketing).
- HR: enter leavers (2051, 4025, 5016 and staff not Active) with last working days; confirm currency for 1002, 1003, 4028.
- 38 joining dates missing; 111 AL b/f not confirmed; Sep-25 attendance summary; non-eligible 2026 AL list; CL 5 days in SETUP.
- Next month: roll SETUP to Oct-26 and load Oct-26 attendance / payroll.
