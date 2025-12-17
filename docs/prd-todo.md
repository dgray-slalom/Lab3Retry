# Product Requirements Document (PRD) - TODO App Upgrade MVP

## 1. Overview

We are upgrading the basic TODO app to support due dates, priority levels, and simple filters so users can better organize and focus on time‑sensitive tasks. The MVP remains deliberately lean and teachable: local‑only storage with no backend changes.

---

## 2. MVP Scope

- Add `dueDate` field: optional ISO `YYYY-MM-DD`; invalid values ignored (treated as absent).
- Add `priority` field: enum `"P1" | "P2" | "P3"`; default `"P3"`.
- Filters: **All**, **Today**, **Overdue**.
- Filter behavior: **All** shows completed tasks; **Today** and **Overdue** show only incomplete tasks.
- Storage: local‑only (no backend or external storage).
- Validation: `title` required.

---

## 3. Post-MVP Scope

- Overdue tasks visually highlighted (e.g., clear emphasis to stand out).
- Sorting rules: overdue first → priority (P1→P3) → due date ascending → undated last.

---

## 4. Out of Scope

- Notifications.
- Recurring tasks.
- Multi‑user.
- Keyboard navigation.
- External storage (remain local‑only).
