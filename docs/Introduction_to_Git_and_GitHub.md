## :open_book: Introduction to Git and GitHub
### :thinking: What is Git and GitHub?
**Git** is a distributed version control system to keep track of changes, collaborate on code, and manage revisions over time.

**GitHub** builds on top of Git as a cloud-based platform, simplifying the collaboration through a user-friendly interface.

## :pushpin: How to create a repository on GitHub?
1. Using the drop-down meny, select **new repository**.
2. Select the account to own the repository.
3. Type the repository name
4. Choose the visibility:
* **Public** repositories are accessible to everyone.
* **Private** repositories are accessble to you, people with share access, and organization members
5. Select **Create repository**

## :pushpin: How to clone a repository on GitHub?
This allows to create a local copy of the repository, being useful for making changes locally and syncing them back to the remote repository.
1. On the main page of the repository, click on the **Code** button
2. Copy the **URL** for the repository using HTTPS, SSH, or GitHub CLI.
3. Locally, open the terminal and navigate to the directory you want to clone the repository.
4. Run the command below replacing with the copied URL:
```bash
git clone repository-url
```
5. Navigate into the repository folder:
```bash
cd repository-name
```
## :pushpin: Git Workflow
The workflow involves three main areas:
* **Working Directory**: Where we're making changes.
* **Staging Area (Index)**: An area for grouping changes that we want to save to history.
* **Repository**: The permanent records of the history.

Git maintains a history of the project through commits. Each commit contains:
* Unique hash identifier
* Parent commit
* Author information
* Timestamp
* Commit message

Commits provide a clear audit trail for reviewing the history of a file.

Within a git repository, a file can exist in several valid states as it goes through the version control process.
* **Untracked**: Initial state of a file when it isn't yet part of the repository.
* **Tracked**: Git is actively monitoring. It can be in one of the substates:
    a. **Unmodified**: It hasn't been modified since the last commit.
    b. **Modified**: It has been change since the last commit, but the changes aren't staged for the next commit.
    c. **Staged**: It has been modified, and the changes have been added to the staging area.
    d. **Commited**: It is in the repository and represents the last version of the file.

## :pushpin: How to setup Git?
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

## :pushpin: How to compare changes?
Git uses simbols and coloring to show file changes:
* ```+``` in gree indicates **added** lines
* ```-``` in red indicates **removed** lines

The `` git diff``` show differeces between the states.
* ``` git diff```: Differences between the working directory and the staging area.
* ``` git diff --staged```: Differences between staging area and previous commit.
* ``` git HEAD~1```: Differences between current commit and previous commit.

## :pushpin: How to work with branches?
The branches allow working on a dependent version without influencing the original.
* The ```main``` branch is usually the trusted working version.
* A ```feature/*``` is a safe space to develop without affecting the trusted version.
* The ```develop``` branch contains the latest development work for the next release.
* The ```release/*``` is used to create new features, and is branched from ```develop```  and merged back when complete.
* The ```hotfix/*``` is used to quickly patch production issues, and is branched from the ```main``` branch.

There are different ways of combining branches, differing in the styles of organization, transparency, and traceability.
* **Fast-forward merge**: Move the new commits from the child branch onto the parent branch.
* **Merge commit**: Apply the changes as a single new commit on the parent branch, leaving the child branch for traceability.
* **Squash merge**: Collapse the commits from one branch into a single new commit on the other branch.


To list the available branches:
```bash 
git branch --list
```

To start a new branch from the current branch:
```bash
git branch my-branch-name
```

To change the working directory to a different branch:
```bash
 git checkout my-branch-name
 ```

To apply the commits from one branch onto another branch (default: Fast-forward merge):
```bash
 git merge my-branch-name -m "message"
 ```

To delete a branch
 ```bash
 git branch my-branch-name
 ```

## :pushpin: Git Collaboration Concepts
Typically, a collborative workflow looks like:
1. Copy a repository to the local machine (**clonning**)
2. Create branches and develop new features (**branching**)
3. Publish the changes to a remote repository, somewhere others can also access (**pushing**)
4. The collaborators decide to merge the changes in the main branch (**pulling**)
5. Additionaly, we can ask for another developer to integrate the changes in the main branch (**pull request**)

### :pushpin: What are pull requests?
A **pull** request is used to signal that the commits from one branch are ready to merged into another branch. Then, the reviewers can comment on changes, add their own, or use the pull request for further discussion. Once approved (if required), the pull request's source branch is merged to the main branch.

### :pushpin: What are Issues?
The **Issues** are used to track ideas, feedback, tasks, or bugs on GitHub.

To create an Issue:
1. Navigate to the main page of the repository
2. Under the repository name, select **Issues**
3. Select **New Issue**
4. If the repository uses issue templates, next to the type of issue, select **Get started**. If the type of issu isn't included, select **Open a blank issue**. 
5. In **Add a title**, enter the title for the issue.
6. In **Add a description**, type the description for issue.
7. If you're a manager of the repository, you can assign the issue to someone.
8. When finished, click on **Submit new issue**

### :pushpin: What are Discussions?
They're designed for conversations, such as Q&A, ideas, or general feedback.

To enable a discussion in the repository:
1. Navigate to the main page of the repository.
2. Under the repository name, select **Settings**
3. Scroll down to the **Features** and under **Discussions**, select **Setup discussions**
4. Under **Start a new discussion**, edit the template to match your community's tone and resources.
5. Select **Start discussion**

To create a new discussion:
1. Navigate to the main page of the repository
2. Under the repository name, selec **Discussions**
3. Select **New discussion**
4. Selec the discussion category by clicking on **Get started**
5. Under **Discussion title**, enter the title for the discussion, and under **Write** enter the body of the discussion.
6. Click on **Start discussion**

To convert a Discussion to an Issue:
1. Navigate to the Discussion
2. Select the ```...``` and **Convert to issue**
3. Confir the conversion and select the repository to create the new issue.


### :rocket: Contributing to an existing repository
```bash
# Clone a GitHub repository
# Replace `owner/repository` with the owner and name of the repository to clone
git clone https://github.com/owner/repository.git

# Navigate to the repository
cd repository

# Create a branch
git branch my-branch

# Switch to the branch
git checkout my-branch

# Make changes

# Stage
git add file1.md file2.md

# Commit
git commit -m "my snapshot"

# pPush
git push --set-upstream origin my-branch
```

### :rocket: Start a repository in GitHub
```bash
# Create directory, and initialize it with git-specific functions
git init my-repo

# Change into the `my-repo` directory
cd my-repo

# Create the first file in the project
touch README.md

# Stage
git add README.md

# Commit
git commit -m "add README to initial commit"

# Provide the path for the repository you created on github
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY-NAME.git

# Push
git push --set-upstream origin main
```
### :pushpin: Contribute to an existing branch on GitHub
```bash
# Change into the `repo` directory
cd repo

# Update all remote tracking branches, and the currently checked out branch
git pull

# Change into the existing branch called `feature-a`
git checkout feature-a

# Stage
git add file1.md

# Commit
git commit -m "edit file1"

# Push
git push
```

## :closed_book: Recap
* Version Control principles
* Configure Git
* Create repositories, staged changes, and commit
* Explore project history and compare changes
* Work with branches
* Collaboration concepts