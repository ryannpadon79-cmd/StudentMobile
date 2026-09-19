# Attendance System Feature Implementation TODO

## Feature 1 — Approve All / Select & Approve (Batch Approvals)
- [x] approval.html: Add "Select All" checkbox, "Approve Selected", "Approve All" buttons
- [x] js/admin.js: Add checkboxes to pending cards + `toggleSelectAll()`, `approveSelected()`, `approveAllPending()`
- [x] css/admin.css: Batch approval styles

 ## Feature 2 — Event Announcement (admin sets event name/date/time)
- [x] admin.html: Add "Event Announcement" card (Event Name, Event Date, Start Time, End Time)
- [x] js/admin.js: `saveEventAnnouncement()` / `loadEventAnnouncement()`
- [x] student.html: Display event announcement card for students
- [x] js/student.js: `loadEventAnnouncement()` + auto-fill event in modal
- [x] js/attendance.js: Auto-fill event field from announcement
- [x] css/student.css: Event announcement card styles

## Feature 3 — Per-Student Attendance Report (click profile)
- [x] courses.html & js/admin.js: Clickable student card → modal with student's attendance schedule
- [x] student.html admin list: clickable student → same report modal (js/student.js `openStudentReport`)

## Feature 4 — Late Detection (15-min grace after Time In closes)
- [x] js/student.js: Mark record as "Late" if time-in within 15 min after close window
- [x] reports.html & js/admin.js: Show "Late" badge in reports/logs
- [x] css: `badge-status-late` style in admin.css and student.css

## Feature 5 — Sentence-Case Student Names
- [x] js/admin.js: Added `toSentenceCase()` helper + applied to all name displays
- [x] js/student.js: Added `toSentenceCase()` helper + applied to all name displays

## Feature 6 — Clear/End Event (removes schedule from students)
- [x] admin.html: Add "Clear / End Event" button
- [x] js/admin.js: `clearEventAnnouncement()` removes event + schedule + sets `attendanceDisabled`
- [x] js/admin.js: `saveEventAnnouncement()` / `saveScheduleSettings()` re-enable attendance (`attendanceDisabled=false`)
- [x] js/student.js: `isAttendanceActive()` helper + hide/disable Time In/Out buttons when inactive
- [x] js/student.js: `openAttendanceModal()` blocks attendance when inactive (defense-in-depth)
- [x] js/attendance.js: legacy `submitData()` blocks attendance when inactive + stores `status` field
- [x] css/admin.css: `.btn-clear-event` style for the red "Clear / End Event" button

## Feature 7 — Admin Edit/Adjust Student Attendance Time
- [x] js/admin.js: `editStudentTime(index)` helper
- [x] js/admin.js: reports.html list — add Edit button per record
- [x] js/admin.js: `openStudentReport()` — add Edit button per row
- [x] js/student.js: `editStudentTime(index)` helper + Edit buttons in admin view
