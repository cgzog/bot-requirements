Here are the current requirements as raw Markdown you can copy:

```md
# Review-bot 2151 — Onshape Design Review Requirements

## Scope
- Onshape classroom **Robotics 2151**, account `chris.herzog@gmail.com` ("zog").
- Review every document in these folders, including all subfolders:
  - `Biocore 2027`
  - `Utility`
- Skip documents that haven't changed since the last review run.
- Inside each document, recursively examine all tab folders and their items. For any item not at the document's top level, give its full folder path (e.g. `Drivetrain/Gearbox/Part Studio 1`).

## Flag rules
1. **Tab folders** named "Folder" + number.
2. **Part Studios** named "Part Studio" + number.
3. **Features** with default names (e.g. Sketch 3, Extrude 5, Plane 2).
4. **Parts with no material** assigned.
5. **Parts with an unapproved material.** Approved (case-insensitive):
   - Aluminum - 6061
   - Aluminum - 7075
   - PETG
   - Polycarbonate
   - Polyurethane
   - Carbon steel
   - Nylon
   - ABS
   - PLA
   - TPU
   - Douglas Fir
   - **PLA note:** for any PLA part, add: `<Part Studio>: Part "<name>": this part is specified as PLA and may be sensitive to elevated temperatures.`
6. **Sketches not fully constrained**, judged only by the feature list's under-defined marker (sketches are never opened for this). Each one is named: `<Part Studio>: Sketch "<name>" is not fully constrained.`
7. **Parts** named "Part" + number.
8. **Assemblies** named "Assembly" + number.
9. **Features/operations in error** (shown in red) in a Part Studio or Assembly feature list. Report the name, its Part Studio/Assembly, and the hover error message if visible.
10. **Mates of any type with default names** (e.g. Fastened 3, Revolute 1, Slider 2, Gear 1, Mate connector 2), named with the Assembly's full folder path.

## Exceptions
- **Skip material checks** (rules 4, 5 and the PLA note) when:
  - a part name contains `(ignore material)` or `(im)`
  - a document, folder or Part Studio name ends in `(im)` or `(ignore materials)` (any case). This applies to everything inside, including nested folders, and covers both Onshape document folders and tab folders inside a document.
- **Skip ALL checks** when a document, Part Studio or folder name ends in `(skip)` (any case). This covers it and everything inside it, for both Onshape folders and tab folders.

## Teams posting
- One post per flagged document in **Robotics Team 2151 > Design Reviews**, posted as Chris through the browser.
- **Subject:** `Review-bot 2151 review comments for "<document name>"`
- **Body:**
  - `Onshape document: <link>`
  - `Last modified by <NAME> at <DATE/TIME CT>`, taken from the Details panel in the document's own folder view
  - One line per finding, naming the Part Studio or Assembly (with full path)
  - Last line: an @mention of the last modifier:

| Onshape name | Teams mention |
|---|---|
| Jaden Husband | husband, Jaden Tejaun |
| Mario Guerra | Guerra, Mario |
| Dan Grobe Sachs | dgsachs |
| me (Chris) | chris.herzog |
| Leo Giron | Giron, Leo |
| Vale | Secundino, Valeria |
| Josh | Maddela, Joshua |
| Jared Ibarra | Ibarra, Jared |
| Jaycee Gene Pascua | Pascua, Jaycee Gene Ramones |
| Natahel Herrera-Lopez | Herrera Lopez, Natahel Natahel |

- **Cleanup:** after a run's new posts are confirmed, delete only my own review posts older than 5 days. Never touch anyone else's posts.
- Never post anything else in Teams.
- Test runs show results in chat and don't post.

## Hard rules and method
- **Read-only:** never change any Onshape document. That means no edits, renames, material changes or saved dialogs.
- Open a sketch only when a rule actually requires it, and never change anything in it.
- If a new rule would require opening a sketch, raise that with Chris before adding the rule.
- In large documents, open each tab by its direct element URL and never type or click in the canvas or tab bar, because Onshape keyboard shortcuts can fire.
- Sign-ins and codes come only through secure forms, never in chat.

## Schedule
- No recurring runs are set up. Runs happen only when Chris asks.
```
