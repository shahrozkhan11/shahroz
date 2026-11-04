
# Git Assignment — Answers
## Part 1
## 1. What is a terminal? How is it different from clicking through folders in a file explorer?
ans: A terminal is a text window where you type commands to control your computer. A file explorer shows folders and files as ss click in the teerminal you type the folder name instead.
##  2. Write the terminal command to:
a: ls-la
b: mkdir project
c: cd
## 3. What does the cd .. command do? What about cd ~?
ans: cd.. moves you up one folder. cd~ takes you straight to your home folder from anywhere.

##  Version control concepts
4 ans: Version control is a system that records every change made your files so you can see the history,compare versions and go back to an older one.Analogy:save points in a game.you save before a hard level and if you fail you load the old save instead of starting again.

5ans: Git is the tool installed on your computer that tracks changes. GitHub is a website that stores Git repositories online so team can share them.Yes Git works fullywithout GitHub.

6ans:
1) Pull request
2) issues
3) GitHub actions\CI-CD

7ans:A repository (repo) is a project folder together with its full change history stored in the hidden .git folder.A remote repository is a copy on a server such as GitHub which the team shares.
##  Git internals 
8ans: HEAD is a pointer that means "shahrozkhan" it points to the branch that you are currently working on. when you switch branches, HEAD moves to the other branch and your files change to match that branchs latest commit.

9ans: gitognore file lists files and folder that Git must never track such as logs,downloaded packages and secrets.

## 2.2 
6ans:Each commit should be one small,clear change.A and B were committed together because they belong together; C was a separate change.Small focused commits are easier to review,easier to undo and make the history easy to read.Split commits whenever changes are unrealated or when one part might need to be reverted on its own.

## 2.3
6ans:If someone changed the remote and i commit locally without pulling my history and the remote history have split apart.My git push would be rejected until i pull.To check before pushing,run git fetch and then git status which says if my branch is ahead of behind or has diverged from origin\main.

## Part 3 — Branching & Merging Lab
3.1
9ans:It was a fast-forward.Main had no new commits after I created the branch so Git just moved the main pointer forward to the branch's last commit and did not create a merge commit.I can tell because the merge output says Fast-forward and git log oneline graph all shows one straight line with no merge commit.

3.2 
15a)ans:Both branches changed the same file team.txt on the same line in different ways.Git cannot know which version is right,so it stops and asks me to decide. The rule:same file + same line = conflict.

B)ans:No.If the changes are on different lines, Git can combine both automatically (auto-merge).

C)ans:No. Different files never conflict.

## Part 4 — GitHub Workflow Challenge
4.1
13a)ans:A pull request is a request to merge a branch into main, with a page where teammates can read the changes, comment, and approve. We do not merge directly because main is the shared, working version: a review catches mistakes and bugs before they reach everyone, lets automated tests run and shares knowledge in the team.

B)ans:1.That the code does what the description says and works (and tests pass).
2.That the change is clear and clean: readable code, no unrelated changes, and no secrets or passwords.

C)ans:A merge commit is a new commit that joins two histories together,so the branch history stays visible in the log.A fast-forward just moves the branch pointer forward when there is nothing new on the other side; no new commit is created and the history is a straight line.

## Part 5 — Merge Conflict Scenarios
A)ans:No conflict. Ahmed changed line 10 and Sara changed line 1 of the same file. Different lines, so Git merges both changes automatically.
B)ans:No conflict. Ali edited style.css and Fatima edited app.js. Different files cannot conflict.
C)ans:Yes, a conflict, because both changed line 5 of config.py to different values. The file would look like this (the first part is the branch you merge into, the second is the branch you merge in):
HEAD 
debug = True
debug = False
feature\devb-branch
D)ans:

E)ans:Yes,it is a good practice.Pulling before you start brings in your teammates'latest changes,so you work on the up-to-date code.If you skip it,you may build on old code,your push can be rejected and you are more likely to get merge conflicts later that are harder to fix.
