# Creating pull requests

In order to contribute code and changes to Hercules, you need to create a pull request. This guide explains the recommended way to prepare and submit pull requests. For more details on contributing to Hercules, please see [CONTRIBUTING.md](https://github.com/HerculesWS/Hercules/blob/master/CONTRIBUTING.md) in the repository.

The guide assumes that you have at least a basic familiarity with Git and with the command line. You can probably do all the listed operation with any Git GUI (SourceTree, GitKraken, etc), but the command line is often less ambiguous and harder to get wrong. And it's the same on every operating system.
When in an instruction you see something similar to `% foo bar`, it means that you have to type the command `foo bar` in your git-enabled shell and press return.

## Prepare your fork for contributing (only the first time)

These steps are only needed the first time you want to create a pull request against Hercules.

1. Fork the project. You can do that by clicking the Fork button in any of the Hercules' GitHub pages.
2. Clone your fork's repository on your local hard drive. `% git clone YOUR_FORK'S_URL` (replace `YOUR_FORK'S_URL` with the clone URL you can find on your fork's GitHub page).

## Prepare your fork for contributing (if you already have a fork)

These steps are needed when you create new pull requests, but you already followed the above steps already once (starting from the second pull request you want to submit). They assume that you NEVER made any commits on the master branch of your fork. If you have, please consider forking again.

All the following commands are to be executed from inside the working copy folder.

1. If you haven't yet, add Hercules as a remote on your working copy (only do this once per working copy. If you delete and clone again the working copy, you need to repeat this operation). `% git remote add hercules https://github.com/HerculesWS/Hercules.git`.
2. Fetch the latest changes from Hercules `% git fetch hercules`
3. Check out your master branch `% git checkout master`
3. Integrate the Hercules changes into your master branch `% git merge --ff-only hercules/master`

## Create the pull request

All the following commands are to be executed from inside the working copy folder.

1. Create a branch for your pull request. Remember that GitHub's pull requests are bound to a branch, so you should create a new branch for each pull request you want to submit (and only delete it after the pull request was merged or rejected). Please choose a suitable name. `% git checkout -b BRANCH-NAME-HERE`
2. Push the empty branch (and associate it to the corresponding branch on the GitHub repository) `% git push --set-upstream origin BRANCH-NAME-HERE`
3. Make your commits, like you normally would
4. Push the changes to GitHub `% git push`
5. Create a pull request using the GitHub web interface
6. In case you need to push more commits (for example after code review), repeat steps 4 and 5.

## Rebase a pull request

It can happen that a change in the Hercules repository breaks the pull request, or if you simply want to update the pull request to target the latest version of Hercules, you'll need to rebase it. Beware of many guides found on the internet, suggesting to merge the upstream change: we don't do that. Our pull request workflow is based on rebasing rather than merging, where possible, in order to have a cleaner history.

1. Fetch the latest changes from Hercules `% git fetch hercules`
2. Check out your pull request's branch `% git checkout BRANCH-NAME-HERE`
3. Start the rebase.
  - If you just want to rebase (update to latest Hercules), without squashing or applying fixups, you can do a simple rebase. `% git rebase hercules/master`
  - If you want to apply a fixup, or to squash your commits ("merge" multiple commits into one), or to reorder them, or to reword their commit message, you need an interactive rebase `% git rebase -i hercules/master`. Your favorite text editor will open, with the list of commits in your branch, and some instructions. Once you save and exit your editor, the rebase will begin.
4. If a conflict occurs, fix it (this is the same as when a merge conflict happens) with your favorite text editor or diff/merge tool, then continue the rebase (note: do NOT use 'git commit' here, but only `% git add file-name-here`). `% git rebase --continue`
5. Once the rebase is complete, you need to push the changes, overwriting the current commits on GitHub's servers. This is called a force-push. `% git push --force origin BRANCH-NAME-HERE`
