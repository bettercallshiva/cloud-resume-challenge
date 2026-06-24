# Cloud Resume Challenge - Troubleshooting & Fixes Log

## Issue 1: PowerShell Blocks npm Commands

### Problem

Running:

```powershell
npm -v
```

produced:

```text
npm.ps1 cannot be loaded because running scripts is disabled on this system
```

### Cause

PowerShell execution policy prevented npm PowerShell scripts from running.

### Solution

Command:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### What This Command Does

* Changes PowerShell execution policy for the current user.
* Allows locally created scripts to run.

### Verification

```powershell
npm -v
node -v
```

Expected:

```text
11.x.x
v24.x.x
```

### Learning

PowerShell execution policies can block Node.js tooling.

---

# Issue 2: Incorrect Vite Project Creation

### Problem

Running:

```powershell
npm create vite@latest cloud-resume-challenge -- --template react
```

resulted in:

```text
"," isn't a valid template
```

### Cause

Template argument was entered incorrectly.

### Solution

Recreate project correctly and select React when prompted.

### Learning

Always verify CLI arguments carefully.

---

# Issue 3: Could Not Find Project Folder

### Problem

```powershell
cd cloud-resume-challenge
```

produced:

```text
Cannot find path
```

### Cause

Project was created in a different location than expected.

### Solution

Locate project folder manually.

Useful commands:

```powershell
Get-ChildItem -Directory
```

or

```powershell
dir
```

### Learning

Always verify current directory before navigating.

---

# Issue 4: Git Add Typo

### Problem

Typed:

```bash
git add.
```

Git responded:

```text
git: 'add.' is not a git command
```

### Cause

Missing space.

### Solution

```bash
git add .
```

### Learning

Git commands are sensitive to spacing.

---

# Issue 5: GitHub Authentication Failure

### Problem

```bash
git push
```

returned:

```text
Invalid username or token
Password authentication is not supported
```

### Cause

GitHub no longer supports account passwords for Git operations.

### Solution

Use GitHub authentication methods:

* Personal Access Token (PAT)
* SSH Authentication (recommended)

### Learning

Modern GitHub authentication does not use account passwords.

---

# Issue 6: Git Push Rejected

### Problem

```bash
git push
```

returned:

```text
Updates were rejected because the remote contains work that you do not have locally
```

### Cause

GitHub repository already contained a README commit.

### Solution

```bash
git pull origin main --allow-unrelated-histories
```

### What This Command Does

* Pulls remote history.
* Allows merging unrelated repositories.

### Learning

Local and remote histories must be merged before pushing.

---

# Issue 7: README Merge Conflict

### Problem

During pull:

```text
CONFLICT (add/add): Merge conflict in README.md
```

### Cause

README existed both locally and remotely.

### Solution

1. Open README.md
2. Remove conflict markers

Example:

```text
<<<<<<< HEAD
=======
>>>>>>> branch
```

3. Save file

4. Commit changes

```bash
git add README.md
git commit -m "Resolve README merge conflict"
```

### Learning

Merge conflicts are normal and must be resolved manually.

---

# Issue 8: WSL Could Not Find Node.js

### Problem

Inside Ubuntu:

```bash
node -v
```

returned:

```text
Command 'node' not found
```

while

```bash
npm -v
```

worked.

### Cause

WSL was seeing Windows npm but not Linux Node.js.

### Investigation Commands

```bash
which npm
which node
```

### Solution

Install Node.js inside Ubuntu.

```bash
sudo apt update
sudo apt install -y nodejs npm
```

### Learning

Cloud environments use Linux-native tools whenever possible.

---

# Issue 9: Typographical Command Errors

### Examples

Wrong:

```bash
git --vesion
```

Correct:

```bash
git --version
```

Wrong:

```bash
np -v
```

Correct:

```bash
npm -v
```

Wrong:

```bash
npm config get prefex
```

Correct:

```bash
npm config get prefix
```

### Learning

Most terminal errors are simple spelling mistakes.

Always read error messages carefully.

---

# Issue 10: HTTPS Git Authentication in WSL

### Problem

Git inside Ubuntu repeatedly asked:

```text
Username:
Password:
```

and push failed.

### Cause

Repository remote was configured with HTTPS.

Current remote:

```bash
git remote -v
```

Output:

```text
https://github.com/bettercallshiva/cloud-resume-challenge.git
```

### Solution

Switch to SSH authentication.

Verify SSH:

```bash
ssh -T git@github.com
```

Expected:

```text
Hi bettercallshiva! You've successfully authenticated
```

Then update remote:

```bash
git remote set-url origin git@github.com:bettercallshiva/cloud-resume-challenge.git
```

### Learning

SSH is the preferred Git authentication method for Linux and Cloud engineers.

---

# Useful Diagnostic Commands

Current Directory:

```bash
pwd
```

List Files:

```bash
ls
```

Current User:

```bash
whoami
```

Git Status:

```bash
git status
```

View Changes:

```bash
git diff
```

Check Git Version:

```bash
git --version
```

Check Node:

```bash
node -v
```

Check npm:

```bash
npm -v
```

Check SSH Connection:

```bash
ssh -T git@github.com
```

Check Git Remote:

```bash
git remote -v
```

---

# Biggest Lessons Learned

1. Read the entire error message.
2. Most issues are configuration problems.
3. Linux is the preferred environment for cloud work.
4. GitHub passwords no longer work for Git operations.
5. SSH authentication is a valuable skill.
6. Merge conflicts are normal.
7. Documentation saves time in the future.
8. Understand commands instead of memorizing them.
