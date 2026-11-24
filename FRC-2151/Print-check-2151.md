```markdown
# 3D Print File Naming Check: Requirements

## Scope
- Watch the Teams "Robotics Team 2151" > "3D Printing (sub team of Build)" channel's files under Printing > To be printed.
- Read the folder and post through the box browser, because the Teams connector doesn't work for the guest account.
- Get each file's exact name and Modified time. SharePoint shows Pacific time, so convert it to Central.

## Schedule
- Runs daily at 7, 10, 13, 16, 19 and 22 CT.
- Each run may start up to 15 minutes early or late.

## Naming rules
- The format is `name - material - mode - color`, then an optional count.
- A space or a hyphen can come before the count.
- The name can't contain hyphens.
- The material is PLA or PETG.
- The mode is Functional or Prototype.
- The color is a conventional color name or "any".
- The count is optional. When present, it is "X", an optional space, and a whole number.
- An X with no number, a number with no X, or a decimal is an error.
- Extra or missing spaces are OK.
- Checks ignore case and the file extension.

## New files
A file counts as new if any of these is true:
- Its name wasn't in the folder at the last run.
- It was renamed.
- Its Modified date is newer than at the last run.

Deleted or moved files never cause a post.

## Post 1: New files staged for printing
- Each run that finds new passing files makes a brand-new post. These posts are never edited.
- It lists only new files that pass the naming rules.
- Body:
  - "These new files have been staged for printing:"
  - A blank line.
  - One file per plain line, with no bullets.
  - A blank line.
  - A clickable "To be printed folder" link.
- Each post is deleted once it is 24 or more hours old.
- The 24-hour rule applies only to these posts.

## Post 2: Undefined 3D Print Jobs
- It lists only failing files.
- Body:
  - An intro line explaining the naming format.
  - A blank line.
  - One plain line per failing file, as `<file name>: <reason>`.
  - A blank line.
  - A clickable "To be printed folder" link.
- It is edited in place when the failing files or their reasons change. A new one is created only if it no longer exists.
- It is left alone if the failures haven't changed.
- A failing file re-uploaded with a newer date that still fails stays in this post.
- A file renamed so it passes leaves this post and shows up in a new-files post.
- It is deleted when nothing fails or the folder is empty.

## Post 3: Files staged for printing (7 AM run only)
- This applies to runs that start between 6:30 and 7:30 AM CT.
- There is one post, edited every morning and never reposted. It is created only if it doesn't exist.
- Body:
  - "These files are staged for printing:"
  - A blank line.
  - Every passing file in the folder, one per plain line.
  - A blank line.
  - A clickable "To be printed folder" link.
- If no files pass, the body becomes "No files to be printed", a blank line, then the link.
- New files appear both here and in their new-files post.

## General
- After each post, edit or delete, verify it worked, including that the links are clickable.
- State is kept in `/home/box/agent-data/print-check/last_result.json`. It records:
  - Each file's name and Modified time.
  - The failing files and their reasons.
  - The new-files posts and when they were posted.
- Only these three kinds of posts made by Chris's account are ever edited or deleted.
- Results go only to the Teams channel.
- Chris gets a message in this chat only when a run fails, such as a sign-in block or a post that can't be made.
```
