# Git Commands — Simple Guide with Use Cases

This is a simple, no-jargon list of all the Git commands you'll actually use day to day, taken from the Handbook and organized by "when do I use this?". Keep this open in a tab while you practice.

---

## 1. Setup (do this once on a new machine)

| Command | What it does | When to use it |
|---|---|---|
| `git config --global user.name "Your Name"` | Sets your name for commits | First thing after installing Git |
| `git config --global user.email "you@example.com"` | Sets your email (use your GitHub email) | Right after setting your name |
| `git config --list` | Shows all your current settings | To check your setup is correct |

---

## 2. Starting a Project

| Command | What it does | When to use it |
|---|---|---|
| `git init` | Starts tracking a folder with Git | Starting a brand-new project from scratch |
| `git clone <repo-url>` | Downloads a full copy of an existing repo | Getting someone else's (or your own) project from GitHub |

---

## 3. Daily Workflow (the ones you'll use constantly)

| Command | What it does | When to use it |
|---|---|---|
| `git status` | Shows what's changed, staged, or untracked | Run this ALL the time — before and after every action |
| `git add <file>` | Stages one file | When you only want to commit a specific file |
| `git add .` | Stages everything changed | Most common — after finishing a chunk of work |
| `git commit -m "message"` | Saves a snapshot of staged changes | After staging, to actually save your progress |
| `git commit -am "message"` | Stages + commits tracked files in one step | Quick commits when you haven't added new files |
| `git log --oneline` | Shows commit history, one line each | To see what you've done so far |
| `git diff` | Shows unstaged changes line-by-line | Before staging, to review what you actually changed |
| `git diff --staged` | Shows staged changes vs last commit | Right before committing, as a final check |

---

## 4. Branching (working on features without breaking main code)

| Command | What it does | When to use it |
|---|---|---|
| `git branch` | Lists local branches | To see where you are |
| `git branch <name>` | Creates a new branch | Starting a new feature/fix |
| `git switch <name>` | Switches to a branch | Moving between branches |
| `git switch -c <name>` | Creates + switches in one step | Most common way to start new work |
| `git branch -d <name>` | Deletes a branch (safe) | After a feature is merged and no longer needed |

---

## 5. Merging & Rebase (combining work)

| Command | What it does | When to use it |
|---|---|---|
| `git merge <branch>` | Merges another branch into your current one | Bringing a finished feature into `main` |
| `git merge --abort` | Cancels a merge that went wrong | You're stuck in a messy conflict and want to start over |
| `git rebase main` | Replays your branch's commits on top of latest `main` | Keeping your feature branch up to date, cleanly |
| `git rebase --abort` | Cancels a rebase in progress | Rebase getting messy, want a clean restart |

> ⚠️ Rule of thumb: **never rebase a branch that's already pushed and shared with others** — only rebase your own local, unshared work.

---

## 6. Undoing Mistakes

| Command | What it does | When to use it |
|---|---|---|
| `git restore <file>` | Discards unstaged edits to one file | You messed up a file and want the last saved version back |
| `git restore .` | Discards ALL unstaged edits | Total "undo everything I haven't committed" button |
| `git restore --staged <file>` | Unstages a file (keeps your edits) | Accidentally staged something you're not ready to commit |
| `git reset --soft HEAD~1` | Undoes last commit, keeps changes staged | You committed too early, want to edit and recommit |
| `git reset --hard HEAD~1` | Deletes last commit AND its changes | You're 100% sure you want to throw that commit away (only if NOT pushed yet) |
| `git revert <commit>` | Creates a new commit that undoes an old one | Safely undoing something that's **already pushed** to GitHub |

---

## 7. Stash (parking your work temporarily)

| Command | What it does | When to use it |
|---|---|---|
| `git stash` | Saves uncommitted work without committing it | You need to switch tasks urgently (e.g. fix a bug) but aren't done with current work |
| `git stash list` | Shows all stashed items | Checking what you've stashed |
| `git stash pop` | Brings back the latest stash and removes it from the list | Returning to your parked work |
| `git stash apply` | Brings back the latest stash but keeps it in the list too | Want to apply the same stash in multiple places |

---

## 8. Working with GitHub (Remotes)

| Command | What it does | When to use it |
|---|---|---|
| `git remote add origin <url>` | Connects your local repo to a GitHub repo | Right after `git init`, before your first push |
| `git remote -v` | Shows connected remotes | To check your repo is linked correctly |
| `git push -u origin main` | Pushes your code + sets upstream (first time) | The very first push of a new repo |
| `git push` | Pushes new commits | Every time after that first push |
| `git pull origin main` | Downloads + merges the latest changes | Before starting work, or before pushing, to avoid conflicts |
| `git fetch origin` | Downloads changes but does NOT merge them | When you want to review what changed before merging it in |

---

## 9. Resolving Merge Conflicts

When Git can't automatically combine two changes, it shows markers like this in the file:

```
<<<<<<< HEAD
your version
=======
their version
>>>>>>> branch-name
```

1. Open the file, decide which version (or combination) to keep.
2. Delete the `<<<<<<<`, `=======`, `>>>>>>>` marker lines.
3. Then run:
   ```
   git add <filename>
   git commit -m "resolve merge conflict"
   ```

---

## 10. Tags (marking releases)

| Command | What it does | When to use it |
|---|---|---|
| `git tag v1.0.0` | Marks the current commit as a version | Marking a stable release point |
| `git tag -a v1.0.0 -m "message"` | Same, but with extra info (recommended) | Official releases |
| `git push origin --tags` | Sends all tags to GitHub | Sharing your release tags |

---

## 11. Ignoring Files

Create a `.gitignore` file and list what Git should skip:

```
.env
node_modules/
__pycache__/
.DS_Store
```

Use this for passwords, API keys, large files, and OS junk files — never let secrets enter your Git history.

---

## Quick Daily Cheat-Flow

```
git status              # what changed?
git add .                # stage it
git commit -m "message"  # save it
git pull origin main     # sync with GitHub first
git push                 # send it to GitHub
```

That's genuinely 90% of what you'll use daily. Master this loop, then slowly pick up branching, stash, and rebase as you need them.

---

📖 For full explanations with diagrams, read the **Git & GitHub Handbook** in the `Resources/` folder — courtesy of **CodeWithHarry**.
