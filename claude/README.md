# Claude companion — voice sessions for the Mood Log

Files that keep Claude on track when you fill out TEAM-CBT logs **by talking**
— e.g. in the car — and get a result you can import straight into the app.

## What's here

| File | Purpose |
|---|---|
| `VOICE-SESSION.md` | The master protocol: Claude's role, driving-mode rules, step-by-step flows for all four tools, Devil's Advocate rules, and the JSON handoff contract. |
| `REFERENCE.md` | The 10 distortions (negative + positive faces, with codes), emotion clusters, coaching techniques, TEAM in one breath. |
| `schema/entry-schema.json` | Exact JSON format Claude must output at session end — matches the app's **Data → Import**. |
| `schema/example-dml.json` | A worked Daily Mood Log entry. |
| `schema/example-habit.json` | A worked Habits & Addictions entry. |

## Setup (Claude mobile app — recommended for driving)

1. In the Claude app, create a **Project** called e.g. *Mood Log sessions*.
2. Add all five files to the project's knowledge.
3. Optionally set the project's custom instructions to one line:
   *"Follow VOICE-SESSION.md for every conversation in this project."*
4. In the car: open the project, start a **voice** conversation, and say
   something like *"Let's do a daily mood log"* or *"I'm fighting a craving —
   habits log please."*

Claude will interview you one question at a time, capture thoughts verbatim,
and at the end put a ```json block in the chat.

## Getting the session into the app

When you're parked: copy the JSON block → Mood Log app → **Data → Import** →
paste → Import. The importer accepts the fenced block as-is, so you don't need
to trim the ``` marks.

It works the other direction too: in any entry in the app, the **⋯ menu →
Copy for Claude** produces a formatted version of the entry plus instructions,
ready to paste into a chat for a deeper working-through.

## Also works in Claude Code

Point a session at this folder ("read the claude/ folder of the mood log
project, then run a voice-style DML session with me") — the same files apply.

## A note on safety

`VOICE-SESSION.md` instructs Claude to stop the exercise and point to real
help if you're in crisis, and to never write your "loving responses" for you
(per Burns, borrowed comebacks don't work). Those two rules are load-bearing —
keep them if you edit the files.
