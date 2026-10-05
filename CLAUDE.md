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

F&F SETTLEMENT tab – ONE simple page (v9, 05-Oct-26; FC said three tabs were too complex – F&F SETTLEMENT / LEAVE
STATEMENT / F&F STATEMENT were replaced by this single tab). One employee at a time, A4 portrait, print area A1:H59:
- A (rows 7–14) yellow inputs C7 Emp#, C8 last working day, C9 separation type, C10 nationality, C11 salary paid up to
  (default EOMONTH(SETUP B7)), C12 no-pay days after cut-off, C13 fixed allowances, C14 leave-pay base (blank = basic);
  right side auto: name, dept/designation, joining, service, basic/ccy, daily rate, basis, payable by (last day + 7).
- B (rows 18–22) pending leave since joining: opening 31-Dec-25 (OPENING BAL D/U/V, used only when D is filled → then
  counts from 01-Jan-26), earned, taken, HR adjustment (yellow), pending days, amount. AL = 2.5 × completed months
  (DATEDIF); day off = (total – AL – SL – EL – PL – NP) ÷ 7 less OFF + PDO; PH worked vs "paid" (yellow, defaults to all
  worked = paid at 1.5× in payroll); R&R from OPENING BAL G/H/I/L.
- C (rows 27–30) SVC and tips: previous month full + leaving month to last day, amounts typed in G (USD).
- D (rows 36–51) final settlement: salary days (hidden helper O18 = last day – paid up to – no-pay), allowances, leave
  items, SVC, tips, other earnings (typed); MRPS 7% (Maldivian), EWT and recoveries typed as negatives; NET.
- F (row 62+) month-by-month working (AL earned / balance, off earned / balance). Hidden helpers in column O (labels P).
- Tested: 1013 → AL 19.0 + day off 7.57 = 26.57 days USD 708.57 + 6 days salary 160 = USD 868.57 (SVC/tips pending);
  4025 → MVR 9,000 (matches F&F model). FC DASHBOARD has no F&F control (row 25 not used).
- Deliver the LibreOffice-recalculated file (values visible in any viewer); preview a page by converting a values-only
  copy of the tab to PDF and pdftoppm.

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
- 05-Oct-26: F&F work – final version v9 = single simple F&F SETTLEMENT tab (earlier drafts v1–v8 superseded); LEAVE APPLICATION CHECK notice check fixed for blank dates.
  Leavers entered: 4025 (LWD 30-Sep-26, base MVR 12,000 → 22.5 days = MVR 9,000) and 1013 Manasa Kaveti
  (LWD 06-Oct-26, due 13-Oct-26: AL 50 earned – 31 taken = 19.0 + day off 7.57 = 26.57 days = USD 708.57 on basic 800). Draft v5.
  5 PH-worked months for 1013 need Yes/No; Sep-25 and Oct-26 attendance missing; Jan–Apr 2025 show no off days.
  4025 joining date 28-Dec-25 added to STAFF MASTER. Reviewed the 4025 F&F model file.

## Open items
- User to review F&F v9 (single tab).
- Decide the leave-pay / no-pay daily base for staff with MWA: basic only (tracker) or basic + MWA (F&F model, Sep payroll NP).
- 1013 F&F: needs separation type, Oct attendance 21-Sep to 06-Oct, salary components, nationality, bank, clearance.
- 4025: pay MVR 9,000 by 07-Oct-26; designation/department differ (tracker Tour Guide / RECREATION vs F&F
  Public Relation and Entertainment Associate / Sales and Marketing).
- HR: enter leavers (2051, 4025, 5016 and staff not Active) with last working days; confirm currency for 1002, 1003, 4028.
- 38 joining dates missing; 111 AL b/f not confirmed; Sep-25 attendance summary; non-eligible 2026 AL list; CL 5 days in SETUP.
- Next month: roll SETUP to Oct-26 and load Oct-26 attendance / payroll.
