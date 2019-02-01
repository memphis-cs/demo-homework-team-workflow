# [▶️](https://www.youtube.com/watch?v=W-EUZbOLsdQ&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=2) Demo: Workflow for Boot Camp Teamwork

In this demonstration, I will explain the workflow to follow for submitting your boot camp team homework in this course. This workflow was largely inspired by the popular [GitHub Flow](https://guides.github.com/introduction/flow/) workflow.

## [▶️](https://www.youtube.com/watch?v=W-EUZbOLsdQ&t=28s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=2) 1. Initial Setup

### [▶️](https://www.youtube.com/watch?v=W-EUZbOLsdQ&t=39s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=2) 1.1. What the Instructor Sets Up

Here are the steps I followed to set up each team's project repo.

#### [▶️](https://www.youtube.com/watch?v=W-EUZbOLsdQ&t=51s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=2) 1.1.1. Local Project/Repo Setup

1. Create a Rails project skeleton.
1. Add a `.ruby-gemset` configuration file.
1. Add and set up the `annotate` gem.
1. Add a `PagesController` with `home` action/page.
1. Commit this version of the project to the local repo.

#### [▶️](https://www.youtube.com/watch?v=yYsCbHcKqz8&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=3) 1.1.2. Remote GitHub Setup

1. Create a private GitHub repo for your team.
1. Push this version to the remote GitHub repo.
1. In GitHub settings, disable _squash_ and _rebase_ merging. These forms of merging effectively change the commit history, and can cause confusion for the purposes of this course. In case you're curious, here is a [GitHub Help article on squash and rebase merging](https://help.github.com/articles/about-pull-request-merges/).
1. Add branch protection rule for `master` branch that requires pull request reviews before merging. Here is a [GitHub Help article on branch protection](https://help.github.com/articles/configuring-protected-branches/).
1. Add each team members as a collaborator with write permission.

### [▶️](https://www.youtube.com/watch?v=k8xpklP-aI4&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=4) 1.2. What You Must Set Up

Once you have been added as a collaborator on a GitHub repo, you should receive an email invitation containing a link to the repo. Before you begin work on a homework assignment, you must clone the remote GitHub repo (i.e., using `git clone ...`). You need to do this only one time, and you can use the cloned repo for all subsequent homework assignments.

## [▶️](https://www.youtube.com/watch?v=9rmeKwWY7WU&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=5) 2. Doing a Homework Task

For each homework assignment, your team must first assign each person a different task. There will generally be four tasks to assign (Task 1 through Task 4); however, if your team has only three members, you should ignore Task 4.

Once your team has agreed upon who will do which task, you must perform the following steps to complete and submit the homework.

### [▶️](https://www.youtube.com/watch?v=9rmeKwWY7WU&t=28s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=5) 2.1. Step 1: Create an Issue for Your Task

- When you start a task, create an issue for the task in GitHub.
  - Title the issues using this form: `Homework 5, Task 3` (replacing the numbers with whatever is appropriate for you).
  - Set the _Labels_ to _enhancement_.
  - Set the _Assignees_ to the person who will perform the task (you).
  - You may ignore the _Milestone_ and _Projects_ settings.

### [▶️](https://www.youtube.com/watch?v=4Jewh3hGyrY&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=6) 2.2. Step 2: Create a Topic Branch for Your Task

- You will do all your work in a topic branch.
- Use a branch-naming convention like this:
  - `iss3` where the issue number for your task is issue #3.
- From the `master` branch, you might use this command to create the branch and check it out:
  - `git checkout -b iss3`
- The first time you push the topic branch, use this command to set the upstream branch (assuming that the topic branch is named `iss3`):
  - `git push -u origin iss3`
- After you run the above push command, you can push and pull from the branch using the shorter forms:
  - `git push`
  - `git pull`

### [▶️](https://www.youtube.com/watch?v=-sHk1LA-s7M&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=7) 2.3. Step 3: Complete Your Task in the Topic Branch

- With the topic branch checked out, make changes, commit them locally, and push them to GitHub. All changes made this way should be fully contained in the topic branch.
- If changes from other teammates are merged into the `master` branch while you are working on your topic branch, you will need merge them into your topic branch before you're done. From your topic branch, you can use this command to merge the remote master branch into your topic branch (although you may need to manually resolve merge conflicts after the command):
  - `git pull origin master`

### [▶️](https://www.youtube.com/watch?v=F2vIlYPUlSc&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=8) 2.4. Step 4: Create a Pull Request (PR)

- Once your task is completed, create a pull request in GitHub.
  - Make the title the exact same as the corresponding issue title.
  - Add a comment "Closes #3" in the description (assuming that the issue is issue #3). This will link the PR with its corresponding issue and will automatically close the issue when the PR is closed. In case you're curious, here is a [GitHub Help article on using keywords in PR comments to close issues](https://help.github.com/articles/closing-issues-using-keywords/).
  - Set the _Reviewers_ to all other team members other than yourself. This will serve to notify them of your pull request.
  - Set the _Labels_ to _enhancement_ (same as the issue).
  - You may ignore the _Milestone_ and _Projects_ settings.

### [▶️](https://www.youtube.com/watch?v=I39HubC7qkw&t=0s&list=PL0s90BggiDzzsLwhp49qf6brCsvUkLUmT&index=9) 2.5. Step 5: Review/Revise/Accept the Pull Request

- Your team must select another team member to serve as reviewer for your pull request. The reviewer must test it to make sure that it works and confirm that it can be fast-forward merged with the `master` branch. They must post comments or change requests if they find issues.
- To test the code, the reviewer can pull the branch to their local repository and check it out using these commands (assuming that the topic branch is named `iss3`):
  - `git fetch origin`
  - `git checkout -b iss3 origin/iss3`
- If changes are needed, you should make them to your working copy and push them to GitHub (all while on the topic branch). The pull request will be automatically updated to reflect the changes. You will probably also want to reply to the comment in the pull request, so the reviewer is notified of what's happened.
- Once the reviewer approves the change, they should also merge it into the `master` branch.
- If other PRs are merged into the `master` branch before yours is, you will need to merge those changes into your topic branch before your PR can be merged.

### 2.6. Fixing Bugs after a PR Has Been Accepted/Merged

- If a buggy PR is accidentally accepted, to correct the bug, you will need to follow steps 1–5 above, but with some small differences. That is, you will need to create an issue for your bug and a PR for your hotfix, and the PR will need to be reviewed and accepted as described above.
- For bug fixes, the above task steps are changed only as follows:
  - In step 1, the issue title must begin with `Bug:` and be followed by a brief description of the bug. For example, an acceptable title might be `Bug: Missing test for numericality validation in Homework 5, Task 3`.
  - In steps 1 and 4, both the issue and PR _Labels_ must be set to _bug_.

## 3. Submitting Your Team's Work

### 3.1 Step 1: Create a Release for the Team's Homework Submission

- Once all team members tasks have been completed and their PRs have been merged into the `master` branch, your team must create a release for the homework. From the GitHub repo page, one team member must follow the "releases" link and create a new release.
  - Set _Tag version_ to `hw5v1` (replacing the `5` with the number of the homework assignment). If changes (e.g., bug fixes) are made to the release after it is created, you can create a new release that includes the changes—just be sure to increment the version (e.g., `hw5v2`).
  - Set _Target_ to the appropriate commit. If it's the latest commit on the `master` branch, you may select `master`. However, if you want to be sure the correct commit is tagged, you can select it from the _Recent Commits_ menu.
  - Set _Release title_ to `Homework 5, version 1` (replacing the `5` with the number of the homework and `1` with the appropriate version of the release).

### 3.2 Step 2: Submit to Dropbox

- As the last step, your team must submit the URL of the release page to the appropriate eCourseware dropbox. Only one team member needs to perform this step. As mentioned in Step 6, if you need to correct a release, don't forget to resubmit the URL as well to reflect the correct version.
