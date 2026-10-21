# 💀 KOK JALAN?

<p align="center">
  <img src="https://img.shields.io/badge/status-still_surviving-yellow?style=for-the-badge" alt="Status: still surviving" />
  <img src="https://img.shields.io/badge/works_on_my_machine-hopefully-success?style=for-the-badge" alt="Works on my machine, hopefully" />
  <img src="https://img.shields.io/badge/mental_health-under_review-red?style=for-the-badge" alt="Mental health under review" />
</p>

<p align="center">
  <b>Masuk project baru. Buka source code. Bengong.</b>
  <br />
  <i>"Bro, ini alurnya dari mana ke mana dah?"</i>
</p>

<p align="center">
  <img src="https://i.kym-cdn.com/photos/images/newsfeed/001/435/941/317.gif" width="400" alt="This is fine meme: the codebase is on fire" />
</p>

**KOK JALAN?** is a codebase explorer for developers who just joined a project and immediately start questioning their career choices.

It helps you understand how files are connected without manually opening 738 files, clicking random imports, and praying to Stack Overflow.

Because sometimes the code is so confusing that the only documentation left is:

```text
// DO NOT TOUCH. IT WORKS.
```

And naturally, someone will ask you to change it tomorrow.

---

## 🤨 The problem

You just joined a new company.

Your senior says:

> "Ini kesini, ini kesini, ini kesini."

tanpa kita tahu buat apanya

The flow:

```text
src/
├── common/
├── common-new/
├── common-final/
├── common-final-v2/
├── utils/
├── utils-old/
├── utils-please-dont-delete/
├── services/
├── services2/
└── index.ts
```

You open `index.ts`.

It imports another file.

That file imports five more files.

One of those files imports something from `common-final-v2`, which imports a utility from `utils-old`.

**Congratulations. You've discovered the family tree.**

<p align="center">
  <img src="https://media.tenor.com/2roX3uxz_68AAAAC/cat-space.gif" width="300" alt="Confused cat meme" />
</p>

You have three options:

- 🔍 Manually trace every import.
- 🧠 Memorize the entire codebase.
- 🗺️ Use KOK JALAN? to visualize the mess.

We both know which one sounds less painful.

---

## 🚀 What is this thing?

KOK JALAN? aims to visualize static dependencies between source files so developers can understand an unfamiliar codebase faster.

| Feature | What it does |
| --- | --- |
| 📂 File scanner | Finds source files worth investigating |
| 🧠 AST parser | Extracts imports and exports from source code |
| 🧭 Module resolver | Figures out which files those imports point to |
| 🕸️ Dependency graph | Turns file relationships into nodes and edges |
| 🎨 Interactive visualization | Lets you explore the graph instead of suffering through tabs |

*These are the planned MVP capabilities; features are still under development.*

### The vision

Turn this:

```text
"Where does this file come from?"
"Why is this imported here?"
"Can I delete this file?"
"WHO WROTE THIS?"
```

Into something a little more manageable:

```text
Component A
    │
    ▼
Service B
    │
    ├── Utility C
    │
    └── API Client D
             │
             ▼
          Types E
```

Less guessing. More understanding.

Fewer accidental production incidents.

Hopefully.

---

## 🛠️ Tech stack

Built with technologies we like and a questionable amount of curiosity.

| Technology | Responsibility |
| --- | --- |
| React + Vite | Frontend |
| TypeScript | Type safety and analyzer implementation |
| React Flow | Interactive dependency graph |
| NestJS | REST API |
| TypeScript Compiler API | AST parsing and module resolution |
| pnpm workspace | Keeping the chaos organized |
| Vitest | Testing things before they test us in production |

### Architecture

```text
KOK JALAN?
│
├── apps/
│   ├── web/              # Pretty pictures go here
│   └── api/              # Backend doing backend things
│
└── packages/
    └── analyzer/         # The actual detective
        ├── scanner/      # Find the files
        ├── parser/       # Read the code
        ├── resolver/     # Follow the imports
        └── graph/        # Connect the dots
```

The analyzer runs as a library inside the NestJS API. No extra analyzer server is required.

---

## 🏃
