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
  pro-rata, amounts from the SVC sheet).
- Notes block: what is payable on exit under the Maldives Employment Act (AL, weekly off, PH, R&R, sick/EL not paid, SVC, timing).
- Part B (all staff): pending AL + R&R + day off and value (leave liability) per currency.
- Weekly off earned = (total days – AL – SL – EL – PL – NP) ÷ 7 from 01-Jan-26, less OFF + PDO taken.
- FC DASHBOARD control 19 counts F&F REDs; COMPLIANCE REVIEW rows 17 and 23 link to this tab.

## Environment notes
- Recalculate with the xlsx skill's `scripts/recalc.py`. If LibreOffice hangs even on a tiny file, `libreoffice-calc` is missing:
  `apt-get install -y libreoffice-calc`. Do not `pkill -f soffice` from a shell whose own command line contains "soffice".
- openpyxl needs `pillow` installed or the logos are dropped on save. EMPLOYEE TRACK B6 Emp# drop-down must be re-added after
  saving (openpyxl drops x14 validations).

## Work log
- 04-Oct-26: Sep-26 tracker built – controls, compliance review, Keplar findings, ATT DATA Jan-25…Sep-26 (Sep-25 missing),
  1012 opening balance and R&R, proposed Oct-26 NP adjustments (net USD -505 / MVR +329).
- 05-Oct-26: F&F SETTLEMENT tab added (draft); LEAVE APPLICATION CHECK notice check fixed for blank dates.

## Open items
- User to review the F&F draft (off-day rule, PH in lieu, SVC note wording).
- HR: enter leavers (2051, 4025, 5016 and staff not Active) with last working days; confirm currency for 1002, 1003, 4028.
- 38 joining dates missing; 111 AL b/f not confirmed; Sep-25 attendance summary; non-eligible 2026 AL list; CL 5 days in SETUP.
- Next month: roll SETUP to Oct-26 and load Oct-26 attendance / payroll.
