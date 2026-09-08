# AppointFlow — Team Appointment Board

A single self-contained web page (`index.html`) — open it in any browser, no install or server required.

## How it works

- **Board view**: appointments are grouped by date and sorted by start time. Each row shows the time range, title, description, and a status badge (Scheduled / Completed / Cancelled).
- **Filters**: the toolbar filters by a specific date and/or status. "Clear filters" resets both.
- **Add appointment**: the "+ Add appointment" button opens a form for title, description (optional), date, start time, and end time.
- **Validation**, checked on submit:
  1. Title, date, start time, and end time are required.
  2. End time must be after start time.
  3. The new time slot can't overlap an existing **non-cancelled** appointment on the same date. If it does, the error names the conflicting appointment and its time, so the user knows exactly what to change.
- **Edit**: reopens the same form pre-filled; the same validation runs, excluding the appointment being edited from its own overlap check.
- **Cancel**: asks for inline confirmation, then marks the appointment "Cancelled." Cancelled appointments stay on the board (struck-through, dimmed, red badge) rather than being deleted, and their time slot becomes available again for new bookings.
- **Complete**: marks a scheduled appointment "Completed."
- **Restore**: a cancelled appointment can be moved back to "Scheduled" (subject to the same overlap check, since another appointment may have taken its slot in the meantime).
- **Feedback**: every add/edit/complete/cancel/restore action shows a toast in the top-right corner confirming what happened; validation errors appear inline next to the relevant field plus a summary banner at the top of the form.
- Six sample appointments across three days (today and the following two days) and all three statuses are preloaded so the board is reviewable immediately.



## Possible next steps

- A real backend (e.g., Node/Express + a database) so the board persists and is shared live across the team, with the same validation enforced server-side.
- Multi-day/week calendar-grid view as an alternative to the list view.
- Assigning appointments to specific team members with per-person filtering.
