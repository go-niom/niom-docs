# Contributing to Niom

Contributing to NIOM is fairly easy. This document shows you how to get started

Please note: we have a [code of conduct](https://github.com/go-niom/niom/blob/master/CODE_OF_CONDUCT.md), please follow it in all your interactions with the `Niom` project.

### Pull Requests or Commits
Titles always we must use prefixes according to below:

> 🚀 Feature, ♻️ Refactor, 🩹 Fix, 🧹 Cleanup 📚 Doc
- 🚀 Feature: Added command
- ♻️ Refactor: Update function or renamed file
- 🩹 Fix: Improve flow
- 🧹 Cleanup: Code Cleanup
- 📚 Doc: Translate to Portuguese middleware redirect

All pull request that contains a feature or fix is mandatory to have unit tests. Your PR is only to be merged if you respect this flow.

###  Submitting a Pull Request (PR)
Before you submit your Pull Request (PR) consider the following guidelines:

1. Search [GitHub Pull Requests][gh_prs] for an open or closed PR
   that relates to your submission. You don't want to duplicate effort.
1. Fork this repository.
   - https://github.com/lmas3009/cleandocs-template

1. Make your changes in a new git branch:

   ```shell
   git checkout -b BRANCH_NAME
   ```

1. Create your patch, **including appropriate test cases**.
1. Follow our [Coding Rules](#rules).

1. Commit your changes using a descriptive commit message that follows our commit message conventions. Adherence to these conventions
   is necessary because release notes are automatically generated from these messages.

   ```shell
   git commit -a
   ```

   Note: the optional commit `-a` command line option will automatically "add" and "rm" edited files.

1. Push your branch to GitHub:

   ```shell
   git push origin BRANCH_NAME
   ```

1. In GitHub, send a pull request to `niom:master`.

- If we suggest changes then:

  - Make the required updates.

  - Rebase your branch and force push to your GitHub repository (this will update your Pull Request):

    ```shell
    git rebase master -i
    git push -f
    ```

That's it! Thank you for your contribution!

#### After your pull request is merged

After your pull request is merged, you can safely delete your branch and pull the changes
from the main (upstream) repository:

- Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:

  ```shell
  git push origin --delete my-fix-branch
  ```

- Check out the master branch:

  ```shell
  git checkout master -f
  ```

- Delete the local branch:

  ```shell
  git branch -D my-fix-branch
  ```

- Update your master with the latest upstream version:

  ```shell
  git pull --ff upstream master
  ```

If you follow these instructions, your PR will land pretty safely in the main repo!