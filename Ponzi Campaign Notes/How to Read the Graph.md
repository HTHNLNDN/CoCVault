---
type: meta
tags: [meta]
---
# How to Read the Graph

← [[00 Campaign Home|Home]] · [[Open Threads and Clues]]

The graph opens as a **case web**: every loose thread plus every person, so you can see which people are tangled in which mysteries. Journal entries, places, items and hub pages are left out by default. The journal and hub pages link to everything and turn the graph into a hairball.

## Colour legend
| Colour | Meaning |
|---|---|
| 🔴 Red | **Open** thread |
| 🟠 Orange | Thread **in progress** (partly answered) |
| 🟢 Green | **Resolved** thread |
| ⚫ Dark slate | **Dead-end** thread, or a **dead** character |
| 🔵 Blue | The party |
| 🟢 Teal | Other people (NPCs) |
| 🟤 Brown | Places |
| 🟣 Violet | Mythos & creatures |
| ⚪ Grey | Items, factions, spells |

Big red nodes with many lines are the biggest open mysteries. Follow a red node's lines to see everyone and everything involved.

## Good ways to look at it
Paste one of these into the graph's **Filters → Search files** box:

| View | Filter |
|---|---|
| **Case web** (default): threads + people | `path:"Threads/" OR path:"People/"` |
| Only threads (how mysteries connect) | `path:"Threads/"` |
| Only what's still open | `path:"Threads/" [status:open]` |
| Clue web: everything except the journal and hub pages | `-path:Journal -path:Indexes -path:Handouts -file:"00 Campaign Home" -file:Timeline -file:"Transcription Notes" -file:"Open Threads and Clues" -file:"Investigation Board" -file:"How to Read the Graph" -file:README` |
| Everything, journal included | *(empty)* |

- **One mystery at a time:** open a thread (e.g. [[Identity of Mr. J]]) and open its **local graph** from the ⋯ menu. At depth 2 you see everyone and everything tangled in it, including places and items.
- Every person, place and item note has a **Threads** table at the bottom showing the live status of each mystery it's part of.
- The **[[Case Board.base|Case Board]]** has the same information as tables: open threads grouped by arc, everything in progress, resolved threads, dead ends, and the cast grouped by alive/dead/missing/captive/unknown.

## Keeping it up to date (works on iPhone)
- **A thread changes:** open it, tap the `status` property and set `open`, `partial`, `resolved` or `dead-end`. Add a line of evidence with the session it came from. The colour and the Case Board update by themselves.
- **Someone dies, vanishes or gets caught:** set the `state` property on their note to `alive`, `dead`, `missing`, `captive` or `unknown`.
- **A new mystery:** copy any thread note (⋯ → Make a copy), rename it and fill it in.

## If the colours don't show
The colour settings live in `.obsidian/graph.json` at the root of the repo, so they only load if you open the **repo folder** as your vault. Otherwise, open graph settings → **Groups** and add these queries with the colours above, in this order:

```
path:"Threads/" [status:open]
path:"Threads/" [status:partial]
path:"Threads/" [status:resolved]
path:"Threads/" [status:"dead-end"]
path:"People/" [state:dead]
path:"People/Party"
path:"People/"
path:Places
path:"Mythos & Creatures"
```
and paste the **Case web** filter from the table above into **Filters → Search files**.
