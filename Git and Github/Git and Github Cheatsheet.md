# GitHub Cheat Sheet

> A compact reference you can drop into Obsidian for quick look‑ups.

---

## 📦 Basic Git Commands

| Action | Command | Notes |
|--------|---------|-------|
| Clone a repo | `git clone <url>` | `https://` or `git@` |
| Create & switch to a branch | `git checkout -b <branch>` | |
| Switch to an existing branch | `git checkout <branch>` | |
| List local branches | `git branch` | |
| List remote branches | `git branch -r` | |
| Track a remote branch | `git checkout --track origin/<branch>` | |
| Pull latest changes | `git pull` | `-r` for rebase |
| Push a branch | `git push -u origin <branch>` | `-u` sets upstream |
| Push all branches | `git push --all` | |
| Delete local branch | `git branch -d <branch>` | `-D` forces |
| Delete remote branch | `git push origin --delete <branch>` | |
| Show commit history | `git log --oneline --graph --decorate` | |
| Show unstaged changes | `git diff` | Between working tree & index |
| Show staged changes | `git diff --cached` | |
| Stash changes | `git stash` | `git stash pop` / `git stash drop` |
| Reset to last commit | `git reset --hard HEAD` | **Wipes uncommitted changes** |

---

## 🚀 Git Workflow

| Step | Command | Typical use |
|------|---------|-------------|
| 1️⃣ Pull latest | `git pull --rebase` | Keep linear history |
| 2️⃣ Create feature branch | `git checkout -b feature/foo` | |
| 3️⃣ Commit work | `git add .` <br> `git commit -m "Add foo"` | |
| 4️⃣ Push feature | `git push -u origin feature/foo` | |
| 5️⃣ Open Pull Request | **GitHub UI** or `gh pr create` | |
| 6️⃣ Review / merge | **GitHub UI** | Resolve conflicts if any |
| 7️⃣ Clean up | `git branch -d feature/foo` <br> `git push origin --delete feature/foo` | |

> [!Tip:] Use **GitHub CLI** (`gh`) to automate steps (`gh pr create`, `gh pr merge`, etc.).

---

## 🔄 Merging & Rebasing

| Action | Command | When to use |
|--------|---------|-------------|
| Merge | `git merge <branch>` | Preserve history (e.g., release branches) |
| Rebase | `git rebase <branch>` | Clean linear history before pushing |
| Interactive rebase | `git rebase -i HEAD~n` | Squash, edit, or reorder commits |
| Abort rebase | `git rebase --abort` | If conflicts are messy |
| Continue rebase | `git rebase --continue` | After resolving conflicts |

---

## 📈 Branch Management

| Task | Command | Note |
|------|---------|------|
| Rename locally | `git branch -m old new` | |
| Rename remote | `git push origin :old new` <br> `git push origin -u new` | `:old` deletes old remote |
| Force‑push (overwrite) | `git push -f origin <branch>` | Use with caution |

---

## 🛠️ Stashing & Unstaging

| Action | Command | Description |
|--------|---------|-------------|
| Stash | `git stash` | Save work without committing |
| List stashes | `git stash list` | |
| Apply stash | `git stash apply` | Keep stash |
| Drop stash | `git stash drop` | |
| Pop stash | `git stash pop` | Apply & drop |
| Unstage file | `git reset HEAD <file>` | |

---

## 📥 Remote Operations

| Action | Command | Description |
|--------|---------|-------------|
| Add remote | `git remote add <name> <url>` | |
| Show remotes | `git remote -v` | |
| Rename remote | `git remote rename <old> <new>` | |
| Remove remote | `git remote remove <name>` | |

---

## ⚙️ GitHub‑Specific Tips

| Feature | Command / Shortcut | Where to use |
|---------|----|--------------|
| Create new repo | `gh repo create` | CLI |
| Clone existing repo | `gh repo clone <owner>/<repo>` | |
| Open repo in browser | `gh repo view --web` | |
| Create PR | `gh pr create -t <title> -b <body> -b <base>` | |
| Merge PR | `gh pr merge <number> --merge` | |
| Close PR | `gh pr close <number>` | |
| View PR | `gh pr view <number> --web` | |
| Create issue | `gh issue create -t <title> -b <body>` | |
| List issues | `gh issue list` | |
| Show repo status | `gh repo view --web` | |
| PR status | `gh pr status` | |

---

## 📌 Common GitHub Actions

| Action | UI / CLI |
|--------|----------|
| Create a branch | *Repository → Branches → New branch* |
| Add collaborators | *Settings → Manage access* |
| Create release | *Releases → Draft a new release* |
| Enable protected branches | *Settings → Branches → Add rule* |
| Require status checks | *Branch protection rules* |

---

## 🔧 Useful Flags & Shortcuts

| Flag | Meaning | Example |
|------|---------|---------|
| `-a` | All commits | `git log -a` |
| `-p` | Show patch | `git show -p` |
| `-s` | Show summary | `git log -s` |
| `--no-ff` | Create merge commit even if fast‑forward possible | `git merge --no-ff feature` |
| `--ff-only` | Fail if not a fast‑forward | `git merge --ff-only release` |
| `-u` | Set upstream tracking | `git push -u origin main` |
| `-m` | Commit message | `git commit -m "Fix bug"` |
| `-v` | Verbose | `git pull -v` |

---

## 🏁 Quick Reference

```bash
# Clone a repository
git clone https://github.com/owner/repo.git

# Create a feature branch
git checkout -b feature/foo

# Make changes, stage, commit
git add .
git commit -m "Add foo feature"

# Push to GitHub and create PR
git push -u origin feature/foo
gh pr create --fill

# Merge after review
git checkout main
git pull --rebase
git merge --no-ff feature/foo
git push

# Clean up
git branch -d feature/foo
git push origin --delete feature/foo
