# ✅ Task Management App

> An Angular application for managing tasks per user — select a user, view their tasks, add new ones, and mark them as complete.

---

## 📌 Description

A multi-component Angular app that implements a simple task management system. Users are listed in a sidebar; selecting one reveals their personal task list. New tasks can be added via a modal dialog, and existing ones can be marked as completed.

---

## 🧩 Components

| Component | Role |
|---|---|
| `app-header` | Top navigation bar with logo and app title |
| `app-user` | User card with avatar and selection highlight |
| `app-tasks` | Task list for the selected user |
| `app-task` | Individual task card (title, due date, summary) |
| `app-new-task` | Modal dialog form for adding a new task |
| `app-card` | Reusable card wrapper component |

---

## 🔁 App Flow

```
Select user → View their tasks → Add task (modal) → Complete task
```

1. Users are rendered in a sidebar via `@for`
2. Clicking a user sets `selectedUserId` and displays their tasks
3. Clicking **Add Task** opens a `<dialog>` modal
4. Submitting the form creates a new task linked to the user
5. Clicking **Complete** removes the task from the list

---

## 🛠️ Tech Stack

![Angular](https://img.shields.io/badge/Angular-18-red?logo=angular)
![TypeScript](https://img.shields.io/badge/TypeScript-5.5-blue?logo=typescript)

| Feature | Implementation |
|---|---|
| Component input | `@Input()` — `user`, `userId`, `name`, `task`, `selected` |
| Component output | `@Output()` — `select`, `close` |
| Two-way binding | `ngModel` (title, summary, due date) |
| Conditional rendering | `@if` / `@else` |
| List rendering | `@for` with `track` |
| Class binding | `[class.active]="selected"` |
| Date formatting | `date: 'fullDate'` pipe |
| Modal | Native HTML `<dialog>` + backdrop overlay |

---

## ⚙️ Installation & Usage

```bash
npm install
ng serve
```

Then open `http://localhost:4200` in your browser.

---

## 🗂️ Project Structure

```
📁 task-management/
├── src/
│   └── app/
│       ├── app.component.*          # Root — user list + task panel
│       ├── header/                  # App header
│       ├── user/                    # User card component
│       ├── tasks/                   # Task list component
│       ├── task/                    # Single task card
│       ├── new-task/                # Add task modal
│       └── card/                    # Reusable card wrapper
└── public/
    └── users/                       # User avatar images
```
