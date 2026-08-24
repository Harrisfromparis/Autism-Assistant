# Student Learning Path

Screen: Student's personalised learning path view  
Mode: Mobile (375×812)  
Tool: Draftboard (edit via MCP server at http://localhost:3030/mcp)

---

## Layout

```
┌─────────────────────────┐
│  ← Back     iLEARN  🔔  │  ← Top Bar
├─────────────────────────┤
│  Hi, Alex! 👋            │
│  Keep going – you're    │
│  doing great!           │
│                         │
│  ████████░░░░  60%      │  ← Overall Progress Bar
│  6 of 10 lessons done   │
├─────────────────────────┤
│  Your Learning Path     │
│                         │
│  ✅ Lesson 1 – Intro     │  ← Completed (green check)
│  ✅ Lesson 2 – Sounds    │
│  ✅ Lesson 3 – Words     │
│  ▶️  Lesson 4 – Phrases  │  ← Current (highlighted)
│  🔒 Lesson 5 – Sentences │  ← Locked
│  🔒 Lesson 6 – Stories   │
├─────────────────────────┤
│  [  Start Lesson 4  ]   │  ← CTA Button
├─────────────────────────┤
│  🏅 Latest Badge         │
│  ┌───────────────────┐  │
│  │ 🌟 Word Explorer  │  │
│  │ Earned yesterday  │  │
│  └───────────────────┘  │
└─────────────────────────┘
```

## Components

- **Top Bar**: Back button, logo, notification bell
- **Greeting**: Personalised motivational message
- **Overall Progress Bar**: Filled percentage + lesson count
- **Lesson List**: Completed (✅), current (▶️ highlighted), locked (🔒)
- **CTA Button**: "Start Lesson N" – always points to the current lesson
- **Latest Badge**: Most recently earned achievement badge

## AI Agent Instructions

When editing this screen via Draftboard MCP:
- The current lesson row should have a distinct background (#EEF2FF) and bold text.
- Locked lessons should be greyed out (opacity 0.4).
- The CTA button should use the primary brand colour (#4F46E5) and full width.
- Motivational messages should rotate from a predefined list stored in the app config.
