## Common Git commands

| COMMAND             | NOTES                                                                                        |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git command --help  | Eg: git rm --help; git config --help                                                         |
| git clone [repoUrl] | to clone a repo                                                                              |
| git fetch origin    | to update branches information in local; get data without merge                              |
| git pull            | fetches and merges data from remote branch for the current branch. eg git pull origin master |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git branch                                       | list all the local branches              |
| git branch -r                                    | list all the remote branches         |
| git branch -a                                    | list all the branches(local and remote)    |
| git branch [branchName]                          | Just create the branch and not switch to it    |
| git branch -d [branchname]                       | to delete a local branch; The -D option is an alias for --delete --force, which deletes the branch "irrespective of its merged status."<br> [https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely](https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely)   |
| git branch -v                                    | List all branches with last commit    |
| git branch --merged / --no-merged              | The useful --merged and --no-merged options can filter this list to branches that you have or have not yet merged into the branch you’re currently on. |
| git branch -vv                                   | See what tracking branches you have set up |
| git checkout dev                                 | to check out a branch, sets local directory to the specific branch, dev     |
| git checkout -b dev                              | creates local branch, dev and switches to it     |
| git checkout -b C A                              | create new branch C from A   |
| git checkout --track -b git-test origin/git-test | checkout a new branch such that it tracks the remote branch as well.<br>[https://stackoverflow.com/questions/4878249/how-do-i-change-the-remote-a-git-branch-is-tracking](https://stackoverflow.com/questions/4878249/how-do-i-change-the-remote-a-git-branch-is-tracking)<br> [https://stackoverflow.com/questions/10002239/difference-between-git-checkout-track-origin-branch-and-git-checkout-b-branch](https://stackoverflow.com/questions/10002239/difference-between-git-checkout-track-origin-branch-and-git-checkout-b-branch) |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git status                   | find and shows status of a branch                                                                                                          |
| git add [Specific item]      | Use -r \*.\* instead (recurse all files). Eg: git add .                                                                                    |
| git add --all                | Use git add --all even better, it also removes files that you removed from the repo                                                        |
| git rm                       |                                                                                                                                            |
| git diff                     | shows difference; what you have changed but not staged yet                                                                                 |
| git diff  --staged          | shows difference; show what staged will go to your next commit                                                                             |
| git diff commit1 commit2     | show difference; See difference of commit. Ex. git diff  7e7a43186a745cd28844328cb4cc6c0ff21c8618 e2387b252e5f27f4587f5891a32a0795abd0e859 |
| git diff origin/master..HEAD | see difference of local commit vs origin                                                                                                   |
| git diff dev origin/dev      |                                                                                                                                            |
| git merge hotfix             | merge hotfix branch with current branch.                                                                                                   |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git checkout HEAD [file]   |                                                                                |
| git checkout -- [file]     | unmodifying a Modified File                                                    |
| git reset HEAD <file name> | unstaging a Staged File                                                        |
| git reset --hard           | reset the current branch; to ignore all local changes; it'll revert everything |
| git clean -fdx             | undo all the changes done to the current branch                                |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git tag       |     |
| git log                                      | to see the commit history log                                                                                                                                                                |
| git log -p -2                                | Show difference of commits, -2 means last 2 entry                                                                                                                                            |
| git log --stat                               | Show some abbreviated stats for each commit                                                                                                                                                  |
| git log --pretty=oneline                     | Compact each commit information to one line                                                                                                                                                  |
| git log --pretty=format:"%h - %an, %ar : %s" | Show commit with format "hash, name, time, description"                                                                                                                                      |
| git log --pretty=format:"%h %s" --graph      | Show branch merge with commits                                                                                                                                                               |
| git log --since=2.weeks                      | Limit output commit by time                                                                                                                                                                  |
| git log -Sfunction_name                      |                                                                                                                                                                                              |
| git log "ServiceMap"                         | Show commits filter by given file path                                                                                                                                                       |
| git log origin/master..HEAD                  | Show local git commits                                                                                                                                                                       |
| git log --oneline --decorate --graph --all   | Show commits in branch view                                                                                                                                                                  |
| git reflog                                   | [https://stackoverflow.com/questions/17857723/whats-the-difference-between-git-reflog-and-log](https://stackoverflow.com/questions/17857723/whats-the-difference-between-git-reflog-and-log) |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git config --list --local                          | [https://stackoverflow.com/questions/46941346/how-to-know-the-git-username-and-email-saved-during-configuration](https://stackoverflow.com/questions/46941346/how-to-know-the-git-username-and-email-saved-during-configuration) |
| git config --local user.name "abc"                 |               |
| git config --local user.email "abc@companyxyz.com" |        |
| ------------------- | -------------------------------------------------------------------------------------------- |
| git remote -v             | shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote |
| git remote show origin    | inspecting a Remote, see more information about a particular remote (eg origin)                             |
| git remote add upstream   |                                                                                                             |
| git remote get-url origin |                                                                                                             |
| git remote set-url origin |                                                                                                             |
| git remote prune origin   | to locally remove stale branches that no longer exist in the remote                                         |
| git remote update origin  |                                                                                                             |


## How to push a local Git branch to master branch

```
    git checkout master
    git pull               # to update the state to the latest remote master state
    git merge develop      # to bring changes to local master from your develop branch
    git push origin master # push current HEAD to remote master branch
```

## Rewind the master branch of the repository to a previous pushed commit
run this:
```
    git reset --hard <last sha that you want to keep>
    git push --force
```
This may have unintended consequences if, for instance, there are collaborators on your repository. But, I am sure you know what you're doing 😉 
<br>[https://stackoverflow.com/questions/69968797/how-to-undo-the-last-commit-on-github](https://stackoverflow.com/questions/69968797/how-to-undo-the-last-commit-on-github)
<br>[https://stackoverflow.com/questions/1270514/undoing-a-git-push](https://stackoverflow.com/questions/1270514/undoing-a-git-push)