# Teacher Dashboard

Screen: Teacher home screen  
Mode: Desktop (1440×900)  
Tool: Draftboard (edit via MCP server at http://localhost:3030/mcp)

---

## Layout

```
┌─────────────────────────────────────────────────────────────┐
│  iLEARN          [🔔 Notifications]  [👤 Ms. Harris]        │  ← Top Nav
├──────────┬──────────────────────────────────────────────────┤
│          │  Good morning, Ms. Harris 👋                      │
│  Nav     │                                                   │
│          │  ┌──────────┐  ┌──────────┐  ┌──────────┐       │
│  🏠 Home │  │ 📊        │  │ 🎓        │  │ ⏱         │       │  ← KPI Cards
│  📚 Class│  │Attendance │  │ Progress  │  │Engagement│       │
│  📈 Stats│  │   94%     │  │   78%     │  │   High   │       │
│  ⚙️ Settings  │  └──────────┘  └──────────┘  └──────────┘  │
│          │                                                   │
│          │  Class List                    [+ Add Student]   │  ← Class List
│          │  ┌─────────────────────────────────────────────┐ │
│          │  │ 👤 Alex B.    Lesson 4/10  ████░░  40%      │ │
│          │  │ 👤 Sam T.     Lesson 7/10  ███████░ 70%     │ │
│          │  │ 👤 Jordan M.  Lesson 2/10  ██░░░░  20%      │ │
│          │  └─────────────────────────────────────────────┘ │
│          │                                                   │
│          │  Upcoming Sessions                               │  ← Scheduler
│          │  ┌─────────────────────────────────────────────┐ │
│          │  │ Mon 10:00  Group A – Social Skills           │ │
│          │  │ Tue 14:00  1:1 – Alex B. (Speech & Lang.)   │ │
│          │  └─────────────────────────────────────────────┘ │
└──────────┴──────────────────────────────────────────────────┘
```

## Components

- **Top Nav**: Logo, notification bell, user avatar + name
- **Sidebar Nav**: Home, Class, Stats, Settings
- **KPI Cards (×3)**: Attendance %, Progress %, Engagement level
- **Class List**: Student avatar, name, current lesson, progress bar
- **Upcoming Sessions**: Date/time, group or 1:1 label, session title

## AI Agent Instructions

When editing this screen via Draftboard MCP:
- Keep KPI cards in a 3-column row at the top of the main content area.
- Progress bars in the class list should use the iLEARN brand colour (#4F46E5).
- Session cards should be sorted by date ascending.
