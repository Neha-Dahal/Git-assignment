# Git Assignment

#### 1. Can we have a global .gitignore ?

Yes, we can have a global .gitignore file that lists all the files that will be ignored on all Git projects. To enable global gitignore, we use the following command:

    git config --global core.excludesfile ~/.gitignore_global

By using a global .gitignore file, we can maintain consistency in our development environment and also prevent accidentally committing files that we don't want to include in our repositories.

#### 2. How to find difference between two commits?

We can use the command `git diff` in order to find the difference between two commits. We can compare between two Git commits by specifying the name of the ref that refers to the commits that we want to compare. A ref may be commit ID or HEAD, which refers to the current branch.

    git diff <commit1> <commit2>

Let's find the differences between two commits in our Git repository.

To retrieve the ID of the commits whose files we want to compare, we use the `git log --oneline` command to briefly obtain the commit ID in the repo.

    git log --oneline

This command returned the commit IDs and commit messages as follows:

    26549d7 (HEAD -> master) second commit
    d26de58 initial commit

To find the difference between these two commits, we use their commit IDs as follows:

    git diff 26549d7 d26de58

This command performs the difference operation across our two commits.

#### 3. Write difference between git add and git commit commands.

**Purpose:** `git add` is used to add modified files to the staging area whereas `git commit` is used to commit the files that have been added in the staging area to the local git repository.

**Syntax:**

**Git add:**

- For specific files:

      git add <file1> <file2> ... <fileN>

- For all files:

      git add .

**Git commit:**

    git commit -m "commit message"

#### 4. How to unstage files?

We can unstage files by using any one of the following ways:

-     git restore --staged <filename>

-     git reset <filename>

-     git rm --cached <filename>

#### 5. How to revert a commit?

To revert a commit, we use the command `git revert` along with commit ID or commit sha.

**Syntax:**

    git revert <commit_id>

#### 6. Difference between revert and reset.

`git revert` undoes the changes from a previous commit. It doesn't change the history.

On the other hand, `git reset` moves the current head of the branch to the specified commit. It changes the commit history.

#### 7. Write the difference between fetch and pull command.

`git fetch` command is used to pull the data to the local repository but it is not merged to the local branch automatically. On the other hand, `git pull` is used to fetch and automatically merge the remote changes.

#### 8. How to handle merge conflicts?

To handle the merge conflicts, we can follow any of the two approaches:

- We can resolve the conflict by fixing it manually. Then, we run `git add` on the file to re-stage it and finally, we commit the merge.

- We can create a pull request in Github, decide if we want to incorporate the changes and resolve the conflicts. Once we've resolved all the conflicts in the file, we mark it as resolved.
