# Progress Tracker

Screen: Per-student progress and KPI tracker (teacher view)  
Mode: Desktop (1440×900)  
Tool: Draftboard (edit via MCP server at http://localhost:3030/mcp)

---

## Layout

```
┌─────────────────────────────────────────────────────────────┐
│  iLEARN  >  Class  >  Alex B.           [Export PDF]  [⚙️]  │  ← Breadcrumb + Actions
├─────────────────────────────────────────────────────────────┤
│  👤 Alex B.   Age: 9   Programme: Speech & Language         │  ← Student Header
│  Teacher: Ms. Harris   Started: Jan 2026                    │
├───────────────────┬─────────────────────────────────────────┤
│  Overview         │  ┌────────┐ ┌────────┐ ┌────────────┐  │
│                   │  │Lessons │ │Sessions│ │Avg. Score  │  │  ← KPI Row
│  Weekly           │  │ 4/10   │ │  12    │ │   82%      │  │
│  Monthly          │  └────────┘ └────────┘ └────────────┘  │
│  All Time         │                                         │
│                   │  Progress Over Time          [Line Chart]│
│                   │  ┌─────────────────────────────────────┐│
│                   │  │                              ╱       ││
│                   │  │                         ╱──╱        ││
│                   │  │                   ╱────╯             ││
│                   │  │  Jan   Feb   Mar  Apr  May  Jun      ││
│                   │  └─────────────────────────────────────┘│
│                   │                                         │
│                   │  Session Notes                          │
│                   │  ┌─────────────────────────────────────┐│
│                   │  │ 22 Aug – Good focus, completed L4   ││
│                   │  │ 15 Aug – Struggled with blends      ││
│                   │  │ [+ Add Note]                        ││
│                   │  └─────────────────────────────────────┘│
└───────────────────┴─────────────────────────────────────────┘
```

## Components

- **Breadcrumb**: iLEARN > Class > Student Name
- **Actions**: Export PDF, Settings
- **Student Header**: Avatar, name, age, programme, teacher, start date
- **Time Filter Sidebar**: Overview / Weekly / Monthly / All Time tabs
- **KPI Row (×3)**: Lessons completed, total sessions, average score
- **Progress Chart**: Line chart of scores over time
- **Session Notes**: Chronological notes with "Add Note" action

## AI Agent Instructions

When editing this screen via Draftboard MCP:
- The line chart should use the brand colour (#4F46E5) for the line and a light fill (#EEF2FF) beneath it.
- KPI cards follow the same 3-column layout as the Teacher Dashboard for visual consistency.
- Session notes are sorted newest-first.
- The "Export PDF" button should be prominent (top-right, secondary button style).
