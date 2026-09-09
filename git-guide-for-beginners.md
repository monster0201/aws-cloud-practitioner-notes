# Git & GitHub — Simple Guide for Beginners

This is your personal reference. Keep it open whenever you forget a command.

---

## 1. What is Git and GitHub? (in simple words)

- **Git** = a tool on your computer that saves "snapshots" (history) of your files, so you never lose old work and can always go back.
- **GitHub** = a website that stores your Git project online, so you can access it from anywhere and show it to others (like recruiters).

Simple line: **Git = save history on your laptop. GitHub = backup + show it online.**

---

## 2. One-Time Setup (do this only once per computer)

Tell Git who you are (only needed the first time):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Check it worked:
```bash
git config --list
```

---

## 3. Starting a NEW Project (like you did for aws-cloud-practitioner-notes)

```bash
mkdir my-project-name        # create a folder
cd my-project-name           # go inside it
git init                     # turn this folder into a Git repo
```

`git init` only needs to run **once per project**, at the very start.

---

## 4. The Daily Git Workflow (you will repeat this often)

This is the cycle you'll use every single day:

```bash
git status          # see what changed
git add .            # stage all changed files (prepare them to be saved)
git commit -m "short message about what you did"   # save the snapshot
git push             # send it to GitHub
```

### Explaining each command:

| Command | What it does | Simple analogy |
|---|---|---|
| `git status` | Shows which files changed | Checking what's new before packing |
| `git add .` | Selects files to save (the `.` means "all files") | Putting items in a box |
| `git commit -m "..."` | Actually saves the snapshot with a message | Sealing the box with a label |
| `git push` | Uploads your commit to GitHub | Sending the box to storage online |

**Tip:** You can `git add` only one file instead of everything:
```bash
git add filename.md
```

---

## 5. Connecting a Local Project to GitHub (only once per project)

**Step A:** Create the empty repo on GitHub.com
- Click **+** → **New repository**
- Give it a name
- Do **NOT** tick "Add README" if you already have files locally
- Click **Create repository**

**Step B:** Copy the URL GitHub gives you, then run:
```bash
git remote add origin https://github.com/YOUR-USERNAME/repo-name.git
git branch -M main
git push -u origin main
```

After this first push, future pushes are just:
```bash
git push
```
(no need to repeat the `-u origin main` part again)

---

## 6. Adding NEW Files or Folders Later (your future workflow)

Whenever you finish a new module/topic and want to save it:

```bash
cd aws-cloud-practitioner-notes      # go to your project folder
nano 02-compute-in-the-cloud/README.md   # write your new notes

git add .
git commit -m "Add Module 2 notes"
git push
```

That's it — same 3 commands every time (`add`, `commit`, `push`), no matter how many new files you create.

---

## 7. Checking Your Work

See your commit history:
```bash
git log --oneline
```

See exactly what changed in a file before committing:
```bash
git diff
```

---

## 8. Common Beginner Mistakes (and fixes)

| Problem | What happened | Fix |
|---|---|---|
| `fatal: not a git repository` | You forgot `git init`, or you're in the wrong folder | Run `cd` into the right folder, then `git init` |
| `git push` asks for username/password but fails | GitHub no longer accepts your normal password for this | Use a **Personal Access Token** instead (ask me, I'll guide you) |
| Forgot to `git add` before commit | Commit says "nothing to commit" | Run `git add .` first |
| Made a typo in commit message | Already committed | `git commit --amend -m "new message"` (only works if you haven't pushed yet) |

---

## 9. Quick Cheat Sheet (memorize these 4 first)

```bash
git status      # what changed?
git add .       # stage everything
git commit -m "message"   # save snapshot
git push        # upload to GitHub
```

95% of your daily work will just be these 4 commands, in this order.

---

## 10. What NOT to worry about yet

As a beginner, ignore these for now (learn later once comfortable):
- Branches (`git branch`, `git checkout`) — used for teamwork, not needed solo
- Merge conflicts — happens mostly in teams
- `.gitignore` — useful later, not urgent for notes

Focus only on: **init → add → commit → push**. Everything else can wait.
