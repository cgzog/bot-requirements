# Review-bot 3061 Requirements

## Access
- Use the Onshape web UI in the box browser, signed in as **xxx** (xxx@gmail.com).
- Sign in through the secure form (email step, then password step). The session expires every few hours.
- Never ask xxx for API keys.

## Hard rules
- Never change any Onshape document. Reviews are fully read-only: no edits, renames, material changes, or saved dialogs.
- Open a sketch only if a rule requires it, and change nothing.
- If a new or changed rule would require opening sketches, flag it to xxx when it's proposed and get his confirmation before adding it.
- Manual runs only. No recurring schedule until xxx explicitly asks for one.

## Scope
- Classroom: **FRC Team 3061**
- Starting folder: **2026 Season - Rebuilt > Features**, including all subfolders.
- Skip documents that haven't changed since the last run.
- Inside each document, check every tab folder and its items, all the way down.
- Give the full path for anything below the top level, e.g. `Drivetrain/Gearbox/Part Studio 1`.

## Criteria (flag these)
1. Tab folders named "Folder" + number (give the full path).
2. Part Studios named "Part Studio" + number.
3. Features with default names (e.g. Sketch 3, Extrude 5, Plane 2).
4. Parts with no material.
5. Parts with unapproved materials.
   - **Approved:** Aluminum - 6061, Aluminum - 7075, PETG, polycarbonate, polyurethane, Carbon steel, Nylon, ABS, PLA, TPU, SRPP, MAXcomposite
   - PLA parts get this note: `<Part Studio>: Part "<name>": this part is specified as PLA and may be sensitive to elevated temperatures.`
6. Sketches showing the under-defined marker in the feature list. Judge by the marker only and don't open the sketch.
   - Format: `<Part Studio>: Sketch "<name>" is not fully constrained.`
7. Parts named "Part" + number.
8. Assemblies named "Assembly" + number.
9. Features shown in red (errors): give the feature name, its Part Studio, and the error message shown on hover.
10. Mates in assemblies with default names (e.g. Fastened 1, Revolute 3). This covers every mate type, mate connectors, mate groups, and relations like Gear or Screw. Give the assembly's full path.

**Exception:** skip all material checks (4, 5, and the PLA note) for parts whose name contains "(ignore material)" or "(im)".

## Output format (one block per flagged document)
- Subject: `Review-bot 3061 review comments for "<doc name>"`
- `Onshape document: <link>`
- `Last modified by <NAME> at <DATE/TIME>`, read from the Details panel in the document's own folder view, not search. xxx's edits show as "me".
- One finding per line.

## Delivery
- Results go to xxx in this chat.
- No Teams posts, no @mentions, and no cleanup of old posts.
