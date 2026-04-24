## :open_book: Introduction to Git
The workflow involves three main areas:
* **Working Directory**: The project files where we're making changes.
* **Staging Area (Index)**: A preparation area for grouping changes we want to save to history.
* **Repository**: The permanent records of the history.

Git maintains a history of the project through commits. Each commit contains:
* Unique hash identifier
* Parent commit
* Author information
* Timestamp
* Commit message

### :pushpin: What are the important commands?
1. To show the current installed version of Git:
```bash
git --version
```

2. To show the Git help documentation:
```bash
git --help
```

3. To set the Git identity:
```bash
git config --global user.name "First Last"

git config --global user.email "email@example.com"
```
:bulb: Confirm the changes by viewing the configuration:

```bash
git config --global --list
```

4. To start a new repository:
```bash
 git init
 ```

5. To group related changes in the staging are:
```bash 
git add
```
 
5. To save the changes to the history:
```bash 
git commit
```

:bulb: Add a commit message using ```bash -m```:

6. To view the current state of the working directory and staging area:
```bash 
git status
```

7. To change the working directory:
```bash 
git checkout
```

### :pushpin: How to initialize a repository in the CLI?
1. In the terminal, navigate to the directory. Then, initialize the Git repository:
```bash 
git init
```

2. After creating a repository, check the status:
```bash
git status
```

### :pushpin: How to compare changes?
Git uses simbols and coloring to show file changes:
* ```+``` in gree indicates **added** lines
* ```-``` in red indicates **removed** lines

The `` git diff``` show differeces between the states.
* `` git diff```: Differences between the working directory and the staging area.
* `` git diff --staged```: Differences between staging area and previous commit.
* `` git HEAD~1```: Differences between current commit and previous commit.

### :pushpin: How to work with branches?
The branches allow working on a dependent version without influencing the original.
* The ```main``` branch is usually the trusted working version.
* A **feature branch** is a safe space to develop without affecting the trusted version.

There are different ways of combining branches, differing in the styles of organization, transparency, and traceability.
* **Fast-forward merge**: Move the new commits from the child branch onto the parent branch.
* **Merge commit**: Apply the changes as a single new commit on the parent branch, leaving the child branch for traceability.
* **Squash merge**: Collapse the commits from one branch into a single new commit on the other branch.


#### :pushpin: What are the important Git commands?
* To list the available branches:
```bash 
git branch --list
```

* To start a new branch from the current branch:
```bash
git branch my-branch-name
```

* To change the working directory to a different branch:
```bash
 git checkout my-branch-name
 ```

* To apply the commits from one branch onto another branch (default: Fast-forward merge):
```bash
 git merge my-branch-name -m "message"
 ```

 * To delete a branch
 ```bash
 git branch my-branch-name
 ```

### :pushpin: Git Collaboration Concepts
Typically, a collborative workflow looks like:
1. Copy a repository to the local machine (**clonning**)
2. Create branches and develop new features (**branching**)
3. Publish the changes to a remote repository, somewhere others can also access (**pushing**)
4. The collaborators decide to merge the changes in the main branch (**pulling**)
5. Additionaly, we can ask for another developer to integrate the changes in the main branch (**pull request**)

## :closed_book: Recap
* Version Control principles
* Configure Git
* Create repositories, staged changes, and commit
* Explore project history and compare changes
* Work with branches
* Collaboration concepts