# task-3
# Git And GitHub

## **Task List: Focused on Repository Management, Commits, Branching, and Merging**

## **Part 1: Creating and Cloning Repositories**

### **Task 1: Create a Local Git Repository**

#### 1. Create a new project folder:

```bash
mkdir MyProject
cd MyProject
```

- It make directory with named MyProject and change the path to MyProject.

#### 2. Initialize it as a Git repository:

```bash
git init
```

- Initailize new empty repository in local.

#### 3. Verify the repository status:

```bash
git status
```

- It shows the untracked files, modified files, and staging area files which is ready to commit.
- **Output**:

```
On branch main
No commits yet
nothing to commit (create/copy files and use "git add" to track)
```

### **Task 2: Clone a Remote Repository**

#### 1. Clone a GitHub repository:

```bash
git clone https://github.com/username/repo.git
```

- It copy the repository-url to the local.

#### 2. Verify the cloned repository structure:

```bash
cd repo
ls -a
```

- It change to repo.
- Lists all files and directories in the current directory (**`repo`** in this case), including hidden files (those starting with a dot, like **`.git`** or **`.gitignore`**).

---

## **Part 2: Understanding Commits and Commit Messages**

### **Task 3: Commit Changes Locally**

#### 1. Create a new file and add content:

```bash
echo "Welcome to Git" > README.md
```

- It create new file with named **`README.md`**.
- In this file, we can add message **`"Welcome to Git"`**.

#### 2. Stage the file:

```bash
git add README.md
```

- It add the directory to the staging area.

#### 3. Commit the staged file:

```bash
git commit -m "Initial commit: Added README.md"
```

- It used to save the changes with the message **`"Initail commit: Added README.md"`**.

### **Task 4: Write Effective Commit Messages**

#### 1. Create a detailed commit message:

```bash
git commit -m "Added initial version of README.md with project overview"
```

- With effective commit message we can used afterwards to see the change or we use that code to the current directory.

#### 2. Commit multiple files with one message:

```bash
touch file1.txt file2.txt
git add .
git commit -m "Added two new files for feature setup"
```

- Its only add **`file1.txt`** and **`file2.txt`** to the staging area.
- Its commit only this two files with message **`"Added two new files for feature setup"`**.

---

## **Part 3: Viewing Commit History with `git log`**

### **Task 5: View Detailed Commit History**

#### 1. View full commit logs:

```bash
git log
```

- Its show all commit history.

#### 2. View commit history in a compact format:

```bash
git log --oneline
```

- Its shows the commit history with their unique code.
- Which used to see commit message.
- **Output**:
  ```
  e23d8a7 Added initial version of README.md
  f7b3c62 Initial commit: Added README.md
  ```

### **Task 6: Customize Log Outputs**

#### 1. View logs with a graphical representation:

```bash
git log --oneline --graph --decorate
```

- **`--oneline`:**

  - Displays each commit in a single line.
  - Includes the commit hash and commit message.
  - Makes the log output concise and easy to read.

- **`--graph`:**

  - Adds a graphical representation of the commit history using ASCII characters (e.g., `|`, `\`, `/`).
  - Shows how branches diverge and merge.

- **`--decorate`:**
  - Adds information about branches, tags, and HEAD pointers to the output.
  - Helps you see which branch or tag a particular commit belongs to.

#### 2. Filter logs for a specific file:

```bash
git log README.md
```

- **`git log`:**
  - Shows the commit history of the repository.
- **`README.md`:**
  - Restricts the log to show only commits that modified this file.

---

## **Part 4: Understanding Branching and Merging**

### **Task 7: Understanding Branching**

#### 1. List all branches:

```bash
git branch
```

- Its shows all branch list.

#### 2. Create a new branch:

```bash
git branch feature-branch
```

- Creates a new branch without switching to it.

#### 3. Switch to the new branch:

```bash
git checkout feature-branch
```

- **Alternative Command**:

```bash
git checkout -b feature-branch
```

- Creates and switches to the branch in one command.

---

## **Part 5: Creating and Working with Branches**

### **Task 8: Make Changes in a Branch**

#### 1. Add content to a file in the new branch:

```bash
echo "Feature in progress" > feature.txt
git add feature.txt
git commit -m "Added feature.txt in feature-branch"
```

- Its create new file with named **`feature.txt`** with a message **`"Feature in progress"`**.
- Added to staging area.
- And commit with message **`"Added feature.txt in feature-branch"`**.

### **Task 9: Merging Branches**

#### 1. Switch back to the `main` branch:

```bash
git checkout main
```

- Its switches to **`main`** branch.

#### 2. Merge the `feature-branch` into `main`:

```bash
git merge feature-branch
```

- Combines the changes from `feature-branch` into `main`.

---

## **Part 6: Resolving Merge Conflicts**

### **Task 10: Simulate a Merge Conflict**

#### 1. Modify the same line in a file on two branches:

```bash
echo "Main branch content" > conflict.txt
git add conflict.txt
git commit -m "Added conflict.txt in main branch"
```

- Its create new file with named **`conflict.txt`** with a message **`"Main branch content"`**.
- Added to staging area.
- And commit with message **`"Added conflict.txt in main branch"`**.

#### 2. Switch to the other branch and make conflicting changes:

```bash
git checkout feature-branch
echo "Feature branch content" > conflict.txt
git add conflict.txt
git commit -m "Modified conflict.txt in feature-branch"
```

- Its switches to **`feature-branch`**.
- added a new lines in this file.
- added to staging aera.
- and commit it message **`"Modified conflict.txt in feature-branch"`**.

#### 3. Merge `feature-branch` into `main`:

```bash
git checkout main
git merge feature-branch
```

- To merge two we need to switch to **`main`** and then merge the **`feature-branch`**.

#### 4. Resolve the conflict by editing the file and choosing the correct version:

- Open `conflict.txt` and decide which changes to keep.
- Stage the resolved file:

```bash
git add conflict.txt
```

- Commit the merge:

```bash
git commit -m "Resolved conflict in conflict.txt"
```

---

## **Part 7: Deleting and Renaming Branches**

### **Task 11: Delete a Branch**

#### 1. Delete a local branch:

```bash
git branch -d feature-branch
```

- This deletes the branch only if it has been fully merged.

#### 2. Force-delete a branch:

```bash
git branch -D feature-branch
```

- Deletes the branch even if it hasn’t been merged.

### **Task 12: Rename a Branch**

#### 1. Rename the current branch:

```bash
git branch -m new-branch-name
```

- It rename the branch **`new-branch-name`**.

#### 2. Rename another branch (not checked out):

```bash
git branch -m old-branch-name new-branch-name
```

- It changes the old name with new name.

---