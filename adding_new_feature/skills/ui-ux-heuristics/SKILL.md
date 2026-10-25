---
name: ui-ux-heuristics
description: Apply Nielsen's 10 usability heuristics whenever designing, building, or reviewing any user interface: websites, apps, dashboards, forms, prototypes, or internal tools.
---

# UI/UX Rules: Nielsen's 10 Usability Heuristics

- **Building UI:** apply all 10 rules, then re-check each one before delivering.
- **Reviewing UI:** report problems in the review format at the end.
- Don't list which rules you applied unless asked.

## 1. Visibility of system status
- Default: loading states, feedback on click, success messages, show where the user is.
- Disable buttons while processing ("Saving…" → "Saved ✓") to stop double clicks.
- Success messages include key details ("Submitted. ID: 10234").
- Show the state of the data: "Last updated 10:30 AM", "Unsaved changes", active filters, "Showing 48 of 312".

## 2. Match between the system and the real world
- Default: plain everyday labels, no field names or tech terms, text labels on unclear icons.
- Use Indian formats: dates as DD/MM/YYYY or "25 Oct 2026", ₹ with Indian grouping (₹1,25,000), 12-hour time with AM/PM.

## 3. User control and freedom
- Default: a clear way back on every screen, Cancel next to the main action.
- Modals close with ✕, the Esc key, and a click outside.
- Offer Undo for delete and bulk actions ("Deleted. Undo").
- Multi-step flows keep entered data when going back. Offer "Clear all" / "Reset filters".

## 4. Consistency and standards
- Default: same action = same label, color, icon and position; follow common conventions.
- One primary button style per screen; destructive actions always styled the same (red).
- One word per concept (don't mix "Student", "Learner" and "Candidate").

## 5. Error prevention
- Default: dropdowns/pickers for known options, validation while typing, required fields marked.
- Show format hints and limits before input ("10-digit mobile number", "Max 5 MB"). If a button is disabled, show why.
- Confirm destructive actions and say exactly what will happen ("Delete 12 students? This can't be undone.").
- Autosave long forms and drafts.

## 6. Recognition rather than recall
- Default: show options on screen, keep field labels visible (not placeholder-only).
- Show names alongside IDs or codes.
- Keep selected filters visible and show a summary before the final confirm.
- Offer autocomplete and recently used items.

## 7. Flexibility and efficiency of use
- Default: a simple path for beginners, keyboard support (Enter, Esc, logical Tab order).
- Lists and tables with more than ~10 items get search, filter, and sort.
- Dashboards: let users choose the parameters (date range, group, category, metric) instead of only fixed pre-built views.
- Remember the user's last-used filters and settings. Offer bulk actions for repeated tasks.

## 8. Aesthetic and minimalist design
- Default: one main purpose and one main action per screen; no decoration or repeated text.
- Key information first; details behind "Show more", tabs, or expandable rows.
- Build hierarchy with size, weight, spacing, and position, not boxes and borders around everything.
- Dashboards: a few high-value numbers and charts, not a wall of cards or text-heavy panels.

## 9. Help users recognize, diagnose, and recover from errors
- Default: say what went wrong + how to fix it, next to the field, keep what was entered, no raw error codes, don't blame the user.
- Always offer a next step: Retry, Resend OTP, Go to home, Contact support.
- Empty states say why it's empty and what to do ("No students match these filters. Clear filters").

## 10. Help and documentation
- Default: the UI works without help; help sits next to where it's needed.
- Use helper text, ⓘ tooltips for unfamiliar terms, and examples ("e.g. SBIN0001234").
- First-time use: a short, skippable intro or a guiding empty state.
- Complex tools: a small searchable FAQ written as task steps.

---

## Review format

Report problems sorted from highest severity to lowest:

| # | Problem | Where | Rule broken | Severity | Fix |
|---|---|---|---|---|---|

Severity: **4 Critical** (users can't finish the task, fix before release) · **3 Major** (users struggle or make mistakes, fix soon) · **2 Minor** (slows users a little) · **1 Cosmetic** (looks off, no effect on use).
