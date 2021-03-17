## What Is the Difference Between Push, Pull, and Fetch?

- `git push` - sends changes from a local branch to a remote repo
- `git pull` - gets changes from a remote branch into your tracking branch and then merges them into a local branch
- `git fetch` - gets changes from a remote branch into your tracking branch but does nothing to your local branch

You might think of `git push` and `git pull` as equivalent, but this isn't entirely correct. `git push` performs a single operation while `git pull` does two. `git push` takes your current branch and checks to see whether you have connected it to a remote tracking branch. If so, git takes the changes from your current branch and pushes those changes to the remote branch. This is how you share code with a remote repository. Think of it as "making the remote branch resemble your local branch".

This operation succeeds only if the remote branch has not diverged from your local branch. That means all the commits from the remote branch are already in your local branch. If, instead, you have local changes that you have not yet pushed to the remote repository, then you need to synchronize your local branch with the remote branch. You can do this in a single operation with `git pull`, or you can use two operations, `git fetch` and `git merge`, to do the same thing.

`git fetch` takes your current branch and checks to see if there is a tracking branch. If so, git looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you need to do a merge. For example, you might do `git merge origin/master` to merge changes from a remote branch named master into your local branch. If you were to do a `git pull`, git would do a `git fetch` followed immediately by a merge.

`git pull` is often what you want to do, but occasionally you might want to use `git fetch` followed by `git merge` to make sure you understand the changes you are merging into your branch before the merge happens.
