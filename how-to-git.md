## How to Git?

### Surival guide
This is a Git surival guide I learn from [Try git](https://try.github.io).

```
mkdir try-git
cd try-git

git init

# create a test file and make some changes to it
touch octocat.txt
echo "Hello, world!" > octocat.txt

git status

git add .
# or git add -A
# option -A ensures file deletion are included

git status

git commit -m "initial commit"

git status

touch a.txt b.txt c.txt
mkdir text
cp -rf [abc].txt text

git status

# txt file in a subdir will also be added
git add '*.txt'
# or: git add -A

git commit -m "add more text files"

git log

# more infomation
git log --summary

# Commit Etiquette:
# Always keep related changes together in separate commits.

git remote
# no output

# create a repo named 'try-git' on GitHub first
# origin is the name of the remote
git remote add origin https://github.com/feici02/try-git.git

# check remotes
git remote
git remote -v

git pull origin master

# push changes to remote: origin, branch: master
# with -u, you can simply run 'git push' next time
git push -u origin master

# now, you can check this repo on GitHub.
# make some changes for octocat.txt, and then commit it on GitHub

# get above updates
git pull origin master

# make some changes to octocat.txt again locally

# HEAD point to the most recent commit
# this is to get the changes by others
git diff HEAD
# this is the same as: git diff
# the changes can be shown

git add octocat.txt
git diff
# the changes can NOT be shown

git diff --staged
# the changes can be shown

# remove file from staging area
git reset octocat.txt

# restore to last commit
# -- tells git there are no more options after it
# to discard the changes made to this file
git checkout -- octocat.txt
# this is the same as: git checkout octocat.txt

# create a new branch called clean_up
git branch clean_up

# switch to branch clean_up
git checkout clean_up

# create and switch branch in one step
# git checkout -b clean_up

# check the branches you have
# the branch with * is the current branch
git branch

# remove all the .txt files
# not only remove the actual files from disk
# directory text is removed, too
# but will also stage the removal of the files for us
git rm '*.txt'

# remove directory text only
# git rm -r text

git status
git commit -m "remove txt files"

# if the files are removed from disk manually
# auto remove files with the commit
# git commit -am "remove txt files"

# switch back to master branch
git checkout master
ls
# all .txt files are still there

# merge the clean_up branch to master
git merge clean_up

git branch
# branch clean_up are still there

# delete branch clean_up
git branch -d clean_up

git branch
# branch clean_up is gone

# above command can't delete a branch that hasn't been merged
# you can use following command instead:
# git branch -D <branch_name>
# or
# git branch -d -f <branch_name>

# push what we have done to remote
git push
```

### Resources
To dive deeper in Git, you can also refer to:
- [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- [GitHub On Demand Training](https://services.github.com/on-demand/)
- [git immersion](http://gitimmersion.com/)
- [Getting Git Right](https://www.atlassian.com/git/)
